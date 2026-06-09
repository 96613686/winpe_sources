# CKSThunkPin::DataFormat(_IRP *,KSIDENTIFIER *,KSDATAFORMAT *)

- ea: `0x14000bd80`
- end: `0x14000be31`
- name: `?DataFormat@CKSThunkPin@@UEAAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEATKSDATAFORMAT@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CKSThunkPin *this, struct _IRP *, struct KSIDENTIFIER *, union KSDATAFORMAT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1400041f0`
- `0x14000b5e0`
- `0x14000bd80`
- `0x14000bea4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000bdb9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000bdb9`
- `ntoskrnl!KeReleaseMutex` at `0x14000be10`
- `ntoskrnl!KeReleaseMutex` at `0x14000be10`

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
      v10 = CKernelFilterDevice::SynchronousForwardIrp(*((PDEVICE_OBJECT **)this - 1), a2);
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
0x14000bd80  push    rbx
0x14000bd82  push    rbp
0x14000bd83  push    rsi
0x14000bd84  push    rdi
0x14000bd85  push    r14
0x14000bd87  sub     rsp, 30h
0x14000bd8b  mov     rax, [rdx+0B8h]
0x14000bd92  mov     rsi, r9
0x14000bd95  mov     r14, r8
0x14000bd98  mov     rbx, rdx
0x14000bd9b  mov     rdi, rcx
0x14000bd9e  cmp     dword ptr [rax+8], 40h ; '@'
0x14000bda2  jb      short loc_14000BE1E
0x14000bda4  xor     r9d, r9d; Alertable
0x14000bda7  mov     [rsp+58h+Timeout], 0; Timeout
0x14000bdb0  xor     r8d, r8d; WaitMode
0x14000bdb3  xor     edx, edx; WaitReason
0x14000bdb5  add     rcx, 8; Object
0x14000bdb9  call    cs:__imp_KeWaitForSingleObject
0x14000bdc0  nop     dword ptr [rax+rax+00h]
0x14000bdc5  mov     eax, [r14+14h]
0x14000bdc9  test    al, 2
0x14000bdcb  jz      short loc_14000BE05
0x14000bdcd  mov     rdx, rsi; union KSDATAFORMAT *
0x14000bdd0  call    ?LocateFormatHandler@CKSThunkPin@@QEAAPEAUIKsWOW64FormatThunk@@PEATKSDATAFORMAT@@@Z; CKSThunkPin::LocateFormatHandler(KSDATAFORMAT *)
0x14000bdd5  mov     rsi, rax
0x14000bdd8  test    rax, rax
0x14000bddb  jz      short loc_14000BE05
0x14000bddd  mov     rcx, [rdi-8]; this
0x14000bde1  mov     rdx, rbx; struct _IRP *
0x14000bde4  call    ?SynchronousForwardIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@@Z; CKernelFilterDevice::SynchronousForwardIrp(_IRP *)
0x14000bde9  mov     ebx, eax
0x14000bdeb  test    eax, eax
0x14000bded  js      short loc_14000BE0A
0x14000bdef  mov     rcx, [rdi+40h]
0x14000bdf3  mov     [rdi+40h], rsi
0x14000bdf7  mov     rdx, [rcx]
0x14000bdfa  mov     rax, [rdx+10h]
0x14000bdfe  call    _guard_dispatch_icall
0x14000be03  jmp     short loc_14000BE0A
0x14000be05  mov     ebx, 0C0000225h
0x14000be0a  xor     edx, edx; Wait
0x14000be0c  lea     rcx, [rdi+8]; Mutex
0x14000be10  call    cs:__imp_KeReleaseMutex
0x14000be17  nop     dword ptr [rax+rax+00h]
0x14000be1c  jmp     short loc_14000BE23
0x14000be1e  mov     ebx, 0C0000225h
0x14000be23  mov     eax, ebx
0x14000be25  add     rsp, 30h
0x14000be29  pop     r14
0x14000be2b  pop     rdi
0x14000be2c  pop     rsi
0x14000be2d  pop     rbp
0x14000be2e  pop     rbx
0x14000be2f  retn
```
