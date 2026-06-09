# CKSThunkPin::CKSThunkPin(_FILE_OBJECT *,CKSThunkDevice *,KSDATAFORMAT *)

- ea: `0x14000bbec`
- end: `0x14000bc59`
- name: `??0CKSThunkPin@@QEAA@PEAU_FILE_OBJECT@@PEAVCKSThunkDevice@@PEATKSDATAFORMAT@@@Z`
- size: `109`
- prototype: `CKSThunkPin *__fastcall(CKSThunkPin *this, struct _FILE_OBJECT *, struct CKSThunkDevice *, union KSDATAFORMAT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001e10`

## callees

- `0x14000bea4`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x14000bc32`
- `ntoskrnl!KeInitializeMutex` at `0x14000bc32`

## pseudocode

```c
CKSThunkPin *__fastcall CKSThunkPin::CKSThunkPin(
        CKSThunkPin *this,
        struct _FILE_OBJECT *a2,
        struct CKSThunkDevice *a3,
        union KSDATAFORMAT *a4)
{
  CKSThunkPin *v6; // rcx

  *((_QWORD *)this + 3) = a2;
  *(_QWORD *)this = &CKSThunkPin::`vftable'{for `CKernelFilterFile'};
  *((_QWORD *)this + 4) = a3;
  *((_QWORD *)this + 5) = &CKSThunkPin::`vftable'{for `CKSAutomationThunk'};
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_BYTE *)this + 116) = 1;
  KeInitializeMutex((PRKMUTEX)((char *)this + 48), 0);
  *((_QWORD *)this + 13) = CKSThunkPin::LocateFormatHandler(v6, a4);
  return this;
}

```

## disassembly

```asm
0x14000bbec  mov     [rsp+arg_0], rbx
0x14000bbf1  push    rdi
0x14000bbf2  sub     rsp, 20h
0x14000bbf6  mov     [rcx+18h], rdx
0x14000bbfa  lea     rax, ??_7CKSThunkPin@@6BCKernelFilterFile@@@; const CKSThunkPin::`vftable'{for `CKernelFilterFile'}
0x14000bc01  mov     [rcx], rax
0x14000bc04  mov     rdi, rcx
0x14000bc07  lea     rax, ??_7CKSThunkPin@@6BCKSAutomationThunk@@@; const CKSThunkPin::`vftable'{for `CKSAutomationThunk'}
0x14000bc0e  mov     [rcx+20h], r8
0x14000bc12  mov     [rcx+28h], rax
0x14000bc16  xor     edx, edx; Level
0x14000bc18  mov     qword ptr [rcx+68h], 0
0x14000bc20  mov     rbx, r9
0x14000bc23  mov     dword ptr [rcx+70h], 0
0x14000bc2a  mov     byte ptr [rcx+74h], 1
0x14000bc2e  add     rcx, 30h ; '0'; Mutex
0x14000bc32  call    cs:__imp_KeInitializeMutex
0x14000bc39  nop     dword ptr [rax+rax+00h]
0x14000bc3e  mov     rdx, rbx; union KSDATAFORMAT *
0x14000bc41  call    ?LocateFormatHandler@CKSThunkPin@@QEAAPEAUIKsWOW64FormatThunk@@PEATKSDATAFORMAT@@@Z; CKSThunkPin::LocateFormatHandler(KSDATAFORMAT *)
0x14000bc46  mov     rbx, [rsp+28h+arg_0]
0x14000bc4b  mov     [rdi+68h], rax
0x14000bc4f  mov     rax, rdi
0x14000bc52  add     rsp, 20h
0x14000bc56  pop     rdi
0x14000bc57  retn
```
