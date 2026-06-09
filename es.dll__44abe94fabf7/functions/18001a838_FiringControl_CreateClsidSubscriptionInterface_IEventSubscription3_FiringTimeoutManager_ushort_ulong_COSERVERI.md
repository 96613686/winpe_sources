# FiringControl::CreateClsidSubscriptionInterface(IEventSubscription3 *,FiringTimeoutManager &,ushort *,ulong,_COSERVERINFO *,bool,SubscriberInterface &,bool &)

- ea: `0x18001a838`
- end: `0x18001ada7`
- name: `?CreateClsidSubscriptionInterface@FiringControl@@AEAAJPEAUIEventSubscription3@@AEAVFiringTimeoutManager@@PEAGKPEAU_COSERVERINFO@@_NAEAUSubscriberInterface@@AEA_N@Z`
- size: `1391`
- prototype: `__int64 __fastcall(FiringControl *this, struct IEventSubscription3 *, struct FiringTimeoutManager *, unsigned __int16 *, unsigned int, struct _COSERVERINFO *, bool, struct SubscriberInterface *, bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f1d8`

## callees

- `0x18001a838`
- `0x18001adb0`
- `0x18001b7e0`
- `0x18001c094`
- `0x18001c0c8`
- `0x18001c59c`
- `0x18001c690`
- `0x18001c8f0`
- `0x18001c9f0`
- `0x18003f608`
- `0x1800434ae`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ab3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004470d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ab3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004470d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001abd6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001abe4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001abd6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001abe4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001a9b9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001a9de`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001a9b9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001a9de`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001acd8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001ad67`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001acd8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001ad67`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001aa0c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001aa0c`

## string_xrefs

- `0x18001ab7d`: `StandardCreateInstance`

## pseudocode

```c
__int64 __fastcall FiringControl::CreateClsidSubscriptionInterface(
        FiringControl *this,
        struct IEventSubscription3 *a2,
        struct FiringTimeoutManager *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        struct _COSERVERINFO *a6,
        bool a7,
        struct SubscriberInterface *a8,
        bool *a9)
{
  HRESULT TerminalServicesSessionId; // ebx
  LPCOLESTR v13; // rsi
  const char *v14; // rdx
  unsigned int v15; // r8d
  struct IUnknown *v17; // r12
  struct IUnknown *v18; // rsi
  struct IUnknown *v19; // r14
  __int64 v20; // rdx
  FiringControl *v21; // rcx
  __int64 v22; // r8
  int v23; // eax
  HRESULT v24; // eax
  FiringControl *v25; // rcx
  int v26[2]; // [rsp+48h] [rbp-120h] BYREF
  IUnknown *v27; // [rsp+50h] [rbp-118h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-110h] BYREF
  __int64 v29; // [rsp+60h] [rbp-108h] BYREF
  struct IUnknown *v30; // [rsp+68h] [rbp-100h]
  struct IUnknown *v31; // [rsp+70h] [rbp-F8h]
  struct FiringTimeoutManager *v32; // [rsp+80h] [rbp-E8h]
  LPCOLESTR v33; // [rsp+90h] [rbp-D8h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-D0h] BYREF
  LPCOLESTR lpsz; // [rsp+A0h] [rbp-C8h]
  GUID Buf1; // [rsp+A8h] [rbp-C0h] BYREF
  GUID pclsid; // [rsp+B8h] [rbp-B0h] BYREF
  GUID *v38; // [rsp+D0h] [rbp-98h] BYREF
  IUnknown *pProxy; // [rsp+D8h] [rbp-90h]
  int v40; // [rsp+E0h] [rbp-88h]
  __int64 v41; // [rsp+E8h] [rbp-80h]
  struct IUnknown *v42; // [rsp+F0h] [rbp-78h]
  int v43; // [rsp+F8h] [rbp-70h]
  GUID *v44; // [rsp+100h] [rbp-68h]
  struct IUnknown *v45; // [rsp+108h] [rbp-60h]
  int v46; // [rsp+110h] [rbp-58h]

  lpsz = a4;
  v32 = a3;
  TerminalServicesSessionId = 0;
  v33 = 0;
  bstrString = 0;
  v26[0] = 0;
  LODWORD(v27) = -1;
  ppv = 0;
  v29 = 0;
  *a9 = 0;
  (*(void (__fastcall **)(struct IEventSubscription3 *, LPCOLESTR *))(*(_QWORD *)a2 + 392LL))(a2, &v33);
  if ( a7 )
  {
    (*(void (__fastcall **)(struct IEventSubscription3 *, BSTR *))(*(_QWORD *)a2 + 184LL))(a2, &bstrString);
    TerminalServicesSessionId = GetTerminalServicesSessionId(bstrString, 0, v26, (unsigned int *)&v27);
    if ( TerminalServicesSessionId < 0 )
      *a9 = 1;
  }
  if ( TerminalServicesSessionId >= 0 )
  {
    v38 = &IID_IUnknown;
    pProxy = 0;
    v40 = 0;
    v41 = *(_QWORD *)(*((_QWORD *)this + 4) + 80LL);
    v42 = 0;
    v43 = 0;
    v44 = &IID_IDispatch;
    v45 = 0;
    v46 = 0;
    pclsid = 0;
    Buf1 = GUID_NULL;
    v13 = lpsz;
    TerminalServicesSessionId = CLSIDFromString(lpsz, &pclsid);
    if ( TerminalServicesSessionId >= 0 )
    {
      if ( !v33 || (TerminalServicesSessionId = CLSIDFromString(v33, &Buf1), TerminalServicesSessionId >= 0) )
      {
        TerminalServicesSessionId = CoCreateInstance(&CLSID_ComActivator, 0, 1u, &IID_IStandardActivator, &ppv);
        if ( TerminalServicesSessionId >= 0 )
        {
          if ( !v26[0] && !memcmp_0(&Buf1, &GUID_NULL, 0x10u)
            || (TerminalServicesSessionId = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                                              ppv,
                                              &IID_ISpecialSystemProperties,
                                              &v29),
                TerminalServicesSessionId >= 0)
            && (!memcmp_0(&Buf1, &GUID_NULL, 0x10u)
             || (TerminalServicesSessionId = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v29 + 64LL))(
                                               v29,
                                               &Buf1),
                 TerminalServicesSessionId >= 0))
            && (!v26[0]
             || (TerminalServicesSessionId = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v29 + 24LL))(
                                               v29,
                                               (unsigned int)v27,
                                               0,
                                               0),
                 TerminalServicesSessionId >= 0)) )
          {
            TerminalServicesSessionId = FiringTimeoutManager::OnEnterActivation(a3, v14, v15, a5, a6);
            if ( TerminalServicesSessionId >= 0 )
              TerminalServicesSessionId = (*(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD, _QWORD, struct _COSERVERINFO *, int, GUID **))(*(_QWORD *)ppv + 32LL))(
                                            ppv,
                                            &pclsid,
                                            0,
                                            a5,
                                            a6,
                                            3,
                                            &v38);
            *((_DWORD *)a3 + 3) = 0;
            *((_QWORD *)a3 + 3) = GetTickCount64();
            if ( *(_DWORD *)a3 != -1 )
              FiringTimeoutManager::OnLeaveWithTimeout(a3);
            if ( TerminalServicesSessionId < 0 )
              goto LABEL_25;
            if ( v43 < 0 && v46 < 0 )
              TerminalServicesSessionId = v43;
            if ( TerminalServicesSessionId < 0 )
            {
LABEL_25:
              LogMessage_HR(0x12u, 0x80001104, TerminalServicesSessionId, 2u, v13, L"StandardCreateInstance");
              *a9 = 0;
              goto LABEL_26;
            }
            v17 = pProxy;
            *(_QWORD *)v26 = pProxy;
            v18 = v42;
            v30 = v42;
            lpsz = (LPCOLESTR)v42;
            v19 = v45;
            v31 = v45;
            v27 = v45;
            if ( FiringTimeoutManager::TimedOut(a3) )
            {
              TerminalServicesSessionId = -2147023436;
LABEL_44:
              FiringControl::ReleaseInterfaceWithTimeout(v21, a3, v17);
              if ( v18 )
                FiringControl::ReleaseInterfaceWithTimeout(v25, a3, v18);
              if ( v19 )
                FiringControl::ReleaseInterfaceWithTimeout(v25, a3, v19);
              goto LABEL_26;
            }
            TerminalServicesSessionId = FiringTimeoutManager::OnEnterCall(a3, v20, v22, 1);
            if ( TerminalServicesSessionId >= 0 )
              TerminalServicesSessionId = DetermineSubscriberLocality(
                                            v17,
                                            (struct SubscriberInterface *)((char *)a8 + 16));
            FiringTimeoutManager::OnLeaveCall(a3);
            if ( TerminalServicesSessionId < 0 )
              goto LABEL_44;
            *((_DWORD *)a3 + 2) = *((_DWORD *)a8 + 4);
            if ( (unsigned int)(*((_DWORD *)a8 + 4) - 1) > 1 )
            {
              TerminalServicesSessionId = CoSetProxyBlanket(
                                            v17,
                                            0xFFFFFFFF,
                                            0xFFFFFFFF,
                                            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                                            0,
                                            2u,
                                            (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                            0x800u);
              if ( TerminalServicesSessionId < 0 )
                goto LABEL_44;
            }
            v23 = *((_DWORD *)a8 + 4);
            if ( v18 )
            {
              *(_QWORD *)a8 = v18;
              v18 = 0;
              v30 = 0;
              if ( (unsigned int)(v23 - 1) <= 1 )
                goto LABEL_44;
              v24 = CoSetProxyBlanket(
                      (IUnknown *)lpsz,
                      0xFFFFFFFF,
                      0xFFFFFFFF,
                      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                      0,
                      2u,
                      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                      0x800u);
            }
            else
            {
              *((_QWORD *)a8 + 1) = v19;
              v19 = 0;
              v31 = 0;
              if ( (unsigned int)(v23 - 1) <= 1 )
                goto LABEL_44;
              v24 = CoSetProxyBlanket(
                      v27,
                      0xFFFFFFFF,
                      0xFFFFFFFF,
                      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                      0,
                      2u,
                      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                      0x800u);
            }
            TerminalServicesSessionId = v24;
            goto LABEL_44;
          }
        }
      }
    }
  }
