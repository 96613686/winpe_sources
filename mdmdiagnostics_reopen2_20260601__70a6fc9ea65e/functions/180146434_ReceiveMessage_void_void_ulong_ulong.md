# ReceiveMessage(void *,void *,ulong,ulong *)

- ea: `0x180146434`
- end: `0x180146683`
- name: `?ReceiveMessage@@YAJPEAX0KPEAK@Z`
- size: `591`
- prototype: `__int64 __fastcall(HANDLE hFile, void *lpBuffer, DWORD nNumberOfBytesToRead, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180145470`
- `0x180145948`
- `0x180145dcc`
- `0x1801460c8`
- `0x180146ba8`

## callees

- `0x1800e7eb8`
- `0x1800ed44c`
- `0x1800ed46c`
- `0x180105294`
- `0x180146434`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180146514`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180146514`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180146565`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180146565`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801464a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801464a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146524`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801465cb`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801465cb`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180146583`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18014660e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180146583`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18014660e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ReceiveMessage(
        HANDLE hFile,
        void *lpBuffer,
        DWORD nNumberOfBytesToRead,
        LPDWORD lpNumberOfBytesTransferred)
{
  __int64 v8; // rdx
  unsigned int LastError; // ebx
  HANDLE EventW; // rax
  const char *v11; // r9
  void *v12; // rbx
  const char *v13; // r9
  DWORD v14; // eax
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // r9
  int lpOverlapped; // [rsp+20h] [rbp-38h]
  unsigned int lpOverlappeda; // [rsp+20h] [rbp-38h]
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  HANDLE v23; // [rsp+98h] [rbp+40h] BYREF

  if ( !lpBuffer )
  {
    v8 = 828;
LABEL_3:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
      (const char *)0x80070057LL,
      lpOverlapped);
    return LastError;
  }
  if ( !lpNumberOfBytesTransferred )
  {
    v8 = 829;
    goto LABEL_3;
  }
  if ( !hFile )
  {
    v8 = 830;
    goto LABEL_3;
  }
  if ( !nNumberOfBytesToRead )
  {
    v8 = 831;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  v23 = EventW;
  if ( EventW )
  {
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = EventW;
    if ( ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, lpNumberOfBytesTransferred, &Overlapped)
      || GetLastError() == 997 )
    {
      v14 = WaitForSingleObject(v12, 0x2710u);
      if ( v14 )
      {
        if ( v14 != 258 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x364,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        (const char *)v14,
                        lpOverlappeda);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
        if ( !CancelIo(hFile) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x35D,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v16);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
        if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x360,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v17);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
      }
      else if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x358,
                      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                      v15);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        return LastError;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
      return 0;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x351,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v13);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x342,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v11);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  }
  return LastError;
}

```

## disassembly

