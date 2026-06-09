# CEventSystem2::NotifyLogonUser(ushort const *,int)

- ea: `0x18000a1f0`
- end: `0x18000ab9d`
- name: `?NotifyLogonUser@CEventSystem2@@UEAAJPEBGH@Z`
- size: `2477`
- prototype: `int(CEventSystem2 *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008938`
- `0x18000a1f0`
- `0x18000aba4`
- `0x18000ac40`
- `0x18000ac54`
- `0x18000ae10`
- `0x18000afe0`
- `0x18000d694`
- `0x18000db98`
- `0x180010410`
- `0x180012654`
- `0x180015850`
- `0x18001f970`
- `0x180025b78`
- `0x18002c714`
- `0x18003ecb0`
- `0x180043496`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004394e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004394e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a95d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a96b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a979`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a987`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a995`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a9a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438b9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438e0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438ed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a95d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a96b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a979`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a987`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a995`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a9a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438b9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438e0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438ed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800438fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a383`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a253`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a253`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000a23a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000a23a`

## string_xrefs

- `0x18000a2f3`: `com\complus\src\events\tier2\eventsystem2.cpp`
- `0x18000aa6f`: `com\complus\src\events\tier2\eventsystem2.cpp`

## pseudocode

```c
__int64 __fastcall CEventSystem2::NotifyLogonUser(CEventSystem2 *this, const unsigned __int16 *a2, int a3)
{
  HRESULT v6; // edi
  BOOL v7; // r15d
  struct _RTL_CRITICAL_SECTION *i; // r14
  CEventSystem2 *v9; // r13
  int v10; // r15d
  RegDatabase *v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  int v13; // r15d
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rcx
  int LockSemaphore; // eax
  int v18; // eax
  int v19; // eax
  __int64 v21; // [rsp+0h] [rbp-2A8h] BYREF
  int v22; // [rsp+40h] [rbp-268h]
  __int64 v23; // [rsp+48h] [rbp-260h] BYREF
  int v24; // [rsp+50h] [rbp-258h] BYREF
  int v25; // [rsp+54h] [rbp-254h] BYREF
  __int64 v26; // [rsp+58h] [rbp-250h] BYREF
  __int64 v27; // [rsp+60h] [rbp-248h] BYREF
  __int64 v28; // [rsp+68h] [rbp-240h] BYREF
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+70h] [rbp-238h]
  PROPVARIANT pvar[2]; // [rsp+78h] [rbp-230h] BYREF
  __int64 v31; // [rsp+88h] [rbp-220h]
  CEventSystem2 *v32; // [rsp+90h] [rbp-218h] BYREF
  struct tagPROPVARIANT v33; // [rsp+98h] [rbp-210h] BYREF
  struct tagPROPVARIANT v34; // [rsp+B0h] [rbp-1F8h] BYREF
  PROPVARIANT v35[2]; // [rsp+C8h] [rbp-1E0h] BYREF
  __int64 v36; // [rsp+D8h] [rbp-1D0h]
  PROPVARIANT v37[2]; // [rsp+E0h] [rbp-1C8h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-1B8h]
  tagPROPVARIANT v39; // [rsp+F8h] [rbp-1B0h] BYREF
  __int64 *v40; // [rsp+110h] [rbp-198h]
  struct tagPROPVARIANT v41; // [rsp+120h] [rbp-188h] BYREF
  struct tagPROPVARIANT v42; // [rsp+140h] [rbp-168h] BYREF
  tagPROPVARIANT v43; // [rsp+160h] [rbp-148h] BYREF
  unsigned __int16 v44[120]; // [rsp+180h] [rbp-128h] BYREF

  v40 = &v21;
  v24 = a3;
  v32 = this;
  v6 = CoImpersonateClient();
  if ( v6 < 0 )
  {
    if ( v6 == -2147417833 )
      v6 = 0;
  }
  else
  {
    v6 = CheckTokenIsLocalSystemOrSENS();
    CoRevertToSelf();
  }
  v22 = v6;
  if ( v6 < 0 )
    return (unsigned int)v6;
  v7 = 0;
  if ( *((_DWORD *)this + 100) )
    return 2147549448LL;
  CSemExclusiveES::Lock((CSemExclusiveES *)&g_LogonListGuard);
  for ( i = (struct _RTL_CRITICAL_SECTION *)g_LogonList; i; i = (struct _RTL_CRITICAL_SECTION *)i->DebugInfo )
  {
    if ( (unsigned __int8)operator==(&i->OwningThread, a2) )
    {
      LockSemaphore = (int)i->LockSemaphore;
      if ( a3 )
      {
        v18 = LockSemaphore + 1;
        LODWORD(i->LockSemaphore) = v18;
        if ( v18 == 1 )
        {
          InternalAssert(
            L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp",
            0x1F8u,
            0x11u,
            L"currentElement.count != 1");
          v18 = (int)i->LockSemaphore;
        }
        v7 = 0;
LABEL_80:
        if ( !v18 )
          CList<LogonListElement,LogonListElement &>::RemoveAt(v16, i);
      }
      else
      {
        v19 = LockSemaphore - 1;
        LODWORD(i->LockSemaphore) = v19;
        if ( v19 == -1 )
          InternalAssert(
            L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp",
            0x1FEu,
            0x11u,
            L"currentElement.count != -1");
        if ( !LODWORD(i->LockSemaphore) )
        {
          v7 = 1;
          v18 = 0;
          goto LABEL_80;
        }
      }
LABEL_10:
      if ( v7 )
      {
        v27 = 0;
        v26 = 0;
        v28 = 0;
        v29 = 0;
        v23 = 0;
        v9 = v32;
        v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, struct tagFieldInfo near **, __int64 *))(**((_QWORD **)v32 + 3) + 40LL))(
                *((_QWORD *)v32 + 3),
                2,
                18,
                &g_subscriptionFields,
                &v27);
        if ( v22 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x23Au, 0x11u, v22);
        v10 = 0;
        v25 = 0;
        i = 0;
        v29 = 0;
        v11 = (RegDatabase *)CoTaskMemAlloc(0x278u);
        if ( v11 )
        {
          v12 = (struct _RTL_CRITICAL_SECTION *)RegDatabase::RegDatabase(v11, a2, &v25);
          v10 = v25;
        }
        else
        {
          v12 = 0;
        }
        if ( v12 )
        {
          if ( v10 < 0 )
          {
            RegDatabase::`scalar deleting destructor'(v12);
          }
          else
          {
            i = v12;
            v29 = v12;
            ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v12->DebugInfo->CriticalSection)(v12);
            v10 = 0;
          }
        }
        else
        {
          v10 = -2147024882;
        }
        v22 = v10;
        if ( v10 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x23Eu, 0x11u, v22);
        v22 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, const WCHAR *))&i->DebugInfo->EntryCount)(
                i,
                L"{26c409cc-ae86-11d1-b616-00805fc79216}");
        if ( v22 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x241u, 0x11u, v22);
        v22 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, __int64, __int64, struct tagFieldInfo near **, __int64 *))&i->DebugInfo->Flags)(
                i,
                2,
                18,
                &g_subscriptionFields,
                &v28);
        if ( v22 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x247u, 0x11u, v22);
        LODWORD(v32) = 0;
        v22 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, CEventSystem2 **, __int64 *))(*(_QWORD *)v28 + 40LL))(
                v28,
                L"ALL",
                0,
                &v32,
                &v26);
        if ( v22 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x24Cu, 0x11u, v22);
        v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 24LL))(v26);
        if ( !v22 )
        {
          v13 = v24;
          while ( 1 )
          {
            v24 = 0;
            v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v26 + 40LL))(
                    v26,
                    1,
                    &v23,
                    &v24);
            if ( v22 || v24 != 1 )
              break;
            memset(&v39, 0, sizeof(v39));
            *(_OWORD *)v37 = 0;
            v38 = 0;
            *(_OWORD *)v35 = 0;
            v36 = 0;
            memset(&v34, 0, sizeof(v34));
            memset(&v33, 0, sizeof(v33));
            *(_OWORD *)pvar = 0;
            v31 = 0;
            v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, tagPROPVARIANT *))(*(_QWORD *)v23 + 24LL))(v23, 0, &v39);
            if ( v22 < 0 )
              InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x270u, 0x11u, v22);
            v22 = (*(__int64 (__fastcall **)(__int64, __int64, struct tagPROPVARIANT *))(*(_QWORD *)v23 + 24LL))(
                    v23,
                    16,
                    &v34);
            if ( v22 < 0 )
              InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x273u, 0x11u, v22);
            v22 = (*(__int64 (__fastcall **)(__int64, __int64, struct tagPROPVARIANT *))(*(_QWORD *)v23 + 24LL))(
                    v23,
                    17,
                    &v33);
            if ( v22 < 0 )
              InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x275u, 0x11u, v22);
            v41 = v33;
            v42 = v34;
            v43 = v39;
            v22 = ConcatenateECID_PARTID_APPID(&v43, &v42, &v41, v14, v44);
            if ( v22 < 0 )
              InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x27Du, 0x11u, v22);
            v22 = (*(__int64 (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)v23 + 24LL))(v23, 4, v37);
            if ( v22 < 0 )
              InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x282u, 0x11u, v22);
            v22 = (*(__int64 (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)v23 + 24LL))(v23, 3, v35);
            if ( v22 < 0 )
              InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x284u, 0x11u, v22);
            v22 = (*(__int64 (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)v23 + 24LL))(v23, 14, pvar);
            if ( v22 < 0 )
              InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x28Cu, 0x11u, v22);
            if ( v13 )
            {
              v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 72LL))(v23, 0);
              if ( v22 < 0 )
                InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x296u, 0x11u, v22);
              v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 48LL))(v27, v23);
              if ( v22 < 0 )
                InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x299u, 0x11u, v22);
              (*(void (__fastcall **)(__int64, _QWORD, unsigned __int16 *, PROPVARIANT, PROPVARIANT, PROPVARIANT))(*((_QWORD *)v9 + 1) + 32LL))(
                (__int64)v9 + 8,
                0,
                v44,
                v37[1],
                v35[1],
                pvar[1]);
            }
            else
            {
              (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *, PROPVARIANT, PROPVARIANT, PROPVARIANT))(*((_QWORD *)v9 + 1) + 32LL))(
                (__int64)v9 + 8,
                2,
                v44,
                v37[1],
                v35[1],
                pvar[1]);
              v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 56LL))(v27, v23);
              if ( v22 < 0 )
                InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x2A9u, 0x11u, v22);
              v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 80LL))(v23, 0);
              if ( v22 < 0 )
                InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x2AEu, 0x11u, v22);
            }
            PropVariantClear(pvar);
            PropVariantClear((PROPVARIANT *)&v33);
            PropVariantClear((PROPVARIANT *)&v34);
            PropVariantClear(v35);
            PropVariantClear(v37);
            PropVariantClear((PROPVARIANT *)&v39);
            if ( v23 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              v23 = 0;
            }
          }
          v22 = 0;
        }
        v15 = v23;
        if ( !v23 )
          goto LABEL_62;
      }
      else
      {
        local_unwind_0(v40, &loc_18000AB99);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v23 = 0;
LABEL_62:
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        v26 = 0;
      }
      if ( v28 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        v28 = 0;
      }
      if ( i )
      {
        ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))i->DebugInfo->ProcessLocksList.Flink)(i);
        v29 = 0;
      }
      if ( v27 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        v27 = 0;
      }
      goto LABEL_86;
    }
  }
  LogonListElement::LogonListElement((LogonListElement *)pvar);
  v22 = CString::AssignNoThrow((CString *)pvar, a2);
  if ( v22 < 0 )
    goto LABEL_86;
  LODWORD(pvar[1]) = a3 != 0 ? 1 : -1;
  v22 = CList<LogonListElement,LogonListElement &>::AddTail(LODWORD(pvar[1]), pvar);
  if ( v22 >= 0 )
  {
    LogonListElement::~LogonListElement((LogonListElement *)pvar);
    v7 = a3 != 0;
    goto LABEL_10;
  }
  if ( *((_DWORD *)pvar[0] - 2) )
    CString::Release((CString *)pvar);
