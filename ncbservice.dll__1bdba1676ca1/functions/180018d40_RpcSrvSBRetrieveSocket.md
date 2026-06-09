# RpcSrvSBRetrieveSocket

- ea: `0x180018d40`
- end: `0x18001945e`
- name: `RpcSrvSBRetrieveSocket`
- size: `1822`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, wchar_t *, const unsigned __int16 *, unsigned __int8, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180002770`
- `0x180002810`
- `0x180004a30`
- `0x18000a0a0`
- `0x18000a160`
- `0x180014780`
- `0x180017804`
- `0x180018d40`
- `0x18001d8e0`
- `0x18001d910`
- `0x18002666c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019389`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800193ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019389`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800193ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019397`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800193fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019397`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800193fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ff2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ff2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001908a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001915c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001908a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001915c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019417`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019417`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180018f63`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180018f63`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001931e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001931e`
- `RPCRT4!RpcRevertToSelf` at `0x1800193a4`
- `RPCRT4!RpcRevertToSelf` at `0x1800193a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800193b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001940d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800193b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001940d`

## string_xrefs

- `0x180019331`: `RpcSrvSBRetrieveSocket: completed`

## pseudocode

```c
__int64 __fastcall RpcSrvSBRetrieveSocket(
        __int64 a1,
        unsigned __int16 *a2,
        wchar_t *a3,
        const unsigned __int16 *a4,
        unsigned __int8 a5,
        _QWORD *a6)
{
  const unsigned __int16 *v6; // rbx
  wchar_t *v7; // rsi
  HANDLE v9; // r14
  LPCRITICAL_SECTION v10; // r15
  int v11; // edi
  char v12; // al
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  LPCRITICAL_SECTION v16; // rcx
  DWORD ProcessId; // esi
  DWORD LastError; // eax
  SocketBrokerContext *v19; // r13
  struct SharedSocket *Socket; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  struct SharedSocket *v23; // rdi
  unsigned int v24; // esi
  __int64 v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rax
  int v30; // eax
  HANDLE ProcessHeap; // rax
  char *v32; // rbx
  void *v33; // rsi
  HANDLE v34; // rax
  void *v35; // rcx
  int v37; // [rsp+40h] [rbp-E8h] BYREF
  bool v38; // [rsp+48h] [rbp-E0h] BYREF
  wchar_t *v39; // [rsp+50h] [rbp-D8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-D0h] BYREF
  HANDLE Process; // [rsp+60h] [rbp-C8h] BYREF
  void *Block; // [rsp+68h] [rbp-C0h] BYREF
  _QWORD *v43; // [rsp+70h] [rbp-B8h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-B0h] BYREF
  const unsigned __int16 *v45; // [rsp+88h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-98h] BYREF
  const wchar_t *v47; // [rsp+A0h] [rbp-88h]
  __int64 v48; // [rsp+A8h] [rbp-80h]
  int *v49; // [rsp+B0h] [rbp-78h]
  __int64 v50; // [rsp+B8h] [rbp-70h]
  void *v51; // [rsp+C0h] [rbp-68h]
  int v52; // [rsp+C8h] [rbp-60h]
  int v53; // [rsp+CCh] [rbp-5Ch]
  int *v54; // [rsp+D0h] [rbp-58h]
  __int64 v55; // [rsp+D8h] [rbp-50h]

  v6 = a4;
  v7 = a3;
  v39 = a3;
  v43 = a6;
  Block = 0;
  v9 = 0;
  Process = 0;
  v10 = 0;
  lpCriticalSection = 0;
  v38 = 0;
  if ( a3 && a4 && a6 )
  {
    if ( (unsigned int)dword_18004D068 > 5 )
    {
      v37 = a5;
      v45 = a4;
      *(_QWORD *)&EventDescriptor.Id = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        a1,
        (unsigned int)&dword_1800454CC,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&EventDescriptor,
        (__int64)&v45,
        (__int64)&v37);
    }
    v11 = RpcHelperRetriveSbContext(
            a2,
            (struct _GUID *)a2,
            &v38,
            (unsigned __int16 **)&lpCriticalSection,
            (struct SocketBrokerContext **)&Block,
            &Process);
    v12 = Microsoft_Windows_Network_Connection_BrokerEnableBits;
    v10 = lpCriticalSection;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v47 = v7;
      v48 = 16;
      v13 = -1;
      do
        ++v13;
      while ( v6[v13] );
      v49 = (int *)v6;
      v50 = (unsigned int)(2 * v13 + 2);
      if ( lpCriticalSection )
      {
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)&lpCriticalSection->DebugInfo + v14) );
        v15 = 2 * v14 + 2;
        v16 = lpCriticalSection;
      }
      else
      {
        v15 = 10;
        v16 = (LPCRITICAL_SECTION)L"NULL";
      }
      v51 = v16;
      v52 = v15;
      v53 = 0;
      McGenEventWrite_EventWriteTransfer(v16, SbRetrieveSocket, a3, 4, &UserData);
      v12 = Microsoft_Windows_Network_Connection_BrokerEnableBits;
    }
    if ( v11 )
    {
      if ( (v12 & 1) != 0 )
      {
        v37 = v11;
        v47 = L"RpcSrvSBRetrieveSocket: RpcHelperRetriveSbContext failed";
        v48 = 114;
        v49 = &v37;
        v50 = 4;
        McGenEventWrite_EventWriteTransfer(a1, NcbApiStatus, a3, 3, &UserData);
      }
      v9 = Process;
      goto LABEL_39;
    }
    v9 = Process;
    ProcessId = GetProcessId(Process);
    if ( !ProcessId )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v37 = LastError;
        v47 = L"Failed to get Process ID";
        v48 = 50;
        v49 = &v37;
        v50 = 4;
        McGenEventWrite_EventWriteTransfer(a1, NcbApiStatus, a3, 3, &UserData);
      }
      goto LABEL_22;
    }
    v19 = (SocketBrokerContext *)Block;
    lpCriticalSection = (LPCRITICAL_SECTION)((char *)Block + 64);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)Block + 64));
    *v43 = 0;
    Socket = SocketBrokerContext::FindSocket(v19, v6);
    v23 = Socket;
    if ( !Socket )
    {
      v11 = 4312;
      v24 = 4312;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v37 = 4312;
        v47 = L"RetrieveSocket: could not find the socket";
        v48 = 84;
        v49 = &v37;
        v50 = 4;
        McGenEventWrite_EventWriteTransfer(v21, NcbApiStatus, v22, 3, &UserData);
        LeaveCriticalSection(lpCriticalSection);
LABEL_35:
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          McTemplateU0zq_EventWriteTransfer(a1, v25, L"RpcSrvSBRetrieveSocket: RetrieveSocket failed", v24);
          v7 = v39;
          goto LABEL_39;
        }
