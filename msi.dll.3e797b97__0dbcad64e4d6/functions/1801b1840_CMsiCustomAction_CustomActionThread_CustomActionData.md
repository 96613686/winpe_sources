# CMsiCustomAction::CustomActionThread(CustomActionData *)

- ea: `0x1801b1840`
- end: `0x1801b1d7e`
- name: `?CustomActionThread@CMsiCustomAction@@CAKPEAVCustomActionData@@@Z`
- size: `1342`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c4bc`
- `0x180010ac0`
- `0x180020620`
- `0x18002ba68`
- `0x18004b6ac`
- `0x18009436c`
- `0x1800d08d0`
- `0x18013d934`
- `0x1801b1840`
- `0x1801c8834`
- `0x180259808`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1801b1a42`
- `KERNEL32!IsDebuggerPresent` at `0x1801b1a42`
- `KERNEL32!GetProcAddress` at `0x1801b1a20`
- `KERNEL32!GetProcAddress` at `0x1801b1a20`
- `KERNEL32!WideCharToMultiByte` at `0x1801b1a05`
- `KERNEL32!WideCharToMultiByte` at `0x1801b1a05`
- `KERNEL32!FreeLibrary` at `0x1801b1c71`
- `KERNEL32!FreeLibrary` at `0x1801b1c71`
- `KERNEL32!GetCurrentProcessId` at `0x1801b1a73`
- `KERNEL32!GetCurrentProcessId` at `0x1801b1a81`
- `KERNEL32!GetCurrentProcessId` at `0x1801b1a73`
- `KERNEL32!GetCurrentProcessId` at `0x1801b1a81`
- `KERNEL32!SetErrorMode` at `0x1801b18f6`
- `KERNEL32!SetErrorMode` at `0x1801b19a7`
- `KERNEL32!SetErrorMode` at `0x1801b18f6`
- `KERNEL32!SetErrorMode` at `0x1801b19a7`
- `USER32!MessageBoxW` at `0x1801b1b10`
- `USER32!MessageBoxW` at `0x1801b1b10`

## string_xrefs

- `0x1801b18b5`: `Custom action server running custom action: DLL: %s, Entrypoint: %s`
- `0x1801b1972`: `Custom action server's custom action threw an exception during load! (%u), returning %u`
- `0x1801b1cd6`: `Custom action server's custom action threw an exception during unload! (%u), returning %u`

## pseudocode

