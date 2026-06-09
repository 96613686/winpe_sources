# CKSThunkPin::CKSThunkPin(_FILE_OBJECT *,CKSThunkDevice *,KSDATAFORMAT *)

- ea: `0x14000ac8c`
- end: `0x14000acf9`
- name: `??0CKSThunkPin@@QEAA@PEAU_FILE_OBJECT@@PEAVCKSThunkDevice@@PEATKSDATAFORMAT@@@Z`
- size: `109`
- prototype: `CKSThunkPin *__fastcall(CKSThunkPin *this, struct _FILE_OBJECT *, struct CKSThunkDevice *, union KSDATAFORMAT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001d90`

## callees

- `0x14000af44`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x14000acd2`
- `ntoskrnl!KeInitializeMutex` at `0x14000acd2`

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
0x14000ac8c  mov     [rsp+arg_0], rbx
0x14000ac91  push    rdi
0x14000ac92  sub     rsp, 20h
0x14000ac96  mov     [rcx+18h], rdx
0x14000ac9a  lea     rax, ??_7CKSThunkPin@@6BCKernelFilterFile@@@; const CKSThunkPin::`vftable'{for `CKernelFilterFile'}
0x14000aca1  mov     [rcx], rax
0x14000aca4  mov     rdi, rcx
0x14000aca7  lea     rax, ??_7CKSThunkPin@@6BCKSAutomationThunk@@@; const CKSThunkPin::`vftable'{for `CKSAutomationThunk'}
0x14000acae  mov     [rcx+20h], r8
0x14000acb2  mov     [rcx+28h], rax
0x14000acb6  xor     edx, edx; Level
0x14000acb8  mov     qword ptr [rcx+68h], 0
0x14000acc0  mov     rbx, r9
0x14000acc3  mov     dword ptr [rcx+70h], 0
0x14000acca  mov     byte ptr [rcx+74h], 1
0x14000acce  add     rcx, 30h ; '0'; Mutex
0x14000acd2  call    cs:__imp_KeInitializeMutex
0x14000acd9  nop     dword ptr [rax+rax+00h]
0x14000acde  mov     rdx, rbx; union KSDATAFORMAT *
0x14000ace1  call    ?LocateFormatHandler@CKSThunkPin@@QEAAPEAUIKsWOW64FormatThunk@@PEATKSDATAFORMAT@@@Z; CKSThunkPin::LocateFormatHandler(KSDATAFORMAT *)
0x14000ace6  mov     rbx, [rsp+28h+arg_0]
0x14000aceb  mov     [rdi+68h], rax
0x14000acef  mov     rax, rdi
0x14000acf2  add     rsp, 20h
0x14000acf6  pop     rdi
0x14000acf7  retn
```
