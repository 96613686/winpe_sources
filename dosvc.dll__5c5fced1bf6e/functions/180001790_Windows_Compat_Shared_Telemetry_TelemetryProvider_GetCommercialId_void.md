# Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)

- ea: `0x180001790`
- end: `0x1800018dd`
- name: `?GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ`
- size: `333`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002f50`

## callees

- `0x180001790`
- `0x1800018f0`
- `0x180001de0`
- `0x180005020`
- `0x180005b2c`
- `0x180007f38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001835`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001835`

## string_xrefs

- `0x180001812`: `CommercialId`

## pseudocode

```c
const unsigned __int16 *Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)
{
  __int64 v0; // rdx
  __int64 v1; // rdx
  __int64 v2; // rcx
  int PersistedLocation; // edi
  __int64 v4; // r8
  int ValueW; // eax
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // r9
  const unsigned __int16 *result; // rax
  DWORD pcbData[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF

  if ( `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::AlreadyRetrieved )
    return &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId;
  memset_0(SubKey, 0, 0x208u);
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                        SubKey,
                        v0,
                        L"DataCollectionGroupPolicy",
                        L"Software\\Policies\\Microsoft\\Windows\\DataCollection");
  if ( PersistedLocation < 0 )
  {
    Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(
      v2,
      v1,
      v4,
      L"Software\\Policies\\Microsoft\\Windows\\DataCollection");
  }
  else
  {
    pcbData[0] = 80;
    `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId = 0;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               SubKey,
               L"CommercialId",
               0x20000002u,
               0,
               &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId,
               pcbData);
    if ( ValueW )
    {
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      if ( ValueW == -2147024894 )
        StringCchCopyW(
          &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId,
          0x28u,
          &dword_18000D644);
    }
  }
  if ( !`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId )
  {
    Windows::Compat::Shared::Registry::GetPersistedLocation(
      SubKey,
      v6,
      L"Diagnostics_AllowTelemetry",
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection");
    v10 = SubKey;
    if ( PersistedLocation < 0 )
      v10 = (WCHAR *)L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection";
    Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(v8, v7, v9, v10);
  }
  result = &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId;
  `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::AlreadyRetrieved = 1;
  return result;
}

```

## disassembly

```asm
0x180001790  push    rbx
0x180001792  sub     rsp, 270h
0x180001799  mov     rax, cs:__security_cookie
0x1800017a0  xor     rax, rsp
0x1800017a3  mov     [rsp+278h+var_18], rax
0x1800017ab  cmp     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, 0; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x1800017b2  jnz     loc_1800018BD
0x1800017b8  xor     edx, edx; Val
0x1800017ba  mov     [rsp+278h+arg_0], rdi
0x1800017c2  mov     r8d, 208h; Size
0x1800017c8  lea     rcx, [rsp+278h+SubKey]; void *
0x1800017cd  call    memset_0
0x1800017d2  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800017d9  lea     r8, aDatacollection; "DataCollectionGroupPolicy"
0x1800017e0  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x1800017e5  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x1800017ea  lea     rbx, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x1800017f1  mov     edi, eax
0x1800017f3  test    eax, eax
0x1800017f5  js      short loc_180001866
0x1800017f7  xor     ecx, ecx
0x1800017f9  mov     [rsp+278h+var_238], 50h ; 'P'
0x180001801  lea     rax, [rsp+278h+var_238]
0x180001806  mov     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, cx; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18000180d  mov     [rsp+278h+pcbData], rax; pcbData
0x180001812  lea     r8, Value; "CommercialId"
0x180001819  mov     [rsp+278h+pvData], rbx; pvData
0x18000181e  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x180001823  mov     [rsp+278h+pdwType], rcx; pdwType
0x180001828  mov     r9d, 20000002h; dwFlags
0x18000182e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180001835  call    cs:__imp_RegGetValueW
0x18000183b  test    eax, eax
0x18000183d  jz      short loc_180001872
0x18000183f  jle     short loc_180001849
0x180001841  movzx   eax, ax
0x180001844  or      eax, 80070000h
0x180001849  cmp     eax, 80070002h
0x18000184e  jnz     short loc_180001872
0x180001850  lea     r8, dword_18000D644; unsigned __int16 *
0x180001857  mov     edx, 28h ; '('; unsigned __int64
0x18000185c  mov     rcx, rbx; unsigned __int16 *
0x18000185f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001864  jmp     short loc_180001872
0x180001866  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18000186d  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x180001872  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, 0; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18000187a  jnz     short loc_1800018A9
0x18000187c  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001883  lea     r8, aDiagnosticsAll; "Diagnostics_AllowTelemetry"
0x18000188a  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18000188f  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180001894  lea     r9, [rsp+278h+SubKey]
0x180001899  test    edi, edi
0x18000189b  jns     short loc_1800018A4
0x18000189d  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800018a4  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x1800018a9  mov     rdi, [rsp+278h+arg_0]
0x1800018b1  mov     rax, rbx
0x1800018b4  mov     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x1800018bb  jmp     short loc_1800018C4
0x1800018bd  lea     rax, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x1800018c4  mov     rcx, [rsp+278h+var_18]
0x1800018cc  xor     rcx, rsp; StackCookie
0x1800018cf  call    __security_check_cookie
0x1800018d4  add     rsp, 270h
0x1800018db  pop     rbx
0x1800018dc  retn
```
