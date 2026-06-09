# std::vector<std::shared_ptr<CMvExtensionKey>,std::allocator<std::shared_ptr<CMvExtensionKey>>>::~vector<std::shared_ptr<CMvExtensionKey>,std::allocator<std::shared_ptr<CMvExtensionKey>>>(void)

- ea: `0x180013bd0`
- end: `0x180013c5d`
- name: `??1?$vector@V?$shared_ptr@VCMvExtensionKey@@@std@@V?$allocator@V?$shared_ptr@VCMvExtensionKey@@@std@@@2@@std@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180013c64`

## callees

- `0x180013bd0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013c37`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013c37`

## pseudocode

```c
void __fastcall std::vector<std::shared_ptr<CMvExtensionKey>>::~vector<std::shared_ptr<CMvExtensionKey>>(void **a1)
{
  char *v2; // rdi
  char *v3; // rbp
  volatile signed __int32 *v4; // rsi

  v2 = (char *)*a1;
  if ( *a1 )
  {
    v3 = (char *)a1[1];
    while ( v2 != v3 )
    {
      v4 = (volatile signed __int32 *)*((_QWORD *)v2 + 1);
      if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
      v2 += 16;
    }
    operator delete(*a1);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180013bd0  push    rbx
0x180013bd2  push    rbp
0x180013bd3  push    rsi
0x180013bd4  push    rdi
0x180013bd5  sub     rsp, 28h
0x180013bd9  mov     rbx, rcx
0x180013bdc  mov     rdi, [rcx]
0x180013bdf  test    rdi, rdi
0x180013be2  jz      short loc_180013C54
0x180013be4  mov     rbp, [rcx+8]
0x180013be8  jmp     short loc_180013C2F
0x180013bea  mov     rsi, [rdi+8]
0x180013bee  test    rsi, rsi
0x180013bf1  jz      short loc_180013C2B
0x180013bf3  or      eax, 0FFFFFFFFh
0x180013bf6  lock xadd [rsi+8], eax
0x180013bfb  cmp     eax, 1
0x180013bfe  jnz     short loc_180013C2B
0x180013c00  mov     rax, [rsi]
0x180013c03  mov     rcx, rsi
0x180013c06  mov     rax, [rax]
0x180013c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c0e  or      eax, 0FFFFFFFFh
0x180013c11  lock xadd [rsi+0Ch], eax
0x180013c16  cmp     eax, 1
0x180013c19  jnz     short loc_180013C2B
0x180013c1b  mov     rax, [rsi]
0x180013c1e  mov     rcx, rsi
0x180013c21  mov     rax, [rax+8]
0x180013c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c2a  nop
0x180013c2b  add     rdi, 10h
0x180013c2f  cmp     rdi, rbp
0x180013c32  jnz     short loc_180013BEA
0x180013c34  mov     rcx, [rbx]
0x180013c37  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013c3d  mov     qword ptr [rbx], 0
0x180013c44  mov     qword ptr [rbx+8], 0
0x180013c4c  mov     qword ptr [rbx+10h], 0
0x180013c54  add     rsp, 28h
0x180013c58  pop     rdi
0x180013c59  pop     rsi
0x180013c5a  pop     rbp
0x180013c5b  pop     rbx
0x180013c5c  retn
```
