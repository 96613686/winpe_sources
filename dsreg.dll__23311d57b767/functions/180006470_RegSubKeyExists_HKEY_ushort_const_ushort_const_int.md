# RegSubKeyExists(HKEY__ *,ushort const *,ushort const *,int *)

- ea: `0x180006470`
- end: `0x1800065c0`
- name: `?RegSubKeyExists@@YAKPEAUHKEY__@@PEBG1PEAH@Z`
- size: `336`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005bbc`

## callees

- `0x180006470`
- `0x1800084f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006541`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006551`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006541`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006551`

## string_xrefs

- `0x180006566`: `RegOpenKeyExW`
- `0x180006589`: `%s: parentKeyPath should not be null.`

## pseudocode

```c
__int64 __fastcall RegSubKeyExists(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int *a4)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !a4 )
  {
    Logger::TraceError(L"%s: pbExists should not be null.", L"RegSubKeyExists");
    v7 = 87;
    goto LABEL_10;
  }
  *a4 = 0;
  if ( a2 )
  {
    if ( a3 )
    {
      v6 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
      v7 = v6;
      if ( v6 == 2 )
      {
        v7 = 0;
        goto LABEL_10;
      }
      if ( v6 )
        goto LABEL_16;
      v6 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult);
      v7 = v6;
      if ( v6 != 2 )
      {
        if ( !v6 )
        {
          *a4 = 1;
          goto LABEL_10;
        }
LABEL_16:
        Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"RegSubKeyExists", L"RegOpenKeyExW", v6);
        goto LABEL_10;
      }
      v7 = 0;
    }
    else
    {
      Logger::TraceError(L"%s: keyName should not be null.", L"RegSubKeyExists");
      v7 = 87;
    }
  }
  else
  {
    Logger::TraceError(L"%s: parentKeyPath should not be null.", L"RegSubKeyExists");
    v7 = 87;
  }
LABEL_10:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180006470  mov     r11, rsp
0x180006473  push    rbx
0x180006474  sub     rsp, 40h
0x180006478  mov     [r11+8], rbp
0x18000647c  xor     ebp, ebp
0x18000647e  mov     [r11+10h], rsi
0x180006482  mov     rsi, r8
0x180006485  mov     [r11+18h], rdi
0x180006489  mov     rdi, r9
0x18000648c  mov     [r11+20h], rbp
0x180006490  mov     [r11-18h], rbp
0x180006494  test    r9, r9
0x180006497  jz      short loc_180006510
0x180006499  mov     [r9], ebp
0x18000649c  test    rdx, rdx
0x18000649f  jz      loc_180006582
0x1800064a5  test    r8, r8
0x1800064a8  jz      loc_18000659C
0x1800064ae  lea     rax, [r11+20h]
0x1800064b2  mov     r9d, 20019h; samDesired
0x1800064b8  xor     r8d, r8d; ulOptions
0x1800064bb  mov     [r11-28h], rax
0x1800064bf  call    cs:__imp_RegOpenKeyExW
0x1800064c5  mov     ebx, eax
0x1800064c7  cmp     eax, 2
0x1800064ca  jz      loc_18000655F
0x1800064d0  test    eax, eax
0x1800064d2  jnz     loc_180006563
0x1800064d8  mov     rcx, [rsp+48h+hKey]; hKey
0x1800064dd  lea     rax, [rsp+48h+var_18]
0x1800064e2  mov     r9d, 20019h; samDesired
0x1800064e8  mov     [rsp+48h+phkResult], rax; phkResult
0x1800064ed  xor     r8d, r8d; ulOptions
0x1800064f0  mov     rdx, rsi; lpSubKey
0x1800064f3  call    cs:__imp_RegOpenKeyExW
0x1800064f9  mov     ebx, eax
0x1800064fb  cmp     eax, 2
0x1800064fe  jz      loc_1800065B9
0x180006504  test    eax, eax
0x180006506  jnz     short loc_180006563
0x180006508  mov     dword ptr [rdi], 1
0x18000650e  jmp     short loc_180006528
0x180006510  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x180006517  lea     rcx, aSPbexistsShoul; "%s: pbExists should not be null."
0x18000651e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006523  mov     ebx, 57h ; 'W'
0x180006528  mov     rcx, [rsp+48h+var_18]; hKey
0x18000652d  mov     rdi, [rsp+48h+arg_10]
0x180006532  mov     rsi, [rsp+48h+arg_8]
0x180006537  mov     rbp, [rsp+48h+arg_0]
0x18000653c  test    rcx, rcx
0x18000653f  jz      short loc_180006547
0x180006541  call    cs:__imp_RegCloseKey
0x180006547  mov     rcx, [rsp+48h+hKey]; hKey
0x18000654c  test    rcx, rcx
0x18000654f  jz      short loc_180006557
0x180006551  call    cs:__imp_RegCloseKey
0x180006557  mov     eax, ebx
0x180006559  add     rsp, 40h
0x18000655d  pop     rbx
0x18000655e  retn
0x18000655f  mov     ebx, ebp
0x180006561  jmp     short loc_180006528
0x180006563  mov     r9d, eax
0x180006566  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x18000656d  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x180006574  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18000657b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006580  jmp     short loc_180006528
0x180006582  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x180006589  lea     rcx, aSParentkeypath; "%s: parentKeyPath should not be null."
0x180006590  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006595  mov     ebx, 57h ; 'W'
0x18000659a  jmp     short loc_180006528
0x18000659c  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x1800065a3  lea     rcx, aSKeynameShould; "%s: keyName should not be null."
0x1800065aa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800065af  mov     ebx, 57h ; 'W'
0x1800065b4  jmp     loc_180006528
0x1800065b9  mov     ebx, ebp
0x1800065bb  jmp     loc_180006528
```
