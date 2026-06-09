# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x18002d724`
- end: `0x18002d84a`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `294`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180050558`

## callees

- `0x18000dd20`
- `0x18002d724`
- `0x18002d998`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d77c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d77c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d82e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d82e`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002d7c4`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002d7c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRenewPeriodInSeconds(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v4; // edi
  const WCHAR *v5; // rax
  LSTATUS v6; // eax
  signed int v7; // ebx
  HKEY v8; // rcx
  HKEY v9; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+38h] BYREF

  v13 = 0;
  v4 = 3628800;
  v12 = 3628800;
  hKey = 0;
  v5 = (const WCHAR *)DMGetKnownRegPath(1);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = hKey;
    hKey = 0;
    if ( v8 )
      RegCloseKey(v8);
    return (unsigned int)v7;
  }
  if ( (int)OmaDmRegistryGetDWORD(hKey, a1, L"RenewalPeriod", &v13) < 0 )
  {
    v7 = 0;
LABEL_13:
    *a2 = v4;
    goto LABEL_14;
  }
  v7 = ULongLongToULong(24LL * v13, &v12);
  if ( v7 >= 0 )
  {
    v7 = ULongLongToULong(60LL * v12, &v12);
    if ( v7 >= 0 )
    {
      v7 = ULongLongToULong(60LL * v12, &v12);
      if ( v7 >= 0 )
      {
        v4 = v12;
        goto LABEL_13;
      }
    }
  }
LABEL_14:
  v9 = hKey;
  hKey = 0;
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002d724  mov     [rsp-18h+arg_0], rbx
0x18002d729  mov     [rsp-18h+arg_8], rsi
0x18002d72e  push    rbp
0x18002d72f  push    rdi
0x18002d730  push    r14
0x18002d732  mov     rbp, rsp
0x18002d735  sub     rsp, 40h
0x18002d739  mov     rsi, rdx
0x18002d73c  mov     r14, rcx
0x18002d73f  mov     [rbp+arg_18], 0
0x18002d746  mov     edi, 375F00h
0x18002d74b  mov     [rbp+arg_10], edi
0x18002d74e  mov     [rbp+hKey], 0
0x18002d756  mov     ecx, 1
0x18002d75b  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18002d760  lea     rcx, [rbp+hKey]
0x18002d764  mov     [rsp+40h+phkResult], rcx; phkResult
0x18002d769  mov     r9d, 20019h; samDesired
0x18002d76f  xor     r8d, r8d; ulOptions
0x18002d772  mov     rdx, rax; lpSubKey
0x18002d775  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d77c  call    cs:__imp_RegOpenKeyExW
0x18002d782  mov     ebx, eax
0x18002d784  test    eax, eax
0x18002d786  jle     short loc_18002D791
0x18002d788  movzx   ebx, ax
0x18002d78b  or      ebx, 80070000h
0x18002d791  test    ebx, ebx
0x18002d793  jns     short loc_18002D7B2
0x18002d795  mov     rcx, [rbp+hKey]; hKey
0x18002d799  mov     [rbp+hKey], 0
0x18002d7a1  test    rcx, rcx
0x18002d7a4  jz      short loc_18002D7AD
0x18002d7a6  call    cs:__imp_RegCloseKey
0x18002d7ac  nop
0x18002d7ad  jmp     loc_18002D835
0x18002d7b2  lea     r9, [rbp+arg_18]
0x18002d7b6  lea     r8, aRenewalperiod; "RenewalPeriod"
0x18002d7bd  mov     rdx, r14
0x18002d7c0  mov     rcx, [rbp+hKey]
0x18002d7c4  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002d7ca  test    eax, eax
0x18002d7cc  jns     short loc_18002D7D2
0x18002d7ce  xor     ebx, ebx
0x18002d7d0  jmp     short loc_18002D81B
0x18002d7d2  mov     eax, [rbp+arg_18]
0x18002d7d5  lea     rcx, [rax+rax*2]
0x18002d7d9  shl     rcx, 3; unsigned __int64
0x18002d7dd  lea     rdx, [rbp+arg_10]; unsigned int *
0x18002d7e1  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002d7e6  mov     ebx, eax
0x18002d7e8  test    eax, eax
0x18002d7ea  js      short loc_18002D81D
0x18002d7ec  mov     eax, [rbp+arg_10]
0x18002d7ef  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x18002d7f3  lea     rdx, [rbp+arg_10]; unsigned int *
0x18002d7f7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002d7fc  mov     ebx, eax
0x18002d7fe  test    eax, eax
0x18002d800  js      short loc_18002D81D
0x18002d802  mov     eax, [rbp+arg_10]
0x18002d805  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x18002d809  lea     rdx, [rbp+arg_10]; unsigned int *
0x18002d80d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002d812  mov     ebx, eax
0x18002d814  test    eax, eax
0x18002d816  js      short loc_18002D81D
0x18002d818  mov     edi, [rbp+arg_10]
0x18002d81b  mov     [rsi], edi
0x18002d81d  mov     rcx, [rbp+hKey]; hKey
0x18002d821  mov     [rbp+hKey], 0
0x18002d829  test    rcx, rcx
0x18002d82c  jz      short loc_18002D835
0x18002d82e  call    cs:__imp_RegCloseKey
0x18002d834  nop
0x18002d835  mov     eax, ebx
0x18002d837  mov     rbx, [rsp+40h+arg_0]
0x18002d83c  mov     rsi, [rsp+40h+arg_8]
0x18002d841  add     rsp, 40h
0x18002d845  pop     r14
0x18002d847  pop     rdi
0x18002d848  pop     rbp
0x18002d849  retn
```
