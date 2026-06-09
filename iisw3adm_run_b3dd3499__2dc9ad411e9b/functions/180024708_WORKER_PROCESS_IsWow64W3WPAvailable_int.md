# WORKER_PROCESS::IsWow64W3WPAvailable(int *)

- ea: `0x180024708`
- end: `0x1800249ae`
- name: `?IsWow64W3WPAvailable@WORKER_PROCESS@@SAJPEAH@Z`
- size: `678`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800184ac`
- `0x180019e7c`

## callees

- `0x180024708`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002478d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002494e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002478d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002494e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180024939`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180024939`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18002477f`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18002477f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024989`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024989`
- `iisutil!PuDbgPrint` at `0x1800247e2`
- `iisutil!PuDbgPrint` at `0x1800247e2`
- `iisutil!PuDbgPrintError` at `0x18002483a`
- `iisutil!PuDbgPrintError` at `0x18002483a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180024884`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800248c4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180024904`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180024884`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800248c4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180024904`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002474e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002474e`

## string_xrefs

- `0x1800247db`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180024833`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x18002480f`: `Failed to get Syswow64 path\n`
- `0x18002485b`: `Failed to get Syswow64 path - returned string too long\n`
- `0x18002489d`: `Copying to string failed\n`
- `0x1800248dd`: `Copying to string failed\n`
- `0x180024919`: `Copying to string failed\n`

## pseudocode

```c
__int64 __fastcall WORKER_PROCESS::IsWow64W3WPAvailable(int *a1)
{
  int v2; // edi
  unsigned int v3; // ebx
  int v4; // esi
  UINT SystemWow64DirectoryW; // eax
  signed int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-498h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-478h]
  unsigned __int16 v15[264]; // [rsp+70h] [rbp-458h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp-248h] BYREF

  memset_0(v15, 0, 0x20Au);
  STRU::STRU((STRU *)v13, v15, 0x105u);
  v2 = 0;
  if ( WORKER_PROCESS::sm_IsWow64W3WPAvailable == -1 )
  {
    v4 = 0;
    SystemWow64DirectoryW = GetSystemWow64DirectoryW(Buffer, 0x105u);
    if ( SystemWow64DirectoryW )
    {
      if ( SystemWow64DirectoryW <= 0x105 )
      {
        v7 = STRU::Append((STRU *)v13, Buffer);
        v3 = v7;
        if ( v7 >= 0 )
        {
          v8 = STRU::Append((STRU *)v13, L"\\inetsrv\\");
          v3 = v8;
          if ( v8 >= 0 )
          {
            v9 = STRU::Append((STRU *)v13, L"w3wp.exe");
            v3 = v9;
            if ( v9 >= 0 )
            {
              FileAttributesW = GetFileAttributesW(lpFileName);
              if ( FileAttributesW == -1 )
              {
                if ( GetLastError() )
                {
                  LastError = GetLastError();
                  v3 = LastError;
                  if ( LastError > 0 )
                    v3 = (unsigned __int16)LastError | 0x80070000;
                }
                else
                {
                  v3 = -2147467259;
                }
              }
              else if ( (FileAttributesW & 0x10) == 0 )
              {
                v4 = 1;
                WORKER_PROCESS::sm_IsWow64W3WPAvailable = 1;
                goto LABEL_32;
              }
              WORKER_PROCESS::sm_IsWow64W3WPAvailable = 0;
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
                8518,
                "WORKER_PROCESS::IsWow64W3WPAvailable",
                v9,
                "Copying to string failed\n");
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
              8501,
              "WORKER_PROCESS::IsWow64W3WPAvailable",
              v8,
              "Copying to string failed\n");
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
            8485,
            "WORKER_PROCESS::IsWow64W3WPAvailable",
            v7,
            "Copying to string failed\n");
        }
      }
      else
      {
        v3 = -2147024785;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
            8467,
            "WORKER_PROCESS::IsWow64W3WPAvailable",
            -2147024785,
            "Failed to get Syswow64 path - returned string too long\n");
      }
    }
    else
    {
      GetLastError();
      if ( GetLastError() == 120 )
      {
        v3 = 0;
        if ( (g_dwDebugFlags & 0x410000) != 0 && (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
            8443,
            "WORKER_PROCESS::IsWow64W3WPAvailable",
            "Enable32bitAppOnWin64 setting will be ignored because Wow64 support was not detected");
      }
      else
      {
        v6 = GetLastError();
        v3 = v6;
        if ( v6 > 0 )
          v3 = (unsigned __int16)v6 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
            8455,
            "WORKER_PROCESS::IsWow64W3WPAvailable",
            v3,
            "Failed to get Syswow64 path\n");
      }
    }
  }
  else
  {
    v3 = 0;
    LOBYTE(v2) = WORKER_PROCESS::sm_IsWow64W3WPAvailable == 1;
    v4 = v2;
  }
LABEL_32:
  *a1 = v4;
  STRU::~STRU((STRU *)v13);
  return v3;
}

```

