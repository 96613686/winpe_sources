# ReceiveMessage(void *,void *,ulong,ulong *)

- ea: `0x180143cec`
- end: `0x180143f0c`
- name: `?ReceiveMessage@@YAJPEAX0KPEAK@Z`
- size: `544`
- prototype: `__int64 __fastcall(HANDLE hFile, void *lpBuffer, DWORD nNumberOfBytesToRead, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, registry_config`

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
- `0x180143cec`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180143dc6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180143dc6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180143e0b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180143e0b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180143d5d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180143d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180143dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180143dd0`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180143e61`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180143e61`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180143e23`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180143e9e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180143e23`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180143e9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180143cec  push    rbp
0x180143cee  push    rbx
0x180143cef  push    rsi
0x180143cf0  push    rdi
0x180143cf1  push    r14
0x180143cf3  push    r15
0x180143cf5  mov     rbp, rsp
0x180143cf8  sub     rsp, 58h
0x180143cfc  mov     rsi, r9
0x180143cff  mov     r14d, r8d
0x180143d02  mov     r15, rdx
0x180143d05  mov     rdi, rcx
0x180143d08  test    rdx, rdx
0x180143d0b  jnz     short loc_180143D2F
0x180143d0d  mov     edx, 33Ch; void *
0x180143d12  mov     ebx, 80070057h
0x180143d17  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180143d1e  mov     r9d, ebx; char *
0x180143d21  mov     rcx, [rbp+30h]; this
0x180143d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143d2a  jmp     loc_180143EFD
0x180143d2f  test    rsi, rsi
0x180143d32  jnz     short loc_180143D3B
0x180143d34  mov     edx, 33Dh
0x180143d39  jmp     short loc_180143D12
0x180143d3b  test    rdi, rdi
0x180143d3e  jnz     short loc_180143D47
0x180143d40  mov     edx, 33Eh
0x180143d45  jmp     short loc_180143D12
0x180143d47  test    r14d, r14d
0x180143d4a  jnz     short loc_180143D53
0x180143d4c  mov     edx, 33Fh
0x180143d51  jmp     short loc_180143D12
0x180143d53  xor     r9d, r9d; lpName
0x180143d56  xor     r8d, r8d; bInitialState
0x180143d59  xor     edx, edx; bManualReset
0x180143d5b  xor     ecx, ecx; lpEventAttributes
0x180143d5d  call    cs:__imp_CreateEventW
0x180143d63  mov     rbx, rax
0x180143d66  mov     [rbp+arg_8], rax
0x180143d6a  test    rax, rax
0x180143d6d  jnz     short loc_180143D95
0x180143d6f  mov     rcx, [rbp+30h]; this
0x180143d73  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180143d7a  mov     edx, 342h; void *
0x180143d7f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180143d84  mov     ebx, eax
0x180143d86  lea     rcx, [rbp+arg_8]
0x180143d8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180143d8f  nop
0x180143d90  jmp     loc_180143EFD
0x180143d95  mov     [rbp+Overlapped.Internal], 0
0x180143d9d  mov     [rbp+Overlapped.InternalHigh], 0
0x180143da5  mov     [rbp+Overlapped.hEvent], rbx
0x180143da9  mov     qword ptr [rbp+Overlapped.10h], 0
0x180143db1  lea     rax, [rbp+Overlapped]
0x180143db5  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x180143dba  mov     r9, rsi; lpNumberOfBytesRead
0x180143dbd  mov     r8d, r14d; nNumberOfBytesToRead
0x180143dc0  mov     rdx, r15; lpBuffer
0x180143dc3  mov     rcx, rdi; hFile
0x180143dc6  call    cs:__imp_ReadFile
0x180143dcc  test    eax, eax
0x180143dce  jnz     short loc_180143E03
0x180143dd0  call    cs:__imp_GetLastError
0x180143dd6  cmp     eax, 3E5h
0x180143ddb  jz      short loc_180143E03
0x180143ddd  mov     rcx, [rbp+30h]; this
0x180143de1  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180143de8  mov     edx, 351h; void *
0x180143ded  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180143df2  mov     ebx, eax
0x180143df4  lea     rcx, [rbp+arg_8]
0x180143df8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180143dfd  nop
0x180143dfe  jmp     loc_180143EFD
0x180143e03  mov     edx, 2710h; dwMilliseconds
0x180143e08  mov     rcx, rbx; hHandle
0x180143e0b  call    cs:__imp_WaitForSingleObject
0x180143e11  test    eax, eax
0x180143e13  jnz     short loc_180143E57
0x180143e15  lea     r9d, [rax+1]; bWait
0x180143e19  mov     r8, rsi; lpNumberOfBytesTransferred
0x180143e1c  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180143e20  mov     rcx, rdi; hFile
0x180143e23  call    cs:__imp_GetOverlappedResult
0x180143e29  test    eax, eax
0x180143e2b  jnz     loc_180143ECB
0x180143e31  mov     rcx, [rbp+30h]; this
0x180143e35  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180143e3c  mov     edx, 358h; void *
0x180143e41  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180143e46  mov     ebx, eax
0x180143e48  lea     rcx, [rbp+arg_8]
0x180143e4c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180143e51  nop
0x180143e52  jmp     loc_180143EFD
0x180143e57  cmp     eax, 102h
0x180143e5c  jnz     short loc_180143ED9
0x180143e5e  mov     rcx, rdi; hFile
0x180143e61  call    cs:__imp_CancelIo
0x180143e67  test    eax, eax
0x180143e69  jnz     short loc_180143E8E
0x180143e6b  mov     rcx, [rbp+30h]; this
0x180143e6f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180143e76  mov     edx, 35Dh; void *
0x180143e7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180143e80  mov     ebx, eax
0x180143e82  lea     rcx, [rbp+arg_8]
0x180143e86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180143e8b  nop
0x180143e8c  jmp     short loc_180143EFD
0x180143e8e  mov     r9d, 1; bWait
0x180143e94  mov     r8, rsi; lpNumberOfBytesTransferred
0x180143e97  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180143e9b  mov     rcx, rdi; hFile
0x180143e9e  call    cs:__imp_GetOverlappedResult
0x180143ea4  test    eax, eax
0x180143ea6  jnz     short loc_180143ECB
0x180143ea8  mov     rcx, [rbp+30h]; this
0x180143eac  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180143eb3  mov     edx, 360h; void *
0x180143eb8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180143ebd  mov     ebx, eax
0x180143ebf  lea     rcx, [rbp+arg_8]
0x180143ec3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180143ec8  nop
0x180143ec9  jmp     short loc_180143EFD
0x180143ecb  lea     rcx, [rbp+arg_8]
0x180143ecf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180143ed4  nop
0x180143ed5  xor     eax, eax
0x180143ed7  jmp     short loc_180143EFF
0x180143ed9  mov     rcx, [rbp+30h]; this
0x180143edd  mov     r9d, eax; char *
0x180143ee0  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180143ee7  mov     edx, 364h; void *
0x180143eec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180143ef1  mov     ebx, eax
0x180143ef3  lea     rcx, [rbp+arg_8]
0x180143ef7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180143efc  nop
0x180143efd  mov     eax, ebx
0x180143eff  add     rsp, 58h
0x180143f03  pop     r15
0x180143f05  pop     r14
0x180143f07  pop     rdi
0x180143f08  pop     rsi
0x180143f09  pop     rbx
0x180143f0a  pop     rbp
0x180143f0b  retn
```
