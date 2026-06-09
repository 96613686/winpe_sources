# AggregateMarshalers(HKEY__ *,ushort const *,CGenericList<CAggregateMarshaler> *,IUnknown *)

- ea: `0x10020ce6`
- end: `0x10020e6a`
- name: `?AggregateMarshalers@@YGJPAUHKEY__@@PBGPAV?$CGenericList@VCAggregateMarshaler@@@@PAUIUnknown@@@Z`
- size: `388`
- prototype: `int __fastcall(HKEY hKey, LPCWSTR lpSubKey, int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1000cf60`
- `0x10010e48`
- `0x10014357`

## callees

- `0x10020bea`
- `0x10020ce6`
- `0x1003a6fd`
- `0x1003aba0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x10020dab`
- `ADVAPI32!RegQueryValueExW` at `0x10020dab`
- `ADVAPI32!RegCloseKey` at `0x10020db9`
- `ADVAPI32!RegCloseKey` at `0x10020e45`
- `ADVAPI32!RegCloseKey` at `0x10020e51`
- `ADVAPI32!RegCloseKey` at `0x10020db9`
- `ADVAPI32!RegCloseKey` at `0x10020e45`
- `ADVAPI32!RegCloseKey` at `0x10020e51`
- `ADVAPI32!RegOpenKeyExW` at `0x10020d22`
- `ADVAPI32!RegOpenKeyExW` at `0x10020d43`
- `ADVAPI32!RegOpenKeyExW` at `0x10020d78`
- `ADVAPI32!RegOpenKeyExW` at `0x10020d22`
- `ADVAPI32!RegOpenKeyExW` at `0x10020d43`
- `ADVAPI32!RegOpenKeyExW` at `0x10020d78`
- `ADVAPI32!RegEnumKeyW` at `0x10020e31`
- `ADVAPI32!RegEnumKeyW` at `0x10020e31`
- `ole32!IIDFromString` at `0x10020dfb`
- `ole32!IIDFromString` at `0x10020dfb`

## pseudocode

```c
int __fastcall AggregateMarshalers(HKEY hKey, LPCWSTR lpSubKey, int a3, int a4)
{
  DWORD v4; // ebx
  LSTATUS i; // eax
  LSTATUS v6; // esi
  GUID *v7; // eax
  GUID *v9; // [esp+10h] [ebp-B0h]
  DWORD cbData; // [esp+18h] [ebp-A8h] BYREF
  HKEY hKeya; // [esp+1Ch] [ebp-A4h] BYREF
  HKEY v12; // [esp+20h] [ebp-A0h] BYREF
  HKEY phkResult; // [esp+24h] [ebp-9Ch] BYREF
  GUID Data; // [esp+28h] [ebp-98h] BYREF
  WCHAR SubKey[66]; // [esp+38h] [ebp-88h] BYREF

  if ( !RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MediaInterfaces", 0, 0x20019u, &hKeya) )
    {
      v4 = 0;
      for ( i = RegEnumKeyW(phkResult, 0, SubKey, 0x40u); !i; i = RegEnumKeyW(phkResult, v4, SubKey, 0x40u) )
      {
        if ( !RegOpenKeyExW(hKeya, SubKey, 0, 0x20019u, &v12) )
        {
          cbData = 16;
          v6 = RegQueryValueExW(v12, L"iid", 0, 0, (LPBYTE)&Data, &cbData);
          RegCloseKey(v12);
          if ( v6 )
            Data = _GUID_00000000_0000_0000_0000_000000000000;
          v7 = (GUID *)operator new(0x30u);
          v9 = v7;
          if ( !v7 )
            break;
          *v7 = Data;
          IIDFromString(SubKey, v7 + 1);
          AddAggregateObject(a3, v9, a4, 0);
        }
        ++v4;
      }
      RegCloseKey(hKeya);
    }
    RegCloseKey(phkResult);
  }
  return 0;
}

```

## disassembly

