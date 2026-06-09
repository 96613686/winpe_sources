# PFsPersistOpenClusterRootKey

- ea: `0x18002cb04`
- end: `0x18002cc72`
- name: `PFsPersistOpenClusterRootKey`
- size: `366`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002d2b4`
- `0x18002db34`

## callees

- `0x1800069d4`
- `0x18002cb04`
- `0x18002d988`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002cb5b`
- `KERNEL32!GetLastError` at `0x18002cb81`
- `KERNEL32!GetLastError` at `0x18002cb5b`
- `KERNEL32!GetLastError` at `0x18002cb81`
- `CLUSAPI!CloseCluster` at `0x18002cc42`
- `CLUSAPI!CloseCluster` at `0x18002cc42`
- `CLUSAPI!GetClusterKey` at `0x18002cb73`
- `CLUSAPI!GetClusterKey` at `0x18002cb73`
- `CLUSAPI!OpenCluster` at `0x18002cb4d`
- `CLUSAPI!OpenCluster` at `0x18002cb4d`
- `CLUSAPI!ClusterRegCreateKey` at `0x18002cc24`
- `CLUSAPI!ClusterRegCreateKey` at `0x18002cc24`
- `CLUSAPI!ClusterRegCloseKey` at `0x18002cc34`
- `CLUSAPI!ClusterRegCloseKey` at `0x18002cc34`

## pseudocode

```c
__int64 __fastcall PFsPersistOpenClusterRootKey(PHKEY phkResult, __int64 a2)
{
  struct _HCLUSTER *v4; // rsi
  DWORD VirtualServerRegistryPath; // ebx
  HKEY ClusterKey; // rdi
  int v7; // ecx
  DWORD dwDisposition[4]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR szSubKey[264]; // [rsp+50h] [rbp-238h] BYREF

  memset_0(szSubKey, 0, 0x208u);
  dwDisposition[0] = 0;
  v4 = OpenCluster(0);
  if ( v4 || (VirtualServerRegistryPath = GetLastError()) == 0 )
  {
    ClusterKey = GetClusterKey(v4, 0xF003Fu);
    if ( ClusterKey || (VirtualServerRegistryPath = GetLastError()) == 0 )
    {
      VirtualServerRegistryPath = NfsGetVirtualServerRegistryPath(a2, szSubKey);
      if ( VirtualServerRegistryPath
        || (v7 = StringCchCatW(szSubKey, 0x104u, L"\\"), v7 >= 0)
        && (v7 = StringCchCatW(szSubKey, 0x104u, L"PersistentPFs"), v7 >= 0) )
      {
        if ( !VirtualServerRegistryPath )
          VirtualServerRegistryPath = ClusterRegCreateKey(
                                        ClusterKey,
                                        szSubKey,
                                        0,
                                        0xF003Fu,
                                        0,
                                        phkResult,
                                        dwDisposition);
      }
      else if ( (v7 & 0x1FFF0000) != 0x70000 || (VirtualServerRegistryPath = (unsigned __int16)v7, !(_WORD)v7) )
      {
        VirtualServerRegistryPath = 22;
      }
      if ( ClusterKey )
        ClusterRegCloseKey(ClusterKey);
    }
    if ( v4 )
      CloseCluster(v4);
  }
  return VirtualServerRegistryPath;
}

```

## disassembly

