# FltpCleanupDeviceObject

- ea: `0x1800682b0`
- end: `0x18006840c`
- name: `FltpCleanupDeviceObject`
- size: `348`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180066fa0`
- `0x1800674b0`
- `0x1800681e0`
- `0x180068260`
- `0x180068900`
- `0x180070c80`
- `0x180078410`

## callees

- `0x18001f1c0`
- `0x180020f28`
- `0x1800682b0`
- `0x180068e20`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x180068386`
- `ntoskrnl!ExReleaseFastMutex` at `0x180068386`
- `ntoskrnl!ExAcquireFastMutex` at `0x180068345`
- `ntoskrnl!ExAcquireFastMutex` at `0x180068345`
- `ntoskrnl!IoDeleteDevice` at `0x180068318`
- `ntoskrnl!IoDeleteDevice` at `0x180068318`
- `ntoskrnl!IoDetachDevice` at `0x1800683fb`
- `ntoskrnl!IoDetachDevice` at `0x1800683fb`

## pseudocode

```c
void __fastcall FltpCleanupDeviceObject(PDEVICE_OBJECT DeviceObject, char a2, int a3)
{
  unsigned __int16 *DeviceExtension; // rbx
  __int64 v5; // rsi
  struct _DEVICE_OBJECT *v6; // rcx
  __int64 v7; // rbp
  __int64 v8; // rcx
  char **v9; // rax
  char *v10; // rsi

  DeviceExtension = (unsigned __int16 *)DeviceObject->DeviceExtension;
  if ( DeviceExtension )
  {
    if ( *DeviceExtension == 0xF106 )
    {
      if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
        McTemplateU0sppwsd_EtwWriteTransfer(DeviceExtension[24] >> 1, a2, a3, (_DWORD)DeviceObject);
      v10 = (char *)(DeviceExtension + 12);
      if ( *((_QWORD *)DeviceExtension + 3) )
      {
        v7 = *((_QWORD *)DeviceExtension + 2);
        ExAcquireFastMutex((PFAST_MUTEX)(v7 + 344));
        *(_DWORD *)(v7 + 416) -= 2;
        v8 = *(_QWORD *)v10;
        if ( *(char **)(*(_QWORD *)v10 + 8LL) != v10 || (v9 = (char **)*((_QWORD *)DeviceExtension + 4), *v9 != v10) )
          __fastfail(3u);
        *v9 = (char *)v8;
        *(_QWORD *)(v8 + 8) = v9;
        *(_QWORD *)v10 = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(v7 + 344));
      }
    }
    else
    {
      if ( *DeviceExtension != 0xF107 )
        return;
      v5 = *((_QWORD *)DeviceExtension + 10);
      if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
        McTemplateU0sppwsdp_EtwWriteTransfer(
          61703,
          *(unsigned __int16 *)(v5 + 112) >> 1,
          a3,
          (_DWORD)DeviceObject,
          v5,
          *(_WORD *)(v5 + 112) >> 1,
          *(_QWORD *)(v5 + 120));
      FltpFreeVolume((char *)v5);
    }
    v6 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 1);
    if ( v6 )
      IoDetachDevice(v6);
    IoDeleteDevice(DeviceObject);
  }
}

```

## disassembly

