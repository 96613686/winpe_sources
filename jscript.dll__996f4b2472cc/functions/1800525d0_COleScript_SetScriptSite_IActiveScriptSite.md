# COleScript::SetScriptSite(IActiveScriptSite *)

- ea: `0x1800525d0`
- end: `0x18005286b`
- name: `?SetScriptSite@COleScript@@UEAAJPEAUIActiveScriptSite@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IActiveScriptSite *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180016aec`
- `0x180016e68`
- `0x1800172e8`
- `0x1800323cc`
- `0x18003fa28`
- `0x1800437f8`
- `0x180047b4c`
- `0x1800525d0`
- `0x1800798d4`
- `0x18007cf28`
- `0x18007ed58`
- `0x18008bb4c`
- `0x1800940a4`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18005283e`
- `KERNEL32!GetTickCount64` at `0x18005283e`
- `KERNEL32!GetCurrentThreadId` at `0x180052615`
- `KERNEL32!GetCurrentThreadId` at `0x18005262d`
- `KERNEL32!GetCurrentThreadId` at `0x180052615`
- `KERNEL32!GetCurrentThreadId` at `0x18005262d`
- `ole32!CoCreateInstance` at `0x18005278c`
- `ole32!CoCreateInstance` at `0x18005278c`

## pseudocode

```c
__int64 __fastcall COleScript::SetScriptSite(COleScript *this, struct IActiveScriptSite *a2)
{
  __int64 result; // rax
  int v5; // ebx
  CSession **v6; // r14
  struct IActiveScriptSiteVtbl *lpVtbl; // rax
  int v8; // eax
  __int64 v9; // rax
  int v10; // ebp
  int i; // ebx
  LPVOID *ppv; // rdi
  struct IActiveScriptSiteVtbl *v13; // rax
  RegistryBasedThrottle *v14; // rdi
  __int64 v15; // rbx
  unsigned int v16; // [rsp+68h] [rbp+10h] BYREF
  __int64 v17; // [rsp+70h] [rbp+18h] BYREF
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( *((_QWORD *)this + 22) )
    return 2147549183LL;
  if ( *((_DWORD *)this + 65) != -1 )
  {
    v5 = *((_DWORD *)this + 65);
    if ( v5 != GetCurrentThreadId() )
      COleScript::LogTelemetryOnSetScriptSiteMultithreading(this);
  }
  v6 = (CSession **)((char *)this + 672);
  *((_DWORD *)this + 65) = GetCurrentThreadId();
  result = CSession::Create((struct CSession **)this + 84, this, a2);
  if ( (int)result < 0 )
  {
    *((_DWORD *)this + 65) = -1;
    return result;
  }
  *((_QWORD *)this + 22) = a2;
  ((void (__fastcall *)(struct IActiveScriptSite *))a2->lpVtbl->AddRef)(a2);
  *(_QWORD *)((char *)this + 740) = 0;
  lpVtbl = a2->lpVtbl;
  v16 = 0;
  if ( ((int (__fastcall *)(struct IActiveScriptSite *, unsigned int *))lpVtbl->GetLCID)(a2, &v16) >= 0
    && COleScript::SetCurrentLocale(this, v16) )
  {
    v8 = *((_DWORD *)this + 50);
    *((_DWORD *)this + 52) = v8;
    *((_DWORD *)this + 53) = v8;
  }
  COleScript::RegisterNamedItems(this);
  if ( *((_DWORD *)this + 66) )
    COleScript::ChangeScriptState(this, SCRIPTSTATE_INITIALIZED);
  *((_DWORD *)this + 212) = *((_DWORD *)this + 172)
                          & 0xFFFFFFFD
                          ^ (*((_DWORD *)this + 212)
                           ^ *((_DWORD *)this + 172))
                          & 0xFFFFFFFC;
  if ( (unsigned int)COleScript::FDebuggerEnabled(this) )
  {
    if ( !(unsigned int)COleScript::DisableInterrupts(this) )
      return 2147500037LL;
    v9 = *((_QWORD *)this + 87);
    if ( v9 )
    {
      v10 = *(_DWORD *)(v9 + 28);
      if ( v10 > 0 )
      {
        for ( i = 0; i < v10; ++i )
          COleScript::DbgRegisterScriptBlock(
            this,
            *(struct CScriptBody **)(*(_DWORD *)(*((_QWORD *)this + 87) + 12LL) * i
                                   + *(_QWORD *)(*((_QWORD *)this + 87) + 16LL)
                                   + 8LL));
      }
    }
    COleScript::EnableInterrupts(this);
  }
  ppv = (LPVOID *)((char *)this + 920);
  if ( !*ppv )
    CoCreateInstance(&CLSID_VSA_IEC, 0, 1u, &IID_ISystemDebugEventFire, ppv);
  if ( *ppv )
    CSession::StartDebugEvents(*v6, (struct ISystemDebugEventFire *)*ppv);
  v17 = 0;
  if ( (unsigned int)QueryProtectedPolicyPtr(
                       (COleScript *)PPID_ProhibitUnsafeExtensions,
                       (struct IRemoteDebugApplicationThread *)&v17)
    && v17 == 2 )
  {
    v13 = a2->lpVtbl;
    v18 = 0;
    if ( ((__int64 (__fastcall *)(struct IActiveScriptSite *, GUID *, __int64 *))v13->QueryInterface)(
           a2,
           &IID_IActiveScriptSiteDebugEx,
           &v18) < 0 )
      SuppressUnsafeExtensionPolicy();
    else
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v14 = g_pTraceLoggingClient;
  if ( *((_DWORD *)g_pTraceLoggingClient + 76)
    || (int)RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(
              g_pTraceLoggingClient,
              "JScriptSetScriptStateStarted") >= 0 )
  {
    v15 = *((_QWORD *)v14 + 37);
    if ( GetTickCount64() - v15 <= *((_QWORD *)v14 + 3) )
      COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800525d0  push    rbx
0x1800525d2  push    rbp
0x1800525d3  push    rsi
0x1800525d4  push    rdi
0x1800525d5  push    r14
0x1800525d7  sub     rsp, 30h
0x1800525db  mov     rsi, rdx
0x1800525de  mov     rdi, rcx
0x1800525e1  test    rdx, rdx
0x1800525e4  jnz     short loc_1800525F0
0x1800525e6  mov     eax, 80004003h
0x1800525eb  jmp     loc_18005285F
0x1800525f0  cmp     qword ptr [rcx+0B0h], 0
0x1800525f8  jz      short loc_180052604
0x1800525fa  mov     eax, 8000FFFFh
0x1800525ff  jmp     loc_18005285F
0x180052604  or      ebp, 0FFFFFFFFh
0x180052607  cmp     [rcx+104h], ebp
0x18005260d  jz      short loc_18005262D
0x18005260f  mov     ebx, [rcx+104h]
0x180052615  call    cs:__imp_GetCurrentThreadId
0x18005261c  nop     dword ptr [rax+rax+00h]
0x180052621  cmp     ebx, eax
0x180052623  jz      short loc_18005262D
0x180052625  mov     rcx, rdi; this
0x180052628  call    ?LogTelemetryOnSetScriptSiteMultithreading@COleScript@@QEAAXXZ; COleScript::LogTelemetryOnSetScriptSiteMultithreading(void)
0x18005262d  call    cs:__imp_GetCurrentThreadId
0x180052634  nop     dword ptr [rax+rax+00h]
0x180052639  lea     r14, [rdi+2A0h]
0x180052640  mov     r8, rsi; struct IActiveScriptSite *
0x180052643  mov     rcx, r14; struct CSession **
0x180052646  mov     [rdi+104h], eax
0x18005264c  mov     rdx, rdi; struct COleScript *
0x18005264f  call    ?Create@CSession@@SAJPEAPEAV1@PEAVCOleScript@@PEAUIActiveScriptSite@@@Z; CSession::Create(CSession * *,COleScript *,IActiveScriptSite *)
0x180052654  test    eax, eax
0x180052656  jns     short loc_180052663
0x180052658  mov     [rdi+104h], ebp
0x18005265e  jmp     loc_18005285F
0x180052663  mov     [rdi+0B0h], rsi
0x18005266a  mov     rcx, rsi
0x18005266d  mov     rax, [rsi]
0x180052670  mov     rax, [rax+8]
0x180052674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052679  mov     qword ptr [rdi+2E4h], 0
0x180052684  lea     rdx, [rsp+58h+arg_8]
0x180052689  mov     rax, [rsi]
0x18005268c  mov     rcx, rsi
0x18005268f  mov     [rsp+58h+arg_8], 0
0x180052697  mov     rax, [rax+18h]
0x18005269b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526a0  test    eax, eax
0x1800526a2  js      short loc_1800526C6
0x1800526a4  mov     edx, [rsp+58h+arg_8]; unsigned int
0x1800526a8  mov     rcx, rdi; this
0x1800526ab  call    ?SetCurrentLocale@COleScript@@QEAAHK@Z; COleScript::SetCurrentLocale(ulong)
0x1800526b0  test    eax, eax
0x1800526b2  jz      short loc_1800526C6
0x1800526b4  mov     eax, [rdi+0C8h]
0x1800526ba  mov     [rdi+0D0h], eax
0x1800526c0  mov     [rdi+0D4h], eax
0x1800526c6  mov     rcx, rdi; this
0x1800526c9  call    ?RegisterNamedItems@COleScript@@AEAAJXZ; COleScript::RegisterNamedItems(void)
0x1800526ce  cmp     dword ptr [rdi+108h], 0
0x1800526d5  jz      short loc_1800526E4
0x1800526d7  mov     edx, 5; enum tagSCRIPTSTATE
0x1800526dc  mov     rcx, rdi; this
0x1800526df  call    ?ChangeScriptState@COleScript@@AEAAXW4tagSCRIPTSTATE@@@Z; COleScript::ChangeScriptState(tagSCRIPTSTATE)
0x1800526e4  mov     ecx, [rdi+2B0h]
0x1800526ea  mov     eax, ecx
0x1800526ec  xor     eax, [rdi+350h]
0x1800526f2  and     ecx, 0FFFFFFFDh
0x1800526f5  and     eax, 0FFFFFFFCh
0x1800526f8  xor     eax, ecx
0x1800526fa  mov     rcx, rdi; this
0x1800526fd  mov     [rdi+350h], eax
0x180052703  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x180052708  test    eax, eax
0x18005270a  jz      short loc_180052766
0x18005270c  mov     rcx, rdi; this
0x18005270f  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180052714  test    eax, eax
0x180052716  jnz     short loc_180052722
0x180052718  mov     eax, 80004005h
0x18005271d  jmp     loc_18005285F
0x180052722  mov     rax, [rdi+2B8h]
0x180052729  test    rax, rax
0x18005272c  jz      short loc_18005275E
0x18005272e  mov     ebp, [rax+1Ch]
0x180052731  test    ebp, ebp
0x180052733  jle     short loc_18005275E
0x180052735  xor     ebx, ebx
0x180052737  mov     rdx, [rdi+2B8h]
0x18005273e  mov     eax, ebx
0x180052740  imul    eax, [rdx+0Ch]
0x180052744  mov     rdx, [rdx+10h]
0x180052748  movsxd  rcx, eax
0x18005274b  mov     rdx, [rcx+rdx+8]; struct CScriptBody *
0x180052750  mov     rcx, rdi; this
0x180052753  call    ?DbgRegisterScriptBlock@COleScript@@QEAAJPEAVCScriptBody@@@Z; COleScript::DbgRegisterScriptBlock(CScriptBody *)
0x180052758  inc     ebx
0x18005275a  cmp     ebx, ebp
0x18005275c  jl      short loc_180052737
0x18005275e  mov     rcx, rdi; this
0x180052761  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180052766  add     rdi, 398h
0x18005276d  cmp     qword ptr [rdi], 0
0x180052771  jnz     short loc_180052798
0x180052773  xor     edx, edx; pUnkOuter
0x180052775  mov     [rsp+58h+ppv], rdi; ppv
0x18005277a  lea     r9, IID_ISystemDebugEventFire; riid
0x180052781  lea     rcx, CLSID_VSA_IEC; rclsid
0x180052788  lea     r8d, [rdx+1]; dwClsContext
0x18005278c  call    cs:__imp_CoCreateInstance
0x180052793  nop     dword ptr [rax+rax+00h]
0x180052798  mov     rdx, [rdi]; struct ISystemDebugEventFire *
0x18005279b  test    rdx, rdx
0x18005279e  jz      short loc_1800527A8
0x1800527a0  mov     rcx, [r14]; this
0x1800527a3  call    ?StartDebugEvents@CSession@@QEAAJPEAUISystemDebugEventFire@@@Z; CSession::StartDebugEvents(ISystemDebugEventFire *)
0x1800527a8  mov     rax, cs:QueryProtectedPolicyPtr
0x1800527af  lea     rdx, [rsp+58h+arg_10]
0x1800527b4  lea     rcx, PPID_ProhibitUnsafeExtensions
0x1800527bb  mov     [rsp+58h+arg_10], 0
0x1800527c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527c9  test    eax, eax
0x1800527cb  jz      short loc_180052814
0x1800527cd  cmp     [rsp+58h+arg_10], 2
0x1800527d3  jnz     short loc_180052814
0x1800527d5  mov     rax, [rsi]
0x1800527d8  lea     r8, [rsp+58h+arg_18]
0x1800527dd  lea     rdx, IID_IActiveScriptSiteDebugEx
0x1800527e4  mov     [rsp+58h+arg_18], 0
0x1800527ed  mov     rcx, rsi
0x1800527f0  mov     rax, [rax]
0x1800527f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527f8  test    eax, eax
0x1800527fa  js      short loc_18005280F
0x1800527fc  mov     rcx, [rsp+58h+arg_18]
0x180052801  mov     rax, [rcx]
0x180052804  mov     rax, [rax+10h]
0x180052808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005280d  jmp     short loc_180052814
0x18005280f  call    SuppressUnsafeExtensionPolicy
0x180052814  mov     rdi, cs:g_pTraceLoggingClient
0x18005281b  cmp     dword ptr [rdi+130h], 0
0x180052822  jnz     short loc_180052837
0x180052824  lea     rdx, aJscriptsetscri; "JScriptSetScriptStateStarted"
0x18005282b  mov     rcx, rdi; this
0x18005282e  call    ?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z; RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)
0x180052833  test    eax, eax
0x180052835  js      short loc_18005285D
0x180052837  mov     rbx, [rdi+128h]
0x18005283e  call    cs:__imp_GetTickCount64
0x180052845  nop     dword ptr [rax+rax+00h]
0x18005284a  sub     rax, rbx
0x18005284d  cmp     rax, [rdi+18h]
0x180052851  ja      short loc_18005285D
0x180052853  mov     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x18005285d  xor     eax, eax
0x18005285f  add     rsp, 30h
0x180052863  pop     r14
0x180052865  pop     rdi
0x180052866  pop     rsi
0x180052867  pop     rbp
0x180052868  pop     rbx
0x180052869  retn
```
