# CscPolicy_QueryCacheQuotaPolicy(ushort const *,unsigned __int64,unsigned __int64 *,unsigned __int64,unsigned __int64 *)

- ea: `0x180013138`
- end: `0x18001327b`
- name: `?CscPolicy_QueryCacheQuotaPolicy@@YAJPEBG_KPEA_K12@Z`
- size: `323`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, unsigned __int64, unsigned __int64 *, unsigned __int64, HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012b48`

## callees

- `0x180013138`
- `0x180013584`
- `0x180014068`
- `0x1800140c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001318c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001318c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013266`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013266`

## string_xrefs

- `0x18001322a`: `CacheQuotaLimit`
- `0x18001324a`: `CacheQuotaLimitUnpinned`

## pseudocode

```c
__int64 __fastcall CscPolicy_QueryCacheQuotaPolicy(
        LPCWSTR lpSubKey,
        unsigned __int64 a2,
        unsigned __int64 *a3,
        unsigned __int64 a4,
        HKEY hKey)
{
  unsigned __int64 *v5; // rdi
  LSTATUS v10; // eax
  signed int CacheQuotaPolicyValue; // ebx

  v5 = (unsigned __int64 *)hKey;
  *a3 = 0;
  hKey = 0;
  *v5 = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
  CacheQuotaPolicyValue = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      CacheQuotaPolicyValue = (unsigned __int16)v10 | 0x80070000;
    if ( (_WORD)CacheQuotaPolicyValue == 2 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, lpSubKey);
      *a3 = a2;
      CacheQuotaPolicyValue = 0;
      *v5 = a4;
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        27,
        (unsigned int)WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
        (_DWORD)lpSubKey,
        CacheQuotaPolicyValue);
    }
  }
  else
  {
    CacheQuotaPolicyValue = CscPolicy_ReadCacheQuotaPolicyValue(hKey, L"CacheQuotaLimit", a2, a3);
    if ( CacheQuotaPolicyValue >= 0 )
      CacheQuotaPolicyValue = CscPolicy_ReadCacheQuotaPolicyValue(hKey, L"CacheQuotaLimitUnpinned", a4, v5);
    RegCloseKey(hKey);
  }
  return (unsigned int)CacheQuotaPolicyValue;
}

```

## disassembly

```asm
0x180013138  mov     r11, rsp
0x18001313b  push    rbx
0x18001313c  push    rbp
0x18001313d  push    rsi
0x18001313e  push    rdi
0x18001313f  push    r14
0x180013141  push    r15
0x180013143  sub     rsp, 38h
0x180013147  mov     rdi, [rsp+68h+hKey]
0x18001314f  lea     rax, [r11+28h]
0x180013153  mov     r14, rdx
0x180013156  mov     qword ptr [r8], 0
0x18001315d  mov     rbp, r9
0x180013160  mov     qword ptr [r11+28h], 0
0x180013168  mov     rsi, r8
0x18001316b  mov     [r11-48h], rax
0x18001316f  mov     r15, rcx
0x180013172  mov     qword ptr [rdi], 0
0x180013179  mov     rdx, rcx; lpSubKey
0x18001317c  mov     r9d, 1; samDesired
0x180013182  xor     r8d, r8d; ulOptions
0x180013185  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001318c  call    cs:__imp_RegOpenKeyExW
0x180013192  mov     ebx, eax
0x180013194  test    eax, eax
0x180013196  jz      loc_180013222
0x18001319c  jle     short loc_1800131A7
0x18001319e  movzx   ebx, ax
0x1800131a1  or      ebx, 80070000h
0x1800131a7  cmp     bx, 2
0x1800131ab  jnz     short loc_1800131EB
0x1800131ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131b4  lea     rax, WPP_GLOBAL_Control
0x1800131bb  cmp     rcx, rax
0x1800131be  jz      short loc_1800131DE
0x1800131c0  test    byte ptr [rcx+1Ch], 80h
0x1800131c4  jz      short loc_1800131DE
0x1800131c6  mov     rcx, [rcx+10h]
0x1800131ca  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x1800131d1  mov     edx, 1Ah
0x1800131d6  mov     r9, r15
0x1800131d9  call    WPP_SF_S
0x1800131de  mov     [rsi], r14
0x1800131e1  xor     ebx, ebx
0x1800131e3  mov     [rdi], rbp
0x1800131e6  jmp     loc_18001326C
0x1800131eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131f2  lea     rax, WPP_GLOBAL_Control
0x1800131f9  cmp     rcx, rax
0x1800131fc  jz      short loc_18001326C
0x1800131fe  test    byte ptr [rcx+1Ch], 80h
0x180013202  jz      short loc_18001326C
0x180013204  mov     rcx, [rcx+10h]
0x180013208  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x18001320f  mov     edx, 1Bh
0x180013214  mov     [rsp+68h+var_48], ebx
0x180013218  mov     r9, r15
0x18001321b  call    WPP_SF_SD
0x180013220  jmp     short loc_18001326C
0x180013222  mov     rcx, [rsp+68h+hKey]; HKEY
0x18001322a  lea     rdx, ValueName; "CacheQuotaLimit"
0x180013231  mov     r9, rsi; unsigned __int64 *
0x180013234  mov     r8, r14; unsigned __int64
0x180013237  call    ?CscPolicy_ReadCacheQuotaPolicyValue@@YAJPEAUHKEY__@@PEBG_KPEA_K@Z; CscPolicy_ReadCacheQuotaPolicyValue(HKEY__ *,ushort const *,unsigned __int64,unsigned __int64 *)
0x18001323c  mov     ebx, eax
0x18001323e  test    eax, eax
0x180013240  js      short loc_18001325E
0x180013242  mov     rcx, [rsp+68h+hKey]; HKEY
0x18001324a  lea     rdx, aCachequotalimi; "CacheQuotaLimitUnpinned"
0x180013251  mov     r9, rdi; unsigned __int64 *
0x180013254  mov     r8, rbp; unsigned __int64
0x180013257  call    ?CscPolicy_ReadCacheQuotaPolicyValue@@YAJPEAUHKEY__@@PEBG_KPEA_K@Z; CscPolicy_ReadCacheQuotaPolicyValue(HKEY__ *,ushort const *,unsigned __int64,unsigned __int64 *)
0x18001325c  mov     ebx, eax
0x18001325e  mov     rcx, [rsp+68h+hKey]; hKey
0x180013266  call    cs:__imp_RegCloseKey
0x18001326c  mov     eax, ebx
0x18001326e  add     rsp, 38h
0x180013272  pop     r15
0x180013274  pop     r14
0x180013276  pop     rdi
0x180013277  pop     rsi
0x180013278  pop     rbp
0x180013279  pop     rbx
0x18001327a  retn
```
