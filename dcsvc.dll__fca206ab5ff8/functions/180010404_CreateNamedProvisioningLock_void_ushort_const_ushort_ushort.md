# CreateNamedProvisioningLock(void *,ushort const *,ushort * *,ushort * *)

- ea: `0x180010404`
- end: `0x1800106ba`
- name: `?CreateNamedProvisioningLock@@YAJPEAXPEBGPEAPEAG2@Z`
- size: `694`
- prototype: `__int64 __fastcall(_DWORD *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011940`

## callees

- `0x18000132c`
- `0x18000fcfc`
- `0x1800101b8`
- `0x180010404`
- `0x1800106c0`
- `0x180010a14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010638`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010641`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010638`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010538`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001052a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001052a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010470`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010470`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800105ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800105ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010697`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010697`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010626`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001062f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010626`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001062f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001061d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001061d`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800105f9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010615`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800105f9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010615`

## string_xrefs

- `0x18001065d`: `CreateNamedProvisioningLock`
- `0x180010576`: `CspReadyEvent`
- `0x18001057d`: `CspReadyEventUAP`
- `0x180010502`: `ConfigManagerMutex`
- `0x180010509`: `ConfigManagerMutexUAP`

## pseudocode

```c
__int64 __fastcall CreateNamedProvisioningLock(
        _DWORD *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  WCHAR *v7; // rdi
  WCHAR *v8; // rsi
  HANDLE v9; // r14
  HANDLE v10; // r15
  signed int MergedSecurityDescriptorForTransientObject; // ebx
  CLockTable *v12; // rcx
  signed int LastError; // eax
  CLockTable *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int v19; // [rsp+48h] [rbp-39h] BYREF
  int v20; // [rsp+4Ch] [rbp-35h] BYREF
  LPCWSTR lpName; // [rsp+50h] [rbp-31h] BYREF
  LPCWSTR v22; // [rsp+58h] [rbp-29h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+60h] [rbp-21h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+78h] [rbp-9h] BYREF
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+90h] [rbp+Fh]
  char v26; // [rsp+98h] [rbp+17h]

  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v7 = 0;
  lpName = 0;
  v8 = 0;
  v22 = 0;
  v20 = 1;
  v19 = 1;
  v25 = &g_csCmRecoveryApi;
  EnterCriticalSection(&g_csCmRecoveryApi);
  v26 = 1;
  v9 = 0;
  v10 = 0;
  if ( !a1 )
  {
    MergedSecurityDescriptorForTransientObject = -2147024890;
LABEL_21:
    FreeTransientObjectSecurityDescriptor(MutexAttributes.lpSecurityDescriptor);
    goto LABEL_23;
  }
  if ( a2 && a3 && a4 )
  {
    *a3 = 0;
    *a4 = 0;
    MergedSecurityDescriptorForTransientObject = CreateLockNames(a2, &lpName, &v22);
    v7 = (WCHAR *)lpName;
    if ( MergedSecurityDescriptorForTransientObject < 0 )
    {
      v8 = (WCHAR *)v22;
      goto LABEL_21;
    }
    MergedSecurityDescriptorForTransientObject = CLockTable::ReferenceLock(v12, lpName, a1[4]);
    v8 = (WCHAR *)v22;
    if ( MergedSecurityDescriptorForTransientObject != 1 )
    {
LABEL_12:
      if ( MergedSecurityDescriptorForTransientObject < 0 )
        goto LABEL_20;
      goto LABEL_13;
    }
    MutexAttributes.nLength = 24;
    MutexAttributes.bInheritHandle = 0;
    MergedSecurityDescriptorForTransientObject = DmGetMergedSecurityDescriptorForTransientObject(
                                                   0,
                                                   L"ConfigManagerMutexUAP",
                                                   L"ConfigManagerMutex",
                                                   &MutexAttributes.lpSecurityDescriptor,
                                                   &v20);
    if ( MergedSecurityDescriptorForTransientObject < 0 )
      goto LABEL_20;
    v9 = CreateMutexW(&MutexAttributes, 0, v7);
    if ( !v9 )
    {
LABEL_10:
      LastError = GetLastError();
      MergedSecurityDescriptorForTransientObject = LastError;
      if ( LastError > 0 )
        MergedSecurityDescriptorForTransientObject = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_12;
    }
    MergedSecurityDescriptorForTransientObject = DmGetMergedSecurityDescriptorForTransientObject(
                                                   1,
                                                   L"CspReadyEventUAP",
                                                   L"CspReadyEvent",
                                                   &EventAttributes.lpSecurityDescriptor,
                                                   &v19);
    if ( MergedSecurityDescriptorForTransientObject >= 0 )
    {
      EventAttributes.nLength = 24;
      EventAttributes.bInheritHandle = 0;
      v10 = CreateEventW(&EventAttributes, 0, 0, v8);
      if ( !v10 )
        goto LABEL_10;
      MergedSecurityDescriptorForTransientObject = CLockTable::AddLock(v14, v7, v9, v10, a1[4]);
      if ( MergedSecurityDescriptorForTransientObject >= 0 )
      {
        v9 = 0;
        v10 = 0;
LABEL_13:
        *a3 = v7;
        v7 = 0;
        *a4 = v8;
        v8 = 0;
      }
    }
  }
  else
  {
    MergedSecurityDescriptorForTransientObject = -2147467261;
  }
LABEL_20:
  if ( v20 )
    goto LABEL_21;
  LocalFree(MutexAttributes.lpSecurityDescriptor);
LABEL_23:
  if ( v19 )
    FreeTransientObjectSecurityDescriptor(EventAttributes.lpSecurityDescriptor);
  else
    LocalFree(EventAttributes.lpSecurityDescriptor);
  CloseHandle(v10);
  CloseHandle(v9);
  free(v8);
  free(v7);
  if ( (unsigned int)dword_18001B0E8 > 5 )
  {
    v19 = MergedSecurityDescriptorForTransientObject;
    v22 = a2;
    lpName = (LPCWSTR)"CreateNamedProvisioningLock";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v15,
      (__int64)&word_1800175C6,
      v16,
      v17,
      &lpName,
      (char **)&v22,
      (__int64)&v19);
  }
  LeaveCriticalSection(&g_csCmRecoveryApi);
  return (unsigned int)MergedSecurityDescriptorForTransientObject;
}

```

