# _TlgActivityBase<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::zInternalStart(void)

- ea: `0x18000dec0`
- end: `0x18000e004`
- name: `?zInternalStart@?$_TlgActivityBase@V?$ActivityData@VDesktopShellHostExtensionsLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0EAAAAAAAAAAA@$04@@QEAAXXZ`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000de30`

## callees

- `0x18000cbd0`
- `0x18000dec0`
- `0x18002a85c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000df94`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000df94`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000deec`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000deec`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000dfdf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000dfdf`

## pseudocode

```c
int __fastcall _TlgActivityBase<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::zInternalStart(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  WINBOOL fPending; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Context; // [rsp+38h] [rbp+10h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`DesktopShellHostExtensionsLogging::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_1800AD140 = 0;
    Context = &qword_1800AD138;
    byte_1800AD148 = 0;
    dword_1800AD14C = 0;
    qword_1800AD138 = (__int64)&DesktopShellHostExtensionsLogging::`vftable';
    qword_1800AD150 = &`DesktopShellHostExtensionsLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_9fb9bd43d52e730c3396f42695231301_::_lambda_invoker_cdecl_);
    qword_1800AD140 = (__int64)qword_1800AD150;
    byte_1800AD148 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1800AD150);
    dword_1800AD14C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800AD138 + 8))(&qword_1800AD138);
    InitOnceComplete(&`DesktopShellHostExtensionsLogging::Instance'::`2'::wrapper, 0, &qword_1800AD138);
  }
  v2 = *((_QWORD *)Context + 1);
  LODWORD(v3) = *(_DWORD *)v2;
  if ( *(_DWORD *)v2 > 5u
    && (v3 = *(_QWORD *)(v2 + 16), (v3 & 0x400000000000LL) != 0)
    && (LODWORD(v3) = 0, (*(_QWORD *)(v2 + 24) & 0x400000000000LL) == *(_QWORD *)(v2 + 24)) )
  {
    LODWORD(v3) = EventActivityIdControl(3u, (LPGUID)(a1 + 8));
    *(_DWORD *)a1 = 1;
  }
  else
  {
    *(_OWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 1;
  }
  return v3;
}

```

## disassembly

```asm
0x18000dec0  push    rbx
0x18000dec2  sub     rsp, 20h
0x18000dec6  mov     rbx, rcx
0x18000dec9  mov     [rsp+28h+arg_10], rsi
0x18000dece  xor     esi, esi
0x18000ded0  lea     r9, [rsp+28h+Context]; lpContext
0x18000ded5  lea     r8, [rsp+28h+fPending]; fPending
0x18000deda  mov     [rsp+28h+Context], rsi
0x18000dedf  xor     edx, edx; dwFlags
0x18000dee1  mov     [rsp+28h+fPending], esi
0x18000dee5  lea     rcx, ?wrapper@?1??Instance@DesktopShellHostExtensionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VDesktopShellHostExtensionsLogging@@@details@wil@@A; lpInitOnce
0x18000deec  call    cs:__imp_InitOnceBeginInitialize
0x18000def2  test    eax, eax
0x18000def4  jz      loc_18000DF9F
0x18000defa  cmp     [rsp+28h+fPending], esi
0x18000defe  jz      loc_18000DF9F
0x18000df04  mov     [rsp+28h+arg_18], rdi
0x18000df09  lea     rax, ??_7DesktopShellHostExtensionsLogging@@6B@; const DesktopShellHostExtensionsLogging::`vftable'
0x18000df10  lea     rdi, qword_1800AD138
0x18000df17  mov     cs:qword_1800AD140, rsi
0x18000df1e  mov     [rsp+28h+Context], rdi
0x18000df23  mov     cs:byte_1800AD148, sil
0x18000df2a  mov     cs:dword_1800AD14C, esi
0x18000df30  mov     cs:qword_1800AD138, rax
0x18000df37  lea     rax, ?__hInner@?1???0StaticHandle@DesktopShellHostExtensionsLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DesktopShellHostExtensionsLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000df3e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_9fb9bd43d52e730c3396f42695231301_@@CA@XZ; void (__cdecl *)()
0x18000df45  mov     cs:qword_1800AD150, rax
0x18000df4c  call    atexit
0x18000df51  mov     rcx, cs:qword_1800AD150; CallbackContext
0x18000df58  mov     cs:qword_1800AD140, rcx
0x18000df5f  mov     cs:byte_1800AD148, 1
0x18000df66  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000df6b  mov     rax, cs:qword_1800AD138
0x18000df72  mov     rcx, rdi
0x18000df75  mov     cs:dword_1800AD14C, 1
0x18000df7f  mov     rax, [rax+8]
0x18000df83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df88  mov     r8, rdi; lpContext
0x18000df8b  lea     rcx, ?wrapper@?1??Instance@DesktopShellHostExtensionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VDesktopShellHostExtensionsLogging@@@details@wil@@A; lpInitOnce
0x18000df92  xor     edx, edx; dwFlags
0x18000df94  call    cs:__imp_InitOnceComplete
0x18000df9a  mov     rdi, [rsp+28h+arg_18]
0x18000df9f  mov     rax, [rsp+28h+Context]
0x18000dfa4  mov     rsi, [rsp+28h+arg_10]
0x18000dfa9  mov     rcx, [rax+8]
0x18000dfad  mov     eax, [rcx]
0x18000dfaf  cmp     eax, 5
0x18000dfb2  jbe     short loc_18000DFF1
0x18000dfb4  mov     rdx, [rcx+18h]
0x18000dfb8  mov     rax, [rcx+10h]
0x18000dfbc  mov     rcx, 400000000000h
0x18000dfc6  test    rcx, rax
0x18000dfc9  jz      short loc_18000DFF1
0x18000dfcb  mov     rax, rdx
0x18000dfce  and     rax, rcx
0x18000dfd1  cmp     rax, rdx
0x18000dfd4  jnz     short loc_18000DFF1
0x18000dfd6  lea     rdx, [rbx+8]; ActivityId
0x18000dfda  mov     ecx, 3; ControlCode
0x18000dfdf  call    cs:__imp_EventActivityIdControl
0x18000dfe5  mov     dword ptr [rbx], 1
0x18000dfeb  add     rsp, 20h
0x18000dfef  pop     rbx
0x18000dff0  retn
0x18000dff1  xorps   xmm0, xmm0
0x18000dff4  movups  xmmword ptr [rbx+8], xmm0
0x18000dff8  mov     dword ptr [rbx], 1
0x18000dffe  add     rsp, 20h
0x18000e002  pop     rbx
0x18000e003  retn
```