LABEL_86:
  LeaveCriticalSection(&g_LogonListGuard);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18000a1f0  mov     [rsp+arg_10], rbx
0x18000a1f5  mov     [rsp+arg_18], rsi
0x18000a1fa  push    rdi
0x18000a1fb  push    r12
0x18000a1fd  push    r13
0x18000a1ff  push    r14
0x18000a201  push    r15
0x18000a203  sub     rsp, 280h
0x18000a20a  mov     rax, cs:__security_cookie
0x18000a211  xor     rax, rsp
0x18000a214  mov     [rsp+2A8h+var_38], rax
0x18000a21c  mov     [rsp+2A8h+var_198], rsp
0x18000a224  mov     esi, r8d
0x18000a227  mov     [rsp+2A8h+var_258], r8d
0x18000a22c  mov     r12, rdx
0x18000a22f  mov     r13, rcx
0x18000a232  mov     [rsp+2A8h+var_218], rcx
0x18000a23a  call    cs:__imp_CoImpersonateClient
0x18000a240  mov     edi, eax
0x18000a242  xor     ebx, ebx
0x18000a244  test    eax, eax
0x18000a246  js      loc_18000AB80
0x18000a24c  call    CheckTokenIsLocalSystemOrSENS
0x18000a251  mov     edi, eax
0x18000a253  call    cs:__imp_CoRevertToSelf
0x18000a259  mov     [rsp+2A8h+var_268], edi
0x18000a25d  test    edi, edi
0x18000a25f  js      loc_18000AB8E
0x18000a265  mov     r15d, ebx
0x18000a268  cmp     [r13+190h], ebx
0x18000a26f  jnz     loc_18000AB92
0x18000a275  lea     rcx, ?g_LogonListGuard@@3VCSemExclusiveES@@A; this
0x18000a27c  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18000a281  mov     r14, cs:?g_LogonList@@3V?$CList@ULogonListElement@@AEAU1@@@A; CList<LogonListElement,LogonListElement &> g_LogonList
0x18000a288  test    r14, r14
0x18000a28b  jnz     loc_18000AA36
0x18000a291  lea     rcx, [rsp+2A8h+pvar]; this
0x18000a296  call    ??0LogonListElement@@QEAA@XZ; LogonListElement::LogonListElement(void)
0x18000a29b  mov     rdx, r12; unsigned __int16 *
0x18000a29e  lea     rcx, [rsp+2A8h+pvar]; this
0x18000a2a3  call    ?AssignNoThrow@CString@@QEAAJPEBG@Z; CString::AssignNoThrow(ushort const *)
0x18000a2a8  mov     [rsp+2A8h+var_268], eax
0x18000a2ac  test    eax, eax
0x18000a2ae  js      loc_18000AB42
0x18000a2b4  mov     eax, esi
0x18000a2b6  neg     eax
0x18000a2b8  sbb     ecx, ecx
0x18000a2ba  and     ecx, 2
0x18000a2bd  dec     ecx
0x18000a2bf  mov     dword ptr [rsp+2A8h+pvar+8], ecx
0x18000a2c6  lea     rdx, [rsp+2A8h+pvar]
0x18000a2cb  call    ?AddTail@?$CList@ULogonListElement@@AEAU1@@@QEAAJAEAULogonListElement@@PEAPEAU__POSITION@@@Z; CList<LogonListElement,LogonListElement &>::AddTail(LogonListElement &,__POSITION * *)
0x18000a2d0  mov     [rsp+2A8h+var_268], eax
0x18000a2d4  test    eax, eax
0x18000a2d6  js      loc_18000AAEC
0x18000a2dc  lea     rcx, [rsp+2A8h+pvar]; this
0x18000a2e1  call    ??1LogonListElement@@QEAA@XZ; LogonListElement::~LogonListElement(void)
0x18000a2e6  mov     r15d, ebx
0x18000a2e9  test    esi, esi
0x18000a2eb  setnz   r15b
0x18000a2ef  lea     edi, [r14+11h]
0x18000a2f3  lea     rsi, aComComplusSrcE_18; "com\\complus\\src\\events\\tier2\\event"...
0x18000a2fa  test    r15d, r15d
0x18000a2fd  jz      loc_18000AB02
0x18000a303  mov     [rsp+2A8h+var_248], rbx
0x18000a308  mov     [rsp+2A8h+var_250], rbx
0x18000a30d  mov     [rsp+2A8h+var_240], rbx
0x18000a312  mov     [rsp+2A8h+var_238], rbx
0x18000a317  mov     [rsp+2A8h+var_260], rbx
0x18000a31c  mov     r13, [rsp+2A8h+var_218]
0x18000a324  mov     rcx, [r13+18h]
0x18000a328  mov     rax, [rcx]
0x18000a32b  lea     rdx, [rsp+2A8h+var_248]
0x18000a330  mov     [rsp+2A8h+var_288], rdx
0x18000a335  lea     r9, ?g_subscriptionFields@@3PAUtagFieldInfo@@A; tagFieldInfo near * g_subscriptionFields
0x18000a33c  mov     edx, 2
0x18000a341  lea     r8d, [rdx+10h]
0x18000a345  mov     rax, [rax+28h]
0x18000a349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a34e  mov     [rsp+2A8h+var_268], eax
0x18000a352  mov     eax, [rsp+2A8h+var_268]
0x18000a356  test    eax, eax
0x18000a358  jns     short loc_18000A36F
0x18000a35a  mov     r8d, edi; unsigned __int16
0x18000a35d  mov     r9d, [rsp+2A8h+var_268]; int
0x18000a362  mov     edx, 23Ah; unsigned int
0x18000a367  mov     rcx, rsi; unsigned __int16 *
0x18000a36a  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a36f  mov     r15d, ebx
0x18000a372  mov     [rsp+2A8h+var_254], ebx
0x18000a376  mov     r14, rbx
0x18000a379  mov     [rsp+2A8h+var_238], rbx
0x18000a37e  mov     ecx, 278h; cb
0x18000a383  call    cs:__imp_CoTaskMemAlloc
0x18000a389  test    rax, rax
0x18000a38c  jnz     loc_18000A813
0x18000a392  mov     rcx, rbx; this
0x18000a395  test    rcx, rcx
0x18000a398  jz      loc_18000A830
0x18000a39e  test    r15d, r15d
0x18000a3a1  js      loc_18000A8A3
0x18000a3a7  mov     r14, rcx
0x18000a3aa  mov     [rsp+2A8h+var_238], rcx
0x18000a3af  mov     rax, [rcx]
0x18000a3b2  mov     rax, [rax+8]
0x18000a3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3bb  mov     r15d, ebx
0x18000a3be  mov     [rsp+2A8h+var_268], r15d
0x18000a3c3  mov     eax, [rsp+2A8h+var_268]
0x18000a3c7  test    eax, eax
0x18000a3c9  js      loc_18000A83B
0x18000a3cf  mov     rax, [r14]
0x18000a3d2  lea     rdx, a26c409ccAe8611; "{26c409cc-ae86-11d1-b616-00805fc79216}"
0x18000a3d9  mov     rcx, r14
0x18000a3dc  mov     rax, [rax+20h]
0x18000a3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3e5  mov     [rsp+2A8h+var_268], eax
0x18000a3e9  mov     eax, [rsp+2A8h+var_268]
0x18000a3ed  test    eax, eax
0x18000a3ef  js      loc_18000A855
0x18000a3f5  mov     rax, [r14]
0x18000a3f8  lea     rcx, [rsp+2A8h+var_240]
0x18000a3fd  mov     [rsp+2A8h+var_288], rcx
0x18000a402  lea     r9, ?g_subscriptionFields@@3PAUtagFieldInfo@@A; tagFieldInfo near * g_subscriptionFields
0x18000a409  mov     edx, 2
0x18000a40e  lea     r8d, [rdx+10h]
0x18000a412  mov     rcx, r14
0x18000a415  mov     rax, [rax+28h]
0x18000a419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a41e  mov     [rsp+2A8h+var_268], eax
0x18000a422  mov     eax, [rsp+2A8h+var_268]
0x18000a426  test    eax, eax
0x18000a428  js      loc_18000A86F
0x18000a42e  mov     dword ptr [rsp+2A8h+var_218], ebx
0x18000a435  mov     rcx, [rsp+2A8h+var_240]
0x18000a43a  mov     rax, [rcx]
0x18000a43d  lea     rdx, [rsp+2A8h+var_250]
0x18000a442  mov     [rsp+2A8h+var_288], rdx
0x18000a447  lea     r9, [rsp+2A8h+var_218]
0x18000a44f  xor     r8d, r8d
0x18000a452  lea     rdx, aAll; "ALL"
0x18000a459  mov     rax, [rax+28h]
0x18000a45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a462  mov     [rsp+2A8h+var_268], eax
0x18000a466  mov     eax, [rsp+2A8h+var_268]
0x18000a46a  test    eax, eax
0x18000a46c  js      loc_18000A889
0x18000a472  mov     rcx, [rsp+2A8h+var_250]
0x18000a477  mov     rax, [rcx]
0x18000a47a  mov     rax, [rax+18h]
0x18000a47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a483  mov     [rsp+2A8h+var_268], eax
0x18000a487  mov     eax, [rsp+2A8h+var_268]
0x18000a48b  test    eax, eax
0x18000a48d  jnz     loc_18000A9CD
0x18000a493  mov     r15d, [rsp+2A8h+var_258]
0x18000a498  mov     [rsp+2A8h+var_258], ebx
0x18000a49c  mov     rcx, [rsp+2A8h+var_250]
0x18000a4a1  mov     rax, [rcx]
0x18000a4a4  lea     r9, [rsp+2A8h+var_258]
0x18000a4a9  lea     r8, [rsp+2A8h+var_260]
0x18000a4ae  mov     edx, 1
0x18000a4b3  mov     rax, [rax+28h]
0x18000a4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4bc  mov     [rsp+2A8h+var_268], eax
0x18000a4c0  mov     eax, [rsp+2A8h+var_268]
0x18000a4c4  test    eax, eax
0x18000a4c6  jnz     loc_18000A9C9
0x18000a4cc  cmp     [rsp+2A8h+var_258], 1
0x18000a4d1  jnz     loc_18000A9C9
0x18000a4d7  xorps   xmm0, xmm0
0x18000a4da  xor     eax, eax
0x18000a4dc  movups  xmmword ptr [rsp+2A8h+var_1B0], xmm0
0x18000a4e4  mov     [rsp+2A8h+var_1A0], rax
0x18000a4ec  xorps   xmm1, xmm1
0x18000a4ef  movups  xmmword ptr [rsp+2A8h+var_1C8], xmm1
0x18000a4f7  mov     [rsp+2A8h+var_1B8], rax
0x18000a4ff  movups  xmmword ptr [rsp+2A8h+var_1E0], xmm0
0x18000a507  mov     [rsp+2A8h+var_1D0], rax
0x18000a50f  movups  xmmword ptr [rsp+2A8h+var_1F8], xmm1
0x18000a517  mov     [rsp+2A8h+var_1E8], rax
0x18000a51f  movups  xmmword ptr [rsp+2A8h+var_210], xmm0
0x18000a527  mov     [rsp+2A8h+var_200], rax
0x18000a52f  movups  xmmword ptr [rsp+2A8h+pvar], xmm1
0x18000a534  mov     [rsp+2A8h+var_220], rax
0x18000a53c  mov     rcx, [rsp+2A8h+var_260]
0x18000a541  mov     rax, [rcx]
0x18000a544  lea     r8, [rsp+2A8h+var_1B0]
0x18000a54c  xor     edx, edx
0x18000a54e  mov     rax, [rax+18h]
0x18000a552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a557  mov     [rsp+2A8h+var_268], eax
0x18000a55b  mov     eax, [rsp+2A8h+var_268]
0x18000a55f  test    eax, eax
0x18000a561  jns     short loc_18000A578
0x18000a563  mov     r8d, edi; unsigned __int16
0x18000a566  mov     r9d, [rsp+2A8h+var_268]; int
0x18000a56b  mov     edx, 270h; unsigned int
0x18000a570  mov     rcx, rsi; unsigned __int16 *
0x18000a573  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a578  mov     rcx, [rsp+2A8h+var_260]
0x18000a57d  mov     rax, [rcx]
0x18000a580  lea     r8, [rsp+2A8h+var_1F8]
0x18000a588  mov     edx, 10h
0x18000a58d  mov     rax, [rax+18h]
0x18000a591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a596  mov     [rsp+2A8h+var_268], eax
0x18000a59a  mov     eax, [rsp+2A8h+var_268]
0x18000a59e  test    eax, eax
0x18000a5a0  jns     short loc_18000A5B7
0x18000a5a2  mov     r8d, edi; unsigned __int16
0x18000a5a5  mov     r9d, [rsp+2A8h+var_268]; int
0x18000a5aa  mov     edx, 273h; unsigned int
0x18000a5af  mov     rcx, rsi; unsigned __int16 *
0x18000a5b2  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a5b7  mov     rcx, [rsp+2A8h+var_260]
0x18000a5bc  mov     rax, [rcx]
0x18000a5bf  lea     r8, [rsp+2A8h+var_210]
0x18000a5c7  mov     edx, edi
0x18000a5c9  mov     rax, [rax+18h]
0x18000a5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5d2  mov     [rsp+2A8h+var_268], eax
0x18000a5d6  mov     eax, [rsp+2A8h+var_268]
0x18000a5da  test    eax, eax
0x18000a5dc  jns     short loc_18000A5F3
0x18000a5de  mov     r8d, edi; unsigned __int16
0x18000a5e1  mov     r9d, [rsp+2A8h+var_268]; int
0x18000a5e6  mov     edx, 275h; unsigned int
0x18000a5eb  mov     rcx, rsi; unsigned __int16 *
0x18000a5ee  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a5f3  movups  xmm0, xmmword ptr [rsp+2A8h+var_210]
0x18000a5fb  movaps  xmmword ptr [rsp+2A8h+var_188], xmm0
0x18000a603  movsd   xmm1, [rsp+2A8h+var_200]
0x18000a60c  movsd   qword ptr [rsp+2A8h+var_188+10h], xmm1
0x18000a615  movups  xmm0, xmmword ptr [rsp+2A8h+var_1F8]
0x18000a61d  movaps  xmmword ptr [rsp+2A8h+var_168], xmm0
0x18000a625  movsd   xmm1, [rsp+2A8h+var_1E8]
0x18000a62e  movsd   qword ptr [rsp+2A8h+var_168+10h], xmm1
0x18000a637  movups  xmm0, xmmword ptr [rsp+2A8h+var_1B0]
0x18000a63f  movaps  xmmword ptr [rsp+2A8h+var_148], xmm0
0x18000a647  movsd   xmm1, [rsp+2A8h+var_1A0]
0x18000a650  movsd   qword ptr [rsp+2A8h+var_148+10h], xmm1
0x18000a659  lea     rax, [rsp+2A8h+var_128]
0x18000a661  mov     [rsp+2A8h+var_288], rax; unsigned __int16 *
0x18000a666  lea     r8, [rsp+2A8h+var_188]; struct tagPROPVARIANT *
0x18000a66e  lea     rdx, [rsp+2A8h+var_168]; struct tagPROPVARIANT *
0x18000a676  lea     rcx, [rsp+2A8h+var_148]; struct tagPROPVARIANT *
0x18000a67e  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x18000a683  mov     [rsp+2A8h+var_268], eax
0x18000a687  mov     eax, [rsp+2A8h+var_268]
0x18000a68b  test    eax, eax
0x18000a68d  jns     short loc_18000A6A4
0x18000a68f  mov     r8d, edi; unsigned __int16
0x18000a692  mov     r9d, [rsp+2A8h+var_268]; int
0x18000a697  mov     edx, 27Dh; unsigned int
0x18000a69c  mov     rcx, rsi; unsigned __int16 *
0x18000a69f  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a6a4  mov     rcx, [rsp+2A8h+var_260]
0x18000a6a9  mov     rax, [rcx]
0x18000a6ac  lea     r8, [rsp+2A8h+var_1C8]
0x18000a6b4  mov     edx, 4
0x18000a6b9  mov     rax, [rax+18h]
0x18000a6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c2  mov     [rsp+2A8h+var_268], eax
0x18000a6c6  mov     eax, [rsp+2A8h+var_268]
0x18000a6ca  test    eax, eax
0x18000a6cc  jns     short loc_18000A6E3
0x18000a6ce  mov     r8d, edi; unsigned __int16
0x18000a6d1  mov     r9d, [rsp+2A8h+var_268]; int
0x18000a6d6  mov     edx, 282h; unsigned int
0x18000a6db  mov     rcx, rsi; unsigned __int16 *
0x18000a6de  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a6e3  mov     rcx, [rsp+2A8h+var_260]
0x18000a6e8  mov     rax, [rcx]
0x18000a6eb  lea     r8, [rsp+2A8h+var_1E0]
0x18000a6f3  mov     edx, 3
0x18000a6f8  mov     rax, [rax+18h]
0x18000a6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a701  mov     [rsp+2A8h+var_268], eax
0x18000a705  mov     eax, [rsp+2A8h+var_268]
0x18000a709  test    eax, eax
0x18000a70b  jns     short loc_18000A722
0x18000a70d  mov     r8d, edi; unsigned __int16
0x18000a710  mov     r9d, [rsp+2A8h+var_268]; int
0x18000a715  mov     edx, 284h; unsigned int
0x18000a71a  mov     rcx, rsi; unsigned __int16 *
0x18000a71d  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a722  mov     rcx, [rsp+2A8h+var_260]
0x18000a727  mov     rax, [rcx]
0x18000a72a  lea     r8, [rsp+2A8h+pvar]
0x18000a72f  mov     edx, 0Eh
0x18000a734  mov     rax, [rax+18h]
0x18000a738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a73d  mov     [rsp+2A8h+var_268], eax
0x18000a741  mov     eax, [rsp+2A8h+var_268]
0x18000a745  test    eax, eax
0x18000a747  jns     short loc_18000A75E
0x18000a749  mov     r8d, edi; unsigned __int16
0x18000a74c  mov     r9d, [rsp+2A8h+var_268]; int
0x18000a751  mov     edx, 28Ch; unsigned int
  ... truncated ...
```
