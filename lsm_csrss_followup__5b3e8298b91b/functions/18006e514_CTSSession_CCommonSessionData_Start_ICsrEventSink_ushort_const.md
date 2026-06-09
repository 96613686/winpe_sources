# CTSSession::CCommonSessionData::Start(ICsrEventSink *,ushort const *)

- ea: `0x18006e514`
- end: `0x18006e69a`
- name: `?Start@CCommonSessionData@CTSSession@@QEAAJPEAVICsrEventSink@@PEBG@Z`
- size: `390`
- prototype: `__int64 __fastcall(CTSSession::CCommonSessionData *__hidden this, struct ICsrEventSink *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18006e6a0`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180025070`
- `0x18002a2c0`
- `0x18004b460`
- `0x18004bfb0`
- `0x18006e514`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006e65c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006e65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e66a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e66a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006e5b7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006e5b7`

## string_xrefs

- `0x18006e570`: `CTSSession::CCommonSessionData::Start`
- `0x18006e5e6`: `Failed to write activity id to initial command args`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTSSession::CCommonSessionData::Start(
        CTSSession::CCommonSessionData *this,
        struct ICsrEventSink *a2,
        wchar_t *a3)
{
  int InstanceOfCsrMgr; // eax
  unsigned int v7; // ebx
  struct ICsrMgr *v8; // rbx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // eax
  HANDLE Process; // [rsp+40h] [rbp-C0h] BYREF
  struct ICsrMgr *v15; // [rsp+48h] [rbp-B8h] BYREF
  const char *v16; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz[64]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  v15 = 0;
  Process = 0;
  InstanceOfCsrMgr = ICsrMgr::GetInstanceOfCsrMgr(&v15);
  v7 = InstanceOfCsrMgr;
  if ( InstanceOfCsrMgr >= 0 )
  {
    v8 = v15;
    if ( !a3 && !(*(unsigned int (__fastcall **)(struct ICsrMgr *))(*(_QWORD *)v15 + 48LL))(v15) )
    {
      StringFromGUID2((const GUID *const)(*((_QWORD *)this + 1) + 3208LL), sz, 64);
      if ( swprintf_s(Buffer, 0x104u, L"winlogon.exe %s", sz) >= 0 )
      {
        a3 = Buffer;
      }
      else if ( (unsigned int)dword_1800DA020 > 2 )
      {
        v16 = "Failed to write activity id to initial command args";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v9,
          (unsigned int)&byte_1800C3B87,
          v10,
          v11,
          (__int64)&v16);
      }
    }
    v12 = (*(__int64 (__fastcall **)(struct ICsrMgr *, char *, wchar_t *, char *, HANDLE *, char *, struct ICsrEventSink *))(*(_QWORD *)v8 + 24LL))(
            v8,
            (char *)this + 16,
            a3,
            (char *)this + 24,
            &Process,
            (char *)this + 56,
            a2);
    v7 = v12;
    if ( v12 >= 0 )
    {
      if ( Process )
      {
        *((_DWORD *)this + 8) = GetProcessId(Process);
        CloseHandle(Process);
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CsrMgr->StartCsr failed: 0x%x in %s",
        (unsigned int)v12,
        "CTSSession::CCommonSessionData::Start");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "ICsrMgr::GetInstanceOfCsrMgr failed: 0x%x in %s",
      (unsigned int)InstanceOfCsrMgr,
      "CTSSession::CCommonSessionData::Start");
  }
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v15);
  return v7;
}

