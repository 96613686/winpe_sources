# CHttpBase::AddRequestHeaders(void)

- ea: `0x1800427b8`
- end: `0x180042ac7`
- name: `?AddRequestHeaders@CHttpBase@@IEAAJXZ`
- size: `783`
- prototype: `__int64 __fastcall(CHttpBase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180046184`

## callees

- `0x180001284`
- `0x180001290`
- `0x180015438`
- `0x180017358`
- `0x1800427b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a75`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180042a63`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180042a63`
- `WININET!HttpAddRequestHeadersW` at `0x180042a6b`
- `WININET!HttpAddRequestHeadersW` at `0x180042a6b`
- `WININET!InternetSetOptionW` at `0x180042806`
- `WININET!InternetSetOptionW` at `0x180042806`

## string_xrefs

- `0x18004286d`: `Content-Type: text/xml; charset=utf-8\nSOAPAction: "http://microsoft.com/DRM/%s/%s"\n`
- `0x180042986`: `Content-Type: text/xml; charset=utf-8\nSOAPAction: "http://microsoft.com/DRM/%s/%s"\n`
- `0x180042874`: `Content-Type: text/xml; charset=utf-8\nAccept-Encoding: gzip, deflate\nSOAPAction: "http://microsoft.com/DRM/%s/%s"\n`

## pseudocode

