# UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)

- ea: `0x18000e524`
- end: `0x18000e5ef`
- name: `?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z`
- size: `203`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned int@<r9d>, bool *, bool)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e7c0`
- `0x18000eddc`
- `0x180012ef0`
- `0x180014598`
- `0x18001b5b4`
- `0x1800363ac`

## callees

- `0x18000a004`
- `0x18000e524`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e5da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e5da`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e5a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e5a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e56e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e56e`

## pseudocode

```c
__int64 __fastcall UtilRegGetDWORD(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        unsigned int a4,
        bool *a5,
        unsigned int pvData)
{
  unsigned int v7; // esi
  HKEY *phkResult; // rax
  LSTATUS v11; // eax
  bool v12; // sf
  bool v13; // cc
  LSTATUS ValueW; // eax
  HKEY hkey; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF

  pvData = a4;
  pcbData = 4;
  v7 = a4;
  hkey = 0;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  v11 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, phkResult);
  v12 = v11 < 0;
  v13 = v11 <= 0;
  if ( !v11 )
  {
    ValueW = RegGetValueW(hkey, 0, lpValue, 0x10u, 0, &pvData, &pcbData);
    v12 = ValueW < 0;
    v13 = ValueW <= 0;
    if ( !ValueW )
      goto LABEL_7;
  }
  if ( !v13 )
    v12 = 1;
  if ( v12 )
    pvData = v7;
  else
LABEL_7:
    v7 = pvData;
  if ( hkey )
    RegCloseKey(hkey);
  return v7;
}

```

## disassembly

```asm
0x18000e524  mov     rax, rsp
0x18000e527  mov     [rax+10h], rbx
0x18000e52b  push    rbp
0x18000e52c  push    rsi
0x18000e52d  push    rdi
0x18000e52e  sub     rsp, 40h
0x18000e532  mov     rdi, rcx
0x18000e535  mov     [rax+30h], r9d
0x18000e539  lea     rcx, [rax+8]
0x18000e53d  mov     dword ptr [rax+20h], 4
0x18000e544  mov     esi, r9d
0x18000e547  mov     qword ptr [rax+8], 0
0x18000e54f  mov     rbp, r8
0x18000e552  mov     rbx, rdx
0x18000e555  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000e55a  mov     r9d, 101h; samDesired
0x18000e560  mov     [rsp+58h+phkResult], rax; phkResult
0x18000e565  xor     r8d, r8d; ulOptions
0x18000e568  mov     rdx, rbx; lpSubKey
0x18000e56b  mov     rcx, rdi; hKey
0x18000e56e  call    cs:__imp_RegOpenKeyExW
0x18000e574  test    eax, eax
0x18000e576  jnz     short loc_18000E5B2
0x18000e578  mov     rcx, [rsp+58h+hkey]; hkey
0x18000e57d  lea     rax, [rsp+58h+arg_18]
0x18000e582  mov     [rsp+58h+pcbData], rax; pcbData
0x18000e587  mov     r9d, 10h; dwFlags
0x18000e58d  lea     rax, [rsp+58h+arg_28]
0x18000e595  mov     r8, rbp; lpValue
0x18000e598  mov     [rsp+58h+pvData], rax; pvData
0x18000e59d  xor     edx, edx; lpSubKey
0x18000e59f  mov     [rsp+58h+phkResult], 0; pdwType
0x18000e5a8  call    cs:__imp_RegGetValueW
0x18000e5ae  test    eax, eax
0x18000e5b0  jz      short loc_18000E5C9
0x18000e5b2  jle     short loc_18000E5BE
0x18000e5b4  movzx   eax, ax
0x18000e5b7  or      eax, 80070000h
0x18000e5bc  test    eax, eax
0x18000e5be  jns     short loc_18000E5C9
0x18000e5c0  mov     [rsp+58h+arg_28], esi
0x18000e5c7  jmp     short loc_18000E5D0
0x18000e5c9  mov     esi, [rsp+58h+arg_28]
0x18000e5d0  mov     rcx, [rsp+58h+hkey]; hKey
0x18000e5d5  test    rcx, rcx
0x18000e5d8  jz      short loc_18000E5E0
0x18000e5da  call    cs:__imp_RegCloseKey
0x18000e5e0  mov     rbx, [rsp+58h+arg_8]
0x18000e5e5  mov     eax, esi
0x18000e5e7  add     rsp, 40h
0x18000e5eb  pop     rdi
0x18000e5ec  pop     rsi
0x18000e5ed  pop     rbp
0x18000e5ee  retn
```
