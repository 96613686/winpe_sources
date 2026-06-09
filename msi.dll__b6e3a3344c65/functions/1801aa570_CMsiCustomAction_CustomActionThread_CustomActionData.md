# CMsiCustomAction::CustomActionThread(CustomActionData *)

- ea: `0x1801aa570`
- end: `0x1801aaa77`
- name: `?CustomActionThread@CMsiCustomAction@@CAKPEAVCustomActionData@@@Z`
- size: `1287`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180022120`
- `0x180025a18`
- `0x18003cd20`
- `0x18004aca8`
- `0x180057008`
- `0x18006e484`
- `0x1800c2bf0`
- `0x180138780`
- `0x1801aa570`
- `0x1801c0374`
- `0x18024f4b8`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1801aa75a`
- `KERNEL32!IsDebuggerPresent` at `0x1801aa75a`
- `KERNEL32!GetProcAddress` at `0x1801aa73e`
- `KERNEL32!GetProcAddress` at `0x1801aa73e`
- `KERNEL32!WideCharToMultiByte` at `0x1801aa729`
- `KERNEL32!WideCharToMultiByte` at `0x1801aa729`
- `KERNEL32!FreeLibrary` at `0x1801aa971`
- `KERNEL32!FreeLibrary` at `0x1801aa971`
- `KERNEL32!GetCurrentProcessId` at `0x1801aa785`
- `KERNEL32!GetCurrentProcessId` at `0x1801aa78d`
- `KERNEL32!GetCurrentProcessId` at `0x1801aa785`
- `KERNEL32!GetCurrentProcessId` at `0x1801aa78d`
- `KERNEL32!SetErrorMode` at `0x1801aa626`
- `KERNEL32!SetErrorMode` at `0x1801aa6d1`
- `KERNEL32!SetErrorMode` at `0x1801aa626`
- `KERNEL32!SetErrorMode` at `0x1801aa6d1`
- `USER32!MessageBoxW` at `0x1801aa816`
- `USER32!MessageBoxW` at `0x1801aa816`

## string_xrefs

