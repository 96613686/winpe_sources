# CTSSession::CCommonSessionData::Start(ICsrEventSink *,ushort const *)

- ea: `0x18007249c`
- end: `0x180072639`
- name: `?Start@CCommonSessionData@CTSSession@@QEAAJPEAVICsrEventSink@@PEBG@Z`
- size: `413`
- prototype: `__int64 __fastcall(CTSSession::CCommonSessionData *__hidden this, struct ICsrEventSink *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180072640`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x18002701c`
- `0x18002c2c4`
- `0x18004e850`
- `0x18004f3c0`
- `0x18007249c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800725ee`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800725ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072602`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072602`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180072543`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180072543`

## string_xrefs

- `0x1800724f8`: `CTSSession::CCommonSessionData::Start`
- `0x180072578`: `Failed to write activity id to initial command args`

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
      else if ( (unsigned int)dword_1800DF020 > 2 )
      {
        v16 = "Failed to write activity id to initial command args";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v9,
          (unsigned int)&byte_1800C8D0F,
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
0x18007249c  push    rbp
0x18007249e  push    rbx
0x18007249f  push    rsi
0x1800724a0  push    rdi
0x1800724a1  push    r14
0x1800724a3  lea     rbp, [rsp-200h]
0x1800724ab  sub     rsp, 300h
0x1800724b2  mov     rax, cs:__security_cookie
0x1800724b9  xor     rax, rsp
0x1800724bc  mov     [rbp+220h+var_30], rax
0x1800724c3  mov     rdi, r8
0x1800724c6  mov     r14, rdx
0x1800724c9  mov     rsi, rcx
0x1800724cc  mov     [rsp+320h+var_2D8], 0
0x1800724d5  mov     [rsp+320h+Process], 0
0x1800724de  lea     rcx, [rsp+320h+var_2D8]; struct ICsrMgr **
0x1800724e3  call    ?GetInstanceOfCsrMgr@ICsrMgr@@SAJPEAPEAV1@@Z; ICsrMgr::GetInstanceOfCsrMgr(ICsrMgr * *)
0x1800724e8  mov     ebx, eax
0x1800724ea  test    eax, eax
0x1800724ec  jns     short loc_18007250E
0x1800724ee  lea     rdx, aIcsrmgrGetinst_0; "ICsrMgr::GetInstanceOfCsrMgr failed: 0x"...
0x1800724f5  mov     r8d, eax
0x1800724f8  lea     r9, aCtssessionCcom_1; "CTSSession::CCommonSessionData::Start"
0x1800724ff  mov     ecx, 8; int
0x180072504  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180072509  jmp     loc_18007260F
0x18007250e  mov     rbx, [rsp+320h+var_2D8]
0x180072513  test    rdi, rdi
0x180072516  jnz     loc_1800725A0
0x18007251c  mov     rax, [rbx]
0x18007251f  mov     rcx, rbx
0x180072522  mov     rax, [rax+30h]
0x180072526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007252b  test    eax, eax
0x18007252d  jnz     short loc_1800725A0
0x18007252f  mov     rcx, [rsi+8]
0x180072533  add     rcx, 0C88h; rguid
0x18007253a  lea     r8d, [rdi+40h]; cchMax
0x18007253e  lea     rdx, [rsp+320h+sz]; lpsz
0x180072543  call    cs:__imp_StringFromGUID2
0x18007254a  nop     dword ptr [rax+rax+00h]
0x18007254f  lea     r9, [rsp+320h+sz]
0x180072554  lea     r8, aWinlogonExeS; "winlogon.exe %s"
0x18007255b  mov     edx, 104h; BufferCount
0x180072560  lea     rcx, [rbp+220h+Buffer]; Buffer
0x180072564  call    swprintf_s
0x180072569  test    eax, eax
0x18007256b  jns     short loc_18007259C
0x18007256d  mov     eax, cs:dword_1800DF020
0x180072573  cmp     eax, 2
0x180072576  jbe     short loc_1800725A0
0x180072578  lea     rax, aFailedToWriteA; "Failed to write activity id to initial "...
0x18007257f  mov     [rsp+320h+var_2D0], rax
0x180072584  lea     rax, [rsp+320h+var_2D0]
0x180072589  mov     [rsp+320h+var_300], rax
0x18007258e  lea     rdx, byte_1800C8D0F
0x180072595  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007259a  jmp     short loc_1800725A0
0x18007259c  lea     rdi, [rbp+220h+Buffer]
0x1800725a0  mov     rax, [rbx]
0x1800725a3  lea     rcx, [rsi+38h]
0x1800725a7  lea     r9, [rsi+18h]
0x1800725ab  lea     rdx, [rsi+10h]
0x1800725af  mov     [rsp+320h+var_2F0], r14
0x1800725b4  mov     [rsp+320h+var_2F8], rcx
0x1800725b9  lea     rcx, [rsp+320h+Process]
0x1800725be  mov     [rsp+320h+var_300], rcx
0x1800725c3  mov     r8, rdi
0x1800725c6  mov     rcx, rbx
0x1800725c9  mov     rax, [rax+18h]
0x1800725cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725d2  mov     ebx, eax
0x1800725d4  test    eax, eax
0x1800725d6  jns     short loc_1800725E4
0x1800725d8  lea     rdx, aCsrmgrStartcsr; "CsrMgr->StartCsr failed: 0x%x in %s"
0x1800725df  jmp     loc_1800724F5
0x1800725e4  mov     rcx, [rsp+320h+Process]; Process
0x1800725e9  test    rcx, rcx
0x1800725ec  jz      short loc_18007260F
0x1800725ee  call    cs:__imp_GetProcessId
0x1800725f5  nop     dword ptr [rax+rax+00h]
0x1800725fa  mov     [rsi+20h], eax
0x1800725fd  mov     rcx, [rsp+320h+Process]; hObject
0x180072602  call    cs:__imp_CloseHandle
0x180072609  nop     dword ptr [rax+rax+00h]
0x18007260e  nop
0x18007260f  lea     rcx, [rsp+320h+var_2D8]
0x180072614  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180072619  mov     eax, ebx
0x18007261b  mov     rcx, [rbp+220h+var_30]
0x180072622  xor     rcx, rsp; StackCookie
0x180072625  call    __security_check_cookie
0x18007262a  add     rsp, 300h
0x180072631  pop     r14
0x180072633  pop     rdi
0x180072634  pop     rsi
0x180072635  pop     rbx
0x180072636  pop     rbp
0x180072637  retn
```
