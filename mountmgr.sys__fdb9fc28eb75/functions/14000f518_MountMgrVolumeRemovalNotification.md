# MountMgrVolumeRemovalNotification

- ea: `0x14000f518`
- end: `0x14000f679`
- name: `MountMgrVolumeRemovalNotification`
- size: `353`
- prototype: `__int64 __fastcall(__int64, IRP *, struct _IRP *MasterIrp)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x14000a050`
- `0x14000f518`

## import_xrefs

- `ntoskrnl!PsGetThreadHardErrorsAreDisabled` at `0x14000f5d4`
- `ntoskrnl!PsGetThreadHardErrorsAreDisabled` at `0x14000f5d4`
- `ntoskrnl!IofCompleteRequest` at `0x14000f65a`
- `ntoskrnl!IofCompleteRequest` at `0x14000f65a`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x14000f5ed`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x14000f616`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x14000f5ed`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x14000f616`

## pseudocode

```c
__int64 __fastcall MountMgrVolumeRemovalNotification(__int64 a1, IRP *a2, struct _IRP *MasterIrp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int Options; // edx
  int v7; // edi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  int Type; // ecx
  char ThreadHardErrorsAreDisabled; // al
  __int64 v13; // rdx
  char v14; // bl
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // rdx
  __int128 v19; // [rsp+20h] [rbp-18h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v19 = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options >= 4 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    Type = (unsigned __int16)MasterIrp->Type;
    if ( Options >= Type + 2 )
    {
      WORD1(v19) = MasterIrp->Type;
      *((_QWORD *)&v19 + 1) = &MasterIrp->Size;
      LOWORD(v19) = Type;
      ThreadHardErrorsAreDisabled = PsGetThreadHardErrorsAreDisabled(KeGetCurrentThread());
      LOBYTE(v13) = 1;
      v14 = ThreadHardErrorsAreDisabled;
      PsSetThreadHardErrorsAreDisabled(KeGetCurrentThread(), v13);
      LOBYTE(v15) = 1;
      v16 = MountMgrMountedDeviceRemoval(a1, &v19, v15);
      LOBYTE(v17) = v14;
      v7 = v16;
      PsSetThreadHardErrorsAreDisabled(KeGetCurrentThread(), v17);
      if ( v7 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v9 = 294;
          v10 = (unsigned int)v7;
          goto LABEL_14;
        }
      }
    }
    else
    {
      v7 = -1073741811;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v9 = 293;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v7 = -1073741811;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v9 = 292;
LABEL_5:
      v10 = 3221225485LL;
LABEL_14:
      WPP_SF_L(v8->AttachedDevice, v9, MasterIrp, v10);
    }
  }
  a2->IoStatus.Status = v7;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000f518  mov     [rsp+arg_0], rbx
0x14000f51d  mov     [rsp+arg_8], rsi
0x14000f522  push    rdi
0x14000f523  sub     rsp, 30h
0x14000f527  mov     rax, [rdx+0B8h]
0x14000f52e  xorps   xmm0, xmm0
0x14000f531  mov     rsi, rdx
0x14000f534  mov     rdi, rcx
0x14000f537  movups  [rsp+38h+var_18], xmm0
0x14000f53c  mov     edx, [rax+10h]
0x14000f53f  cmp     edx, 4
0x14000f542  jnb     short loc_14000F57B
0x14000f544  mov     edi, 0C000000Dh
0x14000f549  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f550  lea     rax, WPP_GLOBAL_Control
0x14000f557  cmp     rcx, rax
0x14000f55a  jz      loc_14000F652
0x14000f560  mov     eax, [rcx+2Ch]
0x14000f563  test    al, 1
0x14000f565  jz      loc_14000F652
0x14000f56b  mov     edx, 124h
0x14000f570  mov     r9d, 0C000000Dh
0x14000f576  jmp     loc_14000F649
0x14000f57b  mov     r8, [rsi+18h]
0x14000f57f  movzx   ecx, word ptr [r8]
0x14000f583  lea     eax, [rcx+2]
0x14000f586  cmp     edx, eax
0x14000f588  jnb     short loc_14000F5B8
0x14000f58a  mov     edi, 0C000000Dh
0x14000f58f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f596  lea     rax, WPP_GLOBAL_Control
0x14000f59d  cmp     rcx, rax
0x14000f5a0  jz      loc_14000F652
0x14000f5a6  mov     eax, [rcx+2Ch]
0x14000f5a9  test    al, 1
0x14000f5ab  jz      loc_14000F652
0x14000f5b1  mov     edx, 125h
0x14000f5b6  jmp     short loc_14000F570
0x14000f5b8  lea     rax, [r8+2]
0x14000f5bc  mov     word ptr [rsp+38h+var_18+2], cx
0x14000f5c1  mov     qword ptr [rsp+38h+var_18+8], rax
0x14000f5c6  mov     word ptr [rsp+38h+var_18], cx
0x14000f5cb  mov     rcx, gs:188h
0x14000f5d4  call    cs:__imp_PsGetThreadHardErrorsAreDisabled
0x14000f5db  nop     dword ptr [rax+rax+00h]
0x14000f5e0  mov     rcx, gs:188h
0x14000f5e9  mov     dl, 1
0x14000f5eb  mov     bl, al
0x14000f5ed  call    cs:__imp_PsSetThreadHardErrorsAreDisabled
0x14000f5f4  nop     dword ptr [rax+rax+00h]
0x14000f5f9  mov     r8b, 1
0x14000f5fc  lea     rdx, [rsp+38h+var_18]
0x14000f601  mov     rcx, rdi
0x14000f604  call    MountMgrMountedDeviceRemoval
0x14000f609  mov     rcx, gs:188h
0x14000f612  mov     dl, bl
0x14000f614  mov     edi, eax
0x14000f616  call    cs:__imp_PsSetThreadHardErrorsAreDisabled
0x14000f61d  nop     dword ptr [rax+rax+00h]
0x14000f622  test    edi, edi
0x14000f624  jns     short loc_14000F652
0x14000f626  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f62d  lea     rax, WPP_GLOBAL_Control
0x14000f634  cmp     rcx, rax
0x14000f637  jz      short loc_14000F652
0x14000f639  mov     edx, [rcx+2Ch]
0x14000f63c  test    dl, 1
0x14000f63f  jz      short loc_14000F652
0x14000f641  mov     edx, 126h
0x14000f646  mov     r9d, edi
0x14000f649  mov     rcx, [rcx+18h]
0x14000f64d  call    WPP_SF_L
0x14000f652  xor     edx, edx; PriorityBoost
0x14000f654  mov     [rsi+30h], edi
0x14000f657  mov     rcx, rsi; Irp
0x14000f65a  call    cs:__imp_IofCompleteRequest
0x14000f661  nop     dword ptr [rax+rax+00h]
0x14000f666  mov     rbx, [rsp+38h+arg_0]
0x14000f66b  mov     eax, edi
0x14000f66d  mov     rsi, [rsp+38h+arg_8]
0x14000f672  add     rsp, 30h
0x14000f676  pop     rdi
0x14000f677  retn
```
