# LogArbitrationForSession(int,void *)

- ea: `0x18002f650`
- end: `0x18002f9f3`
- name: `?LogArbitrationForSession@@YAJHPEAX@Z`
- size: `931`
- prototype: `int(int, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fa00`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180009dd0`
- `0x18000a5d0`
- `0x180014ff0`
- `0x180018200`
- `0x18001f544`
- `0x18002668c`
- `0x18002f650`
- `0x18004b460`
- `0x180097010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18002f8ab`
- `ntdll!EtwEventActivityIdControl` at `0x18002f8ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f9c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f9c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f97a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f98a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f97a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f98a`

## string_xrefs

- `0x18002f6e2`: `DuplicateClientToken failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LogArbitrationForSession(int a1, void *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int InstanceOfUserName; // eax
  struct IUserName *v6; // rdi
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int InstanceOfSessionManagerInternal; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  struct ISessionManagerInternal *v21; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, __int64 *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  struct IUserName *v28; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v29; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v30; // [rsp+90h] [rbp-70h] BYREF
  struct ISessionManagerInternal *v31; // [rsp+98h] [rbp-68h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v33[264]; // [rsp+B0h] [rbp-50h] BYREF

  pv = 0;
  v23 = 0;
  v28 = 0;
  v20 = 0;
  v32 = 0;
  hObject = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v31 = 0;
  v3 = CRpcUtils::DuplicateClientToken(a2, &hObject);
  v4 = v3;
  if ( v3 >= 0 )
  {
    InstanceOfUserName = CUtils::GetInstanceOfUserName(&v28);
    v4 = InstanceOfUserName;
    if ( InstanceOfUserName >= 0 )
    {
      v6 = v28;
      v7 = (*(__int64 (__fastcall **)(struct IUserName *, HANDLE, __int64))(*(_QWORD *)v28 + 24LL))(v28, hObject, 1);
      v4 = v7;
      if ( v7 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)v6 + 40LL))(v6, &pv);
        v4 = v8;
        if ( v8 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)v6 + 48LL))(v6, &v23);
          v4 = v9;
          if ( v9 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(struct IUserName *, unsigned int *))(*(_QWORD *)v6 + 112LL))(v6, &v20);
            v4 = v10;
            if ( v10 >= 0 )
            {
              v21 = 0;
              InstanceOfSessionManagerInternal = ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v21);
              v4 = InstanceOfSessionManagerInternal;
              v31 = v21;
              if ( InstanceOfSessionManagerInternal >= 0 )
              {
                v12 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v21 + 24LL))(
                        v21,
                        &v26);
                v4 = v12;
                if ( v12 >= 0 )
                {
                  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v26 + 24LL))(v26, v20, &v25);
                  v4 = v13;
                  if ( v13 >= 0 )
                  {
                    v14 = (**v25)(v25, qword_1800A2D40, &v24);
                    v4 = v14;
                    if ( v14 >= 0 )
                    {
                      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v24 + 584LL))(v24, &v32);
                      v4 = StringCchPrintfW(v33, 0x104u, L"%s\\%s", v23, pv);
                      EtwEventActivityIdControl(2, &v32);
                      v15 = EVENT_SESSION_ARBITRATION_BEGIN;
                      if ( !a1 )
                        v15 = EVENT_SESSION_ARBITRATION_END;
                      CrimsonHelper::RaiseEvent<unsigned short *,long>(
                        (CrimsonHelper *)&CrimsonHelper::s_instance,
                        (const struct _EVENT_DESCRIPTOR *)v15,
                        (ULONGLONG)v33,
                        v20);
                      if ( a1 )
                      {
                        if ( (unsigned int)dword_1800DA020 > 4 )
                        {
                          v29 = v33;
                          LODWORD(v21) = v20;
                          v30 = (unsigned __int16 *)"Session Arbitration started";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                            v16,
                            (int)byte_1800C1199,
                            v17,
                            v18,
                            (const unsigned __int16 **)&v30,
                            (__int64)&v21,
                            (__int64 **)&v29);
                        }
                      }
                      else if ( (unsigned int)dword_1800DA020 > 4 )
                      {
                        v30 = v33;
                        LODWORD(v21) = v20;
                        v29 = (unsigned __int16 *)"Session Arbitration ended";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                          v16,
                          (int)&word_1800C1156,
                          v17,
                          v18,
                          (const unsigned __int16 **)&v29,
                          (__int64)&v21,
                          (__int64 **)&v30);
                      }
                    }
                    else
                    {
                      _DbgPrintMessage(
                        4,
                        "Getting IID_ITSSessionPrivate failed: 0x%x in %s",
                        (unsigned int)v14,
                        "LogArbitrationForSession");
                    }
                  }
                  else
                  {
                    _DbgPrintMessage(
                      4,
                      "FindSessionById failed: 0x%x in %s",
                      (unsigned int)v13,
                      "LogArbitrationForSession");
                  }
                }
                else
                {
                  _DbgPrintMessage(
                    4,
                    "GetSessionList failed: 0x%x in %s",
                    (unsigned int)v12,
                    "LogArbitrationForSession");
                }
              }
              else
              {
                _DbgPrintMessage(
                  4,
                  "GetInstanceOfSessionManager failed: 0x%x in %s",
                  (unsigned int)InstanceOfSessionManagerInternal,
                  "LogArbitrationForSession");
              }
            }
            else
            {
              _DbgPrintMessage(
                4,
                "Geting user session failed: 0x%x in %s",
                (unsigned int)v10,
                "LogArbitrationForSession");
            }
          }
          else
          {
            _DbgPrintMessage(4, "Geting user domain failed: 0x%x in %s", (unsigned int)v9, "LogArbitrationForSession");
          }
        }
        else
        {
          _DbgPrintMessage(4, "Geting user name failed: 0x%x in %s", (unsigned int)v8, "LogArbitrationForSession");
        }
      }
      else
      {
        _DbgPrintMessage(4, "ptrUserName->Initialize failed: 0x%x in %s", (unsigned int)v7, "LogArbitrationForSession");
      }
    }
    else
    {
      _DbgPrintMessage(
        4,
        "CUtils::GetInstanceOfUserName failed: 0x%x in %s",
        (unsigned int)InstanceOfUserName,
        "LogArbitrationForSession");
    }
  }
  else
  {
    _DbgPrintMessage(4, "DuplicateClientToken failed: 0x%x in %s", (unsigned int)v3, "LogArbitrationForSession");
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v23 )
    CoTaskMemFree(v23);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((__int64 *)&v31);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v24);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((__int64 *)&v25);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v26);
  if ( hObject )
    CloseHandle(hObject);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((__int64 *)&v28);
  return v4;
}

