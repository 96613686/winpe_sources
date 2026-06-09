# CFveApi::MarkDEInitializedInThisBootSession(void)

- ea: `0x1800c7330`
- end: `0x1800c742b`
- name: `?MarkDEInitializedInThisBootSession@CFveApi@@AEAAXXZ`
- size: `251`
- prototype: `void __fastcall(CFveApi *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180053e94`

## callees

- `0x1800090c0`
- `0x1800c463c`
- `0x1800c7330`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c73ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c73ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7405`

## pseudocode

```c
void __fastcall CFveApi::MarkDEInitializedInThisBootSession(CFveApi *this)
{
  unsigned int v2; // r8d
  int DEInitializedInThisBootSessionKeyPath; // ebx
  HKEY hKey; // [rsp+50h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  DEInitializedInThisBootSessionKeyPath = CFveApi::GetDEInitializedInThisBootSessionKeyPath(this, SubKey, v2);
  if ( !DEInitializedInThisBootSessionKeyPath )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
      (unsigned int)DEInitializedInThisBootSessionKeyPath);
  if ( DEInitializedInThisBootSessionKeyPath >= 0 )
LABEL_6:
    RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 1u, 0xF003Fu, 0, &hKey, 0);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800c7330  push    rbx
0x1800c7332  sub     rsp, 280h
0x1800c7339  mov     rax, cs:__security_cookie
0x1800c7340  xor     rax, rsp
0x1800c7343  mov     [rsp+288h+var_18], rax
0x1800c734b  mov     rbx, rcx
0x1800c734e  mov     [rsp+288h+hKey], 0
0x1800c7357  lea     rcx, [rsp+288h+SubKey]; void *
0x1800c735c  xor     edx, edx; Val
0x1800c735e  mov     r8d, 208h; Size
0x1800c7364  call    memset_0
0x1800c7369  lea     rdx, [rsp+288h+SubKey]; unsigned __int16 *
0x1800c736e  mov     rcx, rbx; this
0x1800c7371  call    ?GetDEInitializedInThisBootSessionKeyPath@CFveApi@@AEAAJPEAGK@Z; CFveApi::GetDEInitializedInThisBootSessionKeyPath(ushort *,ulong)
0x1800c7376  mov     ebx, eax
0x1800c7378  test    eax, eax
0x1800c737a  jz      short loc_1800C73B1
0x1800c737c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7383  lea     rax, WPP_GLOBAL_Control
0x1800c738a  cmp     rcx, rax
0x1800c738d  jz      short loc_1800C73AD
0x1800c738f  test    byte ptr [rcx+1Ch], 40h
0x1800c7393  jz      short loc_1800C73AD
0x1800c7395  mov     rcx, [rcx+10h]
0x1800c7399  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c73a0  mov     edx, 6Bh ; 'k'
0x1800c73a5  mov     r9d, ebx
0x1800c73a8  call    WPP_SF_d
0x1800c73ad  test    ebx, ebx
0x1800c73af  js      short loc_1800C73FB
0x1800c73b1  mov     [rsp+288h+lpdwDisposition], 0; lpdwDisposition
0x1800c73ba  lea     rax, [rsp+288h+hKey]
0x1800c73bf  mov     [rsp+288h+phkResult], rax; phkResult
0x1800c73c4  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x1800c73c9  mov     [rsp+288h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800c73d2  xor     r9d, r9d; lpClass
0x1800c73d5  mov     [rsp+288h+samDesired], 0F003Fh; samDesired
0x1800c73dd  xor     r8d, r8d; Reserved
0x1800c73e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c73e7  mov     [rsp+288h+dwOptions], 1; dwOptions
0x1800c73ef  call    cs:__imp_RegCreateKeyExW
0x1800c73f6  nop     dword ptr [rax+rax+00h]
0x1800c73fb  mov     rcx, [rsp+288h+hKey]; hKey
0x1800c7400  test    rcx, rcx
0x1800c7403  jz      short loc_1800C7411
0x1800c7405  call    cs:__imp_RegCloseKey
0x1800c740c  nop     dword ptr [rax+rax+00h]
0x1800c7411  mov     rcx, [rsp+288h+var_18]
0x1800c7419  xor     rcx, rsp; StackCookie
0x1800c741c  call    __security_check_cookie
0x1800c7421  add     rsp, 280h
0x1800c7428  pop     rbx
0x1800c7429  retn
```
