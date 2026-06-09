# DavHttpOpenRequest2

- ea: `0x180006600`
- end: `0x18000691d`
- name: `DavHttpOpenRequest2`
- size: `797`
- prototype: `__int64 __fastcall(HINTERNET hInternet, void *, __int64, __int64, int, int, int, int, int, int, int, int, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180005a50`

## callees

- `0x180006600`
- `0x180007450`
- `0x180010c88`
- `0x1800118a4`
- `0x180011938`
- `0x180011a68`
- `0x180011eb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006846`
- `KERNEL32!LocalAlloc` at `0x1800066e0`
- `KERNEL32!LocalAlloc` at `0x1800066e0`
- `KERNEL32!LocalFree` at `0x1800068ae`
- `KERNEL32!LocalFree` at `0x1800068ae`
- `DAVHLPR!DavUrlEncodeNtPath` at `0x1800066c0`
- `DAVHLPR!DavUrlEncodeNtPath` at `0x18000674e`
- `DAVHLPR!DavUrlEncodeNtPath` at `0x1800066c0`
- `DAVHLPR!DavUrlEncodeNtPath` at `0x18000674e`
- `WINHTTP!WinHttpOpenRequest` at `0x180006822`
- `WINHTTP!WinHttpOpenRequest` at `0x180006822`

## pseudocode

```c
__int64 __fastcall DavHttpOpenRequest2(
        HINTERNET hInternet,
        void *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        __int64 a13,
        _QWORD *a14)
{
  void *v15; // r12
  WCHAR *v16; // rbx
  unsigned int v17; // edi
  DWORD v18; // esi
  WCHAR *v19; // rax
  DWORD LastError; // eax
  const WCHAR *v21; // rsi
  void *v22; // rax
  int v23; // edx
  int v24; // r8d
  __int64 v26; // [rsp+40h] [rbp-288h] BYREF
  void *v27; // [rsp+48h] [rbp-280h]
  WCHAR *v28; // [rsp+50h] [rbp-278h]
  HINTERNET hConnect; // [rsp+58h] [rbp-270h]
  __int64 v30; // [rsp+60h] [rbp-268h]
  _QWORD *v31; // [rsp+68h] [rbp-260h]
  int v32; // [rsp+70h] [rbp-258h]
  wchar_t v33; // [rsp+74h] [rbp-254h]
  _BYTE v34[528]; // [rsp+80h] [rbp-248h] BYREF

  hConnect = a2;
  v30 = a13;
  v31 = a14;
  v15 = 0;
  v27 = 0;
  v16 = 0;
  v28 = 0;
  v26 = 259;
  v32 = *(_DWORD *)L"--";
  v33 = asc_18001514C[2];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, L"DavDoesServerDoDav");
  v17 = 1;
  v18 = DavUrlEncodeNtPath(L"/", 1, v34, &v26);
  if ( v18 == 122 )
  {
    v19 = (WCHAR *)LocalAlloc(0, 2 * v26 + 2);
    v16 = v19;
    v28 = v19;
    if ( !v19 )
    {
      LastError = GetLastError();
      v18 = LastError;
      v17 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids,
          (unsigned int)L"DavDoesServerDoDav",
          LastError);
      goto LABEL_22;
    }
    v18 = DavUrlEncodeNtPath(L"/", 1, v19, &v26);
  }
  if ( v18 )
  {
    v17 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids,
        (unsigned int)L"DavDoesServerDoDav",
        v18);
  }
  else
  {
    v21 = (const WCHAR *)v34;
    if ( v16 )
      v21 = v16;
    v21[v26] = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SSSsd(*((_QWORD *)WPP_GLOBAL_Control + 2), a12, (unsigned int)"NO", (unsigned int)L"DavDoesServerDoDav");
    v22 = WinHttpOpenRequest(hConnect, L"OPTIONS", v21, L"HTTP/1.1", 0, 0, a12 != 0 ? 0x800000 : 0);
    v15 = v22;
    v27 = v22;
    if ( v22 )
      DavSetProxy(hInternet, v22);
    v18 = GetLastError();
  }
LABEL_22:
  if ( v16 )
    LocalFree(v16);
  if ( a14 )
    *a14 = v15;
  SetLastError(v18);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SlD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v24, (unsigned int)L"DavDoesServerDoDav", v17, v18);
  return v17;
}

```

## disassembly

