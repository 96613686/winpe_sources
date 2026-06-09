# ReadReg32Bit(ushort const *,ushort const *,ulong,ulong *)

- ea: `0x1800195cc`
- end: `0x180019717`
- name: `?ReadReg32Bit@@YAJPEBG0KPEAK@Z`
- size: `331`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int, unsigned int *)`
- caller_count: `25`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800064b8`
- `0x180019528`
- `0x180019e74`
- `0x1800381d0`
- `0x180047458`
- `0x18004e64c`
- `0x18004e8f8`
- `0x180075d90`
- `0x180076f6c`
- `0x18007d1ec`
- `0x18007d3ac`
- `0x18007d490`
- `0x18007d5ac`
- `0x18007d73c`
- `0x18007d934`
- `0x1800b9024`
- `0x1800b9278`
- `0x1800b93a8`
- `0x1800b9e90`
- `0x1800bcd78`
- `0x1800c48c4`
- `0x1800c49bc`
- `0x1800c4c5c`
- `0x1800c4f6c`
- `0x1800c7e84`

## callees

- `0x1800195cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019709`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011ffb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019709`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011ffb0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001969f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001969f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019623`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019623`

## pseudocode

```c
__int64 __fastcall ReadReg32Bit(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int a3, unsigned int *a4)
{
  int v7; // esi
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  DWORD cbData; // [rsp+30h] [rbp-48h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-44h] BYREF
  DWORD Type; // [rsp+38h] [rbp-40h] BYREF
  int v15; // [rsp+3Ch] [rbp-3Ch]
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF

  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  v7 = 0;
  v15 = 0;
  hKey = 0;
  v8 = 0;
  *a4 = a3;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( v9 )
  {
    if ( v9 <= 0 )
      v8 = v9;
    else
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 + 2147024894 <= 1 || v8 == -2147023728 )
      v8 = 1;
  }
  else
  {
    v7 = 1;
    v15 = 1;
    cbData = 4;
    *(_DWORD *)Data = a3;
    v10 = RegQueryValueExW(hKey, lpValueName, 0, &Type, Data, &cbData);
    if ( v10 )
    {
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      else
        v8 = v10;
      if ( v8 + 2147024894 <= 1 || v8 == -2147023728 )
        v8 = 1;
    }
    else if ( Type == 4 && cbData == 4 )
    {
      *a4 = *(_DWORD *)Data;
    }
    else
    {
      v8 = -2147024883;
    }
  }
  if ( v7 )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x1800195cc  mov     rax, rsp
