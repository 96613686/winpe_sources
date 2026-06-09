# CEventSystem::Remove(ushort *,ushort *,int *)

- ea: `0x180021e40`
- end: `0x1800226f8`
- name: `?Remove@CEventSystem@@UEAAJPEAG0PEAH@Z`
- size: `2232`
- prototype: `int(CEventSystem *__hidden this, unsigned __int16 *, unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x180005cf0`
- `0x180008938`
- `0x18001f46c`
- `0x180021e40`
- `0x1800231a0`
- `0x18003ecb0`
- `0x1800434de`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800222be`
- `msvcrt!wcsstr` at `0x1800222d7`
- `msvcrt!wcsstr` at `0x1800222f0`
- `msvcrt!wcsstr` at `0x180022309`
- `msvcrt!wcsstr` at `0x180022322`
- `msvcrt!wcsstr` at `0x18002233b`
- `msvcrt!wcsstr` at `0x180022354`
- `msvcrt!wcsstr` at `0x1800222be`
- `msvcrt!wcsstr` at `0x1800222d7`
- `msvcrt!wcsstr` at `0x1800222f0`
- `msvcrt!wcsstr` at `0x180022309`
- `msvcrt!wcsstr` at `0x180022322`
- `msvcrt!wcsstr` at `0x18002233b`
- `msvcrt!wcsstr` at `0x180022354`
- `msvcrt!_itow_s` at `0x1800223df`
- `msvcrt!_itow_s` at `0x1800223df`
- `msvcrt!_wcsicmp` at `0x18002223f`
- `msvcrt!_wcsicmp` at `0x18002223f`
- `ntdll!RtlApplicationVerifierStop` at `0x18002228b`
- `ntdll!RtlApplicationVerifierStop` at `0x180022397`
- `ntdll!RtlApplicationVerifierStop` at `0x18002249e`
- `ntdll!RtlApplicationVerifierStop` at `0x180022515`
- `ntdll!RtlApplicationVerifierStop` at `0x1800225cc`
- `ntdll!RtlApplicationVerifierStop` at `0x180022666`
- `ntdll!RtlApplicationVerifierStop` at `0x18002228b`
- `ntdll!RtlApplicationVerifierStop` at `0x180022397`
- `ntdll!RtlApplicationVerifierStop` at `0x18002249e`
- `ntdll!RtlApplicationVerifierStop` at `0x180022515`
- `ntdll!RtlApplicationVerifierStop` at `0x1800225cc`
- `ntdll!RtlApplicationVerifierStop` at `0x180022666`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021f4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021f4f`

## string_xrefs

- `0x180022201`: `com\complus\src\events\tier1\enum.cpp`
- `0x1800221df`: `com\complus\src\events\tier1\eventsystemobj.cpp`
- `0x1800222cd`: `SubscriberCLSID`
- `0x180022331`: `OwnerSID`
- `0x180022492`: `Invalid query syntax in IEventSystem::Remove`
- `0x18002227f`: `"ALL" used as queryCriteria to IEventSystem::Remove`
- `0x18002238b`: `queryCriteria in IEventSystem::Remove contains no "identifying" subscriber properties`
- `0x180022509`: `queryCriteria in IEventSystem::Remove selected a COM+-configured object`
- `0x1800225c0`: `E_ACCESSDENIED removing a transient subscription in IEventSystem::Remove`
- `0x18002265a`: `queryCriteria in IEventSystem::Remove selects multiple objects`

## pseudocode