```asm
0x180006600  mov     [rsp+arg_10], rbx
0x180006605  mov     [rsp+arg_18], rsi
0x18000660a  push    rdi
0x18000660b  push    r12
0x18000660d  push    r13
0x18000660f  push    r14
0x180006611  push    r15
0x180006613  sub     rsp, 2A0h
0x18000661a  mov     rax, cs:__security_cookie
0x180006621  xor     rax, rsp
0x180006624  mov     [rsp+2C8h+var_38], rax
0x18000662c  mov     [rsp+2C8h+hConnect], rdx
0x180006631  mov     r13, rcx
0x180006634  mov     rax, [rsp+2C8h+arg_60]
0x18000663c  mov     [rsp+2C8h+var_268], rax
0x180006641  mov     r15, [rsp+2C8h+arg_68]
0x180006649  mov     [rsp+2C8h+var_260], r15
0x18000664e  xor     r12d, r12d
0x180006651  mov     [rsp+2C8h+var_280], r12
0x180006656  xor     ebx, ebx
0x180006658  mov     [rsp+2C8h+var_278], rbx
0x18000665d  mov     [rsp+2C8h+var_288], 103h
0x180006666  mov     eax, dword ptr cs:asc_18001514C; "--"
0x18000666c  mov     [rsp+2C8h+var_258], eax
0x180006670  movzx   eax, word ptr cs:asc_18001514C+4; ""
0x180006677  mov     [rsp+2C8h+var_254], ax
0x18000667c  lea     r14, WPP_GLOBAL_Control
0x180006683  mov     rcx, cs:WPP_GLOBAL_Control
0x18000668a  cmp     rcx, r14
0x18000668d  jz      short loc_1800066A5
0x18000668f  test    byte ptr [rcx+1Ch], 2
0x180006693  jz      short loc_1800066A5
0x180006695  lea     r9, aDavdoesserverd; "DavDoesServerDoDav"
0x18000669c  mov     rcx, [rcx+10h]
0x1800066a0  call    WPP_SF_SSS
0x1800066a5  lea     r9, [rsp+2C8h+var_288]
0x1800066aa  lea     r8, [rsp+2C8h+var_248]
0x1800066b2  mov     edi, 1
0x1800066b7  mov     edx, edi
0x1800066b9  lea     rcx, asc_180015154; "/"
0x1800066c0  call    cs:__imp_DavUrlEncodeNtPath
0x1800066c6  mov     esi, eax
0x1800066c8  cmp     eax, 7Ah ; 'z'
0x1800066cb  jnz     loc_180006756
0x1800066d1  mov     rdx, [rsp+2C8h+var_288]
0x1800066d6  lea     rdx, ds:2[rdx*2]; uBytes
0x1800066de  xor     ecx, ecx; uFlags
0x1800066e0  call    cs:__imp_LocalAlloc
0x1800066e6  mov     rbx, rax
0x1800066e9  mov     [rsp+2C8h+var_278], rax
0x1800066ee  test    rax, rax
0x1800066f1  jnz     short loc_18000673C
0x1800066f3  call    cs:__imp_GetLastError
0x1800066f9  mov     esi, eax
0x1800066fb  xor     edi, edi
0x1800066fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006704  cmp     rcx, r14
0x180006707  jz      loc_1800068A6
0x18000670d  test    byte ptr [rcx+1Ch], 1
0x180006711  jz      loc_1800068A6
0x180006717  mov     edx, 0Bh
0x18000671c  mov     dword ptr [rsp+2C8h+pwszReferrer], eax
0x180006720  lea     r9, aDavdoesserverd; "DavDoesServerDoDav"
0x180006727  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18000672e  mov     rcx, [rcx+10h]
0x180006732  call    WPP_SF_Sd
0x180006737  jmp     loc_1800068A6
0x18000673c  lea     r9, [rsp+2C8h+var_288]
0x180006741  mov     r8, rax
0x180006744  mov     rdx, rdi
0x180006747  lea     rcx, asc_180015154; "/"
0x18000674e  call    cs:__imp_DavUrlEncodeNtPath
0x180006754  mov     esi, eax
0x180006756  test    esi, esi
0x180006758  jz      short loc_180006781
0x18000675a  xor     edi, edi
0x18000675c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006763  cmp     rcx, r14
0x180006766  jz      loc_1800068A6
0x18000676c  test    byte ptr [rcx+1Ch], 1
0x180006770  jz      loc_1800068A6
0x180006776  mov     edx, 0Ch
0x18000677b  mov     dword ptr [rsp+2C8h+pwszReferrer], esi
0x18000677f  jmp     short loc_180006720
0x180006781  lea     rsi, [rsp+2C8h+var_248]
0x180006789  test    rbx, rbx
0x18000678c  cmovnz  rsi, rbx
0x180006790  xor     ecx, ecx
0x180006792  mov     rax, [rsp+2C8h+var_288]
0x180006797  mov     [rsi+rax*2], cx
0x18000679b  mov     edx, [rsp+2C8h+arg_58]
0x1800067a2  mov     eax, edx
0x1800067a4  neg     eax
0x1800067a6  sbb     r12d, r12d
0x1800067a9  and     r12d, 800000h
0x1800067b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067b7  cmp     rcx, r14
0x1800067ba  jz      short loc_1800067F5
0x1800067bc  test    byte ptr [rcx+1Ch], 1
0x1800067c0  jz      short loc_1800067F5
0x1800067c2  lea     r8, aNo; "NO"
0x1800067c9  lea     rax, aYes; "YES"
0x1800067d0  test    edx, edx
0x1800067d2  cmovz   rax, r8
0x1800067d6  mov     [rsp+2C8h+var_290], r12d
0x1800067db  mov     qword ptr [rsp+2C8h+dwFlags], rax
0x1800067e0  mov     [rsp+2C8h+ppwszAcceptTypes], rsi
0x1800067e5  lea     r9, aDavdoesserverd; "DavDoesServerDoDav"
0x1800067ec  mov     rcx, [rcx+10h]
0x1800067f0  call    WPP_SF_SSSsd
0x1800067f5  mov     [rsp+2C8h+dwFlags], r12d; dwFlags
0x1800067fa  mov     [rsp+2C8h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x180006803  mov     [rsp+2C8h+pwszReferrer], 0; pwszReferrer
0x18000680c  lea     r9, aHttp11; "HTTP/1.1"
0x180006813  mov     r8, rsi; pwszObjectName
0x180006816  lea     rdx, pwszVerb; "OPTIONS"
0x18000681d  mov     rcx, [rsp+2C8h+hConnect]; hConnect
0x180006822  call    cs:__imp_WinHttpOpenRequest
0x180006828  mov     r12, rax
0x18000682b  mov     [rsp+2C8h+var_280], rax
0x180006830  test    rax, rax
0x180006833  jz      short loc_180006846
0x180006835  mov     r8, [rsp+2C8h+var_268]
0x18000683a  mov     rdx, rax; HINTERNET
0x18000683d  mov     rcx, r13; hInternet
0x180006840  call    DavSetProxy
0x180006845  nop
0x180006846  call    cs:__imp_GetLastError
0x18000684c  mov     esi, eax
0x18000684e  jmp     short loc_1800068A6
0x180006850  xor     edi, edi
0x180006852  mov     esi, 8
0x180006857  lea     rax, WPP_GLOBAL_Control
0x18000685e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006865  cmp     rcx, rax
0x180006868  jz      short loc_180006890
0x18000686a  test    byte ptr [rcx+1Ch], 1
0x18000686e  jz      short loc_180006890
0x180006870  mov     edx, 0Eh
0x180006875  mov     dword ptr [rsp+2C8h+pwszReferrer], esi
0x180006879  lea     r9, aDavdoesserverd; "DavDoesServerDoDav"
0x180006880  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180006887  mov     rcx, [rcx+10h]
0x18000688b  call    WPP_SF_Sd
0x180006890  lea     r14, WPP_GLOBAL_Control
0x180006897  mov     r12, [rsp+2C8h+var_280]
0x18000689c  mov     rbx, [rsp+2C8h+var_278]
0x1800068a1  mov     r15, [rsp+2C8h+var_260]
0x1800068a6  test    rbx, rbx
0x1800068a9  jz      short loc_1800068B4
0x1800068ab  mov     rcx, rbx; hMem
0x1800068ae  call    cs:__imp_LocalFree
0x1800068b4  test    r15, r15
0x1800068b7  jz      short loc_1800068BC
0x1800068b9  mov     [r15], r12
0x1800068bc  mov     ecx, esi; dwErrCode
0x1800068be  call    cs:__imp_SetLastError
0x1800068c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068cb  cmp     rcx, r14
0x1800068ce  jz      short loc_1800068EE
0x1800068d0  test    byte ptr [rcx+1Ch], 2
0x1800068d4  jz      short loc_1800068EE
0x1800068d6  mov     dword ptr [rsp+2C8h+ppwszAcceptTypes], esi
0x1800068da  mov     dword ptr [rsp+2C8h+pwszReferrer], edi
0x1800068de  lea     r9, aDavdoesserverd; "DavDoesServerDoDav"
0x1800068e5  mov     rcx, [rcx+10h]
0x1800068e9  call    WPP_SF_SlD
0x1800068ee  mov     eax, edi
0x1800068f0  mov     rcx, [rsp+2C8h+var_38]
0x1800068f8  xor     rcx, rsp; StackCookie
0x1800068fb  call    __security_check_cookie
0x180006900  lea     r11, [rsp+2C8h+var_28]
0x180006908  mov     rbx, [r11+40h]
0x18000690c  mov     rsi, [r11+48h]
0x180006910  mov     rsp, r11
0x180006913  pop     r15
0x180006915  pop     r14
0x180006917  pop     r13
0x180006919  pop     r12
0x18000691b  pop     rdi
0x18000691c  retn
0x180012080  push    rbp
0x180012082  sub     rsp, 40h
0x180012086  mov     rbp, rdx
0x180012089  mov     rax, [rcx]
0x18001208c  xor     ecx, ecx
0x18001208e  cmp     dword ptr [rax], 0C0000017h
0x180012094  setz    cl
0x180012097  mov     eax, ecx
0x180012099  add     rsp, 40h
0x18001209d  pop     rbp
0x18001209e  retn
```
