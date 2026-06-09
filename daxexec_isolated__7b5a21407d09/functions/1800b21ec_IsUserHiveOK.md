# IsUserHiveOK

- ea: `0x1800b21ec`
- end: `0x1800b23c3`
- name: `IsUserHiveOK`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008fe60`

## callees

- `0x1800b2118`
- `0x1800b2128`
- `0x1800b21ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b22f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b22f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b2227`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b2268`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b2227`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b2268`

## string_xrefs

- `0x1800b22be`: `onecore\com\published\comutils\reghelp.cxx`
- `0x1800b233e`: `onecore\com\published\comutils\reghelp.cxx`
- `0x1800b23a0`: `onecore\com\published\comutils\reghelp.cxx`
- `0x1800b232d`: `IsElevatedToken`
- `0x1800b22ad`: `GetTokenElevationType`
- `0x1800b2387`: `COM will not use the per-user hive in this process.This can cause activation of per-user classes from Elevated and Accessibilty appsto fail with REGDB_E_CLASSNOTREG.`

## pseudocode

```c
__int64 __fastcall IsUserHiveOK(__int64 a1, int *a2)
{
  void *v3; // rcx
  unsigned int v4; // ebx
  signed int v5; // eax
  int v6; // eax
  signed int LastError; // eax
  int v9; // [rsp+70h] [rbp+28h] BYREF
  int v10; // [rsp+74h] [rbp+2Ch]
  DWORD TokenInformation; // [rsp+78h] [rbp+30h] BYREF
  int v12; // [rsp+80h] [rbp+38h] BYREF
  DWORD ReturnLength; // [rsp+88h] [rbp+40h] BYREF

  v10 = HIDWORD(a1);
  *a2 = 0;
  v9 = 0;
  v12 = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( dword_180108038 )
      ComTraceMessage(
        v4,
        "onecore\\com\\published\\comutils\\reghelp.cxx",
        "IsElevatedToken",
        127,
        0,
        L"%!HRESULT!",
        v4);
    if ( (v4 & 0x80000000) != 0 )
      return v4;
LABEL_19:
    v4 = IsUIAccessToken(v3, &v12);
    if ( (v4 & 0x80000000) != 0 )
      return v4;
    v6 = v12 == 0;
    *a2 = v6;
    goto LABEL_21;
  }
  if ( !TokenInformation )
    goto LABEL_19;
  TokenInformation = 0;
  v9 = 1;
  v4 = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenElevationType, &v9, 4u, &TokenInformation) )
  {
    v5 = GetLastError();
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    if ( dword_180108038 )
      ComTraceMessage(
        v4,
        "onecore\\com\\published\\comutils\\reghelp.cxx",
        "GetTokenElevationType",
        174,
        0,
        L"%!HRESULT!",
        v4);
  }
  if ( (v4 & 0x80000000) == 0 )
  {
    if ( v9 == 2 )
    {
      *a2 = 0;
LABEL_22:
      if ( !byte_18010A158 )
      {
        byte_18010A158 = 1;
        if ( dword_180108038 )
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\published\\comutils\\reghelp.cxx",
            "IsUserHiveOK",
            249,
            1,
            L"COM will not use the per-user hive in this process.This can cause activation of per-user classes from Elevat"
             "ed and Accessibilty appsto fail with REGDB_E_CLASSNOTREG.");
      }
      return v4;
    }
    if ( v9 == 1 )
    {
      *a2 = 1;
      v6 = 1;
    }
    else
    {
      v6 = *a2;
    }
LABEL_21:
    if ( v6 )
      return v4;
    goto LABEL_22;
  }
  return v4;
}

```

## disassembly

