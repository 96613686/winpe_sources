# NetworkLegacyUxLogging::Provider(void)

- ea: `0x18000dfc0`
- end: `0x18000e127`
- name: `?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `359`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d880`
- `0x18000dfb0`
- `0x18000e5ec`
- `0x18000e6b8`
- `0x18000e7ec`
- `0x18000e8d0`
- `0x18000eb00`
- `0x180017490`
- `0x180017550`
- `0x18001c030`
- `0x18001c0f0`
- `0x18001fa48`

## callees

- `0x1800026bc`
- `0x18000dfc0`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e0c7`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e0c7`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e0ac`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e0ac`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000dff3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000dff3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e0f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e0f6`

## pseudocode

```c
const struct _tlgProvider_t *NetworkLegacyUxLogging::Provider(void)
{
  _QWORD *v0; // rbx
  ULONGLONG *v1; // r9
  WINBOOL fPending; // [rsp+20h] [rbp-38h] BYREF
  LPVOID Context; // [rsp+28h] [rbp-30h] BYREF
  GUID ProviderId; // [rsp+30h] [rbp-28h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`NetworkLegacyUxLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    Context = &qword_1800463C8;
    qword_1800463D0 = 0;
    byte_1800463D8 = 0;
    dword_1800463DC = 0;
    qword_1800463C8 = (__int64)&NetworkLegacyUxLogging::`vftable';
    CallbackContext = &`NetworkLegacyUxLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_0f38c6fafb7aeb3e11e6a93cf8931294_::_lambda_invoker_cdecl_);
    v0 = CallbackContext;
    qword_1800463D0 = (__int64)CallbackContext;
    byte_1800463D8 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v1 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v0[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v0, v1) )
      EventSetInformation(v0[4], 2, v0[1], *(unsigned __int16 *)v0[1]);
    dword_1800463DC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800463C8 + 8))(&qword_1800463C8);
    InitOnceComplete(&`NetworkLegacyUxLogging::Instance'::`2'::wrapper, 0, &qword_1800463C8);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x18000dfc0  push    rsi
0x18000dfc2  sub     rsp, 50h
0x18000dfc6  mov     rax, cs:__security_cookie
0x18000dfcd  xor     rax, rsp
0x18000dfd0  mov     [rsp+58h+var_18], rax
0x18000dfd5  xor     esi, esi
0x18000dfd7  lea     r9, [rsp+58h+Context]; lpContext
0x18000dfdc  lea     r8, [rsp+58h+fPending]; fPending
0x18000dfe1  mov     [rsp+58h+Context], rsi
0x18000dfe6  xor     edx, edx; dwFlags
0x18000dfe8  mov     [rsp+58h+fPending], esi
0x18000dfec  lea     rcx, ?wrapper@?1??Instance@NetworkLegacyUxLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetworkLegacyUxLogging@@@details@wil@@A; lpInitOnce
0x18000dff3  call    cs:__imp_InitOnceBeginInitialize
0x18000dff9  test    eax, eax
0x18000dffb  jz      loc_18000E10B
0x18000e001  cmp     [rsp+58h+fPending], esi
0x18000e005  jz      loc_18000E10B
0x18000e00b  mov     [rsp+58h+arg_0], rbx
0x18000e010  lea     rax, ??_7NetworkLegacyUxLogging@@6B@; const NetworkLegacyUxLogging::`vftable'
0x18000e017  mov     [rsp+58h+arg_8], rbp
0x18000e01c  lea     rbp, qword_1800463C8
0x18000e023  mov     [rsp+58h+Context], rbp
0x18000e028  mov     [rsp+58h+arg_10], rdi
0x18000e02d  mov     cs:qword_1800463D0, rsi
0x18000e034  mov     cs:byte_1800463D8, sil
0x18000e03b  mov     cs:dword_1800463DC, esi
0x18000e041  mov     cs:qword_1800463C8, rax
0x18000e048  lea     rax, ?__hInner@?1???0StaticHandle@NetworkLegacyUxLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `NetworkLegacyUxLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e04f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0f38c6fafb7aeb3e11e6a93cf8931294_@@CA@XZ; void (__cdecl *)()
0x18000e056  mov     cs:CallbackContext, rax
0x18000e05d  call    atexit
0x18000e062  mov     rbx, cs:CallbackContext
0x18000e069  mov     cs:qword_1800463D0, rbx
0x18000e070  mov     cs:byte_1800463D8, 1
0x18000e077  mov     rax, [rbx+8]
0x18000e07b  movups  xmm0, xmmword ptr [rax-10h]
0x18000e07f  movups  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x18000e084  cmp     [rbx+20h], rsi
0x18000e088  jz      short loc_18000E091
0x18000e08a  mov     ecx, 5
0x18000e08f  int     29h; Win8: RtlFailFast(ecx)
0x18000e091  lea     r9, [rbx+20h]; RegHandle
0x18000e095  mov     [rbx+28h], rsi
0x18000e099  mov     r8, rbx; CallbackContext
0x18000e09c  mov     [rbx+30h], rsi
0x18000e0a0  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000e0a7  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x18000e0ac  call    cs:__imp_EventRegister
0x18000e0b2  test    eax, eax
0x18000e0b4  jnz     short loc_18000E0CD
0x18000e0b6  mov     r8, [rbx+8]
0x18000e0ba  mov     edx, 2
0x18000e0bf  mov     rcx, [rbx+20h]
0x18000e0c3  movzx   r9d, word ptr [r8]
0x18000e0c7  call    cs:__imp_EventSetInformation
0x18000e0cd  mov     rax, cs:qword_1800463C8
0x18000e0d4  mov     rcx, rbp
0x18000e0d7  mov     cs:dword_1800463DC, 1
0x18000e0e1  mov     rax, [rax+8]
0x18000e0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0ea  mov     r8, rbp; lpContext
0x18000e0ed  lea     rcx, ?wrapper@?1??Instance@NetworkLegacyUxLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetworkLegacyUxLogging@@@details@wil@@A; lpInitOnce
0x18000e0f4  xor     edx, edx; dwFlags
0x18000e0f6  call    cs:__imp_InitOnceComplete
0x18000e0fc  mov     rdi, [rsp+58h+arg_10]
0x18000e101  mov     rbp, [rsp+58h+arg_8]
0x18000e106  mov     rbx, [rsp+58h+arg_0]
0x18000e10b  mov     rax, [rsp+58h+Context]
0x18000e110  mov     rax, [rax+8]
0x18000e114  mov     rcx, [rsp+58h+var_18]
0x18000e119  xor     rcx, rsp; StackCookie
0x18000e11c  call    __security_check_cookie
0x18000e121  add     rsp, 50h
0x18000e125  pop     rsi
0x18000e126  retn
```
