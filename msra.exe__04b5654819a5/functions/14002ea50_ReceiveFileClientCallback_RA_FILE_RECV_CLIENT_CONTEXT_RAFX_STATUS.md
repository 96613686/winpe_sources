# ReceiveFileClientCallback(RA_FILE_RECV_CLIENT_CONTEXT *,RAFX_STATUS)

- ea: `0x14002ea50`
- end: `0x14002f0c8`
- name: `?ReceiveFileClientCallback@@YAJPEAURA_FILE_RECV_CLIENT_CONTEXT@@W4RAFX_STATUS@@@Z`
- size: `1656`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x14002e288`
- `0x14002ea50`
- `0x140034ce4`
- `0x140035888`
- `0x14003f9fc`
- `0x14003fa5c`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x14002eb62`
- `KERNEL32!MoveFileExW` at `0x14002eb62`
- `KERNEL32!CreateThread` at `0x14002f02f`
- `KERNEL32!CreateThread` at `0x14002f02f`
- `KERNEL32!GetModuleHandleW` at `0x14002ec3d`
- `KERNEL32!GetModuleHandleW` at `0x14002ec3d`
- `KERNEL32!CloseHandle` at `0x14002f04e`
- `KERNEL32!CloseHandle` at `0x14002f04e`
- `USER32!LoadStringW` at `0x14002ec60`
- `USER32!LoadStringW` at `0x14002ec60`
- `msvcrt!free` at `0x14002ecbc`
- `msvcrt!free` at `0x14002ecbc`
- `msvcrt!calloc` at `0x14002ebe2`
- `msvcrt!calloc` at `0x14002ebe2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002ef53`
- `OLEAUT32!__imp_SysAllocString` at `0x14002ef53`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ef35`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f082`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f096`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ef35`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f082`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f096`
- `SHLWAPI!PathFindExtensionW` at `0x14002edf2`
- `SHLWAPI!PathFindExtensionW` at `0x14002edf2`
- `SHLWAPI!PathFindFileNameW` at `0x14002ee17`
- `SHLWAPI!PathFindFileNameW` at `0x14002ee17`
- `COMDLG32!GetSaveFileNameW` at `0x14002ef0e`
- `COMDLG32!GetSaveFileNameW` at `0x14002ef0e`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002edae`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002edae`

## pseudocode

