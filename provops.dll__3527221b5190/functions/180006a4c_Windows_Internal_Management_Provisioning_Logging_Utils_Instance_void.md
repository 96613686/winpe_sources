# Windows::Internal::Management::Provisioning::Logging::Utils::Instance(void)

- ea: `0x180006a4c`
- end: `0x180006b1c`
- name: `?Instance@Utils@Logging@Provisioning@Management@Internal@Windows@@KAPEAV123456@XZ`
- size: `208`
- prototype: `struct Windows::Internal::Management::Provisioning::Logging::Utils *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005ad0`

## callees

- `0x1800034f4`
- `0x180006a4c`
- `0x180006f50`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006a74`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006a74`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006b0b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006b0b`

## pseudocode

```c
struct Windows::Internal::Management::Provisioning::Logging::Utils *Windows::Internal::Management::Provisioning::Logging::Utils::Instance(
        void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(
         &`Windows::Internal::Management::Provisioning::Logging::Utils::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_18004ABE0 = 0;
    qword_18004ABD8 = (__int64)&Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::`vftable';
    v2 = &qword_18004ABD8;
    byte_18004ABE8 = 0;
    dword_18004ABEC = 0;
    atexit(_lambda_be0b5ea3fa2a9eec32053e25886e5d42_::_lambda_invoker_cdecl_);
    qword_18004ABE0 = (__int64)Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    byte_18004ABE8 = 0;
    dword_18004ABEC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004ABD8 + 8))(&qword_18004ABD8);
    InitOnceComplete(
      &`Windows::Internal::Management::Provisioning::Logging::Utils::Instance'::`2'::wrapper,
      0,
      &qword_18004ABD8);
  }
  return (struct Windows::Internal::Management::Provisioning::Logging::Utils *)v2;
}

```

## disassembly

```asm
0x180006a4c  mov     rax, rsp
0x180006a4f  push    rbx
0x180006a50  sub     rsp, 20h
0x180006a54  lea     r9, [rax+10h]; lpContext
0x180006a58  mov     qword ptr [rax+10h], 0
0x180006a60  lea     r8, [rax+8]; fPending
0x180006a64  mov     dword ptr [rax+8], 0
0x180006a6b  xor     edx, edx; dwFlags
0x180006a6d  lea     rcx, ?wrapper@?1??Instance@Utils@Logging@Provisioning@Management@Internal@Windows@@KAPEAV234567@XZ@4V?$static_lazy@VUtils@Logging@Provisioning@Management@Internal@Windows@@@details@wil@@A; lpInitOnce
0x180006a74  call    cs:__imp_InitOnceBeginInitialize
0x180006a7a  test    eax, eax
0x180006a7c  jz      loc_180006B11
0x180006a82  cmp     [rsp+28h+arg_0], 0
0x180006a87  jz      loc_180006B11
0x180006a8d  lea     rax, ??_7ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::`vftable'
0x180006a94  mov     cs:qword_18004ABE0, 0
0x180006a9f  lea     rbx, qword_18004ABD8
0x180006aa6  mov     cs:qword_18004ABD8, rax
0x180006aad  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_be0b5ea3fa2a9eec32053e25886e5d42_@@CA@XZ; void (__cdecl *)()
0x180006ab4  mov     [rsp+28h+arg_8], rbx
0x180006ab9  mov     cs:byte_18004ABE8, 0
0x180006ac0  mov     cs:dword_18004ABEC, 0
0x180006aca  call    atexit
0x180006acf  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180006ad4  mov     cs:qword_18004ABE0, rax
0x180006adb  mov     rcx, rbx
0x180006ade  mov     rax, cs:qword_18004ABD8
0x180006ae5  mov     cs:byte_18004ABE8, 0
0x180006aec  mov     cs:dword_18004ABEC, 1
0x180006af6  mov     rax, [rax+8]
0x180006afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aff  mov     r8, rbx; lpContext
0x180006b02  lea     rcx, ?wrapper@?1??Instance@Utils@Logging@Provisioning@Management@Internal@Windows@@KAPEAV234567@XZ@4V?$static_lazy@VUtils@Logging@Provisioning@Management@Internal@Windows@@@details@wil@@A; lpInitOnce
0x180006b09  xor     edx, edx; dwFlags
0x180006b0b  call    cs:__imp_InitOnceComplete
0x180006b11  mov     rax, [rsp+28h+arg_8]
0x180006b16  add     rsp, 20h
0x180006b1a  pop     rbx
0x180006b1b  retn
```