## disassembly

```asm
0x180010404  mov     rax, rsp
0x180010407  mov     [rax+8], rbx
0x18001040b  mov     [rax+18h], r8
0x18001040f  mov     [rax+10h], rdx
0x180010413  push    rbp
0x180010414  push    rsi
0x180010415  push    rdi
0x180010416  push    r12
0x180010418  push    r13
0x18001041a  push    r14
0x18001041c  push    r15
0x18001041e  lea     rbp, [rax-5Fh]
0x180010422  sub     rsp, 0A0h
0x180010429  mov     r12, r9
0x18001042c  mov     rbx, r8
0x18001042f  mov     r13, rcx
0x180010432  xorps   xmm0, xmm0
0x180010435  xor     eax, eax
0x180010437  movups  xmmword ptr [rbp+57h+MutexAttributes.nLength], xmm0
0x18001043b  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], rax
0x18001043f  xorps   xmm1, xmm1
0x180010442  movups  xmmword ptr [rbp+57h+EventAttributes.nLength], xmm1
0x180010446  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], rax
0x18001044a  xor     edi, edi
0x18001044c  mov     [rbp+57h+lpName], rdi
0x180010450  xor     esi, esi
0x180010452  mov     [rbp+57h+var_80], rsi
0x180010456  lea     r14d, [rax+1]
0x18001045a  mov     [rbp+57h+var_8C], r14d
0x18001045e  mov     [rbp+57h+var_90], r14d
0x180010462  lea     rax, ?g_csCmRecoveryApi@@3VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection g_csCmRecoveryApi
0x180010469  mov     [rbp+57h+var_48], rax
0x18001046d  mov     rcx, rax; lpCriticalSection
0x180010470  call    cs:__imp_EnterCriticalSection
0x180010476  mov     [rbp+57h+var_40], r14b
0x18001047a  xor     r14d, r14d
0x18001047d  xor     r15d, r15d
0x180010480  test    r13, r13
0x180010483  jnz     short loc_18001048F
0x180010485  mov     ebx, 80070006h
0x18001048a  jmp     loc_1800105F5
0x18001048f  mov     rax, [rbp+57h+arg_8]
0x180010493  test    rax, rax
0x180010496  jz      loc_1800105EA
0x18001049c  test    rbx, rbx
0x18001049f  jz      loc_1800105EA
0x1800104a5  test    r12, r12
0x1800104a8  jz      loc_1800105EA
0x1800104ae  mov     [rbx], r14
0x1800104b1  mov     [r12], r14
0x1800104b5  lea     r8, [rbp+57h+var_80]
0x1800104b9  lea     rdx, [rbp+57h+lpName]
0x1800104bd  mov     rcx, rax
0x1800104c0  call    CreateLockNames
0x1800104c5  mov     ebx, eax
0x1800104c7  mov     rdi, [rbp+57h+lpName]
0x1800104cb  test    eax, eax
0x1800104cd  js      loc_1800105E4
0x1800104d3  mov     r8d, [r13+10h]; unsigned int
0x1800104d7  mov     rdx, rdi; unsigned __int16 *
0x1800104da  call    ?ReferenceLock@CLockTable@@QEAAJPEBGK@Z; CLockTable::ReferenceLock(ushort const *,ulong)
0x1800104df  mov     ebx, eax
0x1800104e1  mov     rsi, [rbp+57h+var_80]
0x1800104e5  cmp     eax, 1
0x1800104e8  jnz     short loc_18001054D
0x1800104ea  mov     [rbp+57h+MutexAttributes.nLength], 18h
0x1800104f1  mov     [rbp+57h+MutexAttributes.bInheritHandle], r14d
0x1800104f5  lea     rax, [rbp+57h+var_8C]
0x1800104f9  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800104fe  lea     r9, [rbp+57h+MutexAttributes.lpSecurityDescriptor]
0x180010502  lea     r8, aConfigmanagerm_1; "ConfigManagerMutex"
0x180010509  lea     rdx, aConfigmanagerm_2; "ConfigManagerMutexUAP"
0x180010510  xor     ecx, ecx
0x180010512  call    ?DmGetMergedSecurityDescriptorForTransientObject@@YAJW4TransientObject_Type@@PEBG1PEAPEAXPEAH@Z; DmGetMergedSecurityDescriptorForTransientObject(TransientObject_Type,ushort const *,ushort const *,void * *,int *)
0x180010517  mov     ebx, eax
0x180010519  test    eax, eax
0x18001051b  js      loc_1800105EF
0x180010521  mov     r8, rdi; lpName
0x180010524  xor     edx, edx; bInitialOwner
0x180010526  lea     rcx, [rbp+57h+MutexAttributes]; lpMutexAttributes
0x18001052a  call    cs:__imp_CreateMutexW
0x180010530  mov     r14, rax
0x180010533  test    rax, rax
0x180010536  jnz     short loc_180010569
0x180010538  call    cs:__imp_GetLastError
0x18001053e  mov     ebx, eax
0x180010540  test    eax, eax
0x180010542  jle     short loc_18001054D
0x180010544  movzx   ebx, ax
0x180010547  or      ebx, 80070000h
0x18001054d  test    ebx, ebx
0x18001054f  js      loc_1800105EF
0x180010555  mov     rax, [rbp+57h+arg_10]
0x180010559  mov     [rax], rdi
0x18001055c  xor     edi, edi
0x18001055e  mov     [r12], rsi
0x180010562  xor     esi, esi
0x180010564  jmp     loc_1800105EF
0x180010569  lea     rax, [rbp+57h+var_90]
0x18001056d  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180010572  lea     r9, [rbp+57h+EventAttributes.lpSecurityDescriptor]
0x180010576  lea     r8, aCspreadyevent; "CspReadyEvent"
0x18001057d  lea     rdx, aCspreadyeventu; "CspReadyEventUAP"
0x180010584  mov     ecx, 1
0x180010589  call    ?DmGetMergedSecurityDescriptorForTransientObject@@YAJW4TransientObject_Type@@PEBG1PEAPEAXPEAH@Z; DmGetMergedSecurityDescriptorForTransientObject(TransientObject_Type,ushort const *,ushort const *,void * *,int *)
0x18001058e  mov     ebx, eax
0x180010590  test    eax, eax
0x180010592  js      short loc_1800105EF
0x180010594  mov     [rbp+57h+EventAttributes.nLength], 18h
0x18001059b  mov     [rbp+57h+EventAttributes.bInheritHandle], r15d
0x18001059f  mov     r9, rsi; lpName
0x1800105a2  xor     r8d, r8d; bInitialState
0x1800105a5  xor     edx, edx; bManualReset
0x1800105a7  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x1800105ab  call    cs:__imp_CreateEventW
0x1800105b1  mov     r15, rax
0x1800105b4  test    rax, rax
0x1800105b7  jz      loc_180010538
0x1800105bd  mov     eax, [r13+10h]
0x1800105c1  mov     dword ptr [rsp+0D0h+var_B0], eax; char
0x1800105c5  mov     r9, r15; void *
0x1800105c8  mov     r8, r14; void *
0x1800105cb  mov     rdx, rdi; unsigned __int16 *
0x1800105ce  call    ?AddLock@CLockTable@@QEAAJPEBGPEAX1K@Z; CLockTable::AddLock(ushort const *,void *,void *,ulong)
0x1800105d3  mov     ebx, eax
0x1800105d5  test    eax, eax
0x1800105d7  js      short loc_1800105EF
0x1800105d9  xor     r14d, r14d
0x1800105dc  xor     r15d, r15d
0x1800105df  jmp     loc_180010555
0x1800105e4  mov     rsi, [rbp+57h+var_80]
0x1800105e8  jmp     short loc_1800105F5
0x1800105ea  mov     ebx, 80004003h
0x1800105ef  cmp     [rbp+57h+var_8C], 0
0x1800105f3  jz      short loc_180010601
0x1800105f5  mov     rcx, [rbp+57h+MutexAttributes.lpSecurityDescriptor]
0x1800105f9  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800105ff  jmp     short loc_18001060B
0x180010601  mov     rcx, [rbp+57h+MutexAttributes.lpSecurityDescriptor]; hMem
0x180010605  call    cs:__imp_LocalFree
0x18001060b  mov     rcx, [rbp+57h+EventAttributes.lpSecurityDescriptor]; hMem
0x18001060f  cmp     [rbp+57h+var_90], 0
0x180010613  jz      short loc_18001061D
0x180010615  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18001061b  jmp     short loc_180010623
0x18001061d  call    cs:__imp_LocalFree
0x180010623  mov     rcx, r15; hObject
0x180010626  call    cs:__imp_CloseHandle
0x18001062c  mov     rcx, r14; hObject
0x18001062f  call    cs:__imp_CloseHandle
0x180010635  mov     rcx, rsi; Block
0x180010638  call    cs:__imp_free
0x18001063e  mov     rcx, rdi; Block
0x180010641  call    cs:__imp_free
0x180010647  mov     eax, cs:dword_18001B0E8
0x18001064d  cmp     eax, 5
0x180010650  jbe     short loc_180010690
0x180010652  mov     [rbp+57h+var_90], ebx
0x180010655  mov     rax, [rbp+57h+arg_8]
0x180010659  mov     [rbp+57h+var_80], rax
0x18001065d  lea     rax, aCreatenamedpro; "CreateNamedProvisioningLock"
0x180010664  mov     [rbp+57h+lpName], rax
0x180010668  lea     rax, [rbp+57h+var_90]
0x18001066c  mov     [rsp+30h], rax
0x180010671  lea     rax, [rbp+57h+var_80]
0x180010675  mov     [rsp+0D0h+var_A8], rax
0x18001067a  lea     rax, [rbp+57h+lpName]
0x18001067e  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180010683  lea     rdx, word_1800175C6
0x18001068a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001068f  nop
0x180010690  lea     rcx, ?g_csCmRecoveryApi@@3VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x180010697  call    cs:__imp_LeaveCriticalSection
0x18001069d  mov     eax, ebx
0x18001069f  mov     rbx, [rsp+0D0h+arg_0]
0x1800106a7  add     rsp, 0A0h
0x1800106ae  pop     r15
0x1800106b0  pop     r14
0x1800106b2  pop     r13
0x1800106b4  pop     r12
0x1800106b6  pop     rdi
0x1800106b7  pop     rsi
0x1800106b8  pop     rbp
0x1800106b9  retn
```
