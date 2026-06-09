# COleScript::SetScriptSite(IActiveScriptSite *)

- ea: `0x180051880`
- end: `0x180051b02`
- name: `?SetScriptSite@COleScript@@UEAAJPEAUIActiveScriptSite@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IActiveScriptSite *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800020c8`
- `0x180003fac`
- `0x180019acc`
- `0x180019e28`
- `0x18001a29c`
- `0x180042618`
- `0x180046e2c`
- `0x180051880`
- `0x1800782bc`
- `0x18007b6f0`
- `0x18007d458`
- `0x180089b4c`
- `0x180091e44`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180051adc`
- `KERNEL32!GetTickCount64` at `0x180051adc`
- `KERNEL32!GetCurrentThreadId` at `0x1800518c5`
- `KERNEL32!GetCurrentThreadId` at `0x1800518d7`
- `KERNEL32!GetCurrentThreadId` at `0x1800518c5`
- `KERNEL32!GetCurrentThreadId` at `0x1800518d7`
- `ole32!CoCreateInstance` at `0x180051a30`
- `ole32!CoCreateInstance` at `0x180051a30`

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
0x180051880  push    rbx
0x180051882  push    rbp
0x180051883  push    rsi
0x180051884  push    rdi
0x180051885  push    r14
0x180051887  sub     rsp, 30h
0x18005188b  mov     rsi, rdx
0x18005188e  mov     rdi, rcx
0x180051891  test    rdx, rdx
0x180051894  jnz     short loc_1800518A0
0x180051896  mov     eax, 80004003h
0x18005189b  jmp     loc_180051AF7
0x1800518a0  cmp     qword ptr [rcx+0B0h], 0
0x1800518a8  jz      short loc_1800518B4
0x1800518aa  mov     eax, 8000FFFFh
0x1800518af  jmp     loc_180051AF7
0x1800518b4  or      ebp, 0FFFFFFFFh
0x1800518b7  cmp     [rcx+104h], ebp
0x1800518bd  jz      short loc_1800518D7
0x1800518bf  mov     ebx, [rcx+104h]
0x1800518c5  call    cs:__imp_GetCurrentThreadId
0x1800518cb  cmp     ebx, eax
0x1800518cd  jz      short loc_1800518D7
0x1800518cf  mov     rcx, rdi; this
0x1800518d2  call    ?LogTelemetryOnSetScriptSiteMultithreading@COleScript@@QEAAXXZ; COleScript::LogTelemetryOnSetScriptSiteMultithreading(void)
0x1800518d7  call    cs:__imp_GetCurrentThreadId
0x1800518dd  lea     r14, [rdi+2A0h]
0x1800518e4  mov     r8, rsi; struct IActiveScriptSite *
0x1800518e7  mov     rcx, r14; struct CSession **
0x1800518ea  mov     [rdi+104h], eax
0x1800518f0  mov     rdx, rdi; struct COleScript *
0x1800518f3  call    ?Create@CSession@@SAJPEAPEAV1@PEAVCOleScript@@PEAUIActiveScriptSite@@@Z; CSession::Create(CSession * *,COleScript *,IActiveScriptSite *)
0x1800518f8  test    eax, eax
0x1800518fa  jns     short loc_180051907
0x1800518fc  mov     [rdi+104h], ebp
0x180051902  jmp     loc_180051AF7
0x180051907  mov     [rdi+0B0h], rsi
0x18005190e  mov     rcx, rsi
0x180051911  mov     rax, [rsi]
0x180051914  mov     rax, [rax+8]
0x180051918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005191d  mov     qword ptr [rdi+2E4h], 0
0x180051928  lea     rdx, [rsp+58h+arg_8]
0x18005192d  mov     rax, [rsi]
0x180051930  mov     rcx, rsi
0x180051933  mov     [rsp+58h+arg_8], 0
0x18005193b  mov     rax, [rax+18h]
0x18005193f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051944  test    eax, eax
0x180051946  js      short loc_18005196A
0x180051948  mov     edx, [rsp+58h+arg_8]; unsigned int
0x18005194c  mov     rcx, rdi; this
0x18005194f  call    ?SetCurrentLocale@COleScript@@QEAAHK@Z; COleScript::SetCurrentLocale(ulong)
0x180051954  test    eax, eax
0x180051956  jz      short loc_18005196A
0x180051958  mov     eax, [rdi+0C8h]
0x18005195e  mov     [rdi+0D0h], eax
0x180051964  mov     [rdi+0D4h], eax
0x18005196a  mov     rcx, rdi; this
0x18005196d  call    ?RegisterNamedItems@COleScript@@AEAAJXZ; COleScript::RegisterNamedItems(void)
0x180051972  cmp     dword ptr [rdi+108h], 0
0x180051979  jz      short loc_180051988
0x18005197b  mov     edx, 5; enum tagSCRIPTSTATE
0x180051980  mov     rcx, rdi; this
0x180051983  call    ?ChangeScriptState@COleScript@@AEAAXW4tagSCRIPTSTATE@@@Z; COleScript::ChangeScriptState(tagSCRIPTSTATE)
0x180051988  mov     ecx, [rdi+2B0h]
0x18005198e  mov     eax, ecx
0x180051990  xor     eax, [rdi+350h]
0x180051996  and     ecx, 0FFFFFFFDh
0x180051999  and     eax, 0FFFFFFFCh
0x18005199c  xor     eax, ecx
0x18005199e  mov     rcx, rdi; this
0x1800519a1  mov     [rdi+350h], eax
0x1800519a7  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x1800519ac  test    eax, eax
0x1800519ae  jz      short loc_180051A0A
0x1800519b0  mov     rcx, rdi; this
0x1800519b3  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x1800519b8  test    eax, eax
0x1800519ba  jnz     short loc_1800519C6
0x1800519bc  mov     eax, 80004005h
0x1800519c1  jmp     loc_180051AF7
0x1800519c6  mov     rax, [rdi+2B8h]
0x1800519cd  test    rax, rax
0x1800519d0  jz      short loc_180051A02
0x1800519d2  mov     ebp, [rax+1Ch]
0x1800519d5  test    ebp, ebp
0x1800519d7  jle     short loc_180051A02
0x1800519d9  xor     ebx, ebx
0x1800519db  mov     rdx, [rdi+2B8h]
0x1800519e2  mov     eax, ebx
0x1800519e4  imul    eax, [rdx+0Ch]
0x1800519e8  mov     rdx, [rdx+10h]
0x1800519ec  movsxd  rcx, eax
0x1800519ef  mov     rdx, [rcx+rdx+8]; struct CScriptBody *
0x1800519f4  mov     rcx, rdi; this
0x1800519f7  call    ?DbgRegisterScriptBlock@COleScript@@QEAAJPEAVCScriptBody@@@Z; COleScript::DbgRegisterScriptBlock(CScriptBody *)
0x1800519fc  inc     ebx
0x1800519fe  cmp     ebx, ebp
0x180051a00  jl      short loc_1800519DB
0x180051a02  mov     rcx, rdi; this
0x180051a05  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180051a0a  add     rdi, 398h
0x180051a11  cmp     qword ptr [rdi], 0
0x180051a15  jnz     short loc_180051A36
0x180051a17  xor     edx, edx; pUnkOuter
0x180051a19  mov     [rsp+58h+ppv], rdi; ppv
0x180051a1e  lea     r9, IID_ISystemDebugEventFire; riid
0x180051a25  lea     rcx, CLSID_VSA_IEC; rclsid
0x180051a2c  lea     r8d, [rdx+1]; dwClsContext
0x180051a30  call    cs:__imp_CoCreateInstance
0x180051a36  mov     rdx, [rdi]; struct ISystemDebugEventFire *
0x180051a39  test    rdx, rdx
0x180051a3c  jz      short loc_180051A46
0x180051a3e  mov     rcx, [r14]; this
0x180051a41  call    ?StartDebugEvents@CSession@@QEAAJPEAUISystemDebugEventFire@@@Z; CSession::StartDebugEvents(ISystemDebugEventFire *)
0x180051a46  mov     rax, cs:QueryProtectedPolicyPtr
0x180051a4d  lea     rdx, [rsp+58h+arg_10]
0x180051a52  lea     rcx, PPID_ProhibitUnsafeExtensions
0x180051a59  mov     [rsp+58h+arg_10], 0
0x180051a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a67  test    eax, eax
0x180051a69  jz      short loc_180051AB2
0x180051a6b  cmp     [rsp+58h+arg_10], 2
0x180051a71  jnz     short loc_180051AB2
0x180051a73  mov     rax, [rsi]
0x180051a76  lea     r8, [rsp+58h+arg_18]
0x180051a7b  lea     rdx, IID_IActiveScriptSiteDebugEx
0x180051a82  mov     [rsp+58h+arg_18], 0
0x180051a8b  mov     rcx, rsi
0x180051a8e  mov     rax, [rax]
0x180051a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a96  test    eax, eax
0x180051a98  js      short loc_180051AAD
0x180051a9a  mov     rcx, [rsp+58h+arg_18]
0x180051a9f  mov     rax, [rcx]
0x180051aa2  mov     rax, [rax+10h]
0x180051aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051aab  jmp     short loc_180051AB2
0x180051aad  call    SuppressUnsafeExtensionPolicy
0x180051ab2  mov     rdi, cs:g_pTraceLoggingClient
0x180051ab9  cmp     dword ptr [rdi+130h], 0
0x180051ac0  jnz     short loc_180051AD5
0x180051ac2  lea     rdx, aJscriptsetscri; "JScriptSetScriptStateStarted"
0x180051ac9  mov     rcx, rdi; this
0x180051acc  call    ?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z; RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)
0x180051ad1  test    eax, eax
0x180051ad3  js      short loc_180051AF5
0x180051ad5  mov     rbx, [rdi+128h]
0x180051adc  call    cs:__imp_GetTickCount64
0x180051ae2  sub     rax, rbx
0x180051ae5  cmp     rax, [rdi+18h]
0x180051ae9  ja      short loc_180051AF5
0x180051aeb  mov     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x180051af5  xor     eax, eax
0x180051af7  add     rsp, 30h
0x180051afb  pop     r14
0x180051afd  pop     rdi
0x180051afe  pop     rsi
0x180051aff  pop     rbp
0x180051b00  pop     rbx
0x180051b01  retn
```
