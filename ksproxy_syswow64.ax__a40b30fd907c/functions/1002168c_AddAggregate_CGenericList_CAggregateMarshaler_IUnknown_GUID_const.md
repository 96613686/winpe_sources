# AddAggregate(CGenericList<CAggregateMarshaler> *,IUnknown *,_GUID const &)

- ea: `0x1002168c`
- end: `0x10021799`
- name: `?AddAggregate@@YGJPAV?$CGenericList@VCAggregateMarshaler@@@@PAUIUnknown@@ABU_GUID@@@Z`
- size: `269`
- prototype: `HRESULT __fastcall(CBaseList *, IUnknown *, GUID *rguid)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1000e780`
- `0x10013c80`
- `0x100181a0`

## callees

- `0x10020bea`
- `0x1002168c`
- `0x1003a6fd`
- `0x1003aba0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x10021720`
- `ADVAPI32!RegQueryValueExW` at `0x10021720`
- `ADVAPI32!RegCloseKey` at `0x1002172b`
- `ADVAPI32!RegCloseKey` at `0x10021780`
- `ADVAPI32!RegCloseKey` at `0x1002172b`
- `ADVAPI32!RegCloseKey` at `0x10021780`
- `ADVAPI32!RegOpenKeyExW` at `0x100216bf`
- `ADVAPI32!RegOpenKeyExW` at `0x100216fd`
- `ADVAPI32!RegOpenKeyExW` at `0x100216bf`
- `ADVAPI32!RegOpenKeyExW` at `0x100216fd`
- `ole32!StringFromGUID2` at `0x100216d9`
- `ole32!StringFromGUID2` at `0x100216d9`

## pseudocode

```c
HRESULT __fastcall AddAggregate(CBaseList *a1, IUnknown *a2, GUID *rguid)
{
  LSTATUS v3; // esi
  LSTATUS v4; // esi
  GUID *v5; // eax
  HRESULT v6; // esi
  DWORD cbData; // [esp+14h] [ebp-70h] BYREF
  HKEY hKey; // [esp+18h] [ebp-6Ch] BYREF
  HKEY phkResult; // [esp+1Ch] [ebp-68h] BYREF
  GUID Data; // [esp+20h] [ebp-64h] BYREF
  OLECHAR sz[40]; // [esp+30h] [ebp-54h] BYREF

  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\MediaInterfaces",
         0,
         0x20019u,
         &phkResult);
  if ( v3 )
    phkResult = 0;
  StringFromGUID2(rguid, sz, 39);
  memset(&Data, 0, sizeof(Data));
  if ( v3
    || RegOpenKeyExW(phkResult, sz, 0, 0x20019u, &hKey)
    || (cbData = 16, v4 = RegQueryValueExW(hKey, L"iid", 0, 0, (LPBYTE)&Data, &cbData), RegCloseKey(hKey), v4) )
  {
    Data = _GUID_00000000_0000_0000_0000_000000000000;
  }
  v5 = (GUID *)operator new(0x30u);
  if ( v5 )
  {
    *v5 = Data;
    v5[1] = *rguid;
    v6 = AddAggregateObject(a1, (int)v5, a2, 0);
  }
  else
  {
    v6 = -2147024882;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v6;
}

```

## disassembly

