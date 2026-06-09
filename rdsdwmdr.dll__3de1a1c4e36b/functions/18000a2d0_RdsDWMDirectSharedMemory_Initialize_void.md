# RdsDWMDirectSharedMemory::Initialize(void *)

- ea: `0x18000a2d0`
- end: `0x18000a440`
- name: `?Initialize@RdsDWMDirectSharedMemory@@UEAAJPEAX@Z`
- size: `368`
- prototype: `__int64 __fastcall(RdsDWMDirectSharedMemory *__hidden this, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180001724`
- `0x180006098`
- `0x18000a2d0`
- `0x18002b960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a346`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000a352`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000a352`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectSharedMemory::Initialize(RdsDWMDirectSharedMemory *this, void *a2)
{
  DWORD CurrentProcessId; // eax
  int v5; // eax
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  DWORD v10; // [rsp+20h] [rbp-79h]
  unsigned int v11; // [rsp+30h] [rbp-69h]
  DWORD pSessionId; // [rsp+50h] [rbp-49h] BYREF
  int v13; // [rsp+54h] [rbp-45h] BYREF
  int v14; // [rsp+58h] [rbp-41h] BYREF
  const char *v15; // [rsp+60h] [rbp-39h] BYREF
  const char *v16; // [rsp+68h] [rbp-31h] BYREF
  const char *v17; // [rsp+70h] [rbp-29h] BYREF
  const char *v18; // [rsp+78h] [rbp-21h] BYREF
  _OWORD v19[4]; // [rsp+80h] [rbp-19h] BYREF
  _OWORD v20[2]; // [rsp+C0h] [rbp+27h]

  v19[0] = *(_OWORD *)L"Local\\62c7994c-06bf-4f86-b4ef-b643a4039351";
  v19[1] = *(_OWORD *)L"c7994c-06bf-4f86-b4ef-b643a4039351";
  v19[2] = *(_OWORD *)L"6bf-4f86-b4ef-b643a4039351";
  v19[3] = *(_OWORD *)L"-b4ef-b643a4039351";
  v20[0] = *(_OWORD *)L"43a4039351";
  *(_QWORD *)((char *)v20 + 14) = *(_QWORD *)L"351";
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  v11 = RdsDWMDirectSharedMemory::m_uiCreationId++;
  v10 = pSessionId;
  v5 = StringCchPrintfW((unsigned __int16 *)this + 4, 0x104u, L"%s-%d-%p-%d", v19, v10, a2, v11);
  v8 = v5;
  if ( v5 < 0 && (unsigned int)dword_180044008 > 2 )
  {
    v13 = 108;
    v15 = "Failed to format the surface name string";
    v14 = v5;
    v16 = "Initialize";
    v17 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
    v18 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      dword_180044008,
      (unsigned int)byte_180038BBB,
      v6,
      v7,
      (__int64)&v18,
      (__int64)&v14,
      (__int64)&v17,
      (__int64)&v13,
      (__int64)&v16,
      (__int64)&v15);
  }
  return v8;
}