```asm
0x180146434  push    rbp
0x180146436  push    rbx
0x180146437  push    rsi
0x180146438  push    rdi
0x180146439  push    r14
0x18014643b  push    r15
0x18014643d  mov     rbp, rsp
0x180146440  sub     rsp, 58h
0x180146444  mov     rsi, r9
0x180146447  mov     r14d, r8d
0x18014644a  mov     r15, rdx
0x18014644d  mov     rdi, rcx
0x180146450  test    rdx, rdx
0x180146453  jnz     short loc_180146477
0x180146455  mov     edx, 33Ch; void *
0x18014645a  mov     ebx, 80070057h
0x18014645f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146466  mov     r9d, ebx; char *
0x180146469  mov     rcx, [rbp+30h]; this
0x18014646d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180146472  jmp     loc_180146673
0x180146477  test    rsi, rsi
0x18014647a  jnz     short loc_180146483
0x18014647c  mov     edx, 33Dh
0x180146481  jmp     short loc_18014645A
0x180146483  test    rdi, rdi
0x180146486  jnz     short loc_18014648F
0x180146488  mov     edx, 33Eh
0x18014648d  jmp     short loc_18014645A
0x18014648f  test    r14d, r14d
0x180146492  jnz     short loc_18014649B
0x180146494  mov     edx, 33Fh
0x180146499  jmp     short loc_18014645A
0x18014649b  xor     r9d, r9d; lpName
0x18014649e  xor     r8d, r8d; bInitialState
0x1801464a1  xor     edx, edx; bManualReset
0x1801464a3  xor     ecx, ecx; lpEventAttributes
0x1801464a5  call    cs:__imp_CreateEventW
0x1801464ac  nop     dword ptr [rax+rax+00h]
0x1801464b1  mov     rbx, rax
0x1801464b4  mov     [rbp+arg_8], rax
0x1801464b8  test    rax, rax
0x1801464bb  jnz     short loc_1801464E3
0x1801464bd  mov     rcx, [rbp+30h]; this
0x1801464c1  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801464c8  mov     edx, 342h; void *
0x1801464cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801464d2  mov     ebx, eax
0x1801464d4  lea     rcx, [rbp+arg_8]
0x1801464d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801464dd  nop
0x1801464de  jmp     loc_180146673
0x1801464e3  mov     [rbp+Overlapped.Internal], 0
0x1801464eb  mov     [rbp+Overlapped.InternalHigh], 0
0x1801464f3  mov     [rbp+Overlapped.hEvent], rbx
0x1801464f7  mov     qword ptr [rbp+Overlapped.10h], 0
0x1801464ff  lea     rax, [rbp+Overlapped]
0x180146503  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x180146508  mov     r9, rsi; lpNumberOfBytesRead
0x18014650b  mov     r8d, r14d; nNumberOfBytesToRead
0x18014650e  mov     rdx, r15; lpBuffer
0x180146511  mov     rcx, rdi; hFile
0x180146514  call    cs:__imp_ReadFile
0x18014651b  nop     dword ptr [rax+rax+00h]
0x180146520  test    eax, eax
0x180146522  jnz     short loc_18014655D
0x180146524  call    cs:__imp_GetLastError
0x18014652b  nop     dword ptr [rax+rax+00h]
0x180146530  cmp     eax, 3E5h
0x180146535  jz      short loc_18014655D
0x180146537  mov     rcx, [rbp+30h]; this
0x18014653b  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146542  mov     edx, 351h; void *
0x180146547  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18014654c  mov     ebx, eax
0x18014654e  lea     rcx, [rbp+arg_8]
0x180146552  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146557  nop
0x180146558  jmp     loc_180146673
0x18014655d  mov     edx, 2710h; dwMilliseconds
0x180146562  mov     rcx, rbx; hHandle
0x180146565  call    cs:__imp_WaitForSingleObject
0x18014656c  nop     dword ptr [rax+rax+00h]
0x180146571  test    eax, eax
0x180146573  jnz     short loc_1801465BD
0x180146575  lea     r9d, [rax+1]; bWait
0x180146579  mov     r8, rsi; lpNumberOfBytesTransferred
0x18014657c  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180146580  mov     rcx, rdi; hFile
0x180146583  call    cs:__imp_GetOverlappedResult
0x18014658a  nop     dword ptr [rax+rax+00h]
0x18014658f  test    eax, eax
0x180146591  jnz     loc_180146641
0x180146597  mov     rcx, [rbp+30h]; this
0x18014659b  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801465a2  mov     edx, 358h; void *
0x1801465a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801465ac  mov     ebx, eax
0x1801465ae  lea     rcx, [rbp+arg_8]
0x1801465b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801465b7  nop
0x1801465b8  jmp     loc_180146673
0x1801465bd  cmp     eax, 102h
0x1801465c2  jnz     loc_18014664F
0x1801465c8  mov     rcx, rdi; hFile
0x1801465cb  call    cs:__imp_CancelIo
0x1801465d2  nop     dword ptr [rax+rax+00h]
0x1801465d7  test    eax, eax
0x1801465d9  jnz     short loc_1801465FE
0x1801465db  mov     rcx, [rbp+30h]; this
0x1801465df  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801465e6  mov     edx, 35Dh; void *
0x1801465eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801465f0  mov     ebx, eax
0x1801465f2  lea     rcx, [rbp+arg_8]
0x1801465f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801465fb  nop
0x1801465fc  jmp     short loc_180146673
0x1801465fe  mov     r9d, 1; bWait
0x180146604  mov     r8, rsi; lpNumberOfBytesTransferred
0x180146607  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18014660b  mov     rcx, rdi; hFile
0x18014660e  call    cs:__imp_GetOverlappedResult
0x180146615  nop     dword ptr [rax+rax+00h]
0x18014661a  test    eax, eax
0x18014661c  jnz     short loc_180146641
0x18014661e  mov     rcx, [rbp+30h]; this
0x180146622  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146629  mov     edx, 360h; void *
0x18014662e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180146633  mov     ebx, eax
0x180146635  lea     rcx, [rbp+arg_8]
0x180146639  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014663e  nop
0x18014663f  jmp     short loc_180146673
0x180146641  lea     rcx, [rbp+arg_8]
0x180146645  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014664a  nop
0x18014664b  xor     eax, eax
0x18014664d  jmp     short loc_180146675
0x18014664f  mov     rcx, [rbp+30h]; this
0x180146653  mov     r9d, eax; char *
0x180146656  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18014665d  mov     edx, 364h; void *
0x180146662  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180146667  mov     ebx, eax
0x180146669  lea     rcx, [rbp+arg_8]
0x18014666d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146672  nop
0x180146673  mov     eax, ebx
0x180146675  add     rsp, 58h
0x180146679  pop     r15
0x18014667b  pop     r14
0x18014667d  pop     rdi
0x18014667e  pop     rsi
0x18014667f  pop     rbx
0x180146680  pop     rbp
0x180146681  retn
```
