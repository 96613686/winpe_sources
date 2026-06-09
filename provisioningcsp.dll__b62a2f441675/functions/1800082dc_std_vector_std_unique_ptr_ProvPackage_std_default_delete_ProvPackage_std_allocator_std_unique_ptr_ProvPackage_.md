# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::~vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>(void)

- ea: `0x1800082dc`
- end: `0x180008355`
- name: `??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008d50`
- `0x18000f58c`
- `0x1800133d8`
- `0x180036181`
- `0x180036468`
- `0x180036889`
- `0x180037582`

## callees

- `0x1800082dc`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008321`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008321`

## pseudocode

```c
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
0x1800082dc  mov     [rsp+arg_0], rbx
0x1800082e1  mov     [rsp+arg_8], rsi
0x1800082e6  push    rdi
0x1800082e7  sub     rsp, 20h
0x1800082eb  mov     rdi, [rcx]
0x1800082ee  mov     rbx, rcx
0x1800082f1  test    rdi, rdi
0x1800082f4  jz      short loc_180008344
0x1800082f6  mov     rsi, [rcx+8]
0x1800082fa  jmp     short loc_180008319
0x1800082fc  mov     rcx, [rdi]
0x1800082ff  test    rcx, rcx
0x180008302  jz      short loc_180008315
0x180008304  mov     rax, [rcx]
0x180008307  mov     edx, 1
0x18000830c  mov     rax, [rax+40h]
0x180008310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008315  add     rdi, 8
0x180008319  cmp     rdi, rsi
0x18000831c  jnz     short loc_1800082FC
0x18000831e  mov     rcx, [rbx]
0x180008321  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008328  nop     dword ptr [rax+rax+00h]
0x18000832d  mov     qword ptr [rbx], 0
0x180008334  mov     qword ptr [rbx+8], 0
0x18000833c  mov     qword ptr [rbx+10h], 0
0x180008344  mov     rbx, [rsp+28h+arg_0]
0x180008349  mov     rsi, [rsp+28h+arg_8]
0x18000834e  add     rsp, 20h
0x180008352  pop     rdi
0x180008353  retn
```
