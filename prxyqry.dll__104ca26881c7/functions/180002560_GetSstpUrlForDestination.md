# GetSstpUrlForDestination

- ea: `0x180002560`
- end: `0x180002c7b`
- name: `GetSstpUrlForDestination`
- size: `1819`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002130`

## callees

- `0x180002560`
- `0x180002c84`
- `0x180002dd4`
- `0x180002e04`
- `0x180002eec`
- `0x180003041`
- `0x180003060`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002860`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002afb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002860`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002afb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002852`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002aed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002852`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002aed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ba1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ba1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c0f`
- `ntdll!wcstok_s` at `0x1800026bd`
- `ntdll!wcstok_s` at `0x1800026bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b5b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800029de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800029de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002a35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002a35`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002bb0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002bb0`
- `WS2_32!WSAStringToAddressW` at `0x180002833`
- `WS2_32!WSAStringToAddressW` at `0x180002833`
- `WS2_32!__imp_WSAStartup` at `0x1800025df`
- `WS2_32!__imp_WSAStartup` at `0x1800025df`
- `WS2_32!__imp_WSACleanup` at `0x180002c49`
- `WS2_32!__imp_WSACleanup` at `0x180002c49`

## string_xrefs

- `0x1800029d2`: `winhttp.dll`
- `0x180002a2b`: `WinHttpCreateUrl`

## pseudocode

```c
__int64 __fastcall GetSstpUrlForDestination(int a1, __int64 a2, _QWORD *a3)
{
  DWORD LastError; // edi
  __int64 v7; // r8
  HRESULT v8; // eax
  _QWORD *v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r9
  wchar_t *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r14
  _QWORD *v16; // rax
  wchar_t *v17; // r8
  wchar_t *v18; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v20; // rax
  _WORD *v21; // rdx
  __int64 v22; // rcx
  _WORD *v23; // rcx
  __int16 v24; // ax
  __int64 v25; // rcx
  wchar_t *v26; // rax
  __int64 v27; // r9
  _QWORD *v28; // rax
  __int64 v29; // rdx
  HMODULE Library; // rax
  HMODULE v31; // r15
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v33)(_QWORD, _QWORD, _QWORD, _QWORD); // r14
  __int64 v34; // r8
  _QWORD *v35; // rax
  __int64 v36; // rdx
  SIZE_T v37; // rbx
  HANDLE v38; // rax
  LPVOID v39; // rax
  void *v40; // rbx
  __int64 v41; // r8
  HANDLE v42; // rax
  HANDLE v43; // rax
  int v45; // [rsp+30h] [rbp-D0h] BYREF
  int AddressLength; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t *Context; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v48[6]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v49; // [rsp+58h] [rbp-A8h]
  int v50; // [rsp+60h] [rbp-A0h]
  __int16 v51; // [rsp+64h] [rbp-9Ch]
  wchar_t *v52; // [rsp+88h] [rbp-78h]
  int v53; // [rsp+90h] [rbp-70h]
  struct sockaddr Address[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct WSAData WSAData; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t pszDest[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t v57[264]; // [rsp+480h] [rbp+380h] BYREF

  AddressLength = 28;
  memset(Address, 0, 28);
  memset_0(v48, 0, 0x68u);
  v45 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  Context = 0;
  LastError = WSAStartup(2u, &WSAData);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v7, LastError, LastError);
    }
    goto LABEL_107;
  }
  if ( WSAData.wVersion == 2 )
  {
    v8 = StringCchPrintfW(pszDest, 0x104u, L"%s", a2);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_107;
      }
      v10 = 12;
LABEL_12:
      v11 = v9[2];
      v12 = (unsigned int)v8;
LABEL_13:
      WPP_SF_d(v11, v10, v9, v12);
      goto LABEL_107;
    }
    wcstok_s(pszDest, L"\\", &Context);
    if ( Context && *Context )
    {
      v8 = StringCchPrintfW(
             v57,
             0x104u,
             L"%s%s%s",
             L"/sra_{BA195980-CD49-458b-9E23-C84EE0ADCD75}/",
             L"?tenant=",
             Context);
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_107;
        }
        v10 = 13;
        goto LABEL_12;
      }
    }
    else
    {
      v8 = StringCchPrintfW(v57, 0x104u, L"%s", L"/sra_{BA195980-CD49-458b-9E23-C84EE0ADCD75}/");
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_107;
        }
        v10 = 14;
        goto LABEL_12;
      }
    }
    v13 = pszDest;
    v14 = 0x7FFFFFFF;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v14;
    }
    while ( v14 );
    v15 = (0x7FFFFFFF - v14) & -(__int64)(v14 != 0);
    if ( !v14 )
    {
      v12 = 87;
      LastError = 87;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_107;
      }
      v10 = 15;
