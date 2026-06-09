# CPerf::InitPerf(void)

- ea: `0x180033138`
- end: `0x180033ddf`
- name: `?InitPerf@CPerf@@QEAAJXZ`
- size: `3239`
- prototype: `__int64 __fastcall(CPerf *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c664`

## callees

- `0x180009924`
- `0x18000d1f0`
- `0x18000f35c`
- `0x180012ea8`
- `0x18002c61c`
- `0x18002c6c8`
- `0x1800312dc`
- `0x180031300`
- `0x180031388`
- `0x180031520`
- `0x18003166c`
- `0x180032918`
- `0x180033004`
- `0x180033138`
- `0x18009bd1c`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180033406`
- `msvcrt!free` at `0x1800334af`
- `msvcrt!free` at `0x1800334b9`
- `msvcrt!free` at `0x180033550`
- `msvcrt!free` at `0x18003355a`
- `msvcrt!free` at `0x1800335eb`
- `msvcrt!free` at `0x1800335f5`
- `msvcrt!free` at `0x1800336bf`
- `msvcrt!free` at `0x1800336c9`
- `msvcrt!free` at `0x180033771`
- `msvcrt!free` at `0x18003377b`
- `msvcrt!free` at `0x180033a30`
- `msvcrt!free` at `0x180033a3a`
- `msvcrt!free` at `0x180033406`
- `msvcrt!free` at `0x1800334af`
- `msvcrt!free` at `0x1800334b9`
- `msvcrt!free` at `0x180033550`
- `msvcrt!free` at `0x18003355a`
- `msvcrt!free` at `0x1800335eb`
- `msvcrt!free` at `0x1800335f5`
- `msvcrt!free` at `0x1800336bf`
- `msvcrt!free` at `0x1800336c9`
- `msvcrt!free` at `0x180033771`
- `msvcrt!free` at `0x18003377b`
- `msvcrt!free` at `0x180033a30`
- `msvcrt!free` at `0x180033a3a`
- `ADVAPI32!GetTokenInformation` at `0x180033360`
- `ADVAPI32!GetTokenInformation` at `0x1800333a7`
- `ADVAPI32!GetTokenInformation` at `0x180033360`
- `ADVAPI32!GetTokenInformation` at `0x1800333a7`
- `ADVAPI32!OpenProcessToken` at `0x1800332c9`
- `ADVAPI32!OpenProcessToken` at `0x1800332c9`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800334ed`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800334ed`
- `ADVAPI32!GetLengthSid` at `0x18003342a`
- `ADVAPI32!GetLengthSid` at `0x18003342a`
- `ADVAPI32!InitializeAcl` at `0x18003344c`
- `ADVAPI32!InitializeAcl` at `0x18003344c`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180033246`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180033246`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180033588`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180033588`
- `KERNEL32!GetLastError` at `0x180033250`
- `KERNEL32!GetLastError` at `0x1800332d3`
- `KERNEL32!GetLastError` at `0x18003336e`
- `KERNEL32!GetLastError` at `0x1800333b1`
- `KERNEL32!GetLastError` at `0x18003345a`
- `KERNEL32!GetLastError` at `0x1800334fb`
- `KERNEL32!GetLastError` at `0x180033596`
- `KERNEL32!GetLastError` at `0x180033660`
- `KERNEL32!GetLastError` at `0x180033712`
- `KERNEL32!GetLastError` at `0x180033a6b`
- `KERNEL32!GetLastError` at `0x180033d50`
- `KERNEL32!GetLastError` at `0x180033250`
- `KERNEL32!GetLastError` at `0x1800332d3`
- `KERNEL32!GetLastError` at `0x18003336e`
- `KERNEL32!GetLastError` at `0x1800333b1`
- `KERNEL32!GetLastError` at `0x18003345a`
- `KERNEL32!GetLastError` at `0x1800334fb`
- `KERNEL32!GetLastError` at `0x180033596`
- `KERNEL32!GetLastError` at `0x180033660`
- `KERNEL32!GetLastError` at `0x180033712`
- `KERNEL32!GetLastError` at `0x180033a6b`
- `KERNEL32!GetLastError` at `0x180033d50`
- `KERNEL32!LeaveCriticalSection` at `0x180033188`
- `KERNEL32!LeaveCriticalSection` at `0x1800332a5`
- `KERNEL32!LeaveCriticalSection` at `0x180033333`
- `KERNEL32!LeaveCriticalSection` at `0x18003341b`
- `KERNEL32!LeaveCriticalSection` at `0x1800334ce`
- `KERNEL32!LeaveCriticalSection` at `0x18003356f`
- `KERNEL32!LeaveCriticalSection` at `0x18003360a`
- `KERNEL32!LeaveCriticalSection` at `0x1800336de`
- `KERNEL32!LeaveCriticalSection` at `0x180033790`
- `KERNEL32!LeaveCriticalSection` at `0x180033ace`
- `KERNEL32!LeaveCriticalSection` at `0x180033b89`
- `KERNEL32!LeaveCriticalSection` at `0x180033bdb`
- `KERNEL32!LeaveCriticalSection` at `0x180033c0e`
- `KERNEL32!LeaveCriticalSection` at `0x180033c93`
- `KERNEL32!LeaveCriticalSection` at `0x180033cfb`
- `KERNEL32!LeaveCriticalSection` at `0x180033d44`
- `KERNEL32!LeaveCriticalSection` at `0x180033db0`
- `KERNEL32!LeaveCriticalSection` at `0x180033188`
- `KERNEL32!LeaveCriticalSection` at `0x1800332a5`
- `KERNEL32!LeaveCriticalSection` at `0x180033333`
- `KERNEL32!LeaveCriticalSection` at `0x18003341b`
- `KERNEL32!LeaveCriticalSection` at `0x1800334ce`
- `KERNEL32!LeaveCriticalSection` at `0x18003356f`
- `KERNEL32!LeaveCriticalSection` at `0x18003360a`
- `KERNEL32!LeaveCriticalSection` at `0x1800336de`
- `KERNEL32!LeaveCriticalSection` at `0x180033790`
- `KERNEL32!LeaveCriticalSection` at `0x180033ace`
- `KERNEL32!LeaveCriticalSection` at `0x180033b89`
- `KERNEL32!LeaveCriticalSection` at `0x180033bdb`
- `KERNEL32!LeaveCriticalSection` at `0x180033c0e`
- `KERNEL32!LeaveCriticalSection` at `0x180033c93`
- `KERNEL32!LeaveCriticalSection` at `0x180033cfb`
- `KERNEL32!LeaveCriticalSection` at `0x180033d44`
- `KERNEL32!LeaveCriticalSection` at `0x180033db0`
- `KERNEL32!GetCurrentProcess` at `0x1800332b6`
- `KERNEL32!GetCurrentProcess` at `0x1800332b6`
- `KERNEL32!CreateFileMappingW` at `0x18003364a`
- `KERNEL32!CreateFileMappingW` at `0x18003364a`
- `KERNEL32!MapViewOfFile` at `0x1800336fc`
- `KERNEL32!MapViewOfFile` at `0x1800336fc`
- `ntdll!NtDeviceIoControlFile` at `0x180033b61`
- `ntdll!NtDeviceIoControlFile` at `0x180033b61`
- `USER32!LoadStringW` at `0x180033a61`
- `USER32!LoadStringW` at `0x180033a61`

## string_xrefs

- `0x180033aef`: `MSMQ Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPerf::InitPerf(CPerf *this)
{
  unsigned int v2; // r8d
  DWORD v3; // edx
  int v4; // eax
  DWORD v5; // ecx
  DWORD LastError; // eax
  int v7; // ebx
  HANDLE CurrentProcess; // rax
  DWORD v9; // eax
  int v10; // ebx
  PSID *v11; // rbx
  DWORD v12; // eax
  int v13; // edi
  DWORD v14; // esi
  struct _ACL *v15; // rdi
  DWORD v16; // eax
  int v17; // esi
  DWORD v18; // eax
  int v19; // esi
  DWORD v20; // eax
  int v21; // esi
  HANDLE v22; // rax
  signed int v23; // esi
  bool v24; // sf
  void *v25; // rax
  bool v26; // sf
  __int64 v27; // r12
  __int64 v28; // r10
  unsigned int v29; // r9d
  unsigned __int64 v30; // r14
  __int64 v31; // rax
  unsigned int v32; // esi
  __int64 v33; // r11
  __int64 v34; // rax
  int v35; // edx
  int v36; // r8d
  unsigned int i; // r8d
  _DWORD *v38; // rcx
  unsigned int v39; // edx
  unsigned int v40; // r10d
  __int64 v41; // r8
  _DWORD *v42; // r8
  unsigned int v43; // r11d
  __int64 j; // rax
  CPerf *v45; // rcx
  signed int v46; // ebx
  bool v47; // sf
  unsigned __int64 *v48; // r14
  CPerf *v49; // rcx
  NTSTATUS v50; // eax
  struct MQPerfProvider *v51; // rax
  MQPerfProvider *v52; // rcx
  int v53; // eax
  MQPerfProvider *v54; // rcx
  int ServiceInstance; // eax
  int v56; // eax
  MQPerfProvider *v57; // rcx
  struct _PERF_COUNTERSET_INSTANCE *QueueInstance; // rax
  MQPerfProvider *v59; // rcx
  int v60; // eax
  DWORD v61; // eax
  int v62; // ebx
  unsigned __int64 *OutputBufferLength; // [rsp+48h] [rbp-B8h]
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp-98h] BYREF
  _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+70h] [rbp-90h] BYREF
  PVOID v67; // [rsp+88h] [rbp-78h]
  void *v68; // [rsp+90h] [rbp-70h]
  _OWORD pSecurityDescriptor[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+B8h] [rbp-48h]
  _RTL_CRITICAL_SECTION *v71; // [rsp+C0h] [rbp-40h]
  PSID *v72; // [rsp+C8h] [rbp-38h]
  WCHAR Buffer[128]; // [rsp+D0h] [rbp-30h] BYREF

  v71 = &stru_18013A920;
  CCriticalSection::Lock((CCriticalSection *)&stru_18013A920);
  if ( dword_18013A900 )
  {
    LeaveCriticalSection(&stru_18013A920);
    return 0;
  }
  Size = 0;
  *((_QWORD *)&xmmword_18013A8F0 + 1) = MmAllocate(saturated_mul((unsigned int)dword_18013A910, 0x10u));
  v2 = 0;
  if ( dword_18013A910 )
  {
    v3 = Size;
    do
    {
      v4 = *(_DWORD *)(qword_18013A908 + 40LL * v2 + 32);
      v3 += 8 * (5 * v4 + *(_DWORD *)(qword_18013A908 + 40LL * v2 + 8) * (v4 + 20)) + 64;
      v5 = v3;
      Size = v3;
      if ( !*(_DWORD *)(qword_18013A908 + 40LL * v2 + 8) )
      {
        v3 += 8 * (*(_DWORD *)(qword_18013A908 + 40LL * v2 + 32) + 1);
        Size = v5 + 8 * (*(_DWORD *)(qword_18013A908 + 40LL * v2 + 32) + 1);
      }
      ++v2;
    }
    while ( v2 < dword_18013A910 );
  }
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v70 = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids, LastError);
    if ( v7 )
      LogMsgNTStatus(v7, (wchar_t *)L"qm\\perf", 0x4C6u);
    LeaveCriticalSection(&stru_18013A920);
    return 3222143015LL;
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v9 = GetLastError();
    v10 = v9;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids, v9);
    if ( v10 )
      LogMsgNTStatus(v10, (wchar_t *)L"qm\\perf", 0x4C7u);
