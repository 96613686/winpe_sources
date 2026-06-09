# FiringControl::SharedFireSubscription(IEventSubscription *,ICallFrame *,ulong)

- ea: `0x18001af70`
- end: `0x18001b68f`
- name: `?SharedFireSubscription@FiringControl@@QEAAJPEAUIEventSubscription@@PEAUICallFrame@@K@Z`
- size: `1823`
- prototype: `__int64 __fastcall(FiringControl *__hidden this, struct IEventSubscription *, struct ICallFrame *, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ecb0`
- `0x18001ae10`

## callees

- `0x180006194`
- `0x180008938`
- `0x18001af70`
- `0x18001b698`
- `0x18001b7e0`
- `0x18001b860`
- `0x18001be20`
- `0x18001c690`
- `0x18001c8f0`
- `0x18002f1d8`
- `0x18003ec70`
- `0x18003ed70`
- `0x18003edc4`
- `0x18003efe8`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b012`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b012`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b004`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b3aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b004`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b3aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b5e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b5e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b57d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b641`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b64c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b65a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b668`
- `OLEAUT32!__imp_SysFreeString` at `0x180044825`
- `OLEAUT32!__imp_SysFreeString` at `0x18004482f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004483c`
- `OLEAUT32!__imp_SysFreeString` at `0x180044849`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b57d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b641`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b64c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b65a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b668`
- `OLEAUT32!__imp_SysFreeString` at `0x180044825`
- `OLEAUT32!__imp_SysFreeString` at `0x18004482f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004483c`
- `OLEAUT32!__imp_SysFreeString` at `0x180044849`

## string_xrefs

