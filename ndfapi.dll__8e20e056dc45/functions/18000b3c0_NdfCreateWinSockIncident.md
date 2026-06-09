# NdfCreateWinSockIncident

- ea: `0x18000b3c0`
- end: `0x18000b80a`
- name: `NdfCreateWinSockIncident`
- size: `1098`
- prototype: `HRESULT __stdcall(SOCKET sock, LPCWSTR host, USHORT port, LPCWSTR appId, SID *userId, NDFHANDLE *handle)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000721c`
- `0x180008f1c`
- `0x1800098b0`
- `0x18000a9e0`
- `0x18000b3c0`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b7bc`
- `KERNEL32!GetLastError` at `0x18000b7bc`
- `KERNEL32!GetModuleFileNameW` at `0x18000b753`
- `KERNEL32!GetModuleFileNameW` at `0x18000b753`
- `ole32!CoTaskMemFree` at `0x18000b7d7`
- `ole32!CoTaskMemFree` at `0x18000b7d7`
- `wdi!WdiCancel` at `0x18000b43b`
- `wdi!WdiCancel` at `0x18000b43b`
- `WS2_32!__imp_getpeername` at `0x18000b5cc`
- `WS2_32!__imp_getpeername` at `0x18000b5cc`
- `WS2_32!__imp_getsockname` at `0x18000b520`
- `WS2_32!__imp_getsockname` at `0x18000b520`
- `WS2_32!__imp_getsockopt` at `0x18000b4c1`
- `WS2_32!__imp_getsockopt` at `0x18000b4c1`
- `WS2_32!__imp_WSAGetLastError` at `0x18000b4cb`
- `WS2_32!__imp_WSAGetLastError` at `0x18000b52a`
- `WS2_32!__imp_WSAGetLastError` at `0x18000b5d6`
- `WS2_32!__imp_WSAGetLastError` at `0x18000b4cb`
- `WS2_32!__imp_WSAGetLastError` at `0x18000b52a`
- `WS2_32!__imp_WSAGetLastError` at `0x18000b5d6`

## string_xrefs

- `0x18000b3f9`: `NdfCreateWinSockIncident`
- `0x18000b4e8`: `protocol`

## pseudocode

```c
HRESULT __stdcall NdfCreateWinSockIncident(
        SOCKET sock,
        LPCWSTR host,
        USHORT port,
        LPCWSTR appId,
        SID *userId,
        NDFHANDLE *handle)
{
  int Error; // eax
  HRESULT SID; // ebx
  int v12; // eax
  DWORD v13; // edx
  int v14; // eax
  __int64 v15; // r8
  LPCWSTR v16; // rax
  int namelen; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h]
  __int64 v20; // [rsp+50h] [rbp-B0h]
  struct sockaddr v21; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v22; // [rsp+70h] [rbp-90h]
  __int128 v23; // [rsp+80h] [rbp-80h]
  __int128 v24; // [rsp+90h] [rbp-70h]
  __int128 v25; // [rsp+A0h] [rbp-60h]
  __int128 v26; // [rsp+B0h] [rbp-50h]
  __int128 v27; // [rsp+C0h] [rbp-40h]
  __int128 v28; // [rsp+D0h] [rbp-30h]
  sockaddr name; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v30; // [rsp+F0h] [rbp-10h]
  __int128 v31; // [rsp+100h] [rbp+0h]
  __int128 v32; // [rsp+110h] [rbp+10h]
  __int128 v33; // [rsp+120h] [rbp+20h]
  __int128 v34; // [rsp+130h] [rbp+30h]
  __int128 v35; // [rsp+140h] [rbp+40h]
  __int128 v36; // [rsp+150h] [rbp+50h]
  char optval[92]; // [rsp+160h] [rbp+60h] BYREF
  BOOL v38; // [rsp+1BCh] [rbp+BCh]
  HELPER_ATTRIBUTE attributes; // [rsp+3E0h] [rbp+2E0h] BYREF
  const wchar_t *v40; // [rsp+470h] [rbp+370h]
  int v41; // [rsp+478h] [rbp+378h]
  sockaddr v42; // [rsp+480h] [rbp+380h]
  __int128 v43; // [rsp+490h] [rbp+390h]
  __int128 v44; // [rsp+4A0h] [rbp+3A0h]
  __int128 v45; // [rsp+4B0h] [rbp+3B0h]
  __int128 v46; // [rsp+4C0h] [rbp+3C0h]
  __int128 v47; // [rsp+4D0h] [rbp+3D0h]
  __int128 v48; // [rsp+4E0h] [rbp+3E0h]
  __int128 v49; // [rsp+4F0h] [rbp+3F0h]
  const wchar_t *v50; // [rsp+500h] [rbp+400h]
  int v51; // [rsp+508h] [rbp+408h]
  struct sockaddr v52; // [rsp+510h] [rbp+410h]
  __int128 v53; // [rsp+520h] [rbp+420h]
  __int128 v54; // [rsp+530h] [rbp+430h]
  __int128 v55; // [rsp+540h] [rbp+440h]
  __int128 v56; // [rsp+550h] [rbp+450h]
  __int128 v57; // [rsp+560h] [rbp+460h]
  __int128 v58; // [rsp+570h] [rbp+470h]
  __int128 v59; // [rsp+580h] [rbp+480h]
  const wchar_t *v60; // [rsp+590h] [rbp+490h]
  int v61; // [rsp+598h] [rbp+498h]
  int v62; // [rsp+5A0h] [rbp+4A0h]
  SID *v63; // [rsp+5A8h] [rbp+4A8h]
  const wchar_t *v64; // [rsp+620h] [rbp+520h]
  int v65; // [rsp+628h] [rbp+528h]
  LPCWSTR v66; // [rsp+630h] [rbp+530h]
  WCHAR Filename[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  v20 = 15;
  v19 = 0;
  LOBYTE(pv[0]) = 0;
  std::string::assign((size_t *)pv, "NdfCreateWinSockIncident", 0x18u);
  TelemeterAPICall(pv);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  *(_OWORD *)pv = 0;
  if ( !sock || !handle )
  {
    SID = -2146895611;
    goto LABEL_37;
  }
  memset_0(&name, 0, 0x80u);
  memset_0(&v21, 0, 0x80u);
  namelen = 628;
  memset_0(optval, 0, 0x274u);
  if ( getsockopt(sock, 0xFFFF, 8197, optval, &namelen) )
  {
    Error = WSAGetLastError();
    SID = Error;
    if ( Error > 0 )
      SID = (unsigned __int16)Error | 0x80070000;
    if ( SID < 0 )
      goto LABEL_37;
  }
  attributes.type = AT_UINT32;
  attributes.pwszName = L"protocol";
  attributes.Boolean = v38;
  namelen = 128;
  if ( getsockname(sock, &name, &namelen) )
  {
    v12 = WSAGetLastError();
    SID = v12;
    if ( v12 > 0 )
      SID = (unsigned __int16)v12 | 0x80070000;
    if ( SID < 0 )
      goto LABEL_37;
  }
  v42 = name;
  v43 = v30;
  v44 = v31;
  v45 = v32;
  v46 = v33;
  v47 = v34;
  v48 = v35;
  v49 = v36;
  v40 = L"localaddr";
  v41 = 13;
  namelen = 128;
  if ( getpeername(sock, &v21, &namelen) )
  {
    v14 = WSAGetLastError();
    SID = v14;
    if ( v14 > 0 )
      SID = (unsigned __int16)v14 | 0x80070000;
    if ( SID < 0 )
      goto LABEL_37;
  }
  if ( v21.sa_family != 2 && v21.sa_family != 23 )
    return -2147024809;
  v53 = v22;
  v55 = v24;
  *(_WORD *)v21.sa_data = port;
  v52 = v21;
  v54 = v23;
  v56 = v25;
  v57 = v26;
  v58 = v27;
  v50 = L"remoteaddr";
  v51 = 13;
  v59 = v28;
  if ( userId )
  {
    v62 = 12;
    v60 = L"userid";
    v63 = userId;
  }
  else
  {
    SID = GetSID((struct tagOCTET_STRING *)pv, v13);
    if ( SID < 0 )
      goto LABEL_37;
    v60 = L"userid";
    v62 = (int)pv[0];
    v63 = (SID *)pv[1];
  }
  v61 = 14;
  memset_0(Filename, 0, 0x208u);
  v15 = 260;
  if ( appId )
  {
    v16 = appId;
    while ( *v16 )
    {
      ++v16;
      if ( !--v15 )
      {
        SID = -2147024809;
        goto LABEL_37;
      }
    }
    goto LABEL_32;
  }
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    appId = Filename;
LABEL_32:
    v64 = L"appid";
    v65 = 10;
    v66 = appId;
    SID = NdfCreateIncident(L"Winsock", 5u, &attributes, handle);
    if ( SID >= 0 && *handle )
      *((_DWORD *)*handle + 4) = 5;
    goto LABEL_37;
  }
  SID = GetLastError();