LABEL_121:
    CHandle::~CHandle((CHandle *)&TokenHandle);
    LeaveCriticalSection(&stru_18013A920);
    return 3222143015LL;
  }
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenOwner, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    v61 = GetLastError();
    v62 = v61;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids, v61);
    if ( v62 )
      LogMsgNTStatus(v62, (wchar_t *)L"qm\\perf", 0x4C8u);
    goto LABEL_121;
  }
  v11 = (PSID *)MmAllocate(TokenInformationLength);
  v72 = v11;
  if ( !GetTokenInformation(TokenHandle, TokenOwner, v11, TokenInformationLength, &TokenInformationLength) )
  {
    v12 = GetLastError();
    v13 = v12;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids, v12);
    if ( v13 )
      LogMsgNTStatus(v13, (wchar_t *)L"qm\\perf", 0x4C9u);
    free(v11);
    CHandle::~CHandle((CHandle *)&TokenHandle);
    LeaveCriticalSection(&stru_18013A920);
    return 3222143015LL;
  }
  v14 = GetLengthSid(*v11) + 16;
  v15 = (struct _ACL *)MmAllocate(v14);
  v68 = v15;
  if ( InitializeAcl(v15, v14, 2u) )
  {
    if ( !AddAccessAllowedAce(v15, 2u, 0xF001Fu, *v11) )
    {
      v18 = GetLastError();
      v19 = v18;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids, v18);
      if ( v19 )
        LogMsgNTStatus(v19, (wchar_t *)L"qm\\perf", 0x469u);
      goto LABEL_51;
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v15, 1) )
    {
      v20 = GetLastError();
      v21 = v20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids, v20);
      if ( v21 )
        LogMsgNTStatus(v21, (wchar_t *)L"qm\\perf", 0x46Au);
      goto LABEL_51;
    }
    *(_QWORD *)&FileMappingAttributes.nLength = 24;
    *(_QWORD *)&FileMappingAttributes.bInheritHandle = 0;
    FileMappingAttributes.lpSecurityDescriptor = pSecurityDescriptor;
    v22 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, Size, 0);
    *(_QWORD *)&xmmword_18013A8F0 = v22;
    if ( !v22 )
    {
      v23 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids);
      v24 = v23 < 0;
      if ( v23 > 0 )
      {
        v23 = (unsigned __int16)v23 | 0x80070000;
        v24 = v23 < 0;
      }
      if ( v24 )
        LogMsgHR(v23, (wchar_t *)L"qm\\perf", 0x46Eu);
