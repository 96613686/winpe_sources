# UpdateHostNameInUrl(GenericStringHandle<ushort> &,GenericStringHandle<ushort>)

- ea: `0x1800d83e0`
- end: `0x1800d8935`
- name: `?UpdateHostNameInUrl@@YAXAEAV?$GenericStringHandle@G@@V1@@Z`
- size: `1365`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008b9cc`

## callees

- `0x180006640`
- `0x18001d7f0`
- `0x18001d830`
- `0x18003acd8`
- `0x180066e6c`
- `0x1800a1114`
- `0x1800a3de8`
- `0x1800b1160`
- `0x1800d83e0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d856b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d85b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d85bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d85c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d875f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d876a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d877e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d880e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d885d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d856b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d85b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d85bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d85c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d875f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d876a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d877e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d880e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d885d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8867`
- `WINHTTP!WinHttpCrackUrl` at `0x1800d855b`
- `WINHTTP!WinHttpCrackUrl` at `0x1800d855b`
- `WINHTTP!WinHttpCreateUrl` at `0x1800d8751`
- `WINHTTP!WinHttpCreateUrl` at `0x1800d8800`
- `WINHTTP!WinHttpCreateUrl` at `0x1800d8751`
- `WINHTTP!WinHttpCreateUrl` at `0x1800d8800`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UpdateHostNameInUrl(unsigned __int64 **a1, DWORD **a2)
{
  unsigned __int64 v3; // rdx
  unsigned __int64 v5; // r12
  DWORD v6; // r12d
  CHAR *v7; // r14
  CHAR *v8; // r15
  unsigned int LastError; // ecx
  int v10; // r11d
  unsigned int v11; // ecx
  WCHAR *v12; // rbx
  unsigned int v13; // ecx
  void **pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+38h] [rbp-C8h]
  int v16; // [rsp+48h] [rbp-B8h]
  int v17; // [rsp+4Ch] [rbp-B4h]
  int v18; // [rsp+50h] [rbp-B0h]
  CHAR *v19; // [rsp+90h] [rbp-70h] BYREF
  CHAR *v20; // [rsp+98h] [rbp-68h] BYREF
  CHAR *v21; // [rsp+A0h] [rbp-60h] BYREF
  CHAR *v22; // [rsp+A8h] [rbp-58h] BYREF
  CHAR *v23; // [rsp+B0h] [rbp-50h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+C0h] [rbp-40h] BYREF
  DWORD pdwUrlLength; // [rsp+190h] [rbp+90h] BYREF
  WCHAR *v27; // [rsp+198h] [rbp+98h] BYREF

  v3 = *(_QWORD *)*a2;
  if ( v3 )
  {
    v5 = **a1;
    if ( v5 <= v3 )
      LODWORD(v5) = v3;
    if ( (unsigned int)v5 > 0x898 )
    {
      v15 = 0;
      pExceptionObject = &ComError::`vftable';
      v16 = -2147012891;
      v17 = 12045;
      v18 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v6 = v5 + 1;
    v7 = (CHAR *)operator new(saturated_mul(v6, 2u));
    v23 = v7;
    v8 = (CHAR *)operator new(saturated_mul(v6, 2u));
    v22 = v8;
    v21 = (CHAR *)operator new(0x202u);
    v20 = (CHAR *)operator new(0x202u);
    v19 = (CHAR *)operator new(saturated_mul(v6, 2u));
    memset_0(&UrlComponents, 0, sizeof(UrlComponents));
    UrlComponents.dwStructSize = 104;
    UrlComponents.lpszHostName = v7;
    UrlComponents.dwHostNameLength = v6;
    UrlComponents.lpszUrlPath = v8;
    UrlComponents.dwUrlPathLength = v6;
    UrlComponents.lpszUserName = v21;
    UrlComponents.dwUserNameLength = 257;
    UrlComponents.lpszPassword = v20;
    UrlComponents.dwPasswordLength = 257;
    UrlComponents.lpszExtraInfo = v19;
    UrlComponents.dwExtraInfoLength = v6;
    if ( !WinHttpCrackUrl((LPCWSTR)*a1 + 6, 0, 0, &UrlComponents) )
    {
      if ( GetLastError() == 122 )
      {
        v15 = 0;
        pExceptionObject = &ComError::`vftable';
        v16 = -2147012891;
        v17 = 12078;
        v18 = 1;
        throw (ComError *)&pExceptionObject;
      }
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v15 = 0;
      pExceptionObject = &ComError::`vftable';
      v16 = LastError;
      v17 = 12080;
      v18 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( !*(_WORD *)v7 )
    {
      v15 = 0;
      pExceptionObject = &ComError::`vftable';
      v16 = -2147012891;
      v17 = 12085;
      v18 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 293, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v8);
    v10 = StringCchCopyW((unsigned __int16 *)v7, v6, (const unsigned __int16 *)*a2 + 6);
    if ( v10 < 0 )
    {
      v15 = 0;
      pExceptionObject = &ComError::`vftable';
      v16 = v10;
      v17 = 12090;
      v18 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        294,
        (unsigned int)&WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
        (_DWORD)v8,
        (__int64)v7);
    UrlComponents.dwHostNameLength = **a2;
    UrlComponents.lpszUserName = (LPSTR)((__int64)UrlComponents.lpszUserName
                                       & -(__int64)(UrlComponents.dwUserNameLength != 0));
    UrlComponents.lpszPassword = (LPSTR)((__int64)UrlComponents.lpszPassword
                                       & -(__int64)(UrlComponents.dwPasswordLength != 0));
    UrlComponents.lpszExtraInfo = (LPSTR)((__int64)UrlComponents.lpszExtraInfo
                                        & -(__int64)(UrlComponents.dwExtraInfoLength != 0));
    pdwUrlLength = 0;
    if ( WinHttpCreateUrl(&UrlComponents, 0, 0, &pdwUrlLength) )
    {
      v15 = 0;
      pExceptionObject = &ComError::`vftable';
      v16 = -2147012891;
      v17 = 12112;
      v18 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( GetLastError() != 122 )
    {
      if ( (int)GetLastError() > 0 )
        v11 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v11 = GetLastError();
      v15 = 0;
      pExceptionObject = &ComError::`vftable';
      v16 = v11;
      v17 = 12107;
      v18 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v12 = (WCHAR *)operator new(saturated_mul(pdwUrlLength + 1, 2u));
    v27 = v12;
    if ( !WinHttpCreateUrl(&UrlComponents, 0, v12, &pdwUrlLength) )
    {
      if ( GetLastError() == 122 )
      {
        v15 = 0;
        pExceptionObject = &ComError::`vftable';
        v16 = -2147012891;
        v17 = 12121;
        v18 = 1;
        throw (ComError *)&pExceptionObject;
      }
      if ( (int)GetLastError() > 0 )
        v13 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v13 = GetLastError();
      v15 = 0;
      pExceptionObject = &ComError::`vftable';
      v16 = v13;
      v17 = 12123;
      v18 = 1;
      throw (ComError *)&pExceptionObject;
    }
    GenericStringHandle<unsigned short>::operator=(a1, v12);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v27);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v19);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v20);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v21);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v22);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v23);
  }
  return GenericStringHandle<unsigned short>::FreeIt(a2);
}

