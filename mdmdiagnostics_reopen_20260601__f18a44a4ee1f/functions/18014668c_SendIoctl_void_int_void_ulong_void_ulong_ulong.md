# SendIoctl(void *,int,void *,ulong,void *,ulong,ulong *)

- ea: `0x18014668c`
- end: `0x180146914`
- name: `?SendIoctl@@YAJPEAXH0K0KPEAK@Z`
- size: `648`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, unsigned int, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

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
- `0x18014668c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801467db`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801467db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801466f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801466f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014679a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014679a`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180146842`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180146842`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801467fa`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180146889`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801467fa`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180146889`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18014678a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18014678a`

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
0x18014668c  mov     [rsp-18h+arg_0], rbx
0x180146691  mov     [rsp-18h+arg_8], rsi
0x180146696  mov     [rsp-18h+BytesReturned], r9d
0x18014669b  push    rbp
0x18014669c  push    rdi
0x18014669d  push    r14
0x18014669f  mov     rbp, rsp
0x1801466a2  sub     rsp, 60h
0x1801466a6  mov     r14, r8
0x1801466a9  mov     rdi, rcx
0x1801466ac  test    r8, r8
0x1801466af  jnz     short loc_1801466D3
0x1801466b1  mov     edx, 2CAh; void *
0x1801466b6  mov     ebx, 80070057h
0x1801466bb  mov     rcx, [rbp+18h]; this
0x1801466bf  mov     r9d, ebx; char *
0x1801466c2  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801466c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801466ce  jmp     loc_1801468FC
0x1801466d3  mov     rsi, [rbp+arg_20]
0x1801466d7  test    rsi, rsi
0x1801466da  jnz     short loc_1801466E3
0x1801466dc  mov     edx, 2CBh
0x1801466e1  jmp     short loc_1801466B6
0x1801466e3  test    rdi, rdi
0x1801466e6  jnz     short loc_1801466EF
0x1801466e8  mov     edx, 2CCh
0x1801466ed  jmp     short loc_1801466B6
0x1801466ef  xor     r9d, r9d; lpName
0x1801466f2  xor     r8d, r8d; bInitialState
0x1801466f5  xor     edx, edx; bManualReset
0x1801466f7  xor     ecx, ecx; lpEventAttributes
0x1801466f9  call    cs:__imp_CreateEventW
0x180146700  nop     dword ptr [rax+rax+00h]
0x180146705  mov     rbx, rax
0x180146708  mov     [rbp+arg_10], rax
0x18014670c  test    rax, rax
0x18014670f  jnz     short loc_180146737
0x180146711  mov     rcx, [rbp+18h]; this
0x180146715  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18014671c  mov     edx, 2D1h; void *
0x180146721  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180146726  mov     ebx, eax
0x180146728  lea     rcx, [rbp+arg_10]
0x18014672c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146731  nop
0x180146732  jmp     loc_1801468FC
0x180146737  mov     [rbp+Overlapped.Internal], 0
0x18014673f  mov     [rbp+Overlapped.InternalHigh], 0
0x180146747  mov     [rbp+Overlapped.hEvent], rbx
0x18014674b  mov     qword ptr [rbp+Overlapped.10h], 0
0x180146753  mov     [rbp+BytesReturned], 0
0x18014675a  lea     rax, [rbp+Overlapped]
0x18014675e  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x180146763  lea     rax, [rbp+BytesReturned]
0x180146767  mov     [rsp+60h+lpBytesReturned], rax; lpBytesReturned
0x18014676c  mov     [rsp+60h+nOutBufferSize], 8; nOutBufferSize
0x180146774  mov     [rsp+60h+lpOutBuffer], rsi; unsigned int
0x180146779  mov     r9d, 10h; nInBufferSize
0x18014677f  mov     r8, r14; lpInBuffer
0x180146782  mov     edx, 8000E004h; dwIoControlCode
0x180146787  mov     rcx, rdi; hDevice
0x18014678a  call    cs:__imp_DeviceIoControl
0x180146791  nop     dword ptr [rax+rax+00h]
0x180146796  test    eax, eax
0x180146798  jnz     short loc_1801467D3
0x18014679a  call    cs:__imp_GetLastError
0x1801467a1  nop     dword ptr [rax+rax+00h]
0x1801467a6  cmp     eax, 3E5h
0x1801467ab  jz      short loc_1801467D3
0x1801467ad  mov     rcx, [rbp+18h]; this
0x1801467b1  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801467b8  mov     edx, 2E4h; void *
0x1801467bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801467c2  mov     ebx, eax
0x1801467c4  lea     rcx, [rbp+arg_10]
0x1801467c8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801467cd  nop
0x1801467ce  jmp     loc_1801468FC
0x1801467d3  mov     edx, 2710h; dwMilliseconds
0x1801467d8  mov     rcx, rbx; hHandle
0x1801467db  call    cs:__imp_WaitForSingleObject
0x1801467e2  nop     dword ptr [rax+rax+00h]
0x1801467e7  test    eax, eax
0x1801467e9  jnz     short loc_180146834
0x1801467eb  lea     r9d, [rax+1]; bWait
0x1801467ef  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x1801467f3  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801467f7  mov     rcx, rdi; hFile
0x1801467fa  call    cs:__imp_GetOverlappedResult
0x180146801  nop     dword ptr [rax+rax+00h]
0x180146806  test    eax, eax
0x180146808  jnz     loc_1801468BC
0x18014680e  mov     rcx, [rbp+18h]; this
0x180146812  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180146819  mov     edx, 2EBh; void *
0x18014681e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180146823  mov     ebx, eax
0x180146825  lea     rcx, [rbp+arg_10]
0x180146829  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014682e  nop
0x18014682f  jmp     loc_1801468FC
0x180146834  cmp     eax, 102h
0x180146839  jnz     loc_1801468D8
0x18014683f  mov     rcx, rdi; hFile
0x180146842  call    cs:__imp_CancelIo
0x180146849  nop     dword ptr [rax+rax+00h]
0x18014684e  test    eax, eax
0x180146850  jnz     short loc_180146878
0x180146852  mov     rcx, [rbp+18h]; this
0x180146856  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18014685d  mov     edx, 2F0h; void *
0x180146862  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180146867  mov     ebx, eax
0x180146869  lea     rcx, [rbp+arg_10]
0x18014686d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180146872  nop
0x180146873  jmp     loc_1801468FC
0x180146878  mov     r9d, 1; bWait
0x18014687e  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x180146882  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180146886  mov     rcx, rdi; hFile
0x180146889  call    cs:__imp_GetOverlappedResult
0x180146890  nop     dword ptr [rax+rax+00h]
0x180146895  test    eax, eax
0x180146897  jnz     short loc_1801468BC
0x180146899  mov     rcx, [rbp+18h]; this
0x18014689d  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801468a4  mov     edx, 2F3h; void *
0x1801468a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801468ae  mov     ebx, eax
0x1801468b0  lea     rcx, [rbp+arg_10]
0x1801468b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801468b9  nop
0x1801468ba  jmp     short loc_1801468FC
0x1801468bc  mov     rcx, [rbp+arg_30]
0x1801468c0  test    rcx, rcx
0x1801468c3  jz      short loc_1801468CA
0x1801468c5  mov     eax, [rbp+BytesReturned]
0x1801468c8  mov     [rcx], eax
0x1801468ca  lea     rcx, [rbp+arg_10]
0x1801468ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801468d3  nop
0x1801468d4  xor     eax, eax
0x1801468d6  jmp     short loc_1801468FE
0x1801468d8  mov     rcx, [rbp+18h]; this
0x1801468dc  mov     r9d, eax; char *
0x1801468df  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801468e6  mov     edx, 2F7h; void *
0x1801468eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801468f0  mov     ebx, eax
0x1801468f2  lea     rcx, [rbp+arg_10]
0x1801468f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801468fb  nop
0x1801468fc  mov     eax, ebx
0x1801468fe  lea     r11, [rsp+60h+var_s0]
0x180146903  mov     rbx, [r11+20h]
0x180146907  mov     rsi, [r11+28h]
0x18014690b  mov     rsp, r11
0x18014690e  pop     r14
0x180146910  pop     rdi
0x180146911  pop     rbp
0x180146912  retn
```
