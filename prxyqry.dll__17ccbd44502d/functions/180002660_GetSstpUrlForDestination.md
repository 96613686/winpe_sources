# GetSstpUrlForDestination

- ea: `0x180002660`
- end: `0x180002e02`
- name: `GetSstpUrlForDestination`
- size: `1954`
- prototype: `__int64 __fastcall(int, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800021c0`

## callees

- `0x180002660`
- `0x180002e08`
- `0x180002f68`
- `0x180002fa0`
- `0x180003098`
- `0x180003201`
- `0x180003220`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002978`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002978`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002964`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002964`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d89`
- `ntdll!wcstok_s` at `0x1800027c3`
- `ntdll!wcstok_s` at `0x1800027c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000298e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000298e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cb7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002b02`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002b02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002b65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002b65`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002d1e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002d1e`
- `WS2_32!WSAStringToAddressW` at `0x18000293f`
- `WS2_32!WSAStringToAddressW` at `0x18000293f`
- `WS2_32!__imp_WSAStartup` at `0x1800026df`
- `WS2_32!__imp_WSAStartup` at `0x1800026df`
- `WS2_32!__imp_WSACleanup` at `0x180002dc9`
- `WS2_32!__imp_WSACleanup` at `0x180002dc9`

## string_xrefs

- `0x180002af6`: `winhttp.dll`
- `0x180002b5b`: `WinHttpCreateUrl`

## pseudocode

```c
__int64 __fastcall GetSstpUrlForDestination(int a1, __int64 a2, _QWORD *a3)
{
  DWORD LastError; // edi
  __int64 v7; // r8
  _QWORD *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  wchar_t *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r14
  _QWORD *v14; // rax
  wchar_t *v15; // r8
  wchar_t *v16; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v18; // rax
  _WORD *v19; // rdx
  __int64 v20; // rcx
  _WORD *v21; // rcx
  __int16 v22; // ax
  __int64 v23; // rcx
  wchar_t *v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rdx
  HMODULE Library; // rax
  HMODULE v28; // r15
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v30)(_QWORD, _QWORD, _QWORD, _QWORD); // r14
  __int64 v31; // r8
  _QWORD *v32; // rax
  __int64 v33; // rdx
  SIZE_T v34; // rbx
  HANDLE v35; // rax
  LPVOID v36; // rax
  void *v37; // rbx
  __int64 v38; // r8
  HANDLE v39; // rax
  HANDLE v40; // rax
  int v42; // [rsp+30h] [rbp-D0h] BYREF
  int AddressLength; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t *Context; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v45[6]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v46; // [rsp+58h] [rbp-A8h]
  int v47; // [rsp+60h] [rbp-A0h]
  __int16 v48; // [rsp+64h] [rbp-9Ch]
  wchar_t *v49; // [rsp+88h] [rbp-78h]
  int v50; // [rsp+90h] [rbp-70h]
  struct sockaddr Address[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct WSAData WSAData; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t pszDest[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t v54[264]; // [rsp+480h] [rbp+380h] BYREF

  AddressLength = 28;
  memset(Address, 0, 28);
  memset_0(v45, 0, 0x68u);
  v42 = 0;
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
    if ( StringCchPrintfW(pszDest, 0x104u, L"%s", a2) < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_107;
      }
      v9 = 12;
LABEL_12:
      v10 = v8[2];
LABEL_13:
      WPP_SF_d(v10, v9, v8);
      goto LABEL_107;
    }
    wcstok_s(pszDest, L"\\", &Context);
    if ( Context && *Context )
    {
      if ( StringCchPrintfW(
             v54,
             0x104u,
             L"%s%s%s",
             L"/sra_{BA195980-CD49-458b-9E23-C84EE0ADCD75}/",
             L"?tenant=",
             Context) < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_107;
        }
        v9 = 13;
        goto LABEL_12;
      }
    }
    else if ( StringCchPrintfW(v54, 0x104u, L"%s", L"/sra_{BA195980-CD49-458b-9E23-C84EE0ADCD75}/") < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_107;
      }
      v9 = 14;
      goto LABEL_12;
    }
    v11 = pszDest;
    v12 = 0x7FFFFFFF;
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v12;
    }
    while ( v12 );
    v13 = (0x7FFFFFFF - v12) & -(__int64)(v12 != 0);
    if ( !v12 )
    {
      LastError = 87;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_107;
      }
      v9 = 15;
