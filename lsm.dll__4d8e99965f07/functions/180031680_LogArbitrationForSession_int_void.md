# LogArbitrationForSession(int,void *)

- ea: `0x180031680`
- end: `0x180031a30`
- name: `?LogArbitrationForSession@@YAJHPEAX@Z`
- size: `944`
- prototype: `int(int, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180031a40`

## callees

- `0x1800077a0`
- `0x18000c17c`
- `0x18000c684`
- `0x18000f320`
- `0x180011440`
- `0x1800124b4`
- `0x180012650`
- `0x180021944`
- `0x180028750`
- `0x180031680`
- `0x18004e850`
- `0x18009c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800318db`
- `ntdll!EtwEventActivityIdControl` at `0x1800318db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800319b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800319c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800319b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800319c6`

## string_xrefs

- `0x180031712`: `DuplicateClientToken failed: 0x%x in %s`

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
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  struct ISessionManagerInternal *v21; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, __int64 *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  void *TargetHandle; // [rsp+78h] [rbp-88h] BYREF
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
  TargetHandle = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v31 = 0;
  v3 = CRpcUtils::DuplicateClientToken(a2, &TargetHandle);
  v4 = v3;
  if ( v3 >= 0 )
  {
    InstanceOfUserName = CUtils::GetInstanceOfUserName(&v28);
    v4 = InstanceOfUserName;
    if ( InstanceOfUserName >= 0 )
    {
      v6 = v28;
      v7 = (*(__int64 (__fastcall **)(struct IUserName *, void *, __int64))(*(_QWORD *)v28 + 24LL))(
             v28,
             TargetHandle,
             1);
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
                    v14 = (**v25)(v25, qword_1800A7960, &v24);
                    v4 = v14;
                    if ( v14 >= 0 )
                    {
                      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v24 + 584LL))(v24, &v32);
                      v4 = StringCchPrintfW(v33, 0x104u, L"%s\\%s", v23, pv);
                      EtwEventActivityIdControl(2, &v32);
                      v15 = EVENT_SESSION_ARBITRATION_BEGIN;
                      if ( !a1 )
                        v15 = EVENT_SESSION_ARBITRATION_END;
                      CrimsonHelper::RaiseEvent<unsigned short *,long>(&CrimsonHelper::s_instance, v15, v33, v20);
                      if ( a1 )
                      {
                        if ( (unsigned int)dword_1800DF020 > 4 )
                        {
                          v29 = v33;
                          LODWORD(v21) = v20;
                          v30 = (unsigned __int16 *)"Session Arbitration started";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                            v16,
                            (unsigned int)byte_1800C6321,
                            v17,
                            v18,
                            (__int64)&v30,
                            (__int64)&v21,
                            (__int64)&v29);
                        }
                      }
                      else if ( (unsigned int)dword_1800DF020 > 4 )
                      {
                        v30 = v33;
                        LODWORD(v21) = v20;
                        v29 = (unsigned __int16 *)"Session Arbitration ended";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                          v16,
                          (unsigned int)&word_1800C62DE,
                          v17,
                          v18,
                          (__int64)&v29,
                          (__int64)&v21,
                          (__int64)&v30);
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
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v31);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v24);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v25);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v26);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&TargetHandle);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v28);
  return v4;
}