```asm
0x18002cb04  mov     [rsp+arg_10], rbx
0x18002cb09  mov     [rsp+arg_18], rbp
0x18002cb0e  push    rsi
0x18002cb0f  push    rdi
0x18002cb10  push    r14
0x18002cb12  sub     rsp, 270h
0x18002cb19  mov     rax, cs:__security_cookie
0x18002cb20  xor     rax, rsp
0x18002cb23  mov     [rsp+288h+var_28], rax
0x18002cb2b  mov     rbp, rdx
0x18002cb2e  mov     r14, rcx
0x18002cb31  xor     edx, edx; Val
0x18002cb33  lea     rcx, [rsp+288h+szSubKey]; void *
0x18002cb38  mov     r8d, 208h; Size
0x18002cb3e  call    memset_0
0x18002cb43  xor     ecx, ecx; lpszClusterName
0x18002cb45  mov     [rsp+288h+dwDisposition], 0
0x18002cb4d  call    cs:__imp_OpenCluster
0x18002cb53  mov     rsi, rax
0x18002cb56  test    rax, rax
0x18002cb59  jnz     short loc_18002CB6B
0x18002cb5b  call    cs:__imp_GetLastError
0x18002cb61  mov     ebx, eax
0x18002cb63  test    eax, eax
0x18002cb65  jnz     loc_18002CC48
0x18002cb6b  mov     edx, 0F003Fh; samDesired
0x18002cb70  mov     rcx, rsi; hCluster
0x18002cb73  call    cs:__imp_GetClusterKey
0x18002cb79  mov     rdi, rax
0x18002cb7c  test    rax, rax
0x18002cb7f  jnz     short loc_18002CB91
0x18002cb81  call    cs:__imp_GetLastError
0x18002cb87  mov     ebx, eax
0x18002cb89  test    eax, eax
0x18002cb8b  jnz     loc_18002CC3A
0x18002cb91  lea     rdx, [rsp+288h+szSubKey]
0x18002cb96  mov     rcx, rbp
0x18002cb99  call    NfsGetVirtualServerRegistryPath
0x18002cb9e  mov     ebx, eax
0x18002cba0  test    eax, eax
0x18002cba2  jnz     short loc_18002CBF7
0x18002cba4  mov     ebp, 104h
0x18002cba9  lea     r8, asc_1800466C0; "\\"
0x18002cbb0  mov     edx, ebp; unsigned __int64
0x18002cbb2  lea     rcx, [rsp+288h+szSubKey]; unsigned __int16 *
0x18002cbb7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002cbbc  mov     ecx, eax
0x18002cbbe  test    eax, eax
0x18002cbc0  js      short loc_18002CBDB
0x18002cbc2  lea     r8, aPersistentpfs; "PersistentPFs"
0x18002cbc9  mov     edx, ebp; unsigned __int64
0x18002cbcb  lea     rcx, [rsp+288h+szSubKey]; unsigned __int16 *
0x18002cbd0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002cbd5  mov     ecx, eax
0x18002cbd7  test    eax, eax
0x18002cbd9  jns     short loc_18002CBF7
0x18002cbdb  mov     eax, ecx
0x18002cbdd  and     eax, 1FFF0000h
0x18002cbe2  cmp     eax, 70000h
0x18002cbe7  jnz     short loc_18002CBF0
0x18002cbe9  movzx   ebx, cx
0x18002cbec  test    ebx, ebx
0x18002cbee  jnz     short loc_18002CC2C
0x18002cbf0  mov     ebx, 16h
0x18002cbf5  jmp     short loc_18002CC2C
0x18002cbf7  test    ebx, ebx
0x18002cbf9  jnz     short loc_18002CC2C
0x18002cbfb  lea     rax, [rsp+288h+dwDisposition]
0x18002cc00  mov     r9d, 0F003Fh; samDesired
0x18002cc06  mov     [rsp+288h+lpdwDisposition], rax; lpdwDisposition
0x18002cc0b  lea     rdx, [rsp+288h+szSubKey]; lpszSubKey
0x18002cc10  mov     [rsp+288h+phkResult], r14; phkResult
0x18002cc15  xor     r8d, r8d; dwOptions
0x18002cc18  mov     rcx, rdi; hKey
0x18002cc1b  mov     [rsp+288h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002cc24  call    cs:__imp_ClusterRegCreateKey
0x18002cc2a  mov     ebx, eax
0x18002cc2c  test    rdi, rdi
0x18002cc2f  jz      short loc_18002CC3A
0x18002cc31  mov     rcx, rdi; hKey
0x18002cc34  call    cs:__imp_ClusterRegCloseKey
0x18002cc3a  test    rsi, rsi
0x18002cc3d  jz      short loc_18002CC48
0x18002cc3f  mov     rcx, rsi; hCluster
0x18002cc42  call    cs:__imp_CloseCluster
0x18002cc48  mov     eax, ebx
0x18002cc4a  mov     rcx, [rsp+288h+var_28]
0x18002cc52  xor     rcx, rsp; StackCookie
0x18002cc55  call    __security_check_cookie
0x18002cc5a  lea     r11, [rsp+288h+var_18]
0x18002cc62  mov     rbx, [r11+30h]
0x18002cc66  mov     rbp, [r11+38h]
0x18002cc6a  mov     rsp, r11
0x18002cc6d  pop     r14
0x18002cc6f  pop     rdi
0x18002cc70  pop     rsi
0x18002cc71  retn
```
