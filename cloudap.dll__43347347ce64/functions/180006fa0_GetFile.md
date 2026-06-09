# GetFile

- ea: `0x180006fa0`
- end: `0x180007680`
- name: `GetFile`
- size: `1760`
- prototype: `__int64 __fastcall(__int64, __int64, WCHAR *, WCHAR *, char, void *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002bb40`
- `0x180031f6c`

## callees

- `0x180006fa0`
- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000753f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000763b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000753f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000763b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000719b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180007255`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000719b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180007255`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007173`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800073e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007173`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800073e5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007388`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007388`

## string_xrefs

- `0x18000709c`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180007179`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000738e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800073f7`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180007444`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000748a`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800074be`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800074f2`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000755f`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800075b4`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180007573`: `CreateDirectoryW`
- `0x1800075c8`: `CreateDirectoryW`
- `0x18000760a`: `SetFileAttributesW`
- `0x180007667`: `CreateFileW`

## pseudocode

```c
__int64 __fastcall GetFile(__int64 a1, __int64 a2, WCHAR *a3, WCHAR *a4, char a5, void *a6, _QWORD *a7)
{
  __int64 v7; // r10
  WCHAR *v8; // r14
  WCHAR *v9; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // r15d
  unsigned __int16 *v16; // rax
  const WCHAR *v17; // r12
  unsigned int v18; // edi
  const UCHAR *v19; // r9
  char v20; // al
  const UCHAR *v21; // rcx
  bool v22; // zf
  HANDLE FileW; // rax
  __int64 v25; // rcx
  const WCHAR *v26; // rax
  __int64 v27; // rax
  WCHAR *v28; // r8
  __int64 v29; // rsi
  __int64 v30; // rcx
  __int64 v31; // rdx
  WCHAR *v32; // rax
  __int64 v33; // rcx
  const WCHAR *v34; // rax
  __int64 v35; // rax
  const unsigned __int16 *v36; // rdx
  WCHAR *v37; // r9
  __int64 v38; // rcx
  __int64 v39; // r8
  WCHAR *v40; // rax
  __int64 v41; // rcx
  const WCHAR *v42; // rax
  __int64 v43; // rax
  WCHAR *v44; // rcx
  __int64 i; // rbp
  WCHAR *v46; // rax
  HLOCAL v47; // rcx
  const UCHAR *v48; // r9
  char v49; // al
  const UCHAR *v50; // rcx
  bool v51; // zf
  const UCHAR *v52; // r9
  char v53; // al
  const UCHAR *v54; // rcx
  bool v55; // zf
  const char *v56; // r9
  const char *v57; // r9
  const char *v58; // rax
  signed int LastError; // eax
  const char *v60; // r9
  signed int v61; // eax
  const char *v62; // r9
  const char *v63; // rax
  __int64 v64; // r8
  signed int v65; // eax
  const char *v66; // r9
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-68h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-68h]
  DWORD dwCreationDispositionb[2]; // [rsp+20h] [rbp-68h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-48h] BYREF

  v7 = -1;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  v8 = a4;
  v9 = a3;
  *a7 = -1;
  *(_OWORD *)&SecurityAttributes.nLength = 0;
  v12 = -1;
  do
    v22 = a4[++v12] == 0;
  while ( !v22 );
  v13 = -1;
  do
    v22 = a3[++v13] == 0;
  while ( !v22 );
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a2 + 2 * v14) );
  do
    ++v7;
  while ( *(_WORD *)(a1 + 2 * v7) );
  v15 = v7 + 4 + v14 + v12 + v13;
  v16 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(2 * v15);
  v17 = v16;
  if ( v16 )
  {
    if ( !a5 )
    {
      v18 = RtlStringCchPrintfW(v16, v15, L"%ws\\%ws\\", a1, a2);
      if ( v18 )
      {
        v19 = "";
        while ( 1 )
        {
          v20 = *(v19 - 1);
          v21 = v19--;
          v22 = v20 == 92;
          if ( v20 == 92 )
            break;
          if ( v19 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
          {
            v22 = v20 == 92;
            break;
          }
        }
        if ( v22 )
          v19 = v21;
        dwCreationDisposition[0] = 1951;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          v18,
          v19,
          *(_QWORD *)dwCreationDisposition,
          "RtlStringCchPrintfW",
          &Class);
        goto LABEL_18;
      }
      if ( !CreateDirectoryW(v17, 0) )
      {
        LastError = GetLastError();
        v18 = LastError;
        if ( LastError != 183 )
        {
          if ( LastError > 0 )
            v18 = (unsigned __int16)LastError | 0xC0070000;
          v60 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          dwCreationDisposition[0] = 1961;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v60, *(_QWORD *)dwCreationDisposition, "CreateDirectoryW", v17);
          goto LABEL_18;
        }
      }
      if ( v15 && v15 <= 0x7FFFFFFFuLL )
      {
        v25 = v15;
        v26 = v17;
        do
        {
          if ( !*v26 )
            break;
          ++v26;
          --v25;
        }
        while ( v25 );
        v18 = -1073741811;
        if ( v25 )
        {
          v18 = 0;
          v27 = v15 - v25;
        }
        else
        {
          v27 = 0;
        }
        if ( v25 )
        {
          v28 = (WCHAR *)&v17[v27];
          v29 = 2147483646;
          v30 = 2147483646;
          v31 = v15 - v27;
          if ( v15 != v27 )
          {
            do
            {
              if ( !v30 )
                break;
              if ( !*v9 )
                break;
              *v28++ = *v9++;
              --v30;
              --v31;
            }
            while ( v31 );
          }
          v32 = v28 - 1;
          v18 = -2147483643;
          if ( v31 )
          {
            v32 = v28;
            v18 = 0;
          }
          *v32 = 0;
          if ( v31 )
          {
            if ( !CreateDirectoryW(v17, 0) )
            {
              v61 = GetLastError();
              v18 = v61;
              if ( v61 != 183 )
              {
                if ( v61 > 0 )
                  v18 = (unsigned __int16)v61 | 0xC0070000;
                v62 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                dwCreationDisposition[0] = 1979;
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  v18,
                  v62,
                  *(_QWORD *)dwCreationDisposition,
                  "CreateDirectoryW",
                  v17);
                goto LABEL_18;
              }
            }
            v33 = v15;
            v34 = v17;
            do
            {
              if ( !*v34 )
                break;
              ++v34;
              --v33;
            }
            while ( v33 );
            v18 = -1073741811;
            if ( v33 )
            {
              v18 = 0;
              v35 = v15 - v33;
            }
            else
            {
              v35 = 0;
            }
            if ( !v33 )
              goto LABEL_85;
            v36 = L"\\";
            v37 = (WCHAR *)&v17[v35];
            v38 = 2147483646;
            v39 = v15 - v35;
            if ( v15 != v35 )
            {
              do
              {
                if ( !v38 )
                  break;
                if ( !*v36 )
                  break;
                *v37++ = *v36++;
                --v38;
                --v39;
              }
              while ( v39 );
            }
            v40 = v37 - 1;
            v18 = -2147483643;
            if ( v39 )
            {
              v40 = v37;
              v18 = 0;
            }
            *v40 = 0;
            if ( v39 )
            {
              v41 = v15;
              v42 = v17;
              do
              {
                if ( !*v42 )
                  break;
                ++v42;
                --v41;
              }
              while ( v41 );
              v18 = -1073741811;
              if ( v41 )
              {
                v18 = 0;
                v43 = v15 - v41;
              }
              else
              {
                v43 = 0;
              }
              if ( v41 )
              {
                v44 = (WCHAR *)&v17[v43];
                for ( i = v15 - v43; i; --i )
                {
                  if ( !v29 )
                    break;
                  if ( !*v8 )
                    break;
                  *v44++ = *v8++;
                  --v29;
                }
                v46 = v44 - 1;
                v18 = -2147483643;
                if ( i )
                {
                  v46 = v44;
                  v18 = 0;
                }
                *v46 = 0;
                if ( i )
                {
                  if ( !SetFileAttributesW(v17, 0x80u) )
                  {
                    GetLastError();
                    v63 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                    dwCreationDisposition[0] = 2031;
                    WPPTraceLogA(
                      0,
                      "0x%08x %s:%u : %s:%ws",
                      v64,
                      v63,
                      *(_QWORD *)dwCreationDisposition,
                      "SetFileAttributesW",
                      v17);
                  }
                  v47 = g_pSystemSD;
                  if ( a6 )
                    v47 = a6;
                  SecurityAttributes.lpSecurityDescriptor = v47;
                  SecurityAttributes.nLength = 24;
                  FileW = CreateFileW(v17, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80000007, 0);
LABEL_21:
                  *a7 = FileW;
                  if ( FileW == (HANDLE)-1LL )
                  {
                    v65 = GetLastError();
                    v18 = v65;
                    if ( v65 > 0 )
                      v18 = (unsigned __int16)v65 | 0xC0070000;
                    v66 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                    dwCreationDispositionb[0] = 2061;
                    WPPTraceLogA(
                      0,
                      "0x%08x %s:%u : %s:%ws",
                      v18,
                      v66,
                      *(_QWORD *)dwCreationDispositionb,
                      "CreateFileW",
                      &Class);
                  }
                  else
                  {
                    v18 = 0;
                  }
                  goto LABEL_18;
                }
              }
              v57 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              dwCreationDisposition[0] = 1993;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                v18,
                v57,
                *(_QWORD *)dwCreationDisposition,
                "RtlStringCchCatW",
                &Class);
            }
            else
            {
LABEL_85:
              v56 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              dwCreationDisposition[0] = 1987;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                v18,
                v56,
                *(_QWORD *)dwCreationDisposition,
                "RtlStringCchCatW",
                &Class);
            }
LABEL_18:
            ((void (__fastcall *)(const WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v17);
            return v18;
          }
        }
      }
      else
      {
        v18 = -1073741811;
      }
      v52 = "";
      while ( 1 )
      {
        v53 = *(v52 - 1);
        v54 = v52--;
        v55 = v53 == 92;
        if ( v53 == 92 )
          break;
        if ( v52 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
        {
          v55 = v53 == 92;
          break;
        }
      }
      if ( v55 )
        v52 = v54;
      dwCreationDisposition[0] = 1969;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v52, *(_QWORD *)dwCreationDisposition, "RtlStringCchCatW", &Class);
      goto LABEL_18;
    }
    v18 = RtlStringCchPrintfW(v16, v15, L"%ws\\%ws\\%ws\\%ws", a1, a2, v9, v8);
    if ( v18 )
    {
      v48 = "";
      while ( 1 )
      {
        v49 = *(v48 - 1);
        v50 = v48--;
        v51 = v49 == 92;
        if ( v49 == 92 )
          break;
        if ( v48 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
        {
          v51 = v49 == 92;
          break;
        }
      }
      if ( v51 )
        v48 = v50;
      dwCreationDispositiona[0] = 2006;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        v18,
        v48,
        *(_QWORD *)dwCreationDispositiona,
        "RtlStringCchPrintfW",
        &Class);
      goto LABEL_18;
    }
    FileW = CreateFileW(v17, 0x80000000, 1u, 0, 3u, 7u, 0);
    goto LABEL_21;
  }
  v58 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v58, 1939, "AllocateLsaHeap", &Class);
  return 3221225495LL;
}

