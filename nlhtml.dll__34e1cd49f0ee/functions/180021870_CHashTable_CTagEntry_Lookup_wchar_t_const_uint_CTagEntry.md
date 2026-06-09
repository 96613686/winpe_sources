# CHashTable<CTagEntry *>::Lookup(wchar_t const *,uint,CTagEntry * &)

- ea: `0x180021870`
- end: `0x1800218e4`
- name: `?Lookup@?$CHashTable@PEAVCTagEntry@@@@UEAAHPEB_WIAEAPEAVCTagEntry@@@Z`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180021870`
- `0x180023370`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall CHashTable<CTagEntry *>::Lookup(__int64 a1, const wchar_t *a2, unsigned int a3, _QWORD *a4)
{
  __int64 v5; // rsi
  __int64 i; // rbx
  const wchar_t *v8; // rdi

  v5 = a3;
  for ( i = *(_QWORD *)(a1 + 8LL * (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) + 8);
        ;
        i = *(_QWORD *)(i + 16) )
  {
    if ( !i )
      return 0;
    v8 = *(const wchar_t **)i;
    if ( !wcsncmp_0(a2, *(const wchar_t **)i, (unsigned int)v5) && !v8[v5] )
      break;
  }
  *a4 = *(_QWORD *)(i + 8);
  return 1;
}

```

## disassembly

```asm
0x180021870  push    rbx
0x180021872  push    rbp
0x180021873  push    rsi
0x180021874  push    rdi
0x180021875  push    r14
0x180021877  push    r15
0x180021879  sub     rsp, 28h
0x18002187d  mov     rax, [rcx]
0x180021880  mov     r14, r9
0x180021883  mov     esi, r8d
0x180021886  mov     rbp, rdx
0x180021889  mov     rbx, rcx
0x18002188c  mov     rax, [rax+10h]
0x180021890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021895  mov     r10d, eax
0x180021898  xor     r15d, r15d
0x18002189b  mov     rbx, [rbx+r10*8+8]
0x1800218a0  jmp     short loc_1800218C2
0x1800218a2  mov     rdi, [rbx]
0x1800218a5  mov     r8d, esi; MaxCount
0x1800218a8  mov     rdx, rdi; String2
0x1800218ab  mov     rcx, rbp; String1
0x1800218ae  call    wcsncmp_0
0x1800218b3  test    eax, eax
0x1800218b5  jnz     short loc_1800218BE
0x1800218b7  cmp     [rdi+rsi*2], r15w
0x1800218bc  jz      short loc_1800218D6
0x1800218be  mov     rbx, [rbx+10h]
0x1800218c2  test    rbx, rbx
0x1800218c5  jnz     short loc_1800218A2
0x1800218c7  xor     eax, eax
0x1800218c9  add     rsp, 28h
0x1800218cd  pop     r15
0x1800218cf  pop     r14
0x1800218d1  pop     rdi
0x1800218d2  pop     rsi
0x1800218d3  pop     rbp
0x1800218d4  pop     rbx
0x1800218d5  retn
0x1800218d6  mov     rax, [rbx+8]
0x1800218da  mov     [r14], rax
0x1800218dd  mov     eax, 1
0x1800218e2  jmp     short loc_1800218C9
```