```c
__int64 __fastcall CHttpBase::AddRequestHeaders(HINTERNET *this)
{
  HINTERNET *v1; // rsi
  int v2; // ebx
  unsigned __int16 *v3; // r12
  const WCHAR *v4; // r14
  unsigned __int16 *v5; // rcx
  unsigned __int64 v6; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rcx
  unsigned int v16; // ebx
  void *v17; // rcx
  BOOL v18; // eax
  __int64 v20; // [rsp+30h] [rbp-48h]
  __int64 v21; // [rsp+38h] [rbp-40h] BYREF
  HINTERNET *v22; // [rsp+80h] [rbp+8h]
  unsigned __int16 *v23; // [rsp+88h] [rbp+10h] BYREF

  v20 = -2;
  v1 = this;
  v2 = 0;
  v3 = 0;
  if ( *((_DWORD *)this + 35) )
  {
    if ( g_fGlobalOptionUseWinhttp
      || (LODWORD(v23) = 1, !InternetSetOptionW(this[13], 0x41u, &v23, 4u)) && GetLastError() == 12009 )
    {
      *((_DWORD *)v1 + 35) = 0;
    }
  }
  v4 = (const WCHAR *)v1[6];
  if ( !v4 )
  {
    if ( ((_BYTE)v1[5] & 2) != 0 )
    {
      v4 = L"Content-Type: application/x-www-form-urlencoded\r\nAccept-Encoding: gzip, deflate\r\n";
      if ( !*((_DWORD *)v1 + 35) )
        v4 = L"Content-Type: application/x-www-form-urlencoded\r\n";
    }
    else if ( v1[7] && v1[8] )
    {
      v5 = L"Content-Type: text/xml; charset=utf-8\r\n"
            "Accept-Encoding: gzip, deflate\r\n"
            "SOAPAction: \"http://microsoft.com/DRM/%s/%s\"\r\n";
      if ( !*((_DWORD *)v1 + 35) )
        v5 = L"Content-Type: text/xml; charset=utf-8\r\nSOAPAction: \"http://microsoft.com/DRM/%s/%s\"\r\n";
      v23 = v5;
      v6 = -1;
      do
        ++v6;
      while ( v5[v6] );
      if ( v6 > 0xFFFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v5);
      v7 = -1;
      do
        ++v7;
      while ( *((_WORD *)v1[7] + v7) );
      v8 = (unsigned int)v6 + v7;
      if ( v8 < (unsigned int)v6 || v8 > 0xFFFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v7);
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)v1[8] + v9) );
      v10 = (unsigned int)v8 + v9;
      if ( v10 < (unsigned int)v8 || v10 > 0xFFFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v10);
      v11 = (unsigned int)v10 + 1LL;
      if ( v11 > 0xFFFFFFFF )
      {
        try
        {
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v10);
        }
        catch ( SafeIntException v21 )
        {
          LODWORD(v23) = -2147467259;
          v1 = v22;
          v2 = -2147467259;
          v3 = 0;
          goto LABEL_47;
        }
      }
      operator delete(v1[6]);
      v1[6] = 0;
      v12 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v11, 2u));
      v1[6] = v12;
      if ( !v12 )
      {
        v2 = -2147024882;
        goto LABEL_47;
      }
      v2 = StringCchPrintfW(v12, (unsigned int)v11, v23, v1[7], v1[8]);
      if ( v2 < 0 )
        goto LABEL_47;
      v4 = (const WCHAR *)v1[6];
    }
    else
    {
      v4 = L"Content-Type: text/xml; charset=utf-8\r\nSOAPAction: \"http://microsoft.com/DRM/%s/%s\"\r\n";
    }
  }
  if ( !*((_DWORD *)v1 + 36) )
    goto LABEL_42;
  v23 = L"%s%s";
  v13 = -1;
  do
    ++v13;
  while ( v4[v13] );
  if ( v4[(unsigned int)(v13 - 2)] != 13 || (v14 = 0, v4[(unsigned int)(v13 - 1)] != 10) )
  {
    v23 = L"%s\r\n%s";
    v14 = 2;
  }
  v15 = (unsigned int)v13 + v14 + 57;
  if ( v15 < v14 )
    goto LABEL_62;
  while ( v15 > 0xFFFFFFFF )
  {
LABEL_62:
    try
    {
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v15);
    }
    catch ( SafeIntException (__int64 *)((char *)&v21 + 4) )
    {
      LODWORD(v23) = -2147467259;
      v1 = v22;
      v2 = -2147467259;
      v3 = 0;
      goto LABEL_47;
    }
  }
  v16 = v13 + v14 + 57;
  v3 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v15, 2u));
  v2 = StringCchPrintfW(v3, v16, v23, v4, L"X-MS-RMS-MSDRM-OPTIONS: ForceCrossTenantActivation=yes\r\n");
  if ( v2 >= 0 )
  {
    v4 = v3;
LABEL_42:
    v17 = v1[13];
    if ( g_fGlobalOptionUseWinhttp )
      v18 = WinHttpAddRequestHeaders(v17, v4, 0xFFFFFFFF, 0xA0000000);
    else
      v18 = HttpAddRequestHeadersW(v17, v4, 0xFFFFFFFF, 0xA0000000);
    if ( !v18 )
    {
      *((_DWORD *)v1 + 30) = GetLastError();
      v2 = -2147168453;
    }
  }
LABEL_47:
  if ( *((_DWORD *)v1 + 36) && v3 )
    operator delete(v3);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800427b8  mov     rax, rsp
0x1800427bb  mov     [rax+8], rcx
0x1800427bf  push    rbx
0x1800427c0  push    rsi
0x1800427c1  push    rdi
0x1800427c2  push    r12
0x1800427c4  push    r13
0x1800427c6  push    r14
0x1800427c8  push    r15
0x1800427ca  sub     rsp, 40h
0x1800427ce  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800427d6  mov     rsi, rcx
0x1800427d9  xor     edi, edi
0x1800427db  mov     ebx, edi
0x1800427dd  mov     r12d, edi
0x1800427e0  cmp     [rcx+8Ch], edi
0x1800427e6  jz      short loc_180042823
0x1800427e8  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, edi; int g_fGlobalOptionUseWinhttp
0x1800427ee  jnz     short loc_18004281D
0x1800427f0  mov     dword ptr [rax+10h], 1
0x1800427f7  lea     r9d, [rdi+4]; dwBufferLength
0x1800427fb  lea     r8, [rax+10h]; lpBuffer
0x1800427ff  lea     edx, [rdi+41h]; dwOption
0x180042802  mov     rcx, [rcx+68h]; hInternet
0x180042806  call    cs:__imp_InternetSetOptionW
0x18004280c  test    eax, eax
0x18004280e  jnz     short loc_180042823
0x180042810  call    cs:__imp_GetLastError
0x180042816  cmp     eax, 2EE9h
0x18004281b  jnz     short loc_180042823
0x18004281d  mov     [rsi+8Ch], edi
0x180042823  mov     r14, [rsi+30h]
0x180042827  test    r14, r14
0x18004282a  jnz     loc_18004298D
0x180042830  test    byte ptr [rsi+28h], 2
0x180042834  jz      short loc_180042853
0x180042836  lea     rax, ?g_wszHTTP_DefaultHeaders@@3QBGB; "Content-Type: application/x-www-form-ur"...
0x18004283d  lea     r14, ?g_wszHTTP_DefaultHeadersWithCompression@@3QBGB; "Content-Type: application/x-www-form-ur"...
0x180042844  cmp     [rsi+8Ch], edi
0x18004284a  cmovz   r14, rax
0x18004284e  jmp     loc_18004298D
0x180042853  cmp     [rsi+38h], rdi
0x180042857  jz      loc_180042986
0x18004285d  cmp     [rsi+40h], rdi
0x180042861  jz      loc_180042986
0x180042867  mov     eax, [rsi+8Ch]
0x18004286d  lea     r14, ?g_wszSOAP_HEADERS@@3QBGB; "Content-Type: text/xml; charset=utf-8\r"...
0x180042874  lea     rcx, ?g_wszSOAP_HEADERSWithCompression@@3QBGB; "Content-Type: text/xml; charset=utf-8\r"...
0x18004287b  test    eax, eax
0x18004287d  cmovz   rcx, r14
0x180042881  mov     [rsp+78h+arg_8], rcx
0x180042889  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004288d  mov     rax, r13
0x180042890  inc     rax
0x180042893  cmp     [rcx+rax*2], di
0x180042897  jnz     short loc_180042890
0x180042899  mov     r15d, 0FFFFFFFFh
0x18004289f  cmp     rax, r15
0x1800428a2  ja      loc_180042ABA
0x1800428a8  mov     rdx, [rsi+38h]
0x1800428ac  mov     rcx, r13
0x1800428af  inc     rcx
0x1800428b2  cmp     [rdx+rcx*2], di
0x1800428b6  jnz     short loc_1800428AF
0x1800428b8  mov     eax, eax
0x1800428ba  lea     rdx, [rax+rcx]
0x1800428be  cmp     rdx, rax
0x1800428c1  jb      loc_180042AB5
0x1800428c7  cmp     rdx, r15
0x1800428ca  ja      loc_180042AB5
0x1800428d0  mov     r8d, edx
0x1800428d3  mov     rcx, [rsi+40h]
0x1800428d7  mov     rax, r13
0x1800428da  inc     rax
0x1800428dd  cmp     [rcx+rax*2], di
0x1800428e1  jnz     short loc_1800428DA
0x1800428e3  lea     rcx, [r8+rax]
0x1800428e7  cmp     rcx, r8
0x1800428ea  jb      loc_180042AB0
0x1800428f0  cmp     rcx, r15
0x1800428f3  ja      loc_180042AB0
0x1800428f9  mov     ebx, ecx
0x1800428fb  inc     rbx
0x1800428fe  cmp     rbx, r15
0x180042901  ja      loc_180042AAA
0x180042907  mov     rcx, [rsi+30h]; Block
0x18004290b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180042910  mov     [rsi+30h], rdi
0x180042914  mov     ebx, ebx
0x180042916  mov     eax, 2
0x18004291b  mul     rbx
0x18004291e  cmovb   rax, r13
0x180042922  mov     rcx, rax; unsigned __int64
0x180042925  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004292a  mov     rcx, rax; unsigned __int16 *
0x18004292d  mov     [rsi+30h], rax
0x180042931  test    rax, rax
0x180042934  jnz     short loc_180042940
0x180042936  mov     ebx, 8007000Eh
0x18004293b  jmp     loc_180042A83
0x180042940  mov     rax, [rsi+40h]
0x180042944  mov     [rsp+78h+var_58], rax
0x180042949  mov     r9, [rsi+38h]
0x18004294d  mov     r8, [rsp+78h+arg_8]; unsigned __int16 *
0x180042955  mov     rdx, rbx; unsigned __int64
0x180042958  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004295d  mov     ebx, eax
0x18004295f  test    eax, eax
0x180042961  js      loc_180042A83
0x180042967  mov     r14, [rsi+30h]
0x18004296b  jmp     short loc_180042997
0x18004296d  xor     edi, edi
0x18004296f  mov     rsi, [rsp+78h+arg_0]
0x180042977  mov     ebx, dword ptr [rsp+78h+arg_8]
0x18004297e  mov     r12d, edi
0x180042981  jmp     loc_180042A83
0x180042986  lea     r14, ?g_wszSOAP_HEADERS@@3QBGB; "Content-Type: text/xml; charset=utf-8\r"...
0x18004298d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180042991  mov     r15d, 0FFFFFFFFh
0x180042997  cmp     [rsi+90h], edi
0x18004299d  jz      loc_180042A4B
0x1800429a3  lea     r9, aSS_0; "%s%s"
0x1800429aa  mov     [rsp+78h+arg_8], r9
0x1800429b2  mov     rdx, r13
0x1800429b5  inc     rdx
0x1800429b8  cmp     [r14+rdx*2], di
0x1800429bd  jnz     short loc_1800429B5
0x1800429bf  lea     eax, [rdx-2]
0x1800429c2  cmp     word ptr [r14+rax*2], 0Dh
0x1800429c8  jnz     short loc_1800429D8
0x1800429ca  mov     r8, rdi
0x1800429cd  lea     eax, [rdx-1]
0x1800429d0  cmp     word ptr [r14+rax*2], 0Ah
0x1800429d6  jz      short loc_1800429ED
0x1800429d8  lea     rax, aSS; "%s\r\n%s"
0x1800429df  mov     [rsp+78h+arg_8], rax
0x1800429e7  mov     r8d, 2
0x1800429ed  mov     eax, edx
0x1800429ef  lea     rcx, [r8+39h]
0x1800429f3  add     rcx, rax
0x1800429f6  cmp     rcx, r8
0x1800429f9  jb      loc_180042AC0
0x1800429ff  cmp     rcx, r15
0x180042a02  ja      loc_180042AC0
0x180042a08  mov     ebx, ecx
0x180042a0a  mov     eax, 2
0x180042a0f  mul     rbx
0x180042a12  cmovb   rax, r13
0x180042a16  mov     rcx, rax; unsigned __int64
0x180042a19  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180042a1e  mov     r12, rax
0x180042a21  lea     rax, ?g_wszHTTP_ForceCrossTenantActivationYesHeader@@3QBGB; "X-MS-RMS-MSDRM-OPTIONS: ForceCrossTenan"...
0x180042a28  mov     [rsp+78h+var_58], rax
0x180042a2d  mov     r9, r14
0x180042a30  mov     r8, [rsp+78h+arg_8]; unsigned __int16 *
0x180042a38  mov     edx, ebx; unsigned __int64
0x180042a3a  mov     rcx, r12; unsigned __int16 *
0x180042a3d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042a42  mov     ebx, eax
0x180042a44  test    eax, eax
0x180042a46  js      short loc_180042A83
0x180042a48  mov     r14, r12
0x180042a4b  mov     rcx, [rsi+68h]; hRequest
0x180042a4f  mov     r9d, 0A0000000h; dwModifiers
0x180042a55  mov     r8d, r15d; dwHeadersLength
0x180042a58  mov     rdx, r14; lpszHeaders
0x180042a5b  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, edi; int g_fGlobalOptionUseWinhttp
0x180042a61  jz      short loc_180042A6B
0x180042a63  call    cs:__imp_WinHttpAddRequestHeaders
0x180042a69  jmp     short loc_180042A71
0x180042a6b  call    cs:__imp_HttpAddRequestHeadersW
0x180042a71  test    eax, eax
0x180042a73  jnz     short loc_180042A83
0x180042a75  call    cs:__imp_GetLastError
0x180042a7b  mov     [rsi+78h], eax
0x180042a7e  mov     ebx, 8004CF3Bh
0x180042a83  cmp     [rsi+90h], edi
0x180042a89  jz      short loc_180042A98
0x180042a8b  test    r12, r12
0x180042a8e  jz      short loc_180042A98
0x180042a90  mov     rcx, r12; Block
0x180042a93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180042a98  mov     eax, ebx
0x180042a9a  add     rsp, 40h
0x180042a9e  pop     r15
0x180042aa0  pop     r14
0x180042aa2  pop     r13
0x180042aa4  pop     r12
0x180042aa6  pop     rdi
0x180042aa7  pop     rsi
0x180042aa8  pop     rbx
0x180042aa9  retn
0x180042aaa  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180042ab0  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180042ab5  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180042aba  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180042ac0  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