LABEL_34:
      v10 = v14[2];
      goto LABEL_13;
    }
    *a3 = 0;
    Address[0].sa_family = 23;
    if ( WSAStringToAddressW(pszDest, 23, 0, Address, &AddressLength) == -1 )
    {
      v16 = pszDest;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v16 = (wchar_t *)HeapAlloc(ProcessHeap, 0, 2 * v13 + 6);
      if ( !v16 )
      {
        LastError = GetLastError();
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_107;
        }
        v9 = 16;
        goto LABEL_34;
      }
      v18 = v13 + 1;
      if ( v13 != -1 )
      {
        v19 = v16 + 1;
        if ( v18 <= 0x7FFFFFFF )
        {
          v20 = 2147483646;
          v15 = pszDest;
          do
          {
            if ( !v20 )
              break;
            if ( !*v15 )
              break;
            *v19++ = *v15++;
            --v20;
            --v18;
          }
          while ( v18 );
          v21 = v19 - 1;
          if ( v18 )
            v21 = v19;
          *v21 = 0;
        }
        else
        {
          *v19 = 0;
        }
      }
      *v16 = 91;
      v16[v13 + 1] = 93;
      v13 += 2;
      v16[v13] = 0;
    }
    v45[0] = 104;
    v46 = v16;
    v47 = v13;
    v22 = 443;
    v45[5] = (a1 != 0) + 1;
    if ( !a1 )
      v22 = 80;
    v48 = v22;
    v23 = 0x7FFFFFFF;
    v49 = v54;
    v24 = v54;
    do
    {
      if ( !*v24 )
        break;
      ++v24;
      --v23;
    }
    while ( v23 );
    if ( !v23 )
    {
      LastError = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v26 = 17;
LABEL_99:
        WPP_SF_d(v25[2], v26, v15);
        goto LABEL_100;
      }
      goto LABEL_100;
    }
    if ( ((0x7FFFFFFF - v23) & ((unsigned __int128)-(__int128)(unsigned __int64)v23 >> 64)) > 0xFFFFFFFF )
    {
      v50 = -1;
      LastError = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v26 = 18;
        goto LABEL_99;
      }
      goto LABEL_100;
    }
    v50 = (0x7FFFFFFF - v23) & ((unsigned __int128)-(__int128)(unsigned __int64)v23 >> 64);
    Library = LoadLibraryExW(L"winhttp.dll", 0, 0);
    v28 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v26 = 19;
        goto LABEL_99;
      }
LABEL_100:
      if ( v16 && v16 != pszDest )
      {
        v40 = GetProcessHeap();
        HeapFree(v40, 0, v16);
      }
      goto LABEL_107;
    }
    ProcAddress = GetProcAddress(Library, "WinHttpCreateUrl");
    v30 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_94;
      }
      v33 = 20;
      goto LABEL_74;
    }
    if ( !((unsigned int (__fastcall *)(_DWORD *, _QWORD, _QWORD, int *))ProcAddress)(v45, 0, 0, &v42) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_94;
        }
        v33 = 21;
        goto LABEL_74;
      }
      LastError = 0;
    }
    v34 = 2LL * (unsigned int)(v42 + 1);
    v35 = GetProcessHeap();
    v36 = HeapAlloc(v35, 0, v34);
    v37 = v36;
    if ( v36 )
    {
      ++v42;
      if ( v30(v45, 0, v36, &v42) )
      {
        *a3 = v37;
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v38);
        }
        v39 = GetProcessHeap();
        HeapFree(v39, 0, v37);
      }
      goto LABEL_94;
    }
    LastError = GetLastError();
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
LABEL_94:
      FreeLibrary(v28);
      goto LABEL_100;
    }
    v33 = 22;
