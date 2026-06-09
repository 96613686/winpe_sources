# CMFTSimpleTypeHandler::InitAvailableInputTypeArray(ulong)

- ea: `0x180009404`
- end: `0x1800094b0`
- name: `?InitAvailableInputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z`
- size: `172`
- prototype: `__int64 __fastcall(CMFTSimpleTypeHandler *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000440c`
- `0x180008e58`

## callees

- `0x180001120`
- `0x180001178`
- `0x180001eb0`
- `0x180009404`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CMFTSimpleTypeHandler::InitAvailableInputTypeArray(CMFTSimpleTypeHandler *this, unsigned int a2)
{
  unsigned int v2; // esi
  unsigned __int64 v3; // rbp
  void **i; // rbx
  __int64 v6; // rcx
  void *v7; // rax

  v2 = 0;
  v3 = a2;
  for ( i = (void **)((char *)this + 24); v2 < *((_DWORD *)this + 4); ++v2 )
  {
    v6 = *((_QWORD *)*i + 2 * v2);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      *((_QWORD *)*i + 2 * v2) = 0;
    }
  }
  operator delete(*i);
  *((_DWORD *)this + 4) = 0;
  if ( (_DWORD)v3 )
  {
    v7 = operator new(saturated_mul(v3, 0x10u));
    *i = v7;
    if ( !v7 )
      return 2147942414LL;
    memset_0(v7, 0, 16 * v3);
    *((_DWORD *)this + 4) = v3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009404  push    rbx
0x180009406  push    rbp
0x180009407  push    rsi
0x180009408  push    rdi
0x180009409  push    r14
0x18000940b  sub     rsp, 20h
0x18000940f  xor     esi, esi
0x180009411  mov     ebp, edx
0x180009413  lea     rbx, [rcx+18h]
0x180009417  mov     rdi, rcx
0x18000941a  cmp     [rcx+10h], esi
0x18000941d  jbe     short loc_18000944F
0x18000941f  mov     rax, [rbx]
0x180009422  mov     r14d, esi
0x180009425  add     r14, r14
0x180009428  mov     rcx, [rax+r14*8]
0x18000942c  test    rcx, rcx
0x18000942f  jz      short loc_180009448
0x180009431  mov     rax, [rcx]
0x180009434  mov     rax, [rax+10h]
0x180009438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000943d  mov     rax, [rbx]
0x180009440  mov     qword ptr [rax+r14*8], 0
0x180009448  inc     esi
0x18000944a  cmp     esi, [rdi+10h]
0x18000944d  jb      short loc_18000941F
0x18000944f  mov     rcx, [rbx]; Block
0x180009452  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009457  mov     dword ptr [rdi+10h], 0
0x18000945e  test    ebp, ebp
0x180009460  jz      short loc_1800094A3
0x180009462  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009469  mov     eax, 10h
0x18000946e  mul     rbp
0x180009471  mov     rsi, rbp
0x180009474  cmovb   rax, rcx
0x180009478  mov     rcx, rax; Size
0x18000947b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009480  mov     [rbx], rax
0x180009483  test    rax, rax
0x180009486  jnz     short loc_18000948F
0x180009488  mov     eax, 8007000Eh
0x18000948d  jmp     short loc_1800094A5
0x18000948f  shl     rsi, 4
0x180009493  xor     edx, edx; Val
0x180009495  mov     r8, rsi; Size
0x180009498  mov     rcx, rax; void *
0x18000949b  call    memset_0
0x1800094a0  mov     [rdi+10h], ebp
0x1800094a3  xor     eax, eax
0x1800094a5  add     rsp, 20h
0x1800094a9  pop     r14
0x1800094ab  pop     rdi
0x1800094ac  pop     rsi
0x1800094ad  pop     rbp
0x1800094ae  pop     rbx
0x1800094af  retn
```