```c
__int64 __fastcall CMsiCustomAction::CustomActionThread(char *Parameter)
{
  const unsigned __int16 **v2; // r15
  UINT v3; // r12d
  HMODULE LibraryW; // r15
  enum iesEnum (__high *ProcAddress)(unsigned int); // r12
  DWORD CurrentProcessId; // ebx
  DWORD v7; // eax
  unsigned int v8; // ebx
  __int64 CurrentThreadId; // rax
  __int64 v10; // rcx
  unsigned int v11; // eax
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-3D8h]
  WCHAR Text; // [rsp+90h] [rbp-368h] BYREF
  _BYTE v15[558]; // [rsp+92h] [rbp-366h] BYREF
  CHAR MultiByteStr; // [rsp+2C0h] [rbp-138h] BYREF
  _BYTE v17[111]; // [rsp+2C1h] [rbp-137h] BYREF
  WCHAR Caption; // [rsp+330h] [rbp-C8h] BYREF
  _BYTE v19[126]; // [rsp+332h] [rbp-C6h] BYREF

  v2 = (const unsigned __int16 **)(Parameter + 8);
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"Custom action server running custom action: DLL: %s, Entrypoint: %s",
      *v2,
      *((const unsigned __int16 **)Parameter + 3),
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  if ( Parameter[37] )
    ((void (__fastcall *)(char *, char *, const unsigned __int16 *, _QWORD, _DWORD))APPHELP::ApphelpFixMsiPackage)(
      Parameter + 40,
      Parameter + 56,
      *v2,
      *((_QWORD *)Parameter + 2),
      0);
  v3 = SetErrorMode(1u);
  LibraryW = (HMODULE)IsolationAwareLoadLibraryW(*v2);
  SetErrorMode(v3);
  if ( LibraryW )
  {
    ProcAddress = 0;
    MultiByteStr = 0;
    memset_0(v17, 0, 0x63u);
    if ( WideCharToMultiByte(0, 0, *((LPCWCH *)Parameter + 3), -1, &MultiByteStr, 100, 0, 0) )
      ProcAddress = (enum iesEnum (__high *)(unsigned int))GetProcAddress(LibraryW, &MultiByteStr);
    if ( ProcAddress )
    {
      if ( Parameter[36] )
      {
        if ( !IsDebuggerPresent() )
        {
          Text = 0;
          memset_0(v15, 0, 0x1FEu);
          CurrentProcessId = GetCurrentProcessId();
          v7 = GetCurrentProcessId();
          LODWORD(lpMultiByteStr) = CurrentProcessId;
          if ( (int)StringCchPrintfW(
                      &Text,
                      0x100u,
                      L"To debug your custom action, attach your debugger to process %d (0x%X) and press OK",
                      v7,
                      lpMultiByteStr) >= 0 )
          {
            Caption = 0;
            memset_0(v19, 0, sizeof(v19));
            if ( !(unsigned int)MsiLoadStringW((HMODULE)0xFFFFFFFFFFFFFFFFLL, 0) )
              Caption = 0;
            MessageBoxW(0, &Text, &Caption, 0x40000u);
          }
        }
      }
      CWERReporter::CWERReporter(
        (CWERReporter *)&Text,
        *((_DWORD *)Parameter + 8),
        *((const unsigned __int16 **)Parameter + 2));
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Custom action server's custom action: (%s, %s)",
          *((const unsigned __int16 **)Parameter + 1),
          *((const unsigned __int16 **)Parameter + 3),
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v8 = CallCustomDllEntrypoint(ProcAddress, Parameter[36] != 0, *((_DWORD *)Parameter + 8));
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Custom action server's custom action is returning %u.",
          (const unsigned __int16 *)v8,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      CWERReporter::~CWERReporter((CWERReporter *)&Text);
    }
    else
    {
      v8 = 1154;
    }
    FreeLibrary(LibraryW);
  }
  else
  {
    v8 = 1157;
  }
  CurrentThreadId = MsiGetCurrentThreadId();
  LOBYTE(v10) = 1;
  v11 = CheckAllHandlesClosed(v10, CurrentThreadId);
  if ( v11 && g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"Custom action server's custom action leaked %d non-remoted handles",
      (const unsigned __int16 *)v11,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  return v8;
}

```

## disassembly

