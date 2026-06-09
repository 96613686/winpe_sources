# ClassShutdownFlush

- ea: `0x1400171d0`
- end: `0x140017392`
- name: `ClassShutdownFlush`
- size: `450`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x1400171d0`
- `0x14001fbf4`
- `0x14003e470`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400172d8`
- `ntoskrnl!IofCallDriver` at `0x1400172d8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140017216`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140017216`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140017285`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140017285`

## pseudocode

```c
NTSTATUS __fastcall ClassShutdownFlush(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  void *DeviceExtension; // rdi
  struct _DEVICE_OBJECT *v5; // rcx
  volatile signed __int32 **v6; // rsi
  __int64 (__fastcall *v7)(PDEVICE_OBJECT, PIRP); // rax
  _DWORD **v9; // r8
  signed __int32 v10; // eax
  signed __int32 v11; // ett

  DeviceExtension = DeviceObject->DeviceExtension;
  if ( (*((_BYTE *)DeviceExtension + 104) & 1) != 0
    && (v5 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 2), (*((_WORD *)DeviceExtension + 320) & 0x40) != 0)
    && *(_DWORD *)(*((_QWORD *)DeviceExtension + 65) + 28LL) == 16 )
  {
    ++Irp->CurrentLocation;
    ++Irp->Tail.Overlay.CurrentStackLocation;
    return IofCallDriver(v5, Irp);
  }
  else
  {
    v6 = (volatile signed __int32 **)DeviceObject->DeviceExtension;
    if ( !ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v6[55] + 2)) )
    {
      _InterlockedIncrement(v6[55]);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_a22cc05f221e30b8049471910da99059_Traceguids,
          *(unsigned int *)v6[55]);
      }
    }
    if ( *((_DWORD *)v6 + 27) )
    {
      v9 = (_DWORD **)DeviceObject->DeviceExtension;
      v10 = *v9[55];
      if ( v10 )
      {
        while ( 1 )
        {
          v11 = v10;
          v10 = _InterlockedCompareExchange(v9[55], v10 - 1, v10);
          if ( v11 == v10 )
            break;
          if ( !v10 )
            goto LABEL_8;
        }
      }
      else
      {
LABEL_8:
        ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v9[55] + 2));
      }
      Irp->IoStatus.Status = -1073741632;
      ClassCompleteRequest(DeviceObject, Irp, 0);
      return -1073741632;
    }
    else
    {
      v7 = *(__int64 (__fastcall **)(PDEVICE_OBJECT, PIRP))(*((_QWORD *)DeviceExtension + 20) + 40LL);
      if ( v7 )
      {
        return v7(DeviceObject, Irp);
      }
      else
      {
        Irp->IoStatus.Status = -1073741808;
        ClassReleaseRemoveLock(DeviceObject, Irp);
        ClassCompleteRequest(DeviceObject, Irp, 0);
        return -1073741808;
      }
    }
  }
}

