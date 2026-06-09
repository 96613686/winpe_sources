# CDocWrapBase<DocTraitsACP>::CoCreateLocally(_GUID const &,ulong,_GUID const &,IUnknown * *,_GUID const &,IUnknown *,tagVARIANT)

- ea: `0x1800066a0`
- end: `0x180006b5a`
- name: `?CoCreateLocally@?$CDocWrapBase@VDocTraitsACP@@@@UEAAJAEBU_GUID@@K0PEAPEAUIUnknown@@0PEAU3@UtagVARIANT@@@Z`
- size: `1210`
- prototype: `HRESULT __fastcall(__int64, IID *, DWORD, IID *, LPVOID *ppv, __int64, __int64, __int128 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180002dcc`
- `0x180002f60`
- `0x1800036c0`
- `0x180005424`
- `0x180005ae4`
- `0x1800066a0`
- `0x18000c7c8`
- `0x18000c988`
- `0x180012b40`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800067f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800068e1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800068fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800069c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006a32`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006a53`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b26`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b47`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800067f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800068e1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800068fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800069c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006a32`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006a53`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b26`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b47`
- `USER32!CloseDesktop` at `0x18000671a`
- `USER32!CloseDesktop` at `0x18000671a`
- `USER32!OpenInputDesktop` at `0x180006708`
- `USER32!OpenInputDesktop` at `0x180006708`
- `ADVAPI32!GetUserNameW` at `0x1800067db`
- `ADVAPI32!GetUserNameW` at `0x1800067db`
- `api-ms-win-core-com-l1-1-0!CoQueryClientBlanket` at `0x180006743`
- `api-ms-win-core-com-l1-1-0!CoQueryClientBlanket` at `0x180006743`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006a19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006a19`

## pseudocode

```c
HRESULT __fastcall CDocWrapBase<DocTraitsACP>::CoCreateLocally(
        __int64 a1,
        IID *a2,
        DWORD a3,
        IID *a4,
        LPVOID *ppv,
        __int64 a6,
        __int64 a7,
        __int128 *a8)
{
  HDESK v8; // rax
  HRESULT result; // eax
  __int64 v10; // r8
  void **v11; // rcx
  DWORD v12; // eax
  void **v13; // rcx
  WCHAR *v14; // rbx
  void *v15; // rcx
  unsigned __int64 v16; // rax
  void **v17; // rcx
  int v18; // ebx
  void **v19; // rdx
  void *v20; // rdi
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rax
  void **v23; // r8
  __int64 v24; // rdx
  void **v25; // r8
  const wchar_t *v26; // r9
  HRESULT Instance; // ebx
  DWORD pcbBuffer; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwClsContext; // [rsp+50h] [rbp-B0h]
  RPC_AUTHZ_HANDLE pPrivs; // [rsp+58h] [rbp-A8h] BYREF
  IID *riid; // [rsp+60h] [rbp-A0h]
  IID *rclsid; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  void *v37[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v38; // [rsp+98h] [rbp-68h]
  unsigned __int64 v39; // [rsp+A0h] [rbp-60h]
  int v40; // [rsp+A8h] [rbp-58h]
  void *v41[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v42; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v43; // [rsp+C8h] [rbp-38h]
  __int128 v44; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v46; // [rsp+F8h] [rbp-8h]
  void *Src[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v48; // [rsp+110h] [rbp+10h]
  unsigned __int64 v49; // [rsp+118h] [rbp+18h]
  int v50; // [rsp+120h] [rbp+20h]

  riid = a4;
  dwClsContext = a3;
  rclsid = a2;
  v36 = a1;
  v35 = a6;
  v34 = a7;
  v8 = OpenInputDesktop(0, 0, 8u);
  if ( !v8 )
    return -2147024891;
  CloseDesktop(v8);
  pPrivs = 0;
  result = CoQueryClientBlanket(0, 0, 0, 0, 0, &pPrivs, 0);
  if ( result )
    return result;
  v39 = 7;
  v38 = 0;
  LOWORD(v37[0]) = 0;
  v40 = -1;
  LOBYTE(v10) = 1;
  if ( (unsigned __int8)std::wstring::_Grow(v37, 129, v10) )
  {
    v11 = v37;
    if ( v39 >= 8 )
      v11 = (void **)v37[0];
    v38 = 0;
    *(_WORD *)v11 = 0;
  }
  if ( v40 == -1 )
    v12 = v39 + ~(_DWORD)v38;
  else
    v12 = v39 - v40 - 1;
  pcbBuffer = v12;
  v40 = v38;
  v13 = v37;
  if ( v39 >= 8 )
    v13 = (void **)v37[0];
  v14 = (WCHAR *)v13 + v38;
  std::wstring::resize(v37);
  if ( !GetUserNameW(v14, &pcbBuffer) )
  {
    if ( v39 < 8 )
      return -2147024891;
    v15 = v37[0];
LABEL_15:
    operator delete(v15);
    return -2147024891;
  }
  if ( v40 != -1 )
  {
    v16 = pcbBuffer - 1 + v40;
    if ( v38 <= v16 )
      std::wstring::_Xran();
    v17 = v37;
    if ( v39 >= 8 )
      v17 = (void **)v37[0];
    *((_WORD *)v17 + v16) = 0;
    std::wstring::resize(v37);
    v40 = -1;
  }
  TSTR::TSTR((TSTR *)v41, (const unsigned __int16 *)pPrivs);
  v18 = -1;
  if ( (int)std::wstring::find(v41) > 0 )
  {
    v46 = 7;
    v45 = 0;
    LOWORD(v44) = 0;
    std::wstring::assign(&v44);
    v49 = 7;
    v48 = 0;
    LOWORD(Src[0]) = 0;
    std::wstring::assign(Src);
    v50 = -1;
    TSTR::operator=(v41, Src);
    if ( v49 >= 8 )
      operator delete(Src[0]);
    v49 = 7;
    v48 = 0;
    LOWORD(Src[0]) = 0;
    if ( v46 >= 8 )
      operator delete((void *)v44);
  }
  v19 = v37;
  v20 = v37[0];
  v21 = v39;
  if ( v39 >= 8 )
    v19 = (void **)v37[0];
  v22 = v42;
  if ( v42 >= v38 )
    v22 = v38;
  v23 = v41;
  if ( v43 >= 8 )
    v23 = (void **)v41[0];
  if ( v22 )
  {
    while ( *(_WORD *)v23 == *(_WORD *)v19 )
    {
      v23 = (void **)((char *)v23 + 2);
      v19 = (void **)((char *)v19 + 2);
      if ( !--v22 )
        goto LABEL_37;
    }
    v18 = *(_WORD *)v23 < *(_WORD *)v19 ? -1 : 1;
  }
  else
  {
LABEL_37:
    if ( v42 >= v38 )
      v18 = v42 != v38;
  }
  if ( v18 )
  {
    v24 = 6;
    if ( v42 < 6 )
      v24 = v42;
    v25 = v41;
    if ( v43 >= 8 )
      v25 = (void **)v41[0];
    if ( v24 )
    {
      v26 = L"SYSTEM";
      while ( *(_WORD *)v25 == *v26 )
      {
        v25 = (void **)((char *)v25 + 2);
        ++v26;
        if ( !--v24 )
          goto LABEL_48;
      }
      goto LABEL_49;
    }
LABEL_48:
    if ( v42 != 6 )
    {
LABEL_49:
      if ( v43 >= 8 )
      {
        operator delete(v41[0]);
        v21 = v39;
        v20 = v37[0];
      }
      v43 = 7;
      v42 = 0;
      LOWORD(v41[0]) = 0;
      if ( v21 < 8 )
        return -2147024891;
      v15 = v20;
      goto LABEL_15;
    }
  }
  Instance = CoCreateInstance(rclsid, 0, dwClsContext, riid, ppv);
  if ( Instance )
    goto LABEL_55;
  v29 = 0;
  Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*ppv)(*ppv, &IID_ICoCreatedLocally, &v29);
  if ( Instance )
  {
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
LABEL_55:
    if ( v43 >= 8 )
      operator delete(v41[0]);
    v43 = 7;
    v42 = 0;
    LOWORD(v41[0]) = 0;
    if ( v39 >= 8 )
      operator delete(v37[0]);
    return Instance;
  }
  v44 = *a8;
  v45 = *((_QWORD *)a8 + 2);
  Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *))(*(_QWORD *)v29 + 24LL))(
               v29,
               *(_QWORD *)(v36 + 128),
               v35,
               v34,
               &v44);
  if ( Instance )
  {
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    goto LABEL_55;
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v43 >= 8 )
    operator delete(v41[0]);
  v43 = 7;
  v42 = 0;
  LOWORD(v41[0]) = 0;
  if ( v39 >= 8 )
    operator delete(v37[0]);
  return 0;
}

