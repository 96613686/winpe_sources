# UL_RESPONSE_CACHE_KEY::CreateCacheKey(ushort const *,ulong,ushort const *,ushort const *)

- ea: `0x1800029c4`
- end: `0x180002a43`
- name: `?CreateCacheKey@UL_RESPONSE_CACHE_KEY@@QEAAJPEBGK00@Z`
- size: `127`
- prototype: `int __fastcall(UL_RESPONSE_CACHE_KEY *this, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800020d0`

## callees

- `0x1800029c4`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180002a1e`
- `msvcrt!_wcsupr` at `0x180002a30`
- `msvcrt!_wcsupr` at `0x180002a1e`
- `msvcrt!_wcsupr` at `0x180002a30`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002a15`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002a27`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002a15`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002a27`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800029db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800029ef`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002a08`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800029db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800029ef`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002a08`

## pseudocode

```c
int __fastcall UL_RESPONSE_CACHE_KEY::CreateCacheKey(
        UL_RESPONSE_CACHE_KEY *this,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  int result; // eax
  wchar_t *Str; // rax
  wchar_t *v9; // rax

  *((_DWORD *)this + 138) = a3;
  result = STRU::Copy(this, a2);
  if ( result >= 0 )
  {
    result = STRU::Copy((UL_RESPONSE_CACHE_KEY *)((char *)this + 184), a4);
    if ( result >= 0 )
    {
      result = STRU::Copy((UL_RESPONSE_CACHE_KEY *)((char *)this + 368), a5);
      if ( result >= 0 )
      {
        Str = STRU::QueryStr(this);
        _wcsupr(Str);
        v9 = STRU::QueryStr((UL_RESPONSE_CACHE_KEY *)((char *)this + 368));
        _wcsupr(v9);
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800029c4  mov     [rsp+arg_0], rbx
0x1800029c9  push    rdi
0x1800029ca  sub     rsp, 20h
0x1800029ce  mov     rdi, r9
0x1800029d1  mov     [rcx+228h], r8d
0x1800029d8  mov     rbx, rcx
0x1800029db  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800029e1  test    eax, eax
0x1800029e3  js      short loc_180002A38
0x1800029e5  lea     rcx, [rbx+0B8h]
0x1800029ec  mov     rdx, rdi
0x1800029ef  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800029f5  test    eax, eax
0x1800029f7  js      short loc_180002A38
0x1800029f9  mov     rdx, [rsp+28h+arg_20]
0x1800029fe  lea     rdi, [rbx+170h]
0x180002a05  mov     rcx, rdi
0x180002a08  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002a0e  test    eax, eax
0x180002a10  js      short loc_180002A38
0x180002a12  mov     rcx, rbx
0x180002a15  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002a1b  mov     rcx, rax; String
0x180002a1e  call    cs:__imp__wcsupr
0x180002a24  mov     rcx, rdi
0x180002a27  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002a2d  mov     rcx, rax; String
0x180002a30  call    cs:__imp__wcsupr
0x180002a36  xor     eax, eax
0x180002a38  mov     rbx, [rsp+28h+arg_0]
0x180002a3d  add     rsp, 20h
0x180002a41  pop     rdi
0x180002a42  retn
```
