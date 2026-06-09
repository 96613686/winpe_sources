# CHttpBase::InitializeHttpRequest(ushort const *)

- ea: `0x180046184`
- end: `0x1800463eb`
- name: `?InitializeHttpRequest@CHttpBase@@IEAAJPEBG@Z`
- size: `615`
- prototype: `__int64 __fastcall(CHttpBase *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180043bc0`
- `0x180045c78`
- `0x180046c7c`

## callees

- `0x180001284`
- `0x1800427b8`
- `0x180045980`
- `0x180046184`
- `0x18004743c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046222`
- `WINHTTP!WinHttpOpen` at `0x1800461ff`
- `WINHTTP!WinHttpOpen` at `0x1800461ff`
- `WINHTTP!WinHttpSetOption` at `0x180046256`
- `WINHTTP!WinHttpSetOption` at `0x180046256`
- `WINHTTP!WinHttpConnect` at `0x1800462d6`
- `WINHTTP!WinHttpConnect` at `0x1800462d6`
- `WINHTTP!WinHttpOpenRequest` at `0x180046379`
- `WINHTTP!WinHttpOpenRequest` at `0x180046379`
- `WININET!HttpOpenRequestW` at `0x1800463a5`
- `WININET!HttpOpenRequestW` at `0x1800463a5`
- `WININET!InternetConnectW` at `0x1800462f8`
- `WININET!InternetConnectW` at `0x1800462f8`
- `WININET!InternetOpenW` at `0x180046213`
- `WININET!InternetOpenW` at `0x180046213`
- `WININET!InternetSetOptionW` at `0x18004625e`
- `WININET!InternetSetOptionW` at `0x18004625e`

## pseudocode

```c
__int64 __fastcall CHttpBase::InitializeHttpRequest(CHttpBase *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rsi
  unsigned int v5; // ebx
  bool v6; // zf
  const WCHAR *v7; // rcx
  void *v8; // rax
  CHttpBase *v10; // rcx
  int ServerAndObjectPath; // eax
  void *v12; // rcx
  HINTERNET v13; // rax
  void *v14; // r10
  DWORD v15; // ecx
  int v16; // eax
  const WCHAR *v17; // rdx
  void *v18; // rax
  LPCWSTR pwszObjectName; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR ppwszAcceptTypes[3]; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 v22; // [rsp+90h] [rbp+30h] BYREF
  int Buffer; // [rsp+98h] [rbp+38h] BYREF
  int v24; // [rsp+A0h] [rbp+40h] BYREF
  LPCWSTR pswzServerName; // [rsp+A8h] [rbp+48h] BYREF

  pswzServerName = 0;
  pwszObjectName = 0;
  v24 = 0;
  v4 = 0;
  v22 = 0;
  ppwszAcceptTypes[0] = L"*/*";
  ppwszAcceptTypes[1] = 0;
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 4) == 0;
    v7 = L"Windows Rights Management Client";
    if ( !v6 )
      v7 = (const WCHAR *)*((_QWORD *)this + 4);
    if ( g_fGlobalOptionUseWinhttp )
      v8 = WinHttpOpen(
             v7,
             dwWINHTTP_ACCESS_TYPE_DEFAULT_PROXY,
             g_wszWINHTTP_NO_PROXY_NAME,
             g_wszWINHTTP_NO_PROXY_BYPASS,
             0);
    else
      v8 = InternetOpenW(v7, dwINTERNET_OPEN_TYPE_PRECONFIG, 0, 0, 0);
    *((_QWORD *)this + 11) = v8;
    if ( v8 )
    {
      Buffer = 600000;
      if ( g_fGlobalOptionUseWinhttp ? WinHttpSetOption(v8, 6u, &Buffer, 4u) : InternetSetOptionW(v8, 6u, &Buffer, 4u) )
      {
        ServerAndObjectPath = CHttpBase::GetServerAndObjectPath(
                                v10,
                                a2,
                                (unsigned __int16 **)&pswzServerName,
                                (unsigned __int16 **)&pwszObjectName,
                                &v24,
                                &v22);
        v4 = (unsigned __int16 *)pswzServerName;
        v5 = ServerAndObjectPath;
        if ( ServerAndObjectPath < 0 )
          goto LABEL_33;
        v12 = (void *)*((_QWORD *)this + 11);
        if ( g_fGlobalOptionUseWinhttp )
          v13 = WinHttpConnect(v12, pswzServerName, v22, 0);
        else
          v13 = InternetConnectW(
                  v12,
                  pswzServerName,
                  v22,
                  (LPCWSTR)((unsigned __int64)&Src & -(__int64)((*((_DWORD *)this + 10) & 8) != 0)),
                  (LPCWSTR)((unsigned __int64)L"     " & -(__int64)((*((_DWORD *)this + 10) & 8) != 0)),
                  3u,
                  0,
                  0);
        *((_QWORD *)this + 12) = v13;
        v14 = v13;
        if ( v13 )
        {
          v15 = g_fGlobalOptionUseWinhttp == 0 ? 0x4400000 : 0;
          if ( v24 )
            v15 |= 0x800000u;
          if ( (*((_DWORD *)this + 10) & 1) != 0 && !g_fGlobalOptionUseWinhttp )
            v15 |= 0x200000u;
          v16 = *((_DWORD *)this + 10) & 2;
          v17 = 0;
          if ( g_fGlobalOptionUseWinhttp )
          {
            if ( !v16 )
              v17 = L"POST";
            v18 = WinHttpOpenRequest(
                    v14,
                    v17,
                    pwszObjectName,
                    L"HTTP/1.0",
                    g_wszWINHTTP_NO_REFERER,
                    ppwszAcceptTypes,
                    v15);
          }
          else
          {
            if ( !v16 )
              v17 = L"POST";
            v18 = HttpOpenRequestW(v14, v17, pwszObjectName, L"HTTP/1.0", 0, ppwszAcceptTypes, v15, 0);
          }
          *((_QWORD *)this + 13) = v18;
          if ( v18 )
          {
            TryToSetCredentialsFromCredVault(v18, v4);
            v5 = CHttpBase::AddRequestHeaders(this);
            goto LABEL_33;
          }
        }
      }
    }
    *((_DWORD *)this + 30) = GetLastError();
    v5 = -2147168453;
  }
  else
  {
    v5 = -2147024809;
  }
LABEL_33:
  operator delete(v4);
  operator delete((void *)pwszObjectName);
  return v5;
}

```