```

## disassembly

```asm
0x18002f650  push    rbp
0x18002f652  push    rbx
0x18002f653  push    rsi
0x18002f654  push    rdi
0x18002f655  lea     rbp, [rsp-1D8h]
0x18002f65d  sub     rsp, 2D8h
0x18002f664  mov     rax, cs:__security_cookie
0x18002f66b  xor     rax, rsp
0x18002f66e  mov     [rbp+1F0h+var_30], rax
0x18002f675  mov     rax, rdx
0x18002f678  mov     esi, ecx
0x18002f67a  mov     [rsp+2F0h+pv], 0
0x18002f683  mov     [rsp+2F0h+var_298], 0
0x18002f68c  mov     [rbp+1F0h+var_270], 0
0x18002f694  mov     [rsp+2F0h+var_2B0], 0
0x18002f69c  xorps   xmm0, xmm0
0x18002f69f  movups  [rbp+1F0h+var_250], xmm0
0x18002f6a3  mov     [rsp+2F0h+hObject], 0
0x18002f6ac  mov     [rsp+2F0h+var_280], 0
0x18002f6b5  mov     [rsp+2F0h+var_288], 0
0x18002f6be  mov     [rsp+2F0h+var_290], 0
0x18002f6c7  mov     [rbp+1F0h+var_258], 0
0x18002f6cf  lea     rdx, [rsp+2F0h+hObject]; TargetHandle
0x18002f6d4  mov     rcx, rax; SourceHandle
0x18002f6d7  call    ?DuplicateClientToken@CRpcUtils@@SAJPEAXPEAPEAX@Z; CRpcUtils::DuplicateClientToken(void *,void * *)
0x18002f6dc  mov     ebx, eax
0x18002f6de  test    eax, eax
0x18002f6e0  jns     short loc_18002F702
0x18002f6e2  lea     rdx, aDuplicateclien; "DuplicateClientToken failed: 0x%x in %s"
0x18002f6e9  mov     r8d, eax
0x18002f6ec  lea     r9, aLogarbitration; "LogArbitrationForSession"
0x18002f6f3  mov     ecx, 4; int
0x18002f6f8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f6fd  jmp     loc_18002F970
0x18002f702  lea     rcx, [rbp+1F0h+var_270]; struct IUserName **
0x18002f706  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18002f70b  mov     ebx, eax
0x18002f70d  test    eax, eax
0x18002f70f  jns     short loc_18002F71A
0x18002f711  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x18002f718  jmp     short loc_18002F6E9
0x18002f71a  mov     rdi, [rbp+1F0h+var_270]
0x18002f71e  mov     rax, [rdi]
0x18002f721  mov     r8d, 1
0x18002f727  mov     rdx, [rsp+2F0h+hObject]
0x18002f72c  mov     rcx, rdi
0x18002f72f  mov     rax, [rax+18h]
0x18002f733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f738  mov     ebx, eax
0x18002f73a  test    eax, eax
0x18002f73c  jns     short loc_18002F747
0x18002f73e  lea     rdx, aPtrusernameIni; "ptrUserName->Initialize failed: 0x%x in"...
0x18002f745  jmp     short loc_18002F6E9
0x18002f747  mov     rax, [rdi]
0x18002f74a  lea     rdx, [rsp+2F0h+pv]
0x18002f74f  mov     rcx, rdi
0x18002f752  mov     rax, [rax+28h]
0x18002f756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f75b  mov     ebx, eax
0x18002f75d  test    eax, eax
0x18002f75f  jns     short loc_18002F76D
0x18002f761  lea     rdx, aGetingUserName; "Geting user name failed: 0x%x in %s"
0x18002f768  jmp     loc_18002F6E9
0x18002f76d  mov     rax, [rdi]
0x18002f770  lea     rdx, [rsp+2F0h+var_298]
0x18002f775  mov     rcx, rdi
0x18002f778  mov     rax, [rax+30h]
0x18002f77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f781  mov     ebx, eax
0x18002f783  test    eax, eax
0x18002f785  jns     short loc_18002F793
0x18002f787  lea     rdx, aGetingUserDoma; "Geting user domain failed: 0x%x in %s"
0x18002f78e  jmp     loc_18002F6E9
0x18002f793  mov     rax, [rdi]
0x18002f796  lea     rdx, [rsp+2F0h+var_2B0]
0x18002f79b  mov     rcx, rdi
0x18002f79e  mov     rax, [rax+70h]
0x18002f7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7a7  mov     ebx, eax
0x18002f7a9  test    eax, eax
0x18002f7ab  jns     short loc_18002F7B9
0x18002f7ad  lea     rdx, aGetingUserSess; "Geting user session failed: 0x%x in %s"
0x18002f7b4  jmp     loc_18002F6E9
0x18002f7b9  mov     [rsp+2F0h+var_2A8], 0
0x18002f7c2  lea     rcx, [rsp+2F0h+var_2A8]; struct ISessionManagerInternal **
0x18002f7c7  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18002f7cc  mov     ebx, eax
0x18002f7ce  mov     rcx, [rsp+2F0h+var_2A8]
0x18002f7d3  mov     [rbp+1F0h+var_258], rcx
0x18002f7d7  test    eax, eax
0x18002f7d9  jns     short loc_18002F7E7
0x18002f7db  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x18002f7e2  jmp     loc_18002F6E9
0x18002f7e7  mov     rax, [rcx]
0x18002f7ea  lea     rdx, [rsp+2F0h+var_280]
0x18002f7ef  mov     rax, [rax+18h]
0x18002f7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7f8  mov     ebx, eax
0x18002f7fa  test    eax, eax
0x18002f7fc  jns     short loc_18002F80A
0x18002f7fe  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18002f805  jmp     loc_18002F6E9
0x18002f80a  mov     rcx, [rsp+2F0h+var_280]
0x18002f80f  mov     rax, [rcx]
0x18002f812  lea     r8, [rsp+2F0h+var_288]
0x18002f817  mov     edx, [rsp+2F0h+var_2B0]
0x18002f81b  mov     rax, [rax+18h]
0x18002f81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f824  mov     ebx, eax
0x18002f826  test    eax, eax
0x18002f828  jns     short loc_18002F836
0x18002f82a  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x18002f831  jmp     loc_18002F6E9
0x18002f836  mov     rcx, [rsp+2F0h+var_288]
0x18002f83b  mov     rax, [rcx]
0x18002f83e  lea     r8, [rsp+2F0h+var_290]
0x18002f843  lea     rdx, qword_1800A2D40
0x18002f84a  mov     rax, [rax]
0x18002f84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f852  mov     ebx, eax
0x18002f854  test    eax, eax
0x18002f856  jns     short loc_18002F864
0x18002f858  lea     rdx, aGettingIidItss_2; "Getting IID_ITSSessionPrivate failed: 0"...
0x18002f85f  jmp     loc_18002F6E9
0x18002f864  mov     rcx, [rsp+2F0h+var_290]
0x18002f869  mov     rax, [rcx]
0x18002f86c  lea     rdx, [rbp+1F0h+var_250]
0x18002f870  mov     rax, [rax+248h]
0x18002f877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f87c  mov     rax, [rsp+2F0h+pv]
0x18002f881  mov     [rsp+2F0h+var_2D0], rax
0x18002f886  mov     r9, [rsp+2F0h+var_298]
0x18002f88b  lea     r8, aSS_0; "%s\\%s"
0x18002f892  mov     edx, 104h; unsigned __int64
0x18002f897  lea     rcx, [rbp+1F0h+var_240]; unsigned __int16 *
0x18002f89b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f8a0  mov     ebx, eax
0x18002f8a2  lea     rdx, [rbp+1F0h+var_250]
0x18002f8a6  mov     ecx, 2
0x18002f8ab  call    cs:__imp_EtwEventActivityIdControl
0x18002f8b1  lea     rax, EVENT_SESSION_ARBITRATION_END
0x18002f8b8  lea     rdx, EVENT_SESSION_ARBITRATION_BEGIN
0x18002f8bf  test    esi, esi
0x18002f8c1  cmovz   rdx, rax
0x18002f8c5  mov     r9d, [rsp+2F0h+var_2B0]
0x18002f8ca  lea     r8, [rbp+1F0h+var_240]
0x18002f8ce  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18002f8d5  call    ??$RaiseEvent@PEAGJ@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAGJ@Z; CrimsonHelper::RaiseEvent<ushort *,long>(_EVENT_DESCRIPTOR const &,ushort *,long)
0x18002f8da  mov     eax, cs:dword_1800DA020
0x18002f8e0  test    esi, esi
0x18002f8e2  jz      short loc_18002F928
0x18002f8e4  cmp     eax, 4
0x18002f8e7  jbe     loc_18002F970
0x18002f8ed  lea     rax, [rbp+1F0h+var_240]
0x18002f8f1  mov     [rbp+1F0h+var_268], rax
0x18002f8f5  mov     eax, [rsp+2F0h+var_2B0]
0x18002f8f9  mov     dword ptr [rsp+2F0h+var_2A8], eax
0x18002f8fd  lea     rax, aSessionArbitra_3; "Session Arbitration started"
0x18002f904  mov     [rbp+1F0h+var_260], rax
0x18002f908  lea     rax, [rbp+1F0h+var_268]
0x18002f90c  mov     [rsp+2F0h+var_2C0], rax
0x18002f911  lea     rax, [rsp+2F0h+var_2A8]
0x18002f916  mov     [rsp+2F0h+var_2C8], rax
0x18002f91b  lea     rax, [rbp+1F0h+var_260]
0x18002f91f  lea     rdx, byte_1800C1199
0x18002f926  jmp     short loc_18002F966
0x18002f928  cmp     eax, 4
0x18002f92b  jbe     short loc_18002F970
0x18002f92d  lea     rax, [rbp+1F0h+var_240]
0x18002f931  mov     [rbp+1F0h+var_260], rax
0x18002f935  mov     eax, [rsp+2F0h+var_2B0]
0x18002f939  mov     dword ptr [rsp+2F0h+var_2A8], eax
0x18002f93d  lea     rax, aSessionArbitra; "Session Arbitration ended"
0x18002f944  mov     [rbp+1F0h+var_268], rax
0x18002f948  lea     rax, [rbp+1F0h+var_260]
0x18002f94c  mov     [rsp+2F0h+var_2C0], rax
0x18002f951  lea     rax, [rsp+2F0h+var_2A8]
0x18002f956  mov     [rsp+2F0h+var_2C8], rax
0x18002f95b  lea     rax, [rbp+1F0h+var_268]
0x18002f95f  lea     rdx, word_1800C1156
0x18002f966  mov     [rsp+2F0h+var_2D0], rax
0x18002f96b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002f970  mov     rcx, [rsp+2F0h+pv]; pv
0x18002f975  test    rcx, rcx
0x18002f978  jz      short loc_18002F980
0x18002f97a  call    cs:__imp_CoTaskMemFree
0x18002f980  mov     rcx, [rsp+2F0h+var_298]; pv
0x18002f985  test    rcx, rcx
0x18002f988  jz      short loc_18002F991
0x18002f98a  call    cs:__imp_CoTaskMemFree
0x18002f990  nop
0x18002f991  lea     rcx, [rbp+1F0h+var_258]
0x18002f995  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002f99a  nop
0x18002f99b  lea     rcx, [rsp+2F0h+var_290]
0x18002f9a0  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002f9a5  nop
0x18002f9a6  lea     rcx, [rsp+2F0h+var_288]
0x18002f9ab  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002f9b0  nop
0x18002f9b1  lea     rcx, [rsp+2F0h+var_280]
0x18002f9b6  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002f9bb  nop
0x18002f9bc  mov     rcx, [rsp+2F0h+hObject]; hObject
0x18002f9c1  test    rcx, rcx
0x18002f9c4  jz      short loc_18002F9CD
0x18002f9c6  call    cs:__imp_CloseHandle
0x18002f9cc  nop
0x18002f9cd  lea     rcx, [rbp+1F0h+var_270]
0x18002f9d1  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002f9d6  mov     eax, ebx
0x18002f9d8  mov     rcx, [rbp+1F0h+var_30]
0x18002f9df  xor     rcx, rsp; StackCookie
0x18002f9e2  call    __security_check_cookie
0x18002f9e7  add     rsp, 2D8h
0x18002f9ee  pop     rdi
0x18002f9ef  pop     rsi
0x18002f9f0  pop     rbx
0x18002f9f1  pop     rbp
0x18002f9f2  retn
```