```

## disassembly

```asm
0x1800066a0  push    rbp
0x1800066a2  push    rbx
0x1800066a3  push    rsi
0x1800066a4  push    rdi
0x1800066a5  push    r12
0x1800066a7  push    r13
0x1800066a9  push    r15
0x1800066ab  lea     rbp, [rsp-30h]
0x1800066b0  sub     rsp, 130h
0x1800066b7  mov     rax, cs:__security_cookie
0x1800066be  xor     rax, rsp
0x1800066c1  mov     [rbp+60h+var_38], rax
0x1800066c5  mov     [rsp+160h+riid], r9
0x1800066ca  mov     [rsp+160h+dwClsContext], r8d
0x1800066cf  mov     [rsp+160h+rclsid], rdx
0x1800066d4  mov     [rbp+60h+var_E0], rcx
0x1800066d8  mov     r12, [rbp+60h+ppv]
0x1800066df  mov     rax, [rbp+60h+arg_28]
0x1800066e6  mov     [rsp+160h+var_E8], rax
0x1800066eb  mov     rax, [rbp+60h+arg_30]
0x1800066f2  mov     [rsp+160h+var_F0], rax
0x1800066f7  mov     r13, [rbp+60h+arg_38]
0x1800066fe  xor     edi, edi
0x180006700  xor     edx, edx; fInherit
0x180006702  xor     ecx, ecx; dwFlags
0x180006704  lea     r8d, [rdi+8]; dwDesiredAccess
0x180006708  call    cs:__imp_OpenInputDesktop
0x18000670e  test    rax, rax
0x180006711  jz      loc_1800067F6
0x180006717  mov     rcx, rax; hDesktop
0x18000671a  call    cs:__imp_CloseDesktop
0x180006720  mov     [rsp+160h+var_108], rdi
0x180006725  mov     [rsp+160h+pCapabilities], rdi; pCapabilities
0x18000672a  lea     rax, [rsp+160h+var_108]
0x18000672f  mov     [rsp+160h+pPrivs], rax; pPrivs
0x180006734  mov     [rsp+160h+pImpLevel], rdi; pImpLevel
0x180006739  xor     r9d, r9d; pAuthnLevel
0x18000673c  xor     r8d, r8d; pServerPrincName
0x18000673f  xor     edx, edx; pAuthzSvc
0x180006741  xor     ecx, ecx; pAuthnSvc
0x180006743  call    cs:__imp_CoQueryClientBlanket
0x180006749  test    eax, eax
0x18000674b  jnz     loc_1800067FB
0x180006751  lea     esi, [rdi+7]
0x180006754  mov     [rbp+60h+var_C0], rsi
0x180006758  mov     [rbp+60h+var_C8], rdi
0x18000675c  mov     word ptr [rbp+60h+var_D8], di
0x180006760  or      r15d, 0FFFFFFFFh
0x180006764  mov     [rbp+60h+var_B8], r15d
0x180006768  mov     r8b, 1
0x18000676b  lea     edx, [rsi+7Ah]
0x18000676e  lea     rcx, [rbp+60h+var_D8]
0x180006772  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180006777  test    al, al
0x180006779  jz      short loc_180006790
0x18000677b  lea     rcx, [rbp+60h+var_D8]
0x18000677f  cmp     [rbp+60h+var_C0], 8
0x180006784  cmovnb  rcx, [rbp+60h+var_D8]
0x180006789  mov     [rbp+60h+var_C8], rdi
0x18000678d  mov     [rcx], di
0x180006790  mov     ecx, dword ptr [rbp+60h+var_C8]
0x180006793  cmp     [rbp+60h+var_B8], r15d
0x180006797  jnz     short loc_1800067A2
0x180006799  mov     eax, ecx
0x18000679b  not     eax
0x18000679d  add     eax, dword ptr [rbp+60h+var_C0]
0x1800067a0  jmp     short loc_1800067AA
0x1800067a2  mov     eax, dword ptr [rbp+60h+var_C0]
0x1800067a5  sub     eax, [rbp+60h+var_B8]
0x1800067a8  dec     eax
0x1800067aa  mov     [rsp+160h+pcbBuffer], eax
0x1800067ae  mov     [rbp+60h+var_B8], ecx
0x1800067b1  lea     rcx, [rbp+60h+var_D8]
0x1800067b5  mov     rdx, [rbp+60h+var_C0]
0x1800067b9  cmp     rdx, 8
0x1800067bd  cmovnb  rcx, [rbp+60h+var_D8]
0x1800067c2  mov     rax, [rbp+60h+var_C8]
0x1800067c6  lea     rbx, [rcx+rax*2]
0x1800067ca  lea     rcx, [rbp+60h+var_D8]
0x1800067ce  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::resize(unsigned __int64)
0x1800067d3  lea     rdx, [rsp+160h+pcbBuffer]; pcbBuffer
0x1800067d8  mov     rcx, rbx; lpBuffer
0x1800067db  call    cs:__imp_GetUserNameW
0x1800067e1  test    eax, eax
0x1800067e3  jnz     short loc_180006819
0x1800067e5  cmp     [rbp+60h+var_C0], 8
0x1800067ea  jb      short loc_1800067F6
0x1800067ec  mov     rcx, [rbp+60h+var_D8]
0x1800067f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800067f6  mov     eax, 80070005h
0x1800067fb  mov     rcx, [rbp+60h+var_38]
0x1800067ff  xor     rcx, rsp; StackCookie
0x180006802  call    __security_check_cookie
0x180006807  add     rsp, 130h
0x18000680e  pop     r15
0x180006810  pop     r13
0x180006812  pop     r12
0x180006814  pop     rdi
0x180006815  pop     rsi
0x180006816  pop     rbx
0x180006817  pop     rbp
0x180006818  retn
0x180006819  mov     ecx, [rbp+60h+var_B8]
0x18000681c  cmp     ecx, r15d
0x18000681f  jz      short loc_180006859
0x180006821  mov     edx, [rsp+160h+pcbBuffer]
0x180006825  dec     edx
0x180006827  lea     eax, [rdx+rcx]
0x18000682a  mov     r8d, eax
0x18000682d  cmp     [rbp+60h+var_C8], r8
0x180006831  jbe     loc_180006B54
0x180006837  lea     rcx, [rbp+60h+var_D8]
0x18000683b  cmp     [rbp+60h+var_C0], 8
0x180006840  cmovnb  rcx, [rbp+60h+var_D8]
0x180006845  mov     [rcx+rax*2], di
0x180006849  add     edx, [rbp+60h+var_B8]
0x18000684c  lea     rcx, [rbp+60h+var_D8]
0x180006850  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::resize(unsigned __int64)
0x180006855  mov     [rbp+60h+var_B8], r15d
0x180006859  mov     rdx, [rsp+160h+var_108]; Src
0x18000685e  lea     rcx, [rbp+60h+var_B0]; this
0x180006862  call    ??0TSTR@@QEAA@PEBG@Z; TSTR::TSTR(ushort const *)
0x180006867  nop
0x180006868  lea     rcx, [rbp+60h+var_B0]
0x18000686c  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find(ushort const *,unsigned __int64)
0x180006871  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006875  test    eax, eax
0x180006877  jle     loc_180006905
0x18000687d  mov     [rbp+60h+var_68], rsi
0x180006881  mov     [rbp+60h+var_70], rdi
0x180006885  mov     word ptr [rbp+60h+var_80], di
0x180006889  movsxd  rcx, eax
0x18000688c  mov     r9, [rbp+60h+var_A0]
0x180006890  sub     r9, rcx
0x180006893  inc     eax
0x180006895  movsxd  r8, eax
0x180006898  lea     rdx, [rbp+60h+var_B0]
0x18000689c  lea     rcx, [rbp+60h+var_80]; void *
0x1800068a0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800068a5  nop
0x1800068a6  mov     [rbp+60h+var_48], rsi
0x1800068aa  mov     [rbp+60h+var_50], rdi
0x1800068ae  mov     word ptr [rbp+60h+Src], di
0x1800068b2  mov     r9, rbx
0x1800068b5  xor     r8d, r8d
0x1800068b8  lea     rdx, [rbp+60h+var_80]
0x1800068bc  lea     rcx, [rbp+60h+Src]; void *
0x1800068c0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800068c5  mov     [rbp+60h+var_40], r15d
0x1800068c9  lea     rdx, [rbp+60h+Src]; Src
0x1800068cd  lea     rcx, [rbp+60h+var_B0]; void *
0x1800068d1  call    ??4TSTR@@QEAAAEAV0@$$QEAV0@@Z; TSTR::operator=(TSTR &&)
0x1800068d6  cmp     [rbp+60h+var_48], 8
0x1800068db  jb      short loc_1800068E7
0x1800068dd  mov     rcx, [rbp+60h+Src]
0x1800068e1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800068e7  mov     [rbp+60h+var_48], rsi
0x1800068eb  mov     [rbp+60h+var_50], rdi
0x1800068ef  mov     word ptr [rbp+60h+Src], di
0x1800068f3  cmp     [rbp+60h+var_68], 8
0x1800068f8  jb      short loc_180006905
0x1800068fa  mov     rcx, qword ptr [rbp+60h+var_80]
0x1800068fe  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006904  nop
0x180006905  lea     rdx, [rbp+60h+var_D8]
0x180006909  mov     rdi, [rbp+60h+var_D8]
0x18000690d  mov     rsi, [rbp+60h+var_C0]
0x180006911  cmp     rsi, 8
0x180006915  cmovnb  rdx, rdi
0x180006919  mov     r11, [rbp+60h+var_C8]
0x18000691d  mov     rcx, [rbp+60h+var_A0]
0x180006921  mov     rax, rcx
0x180006924  cmp     rcx, r11
0x180006927  cmovnb  rax, r11
0x18000692b  lea     r8, [rbp+60h+var_B0]
0x18000692f  mov     r15, [rbp+60h+var_B0]
0x180006933  cmp     [rbp+60h+var_98], 8
0x180006938  cmovnb  r8, r15
0x18000693c  test    rax, rax
0x18000693f  jz      short loc_18000695D
0x180006941  movzx   r9d, word ptr [r8]
0x180006945  cmp     r9w, [rdx]
0x180006949  jnz     loc_1800069F7
0x18000694f  add     r8, 2
0x180006953  add     rdx, 2
0x180006957  sub     rax, 1
0x18000695b  jnz     short loc_180006941
0x18000695d  cmp     rcx, r11
0x180006960  jb      short loc_18000696C
0x180006962  xor     eax, eax
0x180006964  cmp     rcx, r11
0x180006967  setnz   al
0x18000696a  mov     ebx, eax
0x18000696c  test    ebx, ebx
0x18000696e  jz      loc_180006A03
0x180006974  mov     edx, 6
0x180006979  cmp     rcx, rdx
0x18000697c  cmovb   rdx, rcx
0x180006980  lea     r8, [rbp+60h+var_B0]
0x180006984  cmp     [rbp+60h+var_98], 8
0x180006989  cmovnb  r8, r15
0x18000698d  test    rdx, rdx
0x180006990  jz      short loc_1800069B1
0x180006992  lea     r9, aSystem; "SYSTEM"
0x180006999  movzx   eax, word ptr [r9]
0x18000699d  cmp     [r8], ax
0x1800069a1  jnz     short loc_1800069B7
0x1800069a3  add     r8, 2
0x1800069a7  add     r9, 2
0x1800069ab  sub     rdx, 1
0x1800069af  jnz     short loc_180006999
0x1800069b1  cmp     rcx, 6
0x1800069b5  jz      short loc_180006A03
0x1800069b7  cmp     [rbp+60h+var_98], 8
0x1800069bc  jb      short loc_1800069CF
0x1800069be  mov     rcx, r15
0x1800069c1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800069c7  mov     rsi, [rbp+60h+var_C0]
0x1800069cb  mov     rdi, [rbp+60h+var_D8]
0x1800069cf  mov     [rbp+60h+var_98], 7
0x1800069d7  mov     [rbp+60h+var_A0], 0
0x1800069df  xor     eax, eax
0x1800069e1  mov     word ptr [rbp+60h+var_B0], ax
0x1800069e5  cmp     rsi, 8
0x1800069e9  jb      loc_1800067F6
0x1800069ef  mov     rcx, rdi
0x1800069f2  jmp     loc_1800067F0
0x1800069f7  sbb     ebx, ebx
0x1800069f9  and     ebx, 0FFFFFFFEh
0x1800069fc  inc     ebx
0x1800069fe  jmp     loc_18000696C
0x180006a03  mov     [rsp+160h+pImpLevel], r12; ppv
0x180006a08  mov     r9, [rsp+160h+riid]; riid
0x180006a0d  mov     r8d, [rsp+160h+dwClsContext]; dwClsContext
0x180006a12  xor     edx, edx; pUnkOuter
0x180006a14  mov     rcx, [rsp+160h+rclsid]; rclsid
0x180006a19  call    cs:__imp_CoCreateInstance
0x180006a1f  mov     ebx, eax
0x180006a21  xor     edi, edi
0x180006a23  test    eax, eax
0x180006a25  jz      short loc_180006A60
0x180006a27  cmp     [rbp+60h+var_98], 8
0x180006a2c  jb      short loc_180006A38
0x180006a2e  mov     rcx, [rbp+60h+var_B0]
0x180006a32  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006a38  mov     [rbp+60h+var_98], 7
0x180006a40  mov     [rbp+60h+var_A0], rdi
0x180006a44  mov     word ptr [rbp+60h+var_B0], di
0x180006a48  cmp     [rbp+60h+var_C0], 8
0x180006a4d  jb      short loc_180006A59
0x180006a4f  mov     rcx, [rbp+60h+var_D8]
0x180006a53  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006a59  mov     eax, ebx
0x180006a5b  jmp     loc_1800067FB
0x180006a60  mov     [rsp+160h+var_118], rdi
0x180006a65  mov     rcx, [r12]
0x180006a69  mov     rax, [rcx]
0x180006a6c  lea     r8, [rsp+160h+var_118]
0x180006a71  lea     rdx, IID_ICoCreatedLocally
0x180006a78  mov     rax, [rax]
0x180006a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a80  mov     ebx, eax
0x180006a82  test    eax, eax
0x180006a84  jz      short loc_180006A9F
0x180006a86  mov     rcx, [rsp+160h+var_118]
0x180006a8b  test    rcx, rcx
0x180006a8e  jz      short loc_180006A9D
0x180006a90  mov     rdx, [rcx]
0x180006a93  mov     rax, [rdx+10h]
0x180006a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9c  nop
0x180006a9d  jmp     short loc_180006A27
0x180006a9f  mov     rcx, [rsp+160h+var_118]
0x180006aa4  movups  xmm0, xmmword ptr [r13+0]
0x180006aa9  movaps  [rbp+60h+var_80], xmm0
0x180006aad  movsd   xmm1, qword ptr [r13+10h]
0x180006ab3  movsd   [rbp+60h+var_70], xmm1
0x180006ab8  mov     rax, [rcx]
0x180006abb  lea     rdx, [rbp+60h+var_80]
0x180006abf  mov     [rsp+160h+pImpLevel], rdx
0x180006ac4  mov     r9, [rsp+160h+var_F0]
0x180006ac9  mov     r8, [rsp+160h+var_E8]
0x180006ace  mov     rdx, [rbp+60h+var_E0]
0x180006ad2  mov     rdx, [rdx+80h]
0x180006ad9  mov     rax, [rax+18h]
0x180006add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae2  mov     ebx, eax
0x180006ae4  test    eax, eax
0x180006ae6  jz      short loc_180006B04
0x180006ae8  mov     rcx, [rsp+160h+var_118]
0x180006aed  test    rcx, rcx
0x180006af0  jz      short loc_180006AFF
0x180006af2  mov     rdx, [rcx]
0x180006af5  mov     rax, [rdx+10h]
0x180006af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006afe  nop
0x180006aff  jmp     loc_180006A27
0x180006b04  mov     rcx, [rsp+160h+var_118]
0x180006b09  test    rcx, rcx
0x180006b0c  jz      short loc_180006B1B
  ... truncated ...
```