```asm
0x1801b1840  push    rbx
0x1801b1842  push    rsi
0x1801b1843  push    rdi
0x1801b1844  push    r12
0x1801b1846  push    r14
0x1801b1848  push    r15
0x1801b184a  sub     rsp, 3C8h
0x1801b1851  mov     rax, cs:__security_cookie
0x1801b1858  xor     rax, rsp
0x1801b185b  mov     [rsp+3F8h+var_48], rax
0x1801b1863  mov     r14, rcx
0x1801b1866  mov     [rsp+3F8h+var_378], rcx
0x1801b186e  xor     edi, edi
0x1801b1870  mov     ebx, edi
0x1801b1872  lea     r15, [rcx+8]
0x1801b1876  lea     rsi, aNull; "(NULL)"
0x1801b187d  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1801b1883  jz      short loc_1801B18C7
0x1801b1885  xor     edx, edx; unsigned __int16
0x1801b1887  mov     [rsp+3F8h+var_3A0], rdi; void *
0x1801b188c  mov     [rsp+3F8h+var_3A8], edi; unsigned int
0x1801b1890  mov     [rsp+3F8h+var_3B0], rsi; unsigned __int16 *
0x1801b1895  mov     [rsp+3F8h+var_3B8], rsi; unsigned __int16 *
0x1801b189a  mov     [rsp+3F8h+lpUsedDefaultChar], rsi; unsigned __int16 *
0x1801b189f  mov     [rsp+3F8h+lpDefaultChar], rsi; unsigned __int16 *
0x1801b18a4  mov     rax, [rcx+18h]
0x1801b18a8  mov     qword ptr [rsp+3F8h+cbMultiByte], rax; unsigned __int16 *
0x1801b18ad  mov     rax, [r15]
0x1801b18b0  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801b18b5  lea     r9, aCustomActionSe_5; "Custom action server running custom act"...
0x1801b18bc  xor     r8d, r8d; int
0x1801b18bf  lea     ecx, [rdi+9]; int
0x1801b18c2  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801b18c7  cmp     [r14+25h], dil
0x1801b18cb  jz      short loc_1801B18EC
0x1801b18cd  lea     rdx, [r14+38h]
0x1801b18d1  lea     rcx, [r14+28h]
0x1801b18d5  mov     dword ptr [rsp+3F8h+lpMultiByteStr], edi
0x1801b18d9  mov     r9, [r14+10h]
0x1801b18dd  mov     r8, [r15]
0x1801b18e0  mov     rax, cs:?ApphelpFixMsiPackage@APPHELP@@3P6AHPEAU_GUID@@0PEBG1K@ZEA; int (*APPHELP::ApphelpFixMsiPackage)(_GUID *,_GUID *,ushort const *,ushort const *,ulong)
0x1801b18e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b18ec  mov     [rsp+3F8h+var_380], rdi
0x1801b18f1  mov     ecx, 1; uMode
0x1801b18f6  call    cs:__imp_SetErrorMode
0x1801b18fd  nop     dword ptr [rax+rax+00h]
0x1801b1902  mov     r12d, eax
0x1801b1905  mov     [rsp+3F8h+var_388], eax
0x1801b1909  mov     rcx, [r15]; lpLibFileName
0x1801b190c  call    IsolationAwareLoadLibraryW
0x1801b1911  mov     r15, rax
0x1801b1914  mov     [rsp+3F8h+var_380], rax
0x1801b1919  jmp     loc_1801B19A4
0x1801b191e  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801b1925  jz      short loc_1801B1984
0x1801b1927  mov     eax, eax
0x1801b1929  xor     edx, edx; unsigned __int16
0x1801b192b  mov     [rsp+3F8h+var_3A0], rdx; void *
0x1801b1930  mov     [rsp+3F8h+var_3A8], edx; unsigned int
0x1801b1934  lea     rcx, aNull; "(NULL)"
0x1801b193b  mov     [rsp+3F8h+var_3B0], rcx; unsigned __int16 *
0x1801b1940  lea     rcx, aNull; "(NULL)"
0x1801b1947  mov     [rsp+3F8h+var_3B8], rcx; unsigned __int16 *
0x1801b194c  lea     rcx, aNull; "(NULL)"
0x1801b1953  mov     [rsp+3F8h+lpUsedDefaultChar], rcx; unsigned __int16 *
0x1801b1958  lea     rcx, aNull; "(NULL)"
0x1801b195f  mov     [rsp+3F8h+lpDefaultChar], rcx; unsigned __int16 *
0x1801b1964  mov     qword ptr [rsp+3F8h+cbMultiByte], 643h; unsigned __int16 *
0x1801b196d  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801b1972  lea     r9, aCustomActionSe_7; "Custom action server's custom action th"...
0x1801b1979  xor     r8d, r8d; int
0x1801b197c  lea     ecx, [rdx+9]; int
0x1801b197f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801b1984  mov     ebx, 643h
0x1801b1989  xor     edi, edi
0x1801b198b  lea     rsi, aNull; "(NULL)"
0x1801b1992  mov     r15, [rsp+3F8h+var_380]
0x1801b1997  mov     r14, [rsp+3F8h+var_378]
0x1801b199f  mov     r12d, [rsp+3F8h+var_388]
0x1801b19a4  mov     ecx, r12d; uMode
0x1801b19a7  call    cs:__imp_SetErrorMode
0x1801b19ae  nop     dword ptr [rax+rax+00h]
0x1801b19b3  test    r15, r15
0x1801b19b6  jz      loc_1801B1CF8
0x1801b19bc  mov     r12, rdi
0x1801b19bf  mov     [rsp+3F8h+MultiByteStr], dil
0x1801b19c7  xor     edx, edx; Val
0x1801b19c9  lea     r8d, [rdx+63h]; Size
0x1801b19cd  lea     rcx, [rsp+3F8h+var_137]; void *
0x1801b19d5  call    memset_0
0x1801b19da  mov     [rsp+3F8h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1801b19df  mov     [rsp+3F8h+lpDefaultChar], rdi; lpDefaultChar
0x1801b19e4  mov     [rsp+3F8h+cbMultiByte], 64h ; 'd'; cbMultiByte
0x1801b19ec  lea     rax, [rsp+3F8h+MultiByteStr]
0x1801b19f4  mov     [rsp+3F8h+lpMultiByteStr], rax; lpMultiByteStr
0x1801b19f9  or      r9d, 0FFFFFFFFh; cchWideChar
0x1801b19fd  mov     r8, [r14+18h]; lpWideCharStr
0x1801b1a01  xor     edx, edx; dwFlags
0x1801b1a03  xor     ecx, ecx; CodePage
0x1801b1a05  call    cs:__imp_WideCharToMultiByte
0x1801b1a0c  nop     dword ptr [rax+rax+00h]
0x1801b1a11  test    eax, eax
0x1801b1a13  jz      short loc_1801B1A2F
0x1801b1a15  lea     rdx, [rsp+3F8h+MultiByteStr]; lpProcName
0x1801b1a1d  mov     rcx, r15; hModule
0x1801b1a20  call    cs:__imp_GetProcAddress
0x1801b1a27  nop     dword ptr [rax+rax+00h]
0x1801b1a2c  mov     r12, rax
0x1801b1a2f  test    r12, r12
0x1801b1a32  jz      loc_1801B1C69
0x1801b1a38  cmp     [r14+24h], dil
0x1801b1a3c  jz      loc_1801B1B1C
0x1801b1a42  call    cs:__imp_IsDebuggerPresent
0x1801b1a49  nop     dword ptr [rax+rax+00h]
0x1801b1a4e  test    eax, eax
0x1801b1a50  jnz     loc_1801B1B1C
0x1801b1a56  mov     [rsp+3F8h+Text], di
0x1801b1a5e  xor     edx, edx; Val
0x1801b1a60  mov     r8d, 1FEh; Size
0x1801b1a66  lea     rcx, [rsp+3F8h+var_366]; void *
0x1801b1a6e  call    memset_0
0x1801b1a73  call    cs:__imp_GetCurrentProcessId
0x1801b1a7a  nop     dword ptr [rax+rax+00h]
0x1801b1a7f  mov     ebx, eax
0x1801b1a81  call    cs:__imp_GetCurrentProcessId
0x1801b1a88  nop     dword ptr [rax+rax+00h]
0x1801b1a8d  mov     dword ptr [rsp+3F8h+lpMultiByteStr], ebx
0x1801b1a91  mov     r9d, eax
0x1801b1a94  lea     r8, aToDebugYourCus; "To debug your custom action, attach you"...
0x1801b1a9b  mov     edx, 100h; unsigned __int64
0x1801b1aa0  lea     rcx, [rsp+3F8h+Text]; unsigned __int16 *
0x1801b1aa8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801b1aad  test    eax, eax
0x1801b1aaf  js      short loc_1801B1B1C
0x1801b1ab1  mov     [rsp+3F8h+Caption], di
0x1801b1ab9  xor     edx, edx; Val
0x1801b1abb  lea     r8d, [rdx+7Eh]; Size
0x1801b1abf  lea     rcx, [rsp+3F8h+var_C6]; void *
0x1801b1ac7  call    memset_0
0x1801b1acc  mov     word ptr [rsp+3F8h+lpMultiByteStr], di; unsigned __int16
0x1801b1ad1  mov     r9d, 40h ; '@'
0x1801b1ad7  lea     r8, [rsp+3F8h+Caption]
0x1801b1adf  lea     edx, [r9-24h]
0x1801b1ae3  or      rcx, 0FFFFFFFFFFFFFFFFh; hModule
0x1801b1ae7  call    MsiLoadStringW
0x1801b1aec  test    eax, eax
0x1801b1aee  jnz     short loc_1801B1AF8
0x1801b1af0  mov     [rsp+3F8h+Caption], di
0x1801b1af8  mov     r9d, 40000h; uType
0x1801b1afe  lea     r8, [rsp+3F8h+Caption]; lpCaption
0x1801b1b06  lea     rdx, [rsp+3F8h+Text]; lpText
0x1801b1b0e  xor     ecx, ecx; hWnd
0x1801b1b10  call    cs:__imp_MessageBoxW
0x1801b1b17  nop     dword ptr [rax+rax+00h]
0x1801b1b1c  mov     r8, [r14+10h]; unsigned __int16 *
0x1801b1b20  mov     edx, [r14+20h]; unsigned int
0x1801b1b24  lea     rcx, [rsp+3F8h+Text]; this
0x1801b1b2c  call    ??0CWERReporter@@QEAA@KPEBG@Z; CWERReporter::CWERReporter(ulong,ushort const *)
0x1801b1b31  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1801b1b37  jz      short loc_1801B1B7D
0x1801b1b39  xor     edx, edx; unsigned __int16
0x1801b1b3b  mov     [rsp+3F8h+var_3A0], rdi; void *
0x1801b1b40  mov     [rsp+3F8h+var_3A8], edi; unsigned int
0x1801b1b44  mov     [rsp+3F8h+var_3B0], rsi; unsigned __int16 *
0x1801b1b49  mov     [rsp+3F8h+var_3B8], rsi; unsigned __int16 *
0x1801b1b4e  mov     [rsp+3F8h+lpUsedDefaultChar], rsi; unsigned __int16 *
0x1801b1b53  mov     [rsp+3F8h+lpDefaultChar], rsi; unsigned __int16 *
0x1801b1b58  mov     rax, [r14+18h]
0x1801b1b5c  mov     qword ptr [rsp+3F8h+cbMultiByte], rax; unsigned __int16 *
0x1801b1b61  mov     rax, [r14+8]
0x1801b1b65  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801b1b6a  lea     r9, aCustomActionSe_3; "Custom action server's custom action: ("...
0x1801b1b71  xor     r8d, r8d; int
0x1801b1b74  lea     ecx, [rdx+9]; int
0x1801b1b77  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801b1b7c  nop
0x1801b1b7d  cmp     [r14+24h], dil
0x1801b1b81  setnz   dl; bool
0x1801b1b84  mov     r8d, [r14+20h]; unsigned int
0x1801b1b88  mov     rcx, r12; enum iesEnum (__high *)(unsigned int)
0x1801b1b8b  call    ?CallCustomDllEntrypoint@@YAKP6A?AW4iesEnum@@K@Z_NK@Z; CallCustomDllEntrypoint(iesEnum (*)(ulong),bool,ulong)
0x1801b1b90  mov     ebx, eax
0x1801b1b92  mov     [rsp+3F8h+var_384], eax
0x1801b1b96  jmp     short loc_1801B1C15
0x1801b1b98  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801b1b9f  jz      short loc_1801B1BFE
0x1801b1ba1  mov     eax, eax
0x1801b1ba3  xor     edx, edx; unsigned __int16
0x1801b1ba5  mov     [rsp+3F8h+var_3A0], rdx; void *
0x1801b1baa  mov     [rsp+3F8h+var_3A8], edx; unsigned int
0x1801b1bae  lea     rcx, aNull; "(NULL)"
0x1801b1bb5  mov     [rsp+3F8h+var_3B0], rcx; unsigned __int16 *
0x1801b1bba  lea     rcx, aNull; "(NULL)"
0x1801b1bc1  mov     [rsp+3F8h+var_3B8], rcx; unsigned __int16 *
0x1801b1bc6  lea     rcx, aNull; "(NULL)"
0x1801b1bcd  mov     [rsp+3F8h+lpUsedDefaultChar], rcx; unsigned __int16 *
0x1801b1bd2  lea     rcx, aNull; "(NULL)"
0x1801b1bd9  mov     [rsp+3F8h+lpDefaultChar], rcx; unsigned __int16 *
0x1801b1bde  mov     qword ptr [rsp+3F8h+cbMultiByte], 643h; unsigned __int16 *
0x1801b1be7  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801b1bec  lea     r9, aCustomActionSe; "Custom action server's custom action th"...
0x1801b1bf3  xor     r8d, r8d; int
0x1801b1bf6  lea     ecx, [rdx+9]; int
0x1801b1bf9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801b1bfe  mov     ebx, 643h
0x1801b1c03  mov     [rsp+3F8h+var_384], ebx
0x1801b1c07  xor     edi, edi
0x1801b1c09  lea     rsi, aNull; "(NULL)"
0x1801b1c10  mov     r15, [rsp+3F8h+var_380]
0x1801b1c15  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1801b1c1b  jz      short loc_1801B1C5A
0x1801b1c1d  mov     eax, ebx
0x1801b1c1f  xor     edx, edx; unsigned __int16
0x1801b1c21  mov     [rsp+3F8h+var_3A0], rdi; void *
0x1801b1c26  mov     [rsp+3F8h+var_3A8], edi; unsigned int
0x1801b1c2a  mov     [rsp+3F8h+var_3B0], rsi; unsigned __int16 *
0x1801b1c2f  mov     [rsp+3F8h+var_3B8], rsi; unsigned __int16 *
0x1801b1c34  mov     [rsp+3F8h+lpUsedDefaultChar], rsi; unsigned __int16 *
0x1801b1c39  mov     [rsp+3F8h+lpDefaultChar], rsi; unsigned __int16 *
0x1801b1c3e  mov     qword ptr [rsp+3F8h+cbMultiByte], rsi; unsigned __int16 *
0x1801b1c43  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801b1c48  lea     r9, aCustomActionSe_10; "Custom action server's custom action is"...
0x1801b1c4f  xor     r8d, r8d; int
0x1801b1c52  lea     ecx, [rdx+9]; int
0x1801b1c55  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801b1c5a  lea     rcx, [rsp+3F8h+Text]; this
0x1801b1c62  call    ??1CWERReporter@@UEAA@XZ; CWERReporter::~CWERReporter(void)
0x1801b1c67  jmp     short loc_1801B1C6E
0x1801b1c69  mov     ebx, 482h
0x1801b1c6e  mov     rcx, r15; hLibModule
0x1801b1c71  call    cs:__imp_FreeLibrary
0x1801b1c78  nop     dword ptr [rax+rax+00h]
0x1801b1c7d  jmp     loc_1801B1D02
0x1801b1c82  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801b1c89  jz      short loc_1801B1CE8
0x1801b1c8b  mov     eax, eax
0x1801b1c8d  xor     edx, edx; unsigned __int16
0x1801b1c8f  mov     [rsp+3F8h+var_3A0], rdx; void *
0x1801b1c94  mov     [rsp+3F8h+var_3A8], edx; unsigned int
0x1801b1c98  lea     rcx, aNull; "(NULL)"
0x1801b1c9f  mov     [rsp+3F8h+var_3B0], rcx; unsigned __int16 *
0x1801b1ca4  lea     rcx, aNull; "(NULL)"
0x1801b1cab  mov     [rsp+3F8h+var_3B8], rcx; unsigned __int16 *
0x1801b1cb0  lea     rcx, aNull; "(NULL)"
0x1801b1cb7  mov     [rsp+3F8h+lpUsedDefaultChar], rcx; unsigned __int16 *
0x1801b1cbc  lea     rcx, aNull; "(NULL)"
0x1801b1cc3  mov     [rsp+3F8h+lpDefaultChar], rcx; unsigned __int16 *
0x1801b1cc8  mov     qword ptr [rsp+3F8h+cbMultiByte], 643h; unsigned __int16 *
0x1801b1cd1  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801b1cd6  lea     r9, aCustomActionSe_2; "Custom action server's custom action th"...
0x1801b1cdd  xor     r8d, r8d; int
0x1801b1ce0  lea     ecx, [rdx+9]; int
0x1801b1ce3  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801b1ce8  mov     ebx, 643h
0x1801b1ced  xor     edi, edi
0x1801b1cef  lea     rsi, aNull; "(NULL)"
0x1801b1cf6  jmp     short loc_1801B1D02
0x1801b1cf8  mov     eax, 485h
0x1801b1cfd  test    ebx, ebx
0x1801b1cff  cmovz   ebx, eax
0x1801b1d02  call    ?MsiGetCurrentThreadId@@YA?AUUniqueThreadID@@XZ; MsiGetCurrentThreadId(void)
0x1801b1d07  mov     rdx, rax
0x1801b1d0a  mov     cl, 1
0x1801b1d0c  call    ?CheckAllHandlesClosed@@YAI_NUUniqueThreadID@@@Z; CheckAllHandlesClosed(bool,UniqueThreadID)
0x1801b1d11  test    eax, eax
0x1801b1d13  jz      short loc_1801B1D5A
0x1801b1d15  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1801b1d1b  jz      short loc_1801B1D5A
0x1801b1d1d  mov     eax, eax
0x1801b1d1f  xor     edx, edx; unsigned __int16
0x1801b1d21  mov     [rsp+3F8h+var_3A0], rdi; void *
0x1801b1d26  mov     [rsp+3F8h+var_3A8], edi; unsigned int
0x1801b1d2a  mov     [rsp+3F8h+var_3B0], rsi; unsigned __int16 *
0x1801b1d2f  mov     [rsp+3F8h+var_3B8], rsi; unsigned __int16 *
0x1801b1d34  mov     [rsp+3F8h+lpUsedDefaultChar], rsi; unsigned __int16 *
0x1801b1d39  mov     [rsp+3F8h+lpDefaultChar], rsi; unsigned __int16 *
0x1801b1d3e  mov     qword ptr [rsp+3F8h+cbMultiByte], rsi; unsigned __int16 *
0x1801b1d43  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801b1d48  lea     r9, aCustomActionSe_9; "Custom action server's custom action le"...
0x1801b1d4f  xor     r8d, r8d; int
0x1801b1d52  lea     ecx, [rdx+9]; int
0x1801b1d55  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801b1d5a  mov     eax, ebx
0x1801b1d5c  mov     rcx, [rsp+3F8h+var_48]
0x1801b1d64  xor     rcx, rsp; StackCookie
0x1801b1d67  call    __security_check_cookie
0x1801b1d6c  add     rsp, 3C8h
0x1801b1d73  pop     r15
0x1801b1d75  pop     r14
0x1801b1d77  pop     r12
0x1801b1d79  pop     rdi
0x1801b1d7a  pop     rsi
0x1801b1d7b  pop     rbx
0x1801b1d7c  retn
0x180265892  push    rbp
0x180265894  sub     rsp, 60h
0x180265898  mov     rbp, rdx
0x18026589b  call    ?CustomActionExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; CustomActionExceptionFilter(_EXCEPTION_POINTERS *)
0x1802658a0  nop
0x1802658a1  add     rsp, 60h
  ... truncated ...
```
