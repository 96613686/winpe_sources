# TlgHelper::Provider(void)

- ea: `0x18000e7ec`
- end: `0x18000e8d5`
- name: `?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `38`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000425c`
- `0x1800043f8`
- `0x180004470`
- `0x1800044e8`
- `0x180004560`
- `0x1800045dc`
- `0x180004654`
- `0x1800046cc`
- `0x180004744`
- `0x1800047bc`
- `0x180004854`
- `0x1800048ec`
- `0x180004964`
- `0x1800049dc`
- `0x180004a54`
- `0x180004aec`
- `0x180004b84`
- `0x180004bfc`
- `0x180004c74`
- `0x180008bf0`
- `0x1800094d4`
- `0x180009fc0`
- `0x18000a6d4`
- `0x18000aed0`
- `0x18000b238`
- `0x18000dcdc`
- `0x18000e168`
- `0x180010ac4`
- `0x1800115f8`
- `0x180011760`
- `0x1800132f0`
- `0x1800139d0`
- `0x180014030`
- `0x1800149b8`
- `0x18001d4f4`
- `0x18001d5d0`
- `0x18001de90`
- `0x18001e080`

## callees

- `0x180001940`
- `0x180003268`
- `0x18000e7ec`
- `0x180023010`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18000e814`
- `KERNEL32!InitOnceBeginInitialize` at `0x18000e814`
- `KERNEL32!InitOnceComplete` at `0x18000e8c0`
- `KERNEL32!InitOnceComplete` at `0x18000e8c0`

## pseudocode

```c
const struct _tlgProvider_t *TlgHelper::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`TlgHelper::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_18002F858 = 0;
    v2 = &qword_18002F850;
    qword_18002F850 = (__int64)&TlgHelper::`vftable';
    byte_18002F860 = 0;
    dword_18002F864 = 0;
    CallbackContext = &`TlgHelper::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_27248ce03d41213a4b11ef93405cd787_::_lambda_invoker_cdecl_);
    qword_18002F858 = (__int64)CallbackContext;
    byte_18002F860 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_18002F864 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18002F850 + 8))(&qword_18002F850);
    InitOnceComplete(&`TlgHelper::Instance'::`2'::wrapper, 0, &qword_18002F850);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18000e7ec  mov     rax, rsp
0x18000e7ef  push    rbx
0x18000e7f0  sub     rsp, 20h
0x18000e7f4  lea     r9, [rax+10h]; lpContext
0x18000e7f8  mov     qword ptr [rax+10h], 0
0x18000e800  lea     r8, [rax+8]; fPending
0x18000e804  mov     dword ptr [rax+8], 0
0x18000e80b  xor     edx, edx; dwFlags
0x18000e80d  lea     rcx, ?wrapper@?1??Instance@TlgHelper@@KAPEAV2@XZ@4V?$static_lazy@VTlgHelper@@@details@wil@@A; lpInitOnce
0x18000e814  call    cs:__imp_InitOnceBeginInitialize
0x18000e81a  test    eax, eax
0x18000e81c  jz      loc_18000E8C6
0x18000e822  cmp     [rsp+28h+arg_0], 0
0x18000e827  jz      loc_18000E8C6
0x18000e82d  lea     rbx, qword_18002F850
0x18000e834  mov     cs:qword_18002F858, 0
0x18000e83f  lea     rax, ??_7TlgHelper@@6B@; const TlgHelper::`vftable'
0x18000e846  mov     [rsp+28h+arg_8], rbx
0x18000e84b  mov     cs:qword_18002F850, rax
0x18000e852  mov     cs:byte_18002F860, 0
0x18000e859  mov     cs:dword_18002F864, 0
0x18000e863  lea     rax, ?__hInner@?1???0StaticHandle@TlgHelper@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TlgHelper::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e86a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_27248ce03d41213a4b11ef93405cd787_@@CA@XZ; void (__cdecl *)()
0x18000e871  mov     cs:CallbackContext, rax
0x18000e878  call    atexit
0x18000e87d  mov     rcx, cs:CallbackContext; CallbackContext
0x18000e884  mov     cs:qword_18002F858, rcx
0x18000e88b  mov     cs:byte_18002F860, 1
0x18000e892  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000e897  mov     rax, cs:qword_18002F850
0x18000e89e  mov     rcx, rbx
0x18000e8a1  mov     cs:dword_18002F864, 1
0x18000e8ab  mov     rax, [rax+8]
0x18000e8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8b4  mov     r8, rbx; lpContext
0x18000e8b7  lea     rcx, ?wrapper@?1??Instance@TlgHelper@@KAPEAV2@XZ@4V?$static_lazy@VTlgHelper@@@details@wil@@A; lpInitOnce
0x18000e8be  xor     edx, edx; dwFlags
0x18000e8c0  call    cs:__imp_InitOnceComplete
0x18000e8c6  mov     rax, [rsp+28h+arg_8]
0x18000e8cb  mov     rax, [rax+8]
0x18000e8cf  add     rsp, 20h
0x18000e8d3  pop     rbx
0x18000e8d4  retn
```