LABEL_22:
        v7 = v39;
        goto LABEL_39;
      }
LABEL_34:
      LeaveCriticalSection(lpCriticalSection);
      v11 = v24;
      if ( !v24 )
        goto LABEL_22;
      goto LABEL_35;
    }
    v26 = (*(__int64 (__fastcall **)(struct SharedSocket *, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)Socket + 24LL))(
            Socket,
            ProcessId,
            a5,
            v43);
    v24 = v26;
    if ( v26 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v37 = v26;
        v47 = L"RetrieveSocket: GetDuplicatedSocket failed";
        v48 = 86;
        v49 = &v37;
        v50 = 4;
        McGenEventWrite_EventWriteTransfer(v27, NcbApiStatus, v28, 3, &UserData);
      }
      goto LABEL_32;
    }
    if ( *((_BYTE *)v23 + 112) )
    {
      if ( a5 )
LABEL_32:
        SocketBrokerContext::CleanupSocket(v19, v6);
    }
    else
    {
      (*(void (__fastcall **)(struct SharedSocket *))(*(_QWORD *)v23 + 32LL))(v23);
    }
    (*(void (__fastcall **)(struct SharedSocket *))(*(_QWORD *)v23 + 8LL))(v23);
    goto LABEL_34;
  }
  v11 = 87;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v37 = 87;
    v47 = L"RpcSrvSBRetrieveSocket: invalid parameter";
    v48 = 84;
    v49 = &v37;
    v50 = 4;
    McGenEventWrite_EventWriteTransfer(a1, NcbApiStatus, a3, 3, &UserData);
  }