```

## disassembly

```asm
0x1800d83e0  mov     [rsp-8+arg_8], rdx
0x1800d83e5  mov     [rsp-8+arg_0], rcx
0x1800d83ea  push    rbp
0x1800d83eb  push    rbx
0x1800d83ec  push    rsi
0x1800d83ed  push    rdi
0x1800d83ee  push    r12
0x1800d83f0  push    r13
0x1800d83f2  push    r14
0x1800d83f4  push    r15
0x1800d83f6  lea     rbp, [rsp-38h]
0x1800d83fb  sub     rsp, 138h
0x1800d8402  mov     r13, rdx
0x1800d8405  mov     rax, [rdx]
0x1800d8408  mov     rdx, [rax]
0x1800d840b  test    rdx, rdx
0x1800d840e  jnz     short loc_1800D842C
0x1800d8410  mov     rcx, r13
0x1800d8413  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800d8418  add     rsp, 138h
0x1800d841f  pop     r15
0x1800d8421  pop     r14
0x1800d8423  pop     r13
0x1800d8425  pop     r12
0x1800d8427  pop     rdi
0x1800d8428  pop     rsi
0x1800d8429  pop     rbx
0x1800d842a  pop     rbp
0x1800d842b  retn
0x1800d842c  mov     rax, [rcx]
0x1800d842f  mov     r12, [rax]
0x1800d8432  cmp     r12, rdx
0x1800d8435  cmovbe  r12d, edx
0x1800d8439  cmp     r12d, 898h
0x1800d8440  jbe     short loc_1800D8481
0x1800d8442  xorps   xmm0, xmm0
0x1800d8445  movups  [rsp+170h+var_138], xmm0
0x1800d844a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800d8451  mov     [rsp+170h+pExceptionObject], rax
0x1800d8456  mov     [rsp+170h+var_128], 80072EE5h
0x1800d845e  mov     [rsp+170h+var_124], 2F0Dh
0x1800d8466  mov     edi, 1
0x1800d846b  mov     [rsp+170h+var_120], edi
0x1800d846f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800d8476  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800d847b  call    _CxxThrowException_0
0x1800d8481  inc     r12d
0x1800d8484  mov     ebx, r12d
0x1800d8487  mov     edi, 2
0x1800d848c  mov     eax, edi
0x1800d848e  mul     rbx
0x1800d8491  lea     rsi, [rdi-3]
0x1800d8495  cmovb   rax, rsi
0x1800d8499  mov     rcx, rax; dwBytes
0x1800d849c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d84a1  mov     r14, rax
0x1800d84a4  mov     [rbp+70h+var_C0], rax
0x1800d84a8  mov     eax, edi
0x1800d84aa  mul     rbx
0x1800d84ad  cmovb   rax, rsi
0x1800d84b1  mov     rcx, rax; dwBytes
0x1800d84b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d84b9  mov     r15, rax
0x1800d84bc  mov     [rbp+70h+var_C8], rax
0x1800d84c0  mov     edi, 202h
0x1800d84c5  mov     ecx, edi; dwBytes
0x1800d84c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d84cc  mov     rsi, rax
0x1800d84cf  mov     [rbp+70h+var_D0], rax
0x1800d84d3  mov     ecx, edi; dwBytes
0x1800d84d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d84da  mov     rdi, rax
0x1800d84dd  mov     [rbp+70h+var_D8], rax
0x1800d84e1  mov     eax, 2
0x1800d84e6  mul     rbx
0x1800d84e9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d84f0  cmovb   rax, rcx
0x1800d84f4  mov     rcx, rax; dwBytes
0x1800d84f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d84fc  mov     rbx, rax
0x1800d84ff  mov     [rbp+70h+var_E0], rax
0x1800d8503  xor     edx, edx; Val
0x1800d8505  lea     r8d, [rdx+68h]; Size
0x1800d8509  lea     rcx, [rbp+70h+UrlComponents]; void *
0x1800d850d  call    memset_0
0x1800d8512  mov     [rbp+70h+UrlComponents.dwStructSize], 68h ; 'h'
0x1800d8519  mov     [rbp+70h+UrlComponents.lpszHostName], r14
0x1800d851d  mov     [rbp+70h+UrlComponents.dwHostNameLength], r12d
0x1800d8521  mov     [rbp+70h+UrlComponents.lpszUrlPath], r15
0x1800d8525  mov     [rbp+70h+UrlComponents.dwUrlPathLength], r12d
0x1800d8529  mov     [rbp+70h+UrlComponents.lpszUserName], rsi
0x1800d852d  mov     eax, 101h
0x1800d8532  mov     [rbp+70h+UrlComponents.dwUserNameLength], eax
0x1800d8535  mov     [rbp+70h+UrlComponents.lpszPassword], rdi
0x1800d8539  mov     [rbp+70h+UrlComponents.dwPasswordLength], eax
0x1800d853c  mov     [rbp+70h+UrlComponents.lpszExtraInfo], rbx
0x1800d8540  mov     [rbp+70h+UrlComponents.dwExtraInfoLength], r12d
0x1800d8544  mov     rsi, [rbp+70h+arg_0]
0x1800d854b  mov     rcx, [rsi]
0x1800d854e  add     rcx, 0Ch; pwszUrl
0x1800d8552  lea     r9, [rbp+70h+UrlComponents]; lpUrlComponents
0x1800d8556  xor     r8d, r8d; dwFlags
0x1800d8559  xor     edx, edx; dwUrlLength
0x1800d855b  call    cs:__imp_WinHttpCrackUrl
0x1800d8561  xor     ebx, ebx
0x1800d8563  test    eax, eax
0x1800d8565  jnz     loc_1800D8611
0x1800d856b  call    cs:__imp_GetLastError
0x1800d8571  cmp     eax, 7Ah ; 'z'
0x1800d8574  jnz     short loc_1800D85B3
0x1800d8576  xorps   xmm0, xmm0
0x1800d8579  movups  [rsp+170h+var_138], xmm0
0x1800d857e  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800d8585  mov     [rsp+170h+pExceptionObject], rax
0x1800d858a  mov     [rsp+170h+var_128], 80072EE5h
0x1800d8592  mov     [rsp+170h+var_124], 2F2Eh
0x1800d859a  lea     edi, [rbx+1]
0x1800d859d  mov     [rsp+170h+var_120], edi
0x1800d85a1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800d85a8  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800d85ad  call    _CxxThrowException_0
0x1800d85b3  call    cs:__imp_GetLastError
0x1800d85b9  test    eax, eax
0x1800d85bb  jg      short loc_1800D85C7
0x1800d85bd  call    cs:__imp_GetLastError
0x1800d85c3  mov     ecx, eax
0x1800d85c5  jmp     short loc_1800D85D6
0x1800d85c7  call    cs:__imp_GetLastError
0x1800d85cd  movzx   ecx, ax
0x1800d85d0  or      ecx, 80070000h
0x1800d85d6  xorps   xmm0, xmm0
0x1800d85d9  movups  [rsp+170h+var_138], xmm0
0x1800d85de  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800d85e5  mov     [rsp+170h+pExceptionObject], rax
0x1800d85ea  mov     [rsp+170h+var_128], ecx
0x1800d85ee  mov     [rsp+170h+var_124], 2F30h
0x1800d85f6  mov     edi, 1
0x1800d85fb  mov     [rsp+170h+var_120], edi
0x1800d85ff  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800d8606  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800d860b  call    _CxxThrowException_0
0x1800d8611  mov     edi, 1
0x1800d8616  cmp     [r14], bx
0x1800d861a  jnz     short loc_1800D8656
0x1800d861c  xorps   xmm0, xmm0
0x1800d861f  movups  [rsp+170h+var_138], xmm0
0x1800d8624  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800d862b  mov     [rsp+170h+pExceptionObject], rax
0x1800d8630  mov     [rsp+170h+var_128], 80072EE5h
0x1800d8638  mov     [rsp+170h+var_124], 2F35h
0x1800d8640  mov     [rsp+170h+var_120], edi
0x1800d8644  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800d864b  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800d8650  call    _CxxThrowException_0
0x1800d8656  lea     rax, WPP_GLOBAL_Control
0x1800d865d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8664  cmp     rcx, rax
0x1800d8667  jz      short loc_1800D8687
0x1800d8669  test    [rcx+1Ch], dil
0x1800d866d  jz      short loc_1800D8687
0x1800d866f  mov     edx, 125h
0x1800d8674  mov     r9, r15
0x1800d8677  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x1800d867e  mov     rcx, [rcx+10h]
0x1800d8682  call    WPP_SF_S
0x1800d8687  mov     r8, [r13+0]
0x1800d868b  add     r8, 0Ch; unsigned __int16 *
0x1800d868f  mov     edx, r12d; unsigned __int64
0x1800d8692  mov     rcx, r14; unsigned __int16 *
0x1800d8695  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d869a  mov     r11d, eax
0x1800d869d  test    eax, eax
0x1800d869f  jns     short loc_1800D86D8
0x1800d86a1  xorps   xmm0, xmm0
0x1800d86a4  movups  [rsp+170h+var_138], xmm0
0x1800d86a9  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800d86b0  mov     [rsp+170h+pExceptionObject], rax
0x1800d86b5  mov     [rsp+170h+var_128], r11d
0x1800d86ba  mov     [rsp+170h+var_124], 2F3Ah
0x1800d86c2  mov     [rsp+170h+var_120], edi
0x1800d86c6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800d86cd  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800d86d2  call    _CxxThrowException_0
0x1800d86d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d86df  lea     rax, WPP_GLOBAL_Control
0x1800d86e6  cmp     rcx, rax
0x1800d86e9  jz      short loc_1800D870E
0x1800d86eb  test    [rcx+1Ch], dil
0x1800d86ef  jz      short loc_1800D870E
0x1800d86f1  mov     edx, 126h
0x1800d86f6  mov     [rsp+170h+var_150], r14
0x1800d86fb  mov     r9, r15
0x1800d86fe  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x1800d8705  mov     rcx, [rcx+10h]
0x1800d8709  call    WPP_SF_SS
0x1800d870e  mov     rax, [r13+0]
0x1800d8712  mov     ecx, [rax]
0x1800d8714  mov     [rbp+70h+UrlComponents.dwHostNameLength], ecx
0x1800d8717  mov     eax, [rbp+70h+UrlComponents.dwUserNameLength]
0x1800d871a  neg     eax
0x1800d871c  sbb     rcx, rcx
0x1800d871f  and     [rbp+70h+UrlComponents.lpszUserName], rcx
0x1800d8723  mov     eax, [rbp+70h+UrlComponents.dwPasswordLength]
0x1800d8726  neg     eax
0x1800d8728  sbb     rcx, rcx
0x1800d872b  and     [rbp+70h+UrlComponents.lpszPassword], rcx
0x1800d872f  mov     eax, [rbp+70h+UrlComponents.dwExtraInfoLength]
0x1800d8732  neg     eax
0x1800d8734  sbb     rcx, rcx
0x1800d8737  and     [rbp+70h+UrlComponents.lpszExtraInfo], rcx
0x1800d873b  mov     [rbp+70h+pdwUrlLength], ebx
0x1800d8741  lea     r9, [rbp+70h+pdwUrlLength]; pdwUrlLength
0x1800d8748  xor     r8d, r8d; pwszUrl
0x1800d874b  xor     edx, edx; dwFlags
0x1800d874d  lea     rcx, [rbp+70h+UrlComponents]; lpUrlComponents
0x1800d8751  call    cs:__imp_WinHttpCreateUrl
0x1800d8757  test    eax, eax
0x1800d8759  jnz     loc_1800D88FB
0x1800d875f  call    cs:__imp_GetLastError
0x1800d8765  cmp     eax, 7Ah ; 'z'
0x1800d8768  jz      short loc_1800D87C3
0x1800d876a  call    cs:__imp_GetLastError
0x1800d8770  test    eax, eax
0x1800d8772  jg      short loc_1800D877E
0x1800d8774  call    cs:__imp_GetLastError
0x1800d877a  mov     ecx, eax
0x1800d877c  jmp     short loc_1800D878D
0x1800d877e  call    cs:__imp_GetLastError
0x1800d8784  movzx   ecx, ax
0x1800d8787  or      ecx, 80070000h
0x1800d878d  xorps   xmm0, xmm0
0x1800d8790  movups  [rsp+170h+var_138], xmm0
0x1800d8795  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800d879c  mov     [rsp+170h+pExceptionObject], rax
0x1800d87a1  mov     [rsp+170h+var_128], ecx
0x1800d87a5  mov     [rsp+170h+var_124], 2F4Bh
0x1800d87ad  mov     [rsp+170h+var_120], edi
0x1800d87b1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800d87b8  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800d87bd  call    _CxxThrowException_0
0x1800d87c3  mov     edx, [rbp+70h+pdwUrlLength]
0x1800d87c9  inc     edx
0x1800d87cb  mov     eax, 2
0x1800d87d0  mul     rdx
0x1800d87d3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d87da  cmovb   rax, rcx
0x1800d87de  mov     rcx, rax; dwBytes
0x1800d87e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d87e6  mov     rbx, rax
0x1800d87e9  mov     [rbp+70h+arg_18], rax
0x1800d87f0  lea     r9, [rbp+70h+pdwUrlLength]; pdwUrlLength
0x1800d87f7  mov     r8, rax; pwszUrl
0x1800d87fa  xor     edx, edx; dwFlags
0x1800d87fc  lea     rcx, [rbp+70h+UrlComponents]; lpUrlComponents
0x1800d8800  call    cs:__imp_WinHttpCreateUrl
0x1800d8806  test    eax, eax
0x1800d8808  jnz     loc_1800D88AC
0x1800d880e  call    cs:__imp_GetLastError
0x1800d8814  cmp     eax, 7Ah ; 'z'
0x1800d8817  jnz     short loc_1800D8853
0x1800d8819  xorps   xmm0, xmm0
0x1800d881c  movups  [rsp+170h+var_138], xmm0
0x1800d8821  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800d8828  mov     [rsp+170h+pExceptionObject], rax
0x1800d882d  mov     [rsp+170h+var_128], 80072EE5h
0x1800d8835  mov     [rsp+170h+var_124], 2F59h
0x1800d883d  mov     [rsp+170h+var_120], edi
0x1800d8841  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800d8848  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800d884d  call    _CxxThrowException_0
0x1800d8853  call    cs:__imp_GetLastError
0x1800d8859  test    eax, eax
0x1800d885b  jg      short loc_1800D8867
0x1800d885d  call    cs:__imp_GetLastError
0x1800d8863  mov     ecx, eax
0x1800d8865  jmp     short loc_1800D8876
0x1800d8867  call    cs:__imp_GetLastError
0x1800d886d  movzx   ecx, ax
0x1800d8870  or      ecx, 80070000h
0x1800d8876  xorps   xmm0, xmm0
0x1800d8879  movups  [rsp+170h+var_138], xmm0
0x1800d887e  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800d8885  mov     [rsp+170h+pExceptionObject], rax
0x1800d888a  mov     [rsp+170h+var_128], ecx
0x1800d888e  mov     [rsp+170h+var_124], 2F5Bh
0x1800d8896  mov     [rsp+170h+var_120], edi
0x1800d889a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800d88a1  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800d88a6  call    _CxxThrowException_0
0x1800d88ac  mov     rdx, rbx
0x1800d88af  mov     rcx, rsi
0x1800d88b2  call    ??4?$GenericStringHandle@G@@QEAAXPEBG@Z; GenericStringHandle<ushort>::operator=(ushort const *)
0x1800d88b7  nop
0x1800d88b8  lea     rcx, [rbp+70h+arg_18]; void *
0x1800d88bf  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d88c4  nop
0x1800d88c5  lea     rcx, [rbp+70h+var_E0]; void *
0x1800d88c9  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d88ce  nop
0x1800d88cf  lea     rcx, [rbp+70h+var_D8]; void *
  ... truncated ...
```
