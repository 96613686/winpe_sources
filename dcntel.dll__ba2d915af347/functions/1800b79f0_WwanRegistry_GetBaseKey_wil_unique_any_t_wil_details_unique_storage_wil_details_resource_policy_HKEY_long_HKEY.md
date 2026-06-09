# WwanRegistry::GetBaseKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x1800b79f0`
- end: `0x1800b7a8a`
- name: `?GetBaseKey@WwanRegistry@@CA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b8468`
- `0x1800b8a4c`

## callees

- `0x180028858`
- `0x1800b79f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7a51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7a3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7a49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7a49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7a76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7a76`

## pseudocode

```c
bool __fastcall WwanRegistry::GetBaseKey(PHKEY phkResult)
{
  HKEY v3; // rdi
  DWORD LastError; // ebx

  if ( !word_180200040
    && (int)Windows::Compat::Shared::Registry::GetPersistedLocation(
              &word_180200040,
              0x104u,
              L"CellularTelemetryProperty",
              L"Software\\Microsoft\\Cellular\\TelemetryProperty",
              1) < 0 )
  {
    return 0;
  }
  v3 = *phkResult;
  if ( *phkResult )
  {
    LastError = GetLastError();
    RegCloseKey(v3);
    SetLastError(LastError);
  }
  *phkResult = 0;
  return RegOpenKeyExW(HKEY_LOCAL_MACHINE, &word_180200040, 0, 0x20019u, phkResult) == 0;
}

```

## disassembly

```asm
0x1800b79f0  push    rbx
0x1800b79f2  push    rbp
0x1800b79f3  push    rsi
0x1800b79f4  push    rdi
0x1800b79f5  sub     rsp, 38h
0x1800b79f9  xor     ebp, ebp
0x1800b79fb  mov     rsi, rcx
0x1800b79fe  cmp     cs:word_180200040, bp
0x1800b7a05  jnz     short loc_1800B7A36
0x1800b7a07  lea     r9, aSoftwareMicros_55; "Software\\Microsoft\\Cellular\\Telemetr"...
0x1800b7a0e  mov     dword ptr [rsp+58h+phkResult], 1; int
0x1800b7a16  lea     r8, aCellularteleme; "CellularTelemetryProperty"
0x1800b7a1d  mov     edx, 104h; unsigned int
0x1800b7a22  lea     rcx, word_180200040; unsigned __int16 *
0x1800b7a29  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x1800b7a2e  test    eax, eax
0x1800b7a30  jns     short loc_1800B7A36
0x1800b7a32  xor     al, al
0x1800b7a34  jmp     short loc_1800B7A81
0x1800b7a36  mov     rdi, [rsi]
0x1800b7a39  test    rdi, rdi
0x1800b7a3c  jz      short loc_1800B7A57
0x1800b7a3e  call    cs:__imp_GetLastError
0x1800b7a44  mov     rcx, rdi; hKey
0x1800b7a47  mov     ebx, eax
0x1800b7a49  call    cs:__imp_RegCloseKey
0x1800b7a4f  mov     ecx, ebx; dwErrCode
0x1800b7a51  call    cs:__imp_SetLastError
0x1800b7a57  mov     r9d, 20019h; samDesired
0x1800b7a5d  mov     [rsi], rbp
0x1800b7a60  xor     r8d, r8d; ulOptions
0x1800b7a63  mov     [rsp+58h+phkResult], rsi; phkResult
0x1800b7a68  lea     rdx, word_180200040; lpSubKey
0x1800b7a6f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b7a76  call    cs:__imp_RegOpenKeyExW
0x1800b7a7c  test    eax, eax
0x1800b7a7e  setz    al
0x1800b7a81  add     rsp, 38h
0x1800b7a85  pop     rdi
0x1800b7a86  pop     rsi
0x1800b7a87  pop     rbp
0x1800b7a88  pop     rbx
0x1800b7a89  retn
```