LABEL_39:
  if ( (unsigned int)dword_18004D068 > 5 )
  {
    v37 = v11;
    v54 = &v37;
    v55 = 4;
    if ( v6 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v6[v29] );
      v30 = 2 * v29 + 2;
    }
    else
    {
      v6 = (const unsigned __int16 *)qword_18003ED50;
      v30 = 2;
    }
    v51 = (void *)v6;
    v52 = v30;
    v53 = 0;
    v49 = (int *)v7;
    v50 = 16;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18004D070;
    UserData.Size = *(unsigned __int16 *)off_18004D070;
    UserData.Reserved = 2;
    v47 = (const wchar_t *)&unk_1800455B0;
    v48 = 0x10000003CLL;
    LODWORD(v39) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    LODWORD(v39) = v11;
    v47 = L"RpcSrvSBRetrieveSocket: completed";
    v48 = 68;
    v49 = (int *)&v39;
    v50 = 4;
    McGenEventWrite_EventWriteTransfer(a1, NcbApiStatus, a3, 3, &UserData);
  }
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  if ( v38 )
    RpcRevertToSelf();
  if ( v9 )
    CloseHandle(v9);
  v32 = (char *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 6, 0xFFFFFFFF) == 1 && v32 )
  {
    SocketBrokerContext::CleanupSockets((SocketBrokerContext *)v32);
    SocketBrokerContext::DeletePushEnableContext((SocketBrokerContext *)v32);
    v33 = (void *)*((_QWORD *)v32 + 6);
    if ( v33 )
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v33);
    }
    *((_QWORD *)v32 + 6) = 0;
    v35 = (void *)*((_QWORD *)v32 + 7);
    if ( v35 )
      CloseHandle(v35);
    DeleteCriticalSection((LPCRITICAL_SECTION)(v32 + 64));
    operator delete(v32);
  }
  if ( v11 > 0 )
    return (unsigned __int16)v11 | 0x80070000;
  else
    return (unsigned int)v11;
}

