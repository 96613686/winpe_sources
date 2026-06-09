# NPrintTicketUtil::CreateMessage(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000570c`
- end: `0x1800057e8`
- name: `?CreateMessage@NPrintTicketUtil@@YAPEAGPEBG0000@Z`
- size: `220`
- prototype: `unsigned __int16 *__usercall@<rax>(NPrintTicketUtil *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003318`
- `0x180004ec0`
- `0x18001d30c`

## callees

- `0x18000570c`
- `0x180007660`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005796`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005796`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057cb`

## pseudocode

```c
unsigned __int16 *__fastcall NPrintTicketUtil::CreateMessage(
        NPrintTicketUtil *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  __int64 v5; // rax
  __int64 v7; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  OLECHAR *v15; // rdi

  v5 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)this + v7) );
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    LODWORD(v7) = v11 + v7;
  }
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    LODWORD(v7) = v12 + v7;
  }
  if ( a4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a4[v13] );
    LODWORD(v7) = v13 + v7;
  }
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    LODWORD(v7) = v5 + v7;
  }
  v14 = SysAllocStringLen(0, v7);
  v15 = v14;
  if ( !v14
    || (unsigned int)StringCchPrintfW(v14, (unsigned int)(v7 + 1), (const unsigned __int16 *)this, a2, a3, a4, a5) )
  {
    SysFreeString(v15);
    return 0;
  }
  return v15;
}

```

## disassembly

```asm
0x18000570c  push    rbx
0x18000570e  push    rbp
0x18000570f  push    rsi
0x180005710  push    rdi
0x180005711  push    r12
0x180005713  push    r13
0x180005715  push    r14
0x180005717  push    r15
0x180005719  sub     rsp, 48h
0x18000571d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005721  mov     rbp, r9
0x180005724  mov     rbx, rax
0x180005727  xor     r13d, r13d
0x18000572a  mov     r14, r8
0x18000572d  mov     r15, rdx
0x180005730  mov     r12, rcx
0x180005733  inc     rbx
0x180005736  cmp     [rcx+rbx*2], r13w
0x18000573b  jnz     short loc_180005733
0x18000573d  test    r15, r15
0x180005740  jz      short loc_180005751
0x180005742  mov     rcx, rax
0x180005745  inc     rcx
0x180005748  cmp     [rdx+rcx*2], r13w
0x18000574d  jnz     short loc_180005745
0x18000574f  add     ebx, ecx
0x180005751  test    r14, r14
0x180005754  jz      short loc_180005765
0x180005756  mov     rcx, rax
0x180005759  inc     rcx
0x18000575c  cmp     [r8+rcx*2], r13w
0x180005761  jnz     short loc_180005759
0x180005763  add     ebx, ecx
0x180005765  test    rbp, rbp
0x180005768  jz      short loc_180005779
0x18000576a  mov     rcx, rax
0x18000576d  inc     rcx
0x180005770  cmp     [r9+rcx*2], r13w
0x180005775  jnz     short loc_18000576D
0x180005777  add     ebx, ecx
0x180005779  mov     rsi, [rsp+88h+arg_20]
0x180005781  test    rsi, rsi
0x180005784  jz      short loc_180005792
0x180005786  inc     rax
0x180005789  cmp     [rsi+rax*2], r13w
0x18000578e  jnz     short loc_180005786
0x180005790  add     ebx, eax
0x180005792  mov     edx, ebx; ui
0x180005794  xor     ecx, ecx; strIn
0x180005796  call    cs:__imp_SysAllocStringLen
0x18000579c  mov     rdi, rax
0x18000579f  test    rax, rax
0x1800057a2  jz      short loc_1800057C8
0x1800057a4  mov     [rsp+88h+var_58], rsi
0x1800057a9  lea     edx, [rbx+1]; unsigned __int64
0x1800057ac  mov     [rsp+88h+var_60], rbp
0x1800057b1  mov     r9, r15
0x1800057b4  mov     r8, r12; unsigned __int16 *
0x1800057b7  mov     [rsp+88h+var_68], r14
0x1800057bc  mov     rcx, rax; unsigned __int16 *
0x1800057bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800057c4  test    eax, eax
0x1800057c6  jz      short loc_1800057D4
0x1800057c8  mov     rcx, rdi; bstrString
0x1800057cb  call    cs:__imp_SysFreeString
0x1800057d1  mov     rdi, r13
0x1800057d4  mov     rax, rdi
0x1800057d7  add     rsp, 48h
0x1800057db  pop     r15
0x1800057dd  pop     r14
0x1800057df  pop     r13
0x1800057e1  pop     r12
0x1800057e3  pop     rdi
0x1800057e4  pop     rsi
0x1800057e5  pop     rbp
0x1800057e6  pop     rbx
0x1800057e7  retn
```
