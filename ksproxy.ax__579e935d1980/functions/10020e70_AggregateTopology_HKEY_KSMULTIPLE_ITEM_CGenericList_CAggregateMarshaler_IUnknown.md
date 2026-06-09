# AggregateTopology(HKEY__ *,KSMULTIPLE_ITEM *,CGenericList<CAggregateMarshaler> *,IUnknown *)

- ea: `0x10020e70`
- end: `0x10020f99`
- name: `?AggregateTopology@@YGJPAUHKEY__@@PAUKSMULTIPLE_ITEM@@PAV?$CGenericList@VCAggregateMarshaler@@@@PAUIUnknown@@@Z`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1000cf60`

## callees

- `0x10020bea`
- `0x10020e70`
- `0x1003a6fd`
- `0x1003aba0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x10020f16`
- `ADVAPI32!RegQueryValueExW` at `0x10020f16`
- `ADVAPI32!RegCloseKey` at `0x10020f21`
- `ADVAPI32!RegCloseKey` at `0x10020f80`
- `ADVAPI32!RegCloseKey` at `0x10020f21`
- `ADVAPI32!RegCloseKey` at `0x10020f80`
- `ADVAPI32!RegOpenKeyExW` at `0x10020eac`
- `ADVAPI32!RegOpenKeyExW` at `0x10020ef3`
- `ADVAPI32!RegOpenKeyExW` at `0x10020eac`
- `ADVAPI32!RegOpenKeyExW` at `0x10020ef3`
- `ole32!StringFromGUID2` at `0x10020edc`
- `ole32!StringFromGUID2` at `0x10020edc`
- `ole32!IIDFromString` at `0x10020f57`
- `ole32!IIDFromString` at `0x10020f57`

## pseudocode

```c
int __fastcall AggregateTopology(int a1, int a2, int a3, int a4)
{
  int v5; // ebx
  int v6; // ecx
  LSTATUS v7; // esi
  GUID *v8; // eax
  int v10; // [esp+Ch] [ebp-84h]
  GUID *v11; // [esp+14h] [ebp-7Ch]
  DWORD cbData; // [esp+1Ch] [ebp-74h] BYREF
  HKEY phkResult; // [esp+20h] [ebp-70h] BYREF
  HKEY hKey; // [esp+24h] [ebp-6Ch] BYREF
  GUID Data; // [esp+28h] [ebp-68h] BYREF
  OLECHAR sz[42]; // [esp+38h] [ebp-58h] BYREF

  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\MediaInterfaces",
          0,
          0x20019u,
          &phkResult) )
  {
    v5 = *(_DWORD *)(a2 + 4);
    if ( v5 )
    {
      v6 = a2 - 8;
      v10 = a2 - 8;
      do
      {
        StringFromGUID2((const GUID *const)(v6 + 16 * v5), sz, 39);
        if ( !RegOpenKeyExW(phkResult, sz, 0, 0x20019u, &hKey) )
        {
          cbData = 16;
          v7 = RegQueryValueExW(hKey, L"iid", 0, 0, (LPBYTE)&Data, &cbData);
          RegCloseKey(hKey);
          if ( v7 )
            Data = _GUID_00000000_0000_0000_0000_000000000000;
          v8 = (GUID *)operator new(0x30u);
          v11 = v8;
          if ( !v8 )
            break;
          *v8 = Data;
          IIDFromString(sz, v8 + 1);
          AddAggregateObject(a3, v11, a4, 0);
        }
        v6 = v10;
        --v5;
      }
      while ( v5 );
    }
    RegCloseKey(phkResult);
  }
  return 0;
}

