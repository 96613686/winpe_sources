# DDConfig::CFamilyToMPCTable::GetTableFromRegistry(_CRYPTOAPI_BLOB &)

- ea: `0x140066ec0`
- end: `0x140066fd6`
- name: `?GetTableFromRegistry@CFamilyToMPCTable@DDConfig@@CA_NAEAU_CRYPTOAPI_BLOB@@@Z`
- size: `278`
- prototype: `bool __fastcall(LPDWORD lpcbData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140067080`

## callees

- `0x140001020`
- `0x14000fea0`
- `0x140066ec0`
- `0x140067140`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140066fb0`
- `ADVAPI32!RegCloseKey` at `0x140066fb0`
- `ADVAPI32!RegOpenKeyExW` at `0x140066f0c`
- `ADVAPI32!RegOpenKeyExW` at `0x140066f0c`
- `ADVAPI32!RegQueryValueExW` at `0x140066f58`
- `ADVAPI32!RegQueryValueExW` at `0x140066f8d`
- `ADVAPI32!RegQueryValueExW` at `0x140066f58`
- `ADVAPI32!RegQueryValueExW` at `0x140066f8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall DDConfig::CFamilyToMPCTable::GetTableFromRegistry(DWORD *lpcbData)
{
  LPCWSTR *v2; // rax
  LSTATUS v3; // edi
  _QWORD *v4; // rdx
  BYTE *v5; // rax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type[2]; // [rsp+38h] [rbp-20h] BYREF

  *lpcbData = 0;
  *((_QWORD *)lpcbData + 1) = 0;
  v2 = (LPCWSTR *)DDConfig::REGKEYSUFFIX_FamilyTable(Type);
  v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, *v2, 0, 0x20219u, &hKey);
  v4 = (_QWORD *)(*(_QWORD *)Type - 24LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)Type - 24LL + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
  }
  if ( !v3 )
  {
    Type[0] = 0;
    if ( RegQueryValueExW(hKey, 0, 0, Type, 0, lpcbData) || Type[0] != 3 )
    {
      *lpcbData = 0;
    }
    else
    {
      v5 = (BYTE *)operator new[](*lpcbData);
      *((_QWORD *)lpcbData + 1) = v5;
      if ( RegQueryValueExW(hKey, 0, 0, Type, v5, lpcbData) || Type[0] != 3 )
      {
        *lpcbData = 0;
        *((_QWORD *)lpcbData + 1) = 0;
      }
    }
    RegCloseKey(hKey);
  }
  return *((_QWORD *)lpcbData + 1) != 0;
}

```

## disassembly

```asm
0x140066ec0  mov     [rsp+arg_8], rbx
0x140066ec5  push    rdi
0x140066ec6  sub     rsp, 50h
0x140066eca  mov     rax, cs:__security_cookie
0x140066ed1  xor     rax, rsp
0x140066ed4  mov     [rsp+58h+var_18], rax
0x140066ed9  mov     rbx, rcx
0x140066edc  and     dword ptr [rcx], 0
0x140066edf  and     qword ptr [rcx+8], 0
0x140066ee4  lea     rcx, [rsp+58h+Type]
0x140066ee9  call    ?REGKEYSUFFIX_FamilyTable@DDConfig@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; DDConfig::REGKEYSUFFIX_FamilyTable(void)
0x140066eee  nop
0x140066eef  lea     rcx, [rsp+58h+hKey]
0x140066ef4  mov     [rsp+58h+phkResult], rcx; lpData
0x140066ef9  mov     r9d, 20219h; samDesired
0x140066eff  xor     r8d, r8d; ulOptions
0x140066f02  mov     rdx, [rax]; lpSubKey
0x140066f05  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140066f0c  call    cs:__imp_RegOpenKeyExW
0x140066f12  mov     edi, eax
0x140066f14  mov     rdx, qword ptr [rsp+58h+Type]
0x140066f19  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140066f1d  or      ecx, 0FFFFFFFFh
0x140066f20  lock xadd [rdx+10h], ecx
0x140066f25  sub     ecx, 1
0x140066f28  jg      short loc_140066F36
0x140066f2a  lfence
0x140066f2d  mov     rcx, [rdx]
0x140066f30  mov     rax, [rcx]
0x140066f33  call    qword ptr [rax+8]
0x140066f36  test    edi, edi
0x140066f38  jnz     short loc_140066FB6
0x140066f3a  and     [rsp+58h+Type], edi
0x140066f3e  mov     [rsp+58h+lpcbData], rbx; lpcbData
0x140066f43  and     [rsp+58h+phkResult], 0
0x140066f49  lea     r9, [rsp+58h+Type]; lpType
0x140066f4e  xor     r8d, r8d; lpReserved
0x140066f51  xor     edx, edx; lpValueName
0x140066f53  mov     rcx, [rsp+58h+hKey]; hKey
0x140066f58  call    cs:__imp_RegQueryValueExW
0x140066f5e  test    eax, eax
0x140066f60  jnz     short loc_140066FA8
0x140066f62  cmp     [rsp+58h+Type], 3
0x140066f67  jnz     short loc_140066FA8
0x140066f69  mov     ecx, [rbx]; unsigned __int64
0x140066f6b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140066f70  mov     [rbx+8], rax
0x140066f74  mov     [rsp+58h+lpcbData], rbx; lpcbData
0x140066f79  mov     [rsp+58h+phkResult], rax; lpData
0x140066f7e  lea     r9, [rsp+58h+Type]; lpType
0x140066f83  xor     r8d, r8d; lpReserved
0x140066f86  xor     edx, edx; lpValueName
0x140066f88  mov     rcx, [rsp+58h+hKey]; hKey
0x140066f8d  call    cs:__imp_RegQueryValueExW
0x140066f93  test    eax, eax
0x140066f95  jnz     short loc_140066F9E
0x140066f97  cmp     [rsp+58h+Type], 3
0x140066f9c  jz      short loc_140066FAB
0x140066f9e  and     dword ptr [rbx], 0
0x140066fa1  and     qword ptr [rbx+8], 0
0x140066fa6  jmp     short loc_140066FAB
0x140066fa8  and     dword ptr [rbx], 0
0x140066fab  mov     rcx, [rsp+58h+hKey]; hKey
0x140066fb0  call    cs:__imp_RegCloseKey
0x140066fb6  cmp     qword ptr [rbx+8], 0
0x140066fbb  setnz   al
0x140066fbe  mov     rcx, [rsp+58h+var_18]
0x140066fc3  xor     rcx, rsp; StackCookie
0x140066fc6  call    __security_check_cookie
0x140066fcb  mov     rbx, [rsp+58h+arg_8]
0x140066fd0  add     rsp, 50h
0x140066fd4  pop     rdi
0x140066fd5  retn
```
