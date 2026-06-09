# Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)

- ea: `0x18000d28c`
- end: `0x18000d35e`
- name: `?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ce20`

## callees

- `0x18000d28c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d2db`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d2db`

## string_xrefs

- `0x18000d2bc`: `CommercialId`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4)
{
  __int16 *v4; // rbx
  LSTATUS ValueW; // eax
  signed int v6; // ecx
  __int64 result; // rax
  __int64 v8; // rax
  int *v9; // rcx
  __int64 v10; // rdx
  __int16 *v11; // rcx
  DWORD v12; // [rsp+60h] [rbp+18h] BYREF
  int v13; // [rsp+64h] [rbp+1Ch]

  v13 = HIDWORD(a3);
  v12 = 80;
  v4 = &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId;
  `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             a4,
             L"CommercialId",
             0x20000002u,
             0,
             &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId,
             &v12);
  v6 = ValueW;
  if ( !ValueW )
    return 0;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  result = 0;
  if ( v6 < 0 )
    result = (unsigned int)v6;
  if ( (_DWORD)result == -2147024894 )
  {
    v8 = 2147483646;
    v9 = &dword_180011374;
    v10 = 40;
    do
    {
      if ( !v8 )
        break;
      if ( !*(_WORD *)v9 )
        break;
      *v4 = *(_WORD *)v9;
      v9 = (int *)((char *)v9 + 2);
      ++v4;
      --v8;
      --v10;
    }
    while ( v10 );
    v11 = v4 - 1;
    if ( v10 )
      v11 = v4;
    result = v10 == 0 ? 0x8007007A : 0;
    *v11 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000d28c  mov     r11, rsp
0x18000d28f  mov     [r11+8], rbx
0x18000d293  mov     [r11+18h], r8
0x18000d297  push    rdi
0x18000d298  sub     rsp, 40h
0x18000d29c  lea     rax, [r11+18h]
0x18000d2a0  mov     [rsp+48h+arg_10], 50h ; 'P'
0x18000d2a8  mov     [r11-18h], rax
0x18000d2ac  lea     rbx, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18000d2b3  mov     rdx, r9; lpSubKey
0x18000d2b6  mov     [r11-20h], rbx
0x18000d2ba  xor     edi, edi
0x18000d2bc  lea     r8, Value; "CommercialId"
0x18000d2c3  mov     r9d, 20000002h; dwFlags
0x18000d2c9  mov     [r11-28h], rdi
0x18000d2cd  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000d2d4  mov     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, di; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18000d2db  call    cs:__imp_RegGetValueW
0x18000d2e1  mov     ecx, eax
0x18000d2e3  test    eax, eax
0x18000d2e5  jz      short loc_18000D351
0x18000d2e7  jle     short loc_18000D2F2
0x18000d2e9  movzx   ecx, ax
0x18000d2ec  or      ecx, 80070000h
0x18000d2f2  test    ecx, ecx
0x18000d2f4  mov     eax, edi
0x18000d2f6  cmovs   eax, ecx
0x18000d2f9  cmp     eax, 80070002h
0x18000d2fe  jnz     short loc_18000D353
0x18000d300  mov     eax, 7FFFFFFEh
0x18000d305  lea     rcx, dword_180011374
0x18000d30c  mov     edx, 28h ; '('
0x18000d311  test    rax, rax
0x18000d314  jz      short loc_18000D335
0x18000d316  movzx   r8d, word ptr [rcx]
0x18000d31a  test    r8w, r8w
0x18000d31e  jz      short loc_18000D335
0x18000d320  mov     [rbx], r8w
0x18000d324  add     rcx, 2
0x18000d328  add     rbx, 2
0x18000d32c  dec     rax
0x18000d32f  sub     rdx, 1
0x18000d333  jnz     short loc_18000D311
0x18000d335  test    rdx, rdx
0x18000d338  lea     rcx, [rbx-2]
0x18000d33c  cmovnz  rcx, rbx
0x18000d340  neg     rdx
0x18000d343  sbb     eax, eax
0x18000d345  not     eax
0x18000d347  and     eax, 8007007Ah
0x18000d34c  mov     [rcx], di
0x18000d34f  jmp     short loc_18000D353
0x18000d351  mov     eax, edi
0x18000d353  mov     rbx, [rsp+48h+arg_0]
0x18000d358  add     rsp, 40h
0x18000d35c  pop     rdi
0x18000d35d  retn
```
