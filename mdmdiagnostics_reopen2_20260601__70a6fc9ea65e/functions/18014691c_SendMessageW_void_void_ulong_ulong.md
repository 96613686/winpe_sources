# SendMessageW(void *,void *,ulong,ulong *)

- ea: `0x18014691c`
- end: `0x180146b5e`
- name: `?SendMessageW@@YAJPEAX0KPEAK@Z`
- size: `578`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesTransferred)`
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
- `0x18014691c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801469f0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801469f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180146a41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180146a41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180146981`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180146981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146a00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146a00`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180146aa6`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180146aa6`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180146a5e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180146ae9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180146a5e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180146ae9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SendMessageW(
        HANDLE hFile,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
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
    v8 = 776;
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
    v8 = 777;
    goto LABEL_3;
  }
  if ( !hFile )
  {
    v8 = 778;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  v23 = EventW;
  if ( EventW )
  {
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = EventW;
    if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, lpNumberOfBytesTransferred, &Overlapped)
      || GetLastError() == 997 )
    {
      v14 = WaitForSingleObject(v12, 0x2710u);
      if ( v14 )
      {
        if ( v14 != 258 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x330,
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
                        (void *)0x329,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v16);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
        if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x32C,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v17);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
      }
      else if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x324,
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
                  (void *)0x31D,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v13);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x30E,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v11);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  }
  return LastError;
}

