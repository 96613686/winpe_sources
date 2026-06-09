# OpenAppRegKey(char const *)

- ea: `0x180011648`
- end: `0x180011742`
- name: `?OpenAppRegKey@@YAPEAUHKEY__@@PEBD@Z`
- size: `250`
- prototype: `HKEY __fastcall(const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010d8c`

## callees

- `0x18000b410`
- `0x18000be78`
- `0x1800111b8`
- `0x18001153c`
- `0x180011648`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001170f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001170f`

## pseudocode

```c
HKEY __fastcall OpenAppRegKey(const char *a1)
{
  const char *v1; // rcx
  bool v3; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v4; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v5[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  CHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF
  char v8[272]; // [rsp+160h] [rbp+60h] BYREF

  *(_QWORD *)v5 = 0;
  v4 = 261;
  if ( GetModuleInfo(v8, &v4, (unsigned __int64 *)v5)
    && (phkResult = 0, memset_0(SubKey, 0, 0x105u), v4 = 261, v3 = 0, FindAppRegKey(v1, SubKey, &v4, &v3, v8, v5[0]))
    && !RegOpenKeyExA((HKEY)(-(__int64)v3 - 2147483646), SubKey, 0, 1u, &phkResult) )
  {
    return phkResult;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180011648  mov     [rsp-8+arg_0], rdi
0x18001164d  push    rbp
0x18001164e  lea     rbp, [rsp-180h]
0x180011656  sub     rsp, 280h
0x18001165d  mov     rax, cs:__security_cookie
0x180011664  xor     rax, rsp
0x180011667  mov     [rbp+180h+var_10], rax
0x18001166e  mov     edi, 105h
0x180011673  mov     qword ptr [rsp+280h+var_240], 0
0x18001167c  lea     r8, [rsp+280h+var_240]; unsigned __int64 *
0x180011681  mov     [rsp+280h+var_248], rdi
0x180011686  lea     rdx, [rsp+280h+var_248]; unsigned __int64 *
0x18001168b  lea     rcx, [rbp+180h+var_120]; char *
0x18001168f  call    ?GetModuleInfo@@YA_NPEADPEA_K1@Z; GetModuleInfo(char *,unsigned __int64 *,unsigned __int64 *)
0x180011694  test    al, al
0x180011696  jz      loc_180011720
0x18001169c  mov     r8d, edi; Size
0x18001169f  mov     [rsp+280h+var_238], 0
0x1800116a8  xor     edx, edx; Val
0x1800116aa  lea     rcx, [rsp+280h+SubKey]; void *
0x1800116af  call    memset_0
0x1800116b4  mov     eax, [rsp+280h+var_240]
0x1800116b8  lea     r9, [rsp+280h+var_250]; bool *
0x1800116bd  mov     [rsp+280h+var_258], eax; unsigned int
0x1800116c1  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800116c6  lea     rax, [rbp+180h+var_120]
0x1800116ca  mov     [rsp+280h+var_248], rdi
0x1800116cf  lea     rdx, [rsp+280h+SubKey]; char *
0x1800116d4  mov     [rsp+280h+phkResult], rax; char *
0x1800116d9  mov     [rsp+280h+var_250], 0
0x1800116de  call    ?FindAppRegKey@@YA_NPEBDPEADPEA_KPEA_N0I@Z; FindAppRegKey(char const *,char *,unsigned __int64 *,bool *,char const *,uint)
0x1800116e3  test    al, al
0x1800116e5  jz      short loc_180011720
0x1800116e7  mov     al, [rsp+280h+var_250]
0x1800116eb  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x1800116f0  neg     al
0x1800116f2  mov     r9d, 1; samDesired
0x1800116f8  lea     rax, [rsp+280h+var_238]
0x1800116fd  sbb     rcx, rcx
0x180011700  mov     [rsp+280h+phkResult], rax; phkResult
0x180011705  add     rcx, 0FFFFFFFF80000002h; hKey
0x18001170c  xor     r8d, r8d; ulOptions
0x18001170f  call    cs:__imp_RegOpenKeyExA
0x180011715  test    eax, eax
0x180011717  jnz     short loc_180011720
0x180011719  mov     rax, [rsp+280h+var_238]
0x18001171e  jmp     short loc_180011722
0x180011720  xor     eax, eax
0x180011722  mov     rcx, [rbp+180h+var_10]
0x180011729  xor     rcx, rsp; StackCookie
0x18001172c  call    __security_check_cookie
0x180011731  mov     rdi, [rsp+280h+arg_0]
0x180011739  add     rsp, 280h
0x180011740  pop     rbp
0x180011741  retn
```
