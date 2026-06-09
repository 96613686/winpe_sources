# I_ReaderListLookupProviders

- ea: `0x18000ce50`
- end: `0x18000d216`
- name: `I_ReaderListLookupProviders`
- size: `966`
- prototype: `__int64 __fastcall(__int64, _QWORD *, const BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800115c0`

## callees

- `0x180004600`
- `0x18000ce50`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cf04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d057`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d13d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cf04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d057`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d13d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1f9`
- `WinSCard!SCardListCardsW` at `0x18000ce8f`
- `WinSCard!SCardListCardsW` at `0x18000cf94`
- `WinSCard!SCardListCardsW` at `0x18000ce8f`
- `WinSCard!SCardListCardsW` at `0x18000cf94`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000d02c`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000d07a`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000d114`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000d160`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000d02c`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000d07a`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000d114`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000d160`

## pseudocode

```c
__int64 __fastcall I_ReaderListLookupProviders(__int64 a1, _QWORD *a2, const BYTE *a3, DWORD a4)
{
  SCARDCONTEXT v7; // rcx
  __int64 v8; // rcx
  unsigned int v9; // edi
  LPVOID *v10; // r14
  WCHAR *mszCards; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  SCARDCONTEXT v14; // r12
  const WCHAR *v15; // r15
  const WCHAR *v16; // rdx
  WCHAR *v17; // rax
  __int64 v18; // rcx
  LONG CardTypeProviderNameW; // edi
  void *v20; // r8
  const WCHAR *v21; // rdi
  SCARDCONTEXT v22; // r15
  const WCHAR *v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // rcx
  LONG v26; // ebx
  void *v27; // r8
  DWORD pcchProvider; // [rsp+70h] [rbp+8h] BYREF
  DWORD pcchCards; // [rsp+88h] [rbp+20h] BYREF

  pcchCards = a4;
  v7 = *(_QWORD *)(a1 + 232);
  pcchCards = 0;
  v9 = SCardListCardsW(v7, a3, 0, 0, 0, &pcchCards);
  if ( v9 )
  {
    WppTraceIndent(v8, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        167,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        v9);
    }
    v10 = (LPVOID *)(a2 + 2);
    goto LABEL_38;
  }
  mszCards = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * pcchCards);
  a2[2] = mszCards;
  v10 = (LPVOID *)(a2 + 2);
  if ( !mszCards )
  {
    WppTraceIndent(v12, 2);
    v9 = 8;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        168,
        &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent);
    }
    goto LABEL_38;
  }
  v9 = SCardListCardsW(*(_QWORD *)(a1 + 232), a3, 0, 0, mszCards, &pcchCards);
  if ( v9 )
  {
    WppTraceIndent(v13, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        169,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        v9);
    }
    goto LABEL_38;
  }
  v14 = *(_QWORD *)(a1 + 232);
  v15 = (const WCHAR *)*v10;
  v16 = (const WCHAR *)*v10;
  pcchProvider = 0;
  if ( !SCardGetCardTypeProviderNameW(v14, v16, 2u, 0, &pcchProvider) )
  {
    v17 = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * pcchProvider);
    a2[10] = v17;
    CardTypeProviderNameW = SCardGetCardTypeProviderNameW(v14, v15, 2u, v17, &pcchProvider);
    if ( !CardTypeProviderNameW )
      goto LABEL_26;
    WppTraceIndent(v18, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        166,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        CardTypeProviderNameW);
    }
  }
  v20 = (void *)a2[10];
  if ( v20 )
  {
    HeapFree(hHeap, 0, v20);
    a2[10] = 0;
  }
  a2[10] = 0;
LABEL_26:
  v21 = (const WCHAR *)*v10;
  v22 = *(_QWORD *)(a1 + 232);
  v23 = (const WCHAR *)*v10;
  pcchProvider = 0;
  if ( SCardGetCardTypeProviderNameW(v22, v23, 3u, 0, &pcchProvider) )
  {
LABEL_32:
    v27 = (void *)a2[11];
    if ( v27 )
    {
      HeapFree(hHeap, 0, v27);
      a2[11] = 0;
    }
    a2[11] = 0;
    goto LABEL_35;
  }
  v24 = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * pcchProvider);
  a2[11] = v24;
  v26 = SCardGetCardTypeProviderNameW(v22, v21, 3u, v24, &pcchProvider);
  if ( v26 )
  {
    WppTraceIndent(v25, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        166,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        v26);
    }
    goto LABEL_32;
  }