```

## disassembly

```asm
0x18006e514  push    rbp
0x18006e516  push    rbx
0x18006e517  push    rsi
0x18006e518  push    rdi
0x18006e519  push    r14
0x18006e51b  lea     rbp, [rsp-200h]
0x18006e523  sub     rsp, 300h
0x18006e52a  mov     rax, cs:__security_cookie
0x18006e531  xor     rax, rsp
0x18006e534  mov     [rbp+220h+var_30], rax
0x18006e53b  mov     rdi, r8
0x18006e53e  mov     r14, rdx
0x18006e541  mov     rsi, rcx
0x18006e544  mov     [rsp+320h+var_2D8], 0
0x18006e54d  mov     [rsp+320h+Process], 0
0x18006e556  lea     rcx, [rsp+320h+var_2D8]; struct ICsrMgr **
0x18006e55b  call    ?GetInstanceOfCsrMgr@ICsrMgr@@SAJPEAPEAV1@@Z; ICsrMgr::GetInstanceOfCsrMgr(ICsrMgr * *)
0x18006e560  mov     ebx, eax
0x18006e562  test    eax, eax
0x18006e564  jns     short loc_18006E586
0x18006e566  lea     rdx, aIcsrmgrGetinst_0; "ICsrMgr::GetInstanceOfCsrMgr failed: 0x"...
0x18006e56d  mov     r8d, eax
0x18006e570  lea     r9, aCtssessionCcom_1; "CTSSession::CCommonSessionData::Start"
0x18006e577  mov     ecx, 8; int
0x18006e57c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e581  jmp     loc_18006E671
0x18006e586  mov     rbx, [rsp+320h+var_2D8]
0x18006e58b  test    rdi, rdi
0x18006e58e  jnz     short loc_18006E60E
0x18006e590  mov     rax, [rbx]
0x18006e593  mov     rcx, rbx
0x18006e596  mov     rax, [rax+30h]
0x18006e59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e59f  test    eax, eax
0x18006e5a1  jnz     short loc_18006E60E
0x18006e5a3  mov     rcx, [rsi+8]
0x18006e5a7  add     rcx, 0C88h; rguid
0x18006e5ae  lea     r8d, [rdi+40h]; cchMax
0x18006e5b2  lea     rdx, [rsp+320h+sz]; lpsz
0x18006e5b7  call    cs:__imp_StringFromGUID2
0x18006e5bd  lea     r9, [rsp+320h+sz]
0x18006e5c2  lea     r8, aWinlogonExeS; "winlogon.exe %s"
0x18006e5c9  mov     edx, 104h; BufferCount
0x18006e5ce  lea     rcx, [rbp+220h+Buffer]; Buffer
0x18006e5d2  call    swprintf_s
0x18006e5d7  test    eax, eax
0x18006e5d9  jns     short loc_18006E60A
0x18006e5db  mov     eax, cs:dword_1800DA020
0x18006e5e1  cmp     eax, 2
0x18006e5e4  jbe     short loc_18006E60E
0x18006e5e6  lea     rax, aFailedToWriteA; "Failed to write activity id to initial "...
0x18006e5ed  mov     [rsp+320h+var_2D0], rax
0x18006e5f2  lea     rax, [rsp+320h+var_2D0]
0x18006e5f7  mov     [rsp+320h+var_300], rax
0x18006e5fc  lea     rdx, byte_1800C3B87
0x18006e603  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006e608  jmp     short loc_18006E60E
0x18006e60a  lea     rdi, [rbp+220h+Buffer]
0x18006e60e  mov     rax, [rbx]
0x18006e611  lea     rcx, [rsi+38h]
0x18006e615  lea     r9, [rsi+18h]
0x18006e619  lea     rdx, [rsi+10h]
0x18006e61d  mov     [rsp+320h+var_2F0], r14
0x18006e622  mov     [rsp+320h+var_2F8], rcx
0x18006e627  lea     rcx, [rsp+320h+Process]
0x18006e62c  mov     [rsp+320h+var_300], rcx
0x18006e631  mov     r8, rdi
0x18006e634  mov     rcx, rbx
0x18006e637  mov     rax, [rax+18h]
0x18006e63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e640  mov     ebx, eax
0x18006e642  test    eax, eax
0x18006e644  jns     short loc_18006E652
0x18006e646  lea     rdx, aCsrmgrStartcsr; "CsrMgr->StartCsr failed: 0x%x in %s"
0x18006e64d  jmp     loc_18006E56D
0x18006e652  mov     rcx, [rsp+320h+Process]; Process
0x18006e657  test    rcx, rcx
0x18006e65a  jz      short loc_18006E671
0x18006e65c  call    cs:__imp_GetProcessId
0x18006e662  mov     [rsi+20h], eax
0x18006e665  mov     rcx, [rsp+320h+Process]; hObject
0x18006e66a  call    cs:__imp_CloseHandle
0x18006e670  nop
0x18006e671  lea     rcx, [rsp+320h+var_2D8]
0x18006e676  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006e67b  mov     eax, ebx
0x18006e67d  mov     rcx, [rbp+220h+var_30]
0x18006e684  xor     rcx, rsp; StackCookie
0x18006e687  call    __security_check_cookie
0x18006e68c  add     rsp, 300h
0x18006e693  pop     r14
0x18006e695  pop     rdi
0x18006e696  pop     rsi
0x18006e697  pop     rbx
0x18006e698  pop     rbp
0x18006e699  retn
```