LABEL_37:
  if ( LODWORD(pv[0]) )
    CoTaskMemFree(pv[1]);
  return SID;
}

```

## disassembly

```asm
0x18000b3c0  mov     [rsp-8+arg_8], rbx
0x18000b3c5  mov     [rsp-8+arg_10], rsi
0x18000b3ca  push    rbp
0x18000b3cb  push    rdi
0x18000b3cc  push    r12
0x18000b3ce  push    r14
0x18000b3d0  push    r15
0x18000b3d2  lea     rbp, [rsp-7D0h]
0x18000b3da  sub     rsp, 8D0h
0x18000b3e1  mov     rax, cs:__security_cookie
0x18000b3e8  xor     rax, rsp
0x18000b3eb  mov     [rbp+7F0h+var_30], rax
0x18000b3f2  mov     r14, [rbp+7F0h+handle]
0x18000b3f9  lea     rdx, aNdfcreatewinso_0; "NdfCreateWinSockIncident"
0x18000b400  xor     r12d, r12d
0x18000b403  mov     [rsp+8F0h+var_8A0], 0Fh
0x18000b40c  movzx   r15d, r8w
0x18000b410  mov     [rsp+8F0h+var_8A8], r12
0x18000b415  mov     rsi, rcx
0x18000b418  mov     byte ptr [rsp+8F0h+pv], r12b
0x18000b41d  lea     rcx, [rsp+8F0h+pv]; void *
0x18000b422  mov     rdi, r9
0x18000b425  lea     r8d, [r12+18h]; Size
0x18000b42a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000b42f  lea     rcx, [rsp+8F0h+pv]
0x18000b434  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000b439  xor     ecx, ecx
0x18000b43b  call    cs:__imp_WdiCancel
0x18000b441  cmp     eax, 80070505h
0x18000b446  jnz     short loc_18000B452
0x18000b448  mov     eax, 80004004h
0x18000b44d  jmp     loc_18000B7DF
0x18000b452  xorps   xmm0, xmm0
0x18000b455  movups  xmmword ptr [rsp+8F0h+pv], xmm0
0x18000b45a  test    rsi, rsi
0x18000b45d  jz      loc_18000B7C6
0x18000b463  test    r14, r14
0x18000b466  jz      loc_18000B7C6
0x18000b46c  xor     edx, edx; Val
0x18000b46e  lea     rcx, [rbp+7F0h+name]; void *
0x18000b472  mov     r8d, 80h; Size
0x18000b478  call    memset_0
0x18000b47d  xor     edx, edx; Val
0x18000b47f  lea     rcx, [rsp+8F0h+var_890]; void *
0x18000b484  mov     r8d, 80h; Size
0x18000b48a  call    memset_0
0x18000b48f  mov     r8d, 274h; Size
0x18000b495  lea     rcx, [rbp+7F0h+optval]; void *
0x18000b499  xor     edx, edx; Val
0x18000b49b  mov     [rsp+8F0h+namelen], r8d
0x18000b4a0  call    memset_0
0x18000b4a5  lea     rax, [rsp+8F0h+namelen]
0x18000b4aa  mov     edx, 0FFFFh; level
0x18000b4af  lea     r9, [rbp+7F0h+optval]; optval
0x18000b4b3  mov     [rsp+8F0h+optlen], rax; optlen
0x18000b4b8  mov     r8d, 2005h; optname
0x18000b4be  mov     rcx, rsi; s
0x18000b4c1  call    cs:__imp_getsockopt
0x18000b4c7  test    eax, eax
0x18000b4c9  jz      short loc_18000B4E8
0x18000b4cb  call    cs:__imp_WSAGetLastError
0x18000b4d1  mov     ebx, eax
0x18000b4d3  test    eax, eax
0x18000b4d5  jle     short loc_18000B4E0
0x18000b4d7  movzx   ebx, ax
0x18000b4da  or      ebx, 80070000h
0x18000b4e0  test    ebx, ebx
0x18000b4e2  js      loc_18000B7CB
0x18000b4e8  lea     rax, aProtocol; "protocol"
0x18000b4ef  mov     [rbp+7F0h+attributes.type], 7
0x18000b4f9  mov     [rbp+7F0h+attributes.pwszName], rax
0x18000b500  lea     r8, [rsp+8F0h+namelen]; namelen
0x18000b505  mov     eax, [rbp+7F0h+var_734]
0x18000b50b  lea     rdx, [rbp+7F0h+name]; name
0x18000b50f  mov     rcx, rsi; s
0x18000b512  mov     dword ptr [rbp+7F0h+attributes.10h], eax
0x18000b518  mov     [rsp+8F0h+namelen], 80h
0x18000b520  call    cs:__imp_getsockname
0x18000b526  test    eax, eax
0x18000b528  jz      short loc_18000B547
0x18000b52a  call    cs:__imp_WSAGetLastError
0x18000b530  mov     ebx, eax
0x18000b532  test    eax, eax
0x18000b534  jle     short loc_18000B53F
0x18000b536  movzx   ebx, ax
0x18000b539  or      ebx, 80070000h
0x18000b53f  test    ebx, ebx
0x18000b541  js      loc_18000B7CB
0x18000b547  movaps  xmm0, xmmword ptr [rbp+7F0h+name.sa_family]
0x18000b54b  lea     rax, aLocaladdr; "localaddr"
0x18000b552  movaps  xmm1, [rbp+7F0h+var_800]
0x18000b556  lea     r8, [rsp+8F0h+namelen]; namelen
0x18000b55b  movaps  [rbp+7F0h+var_470], xmm0
0x18000b562  lea     rdx, [rsp+8F0h+var_890]; name
0x18000b567  movaps  xmm0, [rbp+7F0h+var_7F0]
0x18000b56b  mov     rcx, rsi; s
0x18000b56e  movaps  [rbp+7F0h+var_460], xmm1
0x18000b575  movaps  xmm1, [rbp+7F0h+var_7E0]
0x18000b579  movaps  [rbp+7F0h+var_450], xmm0
0x18000b580  movaps  xmm0, [rbp+7F0h+var_7D0]
0x18000b584  movaps  [rbp+7F0h+var_440], xmm1
0x18000b58b  movaps  xmm1, [rbp+7F0h+var_7C0]
0x18000b58f  movaps  [rbp+7F0h+var_430], xmm0
0x18000b596  movaps  xmm0, [rbp+7F0h+var_7B0]
0x18000b59a  movaps  [rbp+7F0h+var_420], xmm1
0x18000b5a1  movaps  xmm1, [rbp+7F0h+var_7A0]
0x18000b5a5  movaps  [rbp+7F0h+var_410], xmm0
0x18000b5ac  movaps  [rbp+7F0h+var_400], xmm1
0x18000b5b3  mov     [rbp+7F0h+var_480], rax
0x18000b5ba  mov     [rbp+7F0h+var_478], 0Dh
0x18000b5c4  mov     [rsp+8F0h+namelen], 80h
0x18000b5cc  call    cs:__imp_getpeername
0x18000b5d2  test    eax, eax
0x18000b5d4  jz      short loc_18000B5F3
0x18000b5d6  call    cs:__imp_WSAGetLastError
0x18000b5dc  mov     ebx, eax
0x18000b5de  test    eax, eax
0x18000b5e0  jle     short loc_18000B5EB
0x18000b5e2  movzx   ebx, ax
0x18000b5e5  or      ebx, 80070000h
0x18000b5eb  test    ebx, ebx
0x18000b5ed  js      loc_18000B7CB
0x18000b5f3  mov     esi, 2
0x18000b5f8  cmp     [rsp+8F0h+var_890.sa_family], si
0x18000b5fd  jz      short loc_18000B611
0x18000b5ff  cmp     [rsp+8F0h+var_890.sa_family], 17h
0x18000b605  jz      short loc_18000B611
0x18000b607  mov     eax, 80070057h
0x18000b60c  jmp     loc_18000B7DF
0x18000b611  movaps  xmm1, [rsp+8F0h+var_880]
0x18000b616  lea     rax, aRemoteaddr; "remoteaddr"
0x18000b61d  mov     rcx, [rbp+7F0h+userId]
0x18000b624  movaps  [rbp+7F0h+var_3D0], xmm1
0x18000b62b  movaps  xmm1, [rbp+7F0h+var_860]
0x18000b62f  movaps  [rbp+7F0h+var_3B0], xmm1
0x18000b636  movaps  xmm1, [rbp+7F0h+var_840]
0x18000b63a  mov     word ptr [rsp+8F0h+var_890.sa_data], r15w
0x18000b640  movaps  xmm0, xmmword ptr [rsp+8F0h+var_890.sa_family]
0x18000b645  movaps  [rbp+7F0h+var_3E0], xmm0
0x18000b64c  movaps  xmm0, [rbp+7F0h+var_870]
0x18000b650  movaps  [rbp+7F0h+var_3C0], xmm0
0x18000b657  movaps  xmm0, [rbp+7F0h+var_850]
0x18000b65b  movaps  [rbp+7F0h+var_3A0], xmm0
0x18000b662  movaps  xmm0, [rbp+7F0h+var_830]
0x18000b666  movaps  [rbp+7F0h+var_390], xmm1
0x18000b66d  movaps  xmm1, [rbp+7F0h+var_820]
0x18000b671  movaps  [rbp+7F0h+var_380], xmm0
0x18000b678  mov     [rbp+7F0h+var_3F0], rax
0x18000b67f  mov     [rbp+7F0h+var_3E8], 0Dh
0x18000b689  movaps  [rbp+7F0h+var_370], xmm1
0x18000b690  test    rcx, rcx
0x18000b693  jz      short loc_18000B6B6
0x18000b695  lea     rax, aUserid; "userid"
0x18000b69c  mov     [rbp+7F0h+var_350], 0Ch
0x18000b6a6  mov     [rbp+7F0h+var_360], rax
0x18000b6ad  mov     [rbp+7F0h+var_348], rcx
0x18000b6b4  jmp     short loc_18000B6EE
0x18000b6b6  lea     rcx, [rsp+8F0h+pv]; struct tagOCTET_STRING *
0x18000b6bb  call    ?GetSID@@YAJPEAUtagOCTET_STRING@@H@Z; GetSID(tagOCTET_STRING *,int)
0x18000b6c0  mov     ebx, eax
0x18000b6c2  test    eax, eax
0x18000b6c4  js      loc_18000B7CB
0x18000b6ca  lea     rax, aUserid; "userid"
0x18000b6d1  mov     [rbp+7F0h+var_360], rax
0x18000b6d8  mov     eax, dword ptr [rsp+8F0h+pv]
0x18000b6dc  mov     [rbp+7F0h+var_350], eax
0x18000b6e2  mov     rax, [rsp+8F0h+pv+8]
0x18000b6e7  mov     [rbp+7F0h+var_348], rax
0x18000b6ee  xor     edx, edx; Val
0x18000b6f0  mov     [rbp+7F0h+var_358], 0Eh
0x18000b6fa  mov     r8d, 208h; Size
0x18000b700  lea     rcx, [rbp+7F0h+Filename]; void *
0x18000b707  call    memset_0
0x18000b70c  mov     r8d, 104h; nSize
0x18000b712  test    rdi, rdi
0x18000b715  jz      short loc_18000B74A
0x18000b717  mov     rax, rdi
0x18000b71a  cmp     [rax], r12w
0x18000b71e  jz      short loc_18000B733
0x18000b720  add     rax, rsi
0x18000b723  sub     r8, 1
0x18000b727  jnz     short loc_18000B71A
0x18000b729  mov     ebx, 80070057h
0x18000b72e  jmp     loc_18000B7CB
0x18000b733  lea     rax, [rbp+7F0h+var_2C0]
0x18000b73a  lea     rcx, [rbp+7F0h+var_2C8]
0x18000b741  lea     rdx, [rbp+7F0h+var_2D0]
0x18000b748  jmp     short loc_18000B779
0x18000b74a  lea     rdx, [rbp+7F0h+Filename]; lpFilename
0x18000b751  xor     ecx, ecx; hModule
0x18000b753  call    cs:__imp_GetModuleFileNameW
0x18000b759  test    eax, eax
0x18000b75b  jz      short loc_18000B7BC
0x18000b75d  lea     rdi, [rbp+7F0h+Filename]
0x18000b764  lea     rdx, [rbp+7F0h+var_2D0]
0x18000b76b  lea     rcx, [rbp+7F0h+var_2C8]
0x18000b772  lea     rax, [rbp+7F0h+var_2C0]
0x18000b779  lea     r8, aAppid; "appid"
0x18000b780  mov     r9, r14; handle
0x18000b783  mov     [rdx], r8
0x18000b786  lea     r8, [rbp+7F0h+attributes]; attributes
0x18000b78d  mov     dword ptr [rcx], 0Ah
0x18000b793  lea     rcx, aWinsock; "Winsock"
0x18000b79a  mov     [rax], rdi
0x18000b79d  mov     edi, 5
0x18000b7a2  mov     edx, edi; celt
0x18000b7a4  call    NdfCreateIncident
0x18000b7a9  mov     ebx, eax
0x18000b7ab  test    eax, eax
0x18000b7ad  js      short loc_18000B7CB
0x18000b7af  mov     rax, [r14]
0x18000b7b2  test    rax, rax
0x18000b7b5  jz      short loc_18000B7CB
0x18000b7b7  mov     [rax+10h], edi
0x18000b7ba  jmp     short loc_18000B7CB
0x18000b7bc  call    cs:__imp_GetLastError
0x18000b7c2  mov     ebx, eax
0x18000b7c4  jmp     short loc_18000B7CB
0x18000b7c6  mov     ebx, 8008F905h
0x18000b7cb  cmp     dword ptr [rsp+8F0h+pv], r12d
0x18000b7d0  jz      short loc_18000B7DD
0x18000b7d2  mov     rcx, [rsp+8F0h+pv+8]; pv
0x18000b7d7  call    cs:__imp_CoTaskMemFree
0x18000b7dd  mov     eax, ebx
0x18000b7df  mov     rcx, [rbp+7F0h+var_30]
0x18000b7e6  xor     rcx, rsp; StackCookie
0x18000b7e9  call    __security_check_cookie
0x18000b7ee  lea     r11, [rsp+8F0h+var_20]
0x18000b7f6  mov     rbx, [r11+38h]
0x18000b7fa  mov     rsi, [r11+40h]
0x18000b7fe  mov     rsp, r11
0x18000b801  pop     r15
0x18000b803  pop     r14
0x18000b805  pop     r12
0x18000b807  pop     rdi
0x18000b808  pop     rbp
0x18000b809  retn
```