```

## disassembly

```asm
0x18014691c  push    rbp
0x18014691e  push    rbx
0x18014691f  push    rsi
0x180146920  push    rdi
0x180146921  push    r14
0x180146923  push    r15
0x180146925  mov     rbp, rsp
0x180146928  sub     rsp, 58h
0x18014692c  mov     rsi, r9
0x18014692f  mov     r15d, r8d
0x180146932  mov     r14, rdx
0x180146935  mov     rdi, rcx
0x180146938  test    rdx, rdx
0x18014693b  jnz     short loc_18014695F
0x18014693d  mov     edx, 308h; void *
0x180146942  mov     ebx, 80070057h
0x180146947  mov     rcx, [rbp+30h]; this
0x18014694b  mov     r9d, ebx; char *
0x18014694e  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014695a  jmp     loc_180146B4E
0x18014695f  test    rsi, rsi
0x180146962  jnz     short loc_18014696B
0x180146964  mov     edx, 309h
0x180146969  jmp     short loc_180146942
0x18014696b  test    rdi, rdi
0x18014696e  jnz     short loc_180146977
0x180146970  mov     edx, 30Ah
0x180146975  jmp     short loc_180146942
0x180146977  xor     r9d, r9d; lpName
0x18014697a  xor     r8d, r8d; bInitialState
0x18014697d  xor     edx, edx; bManualReset
0x18014697f  xor     ecx, ecx; lpEventAttributes
0x180146981  call    cs:__imp_CreateEventW
0x180146988  nop     dword ptr [rax+rax+00h]
0x18014698d  mov     rbx, rax
0x180146990  mov     [rbp+arg_8], rax
0x180146994  test    rax, rax
0x180146997  jnz     short loc_1801469BF
0x180146999  mov     rcx, [rbp+30h]; this
0x18014699d  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801469a4  mov     edx, 30Eh; void *
0x1801469a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801469ae  mov     ebx, eax
0x1801469b0  lea     rcx, [rbp+arg_8]
0x1801469b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801469b9  nop
0x1801469ba  jmp     loc_180146B4E
0x1801469bf  mov     [rbp+Overlapped.Internal], 0
0x1801469c7  mov     [rbp+Overlapped.InternalHigh], 0
0x1801469cf  mov     [rbp+Overlapped.hEvent], rbx
0x1801469d3  mov     qword ptr [rbp+Overlapped.10h], 0
0x1801469db  lea     rax, [rbp+Overlapped]
0x1801469df  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x1801469e4  mov     r9, rsi; lpNumberOfBytesWritten
0x1801469e7  mov     r8d, r15d; nNumberOfBytesToWrite
0x1801469ea  mov     rdx, r14; lpBuffer
0x1801469ed  mov     rcx, rdi; hFile
0x1801469f0  call    cs:__imp_WriteFile
0x1801469f7  nop     dword ptr [rax+rax+00h]
0x1801469fc  test    eax, eax
0x1801469fe  jnz     short loc_180146A39
0x180146a00  call    cs:__imp_GetLastError
0x180146a07  nop     dword ptr [rax+rax+00h]
0x180146a0c  cmp     eax, 3E5h
0x180146a11  jz      short loc_180146A39
0x180146a13  mov     rcx, [rbp+30h]; this
0x180146a17  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146a1e  mov     edx, 31Dh; void *
0x180146a23  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180146a28  mov     ebx, eax
0x180146a2a  lea     rcx, [rbp+arg_8]
0x180146a2e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146a33  nop
0x180146a34  jmp     loc_180146B4E
0x180146a39  mov     edx, 2710h; dwMilliseconds
0x180146a3e  mov     rcx, rbx; hHandle
0x180146a41  call    cs:__imp_WaitForSingleObject
0x180146a48  nop     dword ptr [rax+rax+00h]
0x180146a4d  test    eax, eax
0x180146a4f  jnz     short loc_180146A98
0x180146a51  xor     r9d, r9d; bWait
0x180146a54  mov     r8, rsi; lpNumberOfBytesTransferred
0x180146a57  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180146a5b  mov     rcx, rdi; hFile
0x180146a5e  call    cs:__imp_GetOverlappedResult
0x180146a65  nop     dword ptr [rax+rax+00h]
0x180146a6a  test    eax, eax
0x180146a6c  jnz     loc_180146B1C
0x180146a72  mov     rcx, [rbp+30h]; this
0x180146a76  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146a7d  mov     edx, 324h; void *
0x180146a82  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180146a87  mov     ebx, eax
0x180146a89  lea     rcx, [rbp+arg_8]
0x180146a8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146a92  nop
0x180146a93  jmp     loc_180146B4E
0x180146a98  cmp     eax, 102h
0x180146a9d  jnz     loc_180146B2A
0x180146aa3  mov     rcx, rdi; hFile
0x180146aa6  call    cs:__imp_CancelIo
0x180146aad  nop     dword ptr [rax+rax+00h]
0x180146ab2  test    eax, eax
0x180146ab4  jnz     short loc_180146AD9
0x180146ab6  mov     rcx, [rbp+30h]; this
0x180146aba  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146ac1  mov     edx, 329h; void *
0x180146ac6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180146acb  mov     ebx, eax
0x180146acd  lea     rcx, [rbp+arg_8]
0x180146ad1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146ad6  nop
0x180146ad7  jmp     short loc_180146B4E
0x180146ad9  mov     r9d, 1; bWait
0x180146adf  mov     r8, rsi; lpNumberOfBytesTransferred
0x180146ae2  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180146ae6  mov     rcx, rdi; hFile
0x180146ae9  call    cs:__imp_GetOverlappedResult
0x180146af0  nop     dword ptr [rax+rax+00h]
0x180146af5  test    eax, eax
0x180146af7  jnz     short loc_180146B1C
0x180146af9  mov     rcx, [rbp+30h]; this
0x180146afd  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146b04  mov     edx, 32Ch; void *
0x180146b09  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180146b0e  mov     ebx, eax
0x180146b10  lea     rcx, [rbp+arg_8]
0x180146b14  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146b19  nop
0x180146b1a  jmp     short loc_180146B4E
0x180146b1c  lea     rcx, [rbp+arg_8]
0x180146b20  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146b25  nop
0x180146b26  xor     eax, eax
0x180146b28  jmp     short loc_180146B50
0x180146b2a  mov     rcx, [rbp+30h]; this
0x180146b2e  mov     r9d, eax; char *
0x180146b31  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146b38  mov     edx, 330h; void *
0x180146b3d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180146b42  mov     ebx, eax
0x180146b44  lea     rcx, [rbp+arg_8]
0x180146b48  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146b4d  nop
0x180146b4e  mov     eax, ebx
0x180146b50  add     rsp, 58h
0x180146b54  pop     r15
0x180146b56  pop     r14
0x180146b58  pop     rdi
0x180146b59  pop     rsi
0x180146b5a  pop     rbx
0x180146b5b  pop     rbp
0x180146b5c  retn
```