LABEL_60:
      free(v15);
      free(v11);
      CHandle::~CHandle((CHandle *)&TokenHandle);
      LeaveCriticalSection(&stru_18013A920);
      return (unsigned int)v23;
    }
    v25 = MapViewOfFile(v22, 2u, 0, 0, 0);
    PerfApp = v25;
    if ( !v25 )
    {
      v23 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids);
      v26 = v23 < 0;
      if ( v23 > 0 )
      {
        v23 = (unsigned __int16)v23 | 0x80070000;
        v26 = v23 < 0;
      }
      if ( v26 )
        LogMsgHR(v23, (wchar_t *)L"qm\\perf", 0x471u);
      goto LABEL_60;
    }
    memset_0(v25, 0, Size);
    v27 = *((_QWORD *)&xmmword_18013A8F0 + 1);
    v28 = qword_18013A908;
    v29 = dword_18013A910;
    v30 = PerfApp;
    v31 = 0;
    v32 = 0;
    if ( dword_18013A910 )
    {
      v33 = 0;
      do
      {
        v30 = (v31 + 7 + v30) & 0xFFFFFFFFFFFFFFF8uLL;
        v34 = 2 * v33;
        *(_QWORD *)(v27 + 8 * v34 + 8) = v30;
        *(_DWORD *)(v27 + 8 * v34) = 0;
        v35 = *(_DWORD *)(v28 + 40 * v33 + 32);
        v36 = *(_DWORD *)(v28 + 40 * v33 + 8);
        v31 = (unsigned int)(v36 * (8 * v35 + 160) + 8 * (v35 + 4 * (v35 + 2)));
        if ( !v36 )
          v31 = (unsigned int)(8 * v35 + v31 + 8);
        ++v32;
        ++v33;
      }
      while ( v32 < v29 );
      v29 = dword_18013A910;
      v28 = qword_18013A908;
    }
    for ( i = 0; i < v29; ++i )
    {
      v38 = (_DWORD *)(*(_QWORD *)(*((_QWORD *)&xmmword_18013A8F0 + 1) + 16LL * i + 8)
                     + 40LL * *(unsigned int *)(v28 + 40LL * i + 32)
                     + 64);
      v39 = 0;
      if ( *(_DWORD *)(v28 + 40LL * i + 8) )
      {
        do
        {
          *v38 = -16843010;
          v28 = qword_18013A908;
          v38 += 2 * *(unsigned int *)(qword_18013A908 + 40LL * i + 32) + 40;
          ++v39;
        }
        while ( v39 < *(_DWORD *)(qword_18013A908 + 40LL * i + 8) );
        v29 = dword_18013A910;
      }
    }
    dword_18013A900 = 1;
    v40 = 0;
    if ( v29 )
    {
      do
      {
        v41 = *(_QWORD *)(*((_QWORD *)&xmmword_18013A8F0 + 1) + 16LL * v40 + 8);
        *(_DWORD *)v41 = -16843010;
        *(_DWORD *)(v41 + 4) = 40 * *(_DWORD *)(qword_18013A908 + 40LL * v40 + 32) + 64;
        *(_DWORD *)(v41 + 8) = 64;
        *(_DWORD *)(v41 + 12) = *(_DWORD *)(qword_18013A908 + 40LL * v40 + 12);
        *(_DWORD *)(v41 + 16) = 0;
        *(_DWORD *)(v41 + 20) = *(_DWORD *)(qword_18013A908 + 40LL * v40 + 16);
        *(_DWORD *)(v41 + 24) = 0;
        *(_DWORD *)(v41 + 28) = 100;
        *(_QWORD *)(v41 + 32) = *(unsigned int *)(qword_18013A908 + 40LL * v40 + 32);
        *(_DWORD *)(v41 + 40) = -1;
        *(_DWORD *)(v41 + 44) = 0;
        v42 = (_DWORD *)(v41 + 64);
        v43 = 0;
        for ( j = qword_18013A908; v43 < *(_DWORD *)(qword_18013A908 + 40LL * v40 + 32); j = qword_18013A908 )
        {
          *v42 = 40;
          v42[1] = *(_DWORD *)(*(_QWORD *)(qword_18013A908 + 40LL * v40 + 24) + 16LL * v43);
          v42[2] = 0;
          v42[3] = *(_DWORD *)(*(_QWORD *)(qword_18013A908 + 40LL * v40 + 24) + 16LL * v43 + 4);
          v42[4] = 0;
          v42[5] = *(_DWORD *)(*(_QWORD *)(qword_18013A908 + 40LL * v40 + 24) + 16LL * v43 + 8);
          v42[6] = 100;
          v42[7] = *(_DWORD *)(*(_QWORD *)(qword_18013A908 + 40LL * v40 + 24) + 16LL * v43 + 12);
          v42[8] = 8;
          v42[9] = 8 * v43 + 8;
          v42 += 10;
          ++v43;
        }
        if ( !*(_DWORD *)(j + 40LL * v40 + 8) )
          *v42 = 8 * *(_DWORD *)(j + 40LL * v40 + 32) + 8;
        ++v40;
      }
      while ( v40 < dword_18013A910 );
    }
    free(v15);
    free(v11);
    CHandle::~CHandle((CHandle *)&TokenHandle);
    if ( LoadStringW(g_hResourceMod, 0x1776u, Buffer, 128) )
    {
      v48 = (unsigned __int64 *)CPerf::AddInstance(v45, L"MSMQ Queue", Buffer);
      g_pqmCounters = CPerf::GetCounters(v49, (wchar_t *)L"MSMQ Service");
      *(_QWORD *)&FileMappingAttributes.nLength = xmmword_18013A8F0;
      FileMappingAttributes.lpSecurityDescriptor = (LPVOID)PerfApp;
      *(_QWORD *)&FileMappingAttributes.bInheritHandle = v48;
      v67 = g_pqmCounters;
      v50 = NtDeviceIoControlFile(
              g_hAc,
              0,
              0,
              0,
              &`MQpDeviceIoControl'::`2'::Iosb,
              0x1965100Bu,
              0,
              0,
              &FileMappingAttributes,
              0x20u);
      v46 = v50;
      if ( v50 < 0 )
      {
        LogMsgHR(v50, (wchar_t *)L"qm\\perf", 0x32u);
        LeaveCriticalSection(&stru_18013A920);
        return (unsigned int)v46;
      }
      v51 = (struct MQPerfProvider *)MmAllocate(8u);
      v68 = v51;
      if ( v51 )
        *(_QWORD *)v51 = 0;
      else
        v51 = 0;
      g_pPerfProvider = v51;
      v53 = MQPerfProvider::PerfInitialize(v52);
      v46 = v53;
      if ( v53 < 0 )
      {
        LogMsgHR(v53, (wchar_t *)L"qm\\perf", 0x64u);
        LeaveCriticalSection(&stru_18013A920);
        return (unsigned int)v46;
      }
      ServiceInstance = MQPerfProvider::PerfGetServiceInstance(v54);
      v46 = ServiceInstance;
      if ( ServiceInstance < 0 )
      {
        LogMsgHR(ServiceInstance, (wchar_t *)L"qm\\perf", 0x6Eu);
        LeaveCriticalSection(&stru_18013A920);
        return (unsigned int)v46;
      }
      v56 = MQPerfProvider::PerfSetServiceRefValue(
              (MQPerfProvider *)((char *)g_pqmCounters + 80),
              (unsigned __int64 *)g_pqmCounters + 6,
              (unsigned __int64 *)g_pqmCounters + 3,
              (unsigned __int64 *)g_pqmCounters + 1,
              (unsigned __int64 *)g_pqmCounters + 5,
              (unsigned __int64 *)g_pqmCounters + 7,
              (unsigned __int64 *)g_pqmCounters + 2,
              (unsigned __int64 *)g_pqmCounters + 8,
              (unsigned __int64 *)g_pqmCounters + 4,
              OutputBufferLength,
              (unsigned __int64 *)g_pqmCounters + 10,
              (unsigned __int64 *)g_pqmCounters + 9);
      v46 = v56;
      if ( v56 < 0 )
      {
        LogMsgHR(v56, (wchar_t *)L"qm\\perf", 0x78u);
        LeaveCriticalSection(&stru_18013A920);
        return (unsigned int)v46;
      }
      QueueInstance = MQPerfProvider::PerfGetQueueInstance(v57, Buffer);
      if ( !QueueInstance )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids);
        LogMsgHR(-1072824281, (wchar_t *)L"qm\\perf", 0x82u);
        LeaveCriticalSection(&stru_18013A920);
        return 3222143015LL;
      }
      v60 = MQPerfProvider::PerfSetQueueRefValue(v59, QueueInstance, v48 + 3, v48 + 1, v48 + 2, v48);
      v46 = v60;
      if ( v60 < 0 )
        LogMsgHR(v60, (wchar_t *)L"qm\\perf", 0x8Cu);
    }
    else
    {
      v46 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids);
      v47 = v46 < 0;
      if ( v46 > 0 )
      {
        v46 = (unsigned __int16)v46 | 0x80070000;
        v47 = v46 < 0;
      }
      if ( v47 )
        LogMsgHR(v46, (wchar_t *)L"qm\\perf", 0x475u);
    }
    LeaveCriticalSection(&stru_18013A920);
    return (unsigned int)v46;
  }
  v16 = GetLastError();
  v17 = v16;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids, v16);
  if ( v17 )
    LogMsgNTStatus(v17, (wchar_t *)L"qm\\perf", 0x4CAu);
