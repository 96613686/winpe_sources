# DxgAppCompat::CompatValue(char const *,unsigned __int64 *)

- ea: `0x180010ce8`
- end: `0x180010d84`
- name: `?CompatValue@DxgAppCompat@@YAHPEBDPEA_K@Z`
- size: `156`
- prototype: `__int64 __fastcall(DxgAppCompat *__hidden this, const char *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ece4`

## callees

- `0x18000b410`
- `0x18000be78`
- `0x180010ae0`
- `0x180010ce8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180010d4e`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180010d4e`

## pseudocode

```c
__int64 __fastcall DxgAppCompat::CompatValue(DxgAppCompat *this, char *a2, unsigned __int64 *a3)
{
  char *v5; // r9
  char v7[16]; // [rsp+20h] [rbp-98h] BYREF
  char String[112]; // [rsp+30h] [rbp-88h] BYREF

  memset_0(String, 0, 0x64u);
  *(_QWORD *)v7 = 100;
  if ( !(unsigned int)DxgAppCompat::CompatString(this, v7, String, v5) )
    return 0;
  if ( a2 )
  {
    if ( *(_QWORD *)v7 <= 0x64u )
      *(_QWORD *)a2 = atoi(String);
  }
  return 1;
}

```

## disassembly

```asm
0x180010ce8  mov     [rsp+arg_10], rbx
0x180010ced  push    rdi
0x180010cee  sub     rsp, 0B0h
0x180010cf5  mov     rax, cs:__security_cookie
0x180010cfc  xor     rax, rsp
0x180010cff  mov     [rsp+0B8h+var_18], rax
0x180010d07  mov     rdi, rdx
0x180010d0a  mov     rbx, rcx
0x180010d0d  xor     edx, edx; Val
0x180010d0f  lea     rcx, [rsp+0B8h+String]; void *
0x180010d14  lea     r8d, [rdx+64h]; Size
0x180010d18  call    memset_0
0x180010d1d  lea     r8, [rsp+0B8h+String]; unsigned __int64 *
0x180010d22  mov     qword ptr [rsp+0B8h+var_98], 64h ; 'd'; bool
0x180010d2b  lea     rdx, [rsp+0B8h+var_98]; char *
0x180010d30  mov     rcx, rbx; this
0x180010d33  call    ?CompatString@DxgAppCompat@@YAHPEBDPEA_KPEAD_N@Z; DxgAppCompat::CompatString(char const *,unsigned __int64 *,char *,bool)
0x180010d38  test    eax, eax
0x180010d3a  jz      short loc_180010D61
0x180010d3c  test    rdi, rdi
0x180010d3f  jz      short loc_180010D5A
0x180010d41  cmp     qword ptr [rsp+0B8h+var_98], 64h ; 'd'
0x180010d47  ja      short loc_180010D5A
0x180010d49  lea     rcx, [rsp+0B8h+String]; String
0x180010d4e  call    cs:__imp_atoi
0x180010d54  movsxd  rcx, eax
0x180010d57  mov     [rdi], rcx
0x180010d5a  mov     eax, 1
0x180010d5f  jmp     short loc_180010D63
0x180010d61  xor     eax, eax
0x180010d63  mov     rcx, [rsp+0B8h+var_18]
0x180010d6b  xor     rcx, rsp; StackCookie
0x180010d6e  call    __security_check_cookie
0x180010d73  mov     rbx, [rsp+0B8h+arg_10]
0x180010d7b  add     rsp, 0B0h
0x180010d82  pop     rdi
0x180010d83  retn
```
