# Connect(ushort const *,ushort const *,ushort const *,char const *,ulong,void * *,void * *,void * *)

- ea: `0x1400506ac`
- end: `0x140050ad9`
- name: `?Connect@@YAJPEBG00PEBDKPEAPEAX22@Z`
- size: `1069`
- prototype: `__int64 __fastcall(LPCWSTR lpcwszUrl, LPCWSTR pwszVerb, const unsigned __int16 *, char *, DWORD dwOptionalLength, void **, void **, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400521e0`
- `0x140052688`

## callees

- `0x1400039b1`
- `0x140010eb4`
- `0x1400504a4`
- `0x1400506ac`
- `0x140050ff0`
- `0x140052524`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400507f1`
- `KERNEL32!GetLastError` at `0x140050845`
- `KERNEL32!GetLastError` at `0x140050892`
- `KERNEL32!GetLastError` at `0x140050906`
- `KERNEL32!GetLastError` at `0x1400509ab`
- `KERNEL32!GetLastError` at `0x140050a13`
- `KERNEL32!GetLastError` at `0x1400507f1`
- `KERNEL32!GetLastError` at `0x140050845`
- `KERNEL32!GetLastError` at `0x140050892`
- `KERNEL32!GetLastError` at `0x140050906`
- `KERNEL32!GetLastError` at `0x1400509ab`
- `KERNEL32!GetLastError` at `0x140050a13`
- `KERNEL32!HeapAlloc` at `0x14005074b`
- `KERNEL32!HeapAlloc` at `0x14005077a`
- `KERNEL32!HeapAlloc` at `0x14005074b`
- `KERNEL32!HeapAlloc` at `0x14005077a`
- `KERNEL32!HeapFree` at `0x140050a75`
- `KERNEL32!HeapFree` at `0x140050a9a`
- `KERNEL32!HeapFree` at `0x140050a75`
- `KERNEL32!HeapFree` at `0x140050a9a`
- `KERNEL32!GetProcessHeap` at `0x140050732`
- `KERNEL32!GetProcessHeap` at `0x140050766`
- `KERNEL32!GetProcessHeap` at `0x140050a61`
- `KERNEL32!GetProcessHeap` at `0x140050a86`
- `KERNEL32!GetProcessHeap` at `0x140050732`
- `KERNEL32!GetProcessHeap` at `0x140050766`
- `KERNEL32!GetProcessHeap` at `0x140050a61`
- `KERNEL32!GetProcessHeap` at `0x140050a86`
- `WINHTTP!WinHttpOpen` at `0x14005082b`
- `WINHTTP!WinHttpOpen` at `0x14005082b`
- `WINHTTP!WinHttpOpenRequest` at `0x1400508e7`
- `WINHTTP!WinHttpOpenRequest` at `0x1400508e7`
- `WINHTTP!WinHttpSetOption` at `0x14005099b`
- `WINHTTP!WinHttpSetOption` at `0x14005099b`
- `WINHTTP!WinHttpSendRequest` at `0x140050a03`
- `WINHTTP!WinHttpSendRequest` at `0x140050a03`
- `WINHTTP!WinHttpConnect` at `0x140050878`
- `WINHTTP!WinHttpConnect` at `0x140050878`
- `WINHTTP!WinHttpCrackUrl` at `0x1400507e1`
- `WINHTTP!WinHttpCrackUrl` at `0x1400507e1`

## pseudocode

```c
__int64 __fastcall Connect(
        LPCWSTR lpcwszUrl,
        LPCWSTR pwszVerb,
        const unsigned __int16 *a3,
        char *a4,
        DWORD dwOptionalLength,
        void **a6,
        void **a7,
        void **a8)
{
  HANDLE ProcessHeap; // rax
  CHAR *v11; // rax
  CHAR *v12; // r12
  HANDLE v13; // rax
  CHAR *v14; // rax
  CHAR *v15; // rdi
  unsigned __int64 v16; // rcx
  signed int ProxyList; // ebx
  signed int LastError; // eax
  void *v19; // rax
  signed int v20; // eax
  void *v21; // rax
  signed int v22; // eax
  DWORD v23; // eax
  HINTERNET v24; // rax
  HINTERNET *v25; // r14
  signed int v26; // eax
  int v27; // eax
  const WCHAR *v28; // r13
  _QWORD *v29; // r8
  signed int v30; // eax
  void *v31; // r9
  signed int v32; // eax
  HANDLE v33; // rax
  HANDLE v34; // rax
  DWORD dwUrlLength; // [rsp+40h] [rbp-C0h] BYREF
  void **v37; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpszHeaders; // [rsp+50h] [rbp-B0h]
  LPVOID lpOptional; // [rsp+58h] [rbp-A8h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v41[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD **v42; // [rsp+E0h] [rbp-20h] BYREF
  int v43; // [rsp+E8h] [rbp-18h]

  lpszHeaders = a3;
  lpOptional = a4;
  v37 = a8;
  dwUrlLength = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  memset_0(&v42, 0, 0x58u);
  v41[1] = v41;
  v41[0] = v41;
  ProcessHeap = GetProcessHeap();
  v11 = (CHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
  v12 = v11;
  if ( v11 )
  {
    *(_WORD *)v11 = 0;
    v13 = GetProcessHeap();
    v14 = (CHAR *)HeapAlloc(v13, 0, 0x800u);
    v15 = v14;
    if ( !v14 )
    {
      ProxyList = -2147024882;
      goto LABEL_49;
    }
    *(_WORD *)v14 = 0;
    v16 = -1;
    UrlComponents.lpszUrlPath = v14;
    UrlComponents.dwHostNameLength = 1024;
    UrlComponents.dwUrlPathLength = 1024;
    UrlComponents.dwStructSize = 104;
    UrlComponents.lpszHostName = v12;
    do
      ++v16;
    while ( lpcwszUrl[v16] );
    ProxyList = ULongLongToULong(v16, &dwUrlLength);
    if ( ProxyList >= 0 )
    {
      if ( WinHttpCrackUrl(lpcwszUrl, dwUrlLength, 0, &UrlComponents) )
        goto LABEL_10;
      LastError = GetLastError();
      ProxyList = LastError;
      if ( LastError > 0 )
        ProxyList = (unsigned __int16)LastError | 0x80070000;
      if ( ProxyList >= 0 )
      {
LABEL_10:
        v19 = WinHttpOpen(L"msde/10.0", 0, 0, 0, 0);
        *a6 = v19;
        if ( (((unsigned __int64)v19 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          goto LABEL_55;
        v20 = GetLastError();
        ProxyList = v20;
        if ( v20 > 0 )
          ProxyList = (unsigned __int16)v20 | 0x80070000;
        if ( ProxyList >= 0 )
        {
LABEL_55:
          v21 = WinHttpConnect(*a6, (LPCWSTR)UrlComponents.lpszHostName, UrlComponents.nPort, 0);
          *a7 = v21;
          if ( (((unsigned __int64)v21 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
            goto LABEL_56;
          v22 = GetLastError();
          ProxyList = v22;
          if ( v22 > 0 )
            ProxyList = (unsigned __int16)v22 | 0x80070000;
          if ( ProxyList >= 0 )
          {
LABEL_56:
            v23 = 0;
            if ( UrlComponents.nScheme == INTERNET_SCHEME_GOPHER )
              v23 = 0x800000;
            v24 = WinHttpOpenRequest(*a7, pwszVerb, (LPCWSTR)UrlComponents.lpszUrlPath, 0, 0, 0, v23);
            v25 = v37;
            *v37 = v24;
            if ( (((unsigned __int64)v24 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
              goto LABEL_57;
            v26 = GetLastError();
            ProxyList = v26;
            if ( v26 > 0 )
              ProxyList = (unsigned __int16)v26 | 0x80070000;
            if ( ProxyList >= 0 )
            {
LABEL_57:
              ProxyList = SetRequestOptions(*v25);
              if ( ProxyList >= 0 )
              {
                ProxyList = GetProxyList(*a6, lpcwszUrl, (struct _PROXY_LIST *)v41);
                if ( ProxyList >= 0 )
                {
                  v27 = v43;
                  v28 = lpszHeaders;
                  while ( 1 )
                  {
                    ProxyList = 0;
                    if ( v27 )
                    {
                      if ( v42 )
                        v29 = *v42;
                      else
                        v29 = (_QWORD *)v41[0];
                      v42 = (_QWORD **)v29;
                      if ( v29 == v41 )
                      {
                        ProxyList = 1;
                        break;
                      }
                      if ( !WinHttpSetOption(*a6, 0x26u, v29 + 2, 0x18u) )
                      {
                        v30 = GetLastError();
                        if ( v30 > 0 )
                          v30 = (unsigned __int16)v30 | 0x80070000;
                        ProxyList = v30;
                        if ( v30 < 0 )
                          break;
                        ProxyList = 0;
                      }
                    }
                    v31 = 0;
                    if ( lpOptional )
                      v31 = lpOptional;
                    if ( !WinHttpSendRequest(*v25, v28, -(v28 != 0), v31, dwOptionalLength, dwOptionalLength, 0) )
                    {
                      v32 = GetLastError();
                      ProxyList = v32;
                      if ( v32 > 0 )
                        ProxyList = (unsigned __int16)v32 | 0x80070000;
                      if ( (unsigned __int16)ProxyList == 12002
                        || (unsigned __int16)ProxyList == 12007
                        || (unsigned int)(unsigned __int16)ProxyList - 12029 <= 1 )
                      {
                        v27 = v43;
                        if ( v43 )
                          continue;
                      }
                    }
                    break;
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_49:
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v12);
    if ( v15 )
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v15);
    }
  }
  else
  {
    ProxyList = -2147024882;
  }
  CloseProxyList((struct _PROXY_LIST *)v41);
  return (unsigned int)ProxyList;
}

```

## disassembly

```asm
0x1400506ac  push    rbp
0x1400506ae  push    rbx
0x1400506af  push    rsi
0x1400506b0  push    rdi
0x1400506b1  push    r12
0x1400506b3  push    r13
0x1400506b5  push    r14
0x1400506b7  push    r15
0x1400506b9  lea     rbp, [rsp-58h]
0x1400506be  sub     rsp, 158h
0x1400506c5  mov     rax, cs:__security_cookie
0x1400506cc  xor     rax, rsp
0x1400506cf  mov     [rbp+90h+var_50], rax
0x1400506d3  mov     rax, [rbp+90h+arg_38]
0x1400506da  xor     ebx, ebx
0x1400506dc  mov     r15, [rbp+90h+arg_28]
0x1400506e3  mov     r13, rdx
0x1400506e6  mov     r14, [rbp+90h+arg_30]
0x1400506ed  mov     rsi, rcx
0x1400506f0  mov     [rsp+190h+lpszHeaders], r8
0x1400506f5  lea     rcx, [rsp+190h+UrlComponents]; void *
0x1400506fa  lea     r8d, [rbx+68h]; Size
0x1400506fe  mov     [rsp+190h+lpOptional], r9
0x140050703  xor     edx, edx; Val
0x140050705  mov     [rsp+190h+var_148], rax
0x14005070a  mov     [rsp+190h+dwUrlLength], ebx
0x14005070e  call    memset_0
0x140050713  xor     edx, edx; Val
0x140050715  lea     r8d, [rbx+58h]; Size
0x140050719  lea     rcx, [rbp+90h+var_B0]; void *
0x14005071d  call    memset_0
0x140050722  lea     rax, [rbp+90h+var_C0]
0x140050726  mov     [rbp+90h+var_B8], rax
0x14005072a  lea     rax, [rbp+90h+var_C0]
0x14005072e  mov     [rbp+90h+var_C0], rax
0x140050732  call    cs:__imp_GetProcessHeap
0x140050739  nop     dword ptr [rax+rax+00h]
0x14005073e  mov     edi, 800h
0x140050743  xor     edx, edx; dwFlags
0x140050745  mov     rcx, rax; hHeap
0x140050748  mov     r8d, edi; dwBytes
0x14005074b  call    cs:__imp_HeapAlloc
0x140050752  nop     dword ptr [rax+rax+00h]
0x140050757  mov     r12, rax
0x14005075a  test    rax, rax
0x14005075d  jz      loc_140050AA8
0x140050763  mov     [rax], bx
0x140050766  call    cs:__imp_GetProcessHeap
0x14005076d  nop     dword ptr [rax+rax+00h]
0x140050772  mov     r8d, edi; dwBytes
0x140050775  xor     edx, edx; dwFlags
0x140050777  mov     rcx, rax; hHeap
0x14005077a  call    cs:__imp_HeapAlloc
0x140050781  nop     dword ptr [rax+rax+00h]
0x140050786  mov     rdi, rax
0x140050789  test    rax, rax
0x14005078c  jz      loc_140050A5C
0x140050792  mov     [rax], bx
0x140050795  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140050799  mov     [rbp+90h+UrlComponents.lpszUrlPath], rax
0x14005079d  mov     eax, 400h
0x1400507a2  mov     [rbp+90h+UrlComponents.dwHostNameLength], eax
0x1400507a5  mov     [rbp+90h+UrlComponents.dwUrlPathLength], eax
0x1400507a8  mov     [rsp+190h+UrlComponents.dwStructSize], 68h ; 'h'
0x1400507b0  mov     [rsp+190h+UrlComponents.lpszHostName], r12
0x1400507b5  inc     rcx; unsigned __int64
0x1400507b8  cmp     [rsi+rcx*2], bx
0x1400507bc  jnz     short loc_1400507B5
0x1400507be  lea     rdx, [rsp+190h+dwUrlLength]; unsigned int *
0x1400507c3  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1400507c8  mov     ebx, eax
0x1400507ca  test    eax, eax
0x1400507cc  js      loc_140050A61
0x1400507d2  mov     edx, [rsp+190h+dwUrlLength]; dwUrlLength
0x1400507d6  lea     r9, [rsp+190h+UrlComponents]; lpUrlComponents
0x1400507db  xor     r8d, r8d; dwFlags
0x1400507de  mov     rcx, rsi; pwszUrl
0x1400507e1  call    cs:__imp_WinHttpCrackUrl
0x1400507e8  nop     dword ptr [rax+rax+00h]
0x1400507ed  test    eax, eax
0x1400507ef  jnz     short loc_140050814
0x1400507f1  call    cs:__imp_GetLastError
0x1400507f8  nop     dword ptr [rax+rax+00h]
0x1400507fd  mov     ebx, eax
0x1400507ff  test    eax, eax
0x140050801  jle     short loc_14005080C
0x140050803  movzx   ebx, ax
0x140050806  or      ebx, 80070000h
0x14005080c  test    ebx, ebx
0x14005080e  js      loc_140050A61
0x140050814  xor     r9d, r9d; pszProxyBypassW
0x140050817  mov     [rsp+190h+dwFlags], 0; dwFlags
0x14005081f  xor     r8d, r8d; pszProxyW
0x140050822  lea     rcx, pszAgentW; "msde/10.0"
0x140050829  xor     edx, edx; dwAccessType
0x14005082b  call    cs:__imp_WinHttpOpen
0x140050832  nop     dword ptr [rax+rax+00h]
0x140050837  mov     [r15], rax
0x14005083a  inc     rax
0x14005083d  test    rax, 0FFFFFFFFFFFFFFFEh
0x140050843  jnz     short loc_140050868
0x140050845  call    cs:__imp_GetLastError
0x14005084c  nop     dword ptr [rax+rax+00h]
0x140050851  mov     ebx, eax
0x140050853  test    eax, eax
0x140050855  jle     short loc_140050860
0x140050857  movzx   ebx, ax
0x14005085a  or      ebx, 80070000h
0x140050860  test    ebx, ebx
0x140050862  js      loc_140050A61
0x140050868  movzx   r8d, [rbp+90h+UrlComponents.nPort]; nServerPort
0x14005086d  xor     r9d, r9d; dwReserved
0x140050870  mov     rdx, [rsp+190h+UrlComponents.lpszHostName]; pswzServerName
0x140050875  mov     rcx, [r15]; hSession
0x140050878  call    cs:__imp_WinHttpConnect
0x14005087f  nop     dword ptr [rax+rax+00h]
0x140050884  mov     [r14], rax
0x140050887  inc     rax
0x14005088a  test    rax, 0FFFFFFFFFFFFFFFEh
0x140050890  jnz     short loc_1400508B5
0x140050892  call    cs:__imp_GetLastError
0x140050899  nop     dword ptr [rax+rax+00h]
0x14005089e  mov     ebx, eax
0x1400508a0  test    eax, eax
0x1400508a2  jle     short loc_1400508AD
0x1400508a4  movzx   ebx, ax
0x1400508a7  or      ebx, 80070000h
0x1400508ad  test    ebx, ebx
0x1400508af  js      loc_140050A61
0x1400508b5  mov     r8, [rbp+90h+UrlComponents.lpszUrlPath]; pwszObjectName
0x1400508b9  xor     eax, eax
0x1400508bb  cmp     [rsp+190h+UrlComponents.nScheme], 2
0x1400508c0  mov     ecx, 800000h
0x1400508c5  mov     rdx, r13; pwszVerb
0x1400508c8  cmovz   eax, ecx
0x1400508cb  mov     rcx, [r14]; hConnect
0x1400508ce  mov     [rsp+190h+var_160], eax; dwFlags
0x1400508d2  xor     r9d, r9d; pwszVersion
0x1400508d5  mov     [rsp+190h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1400508de  mov     qword ptr [rsp+190h+dwFlags], 0; pwszReferrer
0x1400508e7  call    cs:__imp_WinHttpOpenRequest
0x1400508ee  nop     dword ptr [rax+rax+00h]
0x1400508f3  mov     r14, [rsp+190h+var_148]
0x1400508f8  mov     [r14], rax
0x1400508fb  inc     rax
0x1400508fe  test    rax, 0FFFFFFFFFFFFFFFEh
0x140050904  jnz     short loc_140050929
0x140050906  call    cs:__imp_GetLastError
0x14005090d  nop     dword ptr [rax+rax+00h]
0x140050912  mov     ebx, eax
0x140050914  test    eax, eax
0x140050916  jle     short loc_140050921
0x140050918  movzx   ebx, ax
0x14005091b  or      ebx, 80070000h
0x140050921  test    ebx, ebx
0x140050923  js      loc_140050A61
0x140050929  mov     rcx, [r14]; hInternet
0x14005092c  call    ?SetRequestOptions@@YAJPEAX@Z; SetRequestOptions(void *)
0x140050931  mov     ebx, eax
0x140050933  test    eax, eax
0x140050935  js      loc_140050A61
0x14005093b  mov     rcx, [r15]; hSession
0x14005093e  lea     r8, [rbp+90h+var_C0]; struct _PROXY_LIST *
0x140050942  mov     rdx, rsi; lpcwszUrl
0x140050945  call    ?GetProxyList@@YAJPEAXPEBGPEAU_PROXY_LIST@@@Z; GetProxyList(void *,ushort const *,_PROXY_LIST *)
0x14005094a  mov     ebx, eax
0x14005094c  test    eax, eax
0x14005094e  js      loc_140050A61
0x140050954  mov     esi, [rbp+90h+dwOptionalLength]
0x14005095a  mov     eax, [rbp+90h+var_A8]
0x14005095d  mov     r13, [rsp+190h+lpszHeaders]
0x140050962  xor     ebx, ebx
0x140050964  test    eax, eax
0x140050966  jz      short loc_1400509D8
0x140050968  mov     r8, [rbp+90h+var_B0]
0x14005096c  test    r8, r8
0x14005096f  jnz     short loc_140050977
0x140050971  mov     r8, [rbp+90h+var_C0]
0x140050975  jmp     short loc_14005097A
0x140050977  mov     r8, [r8]
0x14005097a  lea     rax, [rbp+90h+var_C0]
0x14005097e  mov     [rbp+90h+var_B0], r8
0x140050982  cmp     r8, rax
0x140050985  jz      loc_140050A55
0x14005098b  mov     rcx, [r15]; hInternet
0x14005098e  mov     edx, 26h ; '&'; dwOption
0x140050993  add     r8, 10h; lpBuffer
0x140050997  lea     r9d, [rdx-0Eh]; dwBufferLength
0x14005099b  call    cs:__imp_WinHttpSetOption
0x1400509a2  nop     dword ptr [rax+rax+00h]
0x1400509a7  test    eax, eax
0x1400509a9  jnz     short loc_1400509D8
0x1400509ab  call    cs:__imp_GetLastError
0x1400509b2  nop     dword ptr [rax+rax+00h]
0x1400509b7  test    eax, eax
0x1400509b9  jle     short loc_1400509C3
0x1400509bb  movzx   eax, ax
0x1400509be  or      eax, 80070000h
0x1400509c3  mov     ebx, eax
0x1400509c5  test    eax, eax
0x1400509c7  js      loc_140050A61
0x1400509cd  cmp     eax, 1
0x1400509d0  jz      loc_140050A61
0x1400509d6  xor     ebx, ebx
0x1400509d8  mov     rax, [rsp+190h+lpOptional]
0x1400509dd  mov     r9, rbx
0x1400509e0  mov     rcx, [r14]; hRequest
0x1400509e3  test    rax, rax
0x1400509e6  mov     qword ptr [rsp+190h+var_160], rbx; dwContext
0x1400509eb  mov     rdx, r13; lpszHeaders
0x1400509ee  cmovnz  r9, rax; lpOptional
0x1400509f2  mov     dword ptr [rsp+190h+ppwszAcceptTypes], esi; dwTotalLength
0x1400509f6  mov     rax, r13
0x1400509f9  mov     [rsp+190h+dwFlags], esi; dwOptionalLength
0x1400509fd  neg     rax
0x140050a00  sbb     r8d, r8d; dwHeadersLength
0x140050a03  call    cs:__imp_WinHttpSendRequest
0x140050a0a  nop     dword ptr [rax+rax+00h]
0x140050a0f  test    eax, eax
0x140050a11  jnz     short loc_140050A61
0x140050a13  call    cs:__imp_GetLastError
0x140050a1a  nop     dword ptr [rax+rax+00h]
0x140050a1f  mov     ebx, eax
0x140050a21  test    eax, eax
0x140050a23  jle     short loc_140050A2E
0x140050a25  movzx   ebx, ax
0x140050a28  or      ebx, 80070000h
0x140050a2e  movzx   ecx, bx
0x140050a31  sub     ecx, 2EE2h
0x140050a37  jz      short loc_140050A48
0x140050a39  sub     ecx, 5
0x140050a3c  jz      short loc_140050A48
0x140050a3e  sub     ecx, 16h
0x140050a41  jz      short loc_140050A48
0x140050a43  cmp     ecx, 1
0x140050a46  jnz     short loc_140050A61
0x140050a48  mov     eax, [rbp+90h+var_A8]
0x140050a4b  test    eax, eax
0x140050a4d  jnz     loc_140050962
0x140050a53  jmp     short loc_140050A61
0x140050a55  mov     ebx, 1
0x140050a5a  jmp     short loc_140050A61
0x140050a5c  mov     ebx, 8007000Eh
0x140050a61  call    cs:__imp_GetProcessHeap
0x140050a68  nop     dword ptr [rax+rax+00h]
0x140050a6d  mov     r8, r12; lpMem
0x140050a70  xor     edx, edx; dwFlags
0x140050a72  mov     rcx, rax; hHeap
0x140050a75  call    cs:__imp_HeapFree
0x140050a7c  nop     dword ptr [rax+rax+00h]
0x140050a81  test    rdi, rdi
0x140050a84  jz      short loc_140050AAD
0x140050a86  call    cs:__imp_GetProcessHeap
0x140050a8d  nop     dword ptr [rax+rax+00h]
0x140050a92  mov     r8, rdi; lpMem
0x140050a95  xor     edx, edx; dwFlags
0x140050a97  mov     rcx, rax; hHeap
0x140050a9a  call    cs:__imp_HeapFree
0x140050aa1  nop     dword ptr [rax+rax+00h]
0x140050aa6  jmp     short loc_140050AAD
0x140050aa8  mov     ebx, 8007000Eh
0x140050aad  lea     rcx, [rbp+90h+var_C0]; struct _PROXY_LIST *
0x140050ab1  call    ?CloseProxyList@@YAXPEAU_PROXY_LIST@@@Z; CloseProxyList(_PROXY_LIST *)
0x140050ab6  mov     eax, ebx
0x140050ab8  mov     rcx, [rbp+90h+var_50]
0x140050abc  xor     rcx, rsp; StackCookie
0x140050abf  call    __security_check_cookie
0x140050ac4  add     rsp, 158h
0x140050acb  pop     r15
0x140050acd  pop     r14
0x140050acf  pop     r13
0x140050ad1  pop     r12
0x140050ad3  pop     rdi
0x140050ad4  pop     rsi
0x140050ad5  pop     rbx
0x140050ad6  pop     rbp
0x140050ad7  retn
```
