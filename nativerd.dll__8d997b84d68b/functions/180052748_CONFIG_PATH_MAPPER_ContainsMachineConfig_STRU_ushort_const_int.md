# CONFIG_PATH_MAPPER::ContainsMachineConfig(STRU *,ushort const *,int *)

- ea: `0x180052748`
- end: `0x180052851`
- name: `?ContainsMachineConfig@CONFIG_PATH_MAPPER@@CAJPEAVSTRU@@PEBGPEAH@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct STRU *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180052c54`

## callees

- `0x180007de0`
- `0x180052748`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005280a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005280a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005281f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005282e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005281f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005282e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052801`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052801`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180052790`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180052790`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800527c8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800527f0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800527c8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800527f0`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800527a4`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800527a4`

## string_xrefs

- `0x1800527e4`: `CONFIG\machine.config`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::ContainsMachineConfig(struct STRU *a1, const unsigned __int16 *a2, int *a3)
{
  int appended; // ebx
  const WCHAR *Str; // rax
  _BYTE v9[64]; // [rsp+20h] [rbp-168h] BYREF
  unsigned __int16 v10[128]; // [rsp+60h] [rbp-128h] BYREF

  memset_0(v10, 0, sizeof(v10));
  STRU::STRU((STRU *)v9, v10, 0x80u);
  *a3 = 0;
  appended = STRU::Copy((STRU *)v9, a1);
  if ( appended < 0
    || (appended = CONFIG_PATH_MAPPER::AppendTrailingSlash((struct STRU *)v9), appended < 0)
    || (appended = STRU::Append((STRU *)v9, a2), appended < 0)
    || (appended = CONFIG_PATH_MAPPER::AppendTrailingSlash((struct STRU *)v9), appended < 0)
    || (appended = STRU::Append((STRU *)v9, L"CONFIG\\machine.config"), appended < 0) )
  {
    STRU::~STRU((STRU *)v9);
    return (unsigned int)appended;
  }
  else
  {
    Str = STRU::QueryStr((STRU *)v9);
    if ( (GetFileAttributesW(Str) & 0x10) == 0 )
      *a3 = 1;
    STRU::~STRU((STRU *)v9);
    return 0;
  }
}

```

## disassembly

```asm
0x180052748  push    rbx
0x18005274a  push    rsi
0x18005274b  push    rdi
0x18005274c  sub     rsp, 170h
0x180052753  mov     rax, cs:__security_cookie
0x18005275a  xor     rax, rsp
0x18005275d  mov     [rsp+188h+var_28], rax
0x180052765  mov     rdi, r8
0x180052768  mov     rsi, rdx
0x18005276b  mov     rbx, rcx
0x18005276e  xor     edx, edx; Val
0x180052770  mov     r8d, 100h; Size
0x180052776  lea     rcx, [rsp+188h+var_128]; void *
0x18005277b  call    memset_0
0x180052780  mov     r8d, 80h
0x180052786  lea     rdx, [rsp+188h+var_128]
0x18005278b  lea     rcx, [rsp+188h+var_168]
0x180052790  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180052796  mov     rdx, rbx
0x180052799  mov     dword ptr [rdi], 0
0x18005279f  lea     rcx, [rsp+188h+var_168]
0x1800527a4  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800527aa  mov     ebx, eax
0x1800527ac  test    eax, eax
0x1800527ae  js      short loc_180052829
0x1800527b0  lea     rcx, [rsp+188h+var_168]; struct STRU *
0x1800527b5  call    ?AppendTrailingSlash@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@@Z; CONFIG_PATH_MAPPER::AppendTrailingSlash(STRU *)
0x1800527ba  mov     ebx, eax
0x1800527bc  test    eax, eax
0x1800527be  js      short loc_180052829
0x1800527c0  mov     rdx, rsi
0x1800527c3  lea     rcx, [rsp+188h+var_168]
0x1800527c8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800527ce  mov     ebx, eax
0x1800527d0  test    eax, eax
0x1800527d2  js      short loc_180052829
0x1800527d4  lea     rcx, [rsp+188h+var_168]; struct STRU *
0x1800527d9  call    ?AppendTrailingSlash@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@@Z; CONFIG_PATH_MAPPER::AppendTrailingSlash(STRU *)
0x1800527de  mov     ebx, eax
0x1800527e0  test    eax, eax
0x1800527e2  js      short loc_180052829
0x1800527e4  lea     rdx, aConfigMachineC_0; "CONFIG\\machine.config"
0x1800527eb  lea     rcx, [rsp+188h+var_168]
0x1800527f0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800527f6  mov     ebx, eax
0x1800527f8  test    eax, eax
0x1800527fa  js      short loc_180052829
0x1800527fc  lea     rcx, [rsp+188h+var_168]
0x180052801  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180052807  mov     rcx, rax; lpFileName
0x18005280a  call    cs:__imp_GetFileAttributesW
0x180052810  test    al, 10h
0x180052812  jnz     short loc_18005281A
0x180052814  mov     dword ptr [rdi], 1
0x18005281a  lea     rcx, [rsp+188h+var_168]
0x18005281f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180052825  xor     eax, eax
0x180052827  jmp     short loc_180052836
0x180052829  lea     rcx, [rsp+188h+var_168]
0x18005282e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180052834  mov     eax, ebx
0x180052836  mov     rcx, [rsp+188h+var_28]
0x18005283e  xor     rcx, rsp; StackCookie
0x180052841  call    __security_check_cookie
0x180052846  add     rsp, 170h
0x18005284d  pop     rdi
0x18005284e  pop     rsi
0x18005284f  pop     rbx
0x180052850  retn
```