```

## disassembly

```asm
0x10020e70  mov     edi, edi
0x10020e72  push    ebp
0x10020e73  mov     ebp, esp
0x10020e75  sub     esp, 84h
0x10020e7b  mov     eax, ___security_cookie
0x10020e80  xor     eax, ebp
0x10020e82  mov     [ebp+var_4], eax
0x10020e85  mov     eax, [ebp+arg_0]
0x10020e88  push    ebx
0x10020e89  push    esi
0x10020e8a  push    edi
0x10020e8b  mov     [ebp+var_80], eax
0x10020e8e  xor     edi, edi
0x10020e90  mov     eax, [ebp+arg_4]
0x10020e93  mov     esi, edx
0x10020e95  mov     [ebp+var_78], eax
0x10020e98  lea     eax, [ebp+phkResult]
0x10020e9b  push    eax; phkResult
0x10020e9c  push    20019h; samDesired
0x10020ea1  push    edi; ulOptions
0x10020ea2  push    offset aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x10020ea7  push    80000002h; hKey
0x10020eac  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10020eb2  test    eax, eax
0x10020eb4  jnz     loc_10020F86
0x10020eba  mov     ebx, [esi+4]
0x10020ebd  test    ebx, ebx
0x10020ebf  jz      loc_10020F7D
0x10020ec5  lea     ecx, [esi-8]
0x10020ec8  mov     [ebp+var_84], ecx
0x10020ece  push    27h ; '''; cchMax
0x10020ed0  lea     eax, [ebp+sz]
0x10020ed3  push    eax; lpsz
0x10020ed4  mov     eax, ebx
0x10020ed6  shl     eax, 4
0x10020ed9  add     eax, ecx
0x10020edb  push    eax; rguid
0x10020edc  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x10020ee2  lea     eax, [ebp+hKey]
0x10020ee5  push    eax; phkResult
0x10020ee6  push    20019h; samDesired
0x10020eeb  push    edi; ulOptions
0x10020eec  lea     eax, [ebp+sz]
0x10020eef  push    eax; lpSubKey
0x10020ef0  push    [ebp+phkResult]; hKey
0x10020ef3  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10020ef9  test    eax, eax
0x10020efb  jnz     short loc_10020F6E
0x10020efd  lea     eax, [ebp+cbData]
0x10020f00  mov     [ebp+cbData], 10h
0x10020f07  push    eax; lpcbData
0x10020f08  lea     eax, [ebp+Data]
0x10020f0b  push    eax; lpData
0x10020f0c  push    edi; lpType
0x10020f0d  push    edi; lpReserved
0x10020f0e  push    offset aIid; "iid"
0x10020f13  push    [ebp+hKey]; hKey
0x10020f16  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x10020f1c  push    [ebp+hKey]; hKey
0x10020f1f  mov     esi, eax
0x10020f21  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10020f27  test    esi, esi
0x10020f29  jz      short loc_10020F37
0x10020f2b  mov     esi, offset __GUID_00000000_0000_0000_0000_000000000000
0x10020f30  lea     edi, [ebp+Data]
0x10020f33  movsd
0x10020f34  movsd
0x10020f35  movsd
0x10020f36  movsd
0x10020f37  push    30h ; '0'; Size
0x10020f39  call    ??2@YAPAXI@Z; operator new(uint)
0x10020f3e  mov     [ebp+var_7C], eax
0x10020f41  pop     ecx
0x10020f42  test    eax, eax
0x10020f44  jz      short loc_10020F7D
0x10020f46  mov     edi, eax
0x10020f48  lea     esi, [ebp+Data]
0x10020f4b  add     eax, 10h
0x10020f4e  push    eax; lpiid
0x10020f4f  lea     eax, [ebp+sz]
0x10020f52  movsd
0x10020f53  push    eax; lpsz
0x10020f54  movsd
0x10020f55  movsd
0x10020f56  movsd
0x10020f57  call    ds:__imp__IIDFromString@8; IIDFromString(x,x)
0x10020f5d  mov     edx, [ebp+var_7C]
0x10020f60  xor     edi, edi
0x10020f62  mov     ecx, [ebp+var_80]
0x10020f65  push    edi
0x10020f66  push    [ebp+var_78]
0x10020f69  call    ?AddAggregateObject@@YGJPAV?$CGenericList@VCAggregateMarshaler@@@@PAVCAggregateMarshaler@@PAUIUnknown@@H@Z; AddAggregateObject(CGenericList<CAggregateMarshaler> *,CAggregateMarshaler *,IUnknown *,int)
0x10020f6e  mov     ecx, [ebp+var_84]
0x10020f74  sub     ebx, 1
0x10020f77  jnz     loc_10020ECE
0x10020f7d  push    [ebp+phkResult]; hKey
0x10020f80  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10020f86  mov     ecx, [ebp+var_4]
0x10020f89  xor     eax, eax
0x10020f8b  pop     edi
0x10020f8c  pop     esi
0x10020f8d  xor     ecx, ebp; StackCookie
0x10020f8f  pop     ebx
0x10020f90  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10020f95  leave
0x10020f96  retn    8
```
