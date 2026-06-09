# WwanRegistry_2::GetBaseKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x18004f8b0`
- end: `0x18004f94a`
- name: `?GetBaseKey@WwanRegistry_2@@CA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800505d8`
- `0x1800519f0`

## callees

- `0x180028858`
- `0x18004f8b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f911`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f909`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f909`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f936`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f936`

## pseudocode

```c
bool __fastcall WwanRegistry_2::GetBaseKey(PHKEY phkResult)
{
  HKEY v3; // rdi
  DWORD LastError; // ebx

  if ( !word_1801FF670
    && (int)Windows::Compat::Shared::Registry::GetPersistedLocation(
              &word_1801FF670,
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
  return RegOpenKeyExW(HKEY_LOCAL_MACHINE, &word_1801FF670, 0, 0x20019u, phkResult) == 0;
}

```

## disassembly

```asm
0x18004f8b0  push    rbx
0x18004f8b2  push    rbp
0x18004f8b3  push    rsi
0x18004f8b4  push    rdi
0x18004f8b5  sub     rsp, 38h
0x18004f8b9  xor     ebp, ebp
0x18004f8bb  mov     rsi, rcx
0x18004f8be  cmp     cs:word_1801FF670, bp
0x18004f8c5  jnz     short loc_18004F8F6
0x18004f8c7  lea     r9, aSoftwareMicros_55; "Software\\Microsoft\\Cellular\\Telemetr"...
0x18004f8ce  mov     dword ptr [rsp+58h+phkResult], 1; int
0x18004f8d6  lea     r8, aCellularteleme; "CellularTelemetryProperty"
0x18004f8dd  mov     edx, 104h; unsigned int
0x18004f8e2  lea     rcx, word_1801FF670; unsigned __int16 *
0x18004f8e9  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18004f8ee  test    eax, eax
0x18004f8f0  jns     short loc_18004F8F6
0x18004f8f2  xor     al, al
0x18004f8f4  jmp     short loc_18004F941
0x18004f8f6  mov     rdi, [rsi]
0x18004f8f9  test    rdi, rdi
0x18004f8fc  jz      short loc_18004F917
0x18004f8fe  call    cs:__imp_GetLastError
0x18004f904  mov     rcx, rdi; hKey
0x18004f907  mov     ebx, eax
0x18004f909  call    cs:__imp_RegCloseKey
0x18004f90f  mov     ecx, ebx; dwErrCode
0x18004f911  call    cs:__imp_SetLastError
0x18004f917  mov     r9d, 20019h; samDesired
0x18004f91d  mov     [rsi], rbp
0x18004f920  xor     r8d, r8d; ulOptions
0x18004f923  mov     [rsp+58h+phkResult], rsi; phkResult
0x18004f928  lea     rdx, word_1801FF670; lpSubKey
0x18004f92f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f936  call    cs:__imp_RegOpenKeyExW
0x18004f93c  test    eax, eax
0x18004f93e  setz    al
0x18004f941  add     rsp, 38h
0x18004f945  pop     rdi
0x18004f946  pop     rsi
0x18004f947  pop     rbp
0x18004f948  pop     rbx
0x18004f949  retn
```