```asm
0x1800b21ec  mov     [rsp-20h+arg_0], rcx
0x1800b21f1  push    rbp
0x1800b21f2  push    rbx
0x1800b21f3  push    rsi
0x1800b21f4  push    rdi
0x1800b21f5  mov     rbp, rsp
0x1800b21f8  sub     rsp, 48h
0x1800b21fc  xor     esi, esi
0x1800b21fe  lea     rax, [rbp+arg_18]
0x1800b2202  mov     rdi, rdx
0x1800b2205  mov     [rdx], esi
0x1800b2207  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800b220b  mov     dword ptr [rbp+arg_0], esi
0x1800b220e  mov     [rbp+arg_10], esi
0x1800b2211  lea     r9d, [rsi+4]; TokenInformationLength
0x1800b2215  mov     [rbp+arg_18], esi
0x1800b2218  lea     edx, [rsi+14h]; TokenInformationClass
0x1800b221b  mov     [rbp+TokenInformation], esi
0x1800b221e  lea     rcx, [rsi-4]; TokenHandle
0x1800b2222  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800b2227  call    cs:__imp_GetTokenInformation
0x1800b222e  nop     dword ptr [rax+rax+00h]
0x1800b2233  test    eax, eax
0x1800b2235  jz      loc_1800B22F8
0x1800b223b  cmp     [rbp+TokenInformation], esi
0x1800b223e  jz      loc_1800B2350
0x1800b2244  lea     rax, [rbp+TokenInformation]
0x1800b2248  mov     [rbp+TokenInformation], esi
0x1800b224b  lea     r9d, [rsi+4]; TokenInformationLength
0x1800b224f  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800b2254  lea     r8, [rbp+arg_0]; TokenInformation
0x1800b2258  mov     dword ptr [rbp+arg_0], 1
0x1800b225f  lea     edx, [rsi+12h]; TokenInformationClass
0x1800b2262  mov     ebx, esi
0x1800b2264  lea     rcx, [rsi-4]; TokenHandle
0x1800b2268  call    cs:__imp_GetTokenInformation
0x1800b226f  nop     dword ptr [rax+rax+00h]
0x1800b2274  test    eax, eax
0x1800b2276  jnz     short loc_1800B22CC
0x1800b2278  call    cs:__imp_GetLastError
0x1800b227f  nop     dword ptr [rax+rax+00h]
0x1800b2284  mov     ebx, eax
0x1800b2286  test    eax, eax
0x1800b2288  jle     short loc_1800B2293
0x1800b228a  movzx   ebx, ax
0x1800b228d  or      ebx, 80070000h
0x1800b2293  mov     eax, cs:dword_180108038
0x1800b2299  test    eax, eax
0x1800b229b  jz      short loc_1800B22CC
0x1800b229d  mov     [rsp+48h+var_18], ebx
0x1800b22a1  lea     rax, aHresult; "%!HRESULT!"
0x1800b22a8  mov     [rsp+48h+var_20], rax
0x1800b22ad  lea     r8, aGettokenelevat; "GetTokenElevationType"
0x1800b22b4  mov     r9d, 0AEh
0x1800b22ba  mov     dword ptr [rsp+48h+ReturnLength], esi
0x1800b22be  lea     rdx, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x1800b22c5  mov     ecx, ebx
0x1800b22c7  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800b22cc  test    ebx, ebx
0x1800b22ce  js      loc_1800B23B7
0x1800b22d4  cmp     dword ptr [rbp+arg_0], 2
0x1800b22d8  jnz     short loc_1800B22E1
0x1800b22da  mov     [rdi], esi
0x1800b22dc  jmp     loc_1800B236D
0x1800b22e1  cmp     dword ptr [rbp+arg_0], 1
0x1800b22e5  jnz     short loc_1800B22F4
0x1800b22e7  mov     dword ptr [rdi], 1
0x1800b22ed  mov     eax, 1
0x1800b22f2  jmp     short loc_1800B2369
0x1800b22f4  mov     eax, [rdi]
0x1800b22f6  jmp     short loc_1800B2369
0x1800b22f8  call    cs:__imp_GetLastError
0x1800b22ff  nop     dword ptr [rax+rax+00h]
0x1800b2304  mov     ebx, eax
0x1800b2306  test    eax, eax
0x1800b2308  jle     short loc_1800B2313
0x1800b230a  movzx   ebx, ax
0x1800b230d  or      ebx, 80070000h
0x1800b2313  mov     eax, cs:dword_180108038
0x1800b2319  test    eax, eax
0x1800b231b  jz      short loc_1800B234C
0x1800b231d  mov     [rsp+48h+var_18], ebx
0x1800b2321  lea     rax, aHresult; "%!HRESULT!"
0x1800b2328  mov     [rsp+48h+var_20], rax
0x1800b232d  lea     r8, aIselevatedtoke; "IsElevatedToken"
0x1800b2334  mov     r9d, 7Fh
0x1800b233a  mov     dword ptr [rsp+48h+ReturnLength], esi
0x1800b233e  lea     rdx, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x1800b2345  mov     ecx, ebx
0x1800b2347  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800b234c  test    ebx, ebx
0x1800b234e  js      short loc_1800B23B7
0x1800b2350  lea     rdx, [rbp+arg_10]; int *
0x1800b2354  call    ?IsUIAccessToken@@YAJPEAXPEAH@Z; IsUIAccessToken(void *,int *)
0x1800b2359  mov     ebx, eax
0x1800b235b  test    eax, eax
0x1800b235d  js      short loc_1800B23B7
0x1800b235f  cmp     [rbp+arg_10], esi
0x1800b2362  mov     eax, esi
0x1800b2364  setz    al
0x1800b2367  mov     [rdi], eax
0x1800b2369  test    eax, eax
0x1800b236b  jnz     short loc_1800B23B7
0x1800b236d  cmp     cs:byte_18010A158, sil
0x1800b2374  jnz     short loc_1800B23B7
0x1800b2376  mov     eax, cs:dword_180108038
0x1800b237c  mov     cs:byte_18010A158, 1
0x1800b2383  test    eax, eax
0x1800b2385  jz      short loc_1800B23B7
0x1800b2387  lea     rax, aComWillNotUseT; "COM will not use the per-user hive in t"...
0x1800b238e  mov     r9d, 0F9h
0x1800b2394  mov     [rsp+48h+var_20], rax
0x1800b2399  lea     r8, aIsuserhiveok; "IsUserHiveOK"
0x1800b23a0  lea     rdx, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x1800b23a7  mov     dword ptr [rsp+48h+ReturnLength], 1
0x1800b23af  or      ecx, 0FFFFFFFFh
0x1800b23b2  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800b23b7  mov     eax, ebx
0x1800b23b9  add     rsp, 48h
0x1800b23bd  pop     rdi
0x1800b23be  pop     rsi
0x1800b23bf  pop     rbx
0x1800b23c0  pop     rbp
0x1800b23c1  retn
```