```c
__int64 __fastcall CEventSystem::Remove(CEventSystem *this, unsigned __int16 *a2, unsigned __int16 *a3, int *a4)
{
  char v6; // r14
  char v7; // r12
  int v8; // esi
  int v9; // r13d
  LPVOID v10; // rax
  struct IEventSystemTier2 *v11; // rsi
  int v12; // esi
  int v13; // r13d
  int Description2; // [rsp+28h] [rbp-E0h]
  int v16; // [rsp+54h] [rbp-B4h]
  int v17; // [rsp+54h] [rbp-B4h]
  int v18; // [rsp+5Ch] [rbp-ACh] BYREF
  int v19; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+68h] [rbp-A0h] BYREF
  int *v21; // [rsp+70h] [rbp-98h] BYREF
  int v22; // [rsp+78h] [rbp-90h] BYREF
  int v23; // [rsp+7Ch] [rbp-8Ch]
  __int64 v24; // [rsp+80h] [rbp-88h] BYREF
  struct IEventSystemTier2 *v25; // [rsp+88h] [rbp-80h]
  int v26; // [rsp+90h] [rbp-78h]
  CEventSystem *v27; // [rsp+98h] [rbp-70h]
  __int64 v28; // [rsp+A0h] [rbp-68h] BYREF
  wchar_t Buffer[12]; // [rsp+A8h] [rbp-60h] BYREF

  v21 = a4;
  v27 = this;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !a3 || !a2 || !*a3 )
    return 2147942487LL;
  v6 = 0;
  v7 = 0;
  if ( !wcscmp_0(a2, L"EventSystem.EventSubscriptionCollection") )
  {
    v8 = 1;
    v18 = 1;
    v7 = 1;
  }
  else if ( !wcscmp_0(a2, L"EventSystem.EventClass") )
  {
    v8 = 0;
    v18 = 0;
  }
  else if ( !wcscmp_0(a2, L"EventSystem.EventSubscription") )
  {
    v8 = 1;
    v18 = 1;
  }
  else
  {
    if ( wcscmp_0(a2, L"EventSystem.EventClassCollection") )
    {
      if ( !wcscmp_0(a2, L"EventSystem.EventPublisherCollection") || !wcscmp_0(a2, L"EventSystem.EventPublisher") )
        return 1;
      else
        return 2147942487LL;
    }
    v8 = 0;
    v18 = 0;
    v7 = 1;
  }
  v25 = 0;
  v24 = 0;
  if ( EsVerifierSettings::s_bEnableRemoveQueryValidityHeuristics )
  {
    if ( !_wcsicmp(a3, L"ALL") )
    {
      RtlApplicationVerifierStop(
        0x10000419u,
        "\"ALL\" used as queryCriteria to IEventSystem::Remove",
        a2,
        "progID parameter",
        a3,
        "queryCriteria parameter",
        0,
        Description4,
        0,
        Description4);
      v6 = 1;
    }
    if ( !v6
      && v8 == 1
      && !wcsstr(a3, L"SubscriptionID")
      && !wcsstr(a3, L"SubscriberCLSID")
      && !wcsstr(a3, L"SubscriberMoniker")
      && !wcsstr(a3, L"SubscriptionName")
      && !wcsstr(a3, L"Description")
      && !wcsstr(a3, L"OwnerSID")
      && !wcsstr(a3, L"MachineName") )
    {
      RtlApplicationVerifierStop(
        0x1000041Au,
        "queryCriteria in IEventSystem::Remove contains no \"identifying\" subscriber properties",
        a2,
        "progID parameter",
        a3,
        "queryCriteria parameter",
        0,
        Description4,
        0,
        Description4);
      v6 = 1;
    }
  }
  v19 = *((unsigned __int8 *)v27 + 60);
  v25 = (struct IEventSystemTier2 *)*((_QWORD *)v27 + 3);
  v9 = -2147024882;
  v22 = -2147024882;
  v10 = CoTaskMemAlloc(0xA0u);
  if ( v10 )
  {
    LOBYTE(Description2) = 0;
    v11 = (struct IEventSystemTier2 *)EventObjectCollection::EventObjectCollection(
                                        (__int64)v10,
                                        v8,
                                        a3,
                                        (__int64)v21,
                                        v25,
                                        Description2,
                                        1u,
                                        v19,
                                        1,
                                        &v22);
    v9 = v22;
  }
  else
  {
    v11 = 0;
  }
  v25 = v11;
  if ( !v11 )
    InternalError(L"com\\complus\\src\\events\\tier1\\enum.cpp", 0x299u, 0xC0001204, 0x10u);
  if ( v9 < 0 )
  {
    if ( v11 )
      EventObjectCollection::`scalar deleting destructor'(v11);
    v11 = 0;
    v25 = 0;
  }
  else
  {
    (*(void (__fastcall **)(struct IEventSystemTier2 *))(*(_QWORD *)v11 + 8LL))(v11);
  }
  v16 = v9;
  if ( v9 < 0 )
  {
    _itow_s(*v21, Buffer, 0xCu, 10);
    CEventSystem::SetQueryErrorInfo(v27, 0xC000120C, 4u, a2, a3, Buffer, &a3[*v21]);
    if ( (v9 == -2147220989 || v9 == -2147220988 || v9 == -2147316576)
      && EsVerifierSettings::s_bEnableRemoveQueryValidityHeuristics
      && !v6 )
    {
      RtlApplicationVerifierStop(
        0x10000418u,
        "Invalid query syntax in IEventSystem::Remove",
        a2,
        "progID parameter",
        a3,
        "queryCriteria parameter",
        (PVOID)*v21,
        "Approximate error location",
        0,
        Description4);
      v6 = 1;
    }
  }
  else
  {
    v16 = (*(__int64 (__fastcall **)(struct IEventSystemTier2 *, __int64 *))(*(_QWORD *)v11 + 72LL))(v11, &v24);
    (*(void (__fastcall **)(struct IEventSystemTier2 *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( !v16 )
  {
    v12 = 0;
    v26 = 0;
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 40LL))(v24);
    v13 = v18;
    while ( 1 )
    {
      v20 = 0;
      v18 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v24 + 32LL))(v24, 1, &v20, &v18);
      if ( v16 < 0 )
        break;
      if ( v16 == 1 || v18 != 1 )
      {
        v16 = 0;
        break;
      }
      ++v23;
      v21 = 0;
      v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, int **))v20)(v20, &IID_IEventSystemPersistable, &v21);
      if ( v17 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventsystemobj.cpp", 0x225u, 0x10u, v17);
      v16 = (*(__int64 (__fastcall **)(int *, _QWORD, _QWORD))(*(_QWORD *)v21 + 32LL))(
              v21,
              *((unsigned __int8 *)v27 + 60),
              *((_QWORD *)v27 + 3));
      if ( v16 < 0 )
      {
        v26 = ++v12;
        if ( EsVerifierSettings::s_bEnableRemoveQueryValidityHeuristics && !v6 )
        {
          if ( v16 == -2147220978 )
          {
            RtlApplicationVerifierStop(
              0x1000041Bu,
              "queryCriteria in IEventSystem::Remove selected a COM+-configured object",
              a2,
              "progID parameter",
              a3,
              "queryCriteria parameter",
              0,
              Description4,
              0,
              Description4);
            v6 = 1;
          }
          else if ( v16 == -2147024891 && v13 == 1 )
          {
            v28 = 0;
            (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v20)(
              v20,
              &GUID_9b724996_d383_4c5f_b0f6_2814708c7633,
              &v28);
            v19 = 0;
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 24LL))(v28, &v19);
            if ( v19 )
            {
              RtlApplicationVerifierStop(
                0x1000041Cu,
                "E_ACCESSDENIED removing a transient subscription in IEventSystem::Remove",
                a2,
                "progID parameter",
                a3,
                "queryCriteria parameter",
                0,
                Description4,
                0,
                Description4);
              v6 = 1;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
        }
      }
      (*(void (__fastcall **)(int *))(*(_QWORD *)v21 + 16LL))(v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
      if ( !v7 )
      {
        if ( EsVerifierSettings::s_bEnableRemoveQueryValidityHeuristics && !v6 )
        {
          v18 = 0;
          (*(void (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v24 + 32LL))(v24, 1, &v20, &v18);
          if ( v18 )
            RtlApplicationVerifierStop(
              0x1000041Du,
              "queryCriteria in IEventSystem::Remove selects multiple objects",
              a2,
              "progID parameter",
              a3,
              "queryCriteria parameter",
              0,
              Description4,
              0,
              Description4);
          if ( v20 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v20 = 0;
          }
        }
        break;
      }
    }
    if ( v7 )
      v16 = v12 != 0 ? 0x8004020B : 0;
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180021e40  push    rbx
0x180021e42  push    rsi
0x180021e43  push    rdi
0x180021e44  push    r12
0x180021e46  push    r13
0x180021e48  push    r14
0x180021e4a  push    r15
0x180021e4c  sub     rsp, 0D0h
0x180021e53  mov     rax, cs:__security_cookie
0x180021e5a  xor     rax, rsp
0x180021e5d  mov     [rsp+108h+var_48], rax
0x180021e65  mov     [rsp+108h+var_98], r9
0x180021e6a  mov     rbx, r8
0x180021e6d  mov     rdi, rdx
0x180021e70  mov     [rsp+108h+var_70], rcx
0x180021e78  xor     r13d, r13d
0x180021e7b  test    r9, r9
0x180021e7e  jz      loc_1800226EA
0x180021e84  mov     [r9], r13d
0x180021e87  test    rbx, rbx
0x180021e8a  jz      loc_1800226F1
0x180021e90  test    rdx, rdx
0x180021e93  jz      loc_1800226F1
0x180021e99  cmp     [r8], r13w
0x180021e9d  jz      loc_1800226F1
0x180021ea3  mov     [rsp+108h+var_B4], r13d
0x180021ea8  mov     r14b, r13b
0x180021eab  mov     r12b, r13b
0x180021eae  mov     [rsp+108h+var_B0], r13b
0x180021eb3  lea     rdx, aEventsystemEve_1; "EventSystem.EventSubscriptionCollection"
0x180021eba  mov     rcx, rdi; String1
0x180021ebd  call    wcscmp_0
0x180021ec2  test    eax, eax
0x180021ec4  jz      loc_180022212
0x180021eca  lea     rdx, aEventsystemEve_2; "EventSystem.EventClass"
0x180021ed1  mov     rcx, rdi; String1
0x180021ed4  call    wcscmp_0
0x180021ed9  test    eax, eax
0x180021edb  jz      loc_1800221C2
0x180021ee1  lea     rdx, aEventsystemEve_5; "EventSystem.EventSubscription"
0x180021ee8  mov     rcx, rdi; String1
0x180021eeb  call    wcscmp_0
0x180021ef0  test    eax, eax
0x180021ef2  jnz     loc_18002218F
0x180021ef8  lea     esi, [rax+1]
0x180021efb  mov     [rsp+108h+var_AC], esi
0x180021eff  mov     [rsp+108h+var_80], r13
0x180021f07  mov     [rsp+108h+var_88], r13
0x180021f0f  cmp     cs:?s_bEnableRemoveQueryValidityHeuristics@EsVerifierSettings@@0_NA, r13b; bool EsVerifierSettings::s_bEnableRemoveQueryValidityHeuristics
0x180021f16  jnz     loc_180022235
0x180021f1c  lea     r15, Description4
0x180021f23  mov     rcx, [rsp+108h+var_70]
0x180021f2b  movzx   eax, byte ptr [rcx+3Ch]
0x180021f2f  mov     [rsp+108h+var_A8], eax
0x180021f33  mov     rax, [rcx+18h]
0x180021f37  mov     [rsp+108h+var_80], rax
0x180021f3f  mov     r13d, 8007000Eh
0x180021f45  mov     [rsp+108h+var_90], r13d
0x180021f4a  mov     ecx, 0A0h; cb
0x180021f4f  call    cs:__imp_CoTaskMemAlloc
0x180021f55  test    rax, rax
0x180021f58  jz      loc_180022036
0x180021f5e  lea     rcx, [rsp+108h+var_90]
0x180021f63  mov     [rsp+108h+Description4], rcx
0x180021f68  mov     dword ptr [rsp+108h+Value4], 1
0x180021f70  mov     ecx, [rsp+108h+var_A8]
0x180021f74  mov     dword ptr [rsp+108h+Description3], ecx
0x180021f78  mov     byte ptr [rsp+108h+Value3], 1
0x180021f7d  mov     byte ptr [rsp+108h+Description2], 0
0x180021f82  mov     rcx, [rsp+108h+var_80]
0x180021f8a  mov     [rsp+108h+Value2], rcx
0x180021f8f  mov     r9, [rsp+108h+var_98]
0x180021f94  mov     r8, rbx
0x180021f97  mov     edx, esi
0x180021f99  mov     rcx, rax
0x180021f9c  call    ??0EventObjectCollection@@AEAA@W4__MIDL___MIDL_itf_esstruct_0000_0000_0001@@PEBGPEAHPEAUIEventSystemTier2@@_N4HHAEAJ@Z; EventObjectCollection::EventObjectCollection(__MIDL___MIDL_itf_esstruct_0000_0000_0001,ushort const *,int *,IEventSystemTier2 *,bool,bool,int,int,long &)
0x180021fa1  mov     rsi, rax
0x180021fa4  mov     r13d, [rsp+108h+var_90]
0x180021fa9  mov     [rsp+108h+var_80], rsi
0x180021fb1  test    rsi, rsi
0x180021fb4  jz      loc_1800221F0
0x180021fba  test    r13d, r13d
0x180021fbd  js      loc_1800223AA
0x180021fc3  mov     rax, [rsi]
0x180021fc6  mov     rcx, rsi
0x180021fc9  mov     rax, [rax+8]
0x180021fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fd2  mov     [rsp+108h+var_B4], r13d
0x180021fd7  mov     eax, [rsp+108h+var_B4]
0x180021fdb  xor     r13d, r13d
0x180021fde  test    eax, eax
0x180021fe0  js      loc_1800223C6
0x180021fe6  mov     rax, [rsi]
0x180021fe9  lea     rdx, [rsp+108h+var_88]
0x180021ff1  mov     rcx, rsi
0x180021ff4  mov     rax, [rax+48h]
0x180021ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ffd  mov     [rsp+108h+var_B4], eax
0x180022001  mov     rax, [rsi]
0x180022004  mov     rcx, rsi
0x180022007  mov     rax, [rax+10h]
0x18002200b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022010  mov     eax, [rsp+108h+var_B4]
0x180022014  test    eax, eax
0x180022016  jz      short loc_18002203D
0x180022018  mov     rcx, [rsp+108h+var_88]
0x180022020  test    rcx, rcx
0x180022023  jz      short loc_180022031
0x180022025  mov     rax, [rcx]
0x180022028  mov     rax, [rax+10h]
0x18002202c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022031  jmp     loc_1800226C3
0x180022036  xor     esi, esi
0x180022038  jmp     loc_180021FA9
0x18002203d  mov     esi, r13d
0x180022040  mov     [rsp+108h+var_78], r13d
0x180022048  mov     [rsp+108h+var_8C], r13d
0x18002204d  mov     rcx, [rsp+108h+var_88]
0x180022055  mov     rax, [rcx]
0x180022058  mov     rax, [rax+28h]
0x18002205c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022061  mov     r13d, [rsp+108h+var_AC]
0x180022066  mov     [rsp+108h+var_A0], 0
0x18002206f  mov     [rsp+108h+var_AC], 0
0x180022077  mov     rcx, [rsp+108h+var_88]
0x18002207f  mov     rax, [rcx]
0x180022082  lea     r9, [rsp+108h+var_AC]
0x180022087  lea     r8, [rsp+108h+var_A0]
0x18002208c  mov     edx, 1
0x180022091  mov     rax, [rax+20h]
0x180022095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002209a  mov     [rsp+108h+var_B4], eax
0x18002209e  mov     eax, [rsp+108h+var_B4]
0x1800220a2  test    eax, eax
0x1800220a4  js      loc_180022174
0x1800220aa  mov     eax, [rsp+108h+var_B4]
0x1800220ae  cmp     eax, 1
0x1800220b1  jz      loc_180022695
0x1800220b7  cmp     [rsp+108h+var_AC], 1
0x1800220bc  jnz     loc_180022695
0x1800220c2  inc     [rsp+108h+var_8C]
0x1800220c6  mov     [rsp+108h+var_98], 0
0x1800220cf  mov     rcx, [rsp+108h+var_A0]
0x1800220d4  mov     rax, [rcx]
0x1800220d7  lea     r8, [rsp+108h+var_98]
0x1800220dc  lea     rdx, IID_IEventSystemPersistable
0x1800220e3  mov     rax, [rax]
0x1800220e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220eb  mov     [rsp+108h+var_B4], eax
0x1800220ef  mov     eax, [rsp+108h+var_B4]
0x1800220f3  test    eax, eax
0x1800220f5  js      loc_1800221CF
0x1800220fb  mov     rcx, [rsp+108h+var_98]
0x180022100  mov     rax, [rcx]
0x180022103  mov     r8, [rsp+108h+var_70]
0x18002210b  movzx   edx, byte ptr [r8+3Ch]
0x180022110  mov     r8, [r8+18h]
0x180022114  mov     rax, [rax+20h]
0x180022118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002211d  mov     [rsp+108h+var_B4], eax
0x180022121  mov     eax, [rsp+108h+var_B4]
0x180022125  xor     ecx, ecx
0x180022127  test    eax, eax
0x180022129  js      loc_1800224B1
0x18002212f  mov     rcx, [rsp+108h+var_98]
0x180022134  mov     rax, [rcx]
0x180022137  mov     rax, [rax+10h]
0x18002213b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022140  mov     rcx, [rsp+108h+var_A0]
0x180022145  mov     rax, [rcx]
0x180022148  mov     rax, [rax+10h]
0x18002214c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022151  mov     [rsp+108h+var_A0], 0
0x18002215a  test    r12b, r12b
0x18002215d  jz      short loc_180022164
0x18002215f  jmp     loc_180022066
0x180022164  xor     r13d, r13d
0x180022167  cmp     cs:?s_bEnableRemoveQueryValidityHeuristics@EsVerifierSettings@@0_NA, r13b; bool EsVerifierSettings::s_bEnableRemoveQueryValidityHeuristics
0x18002216e  jnz     loc_1800225F3
0x180022174  test    r12b, r12b
0x180022177  jz      loc_180022018
0x18002217d  neg     esi
0x18002217f  sbb     eax, eax
0x180022181  and     eax, 8004020Bh
0x180022186  mov     [rsp+108h+var_B4], eax
0x18002218a  jmp     loc_180022018
0x18002218f  lea     rdx, aEventsystemEve_3; "EventSystem.EventClassCollection"
0x180022196  mov     rcx, rdi; String1
0x180022199  call    wcscmp_0
0x18002219e  test    eax, eax
0x1800221a0  jz      loc_180022228
0x1800221a6  lea     rdx, aEventsystemEve_4; "EventSystem.EventPublisherCollection"
0x1800221ad  mov     rcx, rdi; String1
0x1800221b0  call    wcscmp_0
0x1800221b5  test    eax, eax
0x1800221b7  jnz     loc_1800226A2
0x1800221bd  jmp     loc_1800226BC
0x1800221c2  mov     esi, r13d
0x1800221c5  mov     [rsp+108h+var_AC], r13d
0x1800221ca  jmp     loc_180021EFF
0x1800221cf  mov     r8d, 10h; unsigned __int16
0x1800221d5  mov     r9d, [rsp+108h+var_B4]; int
0x1800221da  mov     edx, 225h; unsigned int
0x1800221df  lea     rcx, aComComplusSrcE_6; "com\\complus\\src\\events\\tier1\\event"...
0x1800221e6  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x1800221eb  jmp     loc_1800220FB
0x1800221f0  mov     edx, 299h; unsigned int
0x1800221f5  mov     r9d, 10h; unsigned __int16
0x1800221fb  mov     r8d, 0C0001204h; unsigned int
0x180022201  lea     rcx, aComComplusSrcE_21; "com\\complus\\src\\events\\tier1\\enum."...
0x180022208  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18002220d  jmp     loc_180021FBA
0x180022212  mov     esi, 1
0x180022217  mov     [rsp+108h+var_AC], esi
0x18002221b  mov     r12b, sil
0x18002221e  mov     [rsp+108h+var_B0], r12b
0x180022223  jmp     loc_180021EFF
0x180022228  mov     esi, r13d
0x18002222b  mov     [rsp+108h+var_AC], r13d
0x180022230  mov     r12b, 1
0x180022233  jmp     short loc_18002221E
0x180022235  lea     rdx, aAll; "ALL"
0x18002223c  mov     rcx, rbx; String1
0x18002223f  call    cs:__imp__wcsicmp
0x180022245  lea     r15, Description4
0x18002224c  test    eax, eax
0x18002224e  jnz     short loc_18002229B
0x180022250  mov     [rsp+108h+Description4], r15; Description4
0x180022255  mov     [rsp+108h+Value4], r13; Value4
0x18002225a  mov     [rsp+108h+Description3], r15; Description3
0x18002225f  mov     [rsp+108h+Value3], r13; Value3
0x180022264  lea     r13, Description2; "queryCriteria parameter"
0x18002226b  mov     [rsp+108h+Description2], r13; Description2
0x180022270  mov     [rsp+108h+Value2], rbx; Value2
0x180022275  lea     r9, Description1; "progID parameter"
0x18002227c  mov     r8, rdi; Value1
0x18002227f  lea     rdx, Message; "\"ALL\" used as queryCriteria to IEvent"...
0x180022286  mov     ecx, 10000419h; Code
0x18002228b  call    cs:__imp_RtlApplicationVerifierStop
0x180022291  mov     r14b, 1
0x180022294  mov     [rsp+108h+var_B8], r14b
0x180022299  jmp     short loc_1800222A2
0x18002229b  lea     r13, Description2; "queryCriteria parameter"
0x1800222a2  test    r14b, r14b
0x1800222a5  jnz     loc_180021F23
0x1800222ab  cmp     esi, 1
0x1800222ae  jnz     loc_180021F23
0x1800222b4  lea     rdx, aSubscriptionid; "SubscriptionID"
0x1800222bb  mov     rcx, rbx; Str
0x1800222be  call    cs:__imp_wcsstr
0x1800222c4  test    rax, rax
0x1800222c7  jnz     loc_180021F23
0x1800222cd  lea     rdx, aSubscriberclsi; "SubscriberCLSID"
0x1800222d4  mov     rcx, rbx; Str
0x1800222d7  call    cs:__imp_wcsstr
0x1800222dd  test    rax, rax
0x1800222e0  jnz     loc_180021F23
0x1800222e6  lea     rdx, aSubscribermoni; "SubscriberMoniker"
0x1800222ed  mov     rcx, rbx; Str
0x1800222f0  call    cs:__imp_wcsstr
0x1800222f6  test    rax, rax
0x1800222f9  jnz     loc_180021F23
0x1800222ff  lea     rdx, aSubscriptionna; "SubscriptionName"
0x180022306  mov     rcx, rbx; Str
0x180022309  call    cs:__imp_wcsstr
0x18002230f  test    rax, rax
0x180022312  jnz     loc_180021F23
0x180022318  lea     rdx, aDescription; "Description"
0x18002231f  mov     rcx, rbx; Str
0x180022322  call    cs:__imp_wcsstr
0x180022328  test    rax, rax
0x18002232b  jnz     loc_180021F23
0x180022331  lea     rdx, aOwnersid; "OwnerSID"
0x180022338  mov     rcx, rbx; Str
0x18002233b  call    cs:__imp_wcsstr
0x180022341  test    rax, rax
0x180022344  jnz     loc_180021F23
0x18002234a  lea     rdx, aMachinename; "MachineName"
0x180022351  mov     rcx, rbx; Str
0x180022354  call    cs:__imp_wcsstr
0x18002235a  test    rax, rax
0x18002235d  jnz     loc_180021F23
0x180022363  mov     [rsp+108h+Description4], r15; Description4
0x180022368  mov     [rsp+108h+Value4], rax; Value4
0x18002236d  mov     [rsp+108h+Description3], r15; Description3
0x180022372  mov     [rsp+108h+Value3], rax; Value3
0x180022377  mov     [rsp+108h+Description2], r13; Description2
0x18002237c  mov     [rsp+108h+Value2], rbx; Value2
0x180022381  lea     r9, Description1; "progID parameter"
0x180022388  mov     r8, rdi; Value1
0x18002238b  lea     rdx, aQuerycriteriaI; "queryCriteria in IEventSystem::Remove c"...
0x180022392  mov     ecx, 1000041Ah; Code
0x180022397  call    cs:__imp_RtlApplicationVerifierStop
0x18002239d  mov     r14b, sil
0x1800223a0  mov     [rsp+108h+var_B8], sil
0x1800223a5  jmp     loc_180021F23
0x1800223aa  test    rsi, rsi
0x1800223ad  jz      short loc_1800223B7
0x1800223af  mov     rcx, rsi; this
0x1800223b2  call    ??_GEventObjectCollection@@AEAAPEAXI@Z; EventObjectCollection::`scalar deleting destructor'(uint)
  ... truncated ...
```
