# OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)

- ea: `0x180004b04`
- end: `0x180004d5f`
- name: `?LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `603`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800055f4`

## callees

- `0x180004b04`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180004d38`
- `KERNEL32!FreeLibrary` at `0x180004d38`
- `KERNEL32!LoadLibraryExW` at `0x180004b29`
- `KERNEL32!LoadLibraryExW` at `0x180004b29`
- `KERNEL32!GetProcAddress` at `0x180004b55`
- `KERNEL32!GetProcAddress` at `0x180004b79`
- `KERNEL32!GetProcAddress` at `0x180004b9d`
- `KERNEL32!GetProcAddress` at `0x180004bc1`
- `KERNEL32!GetProcAddress` at `0x180004be5`
- `KERNEL32!GetProcAddress` at `0x180004c09`
- `KERNEL32!GetProcAddress` at `0x180004c2d`
- `KERNEL32!GetProcAddress` at `0x180004c51`
- `KERNEL32!GetProcAddress` at `0x180004c75`
- `KERNEL32!GetProcAddress` at `0x180004c99`
- `KERNEL32!GetProcAddress` at `0x180004cb9`
- `KERNEL32!GetProcAddress` at `0x180004cd9`
- `KERNEL32!GetProcAddress` at `0x180004cf9`
- `KERNEL32!GetProcAddress` at `0x180004b55`
- `KERNEL32!GetProcAddress` at `0x180004b79`
- `KERNEL32!GetProcAddress` at `0x180004b9d`
- `KERNEL32!GetProcAddress` at `0x180004bc1`
- `KERNEL32!GetProcAddress` at `0x180004be5`
- `KERNEL32!GetProcAddress` at `0x180004c09`
- `KERNEL32!GetProcAddress` at `0x180004c2d`
- `KERNEL32!GetProcAddress` at `0x180004c51`
- `KERNEL32!GetProcAddress` at `0x180004c75`
- `KERNEL32!GetProcAddress` at `0x180004c99`
- `KERNEL32!GetProcAddress` at `0x180004cb9`
- `KERNEL32!GetProcAddress` at `0x180004cd9`
- `KERNEL32!GetProcAddress` at `0x180004cf9`

## string_xrefs

- `0x180004b1c`: `OneSettingsClient.dll`
- `0x180004b4b`: `OneSettingsCreateDownloadConfig`
- `0x180004b72`: `OneSettingsFreeDownloadConfig`
- `0x180004b96`: `OneSettingsSetConfigBoolProperty`
- `0x180004bba`: `OneSettingsSetConfigDwordProperty`
- `0x180004bde`: `OneSettingsSetConfigWideStringProperty`
- `0x180004c02`: `OneSettingsSetConfigHandleProperty`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  HMODULE Library; // rax
  __int64 result; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  HMODULE v17; // rcx

  if ( *((_DWORD *)this + 440) )
    goto LABEL_20;
  Library = LoadLibraryExW(L"OneSettingsClient.dll", 0, 0x800u);
  *((_QWORD *)this + 219) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "OneSettingsCreateDownloadConfig");
    *((_QWORD *)this + 221) = ProcAddress;
    if ( !ProcAddress )
      goto LABEL_19;
    v5 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsFreeDownloadConfig");
    *((_QWORD *)this + 222) = v5;
    if ( !v5 )
      goto LABEL_19;
    v6 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsSetConfigBoolProperty");
    *((_QWORD *)this + 223) = v6;
    if ( !v6 )
      goto LABEL_19;
    v7 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsSetConfigDwordProperty");
    *((_QWORD *)this + 224) = v7;
    if ( !v7 )
      goto LABEL_19;
    v8 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsSetConfigWideStringProperty");
    *((_QWORD *)this + 225) = v8;
    if ( !v8 )
      goto LABEL_19;
    v9 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsSetConfigHandleProperty");
    *((_QWORD *)this + 226) = v9;
    if ( !v9 )
      goto LABEL_19;
    v10 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsFreeDownloadResponse");
    *((_QWORD *)this + 227) = v10;
    if ( !v10 )
      goto LABEL_19;
    v11 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsGetResponseDwordProperty");
    *((_QWORD *)this + 228) = v11;
    if ( !v11 )
      goto LABEL_19;
    v12 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsGetResponseStringProperty");
    *((_QWORD *)this + 229) = v12;
    if ( !v12
      || (v13 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsGetResponseWideStringProperty"),
          (*((_QWORD *)this + 230) = v13) == 0)
      || (v14 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsStartDownloadSession"),
          (*((_QWORD *)this + 231) = v14) == 0)
      || (v15 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsEndDownloadSession"),
          (*((_QWORD *)this + 232) = v15) == 0) )
    {
LABEL_19:
      result = 2147942527LL;
      goto LABEL_4;
    }
    v16 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsDownloadEndpoint");
    *((_QWORD *)this + 233) = v16;
    if ( !v16 )
    {
      result = 2147942527LL;
      `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient'::`2'::Result = -2147024769;
      goto LABEL_21;
    }