## disassembly

```asm
0x180024708  push    rbx
0x18002470a  push    rsi
0x18002470b  push    rdi
0x18002470c  push    r14
0x18002470e  sub     rsp, 4A8h
0x180024715  mov     rax, cs:__security_cookie
0x18002471c  xor     rax, rsp
0x18002471f  mov     [rsp+4C8h+var_38], rax
0x180024727  mov     r14, rcx
0x18002472a  xor     edx, edx; Val
0x18002472c  lea     rcx, [rsp+4C8h+var_458]; void *
0x180024731  mov     r8d, 20Ah; Size
0x180024737  call    memset_0
0x18002473c  mov     ebx, 105h
0x180024741  lea     rdx, [rsp+4C8h+var_458]
0x180024746  mov     r8d, ebx
0x180024749  lea     rcx, [rsp+4C8h+var_498]
0x18002474e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180024754  mov     eax, cs:?sm_IsWow64W3WPAvailable@WORKER_PROCESS@@0KA; ulong WORKER_PROCESS::sm_IsWow64W3WPAvailable
0x18002475a  xor     edi, edi
0x18002475c  cmp     eax, 0FFFFFFFFh
0x18002475f  jz      short loc_180024773
0x180024761  lea     esi, [rdi+1]
0x180024764  mov     ebx, edi
0x180024766  cmp     eax, esi
0x180024768  setz    dil
0x18002476c  mov     esi, edi
0x18002476e  jmp     loc_180024981
0x180024773  mov     edx, ebx; uSize
0x180024775  lea     rcx, [rsp+4C8h+Buffer]; lpBuffer
0x18002477d  mov     esi, edi
0x18002477f  call    cs:__imp_GetSystemWow64DirectoryW
0x180024785  test    eax, eax
0x180024787  jnz     loc_180024845
0x18002478d  call    cs:__imp_GetLastError
0x180024793  call    cs:__imp_GetLastError
0x180024799  cmp     eax, 78h ; 'x'
0x18002479c  jnz     short loc_1800247ED
0x18002479e  mov     eax, cs:g_dwDebugFlags
0x1800247a4  mov     ebx, edi
0x1800247a6  test    eax, 410000h
0x1800247ab  setnz   cl
0x1800247ae  test    al, 3
0x1800247b0  setnz   al
0x1800247b3  test    al, cl
0x1800247b5  jz      loc_180024981
0x1800247bb  mov     rcx, cs:g_pDebug
0x1800247c2  lea     rax, aEnable32bitapp; "Enable32bitAppOnWin64 setting will be i"...
0x1800247c9  lea     r9, aWorkerProcessI_4; "WORKER_PROCESS::IsWow64W3WPAvailable"
0x1800247d0  mov     [rsp+4C8h+var_4A8], rax
0x1800247d5  mov     r8d, 20FBh
0x1800247db  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800247e2  call    cs:__imp_PuDbgPrint
0x1800247e8  jmp     loc_180024981
0x1800247ed  call    cs:__imp_GetLastError
0x1800247f3  mov     ebx, eax
0x1800247f5  test    eax, eax
0x1800247f7  jle     short loc_180024802
0x1800247f9  movzx   ebx, ax
0x1800247fc  or      ebx, 80070000h
0x180024802  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024809  jz      loc_180024981
0x18002480f  lea     rax, aFailedToGetSys; "Failed to get Syswow64 path\n"
0x180024816  mov     r8d, 2107h
0x18002481c  mov     [rsp+4C8h+var_4A0], rax
0x180024821  mov     dword ptr [rsp+4C8h+var_4A8], ebx
0x180024825  mov     rcx, cs:g_pDebug
0x18002482c  lea     r9, aWorkerProcessI_4; "WORKER_PROCESS::IsWow64W3WPAvailable"
0x180024833  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002483a  call    cs:__imp_PuDbgPrintError
0x180024840  jmp     loc_180024981
0x180024845  cmp     eax, ebx
0x180024847  jbe     short loc_180024877
0x180024849  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024850  mov     ebx, 8007006Fh
0x180024855  jz      loc_180024981
0x18002485b  lea     rax, aFailedToGetSys_0; "Failed to get Syswow64 path - returned "...
0x180024862  mov     r8d, 2113h
0x180024868  mov     [rsp+4C8h+var_4A0], rax
0x18002486d  mov     dword ptr [rsp+4C8h+var_4A8], 8007006Fh
0x180024875  jmp     short loc_180024825
0x180024877  lea     rdx, [rsp+4C8h+Buffer]
0x18002487f  lea     rcx, [rsp+4C8h+var_498]
0x180024884  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002488a  mov     ebx, eax
0x18002488c  test    eax, eax
0x18002488e  jns     short loc_1800248B8
0x180024890  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024897  jz      loc_180024981
0x18002489d  lea     rcx, aCopyingToStrin; "Copying to string failed\n"
0x1800248a4  mov     r8d, 2125h
0x1800248aa  mov     [rsp+4C8h+var_4A0], rcx
0x1800248af  mov     dword ptr [rsp+4C8h+var_4A8], eax
0x1800248b3  jmp     loc_180024825
0x1800248b8  lea     rdx, aInetsrv; "\\inetsrv\\"
0x1800248bf  lea     rcx, [rsp+4C8h+var_498]
0x1800248c4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800248ca  mov     ebx, eax
0x1800248cc  test    eax, eax
0x1800248ce  jns     short loc_1800248F8
0x1800248d0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800248d7  jz      loc_180024981
0x1800248dd  lea     rcx, aCopyingToStrin; "Copying to string failed\n"
0x1800248e4  mov     r8d, 2135h
0x1800248ea  mov     [rsp+4C8h+var_4A0], rcx
0x1800248ef  mov     dword ptr [rsp+4C8h+var_4A8], eax
0x1800248f3  jmp     loc_180024825
0x1800248f8  lea     rdx, aW3wpExe; "w3wp.exe"
0x1800248ff  lea     rcx, [rsp+4C8h+var_498]
0x180024904  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002490a  mov     ebx, eax
0x18002490c  test    eax, eax
0x18002490e  jns     short loc_180024934
0x180024910  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024917  jz      short loc_180024981
0x180024919  lea     rcx, aCopyingToStrin; "Copying to string failed\n"
0x180024920  mov     r8d, 2146h
0x180024926  mov     [rsp+4C8h+var_4A0], rcx
0x18002492b  mov     dword ptr [rsp+4C8h+var_4A8], eax
0x18002492f  jmp     loc_180024825
0x180024934  mov     rcx, [rsp+4C8h+lpFileName]; lpFileName
0x180024939  call    cs:__imp_GetFileAttributesW
0x18002493f  cmp     eax, 0FFFFFFFFh
0x180024942  jnz     short loc_180024972
0x180024944  call    cs:__imp_GetLastError
0x18002494a  test    eax, eax
0x18002494c  jz      short loc_180024965
0x18002494e  call    cs:__imp_GetLastError
0x180024954  mov     ebx, eax
0x180024956  test    eax, eax
0x180024958  jle     short loc_18002496A
0x18002495a  movzx   ebx, ax
0x18002495d  or      ebx, 80070000h
0x180024963  jmp     short loc_18002496A
0x180024965  mov     ebx, 80004005h
0x18002496a  mov     cs:?sm_IsWow64W3WPAvailable@WORKER_PROCESS@@0KA, edi; ulong WORKER_PROCESS::sm_IsWow64W3WPAvailable
0x180024970  jmp     short loc_180024981
0x180024972  test    al, 10h
0x180024974  jnz     short loc_18002496A
0x180024976  mov     esi, 1
0x18002497b  mov     cs:?sm_IsWow64W3WPAvailable@WORKER_PROCESS@@0KA, esi; ulong WORKER_PROCESS::sm_IsWow64W3WPAvailable
0x180024981  lea     rcx, [rsp+4C8h+var_498]
0x180024986  mov     [r14], esi
0x180024989  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002498f  mov     eax, ebx
0x180024991  mov     rcx, [rsp+4C8h+var_38]
0x180024999  xor     rcx, rsp; StackCookie
0x18002499c  call    __security_check_cookie
0x1800249a1  add     rsp, 4A8h
0x1800249a8  pop     r14
0x1800249aa  pop     rdi
0x1800249ab  pop     rsi
0x1800249ac  pop     rbx
0x1800249ad  retn
```