```

## disassembly

```asm
0x180006fa0  mov     [rsp+arg_8], rbx
0x180006fa5  mov     [rsp+arg_10], rsi
0x180006faa  push    rdi
0x180006fab  push    r12
0x180006fad  push    r13
0x180006faf  push    r14
0x180006fb1  push    r15
0x180006fb3  sub     rsp, 60h
0x180006fb7  mov     r13, [rsp+88h+arg_30]
0x180006fbf  xor     eax, eax
0x180006fc1  mov     r10, 0FFFFFFFFFFFFFFFFh
0x180006fc8  mov     qword ptr [rsp+88h+SecurityAttributes.bInheritHandle], rax
0x180006fcd  xorps   xmm0, xmm0
0x180006fd0  mov     r14, r9
0x180006fd3  mov     rbx, r8
0x180006fd6  mov     rdi, rdx
0x180006fd9  mov     [r13+0], r10
0x180006fdd  mov     rsi, rcx
0x180006fe0  movups  xmmword ptr [rsp+88h+SecurityAttributes.nLength], xmm0
0x180006fe5  mov     rax, r10
0x180006fe8  nop     dword ptr [rax+rax+00000000h]
0x180006ff0  cmp     word ptr [r9+rax*2+2], 0
0x180006ff7  lea     rax, [rax+1]
0x180006ffb  jnz     short loc_180006FF0
0x180006ffd  mov     rcx, r10
0x180007000  cmp     word ptr [r8+rcx*2+2], 0
0x180007007  lea     rcx, [rcx+1]
0x18000700b  jnz     short loc_180007000
0x18000700d  mov     rdx, r10
0x180007010  inc     rdx
0x180007013  cmp     word ptr [rdi+rdx*2], 0
0x180007018  jnz     short loc_180007010
0x18000701a  nop     word ptr [rax+rax+00h]
0x180007020  inc     r10
0x180007023  cmp     word ptr [rsi+r10*2], 0
0x180007029  jnz     short loc_180007020
0x18000702b  lea     r15d, [rax+rcx]
0x18000702f  add     r10d, 4
0x180007033  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000703a  add     r15d, edx
0x18000703d  add     r15d, r10d
0x180007040  mov     rax, [rax+28h]
0x180007044  lea     ecx, [r15+r15]
0x180007048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000704d  mov     r12, rax
0x180007050  test    rax, rax
0x180007053  jz      loc_1800074F2
0x180007059  cmp     [rsp+88h+arg_20], 0
0x180007061  mov     r9, rsi
0x180007064  mov     [rsp+88h+arg_0], rbp
0x18000706c  mov     rcx, rax; unsigned __int16 *
0x18000706f  mov     ebp, r15d
0x180007072  mov     edx, ebp; unsigned __int64
0x180007074  jnz     loc_180007125
0x18000707a  lea     r8, aWsWs_0; "%ws\\%ws\\"
0x180007081  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi
0x180007086  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000708b  mov     edi, eax
0x18000708d  test    eax, eax
0x18000708f  jz      loc_180007196
0x180007095  lea     r9, pbInput+24h; ""
0x18000709c  lea     rbx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x1800070a3  movzx   eax, byte ptr [r9-1]
0x1800070a8  mov     rcx, r9
0x1800070ab  dec     r9
0x1800070ae  cmp     al, 5Ch ; '\'
0x1800070b0  jz      short loc_1800070B9
0x1800070b2  cmp     r9, rbx
0x1800070b5  ja      short loc_1800070A3
0x1800070b7  cmp     al, 5Ch ; '\'
0x1800070b9  cmovz   r9, rcx
0x1800070bd  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x1800070c4  lea     rcx, Class
0x1800070cb  mov     [rsp+88h+hTemplateFile], rcx
0x1800070d0  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax
0x1800070d5  mov     [rsp+88h+dwCreationDisposition], 79Fh
0x1800070dd  mov     r8d, edi
0x1800070e0  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800070e7  xor     ecx, ecx
0x1800070e9  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800070ee  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800070f5  mov     rcx, r12
0x1800070f8  mov     rax, [rax+30h]
0x1800070fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007101  mov     rbp, [rsp+88h+arg_0]
0x180007109  mov     eax, edi
0x18000710b  lea     r11, [rsp+88h+var_28]
0x180007110  mov     rbx, [r11+38h]
0x180007114  mov     rsi, [r11+40h]
0x180007118  mov     rsp, r11
0x18000711b  pop     r15
0x18000711d  pop     r14
0x18000711f  pop     r13
0x180007121  pop     r12
0x180007123  pop     rdi
0x180007124  retn
0x180007125  mov     [rsp+88h+hTemplateFile], r14
0x18000712a  lea     r8, aWsWsWsWs; "%ws\\%ws\\%ws\\%ws"
0x180007131  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbx
0x180007136  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi
0x18000713b  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007140  mov     edi, eax
0x180007142  test    eax, eax
0x180007144  jnz     loc_1800073F0
0x18000714a  xor     r15d, r15d
0x18000714d  xor     r9d, r9d; lpSecurityAttributes
0x180007150  mov     [rsp+88h+hTemplateFile], r15; hTemplateFile
0x180007155  mov     edx, 80000000h; dwDesiredAccess
0x18000715a  mov     [rsp+88h+dwFlagsAndAttributes], 7; dwFlagsAndAttributes
0x180007162  mov     r8d, 1; dwShareMode
0x180007168  mov     rcx, r12; lpFileName
0x18000716b  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180007173  call    cs:__imp_CreateFileW
0x180007179  lea     rbx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180007180  mov     [r13+0], rax
0x180007184  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007188  jz      loc_18000763B
0x18000718e  mov     edi, r15d
0x180007191  jmp     loc_1800070EE
0x180007196  xor     edx, edx; lpSecurityAttributes
0x180007198  mov     rcx, r12; lpPathName
0x18000719b  call    cs:__imp_CreateDirectoryW
0x1800071a1  test    eax, eax
0x1800071a3  jz      loc_18000753F
0x1800071a9  test    r15d, r15d
0x1800071ac  jz      loc_180007631
0x1800071b2  cmp     rbp, 7FFFFFFFh
0x1800071b9  ja      loc_180007631
0x1800071bf  mov     rcx, rbp
0x1800071c2  mov     rax, r12
0x1800071c5  cmp     word ptr [rax], 0
0x1800071c9  jz      short loc_1800071D5
0x1800071cb  add     rax, 2
0x1800071cf  sub     rcx, 1
0x1800071d3  jnz     short loc_1800071C5
0x1800071d5  xor     r15d, r15d
0x1800071d8  mov     edi, 0C000000Dh
0x1800071dd  test    rcx, rcx
0x1800071e0  cmovnz  edi, r15d
0x1800071e4  jz      loc_18000758C
0x1800071ea  mov     rax, rbp
0x1800071ed  sub     rax, rcx
0x1800071f0  test    rcx, rcx
0x1800071f3  jz      loc_18000743D
0x1800071f9  mov     rdx, rbp
0x1800071fc  lea     r8, [r12+rax*2]
0x180007200  mov     esi, 7FFFFFFEh
0x180007205  mov     ecx, esi
0x180007207  sub     rdx, rax
0x18000720a  jz      short loc_180007232
0x18000720c  nop     dword ptr [rax+00h]
0x180007210  test    rcx, rcx
0x180007213  jz      short loc_180007232
0x180007215  movzx   eax, word ptr [rbx]
0x180007218  test    ax, ax
0x18000721b  jz      short loc_180007232
0x18000721d  mov     [r8], ax
0x180007221  add     rbx, 2
0x180007225  add     r8, 2
0x180007229  dec     rcx
0x18000722c  sub     rdx, 1
0x180007230  jnz     short loc_180007210
0x180007232  test    rdx, rdx
0x180007235  lea     rax, [r8-2]
0x180007239  mov     edi, 80000005h
0x18000723e  cmovnz  rax, r8
0x180007242  cmovnz  edi, r15d
0x180007246  mov     [rax], r15w
0x18000724a  jz      loc_18000743D
0x180007250  xor     edx, edx; lpSecurityAttributes
0x180007252  mov     rcx, r12; lpPathName
0x180007255  call    cs:__imp_CreateDirectoryW
0x18000725b  test    eax, eax
0x18000725d  jz      loc_180007594
0x180007263  mov     rcx, rbp
0x180007266  mov     rax, r12
0x180007269  nop     dword ptr [rax+00000000h]
0x180007270  cmp     [rax], r15w
0x180007274  jz      short loc_180007280
0x180007276  add     rax, 2
0x18000727a  sub     rcx, 1
0x18000727e  jnz     short loc_180007270
0x180007280  test    rcx, rcx
0x180007283  mov     edi, 0C000000Dh
0x180007288  cmovnz  edi, r15d
0x18000728c  jz      loc_1800075E1
0x180007292  mov     rax, rbp
0x180007295  sub     rax, rcx
0x180007298  test    rcx, rcx
0x18000729b  jz      loc_18000748A
0x1800072a1  mov     r8, rbp
0x1800072a4  lea     rdx, asc_180085528; "\\"
0x1800072ab  lea     r9, [r12+rax*2]
0x1800072af  mov     rcx, rsi
0x1800072b2  sub     r8, rax
0x1800072b5  jz      short loc_1800072D9
0x1800072b7  test    rcx, rcx
0x1800072ba  jz      short loc_1800072D9
0x1800072bc  movzx   eax, word ptr [rdx]
0x1800072bf  test    ax, ax
0x1800072c2  jz      short loc_1800072D9
0x1800072c4  mov     [r9], ax
0x1800072c8  add     rdx, 2
0x1800072cc  add     r9, 2
0x1800072d0  dec     rcx
0x1800072d3  sub     r8, 1
0x1800072d7  jnz     short loc_1800072B7
0x1800072d9  test    r8, r8
0x1800072dc  lea     rax, [r9-2]
0x1800072e0  mov     edi, 80000005h
0x1800072e5  cmovnz  rax, r9
0x1800072e9  cmovnz  edi, r15d
0x1800072ed  mov     [rax], r15w
0x1800072f1  jz      loc_18000748A
0x1800072f7  mov     rcx, rbp
0x1800072fa  mov     rax, r12
0x1800072fd  nop     dword ptr [rax]
0x180007300  cmp     [rax], r15w
0x180007304  jz      short loc_180007310
0x180007306  add     rax, 2
0x18000730a  sub     rcx, 1
0x18000730e  jnz     short loc_180007300
0x180007310  test    rcx, rcx
0x180007313  mov     edi, 0C000000Dh
0x180007318  cmovnz  edi, r15d
0x18000731c  jz      loc_1800075E9
0x180007322  mov     rax, rbp
0x180007325  sub     rax, rcx
0x180007328  test    rcx, rcx
0x18000732b  jz      loc_1800074BE
0x180007331  lea     rcx, [r12+rax*2]
0x180007335  sub     rbp, rax
0x180007338  jz      short loc_180007362
0x18000733a  nop     word ptr [rax+rax+00h]
0x180007340  test    rsi, rsi
0x180007343  jz      short loc_180007362
0x180007345  movzx   eax, word ptr [r14]
0x180007349  test    ax, ax
0x18000734c  jz      short loc_180007362
0x18000734e  mov     [rcx], ax
0x180007351  add     r14, 2
0x180007355  add     rcx, 2
0x180007359  dec     rsi
0x18000735c  sub     rbp, 1
0x180007360  jnz     short loc_180007340
0x180007362  test    rbp, rbp
0x180007365  lea     rax, [rcx-2]
0x180007369  mov     edi, 80000005h
0x18000736e  cmovnz  rax, rcx
0x180007372  cmovnz  edi, r15d
0x180007376  mov     [rax], r15w
0x18000737a  jz      loc_1800074BE
0x180007380  mov     edx, 80h; dwFileAttributes
0x180007385  mov     rcx, r12; lpFileName
0x180007388  call    cs:__imp_SetFileAttributesW
0x18000738e  lea     rbx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180007395  test    eax, eax
0x180007397  jz      loc_1800075F1
0x18000739d  mov     rax, [rsp+88h+arg_28]
0x1800073a5  lea     r9, [rsp+88h+SecurityAttributes]; lpSecurityAttributes
0x1800073aa  mov     rcx, cs:?g_pSystemSD@@3PEAXEA; void * g_pSystemSD
0x1800073b1  test    rax, rax
0x1800073b4  mov     [rsp+88h+hTemplateFile], r15; hTemplateFile
0x1800073b9  mov     edx, 40000000h; dwDesiredAccess
0x1800073be  cmovnz  rcx, rax
0x1800073c2  mov     [rsp+88h+dwFlagsAndAttributes], 80000007h; dwFlagsAndAttributes
0x1800073ca  mov     [rsp+88h+SecurityAttributes.lpSecurityDescriptor], rcx
0x1800073cf  xor     r8d, r8d; dwShareMode
0x1800073d2  mov     rcx, r12; lpFileName
0x1800073d5  mov     [rsp+88h+SecurityAttributes.nLength], 18h
0x1800073dd  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x1800073e5  call    cs:__imp_CreateFileW
0x1800073eb  jmp     loc_180007180
0x1800073f0  lea     r9, pbInput+24h; ""
0x1800073f7  lea     rbx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x1800073fe  movzx   eax, byte ptr [r9-1]
0x180007403  mov     rcx, r9
0x180007406  dec     r9
0x180007409  cmp     al, 5Ch ; '\'
0x18000740b  jz      short loc_180007414
0x18000740d  cmp     r9, rbx
0x180007410  ja      short loc_1800073FE
0x180007412  cmp     al, 5Ch ; '\'
0x180007414  cmovz   r9, rcx
0x180007418  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18000741f  lea     rcx, Class
0x180007426  mov     [rsp+88h+hTemplateFile], rcx
0x18000742b  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax
0x180007430  mov     [rsp+88h+dwCreationDisposition], 7D6h
0x180007438  jmp     loc_1800070DD
0x18000743d  lea     r9, pbInput+24h; ""
0x180007444  lea     rbx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000744b  movzx   eax, byte ptr [r9-1]
0x180007450  mov     rcx, r9
0x180007453  dec     r9
0x180007456  cmp     al, 5Ch ; '\'
0x180007458  jz      short loc_180007461
0x18000745a  cmp     r9, rbx
0x18000745d  ja      short loc_18000744B
0x18000745f  cmp     al, 5Ch ; '\'
  ... truncated ...
```
