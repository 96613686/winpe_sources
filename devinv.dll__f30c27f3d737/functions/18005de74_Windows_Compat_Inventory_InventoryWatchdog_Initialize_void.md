# Windows::Compat::Inventory::InventoryWatchdog::Initialize(void)

- ea: `0x18005de74`
- end: `0x18005e0cf`
- name: `?Initialize@InventoryWatchdog@Inventory@Compat@Windows@@QEAAJXZ`
- size: `603`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005d038`

## callees

- `0x18000d164`
- `0x18000d184`
- `0x18005de74`
- `0x18005fee8`
- `0x180060294`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e0be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e0be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005de8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005de8b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005dea9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005e03b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005dea9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005e03b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dfd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dfd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dfbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dfeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e04c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dfbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dfeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e04c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e073`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005dfa5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005dfa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005dfca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005dfca`

## string_xrefs

- `0x18005ded0`: `CreateEvent failed [%#x]`
- `0x18005df0a`: `CreateEvent failed [%#x]`
- `0x18005df44`: `CreateEvent failed [%#x]`
- `0x18005dedd`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18005df17`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18005df51`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18005e002`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18005e063`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18005e08e`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18005df6e`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x18005e017`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x18005dff5`: `CreateThread failed [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::InventoryWatchdog::Initialize(
        Windows::Compat::Inventory::InventoryWatchdog *this)
{
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  DWORD v2; // ebx
  __int64 v3; // rdx
  int v4; // eax
  int v5; // eax
  HANDLE Thread; // rdi
  HANDLE v7; // rsi
  DWORD LastError; // ebx
  DWORD v9; // eax
  const char *v10; // r9
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  AcquireSRWLockExclusive(&stru_180156A88);
  if ( (char *)qword_180156A90 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && WaitForSingleObject(qword_180156A90, 0) == 258 )
    goto LABEL_20;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&qword_180156A98);
  v2 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      78,
      "CreateEvent failed [%#x]",
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
    v3 = 79;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
      (const char *)v2,
      dwCreationFlags);
    goto LABEL_21;
  }
  v4 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&qword_180156AA0);
  v2 = v4;
  if ( v4 < 0 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Initialize", 85, "CreateEvent failed [%#x]", v4);
    v3 = 86;
    goto LABEL_9;
  }
  v5 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&qword_180156AA8);
  v2 = v5;
  if ( v5 < 0 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Initialize", 92, "CreateEvent failed [%#x]", v5);
    v3 = 93;
    goto LABEL_9;
  }
  Thread = CreateThread(0, 1u, Windows::Compat::Inventory::InventoryWatchdog::ThreadProc, &dword_180156A70, 0, 0);
  v7 = qword_180156A90;
  if ( (char *)qword_180156A90 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v7);
    SetLastError(LastError);
  }
  qword_180156A90 = Thread;
  if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v9 = GetLastError();
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Initialize", 99, "CreateThread failed [%d]", v9);
    v2 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x64,
           (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
           v10);
    goto LABEL_21;
  }
  v11 = WaitForSingleObject(qword_180156AA8, 0x2710u);
  v2 = v11;
  if ( !v11 )
  {
LABEL_20:
    v2 = 0;
    goto LABEL_21;
  }
  if ( v11 == -1 )
  {
    v12 = GetLastError();
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      108,
      "WaitForSingleObject failed [%d]",
      v12);
    v2 = GetLastError();
  }
  else
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      113,
      "WaitForSingleObject returned [%d]",
      v11);
  }
  Windows::Compat::Inventory::InventoryWatchdog::Stop((Windows::Compat::Inventory::InventoryWatchdog *)&dword_180156A70);
  if ( (int)v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
LABEL_21:
  ReleaseSRWLockExclusive(&stru_180156A88);
  return v2;
}

```

## disassembly

```asm
0x18005de74  mov     [rsp+arg_0], rcx
0x18005de79  push    rbx
0x18005de7a  push    rbp
0x18005de7b  push    rsi
0x18005de7c  push    rdi
0x18005de7d  sub     rsp, 38h
0x18005de81  lea     rbp, stru_180156A88
0x18005de88  mov     rcx, rbp; SRWLock
0x18005de8b  call    cs:__imp_AcquireSRWLockExclusive
0x18005de91  mov     [rsp+58h+arg_0], rbp
0x18005de96  mov     rcx, cs:qword_180156A90; hHandle
0x18005de9d  lea     rax, [rcx-1]
0x18005dea1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005dea5  ja      short loc_18005DEBA
0x18005dea7  xor     edx, edx; dwMilliseconds
0x18005dea9  call    cs:__imp_WaitForSingleObject
0x18005deaf  cmp     eax, 102h
0x18005deb4  jz      loc_18005E0B9
0x18005deba  lea     rcx, qword_180156A98
0x18005dec1  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18005dec6  mov     ebx, eax
0x18005dec8  test    eax, eax
0x18005deca  jns     short loc_18005DEF4
0x18005decc  mov     [rsp+58h+dwCreationFlags], eax
0x18005ded0  lea     r9, aCreateeventFai_0; "CreateEvent failed [%#x]"
0x18005ded7  mov     r8d, 4Eh ; 'N'
0x18005dedd  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18005dee4  lea     ecx, [r8-4Dh]
0x18005dee8  call    AslLogCallPrintf
0x18005deed  mov     edx, 4Fh ; 'O'
0x18005def2  jmp     short loc_18005DF66
0x18005def4  lea     rcx, qword_180156AA0
0x18005defb  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18005df00  mov     ebx, eax
0x18005df02  test    eax, eax
0x18005df04  jns     short loc_18005DF2E
0x18005df06  mov     [rsp+58h+dwCreationFlags], eax
0x18005df0a  lea     r9, aCreateeventFai_0; "CreateEvent failed [%#x]"
0x18005df11  mov     r8d, 55h ; 'U'
0x18005df17  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18005df1e  lea     ecx, [r8-54h]
0x18005df22  call    AslLogCallPrintf
0x18005df27  mov     edx, 56h ; 'V'
0x18005df2c  jmp     short loc_18005DF66
0x18005df2e  lea     rcx, qword_180156AA8
0x18005df35  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18005df3a  mov     ebx, eax
0x18005df3c  test    eax, eax
0x18005df3e  jns     short loc_18005DF7F
0x18005df40  mov     [rsp+58h+dwCreationFlags], eax; int
0x18005df44  lea     r9, aCreateeventFai_0; "CreateEvent failed [%#x]"
0x18005df4b  mov     r8d, 5Ch ; '\'
0x18005df51  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18005df58  lea     ecx, [r8-5Bh]
0x18005df5c  call    AslLogCallPrintf
0x18005df61  mov     edx, 5Dh ; ']'; void *
0x18005df66  mov     rcx, [rsp+58h]; this
0x18005df6b  mov     r9d, ebx; char *
0x18005df6e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\appcompat"...
0x18005df75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005df7a  jmp     loc_18005E0BB
0x18005df7f  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18005df88  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18005df90  lea     r9, dword_180156A70; lpParameter
0x18005df97  lea     r8, ?ThreadProc@InventoryWatchdog@Inventory@Compat@Windows@@CAKPEAX@Z; lpStartAddress
0x18005df9e  mov     edx, 1; dwStackSize
0x18005dfa3  xor     ecx, ecx; lpThreadAttributes
0x18005dfa5  call    cs:__imp_CreateThread
0x18005dfab  mov     rdi, rax
0x18005dfae  mov     rsi, cs:qword_180156A90
0x18005dfb5  lea     rdx, [rsi-1]
0x18005dfb9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005dfbd  ja      short loc_18005DFD8
0x18005dfbf  call    cs:__imp_GetLastError
0x18005dfc5  mov     ebx, eax
0x18005dfc7  mov     rcx, rsi; hObject
0x18005dfca  call    cs:__imp_CloseHandle
0x18005dfd0  mov     ecx, ebx; dwErrCode
0x18005dfd2  call    cs:__imp_SetLastError
0x18005dfd8  mov     cs:qword_180156A90, rdi
0x18005dfdf  lea     rax, [rdi+1]
0x18005dfe3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18005dfe9  jnz     short loc_18005E02F
0x18005dfeb  call    cs:__imp_GetLastError
0x18005dff1  mov     [rsp+58h+dwCreationFlags], eax
0x18005dff5  lea     r9, aCreatethreadFa; "CreateThread failed [%d]"
0x18005dffc  mov     r8d, 63h ; 'c'
0x18005e002  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18005e009  lea     ecx, [r8-62h]
0x18005e00d  call    AslLogCallPrintf
0x18005e012  mov     rcx, [rsp+58h]; this
0x18005e017  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\appcompat"...
0x18005e01e  mov     edx, 64h ; 'd'; void *
0x18005e023  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005e028  mov     ebx, eax
0x18005e02a  jmp     loc_18005E0BB
0x18005e02f  mov     edx, 2710h; dwMilliseconds
0x18005e034  mov     rcx, cs:qword_180156AA8; hHandle
0x18005e03b  call    cs:__imp_WaitForSingleObject
0x18005e041  mov     ebx, eax
0x18005e043  test    eax, eax
0x18005e045  jz      short loc_18005E0B9
0x18005e047  cmp     eax, 0FFFFFFFFh
0x18005e04a  jnz     short loc_18005E07D
0x18005e04c  call    cs:__imp_GetLastError
0x18005e052  mov     [rsp+58h+dwCreationFlags], eax
0x18005e056  lea     r9, aWaitforsingleo_0; "WaitForSingleObject failed [%d]"
0x18005e05d  mov     r8d, 6Ch ; 'l'
0x18005e063  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18005e06a  lea     ecx, [r8-6Bh]
0x18005e06e  call    AslLogCallPrintf
0x18005e073  call    cs:__imp_GetLastError
0x18005e079  mov     ebx, eax
0x18005e07b  jmp     short loc_18005E09E
0x18005e07d  mov     [rsp+58h+dwCreationFlags], eax
0x18005e081  lea     r9, aWaitforsingleo_1; "WaitForSingleObject returned [%d]"
0x18005e088  mov     r8d, 71h ; 'q'
0x18005e08e  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18005e095  lea     ecx, [r8-70h]
0x18005e099  call    AslLogCallPrintf
0x18005e09e  lea     rcx, dword_180156A70; this
0x18005e0a5  call    ?Stop@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::Stop(void)
0x18005e0aa  test    ebx, ebx
0x18005e0ac  jle     short loc_18005E0BB
0x18005e0ae  movzx   ebx, bx
0x18005e0b1  or      ebx, 80070000h
0x18005e0b7  jmp     short loc_18005E0BB
0x18005e0b9  xor     ebx, ebx
0x18005e0bb  mov     rcx, rbp; SRWLock
0x18005e0be  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e0c4  mov     eax, ebx
0x18005e0c6  add     rsp, 38h
0x18005e0ca  pop     rdi
0x18005e0cb  pop     rsi
0x18005e0cc  pop     rbp
0x18005e0cd  pop     rbx
0x18005e0ce  retn
```