```

## disassembly

```asm
0x180018d40  push    rbx
0x180018d42  push    rsi
0x180018d43  push    rdi
0x180018d44  push    r12
0x180018d46  push    r13
0x180018d48  push    r14
0x180018d4a  push    r15
0x180018d4c  sub     rsp, 0F0h
0x180018d53  mov     rax, cs:__security_cookie
0x180018d5a  xor     rax, rsp
0x180018d5d  mov     [rsp+128h+var_48], rax
0x180018d65  mov     rbx, r9
0x180018d68  mov     rsi, r8
0x180018d6b  mov     [rsp+128h+var_D8], r8
0x180018d70  mov     rdi, rdx
0x180018d73  mov     rax, [rsp+128h+arg_28]
0x180018d7b  mov     [rsp+128h+var_B8], rax
0x180018d80  xor     r13d, r13d
0x180018d83  mov     [rsp+128h+Block], r13
0x180018d88  mov     r14d, r13d
0x180018d8b  mov     [rsp+128h+Process], r13
0x180018d90  mov     r15d, r13d
0x180018d93  mov     [rsp+128h+lpCriticalSection], r13
0x180018d98  mov     [rsp+128h+var_E0], r13b
0x180018d9d  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180018da4  test    r8, r8
0x180018da7  jz      loc_180019192
0x180018dad  test    rbx, rbx
0x180018db0  jz      loc_180019192
0x180018db6  test    rax, rax
0x180018db9  jz      loc_180019192
0x180018dbf  mov     eax, cs:dword_18004D068
0x180018dc5  cmp     eax, 5
0x180018dc8  jbe     short loc_180018E10
0x180018dca  movzx   eax, [rsp+128h+arg_20]
0x180018dd2  mov     [rsp+128h+var_E8], eax
0x180018dd6  mov     [rsp+128h+var_A0], rbx
0x180018dde  mov     qword ptr [rsp+128h+EventDescriptor.Id], r8
0x180018de3  lea     rax, [rsp+128h+var_E8]
0x180018de8  mov     [rsp+128h+var_F8], rax
0x180018ded  lea     rax, [rsp+128h+var_A0]
0x180018df5  mov     [rsp+128h+UserData], rax
0x180018dfa  lea     rax, [rsp+128h+EventDescriptor]
0x180018dff  mov     qword ptr [rsp+128h+UserDataCount], rax
0x180018e04  lea     rdx, dword_1800454CC
0x180018e0b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180018e10  lea     rax, [rsp+128h+Process]
0x180018e15  mov     [rsp+128h+UserData], rax; void **
0x180018e1a  lea     rax, [rsp+128h+Block]
0x180018e1f  mov     qword ptr [rsp+128h+UserDataCount], rax; struct SocketBrokerContext **
0x180018e24  lea     r9, [rsp+128h+lpCriticalSection]; unsigned __int16 **
0x180018e29  lea     r8, [rsp+128h+var_E0]; bool *
0x180018e2e  mov     rcx, rdi; unsigned __int16 *
0x180018e31  call    ?RpcHelperRetriveSbContext@@YAKPEBGPEAU_GUID@@PEA_NPEAPEAGPEAPEAVSocketBrokerContext@@PEAPEAX@Z; RpcHelperRetriveSbContext(ushort const *,_GUID *,bool *,ushort * *,SocketBrokerContext * *,void * *)
0x180018e36  mov     edi, eax
0x180018e38  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180018e3e  mov     r15, [rsp+128h+lpCriticalSection]
0x180018e43  test    al, 1
0x180018e45  jz      loc_180018EF2
0x180018e4b  mov     [rsp+128h+var_88], rsi
0x180018e53  mov     [rsp+128h+var_80], 10h
0x180018e5f  mov     rax, r12
0x180018e62  lea     rax, [rax+1]
0x180018e66  cmp     [rbx+rax*2], r13w
0x180018e6b  jnz     short loc_180018E62
0x180018e6d  lea     eax, ds:2[rax*2]
0x180018e74  mov     [rsp+128h+var_78], rbx
0x180018e7c  mov     dword ptr [rsp+128h+var_70], eax
0x180018e83  mov     dword ptr [rsp+128h+var_70+4], r13d
0x180018e8b  test    r15, r15
0x180018e8e  jz      short loc_180018EAA
0x180018e90  mov     rax, r12
0x180018e93  lea     rax, [rax+1]
0x180018e97  cmp     [r15+rax*2], r13w
0x180018e9c  jnz     short loc_180018E93
0x180018e9e  lea     eax, ds:2[rax*2]
0x180018ea5  mov     rcx, r15
0x180018ea8  jmp     short loc_180018EB6
0x180018eaa  mov     eax, 0Ah
0x180018eaf  lea     rcx, aNull_1; "NULL"
0x180018eb6  mov     [rsp+128h+var_68], rcx
0x180018ebe  mov     [rsp+128h+var_60], eax
0x180018ec5  mov     [rsp+128h+var_5C], r13d
0x180018ecd  lea     rax, [rsp+128h+var_98]
0x180018ed5  mov     qword ptr [rsp+128h+UserDataCount], rax
0x180018eda  mov     r9d, 4
0x180018ee0  lea     rdx, SbRetrieveSocket
0x180018ee7  call    McGenEventWrite_EventWriteTransfer
0x180018eec  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180018ef2  test    edi, edi
0x180018ef4  jz      short loc_180018F5B
0x180018ef6  test    al, 1
0x180018ef8  jz      short loc_180018F51
0x180018efa  mov     [rsp+128h+var_E8], edi
0x180018efe  lea     rax, aRpcsrvsbretrie; "RpcSrvSBRetrieveSocket: RpcHelperRetriv"...
0x180018f05  mov     [rsp+128h+var_88], rax
0x180018f0d  mov     [rsp+128h+var_80], 72h ; 'r'
0x180018f19  lea     rax, [rsp+128h+var_E8]
0x180018f1e  mov     [rsp+128h+var_78], rax
0x180018f26  mov     [rsp+128h+var_70], 4
0x180018f32  lea     rax, [rsp+128h+var_98]
0x180018f3a  mov     qword ptr [rsp+128h+UserDataCount], rax
0x180018f3f  mov     r9d, 3
0x180018f45  lea     rdx, NcbApiStatus
0x180018f4c  call    McGenEventWrite_EventWriteTransfer
0x180018f51  mov     r14, [rsp+128h+Process]
0x180018f56  jmp     loc_1800191F7
0x180018f5b  mov     r14, [rsp+128h+Process]
0x180018f60  mov     rcx, r14; Process
0x180018f63  call    cs:__imp_GetProcessId
0x180018f69  mov     esi, eax
0x180018f6b  test    eax, eax
0x180018f6d  jnz     short loc_180018FE1
0x180018f6f  call    cs:__imp_GetLastError
0x180018f75  mov     edi, eax
0x180018f77  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180018f7e  jz      short loc_180018FD7
0x180018f80  mov     [rsp+128h+var_E8], eax
0x180018f84  lea     rax, aFailedToGetPro_1; "Failed to get Process ID"
0x180018f8b  mov     [rsp+128h+var_88], rax
0x180018f93  mov     [rsp+128h+var_80], 32h ; '2'
0x180018f9f  lea     rax, [rsp+128h+var_E8]
0x180018fa4  mov     [rsp+128h+var_78], rax
0x180018fac  mov     [rsp+128h+var_70], 4
0x180018fb8  lea     rax, [rsp+128h+var_98]
0x180018fc0  mov     qword ptr [rsp+128h+UserDataCount], rax
0x180018fc5  mov     r9d, 3
0x180018fcb  lea     rdx, NcbApiStatus
0x180018fd2  call    McGenEventWrite_EventWriteTransfer
0x180018fd7  mov     rsi, [rsp+128h+var_D8]
0x180018fdc  jmp     loc_1800191F7
0x180018fe1  mov     r13, [rsp+128h+Block]
0x180018fe6  lea     rax, [r13+40h]
0x180018fea  mov     [rsp+128h+lpCriticalSection], rax
0x180018fef  mov     rcx, rax; lpCriticalSection
0x180018ff2  call    cs:__imp_EnterCriticalSection
0x180018ff8  mov     rax, [rsp+128h+var_B8]
0x180018ffd  mov     qword ptr [rax], 0
0x180019004  mov     rdx, rbx; unsigned __int16 *
0x180019007  mov     rcx, r13; this
0x18001900a  call    ?FindSocket@SocketBrokerContext@@AEAAPEAVSharedSocket@@PEBG@Z; SocketBrokerContext::FindSocket(ushort const *)
0x18001900f  mov     rdi, rax
0x180019012  test    rax, rax
0x180019015  jnz     short loc_180019095
0x180019017  mov     edi, 10D8h
0x18001901c  mov     esi, edi
0x18001901e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180019025  jz      loc_180019157
0x18001902b  mov     [rsp+128h+var_E8], edi
0x18001902f  lea     rax, aRetrievesocket_1; "RetrieveSocket: could not find the sock"...
0x180019036  mov     [rsp+128h+var_88], rax
0x18001903e  mov     [rsp+128h+var_80], 54h ; 'T'
0x18001904a  xor     r13d, r13d
0x18001904d  lea     rax, [rsp+128h+var_E8]
0x180019052  mov     [rsp+128h+var_78], rax
0x18001905a  mov     [rsp+128h+var_70], 4
0x180019066  lea     rax, [rsp+128h+var_98]
0x18001906e  mov     qword ptr [rsp+128h+UserDataCount], rax
0x180019073  mov     r9d, 3
0x180019079  lea     rdx, NcbApiStatus
0x180019080  call    McGenEventWrite_EventWriteTransfer
0x180019085  mov     rcx, [rsp+128h+lpCriticalSection]; lpCriticalSection
0x18001908a  call    cs:__imp_LeaveCriticalSection
0x180019090  jmp     loc_18001916F
0x180019095  mov     rax, [rax]
0x180019098  mov     r9, [rsp+128h+var_B8]
0x18001909d  movzx   r8d, [rsp+128h+arg_20]
0x1800190a6  mov     edx, esi
0x1800190a8  mov     rcx, rdi
0x1800190ab  mov     rax, [rax+18h]
0x1800190af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190b4  mov     esi, eax
0x1800190b6  test    eax, eax
0x1800190b8  jz      short loc_18001911C
0x1800190ba  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800190c1  jz      short loc_18001913D
0x1800190c3  mov     [rsp+128h+var_E8], eax
0x1800190c7  lea     rax, aRetrievesocket; "RetrieveSocket: GetDuplicatedSocket fai"...
0x1800190ce  mov     [rsp+128h+var_88], rax
0x1800190d6  mov     [rsp+128h+var_80], 56h ; 'V'
0x1800190e2  lea     rax, [rsp+128h+var_E8]
0x1800190e7  mov     [rsp+128h+var_78], rax
0x1800190ef  mov     [rsp+128h+var_70], 4
0x1800190fb  lea     rax, [rsp+128h+var_98]
0x180019103  mov     qword ptr [rsp+128h+UserDataCount], rax
0x180019108  mov     r9d, 3
0x18001910e  lea     rdx, NcbApiStatus
0x180019115  call    McGenEventWrite_EventWriteTransfer
0x18001911a  jmp     short loc_18001913D
0x18001911c  cmp     byte ptr [rdi+70h], 0
0x180019120  jnz     short loc_180019133
0x180019122  mov     rax, [rdi]
0x180019125  mov     rcx, rdi
0x180019128  mov     rax, [rax+20h]
0x18001912c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019131  jmp     short loc_180019148
0x180019133  cmp     [rsp+128h+arg_20], 0
0x18001913b  jz      short loc_180019148
0x18001913d  mov     rdx, rbx; unsigned __int16 *
0x180019140  mov     rcx, r13; this
0x180019143  call    ?CleanupSocket@SocketBrokerContext@@AEAAXPEBG@Z; SocketBrokerContext::CleanupSocket(ushort const *)
0x180019148  mov     rax, [rdi]
0x18001914b  mov     rcx, rdi
0x18001914e  mov     rax, [rax+8]
0x180019152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019157  mov     rcx, [rsp+128h+lpCriticalSection]; lpCriticalSection
0x18001915c  call    cs:__imp_LeaveCriticalSection
0x180019162  mov     edi, esi
0x180019164  xor     r13d, r13d
0x180019167  test    esi, esi
0x180019169  jz      loc_180018FD7
0x18001916f  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180019176  jz      loc_180018FD7
0x18001917c  mov     r9d, esi
0x18001917f  lea     r8, aRpcsrvsbretrie_4; "RpcSrvSBRetrieveSocket: RetrieveSocket "...
0x180019186  call    McTemplateU0zq_EventWriteTransfer
0x18001918b  mov     rsi, [rsp+128h+var_D8]
0x180019190  jmp     short loc_1800191F7
0x180019192  mov     edi, 57h ; 'W'
0x180019197  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001919e  jz      short loc_1800191F7
0x1800191a0  mov     [rsp+128h+var_E8], edi
0x1800191a4  lea     rax, aRpcsrvsbretrie_3; "RpcSrvSBRetrieveSocket: invalid paramet"...
0x1800191ab  mov     [rsp+128h+var_88], rax
0x1800191b3  mov     [rsp+128h+var_80], 54h ; 'T'
0x1800191bf  lea     rax, [rsp+128h+var_E8]
0x1800191c4  mov     [rsp+128h+var_78], rax
0x1800191cc  mov     [rsp+128h+var_70], 4
0x1800191d8  lea     rax, [rsp+128h+var_98]
0x1800191e0  mov     qword ptr [rsp+128h+UserDataCount], rax
0x1800191e5  mov     r9d, 3
0x1800191eb  lea     rdx, NcbApiStatus
0x1800191f2  call    McGenEventWrite_EventWriteTransfer
0x1800191f7  mov     eax, cs:dword_18004D068
0x1800191fd  cmp     eax, 5
0x180019200  jbe     loc_180019324
0x180019206  mov     [rsp+128h+var_E8], edi
0x18001920a  lea     rax, [rsp+128h+var_E8]
0x18001920f  mov     [rsp+128h+var_58], rax
0x180019217  mov     [rsp+128h+var_50], 4
0x180019223  test    rbx, rbx
0x180019226  jz      short loc_180019244
0x180019228  mov     rax, r12
0x18001922b  nop     dword ptr [rax+rax+00h]
0x180019230  lea     rax, [rax+1]
0x180019234  cmp     word ptr [rbx+rax*2], 0
0x180019239  jnz     short loc_180019230
0x18001923b  lea     eax, ds:2[rax*2]
0x180019242  jmp     short loc_180019250
0x180019244  lea     rbx, qword_18003ED50
0x18001924b  mov     eax, 2
0x180019250  mov     [rsp+128h+var_68], rbx
0x180019258  mov     [rsp+128h+var_60], eax
0x18001925f  mov     [rsp+128h+var_5C], r13d
0x180019267  mov     [rsp+128h+var_78], rsi
0x18001926f  mov     [rsp+128h+var_70], 10h
0x18001927b  mov     dword ptr [rsp+128h+EventDescriptor.Id], 0B000000h
0x180019283  movzx   eax, cs:word_1800455A6
0x18001928a  mov     dword ptr [rsp+128h+EventDescriptor.Level], eax
0x18001928e  mov     [rsp+128h+EventDescriptor.Keyword], r13
0x180019296  mov     rax, cs:off_18004D070
0x18001929d  mov     [rsp+128h+var_98.Ptr], rax
0x1800192a5  movzx   eax, word ptr [rax]
0x1800192a8  mov     [rsp+128h+var_98.Size], eax
0x1800192af  mov     dword ptr [rsp+128h+var_98.0Ch], 2
0x1800192ba  lea     rax, unk_1800455B0
0x1800192c1  mov     [rsp+128h+var_88], rax
0x1800192c9  mov     dword ptr [rsp+128h+var_80], 3Ch ; '<'
0x1800192d4  mov     dword ptr [rsp+128h+var_80+4], 1
0x1800192df  lea     rax, _TraceLoggingMetadataEnd
0x1800192e6  lea     rcx, _TraceLoggingMetadata
0x1800192ed  sub     eax, ecx
0x1800192ef  mov     dword ptr [rsp+128h+var_D8], eax
0x1800192f3  mov     eax, dword ptr [rsp+128h+var_D8]
0x1800192f7  lea     rax, [rsp+128h+var_98]
0x1800192ff  mov     [rsp+128h+UserData], rax; UserData
0x180019304  mov     [rsp+128h+UserDataCount], 5; UserDataCount
0x18001930c  xor     r9d, r9d; RelatedActivityId
0x18001930f  xor     r8d, r8d; ActivityId
0x180019312  lea     rdx, [rsp+128h+EventDescriptor]; EventDescriptor
0x180019317  mov     rcx, cs:RegHandle; RegHandle
0x18001931e  call    cs:__imp_EventWriteTransfer
0x180019324  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001932b  jz      short loc_180019384
0x18001932d  mov     dword ptr [rsp+128h+var_D8], edi
0x180019331  lea     rax, aRpcsrvsbretrie_1; "RpcSrvSBRetrieveSocket: completed"
0x180019338  mov     [rsp+128h+var_88], rax
0x180019340  mov     [rsp+128h+var_80], 44h ; 'D'
0x18001934c  lea     rax, [rsp+128h+var_D8]
0x180019351  mov     [rsp+128h+var_78], rax
0x180019359  mov     [rsp+128h+var_70], 4
0x180019365  lea     rax, [rsp+128h+var_98]
0x18001936d  mov     qword ptr [rsp+128h+UserDataCount], rax
0x180019372  mov     r9d, 3
0x180019378  lea     rdx, NcbApiStatus
0x18001937f  call    McGenEventWrite_EventWriteTransfer
0x180019384  test    r15, r15
0x180019387  jz      short loc_18001939D
0x180019389  call    cs:__imp_GetProcessHeap
0x18001938f  mov     rcx, rax; hHeap
  ... truncated ...
```
