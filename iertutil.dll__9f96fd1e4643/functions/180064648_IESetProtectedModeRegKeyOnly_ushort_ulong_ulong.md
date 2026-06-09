# IESetProtectedModeRegKeyOnly(ushort *,ulong,ulong)

- ea: `0x180064648`
- end: `0x1800647ba`
- name: `?IESetProtectedModeRegKeyOnly@@YAJPEAGKK@Z`
- size: `370`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800644cc`

## callees

- `0x180018410`
- `0x180044474`
- `0x18005ee90`
- `0x18005ef00`
- `0x180064648`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064790`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064788`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064788`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064683`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064683`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800647a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800647a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800646c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800646c8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800646fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800646fb`

## pseudocode

```c
__int64 __fastcall IESetProtectedModeRegKeyOnly(LPCWSTR lpSubKey, int a2, int a3)
{
  LSTATUS v6; // eax
  int v7; // ebx
  enum _SE_OBJECT_TYPE v8; // edx
  unsigned int v9; // edx
  char Bool; // al
  signed int LastError; // eax
  PSID Sid; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+40h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 8u, 0xE0006u, &hKey)
    || (v6 = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0, 8u, 0xE0006u, 0, &hKey, 0), (v7 = v6) == 0) )
  {
    Sid = 0;
    if ( !ConvertStringSidToSidW(L"LW", &Sid) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_20;
    }
    if ( a2 != 2 || (v7 = SetHandleIntegrityLevel(hKey, v8, Sid, 0, 0), v7 >= 0) )
    {
      v7 = SetWindowsHandleAccessTrustedAC(hKey, 0x400u, 0);
      switch ( a3 )
      {
        case 1:
          v9 = 131097;
          break;
        case 2:
          v9 = 131103;
          break;
        case 4:
          Bool = IEConfiguration_GetBool(268435519);
          v9 = 131103;
          if ( !Bool )
            v9 = 983103;
          break;
        default:
          goto LABEL_16;
      }
      v7 = SetRegistryKeyAppContainer(hKey, v9);
    }
LABEL_16:
    if ( Sid )
      LocalFree(Sid);
LABEL_20:
    RegCloseKey(hKey);
    return (unsigned int)v7;
  }
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180064648  push    rbp
0x18006464a  push    rbx
0x18006464b  push    rsi
0x18006464c  push    rdi
0x18006464d  mov     rbp, rsp
0x180064650  sub     rsp, 68h
0x180064654  mov     esi, edx
0x180064656  mov     [rbp+hKey], 0
0x18006465e  mov     rdx, rcx; lpSubKey
0x180064661  lea     rax, [rbp+hKey]
0x180064665  mov     edi, r8d
0x180064668  mov     [rsp+68h+phkResult], rax; phkResult
0x18006466d  mov     rbx, rcx
0x180064670  mov     r9d, 0E0006h; samDesired
0x180064676  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18006467d  mov     r8d, 8; ulOptions
0x180064683  call    cs:__imp_RegOpenKeyExW
0x180064689  test    eax, eax
0x18006468b  jz      short loc_1800646E8
0x18006468d  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180064696  lea     rax, [rbp+hKey]
0x18006469a  mov     [rsp+68h+var_30], rax; phkResult
0x18006469f  xor     r9d, r9d; lpClass
0x1800646a2  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800646ab  xor     r8d, r8d; Reserved
0x1800646ae  mov     [rsp+68h+samDesired], 0E0006h; samDesired
0x1800646b6  mov     rdx, rbx; lpSubKey
0x1800646b9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800646c0  mov     dword ptr [rsp+68h+phkResult], 8; dwOptions
0x1800646c8  call    cs:__imp_RegCreateKeyExW
0x1800646ce  mov     ebx, eax
0x1800646d0  test    eax, eax
0x1800646d2  jz      short loc_1800646E8
0x1800646d4  jle     loc_1800647AF
0x1800646da  movzx   ebx, ax
0x1800646dd  or      ebx, 80070000h
0x1800646e3  jmp     loc_1800647AF
0x1800646e8  lea     rdx, [rbp+Sid]; Sid
0x1800646ec  mov     [rbp+Sid], 0
0x1800646f4  lea     rcx, StringSid; "LW"
0x1800646fb  call    cs:__imp_ConvertStringSidToSidW
0x180064701  test    eax, eax
0x180064703  jz      loc_180064790
0x180064709  cmp     esi, 2
0x18006470c  jnz     short loc_18006472C
0x18006470e  mov     r8, [rbp+Sid]; void *
0x180064712  xor     r9d, r9d; bool *
0x180064715  mov     rcx, [rbp+hKey]; void *
0x180064719  mov     dword ptr [rsp+68h+phkResult], 0; unsigned int
0x180064721  call    ?SetHandleIntegrityLevel@@YAJPEAXW4_SE_OBJECT_TYPE@@0PEA_NK@Z; SetHandleIntegrityLevel(void *,_SE_OBJECT_TYPE,void *,bool *,ulong)
0x180064726  mov     ebx, eax
0x180064728  test    eax, eax
0x18006472a  js      short loc_18006477F
0x18006472c  mov     rcx, [rbp+hKey]; void *
0x180064730  xor     r8d, r8d; bool *
0x180064733  mov     edx, 400h; unsigned int
0x180064738  call    ?SetWindowsHandleAccessTrustedAC@@YAJPEAXKPEA_N@Z; SetWindowsHandleAccessTrustedAC(void *,ulong,bool *)
0x18006473d  mov     ebx, eax
0x18006473f  cmp     edi, 1
0x180064742  jnz     short loc_18006474B
0x180064744  mov     edx, 20019h
0x180064749  jmp     short loc_180064774
0x18006474b  cmp     edi, 2
0x18006474e  jnz     short loc_180064757
0x180064750  mov     edx, 2001Fh
0x180064755  jmp     short loc_180064774
0x180064757  cmp     edi, 4
0x18006475a  jnz     short loc_18006477F
0x18006475c  mov     ecx, 1000003Fh
0x180064761  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180064766  mov     edx, 2001Fh
0x18006476b  test    al, al
0x18006476d  jnz     short loc_180064774
0x18006476f  mov     edx, 0F003Fh; unsigned int
0x180064774  mov     rcx, [rbp+hKey]; Handle
0x180064778  call    ?SetRegistryKeyAppContainer@@YAJPEAUHKEY__@@K@Z; SetRegistryKeyAppContainer(HKEY__ *,ulong)
0x18006477d  mov     ebx, eax
0x18006477f  mov     rcx, [rbp+Sid]; hMem
0x180064783  test    rcx, rcx
0x180064786  jz      short loc_1800647A5
0x180064788  call    cs:__imp_LocalFree
0x18006478e  jmp     short loc_1800647A5
0x180064790  call    cs:__imp_GetLastError
0x180064796  mov     ebx, eax
0x180064798  test    eax, eax
0x18006479a  jle     short loc_1800647A5
0x18006479c  movzx   ebx, ax
0x18006479f  or      ebx, 80070000h
0x1800647a5  mov     rcx, [rbp+hKey]; hKey
0x1800647a9  call    cs:__imp_RegCloseKey
0x1800647af  mov     eax, ebx
0x1800647b1  add     rsp, 68h
0x1800647b5  pop     rdi
0x1800647b6  pop     rsi
0x1800647b7  pop     rbx
0x1800647b8  pop     rbp
0x1800647b9  retn
```