LABEL_34:
      v11 = v16[2];
      goto LABEL_13;
    }
    *a3 = 0;
    Address[0].sa_family = 23;
    if ( WSAStringToAddressW(pszDest, 23, 0, Address, &AddressLength) == -1 )
    {
      v18 = pszDest;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v18 = (wchar_t *)HeapAlloc(ProcessHeap, 0, 2 * v15 + 6);
      if ( !v18 )
      {
        LastError = GetLastError();
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_107;
        }
        v10 = 16;
        v12 = LastError;
        goto LABEL_34;
      }
      v20 = v15 + 1;
      if ( v15 != -1 )
      {
        v21 = v18 + 1;
        if ( v20 <= 0x7FFFFFFF )
        {
          v22 = 2147483646;
          v17 = pszDest;
          do
          {
            if ( !v22 )
              break;
            if ( !*v17 )
              break;
            *v21++ = *v17++;
            --v22;
            --v20;
          }
          while ( v20 );
          v23 = v21 - 1;
          if ( v20 )
            v23 = v21;
          *v23 = 0;
        }
        else
        {
          *v21 = 0;
        }
      }
      *v18 = 91;
      v18[v15 + 1] = 93;
      v15 += 2;
      v18[v15] = 0;
    }
    v48[0] = 104;
    v49 = v18;
    v50 = v15;
    v24 = 443;
    v48[5] = (a1 != 0) + 1;
    if ( !a1 )
      v24 = 80;
    v51 = v24;
    v25 = 0x7FFFFFFF;
    v52 = v57;
    v26 = v57;
    do
    {
      if ( !*v26 )
        break;
      ++v26;
      --v25;
    }
    while ( v25 );
    if ( !v25 )
    {
      v27 = 87;
      LastError = 87;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v29 = 17;
LABEL_99:
        WPP_SF_d(v28[2], v29, v17, v27);
        goto LABEL_100;
      }
      goto LABEL_100;
    }
    if ( ((0x7FFFFFFF - v25) & ((unsigned __int128)-(__int128)(unsigned __int64)v25 >> 64)) > 0xFFFFFFFF )
    {
      v27 = 87;
      v53 = -1;
      LastError = 87;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v29 = 18;
        goto LABEL_99;
      }
      goto LABEL_100;
    }
    v53 = (0x7FFFFFFF - v25) & ((unsigned __int128)-(__int128)(unsigned __int64)v25 >> 64);
    Library = LoadLibraryExW(L"winhttp.dll", 0, 0);
    v31 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v29 = 19;
        v27 = LastError;
        goto LABEL_99;
      }
LABEL_100:
      if ( v18 && v18 != pszDest )
      {
        v43 = GetProcessHeap();
        HeapFree(v43, 0, v18);
      }
      goto LABEL_107;
    }
    ProcAddress = GetProcAddress(Library, "WinHttpCreateUrl");
    v33 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_94;
      }
      v36 = 20;
      goto LABEL_74;
    }
    if ( !((unsigned int (__fastcall *)(_DWORD *, _QWORD, _QWORD, int *))ProcAddress)(v48, 0, 0, &v45) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_94;
        }
        v36 = 21;
        goto LABEL_74;
      }
      LastError = 0;
    }
    v37 = 2LL * (unsigned int)(v45 + 1);
    v38 = GetProcessHeap();
    v39 = HeapAlloc(v38, 0, v37);
    v40 = v39;
    if ( v39 )
    {
      ++v45;
      if ( v33(v48, 0, v39, &v45) )
      {
        *a3 = v40;
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v41, LastError);
        }
        v42 = GetProcessHeap();
        HeapFree(v42, 0, v40);
      }
      goto LABEL_94;
    }
    LastError = GetLastError();
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
LABEL_94:
      FreeLibrary(v31);
      goto LABEL_100;
    }
    v36 = 22;