LABEL_20:
    result = (unsigned int)`OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient'::`2'::Result;
LABEL_21:
    if ( (int)result >= 0 )
      goto LABEL_24;
    goto LABEL_22;
  }
  result = 2147942526LL;
LABEL_4:
  `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient'::`2'::Result = result;
LABEL_22:
  v17 = (HMODULE)*((_QWORD *)this + 219);
  if ( v17 )
  {
    FreeLibrary(v17);
    result = (unsigned int)`OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient'::`2'::Result;
    *((_QWORD *)this + 219) = 0;
  }
LABEL_24:
  *((_DWORD *)this + 440) = 1;
  return result;
}

```

## disassembly

```asm
0x180004b04  push    rbx
0x180004b06  sub     rsp, 20h
0x180004b0a  cmp     dword ptr [rcx+6E0h], 0
0x180004b11  mov     rbx, rcx
0x180004b14  jnz     loc_180004D22
0x180004b1a  xor     edx, edx; hFile
0x180004b1c  lea     rcx, aOnesettingscli; "OneSettingsClient.dll"
0x180004b23  mov     r8d, 800h; dwFlags
0x180004b29  call    cs:__imp_LoadLibraryExW
0x180004b2f  mov     [rbx+6D8h], rax
0x180004b36  test    rax, rax
0x180004b39  jnz     short loc_180004B4B
0x180004b3b  mov     eax, 8007007Eh
0x180004b40  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x180004b46  jmp     loc_180004D2C
0x180004b4b  lea     rdx, aOnesettingscre; "OneSettingsCreateDownloadConfig"
0x180004b52  mov     rcx, rax; hModule
0x180004b55  call    cs:__imp_GetProcAddress
0x180004b5b  mov     [rbx+6E8h], rax
0x180004b62  test    rax, rax
0x180004b65  jz      loc_180004D18
0x180004b6b  mov     rcx, [rbx+6D8h]; hModule
0x180004b72  lea     rdx, aOnesettingsfre_0; "OneSettingsFreeDownloadConfig"
0x180004b79  call    cs:__imp_GetProcAddress
0x180004b7f  mov     [rbx+6F0h], rax
0x180004b86  test    rax, rax
0x180004b89  jz      loc_180004D18
0x180004b8f  mov     rcx, [rbx+6D8h]; hModule
0x180004b96  lea     rdx, aOnesettingsset; "OneSettingsSetConfigBoolProperty"
0x180004b9d  call    cs:__imp_GetProcAddress
0x180004ba3  mov     [rbx+6F8h], rax
0x180004baa  test    rax, rax
0x180004bad  jz      loc_180004D18
0x180004bb3  mov     rcx, [rbx+6D8h]; hModule
0x180004bba  lea     rdx, aOnesettingsset_2; "OneSettingsSetConfigDwordProperty"
0x180004bc1  call    cs:__imp_GetProcAddress
0x180004bc7  mov     [rbx+700h], rax
0x180004bce  test    rax, rax
0x180004bd1  jz      loc_180004D18
0x180004bd7  mov     rcx, [rbx+6D8h]; hModule
0x180004bde  lea     rdx, aOnesettingsset_0; "OneSettingsSetConfigWideStringProperty"
0x180004be5  call    cs:__imp_GetProcAddress
0x180004beb  mov     [rbx+708h], rax
0x180004bf2  test    rax, rax
0x180004bf5  jz      loc_180004D18
0x180004bfb  mov     rcx, [rbx+6D8h]; hModule
0x180004c02  lea     rdx, aOnesettingsset_1; "OneSettingsSetConfigHandleProperty"
0x180004c09  call    cs:__imp_GetProcAddress
0x180004c0f  mov     [rbx+710h], rax
0x180004c16  test    rax, rax
0x180004c19  jz      loc_180004D18
0x180004c1f  mov     rcx, [rbx+6D8h]; hModule
0x180004c26  lea     rdx, aOnesettingsfre; "OneSettingsFreeDownloadResponse"
0x180004c2d  call    cs:__imp_GetProcAddress
0x180004c33  mov     [rbx+718h], rax
0x180004c3a  test    rax, rax
0x180004c3d  jz      loc_180004D18
0x180004c43  mov     rcx, [rbx+6D8h]; hModule
0x180004c4a  lea     rdx, aOnesettingsget; "OneSettingsGetResponseDwordProperty"
0x180004c51  call    cs:__imp_GetProcAddress
0x180004c57  mov     [rbx+720h], rax
0x180004c5e  test    rax, rax
0x180004c61  jz      loc_180004D18
0x180004c67  mov     rcx, [rbx+6D8h]; hModule
0x180004c6e  lea     rdx, aOnesettingsget_0; "OneSettingsGetResponseStringProperty"
0x180004c75  call    cs:__imp_GetProcAddress
0x180004c7b  mov     [rbx+728h], rax
0x180004c82  test    rax, rax
0x180004c85  jz      loc_180004D18
0x180004c8b  mov     rcx, [rbx+6D8h]; hModule
0x180004c92  lea     rdx, aOnesettingsget_1; "OneSettingsGetResponseWideStringPropert"...
0x180004c99  call    cs:__imp_GetProcAddress
0x180004c9f  mov     [rbx+730h], rax
0x180004ca6  test    rax, rax
0x180004ca9  jz      short loc_180004D18
0x180004cab  mov     rcx, [rbx+6D8h]; hModule
0x180004cb2  lea     rdx, aOnesettingssta; "OneSettingsStartDownloadSession"
0x180004cb9  call    cs:__imp_GetProcAddress
0x180004cbf  mov     [rbx+738h], rax
0x180004cc6  test    rax, rax
0x180004cc9  jz      short loc_180004D18
0x180004ccb  mov     rcx, [rbx+6D8h]; hModule
0x180004cd2  lea     rdx, aOnesettingsend; "OneSettingsEndDownloadSession"
0x180004cd9  call    cs:__imp_GetProcAddress
0x180004cdf  mov     [rbx+740h], rax
0x180004ce6  test    rax, rax
0x180004ce9  jz      short loc_180004D18
0x180004ceb  mov     rcx, [rbx+6D8h]; hModule
0x180004cf2  lea     rdx, aOnesettingsdow; "OneSettingsDownloadEndpoint"
0x180004cf9  call    cs:__imp_GetProcAddress
0x180004cff  mov     [rbx+748h], rax
0x180004d06  test    rax, rax
0x180004d09  jnz     short loc_180004D22
0x180004d0b  mov     eax, 8007007Fh
0x180004d10  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x180004d16  jmp     short loc_180004D28
0x180004d18  mov     eax, 8007007Fh
0x180004d1d  jmp     loc_180004B40
0x180004d22  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x180004d28  test    eax, eax
0x180004d2a  jns     short loc_180004D4F
0x180004d2c  mov     rcx, [rbx+6D8h]; hLibModule
0x180004d33  test    rcx, rcx
0x180004d36  jz      short loc_180004D4F
0x180004d38  call    cs:__imp_FreeLibrary
0x180004d3e  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x180004d44  mov     qword ptr [rbx+6D8h], 0
0x180004d4f  mov     dword ptr [rbx+6E0h], 1
0x180004d59  add     rsp, 20h
0x180004d5d  pop     rbx
0x180004d5e  retn
```