## disassembly

```asm
0x180046184  push    rbp
0x180046186  push    rbx
0x180046187  push    rsi
0x180046188  push    rdi
0x180046189  push    r14
0x18004618b  mov     rbp, rsp
0x18004618e  sub     rsp, 60h
0x180046192  xor     r14d, r14d
0x180046195  lea     rax, asc_18006D1A0; "*/*"
0x18004619c  mov     [rbp+pswzServerName], r14
0x1800461a0  mov     rbx, rdx
0x1800461a3  mov     [rbp+pwszObjectName], r14
0x1800461a7  mov     rdi, rcx
0x1800461aa  mov     [rbp+arg_10], r14d
0x1800461ae  mov     esi, r14d
0x1800461b1  mov     [rbp+arg_0], r14w
0x1800461b6  mov     [rbp+ppwszAcceptTypes], rax
0x1800461ba  mov     [rbp+var_10], r14
0x1800461be  test    rdx, rdx
0x1800461c1  jnz     short loc_1800461CD
0x1800461c3  mov     ebx, 80070057h
0x1800461c8  jmp     loc_1800463CD
0x1800461cd  cmp     [rdi+20h], r14
0x1800461d1  lea     rcx, ?g_wszHTTP_DefaultAppName@@3QBGB; "Windows Rights Management Client"
0x1800461d8  mov     [rsp+60h+dwFlags], r14d; dwFlags
0x1800461dd  cmovnz  rcx, [rdi+20h]; lpszAgent
0x1800461e2  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r14d; int g_fGlobalOptionUseWinhttp
0x1800461e9  jz      short loc_180046207
0x1800461eb  mov     r9, cs:?g_wszWINHTTP_NO_PROXY_BYPASS@@3PEAGEA; pszProxyBypassW
0x1800461f2  mov     r8, cs:?g_wszWINHTTP_NO_PROXY_NAME@@3PEAGEA; pszProxyW
0x1800461f9  mov     edx, cs:?dwWINHTTP_ACCESS_TYPE_DEFAULT_PROXY@@3KA; dwAccessType
0x1800461ff  call    cs:__imp_WinHttpOpen
0x180046205  jmp     short loc_180046219
0x180046207  mov     edx, cs:?dwINTERNET_OPEN_TYPE_PRECONFIG@@3KA; dwAccessType
0x18004620d  xor     r9d, r9d; lpszProxyBypass
0x180046210  xor     r8d, r8d; lpszProxy
0x180046213  call    cs:__imp_InternetOpenW
0x180046219  mov     [rdi+58h], rax
0x18004621d  test    rax, rax
0x180046220  jnz     short loc_180046235
0x180046222  call    cs:__imp_GetLastError
0x180046228  mov     [rdi+78h], eax
0x18004622b  mov     ebx, 8004CF3Bh
0x180046230  jmp     loc_1800463CD
0x180046235  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r14d; int g_fGlobalOptionUseWinhttp
0x18004623c  lea     r8, [rbp+Buffer]; lpBuffer
0x180046240  mov     r9d, 4; dwBufferLength
0x180046246  mov     [rbp+Buffer], 927C0h
0x18004624d  mov     rcx, rax; hInternet
0x180046250  lea     edx, [r9+2]; dwOption
0x180046254  jz      short loc_18004625E
0x180046256  call    cs:__imp_WinHttpSetOption
0x18004625c  jmp     short loc_180046264
0x18004625e  call    cs:__imp_InternetSetOptionW
0x180046264  test    eax, eax
0x180046266  jz      short loc_180046222
0x180046268  lea     rax, [rbp+arg_0]
0x18004626c  mov     rdx, rbx; unsigned __int16 *
0x18004626f  mov     qword ptr [rsp+60h+dwService], rax; unsigned __int16 *
0x180046274  lea     r9, [rbp+pwszObjectName]; unsigned __int16 **
0x180046278  lea     rax, [rbp+arg_10]
0x18004627c  lea     r8, [rbp+pswzServerName]; unsigned __int16 **
0x180046280  mov     qword ptr [rsp+60h+dwFlags], rax; int *
0x180046285  call    ?GetServerAndObjectPath@CHttpBase@@AEAAJPEBGPEAPEAG1PEAHPEAG@Z; CHttpBase::GetServerAndObjectPath(ushort const *,ushort * *,ushort * *,int *,ushort *)
0x18004628a  mov     rsi, [rbp+pswzServerName]
0x18004628e  mov     ebx, eax
0x180046290  test    eax, eax
0x180046292  js      loc_1800463CD
0x180046298  mov     ecx, [rdi+28h]
0x18004629b  lea     r8, asc_18006D1A8; "     "
0x1800462a2  and     ecx, 8
0x1800462a5  mov     eax, ecx
0x1800462a7  neg     eax
0x1800462a9  lea     rax, Src
0x1800462b0  sbb     rdx, rdx
0x1800462b3  and     rdx, r8
0x1800462b6  movzx   r8d, [rbp+arg_0]; nServerPort
0x1800462bb  neg     ecx
0x1800462bd  mov     rcx, [rdi+58h]; hInternet
0x1800462c1  sbb     r9, r9
0x1800462c4  and     r9, rax; lpszUserName
0x1800462c7  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r14d; int g_fGlobalOptionUseWinhttp
0x1800462ce  jz      short loc_1800462DE
0x1800462d0  xor     r9d, r9d; dwReserved
0x1800462d3  mov     rdx, rsi; pswzServerName
0x1800462d6  call    cs:__imp_WinHttpConnect
0x1800462dc  jmp     short loc_1800462FE
0x1800462de  mov     [rsp+60h+dwContext], r14; dwContext
0x1800462e3  mov     [rsp+60h+var_30], r14d; dwFlags
0x1800462e8  mov     [rsp+60h+dwService], 3; dwService
0x1800462f0  mov     qword ptr [rsp+60h+dwFlags], rdx; lpszPassword
0x1800462f5  mov     rdx, rsi; lpszServerName
0x1800462f8  call    cs:__imp_InternetConnectW
0x1800462fe  mov     [rdi+60h], rax
0x180046302  mov     r10, rax
0x180046305  test    rax, rax
0x180046308  jz      loc_180046222
0x18004630e  mov     edx, cs:?g_fGlobalOptionUseWinhttp@@3HA; int g_fGlobalOptionUseWinhttp
0x180046314  mov     eax, edx
0x180046316  neg     eax
0x180046318  sbb     ecx, ecx
0x18004631a  not     ecx
0x18004631c  and     ecx, 4400000h
0x180046322  cmp     [rbp+arg_10], r14d
0x180046326  jz      short loc_18004632C
0x180046328  bts     ecx, 17h
0x18004632c  mov     eax, [rdi+28h]
0x18004632f  test    al, 1
0x180046331  jz      short loc_18004633B
0x180046333  test    edx, edx
0x180046335  jnz     short loc_18004633B
0x180046337  bts     ecx, 15h
0x18004633b  and     eax, 2
0x18004633e  lea     r8, szVerb; "POST"
0x180046345  test    edx, edx
0x180046347  lea     r9, szVersion; "HTTP/1.0"
0x18004634e  mov     rdx, r14
0x180046351  jz      short loc_180046381
0x180046353  test    eax, eax
0x180046355  mov     [rsp+60h+var_30], ecx; dwFlags
0x180046359  lea     rax, [rbp+ppwszAcceptTypes]
0x18004635d  mov     rcx, r10; hConnect
0x180046360  mov     qword ptr [rsp+60h+dwService], rax; ppwszAcceptTypes
0x180046365  cmovz   rdx, r8; pwszVerb
0x180046369  mov     rax, cs:?g_wszWINHTTP_NO_REFERER@@3PEAGEA; ushort * g_wszWINHTTP_NO_REFERER
0x180046370  mov     r8, [rbp+pwszObjectName]; pwszObjectName
0x180046374  mov     qword ptr [rsp+60h+dwFlags], rax; pwszReferrer
0x180046379  call    cs:__imp_WinHttpOpenRequest
0x18004637f  jmp     short loc_1800463AB
0x180046381  test    eax, eax
0x180046383  mov     [rsp+60h+dwContext], r14; dwContext
0x180046388  mov     [rsp+60h+var_30], ecx; dwFlags
0x18004638c  lea     rax, [rbp+ppwszAcceptTypes]
0x180046390  cmovz   rdx, r8; lpszVerb
0x180046394  mov     qword ptr [rsp+60h+dwService], rax; lplpszAcceptTypes
0x180046399  mov     r8, [rbp+pwszObjectName]; lpszObjectName
0x18004639d  mov     rcx, r10; hConnect
0x1800463a0  mov     qword ptr [rsp+60h+dwFlags], r14; lpszReferrer
0x1800463a5  call    cs:__imp_HttpOpenRequestW
0x1800463ab  mov     [rdi+68h], rax
0x1800463af  test    rax, rax
0x1800463b2  jz      loc_180046222
0x1800463b8  mov     rdx, rsi; unsigned __int16 *
0x1800463bb  mov     rcx, rax; hInternet
0x1800463be  call    ?TryToSetCredentialsFromCredVault@@YAJPEAXPEAG@Z; TryToSetCredentialsFromCredVault(void *,ushort *)
0x1800463c3  mov     rcx, rdi; this
0x1800463c6  call    ?AddRequestHeaders@CHttpBase@@IEAAJXZ; CHttpBase::AddRequestHeaders(void)
0x1800463cb  mov     ebx, eax
0x1800463cd  mov     rcx, rsi; Block
0x1800463d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800463d5  mov     rcx, [rbp+pwszObjectName]; Block
0x1800463d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800463de  mov     eax, ebx
0x1800463e0  add     rsp, 60h
0x1800463e4  pop     r14
0x1800463e6  pop     rdi
0x1800463e7  pop     rsi
0x1800463e8  pop     rbx
0x1800463e9  pop     rbp
0x1800463ea  retn
```
