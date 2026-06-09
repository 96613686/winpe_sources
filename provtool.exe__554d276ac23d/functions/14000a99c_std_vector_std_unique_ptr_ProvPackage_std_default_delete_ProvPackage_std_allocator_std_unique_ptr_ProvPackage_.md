# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::emplace_back<ProvPackage *>(ProvPackage * &&)

- ea: `0x14000a99c`
- end: `0x14000aa34`
- name: `??$emplace_back@PEAVProvPackage@@@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAAX$$QEAPEAVProvPackage@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b454`

## callees

- `0x140008ca8`
- `0x14000a99c`
- `0x14000bca4`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // r8
  __int64 v4; // rdx
  __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rcx
  __int64 result; // rax

  v2 = a1[2];
  v4 = a1[1];
  if ( v4 == v2 && !((v2 - v4) >> 3) )
  {
    v6 = (v4 - *a1) >> 3;
    if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
      std::vector<std::unique_ptr<ProvPackage>>::_Xlen();
    v7 = v6 + 1;
    v8 = (v2 - *a1) >> 3;
    v9 = 0;
    if ( 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) >= v8 )
      v9 = v8 + (v8 >> 1);
    if ( v9 >= v7 )
      v7 = v9;
    std::vector<std::unique_ptr<ProvPackage>>::_Reallocate(a1, v7);
  }
  result = *a2;
  *(_QWORD *)a1[1] = *a2;
  a1[1] += 8LL;
  return result;
}

```

## disassembly

```asm
0x14000a99c  mov     [rsp+arg_0], rbx
0x14000a9a1  push    rdi
0x14000a9a2  sub     rsp, 20h
0x14000a9a6  mov     r8, [rcx+10h]
0x14000a9aa  mov     rdi, rdx
0x14000a9ad  mov     rdx, [rcx+8]
0x14000a9b1  mov     rbx, rcx
0x14000a9b4  cmp     rdx, r8
0x14000a9b7  jnz     short loc_14000AA14
0x14000a9b9  mov     rax, r8
0x14000a9bc  sub     rax, rdx
0x14000a9bf  sar     rax, 3
0x14000a9c3  cmp     rax, 1
0x14000a9c7  jnb     short loc_14000AA14
0x14000a9c9  sub     rdx, [rcx]
0x14000a9cc  mov     r9, 1FFFFFFFFFFFFFFFh
0x14000a9d6  sar     rdx, 3
0x14000a9da  mov     rax, r9
0x14000a9dd  sub     rax, rdx
0x14000a9e0  cmp     rax, 1
0x14000a9e4  jb      short loc_14000AA2E
0x14000a9e6  sub     r8, [rcx]
0x14000a9e9  inc     rdx
0x14000a9ec  sar     r8, 3
0x14000a9f0  xor     ecx, ecx
0x14000a9f2  mov     rax, r8
0x14000a9f5  shr     rax, 1
0x14000a9f8  sub     r9, rax
0x14000a9fb  add     rax, r8
0x14000a9fe  cmp     r9, r8
0x14000aa01  cmovnb  rcx, rax
0x14000aa05  cmp     rcx, rdx
0x14000aa08  cmovnb  rdx, rcx
0x14000aa0c  mov     rcx, rbx
0x14000aa0f  call    ?_Reallocate@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<ProvPackage>>::_Reallocate(unsigned __int64)
0x14000aa14  mov     rcx, [rbx+8]
0x14000aa18  mov     rax, [rdi]
0x14000aa1b  mov     [rcx], rax
0x14000aa1e  add     qword ptr [rbx+8], 8
0x14000aa23  mov     rbx, [rsp+28h+arg_0]
0x14000aa28  add     rsp, 20h
0x14000aa2c  pop     rdi
0x14000aa2d  retn
0x14000aa2e  call    ?_Xlen@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<ProvPackage>>::_Xlen(void)
```