```asm
0x10020ce6  mov     edi, edi
0x10020ce8  push    ebp
0x10020ce9  mov     ebp, esp
0x10020ceb  sub     esp, 0B4h
0x10020cf1  mov     eax, ___security_cookie
0x10020cf6  xor     eax, ebp
0x10020cf8  mov     [ebp+var_4], eax
0x10020cfb  mov     eax, [ebp+arg_0]
0x10020cfe  push    ebx
0x10020cff  push    esi
0x10020d00  push    edi
0x10020d01  mov     [ebp+var_B4], eax
0x10020d07  mov     edi, 20019h
0x10020d0c  mov     eax, [ebp+arg_4]
0x10020d0f  xor     esi, esi
0x10020d11  mov     [ebp+var_AC], eax
0x10020d17  lea     eax, [ebp+phkResult]
0x10020d1d  push    eax; phkResult
0x10020d1e  push    edi; samDesired
0x10020d1f  push    esi; ulOptions
0x10020d20  push    edx; lpSubKey
0x10020d21  push    ecx; hKey
0x10020d22  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10020d28  test    eax, eax
0x10020d2a  jnz     loc_10020E57
0x10020d30  lea     eax, [ebp+hKey]
0x10020d36  push    eax; phkResult
0x10020d37  push    edi; samDesired
0x10020d38  push    esi; ulOptions
0x10020d39  push    offset aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x10020d3e  push    80000002h; hKey
0x10020d43  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10020d49  test    eax, eax
0x10020d4b  jnz     loc_10020E4B
0x10020d51  push    40h ; '@'
0x10020d53  lea     eax, [ebp+SubKey]
0x10020d59  mov     ebx, esi
0x10020d5b  push    eax
0x10020d5c  push    esi
0x10020d5d  jmp     loc_10020E2B
0x10020d62  lea     eax, [ebp+var_A0]
0x10020d68  push    eax; phkResult
0x10020d69  push    edi; samDesired
0x10020d6a  push    esi; ulOptions
0x10020d6b  lea     eax, [ebp+SubKey]
0x10020d71  push    eax; lpSubKey
0x10020d72  push    [ebp+hKey]; hKey
0x10020d78  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10020d7e  test    eax, eax
0x10020d80  jnz     loc_10020E20
0x10020d86  lea     eax, [ebp+cbData]
0x10020d8c  mov     [ebp+cbData], 10h
0x10020d96  push    eax; lpcbData
0x10020d97  lea     eax, [ebp+Data]
0x10020d9d  push    eax; lpData
0x10020d9e  push    esi; lpType
0x10020d9f  push    esi; lpReserved
0x10020da0  push    offset aIid; "iid"
0x10020da5  push    [ebp+var_A0]; hKey
0x10020dab  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x10020db1  push    [ebp+var_A0]; hKey
0x10020db7  mov     esi, eax
0x10020db9  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10020dbf  test    esi, esi
0x10020dc1  jz      short loc_10020DD2
0x10020dc3  mov     esi, offset __GUID_00000000_0000_0000_0000_000000000000
0x10020dc8  lea     edi, [ebp+Data]
0x10020dce  movsd
0x10020dcf  movsd
0x10020dd0  movsd
0x10020dd1  movsd
0x10020dd2  push    30h ; '0'; Size
0x10020dd4  call    ??2@YAPAXI@Z; operator new(uint)
0x10020dd9  mov     [ebp+var_B0], eax
0x10020ddf  pop     ecx
0x10020de0  test    eax, eax
0x10020de2  jz      short loc_10020E3F
0x10020de4  mov     edi, eax
0x10020de6  lea     esi, [ebp+Data]
0x10020dec  add     eax, 10h
0x10020def  push    eax; lpiid
0x10020df0  lea     eax, [ebp+SubKey]
0x10020df6  movsd
0x10020df7  push    eax; lpsz
0x10020df8  movsd
0x10020df9  movsd
0x10020dfa  movsd
0x10020dfb  call    ds:__imp__IIDFromString@8; IIDFromString(x,x)
0x10020e01  mov     edx, [ebp+var_B0]
0x10020e07  xor     esi, esi
0x10020e09  mov     ecx, [ebp+var_B4]
0x10020e0f  push    esi
0x10020e10  push    [ebp+var_AC]
0x10020e16  call    ?AddAggregateObject@@YGJPAV?$CGenericList@VCAggregateMarshaler@@@@PAVCAggregateMarshaler@@PAUIUnknown@@H@Z; AddAggregateObject(CGenericList<CAggregateMarshaler> *,CAggregateMarshaler *,IUnknown *,int)
0x10020e1b  mov     edi, 20019h
0x10020e20  push    40h ; '@'; cchName
0x10020e22  lea     eax, [ebp+SubKey]
0x10020e28  inc     ebx
0x10020e29  push    eax; lpName
0x10020e2a  push    ebx; dwIndex
0x10020e2b  push    [ebp+phkResult]; hKey
0x10020e31  call    ds:__imp__RegEnumKeyW@16; RegEnumKeyW(x,x,x,x)
0x10020e37  test    eax, eax
0x10020e39  jz      loc_10020D62
0x10020e3f  push    [ebp+hKey]; hKey
0x10020e45  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10020e4b  push    [ebp+phkResult]; hKey
0x10020e51  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10020e57  mov     ecx, [ebp+var_4]
0x10020e5a  xor     eax, eax
0x10020e5c  pop     edi
0x10020e5d  pop     esi
0x10020e5e  xor     ecx, ebp; StackCookie
0x10020e60  pop     ebx
0x10020e61  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10020e66  leave
0x10020e67  retn    8
```
