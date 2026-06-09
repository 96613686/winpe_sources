# IterateOverRegistryKey

- ea: `0x1800120d8`
- end: `0x180012257`
- name: `IterateOverRegistryKey`
- size: `383`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011f74`

## callees

- `0x180010670`
- `0x1800120d8`
- `0x18001d8e0`
- `0x18001e368`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800121c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800121c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012157`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012157`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012228`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012199`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012199`

## pseudocode

```c
__int64 __fastcall IterateOverRegistryKey(HKEY hKey, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  HKEY v6; // rbx
  DWORD v7; // esi
  LSTATUS EntryFromPersistentStore; // eax
  unsigned int v9; // edi
  __int64 v11; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  phkResult = 0;
  memset_0(Name, 0, 0x20Au);
  v7 = 0;
  cchName[0] = 261;
  EntryFromPersistentStore = 0;
  LOBYTE(v11) = 1;
  while ( 2 )
  {
    if ( !EntryFromPersistentStore )
    {
      while ( 1 )
      {
        cchName[0] = 261;
        if ( (unsigned __int64)v6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          RegCloseKey(v6);
          phkResult = 0;
        }
        EntryFromPersistentStore = RegEnumKeyExW(hKey, v7++, Name, cchName, 0, 0, 0, 0);
        if ( EntryFromPersistentStore )
          goto LABEL_10;
        if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
        {
          EntryFromPersistentStore = StubNlmCacheLoadEntryFromPersistentStore(phkResult, a5, (__int64)&v11);
          if ( !EntryFromPersistentStore )
            break;
        }
        v6 = phkResult;
      }
      if ( (_BYTE)v11 )
      {
LABEL_10:
        v6 = phkResult;
        continue;
      }
      v6 = phkResult;
    }
    break;
  }
  v9 = 0;
  if ( EntryFromPersistentStore != 259 )
    v9 = EntryFromPersistentStore;
  if ( (unsigned __int64)v6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v6);
  return v9;
}

```

## disassembly

```asm
0x1800120d8  mov     [rsp-8+arg_8], rbx
0x1800120dd  mov     [rsp-8+arg_10], rsi
0x1800120e2  push    rbp
0x1800120e3  push    rdi
0x1800120e4  push    r14
0x1800120e6  lea     rbp, [rsp-180h]
0x1800120ee  sub     rsp, 280h
0x1800120f5  mov     rax, cs:__security_cookie
0x1800120fc  xor     rax, rsp
0x1800120ff  mov     [rbp+190h+var_20], rax
0x180012106  mov     r14, [rbp+190h+arg_20]
0x18001210d  mov     rdi, rcx
0x180012110  xor     ebx, ebx
0x180012112  lea     rcx, [rsp+290h+Name]; void *
0x180012117  xor     edx, edx; Val
0x180012119  mov     [rsp+290h+phkResult], rbx
0x18001211e  mov     r8d, 20Ah; Size
0x180012124  call    memset_0
0x180012129  xor     esi, esi
0x18001212b  mov     [rsp+290h+cchName], 105h
0x180012133  xor     eax, eax
0x180012135  mov     byte ptr [rsp+290h+var_250], 1
0x18001213a  test    eax, eax
0x18001213c  jnz     loc_180012211
0x180012142  lea     rax, [rbx-1]
0x180012146  mov     [rsp+290h+cchName], 105h
0x18001214e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012152  ja      short loc_180012166
0x180012154  mov     rcx, rbx; hKey
0x180012157  call    cs:__imp_RegCloseKey
0x18001215d  mov     [rsp+290h+phkResult], 0
0x180012166  mov     [rsp+290h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001216f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180012174  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18001217d  lea     r8, [rsp+290h+Name]; lpName
0x180012182  mov     [rsp+290h+lpClass], 0; lpClass
0x18001218b  mov     edx, esi; dwIndex
0x18001218d  mov     rcx, rdi; hKey
0x180012190  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180012199  call    cs:__imp_RegEnumKeyExW
0x18001219f  inc     esi
0x1800121a1  test    eax, eax
0x1800121a3  jnz     short loc_180012202
0x1800121a5  lea     rax, [rsp+290h+phkResult]
0x1800121aa  mov     r9d, 20019h; samDesired
0x1800121b0  xor     r8d, r8d; ulOptions
0x1800121b3  mov     [rsp+290h+lpReserved], rax; phkResult
0x1800121b8  lea     rdx, [rsp+290h+Name]; lpSubKey
0x1800121bd  mov     rcx, rdi; hKey
0x1800121c0  call    cs:__imp_RegOpenKeyExW
0x1800121c6  test    eax, eax
0x1800121c8  jnz     short loc_1800121F1
0x1800121ca  mov     rcx, [rsp+290h+phkResult]; hKey
0x1800121cf  lea     rax, [rsp+290h+var_250]
0x1800121d4  mov     [rsp+290h+lpClass], rax; __int64
0x1800121d9  lea     r9, [rsp+290h+Name]
0x1800121de  mov     r8, rdi
0x1800121e1  mov     [rsp+290h+lpReserved], r14; __int64
0x1800121e6  xor     edx, edx
0x1800121e8  call    StubNlmCacheLoadEntryFromPersistentStore
0x1800121ed  test    eax, eax
0x1800121ef  jz      short loc_1800121FB
0x1800121f1  mov     rbx, [rsp+290h+phkResult]
0x1800121f6  jmp     loc_180012142
0x1800121fb  cmp     byte ptr [rsp+290h+var_250], 0
0x180012200  jz      short loc_18001220C
0x180012202  mov     rbx, [rsp+290h+phkResult]
0x180012207  jmp     loc_18001213A
0x18001220c  mov     rbx, [rsp+290h+phkResult]
0x180012211  xor     edi, edi
0x180012213  lea     rcx, [rbx-1]
0x180012217  cmp     eax, 103h
0x18001221c  cmovnz  edi, eax
0x18001221f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180012223  ja      short loc_18001222E
0x180012225  mov     rcx, rbx; hKey
0x180012228  call    cs:__imp_RegCloseKey
0x18001222e  mov     eax, edi
0x180012230  mov     rcx, [rbp+190h+var_20]
0x180012237  xor     rcx, rsp; StackCookie
0x18001223a  call    __security_check_cookie
0x18001223f  lea     r11, [rsp+290h+var_10]
0x180012247  mov     rbx, [r11+28h]
0x18001224b  mov     rsi, [r11+30h]
0x18001224f  mov     rsp, r11
0x180012252  pop     r14
0x180012254  pop     rdi
0x180012255  pop     rbp
0x180012256  retn
```
