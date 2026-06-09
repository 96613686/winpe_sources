# VARY_BY_CACHE_KEY::CreateCacheKey(ushort const *,ulong,ushort const *,ushort const *)

- ea: `0x180004a74`
- end: `0x180004b05`
- name: `?CreateCacheKey@VARY_BY_CACHE_KEY@@QEAAJPEBGK00@Z`
- size: `145`
- prototype: `int __fastcall(VARY_BY_CACHE_KEY *this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004778`

## callees

- `0x180004a74`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180004ae2`
- `msvcrt!_wcsupr` at `0x180004af4`
- `msvcrt!_wcsupr` at `0x180004ae2`
- `msvcrt!_wcsupr` at `0x180004af4`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180004ab3`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180004ab3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004aa0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004aa0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004ad9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004aeb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004ad9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004aeb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004a90`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004acc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004a90`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004acc`

## pseudocode

```c
int __fastcall VARY_BY_CACHE_KEY::CreateCacheKey(
        VARY_BY_CACHE_KEY *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  int result; // eax
  wchar_t *Str; // rax
  wchar_t *v11; // rax

  result = STRU::Copy(this, L"MACHINE/WEBROOT/APPHOST/");
  if ( result >= 0 )
  {
    result = STRU::Append(this, a4);
    if ( result >= 0 )
    {
      result = STRU::Append(this, a2, a3);
      if ( result >= 0 )
      {
        result = STRU::Copy((VARY_BY_CACHE_KEY *)((char *)this + 312), a5);
        if ( result >= 0 )
        {
          Str = STRU::QueryStr(this);
          _wcsupr(Str);
          v11 = STRU::QueryStr((VARY_BY_CACHE_KEY *)((char *)this + 312));
          _wcsupr(v11);
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004a74  push    rbx
0x180004a76  push    rbp
0x180004a77  push    rsi
0x180004a78  push    rdi
0x180004a79  sub     rsp, 28h
0x180004a7d  mov     rbp, rdx
0x180004a80  mov     rdi, r9
0x180004a83  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x180004a8a  mov     esi, r8d
0x180004a8d  mov     rbx, rcx
0x180004a90  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004a96  test    eax, eax
0x180004a98  js      short loc_180004AFC
0x180004a9a  mov     rdx, rdi
0x180004a9d  mov     rcx, rbx
0x180004aa0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004aa6  test    eax, eax
0x180004aa8  js      short loc_180004AFC
0x180004aaa  mov     r8d, esi
0x180004aad  mov     rdx, rbp
0x180004ab0  mov     rcx, rbx
0x180004ab3  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180004ab9  test    eax, eax
0x180004abb  js      short loc_180004AFC
0x180004abd  mov     rdx, [rsp+48h+arg_20]
0x180004ac2  lea     rdi, [rbx+138h]
0x180004ac9  mov     rcx, rdi
0x180004acc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004ad2  test    eax, eax
0x180004ad4  js      short loc_180004AFC
0x180004ad6  mov     rcx, rbx
0x180004ad9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004adf  mov     rcx, rax; String
0x180004ae2  call    cs:__imp__wcsupr
0x180004ae8  mov     rcx, rdi
0x180004aeb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004af1  mov     rcx, rax; String
0x180004af4  call    cs:__imp__wcsupr
0x180004afa  xor     eax, eax
0x180004afc  add     rsp, 28h
0x180004b00  pop     rdi
0x180004b01  pop     rsi
0x180004b02  pop     rbp
0x180004b03  pop     rbx
0x180004b04  retn
```
