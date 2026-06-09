# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::~vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>(void)

- ea: `0x180010b5c`
- end: `0x180010bce`
- name: `??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800141f0`
- `0x180014810`
- `0x18004481e`
- `0x1800448de`
- `0x1800462c9`

## callees

- `0x180010b5c`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010ba1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010ba1`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(__int64 a1)
{
  _QWORD *v1; // rdi
  _QWORD *v3; // rsi

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(_QWORD **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *v1 )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v1 + 64LL))(*v1, 1);
      ++v1;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180010b5c  mov     [rsp+arg_0], rbx
0x180010b61  mov     [rsp+arg_8], rsi
0x180010b66  push    rdi
0x180010b67  sub     rsp, 20h
0x180010b6b  mov     rdi, [rcx]
0x180010b6e  mov     rbx, rcx
0x180010b71  test    rdi, rdi
0x180010b74  jz      short loc_180010BBE
0x180010b76  mov     rsi, [rcx+8]
0x180010b7a  jmp     short loc_180010B99
0x180010b7c  mov     rcx, [rdi]
0x180010b7f  test    rcx, rcx
0x180010b82  jz      short loc_180010B95
0x180010b84  mov     rax, [rcx]
0x180010b87  mov     edx, 1
0x180010b8c  mov     rax, [rax+40h]
0x180010b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b95  add     rdi, 8
0x180010b99  cmp     rdi, rsi
0x180010b9c  jnz     short loc_180010B7C
0x180010b9e  mov     rcx, [rbx]
0x180010ba1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010ba7  mov     qword ptr [rbx], 0
0x180010bae  mov     qword ptr [rbx+8], 0
0x180010bb6  mov     qword ptr [rbx+10h], 0
0x180010bbe  mov     rbx, [rsp+28h+arg_0]
0x180010bc3  mov     rsi, [rsp+28h+arg_8]
0x180010bc8  add     rsp, 20h
0x180010bcc  pop     rdi
0x180010bcd  retn
```
