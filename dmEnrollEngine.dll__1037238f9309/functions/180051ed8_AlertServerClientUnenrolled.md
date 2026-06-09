# AlertServerClientUnenrolled

- ea: `0x180051ed8`
- end: `0x180052123`
- name: `AlertServerClientUnenrolled`
- size: `587`
- prototype: `__int64 __fastcall(int, int, int, int, PHKEY, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006f280`

## callees

- `0x18001aec8`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x18003b068`
- `0x18003b118`
- `0x180051ed8`
- `0x180073450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051f65`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051fd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051fd5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800520d5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800520d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800520a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800520a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051fef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051fef`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x18005207b`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x18005207b`

## string_xrefs

- `0x180051f99`: `com.microsoft:mdm.unenrollment.userrequest`

## pseudocode

```c
__int64 __fastcall AlertServerClientUnenrolled(
        __int64 a1,
        __int64 a2,
        int a3,
        LPCWSTR *a4,
        PHKEY phkResult,
        HANDLE *a6)
{
  __int64 v10; // r8
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v13; // r8
  signed int v14; // ebx
  CEnrollmentLogger *Logger; // rax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  _DWORD v19[2]; // [rsp+40h] [rbp-98h] BYREF
  const wchar_t *v20; // [rsp+48h] [rbp-90h]
  __int64 v21; // [rsp+58h] [rbp-80h]
  int v22; // [rsp+60h] [rbp-78h]
  int v23; // [rsp+64h] [rbp-74h]
  _BYTE v24[16]; // [rsp+80h] [rbp-58h] BYREF

  memset_0(v19, 0, 0x40u);
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, FunctionEntryPointEvent, v10, 1, v24);
  EventW = CreateEventW(0, 1, 0, 0);
  *a6 = EventW;
  if ( EventW )
  {
    v19[0] = 64;
    v20 = L"com.microsoft:mdm.unenrollment.userrequest";
    v19[1] = 1226;
    v21 = a2;
    v22 = a3;
    v23 = 2;
    if ( !a1 )
    {
      v14 = -2147418113;
      goto LABEL_8;
    }
    v14 = OmaDmInitiateSessionAsDevice(a1, 1, 2, v19, 1, a4, 9);
    if ( v14 < 0 )
      goto LABEL_8;
    v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *a4, 0, 0x20019u, phkResult);
    v14 = v17;
    if ( v17 > 0 )
      v14 = (unsigned __int16)v17 | 0x80070000;
    if ( v14 < 0 )
      goto LABEL_8;
    v18 = RegNotifyChangeKeyValue(*phkResult, 1, 5u, *a6, 1);
    v14 = v18;
    if ( v18 > 0 )
      v14 = (unsigned __int16)v18 | 0x80070000;
  }
  else
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v14 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(
        MDM_ENTERPRISE_DIAGNOSTICS_Context,
        EnterpriseDiagnosticsUnenrollAlertSendSuccess,
        v13,
        1,
        v24);
    goto LABEL_16;
  }
LABEL_8:
  if ( *a6 )
  {
    CloseHandle(*a6);
    *a6 = 0;
  }
  if ( phkResult && *phkResult )
  {
    RegCloseKey(*phkResult);
    *phkResult = 0;
  }
  if ( v14 == -2147024894 )
    v14 = 1;
  Logger = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogUnenrollAlertSendFail(Logger, v14);
LABEL_16:
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, FunctionReturnValueEvent, (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180051ed8  push    rbx
0x180051eda  push    rbp
0x180051edb  push    rsi
0x180051edc  push    rdi
0x180051edd  push    r12
0x180051edf  push    r14
0x180051ee1  push    r15
0x180051ee3  sub     rsp, 0A0h
0x180051eea  mov     rax, cs:__security_cookie
0x180051ef1  xor     rax, rsp
0x180051ef4  mov     [rsp+0D8h+var_48], rax
0x180051efc  mov     rsi, [rsp+0D8h+arg_20]
0x180051f04  mov     rbp, rdx
0x180051f07  mov     r14, [rsp+0D8h+arg_28]
0x180051f0f  xor     edx, edx; Val
0x180051f11  mov     r15d, r8d
0x180051f14  mov     rbx, rcx
0x180051f17  lea     rcx, [rsp+0D8h+var_98]; void *
0x180051f1c  mov     rdi, r9
0x180051f1f  lea     r8d, [rdx+40h]; Size
0x180051f23  call    memset_0
0x180051f28  mov     r12d, 1
0x180051f2e  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r12b
0x180051f35  jz      short loc_180051F5A
0x180051f37  lea     rax, [rsp+0D8h+var_58]
0x180051f3f  mov     r9d, r12d
0x180051f42  lea     rdx, FunctionEntryPointEvent
0x180051f49  mov     [rsp+0D8h+phkResult], rax
0x180051f4e  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180051f55  call    McGenEventWrite_EventWriteTransfer
0x180051f5a  xor     r9d, r9d; lpName
0x180051f5d  xor     r8d, r8d; bInitialState
0x180051f60  mov     edx, r12d; bManualReset
0x180051f63  xor     ecx, ecx; lpEventAttributes
0x180051f65  call    cs:__imp_CreateEventW
0x180051f6b  mov     [r14], rax
0x180051f6e  test    rax, rax
0x180051f71  jnz     short loc_180051F91
0x180051f73  call    cs:__imp_GetLastError
0x180051f79  mov     ebx, eax
0x180051f7b  test    eax, eax
0x180051f7d  jle     loc_1800520E6
0x180051f83  movzx   ebx, ax
0x180051f86  or      ebx, 80070000h
0x180051f8c  jmp     loc_1800520E6
0x180051f91  mov     [rsp+0D8h+var_98], 40h ; '@'
0x180051f99  lea     rax, aComMicrosoftMd; "com.microsoft:mdm.unenrollment.userrequ"...
0x180051fa0  mov     [rsp+0D8h+var_90], rax
0x180051fa5  mov     [rsp+0D8h+var_94], 4CAh
0x180051fad  mov     [rsp+0D8h+var_80], rbp
0x180051fb2  mov     [rsp+0D8h+var_78], r15d
0x180051fb7  mov     [rsp+0D8h+var_74], 2
0x180051fbf  test    rbx, rbx
0x180051fc2  jnz     loc_180052058
0x180051fc8  mov     ebx, 8000FFFFh
0x180051fcd  mov     rcx, [r14]; hObject
0x180051fd0  test    rcx, rcx
0x180051fd3  jz      short loc_180051FE2
0x180051fd5  call    cs:__imp_CloseHandle
0x180051fdb  mov     qword ptr [r14], 0
0x180051fe2  test    rsi, rsi
0x180051fe5  jz      short loc_180051FFC
0x180051fe7  mov     rcx, [rsi]; hKey
0x180051fea  test    rcx, rcx
0x180051fed  jz      short loc_180051FFC
0x180051fef  call    cs:__imp_RegCloseKey
0x180051ff5  mov     qword ptr [rsi], 0
0x180051ffc  cmp     ebx, 80070002h
0x180052002  cmovz   ebx, r12d
0x180052006  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005200b  mov     edx, ebx; int
0x18005200d  mov     rcx, rax; this
0x180052010  call    ?LogUnenrollAlertSendFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogUnenrollAlertSendFail(long)
0x180052015  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r12b
0x18005201c  jz      short loc_180052034
0x18005201e  mov     r8d, ebx
0x180052021  lea     rdx, FunctionReturnValueEvent
0x180052028  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18005202f  call    McTemplateU0q_EventWriteTransfer
0x180052034  mov     eax, ebx
0x180052036  mov     rcx, [rsp+0D8h+var_48]
0x18005203e  xor     rcx, rsp; StackCookie
0x180052041  call    __security_check_cookie
0x180052046  add     rsp, 0A0h
0x18005204d  pop     r15
0x18005204f  pop     r14
0x180052051  pop     r12
0x180052053  pop     rdi
0x180052054  pop     rsi
0x180052055  pop     rbp
0x180052056  pop     rbx
0x180052057  retn
0x180052058  mov     [rsp+0D8h+var_A8], 9
0x180052060  lea     r9, [rsp+0D8h+var_98]
0x180052065  mov     [rsp+0D8h+var_B0], rdi
0x18005206a  mov     r8d, 2
0x180052070  mov     edx, r12d
0x180052073  mov     dword ptr [rsp+0D8h+phkResult], r12d
0x180052078  mov     rcx, rbx
0x18005207b  call    cs:__imp_OmaDmInitiateSessionAsDevice
0x180052081  mov     ebx, eax
0x180052083  test    eax, eax
0x180052085  js      loc_180051FCD
0x18005208b  mov     rdx, [rdi]; lpSubKey
0x18005208e  mov     r9d, 20019h; samDesired
0x180052094  xor     r8d, r8d; ulOptions
0x180052097  mov     [rsp+0D8h+phkResult], rsi; phkResult
0x18005209c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800520a3  call    cs:__imp_RegOpenKeyExW
0x1800520a9  mov     ebx, eax
0x1800520ab  mov     edi, 80070000h
0x1800520b0  test    eax, eax
0x1800520b2  jle     short loc_1800520B9
0x1800520b4  movzx   ebx, ax
0x1800520b7  or      ebx, edi
0x1800520b9  test    ebx, ebx
0x1800520bb  js      loc_180051FCD
0x1800520c1  mov     r9, [r14]; hEvent
0x1800520c4  mov     r8d, 5; dwNotifyFilter
0x1800520ca  mov     rcx, [rsi]; hKey
0x1800520cd  mov     edx, r12d; bWatchSubtree
0x1800520d0  mov     dword ptr [rsp+0D8h+phkResult], r12d; fAsynchronous
0x1800520d5  call    cs:__imp_RegNotifyChangeKeyValue
0x1800520db  mov     ebx, eax
0x1800520dd  test    eax, eax
0x1800520df  jle     short loc_1800520E6
0x1800520e1  movzx   ebx, ax
0x1800520e4  or      ebx, edi
0x1800520e6  test    ebx, ebx
0x1800520e8  js      loc_180051FCD
0x1800520ee  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 2
0x1800520f5  jz      loc_180052015
0x1800520fb  lea     rax, [rsp+0D8h+var_58]
0x180052103  mov     r9d, r12d
0x180052106  lea     rdx, EnterpriseDiagnosticsUnenrollAlertSendSuccess
0x18005210d  mov     [rsp+0D8h+phkResult], rax
0x180052112  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180052119  call    McGenEventWrite_EventWriteTransfer
0x18005211e  jmp     loc_180052015
```