```asm
0x1002168c  mov     edi, edi
0x1002168e  push    ebp
0x1002168f  mov     ebp, esp
0x10021691  sub     esp, 78h
0x10021694  mov     eax, ___security_cookie
0x10021699  xor     eax, ebp
0x1002169b  mov     [ebp+var_4], eax
0x1002169e  push    ebx
0x1002169f  mov     ebx, [ebp+rguid]
0x100216a2  lea     eax, [ebp+phkResult]
0x100216a5  push    esi
0x100216a6  push    edi
0x100216a7  push    eax; phkResult
0x100216a8  push    20019h; samDesired
0x100216ad  push    0; ulOptions
0x100216af  push    offset aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x100216b4  push    80000002h; hKey
0x100216b9  mov     [ebp+var_74], edx
0x100216bc  mov     [ebp+var_78], ecx
0x100216bf  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100216c5  mov     esi, eax
0x100216c7  test    esi, esi
0x100216c9  jz      short loc_100216D2
0x100216cb  mov     [ebp+phkResult], 0
0x100216d2  push    27h ; '''; cchMax
0x100216d4  lea     eax, [ebp+sz]
0x100216d7  push    eax; lpsz
0x100216d8  push    ebx; rguid
0x100216d9  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x100216df  xor     eax, eax
0x100216e1  lea     edi, [ebp+Data]
0x100216e4  stosd
0x100216e5  stosd
0x100216e6  stosd
0x100216e7  stosd
0x100216e8  test    esi, esi
0x100216ea  jnz     short loc_10021735
0x100216ec  lea     eax, [ebp+hKey]
0x100216ef  push    eax; phkResult
0x100216f0  push    20019h; samDesired
0x100216f5  push    esi; ulOptions
0x100216f6  lea     eax, [ebp+sz]
0x100216f9  push    eax; lpSubKey
0x100216fa  push    [ebp+phkResult]; hKey
0x100216fd  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10021703  test    eax, eax
0x10021705  jnz     short loc_10021735
0x10021707  lea     eax, [ebp+cbData]
0x1002170a  mov     [ebp+cbData], 10h
0x10021711  push    eax; lpcbData
0x10021712  lea     eax, [ebp+Data]
0x10021715  push    eax; lpData
0x10021716  push    esi; lpType
0x10021717  push    esi; lpReserved
0x10021718  push    offset aIid; "iid"
0x1002171d  push    [ebp+hKey]; hKey
0x10021720  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x10021726  push    [ebp+hKey]; hKey
0x10021729  mov     esi, eax
0x1002172b  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10021731  test    esi, esi
0x10021733  jz      short loc_10021741
0x10021735  mov     esi, offset __GUID_00000000_0000_0000_0000_000000000000
0x1002173a  lea     edi, [ebp+Data]
0x1002173d  movsd
0x1002173e  movsd
0x1002173f  movsd
0x10021740  movsd
0x10021741  push    30h ; '0'; Size
0x10021743  call    ??2@YAPAXI@Z; operator new(uint)
0x10021748  pop     ecx
0x10021749  test    eax, eax
0x1002174b  jz      short loc_10021772
0x1002174d  mov     edi, eax
0x1002174f  mov     ecx, [ebp+var_78]
0x10021752  lea     esi, [ebp+Data]
0x10021755  mov     edx, eax
0x10021757  push    0
0x10021759  push    [ebp+var_74]
0x1002175c  movsd
0x1002175d  movsd
0x1002175e  movsd
0x1002175f  movsd
0x10021760  mov     esi, ebx
0x10021762  lea     edi, [eax+10h]
0x10021765  movsd
0x10021766  movsd
0x10021767  movsd
0x10021768  movsd
0x10021769  call    ?AddAggregateObject@@YGJPAV?$CGenericList@VCAggregateMarshaler@@@@PAVCAggregateMarshaler@@PAUIUnknown@@H@Z; AddAggregateObject(CGenericList<CAggregateMarshaler> *,CAggregateMarshaler *,IUnknown *,int)
0x1002176e  mov     esi, eax
0x10021770  jmp     short loc_10021777
0x10021772  mov     esi, 8007000Eh
0x10021777  cmp     [ebp+phkResult], 0
0x1002177b  jz      short loc_10021786
0x1002177d  push    [ebp+phkResult]; hKey
0x10021780  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10021786  mov     ecx, [ebp+var_4]
0x10021789  mov     eax, esi
0x1002178b  pop     edi
0x1002178c  pop     esi
0x1002178d  xor     ecx, ebp; StackCookie
0x1002178f  pop     ebx
0x10021790  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10021795  leave
0x10021796  retn    4
```
