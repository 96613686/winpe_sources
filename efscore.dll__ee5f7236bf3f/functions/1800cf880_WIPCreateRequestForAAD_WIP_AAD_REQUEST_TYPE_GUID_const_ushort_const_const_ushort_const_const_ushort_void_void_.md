# WIPCreateRequestForAAD(_WIP_AAD_REQUEST_TYPE,_GUID * const,ushort const * const,ushort const * const,ushort * *,void * *,void * *,void * *)

- ea: `0x1800cf880`
- end: `0x1800cfe16`
- name: `?WIPCreateRequestForAAD@@YAJW4_WIP_AAD_REQUEST_TYPE@@QEAU_GUID@@QEBG2PEAPEAGPEAPEAX44@Z`
- size: `1430`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ab620`
- `0x1800baeb0`

## callees

- `0x180005045`
- `0x180012424`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800cdbe0`
- `0x1800cf880`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cfa93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cfa93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfa82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfd12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfd39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfd60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfd86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfa82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfd12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfd39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfd60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfd86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfd20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfd47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfd6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfd94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfd20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfd47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfd6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfd94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfa28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfb63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfbac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfc39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfc77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfcb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfa28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfb63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfbac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfc39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfc77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfcb5`
- `WINHTTP!WinHttpConnect` at `0x1800cfb9e`
- `WINHTTP!WinHttpConnect` at `0x1800cfb9e`
- `WINHTTP!WinHttpCrackUrl` at `0x1800cf9ff`
- `WINHTTP!WinHttpCrackUrl` at `0x1800cf9ff`
- `WINHTTP!WinHttpSetOption` at `0x1800cfc6d`
- `WINHTTP!WinHttpSetOption` at `0x1800cfc6d`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cfda2`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cfdb0`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cfdbe`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cfda2`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cfdb0`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cfdbe`
- `WINHTTP!WinHttpOpenRequest` at `0x1800cfc2b`
- `WINHTTP!WinHttpOpenRequest` at `0x1800cfc2b`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800cfcab`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800cfcab`
- `WINHTTP!WinHttpOpen` at `0x1800cfb55`
- `WINHTTP!WinHttpOpen` at `0x1800cfb55`

## pseudocode

```c
__int64 __fastcall WIPCreateRequestForAAD(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        LPVOID *a5,
        _QWORD *a6,
        _QWORD *a7,
        _QWORD *a8)
{
  void *v10; // r14
  void *v11; // r15
  void *v12; // rsi
  int v13; // ecx
  int v14; // ecx
  unsigned int v15; // ebx
  int v16; // ecx
  signed int LastError; // eax
  SIZE_T v18; // rbx
  HANDLE ProcessHeap; // rax
  int v20; // ecx
  unsigned __int16 *v21; // rbx
  int v22; // r8d
  void *v23; // rax
  signed int v24; // eax
  signed int v25; // eax
  unsigned int v26; // edi
  unsigned int v27; // edi
  const WCHAR *v28; // rdx
  void *v29; // rax
  signed int v30; // eax
  signed int v31; // eax
  signed int v32; // eax
  WCHAR *v33; // rdi
  HANDLE v34; // rax
  WCHAR *v35; // rdi
  HANDLE v36; // rax
  void *v37; // rdi
  HANDLE v38; // rax
  WCHAR *v39; // rdi
  HANDLE v40; // rax
  char dwFlags; // [rsp+28h] [rbp-B9h]
  LPVOID lpMem; // [rsp+48h] [rbp-99h] BYREF
  LPCWSTR pwszUrl; // [rsp+50h] [rbp-91h] BYREF
  LPCWSTR lpszHeaders; // [rsp+58h] [rbp-89h] BYREF
  int Buffer; // [rsp+60h] [rbp-81h] BYREF
  LPCWSTR pswzServerName; // [rsp+68h] [rbp-79h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+78h] [rbp-69h] BYREF

  pwszUrl = 0;
  lpszHeaders = 0;
  lpMem = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  pswzServerName = 0;
  Buffer = 1;
  fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 46, 172);
  if ( a5 )
    *a5 = 0;
  if ( a6 )
  {
    v14 = 0;
    *a6 = 0;
  }
  if ( a7 )
  {
    v14 = 0;
    *a7 = 0;
  }
  if ( a8 )
    *a8 = 0;
  fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 190);
  v15 = CreateWIPRequestDataForAAD(a1, a2, a3, a4, &pwszUrl, &lpszHeaders, &lpMem);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v15,
              46,
              190) >= 0
    && v15 != 1 )
  {
    memset_0(&UrlComponents, 0, sizeof(UrlComponents));
    UrlComponents.dwStructSize = 104;
    UrlComponents.dwHostNameLength = -1;
    UrlComponents.dwUrlPathLength = -1;
    if ( WinHttpCrackUrl(pwszUrl, 0, 0, &UrlComponents) )
      goto LABEL_15;
    fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 220);
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v15,
                46,
                220) >= 0 )
    {
LABEL_15:
      v18 = 2LL * (UrlComponents.dwHostNameLength + 1);
      ProcessHeap = GetProcessHeap();
      pswzServerName = (LPCWSTR)HeapAlloc(ProcessHeap, 8u, v18);
      v21 = (unsigned __int16 *)pswzServerName;
      if ( !pswzServerName )
      {
        v15 = -2147024882;
        dwFlags = -26;
        v22 = -2147024882;
LABEL_17:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v22, 46, dwFlags);
        goto LABEL_50;
      }
      fnEfsLogTrace1Strings(v20, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 235);
      v15 = StringCchCopyNW(
              v21,
              UrlComponents.dwHostNameLength + 1,
              (const unsigned __int16 *)UrlComponents.lpszHostName,
              UrlComponents.dwHostNameLength);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v15,
                  46,
                  235) < 0 )
        goto LABEL_50;
      v23 = WinHttpOpen(0, 4u, 0, 0, 0);
      v10 = v23;
      if ( !v23 )
      {
        v24 = GetLastError();
        v15 = v24;
        if ( v24 > 0 )
          v15 = (unsigned __int16)v24 | 0x80070000;
        dwFlags = -8;
LABEL_24:
        v22 = v15;
        goto LABEL_17;
      }
      v11 = WinHttpConnect(v23, pswzServerName, 0x1BBu, 0);
      if ( !v11 )
      {
        v25 = GetLastError();
        v15 = v25;
        if ( v25 > 0 )
          v15 = (unsigned __int16)v25 | 0x80070000;
        dwFlags = 2;
        goto LABEL_24;
      }
      v26 = a1 - 1;
      if ( v26 && (v27 = v26 - 1) != 0 )
      {
        if ( v27 != 1 )
        {
          v15 = -2147024809;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 46, 24);
          goto LABEL_50;
        }
        v28 = L"POST";
      }
      else
      {
        v28 = L"GET";
      }
      v29 = WinHttpOpenRequest(
              v11,
              v28,
              (LPCWSTR)UrlComponents.lpszUrlPath,
              0,
              0,
              &WIP_HTTP_OPEN_REQUEST_ACCEPT_JSON,
              0x800000u);
      v12 = v29;
      if ( !v29 )
      {
        v30 = GetLastError();
        v15 = v30;
        if ( v30 > 0 )
          v15 = (unsigned __int16)v30 | 0x80070000;
        dwFlags = 35;
        goto LABEL_24;
      }
      if ( !WinHttpSetOption(v29, 0x4Fu, &Buffer, 4u) )
      {
        v31 = GetLastError();
        v15 = v31;
        if ( v31 > 0 )
          v15 = (unsigned __int16)v31 | 0x80070000;
        dwFlags = 46;
        goto LABEL_24;
      }
      if ( !WinHttpAddRequestHeaders(v12, lpszHeaders, 0xFFFFFFFF, 0xA0000000) )
      {
        v32 = GetLastError();
        v15 = v32;
        if ( v32 > 0 )
          v15 = (unsigned __int16)v32 | 0x80070000;
        dwFlags = 55;
        goto LABEL_24;
      }
      if ( a5 )
      {
        *a5 = lpMem;
        lpMem = 0;
      }
      *a8 = v12;
      *a6 = v10;
      v10 = 0;
      *a7 = v11;
      v11 = 0;
      v12 = 0;
    }
  }
