# MountMgrVolumeArrivalNotification

- ea: `0x14000d9a0`
- end: `0x14000db4d`
- name: `MountMgrVolumeArrivalNotification`
- size: `429`
- prototype: `__int64 __fastcall(__int64, IRP *, struct _IRP *MasterIrp)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x14000d9a0`
- `0x140014fc0`
- `0x140017fc0`

## import_xrefs

- `ntoskrnl!PsGetThreadHardErrorsAreDisabled` at `0x14000da6e`
- `ntoskrnl!PsGetThreadHardErrorsAreDisabled` at `0x14000da6e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dac0`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dad0`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dac0`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dad0`
- `ntoskrnl!IofCompleteRequest` at `0x14000db2b`
- `ntoskrnl!IofCompleteRequest` at `0x14000db2b`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x14000da88`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x14000dae8`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x14000da88`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x14000dae8`

## pseudocode

```c
__int64 __fastcall MountMgrVolumeArrivalNotification(__int64 a1, IRP *a2, struct _IRP *MasterIrp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int Options; // edx
  int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  int Type; // ecx
  char ThreadHardErrorsAreDisabled; // al
  __int64 v13; // rdx
  char v14; // r14
  __int64 v15; // rdx
  __int64 v16; // r8
  __int128 v18; // [rsp+20h] [rbp-10h] BYREF
  PVOID Object; // [rsp+58h] [rbp+28h] BYREF
  PVOID v20; // [rsp+60h] [rbp+30h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v20 = 0;
  v18 = 0;
  Object = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options >= 4 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    Type = (unsigned __int16)MasterIrp->Type;
    if ( Options >= Type + 2 )
    {
      WORD1(v18) = MasterIrp->Type;
      *((_QWORD *)&v18 + 1) = &MasterIrp->Size;
      LOWORD(v18) = Type;
      ThreadHardErrorsAreDisabled = PsGetThreadHardErrorsAreDisabled(KeGetCurrentThread());
      LOBYTE(v13) = 1;
      v14 = ThreadHardErrorsAreDisabled;
      PsSetThreadHardErrorsAreDisabled(KeGetCurrentThread(), v13);
      v7 = OpenDevice(&v18, &v20, &Object);
      if ( v7 >= 0 )
      {
        LOBYTE(v16) = 1;
        v7 = MountMgrMountedDeviceArrival(a1, &v18, v16);
        ObfDereferenceObject(Object);
        ObfDereferenceObject(v20);
      }
      LOBYTE(v15) = v14;
      PsSetThreadHardErrorsAreDisabled(KeGetCurrentThread(), v15);
      if ( v7 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v9 = 297;
          v10 = (unsigned int)v7;
          goto LABEL_16;
        }
      }
    }
    else
    {
      v7 = -1073741811;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v9 = 296;
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
      v9 = 295;
LABEL_5:
      v10 = 3221225485LL;
LABEL_16:
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
0x14000d9a0  mov     [rsp-18h+arg_0], rbx
0x14000d9a5  mov     [rsp-18h+arg_18], rsi
0x14000d9aa  push    rbp
0x14000d9ab  push    rdi
0x14000d9ac  push    r14
0x14000d9ae  mov     rbp, rsp
0x14000d9b1  sub     rsp, 30h
0x14000d9b5  mov     rax, [rdx+0B8h]
0x14000d9bc  xorps   xmm0, xmm0
0x14000d9bf  mov     rdi, rdx
0x14000d9c2  mov     [rbp+arg_10], 0
0x14000d9ca  movups  [rbp+var_10], xmm0
0x14000d9ce  mov     rsi, rcx
0x14000d9d1  mov     [rbp+Object], 0
0x14000d9d9  mov     edx, [rax+10h]
0x14000d9dc  cmp     edx, 4
0x14000d9df  jnb     short loc_14000DA18
0x14000d9e1  mov     ebx, 0C000000Dh
0x14000d9e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9ed  lea     rax, WPP_GLOBAL_Control
0x14000d9f4  cmp     rcx, rax
0x14000d9f7  jz      loc_14000DB23
0x14000d9fd  mov     eax, [rcx+2Ch]
0x14000da00  test    al, 1
0x14000da02  jz      loc_14000DB23
0x14000da08  mov     edx, 127h
0x14000da0d  mov     r9d, 0C000000Dh
0x14000da13  jmp     loc_14000DB1A
0x14000da18  mov     r8, [rdi+18h]
0x14000da1c  movzx   ecx, word ptr [r8]
0x14000da20  lea     eax, [rcx+2]
0x14000da23  cmp     edx, eax
0x14000da25  jnb     short loc_14000DA55
0x14000da27  mov     ebx, 0C000000Dh
0x14000da2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da33  lea     rax, WPP_GLOBAL_Control
0x14000da3a  cmp     rcx, rax
0x14000da3d  jz      loc_14000DB23
0x14000da43  mov     eax, [rcx+2Ch]
0x14000da46  test    al, 1
0x14000da48  jz      loc_14000DB23
0x14000da4e  mov     edx, 128h
0x14000da53  jmp     short loc_14000DA0D
0x14000da55  lea     rax, [r8+2]
0x14000da59  mov     word ptr [rbp+var_10+2], cx
0x14000da5d  mov     qword ptr [rbp+var_10+8], rax
0x14000da61  mov     word ptr [rbp+var_10], cx
0x14000da65  mov     rcx, gs:188h
0x14000da6e  call    cs:__imp_PsGetThreadHardErrorsAreDisabled
0x14000da75  nop     dword ptr [rax+rax+00h]
0x14000da7a  mov     rcx, gs:188h
0x14000da83  mov     dl, 1
0x14000da85  mov     r14b, al
0x14000da88  call    cs:__imp_PsSetThreadHardErrorsAreDisabled
0x14000da8f  nop     dword ptr [rax+rax+00h]
0x14000da94  lea     r8, [rbp+Object]
0x14000da98  lea     rdx, [rbp+arg_10]
0x14000da9c  lea     rcx, [rbp+var_10]
0x14000daa0  call    OpenDevice
0x14000daa5  mov     ebx, eax
0x14000daa7  test    eax, eax
0x14000daa9  js      short loc_14000DADC
0x14000daab  mov     r8b, 1
0x14000daae  lea     rdx, [rbp+var_10]
0x14000dab2  mov     rcx, rsi
0x14000dab5  call    MountMgrMountedDeviceArrival
0x14000daba  mov     rcx, [rbp+Object]; Object
0x14000dabe  mov     ebx, eax
0x14000dac0  call    cs:__imp_ObfDereferenceObject
0x14000dac7  nop     dword ptr [rax+rax+00h]
0x14000dacc  mov     rcx, [rbp+arg_10]; Object
0x14000dad0  call    cs:__imp_ObfDereferenceObject
0x14000dad7  nop     dword ptr [rax+rax+00h]
0x14000dadc  mov     rcx, gs:188h
0x14000dae5  mov     dl, r14b
0x14000dae8  call    cs:__imp_PsSetThreadHardErrorsAreDisabled
0x14000daef  nop     dword ptr [rax+rax+00h]
0x14000daf4  test    ebx, ebx
0x14000daf6  jns     short loc_14000DB23
0x14000daf8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000daff  lea     rax, WPP_GLOBAL_Control
0x14000db06  cmp     rcx, rax
0x14000db09  jz      short loc_14000DB23
0x14000db0b  mov     eax, [rcx+2Ch]
0x14000db0e  test    al, 1
0x14000db10  jz      short loc_14000DB23
0x14000db12  mov     edx, 129h
0x14000db17  mov     r9d, ebx
0x14000db1a  mov     rcx, [rcx+18h]
0x14000db1e  call    WPP_SF_L
0x14000db23  xor     edx, edx; PriorityBoost
0x14000db25  mov     [rdi+30h], ebx
0x14000db28  mov     rcx, rdi; Irp
0x14000db2b  call    cs:__imp_IofCompleteRequest
0x14000db32  nop     dword ptr [rax+rax+00h]
0x14000db37  mov     rsi, [rsp+30h+arg_18]
0x14000db3c  mov     eax, ebx
0x14000db3e  mov     rbx, [rsp+30h+arg_0]
0x14000db43  add     rsp, 30h
0x14000db47  pop     r14
0x14000db49  pop     rdi
0x14000db4a  pop     rbp
0x14000db4b  retn
```