- `0x18001b41f`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001b43b`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001b457`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001b473`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001b67e`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
__int64 __fastcall FiringControl::SharedFireSubscription(
        FiringControl *this,
        struct IEventSubscription *a2,
        struct ICallFrame *a3,
        int a4)
{
  int v7; // r12d
  bool v8; // r13
  int v9; // edi
  int v10; // eax
  int TransientSubscriptionInterface; // eax
  FiringControl *v12; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // edx
  int v19; // edx
  unsigned int v20; // edx
  int v21; // r12d
  int v22; // r12d
  bool v23; // [rsp+50h] [rbp-108h] BYREF
  bool v24; // [rsp+51h] [rbp-107h] BYREF
  int v25; // [rsp+54h] [rbp-104h]
  BSTR v26; // [rsp+58h] [rbp-100h] BYREF
  int v27; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v28; // [rsp+68h] [rbp-F0h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-E8h] BYREF
  BSTR v30; // [rsp+78h] [rbp-E0h] BYREF
  BSTR v31; // [rsp+80h] [rbp-D8h] BYREF
  BSTR v32; // [rsp+88h] [rbp-D0h] BYREF
  int v33; // [rsp+90h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+98h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-B8h] BYREF
  struct IUnknown *v36[2]; // [rsp+A8h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-A0h]
  _DWORD v38[2]; // [rsp+C0h] [rbp-98h] BYREF
  __int64 v39; // [rsp+C8h] [rbp-90h]
  ULONGLONG TickCount64; // [rsp+D8h] [rbp-80h]
  __int64 v41; // [rsp+E8h] [rbp-70h]
  char v42; // [rsp+F0h] [rbp-68h]
  __int64 v43; // [rsp+F8h] [rbp-60h]
  unsigned __int16 v44[12]; // [rsp+100h] [rbp-58h] BYREF

  LODWORD(hMem) = a4;
  v25 = 0;
  v34 = 0;
  v23 = 0;
  v33 = 0;
  v27 = 0;
  v7 = 0;
  LODWORD(v26) = 0;
  v8 = 0;
  v24 = 0;
  LOBYTE(v28) = 0;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  v38[0] = a4;
  v39 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  TickCount64 = GetTickCount64();
  v38[1] = GetCurrentThreadId();
  v9 = ((__int64 (__fastcall *)(struct IEventSubscription *, int *))a2->lpVtbl->get_PerUser)(a2, &v33);
  v25 = v9;
  if ( v9 < 0 )
  {
    v23 = 1;
  }
  else
  {
    v10 = ((__int64 (__fastcall *)(struct IEventSubscription *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_9b724996_d383_4c5f_b0f6_2814708c7633,
            &v34);
    v25 = v10;
    if ( v10 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xE50u, 0x12u, v10);
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 24LL))(v34, &v27);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
    if ( v27 )
    {
      TransientSubscriptionInterface = FiringControl::GetTransientSubscriptionInterface(
                                         this,
                                         a2,
                                         (struct FiringTimeoutManager *)v38,
                                         (struct SubscriberInterface *)v36,
                                         &v23);
      v25 = TransientSubscriptionInterface;
    }
    else
    {
      TransientSubscriptionInterface = FiringControl::CreatePersistentSubscriptionInterface(
                                         this,
                                         a2,
                                         (struct FiringTimeoutManager *)v38,
                                         v33 == 1,
                                         (struct SubscriberInterface *)v36,
                                         &v23,
                                         (enum SubscriptionBlockedReason *)&v26);
      v25 = TransientSubscriptionInterface;
      v7 = (int)v26;
    }
    v9 = TransientSubscriptionInterface;
    if ( TransientSubscriptionInterface >= 0 )
    {
      v9 = FiringControl::CheckForUnsupportedSubscriberObject(
             v12,
             (struct FiringTimeoutManager *)v38,
             (struct SubscriberInterface *)v36,
             v27 == 1,
             &v23,
             (enum SubscriptionBlockedReason *)&v26);
      v25 = v9;
      if ( v9 >= 0 )
      {
        v9 = FiringControl::CallEventMethod(
               this,
               a2,
               (struct FiringTimeoutManager *)v38,
               (struct SubscriberInterface *)v36,
               v27 == 1,
               a3,
               &v24,
               &v23);
        v25 = v9;
        v8 = v24;
      }
      v7 = (int)v26;
    }
    if ( v9 < 0 && v38[0] != -1 )
    {
      v12 = (FiringControl *)(GetTickCount64() + v41 - TickCount64);
      v19 = (unsigned __int8)v28;
      if ( (unsigned __int64)v12 > v38[0] )
        v19 = 1;
      LODWORD(v28) = v19;
    }
    if ( v36[0] )
    {
      FiringControl::ReleaseInterfaceWithTimeout(v12, (struct FiringTimeoutManager *)v38, v36[0]);
      v36[0] = 0;
    }
    else if ( v36[1] )
    {
      FiringControl::ReleaseInterfaceWithTimeout(v12, (struct FiringTimeoutManager *)v38, v36[1]);
      v36[1] = 0;
    }
  }
  if ( v9 < 0 && ((_BYTE)v28 || v23 && v9 != -2147023179 && v9 != -2147417848 && v9 != -2147418110 && v9 != -2147467262) )
  {
    v26 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v14 = ((__int64 (__fastcall *)(struct IEventSubscription *, BSTR *))a2->lpVtbl->get_EventClassID)(a2, &v26);
    if ( v14 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xEBBu, 0x12u, v14);
    v15 = ((__int64 (__fastcall *)(struct IEventSubscription *, BSTR *))a2->lpVtbl->get_PublisherID)(a2, &v30);
    if ( v15 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xEBEu, 0x12u, v15);
    v16 = ((__int64 (__fastcall *)(struct IEventSubscription *, BSTR *))a2->lpVtbl->get_SubscriberCLSID)(a2, &v31);
    if ( v16 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xEC1u, 0x12u, v16);
    v17 = ((__int64 (__fastcall *)(struct IEventSubscription *, BSTR *))a2->lpVtbl->get_SubscriptionName)(a2, &v32);
    if ( v17 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xEC4u, 0x12u, v17);
    if ( (_BYTE)v28 )
    {
      v18 = (unsigned int)hMem / 0x3E8;
      if ( !((unsigned int)hMem / 0x3E8) )
        v18 = 1;
      StringCchPrintfW(v44, 0xBu, L"%d", v18);
      LogMessage_HR(0x12u, 0x80001213, v9, 6u, *(_QWORD *)(*((_QWORD *)this + 4) + 8LL), v26, v30, v31, v32, v44);
    }
    else
    {
      if ( v8 )
      {
        v20 = 1073746450;
      }
      else
      {
        if ( v7 )
        {
          hMem = 0;
          v21 = v7 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              if ( v22 == 1 && EnsureResourceString(&qword_180064640) )
                FormatMessageFromString((unsigned __int16 **)&hMem, qword_180064640);
            }
            else if ( EnsureResourceString(&qword_180064630) )
            {
              FormatMessageFromString((unsigned __int16 **)&hMem, qword_180064630);
            }
          }
          else
          {
            bstrString = 0;
            v28 = 0;
            ((void (__fastcall *)(struct IEventSubscription *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_fbc1d17d_c498_43a0_81af_423ddd530af6,
              &v28);
            (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 344LL))(v28, &bstrString);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            FormatReasonMessage_PerUserMonikerSubscription((unsigned __int16 **)&hMem, bstrString);
            if ( bstrString )
              SysFreeString(bstrString);
          }
          LogMessage(0x12u, 0x80001215, 6u, *(_QWORD *)(*((_QWORD *)this + 4) + 8LL), v26, v30, v31, v32, hMem);
          if ( hMem )
            LocalFree(hMem);
          goto LABEL_57;
        }
        v20 = -2147479294;
      }
      LogMessage_HR(0x12u, v20, v9, 5u, *(_QWORD *)(*((_QWORD *)this + 4) + 8LL), v26, v30, v31, v32);
    }
LABEL_57:
    SysFreeString(v26);
    SysFreeString(v30);
    SysFreeString(v31);
    SysFreeString(v32);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001af70  mov     r11, rsp
0x18001af73  push    rbx
0x18001af74  push    rsi
0x18001af75  push    rdi
0x18001af76  push    r12
0x18001af78  push    r13
0x18001af7a  push    r14
0x18001af7c  push    r15
0x18001af7e  sub     rsp, 120h
0x18001af85  mov     rax, cs:__security_cookie
0x18001af8c  xor     rax, rsp
0x18001af8f  mov     [rsp+158h+var_40], rax
0x18001af97  mov     eax, r9d
0x18001af9a  mov     dword ptr [rsp+158h+hMem], eax
0x18001af9e  mov     rsi, r8
0x18001afa1  mov     rbx, rdx
0x18001afa4  mov     r15, rcx
0x18001afa7  xor     edx, edx
0x18001afa9  mov     [rsp+158h+var_104], edx
0x18001afad  mov     [r11-0C0h], rdx
0x18001afb4  mov     [rsp+158h+var_108], dl
0x18001afb8  mov     [rsp+158h+var_C8], edx
0x18001afbf  mov     [rsp+158h+var_F8], edx
0x18001afc3  mov     r12d, edx
0x18001afc6  mov     dword ptr [rsp+158h+var_100], edx
0x18001afca  xor     r13b, r13b
0x18001afcd  mov     [rsp+158h+var_107], r13b
0x18001afd2  mov     byte ptr [rsp+158h+var_F0], dl
0x18001afd6  xorps   xmm0, xmm0
0x18001afd9  xor     ecx, ecx
0x18001afdb  movups  xmmword ptr [rsp+158h+var_B0], xmm0
0x18001afe3  mov     [r11-0A0h], rcx
0x18001afea  mov     [rsp+158h+var_98], eax
0x18001aff1  mov     [r11-90h], rdx
0x18001aff8  mov     [r11-70h], rdx
0x18001affc  mov     [r11-68h], cl
0x18001b000  mov     [r11-60h], rdx
0x18001b004  call    cs:__imp_GetTickCount64
0x18001b00a  mov     [rsp+158h+var_80], rax
0x18001b012  call    cs:__imp_GetCurrentThreadId
0x18001b018  mov     [rsp+158h+var_94], eax
0x18001b01f  mov     rax, [rbx]
0x18001b022  lea     rdx, [rsp+158h+var_C8]
0x18001b02a  mov     rcx, rbx
0x18001b02d  mov     rax, [rax+0A8h]
0x18001b034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b039  mov     edi, eax
0x18001b03b  mov     [rsp+158h+var_104], eax
0x18001b03f  test    eax, eax
0x18001b041  js      loc_18001B387
0x18001b047  mov     rax, [rbx]
0x18001b04a  lea     r8, [rsp+158h+var_C0]
0x18001b052  lea     rdx, _GUID_9b724996_d383_4c5f_b0f6_2814708c7633
0x18001b059  mov     rcx, rbx
0x18001b05c  mov     rax, [rax]
0x18001b05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b064  mov     [rsp+158h+var_104], eax
0x18001b068  mov     r14d, 12h
0x18001b06e  test    eax, eax
0x18001b070  js      loc_18001B673
0x18001b076  mov     rcx, [rsp+158h+var_C0]
0x18001b07e  mov     rax, [rcx]
0x18001b081  lea     rdx, [rsp+158h+var_F8]
0x18001b086  mov     rax, [rax+18h]
0x18001b08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b08f  mov     rcx, [rsp+158h+var_C0]
0x18001b097  mov     rax, [rcx]
0x18001b09a  mov     rax, [rax+10h]
0x18001b09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0a3  xor     ecx, ecx
0x18001b0a5  mov     [rsp+158h+var_C0], rcx
0x18001b0ad  lea     r8, [rsp+158h+var_98]; struct FiringTimeoutManager *
0x18001b0b5  mov     rdx, rbx; struct IEventSubscription *
0x18001b0b8  mov     rcx, r15; this
0x18001b0bb  cmp     [rsp+158h+var_F8], 0
0x18001b0c0  jz      loc_18001B17A
0x18001b0c6  lea     rax, [rsp+158h+var_108]
0x18001b0cb  mov     [rsp+158h+var_138], rax; bool *
0x18001b0d0  lea     r9, [rsp+158h+var_B0]; struct SubscriberInterface *
0x18001b0d8  call    ?GetTransientSubscriptionInterface@FiringControl@@AEAAJPEAUIEventSubscription@@AEAVFiringTimeoutManager@@AEAUSubscriberInterface@@AEA_N@Z; FiringControl::GetTransientSubscriptionInterface(IEventSubscription *,FiringTimeoutManager &,SubscriberInterface &,bool &)
0x18001b0dd  mov     [rsp+158h+var_104], eax
0x18001b0e1  mov     edi, eax
0x18001b0e3  test    eax, eax
0x18001b0e5  js      loc_18001B1BA
0x18001b0eb  cmp     [rsp+158h+var_F8], 1
0x18001b0f0  setz    r9b; bool
0x18001b0f4  lea     rax, [rsp+158h+var_100]
0x18001b0f9  mov     [rsp+158h+var_130], rax; enum SubscriptionBlockedReason *
0x18001b0fe  lea     rax, [rsp+158h+var_108]
0x18001b103  mov     [rsp+158h+var_138], rax; bool *
0x18001b108  lea     r8, [rsp+158h+var_B0]; struct SubscriberInterface *
0x18001b110  lea     rdx, [rsp+158h+var_98]; struct FiringTimeoutManager *
0x18001b118  call    ?CheckForUnsupportedSubscriberObject@FiringControl@@AEAAJAEAVFiringTimeoutManager@@AEAUSubscriberInterface@@_NAEA_NAEAW4SubscriptionBlockedReason@@@Z; FiringControl::CheckForUnsupportedSubscriberObject(FiringTimeoutManager &,SubscriberInterface &,bool,bool &,SubscriptionBlockedReason &)
0x18001b11d  mov     edi, eax
0x18001b11f  mov     [rsp+158h+var_104], eax
0x18001b123  test    eax, eax
0x18001b125  js      short loc_18001B173
0x18001b127  cmp     [rsp+158h+var_F8], 1
0x18001b12c  setz    al
0x18001b12f  lea     rcx, [rsp+158h+var_108]
0x18001b134  mov     [rsp+158h+var_120], rcx; bool *
0x18001b139  lea     rcx, [rsp+158h+var_107]
0x18001b13e  mov     [rsp+158h+var_128], rcx; bool *
0x18001b143  mov     [rsp+158h+var_130], rsi; struct ICallFrame *
0x18001b148  mov     byte ptr [rsp+158h+var_138], al; bool
0x18001b14c  lea     r9, [rsp+158h+var_B0]; struct SubscriberInterface *
0x18001b154  lea     r8, [rsp+158h+var_98]; struct FiringTimeoutManager *
0x18001b15c  mov     rdx, rbx; struct IEventSubscription *
0x18001b15f  mov     rcx, r15; this
0x18001b162  call    ?CallEventMethod@FiringControl@@AEAAJPEAUIEventSubscription@@AEAVFiringTimeoutManager@@AEAUSubscriberInterface@@_NPEAUICallFrame@@AEA_N5@Z; FiringControl::CallEventMethod(IEventSubscription *,FiringTimeoutManager &,SubscriberInterface &,bool,ICallFrame *,bool &,bool &)
0x18001b167  mov     edi, eax
0x18001b169  mov     [rsp+158h+var_104], eax
0x18001b16d  movzx   r13d, [rsp+158h+var_107]
0x18001b173  mov     r12d, dword ptr [rsp+158h+var_100]
0x18001b178  jmp     short loc_18001B1BA
0x18001b17a  cmp     [rsp+158h+var_C8], 1
0x18001b182  setz    r9b; bool
0x18001b186  lea     rax, [rsp+158h+var_100]
0x18001b18b  mov     [rsp+158h+var_128], rax; enum SubscriptionBlockedReason *
0x18001b190  lea     rax, [rsp+158h+var_108]
0x18001b195  mov     [rsp+158h+var_130], rax; bool *
0x18001b19a  lea     rax, [rsp+158h+var_B0]
0x18001b1a2  mov     [rsp+158h+var_138], rax; struct SubscriberInterface *
0x18001b1a7  call    ?CreatePersistentSubscriptionInterface@FiringControl@@AEAAJPEAUIEventSubscription@@AEAVFiringTimeoutManager@@_NAEAUSubscriberInterface@@AEA_NAEAW4SubscriptionBlockedReason@@@Z; FiringControl::CreatePersistentSubscriptionInterface(IEventSubscription *,FiringTimeoutManager &,bool,SubscriberInterface &,bool &,SubscriptionBlockedReason &)
0x18001b1ac  mov     [rsp+158h+var_104], eax
0x18001b1b0  mov     r12d, dword ptr [rsp+158h+var_100]
0x18001b1b5  jmp     loc_18001B0E1
0x18001b1ba  test    edi, edi
0x18001b1bc  js      loc_18001B39C
0x18001b1c2  mov     esi, 1
0x18001b1c7  mov     r8, [rsp+158h+var_B0]; struct IUnknown *
0x18001b1cf  test    r8, r8
0x18001b1d2  jz      loc_18001B3E5
0x18001b1d8  lea     rdx, [rsp+158h+var_98]; struct FiringTimeoutManager *
0x18001b1e0  call    ?ReleaseInterfaceWithTimeout@FiringControl@@AEAAXAEAVFiringTimeoutManager@@PEAUIUnknown@@@Z; FiringControl::ReleaseInterfaceWithTimeout(FiringTimeoutManager &,IUnknown *)
0x18001b1e5  mov     [rsp+158h+var_B0], 0
0x18001b1f1  test    edi, edi
0x18001b1f3  js      short loc_18001B21A
0x18001b1f5  mov     eax, edi
0x18001b1f7  mov     rcx, [rsp+158h+var_40]
0x18001b1ff  xor     rcx, rsp; StackCookie
0x18001b202  call    __security_check_cookie
0x18001b207  add     rsp, 120h
0x18001b20e  pop     r15
0x18001b210  pop     r14
0x18001b212  pop     r13
0x18001b214  pop     r12
0x18001b216  pop     rdi
0x18001b217  pop     rsi
0x18001b218  pop     rbx
0x18001b219  retn
0x18001b21a  cmp     byte ptr [rsp+158h+var_F0], 0
0x18001b21f  jnz     short loc_18001B248
0x18001b221  cmp     [rsp+158h+var_108], 0
0x18001b226  jz      short loc_18001B1F5
0x18001b228  cmp     edi, 800706B5h
0x18001b22e  jz      short loc_18001B1F5
0x18001b230  cmp     edi, 80010108h
0x18001b236  jz      short loc_18001B1F5
0x18001b238  cmp     edi, 80010002h
0x18001b23e  jz      short loc_18001B1F5
0x18001b240  cmp     edi, 80004002h
0x18001b246  jz      short loc_18001B1F5
0x18001b248  mov     [rsp+158h+var_100], 0
0x18001b251  mov     [rsp+158h+var_E0], 0
0x18001b25a  mov     [rsp+158h+var_D8], 0
0x18001b266  mov     [rsp+158h+var_D0], 0
0x18001b272  mov     rax, [rbx]
0x18001b275  lea     rdx, [rsp+158h+var_100]
0x18001b27a  mov     rcx, rbx
0x18001b27d  mov     rax, [rax+68h]
0x18001b281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b286  test    eax, eax
0x18001b288  js      loc_18001B414
0x18001b28e  mov     rax, [rbx]
0x18001b291  lea     rdx, [rsp+158h+var_E0]
0x18001b296  mov     rcx, rbx
0x18001b299  mov     rax, [rax+58h]
0x18001b29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2a2  test    eax, eax
0x18001b2a4  js      loc_18001B430
0x18001b2aa  mov     rax, [rbx]
0x18001b2ad  lea     rdx, [rsp+158h+var_D8]
0x18001b2b5  mov     rcx, rbx
0x18001b2b8  mov     rax, [rax+88h]
0x18001b2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2c4  test    eax, eax
0x18001b2c6  js      loc_18001B44C
0x18001b2cc  mov     rax, [rbx]
0x18001b2cf  lea     rdx, [rsp+158h+var_D0]
0x18001b2d7  mov     rcx, rbx
0x18001b2da  mov     rax, [rax+48h]
0x18001b2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2e3  test    eax, eax
0x18001b2e5  js      loc_18001B468
0x18001b2eb  cmp     byte ptr [rsp+158h+var_F0], 0
0x18001b2f0  jz      loc_18001B484
0x18001b2f6  mov     eax, 10624DD3h
0x18001b2fb  mul     dword ptr [rsp+158h+hMem]
0x18001b2ff  shr     edx, 6
0x18001b302  test    edx, edx
0x18001b304  cmovz   edx, esi
0x18001b307  mov     r9d, edx
0x18001b30a  lea     r8, aD; "%d"
0x18001b311  mov     edx, 0Bh; unsigned __int64
0x18001b316  lea     rcx, [rsp+158h+var_58]; unsigned __int16 *
0x18001b31e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b323  mov     rcx, [r15+20h]
0x18001b327  lea     rax, [rsp+158h+var_58]
0x18001b32f  mov     [rsp+158h+var_110], rax
0x18001b334  mov     rax, [rsp+158h+var_D0]
0x18001b33c  mov     [rsp+158h+var_118], rax
0x18001b341  mov     rax, [rsp+158h+var_D8]
0x18001b349  mov     [rsp+158h+var_120], rax
0x18001b34e  mov     rax, [rsp+158h+var_E0]
0x18001b353  mov     [rsp+158h+var_128], rax
0x18001b358  mov     rax, [rsp+158h+var_100]
0x18001b35d  mov     [rsp+158h+var_130], rax
0x18001b362  mov     rax, [rcx+8]
0x18001b366  mov     [rsp+158h+var_138], rax
0x18001b36b  mov     r9d, 6; unsigned int
0x18001b371  mov     r8d, edi; int
0x18001b374  mov     edx, 80001213h; unsigned int
0x18001b379  movzx   ecx, r14w; unsigned __int16
0x18001b37d  call    ?LogMessage_HR@@YAXGKJKZZ; LogMessage_HR(ushort,ulong,long,ulong,...)
0x18001b382  jmp     loc_18001B63C
0x18001b387  mov     [rsp+158h+var_108], 1
0x18001b38c  mov     esi, 1
0x18001b391  mov     r14d, 12h
0x18001b397  jmp     loc_18001B1F1
0x18001b39c  cmp     [rsp+158h+var_98], 0FFFFFFFFh
0x18001b3a4  jz      loc_18001B1C2
0x18001b3aa  call    cs:__imp_GetTickCount64
0x18001b3b0  mov     rcx, [rsp+158h+var_70]
0x18001b3b8  sub     rcx, [rsp+158h+var_80]
0x18001b3c0  add     rcx, rax
0x18001b3c3  mov     eax, [rsp+158h+var_98]
0x18001b3ca  mov     edx, dword ptr [rsp+158h+var_F0]
0x18001b3ce  movzx   edx, dl
0x18001b3d1  mov     esi, 1
0x18001b3d6  cmp     rcx, rax
0x18001b3d9  cmova   edx, esi
0x18001b3dc  mov     dword ptr [rsp+158h+var_F0], edx
0x18001b3e0  jmp     loc_18001B1C7
0x18001b3e5  mov     r8, [rsp+158h+var_B0+8]; struct IUnknown *
0x18001b3ed  test    r8, r8
0x18001b3f0  jz      loc_18001B1F1
0x18001b3f6  lea     rdx, [rsp+158h+var_98]; struct FiringTimeoutManager *
0x18001b3fe  call    ?ReleaseInterfaceWithTimeout@FiringControl@@AEAAXAEAVFiringTimeoutManager@@PEAUIUnknown@@@Z; FiringControl::ReleaseInterfaceWithTimeout(FiringTimeoutManager &,IUnknown *)
0x18001b403  mov     [rsp+158h+var_B0+8], 0
0x18001b40f  jmp     loc_18001B1F1
0x18001b414  mov     r8d, r14d; unsigned __int16
0x18001b417  mov     r9d, eax; int
0x18001b41a  mov     edx, 0EBBh; unsigned int
0x18001b41f  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001b426  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001b42b  jmp     loc_18001B28E
0x18001b430  mov     r8d, r14d; unsigned __int16
0x18001b433  mov     r9d, eax; int
0x18001b436  mov     edx, 0EBEh; unsigned int
0x18001b43b  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001b442  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001b447  jmp     loc_18001B2AA
0x18001b44c  mov     r8d, r14d; unsigned __int16
0x18001b44f  mov     r9d, eax; int
0x18001b452  mov     edx, 0EC1h; unsigned int
0x18001b457  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001b45e  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001b463  jmp     loc_18001B2CC
0x18001b468  mov     r8d, r14d; unsigned __int16
0x18001b46b  mov     r9d, eax; int
0x18001b46e  mov     edx, 0EC4h; unsigned int
0x18001b473  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001b47a  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001b47f  jmp     loc_18001B2EB
0x18001b484  test    r13b, r13b
0x18001b487  jz      short loc_18001B493
0x18001b489  mov     edx, 40001212h
0x18001b48e  jmp     loc_18001B5EE
0x18001b493  test    r12d, r12d
0x18001b496  jz      loc_18001B5E9
0x18001b49c  xor     ecx, ecx
0x18001b49e  mov     [rsp+158h+hMem], rcx
0x18001b4a3  sub     r12d, 1
0x18001b4a7  jz      short loc_18001B50A
0x18001b4a9  sub     r12d, 1
0x18001b4ad  jz      short loc_18001B4E3
0x18001b4af  cmp     r12d, 1
0x18001b4b3  jnz     loc_18001B583
0x18001b4b9  lea     rcx, qword_180064640; unsigned __int16 **
0x18001b4c0  call    ?EnsureResourceString@@YA_NAEAPEAG@Z; EnsureResourceString(ushort * &)
0x18001b4c5  test    al, al
0x18001b4c7  jz      loc_18001B583
0x18001b4cd  mov     rdx, cs:qword_180064640; unsigned __int16 *
0x18001b4d4  lea     rcx, [rsp+158h+hMem]; unsigned __int16 **
0x18001b4d9  call    ?FormatMessageFromString@@YAXPEAPEAGPEAGZZ; FormatMessageFromString(ushort * *,ushort *,...)
0x18001b4de  jmp     loc_18001B583
0x18001b4e3  lea     rcx, qword_180064630; unsigned __int16 **
0x18001b4ea  call    ?EnsureResourceString@@YA_NAEAPEAG@Z; EnsureResourceString(ushort * &)
0x18001b4ef  test    al, al
  ... truncated ...
```
