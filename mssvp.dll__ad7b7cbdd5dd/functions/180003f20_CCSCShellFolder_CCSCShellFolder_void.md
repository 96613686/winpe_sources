# CCSCShellFolder::~CCSCShellFolder(void)

- ea: `0x180003f20`
- end: `0x180003fcc`
- name: `??1CCSCShellFolder@@QEAA@XZ`
- size: `172`
- prototype: `void __fastcall(CCSCShellFolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009f0c`

## callees

- `0x180003f20`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003fbf`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180003f4d`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180003f4d`

## pseudocode

```c
void __fastcall CCSCShellFolder::~CCSCShellFolder(CCSCShellFolder *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &CCSCShellFolder::`vftable'{for `IShellFolder2'};
  *((_QWORD *)this + 1) = &CCSCShellFolder::`vftable'{for `IPersistFolder2'};
  *((_QWORD *)this + 2) = &CCSCShellFolder::`vftable'{for `IDelegateFolder'};
  ILFree(*((LPITEMIDLIST *)this + 15));
  v2 = *((_QWORD *)this + 14);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 13);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 12);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 11);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( *((_BYTE *)this + 72) )
  {
    *((_BYTE *)this + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  }
}

```

## disassembly

```asm
0x180003f20  push    rbx
0x180003f22  sub     rsp, 20h
0x180003f26  mov     rbx, rcx
0x180003f29  lea     rax, ??_7CCSCShellFolder@@6BIShellFolder2@@@; const CCSCShellFolder::`vftable'{for `IShellFolder2'}
0x180003f30  mov     [rcx], rax
0x180003f33  lea     rax, ??_7CCSCShellFolder@@6BIPersistFolder2@@@; const CCSCShellFolder::`vftable'{for `IPersistFolder2'}
0x180003f3a  mov     [rcx+8], rax
0x180003f3e  lea     rax, ??_7CCSCShellFolder@@6BIDelegateFolder@@@; const CCSCShellFolder::`vftable'{for `IDelegateFolder'}
0x180003f45  mov     [rcx+10h], rax
0x180003f49  mov     rcx, [rcx+78h]; pidl
0x180003f4d  call    cs:__imp_ILFree
0x180003f53  nop
0x180003f54  mov     rcx, [rbx+70h]
0x180003f58  test    rcx, rcx
0x180003f5b  jz      short loc_180003F6A
0x180003f5d  mov     rax, [rcx]
0x180003f60  mov     rax, [rax+10h]
0x180003f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f69  nop
0x180003f6a  mov     rcx, [rbx+68h]
0x180003f6e  test    rcx, rcx
0x180003f71  jz      short loc_180003F80
0x180003f73  mov     rax, [rcx]
0x180003f76  mov     rax, [rax+10h]
0x180003f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f7f  nop
0x180003f80  mov     rcx, [rbx+60h]
0x180003f84  test    rcx, rcx
0x180003f87  jz      short loc_180003F96
0x180003f89  mov     rax, [rcx]
0x180003f8c  mov     rax, [rax+10h]
0x180003f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f95  nop
0x180003f96  mov     rcx, [rbx+58h]
0x180003f9a  test    rcx, rcx
0x180003f9d  jz      short loc_180003FAC
0x180003f9f  mov     rax, [rcx]
0x180003fa2  mov     rax, [rax+10h]
0x180003fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fab  nop
0x180003fac  lea     rcx, [rbx+20h]
0x180003fb0  cmp     byte ptr [rcx+28h], 0
0x180003fb4  jz      short loc_180003FC6
0x180003fb6  mov     byte ptr [rcx+28h], 0
0x180003fba  add     rsp, 20h
0x180003fbe  pop     rbx
0x180003fbf  jmp     cs:__imp_DeleteCriticalSection
0x180003fc6  add     rsp, 20h
0x180003fca  pop     rbx
0x180003fcb  retn
```
