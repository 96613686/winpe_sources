# Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)

- ea: `0x180001de0`
- end: `0x180001e6e`
- name: `?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z`
- size: `142`
- prototype: `int __fastcall(__int64, __int64, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001790`

## callees

- `0x180001de0`
- `0x180007f38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001e31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001e31`

## string_xrefs

- `0x180001e0f`: `CommercialId`

## pseudocode

```c
int __fastcall Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4)
{
  int result; // eax
  bool v5; // sf
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF
  int v7; // [rsp+64h] [rbp+1Ch]

  v7 = HIDWORD(a3);
  pcbData = 80;
  `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId = 0;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             a4,
             L"CommercialId",
             0x20000002u,
             0,
             &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId,
             &pcbData);
  v5 = result < 0;
  if ( !result )
    return 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result < 0;
  }
  if ( !v5 )
    return 0;
  if ( result == -2147024894 )
    return StringCchCopyW(
             &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId,
             0x28u,
             &dword_18000D644);
  return result;
}

```

## disassembly

```asm
0x180001de0  mov     qword ptr [rsp+arg_10], r8
0x180001de5  push    rbx
0x180001de6  sub     rsp, 40h
0x180001dea  xor     eax, eax
0x180001dec  mov     [rsp+48h+arg_10], 50h ; 'P'
0x180001df4  mov     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, ax; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180001dfb  lea     rbx, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180001e02  lea     rax, [rsp+48h+arg_10]
0x180001e07  mov     rdx, r9; lpSubKey
0x180001e0a  mov     [rsp+48h+pcbData], rax; pcbData
0x180001e0f  lea     r8, Value; "CommercialId"
0x180001e16  mov     [rsp+48h+pvData], rbx; pvData
0x180001e1b  mov     r9d, 20000002h; dwFlags
0x180001e21  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180001e28  mov     [rsp+48h+pdwType], 0; pdwType
0x180001e31  call    cs:__imp_RegGetValueW
0x180001e37  test    eax, eax
0x180001e39  jz      short loc_180001E66
0x180001e3b  jle     short loc_180001E47
0x180001e3d  movzx   eax, ax
0x180001e40  or      eax, 80070000h
0x180001e45  test    eax, eax
0x180001e47  jns     short loc_180001E66
0x180001e49  cmp     eax, 80070002h
0x180001e4e  jnz     short loc_180001E68
0x180001e50  lea     r8, dword_18000D644; unsigned __int16 *
0x180001e57  mov     edx, 28h ; '('; unsigned __int64
0x180001e5c  mov     rcx, rbx; unsigned __int16 *
0x180001e5f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001e64  jmp     short loc_180001E68
0x180001e66  xor     eax, eax
0x180001e68  add     rsp, 40h
0x180001e6c  pop     rbx
0x180001e6d  retn
```
