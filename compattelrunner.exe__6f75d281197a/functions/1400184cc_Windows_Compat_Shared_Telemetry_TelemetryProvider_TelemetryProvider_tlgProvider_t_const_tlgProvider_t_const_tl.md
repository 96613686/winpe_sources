# Windows::Compat::Shared::Telemetry::TelemetryProvider::TelemetryProvider(_tlgProvider_t const *,_tlgProvider_t const *,_tlgProvider_t const *,_tlgProvider_t const *)

- ea: `0x1400184cc`
- end: `0x14001871e`
- name: `??0TelemetryProvider@Telemetry@Shared@Compat@Windows@@QEAA@PEBU_tlgProvider_t@@000@Z`
- size: `594`
- prototype: `__int64 __fastcall(Windows::Compat::Shared::Telemetry::TelemetryProvider *__hidden this, const struct _tlgProvider_t *, const struct _tlgProvider_t *, const struct _tlgProvider_t *, const struct _tlgProvider_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400017f0`

## callees

- `0x14000145c`
- `0x140001e90`
- `0x1400184cc`
- `0x140018724`
- `0x140018c98`
- `0x140018db8`
- `0x140018e74`

## import_xrefs

- `ntdll!WinSqmIsOptedInEx` at `0x1400185c7`
- `ntdll!WinSqmIsOptedInEx` at `0x1400186de`
- `ntdll!WinSqmIsOptedInEx` at `0x1400185c7`
- `ntdll!WinSqmIsOptedInEx` at `0x1400186de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001863d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001863d`

## string_xrefs

- `0x14001860b`: `CommercialDataOptIn`

## pseudocode

```c
PVOID *__fastcall Windows::Compat::Shared::Telemetry::TelemetryProvider::TelemetryProvider(
        Windows::Compat::Shared::Telemetry::TelemetryProvider *this,
        const struct _tlgProvider_t *a2,
        const struct _tlgProvider_t *a3,
        const struct _tlgProvider_t *a4)
{
  TraceLoggingCorrelationVector *v4; // rax
  PVOID v5; // rax
  char v6; // al
  PVOID v7; // rax
  char IsWin10TelemetryTypeAllowed; // al
  const struct _tlgProvider_t *pcbData; // [rsp+60h] [rbp+18h] BYREF
  TraceLoggingCorrelationVector *pvData; // [rsp+68h] [rbp+20h] BYREF

  pvData = a4;
  pcbData = a3;
  dword_1400C8DA9 = 0x1000000;
  InventoryCoreProvider = &qword_1400C8060;
  xmmword_1400C8D10 = 0;
  CallbackContext = &qword_1400C8028;
  qword_1400C8D20 = 0;
  qword_1400C8D00 = (__int64)&qword_1400C8098;
  byte_1400C8D28 = 0;
  qword_1400C8D08 = (__int64)&qword_1400C7FF0;
  pvData = (TraceLoggingCorrelationVector *)operator new(0x90u);
  v4 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(pvData);
  qword_1400C8D20 = (__int64)v4;
  if ( v4 )
    TraceLoggingCorrelationVector::ToString(v4, &byte_1400C8D28);
  if ( !HIBYTE(dword_1400C8DA9) )
    goto LABEL_23;
  if ( !IsWindows10OrGreater() )
  {
    if ( `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked )
    {
      v6 = `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn;
    }
    else
    {
      v6 = IsWindows10OrGreater()
         ? Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(1u)
         : (unsigned int)WinSqmIsOptedInEx(4) == 1;
      `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn = v6;
      `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked = 1;
    }
    if ( !v6 )
    {
      if ( !`Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial'::`2'::AlreadyChecked )
      {
        if ( !IsWindows10OrGreater() )
        {
          LODWORD(pvData) = 0;
          LODWORD(pcbData) = 4;
          RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
            L"CommercialDataOptIn",
            0x20000018u,
            0,
            &pvData,
            (LPDWORD)&pcbData);
          `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial'::`2'::IsOptedIn = (_DWORD)pvData != 0;
        }
        `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial'::`2'::AlreadyChecked = 1;
      }
      if ( `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial'::`2'::IsOptedIn )
      {
        if ( !(_BYTE)dword_1400C8DA9 )
        {
          TraceLoggingRegister_EventRegister_EventSetInformation(InventoryCoreProvider);
          LOBYTE(dword_1400C8DA9) = 1;
        }
        v5 = InventoryCoreProvider;
        goto LABEL_24;
      }
LABEL_23:
      v5 = (PVOID)qword_1400C8D08;
      goto LABEL_24;
    }
  }
  if ( !BYTE1(dword_1400C8DA9) )
  {
    TraceLoggingRegister_EventRegister_EventSetInformation(CallbackContext);
    BYTE1(dword_1400C8DA9) = 1;
  }
  v5 = CallbackContext;