```c
__int64 __fastcall ReceiveFileClientCallback(__int64 a1, unsigned int a2)
{
  bool v4; // zf
  unsigned __int16 *v5; // r14
  unsigned __int16 *v6; // r15
  unsigned int v8; // ebx
  unsigned int v9; // edi
  unsigned int v10; // edi
  unsigned int v11; // edi
  unsigned int v12; // edi
  CEventLogger *v13; // rcx
  CEventLogger *v14; // rcx
  TASKDIALOGCONFIG *v15; // rdi
  unsigned int v16; // r9d
  HMODULE ModuleHandleW; // rax
  CEventLogger *v18; // rcx
  unsigned int v19; // r9d
  CRATicket *v20; // rcx
  signed int v21; // eax
  CEventLogger *v22; // rcx
  CEventLogger *v23; // rcx
  HRESULT v24; // eax
  CEventLogger *v25; // rcx
  LPWSTR ExtensionW; // rax
  __int64 v27; // rbx
  const WCHAR *v28; // r12
  LPWSTR FileNameW; // rax
  __int64 v30; // rdx
  OLECHAR *v31; // r8
  CEventLogger *v32; // rcx
  int DirectoryAsBSTR; // eax
  HWND v34; // rcx
  OLECHAR *v35; // rcx
  BSTR v36; // rax
  CEventLogger *v37; // r13
  __int64 v38; // rax
  HANDLE Thread; // rax
  int pnButton; // [rsp+30h] [rbp-D0h] BYREF
  BOOL pfVerificationFlagChecked; // [rsp+34h] [rbp-CCh] BYREF
  int pnRadioButton; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v43; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v44; // [rsp+48h] [rbp-B8h] BYREF
  struct tagOFNW v45; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR psz[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[1024]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v48[1024]; // [rsp+B00h] [rbp+A00h] BYREF
  _BYTE v49[2048]; // [rsp+1300h] [rbp+1200h] BYREF

  memset_0(&v45, 0, sizeof(v45));
  memset_0(v48, 0, sizeof(v48));
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v49, 0, sizeof(v49));
  memset_0(psz, 0, 0x208u);
  v4 = (*(_BYTE *)(a1 + 28) & 1) == 0;
  v5 = 0;
  pfVerificationFlagChecked = 0;
  v6 = 0;
  pnButton = 0;
  pnRadioButton = 0;
  v44 = 0;
  v43 = 0;
  if ( !v4 )
    return ContactXferMonitor(a1, a2);
  v8 = 0;
  v9 = a2 - 8;
  if ( !v9 )
  {
    *((_DWORD *)_AtlModule + 228) = 8;
    goto LABEL_50;
  }
  v10 = v9 - 2;
  if ( !v10 )
  {
    *((_DWORD *)_AtlModule + 228) = 8;
    return v8;
  }
  v11 = v10 - 2;
  if ( !v11 )
  {
    v15 = (TASKDIALOGCONFIG *)calloc(1u, 0xA0u);
    if ( !v15 )
    {
      v16 = 537;
LABEL_14:
      v8 = -2147024882;
      CEventLogger::LogError(
        v14,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
        v16,
        L"ReceiveFileClientCallback",
        0x8007000E);
LABEL_20:
      *((_DWORD *)_AtlModule + 228) = 14;
      if ( v15 )
        free(v15);
      goto LABEL_50;
    }
    *((_DWORD *)_AtlModule + 228) = 13;
    ModuleHandleW = GetModuleHandleW(0);
    if ( LoadStringW(ModuleHandleW, 0x266u, Buffer, 1024) )
    {
      v20 = (CRATicket *)*((_QWORD *)_AtlModule + 104);
      if ( *((_DWORD *)_AtlModule + 206) == 111 )
        CRATicket::get_ExpertName(v20, &v43);
      else
        CRATicket::get_NoviceName(v20, &v43);
      v6 = v43;
      v21 = StringCchPrintfW(v48, 0x400u, Buffer, v43);
      v8 = v21;
      if ( v21 < 0 )
      {
        CEventLogger::LogError(
          v22,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
          0x22Fu,
          L"ReceiveFileClientCallback",
          v21);
        goto LABEL_20;
      }
      v23 = _AtlModule;
      v15->cbSize = 160;
      v15->dwFlags = 2056;
      v15->dwCommonButtons = 6;
      v15->hwndParent = (HWND)*((_QWORD *)v23 + 101);
      v15->hInstance = (HINSTANCE)*((_QWORD *)v23 + 76);
      v15->pszMainInstruction = v48;
      v15->pfCallback = (PFTASKDIALOGCALLBACK)IncomingFileCallbackProc;
      v15->pszWindowTitle = (PCWSTR)612;
      v15->hMainIcon = 0;
      v15->pszContent = 0;
      v15->cButtons = 0;
      v15->pButtons = 0;
      v15->nDefaultButton = 4;
      v15->pszVerificationText = 0;
      v15->lpCallbackData = 0;
      v24 = TaskDialogIndirect(v15, &pnButton, &pnRadioButton, &pfVerificationFlagChecked);
      v8 = v24;
      if ( v24 < 0 )
      {
        CEventLogger::LogError(
          v25,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
          0x249u,
          L"ReceiveFileClientCallback",
          v24);
        goto LABEL_20;
      }
      if ( *((_DWORD *)_AtlModule + 228) == 8 || pnButton != 6 )
        goto LABEL_19;
      ExtensionW = PathFindExtensionW(*(LPCWSTR *)(a1 + 8));
      v27 = 2147483646;
      v28 = (const WCHAR *)((unsigned __int64)(ExtensionW + 1) & -(__int64)(*ExtensionW != 0));
      FileNameW = PathFindFileNameW(*(LPCWSTR *)(a1 + 8));
      v30 = 260;
      v31 = psz;
      do
      {
        if ( !v27 )
          break;
        if ( !*FileNameW )
          break;
        *v31++ = *FileNameW++;
        --v27;
        --v30;
      }
      while ( v30 );
      v32 = (CEventLogger *)(v31 - 1);
      v8 = v30 == 0 ? 0x8007007A : 0;
      if ( v30 )
        v32 = (CEventLogger *)v31;
      *(_WORD *)v32 = 0;
      if ( !v30 )
      {
        CEventLogger::LogError(
          v32,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
          0x271u,
          L"ReceiveFileClientCallback",
          v8);
        goto LABEL_20;
      }
      DirectoryAsBSTR = GetDirectoryAsBSTR(16, &v44, 0);
      v5 = v44;
      if ( DirectoryAsBSTR < 0 )
        goto LABEL_19;
      v45.lStructSize = 152;
      v34 = (HWND)*((_QWORD *)_AtlModule + 101);
      v45.lpstrFilter = (LPCWSTR)v49;
      v45.hwndOwner = v34;
      v45.lpstrFile = psz;
      v45.hInstance = 0;
      v45.lpstrCustomFilter = 0;
      *(_QWORD *)&v45.nMaxCustFilter = 0;
      v45.nMaxFile = 260;
      v45.lpstrFileTitle = 0;
      v45.nMaxFileTitle = 0;
      v45.lpstrInitialDir = v44;
      v45.lpstrTitle = 0;
      *(_QWORD *)&v45.Flags = 2;
      memset(&v45.lCustData, 0, 24);
      v45.lpstrDefExt = v28;
      if ( !GetSaveFileNameW(&v45) )
      {
LABEL_19:
        v8 = -2147467259;
        goto LABEL_20;
      }
      v35 = (OLECHAR *)*((_QWORD *)_AtlModule + 115);
      if ( v35 )
      {
        SysFreeString(v35);
        *((_QWORD *)_AtlModule + 115) = 0;
      }
      v36 = SysAllocString(psz);
      v37 = _AtlModule;
      *((_QWORD *)_AtlModule + 115) = v36;
      if ( !v36 )
      {
        v16 = 668;
        goto LABEL_14;
      }
      v38 = *(_QWORD *)(a1 + 16) + 1LL;
      *((_QWORD *)v37 + 118) = 0;
      *((_QWORD *)v37 + 117) = v38;
      memset_0(&v15->hInstance, 0, 0x94u);
      v15->cbSize = 160;
      v15->hwndParent = 0;
      v15->hInstance = (HINSTANCE)*((_QWORD *)v37 + 76);
      v15->dwFlags = 2568;
      v15->dwCommonButtons = 8;
      v15->pszWindowTitle = (PCWSTR)610;
      v15->hMainIcon = 0;
      v15->pszMainInstruction = (PCWSTR)*((_QWORD *)v37 + 115);
      v15->pfCallback = (PFTASKDIALOGCALLBACK)FileDialogProc;
      v15->pszContent = (PCWSTR)608;
      v15->cButtons = 0;
      v15->pButtons = 0;
      v15->pszVerificationText = 0;
      v15->lpCallbackData = 0;
      *((_DWORD *)v37 + 228) = 13;
      Thread = CreateThread(0, 0, ShowFileDialogThreadFunc, v15, 0, 0);
      if ( Thread )
      {
        CloseHandle(Thread);
        goto LABEL_50;
      }
      v19 = 705;
    }
    else
    {
      v19 = 547;
    }
    CEventLogger::LogError(
      v18,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
      v19,
      L"ReceiveFileClientCallback",
      0);
    goto LABEL_19;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 == 1 )
    {
      if ( MoveFileExW(*(LPCWSTR *)a1, *((LPCWSTR *)_AtlModule + 115), 3u) )
      {
        *((_DWORD *)_AtlModule + 228) = 14;
      }
      else
      {
        *((_DWORD *)_AtlModule + 228) = 7;
        CEventLogger::LogError(
          v13,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
          0x2E8u,
          L"ReceiveFileClientCallback",
          0);
      }
      return v8;
    }
LABEL_50:
    if ( v5 )
      SysFreeString(v5);
    if ( v6 )
      SysFreeString(v6);
    return v8;
  }
  *((_QWORD *)_AtlModule + 118) = *(_QWORD *)(a1 + 16);
  return v8;
}

```

