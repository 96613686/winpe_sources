# DusmWwan::WwanCallback(_L2_NOTIFICATION_DATA *,void *)

- ea: `0x18003c1c0`
- end: `0x18003c557`
- name: `?WwanCallback@DusmWwan@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z`
- size: `919`
- prototype: `void __fastcall(struct _L2_NOTIFICATION_DATA *, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x1800062a0`
- `0x180006a38`
- `0x180006afc`
- `0x180013444`
- `0x18001bf4c`
- `0x18001db50`
- `0x18002f510`
- `0x18003ad84`
- `0x18003b814`
- `0x18003be1c`
- `0x18003c1c0`

## string_xrefs

- `0x18003c2fd`: `WwanMsmEventTypeProfileIStreamCreated`
- `0x18003c29a`: `WwanMsmEventTypeProfileIStreamDeleted`

## pseudocode

```c
void __fastcall DusmWwan::WwanCallback(struct _L2_NOTIFICATION_DATA *a1, void *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  GUID *v10; // rdi
  _DWORD *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  const wchar_t *pData; // rdi
  _DWORD *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  GUID *v18; // rbx
  unsigned int ProfileIndexImpl; // eax
  _DWORD *v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 NotificationCode; // rcx
  _DWORD *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 (__fastcall **v27)(); // rcx
  GUID InterfaceGuid; // xmm0
  _DWORD *v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // rdx
  int v35; // ebx
  __int64 v36; // rcx
  int v37; // edi
  _DWORD *v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  wil *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  int v44; // edi
  const wil::ResultException *v45; // rbx
  _DWORD *v46; // r8
  __int64 v47; // r9
  __int64 v48; // [rsp+50h] [rbp-68h] BYREF
  __int64 v49; // [rsp+58h] [rbp-60h] BYREF
  __int64 v50; // [rsp+60h] [rbp-58h] BYREF
  const wil::ResultException *v51; // [rsp+68h] [rbp-50h] BYREF
  __int64 (__fastcall **v52)(); // [rsp+70h] [rbp-48h] BYREF
  GUID v53; // [rsp+78h] [rbp-40h]
  unsigned int v54; // [rsp+88h] [rbp-30h]
  __int64 (__fastcall ***v55)(); // [rsp+A8h] [rbp-10h]
  __int64 v56; // [rsp+C0h] [rbp+8h] BYREF
  __int64 p_InterfaceGuid; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v58; // [rsp+D8h] [rbp+20h] BYREF

  if ( a1->NotificationSource != 2 )
  {
    if ( a1->NotificationSource != 4 )
      return;
    NotificationCode = a1->NotificationCode;
    if ( (_DWORD)NotificationCode )
    {
      if ( (_DWORD)NotificationCode != 1 )
        return;
      v24 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(NotificationCode, a2) + 8);
      if ( *v24 > 5u )
      {
        v56 = (__int64)"WwanPnpEventTypeInterfaceRemoval";
        p_InterfaceGuid = (__int64)&a1->InterfaceGuid;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          (int)v24,
          (int)&dword_18005B524,
          v25,
          v26,
          &p_InterfaceGuid,
          (const wchar_t **)&v56);
      }
      v27 = off_18004CDB8;
      InterfaceGuid = a1->InterfaceGuid;
    }
    else
    {
      v29 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(NotificationCode, a2) + 8);
      if ( *v29 > 5u )
      {
        v56 = (__int64)"WwanPnpEventTypeInterfaceArrival";
        p_InterfaceGuid = (__int64)&a1->InterfaceGuid;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          (int)v29,
          (int)byte_18005B4CB,
          v30,
          v31,
          &p_InterfaceGuid,
          (const wchar_t **)&v56);
      }
      v27 = off_18004CD88;
      InterfaceGuid = a1->InterfaceGuid;
    }
    goto LABEL_32;
  }
  v3 = a1->NotificationCode - 6;
  if ( !(_DWORD)v3 || (v3 = (unsigned int)(v3 - 4), !(_DWORD)v3) || (v3 = (unsigned int)(v3 - 5), !(_DWORD)v3) )
  {
LABEL_10:
    v7 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v3, a2) + 8);
    if ( *v7 <= 5u )
    {
      v10 = &a1->InterfaceGuid;
    }
    else
    {
      p_InterfaceGuid = (__int64)"WwanNotificationSourceMsm";
      LODWORD(v56) = a1->NotificationCode;
      v10 = &a1->InterfaceGuid;
      v58 = (__int64)&a1->InterfaceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (int)v7,
        (int)byte_18005B62B,
        v8,
        v9,
        &v58,
        (__int64)&v56,
        (const wchar_t **)&p_InterfaceGuid);
    }
    DusmWwan::UpdateConnectionStatesAndNotifyNLM(DusmWwan::s_pInstance, v10, a1->NotificationCode);
    return;
  }
  v4 = (unsigned int)(v3 - 3);
  if ( !(_DWORD)v4 )
  {
    v20 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v4, a2) + 8);
    if ( *v20 > 5u )
    {
      v56 = (__int64)"WwanMsmEventTypeSubscriberInfo";
      p_InterfaceGuid = (__int64)&a1->InterfaceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        (int)v20,
        (int)&dword_18005B5D4,
        v21,
        v22,
        &p_InterfaceGuid,
        (const wchar_t **)&v56);
    }
    DusmWwan::UpdateConnectionList(DusmWwan::s_pInstance);
    return;
  }
  v5 = (unsigned int)(v4 - 27);
  if ( !(_DWORD)v5 )
  {
    pData = (const wchar_t *)a1->pData;
    v15 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v5, a2) + 8);
    if ( *v15 <= 5u )
    {
      v18 = &a1->InterfaceGuid;
    }
    else
    {
      v58 = (__int64)"WwanMsmEventTypeProfileIStreamCreated";
      LODWORD(v56) = *((_DWORD *)pData + 769);
      v48 = (__int64)(pData + 1540);
      v49 = (__int64)(pData + 1556);
      LODWORD(p_InterfaceGuid) = *((_DWORD *)pData + 768);
      v18 = &a1->InterfaceGuid;
      v50 = (__int64)v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (int)v15,
        (int)&byte_18005B699,
        v16,
        v17,
        &v50,
        (__int64)&p_InterfaceGuid,
        (const WCHAR **)&v49,
        (const WCHAR **)&v48,
        (__int64)&v56,
        (const wchar_t **)&v58);
    }
    try
    {
      ProfileIndexImpl = QueryProfileIndexImpl(v18, pData);
      v27 = off_18004CDE8;
      InterfaceGuid = *v18;
      v54 = ProfileIndexImpl;
    }
    catch ( const wil::ResultException *v51 )
    {
      if ( (wil::ResultFromCaughtException((wil *)off_18004CDE8) & 0x1FFF0000) == 0x70000 )
        v44 = (unsigned __int16)wil::ResultFromCaughtException(v41);
      else
        v44 = wil::ResultFromCaughtException(v41);
      v45 = v51;
      v46 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v43, v42) + 8);
      if ( *v46 > 5u )
      {
        v50 = *((_QWORD *)v45 + 6);
        LODWORD(v56) = *((_DWORD *)v45 + 22);
        v49 = *((_QWORD *)v45 + 10);
        LODWORD(p_InterfaceGuid) = *((_DWORD *)v45 + 8);
        LODWORD(v58) = v44;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          (int)v46,
          (int)&byte_18005B453,
          (__int64)v46,
          v47,
          (__int64)&v58,
          (__int64)&p_InterfaceGuid,
          (const wchar_t **)&v49,
          (__int64)&v56,
          (const WCHAR **)&v50);
      }
      return;
    }
    catch ( ... )
    {
      v33 = wil::ResultFromCaughtException((wil *)off_18004CDE8);
      v35 = v33;
      v36 = v33 & 0x1FFF0000;
      v37 = (unsigned __int16)v33;
      if ( (_DWORD)v36 != 458752 )
        v37 = v33;
      v38 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v36, v34) + 8);
      if ( *v38 > 5u )
      {
        LODWORD(v56) = v35;
        LODWORD(p_InterfaceGuid) = v37;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v38,
          (int)byte_18005B499,
          v39,
          v40,
          (__int64)&p_InterfaceGuid,
          (__int64)&v56);
      }
      return;
    }
LABEL_32:
    v52 = v27;
    v53 = InterfaceGuid;
    v55 = &v52;
    DusmAsync::SubmitOrderedWork((__int64)&v52);
    std::function<long (void)>::~function<long (void)>((__int64)&v52, v32);
    return;
  }
  v6 = (unsigned int)(v5 - 2);
  if ( (_DWORD)v6 )
  {
    v3 = (unsigned int)(v6 - 1);
    if ( (_DWORD)v3 )
    {
      v3 = (unsigned int)(v3 - 1);
      if ( (unsigned int)v3 > 1 )
        return;
    }
    goto LABEL_10;
  }
  v11 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v6, a2) + 8);
  if ( *v11 > 5u )
  {
    v56 = (__int64)"WwanMsmEventTypeProfileIStreamDeleted";
    p_InterfaceGuid = (__int64)&a1->InterfaceGuid;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
      (int)v11,
      (int)byte_18005B57D,
      v12,
      v13,
      &p_InterfaceGuid,
      (const wchar_t **)&v56);
  }
  DusmCache::FlushCostCache();
}

```

