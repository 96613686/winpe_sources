# _dynamic_initializer_for__InventoryCoreProvider__

- ea: `0x1800042a0`
- end: `0x1800043f7`
- name: `_dynamic_initializer_for__InventoryCoreProvider__`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a6c`
- `0x1800042a0`
- `0x180005e40`
- `0x1800061f0`
- `0x180006270`
- `0x180006ec4`
- `0x180011e88`
- `0x180011fa8`
- `0x180025c1c`
- `0x18002db94`
- `0x180030ee8`

## import_xrefs

- `ntdll!WinSqmIsOptedInEx` at `0x1800043a5`
- `ntdll!WinSqmIsOptedInEx` at `0x1800043a5`
- `RPCRT4!UuidCreate` at `0x1800042db`
- `RPCRT4!UuidCreate` at `0x1800042db`

## pseudocode

```c
int dynamic_initializer_for__InventoryCoreProvider__()
{
  _BYTE *v0; // rbx
  Windows::Compat::Shared::Telemetry::TelemetryProvider *v1; // rcx
  unsigned __int16 v2; // r8
  unsigned __int16 v3; // r8
  __int64 *v4; // rax
  char IsWin10TelemetryTypeAllowed; // al
  UUID v7; // [rsp+20h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-28h] BYREF

  v0 = operator new(0x90u);
  Uuid = 0;
  v0[130] = 65;
  UuidCreate(&Uuid);
  v7 = Uuid;
  v0[129] = 17;
  *((_QWORD *)v0 + 17) = 0x1300000000LL;
  memset_0(v0, 0, 0x81u);
  TLV::Base64Encode<129>(&v7, 12, v0);
  *((_WORD *)v0 + 8) = 46;
  Block = v0;
  TraceLoggingCorrelationVector::ToString((TraceLoggingCorrelationVector *)v0, &byte_1801559D8);
  Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(v1, 0);
  if ( IsWindowsVersionOrGreater(0xAu, 0, v2)
    || (`Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::AlreadyChecked
      ? (IsWin10TelemetryTypeAllowed = `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::IsOptedIn)
      : (!IsWindowsVersionOrGreater(0xAu, 0, v3)
       ? (IsWin10TelemetryTypeAllowed = (unsigned int)WinSqmIsOptedInEx(4) == 1)
       : (IsWin10TelemetryTypeAllowed = Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(2u)),
         `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::IsOptedIn = IsWin10TelemetryTypeAllowed,
         `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::AlreadyChecked = 1),
        IsWin10TelemetryTypeAllowed) )
  {
    if ( !byte_180155A5A )
    {
      TraceLoggingRegister_EventRegister_2U(CallbackContext);
      byte_180155A5A = 1;
    }
    v4 = (__int64 *)CallbackContext;
  }
  else
  {
    v4 = off_1801559B8;
  }
  qword_1801559C8 = (__int64)v4;
  return atexit(dynamic_atexit_destructor_for__InventoryCoreProvider__);
}

```

## disassembly

```asm
0x1800042a0  push    rbx
0x1800042a2  sub     rsp, 50h
0x1800042a6  mov     rax, cs:__security_cookie
0x1800042ad  xor     rax, rsp
0x1800042b0  mov     [rsp+58h+var_18], rax
0x1800042b5  mov     ecx, 90h; Size
0x1800042ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800042bf  mov     qword ptr [rsp+58h+Uuid.Data1], rax
0x1800042c4  lea     rcx, [rsp+58h+Uuid]; Uuid
0x1800042c9  xorps   xmm0, xmm0
0x1800042cc  mov     rbx, rax
0x1800042cf  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x1800042d4  mov     byte ptr [rax+82h], 41h ; 'A'
0x1800042db  call    cs:__imp_UuidCreate
0x1800042e1  movaps  xmm0, xmmword ptr [rsp+58h+Uuid.Data1]
0x1800042e6  mov     rax, 1300000000h
0x1800042f0  movdqa  [rsp+58h+var_38], xmm0
0x1800042f6  xor     edx, edx; Val
0x1800042f8  mov     byte ptr [rbx+81h], 11h
0x1800042ff  mov     r8d, 81h; Size
0x180004305  mov     rcx, rbx; void *
0x180004308  mov     [rbx+88h], rax
0x18000430f  call    memset_0
0x180004314  mov     r8, rbx
0x180004317  lea     rcx, [rsp+58h+var_38]
0x18000431c  mov     edx, 0Ch
0x180004321  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180004326  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18000432c  lea     rdx, byte_1801559D8; char *
0x180004333  mov     rcx, rbx; this
0x180004336  mov     cs:Block, rbx
0x18000433d  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x180004342  xor     edx, edx; bool
0x180004344  call    ?InitializeCoreProvider@TelemetryProvider@Telemetry@Shared@Compat@Windows@@IEAAX_N@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(bool)
0x180004349  xor     edx, edx; unsigned __int16
0x18000434b  lea     ebx, [rdx+0Ah]
0x18000434e  mov     ecx, ebx; unsigned __int16
0x180004350  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180004355  test    al, al
0x180004357  jz      short loc_18000437E
0x180004359  cmp     cs:byte_180155A5A, 0
0x180004360  jnz     short loc_180004375
0x180004362  mov     rcx, cs:CallbackContext; CallbackContext
0x180004369  call    TraceLoggingRegister_EventRegister_2U
0x18000436e  mov     cs:byte_180155A5A, 1
0x180004375  mov     rax, cs:CallbackContext
0x18000437c  jmp     short loc_1800043D1
0x18000437e  cmp     cs:?AlreadyChecked@?1??IsOptedIntoGeneral@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, 0; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral(bool)'::`2'::AlreadyChecked
0x180004385  jnz     short loc_1800043C0
0x180004387  xor     edx, edx; unsigned __int16
0x180004389  mov     ecx, ebx; unsigned __int16
0x18000438b  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180004390  test    al, al
0x180004392  jz      short loc_1800043A0
0x180004394  mov     ecx, 2; unsigned int
0x180004399  call    ?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)
0x18000439e  jmp     short loc_1800043B1
0x1800043a0  mov     ecx, 4
0x1800043a5  call    cs:__imp_WinSqmIsOptedInEx
0x1800043ab  cmp     eax, 1
0x1800043ae  setz    al
0x1800043b1  mov     cs:?IsOptedIn@?1??IsOptedIntoGeneral@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, al; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral(bool)'::`2'::IsOptedIn
0x1800043b7  mov     cs:?AlreadyChecked@?1??IsOptedIntoGeneral@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral(bool)'::`2'::AlreadyChecked
0x1800043be  jmp     short loc_1800043C6
0x1800043c0  mov     al, cs:?IsOptedIn@?1??IsOptedIntoGeneral@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral(bool)'::`2'::IsOptedIn
0x1800043c6  test    al, al
0x1800043c8  jnz     short loc_180004359
0x1800043ca  mov     rax, cs:off_1801559B8
0x1800043d1  lea     rcx, _dynamic_atexit_destructor_for__InventoryCoreProvider__; void (__cdecl *)()
0x1800043d8  mov     cs:qword_1801559C8, rax
0x1800043df  call    atexit
0x1800043e4  mov     rcx, [rsp+58h+var_18]
0x1800043e9  xor     rcx, rsp; StackCookie
0x1800043ec  call    __security_check_cookie
0x1800043f1  add     rsp, 50h
0x1800043f5  pop     rbx
0x1800043f6  retn
```
