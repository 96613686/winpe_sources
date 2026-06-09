# ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)

- ea: `0x14002c0a4`
- end: `0x14002c3af`
- name: `?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z`
- size: `779`
- prototype: `__int64 __fastcall(int, int, HWND, int, const unsigned __int16 *, int)`
- caller_count: `31`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000e8b8`
- `0x14000fcb4`
- `0x140012794`
- `0x140013f4c`
- `0x140014574`
- `0x1400146cc`
- `0x1400194c8`
- `0x14001bd94`
- `0x14001c340`
- `0x14001c458`
- `0x14001d1ac`
- `0x14001d28c`
- `0x14001da70`
- `0x14001db80`
- `0x14002090c`
- `0x140021bb0`
- `0x140021d04`
- `0x140021e00`
- `0x1400223c4`
- `0x140026270`
- `0x140028a7c`
- `0x14002a6bc`
- `0x14002c670`
- `0x14002e450`
- `0x14003175c`
- `0x140031a2c`
- `0x140031adc`
- `0x140031e8c`
- `0x140032274`
- `0x140032f7c`
- `0x140034200`

## callees

- `0x140002463`
- `0x140026874`
- `0x14002c0a4`
- `0x14003500c`
- `0x140035888`
- `0x140037e08`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14002c1fe`
- `KERNEL32!LoadLibraryExW` at `0x14002c1fe`
- `KERNEL32!FreeLibrary` at `0x14002c2af`
- `KERNEL32!FreeLibrary` at `0x14002c2af`
- `KERNEL32!GetModuleHandleW` at `0x14002c187`
- `KERNEL32!GetModuleHandleW` at `0x14002c30c`
- `KERNEL32!GetModuleHandleW` at `0x14002c187`
- `KERNEL32!GetModuleHandleW` at `0x14002c30c`
- `KERNEL32!FormatMessageW` at `0x14002c235`
- `KERNEL32!FormatMessageW` at `0x14002c26d`
- `KERNEL32!FormatMessageW` at `0x14002c235`
- `KERNEL32!FormatMessageW` at `0x14002c26d`
- `USER32!LoadStringW` at `0x14002c1a6`
- `USER32!LoadStringW` at `0x14002c1a6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c2c3`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c2c3`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002c37b`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002c37b`

## string_xrefs

- `0x14002c1d1`: `rdpsharercom.dll`

## pseudocode

```c
__int64 __fastcall ShowErrorMessage(
        unsigned int a1,
        unsigned __int16 a2,
        HWND a3,
        signed int a4,
        unsigned __int16 *a5,
        int a6)
{
  HICON v6; // rdi
  LPCWSTR v11; // r14
  unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  HMODULE ModuleHandleW; // rax
  CEventLogger *v15; // rcx
  OLECHAR *v16; // rdi
  HMODULE Library; // rbx
  TASKDIALOG_FLAGS v18; // ebx
  HMODULE v19; // rax
  LPCWSTR lpLibFileName; // [rsp+40h] [rbp-C0h] BYREF
  BOOL pfVerificationFlagChecked; // [rsp+48h] [rbp-B8h] BYREF
  int pnRadioButton; // [rsp+4Ch] [rbp-B4h] BYREF
  int pnButton; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v25; // [rsp+58h] [rbp-A8h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR lpBuffer[1024]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Buffer[1024]; // [rsp+900h] [rbp+800h] BYREF

  v6 = (HICON)a5;
  v25 = a5;
  memset_0(Buffer, 0, sizeof(Buffer));
  pfVerificationFlagChecked = 0;
  pnRadioButton = 0;
  pnButton = 0;
  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  memset_0(lpBuffer, 0, sizeof(lpBuffer));
  v11 = 0;
  lpLibFileName = 0;
  CSqmManager::RecordError((CEventLogger *)((char *)_AtlModule + 496), a1, a4);
  if ( !a3 && a1 == 549 )
  {
    v13 = 0;
    if ( !(unsigned int)CreateOrPulseEvent((void **)&lpLibFileName, v12) )
      return v13;
    v11 = lpLibFileName;
  }
  ModuleHandleW = GetModuleHandleW(0);
  if ( LoadStringW(ModuleHandleW, a1, Buffer, 1024) )
    CEventLogger::LogEvent(v15, &Error_Message_Displayed, Buffer);
  if ( a4 < 0 )
  {
    lpLibFileName = 0;
    GetDirectoryAsBSTR(37, (unsigned __int16 **)&lpLibFileName, L"rdpsharercom.dll");
    v16 = (OLECHAR *)lpLibFileName;
    Library = LoadLibraryExW(lpLibFileName, 0, 0x20u);
    if ( FormatMessageW(0xA00u, Library, a4, 0x400u, lpBuffer, 0x400u, 0)
      || FormatMessageW(0x1200u, 0, a4, 0x400u, lpBuffer, 0x400u, 0) )
    {
      pTaskConfig.pszExpandedControlText = (PCWSTR)553;
      pTaskConfig.pszExpandedInformation = lpBuffer;
      pTaskConfig.pszCollapsedControlText = (PCWSTR)552;
    }
    else
    {
      memset(&pTaskConfig.pszExpandedInformation, 0, 24);
    }
    if ( Library )
      FreeLibrary(Library);
    if ( v16 )
      SysFreeString(v16);
    v6 = (HICON)v25;
  }
  v18 = v11 != 0 ? 2120 : 72;
  if ( a6 )
  {
    v18 |= 1u;
    pTaskConfig.pszFooter = (PCWSTR)(unsigned __int16)a6;
  }
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = a3;
  v19 = GetModuleHandleW(0);
  pTaskConfig.dwFlags = v18;
  pTaskConfig.hInstance = v19;
  pTaskConfig.pszMainInstruction = (PCWSTR)a2;
  pTaskConfig.pszContent = (PCWSTR)(unsigned __int16)a1;
  pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)ErrorDialogCallback;
  pTaskConfig.dwCommonButtons = 1;
  pTaskConfig.pszWindowTitle = (PCWSTR)100;
  pTaskConfig.hMainIcon = v6;
  pTaskConfig.cButtons = 0;
  pTaskConfig.pButtons = 0;
  pTaskConfig.nDefaultButton = 0;
  pTaskConfig.pszVerificationText = 0;
  pTaskConfig.hFooterIcon = 0;
  pTaskConfig.lpCallbackData = (LONG_PTR)v11;
  return (unsigned int)TaskDialogIndirect(&pTaskConfig, &pnButton, &pnRadioButton, &pfVerificationFlagChecked);
}

