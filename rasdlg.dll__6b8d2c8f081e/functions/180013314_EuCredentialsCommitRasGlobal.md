# EuCredentialsCommitRasGlobal

- ea: `0x180013314`
- end: `0x1800134c7`
- name: `EuCredentialsCommitRasGlobal`
- size: `435`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180012b78`

## callees

- `0x180013314`
- `0x18003ce6c`
- `0x18003d184`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001335f`
- `rtutils!TracePrintfExA` at `0x180013411`
- `rtutils!TracePrintfExA` at `0x180013472`
- `rtutils!TracePrintfExA` at `0x18001335f`
- `rtutils!TracePrintfExA` at `0x180013411`
- `rtutils!TracePrintfExA` at `0x180013472`

## string_xrefs

- `0x180013355`: `EuCredentialsCommitRasGlobal`
- `0x180013466`: `EuCredsCommitRasGlobal: RasSetCredentials=%d`

## pseudocode

```c
__int64 __fastcall EuCredentialsCommitRasGlobal(__int64 a1)
{
  DWORD v2; // ebx
  bool v3; // zf
  int v4; // eax
  __int16 *v5; // rcx
  __int64 v6; // rcx
  wchar_t *v7; // rax
  int v9; // [rsp+20h] [rbp-468h]
  _DWORD v10[2]; // [rsp+40h] [rbp-448h] BYREF
  wchar_t v11[257]; // [rsp+48h] [rbp-440h] BYREF
  wchar_t v12[275]; // [rsp+24Ah] [rbp-23Eh] BYREF

  v2 = 0;
  memset_0(v10, 0, 0x42Cu);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "EuCredentialsCommitRasGlobal");
  if ( *(_QWORD *)(a1 + 1544) )
  {
    memset_0(v11, 0, 0x424u);
    v3 = *(_DWORD *)(a1 + 1536) == 0;
    v4 = 3;
    v10[0] = 1068;
    if ( !v3 )
      v4 = 11;
    v5 = *(__int16 **)(a1 + 1552);
    v10[1] = v4;
    EncodePasswordW(v5);
    v2 = StringCchCopyWrapW(v12, 0x101u, *(const wchar_t **)(a1 + 1552));
    EncodePasswordW(*(__int16 **)(a1 + 1552));
    if ( !v2 )
    {
      v2 = StringCchCopyWrapW(v11, 0x101u, *(const wchar_t **)(a1 + 1544));
      if ( !v2 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "RasSetCredentials(p,TRUE)");
        v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _DWORD *, _QWORD))g_pRasSetCredentials)(
               **(_QWORD **)(a1 + 64),
               *(_QWORD *)(*(_QWORD *)(a1 + 872) + 8LL),
               v10,
               0);
        v6 = 514;
        v7 = v12;
        do
        {
          *(_BYTE *)v7 = 0;
          v7 = (wchar_t *)((char *)v7 + 1);
          --v6;
        }
        while ( v6 );
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "EuCredsCommitRasGlobal: RasSetCredentials=%d", v2);
        if ( v2 )
          ErrorDlgUtil(*(HWND *)(*(_QWORD *)(a1 + 16) + 4LL), 0x13Bu, v2, 0, v9, 0x169u, 0xFAu);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180013314  mov     [rsp+arg_8], rbx
0x180013319  push    rdi
0x18001331a  sub     rsp, 480h
0x180013321  mov     rax, cs:__security_cookie
0x180013328  xor     rax, rsp
0x18001332b  mov     [rsp+488h+var_18], rax
0x180013333  mov     rdi, rcx
0x180013336  xor     edx, edx; Val
0x180013338  lea     rcx, [rsp+488h+var_448]; void *
0x18001333d  mov     r8d, 42Ch; Size
0x180013343  xor     ebx, ebx
0x180013345  call    memset_0
0x18001334a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180013350  cmp     ecx, 0FFFFFFFFh
0x180013353  jz      short loc_180013365
0x180013355  lea     r8, aEucredentialsc; "EuCredentialsCommitRasGlobal"
0x18001335c  lea     edx, [rbx+0Ch]; dwFlags
0x18001335f  call    cs:__imp_TracePrintfExA
0x180013365  cmp     [rdi+608h], rbx
0x18001336c  jz      loc_1800134A4
0x180013372  xor     edx, edx; Val
0x180013374  lea     rcx, [rsp+488h+var_440]; void *
0x180013379  mov     r8d, 424h; Size
0x18001337f  call    memset_0
0x180013384  cmp     [rdi+600h], ebx
0x18001338a  mov     eax, 3
0x18001338f  mov     [rsp+488h+var_448], 42Ch
0x180013397  lea     ecx, [rax+8]
0x18001339a  cmovnz  eax, ecx
0x18001339d  mov     rcx, [rdi+610h]
0x1800133a4  mov     [rsp+488h+var_444], eax
0x1800133a8  call    EncodePasswordW
0x1800133ad  mov     r8, [rdi+610h]
0x1800133b4  lea     rcx, [rsp+488h+var_23E]
0x1800133bc  mov     edx, 101h
0x1800133c1  call    StringCchCopyWrapW
0x1800133c6  mov     rcx, [rdi+610h]
0x1800133cd  mov     ebx, eax
0x1800133cf  call    EncodePasswordW
0x1800133d4  test    ebx, ebx
0x1800133d6  jnz     loc_1800134A4
0x1800133dc  mov     r8, [rdi+608h]
0x1800133e3  lea     rcx, [rsp+488h+var_440]
0x1800133e8  mov     edx, 101h
0x1800133ed  call    StringCchCopyWrapW
0x1800133f2  mov     ebx, eax
0x1800133f4  test    eax, eax
0x1800133f6  jnz     loc_1800134A4
0x1800133fc  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180013402  cmp     ecx, 0FFFFFFFFh
0x180013405  jz      short loc_180013417
0x180013407  lea     r8, aRassetcredenti_0; "RasSetCredentials(p,TRUE)"
0x18001340e  lea     edx, [rax+0Ch]; dwFlags
0x180013411  call    cs:__imp_TracePrintfExA
0x180013417  mov     rdx, [rdi+368h]
0x18001341e  lea     r8, [rsp+488h+var_448]
0x180013423  mov     rcx, [rdi+40h]
0x180013427  xor     r9d, r9d
0x18001342a  mov     rax, cs:g_pRasSetCredentials
0x180013431  mov     rdx, [rdx+8]
0x180013435  mov     rcx, [rcx]
0x180013438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001343d  mov     ebx, eax
0x18001343f  mov     ecx, 202h
0x180013444  lea     rax, [rsp+488h+var_23E]
0x18001344c  mov     byte ptr [rax], 0
0x18001344f  inc     rax
0x180013452  sub     rcx, 1
0x180013456  jnz     short loc_18001344C
0x180013458  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001345e  cmp     ecx, 0FFFFFFFFh
0x180013461  jz      short loc_180013478
0x180013463  mov     r9d, ebx
0x180013466  lea     r8, aEucredscommitr; "EuCredsCommitRasGlobal: RasSetCredentia"...
0x18001346d  mov     edx, 0Ch; dwFlags
0x180013472  call    cs:__imp_TracePrintfExA
0x180013478  test    ebx, ebx
0x18001347a  jz      short loc_1800134A4
0x18001347c  mov     rcx, [rdi+10h]
0x180013480  xor     r9d, r9d
0x180013483  mov     [rsp+488h+var_458], 0FAh; UINT
0x18001348b  mov     r8d, ebx; dwMessageId
0x18001348e  mov     edx, 13Bh; uID
0x180013493  mov     [rsp+488h+var_460], 169h; UINT
0x18001349b  mov     rcx, [rcx+4]; hWnd
0x18001349f  call    ErrorDlgUtil
0x1800134a4  mov     eax, ebx
0x1800134a6  mov     rcx, [rsp+488h+var_18]
0x1800134ae  xor     rcx, rsp; StackCookie
0x1800134b1  call    __security_check_cookie
0x1800134b6  mov     rbx, [rsp+488h+arg_8]
0x1800134be  add     rsp, 480h
0x1800134c5  pop     rdi
0x1800134c6  retn
```
