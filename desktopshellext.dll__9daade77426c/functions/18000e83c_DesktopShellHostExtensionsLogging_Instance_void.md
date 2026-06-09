# DesktopShellHostExtensionsLogging::Instance(void)

- ea: `0x18000e83c`
- end: `0x18000e9aa`
- name: `?Instance@DesktopShellHostExtensionsLogging@@KAPEAV1@XZ`
- size: `366`
- prototype: `struct DesktopShellHostExtensionsLogging *(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009cc0`
- `0x180013080`
- `0x1800132a0`
- `0x180030d40`

## callees

- `0x18000e83c`
- `0x18002a3d0`
- `0x18002a85c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e982`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e982`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e87c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e87c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e93b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e93b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e953`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e953`

## pseudocode

```c
struct DesktopShellHostExtensionsLogging *DesktopShellHostExtensionsLogging::Instance(void)
{
  _QWORD *v0; // rbx
  _QWORD *v1; // rdi
  bool v2; // zf
  ULONGLONG *v3; // r9
  WINBOOL v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 *v6; // [rsp+28h] [rbp-30h] BYREF
  GUID ProviderId; // [rsp+30h] [rbp-28h] BYREF

  v6 = 0;
  v5 = 0;
  if ( InitOnceBeginInitialize(&`DesktopShellHostExtensionsLogging::Instance'::`2'::wrapper, 0, &v5, (LPVOID *)&v6)
    && v5 )
  {
    qword_1800AD140 = 0;
    v6 = &qword_1800AD138;
    qword_1800AD138 = (__int64)&DesktopShellHostExtensionsLogging::`vftable';
    byte_1800AD148 = 0;
    dword_1800AD14C = 0;
    qword_1800AD150 = &`DesktopShellHostExtensionsLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_9fb9bd43d52e730c3396f42695231301_::_lambda_invoker_cdecl_);
    v0 = qword_1800AD150;
    qword_1800AD140 = (__int64)qword_1800AD150;
    byte_1800AD148 = 1;
    v1 = (char *)qword_1800AD150 + 32;
    v2 = *((_QWORD *)qword_1800AD150 + 4) == 0;
    ProviderId = *(GUID *)(*((_QWORD *)qword_1800AD150 + 1) - 16LL);
    if ( !v2 )
      __fastfail(5u);
    v3 = (ULONGLONG *)((char *)qword_1800AD150 + 32);
    *((_QWORD *)qword_1800AD150 + 5) = 0;
    v0[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v0, v3) )
      EventSetInformation(*v1, 2, v0[1], *(unsigned __int16 *)v0[1]);
    dword_1800AD14C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800AD138 + 8))(&qword_1800AD138);
    InitOnceComplete(&`DesktopShellHostExtensionsLogging::Instance'::`2'::wrapper, 0, &qword_1800AD138);
  }
  return (struct DesktopShellHostExtensionsLogging *)v6;
}

```

## disassembly

```asm
0x18000e83c  mov     r11, rsp
0x18000e83f  mov     [r11+8], rbx
0x18000e843  mov     [r11+10h], rbp
0x18000e847  push    rdi
0x18000e848  sub     rsp, 50h
0x18000e84c  mov     rax, cs:__security_cookie
0x18000e853  xor     rax, rsp
0x18000e856  mov     [rsp+58h+var_18], rax
0x18000e85b  lea     r9, [r11-30h]; lpContext
0x18000e85f  mov     qword ptr [r11-30h], 0
0x18000e867  lea     r8, [r11-38h]; fPending
0x18000e86b  mov     [rsp+58h+var_38], 0
0x18000e873  xor     edx, edx; dwFlags
0x18000e875  lea     rcx, ?wrapper@?1??Instance@DesktopShellHostExtensionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VDesktopShellHostExtensionsLogging@@@details@wil@@A; lpInitOnce
0x18000e87c  call    cs:__imp_InitOnceBeginInitialize
0x18000e882  test    eax, eax
0x18000e884  jz      loc_18000E988
0x18000e88a  cmp     [rsp+58h+var_38], 0
0x18000e88f  jz      loc_18000E988
0x18000e895  lea     rbp, qword_1800AD138
0x18000e89c  mov     cs:qword_1800AD140, 0
0x18000e8a7  lea     rax, ??_7DesktopShellHostExtensionsLogging@@6B@; const DesktopShellHostExtensionsLogging::`vftable'
0x18000e8ae  mov     [rsp+58h+var_30], rbp
0x18000e8b3  mov     cs:qword_1800AD138, rax
0x18000e8ba  mov     cs:byte_1800AD148, 0
0x18000e8c1  mov     cs:dword_1800AD14C, 0
0x18000e8cb  lea     rax, ?__hInner@?1???0StaticHandle@DesktopShellHostExtensionsLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DesktopShellHostExtensionsLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e8d2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_9fb9bd43d52e730c3396f42695231301_@@CA@XZ; void (__cdecl *)()
0x18000e8d9  mov     cs:qword_1800AD150, rax
0x18000e8e0  call    atexit
0x18000e8e5  mov     rbx, cs:qword_1800AD150
0x18000e8ec  mov     cs:qword_1800AD140, rbx
0x18000e8f3  mov     cs:byte_1800AD148, 1
0x18000e8fa  mov     rax, [rbx+8]
0x18000e8fe  lea     rdi, [rbx+20h]
0x18000e902  cmp     qword ptr [rdi], 0
0x18000e906  movups  xmm0, xmmword ptr [rax-10h]
0x18000e90a  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x18000e910  jz      short loc_18000E919
0x18000e912  mov     ecx, 5
0x18000e917  int     29h; Win8: RtlFailFast(ecx)
0x18000e919  mov     r9, rdi; RegHandle
0x18000e91c  mov     qword ptr [rbx+28h], 0
0x18000e924  mov     r8, rbx; CallbackContext
0x18000e927  mov     qword ptr [rbx+30h], 0
0x18000e92f  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000e936  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x18000e93b  call    cs:__imp_EventRegister
0x18000e941  test    eax, eax
0x18000e943  jnz     short loc_18000E959
0x18000e945  mov     r8, [rbx+8]
0x18000e949  lea     edx, [rax+2]
0x18000e94c  mov     rcx, [rdi]
0x18000e94f  movzx   r9d, word ptr [r8]
0x18000e953  call    cs:__imp_EventSetInformation
0x18000e959  mov     rax, cs:qword_1800AD138
0x18000e960  mov     rcx, rbp
0x18000e963  mov     cs:dword_1800AD14C, 1
0x18000e96d  mov     rax, [rax+8]
0x18000e971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e976  mov     r8, rbp; lpContext
0x18000e979  lea     rcx, ?wrapper@?1??Instance@DesktopShellHostExtensionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VDesktopShellHostExtensionsLogging@@@details@wil@@A; lpInitOnce
0x18000e980  xor     edx, edx; dwFlags
0x18000e982  call    cs:__imp_InitOnceComplete
0x18000e988  mov     rax, [rsp+58h+var_30]
0x18000e98d  mov     rcx, [rsp+58h+var_18]
0x18000e992  xor     rcx, rsp; StackCookie
0x18000e995  call    __security_check_cookie
0x18000e99a  mov     rbx, [rsp+58h+arg_0]
0x18000e99f  mov     rbp, [rsp+58h+arg_8]
0x18000e9a4  add     rsp, 50h
0x18000e9a8  pop     rdi
0x18000e9a9  retn
```
