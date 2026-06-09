# SendIoctl(void *,int,void *,ulong,void *,ulong,ulong *)

- ea: `0x180143f14`
- end: `0x18014416e`
- name: `?SendIoctl@@YAJPEAXH0K0KPEAK@Z`
- size: `602`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, unsigned int, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180142d30`
- `0x180143204`
- `0x180143688`
- `0x180143984`
- `0x1801443d4`

## callees

- `0x1800e7cc0`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x180104108`
- `0x180143f14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180144051`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180144051`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180143f81`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180143f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144016`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801440ac`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801440ac`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18014406a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801440ea`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18014406a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801440ea`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18014400c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18014400c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SendIoctl(
        HANDLE hFile,
        __int64 a2,
        void *a3,
        DWORD a4,
        LPVOID a5,
        unsigned int a6,
        unsigned int *a7)
{
  __int64 v9; // rdx
  unsigned int LastError; // ebx
  void *v11; // rsi
  HANDLE EventW; // rax
  const char *v13; // r9
  void *v14; // rbx
  const char *v15; // r9
  DWORD v16; // eax
  const char *v17; // r9
  const char *v18; // r9
  const char *v19; // r9
  int lpOutBuffer; // [rsp+20h] [rbp-40h]
  unsigned int lpOutBuffera; // [rsp+20h] [rbp-40h]
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HANDLE v25; // [rsp+90h] [rbp+30h] BYREF
  DWORD BytesReturned; // [rsp+98h] [rbp+38h] BYREF

  BytesReturned = a4;
  if ( !a3 )
  {
    v9 = 714;
LABEL_3:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
      (const char *)0x80070057LL,
      lpOutBuffer);
    return LastError;
  }
  v11 = a5;
  if ( !a5 )
  {
    v9 = 715;
    goto LABEL_3;
  }
  if ( !hFile )
  {
    v9 = 716;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v14 = EventW;
  v25 = EventW;
  if ( !EventW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2D1,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v13);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    return LastError;
  }
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = EventW;
  BytesReturned = 0;
  if ( !DeviceIoControl(hFile, 0x8000E004, a3, 0x10u, v11, 8u, &BytesReturned, &Overlapped) && GetLastError() != 997 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2E4,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v15);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    return LastError;
  }
  v16 = WaitForSingleObject(v14, 0x2710u);
  if ( v16 )
  {
    if ( v16 != 258 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x2F7,
                    (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                    (const char *)v16,
                    lpOutBuffera);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
      return LastError;
    }
    if ( !CancelIo(hFile) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2F0,
                    (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                    v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
      return LastError;
    }
    if ( !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2F3,
                    (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                    v19);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
      return LastError;
    }
  }
  else if ( !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2EB,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v17);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    return LastError;
  }
  if ( a7 )
    *a7 = BytesReturned;
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
  return 0;
}

```

## disassembly

