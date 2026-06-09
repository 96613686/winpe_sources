# TOKEN_CACHE_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)

- ea: `0x180058e98`
- end: `0x180058f59`
- name: `?CreateCacheKey@TOKEN_CACHE_KEY@@QEAAJPEBG0K@Z`
- size: `193`
- prototype: `int(TOKEN_CACHE_KEY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180059230`

## callees

- `0x180058e98`
- `0x180059c30`

## import_xrefs

- `msvcrt!_ultow` at `0x180058f12`
- `msvcrt!_ultow` at `0x180058f12`
- `msvcrt!_wcsupr` at `0x180058eff`
- `msvcrt!_wcsupr` at `0x180058eff`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180058ef6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180058ef6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058ec5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058ec5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058ed9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058ee9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058f20`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058f34`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058ed9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058ee9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058f20`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058f34`

## pseudocode

```c
int __fastcall TOKEN_CACHE_KEY::CreateCacheKey(
        TOKEN_CACHE_KEY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int result; // eax
  wchar_t *Str; // rax
  wchar_t Buffer[40]; // [rsp+20h] [rbp-78h] BYREF

  if ( !a2 || !a3 )
    return -2147024809;
  result = STRU::Copy(this, a2);
  if ( result >= 0 )
  {
    result = STRU::Append(this, L"\\");
    if ( result >= 0 )
    {
      result = STRU::Append(this, a3);
      if ( result >= 0 )
      {
        Str = STRU::QueryStr(this);
        _wcsupr(Str);
        _ultow(a4, Buffer, 10);
        result = STRU::Append(this, Buffer);
        if ( result >= 0 )
          return STRU::Append(this, L"\\");
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180058e98  push    rbx
0x180058e9a  push    rsi
0x180058e9b  push    rdi
0x180058e9c  sub     rsp, 80h
0x180058ea3  mov     rax, cs:__security_cookie
0x180058eaa  xor     rax, rsp
0x180058ead  mov     [rsp+98h+var_28], rax
0x180058eb2  mov     esi, r9d
0x180058eb5  mov     rdi, r8
0x180058eb8  mov     rbx, rcx
0x180058ebb  test    rdx, rdx
0x180058ebe  jz      short loc_180058F3C
0x180058ec0  test    r8, r8
0x180058ec3  jz      short loc_180058F3C
0x180058ec5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180058ecb  test    eax, eax
0x180058ecd  js      short loc_180058F41
0x180058ecf  lea     rdx, asc_18005F940; "\\"
0x180058ed6  mov     rcx, rbx
0x180058ed9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180058edf  test    eax, eax
0x180058ee1  js      short loc_180058F41
0x180058ee3  mov     rdx, rdi
0x180058ee6  mov     rcx, rbx
0x180058ee9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180058eef  test    eax, eax
0x180058ef1  js      short loc_180058F41
0x180058ef3  mov     rcx, rbx
0x180058ef6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180058efc  mov     rcx, rax; String
0x180058eff  call    cs:__imp__wcsupr
0x180058f05  mov     r8d, 0Ah; Radix
0x180058f0b  lea     rdx, [rsp+98h+Buffer]; Buffer
0x180058f10  mov     ecx, esi; Value
0x180058f12  call    cs:__imp__ultow
0x180058f18  lea     rdx, [rsp+98h+Buffer]
0x180058f1d  mov     rcx, rbx
0x180058f20  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180058f26  test    eax, eax
0x180058f28  js      short loc_180058F41
0x180058f2a  lea     rdx, asc_18005F940; "\\"
0x180058f31  mov     rcx, rbx
0x180058f34  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180058f3a  jmp     short loc_180058F41
0x180058f3c  mov     eax, 80070057h
0x180058f41  mov     rcx, [rsp+98h+var_28]
0x180058f46  xor     rcx, rsp; StackCookie
0x180058f49  call    __security_check_cookie
0x180058f4e  add     rsp, 80h
0x180058f55  pop     rdi
0x180058f56  pop     rsi
0x180058f57  pop     rbx
0x180058f58  retn
```
