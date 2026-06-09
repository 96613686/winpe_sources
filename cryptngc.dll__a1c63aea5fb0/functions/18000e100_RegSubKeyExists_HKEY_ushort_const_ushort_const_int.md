# RegSubKeyExists(HKEY__ *,ushort const *,ushort const *,int *)

- ea: `0x18000e100`
- end: `0x18000e241`
- name: `?RegSubKeyExists@@YAKPEAUHKEY__@@PEBG1PEAH@Z`
- size: `321`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d770`

## callees

- `0x18000e100`
- `0x180027448`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e1a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e1ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e1a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e1ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e223`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e233`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e223`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e233`

## string_xrefs

- `0x18000e158`: `%s: parentKeyPath should not be null.`
- `0x18000e1b8`: `RegOpenKeyExW`

## pseudocode

```c
__int64 __fastcall RegSubKeyExists(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int *a4)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !a4 )
  {
    Logger::TraceError(L"%s: pbExists should not be null.", L"RegSubKeyExists");
    v6 = 87;
    goto LABEL_15;
  }
  *a4 = 0;
  if ( !a2 )
  {
    Logger::TraceError(L"%s: parentKeyPath should not be null.", L"RegSubKeyExists");
    v6 = 87;
    goto LABEL_15;
  }
  if ( !a3 )
  {
    Logger::TraceError(L"%s: keyName should not be null.", L"RegSubKeyExists");
    v6 = 87;
    goto LABEL_15;
  }
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v6 = v7;
  if ( v7 == 2 )
  {
    v6 = 0;
    goto LABEL_15;
  }
  if ( v7 )
    goto LABEL_10;
  v7 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult);
  v6 = v7;
  if ( v7 == 2 )
  {
    v6 = 0;
  }
  else
  {
    if ( v7 )
    {
LABEL_10:
      Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"RegSubKeyExists", L"RegOpenKeyExW", v7);
      goto LABEL_15;
    }
    *a4 = 1;
  }
LABEL_15:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18000e100  push    rbx
0x18000e102  sub     rsp, 40h
0x18000e106  mov     [rsp+48h+arg_0], rbp
0x18000e10b  xor     ebp, ebp
0x18000e10d  mov     [rsp+48h+arg_8], rsi
0x18000e112  mov     rsi, r8
0x18000e115  mov     [rsp+48h+arg_10], rdi
0x18000e11a  mov     rdi, r9
0x18000e11d  mov     [rsp+48h+hKey], rbp
0x18000e122  mov     [rsp+48h+var_18], rbp
0x18000e127  test    r9, r9
0x18000e12a  jnz     short loc_18000E149
0x18000e12c  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x18000e133  lea     rcx, aSPbexistsShoul; "%s: pbExists should not be null."
0x18000e13a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e13f  mov     ebx, 57h ; 'W'
0x18000e144  jmp     loc_18000E20A
0x18000e149  mov     [r9], ebp
0x18000e14c  test    rdx, rdx
0x18000e14f  jnz     short loc_18000E16E
0x18000e151  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x18000e158  lea     rcx, aSParentkeypath; "%s: parentKeyPath should not be null."
0x18000e15f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e164  mov     ebx, 57h ; 'W'
0x18000e169  jmp     loc_18000E20A
0x18000e16e  test    rsi, rsi
0x18000e171  jnz     short loc_18000E18D
0x18000e173  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x18000e17a  lea     rcx, aSKeynameShould; "%s: keyName should not be null."
0x18000e181  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e186  mov     ebx, 57h ; 'W'
0x18000e18b  jmp     short loc_18000E20A
0x18000e18d  lea     rax, [rsp+48h+hKey]
0x18000e192  mov     r9d, 20019h; samDesired
0x18000e198  xor     r8d, r8d; ulOptions
0x18000e19b  mov     [rsp+48h+phkResult], rax; phkResult
0x18000e1a0  call    cs:__imp_RegOpenKeyExW
0x18000e1a6  mov     ebx, eax
0x18000e1a8  cmp     eax, 2
0x18000e1ab  jnz     short loc_18000E1B1
0x18000e1ad  mov     ebx, ebp
0x18000e1af  jmp     short loc_18000E20A
0x18000e1b1  test    eax, eax
0x18000e1b3  jz      short loc_18000E1D4
0x18000e1b5  mov     r9d, eax
0x18000e1b8  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x18000e1bf  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x18000e1c6  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000e1cd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e1d2  jmp     short loc_18000E20A
0x18000e1d4  mov     rcx, [rsp+48h+hKey]; hKey
0x18000e1d9  lea     rax, [rsp+48h+var_18]
0x18000e1de  mov     r9d, 20019h; samDesired
0x18000e1e4  mov     [rsp+48h+phkResult], rax; phkResult
0x18000e1e9  xor     r8d, r8d; ulOptions
0x18000e1ec  mov     rdx, rsi; lpSubKey
0x18000e1ef  call    cs:__imp_RegOpenKeyExW
0x18000e1f5  mov     ebx, eax
0x18000e1f7  cmp     eax, 2
0x18000e1fa  jnz     short loc_18000E200
0x18000e1fc  mov     ebx, ebp
0x18000e1fe  jmp     short loc_18000E20A
0x18000e200  test    eax, eax
0x18000e202  jnz     short loc_18000E1B5
0x18000e204  mov     dword ptr [rdi], 1
0x18000e20a  mov     rcx, [rsp+48h+var_18]; hKey
0x18000e20f  mov     rdi, [rsp+48h+arg_10]
0x18000e214  mov     rsi, [rsp+48h+arg_8]
0x18000e219  mov     rbp, [rsp+48h+arg_0]
0x18000e21e  test    rcx, rcx
0x18000e221  jz      short loc_18000E229
0x18000e223  call    cs:__imp_RegCloseKey
0x18000e229  mov     rcx, [rsp+48h+hKey]; hKey
0x18000e22e  test    rcx, rcx
0x18000e231  jz      short loc_18000E239
0x18000e233  call    cs:__imp_RegCloseKey
0x18000e239  mov     eax, ebx
0x18000e23b  add     rsp, 40h
0x18000e23f  pop     rbx
0x18000e240  retn
```
