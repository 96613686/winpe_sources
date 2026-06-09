# CIPropertyStorageWrapper::CIPropertyStorageWrapper(void)

- ea: `0x180010d40`
- end: `0x180010d81`
- name: `??0CIPropertyStorageWrapper@@QEAA@XZ`
- size: `65`
- prototype: `CIPropertyStorageWrapper *__fastcall(CIPropertyStorageWrapper *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800064e0`
- `0x18000e958`
- `0x180010e98`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180010d6e`
- `KERNEL32!CreateMutexW` at `0x180010d6e`

## pseudocode

```c
CIPropertyStorageWrapper *__fastcall CIPropertyStorageWrapper::CIPropertyStorageWrapper(CIPropertyStorageWrapper *this)
{
  *((_DWORD *)this + 8) = 2;
  *(_QWORD *)this = &CIPropertyStorageWrapper::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = CreateMutexW(0, 0, 0);
  return this;
}

```

## disassembly

```asm
0x180010d40  push    rbx
0x180010d42  sub     rsp, 20h
0x180010d46  lea     rax, ??_7CIPropertyStorageWrapper@@6B@; const CIPropertyStorageWrapper::`vftable'
0x180010d4d  mov     dword ptr [rcx+20h], 2
0x180010d54  mov     [rcx], rax
0x180010d57  mov     rbx, rcx
0x180010d5a  xor     eax, eax
0x180010d5c  xor     r8d, r8d; lpName
0x180010d5f  mov     [rcx+8], eax
0x180010d62  xor     edx, edx; bInitialOwner
0x180010d64  mov     [rcx+10h], rax
0x180010d68  mov     [rcx+18h], rax
0x180010d6c  xor     ecx, ecx; lpMutexAttributes
0x180010d6e  call    cs:__imp_CreateMutexW
0x180010d74  mov     [rbx+28h], rax
0x180010d78  mov     rax, rbx
0x180010d7b  add     rsp, 20h
0x180010d7f  pop     rbx
0x180010d80  retn
```