```

## disassembly

```asm
0x180031680  push    rbp
0x180031682  push    rbx
0x180031683  push    rsi
0x180031684  push    rdi
0x180031685  lea     rbp, [rsp-1D8h]
0x18003168d  sub     rsp, 2D8h
0x180031694  mov     rax, cs:__security_cookie
0x18003169b  xor     rax, rsp
0x18003169e  mov     [rbp+1F0h+var_30], rax
0x1800316a5  mov     rax, rdx
0x1800316a8  mov     esi, ecx
0x1800316aa  mov     [rsp+2F0h+pv], 0
0x1800316b3  mov     [rsp+2F0h+var_298], 0
0x1800316bc  mov     [rbp+1F0h+var_270], 0
0x1800316c4  mov     [rsp+2F0h+var_2B0], 0
0x1800316cc  xorps   xmm0, xmm0
0x1800316cf  movups  [rbp+1F0h+var_250], xmm0
0x1800316d3  mov     [rsp+2F0h+TargetHandle], 0
0x1800316dc  mov     [rsp+2F0h+var_280], 0
0x1800316e5  mov     [rsp+2F0h+var_288], 0
0x1800316ee  mov     [rsp+2F0h+var_290], 0
0x1800316f7  mov     [rbp+1F0h+var_258], 0
0x1800316ff  lea     rdx, [rsp+2F0h+TargetHandle]; TargetHandle
0x180031704  mov     rcx, rax; SourceHandle
0x180031707  call    ?DuplicateClientToken@CRpcUtils@@SAJPEAXPEAPEAX@Z; CRpcUtils::DuplicateClientToken(void *,void * *)
0x18003170c  mov     ebx, eax
0x18003170e  test    eax, eax
0x180031710  jns     short loc_180031732
0x180031712  lea     rdx, aDuplicateclien; "DuplicateClientToken failed: 0x%x in %s"
0x180031719  mov     r8d, eax
0x18003171c  lea     r9, aLogarbitration; "LogArbitrationForSession"
0x180031723  mov     ecx, 4; int
0x180031728  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003172d  jmp     loc_1800319A6
0x180031732  lea     rcx, [rbp+1F0h+var_270]; struct IUserName **
0x180031736  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18003173b  mov     ebx, eax
0x18003173d  test    eax, eax
0x18003173f  jns     short loc_18003174A
0x180031741  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x180031748  jmp     short loc_180031719
0x18003174a  mov     rdi, [rbp+1F0h+var_270]
0x18003174e  mov     rax, [rdi]
0x180031751  mov     r8d, 1
0x180031757  mov     rdx, [rsp+2F0h+TargetHandle]
0x18003175c  mov     rcx, rdi
0x18003175f  mov     rax, [rax+18h]
0x180031763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031768  mov     ebx, eax
0x18003176a  test    eax, eax
0x18003176c  jns     short loc_180031777
0x18003176e  lea     rdx, aPtrusernameIni; "ptrUserName->Initialize failed: 0x%x in"...
0x180031775  jmp     short loc_180031719
0x180031777  mov     rax, [rdi]
0x18003177a  lea     rdx, [rsp+2F0h+pv]
0x18003177f  mov     rcx, rdi
0x180031782  mov     rax, [rax+28h]
0x180031786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003178b  mov     ebx, eax
0x18003178d  test    eax, eax
0x18003178f  jns     short loc_18003179D
0x180031791  lea     rdx, aGetingUserName; "Geting user name failed: 0x%x in %s"
0x180031798  jmp     loc_180031719
0x18003179d  mov     rax, [rdi]
0x1800317a0  lea     rdx, [rsp+2F0h+var_298]
0x1800317a5  mov     rcx, rdi
0x1800317a8  mov     rax, [rax+30h]
0x1800317ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800317b1  mov     ebx, eax
0x1800317b3  test    eax, eax
0x1800317b5  jns     short loc_1800317C3
0x1800317b7  lea     rdx, aGetingUserDoma; "Geting user domain failed: 0x%x in %s"
0x1800317be  jmp     loc_180031719
0x1800317c3  mov     rax, [rdi]
0x1800317c6  lea     rdx, [rsp+2F0h+var_2B0]
0x1800317cb  mov     rcx, rdi
0x1800317ce  mov     rax, [rax+70h]
0x1800317d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800317d7  mov     ebx, eax
0x1800317d9  test    eax, eax
0x1800317db  jns     short loc_1800317E9
0x1800317dd  lea     rdx, aGetingUserSess; "Geting user session failed: 0x%x in %s"
0x1800317e4  jmp     loc_180031719
0x1800317e9  mov     [rsp+2F0h+var_2A8], 0
0x1800317f2  lea     rcx, [rsp+2F0h+var_2A8]; struct ISessionManagerInternal **
0x1800317f7  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x1800317fc  mov     ebx, eax
0x1800317fe  mov     rcx, [rsp+2F0h+var_2A8]
0x180031803  mov     [rbp+1F0h+var_258], rcx
0x180031807  test    eax, eax
0x180031809  jns     short loc_180031817
0x18003180b  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x180031812  jmp     loc_180031719
0x180031817  mov     rax, [rcx]
0x18003181a  lea     rdx, [rsp+2F0h+var_280]
0x18003181f  mov     rax, [rax+18h]
0x180031823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031828  mov     ebx, eax
0x18003182a  test    eax, eax
0x18003182c  jns     short loc_18003183A
0x18003182e  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x180031835  jmp     loc_180031719
0x18003183a  mov     rcx, [rsp+2F0h+var_280]
0x18003183f  mov     rax, [rcx]
0x180031842  lea     r8, [rsp+2F0h+var_288]
0x180031847  mov     edx, [rsp+2F0h+var_2B0]
0x18003184b  mov     rax, [rax+18h]
0x18003184f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031854  mov     ebx, eax
0x180031856  test    eax, eax
0x180031858  jns     short loc_180031866
0x18003185a  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x180031861  jmp     loc_180031719
0x180031866  mov     rcx, [rsp+2F0h+var_288]
0x18003186b  mov     rax, [rcx]
0x18003186e  lea     r8, [rsp+2F0h+var_290]
0x180031873  lea     rdx, qword_1800A7960
0x18003187a  mov     rax, [rax]
0x18003187d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031882  mov     ebx, eax
0x180031884  test    eax, eax
0x180031886  jns     short loc_180031894
0x180031888  lea     rdx, aGettingIidItss_2; "Getting IID_ITSSessionPrivate failed: 0"...
0x18003188f  jmp     loc_180031719
0x180031894  mov     rcx, [rsp+2F0h+var_290]
0x180031899  mov     rax, [rcx]
0x18003189c  lea     rdx, [rbp+1F0h+var_250]
0x1800318a0  mov     rax, [rax+248h]
0x1800318a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318ac  mov     rax, [rsp+2F0h+pv]
0x1800318b1  mov     [rsp+2F0h+var_2D0], rax
0x1800318b6  mov     r9, [rsp+2F0h+var_298]
0x1800318bb  lea     r8, aSS_0; "%s\\%s"
0x1800318c2  mov     edx, 104h; unsigned __int64
0x1800318c7  lea     rcx, [rbp+1F0h+var_240]; unsigned __int16 *
0x1800318cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800318d0  mov     ebx, eax
0x1800318d2  lea     rdx, [rbp+1F0h+var_250]
0x1800318d6  mov     ecx, 2
0x1800318db  call    cs:__imp_EtwEventActivityIdControl
0x1800318e2  nop     dword ptr [rax+rax+00h]
0x1800318e7  lea     rax, EVENT_SESSION_ARBITRATION_END
0x1800318ee  lea     rdx, EVENT_SESSION_ARBITRATION_BEGIN
0x1800318f5  test    esi, esi
0x1800318f7  cmovz   rdx, rax
0x1800318fb  mov     r9d, [rsp+2F0h+var_2B0]
0x180031900  lea     r8, [rbp+1F0h+var_240]
0x180031904  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18003190b  call    ??$RaiseEvent@PEAGJ@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAGJ@Z; CrimsonHelper::RaiseEvent<ushort *,long>(_EVENT_DESCRIPTOR const &,ushort *,long)
0x180031910  mov     eax, cs:dword_1800DF020
0x180031916  test    esi, esi
0x180031918  jz      short loc_18003195E
0x18003191a  cmp     eax, 4
0x18003191d  jbe     loc_1800319A6
0x180031923  lea     rax, [rbp+1F0h+var_240]
0x180031927  mov     [rbp+1F0h+var_268], rax
0x18003192b  mov     eax, [rsp+2F0h+var_2B0]
0x18003192f  mov     dword ptr [rsp+2F0h+var_2A8], eax
0x180031933  lea     rax, aSessionArbitra_3; "Session Arbitration started"
0x18003193a  mov     [rbp+1F0h+var_260], rax
0x18003193e  lea     rax, [rbp+1F0h+var_268]
0x180031942  mov     [rsp+2F0h+var_2C0], rax
0x180031947  lea     rax, [rsp+2F0h+var_2A8]
0x18003194c  mov     [rsp+2F0h+var_2C8], rax
0x180031951  lea     rax, [rbp+1F0h+var_260]
0x180031955  lea     rdx, byte_1800C6321
0x18003195c  jmp     short loc_18003199C
0x18003195e  cmp     eax, 4
0x180031961  jbe     short loc_1800319A6
0x180031963  lea     rax, [rbp+1F0h+var_240]
0x180031967  mov     [rbp+1F0h+var_260], rax
0x18003196b  mov     eax, [rsp+2F0h+var_2B0]
0x18003196f  mov     dword ptr [rsp+2F0h+var_2A8], eax
0x180031973  lea     rax, aSessionArbitra; "Session Arbitration ended"
0x18003197a  mov     [rbp+1F0h+var_268], rax
0x18003197e  lea     rax, [rbp+1F0h+var_260]
0x180031982  mov     [rsp+2F0h+var_2C0], rax
0x180031987  lea     rax, [rsp+2F0h+var_2A8]
0x18003198c  mov     [rsp+2F0h+var_2C8], rax
0x180031991  lea     rax, [rbp+1F0h+var_268]
0x180031995  lea     rdx, word_1800C62DE
0x18003199c  mov     [rsp+2F0h+var_2D0], rax
0x1800319a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800319a6  mov     rcx, [rsp+2F0h+pv]; pv
0x1800319ab  test    rcx, rcx
0x1800319ae  jz      short loc_1800319BC
0x1800319b0  call    cs:__imp_CoTaskMemFree
0x1800319b7  nop     dword ptr [rax+rax+00h]
0x1800319bc  mov     rcx, [rsp+2F0h+var_298]; pv
0x1800319c1  test    rcx, rcx
0x1800319c4  jz      short loc_1800319D3
0x1800319c6  call    cs:__imp_CoTaskMemFree
0x1800319cd  nop     dword ptr [rax+rax+00h]
0x1800319d2  nop
0x1800319d3  lea     rcx, [rbp+1F0h+var_258]
0x1800319d7  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800319dc  nop
0x1800319dd  lea     rcx, [rsp+2F0h+var_290]
0x1800319e2  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800319e7  nop
0x1800319e8  lea     rcx, [rsp+2F0h+var_288]
0x1800319ed  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800319f2  nop
0x1800319f3  lea     rcx, [rsp+2F0h+var_280]
0x1800319f8  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800319fd  nop
0x1800319fe  lea     rcx, [rsp+2F0h+TargetHandle]; this
0x180031a03  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180031a08  nop
0x180031a09  lea     rcx, [rbp+1F0h+var_270]
0x180031a0d  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180031a12  mov     eax, ebx
0x180031a14  mov     rcx, [rbp+1F0h+var_30]
0x180031a1b  xor     rcx, rsp; StackCookie
0x180031a1e  call    __security_check_cookie
0x180031a23  add     rsp, 2D8h
0x180031a2a  pop     rdi
0x180031a2b  pop     rsi
0x180031a2c  pop     rbx
0x180031a2d  pop     rbp
0x180031a2e  retn
```