LABEL_51:
  free(v15);
  free(v11);
  CHandle::~CHandle((CHandle *)&TokenHandle);
  LeaveCriticalSection(&stru_18013A920);
  return 3222143015LL;
}

```

## disassembly

```asm
0x180033138  push    rbp
0x18003313a  push    rbx
0x18003313b  push    rsi
0x18003313c  push    rdi
0x18003313d  push    r12
0x18003313f  push    r13
0x180033141  push    r14
0x180033143  push    r15
0x180033145  lea     rbp, [rsp-0E8h]
0x18003314d  sub     rsp, 1E8h
0x180033154  mov     rax, cs:__security_cookie
0x18003315b  xor     rax, rsp
0x18003315e  mov     [rbp+120h+var_50], rax
0x180033165  lea     r14, stru_18013A920
0x18003316c  mov     [rbp+120h+var_160], r14
0x180033170  mov     rcx, r14; this
0x180033173  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180033178  nop
0x180033179  xor     r13d, r13d
0x18003317c  cmp     cs:dword_18013A900, r13d
0x180033183  jz      short loc_180033196
0x180033185  mov     rcx, r14; lpCriticalSection
0x180033188  call    cs:__imp_LeaveCriticalSection
0x18003318e  nop
0x18003318f  xor     eax, eax
0x180033191  jmp     loc_180033DBC
0x180033196  mov     cs:Size, r13d
0x18003319d  mov     ecx, cs:dword_18013A910
0x1800331a3  mov     eax, 10h
0x1800331a8  mul     rcx
0x1800331ab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800331b2  cmovb   rax, rcx
0x1800331b6  mov     rcx, rax; unsigned __int64
0x1800331b9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800331be  mov     qword ptr cs:xmmword_18013A8F0+8, rax
0x1800331c5  mov     r8d, r13d
0x1800331c8  mov     r15d, 1
0x1800331ce  mov     r11d, cs:dword_18013A910
0x1800331d5  test    r11d, r11d
0x1800331d8  jz      short loc_18003322E
0x1800331da  mov     r9, cs:qword_18013A908
0x1800331e1  mov     edx, cs:Size
0x1800331e7  mov     eax, r8d
0x1800331ea  lea     r10, [rax+rax*4]
0x1800331ee  mov     eax, [r9+r10*8+20h]
0x1800331f3  lea     ecx, [rax+14h]
0x1800331f6  imul    ecx, [r9+r10*8+8]
0x1800331fc  lea     eax, [rax+rax*4]
0x1800331ff  add     ecx, eax
0x180033201  lea     edx, [rdx+rcx*8]
0x180033204  add     edx, 40h ; '@'
0x180033207  mov     ecx, edx
0x180033209  mov     cs:Size, edx
0x18003320f  cmp     [r9+r10*8+8], r13d
0x180033214  jnz     short loc_180033226
0x180033216  mov     edx, [r9+r10*8+20h]
0x18003321b  inc     edx
0x18003321d  lea     edx, [rcx+rdx*8]
0x180033220  mov     cs:Size, edx
0x180033226  add     r8d, r15d
0x180033229  cmp     r8d, r11d
0x18003322c  jb      short loc_1800331E7
0x18003322e  xorps   xmm0, xmm0
0x180033231  xor     eax, eax
0x180033233  movups  [rbp+120h+pSecurityDescriptor], xmm0
0x180033237  movups  [rbp+120h+var_178], xmm0
0x18003323b  mov     [rbp+120h+var_168], rax
0x18003323f  mov     edx, r15d; dwRevision
0x180033242  lea     rcx, [rbp+120h+pSecurityDescriptor]; pSecurityDescriptor
0x180033246  call    cs:__imp_InitializeSecurityDescriptor
0x18003324c  test    eax, eax
0x18003324e  jnz     short loc_1800332B1
0x180033250  call    cs:__imp_GetLastError
0x180033256  mov     ebx, eax
0x180033258  lea     rdx, WPP_GLOBAL_Control
0x18003325f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033266  cmp     rcx, rdx
0x180033269  jz      short loc_180033289
0x18003326b  test    [rcx+1Ch], r15b
0x18003326f  jz      short loc_180033289
0x180033271  mov     edx, 17h
0x180033276  mov     r9d, eax
0x180033279  lea     r8, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids
0x180033280  mov     rcx, [rcx+10h]
0x180033284  call    WPP_SF_d
0x180033289  test    ebx, ebx
0x18003328b  jz      short loc_1800332A2
0x18003328d  mov     r8d, 4C6h; unsigned __int16
0x180033293  lea     rdx, aQmPerf; "qm\\perf"
0x18003329a  mov     ecx, ebx; int
0x18003329c  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x1800332a1  nop
0x1800332a2  mov     rcx, r14; lpCriticalSection
0x1800332a5  call    cs:__imp_LeaveCriticalSection
0x1800332ab  nop
0x1800332ac  jmp     loc_180033DB7
0x1800332b1  mov     [rsp+220h+TokenHandle], r13
0x1800332b6  call    cs:__imp_GetCurrentProcess
0x1800332bc  lea     r8, [rsp+220h+TokenHandle]; TokenHandle
0x1800332c1  mov     edx, 8; DesiredAccess
0x1800332c6  mov     rcx, rax; ProcessHandle
0x1800332c9  call    cs:__imp_OpenProcessToken
0x1800332cf  test    eax, eax
0x1800332d1  jnz     short loc_18003333F
0x1800332d3  call    cs:__imp_GetLastError
0x1800332d9  mov     ebx, eax
0x1800332db  lea     rdx, WPP_GLOBAL_Control
0x1800332e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800332e9  cmp     rcx, rdx
0x1800332ec  jz      short loc_18003330C
0x1800332ee  test    [rcx+1Ch], r15b
0x1800332f2  jz      short loc_18003330C
0x1800332f4  mov     edx, 18h
0x1800332f9  mov     r9d, eax
0x1800332fc  lea     r8, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids
0x180033303  mov     rcx, [rcx+10h]
0x180033307  call    WPP_SF_d
0x18003330c  test    ebx, ebx
0x18003330e  jz      short loc_180033325
0x180033310  mov     r8d, 4C7h; unsigned __int16
0x180033316  lea     rdx, aQmPerf; "qm\\perf"
0x18003331d  mov     ecx, ebx; int
0x18003331f  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180033324  nop
0x180033325  lea     rcx, [rsp+220h+TokenHandle]; this
0x18003332a  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18003332f  nop
0x180033330  mov     rcx, r14; lpCriticalSection
0x180033333  call    cs:__imp_LeaveCriticalSection
0x180033339  nop
0x18003333a  jmp     loc_180033DB7
0x18003333f  mov     [rsp+220h+TokenInformationLength], r13d
0x180033344  lea     rax, [rsp+220h+TokenInformationLength]
0x180033349  mov     [rsp+220h+ReturnLength], rax; ReturnLength
0x18003334e  xor     r9d, r9d; TokenInformationLength
0x180033351  xor     r8d, r8d; TokenInformation
0x180033354  lea     r12d, [r9+4]
0x180033358  mov     edx, r12d; TokenInformationClass
0x18003335b  mov     rcx, [rsp+220h+TokenHandle]; TokenHandle
0x180033360  call    cs:__imp_GetTokenInformation
0x180033366  test    eax, eax
0x180033368  jnz     loc_180033D50
0x18003336e  call    cs:__imp_GetLastError
0x180033374  cmp     eax, 7Ah ; 'z'
0x180033377  jnz     loc_180033D50
0x18003337d  mov     ecx, [rsp+220h+TokenInformationLength]; unsigned __int64
0x180033381  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180033386  mov     rbx, rax
0x180033389  mov     [rbp+120h+var_158], rax
0x18003338d  lea     rax, [rsp+220h+TokenInformationLength]
0x180033392  mov     [rsp+220h+ReturnLength], rax; ReturnLength
0x180033397  mov     r9d, [rsp+220h+TokenInformationLength]; TokenInformationLength
0x18003339c  mov     r8, rbx; TokenInformation
0x18003339f  mov     edx, r12d; TokenInformationClass
0x1800333a2  mov     rcx, [rsp+220h+TokenHandle]; TokenHandle
0x1800333a7  call    cs:__imp_GetTokenInformation
0x1800333ad  test    eax, eax
0x1800333af  jnz     short loc_180033427
0x1800333b1  call    cs:__imp_GetLastError
0x1800333b7  mov     edi, eax
0x1800333b9  lea     rdx, WPP_GLOBAL_Control
0x1800333c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333c7  cmp     rcx, rdx
0x1800333ca  jz      short loc_1800333EA
0x1800333cc  test    [rcx+1Ch], r15b
0x1800333d0  jz      short loc_1800333EA
0x1800333d2  lea     edx, [r12+16h]
0x1800333d7  mov     r9d, eax
0x1800333da  lea     r8, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids
0x1800333e1  mov     rcx, [rcx+10h]
0x1800333e5  call    WPP_SF_d
0x1800333ea  test    edi, edi
0x1800333ec  jz      short loc_180033403
0x1800333ee  mov     r8d, 4C9h; unsigned __int16
0x1800333f4  lea     rdx, aQmPerf; "qm\\perf"
0x1800333fb  mov     ecx, edi; int
0x1800333fd  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180033402  nop
0x180033403  mov     rcx, rbx; Block
0x180033406  call    cs:__imp_free
0x18003340c  nop
0x18003340d  lea     rcx, [rsp+220h+TokenHandle]; this
0x180033412  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180033417  nop
0x180033418  mov     rcx, r14; lpCriticalSection
0x18003341b  call    cs:__imp_LeaveCriticalSection
0x180033421  nop
0x180033422  jmp     loc_180033DB7
0x180033427  mov     rcx, [rbx]; pSid
0x18003342a  call    cs:__imp_GetLengthSid
0x180033430  lea     esi, [rax+10h]
0x180033433  mov     ecx, esi; unsigned __int64
0x180033435  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18003343a  mov     rdi, rax
0x18003343d  mov     [rbp+120h+var_190], rax
0x180033441  mov     r8d, 2; dwAclRevision
0x180033447  mov     edx, esi; nAclLength
0x180033449  mov     rcx, rax; pAcl
0x18003344c  call    cs:__imp_InitializeAcl
0x180033452  test    eax, eax
0x180033454  jnz     loc_1800334DA
0x18003345a  call    cs:__imp_GetLastError
0x180033460  mov     esi, eax
0x180033462  lea     rdx, WPP_GLOBAL_Control
0x180033469  mov     rcx, cs:WPP_GLOBAL_Control
0x180033470  cmp     rcx, rdx
0x180033473  jz      short loc_180033493
0x180033475  test    [rcx+1Ch], r15b
0x180033479  jz      short loc_180033493
0x18003347b  mov     edx, 1Bh
0x180033480  mov     r9d, eax
0x180033483  lea     r8, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids
0x18003348a  mov     rcx, [rcx+10h]
0x18003348e  call    WPP_SF_d
0x180033493  test    esi, esi
0x180033495  jz      short loc_1800334AC
0x180033497  mov     r8d, 4CAh; unsigned __int16
0x18003349d  lea     rdx, aQmPerf; "qm\\perf"
0x1800334a4  mov     ecx, esi; int
0x1800334a6  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x1800334ab  nop
0x1800334ac  mov     rcx, rdi; Block
0x1800334af  call    cs:__imp_free
0x1800334b5  nop
0x1800334b6  mov     rcx, rbx; Block
0x1800334b9  call    cs:__imp_free
0x1800334bf  nop
0x1800334c0  lea     rcx, [rsp+220h+TokenHandle]; this
0x1800334c5  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1800334ca  nop
0x1800334cb  mov     rcx, r14; lpCriticalSection
0x1800334ce  call    cs:__imp_LeaveCriticalSection
0x1800334d4  nop
0x1800334d5  jmp     loc_180033DB7
0x1800334da  mov     r9, [rbx]; pSid
0x1800334dd  mov     esi, 2
0x1800334e2  mov     r8d, 0F001Fh; AccessMask
0x1800334e8  mov     edx, esi; dwAceRevision
0x1800334ea  mov     rcx, rdi; pAcl
0x1800334ed  call    cs:__imp_AddAccessAllowedAce
0x1800334f3  test    eax, eax
0x1800334f5  jnz     loc_18003357B
0x1800334fb  call    cs:__imp_GetLastError
0x180033501  mov     esi, eax
0x180033503  lea     rdx, WPP_GLOBAL_Control
0x18003350a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033511  cmp     rcx, rdx
0x180033514  jz      short loc_180033534
0x180033516  test    [rcx+1Ch], r15b
0x18003351a  jz      short loc_180033534
0x18003351c  mov     edx, 1Ch
0x180033521  mov     r9d, eax
0x180033524  lea     r8, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids
0x18003352b  mov     rcx, [rcx+10h]
0x18003352f  call    WPP_SF_d
0x180033534  test    esi, esi
0x180033536  jz      short loc_18003354D
0x180033538  mov     r8d, 469h; unsigned __int16
0x18003353e  lea     rdx, aQmPerf; "qm\\perf"
0x180033545  mov     ecx, esi; int
0x180033547  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18003354c  nop
0x18003354d  mov     rcx, rdi; Block
0x180033550  call    cs:__imp_free
0x180033556  nop
0x180033557  mov     rcx, rbx; Block
0x18003355a  call    cs:__imp_free
0x180033560  nop
0x180033561  lea     rcx, [rsp+220h+TokenHandle]; this
0x180033566  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18003356b  nop
0x18003356c  mov     rcx, r14; lpCriticalSection
0x18003356f  call    cs:__imp_LeaveCriticalSection
0x180033575  nop
0x180033576  jmp     loc_180033DB7
0x18003357b  mov     r9d, r15d; bDaclDefaulted
0x18003357e  mov     r8, rdi; pDacl
0x180033581  mov     edx, r15d; bDaclPresent
0x180033584  lea     rcx, [rbp+120h+pSecurityDescriptor]; pSecurityDescriptor
0x180033588  call    cs:__imp_SetSecurityDescriptorDacl
0x18003358e  test    eax, eax
0x180033590  jnz     loc_180033616
0x180033596  call    cs:__imp_GetLastError
0x18003359c  mov     esi, eax
0x18003359e  lea     rdx, WPP_GLOBAL_Control
0x1800335a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335ac  cmp     rcx, rdx
0x1800335af  jz      short loc_1800335CF
0x1800335b1  test    [rcx+1Ch], r15b
0x1800335b5  jz      short loc_1800335CF
0x1800335b7  mov     edx, 1Dh
0x1800335bc  mov     r9d, eax
0x1800335bf  lea     r8, WPP_7fbd69fcc94d3a54dec861f45e3bbc23_Traceguids
0x1800335c6  mov     rcx, [rcx+10h]
0x1800335ca  call    WPP_SF_d
0x1800335cf  test    esi, esi
0x1800335d1  jz      short loc_1800335E8
0x1800335d3  mov     r8d, 46Ah; unsigned __int16
0x1800335d9  lea     rdx, aQmPerf; "qm\\perf"
0x1800335e0  mov     ecx, esi; int
  ... truncated ...
```
