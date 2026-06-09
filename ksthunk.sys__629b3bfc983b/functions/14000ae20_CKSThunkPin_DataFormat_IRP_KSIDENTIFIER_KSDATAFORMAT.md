# CKSThunkPin::DataFormat(_IRP *,KSIDENTIFIER *,KSDATAFORMAT *)

- ea: `0x14000ae20`
- end: `0x14000aed1`
- name: `?DataFormat@CKSThunkPin@@UEAAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEATKSDATAFORMAT@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CKSThunkPin *this, struct _IRP *, struct KSIDENTIFIER *, union KSDATAFORMAT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140003770`
- `0x14000a5e0`
- `0x14000ae20`
- `0x14000af44`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000ae59`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ae59`
- `ntoskrnl!KeReleaseMutex` at `0x14000aeb0`
- `ntoskrnl!KeReleaseMutex` at `0x14000aeb0`

## pseudocode

```c
__int64 __fastcall CKSThunkPin::DataFormat(
        CKSThunkPin *this,
        struct _IRP *a2,
        struct KSIDENTIFIER *a3,
        union KSDATAFORMAT *a4)
{
  CKSThunkPin *v8; // rcx
  struct IKsWOW64FormatThunk *FormatHandler; // rsi
  int v10; // ebx
  __int64 v11; // rcx

  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 0x40 )
  {
    return (unsigned int)-1073741275;
  }
  else
  {
    KeWaitForSingleObject((char *)this + 8, Executive, 0, 0, 0);
    if ( (a3->Flags & 2) != 0 && (FormatHandler = CKSThunkPin::LocateFormatHandler(v8, a4)) != 0 )
    {
      v10 = CKernelFilterDevice::SynchronousForwardIrp(*((CKernelFilterDevice **)this - 1), a2);
      if ( v10 >= 0 )
      {
        v11 = *((_QWORD *)this + 8);
        *((_QWORD *)this + 8) = FormatHandler;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    else
    {
      v10 = -1073741275;
    }
    KeReleaseMutex((PRKMUTEX)((char *)this + 8), 0);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000ae20  push    rbx
0x14000ae22  push    rbp
0x14000ae23  push    rsi
0x14000ae24  push    rdi
0x14000ae25  push    r14
0x14000ae27  sub     rsp, 30h
0x14000ae2b  mov     rax, [rdx+0B8h]
0x14000ae32  mov     rsi, r9
0x14000ae35  mov     r14, r8
0x14000ae38  mov     rbx, rdx
0x14000ae3b  mov     rdi, rcx
0x14000ae3e  cmp     dword ptr [rax+8], 40h ; '@'
0x14000ae42  jb      short loc_14000AEBE
0x14000ae44  xor     r9d, r9d; Alertable
0x14000ae47  mov     [rsp+58h+Timeout], 0; Timeout
0x14000ae50  xor     r8d, r8d; WaitMode
0x14000ae53  xor     edx, edx; WaitReason
0x14000ae55  add     rcx, 8; Object
0x14000ae59  call    cs:__imp_KeWaitForSingleObject
0x14000ae60  nop     dword ptr [rax+rax+00h]
0x14000ae65  mov     eax, [r14+14h]
0x14000ae69  test    al, 2
0x14000ae6b  jz      short loc_14000AEA5
0x14000ae6d  mov     rdx, rsi; union KSDATAFORMAT *
0x14000ae70  call    ?LocateFormatHandler@CKSThunkPin@@QEAAPEAUIKsWOW64FormatThunk@@PEATKSDATAFORMAT@@@Z; CKSThunkPin::LocateFormatHandler(KSDATAFORMAT *)
0x14000ae75  mov     rsi, rax
0x14000ae78  test    rax, rax
0x14000ae7b  jz      short loc_14000AEA5
0x14000ae7d  mov     rcx, [rdi-8]; this
0x14000ae81  mov     rdx, rbx; struct _IRP *
0x14000ae84  call    ?SynchronousForwardIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@@Z; CKernelFilterDevice::SynchronousForwardIrp(_IRP *)
0x14000ae89  mov     ebx, eax
0x14000ae8b  test    eax, eax
0x14000ae8d  js      short loc_14000AEAA
0x14000ae8f  mov     rcx, [rdi+40h]
0x14000ae93  mov     [rdi+40h], rsi
0x14000ae97  mov     rdx, [rcx]
0x14000ae9a  mov     rax, [rdx+10h]
0x14000ae9e  call    _guard_dispatch_icall
0x14000aea3  jmp     short loc_14000AEAA
0x14000aea5  mov     ebx, 0C0000225h
0x14000aeaa  xor     edx, edx; Wait
0x14000aeac  lea     rcx, [rdi+8]; Mutex
0x14000aeb0  call    cs:__imp_KeReleaseMutex
0x14000aeb7  nop     dword ptr [rax+rax+00h]
0x14000aebc  jmp     short loc_14000AEC3
0x14000aebe  mov     ebx, 0C0000225h
0x14000aec3  mov     eax, ebx
0x14000aec5  add     rsp, 30h
0x14000aec9  pop     r14
0x14000aecb  pop     rdi
0x14000aecc  pop     rsi
0x14000aecd  pop     rbp
0x14000aece  pop     rbx
0x14000aecf  retn
```
