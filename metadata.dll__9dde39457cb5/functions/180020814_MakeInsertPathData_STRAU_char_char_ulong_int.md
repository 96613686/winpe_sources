# MakeInsertPathData(STRAU *,char *,char *,ulong *,int)

- ea: `0x180020814`
- end: `0x180020939`
- name: `?MakeInsertPathData@@YAJPEAVSTRAU@@PEAD1PEAKH@Z`
- size: `293`
- prototype: `int(struct STRAU *, char *, char *, unsigned int *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ef4`

## callees

- `0x180020814`

## import_xrefs

- `msvcrt!_mbsstr` at `0x1800208c5`
- `msvcrt!_mbsstr` at `0x1800208c5`
- `msvcrt!wcsstr` at `0x180020851`
- `msvcrt!wcsstr` at `0x180020851`
- `IisRTL!?Append@STRAU@@QEAAHPEBDK@Z` at `0x1800208df`
- `IisRTL!?Append@STRAU@@QEAAHPEBDK@Z` at `0x1800208df`
- `IisRTL!?Append@STRAU@@QEAAHPEBGK@Z` at `0x18002086e`
- `IisRTL!?Append@STRAU@@QEAAHPEBGK@Z` at `0x18002086e`
- `IisRTL!?SetLen@STRAU@@QEAAHK@Z` at `0x180020833`
- `IisRTL!?SetLen@STRAU@@QEAAHK@Z` at `0x180020833`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18002087f`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18002089b`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18002087f`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18002089b`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x1800208f0`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18002090c`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x1800208f0`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18002090c`
- `IisRTL!?QueryCB@STRAU@@QEAAIH@Z` at `0x1800208b0`
- `IisRTL!?QueryCB@STRAU@@QEAAIH@Z` at `0x18002091c`
- `IisRTL!?QueryCB@STRAU@@QEAAIH@Z` at `0x1800208b0`
- `IisRTL!?QueryCB@STRAU@@QEAAIH@Z` at `0x18002091c`

## string_xrefs

- `0x180020847`: `<%INSERT_PATH%>`
- `0x1800208bb`: `<%INSERT_PATH%>`

## pseudocode