## disassembly

```asm
0x14002ea50  push    rbp
0x14002ea52  push    rbx
0x14002ea53  push    rsi
0x14002ea54  push    rdi
0x14002ea55  push    r12
0x14002ea57  push    r13
0x14002ea59  push    r14
0x14002ea5b  push    r15
0x14002ea5d  lea     rbp, [rsp-1A18h]
0x14002ea65  mov     eax, 1B18h
0x14002ea6a  call    _alloca_probe
0x14002ea6f  sub     rsp, rax
0x14002ea72  mov     rax, cs:__security_cookie
0x14002ea79  xor     rax, rsp
0x14002ea7c  mov     [rbp+1A50h+var_50], rax
0x14002ea83  mov     edi, edx
0x14002ea85  mov     rsi, rcx
0x14002ea88  xor     edx, edx; Val
0x14002ea8a  lea     rcx, [rsp+1B50h+var_1B00]; void *
0x14002ea8f  mov     r8d, 98h; Size
0x14002ea95  call    memset_0
0x14002ea9a  mov     ebx, 800h
0x14002ea9f  lea     rcx, [rbp+1A50h+var_1050]; void *
0x14002eaa6  mov     r8d, ebx; Size
0x14002eaa9  xor     edx, edx; Val
0x14002eaab  call    memset_0
0x14002eab0  mov     r8d, ebx; Size
0x14002eab3  lea     rcx, [rbp+1A50h+Buffer]; void *
0x14002eaba  xor     edx, edx; Val
0x14002eabc  call    memset_0
0x14002eac1  mov     r8d, ebx; Size
0x14002eac4  lea     rcx, [rbp+1A50h+var_850]; void *
0x14002eacb  xor     edx, edx; Val
0x14002eacd  call    memset_0
0x14002ead2  xor     edx, edx; Val
0x14002ead4  lea     rcx, [rbp+1A50h+psz]; void *
0x14002ead8  mov     r8d, 208h; Size
0x14002eade  call    memset_0
0x14002eae3  xor     r13d, r13d
0x14002eae6  test    byte ptr [rsi+1Ch], 1
0x14002eaea  mov     r14d, r13d
0x14002eaed  mov     [rsp+1B50h+pfVerificationFlagChecked], r13d
0x14002eaf2  mov     r15d, r13d
0x14002eaf5  mov     [rsp+1B50h+pnButton], r13d
0x14002eafa  mov     [rsp+1B50h+pnRadioButton], r13d
0x14002eaff  mov     [rsp+1B50h+var_1B08], r13
0x14002eb04  mov     [rsp+1B50h+var_1B10], r13
0x14002eb09  jz      short loc_14002EB1A
0x14002eb0b  mov     edx, edi
0x14002eb0d  mov     rcx, rsi
0x14002eb10  call    ?ContactXferMonitor@@YAJPEAURA_FILE_RECV_CLIENT_CONTEXT@@W4RAFX_STATUS@@@Z; ContactXferMonitor(RA_FILE_RECV_CLIENT_CONTEXT *,RAFX_STATUS)
0x14002eb15  jmp     loc_14002F0A4
0x14002eb1a  mov     r12d, 8
0x14002eb20  mov     ebx, r13d
0x14002eb23  sub     edi, r12d
0x14002eb26  jz      loc_14002F06C
0x14002eb2c  sub     edi, 2
0x14002eb2f  jz      loc_14002F05C
0x14002eb35  sub     edi, 2
0x14002eb38  jz      loc_14002EBD8
0x14002eb3e  sub     edi, 1
0x14002eb41  jz      short loc_14002EBC1
0x14002eb43  cmp     edi, 1
0x14002eb46  jnz     loc_14002F07A
0x14002eb4c  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002eb53  lea     r8d, [r12-5]; dwFlags
0x14002eb58  mov     rcx, [rsi]; lpExistingFileName
0x14002eb5b  mov     rdx, [rdx+398h]; lpNewFileName
0x14002eb62  call    cs:__imp_MoveFileExW
0x14002eb69  nop     dword ptr [rax+rax+00h]
0x14002eb6e  test    eax, eax
0x14002eb70  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002eb77  jnz     short loc_14002EBB2
0x14002eb79  mov     dword ptr [rax+390h], 7
0x14002eb83  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\ui\\filexfer.cpp"
0x14002eb8a  lea     rax, aReceivefilecli; "ReceiveFileClientCallback"
0x14002eb91  mov     dword ptr [rsp+1B50h+lpThreadId], r13d; unsigned int
0x14002eb96  mov     r9d, 2E8h; unsigned int
0x14002eb9c  mov     qword ptr [rsp+1B50h+dwCreationFlags], rax; unsigned __int16 *
0x14002eba1  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002eba8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002ebad  jmp     loc_14002F0A2
0x14002ebb2  mov     dword ptr [rax+390h], 0Eh
0x14002ebbc  jmp     loc_14002F0A2
0x14002ebc1  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002ebc8  mov     rcx, [rsi+10h]
0x14002ebcc  mov     [rax+3B0h], rcx
0x14002ebd3  jmp     loc_14002F0A2
0x14002ebd8  mov     edx, 0A0h; Size
0x14002ebdd  mov     ecx, 1; Count
0x14002ebe2  call    cs:__imp_calloc
0x14002ebe9  nop     dword ptr [rax+rax+00h]
0x14002ebee  mov     rdi, rax
0x14002ebf1  test    rax, rax
0x14002ebf4  jnz     short loc_14002EC2A
0x14002ebf6  mov     r9d, 219h; unsigned int
0x14002ebfc  mov     dword ptr [rsp+1B50h+lpThreadId], 8007000Eh; unsigned int
0x14002ec04  mov     ebx, 8007000Eh
0x14002ec09  lea     rax, aReceivefilecli; "ReceiveFileClientCallback"
0x14002ec10  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\ui\\filexfer.cpp"
0x14002ec17  mov     qword ptr [rsp+1B50h+dwCreationFlags], rax; unsigned __int16 *
0x14002ec1c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002ec23  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002ec28  jmp     short loc_14002EC9F
0x14002ec2a  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002ec31  xor     ecx, ecx; lpModuleName
0x14002ec33  mov     dword ptr [rax+390h], 0Dh
0x14002ec3d  call    cs:__imp_GetModuleHandleW
0x14002ec44  nop     dword ptr [rax+rax+00h]
0x14002ec49  mov     ebx, 400h
0x14002ec4e  lea     r8, [rbp+1A50h+Buffer]; lpBuffer
0x14002ec55  mov     rcx, rax; hInstance
0x14002ec58  mov     r9d, ebx; cchBufferMax
0x14002ec5b  mov     edx, 266h; uID
0x14002ec60  call    cs:__imp_LoadStringW
0x14002ec67  nop     dword ptr [rax+rax+00h]
0x14002ec6c  test    eax, eax
0x14002ec6e  jnz     short loc_14002ECCD
0x14002ec70  mov     r9d, 223h; unsigned int
0x14002ec76  lea     rax, aReceivefilecli; "ReceiveFileClientCallback"
0x14002ec7d  mov     dword ptr [rsp+1B50h+lpThreadId], r13d; unsigned int
0x14002ec82  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\ui\\filexfer.cpp"
0x14002ec89  mov     qword ptr [rsp+1B50h+dwCreationFlags], rax; unsigned __int16 *
0x14002ec8e  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002ec95  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002ec9a  mov     ebx, 80004005h
0x14002ec9f  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002eca6  mov     dword ptr [rax+390h], 0Eh
0x14002ecb0  test    rdi, rdi
0x14002ecb3  jz      loc_14002F07A
0x14002ecb9  mov     rcx, rdi; Block
0x14002ecbc  call    cs:__imp_free
0x14002ecc3  nop     dword ptr [rax+rax+00h]
0x14002ecc8  jmp     loc_14002F07A
0x14002eccd  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002ecd4  lea     rdx, [rsp+1B50h+var_1B10]; unsigned __int16 **
0x14002ecd9  cmp     dword ptr [rcx+338h], 6Fh ; 'o'
0x14002ece0  mov     rcx, [rcx+340h]; this
0x14002ece7  jnz     short loc_14002ECF0
0x14002ece9  call    ?get_ExpertName@CRATicket@@QEAAJPEAPEAG@Z; CRATicket::get_ExpertName(ushort * *)
0x14002ecee  jmp     short loc_14002ECF5
0x14002ecf0  call    ?get_NoviceName@CRATicket@@QEAAJPEAPEAG@Z; CRATicket::get_NoviceName(ushort * *)
0x14002ecf5  mov     r15, [rsp+1B50h+var_1B10]
0x14002ecfa  lea     r8, [rbp+1A50h+Buffer]; unsigned __int16 *
0x14002ed01  mov     r9, r15
0x14002ed04  lea     rcx, [rbp+1A50h+var_1050]; unsigned __int16 *
0x14002ed0b  mov     rdx, rbx; unsigned __int64
0x14002ed0e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002ed13  mov     ebx, eax
0x14002ed15  test    eax, eax
0x14002ed17  jns     short loc_14002ED28
0x14002ed19  mov     dword ptr [rsp+1B50h+lpThreadId], eax
0x14002ed1d  mov     r9d, 22Fh
0x14002ed23  jmp     loc_14002EC09
0x14002ed28  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002ed2f  lea     r9, [rsp+1B50h+pfVerificationFlagChecked]; pfVerificationFlagChecked
0x14002ed34  lea     r8, [rsp+1B50h+pnRadioButton]; pnRadioButton
0x14002ed39  mov     dword ptr [rdi], 0A0h
0x14002ed3f  lea     rdx, [rsp+1B50h+pnButton]; pnButton
0x14002ed44  mov     dword ptr [rdi+14h], 808h
0x14002ed4b  mov     dword ptr [rdi+18h], 6
0x14002ed52  mov     rax, [rcx+328h]
0x14002ed59  mov     [rdi+4], rax
0x14002ed5d  mov     rax, [rcx+260h]
0x14002ed64  mov     rcx, rdi; pTaskConfig
0x14002ed67  mov     [rdi+0Ch], rax
0x14002ed6b  lea     rax, [rbp+1A50h+var_1050]
0x14002ed72  mov     [rdi+2Ch], rax
0x14002ed76  lea     rax, ?IncomingFileCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z; IncomingFileCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x14002ed7d  mov     [rdi+8Ch], rax
0x14002ed84  mov     qword ptr [rdi+1Ch], 264h
0x14002ed8c  mov     [rdi+24h], r13
0x14002ed90  mov     [rdi+34h], r13
0x14002ed94  mov     [rdi+3Ch], r13d
0x14002ed98  mov     [rdi+40h], r13
0x14002ed9c  mov     dword ptr [rdi+48h], 4
0x14002eda3  mov     [rdi+5Ch], r13
0x14002eda7  mov     [rdi+94h], r13
0x14002edae  call    cs:__imp_TaskDialogIndirect
0x14002edb5  nop     dword ptr [rax+rax+00h]
0x14002edba  mov     ebx, eax
0x14002edbc  test    eax, eax
0x14002edbe  jns     short loc_14002EDCF
0x14002edc0  mov     dword ptr [rsp+1B50h+lpThreadId], eax
0x14002edc4  mov     r9d, 249h
0x14002edca  jmp     loc_14002EC09
0x14002edcf  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002edd6  cmp     [rax+390h], r12d
0x14002eddd  jz      loc_14002EC9A
0x14002ede3  cmp     [rsp+1B50h+pnButton], 6
0x14002ede8  jnz     loc_14002EC9A
0x14002edee  mov     rcx, [rsi+8]; pszPath
0x14002edf2  call    cs:__imp_PathFindExtensionW
0x14002edf9  nop     dword ptr [rax+rax+00h]
0x14002edfe  mov     ebx, 7FFFFFFEh
0x14002ee03  movzx   ecx, word ptr [rax]
0x14002ee06  add     rax, 2
0x14002ee0a  neg     cx
0x14002ee0d  mov     rcx, [rsi+8]; pszPath
0x14002ee11  sbb     r12, r12
0x14002ee14  and     r12, rax
0x14002ee17  call    cs:__imp_PathFindFileNameW
0x14002ee1e  nop     dword ptr [rax+rax+00h]
0x14002ee23  mov     edx, 104h
0x14002ee28  lea     r8, [rbp+1A50h+psz]
0x14002ee2c  test    rbx, rbx
0x14002ee2f  jz      short loc_14002EE4E
0x14002ee31  movzx   ecx, word ptr [rax]
0x14002ee34  test    cx, cx
0x14002ee37  jz      short loc_14002EE4E
0x14002ee39  mov     [r8], cx
0x14002ee3d  add     rax, 2
0x14002ee41  add     r8, 2
0x14002ee45  dec     rbx
0x14002ee48  sub     rdx, 1
0x14002ee4c  jnz     short loc_14002EE2C
0x14002ee4e  mov     rax, rdx
0x14002ee51  lea     rcx, [r8-2]
0x14002ee55  neg     rax
0x14002ee58  sbb     ebx, ebx
0x14002ee5a  not     ebx
0x14002ee5c  and     ebx, 8007007Ah
0x14002ee62  test    rdx, rdx
0x14002ee65  cmovnz  rcx, r8
0x14002ee69  mov     [rcx], r13w
0x14002ee6d  jnz     short loc_14002EE7E
0x14002ee6f  mov     dword ptr [rsp+1B50h+lpThreadId], ebx
0x14002ee73  mov     r9d, 271h
0x14002ee79  jmp     loc_14002EC09
0x14002ee7e  xor     r8d, r8d; unsigned __int16 *
0x14002ee81  lea     rdx, [rsp+1B50h+var_1B08]; unsigned __int16 **
0x14002ee86  lea     ecx, [r8+10h]; csidl
0x14002ee8a  call    ?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z; GetDirectoryAsBSTR(int,ushort * *,ushort *)
0x14002ee8f  mov     r14, [rsp+1B50h+var_1B08]
0x14002ee94  test    eax, eax
0x14002ee96  js      loc_14002EC9A
0x14002ee9c  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002eea3  mov     [rsp+1B50h+var_1B00.lStructSize], 98h
0x14002eeab  mov     rcx, [rax+328h]
0x14002eeb2  lea     rax, [rbp+1A50h+var_850]
0x14002eeb9  mov     [rsp+1B50h+var_1B00.lpstrFilter], rax
0x14002eebe  lea     rax, [rbp+1A50h+psz]
0x14002eec2  mov     [rsp+1B50h+var_1B00.hwndOwner], rcx
0x14002eec7  lea     rcx, [rsp+1B50h+var_1B00]; LPOPENFILENAMEW
0x14002eecc  mov     [rbp+1A50h+var_1B00.lpstrFile], rax
0x14002eed0  mov     [rsp+1B50h+var_1B00.hInstance], r13
0x14002eed5  mov     [rsp+1B50h+var_1B00.lpstrCustomFilter], r13
0x14002eeda  mov     qword ptr [rsp+1B50h+var_1B00.nMaxCustFilter], r13
0x14002eedf  mov     [rbp+1A50h+var_1B00.nMaxFile], 104h
0x14002eee6  mov     [rbp+1A50h+var_1B00.lpstrFileTitle], r13
0x14002eeea  mov     [rbp+1A50h+var_1B00.nMaxFileTitle], r13d
0x14002eeee  mov     [rbp+1A50h+var_1B00.lpstrInitialDir], r14
0x14002eef2  mov     [rbp+1A50h+var_1B00.lpstrTitle], r13
0x14002eef6  mov     qword ptr [rbp+1A50h+var_1B00.Flags], 2
0x14002eefe  mov     [rbp+1A50h+var_1B00.lCustData], r13
0x14002ef02  mov     [rbp+1A50h+var_1B00.lpfnHook], r13
0x14002ef06  mov     [rbp+1A50h+var_1B00.lpTemplateName], r13
0x14002ef0a  mov     [rbp+1A50h+var_1B00.lpstrDefExt], r12
0x14002ef0e  call    cs:__imp_GetSaveFileNameW
0x14002ef15  nop     dword ptr [rax+rax+00h]
0x14002ef1a  test    eax, eax
0x14002ef1c  jz      loc_14002EC9A
0x14002ef22  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002ef29  mov     rcx, [rax+398h]; bstrString
0x14002ef30  test    rcx, rcx
0x14002ef33  jz      short loc_14002EF4F
0x14002ef35  call    cs:__imp_SysFreeString
0x14002ef3c  nop     dword ptr [rax+rax+00h]
0x14002ef41  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002ef48  mov     [rax+398h], r13
0x14002ef4f  lea     rcx, [rbp+1A50h+psz]; psz
0x14002ef53  call    cs:__imp_SysAllocString
0x14002ef5a  nop     dword ptr [rax+rax+00h]
0x14002ef5f  mov     r13, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002ef66  xor     r12d, r12d
0x14002ef69  mov     [r13+398h], rax
0x14002ef70  test    rax, rax
0x14002ef73  jnz     short loc_14002EF80
0x14002ef75  mov     r9d, 29Ch
0x14002ef7b  jmp     loc_14002EBFC
0x14002ef80  mov     rax, [rsi+10h]
0x14002ef84  lea     rcx, [rdi+0Ch]; void *
0x14002ef88  inc     rax
0x14002ef8b  mov     [r13+3B0h], r12
0x14002ef92  xor     edx, edx; Val
0x14002ef94  mov     [r13+3A8h], rax
0x14002ef9b  mov     r8d, 94h; Size
0x14002efa1  call    memset_0
0x14002efa6  mov     dword ptr [rdi], 0A0h
0x14002efac  lea     r8, ?ShowFileDialogThreadFunc@@YAKPEAX@Z; lpStartAddress
0x14002efb3  mov     [rdi+4], r12
0x14002efb7  mov     r9, rdi; lpParameter
0x14002efba  mov     rax, [r13+260h]
0x14002efc1  xor     edx, edx; dwStackSize
0x14002efc3  mov     [rdi+0Ch], rax
0x14002efc7  xor     ecx, ecx; lpThreadAttributes
0x14002efc9  mov     dword ptr [rdi+14h], 0A08h
0x14002efd0  mov     dword ptr [rdi+18h], 8
0x14002efd7  mov     qword ptr [rdi+1Ch], 262h
0x14002efdf  mov     [rdi+24h], r12
  ... truncated ...
```