```

## disassembly

```asm
0x1400171d0  mov     [rsp+arg_8], rbx
0x1400171d5  mov     [rsp+arg_10], rbp
0x1400171da  push    rdi
0x1400171db  sub     rsp, 20h
0x1400171df  mov     rdi, [rcx+40h]
0x1400171e3  mov     rbp, rdx
0x1400171e6  mov     rbx, rcx
0x1400171e9  test    byte ptr [rdi+68h], 1
0x1400171ed  jz      short loc_140017202
0x1400171ef  movzx   eax, word ptr [rdi+280h]
0x1400171f6  mov     rcx, [rdi+10h]; DeviceObject
0x1400171fa  test    al, 40h
0x1400171fc  jnz     loc_1400172BC
0x140017202  mov     [rsp+28h+arg_0], rsi
0x140017207  mov     rsi, [rbx+40h]
0x14001720b  mov     rcx, [rsi+1B8h]
0x140017212  add     rcx, 8; RunRefCacheAware
0x140017216  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14001721d  nop     dword ptr [rax+rax+00h]
0x140017222  test    al, al
0x140017224  jz      loc_1400172F5
0x14001722a  cmp     dword ptr [rsi+6Ch], 0
0x14001722e  mov     rsi, [rsp+28h+arg_0]
0x140017233  jnz     short loc_140017265
0x140017235  mov     rax, [rdi+0A0h]
0x14001723c  mov     rdx, rbp; Tag
0x14001723f  mov     rcx, rbx; DeviceObject
0x140017242  mov     rax, [rax+28h]
0x140017246  test    rax, rax
0x140017249  jz      loc_14001736E
0x14001724f  call    _guard_dispatch_icall
0x140017254  mov     rbx, [rsp+28h+arg_8]
0x140017259  mov     rbp, [rsp+28h+arg_10]
0x14001725e  add     rsp, 20h
0x140017262  pop     rdi
0x140017263  retn
0x140017265  mov     r8, [rbx+40h]
0x140017269  mov     rax, [r8+1B8h]
0x140017270  mov     eax, [rax]
0x140017272  test    eax, eax
0x140017274  jnz     loc_140017351
0x14001727a  mov     rcx, [r8+1B8h]
0x140017281  add     rcx, 8; RunRefCacheAware
0x140017285  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14001728c  nop     dword ptr [rax+rax+00h]
0x140017291  xor     r8d, r8d; PriorityBoost
0x140017294  mov     dword ptr [rbp+30h], 0C00000C0h
0x14001729b  mov     rdx, rbp; Irp
0x14001729e  mov     rcx, rbx; DeviceObject
0x1400172a1  call    ClassCompleteRequest
0x1400172a6  mov     eax, 0C00000C0h
0x1400172ab  mov     rbx, [rsp+28h+arg_8]
0x1400172b0  mov     rbp, [rsp+28h+arg_10]
0x1400172b5  add     rsp, 20h
0x1400172b9  pop     rdi
0x1400172ba  retn
0x1400172bc  mov     rax, [rdi+208h]
0x1400172c3  cmp     dword ptr [rax+1Ch], 10h
0x1400172c7  jnz     loc_140017202
0x1400172cd  inc     byte ptr [rdx+43h]
0x1400172d0  add     qword ptr [rdx+0B8h], 48h ; 'H'
0x1400172d8  call    cs:__imp_IofCallDriver
0x1400172df  nop     dword ptr [rax+rax+00h]
0x1400172e4  mov     rbx, [rsp+28h+arg_8]
0x1400172e9  mov     rbp, [rsp+28h+arg_10]
0x1400172ee  add     rsp, 20h
0x1400172f2  pop     rdi
0x1400172f3  retn
0x1400172f5  mov     rax, [rsi+1B8h]
0x1400172fc  lock inc dword ptr [rax]
0x1400172ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140017306  lea     rax, WPP_GLOBAL_Control
0x14001730d  cmp     rcx, rax
0x140017310  jz      loc_14001722A
0x140017316  test    dword ptr [rcx+2Ch], 200h
0x14001731d  jz      loc_14001722A
0x140017323  cmp     byte ptr [rcx+29h], 5
0x140017327  jb      loc_14001722A
0x14001732d  mov     r9, [rsi+1B8h]
0x140017334  lea     r8, WPP_a22cc05f221e30b8049471910da99059_Traceguids
0x14001733b  mov     rcx, [rcx+18h]
0x14001733f  mov     edx, 0Eh
0x140017344  mov     r9d, [r9]
0x140017347  call    WPP_SF_d
0x14001734c  jmp     loc_14001722A
0x140017351  mov     rcx, [r8+1B8h]
0x140017358  lea     edx, [rax-1]
0x14001735b  lock cmpxchg [rcx], edx
0x14001735f  jz      loc_140017291
0x140017365  test    eax, eax
0x140017367  jnz     short loc_140017351
0x140017369  jmp     loc_14001727A
0x14001736e  mov     dword ptr [rbp+30h], 0C0000010h
0x140017375  call    ClassReleaseRemoveLock
0x14001737a  xor     r8d, r8d; PriorityBoost
0x14001737d  mov     rdx, rbp; Irp
0x140017380  mov     rcx, rbx; DeviceObject
0x140017383  call    ClassCompleteRequest
0x140017388  mov     eax, 0C0000010h
0x14001738d  jmp     loc_140017254
```