```c
__int64 __fastcall MakeInsertPathData(struct STRAU *a1, char *a2, const wchar_t *a3, unsigned int *a4, int a5)
{
  int v9; // ebx
  wchar_t *v10; // rax
  wchar_t *v11; // r14
  unsigned int v12; // eax
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // r14

  v9 = 0;
  STRAU::SetLen(a1, 0);
  if ( a5 )
  {
    do
    {
      v10 = wcsstr(a3, L"<%INSERT_PATH%>");
      v11 = v10;
      if ( !v10 )
        break;
      if ( !STRAU::Append(a1, a3, v10 - a3) )
        v9 = -2147024882;
      a3 = v11 + 15;
      if ( !STRAU::Append(a1, (const unsigned __int16 *)a2) )
      {
        v9 = -2147024882;
        break;
      }
    }
    while ( v9 >= 0 );
    if ( !STRAU::Append(a1, a3) )
      v9 = -2147024882;
    v12 = STRAU::QueryCB(a1, a5) + 2;
  }
  else
  {
    do
    {
      v13 = _mbsstr((const unsigned __int8 *)a3, "<%INSERT_PATH%>");
      v14 = v13;
      if ( !v13 )
        break;
      if ( !STRAU::Append(a1, (const char *)a3, (_DWORD)v13 - (_DWORD)a3) )
        v9 = -2147024882;
      a3 = (const wchar_t *)(v14 + 15);
      if ( !STRAU::Append(a1, a2) )
      {
        v9 = -2147024882;
        break;
      }
    }
    while ( v9 >= 0 );
    if ( !STRAU::Append(a1, (const char *)a3) )
      v9 = -2147024882;
    v12 = STRAU::QueryCB(a1, 0) + 1;
  }
  *a4 = v12;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180020814  push    rbx
0x180020816  push    rbp
0x180020817  push    rsi
0x180020818  push    rdi
0x180020819  push    r12
0x18002081b  push    r13
0x18002081d  push    r14
0x18002081f  sub     rsp, 20h
0x180020823  mov     r13, rdx
0x180020826  mov     r12, r9
0x180020829  xor     edx, edx
0x18002082b  mov     rdi, r8
0x18002082e  mov     rsi, rcx
0x180020831  xor     ebx, ebx
0x180020833  call    cs:__imp_?SetLen@STRAU@@QEAAHK@Z; STRAU::SetLen(ulong)
0x180020839  mov     ebp, 8007000Eh
0x18002083e  cmp     [rsp+58h+arg_20], ebx
0x180020845  jz      short loc_1800208BB
0x180020847  lea     rdx, aInsertPath; "<%INSERT_PATH%>"
0x18002084e  mov     rcx, rdi; Str
0x180020851  call    cs:__imp_wcsstr
0x180020857  mov     r14, rax
0x18002085a  test    rax, rax
0x18002085d  jz      short loc_180020895
0x18002085f  mov     r8, rax
0x180020862  mov     rdx, rdi
0x180020865  sub     r8, rdi
0x180020868  mov     rcx, rsi
0x18002086b  sar     r8, 1
0x18002086e  call    cs:__imp_?Append@STRAU@@QEAAHPEBGK@Z; STRAU::Append(ushort const *,ulong)
0x180020874  mov     rdx, r13
0x180020877  mov     rcx, rsi
0x18002087a  test    eax, eax
0x18002087c  cmovz   ebx, ebp
0x18002087f  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x180020885  lea     rdi, [r14+1Eh]
0x180020889  test    eax, eax
0x18002088b  jz      short loc_180020893
0x18002088d  test    ebx, ebx
0x18002088f  jns     short loc_180020847
0x180020891  jmp     short loc_180020895
0x180020893  mov     ebx, ebp
0x180020895  mov     rdx, rdi
0x180020898  mov     rcx, rsi
0x18002089b  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x1800208a1  mov     edx, [rsp+58h+arg_20]
0x1800208a8  mov     rcx, rsi
0x1800208ab  test    eax, eax
0x1800208ad  cmovz   ebx, ebp
0x1800208b0  call    cs:__imp_?QueryCB@STRAU@@QEAAIH@Z; STRAU::QueryCB(int)
0x1800208b6  add     eax, 2
0x1800208b9  jmp     short loc_180020924
0x1800208bb  lea     rdx, Substr; "<%INSERT_PATH%>"
0x1800208c2  mov     rcx, rdi; Str
0x1800208c5  call    cs:__imp__mbsstr
0x1800208cb  mov     r14, rax
0x1800208ce  test    rax, rax
0x1800208d1  jz      short loc_180020906
0x1800208d3  mov     r8d, r14d
0x1800208d6  mov     rdx, rdi
0x1800208d9  sub     r8d, edi
0x1800208dc  mov     rcx, rsi
0x1800208df  call    cs:__imp_?Append@STRAU@@QEAAHPEBDK@Z; STRAU::Append(char const *,ulong)
0x1800208e5  mov     rdx, r13
0x1800208e8  mov     rcx, rsi
0x1800208eb  test    eax, eax
0x1800208ed  cmovz   ebx, ebp
0x1800208f0  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x1800208f6  lea     rdi, [r14+0Fh]
0x1800208fa  test    eax, eax
0x1800208fc  jz      short loc_180020904
0x1800208fe  test    ebx, ebx
0x180020900  jns     short loc_1800208BB
0x180020902  jmp     short loc_180020906
0x180020904  mov     ebx, ebp
0x180020906  mov     rdx, rdi
0x180020909  mov     rcx, rsi
0x18002090c  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x180020912  test    eax, eax
0x180020914  mov     rcx, rsi
0x180020917  cmovz   ebx, ebp
0x18002091a  xor     edx, edx
0x18002091c  call    cs:__imp_?QueryCB@STRAU@@QEAAIH@Z; STRAU::QueryCB(int)
0x180020922  inc     eax
0x180020924  mov     [r12], eax
0x180020928  mov     eax, ebx
0x18002092a  add     rsp, 20h
0x18002092e  pop     r14
0x180020930  pop     r13
0x180020932  pop     r12
0x180020934  pop     rdi
0x180020935  pop     rsi
0x180020936  pop     rbp
0x180020937  pop     rbx
0x180020938  retn
```