- `0x1801aa5e5`: `Custom action server running custom action: DLL: %s, Entrypoint: %s`
- `0x1801aa69c`: `Custom action server's custom action threw an exception during load! (%u), returning %u`
- `0x1801aa9d0`: `Custom action server's custom action threw an exception during unload! (%u), returning %u`

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
0x1801aa570  push    rbx
0x1801aa572  push    rsi
0x1801aa573  push    rdi
0x1801aa574  push    r12
0x1801aa576  push    r14
0x1801aa578  push    r15
0x1801aa57a  sub     rsp, 3C8h
0x1801aa581  mov     rax, cs:__security_cookie
0x1801aa588  xor     rax, rsp
0x1801aa58b  mov     [rsp+3F8h+var_48], rax
0x1801aa593  mov     r14, rcx
0x1801aa596  mov     [rsp+3F8h+var_378], rcx
0x1801aa59e  xor     edi, edi
0x1801aa5a0  mov     ebx, edi
0x1801aa5a2  lea     r15, [rcx+8]
0x1801aa5a6  lea     rsi, aNull; "(NULL)"
0x1801aa5ad  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1801aa5b3  jz      short loc_1801AA5F7
0x1801aa5b5  xor     edx, edx; unsigned __int16
0x1801aa5b7  mov     [rsp+3F8h+var_3A0], rdi; void *
0x1801aa5bc  mov     [rsp+3F8h+var_3A8], edi; unsigned int
0x1801aa5c0  mov     [rsp+3F8h+var_3B0], rsi; unsigned __int16 *
0x1801aa5c5  mov     [rsp+3F8h+var_3B8], rsi; unsigned __int16 *
0x1801aa5ca  mov     [rsp+3F8h+lpUsedDefaultChar], rsi; unsigned __int16 *
0x1801aa5cf  mov     [rsp+3F8h+lpDefaultChar], rsi; unsigned __int16 *
0x1801aa5d4  mov     rax, [rcx+18h]
0x1801aa5d8  mov     qword ptr [rsp+3F8h+cbMultiByte], rax; unsigned __int16 *
0x1801aa5dd  mov     rax, [r15]
0x1801aa5e0  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801aa5e5  lea     r9, aCustomActionSe_5; "Custom action server running custom act"...
0x1801aa5ec  xor     r8d, r8d; int
0x1801aa5ef  lea     ecx, [rdi+9]; int
0x1801aa5f2  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801aa5f7  cmp     [r14+25h], dil
0x1801aa5fb  jz      short loc_1801AA61C
0x1801aa5fd  lea     rdx, [r14+38h]
0x1801aa601  lea     rcx, [r14+28h]
0x1801aa605  mov     dword ptr [rsp+3F8h+lpMultiByteStr], edi
0x1801aa609  mov     r9, [r14+10h]
0x1801aa60d  mov     r8, [r15]
0x1801aa610  mov     rax, cs:?ApphelpFixMsiPackage@APPHELP@@3P6AHPEAU_GUID@@0PEBG1K@ZEA; int (*APPHELP::ApphelpFixMsiPackage)(_GUID *,_GUID *,ushort const *,ushort const *,ulong)
0x1801aa617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aa61c  mov     [rsp+3F8h+var_380], rdi
0x1801aa621  mov     ecx, 1; uMode
0x1801aa626  call    cs:__imp_SetErrorMode
0x1801aa62c  mov     r12d, eax
0x1801aa62f  mov     [rsp+3F8h+var_388], eax
0x1801aa633  mov     rcx, [r15]; lpLibFileName
0x1801aa636  call    IsolationAwareLoadLibraryW
0x1801aa63b  mov     r15, rax
0x1801aa63e  mov     [rsp+3F8h+var_380], rax
0x1801aa643  jmp     loc_1801AA6CE
0x1801aa648  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801aa64f  jz      short loc_1801AA6AE
0x1801aa651  mov     eax, eax
0x1801aa653  xor     edx, edx; unsigned __int16
0x1801aa655  mov     [rsp+3F8h+var_3A0], rdx; void *
0x1801aa65a  mov     [rsp+3F8h+var_3A8], edx; unsigned int
0x1801aa65e  lea     rcx, aNull; "(NULL)"
0x1801aa665  mov     [rsp+3F8h+var_3B0], rcx; unsigned __int16 *
0x1801aa66a  lea     rcx, aNull; "(NULL)"
0x1801aa671  mov     [rsp+3F8h+var_3B8], rcx; unsigned __int16 *
0x1801aa676  lea     rcx, aNull; "(NULL)"
0x1801aa67d  mov     [rsp+3F8h+lpUsedDefaultChar], rcx; unsigned __int16 *
0x1801aa682  lea     rcx, aNull; "(NULL)"
0x1801aa689  mov     [rsp+3F8h+lpDefaultChar], rcx; unsigned __int16 *
0x1801aa68e  mov     qword ptr [rsp+3F8h+cbMultiByte], 643h; unsigned __int16 *
0x1801aa697  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801aa69c  lea     r9, aCustomActionSe_7; "Custom action server's custom action th"...
0x1801aa6a3  xor     r8d, r8d; int
0x1801aa6a6  lea     ecx, [rdx+9]; int
0x1801aa6a9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801aa6ae  mov     ebx, 643h
0x1801aa6b3  xor     edi, edi
0x1801aa6b5  lea     rsi, aNull; "(NULL)"
0x1801aa6bc  mov     r15, [rsp+3F8h+var_380]
0x1801aa6c1  mov     r14, [rsp+3F8h+var_378]
0x1801aa6c9  mov     r12d, [rsp+3F8h+var_388]
0x1801aa6ce  mov     ecx, r12d; uMode
0x1801aa6d1  call    cs:__imp_SetErrorMode
0x1801aa6d7  test    r15, r15
0x1801aa6da  jz      loc_1801AA9F2
0x1801aa6e0  mov     r12, rdi
0x1801aa6e3  mov     [rsp+3F8h+MultiByteStr], dil
0x1801aa6eb  xor     edx, edx; Val
0x1801aa6ed  lea     r8d, [rdx+63h]; Size
0x1801aa6f1  lea     rcx, [rsp+3F8h+var_137]; void *
0x1801aa6f9  call    memset_0
0x1801aa6fe  mov     [rsp+3F8h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1801aa703  mov     [rsp+3F8h+lpDefaultChar], rdi; lpDefaultChar
0x1801aa708  mov     [rsp+3F8h+cbMultiByte], 64h ; 'd'; cbMultiByte
0x1801aa710  lea     rax, [rsp+3F8h+MultiByteStr]
0x1801aa718  mov     [rsp+3F8h+lpMultiByteStr], rax; lpMultiByteStr
0x1801aa71d  or      r9d, 0FFFFFFFFh; cchWideChar
0x1801aa721  mov     r8, [r14+18h]; lpWideCharStr
0x1801aa725  xor     edx, edx; dwFlags
0x1801aa727  xor     ecx, ecx; CodePage
0x1801aa729  call    cs:__imp_WideCharToMultiByte
0x1801aa72f  test    eax, eax
0x1801aa731  jz      short loc_1801AA747
0x1801aa733  lea     rdx, [rsp+3F8h+MultiByteStr]; lpProcName
0x1801aa73b  mov     rcx, r15; hModule
0x1801aa73e  call    cs:__imp_GetProcAddress
0x1801aa744  mov     r12, rax
0x1801aa747  test    r12, r12
0x1801aa74a  jz      loc_1801AA969
0x1801aa750  cmp     [r14+24h], dil
0x1801aa754  jz      loc_1801AA81C
0x1801aa75a  call    cs:__imp_IsDebuggerPresent
0x1801aa760  test    eax, eax
0x1801aa762  jnz     loc_1801AA81C
0x1801aa768  mov     [rsp+3F8h+Text], di
0x1801aa770  xor     edx, edx; Val
0x1801aa772  mov     r8d, 1FEh; Size
0x1801aa778  lea     rcx, [rsp+3F8h+var_366]; void *
0x1801aa780  call    memset_0
0x1801aa785  call    cs:__imp_GetCurrentProcessId
0x1801aa78b  mov     ebx, eax
0x1801aa78d  call    cs:__imp_GetCurrentProcessId
0x1801aa793  mov     dword ptr [rsp+3F8h+lpMultiByteStr], ebx
0x1801aa797  mov     r9d, eax
0x1801aa79a  lea     r8, aToDebugYourCus; "To debug your custom action, attach you"...
0x1801aa7a1  mov     edx, 100h; unsigned __int64
0x1801aa7a6  lea     rcx, [rsp+3F8h+Text]; unsigned __int16 *
0x1801aa7ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801aa7b3  test    eax, eax
0x1801aa7b5  js      short loc_1801AA81C
0x1801aa7b7  mov     [rsp+3F8h+Caption], di
0x1801aa7bf  xor     edx, edx; Val
0x1801aa7c1  lea     r8d, [rdx+7Eh]; Size
0x1801aa7c5  lea     rcx, [rsp+3F8h+var_C6]; void *
0x1801aa7cd  call    memset_0
0x1801aa7d2  mov     word ptr [rsp+3F8h+lpMultiByteStr], di; unsigned __int16
0x1801aa7d7  mov     r9d, 40h ; '@'
0x1801aa7dd  lea     r8, [rsp+3F8h+Caption]
0x1801aa7e5  lea     edx, [r9-24h]
0x1801aa7e9  or      rcx, 0FFFFFFFFFFFFFFFFh; hModule
0x1801aa7ed  call    MsiLoadStringW
0x1801aa7f2  test    eax, eax
0x1801aa7f4  jnz     short loc_1801AA7FE
0x1801aa7f6  mov     [rsp+3F8h+Caption], di
0x1801aa7fe  mov     r9d, 40000h; uType
0x1801aa804  lea     r8, [rsp+3F8h+Caption]; lpCaption
0x1801aa80c  lea     rdx, [rsp+3F8h+Text]; lpText
0x1801aa814  xor     ecx, ecx; hWnd
0x1801aa816  call    cs:__imp_MessageBoxW
0x1801aa81c  mov     r8, [r14+10h]; unsigned __int16 *
0x1801aa820  mov     edx, [r14+20h]; unsigned int
0x1801aa824  lea     rcx, [rsp+3F8h+Text]; this
0x1801aa82c  call    ??0CWERReporter@@QEAA@KPEBG@Z; CWERReporter::CWERReporter(ulong,ushort const *)
0x1801aa831  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1801aa837  jz      short loc_1801AA87D
0x1801aa839  xor     edx, edx; unsigned __int16
0x1801aa83b  mov     [rsp+3F8h+var_3A0], rdi; void *
0x1801aa840  mov     [rsp+3F8h+var_3A8], edi; unsigned int
0x1801aa844  mov     [rsp+3F8h+var_3B0], rsi; unsigned __int16 *
0x1801aa849  mov     [rsp+3F8h+var_3B8], rsi; unsigned __int16 *
0x1801aa84e  mov     [rsp+3F8h+lpUsedDefaultChar], rsi; unsigned __int16 *
0x1801aa853  mov     [rsp+3F8h+lpDefaultChar], rsi; unsigned __int16 *
0x1801aa858  mov     rax, [r14+18h]
0x1801aa85c  mov     qword ptr [rsp+3F8h+cbMultiByte], rax; unsigned __int16 *
0x1801aa861  mov     rax, [r14+8]
0x1801aa865  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801aa86a  lea     r9, aCustomActionSe_3; "Custom action server's custom action: ("...
0x1801aa871  xor     r8d, r8d; int
0x1801aa874  lea     ecx, [rdx+9]; int
0x1801aa877  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801aa87c  nop
0x1801aa87d  cmp     [r14+24h], dil
0x1801aa881  setnz   dl; bool
0x1801aa884  mov     r8d, [r14+20h]; unsigned int
0x1801aa888  mov     rcx, r12; enum iesEnum (__high *)(unsigned int)
0x1801aa88b  call    ?CallCustomDllEntrypoint@@YAKP6A?AW4iesEnum@@K@Z_NK@Z; CallCustomDllEntrypoint(iesEnum (*)(ulong),bool,ulong)
0x1801aa890  mov     ebx, eax
0x1801aa892  mov     [rsp+3F8h+var_384], eax
0x1801aa896  jmp     short loc_1801AA915
0x1801aa898  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801aa89f  jz      short loc_1801AA8FE
0x1801aa8a1  mov     eax, eax
0x1801aa8a3  xor     edx, edx; unsigned __int16
0x1801aa8a5  mov     [rsp+3F8h+var_3A0], rdx; void *
0x1801aa8aa  mov     [rsp+3F8h+var_3A8], edx; unsigned int
0x1801aa8ae  lea     rcx, aNull; "(NULL)"
0x1801aa8b5  mov     [rsp+3F8h+var_3B0], rcx; unsigned __int16 *
0x1801aa8ba  lea     rcx, aNull; "(NULL)"
0x1801aa8c1  mov     [rsp+3F8h+var_3B8], rcx; unsigned __int16 *
0x1801aa8c6  lea     rcx, aNull; "(NULL)"
0x1801aa8cd  mov     [rsp+3F8h+lpUsedDefaultChar], rcx; unsigned __int16 *
0x1801aa8d2  lea     rcx, aNull; "(NULL)"
0x1801aa8d9  mov     [rsp+3F8h+lpDefaultChar], rcx; unsigned __int16 *
0x1801aa8de  mov     qword ptr [rsp+3F8h+cbMultiByte], 643h; unsigned __int16 *
0x1801aa8e7  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801aa8ec  lea     r9, aCustomActionSe; "Custom action server's custom action th"...
0x1801aa8f3  xor     r8d, r8d; int
0x1801aa8f6  lea     ecx, [rdx+9]; int
0x1801aa8f9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801aa8fe  mov     ebx, 643h
0x1801aa903  mov     [rsp+3F8h+var_384], ebx
0x1801aa907  xor     edi, edi
0x1801aa909  lea     rsi, aNull; "(NULL)"
0x1801aa910  mov     r15, [rsp+3F8h+var_380]
0x1801aa915  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1801aa91b  jz      short loc_1801AA95A
0x1801aa91d  mov     eax, ebx
0x1801aa91f  xor     edx, edx; unsigned __int16
0x1801aa921  mov     [rsp+3F8h+var_3A0], rdi; void *
0x1801aa926  mov     [rsp+3F8h+var_3A8], edi; unsigned int
0x1801aa92a  mov     [rsp+3F8h+var_3B0], rsi; unsigned __int16 *
0x1801aa92f  mov     [rsp+3F8h+var_3B8], rsi; unsigned __int16 *
0x1801aa934  mov     [rsp+3F8h+lpUsedDefaultChar], rsi; unsigned __int16 *
0x1801aa939  mov     [rsp+3F8h+lpDefaultChar], rsi; unsigned __int16 *
0x1801aa93e  mov     qword ptr [rsp+3F8h+cbMultiByte], rsi; unsigned __int16 *
0x1801aa943  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801aa948  lea     r9, aCustomActionSe_10; "Custom action server's custom action is"...
0x1801aa94f  xor     r8d, r8d; int
0x1801aa952  lea     ecx, [rdx+9]; int
0x1801aa955  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801aa95a  lea     rcx, [rsp+3F8h+Text]; this
0x1801aa962  call    ??1CWERReporter@@UEAA@XZ; CWERReporter::~CWERReporter(void)
0x1801aa967  jmp     short loc_1801AA96E
0x1801aa969  mov     ebx, 482h
0x1801aa96e  mov     rcx, r15; hLibModule
0x1801aa971  call    cs:__imp_FreeLibrary
0x1801aa977  jmp     loc_1801AA9FC
0x1801aa97c  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801aa983  jz      short loc_1801AA9E2
0x1801aa985  mov     eax, eax
0x1801aa987  xor     edx, edx; unsigned __int16
0x1801aa989  mov     [rsp+3F8h+var_3A0], rdx; void *
0x1801aa98e  mov     [rsp+3F8h+var_3A8], edx; unsigned int
0x1801aa992  lea     rcx, aNull; "(NULL)"
0x1801aa999  mov     [rsp+3F8h+var_3B0], rcx; unsigned __int16 *
0x1801aa99e  lea     rcx, aNull; "(NULL)"
0x1801aa9a5  mov     [rsp+3F8h+var_3B8], rcx; unsigned __int16 *
0x1801aa9aa  lea     rcx, aNull; "(NULL)"
0x1801aa9b1  mov     [rsp+3F8h+lpUsedDefaultChar], rcx; unsigned __int16 *
0x1801aa9b6  lea     rcx, aNull; "(NULL)"
0x1801aa9bd  mov     [rsp+3F8h+lpDefaultChar], rcx; unsigned __int16 *
0x1801aa9c2  mov     qword ptr [rsp+3F8h+cbMultiByte], 643h; unsigned __int16 *
0x1801aa9cb  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801aa9d0  lea     r9, aCustomActionSe_2; "Custom action server's custom action th"...
0x1801aa9d7  xor     r8d, r8d; int
0x1801aa9da  lea     ecx, [rdx+9]; int
0x1801aa9dd  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801aa9e2  mov     ebx, 643h
0x1801aa9e7  xor     edi, edi
0x1801aa9e9  lea     rsi, aNull; "(NULL)"
0x1801aa9f0  jmp     short loc_1801AA9FC
0x1801aa9f2  mov     eax, 485h
0x1801aa9f7  test    ebx, ebx
0x1801aa9f9  cmovz   ebx, eax
0x1801aa9fc  call    ?MsiGetCurrentThreadId@@YA?AUUniqueThreadID@@XZ; MsiGetCurrentThreadId(void)
0x1801aaa01  mov     rdx, rax
0x1801aaa04  mov     cl, 1
0x1801aaa06  call    ?CheckAllHandlesClosed@@YAI_NUUniqueThreadID@@@Z; CheckAllHandlesClosed(bool,UniqueThreadID)
0x1801aaa0b  test    eax, eax
0x1801aaa0d  jz      short loc_1801AAA54
0x1801aaa0f  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x1801aaa15  jz      short loc_1801AAA54
0x1801aaa17  mov     eax, eax
0x1801aaa19  xor     edx, edx; unsigned __int16
0x1801aaa1b  mov     [rsp+3F8h+var_3A0], rdi; void *
0x1801aaa20  mov     [rsp+3F8h+var_3A8], edi; unsigned int
0x1801aaa24  mov     [rsp+3F8h+var_3B0], rsi; unsigned __int16 *
0x1801aaa29  mov     [rsp+3F8h+var_3B8], rsi; unsigned __int16 *
0x1801aaa2e  mov     [rsp+3F8h+lpUsedDefaultChar], rsi; unsigned __int16 *
0x1801aaa33  mov     [rsp+3F8h+lpDefaultChar], rsi; unsigned __int16 *
0x1801aaa38  mov     qword ptr [rsp+3F8h+cbMultiByte], rsi; unsigned __int16 *
0x1801aaa3d  mov     [rsp+3F8h+lpMultiByteStr], rax; unsigned __int16 *
0x1801aaa42  lea     r9, aCustomActionSe_9; "Custom action server's custom action le"...
0x1801aaa49  xor     r8d, r8d; int
0x1801aaa4c  lea     ecx, [rdx+9]; int
0x1801aaa4f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801aaa54  mov     eax, ebx
0x1801aaa56  mov     rcx, [rsp+3F8h+var_48]
0x1801aaa5e  xor     rcx, rsp; StackCookie
0x1801aaa61  call    __security_check_cookie
0x1801aaa66  add     rsp, 3C8h
0x1801aaa6d  pop     r15
0x1801aaa6f  pop     r14
0x1801aaa71  pop     r12
0x1801aaa73  pop     rdi
0x1801aaa74  pop     rsi
0x1801aaa75  pop     rbx
0x1801aaa76  retn
0x18025b192  push    rbp
0x18025b194  sub     rsp, 60h
0x18025b198  mov     rbp, rdx
0x18025b19b  call    ?CustomActionExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; CustomActionExceptionFilter(_EXCEPTION_POINTERS *)
0x18025b1a0  nop
0x18025b1a1  add     rsp, 60h
0x18025b1a5  pop     rbp
0x18025b1a6  retn
0x18025b1a8  push    rbp
0x18025b1aa  sub     rsp, 60h
0x18025b1ae  mov     rbp, rdx
0x18025b1b1  mov     [rbp+68h], rcx
0x18025b1b5  mov     rax, [rbp+68h]
0x18025b1b9  test    rax, rax
0x18025b1bc  jz      short loc_18025B201
  ... truncated ...
```