LABEL_74:
    WPP_SF_d(v35[2], v36, v34, LastError);
    goto LABEL_94;
  }
  LastError = 10092;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
  }
LABEL_107:
  WSACleanup();
  return LastError;
}

```

## disassembly

```asm
0x180002560  mov     [rsp-8+arg_0], rbx
0x180002565  push    rbp
0x180002566  push    rsi
0x180002567  push    rdi
0x180002568  push    r12
0x18000256a  push    r13
0x18000256c  push    r14
0x18000256e  push    r15
0x180002570  lea     rbp, [rsp-5A0h]
0x180002578  sub     rsp, 6A0h
0x18000257f  mov     rax, cs:__security_cookie
0x180002586  xor     rax, rsp
0x180002589  mov     [rbp+5D0h+var_40], rax
0x180002590  xorps   xmm0, xmm0
0x180002593  mov     [rsp+6D0h+AddressLength], 1Ch
0x18000259b  mov     rbx, rdx
0x18000259e  mov     r13, r8
0x1800025a1  xor     edx, edx; Val
0x1800025a3  mov     r12d, ecx
0x1800025a6  movups  xmmword ptr [rbp+5D0h+Address], xmm0
0x1800025aa  lea     rcx, [rsp+6D0h+var_690]; void *
0x1800025af  movups  xmmword ptr [rbp+5D0h+Address+0Ch], xmm0
0x1800025b3  lea     r8d, [rdx+68h]; Size
0x1800025b7  call    memset_0
0x1800025bc  xor     esi, esi
0x1800025be  lea     rcx, [rbp+5D0h+WSAData]; void *
0x1800025c2  xor     edx, edx; Val
0x1800025c4  mov     [rsp+6D0h+var_6A0], esi
0x1800025c8  mov     r8d, 198h; Size
0x1800025ce  call    memset_0
0x1800025d3  lea     ecx, [rsi+2]; wVersionRequested
0x1800025d6  mov     [rsp+6D0h+Context], rsi
0x1800025db  lea     rdx, [rbp+5D0h+WSAData]; lpWSAData
0x1800025df  call    cs:__imp_WSAStartup
0x1800025e5  mov     edi, eax
0x1800025e7  test    eax, eax
0x1800025e9  jz      short loc_18000262E
0x1800025eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800025f2  lea     rcx, WPP_GLOBAL_Control
0x1800025f9  cmp     rax, rcx
0x1800025fc  jz      loc_180002C49
0x180002602  test    byte ptr [rax+1Ch], 40h
0x180002606  jz      loc_180002C49
0x18000260c  cmp     byte ptr [rax+19h], 1
0x180002610  jb      loc_180002C49
0x180002616  mov     rcx, [rax+10h]
0x18000261a  lea     edx, [rsi+0Ah]
0x18000261d  mov     r9d, edi
0x180002620  mov     dword ptr [rsp+6D0h+lpAddressLength], edi
0x180002624  call    WPP_SF_dD
0x180002629  jmp     loc_180002C49
0x18000262e  movzx   eax, [rbp+5D0h+WSAData.wVersion]
0x180002632  cmp     al, 2
0x180002634  jnz     loc_180002C17
0x18000263a  shr     ax, 8
0x18000263e  test    al, al
0x180002640  jnz     loc_180002C17
0x180002646  mov     esi, 104h
0x18000264b  lea     r8, aS; "%s"
0x180002652  mov     edx, esi; cchDest
0x180002654  lea     rcx, [rbp+5D0h+pszDest]; pszDest
0x18000265b  mov     r9, rbx
0x18000265e  call    StringCchPrintfW
0x180002663  xor     ebx, ebx
0x180002665  test    eax, eax
0x180002667  jns     short loc_1800026AA
0x180002669  mov     r8, cs:WPP_GLOBAL_Control
0x180002670  lea     rcx, WPP_GLOBAL_Control
0x180002677  cmp     r8, rcx
0x18000267a  jz      loc_180002C49
0x180002680  test    byte ptr [r8+1Ch], 40h
0x180002685  jz      loc_180002C49
0x18000268b  cmp     byte ptr [r8+19h], 1
0x180002690  jb      loc_180002C49
0x180002696  lea     edx, [rbx+0Ch]
0x180002699  mov     rcx, [r8+10h]
0x18000269d  mov     r9d, eax
0x1800026a0  call    WPP_SF_d
0x1800026a5  jmp     loc_180002C49
0x1800026aa  lea     r8, [rsp+6D0h+Context]; Context
0x1800026af  lea     rdx, Delimiter; "\\"
0x1800026b6  lea     rcx, [rbp+5D0h+pszDest]; String
0x1800026bd  call    cs:__imp_wcstok_s
0x1800026c3  mov     rax, [rsp+6D0h+Context]
0x1800026c8  test    rax, rax
0x1800026cb  jz      short loc_18000273F
0x1800026cd  cmp     [rax], bx
0x1800026d0  jz      short loc_18000273F
0x1800026d2  mov     [rsp+6D0h+var_6A8], rax
0x1800026d7  lea     r9, aSraBa195980Cd4; "/sra_{BA195980-CD49-458b-9E23-C84EE0ADC"...
0x1800026de  lea     rax, aTenant; "?tenant="
0x1800026e5  mov     rdx, rsi; cchDest
0x1800026e8  lea     r8, aSSS; "%s%s%s"
0x1800026ef  mov     [rsp+6D0h+lpAddressLength], rax
0x1800026f4  lea     rcx, [rbp+5D0h+var_250]; pszDest
0x1800026fb  call    StringCchPrintfW
0x180002700  test    eax, eax
0x180002702  jns     loc_180002797
0x180002708  mov     r8, cs:WPP_GLOBAL_Control
0x18000270f  lea     rcx, WPP_GLOBAL_Control
0x180002716  cmp     r8, rcx
0x180002719  jz      loc_180002C49
0x18000271f  test    byte ptr [r8+1Ch], 40h
0x180002724  jz      loc_180002C49
0x18000272a  cmp     byte ptr [r8+19h], 1
0x18000272f  jb      loc_180002C49
0x180002735  mov     edx, 0Dh
0x18000273a  jmp     loc_180002699
0x18000273f  lea     r9, aSraBa195980Cd4; "/sra_{BA195980-CD49-458b-9E23-C84EE0ADC"...
0x180002746  mov     rdx, rsi; cchDest
0x180002749  lea     r8, aS; "%s"
0x180002750  lea     rcx, [rbp+5D0h+var_250]; pszDest
0x180002757  call    StringCchPrintfW
0x18000275c  test    eax, eax
0x18000275e  jns     short loc_180002797
0x180002760  mov     r8, cs:WPP_GLOBAL_Control
0x180002767  lea     rcx, WPP_GLOBAL_Control
0x18000276e  cmp     r8, rcx
0x180002771  jz      loc_180002C49
0x180002777  test    byte ptr [r8+1Ch], 40h
0x18000277c  jz      loc_180002C49
0x180002782  cmp     byte ptr [r8+19h], 1
0x180002787  jb      loc_180002C49
0x18000278d  mov     edx, 0Eh
0x180002792  jmp     loc_180002699
0x180002797  mov     r15d, 7FFFFFFFh
0x18000279d  lea     rax, [rbp+5D0h+pszDest]
0x1800027a4  mov     edx, r15d
0x1800027a7  cmp     [rax], bx
0x1800027aa  jz      short loc_1800027B6
0x1800027ac  add     rax, 2
0x1800027b0  sub     rdx, 1
0x1800027b4  jnz     short loc_1800027A7
0x1800027b6  mov     rcx, r15
0x1800027b9  mov     rax, rdx
0x1800027bc  sub     rcx, rdx
0x1800027bf  neg     rax
0x1800027c2  sbb     r14, r14
0x1800027c5  and     r14, rcx
0x1800027c8  test    rdx, rdx
0x1800027cb  jnz     short loc_18000280C
0x1800027cd  lea     r9d, [rdx+57h]
0x1800027d1  mov     edi, r9d
0x1800027d4  mov     rax, cs:WPP_GLOBAL_Control
0x1800027db  lea     rcx, WPP_GLOBAL_Control
0x1800027e2  cmp     rax, rcx
0x1800027e5  jz      loc_180002C49
0x1800027eb  test    byte ptr [rax+1Ch], 40h
0x1800027ef  jz      loc_180002C49
0x1800027f5  cmp     byte ptr [rax+19h], 1
0x1800027f9  jb      loc_180002C49
0x1800027ff  lea     edx, [r9-48h]
0x180002803  mov     rcx, [rax+10h]
0x180002807  jmp     loc_1800026A0
0x18000280c  mov     ecx, 17h
0x180002811  mov     [r13+0], rbx
0x180002815  mov     word ptr [rbp+5D0h+Address], cx
0x180002819  lea     rax, [rsp+6D0h+AddressLength]
0x18000281e  mov     edx, ecx; AddressFamily
0x180002820  mov     [rsp+6D0h+lpAddressLength], rax; lpAddressLength
0x180002825  lea     rcx, [rbp+5D0h+pszDest]; AddressString
0x18000282c  xor     r8d, r8d; lpProtocolInfo
0x18000282f  lea     r9, [rbp+5D0h+Address]; lpAddress
0x180002833  call    cs:__imp_WSAStringToAddressW
0x180002839  cmp     eax, 0FFFFFFFFh
0x18000283c  jnz     short loc_18000284A
0x18000283e  lea     rsi, [rbp+5D0h+pszDest]
0x180002845  jmp     loc_180002919
0x18000284a  lea     rbx, ds:6[r14*2]
0x180002852  call    cs:__imp_GetProcessHeap
0x180002858  mov     r8, rbx; dwBytes
0x18000285b  xor     edx, edx; dwFlags
0x18000285d  mov     rcx, rax; hHeap
0x180002860  call    cs:__imp_HeapAlloc
0x180002866  xor     ebx, ebx
0x180002868  mov     rsi, rax
0x18000286b  test    rax, rax
0x18000286e  jnz     short loc_1800028AE
0x180002870  call    cs:__imp_GetLastError
0x180002876  mov     edi, eax
0x180002878  mov     rax, cs:WPP_GLOBAL_Control
0x18000287f  lea     rcx, WPP_GLOBAL_Control
0x180002886  cmp     rax, rcx
0x180002889  jz      loc_180002C49
0x18000288f  test    byte ptr [rax+1Ch], 40h
0x180002893  jz      loc_180002C49
0x180002899  cmp     byte ptr [rax+19h], 1
0x18000289d  jb      loc_180002C49
0x1800028a3  lea     edx, [rsi+10h]
0x1800028a6  mov     r9d, edi
0x1800028a9  jmp     loc_180002803
0x1800028ae  lea     rax, [r14+1]
0x1800028b2  test    rax, rax
0x1800028b5  jz      short loc_180002903
0x1800028b7  lea     rdx, [rsi+2]
0x1800028bb  cmp     rax, r15
0x1800028be  jbe     short loc_1800028C5
0x1800028c0  mov     [rdx], bx
0x1800028c3  jmp     short loc_180002903
0x1800028c5  mov     ecx, 7FFFFFFEh
0x1800028ca  lea     r8, [rbp+5D0h+pszDest]
0x1800028d1  test    rcx, rcx
0x1800028d4  jz      short loc_1800028F5
0x1800028d6  movzx   r9d, word ptr [r8]
0x1800028da  test    r9w, r9w
0x1800028de  jz      short loc_1800028F5
0x1800028e0  mov     [rdx], r9w
0x1800028e4  add     r8, 2
0x1800028e8  add     rdx, 2
0x1800028ec  dec     rcx
0x1800028ef  sub     rax, 1
0x1800028f3  jnz     short loc_1800028D1
0x1800028f5  test    rax, rax
0x1800028f8  lea     rcx, [rdx-2]
0x1800028fc  cmovnz  rcx, rdx
0x180002900  mov     [rcx], bx
0x180002903  mov     word ptr [rsi], 5Bh ; '['
0x180002908  mov     word ptr [rsi+r14*2+2], 5Dh ; ']'
0x180002910  add     r14, 2
0x180002914  mov     [rsi+r14*2], bx
0x180002919  mov     eax, r12d
0x18000291c  mov     [rsp+6D0h+var_690], 68h ; 'h'
0x180002924  neg     eax
0x180002926  mov     [rsp+6D0h+var_678], rsi
0x18000292b  mov     [rsp+6D0h+var_670], r14d
0x180002930  mov     eax, 1BBh
0x180002935  sbb     ecx, ecx
0x180002937  neg     ecx
0x180002939  inc     ecx
0x18000293b  mov     [rsp+6D0h+var_67C], ecx
0x18000293f  test    r12d, r12d
0x180002942  jnz     short loc_180002949
0x180002944  mov     eax, 50h ; 'P'
0x180002949  mov     [rsp+6D0h+var_66C], ax
0x18000294e  mov     rcx, r15
0x180002951  lea     rax, [rbp+5D0h+var_250]
0x180002958  mov     [rbp+5D0h+var_648], rax
0x18000295c  lea     rax, [rbp+5D0h+var_250]
0x180002963  cmp     [rax], bx
0x180002966  jz      short loc_180002972
0x180002968  add     rax, 2
0x18000296c  sub     rcx, 1
0x180002970  jnz     short loc_180002963
0x180002972  sub     r15, rcx
0x180002975  mov     rax, rcx
0x180002978  neg     rax
0x18000297b  sbb     rdx, rdx
0x18000297e  and     rdx, r15
0x180002981  test    rcx, rcx
0x180002984  jnz     short loc_1800029C1
0x180002986  lea     r9d, [rcx+57h]
0x18000298a  mov     edi, r9d
0x18000298d  mov     rax, cs:WPP_GLOBAL_Control
0x180002994  lea     rcx, WPP_GLOBAL_Control
0x18000299b  cmp     rax, rcx
0x18000299e  jz      loc_180002BF0
0x1800029a4  test    byte ptr [rax+1Ch], 40h
0x1800029a8  jz      loc_180002BF0
0x1800029ae  cmp     byte ptr [rax+19h], 1
0x1800029b2  jb      loc_180002BF0
0x1800029b8  lea     edx, [r9-46h]
0x1800029bc  jmp     loc_180002BE7
0x1800029c1  mov     eax, 0FFFFFFFFh
0x1800029c6  cmp     rdx, rax
0x1800029c9  ja      loc_180002BB8
0x1800029cf  mov     [rbp+5D0h+var_640], edx
0x1800029d2  lea     rcx, LibFileName; "winhttp.dll"
0x1800029d9  xor     edx, edx; hFile
0x1800029db  xor     r8d, r8d; dwFlags
0x1800029de  call    cs:__imp_LoadLibraryExW
0x1800029e4  mov     r15, rax
0x1800029e7  test    rax, rax
0x1800029ea  jnz     short loc_180002A2B
0x1800029ec  call    cs:__imp_GetLastError
0x1800029f2  mov     edi, eax
0x1800029f4  mov     rax, cs:WPP_GLOBAL_Control
0x1800029fb  lea     rcx, WPP_GLOBAL_Control
0x180002a02  cmp     rax, rcx
0x180002a05  jz      loc_180002BF0
0x180002a0b  test    byte ptr [rax+1Ch], 40h
0x180002a0f  jz      loc_180002BF0
0x180002a15  cmp     byte ptr [rax+19h], 1
0x180002a19  jb      loc_180002BF0
0x180002a1f  lea     edx, [r15+13h]
0x180002a23  mov     r9d, edi
0x180002a26  jmp     loc_180002BE7
0x180002a2b  lea     rdx, ProcName; "WinHttpCreateUrl"
0x180002a32  mov     rcx, r15; hModule
0x180002a35  call    cs:__imp_GetProcAddress
0x180002a3b  mov     r14, rax
0x180002a3e  test    rax, rax
0x180002a41  jnz     short loc_180002A8B
0x180002a43  call    cs:__imp_GetLastError
0x180002a49  mov     edi, eax
0x180002a4b  mov     rax, cs:WPP_GLOBAL_Control
0x180002a52  lea     rcx, WPP_GLOBAL_Control
0x180002a59  cmp     rax, rcx
0x180002a5c  jz      loc_180002BAD
0x180002a62  test    byte ptr [rax+1Ch], 40h
0x180002a66  jz      loc_180002BAD
  ... truncated ...
```