```

## disassembly

```asm
0x18000a2d0  mov     [rsp-8+arg_10], rbx
0x18000a2d5  mov     [rsp-8+arg_18], rdi
0x18000a2da  push    rbp
0x18000a2db  lea     rbp, [rsp-57h]
0x18000a2e0  sub     rsp, 0F0h
0x18000a2e7  mov     rax, cs:__security_cookie
0x18000a2ee  xor     rax, rsp
0x18000a2f1  mov     [rbp+57h+var_10], rax
0x18000a2f5  movaps  xmm0, xmmword ptr cs:aLocal62c7994c0; "Local\\62c7994c-06bf-4f86-b4ef-b643a403"...
0x18000a2fc  mov     rdi, rdx
0x18000a2ff  movaps  xmm1, xmmword ptr cs:aLocal62c7994c0+10h; "c7994c-06bf-4f86-b4ef-b643a4039351"
0x18000a306  mov     rbx, rcx
0x18000a309  movaps  [rbp+57h+var_70], xmm0
0x18000a30d  movaps  xmm0, xmmword ptr cs:aLocal62c7994c0+20h; "6bf-4f86-b4ef-b643a4039351"
0x18000a314  movaps  [rbp+57h+var_60], xmm1
0x18000a318  movaps  xmm1, xmmword ptr cs:aLocal62c7994c0+30h; "-b4ef-b643a4039351"
0x18000a31f  movaps  [rbp+57h+var_50], xmm0
0x18000a323  movaps  xmm0, xmmword ptr cs:aLocal62c7994c0+40h; "43a4039351"
0x18000a32a  movaps  [rbp+57h+var_40], xmm1
0x18000a32e  movsd   xmm1, qword ptr cs:aLocal62c7994c0+4Eh; "351"
0x18000a336  movaps  xmmword ptr [rbp+57h+var_30], xmm0
0x18000a33a  movsd   qword ptr [rbp+57h+var_30+0Eh], xmm1
0x18000a33f  mov     [rbp+57h+pSessionId], 0
0x18000a346  call    cs:__imp_GetCurrentProcessId
0x18000a34c  mov     ecx, eax; dwProcessId
0x18000a34e  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x18000a352  call    cs:__imp_ProcessIdToSessionId
0x18000a358  mov     edx, cs:?m_uiCreationId@RdsDWMDirectSharedMemory@@0IA; uint RdsDWMDirectSharedMemory::m_uiCreationId
0x18000a35e  lea     rcx, [rbx+8]; unsigned __int16 *
0x18000a362  mov     dword ptr [rsp+0F0h+var_C0], edx
0x18000a366  lea     r9, [rbp+57h+var_70]
0x18000a36a  mov     [rsp+0F0h+var_C8], rdi
0x18000a36f  lea     r8, aSDPD; "%s-%d-%p-%d"
0x18000a376  lea     eax, [rdx+1]
0x18000a379  mov     edx, 104h; unsigned __int64
0x18000a37e  mov     cs:?m_uiCreationId@RdsDWMDirectSharedMemory@@0IA, eax; uint RdsDWMDirectSharedMemory::m_uiCreationId
0x18000a384  mov     eax, [rbp+57h+pSessionId]
0x18000a387  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18000a38b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a390  mov     ebx, eax
0x18000a392  test    eax, eax
0x18000a394  jns     loc_18000A41D
0x18000a39a  mov     ecx, cs:dword_180044008
0x18000a3a0  cmp     ecx, 2
0x18000a3a3  jbe     short loc_18000A41D
0x18000a3a5  lea     rax, aFailedToFormat; "Failed to format the surface name strin"...
0x18000a3ac  mov     [rbp+57h+var_9C], 6Ch ; 'l'
0x18000a3b3  mov     [rbp+57h+var_90], rax
0x18000a3b7  lea     rdx, byte_180038BBB
0x18000a3be  lea     rax, aInitialize; "Initialize"
0x18000a3c5  mov     [rbp+57h+var_98], ebx
0x18000a3c8  mov     [rbp+57h+var_88], rax
0x18000a3cc  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000a3d3  mov     [rbp+57h+var_80], rax
0x18000a3d7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000a3de  mov     [rbp+57h+var_78], rax
0x18000a3e2  lea     rax, [rbp+57h+var_90]
0x18000a3e6  mov     [rsp+0F0h+var_A8], rax
0x18000a3eb  lea     rax, [rbp+57h+var_88]
0x18000a3ef  mov     [rsp+0F0h+var_B0], rax
0x18000a3f4  lea     rax, [rbp+57h+var_9C]
0x18000a3f8  mov     [rsp+0F0h+var_B8], rax
0x18000a3fd  lea     rax, [rbp+57h+var_80]
0x18000a401  mov     [rsp+0F0h+var_C0], rax
0x18000a406  lea     rax, [rbp+57h+var_98]
0x18000a40a  mov     [rsp+0F0h+var_C8], rax
0x18000a40f  lea     rax, [rbp+57h+var_78]
0x18000a413  mov     [rsp+0F0h+var_D0], rax
0x18000a418  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000a41d  mov     eax, ebx
0x18000a41f  mov     rcx, [rbp+57h+var_10]
0x18000a423  xor     rcx, rsp; StackCookie
0x18000a426  call    __security_check_cookie
0x18000a42b  lea     r11, [rsp+0F0h+var_s0]
0x18000a433  mov     rbx, [r11+20h]
0x18000a437  mov     rdi, [r11+28h]
0x18000a43b  mov     rsp, r11
0x18000a43e  pop     rbp
0x18000a43f  retn
```