LABEL_24:
  *(_QWORD *)&xmmword_1400C8D10 = v5;
  if ( IsWindows10OrGreater()
    || (`Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::AlreadyChecked
      ? (IsWin10TelemetryTypeAllowed = `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::IsOptedIn)
      : (!IsWindows10OrGreater()
       ? (IsWin10TelemetryTypeAllowed = (unsigned int)WinSqmIsOptedInEx(4) == 1)
       : (IsWin10TelemetryTypeAllowed = Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(2u)),
         `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::IsOptedIn = IsWin10TelemetryTypeAllowed,
         `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::AlreadyChecked = 1),
        IsWin10TelemetryTypeAllowed) )
  {
    if ( !BYTE1(dword_1400C8DA9) )
    {
      TraceLoggingRegister_EventRegister_EventSetInformation(CallbackContext);
      BYTE1(dword_1400C8DA9) = 1;
    }
    v7 = CallbackContext;
  }
  else
  {
    v7 = (PVOID)qword_1400C8D08;
  }
  *((_QWORD *)&xmmword_1400C8D10 + 1) = v7;
  return &InventoryCoreProvider;
}

```

## disassembly

```asm
0x1400184cc  mov     [rsp+arg_18], r9
0x1400184d1  mov     [rsp+arg_10], r8
0x1400184d6  push    rbx
0x1400184d7  sub     rsp, 40h
0x1400184db  lea     rax, qword_1400C8060
0x1400184e2  mov     cs:dword_1400C8DA9, 1000000h
0x1400184ec  mov     cs:?InventoryCoreProvider@@3VTelemetryProvider@Telemetry@Shared@Compat@Windows@@A, rax; Windows::Compat::Shared::Telemetry::TelemetryProvider InventoryCoreProvider
0x1400184f3  xorps   xmm0, xmm0
0x1400184f6  lea     rax, qword_1400C8028
0x1400184fd  movdqa  cs:xmmword_1400C8D10, xmm0
0x140018505  mov     cs:CallbackContext, rax
0x14001850c  xor     ebx, ebx
0x14001850e  lea     rax, qword_1400C8098
0x140018515  mov     cs:qword_1400C8D20, rbx
0x14001851c  mov     cs:qword_1400C8D00, rax
0x140018523  mov     ecx, 90h; Size
0x140018528  lea     rax, qword_1400C7FF0
0x14001852f  mov     cs:byte_1400C8D28, bl
0x140018535  mov     cs:qword_1400C8D08, rax
0x14001853c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140018541  mov     rcx, rax; this
0x140018544  mov     [rsp+48h+arg_18], rax
0x140018549  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x14001854e  mov     cs:qword_1400C8D20, rax
0x140018555  test    rax, rax
0x140018558  jz      short loc_140018569
0x14001855a  lea     rdx, byte_1400C8D28; char *
0x140018561  mov     rcx, rax; this
0x140018564  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x140018569  cmp     byte ptr cs:dword_1400C8DA9+3, bl
0x14001856f  jz      loc_140018681
0x140018575  call    ?IsWindows10OrGreater@@YA_NXZ; IsWindows10OrGreater(void)
0x14001857a  test    al, al
0x14001857c  jz      short loc_1400185A5
0x14001857e  cmp     byte ptr cs:dword_1400C8DA9+1, bl
0x140018584  jnz     short loc_140018599
0x140018586  mov     rcx, cs:CallbackContext; CallbackContext
0x14001858d  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x140018592  mov     byte ptr cs:dword_1400C8DA9+1, 1
0x140018599  mov     rax, cs:CallbackContext
0x1400185a0  jmp     loc_140018688
0x1400185a5  cmp     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, bl; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x1400185ab  jnz     short loc_1400185E2
0x1400185ad  call    ?IsWindows10OrGreater@@YA_NXZ; IsWindows10OrGreater(void)
0x1400185b2  test    al, al
0x1400185b4  jz      short loc_1400185C2
0x1400185b6  mov     ecx, 1; unsigned int
0x1400185bb  call    ?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)
0x1400185c0  jmp     short loc_1400185D3
0x1400185c2  mov     ecx, 4
0x1400185c7  call    cs:__imp_WinSqmIsOptedInEx
0x1400185cd  cmp     eax, 1
0x1400185d0  setz    al
0x1400185d3  mov     cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, al; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x1400185d9  mov     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x1400185e0  jmp     short loc_1400185E8
0x1400185e2  mov     al, cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x1400185e8  test    al, al
0x1400185ea  jnz     short loc_14001857E
0x1400185ec  cmp     cs:?AlreadyChecked@?1??IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, bl; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)'::`2'::AlreadyChecked
0x1400185f2  jnz     short loc_140018655
0x1400185f4  call    ?IsWindows10OrGreater@@YA_NXZ; IsWindows10OrGreater(void)
0x1400185f9  test    al, al
0x1400185fb  jnz     short loc_14001864E
0x1400185fd  lea     rax, [rsp+48h+arg_10]
0x140018602  mov     dword ptr [rsp+48h+arg_18], ebx
0x140018606  mov     [rsp+48h+pcbData], rax; pcbData
0x14001860b  lea     r8, aCommercialdata; "CommercialDataOptIn"
0x140018612  lea     rax, [rsp+48h+arg_18]
0x140018617  mov     dword ptr [rsp+48h+arg_10], 4
0x14001861f  mov     [rsp+48h+pvData], rax; pvData
0x140018624  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001862b  mov     r9d, 20000018h; dwFlags
0x140018631  mov     [rsp+48h+pdwType], rbx; pdwType
0x140018636  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001863d  call    cs:__imp_RegGetValueW
0x140018643  cmp     dword ptr [rsp+48h+arg_18], ebx
0x140018647  setnz   cs:?IsOptedIn@?1??IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)'::`2'::IsOptedIn
0x14001864e  mov     cs:?AlreadyChecked@?1??IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)'::`2'::AlreadyChecked
0x140018655  cmp     cs:?IsOptedIn@?1??IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, bl; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)'::`2'::IsOptedIn
0x14001865b  jz      short loc_140018681
0x14001865d  cmp     byte ptr cs:dword_1400C8DA9, bl
0x140018663  jnz     short loc_140018678
0x140018665  mov     rcx, cs:?InventoryCoreProvider@@3VTelemetryProvider@Telemetry@Shared@Compat@Windows@@A; CallbackContext
0x14001866c  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x140018671  mov     byte ptr cs:dword_1400C8DA9, 1
0x140018678  mov     rax, cs:?InventoryCoreProvider@@3VTelemetryProvider@Telemetry@Shared@Compat@Windows@@A; Windows::Compat::Shared::Telemetry::TelemetryProvider InventoryCoreProvider
0x14001867f  jmp     short loc_140018688
0x140018681  mov     rax, cs:qword_1400C8D08
0x140018688  mov     qword ptr cs:xmmword_1400C8D10, rax
0x14001868f  call    ?IsWindows10OrGreater@@YA_NXZ; IsWindows10OrGreater(void)
0x140018694  test    al, al
0x140018696  jz      short loc_1400186BC
0x140018698  cmp     byte ptr cs:dword_1400C8DA9+1, bl
0x14001869e  jnz     short loc_1400186B3
0x1400186a0  mov     rcx, cs:CallbackContext; CallbackContext
0x1400186a7  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x1400186ac  mov     byte ptr cs:dword_1400C8DA9+1, 1
0x1400186b3  mov     rax, cs:CallbackContext
0x1400186ba  jmp     short loc_14001870A
0x1400186bc  cmp     cs:?AlreadyChecked@?1??IsOptedIntoGeneral@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, bl; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral(bool)'::`2'::AlreadyChecked
0x1400186c2  jnz     short loc_1400186F9
0x1400186c4  call    ?IsWindows10OrGreater@@YA_NXZ; IsWindows10OrGreater(void)
0x1400186c9  test    al, al
0x1400186cb  jz      short loc_1400186D9
0x1400186cd  mov     ecx, 2; unsigned int
0x1400186d2  call    ?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)
0x1400186d7  jmp     short loc_1400186EA
0x1400186d9  mov     ecx, 4
0x1400186de  call    cs:__imp_WinSqmIsOptedInEx
0x1400186e4  cmp     eax, 1
0x1400186e7  setz    al
0x1400186ea  mov     cs:?IsOptedIn@?1??IsOptedIntoGeneral@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, al; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral(bool)'::`2'::IsOptedIn
0x1400186f0  mov     cs:?AlreadyChecked@?1??IsOptedIntoGeneral@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral(bool)'::`2'::AlreadyChecked
0x1400186f7  jmp     short loc_1400186FF
0x1400186f9  mov     al, cs:?IsOptedIn@?1??IsOptedIntoGeneral@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral(bool)'::`2'::IsOptedIn
0x1400186ff  test    al, al
0x140018701  jnz     short loc_140018698
0x140018703  mov     rax, cs:qword_1400C8D08
0x14001870a  mov     qword ptr cs:xmmword_1400C8D10+8, rax
0x140018711  lea     rax, ?InventoryCoreProvider@@3VTelemetryProvider@Telemetry@Shared@Compat@Windows@@A; Windows::Compat::Shared::Telemetry::TelemetryProvider InventoryCoreProvider
0x140018718  add     rsp, 40h
0x14001871c  pop     rbx
0x14001871d  retn
```