## disassembly

```asm
0x18003c1c0  mov     [rsp+arg_8], rbx
0x18003c1c5  push    rdi
0x18003c1c6  sub     rsp, 0B0h
0x18003c1cd  mov     rbx, rcx
0x18003c1d0  cmp     dword ptr [rcx], 2
0x18003c1d3  jnz     loc_18003C43A
0x18003c1d9  mov     ecx, [rcx+4]
0x18003c1dc  sub     ecx, 6
0x18003c1df  jz      short loc_18003C219
0x18003c1e1  sub     ecx, 4
0x18003c1e4  jz      short loc_18003C219
0x18003c1e6  sub     ecx, 5
0x18003c1e9  jz      short loc_18003C219
0x18003c1eb  sub     ecx, 3
0x18003c1ee  jz      loc_18003C3BF
0x18003c1f4  sub     ecx, 1Bh
0x18003c1f7  jz      loc_18003C2E5
0x18003c1fd  sub     ecx, 2
0x18003c200  jz      loc_18003C28A
0x18003c206  sub     ecx, 1
0x18003c209  jz      short loc_18003C219
0x18003c20b  sub     ecx, 1
0x18003c20e  jz      short loc_18003C219
0x18003c210  cmp     ecx, 1
0x18003c213  jnz     loc_18003C544
0x18003c219  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003c21e  mov     rcx, [rax+8]; int
0x18003c222  mov     eax, [rcx]
0x18003c224  cmp     eax, 5
0x18003c227  jbe     loc_18003C41E
0x18003c22d  lea     rax, aWwannotificati; "WwanNotificationSourceMsm"
0x18003c234  mov     [rsp+0B8h+arg_10], rax
0x18003c23c  mov     eax, [rbx+4]
0x18003c23f  mov     dword ptr [rsp+0B8h+arg_0], eax
0x18003c246  lea     rdi, [rbx+8]
0x18003c24a  mov     [rsp+0B8h+arg_18], rdi
0x18003c252  lea     rax, [rsp+0B8h+arg_10]
0x18003c25a  mov     [rsp+0B8h+var_88], rax; __int64
0x18003c25f  lea     rax, [rsp+0B8h+arg_0]
0x18003c267  mov     [rsp+0B8h+var_90], rax; __int64
0x18003c26c  lea     rax, [rsp+0B8h+arg_18]
0x18003c274  mov     [rsp+0B8h+var_98], rax; __int64
0x18003c279  lea     rdx, byte_18005B62B
0x18003c280  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003c285  jmp     loc_18003C422
0x18003c28a  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003c28f  mov     rcx, [rax+8]; int
0x18003c293  mov     eax, [rcx]
0x18003c295  cmp     eax, 5
0x18003c298  jbe     short loc_18003C2DB
0x18003c29a  lea     rax, aWwanmsmeventty; "WwanMsmEventTypeProfileIStreamDeleted"
0x18003c2a1  mov     [rsp+0B8h+arg_0], rax
0x18003c2a9  lea     rax, [rbx+8]
0x18003c2ad  mov     [rsp+0B8h+arg_10], rax
0x18003c2b5  lea     rax, [rsp+0B8h+arg_0]
0x18003c2bd  mov     [rsp+0B8h+var_90], rax; __int64
0x18003c2c2  lea     rax, [rsp+0B8h+arg_10]
0x18003c2ca  mov     [rsp+0B8h+var_98], rax; __int64
0x18003c2cf  lea     rdx, byte_18005B57D
0x18003c2d6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18003c2db  call    ?FlushCostCache@DusmCache@@SAXXZ; DusmCache::FlushCostCache(void)
0x18003c2e0  jmp     loc_18003C544
0x18003c2e5  mov     rdi, [rbx+20h]
0x18003c2e9  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003c2ee  mov     rcx, [rax+8]; int
0x18003c2f2  mov     eax, [rcx]
0x18003c2f4  cmp     eax, 5
0x18003c2f7  jbe     loc_18003C39A
0x18003c2fd  lea     rax, aWwanmsmeventty_1; "WwanMsmEventTypeProfileIStreamCreated"
0x18003c304  mov     [rsp+0B8h+arg_18], rax
0x18003c30c  mov     eax, [rdi+0C04h]
0x18003c312  mov     dword ptr [rsp+0B8h+arg_0], eax
0x18003c319  lea     rax, [rdi+0C08h]
0x18003c320  mov     [rsp+0B8h+var_68], rax
0x18003c325  lea     rax, [rdi+0C28h]
0x18003c32c  mov     [rsp+0B8h+var_60], rax
0x18003c331  mov     eax, [rdi+0C00h]
0x18003c337  mov     dword ptr [rsp+0B8h+arg_10], eax
0x18003c33e  add     rbx, 8
0x18003c342  mov     [rsp+0B8h+var_58], rbx
0x18003c347  lea     rax, [rsp+0B8h+arg_18]
0x18003c34f  mov     [rsp+0B8h+var_70], rax; __int64
0x18003c354  lea     rax, [rsp+0B8h+arg_0]
0x18003c35c  mov     [rsp+0B8h+var_78], rax; __int64
0x18003c361  lea     rax, [rsp+0B8h+var_68]
0x18003c366  mov     [rsp+0B8h+var_80], rax; __int64
0x18003c36b  lea     rax, [rsp+0B8h+var_60]
0x18003c370  mov     [rsp+0B8h+var_88], rax; __int64
0x18003c375  lea     rax, [rsp+0B8h+arg_10]
0x18003c37d  mov     [rsp+0B8h+var_90], rax; __int64
0x18003c382  lea     rax, [rsp+0B8h+var_58]
0x18003c387  mov     [rsp+0B8h+var_98], rax; __int64
0x18003c38c  lea     rdx, byte_18005B699; int
0x18003c393  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@U2@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@54AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003c398  jmp     short loc_18003C39E
0x18003c39a  add     rbx, 8
0x18003c39e  mov     rdx, rdi; wchar_t *
0x18003c3a1  mov     rcx, rbx; struct _GUID *
0x18003c3a4  call    ?QueryProfileIndexImpl@@YAKAEBU_GUID@@PEB_W@Z; QueryProfileIndexImpl(_GUID const &,wchar_t const *)
0x18003c3a9  lea     rcx, off_18004CDE8
0x18003c3b0  movups  xmm0, xmmword ptr [rbx]
0x18003c3b3  mov     [rsp+0B8h+var_30], eax
0x18003c3ba  jmp     loc_18003C517
0x18003c3bf  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003c3c4  mov     rcx, [rax+8]; int
0x18003c3c8  mov     eax, [rcx]
0x18003c3ca  cmp     eax, 5
0x18003c3cd  jbe     short loc_18003C410
0x18003c3cf  lea     rax, aWwanmsmeventty_0; "WwanMsmEventTypeSubscriberInfo"
0x18003c3d6  mov     [rsp+0B8h+arg_0], rax
0x18003c3de  lea     rax, [rbx+8]
0x18003c3e2  mov     [rsp+0B8h+arg_10], rax
0x18003c3ea  lea     rax, [rsp+0B8h+arg_0]
0x18003c3f2  mov     [rsp+0B8h+var_90], rax; __int64
0x18003c3f7  lea     rax, [rsp+0B8h+arg_10]
0x18003c3ff  mov     [rsp+0B8h+var_98], rax; __int64
0x18003c404  lea     rdx, dword_18005B5D4
0x18003c40b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18003c410  mov     rcx, cs:?s_pInstance@DusmWwan@@0PEAV1@EA; this
0x18003c417  call    ?UpdateConnectionList@DusmWwan@@AEBAXXZ; DusmWwan::UpdateConnectionList(void)
0x18003c41c  jmp     short loc_18003C435
0x18003c41e  lea     rdi, [rbx+8]
0x18003c422  mov     r8d, [rbx+4]
0x18003c426  mov     rdx, rdi
0x18003c429  mov     rcx, cs:?s_pInstance@DusmWwan@@0PEAV1@EA; DusmWwan * DusmWwan::s_pInstance
0x18003c430  call    ?UpdateConnectionStatesAndNotifyNLM@DusmWwan@@AEBAXAEBU_GUID@@W4WWAN_MSM_EVENT_TYPE@@@Z; DusmWwan::UpdateConnectionStatesAndNotifyNLM(_GUID const &,WWAN_MSM_EVENT_TYPE)
0x18003c435  jmp     loc_18003C544
0x18003c43a  cmp     dword ptr [rcx], 4
0x18003c43d  jnz     loc_18003C544
0x18003c443  mov     ecx, [rcx+4]
0x18003c446  test    ecx, ecx
0x18003c448  jz      short loc_18003C4B6
0x18003c44a  cmp     ecx, 1
0x18003c44d  jnz     loc_18003C544
0x18003c453  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003c458  mov     rcx, [rax+8]; int
0x18003c45c  mov     eax, [rcx]
0x18003c45e  cmp     eax, 5
0x18003c461  jbe     short loc_18003C4A4
0x18003c463  lea     rax, aWwanpnpeventty; "WwanPnpEventTypeInterfaceRemoval"
0x18003c46a  mov     [rsp+0B8h+arg_0], rax
0x18003c472  lea     rax, [rbx+8]
0x18003c476  mov     [rsp+0B8h+arg_10], rax
0x18003c47e  lea     rax, [rsp+0B8h+arg_0]
0x18003c486  mov     [rsp+0B8h+var_90], rax; __int64
0x18003c48b  lea     rax, [rsp+0B8h+arg_10]
0x18003c493  mov     [rsp+0B8h+var_98], rax; __int64
0x18003c498  lea     rdx, dword_18005B524
0x18003c49f  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18003c4a4  mov     eax, 8
0x18003c4a9  lea     rcx, off_18004CDB8
0x18003c4b0  movups  xmm0, xmmword ptr [rbx+rax]
0x18003c4b4  jmp     short loc_18003C517
0x18003c4b6  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003c4bb  mov     rcx, [rax+8]; int
0x18003c4bf  mov     eax, [rcx]
0x18003c4c1  cmp     eax, 5
0x18003c4c4  jbe     short loc_18003C507
0x18003c4c6  lea     rax, aWwanpnpeventty_0; "WwanPnpEventTypeInterfaceArrival"
0x18003c4cd  mov     [rsp+0B8h+arg_0], rax
0x18003c4d5  lea     rax, [rbx+8]
0x18003c4d9  mov     [rsp+0B8h+arg_10], rax
0x18003c4e1  lea     rax, [rsp+0B8h+arg_0]
0x18003c4e9  mov     [rsp+0B8h+var_90], rax; __int64
0x18003c4ee  lea     rax, [rsp+0B8h+arg_10]
0x18003c4f6  mov     [rsp+0B8h+var_98], rax; __int64
0x18003c4fb  lea     rdx, byte_18005B4CB
0x18003c502  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18003c507  mov     eax, 8
0x18003c50c  lea     rcx, off_18004CD88
0x18003c513  movups  xmm0, xmmword ptr [rax+rbx]
0x18003c517  lea     rax, [rsp+0B8h+var_48]
0x18003c51c  mov     [rsp+0B8h+var_48], rcx
0x18003c521  movdqu  [rsp+0B8h+var_40], xmm0
0x18003c527  mov     [rsp+0B8h+var_10], rax
0x18003c52f  lea     rcx, [rsp+0B8h+var_48]
0x18003c534  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x18003c539  lea     rcx, [rsp+0B8h+var_48]
0x18003c53e  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18003c543  nop
0x18003c544  mov     rbx, [rsp+0B8h+arg_8]
0x18003c54c  add     rsp, 0B0h
0x18003c553  pop     rdi
0x18003c554  retn
0x18003c555  jmp     short loc_18003C544
```
