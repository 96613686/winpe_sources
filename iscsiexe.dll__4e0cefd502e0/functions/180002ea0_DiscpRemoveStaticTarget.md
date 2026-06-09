# DiscpRemoveStaticTarget

- ea: `0x180002ea0`
- end: `0x180002f96`
- name: `DiscpRemoveStaticTarget`
- size: `246`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004850`

## callees

- `0x180002ea0`
- `0x180003198`
- `0x18000325c`
- `0x180006598`
- `0x1800079ac`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180002f1c`
- `ISCSIUM!DiscpAllocMemory` at `0x180002f1c`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x180002efd`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x180002efd`
- `ISCSIUM!DiscpFreeMemory` at `0x180002f69`
- `ISCSIUM!DiscpFreeMemory` at `0x180002f69`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002f52`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002f60`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002f52`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002f60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f74`

## pseudocode

```c
__int64 __fastcall DiscpRemoveStaticTarget(LPCWSTR lpValueName)
{
  unsigned int TargetByTag; // ebx
  __int64 v3; // rax
  unsigned int v4; // r14d
  wchar_t *v5; // rax
  wchar_t *v6; // rsi
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  volatile signed __int32 *v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  hKey = 0;
  if ( DiscpRestrictNewStaticTargets )
  {
    return (unsigned int)-268500891;
  }
  else
  {
    TargetByTag = DiscpFindTargetByTag((__int64)lpValueName, 2, &v9);
    if ( !TargetByTag )
      TargetByTag = DiscpRemoveTarget(v9);
    if ( !(unsigned int)DiscpOpenRegistryKey(
                          &hKey,
                          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Static Targets",
                          131103) )
    {
      v3 = -1;
      do
        ++v3;
      while ( lpValueName[v3] );
      v4 = v3 + 2;
      v5 = (wchar_t *)DiscpAllocMemory((unsigned int)(2 * (v3 + 2)));
      v6 = v5;
      if ( v5 )
      {
        StringCchCopyW(v5, v4, L"*");
        StringCchCatW(v6, v4, lpValueName);
        RegDeleteValueW(hKey, lpValueName);
        RegDeleteValueW(hKey, v6);
        DiscpFreeMemory(v6);
      }
      RegCloseKey(hKey);
    }
  }
  return TargetByTag;
}

```

## disassembly

```asm
0x180002ea0  mov     rax, rsp
0x180002ea3  mov     [rax+8], rbx
0x180002ea7  mov     [rax+20h], rbp
0x180002eab  push    rsi
0x180002eac  push    rdi
0x180002ead  push    r14
0x180002eaf  sub     rsp, 20h
0x180002eb3  xor     ebp, ebp
0x180002eb5  mov     rdi, rcx
0x180002eb8  cmp     cs:DiscpRestrictNewStaticTargets, bpl
0x180002ebf  mov     [rax+18h], rbp
0x180002ec3  mov     [rax+10h], rbp
0x180002ec7  jnz     loc_180002F7C
0x180002ecd  lea     r8, [rax+18h]
0x180002ed1  lea     edx, [rbp+2]
0x180002ed4  call    DiscpFindTargetByTag
0x180002ed9  mov     ebx, eax
0x180002edb  test    eax, eax
0x180002edd  jnz     short loc_180002EEB
0x180002edf  mov     rcx, [rsp+38h+arg_10]
0x180002ee4  call    DiscpRemoveTarget
0x180002ee9  mov     ebx, eax
0x180002eeb  mov     r8d, 2001Fh
0x180002ef1  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x180002ef8  lea     rcx, [rsp+38h+hKey]
0x180002efd  call    cs:__imp_DiscpOpenRegistryKey
0x180002f03  test    eax, eax
0x180002f05  jnz     short loc_180002F81
0x180002f07  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002f0b  inc     rax
0x180002f0e  cmp     [rdi+rax*2], bp
0x180002f12  jnz     short loc_180002F0B
0x180002f14  lea     r14d, [rax+2]
0x180002f18  lea     ecx, [r14+r14]
0x180002f1c  call    cs:__imp_DiscpAllocMemory
0x180002f22  mov     rsi, rax
0x180002f25  test    rax, rax
0x180002f28  jz      short loc_180002F6F
0x180002f2a  lea     r8, pszSrc; "*"
0x180002f31  mov     edx, r14d; cchDest
0x180002f34  mov     rcx, rax; pszDest
0x180002f37  call    StringCchCopyW
0x180002f3c  mov     r8, rdi; pszSrc
0x180002f3f  mov     edx, r14d; cchDest
0x180002f42  mov     rcx, rsi; pszDest
0x180002f45  call    StringCchCatW
0x180002f4a  mov     rcx, [rsp+38h+hKey]; hKey
0x180002f4f  mov     rdx, rdi; lpValueName
0x180002f52  call    cs:__imp_RegDeleteValueW
0x180002f58  mov     rcx, [rsp+38h+hKey]; hKey
0x180002f5d  mov     rdx, rsi; lpValueName
0x180002f60  call    cs:__imp_RegDeleteValueW
0x180002f66  mov     rcx, rsi
0x180002f69  call    cs:__imp_DiscpFreeMemory
0x180002f6f  mov     rcx, [rsp+38h+hKey]; hKey
0x180002f74  call    cs:__imp_RegCloseKey
0x180002f7a  jmp     short loc_180002F81
0x180002f7c  mov     ebx, 0EFFF0065h
0x180002f81  mov     rbp, [rsp+38h+arg_18]
0x180002f86  mov     eax, ebx
0x180002f88  mov     rbx, [rsp+38h+arg_0]
0x180002f8d  add     rsp, 20h
0x180002f91  pop     r14
0x180002f93  pop     rdi
0x180002f94  pop     rsi
0x180002f95  retn
```