LABEL_35:
  if ( a2[11] || a2[10] )
    return 0;
  v9 = -2146435044;
LABEL_38:
  if ( *v10 )
  {
    HeapFree(hHeap, 0, *v10);
    *v10 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18000ce50  mov     r11, rsp
0x18000ce53  mov     [r11+20h], r9d
0x18000ce57  push    rbx
0x18000ce58  push    rbp
0x18000ce59  push    rsi
0x18000ce5a  push    rdi
0x18000ce5b  push    r13
0x18000ce5d  push    r14
0x18000ce5f  sub     rsp, 38h
0x18000ce63  mov     rsi, r8
0x18000ce66  lea     rax, [r11+20h]
0x18000ce6a  mov     rbp, rdx
0x18000ce6d  mov     [r11-40h], rax
0x18000ce71  mov     rbx, rcx
0x18000ce74  xor     r13d, r13d
0x18000ce77  mov     rcx, [rcx+0E8h]; hContext
0x18000ce7e  mov     rdx, rsi; pbAtr
0x18000ce81  xor     r9d, r9d; cguidInterfaceCount
0x18000ce84  mov     [r11-48h], r13
0x18000ce88  xor     r8d, r8d; rgquidInterfaces
0x18000ce8b  mov     [r11+20h], r13d
0x18000ce8f  call    cs:__imp_SCardListCardsW
0x18000ce95  mov     edi, eax
0x18000ce97  test    eax, eax
0x18000ce99  jz      short loc_18000CEED
0x18000ce9b  mov     edx, 2
0x18000cea0  call    WppTraceIndent
0x18000cea5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ceac  lea     rsi, WPP_GLOBAL_Control
0x18000ceb3  cmp     rcx, rsi
0x18000ceb6  jz      short loc_18000CEE4
0x18000ceb8  test    byte ptr [rcx+1Ch], 1
0x18000cebc  jz      short loc_18000CEE4
0x18000cebe  cmp     byte ptr [rcx+19h], 2
0x18000cec2  jb      short loc_18000CEE4
0x18000cec4  mov     r9, cs:WPP_pszIndent
0x18000cecb  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000ced2  mov     rcx, [rcx+10h]
0x18000ced6  mov     edx, 0A7h
0x18000cedb  mov     dword ptr [rsp+68h+mszCards], edi
0x18000cedf  call    WPP_SF_sD
0x18000cee4  lea     r14, [rbp+10h]
0x18000cee8  jmp     loc_18000D1E8
0x18000ceed  mov     r8d, [rsp+68h+arg_18]
0x18000cef5  mov     edx, 8; dwFlags
0x18000cefa  mov     rcx, cs:hHeap; hHeap
0x18000cf01  add     r8, r8; dwBytes
0x18000cf04  call    cs:__imp_HeapAlloc
0x18000cf0a  mov     [rbp+10h], rax
0x18000cf0e  lea     r14, [rbp+10h]
0x18000cf12  test    rax, rax
0x18000cf15  jnz     short loc_18000CF72
0x18000cf17  mov     edx, 2
0x18000cf1c  call    WppTraceIndent
0x18000cf21  mov     edi, 8
0x18000cf26  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf2d  lea     rsi, WPP_GLOBAL_Control
0x18000cf34  cmp     rcx, rsi
0x18000cf37  jz      loc_18000D1E8
0x18000cf3d  test    byte ptr [rcx+1Ch], 1
0x18000cf41  jz      loc_18000D1E8
0x18000cf47  cmp     byte ptr [rcx+19h], 2
0x18000cf4b  jb      loc_18000D1E8
0x18000cf51  mov     r9, cs:WPP_pszIndent
0x18000cf58  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000cf5f  mov     rcx, [rcx+10h]
0x18000cf63  mov     edx, 0A8h
0x18000cf68  call    WPP_SF_s
0x18000cf6d  jmp     loc_18000D1E8
0x18000cf72  lea     rcx, [rsp+68h+arg_18]
0x18000cf7a  xor     r9d, r9d; cguidInterfaceCount
0x18000cf7d  mov     [rsp+68h+pcchCards], rcx; pcchCards
0x18000cf82  xor     r8d, r8d; rgquidInterfaces
0x18000cf85  mov     rcx, [rbx+0E8h]; hContext
0x18000cf8c  mov     rdx, rsi; pbAtr
0x18000cf8f  mov     [rsp+68h+mszCards], rax; mszCards
0x18000cf94  call    cs:__imp_SCardListCardsW
0x18000cf9a  mov     edi, eax
0x18000cf9c  test    eax, eax
0x18000cf9e  jz      short loc_18000CFFA
0x18000cfa0  mov     edx, 2
0x18000cfa5  call    WppTraceIndent
0x18000cfaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfb1  lea     rsi, WPP_GLOBAL_Control
0x18000cfb8  cmp     rcx, rsi
0x18000cfbb  jz      loc_18000D1E8
0x18000cfc1  test    byte ptr [rcx+1Ch], 1
0x18000cfc5  jz      loc_18000D1E8
0x18000cfcb  cmp     byte ptr [rcx+19h], 2
0x18000cfcf  jb      loc_18000D1E8
0x18000cfd5  mov     r9, cs:WPP_pszIndent
0x18000cfdc  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000cfe3  mov     rcx, [rcx+10h]
0x18000cfe7  mov     edx, 0A9h
0x18000cfec  mov     dword ptr [rsp+68h+mszCards], edi
0x18000cff0  call    WPP_SF_sD
0x18000cff5  jmp     loc_18000D1E8
0x18000cffa  mov     [rsp+68h+arg_8], r12
0x18000cfff  lea     rax, [rsp+68h+pcchProvider]
0x18000d004  mov     r12, [rbx+0E8h]
0x18000d00b  xor     r9d, r9d; szProvider
0x18000d00e  mov     [rsp+68h+var_38], r15
0x18000d013  mov     r8d, 2; dwProviderId
0x18000d019  mov     r15, [r14]
0x18000d01c  mov     rcx, r12; hContext
0x18000d01f  mov     rdx, r15; szCardName
0x18000d022  mov     [rsp+68h+pcchProvider], r13d
0x18000d027  mov     [rsp+68h+mszCards], rax; pcchProvider
0x18000d02c  call    cs:__imp_SCardGetCardTypeProviderNameW
0x18000d032  lea     rsi, WPP_GLOBAL_Control
0x18000d039  mov     edi, eax
0x18000d03b  test    eax, eax
0x18000d03d  jnz     loc_18000D0C8
0x18000d043  mov     r8d, [rsp+68h+pcchProvider]
0x18000d048  mov     edx, 8; dwFlags
0x18000d04d  mov     rcx, cs:hHeap; hHeap
0x18000d054  add     r8, r8; dwBytes
0x18000d057  call    cs:__imp_HeapAlloc
0x18000d05d  lea     rcx, [rsp+68h+pcchProvider]
0x18000d062  mov     r8d, 2; dwProviderId
0x18000d068  mov     r9, rax; szProvider
0x18000d06b  mov     [rbp+50h], rax
0x18000d06f  mov     [rsp+68h+mszCards], rcx; pcchProvider
0x18000d074  mov     rdx, r15; szCardName
0x18000d077  mov     rcx, r12; hContext
0x18000d07a  call    cs:__imp_SCardGetCardTypeProviderNameW
0x18000d080  mov     edi, eax
0x18000d082  test    eax, eax
0x18000d084  jz      short loc_18000D0EC
0x18000d086  mov     edx, 2
0x18000d08b  call    WppTraceIndent
0x18000d090  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d097  cmp     rcx, rsi
0x18000d09a  jz      short loc_18000D0C8
0x18000d09c  test    byte ptr [rcx+1Ch], 1
0x18000d0a0  jz      short loc_18000D0C8
0x18000d0a2  cmp     byte ptr [rcx+19h], 2
0x18000d0a6  jb      short loc_18000D0C8
0x18000d0a8  mov     r9, cs:WPP_pszIndent
0x18000d0af  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000d0b6  mov     rcx, [rcx+10h]
0x18000d0ba  mov     edx, 0A6h
0x18000d0bf  mov     dword ptr [rsp+68h+mszCards], edi
0x18000d0c3  call    WPP_SF_sD
0x18000d0c8  mov     r8, [rbp+50h]; lpMem
0x18000d0cc  test    r8, r8
0x18000d0cf  jz      short loc_18000D0E4
0x18000d0d1  mov     rcx, cs:hHeap; hHeap
0x18000d0d8  xor     edx, edx; dwFlags
0x18000d0da  call    cs:__imp_HeapFree
0x18000d0e0  mov     [rbp+50h], r13
0x18000d0e4  test    edi, edi
0x18000d0e6  jz      short loc_18000D0EC
0x18000d0e8  mov     [rbp+50h], r13
0x18000d0ec  mov     rdi, [r14]
0x18000d0ef  lea     rax, [rsp+68h+pcchProvider]
0x18000d0f4  mov     r15, [rbx+0E8h]
0x18000d0fb  mov     rdx, rdi; szCardName
0x18000d0fe  mov     rcx, r15; hContext
0x18000d101  mov     [rsp+68h+pcchProvider], r13d
0x18000d106  xor     r9d, r9d; szProvider
0x18000d109  mov     [rsp+68h+mszCards], rax; pcchProvider
0x18000d10e  mov     r8d, 3; dwProviderId
0x18000d114  call    cs:__imp_SCardGetCardTypeProviderNameW
0x18000d11a  mov     r12, [rsp+68h+arg_8]
0x18000d11f  mov     ebx, eax
0x18000d121  test    eax, eax
0x18000d123  jnz     loc_18000D1AE
0x18000d129  mov     r8d, [rsp+68h+pcchProvider]
0x18000d12e  mov     edx, 8; dwFlags
0x18000d133  mov     rcx, cs:hHeap; hHeap
0x18000d13a  add     r8, r8; dwBytes
0x18000d13d  call    cs:__imp_HeapAlloc
0x18000d143  lea     rcx, [rsp+68h+pcchProvider]
0x18000d148  mov     r8d, 3; dwProviderId
0x18000d14e  mov     r9, rax; szProvider
0x18000d151  mov     [rbp+58h], rax
0x18000d155  mov     [rsp+68h+mszCards], rcx; pcchProvider
0x18000d15a  mov     rdx, rdi; szCardName
0x18000d15d  mov     rcx, r15; hContext
0x18000d160  call    cs:__imp_SCardGetCardTypeProviderNameW
0x18000d166  mov     ebx, eax
0x18000d168  test    eax, eax
0x18000d16a  jz      short loc_18000D1D2
0x18000d16c  mov     edx, 2
0x18000d171  call    WppTraceIndent
0x18000d176  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d17d  cmp     rcx, rsi
0x18000d180  jz      short loc_18000D1AE
0x18000d182  test    byte ptr [rcx+1Ch], 1
0x18000d186  jz      short loc_18000D1AE
0x18000d188  cmp     byte ptr [rcx+19h], 2
0x18000d18c  jb      short loc_18000D1AE
0x18000d18e  mov     r9, cs:WPP_pszIndent
0x18000d195  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000d19c  mov     rcx, [rcx+10h]
0x18000d1a0  mov     edx, 0A6h
0x18000d1a5  mov     dword ptr [rsp+68h+mszCards], ebx
0x18000d1a9  call    WPP_SF_sD
0x18000d1ae  mov     r8, [rbp+58h]; lpMem
0x18000d1b2  test    r8, r8
0x18000d1b5  jz      short loc_18000D1CA
0x18000d1b7  mov     rcx, cs:hHeap; hHeap
0x18000d1be  xor     edx, edx; dwFlags
0x18000d1c0  call    cs:__imp_HeapFree
0x18000d1c6  mov     [rbp+58h], r13
0x18000d1ca  test    ebx, ebx
0x18000d1cc  jz      short loc_18000D1D2
0x18000d1ce  mov     [rbp+58h], r13
0x18000d1d2  mov     r15, [rsp+68h+var_38]
0x18000d1d7  cmp     [rbp+58h], r13
0x18000d1db  jnz     short loc_18000D206
0x18000d1dd  cmp     [rbp+50h], r13
0x18000d1e1  jnz     short loc_18000D206
0x18000d1e3  mov     edi, 8010001Ch
0x18000d1e8  mov     r8, [r14]; lpMem
0x18000d1eb  test    r8, r8
0x18000d1ee  jz      short loc_18000D202
0x18000d1f0  mov     rcx, cs:hHeap; hHeap
0x18000d1f7  xor     edx, edx; dwFlags
0x18000d1f9  call    cs:__imp_HeapFree
0x18000d1ff  mov     [r14], r13
0x18000d202  mov     eax, edi
0x18000d204  jmp     short loc_18000D209
0x18000d206  mov     eax, r13d
0x18000d209  add     rsp, 38h
0x18000d20d  pop     r14
0x18000d20f  pop     r13
0x18000d211  pop     rdi
0x18000d212  pop     rsi
0x18000d213  pop     rbp
0x18000d214  pop     rbx
0x18000d215  retn
```