LABEL_26:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  SysFreeString((BSTR)v33);
  SysFreeString(bstrString);
  return (unsigned int)TerminalServicesSessionId;
}

```

## disassembly

```asm
0x18001a838  push    rbx
0x18001a83a  push    rsi
0x18001a83b  push    rdi
0x18001a83c  push    r12
0x18001a83e  push    r13
0x18001a840  push    r14
0x18001a842  push    r15
0x18001a844  sub     rsp, 130h
0x18001a84b  mov     rax, cs:__security_cookie
0x18001a852  xor     rax, rsp
0x18001a855  mov     [rsp+168h+var_48], rax
0x18001a85d  mov     [rsp+168h+lpsz], r9
0x18001a865  mov     rdi, r8
0x18001a868  mov     rsi, rdx
0x18001a86b  mov     r14, rcx
0x18001a86e  mov     r13, [rsp+168h+arg_38]
0x18001a876  mov     [rsp+168h+var_E8], r8
0x18001a87e  mov     r12, [rsp+168h+arg_28]
0x18001a886  mov     r15, [rsp+168h+arg_40]
0x18001a88e  xor     eax, eax
0x18001a890  mov     ebx, eax
0x18001a892  mov     [rsp+168h+var_D8], rax
0x18001a89a  mov     [rsp+168h+bstrString], rax
0x18001a8a2  mov     [rsp+168h+var_120], eax
0x18001a8a6  mov     dword ptr [rsp+168h+var_118], 0FFFFFFFFh
0x18001a8ae  mov     [rsp+168h+var_110], rax
0x18001a8b3  mov     [rsp+168h+var_108], rax
0x18001a8b8  mov     [r15], al
0x18001a8bb  mov     rax, [rdx]
0x18001a8be  lea     rdx, [rsp+168h+var_D8]
0x18001a8c6  mov     rcx, rsi
0x18001a8c9  mov     rax, [rax+188h]
0x18001a8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8d5  cmp     [rsp+168h+arg_30], bl
0x18001a8dc  jz      short loc_18001A91B
0x18001a8de  mov     rax, [rsi]
0x18001a8e1  lea     rdx, [rsp+168h+bstrString]
0x18001a8e9  mov     rcx, rsi
0x18001a8ec  mov     rax, [rax+0B8h]
0x18001a8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8f8  lea     r9, [rsp+168h+var_118]; unsigned int *
0x18001a8fd  lea     r8, [rsp+168h+var_120]; int *
0x18001a902  xor     edx, edx; bool
0x18001a904  mov     rcx, [rsp+168h+bstrString]; unsigned __int16 *
0x18001a90c  call    ?GetTerminalServicesSessionId@@YAJPEAG_NPEAHPEAK@Z; GetTerminalServicesSessionId(ushort *,bool,int *,ulong *)
0x18001a911  mov     ebx, eax
0x18001a913  test    eax, eax
0x18001a915  jns     short loc_18001A91B
0x18001a917  mov     byte ptr [r15], 1
0x18001a91b  test    ebx, ebx
0x18001a91d  js      loc_18001ABA2
0x18001a923  lea     rax, IID_IUnknown
0x18001a92a  mov     [rsp+168h+var_98], rax
0x18001a932  mov     [rsp+168h+pProxy], 0
0x18001a93e  mov     [rsp+168h+var_88], 0
0x18001a949  mov     rax, [r14+20h]
0x18001a94d  mov     rcx, [rax+50h]
0x18001a951  mov     [rsp+168h+var_80], rcx
0x18001a959  xor     r14d, r14d
0x18001a95c  mov     [rsp+168h+var_78], r14
0x18001a964  mov     [rsp+168h+var_70], r14d
0x18001a96c  lea     rax, IID_IDispatch
0x18001a973  mov     [rsp+168h+var_68], rax
0x18001a97b  mov     [rsp+168h+var_60], r14
0x18001a983  mov     [rsp+168h+var_58], r14d
0x18001a98b  xorps   xmm0, xmm0
0x18001a98e  movups  xmmword ptr [rsp+168h+pclsid.Data1], xmm0
0x18001a996  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18001a99d  movdqu  xmmword ptr [rsp+168h+Buf1.Data1], xmm1
0x18001a9a6  lea     rdx, [rsp+168h+pclsid]; pclsid
0x18001a9ae  mov     rsi, [rsp+168h+lpsz]
0x18001a9b6  mov     rcx, rsi; lpsz
0x18001a9b9  call    cs:__imp_CLSIDFromString
0x18001a9bf  mov     ebx, eax
0x18001a9c1  test    eax, eax
0x18001a9c3  js      loc_18001ABA2
0x18001a9c9  mov     rcx, [rsp+168h+var_D8]; lpsz
0x18001a9d1  test    rcx, rcx
0x18001a9d4  jz      short loc_18001A9EE
0x18001a9d6  lea     rdx, [rsp+168h+Buf1]; pclsid
0x18001a9de  call    cs:__imp_CLSIDFromString
0x18001a9e4  mov     ebx, eax
0x18001a9e6  test    eax, eax
0x18001a9e8  js      loc_18001ABA2
0x18001a9ee  lea     rax, [rsp+168h+var_110]
0x18001a9f3  mov     [rsp+168h+ppv], rax; ppv
0x18001a9f8  lea     r9, IID_IStandardActivator; riid
0x18001a9ff  xor     edx, edx; pUnkOuter
0x18001aa01  lea     r8d, [rdx+1]; dwClsContext
0x18001aa05  lea     rcx, CLSID_ComActivator; rclsid
0x18001aa0c  call    cs:__imp_CoCreateInstance
0x18001aa12  mov     ebx, eax
0x18001aa14  test    eax, eax
0x18001aa16  js      loc_18001ABA2
0x18001aa1c  cmp     [rsp+168h+var_120], r14d
0x18001aa21  jnz     short loc_18001AA45
0x18001aa23  mov     r8d, 10h; Size
0x18001aa29  lea     rdx, GUID_NULL; Buf2
0x18001aa30  lea     rcx, [rsp+168h+Buf1]; Buf1
0x18001aa38  call    memcmp_0
0x18001aa3d  test    eax, eax
0x18001aa3f  jz      loc_18001AAD8
0x18001aa45  mov     rcx, [rsp+168h+var_110]
0x18001aa4a  mov     rax, [rcx]
0x18001aa4d  lea     r8, [rsp+168h+var_108]
0x18001aa52  lea     rdx, IID_ISpecialSystemProperties
0x18001aa59  mov     rax, [rax]
0x18001aa5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa61  mov     ebx, eax
0x18001aa63  test    eax, eax
0x18001aa65  js      loc_18001ABA2
0x18001aa6b  mov     r8d, 10h; Size
0x18001aa71  lea     rdx, GUID_NULL; Buf2
0x18001aa78  lea     rcx, [rsp+168h+Buf1]; Buf1
0x18001aa80  call    memcmp_0
0x18001aa85  test    eax, eax
0x18001aa87  jz      short loc_18001AAAC
0x18001aa89  mov     rcx, [rsp+168h+var_108]
0x18001aa8e  mov     rax, [rcx]
0x18001aa91  lea     rdx, [rsp+168h+Buf1]
0x18001aa99  mov     rax, [rax+40h]
0x18001aa9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaa2  mov     ebx, eax
0x18001aaa4  test    eax, eax
0x18001aaa6  js      loc_18001ABA2
0x18001aaac  cmp     [rsp+168h+var_120], r14d
0x18001aab1  jz      short loc_18001AAD8
0x18001aab3  mov     rcx, [rsp+168h+var_108]
0x18001aab8  mov     rax, [rcx]
0x18001aabb  xor     r9d, r9d
0x18001aabe  xor     r8d, r8d
0x18001aac1  mov     edx, dword ptr [rsp+168h+var_118]
0x18001aac5  mov     rax, [rax+18h]
0x18001aac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aace  mov     ebx, eax
0x18001aad0  test    eax, eax
0x18001aad2  js      loc_18001ABA2
0x18001aad8  mov     [rsp+168h+ppv], r12; struct _COSERVERINFO *
0x18001aadd  mov     r9d, [rsp+168h+arg_20]; unsigned int
0x18001aae5  mov     rcx, rdi; Parameter
0x18001aae8  call    ?OnEnterActivation@FiringTimeoutManager@@QEAAJPEBDKKPEAU_COSERVERINFO@@@Z; FiringTimeoutManager::OnEnterActivation(char const *,ulong,ulong,_COSERVERINFO *)
0x18001aaed  mov     ebx, eax
0x18001aaef  mov     [rsp+168h+var_128], eax
0x18001aaf3  test    eax, eax
0x18001aaf5  js      short loc_18001AB3B
0x18001aaf7  mov     rcx, [rsp+168h+var_110]
0x18001aafc  mov     rax, [rcx]
0x18001aaff  lea     rdx, [rsp+168h+var_98]
0x18001ab07  mov     [rsp+168h+pAuthInfo], rdx
0x18001ab0c  mov     [rsp+168h+dwImpLevel], 3
0x18001ab14  mov     [rsp+168h+ppv], r12
0x18001ab19  mov     r9d, [rsp+168h+arg_20]
0x18001ab21  xor     r8d, r8d
0x18001ab24  lea     rdx, [rsp+168h+pclsid]
0x18001ab2c  mov     rax, [rax+20h]
0x18001ab30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab35  mov     ebx, eax
0x18001ab37  mov     [rsp+168h+var_128], eax
0x18001ab3b  mov     [rdi+0Ch], r14d
0x18001ab3f  call    cs:__imp_GetTickCount64
0x18001ab45  mov     [rdi+18h], rax
0x18001ab49  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18001ab4c  jz      short loc_18001AB56
0x18001ab4e  mov     rcx, rdi; this
0x18001ab51  call    ?OnLeaveWithTimeout@FiringTimeoutManager@@AEAAXXZ; FiringTimeoutManager::OnLeaveWithTimeout(void)
0x18001ab56  test    ebx, ebx
0x18001ab58  js      short loc_18001AB78
0x18001ab5a  mov     eax, [rsp+168h+var_70]
0x18001ab61  test    eax, eax
0x18001ab63  jns     short loc_18001AB70
0x18001ab65  cmp     [rsp+168h+var_58], r14d
0x18001ab6d  cmovl   ebx, eax
0x18001ab70  test    ebx, ebx
0x18001ab72  jns     loc_18001AC0F
0x18001ab78  mov     ecx, 12h; unsigned __int16
0x18001ab7d  lea     rax, aStandardcreate; "StandardCreateInstance"
0x18001ab84  mov     qword ptr [rsp+168h+dwImpLevel], rax
0x18001ab89  mov     [rsp+168h+ppv], rsi
0x18001ab8e  lea     r9d, [rcx-10h]; unsigned int
0x18001ab92  mov     r8d, ebx; int
0x18001ab95  mov     edx, 80001104h; unsigned int
0x18001ab9a  call    ?LogMessage_HR@@YAXGKJKZZ; LogMessage_HR(ushort,ulong,long,ulong,...)
0x18001ab9f  mov     [r15], r14b
0x18001aba2  mov     rcx, [rsp+168h+var_110]
0x18001aba7  test    rcx, rcx
0x18001abaa  jz      short loc_18001ABB8
0x18001abac  mov     rax, [rcx]
0x18001abaf  mov     rax, [rax+10h]
0x18001abb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abb8  mov     rcx, [rsp+168h+var_108]
0x18001abbd  test    rcx, rcx
0x18001abc0  jz      short loc_18001ABCE
0x18001abc2  mov     rax, [rcx]
0x18001abc5  mov     rax, [rax+10h]
0x18001abc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abce  mov     rcx, [rsp+168h+var_D8]; bstrString
0x18001abd6  call    cs:__imp_SysFreeString
0x18001abdc  mov     rcx, [rsp+168h+bstrString]; bstrString
0x18001abe4  call    cs:__imp_SysFreeString
0x18001abea  mov     eax, ebx
0x18001abec  mov     rcx, [rsp+168h+var_48]
0x18001abf4  xor     rcx, rsp; StackCookie
0x18001abf7  call    __security_check_cookie
0x18001abfc  add     rsp, 130h
0x18001ac03  pop     r15
0x18001ac05  pop     r14
0x18001ac07  pop     r13
0x18001ac09  pop     r12
0x18001ac0b  pop     rdi
0x18001ac0c  pop     rsi
0x18001ac0d  pop     rbx
0x18001ac0e  retn
0x18001ac0f  mov     r12, [rsp+168h+pProxy]
0x18001ac17  mov     qword ptr [rsp+168h+var_120], r12
0x18001ac1c  mov     rsi, [rsp+168h+var_78]
0x18001ac24  mov     [rsp+168h+var_100], rsi
0x18001ac29  mov     [rsp+168h+lpsz], rsi
0x18001ac31  mov     r14, [rsp+168h+var_60]
0x18001ac39  mov     [rsp+168h+var_F8], r14
0x18001ac3e  mov     [rsp+168h+var_118], r14
0x18001ac43  mov     rcx, rdi; this
0x18001ac46  call    ?TimedOut@FiringTimeoutManager@@QEAA_NXZ; FiringTimeoutManager::TimedOut(void)
0x18001ac4b  test    al, al
0x18001ac4d  jz      short loc_18001AC5D
0x18001ac4f  mov     ebx, 800705B4h
0x18001ac54  mov     [rsp+168h+var_128], ebx
0x18001ac58  jmp     loc_18001AD73
0x18001ac5d  mov     r9d, 1
0x18001ac63  mov     rcx, rdi
0x18001ac66  call    ?OnEnterCall@FiringTimeoutManager@@QEAAJPEBDKW4Locality@@@Z; FiringTimeoutManager::OnEnterCall(char const *,ulong,Locality)
0x18001ac6b  mov     ebx, eax
0x18001ac6d  mov     [rsp+168h+var_128], eax
0x18001ac71  test    eax, eax
0x18001ac73  js      short loc_18001AC87
0x18001ac75  lea     rdx, [r13+10h]; enum Locality *
0x18001ac79  mov     rcx, r12; struct IUnknown *
0x18001ac7c  call    ?DetermineSubscriberLocality@@YAJPEAUIUnknown@@AEAW4Locality@@@Z; DetermineSubscriberLocality(IUnknown *,Locality &)
0x18001ac81  mov     ebx, eax
0x18001ac83  mov     [rsp+168h+var_128], eax
0x18001ac87  mov     rcx, rdi; this
0x18001ac8a  call    ?OnLeaveCall@FiringTimeoutManager@@QEAAXXZ; FiringTimeoutManager::OnLeaveCall(void)
0x18001ac8f  test    ebx, ebx
0x18001ac91  js      loc_18001AD73
0x18001ac97  mov     eax, [r13+10h]
0x18001ac9b  mov     [rdi+8], eax
0x18001ac9e  mov     eax, [r13+10h]
0x18001aca2  dec     eax
0x18001aca4  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001aca8  cmp     eax, 1
0x18001acab  jbe     short loc_18001ACEC
0x18001acad  mov     [rsp+168h+dwCapabilities], 800h; dwCapabilities
0x18001acb5  mov     [rsp+168h+pAuthInfo], r15; pAuthInfo
0x18001acba  mov     [rsp+168h+dwImpLevel], 2; dwImpLevel
0x18001acc2  mov     dword ptr [rsp+168h+ppv], 0; dwAuthnLevel
0x18001acca  mov     r9, r15; pServerPrincName
0x18001accd  or      eax, 0FFFFFFFFh
0x18001acd0  mov     r8d, eax; dwAuthzSvc
0x18001acd3  mov     edx, eax; dwAuthnSvc
0x18001acd5  mov     rcx, r12; pProxy
0x18001acd8  call    cs:__imp_CoSetProxyBlanket
0x18001acde  mov     ebx, eax
0x18001ace0  mov     [rsp+168h+var_128], eax
0x18001ace4  test    eax, eax
0x18001ace6  js      loc_18001AD73
0x18001acec  mov     eax, [r13+10h]
0x18001acf0  test    rsi, rsi
0x18001acf3  jz      short loc_18001AD2A
0x18001acf5  mov     [r13+0], rsi
0x18001acf9  xor     esi, esi
0x18001acfb  mov     [rsp+168h+var_100], rsi
0x18001ad00  dec     eax
0x18001ad02  cmp     eax, 1
0x18001ad05  jbe     short loc_18001AD73
0x18001ad07  mov     [rsp+168h+dwCapabilities], 800h
0x18001ad0f  mov     [rsp+168h+pAuthInfo], r15
0x18001ad14  mov     [rsp+168h+dwImpLevel], 2
0x18001ad1c  mov     dword ptr [rsp+168h+ppv], esi
0x18001ad20  mov     rcx, [rsp+168h+lpsz]
0x18001ad28  jmp     short loc_18001AD5C
0x18001ad2a  mov     [r13+8], r14
0x18001ad2e  xor     r14d, r14d
0x18001ad31  mov     [rsp+168h+var_F8], r14
0x18001ad36  dec     eax
0x18001ad38  cmp     eax, 1
0x18001ad3b  jbe     short loc_18001AD73
0x18001ad3d  mov     [rsp+168h+dwCapabilities], 800h; dwCapabilities
0x18001ad45  mov     [rsp+168h+pAuthInfo], r15; pAuthInfo
0x18001ad4a  mov     [rsp+168h+dwImpLevel], 2; dwImpLevel
0x18001ad52  mov     dword ptr [rsp+168h+ppv], r14d; dwAuthnLevel
0x18001ad57  mov     rcx, [rsp+168h+var_118]; pProxy
0x18001ad5c  or      eax, 0FFFFFFFFh
0x18001ad5f  mov     r9, r15; pServerPrincName
0x18001ad62  mov     r8d, eax; dwAuthzSvc
0x18001ad65  mov     edx, eax; dwAuthnSvc
0x18001ad67  call    cs:__imp_CoSetProxyBlanket
0x18001ad6d  mov     [rsp+168h+var_128], eax
0x18001ad71  mov     ebx, eax
0x18001ad73  mov     r8, r12; struct IUnknown *
0x18001ad76  mov     rdx, rdi; struct FiringTimeoutManager *
0x18001ad79  call    ?ReleaseInterfaceWithTimeout@FiringControl@@AEAAXAEAVFiringTimeoutManager@@PEAUIUnknown@@@Z; FiringControl::ReleaseInterfaceWithTimeout(FiringTimeoutManager &,IUnknown *)
  ... truncated ...
```