```asm
0x180143f14  mov     [rsp-18h+arg_0], rbx
0x180143f19  mov     [rsp-18h+arg_8], rsi
0x180143f1e  mov     [rsp-18h+BytesReturned], r9d
0x180143f23  push    rbp
0x180143f24  push    rdi
0x180143f25  push    r14
0x180143f27  mov     rbp, rsp
0x180143f2a  sub     rsp, 60h
0x180143f2e  mov     r14, r8
0x180143f31  mov     rdi, rcx
0x180143f34  test    r8, r8
0x180143f37  jnz     short loc_180143F5B
0x180143f39  mov     edx, 2CAh; void *
0x180143f3e  mov     ebx, 80070057h
0x180143f43  mov     rcx, [rbp+18h]; this
0x180143f47  mov     r9d, ebx; char *
0x180143f4a  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180143f51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143f56  jmp     loc_180144157
0x180143f5b  mov     rsi, [rbp+arg_20]
0x180143f5f  test    rsi, rsi
0x180143f62  jnz     short loc_180143F6B
0x180143f64  mov     edx, 2CBh
0x180143f69  jmp     short loc_180143F3E
0x180143f6b  test    rdi, rdi
0x180143f6e  jnz     short loc_180143F77
0x180143f70  mov     edx, 2CCh
0x180143f75  jmp     short loc_180143F3E
0x180143f77  xor     r9d, r9d; lpName
0x180143f7a  xor     r8d, r8d; bInitialState
0x180143f7d  xor     edx, edx; bManualReset
0x180143f7f  xor     ecx, ecx; lpEventAttributes
0x180143f81  call    cs:__imp_CreateEventW
0x180143f87  mov     rbx, rax
0x180143f8a  mov     [rbp+arg_10], rax
0x180143f8e  test    rax, rax
0x180143f91  jnz     short loc_180143FB9
0x180143f93  mov     rcx, [rbp+18h]; this
0x180143f97  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180143f9e  mov     edx, 2D1h; void *
0x180143fa3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180143fa8  mov     ebx, eax
0x180143faa  lea     rcx, [rbp+arg_10]
0x180143fae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180143fb3  nop
0x180143fb4  jmp     loc_180144157
0x180143fb9  mov     [rbp+Overlapped.Internal], 0
0x180143fc1  mov     [rbp+Overlapped.InternalHigh], 0
0x180143fc9  mov     [rbp+Overlapped.hEvent], rbx
0x180143fcd  mov     qword ptr [rbp+Overlapped.10h], 0
0x180143fd5  mov     [rbp+BytesReturned], 0
0x180143fdc  lea     rax, [rbp+Overlapped]
0x180143fe0  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x180143fe5  lea     rax, [rbp+BytesReturned]
0x180143fe9  mov     [rsp+60h+lpBytesReturned], rax; lpBytesReturned
0x180143fee  mov     [rsp+60h+nOutBufferSize], 8; nOutBufferSize
0x180143ff6  mov     [rsp+60h+lpOutBuffer], rsi; unsigned int
0x180143ffb  mov     r9d, 10h; nInBufferSize
0x180144001  mov     r8, r14; lpInBuffer
0x180144004  mov     edx, 8000E004h; dwIoControlCode
0x180144009  mov     rcx, rdi; hDevice
0x18014400c  call    cs:__imp_DeviceIoControl
0x180144012  test    eax, eax
0x180144014  jnz     short loc_180144049
0x180144016  call    cs:__imp_GetLastError
0x18014401c  cmp     eax, 3E5h
0x180144021  jz      short loc_180144049
0x180144023  mov     rcx, [rbp+18h]; this
0x180144027  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18014402e  mov     edx, 2E4h; void *
0x180144033  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180144038  mov     ebx, eax
0x18014403a  lea     rcx, [rbp+arg_10]
0x18014403e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180144043  nop
0x180144044  jmp     loc_180144157
0x180144049  mov     edx, 2710h; dwMilliseconds
0x18014404e  mov     rcx, rbx; hHandle
0x180144051  call    cs:__imp_WaitForSingleObject
0x180144057  test    eax, eax
0x180144059  jnz     short loc_18014409E
0x18014405b  lea     r9d, [rax+1]; bWait
0x18014405f  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x180144063  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180144067  mov     rcx, rdi; hFile
0x18014406a  call    cs:__imp_GetOverlappedResult
0x180144070  test    eax, eax
0x180144072  jnz     loc_180144117
0x180144078  mov     rcx, [rbp+18h]; this
0x18014407c  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180144083  mov     edx, 2EBh; void *
0x180144088  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18014408d  mov     ebx, eax
0x18014408f  lea     rcx, [rbp+arg_10]
0x180144093  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180144098  nop
0x180144099  jmp     loc_180144157
0x18014409e  cmp     eax, 102h
0x1801440a3  jnz     loc_180144133
0x1801440a9  mov     rcx, rdi; hFile
0x1801440ac  call    cs:__imp_CancelIo
0x1801440b2  test    eax, eax
0x1801440b4  jnz     short loc_1801440D9
0x1801440b6  mov     rcx, [rbp+18h]; this
0x1801440ba  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801440c1  mov     edx, 2F0h; void *
0x1801440c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801440cb  mov     ebx, eax
0x1801440cd  lea     rcx, [rbp+arg_10]
0x1801440d1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801440d6  nop
0x1801440d7  jmp     short loc_180144157
0x1801440d9  mov     r9d, 1; bWait
0x1801440df  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x1801440e3  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801440e7  mov     rcx, rdi; hFile
0x1801440ea  call    cs:__imp_GetOverlappedResult
0x1801440f0  test    eax, eax
0x1801440f2  jnz     short loc_180144117
0x1801440f4  mov     rcx, [rbp+18h]; this
0x1801440f8  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801440ff  mov     edx, 2F3h; void *
0x180144104  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180144109  mov     ebx, eax
0x18014410b  lea     rcx, [rbp+arg_10]
0x18014410f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180144114  nop
0x180144115  jmp     short loc_180144157
0x180144117  mov     rcx, [rbp+arg_30]
0x18014411b  test    rcx, rcx
0x18014411e  jz      short loc_180144125
0x180144120  mov     eax, [rbp+BytesReturned]
0x180144123  mov     [rcx], eax
0x180144125  lea     rcx, [rbp+arg_10]
0x180144129  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014412e  nop
0x18014412f  xor     eax, eax
0x180144131  jmp     short loc_180144159
0x180144133  mov     rcx, [rbp+18h]; this
0x180144137  mov     r9d, eax; char *
0x18014413a  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180144141  mov     edx, 2F7h; void *
0x180144146  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18014414b  mov     ebx, eax
0x18014414d  lea     rcx, [rbp+arg_10]
0x180144151  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180144156  nop
0x180144157  mov     eax, ebx
0x180144159  lea     r11, [rsp+60h+var_s0]
0x18014415e  mov     rbx, [r11+20h]
0x180144162  mov     rsi, [r11+28h]
0x180144166  mov     rsp, r11
0x180144169  pop     r14
0x18014416b  pop     rdi
0x18014416c  pop     rbp
0x18014416d  retn
```