```

## disassembly

```asm
0x14002c0a4  push    rbp
0x14002c0a6  push    rbx
0x14002c0a7  push    rsi
0x14002c0a8  push    rdi
0x14002c0a9  push    r12
0x14002c0ab  push    r13
0x14002c0ad  push    r14
0x14002c0af  push    r15
0x14002c0b1  lea     rbp, [rsp-1018h]
0x14002c0b9  mov     eax, 1118h
0x14002c0be  call    _alloca_probe
0x14002c0c3  sub     rsp, rax
0x14002c0c6  mov     rax, cs:__security_cookie
0x14002c0cd  xor     rax, rsp
0x14002c0d0  mov     [rbp+1050h+var_50], rax
0x14002c0d7  mov     rdi, [rbp+1050h+arg_20]
0x14002c0de  mov     r12, r8
0x14002c0e1  mov     r13d, edx
0x14002c0e4  mov     ebx, 800h
0x14002c0e9  mov     r15d, ecx
0x14002c0ec  mov     r8d, ebx; Size
0x14002c0ef  xor     edx, edx; Val
0x14002c0f1  mov     [rsp+1150h+var_10F8], rdi
0x14002c0f6  lea     rcx, [rbp+1050h+Buffer]; void *
0x14002c0fd  mov     esi, r9d
0x14002c100  call    memset_0
0x14002c105  xor     edx, edx; Val
0x14002c107  mov     [rsp+1150h+pfVerificationFlagChecked], 0
0x14002c10f  mov     r8d, 0A0h; Size
0x14002c115  mov     [rsp+1150h+pnRadioButton], 0
0x14002c11d  lea     rcx, [rsp+1150h+pTaskConfig]; void *
0x14002c122  mov     [rsp+1150h+pnButton], 0
0x14002c12a  call    memset_0
0x14002c12f  mov     r8d, ebx; Size
0x14002c132  lea     rcx, [rbp+1050h+var_1050]; void *
0x14002c136  xor     edx, edx; Val
0x14002c138  call    memset_0
0x14002c13d  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002c144  xor     r14d, r14d
0x14002c147  add     rcx, 1F0h; this
0x14002c14e  mov     [rsp+1150h+lpLibFileName], r14
0x14002c153  mov     r8d, esi; unsigned int
0x14002c156  mov     edx, r15d; unsigned int
0x14002c159  call    ?RecordError@CSqmManager@@QEAAXKK@Z; CSqmManager::RecordError(ulong,ulong)
0x14002c15e  test    r12, r12
0x14002c161  jnz     short loc_14002C185
0x14002c163  cmp     r15d, 225h
0x14002c16a  jnz     short loc_14002C185
0x14002c16c  lea     rcx, [rsp+1150h+lpLibFileName]; void **
0x14002c171  xor     ebx, ebx
0x14002c173  call    ?CreateOrPulseEvent@@YAHPEAPEAXPEAG@Z; CreateOrPulseEvent(void * *,ushort *)
0x14002c178  test    eax, eax
0x14002c17a  jz      loc_14002C389
0x14002c180  mov     r14, [rsp+1150h+lpLibFileName]
0x14002c185  xor     ecx, ecx; lpModuleName
0x14002c187  call    cs:__imp_GetModuleHandleW
0x14002c18e  nop     dword ptr [rax+rax+00h]
0x14002c193  mov     r9d, 400h; cchBufferMax
0x14002c199  lea     r8, [rbp+1050h+Buffer]; lpBuffer
0x14002c1a0  mov     rcx, rax; hInstance
0x14002c1a3  mov     edx, r15d; uID
0x14002c1a6  call    cs:__imp_LoadStringW
0x14002c1ad  nop     dword ptr [rax+rax+00h]
0x14002c1b2  test    eax, eax
0x14002c1b4  jz      short loc_14002C1C9
0x14002c1b6  lea     r8, [rbp+1050h+Buffer]; unsigned __int16 *
0x14002c1bd  lea     rdx, Error_Message_Displayed; struct _EVENT_DESCRIPTOR *
0x14002c1c4  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x14002c1c9  test    esi, esi
0x14002c1cb  jns     loc_14002C2D6
0x14002c1d1  lea     r8, aRdpsharercomDl; "rdpsharercom.dll"
0x14002c1d8  mov     [rsp+1150h+lpLibFileName], 0
0x14002c1e1  lea     rdx, [rsp+1150h+lpLibFileName]; unsigned __int16 **
0x14002c1e6  mov     ecx, 25h ; '%'; csidl
0x14002c1eb  call    ?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z; GetDirectoryAsBSTR(int,ushort * *,ushort *)
0x14002c1f0  mov     rdi, [rsp+1150h+lpLibFileName]
0x14002c1f5  xor     edx, edx; hFile
0x14002c1f7  mov     rcx, rdi; lpLibFileName
0x14002c1fa  lea     r8d, [rdx+20h]; dwFlags
0x14002c1fe  call    cs:__imp_LoadLibraryExW
0x14002c205  nop     dword ptr [rax+rax+00h]
0x14002c20a  mov     r9d, 400h; dwLanguageId
0x14002c210  mov     [rsp+1150h+Arguments], 0; Arguments
0x14002c219  mov     rbx, rax
0x14002c21c  mov     [rsp+1150h+nSize], r9d; nSize
0x14002c221  lea     rax, [rbp+1050h+var_1050]
0x14002c225  mov     rdx, rbx; lpSource
0x14002c228  mov     r8d, esi; dwMessageId
0x14002c22b  mov     [rsp+1150h+lpBuffer], rax; lpBuffer
0x14002c230  mov     ecx, 0A00h; dwFlags
0x14002c235  call    cs:__imp_FormatMessageW
0x14002c23c  nop     dword ptr [rax+rax+00h]
0x14002c241  test    eax, eax
0x14002c243  jnz     short loc_14002C28D
0x14002c245  mov     ecx, 400h
0x14002c24a  mov     [rsp+1150h+Arguments], 0; Arguments
0x14002c253  mov     [rsp+1150h+nSize], ecx; nSize
0x14002c257  lea     rax, [rbp+1050h+var_1050]
0x14002c25b  mov     r9d, ecx; dwLanguageId
0x14002c25e  mov     [rsp+1150h+lpBuffer], rax; lpBuffer
0x14002c263  mov     ecx, 1200h; dwFlags
0x14002c268  mov     r8d, esi; dwMessageId
0x14002c26b  xor     edx, edx; lpSource
0x14002c26d  call    cs:__imp_FormatMessageW
0x14002c274  nop     dword ptr [rax+rax+00h]
0x14002c279  xor     esi, esi
0x14002c27b  test    eax, eax
0x14002c27d  jnz     short loc_14002C28F
0x14002c27f  mov     [rbp+1050h+pTaskConfig.pszExpandedInformation], rsi
0x14002c283  mov     [rbp+1050h+pTaskConfig.pszExpandedControlText], rsi
0x14002c287  mov     [rbp+1050h+pTaskConfig.pszCollapsedControlText], rsi
0x14002c28b  jmp     short loc_14002C2A7
0x14002c28d  xor     esi, esi
0x14002c28f  lea     rax, [rbp+1050h+var_1050]
0x14002c293  mov     [rbp+1050h+pTaskConfig.pszExpandedControlText], 229h
0x14002c29b  mov     [rbp+1050h+pTaskConfig.pszExpandedInformation], rax
0x14002c29f  mov     [rbp+1050h+pTaskConfig.pszCollapsedControlText], 228h
0x14002c2a7  test    rbx, rbx
0x14002c2aa  jz      short loc_14002C2BB
0x14002c2ac  mov     rcx, rbx; hLibModule
0x14002c2af  call    cs:__imp_FreeLibrary
0x14002c2b6  nop     dword ptr [rax+rax+00h]
0x14002c2bb  test    rdi, rdi
0x14002c2be  jz      short loc_14002C2CF
0x14002c2c0  mov     rcx, rdi; bstrString
0x14002c2c3  call    cs:__imp_SysFreeString
0x14002c2ca  nop     dword ptr [rax+rax+00h]
0x14002c2cf  mov     rdi, [rsp+1150h+var_10F8]
0x14002c2d4  jmp     short loc_14002C2D8
0x14002c2d6  xor     esi, esi
0x14002c2d8  mov     rax, r14
0x14002c2db  neg     rax
0x14002c2de  mov     eax, [rbp+1050h+arg_28]
0x14002c2e4  sbb     ebx, ebx
0x14002c2e6  and     ebx, 800h
0x14002c2ec  add     ebx, 48h ; 'H'
0x14002c2ef  test    eax, eax
0x14002c2f1  jz      short loc_14002C2FD
0x14002c2f3  movzx   eax, ax
0x14002c2f6  or      ebx, 1
0x14002c2f9  mov     [rbp+1050h+pTaskConfig.pszFooter], rax
0x14002c2fd  xor     ecx, ecx; lpModuleName
0x14002c2ff  mov     [rsp+1150h+pTaskConfig.cbSize], 0A0h
0x14002c307  mov     [rsp+1150h+pTaskConfig.hwndParent], r12
0x14002c30c  call    cs:__imp_GetModuleHandleW
0x14002c313  nop     dword ptr [rax+rax+00h]
0x14002c318  lea     r9, [rsp+1150h+pfVerificationFlagChecked]; pfVerificationFlagChecked
0x14002c31d  mov     [rsp+1150h+pTaskConfig.dwFlags], ebx
0x14002c321  mov     [rsp+1150h+pTaskConfig.hInstance], rax
0x14002c326  lea     r8, [rsp+1150h+pnRadioButton]; pnRadioButton
0x14002c32b  movzx   eax, r13w
0x14002c32f  lea     rdx, [rsp+1150h+pnButton]; pnButton
0x14002c334  mov     [rbp+1050h+pTaskConfig.pszMainInstruction], rax
0x14002c338  lea     rcx, [rsp+1150h+pTaskConfig]; pTaskConfig
0x14002c33d  movzx   eax, r15w
0x14002c341  mov     [rbp+1050h+pTaskConfig.pszContent], rax
0x14002c345  lea     rax, ?ErrorDialogCallback@@YAJPEAUHWND__@@I_K_J2@Z; ErrorDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x14002c34c  mov     [rbp+1050h+pTaskConfig.pfCallback], rax
0x14002c350  mov     [rsp+1150h+pTaskConfig.dwCommonButtons], 1
0x14002c358  mov     [rsp+1150h+pTaskConfig.pszWindowTitle], 64h ; 'd'
0x14002c361  mov     qword ptr [rbp+1050h+pTaskConfig.24h], rdi
0x14002c365  mov     [rbp+1050h+pTaskConfig.cButtons], esi
0x14002c368  mov     [rbp+1050h+pTaskConfig.pButtons], rsi
0x14002c36c  mov     [rbp+1050h+pTaskConfig.nDefaultButton], esi
0x14002c36f  mov     [rbp+1050h+pTaskConfig.pszVerificationText], rsi
0x14002c373  mov     qword ptr [rbp+1050h+pTaskConfig.7Ch], rsi
0x14002c377  mov     [rbp+1050h+pTaskConfig.lpCallbackData], r14
0x14002c37b  call    cs:__imp_TaskDialogIndirect
0x14002c382  nop     dword ptr [rax+rax+00h]
0x14002c387  mov     ebx, eax
0x14002c389  mov     eax, ebx
0x14002c38b  mov     rcx, [rbp+1050h+var_50]
0x14002c392  xor     rcx, rsp; StackCookie
0x14002c395  call    __security_check_cookie
0x14002c39a  add     rsp, 1118h
0x14002c3a1  pop     r15
0x14002c3a3  pop     r14
0x14002c3a5  pop     r13
0x14002c3a7  pop     r12
0x14002c3a9  pop     rdi
0x14002c3aa  pop     rsi
0x14002c3ab  pop     rbx
0x14002c3ac  pop     rbp
0x14002c3ad  retn
```