LABEL_74:
    WPP_SF_d(v32[2], v33, v31);
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
0x180002660  mov     [rsp-8+arg_0], rbx
0x180002665  push    rbp
0x180002666  push    rsi
0x180002667  push    rdi
0x180002668  push    r12
0x18000266a  push    r13
0x18000266c  push    r14
0x18000266e  push    r15
0x180002670  lea     rbp, [rsp-5A0h]
0x180002678  sub     rsp, 6A0h
0x18000267f  mov     rax, cs:__security_cookie
0x180002686  xor     rax, rsp
0x180002689  mov     [rbp+5D0h+var_40], rax
0x180002690  xorps   xmm0, xmm0
0x180002693  mov     [rsp+6D0h+AddressLength], 1Ch
0x18000269b  mov     rbx, rdx
0x18000269e  mov     r13, r8
0x1800026a1  xor     edx, edx; Val
0x1800026a3  mov     r12d, ecx
0x1800026a6  movups  xmmword ptr [rbp+5D0h+Address], xmm0
0x1800026aa  lea     rcx, [rsp+6D0h+var_690]; void *
0x1800026af  movups  xmmword ptr [rbp+5D0h+Address+0Ch], xmm0
0x1800026b3  lea     r8d, [rdx+68h]; Size
0x1800026b7  call    memset_0
0x1800026bc  xor     esi, esi
0x1800026be  lea     rcx, [rbp+5D0h+WSAData]; void *
0x1800026c2  xor     edx, edx; Val
0x1800026c4  mov     [rsp+6D0h+var_6A0], esi
0x1800026c8  mov     r8d, 198h; Size
0x1800026ce  call    memset_0
0x1800026d3  lea     ecx, [rsi+2]; wVersionRequested
0x1800026d6  mov     [rsp+6D0h+Context], rsi
0x1800026db  lea     rdx, [rbp+5D0h+WSAData]; lpWSAData
0x1800026df  call    cs:__imp_WSAStartup
0x1800026e6  nop     dword ptr [rax+rax+00h]
0x1800026eb  mov     edi, eax
0x1800026ed  test    eax, eax
0x1800026ef  jz      short loc_180002734
0x1800026f1  mov     rax, cs:WPP_GLOBAL_Control
0x1800026f8  lea     rcx, WPP_GLOBAL_Control
0x1800026ff  cmp     rax, rcx
0x180002702  jz      loc_180002DC9
0x180002708  test    byte ptr [rax+1Ch], 40h
0x18000270c  jz      loc_180002DC9
0x180002712  cmp     byte ptr [rax+19h], 1
0x180002716  jb      loc_180002DC9
0x18000271c  mov     rcx, [rax+10h]
0x180002720  lea     edx, [rsi+0Ah]
0x180002723  mov     r9d, edi
0x180002726  mov     dword ptr [rsp+6D0h+lpAddressLength], edi
0x18000272a  call    WPP_SF_dD
0x18000272f  jmp     loc_180002DC9
0x180002734  movzx   eax, [rbp+5D0h+WSAData.wVersion]
0x180002738  cmp     al, 2
0x18000273a  jnz     loc_180002D97
0x180002740  shr     ax, 8
0x180002744  test    al, al
0x180002746  jnz     loc_180002D97
0x18000274c  mov     esi, 104h
0x180002751  lea     r8, aS; "%s"
0x180002758  mov     edx, esi; cchDest
0x18000275a  lea     rcx, [rbp+5D0h+pszDest]; pszDest
0x180002761  mov     r9, rbx
0x180002764  call    StringCchPrintfW
0x180002769  xor     ebx, ebx
0x18000276b  test    eax, eax
0x18000276d  jns     short loc_1800027B0
0x18000276f  mov     r8, cs:WPP_GLOBAL_Control
0x180002776  lea     rcx, WPP_GLOBAL_Control
0x18000277d  cmp     r8, rcx
0x180002780  jz      loc_180002DC9
0x180002786  test    byte ptr [r8+1Ch], 40h
0x18000278b  jz      loc_180002DC9
0x180002791  cmp     byte ptr [r8+19h], 1
0x180002796  jb      loc_180002DC9
0x18000279c  lea     edx, [rbx+0Ch]
0x18000279f  mov     rcx, [r8+10h]
0x1800027a3  mov     r9d, eax
0x1800027a6  call    WPP_SF_d
0x1800027ab  jmp     loc_180002DC9
0x1800027b0  lea     r8, [rsp+6D0h+Context]; Context
0x1800027b5  lea     rdx, Delimiter; "\\"
0x1800027bc  lea     rcx, [rbp+5D0h+pszDest]; String
0x1800027c3  call    cs:__imp_wcstok_s
0x1800027ca  nop     dword ptr [rax+rax+00h]
0x1800027cf  mov     rax, [rsp+6D0h+Context]
0x1800027d4  test    rax, rax
0x1800027d7  jz      short loc_18000284B
0x1800027d9  cmp     [rax], bx
0x1800027dc  jz      short loc_18000284B
0x1800027de  mov     [rsp+6D0h+var_6A8], rax
0x1800027e3  lea     r9, aSraBa195980Cd4; "/sra_{BA195980-CD49-458b-9E23-C84EE0ADC"...
0x1800027ea  lea     rax, aTenant; "?tenant="
0x1800027f1  mov     rdx, rsi; cchDest
0x1800027f4  lea     r8, aSSS; "%s%s%s"
0x1800027fb  mov     [rsp+6D0h+lpAddressLength], rax
0x180002800  lea     rcx, [rbp+5D0h+var_250]; pszDest
0x180002807  call    StringCchPrintfW
0x18000280c  test    eax, eax
0x18000280e  jns     loc_1800028A3
0x180002814  mov     r8, cs:WPP_GLOBAL_Control
0x18000281b  lea     rcx, WPP_GLOBAL_Control
0x180002822  cmp     r8, rcx
0x180002825  jz      loc_180002DC9
0x18000282b  test    byte ptr [r8+1Ch], 40h
0x180002830  jz      loc_180002DC9
0x180002836  cmp     byte ptr [r8+19h], 1
0x18000283b  jb      loc_180002DC9
0x180002841  mov     edx, 0Dh
0x180002846  jmp     loc_18000279F
0x18000284b  lea     r9, aSraBa195980Cd4; "/sra_{BA195980-CD49-458b-9E23-C84EE0ADC"...
0x180002852  mov     rdx, rsi; cchDest
0x180002855  lea     r8, aS; "%s"
0x18000285c  lea     rcx, [rbp+5D0h+var_250]; pszDest
0x180002863  call    StringCchPrintfW
0x180002868  test    eax, eax
0x18000286a  jns     short loc_1800028A3
0x18000286c  mov     r8, cs:WPP_GLOBAL_Control
0x180002873  lea     rcx, WPP_GLOBAL_Control
0x18000287a  cmp     r8, rcx
0x18000287d  jz      loc_180002DC9
0x180002883  test    byte ptr [r8+1Ch], 40h
0x180002888  jz      loc_180002DC9
0x18000288e  cmp     byte ptr [r8+19h], 1
0x180002893  jb      loc_180002DC9
0x180002899  mov     edx, 0Eh
0x18000289e  jmp     loc_18000279F
0x1800028a3  mov     r15d, 7FFFFFFFh
0x1800028a9  lea     rax, [rbp+5D0h+pszDest]
0x1800028b0  mov     edx, r15d
0x1800028b3  cmp     [rax], bx
0x1800028b6  jz      short loc_1800028C2
0x1800028b8  add     rax, 2
0x1800028bc  sub     rdx, 1
0x1800028c0  jnz     short loc_1800028B3
0x1800028c2  mov     rcx, r15
0x1800028c5  mov     rax, rdx
0x1800028c8  sub     rcx, rdx
0x1800028cb  neg     rax
0x1800028ce  sbb     r14, r14
0x1800028d1  and     r14, rcx
0x1800028d4  test    rdx, rdx
0x1800028d7  jnz     short loc_180002918
0x1800028d9  lea     r9d, [rdx+57h]
0x1800028dd  mov     edi, r9d
0x1800028e0  mov     rax, cs:WPP_GLOBAL_Control
0x1800028e7  lea     rcx, WPP_GLOBAL_Control
0x1800028ee  cmp     rax, rcx
0x1800028f1  jz      loc_180002DC9
0x1800028f7  test    byte ptr [rax+1Ch], 40h
0x1800028fb  jz      loc_180002DC9
0x180002901  cmp     byte ptr [rax+19h], 1
0x180002905  jb      loc_180002DC9
0x18000290b  lea     edx, [r9-48h]
0x18000290f  mov     rcx, [rax+10h]
0x180002913  jmp     loc_1800027A6
0x180002918  mov     ecx, 17h
0x18000291d  mov     [r13+0], rbx
0x180002921  mov     word ptr [rbp+5D0h+Address], cx
0x180002925  lea     rax, [rsp+6D0h+AddressLength]
0x18000292a  mov     edx, ecx; AddressFamily
0x18000292c  mov     [rsp+6D0h+lpAddressLength], rax; lpAddressLength
0x180002931  lea     rcx, [rbp+5D0h+pszDest]; AddressString
0x180002938  xor     r8d, r8d; lpProtocolInfo
0x18000293b  lea     r9, [rbp+5D0h+Address]; lpAddress
0x18000293f  call    cs:__imp_WSAStringToAddressW
0x180002946  nop     dword ptr [rax+rax+00h]
0x18000294b  cmp     eax, 0FFFFFFFFh
0x18000294e  jnz     short loc_18000295C
0x180002950  lea     rsi, [rbp+5D0h+pszDest]
0x180002957  jmp     loc_180002A3D
0x18000295c  lea     rbx, ds:6[r14*2]
0x180002964  call    cs:__imp_GetProcessHeap
0x18000296b  nop     dword ptr [rax+rax+00h]
0x180002970  mov     r8, rbx; dwBytes
0x180002973  xor     edx, edx; dwFlags
0x180002975  mov     rcx, rax; hHeap
0x180002978  call    cs:__imp_HeapAlloc
0x18000297f  nop     dword ptr [rax+rax+00h]
0x180002984  xor     ebx, ebx
0x180002986  mov     rsi, rax
0x180002989  test    rax, rax
0x18000298c  jnz     short loc_1800029D2
0x18000298e  call    cs:__imp_GetLastError
0x180002995  nop     dword ptr [rax+rax+00h]
0x18000299a  mov     edi, eax
0x18000299c  mov     rax, cs:WPP_GLOBAL_Control
0x1800029a3  lea     rcx, WPP_GLOBAL_Control
0x1800029aa  cmp     rax, rcx
0x1800029ad  jz      loc_180002DC9
0x1800029b3  test    byte ptr [rax+1Ch], 40h
0x1800029b7  jz      loc_180002DC9
0x1800029bd  cmp     byte ptr [rax+19h], 1
0x1800029c1  jb      loc_180002DC9
0x1800029c7  lea     edx, [rsi+10h]
0x1800029ca  mov     r9d, edi
0x1800029cd  jmp     loc_18000290F
0x1800029d2  lea     rax, [r14+1]
0x1800029d6  test    rax, rax
0x1800029d9  jz      short loc_180002A27
0x1800029db  lea     rdx, [rsi+2]
0x1800029df  cmp     rax, r15
0x1800029e2  jbe     short loc_1800029E9
0x1800029e4  mov     [rdx], bx
0x1800029e7  jmp     short loc_180002A27
0x1800029e9  mov     ecx, 7FFFFFFEh
0x1800029ee  lea     r8, [rbp+5D0h+pszDest]
0x1800029f5  test    rcx, rcx
0x1800029f8  jz      short loc_180002A19
0x1800029fa  movzx   r9d, word ptr [r8]
0x1800029fe  test    r9w, r9w
0x180002a02  jz      short loc_180002A19
0x180002a04  mov     [rdx], r9w
0x180002a08  add     r8, 2
0x180002a0c  add     rdx, 2
0x180002a10  dec     rcx
0x180002a13  sub     rax, 1
0x180002a17  jnz     short loc_1800029F5
0x180002a19  test    rax, rax
0x180002a1c  lea     rcx, [rdx-2]
0x180002a20  cmovnz  rcx, rdx
0x180002a24  mov     [rcx], bx
0x180002a27  mov     word ptr [rsi], 5Bh ; '['
0x180002a2c  mov     word ptr [rsi+r14*2+2], 5Dh ; ']'
0x180002a34  add     r14, 2
0x180002a38  mov     [rsi+r14*2], bx
0x180002a3d  mov     eax, r12d
0x180002a40  mov     [rsp+6D0h+var_690], 68h ; 'h'
0x180002a48  neg     eax
0x180002a4a  mov     [rsp+6D0h+var_678], rsi
0x180002a4f  mov     [rsp+6D0h+var_670], r14d
0x180002a54  mov     eax, 1BBh
0x180002a59  sbb     ecx, ecx
0x180002a5b  neg     ecx
0x180002a5d  inc     ecx
0x180002a5f  mov     [rsp+6D0h+var_67C], ecx
0x180002a63  test    r12d, r12d
0x180002a66  jnz     short loc_180002A6D
0x180002a68  mov     eax, 50h ; 'P'
0x180002a6d  mov     [rsp+6D0h+var_66C], ax
0x180002a72  mov     rcx, r15
0x180002a75  lea     rax, [rbp+5D0h+var_250]
0x180002a7c  mov     [rbp+5D0h+var_648], rax
0x180002a80  lea     rax, [rbp+5D0h+var_250]
0x180002a87  cmp     [rax], bx
0x180002a8a  jz      short loc_180002A96
0x180002a8c  add     rax, 2
0x180002a90  sub     rcx, 1
0x180002a94  jnz     short loc_180002A87
0x180002a96  sub     r15, rcx
0x180002a99  mov     rax, rcx
0x180002a9c  neg     rax
0x180002a9f  sbb     rdx, rdx
0x180002aa2  and     rdx, r15
0x180002aa5  test    rcx, rcx
0x180002aa8  jnz     short loc_180002AE5
0x180002aaa  lea     r9d, [rcx+57h]
0x180002aae  mov     edi, r9d
0x180002ab1  mov     rax, cs:WPP_GLOBAL_Control
0x180002ab8  lea     rcx, WPP_GLOBAL_Control
0x180002abf  cmp     rax, rcx
0x180002ac2  jz      loc_180002D64
0x180002ac8  test    byte ptr [rax+1Ch], 40h
0x180002acc  jz      loc_180002D64
0x180002ad2  cmp     byte ptr [rax+19h], 1
0x180002ad6  jb      loc_180002D64
0x180002adc  lea     edx, [r9-46h]
0x180002ae0  jmp     loc_180002D5B
0x180002ae5  mov     eax, 0FFFFFFFFh
0x180002aea  cmp     rdx, rax
0x180002aed  ja      loc_180002D2C
0x180002af3  mov     [rbp+5D0h+var_640], edx
0x180002af6  lea     rcx, LibFileName; "winhttp.dll"
0x180002afd  xor     edx, edx; hFile
0x180002aff  xor     r8d, r8d; dwFlags
0x180002b02  call    cs:__imp_LoadLibraryExW
0x180002b09  nop     dword ptr [rax+rax+00h]
0x180002b0e  mov     r15, rax
0x180002b11  test    rax, rax
0x180002b14  jnz     short loc_180002B5B
0x180002b16  call    cs:__imp_GetLastError
0x180002b1d  nop     dword ptr [rax+rax+00h]
0x180002b22  mov     edi, eax
0x180002b24  mov     rax, cs:WPP_GLOBAL_Control
0x180002b2b  lea     rcx, WPP_GLOBAL_Control
0x180002b32  cmp     rax, rcx
0x180002b35  jz      loc_180002D64
0x180002b3b  test    byte ptr [rax+1Ch], 40h
0x180002b3f  jz      loc_180002D64
0x180002b45  cmp     byte ptr [rax+19h], 1
0x180002b49  jb      loc_180002D64
0x180002b4f  lea     edx, [r15+13h]
0x180002b53  mov     r9d, edi
0x180002b56  jmp     loc_180002D5B
0x180002b5b  lea     rdx, ProcName; "WinHttpCreateUrl"
0x180002b62  mov     rcx, r15; hModule
0x180002b65  call    cs:__imp_GetProcAddress
0x180002b6c  nop     dword ptr [rax+rax+00h]
0x180002b71  mov     r14, rax
0x180002b74  test    rax, rax
  ... truncated ...
```