0x1800195cf  push    rbx
0x1800195d0  push    rsi
0x1800195d1  push    r12
0x1800195d3  push    r14
0x1800195d5  push    r15
0x1800195d7  sub     rsp, 50h
0x1800195db  mov     r14, r9
0x1800195de  mov     r15d, r8d
0x1800195e1  mov     r12, rdx
0x1800195e4  mov     dword ptr [rax-40h], 0
0x1800195eb  mov     dword ptr [rax-44h], 0
0x1800195f2  mov     dword ptr [rax-48h], 0
0x1800195f9  xor     esi, esi
0x1800195fb  mov     [rax-3Ch], esi
0x1800195fe  mov     [rax-38h], rsi
0x180019602  xor     ebx, ebx
0x180019604  mov     [r9], r8d
0x180019607  lea     rax, [rax-38h]
0x18001960b  mov     [rsp+78h+phkResult], rax; phkResult
0x180019610  mov     r9d, 20019h; samDesired
0x180019616  xor     r8d, r8d; ulOptions
0x180019619  mov     rdx, rcx; lpSubKey
0x18001961c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019623  call    cs:__imp_RegOpenKeyExW
0x18001962a  nop     dword ptr [rax+rax+00h]
0x18001962f  test    eax, eax
0x180019631  jz      short loc_180019665
0x180019633  jle     short loc_180019661
0x180019635  movzx   ebx, ax
0x180019638  or      ebx, 80070000h
0x18001963e  lea     eax, [rbx+7FF8FFFEh]
0x180019644  cmp     eax, 1
0x180019647  ja      short loc_180019653
0x180019649  mov     ebx, 1
0x18001964e  jmp     loc_1800196F0
0x180019653  cmp     ebx, 80070490h
0x180019659  jnz     loc_1800196F0
0x18001965f  jmp     short loc_180019649
0x180019661  mov     ebx, eax
0x180019663  jmp     short loc_18001963E
0x180019665  mov     esi, 1
0x18001966a  mov     [rsp+78h+var_3C], esi
0x18001966e  mov     [rsp+78h+cbData], 4
0x180019676  mov     dword ptr [rsp+78h+Data], r15d
0x18001967b  lea     rax, [rsp+78h+cbData]
0x180019680  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180019685  lea     rax, [rsp+78h+Data]
0x18001968a  mov     [rsp+78h+phkResult], rax; lpData
0x18001968f  lea     r9, [rsp+78h+Type]; lpType
0x180019694  xor     r8d, r8d; lpReserved
0x180019697  mov     rdx, r12; lpValueName
0x18001969a  mov     rcx, [rsp+78h+hKey]; hKey
0x18001969f  call    cs:__imp_RegQueryValueExW
0x1800196a6  nop     dword ptr [rax+rax+00h]
0x1800196ab  test    eax, eax
0x1800196ad  jnz     short loc_1800196BD
0x1800196af  cmp     [rsp+78h+Type], 4
0x1800196b4  jz      short loc_1800196E2
0x1800196b6  mov     ebx, 8007000Dh
0x1800196bb  jmp     short loc_1800196F0
0x1800196bd  jg      short loc_1800196C3
0x1800196bf  mov     ebx, eax
0x1800196c1  jmp     short loc_1800196CC
0x1800196c3  movzx   ebx, ax
0x1800196c6  or      ebx, 80070000h
0x1800196cc  lea     eax, [rbx+7FF8FFFEh]
0x1800196d2  cmp     eax, esi
0x1800196d4  jbe     short loc_1800196DE
0x1800196d6  cmp     ebx, 80070490h
0x1800196dc  jnz     short loc_1800196F0
0x1800196de  mov     ebx, esi
0x1800196e0  jmp     short loc_1800196F0
0x1800196e2  cmp     [rsp+78h+cbData], 4
0x1800196e7  jnz     short loc_1800196B6
0x1800196e9  mov     eax, dword ptr [rsp+78h+Data]
0x1800196ed  mov     [r14], eax
0x1800196f0  test    esi, esi
0x1800196f2  jnz     short loc_180019704
0x1800196f4  mov     eax, ebx
0x1800196f6  add     rsp, 50h
0x1800196fa  pop     r15
0x1800196fc  pop     r14
0x1800196fe  pop     r12
0x180019700  pop     rsi
0x180019701  pop     rbx
0x180019702  retn
0x180019704  mov     rcx, [rsp+78h+hKey]; hKey
0x180019709  call    cs:__imp_RegCloseKey
0x180019710  nop     dword ptr [rax+rax+00h]
0x180019715  jmp     short loc_1800196F4
0x18011ff9d  push    rbp
0x18011ff9f  sub     rsp, 30h
0x18011ffa3  mov     rbp, rdx
0x18011ffa6  cmp     dword ptr [rbp+3Ch], 0
0x18011ffaa  jz      short loc_18011FFBD
0x18011ffac  mov     rcx, [rbp+40h]; hKey
0x18011ffb0  call    cs:__imp_RegCloseKey
0x18011ffb7  nop     dword ptr [rax+rax+00h]
0x18011ffbc  nop
0x18011ffbd  add     rsp, 30h
0x18011ffc1  pop     rbp
0x18011ffc2  retn
```