```asm
0x1800682b0  mov     [rsp+arg_8], rbx
0x1800682b5  mov     [rsp+arg_10], rbp
0x1800682ba  push    rdi
0x1800682bb  sub     rsp, 50h
0x1800682bf  mov     rbx, [rcx+40h]
0x1800682c3  mov     ebp, edx
0x1800682c5  mov     rdi, rcx
0x1800682c8  test    rbx, rbx
0x1800682cb  jz      short loc_180068329
0x1800682cd  movzx   eax, word ptr [rbx]
0x1800682d0  mov     ecx, 0F106h
0x1800682d5  mov     [rsp+58h+arg_0], rsi
0x1800682da  cmp     ax, cx
0x1800682dd  jz      loc_180068397
0x1800682e3  mov     ecx, 0F107h
0x1800682e8  cmp     ax, cx
0x1800682eb  jnz     short loc_180068324
0x1800682ed  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x1800682f4  mov     rsi, [rbx+50h]
0x1800682f8  jnz     loc_1800683C9
0x1800682fe  mov     edx, ebp
0x180068300  mov     rcx, rsi; OwnerId
0x180068303  call    FltpFreeVolume
0x180068308  mov     rcx, [rbx+8]; TargetDevice
0x18006830c  test    rcx, rcx
0x18006830f  jnz     loc_1800683FB
0x180068315  mov     rcx, rdi; DeviceObject
0x180068318  call    cs:__imp_IoDeleteDevice
0x18006831f  nop     dword ptr [rax+rax+00h]
0x180068324  mov     rsi, [rsp+58h+arg_0]
0x180068329  mov     rbx, [rsp+58h+arg_8]
0x18006832e  mov     rbp, [rsp+58h+arg_10]
0x180068333  add     rsp, 50h
0x180068337  pop     rdi
0x180068338  retn
0x18006833a  mov     rbp, [rbx+10h]
0x18006833e  lea     rcx, [rbp+158h]; FastMutex
0x180068345  call    cs:__imp_ExAcquireFastMutex
0x18006834c  nop     dword ptr [rax+rax+00h]
0x180068351  add     dword ptr [rbp+1A0h], 0FFFFFFFEh
0x180068358  mov     rcx, [rsi]
0x18006835b  cmp     [rcx+8], rsi
0x18006835f  jnz     short loc_18006836A
0x180068361  mov     rax, [rsi+8]
0x180068365  cmp     [rax], rsi
0x180068368  jz      short loc_180068371
0x18006836a  mov     ecx, 3
0x18006836f  int     29h; Win8: RtlFailFast(ecx)
0x180068371  mov     [rax], rcx
0x180068374  mov     [rcx+8], rax
0x180068378  lea     rcx, [rbp+158h]; FastMutex
0x18006837f  mov     qword ptr [rsi], 0
0x180068386  call    cs:__imp_ExReleaseFastMutex
0x18006838d  nop     dword ptr [rax+rax+00h]
0x180068392  jmp     loc_180068308
0x180068397  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x18006839e  jz      loc_18007A558
0x1800683a4  movzx   ecx, word ptr [rbx+30h]
0x1800683a8  mov     r9, rdi
0x1800683ab  mov     rax, [rbx+38h]
0x1800683af  shr     ecx, 1
0x1800683b1  mov     [rsp+58h+var_18], ebp
0x1800683b5  mov     [rsp+58h+var_28], rax
0x1800683ba  mov     [rsp+58h+var_30], ecx
0x1800683be  call    McTemplateU0sppwsd_EtwWriteTransfer
0x1800683c3  nop
0x1800683c4  jmp     loc_18007A558
0x1800683c9  mov     rax, [rbx+8]
0x1800683cd  mov     r9, rdi
0x1800683d0  movzx   edx, word ptr [rsi+70h]
0x1800683d4  mov     [rsp+58h+var_10], rax
0x1800683d9  mov     rax, [rsi+78h]
0x1800683dd  mov     [rsp+58h+var_18], ebp
0x1800683e1  mov     [rsp+58h+var_28], rax
0x1800683e6  shr     edx, 1
0x1800683e8  mov     [rsp+58h+var_30], edx
0x1800683ec  mov     [rsp+58h+var_38], rsi
0x1800683f1  call    McTemplateU0sppwsdp_EtwWriteTransfer
0x1800683f6  jmp     loc_1800682FE
0x1800683fb  call    cs:__imp_IoDetachDevice
0x180068402  nop     dword ptr [rax+rax+00h]
0x180068407  jmp     loc_180068315
0x18007a558  mov     rax, [rbx+18h]
0x18007a55c  lea     rsi, [rbx+18h]
0x18007a560  test    rax, rax
0x18007a563  jz      loc_180068308
0x18007a569  jmp     loc_18006833A
```
