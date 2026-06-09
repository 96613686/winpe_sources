# SetDefaultUserHiveSecurity(ushort const *,HKEY__ *)

- ea: `0x18000df6c`
- end: `0x18000e033`
- name: `?SetDefaultUserHiveSecurity@@YAJPEBGPEAUHKEY__@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a250`
- `0x18000dd18`
- `0x1800123ac`

## callees

- `0x18000df6c`
- `0x18000e194`
- `0x1800121fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e015`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e015`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dfa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dfa7`

## pseudocode

```c
__int64 __fastcall SetDefaultUserHiveSecurity(const unsigned __int16 *a1, HKEY a2)
{
  HKEY v4; // rax
  LSTATUS v5; // eax
  signed int v6; // ebx
  __int64 v7; // r9
  int (*v8)(HKEY, void *, void *, int, int); // r8
  int v9; // edi
  __int64 result; // rax
  int (*v11)(HKEY, void *, void *, int, int); // [rsp+30h] [rbp-38h]
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = a2;
  v4 = a2;
  if ( !a2 )
  {
    v5 = RegOpenKeyExW(HKEY_USERS, a1, 0, 0x60019u, &hKey);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 < 0 )
      return (unsigned int)v6;
    v4 = hKey;
  }
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v6 = SetHiveSecurity_(
         a1,
         L"D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)",
         L"D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)",
         v7 + 78,
         v4,
         1,
         v11);
  v9 = SetDefaultHiveAppContainerSecurity_(a1, hKey, v8);
  if ( hKey != a2 )
    RegCloseKey(hKey);
  if ( v6 < 0 )
    return (unsigned int)v6;
  result = 0;
  if ( v9 < 0 )
    return (unsigned int)v9;
  return result;
}

```

## disassembly

```asm
0x18000df6c  push    rbx
0x18000df6e  push    rbp
0x18000df6f  push    rsi
0x18000df70  push    rdi
0x18000df71  sub     rsp, 48h
0x18000df75  xor     ebp, ebp
0x18000df77  mov     [rsp+68h+hKey], rdx
0x18000df7c  mov     rsi, rdx
0x18000df7f  mov     rdi, rcx
0x18000df82  mov     rax, rdx
0x18000df85  test    rdx, rdx
0x18000df88  jnz     short loc_18000DFC5
0x18000df8a  lea     rax, [rsp+68h+hKey]
0x18000df8f  mov     rdx, rcx; lpSubKey
0x18000df92  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000df99  mov     [rsp+68h+phkResult], rax; phkResult
0x18000df9e  mov     r9d, 60019h; samDesired
0x18000dfa4  xor     r8d, r8d; ulOptions
0x18000dfa7  call    cs:__imp_RegOpenKeyExW
0x18000dfad  mov     ebx, eax
0x18000dfaf  test    eax, eax
0x18000dfb1  jle     short loc_18000DFBC
0x18000dfb3  movzx   ebx, ax
0x18000dfb6  or      ebx, 80070000h
0x18000dfbc  test    ebx, ebx
0x18000dfbe  js      short loc_18000E01F
0x18000dfc0  mov     rax, [rsp+68h+hKey]
0x18000dfc5  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000dfc9  inc     r9
0x18000dfcc  cmp     [rdi+r9*2], bp
0x18000dfd1  jnz     short loc_18000DFC9
0x18000dfd3  add     r9, 4Eh ; 'N'; unsigned __int64
0x18000dfd7  mov     [rsp+68h+var_40], 1; int
0x18000dfdf  lea     r8, ?c_szInherited@?1??SetUserHiveSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z@4QBGB; "D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY"...
0x18000dfe6  mov     [rsp+68h+phkResult], rax; HKEY
0x18000dfeb  lea     rdx, ?c_szNonInherited@?1??SetUserHiveSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A"...
0x18000dff2  mov     rcx, rdi; unsigned __int16 *
0x18000dff5  call    ?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z; SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18000dffa  mov     rdx, [rsp+68h+hKey]; hKey
0x18000dfff  mov     rcx, rdi; unsigned __int16 *
0x18000e002  mov     ebx, eax
0x18000e004  call    ?SetDefaultHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z; SetDefaultHiveAppContainerSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))
0x18000e009  mov     rcx, [rsp+68h+hKey]; hKey
0x18000e00e  mov     edi, eax
0x18000e010  cmp     rcx, rsi
0x18000e013  jz      short loc_18000E01B
0x18000e015  call    cs:__imp_RegCloseKey
0x18000e01b  test    ebx, ebx
0x18000e01d  jns     short loc_18000E023
0x18000e01f  mov     eax, ebx
0x18000e021  jmp     short loc_18000E02A
0x18000e023  test    edi, edi
0x18000e025  mov     eax, ebp
0x18000e027  cmovs   eax, edi
0x18000e02a  add     rsp, 48h
0x18000e02e  pop     rdi
0x18000e02f  pop     rsi
0x18000e030  pop     rbp
0x18000e031  pop     rbx
0x18000e032  retn
```
