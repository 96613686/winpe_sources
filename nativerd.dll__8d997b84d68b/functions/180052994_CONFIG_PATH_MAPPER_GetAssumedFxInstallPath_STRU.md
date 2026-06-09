# CONFIG_PATH_MAPPER::GetAssumedFxInstallPath(STRU *)

- ea: `0x180052994`
- end: `0x180052ac4`
- name: `?GetAssumedFxInstallPath@CONFIG_PATH_MAPPER@@CAJPEAVSTRU@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180052c54`

## callees

- `0x180052994`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180052a30`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180052a30`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180052a53`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180052a53`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180052a18`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180052a3d`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180052a18`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180052a3d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180052a8d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180052a98`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180052a8d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180052a98`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052a25`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052a5e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052a25`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052a5e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800529e4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180052a0d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800529e4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180052a0d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052a6a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052a6a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180052a80`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180052a80`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::GetAssumedFxInstallPath(struct STRU *a1)
{
  UINT SizeCCH; // ebx
  WCHAR *Str; // rax
  UINT SystemWindowsDirectoryW; // ebx
  int v5; // ebx
  const unsigned __int16 *v6; // rax
  _BYTE v8[56]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v9[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v10[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v11[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset_0(v10, 0, 0x208u);
  STRU::STRU((STRU *)v9, v10, 0x104u);
  memset_0(v11, 0, 0x208u);
  STRU::STRU((STRU *)v8, v11, 0x104u);
  SizeCCH = STRU::QuerySizeCCH((STRU *)v8);
  Str = STRU::QueryStr((STRU *)v8);
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Str, SizeCCH);
  if ( SystemWindowsDirectoryW <= STRU::QuerySizeCCH((STRU *)v8) )
  {
    STRU::SyncWithBuffer((STRU *)v8);
    v6 = STRU::QueryStr((STRU *)v8);
    v5 = STRU::Copy(a1, v6);
    if ( v5 >= 0 )
      v5 = STRU::Append(a1, L"\\Microsoft.NET\\Framework64");
  }
  else
  {
    v5 = -2147024774;
  }
  STRU::~STRU((STRU *)v8);
  STRU::~STRU((STRU *)v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180052994  mov     [rsp-8+arg_8], rbx
0x180052999  mov     [rsp-8+arg_10], rdi
0x18005299e  push    rbp
0x18005299f  lea     rbp, [rsp-3C0h]
0x1800529a7  sub     rsp, 4C0h
0x1800529ae  mov     rax, cs:__security_cookie
0x1800529b5  xor     rax, rsp
0x1800529b8  mov     [rbp+3C0h+var_10], rax
0x1800529bf  mov     rdi, rcx
0x1800529c2  xor     edx, edx; Val
0x1800529c4  lea     rcx, [rbp+3C0h+var_430]; void *
0x1800529c8  mov     r8d, 208h; Size
0x1800529ce  call    memset_0
0x1800529d3  mov     ebx, 104h
0x1800529d8  lea     rdx, [rbp+3C0h+var_430]
0x1800529dc  mov     r8d, ebx
0x1800529df  lea     rcx, [rsp+4C0h+var_468]
0x1800529e4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800529ea  xor     edx, edx; Val
0x1800529ec  lea     rcx, [rbp+3C0h+var_220]; void *
0x1800529f3  mov     r8d, 208h; Size
0x1800529f9  call    memset_0
0x1800529fe  mov     r8d, ebx
0x180052a01  lea     rdx, [rbp+3C0h+var_220]
0x180052a08  lea     rcx, [rsp+4C0h+var_4A0]
0x180052a0d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180052a13  lea     rcx, [rsp+4C0h+var_4A0]
0x180052a18  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x180052a1e  lea     rcx, [rsp+4C0h+var_4A0]
0x180052a23  mov     ebx, eax
0x180052a25  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180052a2b  mov     rcx, rax; lpBuffer
0x180052a2e  mov     edx, ebx; uSize
0x180052a30  call    cs:__imp_GetSystemWindowsDirectoryW
0x180052a36  lea     rcx, [rsp+4C0h+var_4A0]
0x180052a3b  mov     ebx, eax
0x180052a3d  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x180052a43  cmp     ebx, eax
0x180052a45  jbe     short loc_180052A4E
0x180052a47  mov     ebx, 8007007Ah
0x180052a4c  jmp     short loc_180052A88
0x180052a4e  lea     rcx, [rsp+4C0h+var_4A0]
0x180052a53  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180052a59  lea     rcx, [rsp+4C0h+var_4A0]
0x180052a5e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180052a64  mov     rdx, rax
0x180052a67  mov     rcx, rdi
0x180052a6a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180052a70  mov     ebx, eax
0x180052a72  test    eax, eax
0x180052a74  js      short loc_180052A88
0x180052a76  lea     rdx, aMicrosoftNetFr; "\\Microsoft.NET\\Framework64"
0x180052a7d  mov     rcx, rdi
0x180052a80  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180052a86  mov     ebx, eax
0x180052a88  lea     rcx, [rsp+4C0h+var_4A0]
0x180052a8d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180052a93  lea     rcx, [rsp+4C0h+var_468]
0x180052a98  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180052a9e  mov     eax, ebx
0x180052aa0  mov     rcx, [rbp+3C0h+var_10]
0x180052aa7  xor     rcx, rsp; StackCookie
0x180052aaa  call    __security_check_cookie
0x180052aaf  lea     r11, [rsp+4C0h+var_s0]
0x180052ab7  mov     rbx, [r11+18h]
0x180052abb  mov     rdi, [r11+20h]
0x180052abf  mov     rsp, r11
0x180052ac2  pop     rbp
0x180052ac3  retn
```
