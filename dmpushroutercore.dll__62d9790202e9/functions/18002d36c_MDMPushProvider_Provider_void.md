# MDMPushProvider::Provider(void)

- ea: `0x18002d36c`
- end: `0x18002d455`
- name: `?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026ebc`
- `0x18002cfa0`
- `0x18002d45c`
- `0x18002dc14`
- `0x18002dd58`
- `0x18002de9c`
- `0x18002e054`
- `0x18002e170`
- `0x18002e3f0`
- `0x18002e670`

## callees

- `0x180001008`
- `0x180003dd8`
- `0x18002d36c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002d394`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002d394`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002d440`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002d440`

## pseudocode

```c
const struct _tlgProvider_t *MDMPushProvider::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`MDMPushProvider::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180051208 = 0;
    v2 = &qword_180051200;
    qword_180051200 = (__int64)&MDMPushProvider::`vftable';
    byte_180051210 = 0;
    dword_180051214 = 0;
    CallbackContext = &`MDMPushProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8e2e3e542c2dc97e9f262390b1f584c8_::_lambda_invoker_cdecl_);
    qword_180051208 = (__int64)CallbackContext;
    byte_180051210 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180051214 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180051200 + 8))(&qword_180051200);
    InitOnceComplete(&`MDMPushProvider::Instance'::`2'::wrapper, 0, &qword_180051200);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18002d36c  mov     rax, rsp
0x18002d36f  push    rbx
0x18002d370  sub     rsp, 20h
0x18002d374  lea     r9, [rax+10h]; lpContext
0x18002d378  mov     qword ptr [rax+10h], 0
0x18002d380  lea     r8, [rax+8]; fPending
0x18002d384  mov     dword ptr [rax+8], 0
0x18002d38b  xor     edx, edx; dwFlags
0x18002d38d  lea     rcx, ?wrapper@?1??Instance@MDMPushProvider@@KAPEAV2@XZ@4V?$static_lazy@VMDMPushProvider@@@details@wil@@A; lpInitOnce
0x18002d394  call    cs:__imp_InitOnceBeginInitialize
0x18002d39a  test    eax, eax
0x18002d39c  jz      loc_18002D446
0x18002d3a2  cmp     [rsp+28h+arg_0], 0
0x18002d3a7  jz      loc_18002D446
0x18002d3ad  lea     rbx, qword_180051200
0x18002d3b4  mov     cs:qword_180051208, 0
0x18002d3bf  lea     rax, ??_7MDMPushProvider@@6B@; const MDMPushProvider::`vftable'
0x18002d3c6  mov     [rsp+28h+arg_8], rbx
0x18002d3cb  mov     cs:qword_180051200, rax
0x18002d3d2  mov     cs:byte_180051210, 0
0x18002d3d9  mov     cs:dword_180051214, 0
0x18002d3e3  lea     rax, ?__hInner@?1???0StaticHandle@MDMPushProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MDMPushProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002d3ea  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8e2e3e542c2dc97e9f262390b1f584c8_@@CA@XZ; void (__cdecl *)()
0x18002d3f1  mov     cs:CallbackContext, rax
0x18002d3f8  call    atexit
0x18002d3fd  mov     rcx, cs:CallbackContext; CallbackContext
0x18002d404  mov     cs:qword_180051208, rcx
0x18002d40b  mov     cs:byte_180051210, 1
0x18002d412  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002d417  mov     rax, cs:qword_180051200
0x18002d41e  mov     rcx, rbx
0x18002d421  mov     cs:dword_180051214, 1
0x18002d42b  mov     rax, [rax+8]
0x18002d42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d434  mov     r8, rbx; lpContext
0x18002d437  lea     rcx, ?wrapper@?1??Instance@MDMPushProvider@@KAPEAV2@XZ@4V?$static_lazy@VMDMPushProvider@@@details@wil@@A; lpInitOnce
0x18002d43e  xor     edx, edx; dwFlags
0x18002d440  call    cs:__imp_InitOnceComplete
0x18002d446  mov     rax, [rsp+28h+arg_8]
0x18002d44b  mov     rax, [rax+8]
0x18002d44f  add     rsp, 20h
0x18002d453  pop     rbx
0x18002d454  retn
```