LABEL_50:
  v33 = (WCHAR *)pwszUrl;
  if ( pwszUrl )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33);
    pwszUrl = 0;
  }
  v35 = (WCHAR *)lpszHeaders;
  if ( lpszHeaders )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v35);
    lpszHeaders = 0;
  }
  v37 = lpMem;
  if ( lpMem )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v37);
    lpMem = 0;
  }
  v39 = (WCHAR *)pswzServerName;
  if ( pswzServerName )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v39);
  }
  if ( v10 )
    WinHttpCloseHandle(v10);
  if ( v11 )
    WinHttpCloseHandle(v11);
  if ( v12 )
    WinHttpCloseHandle(v12);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v15,
    46,
    98);
  return v15;
}

```

## disassembly

```asm
0x1800cf880  mov     rax, rsp
0x1800cf883  mov     [rax+8], rbx
0x1800cf887  mov     [rax+18h], r8
0x1800cf88b  mov     [rax+10h], rdx
0x1800cf88f  push    rbp
0x1800cf890  push    rsi
0x1800cf891  push    rdi
0x1800cf892  push    r12
0x1800cf894  push    r13
0x1800cf896  push    r14
0x1800cf898  push    r15
0x1800cf89a  lea     rbp, [rax-3Fh]
0x1800cf89e  sub     rsp, 0E0h
0x1800cf8a5  xor     r13d, r13d
0x1800cf8a8  mov     edi, ecx
0x1800cf8aa  xor     edx, edx; Val
0x1800cf8ac  mov     [rsp+110h+pwszUrl], r13
0x1800cf8b1  lea     rcx, [rbp+37h+UrlComponents]; void *
0x1800cf8b5  mov     [rsp+110h+lpszHeaders], r13
0x1800cf8ba  mov     rbx, r9
0x1800cf8bd  mov     [rsp+110h+lpMem], r13
0x1800cf8c2  lea     r8d, [r13+68h]; Size
0x1800cf8c6  mov     r14d, r13d
0x1800cf8c9  mov     r15d, r13d
0x1800cf8cc  mov     esi, r13d
0x1800cf8cf  call    memset_0
0x1800cf8d4  lea     r9d, [r13+2Eh]
0x1800cf8d8  mov     [rbp+37h+pswzServerName], r13
0x1800cf8dc  lea     r8, sourceString
0x1800cf8e3  mov     [rsp+110h+Buffer], 1
0x1800cf8eb  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800cf8f2  mov     [rsp+110h+dwFlags], 3ACh
0x1800cf8fa  call    fnEfsLogTrace1Strings
0x1800cf8ff  mov     r12, [rbp+37h+arg_20]
0x1800cf903  test    r12, r12
0x1800cf906  jz      short loc_1800CF90E
0x1800cf908  xor     eax, eax
0x1800cf90a  mov     [r12], rax
0x1800cf90e  mov     rax, [rbp+37h+arg_28]
0x1800cf912  test    rax, rax
0x1800cf915  jz      short loc_1800CF91C
0x1800cf917  xor     ecx, ecx
0x1800cf919  mov     [rax], rcx
0x1800cf91c  mov     rax, [rbp+37h+arg_30]
0x1800cf920  test    rax, rax
0x1800cf923  jz      short loc_1800CF92A
0x1800cf925  xor     ecx, ecx
0x1800cf927  mov     [rax], rcx
0x1800cf92a  mov     r13, [rbp+37h+arg_38]
0x1800cf92e  test    r13, r13
0x1800cf931  jz      short loc_1800CF939
0x1800cf933  xor     eax, eax
0x1800cf935  mov     [r13+0], rax
0x1800cf939  mov     r9d, 2Eh ; '.'
0x1800cf93f  mov     [rsp+110h+dwFlags], 3BEh
0x1800cf947  lea     r8, sourceString
0x1800cf94e  lea     rdx, EFS_TRACE_START_EVENT
0x1800cf955  call    fnEfsLogTrace1Strings
0x1800cf95a  mov     r8, [rbp+37h+arg_10]
0x1800cf95e  lea     rax, [rsp+110h+lpMem]
0x1800cf963  mov     rdx, [rbp+37h+arg_8]
0x1800cf967  mov     r9, rbx
0x1800cf96a  mov     [rsp+30h], rax
0x1800cf96f  mov     ecx, edi
0x1800cf971  lea     rax, [rsp+110h+lpszHeaders]
0x1800cf976  mov     [rsp+110h+ppwszAcceptTypes], rax
0x1800cf97b  lea     rax, [rsp+110h+pwszUrl]
0x1800cf980  mov     qword ptr [rsp+110h+dwFlags], rax
0x1800cf985  call    ?CreateWIPRequestDataForAAD@@YAJW4_WIP_AAD_REQUEST_TYPE@@QEAU_GUID@@QEBG2PEAPEAG33@Z; CreateWIPRequestDataForAAD(_WIP_AAD_REQUEST_TYPE,_GUID * const,ushort const * const,ushort const * const,ushort * *,ushort * *,ushort * *)
0x1800cf98a  mov     rcx, cs:g_hPublisher
0x1800cf991  lea     r9, sourceString
0x1800cf998  mov     dword ptr [rsp+30h], 3BEh
0x1800cf9a0  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cf9a7  mov     dword ptr [rsp+110h+ppwszAcceptTypes], 2Eh ; '.'
0x1800cf9af  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cf9b6  mov     [rsp+110h+dwFlags], eax
0x1800cf9ba  mov     ebx, eax
0x1800cf9bc  call    fnEfsLogTrace1String1Dword
0x1800cf9c1  test    eax, eax
0x1800cf9c3  js      loc_1800CFD08
0x1800cf9c9  cmp     ebx, 1
0x1800cf9cc  jz      loc_1800CFD08
0x1800cf9d2  mov     ebx, 68h ; 'h'
0x1800cf9d7  lea     rcx, [rbp+37h+UrlComponents]; void *
0x1800cf9db  mov     r8d, ebx; Size
0x1800cf9de  xor     edx, edx; Val
0x1800cf9e0  call    memset_0
0x1800cf9e5  mov     rcx, [rsp+110h+pwszUrl]; pwszUrl
0x1800cf9ea  lea     r9, [rbp+37h+UrlComponents]; lpUrlComponents
0x1800cf9ee  or      eax, 0FFFFFFFFh
0x1800cf9f1  mov     [rbp+37h+UrlComponents.dwStructSize], ebx
0x1800cf9f4  xor     r8d, r8d; dwFlags
0x1800cf9f7  mov     [rbp+37h+UrlComponents.dwHostNameLength], eax
0x1800cf9fa  xor     edx, edx; dwUrlLength
0x1800cf9fc  mov     [rbp+37h+UrlComponents.dwUrlPathLength], eax
0x1800cf9ff  call    cs:__imp_WinHttpCrackUrl
0x1800cfa05  test    eax, eax
0x1800cfa07  jnz     short loc_1800CFA7A
0x1800cfa09  lea     r9d, [rbx-3Ah]
0x1800cfa0d  mov     [rsp+110h+dwFlags], 3DCh
0x1800cfa15  lea     r8, sourceString
0x1800cfa1c  lea     rdx, EFS_TRACE_START_EVENT
0x1800cfa23  call    fnEfsLogTrace1Strings
0x1800cfa28  call    cs:__imp_GetLastError
0x1800cfa2e  mov     ebx, eax
0x1800cfa30  test    eax, eax
0x1800cfa32  jle     short loc_1800CFA3D
0x1800cfa34  movzx   ebx, ax
0x1800cfa37  or      ebx, 80070000h
0x1800cfa3d  mov     rcx, cs:g_hPublisher
0x1800cfa44  lea     r9, sourceString
0x1800cfa4b  mov     dword ptr [rsp+30h], 3DCh
0x1800cfa53  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cfa5a  mov     dword ptr [rsp+110h+ppwszAcceptTypes], 2Eh ; '.'
0x1800cfa62  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cfa69  mov     [rsp+110h+dwFlags], ebx
0x1800cfa6d  call    fnEfsLogTrace1String1Dword
0x1800cfa72  test    eax, eax
0x1800cfa74  js      loc_1800CFD08
0x1800cfa7a  mov     ebx, [rbp+37h+UrlComponents.dwHostNameLength]
0x1800cfa7d  inc     ebx
0x1800cfa7f  add     rbx, rbx
0x1800cfa82  call    cs:__imp_GetProcessHeap
0x1800cfa88  mov     r8, rbx; dwBytes
0x1800cfa8b  mov     edx, 8; dwFlags
0x1800cfa90  mov     rcx, rax; hHeap
0x1800cfa93  call    cs:__imp_HeapAlloc
0x1800cfa99  mov     [rbp+37h+pswzServerName], rax
0x1800cfa9d  mov     rbx, rax
0x1800cfaa0  mov     r9d, 2Eh ; '.'
0x1800cfaa6  test    rax, rax
0x1800cfaa9  jnz     short loc_1800CFAD6
0x1800cfaab  mov     ebx, 8007000Eh
0x1800cfab0  mov     [rsp+110h+dwFlags], 3E6h
0x1800cfab8  mov     r8d, 8007000Eh
0x1800cfabe  mov     rcx, cs:g_hPublisher
0x1800cfac5  lea     rdx, EFS_TRACE_ERROR
0x1800cfacc  call    fnEfsLogTrace1
0x1800cfad1  jmp     loc_1800CFD08
0x1800cfad6  lea     r8, sourceString
0x1800cfadd  mov     [rsp+110h+dwFlags], 3EBh
0x1800cfae5  lea     rdx, EFS_TRACE_START_EVENT
0x1800cfaec  call    fnEfsLogTrace1Strings
0x1800cfaf1  mov     eax, [rbp+37h+UrlComponents.dwHostNameLength]
0x1800cfaf4  mov     rcx, rbx; unsigned __int16 *
0x1800cfaf7  mov     r8, [rbp+37h+UrlComponents.lpszHostName]; unsigned __int16 *
0x1800cfafb  mov     r9d, eax; unsigned __int64
0x1800cfafe  lea     edx, [rax+1]; unsigned __int64
0x1800cfb01  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800cfb06  mov     rcx, cs:g_hPublisher
0x1800cfb0d  lea     r9, sourceString
0x1800cfb14  mov     dword ptr [rsp+30h], 3EBh
0x1800cfb1c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cfb23  mov     dword ptr [rsp+110h+ppwszAcceptTypes], 2Eh ; '.'
0x1800cfb2b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cfb32  mov     [rsp+110h+dwFlags], eax
0x1800cfb36  mov     ebx, eax
0x1800cfb38  call    fnEfsLogTrace1String1Dword
0x1800cfb3d  test    eax, eax
0x1800cfb3f  js      loc_1800CFD08
0x1800cfb45  xor     r9d, r9d; pszProxyBypassW
0x1800cfb48  mov     [rsp+110h+dwFlags], esi; dwFlags
0x1800cfb4c  xor     r8d, r8d; pszProxyW
0x1800cfb4f  xor     ecx, ecx; pszAgentW
0x1800cfb51  lea     edx, [r9+4]; dwAccessType
0x1800cfb55  call    cs:__imp_WinHttpOpen
0x1800cfb5b  mov     r14, rax
0x1800cfb5e  test    rax, rax
0x1800cfb61  jnz     short loc_1800CFB8E
0x1800cfb63  call    cs:__imp_GetLastError
0x1800cfb69  mov     ebx, eax
0x1800cfb6b  test    eax, eax
0x1800cfb6d  jle     short loc_1800CFB78
0x1800cfb6f  movzx   ebx, ax
0x1800cfb72  or      ebx, 80070000h
0x1800cfb78  mov     [rsp+110h+dwFlags], 3F8h
0x1800cfb80  mov     r9d, 2Eh ; '.'
0x1800cfb86  mov     r8d, ebx
0x1800cfb89  jmp     loc_1800CFABE
0x1800cfb8e  mov     rdx, [rbp+37h+pswzServerName]; pswzServerName
0x1800cfb92  mov     r8d, 1BBh; nServerPort
0x1800cfb98  xor     r9d, r9d; dwReserved
0x1800cfb9b  mov     rcx, r14; hSession
0x1800cfb9e  call    cs:__imp_WinHttpConnect
0x1800cfba4  mov     r15, rax
0x1800cfba7  test    rax, rax
0x1800cfbaa  jnz     short loc_1800CFBCB
0x1800cfbac  call    cs:__imp_GetLastError
0x1800cfbb2  mov     ebx, eax
0x1800cfbb4  test    eax, eax
0x1800cfbb6  jle     short loc_1800CFBC1
0x1800cfbb8  movzx   ebx, ax
0x1800cfbbb  or      ebx, 80070000h
0x1800cfbc1  mov     [rsp+110h+dwFlags], 402h
0x1800cfbc9  jmp     short loc_1800CFB80
0x1800cfbcb  sub     edi, 1
0x1800cfbce  jz      short loc_1800CFC01
0x1800cfbd0  sub     edi, 1
0x1800cfbd3  jz      short loc_1800CFC01
0x1800cfbd5  cmp     edi, 1
0x1800cfbd8  jz      short loc_1800CFBF8
0x1800cfbda  mov     ebx, 80070057h
0x1800cfbdf  mov     [rsp+110h+dwFlags], 418h
0x1800cfbe7  mov     r9d, 2Eh ; '.'
0x1800cfbed  mov     r8d, 80070057h
0x1800cfbf3  jmp     loc_1800CFABE
0x1800cfbf8  lea     rdx, aPost; "POST"
0x1800cfbff  jmp     short loc_1800CFC08
0x1800cfc01  lea     rdx, pwszVerb; "GET"
0x1800cfc08  mov     r8, [rbp+37h+UrlComponents.lpszUrlPath]; pwszObjectName
0x1800cfc0c  lea     rax, ?WIP_HTTP_OPEN_REQUEST_ACCEPT_JSON@@3PAPEBGA; ushort const * near * WIP_HTTP_OPEN_REQUEST_ACCEPT_JSON
0x1800cfc13  mov     dword ptr [rsp+30h], 800000h; dwFlags
0x1800cfc1b  xor     r9d, r9d; pwszVersion
0x1800cfc1e  mov     [rsp+110h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x1800cfc23  mov     rcx, r15; hConnect
0x1800cfc26  mov     qword ptr [rsp+110h+dwFlags], rsi; pwszReferrer
0x1800cfc2b  call    cs:__imp_WinHttpOpenRequest
0x1800cfc31  mov     rsi, rax
0x1800cfc34  test    rax, rax
0x1800cfc37  jnz     short loc_1800CFC5B
0x1800cfc39  call    cs:__imp_GetLastError
0x1800cfc3f  mov     ebx, eax
0x1800cfc41  test    eax, eax
0x1800cfc43  jle     short loc_1800CFC4E
0x1800cfc45  movzx   ebx, ax
0x1800cfc48  or      ebx, 80070000h
0x1800cfc4e  mov     [rsp+110h+dwFlags], 423h
0x1800cfc56  jmp     loc_1800CFB80
0x1800cfc5b  mov     r9d, 4; dwBufferLength
0x1800cfc61  lea     r8, [rsp+110h+Buffer]; lpBuffer
0x1800cfc66  mov     rcx, rsi; hInternet
0x1800cfc69  lea     edx, [r9+4Bh]; dwOption
0x1800cfc6d  call    cs:__imp_WinHttpSetOption
0x1800cfc73  test    eax, eax
0x1800cfc75  jnz     short loc_1800CFC99
0x1800cfc77  call    cs:__imp_GetLastError
0x1800cfc7d  mov     ebx, eax
0x1800cfc7f  test    eax, eax
0x1800cfc81  jle     short loc_1800CFC8C
0x1800cfc83  movzx   ebx, ax
0x1800cfc86  or      ebx, 80070000h
0x1800cfc8c  mov     [rsp+110h+dwFlags], 42Eh
0x1800cfc94  jmp     loc_1800CFB80
0x1800cfc99  mov     rdx, [rsp+110h+lpszHeaders]; lpszHeaders
0x1800cfc9e  mov     r9d, 0A0000000h; dwModifiers
0x1800cfca4  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x1800cfca8  mov     rcx, rsi; hRequest
0x1800cfcab  call    cs:__imp_WinHttpAddRequestHeaders
0x1800cfcb1  test    eax, eax
0x1800cfcb3  jnz     short loc_1800CFCD7
0x1800cfcb5  call    cs:__imp_GetLastError
0x1800cfcbb  mov     ebx, eax
0x1800cfcbd  test    eax, eax
0x1800cfcbf  jle     short loc_1800CFCCA
0x1800cfcc1  movzx   ebx, ax
0x1800cfcc4  or      ebx, 80070000h
0x1800cfcca  mov     [rsp+110h+dwFlags], 437h
0x1800cfcd2  jmp     loc_1800CFB80
0x1800cfcd7  test    r12, r12
0x1800cfcda  jz      short loc_1800CFCEE
0x1800cfcdc  mov     rax, [rsp+110h+lpMem]
0x1800cfce1  mov     [r12], rax
0x1800cfce5  mov     [rsp+110h+lpMem], 0
0x1800cfcee  mov     rax, [rbp+37h+arg_28]
0x1800cfcf2  mov     [r13+0], rsi
0x1800cfcf6  mov     [rax], r14
0x1800cfcf9  xor     r14d, r14d
0x1800cfcfc  mov     rax, [rbp+37h+arg_30]
0x1800cfd00  mov     [rax], r15
0x1800cfd03  xor     r15d, r15d
0x1800cfd06  xor     esi, esi
0x1800cfd08  mov     rdi, [rsp+110h+pwszUrl]
0x1800cfd0d  test    rdi, rdi
0x1800cfd10  jz      short loc_1800CFD2F
0x1800cfd12  call    cs:__imp_GetProcessHeap
0x1800cfd18  mov     r8, rdi; lpMem
0x1800cfd1b  xor     edx, edx; dwFlags
0x1800cfd1d  mov     rcx, rax; hHeap
0x1800cfd20  call    cs:__imp_HeapFree
0x1800cfd26  mov     [rsp+110h+pwszUrl], 0
0x1800cfd2f  mov     rdi, [rsp+110h+lpszHeaders]
0x1800cfd34  test    rdi, rdi
0x1800cfd37  jz      short loc_1800CFD56
0x1800cfd39  call    cs:__imp_GetProcessHeap
0x1800cfd3f  mov     r8, rdi; lpMem
0x1800cfd42  xor     edx, edx; dwFlags
0x1800cfd44  mov     rcx, rax; hHeap
0x1800cfd47  call    cs:__imp_HeapFree
0x1800cfd4d  mov     [rsp+110h+lpszHeaders], 0
0x1800cfd56  mov     rdi, [rsp+110h+lpMem]
0x1800cfd5b  test    rdi, rdi
0x1800cfd5e  jz      short loc_1800CFD7D
0x1800cfd60  call    cs:__imp_GetProcessHeap
0x1800cfd66  mov     r8, rdi; lpMem
0x1800cfd69  xor     edx, edx; dwFlags
0x1800cfd6b  mov     rcx, rax; hHeap
0x1800cfd6e  call    cs:__imp_HeapFree
0x1800cfd74  mov     [rsp+110h+lpMem], 0
0x1800cfd7d  mov     rdi, [rbp+37h+pswzServerName]
0x1800cfd81  test    rdi, rdi
  ... truncated ...
```
