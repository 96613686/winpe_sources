# I_CidUtilCheckForCompatibleId

- ea: `0x18002271c`
- end: `0x1800227c2`
- name: `I_CidUtilCheckForCompatibleId`
- size: `166`
- prototype: `__int64 __fastcall(SCARDHANDLE, void *, __int64, __int64, wchar_t **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021c20`

## callees

- `0x18000b010`
- `0x1800223d4`
- `0x1800226f0`
- `0x18002271c`

## pseudocode

```c
__int64 __fastcall I_CidUtilCheckForCompatibleId(
        SCARDHANDLE a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        wchar_t **a5,
        int a6)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  size_t v9; // rsi
  wchar_t *v10; // rax
  wchar_t *v11; // rdi
  size_t Size; // [rsp+30h] [rbp-48h]

  LODWORD(Size) = 9;
  v7 = CidUtilTransmit(a1, (__int64)a2, 0xA4u, 4u, 0, a2, Size, 0, 0, a6);
  if ( !v7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a4 + 2 * v8) );
    v9 = v8 + 14;
    v10 = (wchar_t *)MIDL_user_allocate(2 * (v8 + 14));
    v11 = v10;
    if ( v10 )
    {
      StringCchPrintfW(v10, v9, L"%s%s", L"SCFILTER\\CID_", a4);
      *a5 = v11;
    }
    else
    {
      return 8;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18002271c  mov     r11, rsp
0x18002271f  push    rbx
0x180022720  push    rbp
0x180022721  push    rsi
0x180022722  push    rdi
0x180022723  push    r14
0x180022725  sub     rsp, 50h
0x180022729  mov     eax, [rsp+78h+arg_28]
0x180022730  xor     r14d, r14d
0x180022733  mov     [rsp+78h+var_30], eax; int
0x180022737  mov     rbp, r9
0x18002273a  mov     [r11-38h], r14
0x18002273e  mov     r9b, 4
0x180022741  mov     [r11-40h], r14
0x180022745  mov     r8b, 0A4h
0x180022748  mov     dword ptr [rsp+78h+Size], 9; Size
0x180022750  mov     [r11-50h], rdx
0x180022754  mov     [r11-58h], r14b
0x180022758  call    CidUtilTransmit
0x18002275d  mov     ebx, eax
0x18002275f  test    eax, eax
0x180022761  jnz     short loc_1800227B5
0x180022763  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180022767  inc     rcx
0x18002276a  cmp     [rbp+rcx*2+0], r14w
0x180022770  jnz     short loc_180022767
0x180022772  lea     rsi, [rcx+0Eh]
0x180022776  lea     rcx, [rsi+rsi]; size
0x18002277a  call    MIDL_user_allocate
0x18002277f  mov     rdi, rax
0x180022782  test    rax, rax
0x180022785  jnz     short loc_18002278C
0x180022787  lea     ebx, [rax+8]
0x18002278a  jmp     short loc_1800227B5
0x18002278c  lea     r9, aScfilterCid; "SCFILTER\\CID_"
0x180022793  mov     [rsp+78h+var_58], rbp
0x180022798  lea     r8, aSS; "%s%s"
0x18002279f  mov     rdx, rsi; cchDest
0x1800227a2  mov     rcx, rdi; pszDest
0x1800227a5  call    StringCchPrintfW
0x1800227aa  mov     rax, [rsp+78h+arg_20]
0x1800227b2  mov     [rax], rdi
0x1800227b5  mov     eax, ebx
0x1800227b7  add     rsp, 50h
0x1800227bb  pop     r14
0x1800227bd  pop     rdi
0x1800227be  pop     rsi
0x1800227bf  pop     rbp
0x1800227c0  pop     rbx
0x1800227c1  retn
```
