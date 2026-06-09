# DDConfig::CRegistrationEntry::GetMpcDataFromRegistry(int,_CRYPTOAPI_BLOB &)

- ea: `0x140066790`
- end: `0x1400668a8`
- name: `?GetMpcDataFromRegistry@CRegistrationEntry@DDConfig@@SA_NHAEAU_CRYPTOAPI_BLOB@@@Z`
- size: `280`
- prototype: `static bool(int, struct _CRYPTOAPI_BLOB *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140066134`
- `0x140066a90`

## callees

- `0x140001020`
- `0x14000fea0`
- `0x140066790`
- `0x140066a00`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140066882`
- `ADVAPI32!RegCloseKey` at `0x140066882`
- `ADVAPI32!RegOpenKeyExW` at `0x1400667de`
- `ADVAPI32!RegOpenKeyExW` at `0x1400667de`
- `ADVAPI32!RegQueryValueExW` at `0x14006682a`
- `ADVAPI32!RegQueryValueExW` at `0x14006685f`
- `ADVAPI32!RegQueryValueExW` at `0x14006682a`
- `ADVAPI32!RegQueryValueExW` at `0x14006685f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall DDConfig::CRegistrationEntry::GetMpcDataFromRegistry(unsigned int a1, struct _CRYPTOAPI_BLOB *a2)
{
  LPCWSTR *RegistryPath; // rax
  LSTATUS v4; // edi
  _QWORD *v5; // rdx
  BYTE *v6; // rax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type[2]; // [rsp+38h] [rbp-20h] BYREF

  a2->cbData = 0;
  a2->pbData = 0;
  RegistryPath = (LPCWSTR *)DDConfig::CRegistrationEntry::GetRegistryPath(Type, a1);
  v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, *RegistryPath, 0, 0x20219u, &hKey);
  v5 = (_QWORD *)(*(_QWORD *)Type - 24LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)Type - 24LL + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  }
  if ( !v4 )
  {
    Type[0] = 0;
    if ( RegQueryValueExW(hKey, 0, 0, Type, 0, &a2->cbData) || Type[0] != 3 )
    {
      a2->cbData = 0;
    }
    else
    {
      v6 = (BYTE *)operator new[](a2->cbData);
      a2->pbData = v6;
      if ( RegQueryValueExW(hKey, 0, 0, Type, v6, &a2->cbData) || Type[0] != 3 )
      {
        a2->cbData = 0;
        a2->pbData = 0;
      }
    }
    RegCloseKey(hKey);
  }
  return a2->pbData != 0;
}

```

## disassembly

```asm
0x140066790  mov     [rsp+arg_10], rbx
0x140066795  push    rdi
0x140066796  sub     rsp, 50h
0x14006679a  mov     rax, cs:__security_cookie
0x1400667a1  xor     rax, rsp
0x1400667a4  mov     [rsp+58h+var_18], rax
0x1400667a9  mov     rbx, rdx
0x1400667ac  and     dword ptr [rdx], 0
0x1400667af  and     qword ptr [rdx+8], 0
0x1400667b4  mov     edx, ecx
0x1400667b6  lea     rcx, [rsp+58h+Type]
0x1400667bb  call    ?GetRegistryPath@CRegistrationEntry@DDConfig@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; DDConfig::CRegistrationEntry::GetRegistryPath(int)
0x1400667c0  nop
0x1400667c1  lea     rcx, [rsp+58h+hKey]
0x1400667c6  mov     [rsp+58h+phkResult], rcx; lpData
0x1400667cb  mov     r9d, 20219h; samDesired
0x1400667d1  xor     r8d, r8d; ulOptions
0x1400667d4  mov     rdx, [rax]; lpSubKey
0x1400667d7  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1400667de  call    cs:__imp_RegOpenKeyExW
0x1400667e4  mov     edi, eax
0x1400667e6  mov     rdx, qword ptr [rsp+58h+Type]
0x1400667eb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400667ef  or      ecx, 0FFFFFFFFh
0x1400667f2  lock xadd [rdx+10h], ecx
0x1400667f7  sub     ecx, 1
0x1400667fa  jg      short loc_140066808
0x1400667fc  lfence
0x1400667ff  mov     rcx, [rdx]
0x140066802  mov     rax, [rcx]
0x140066805  call    qword ptr [rax+8]
0x140066808  test    edi, edi
0x14006680a  jnz     short loc_140066888
0x14006680c  and     [rsp+58h+Type], edi
0x140066810  mov     [rsp+58h+lpcbData], rbx; lpcbData
0x140066815  and     [rsp+58h+phkResult], 0
0x14006681b  lea     r9, [rsp+58h+Type]; lpType
0x140066820  xor     r8d, r8d; lpReserved
0x140066823  xor     edx, edx; lpValueName
0x140066825  mov     rcx, [rsp+58h+hKey]; hKey
0x14006682a  call    cs:__imp_RegQueryValueExW
0x140066830  test    eax, eax
0x140066832  jnz     short loc_14006687A
0x140066834  cmp     [rsp+58h+Type], 3
0x140066839  jnz     short loc_14006687A
0x14006683b  mov     ecx, [rbx]; unsigned __int64
0x14006683d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140066842  mov     [rbx+8], rax
0x140066846  mov     [rsp+58h+lpcbData], rbx; lpcbData
0x14006684b  mov     [rsp+58h+phkResult], rax; lpData
0x140066850  lea     r9, [rsp+58h+Type]; lpType
0x140066855  xor     r8d, r8d; lpReserved
0x140066858  xor     edx, edx; lpValueName
0x14006685a  mov     rcx, [rsp+58h+hKey]; hKey
0x14006685f  call    cs:__imp_RegQueryValueExW
0x140066865  test    eax, eax
0x140066867  jnz     short loc_140066870
0x140066869  cmp     [rsp+58h+Type], 3
0x14006686e  jz      short loc_14006687D
0x140066870  and     dword ptr [rbx], 0
0x140066873  and     qword ptr [rbx+8], 0
0x140066878  jmp     short loc_14006687D
0x14006687a  and     dword ptr [rbx], 0
0x14006687d  mov     rcx, [rsp+58h+hKey]; hKey
0x140066882  call    cs:__imp_RegCloseKey
0x140066888  cmp     qword ptr [rbx+8], 0
0x14006688d  setnz   al
0x140066890  mov     rcx, [rsp+58h+var_18]
0x140066895  xor     rcx, rsp; StackCookie
0x140066898  call    __security_check_cookie
0x14006689d  mov     rbx, [rsp+58h+arg_10]
0x1400668a2  add     rsp, 50h
0x1400668a6  pop     rdi
0x1400668a7  retn
```
