# W3_URL_INFO_KEY::Initialize(ushort const *,ulong,ushort const *,ulong,ulong)

- ea: `0x180001550`
- end: `0x1800015f0`
- name: `?Initialize@W3_URL_INFO_KEY@@QEAAJPEBGK0KK@Z`
- size: `160`
- prototype: `__int64 __fastcall(W3_URL_INFO_KEY *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002bf0`
- `0x180020e20`

## callees

- `0x180001550`

## import_xrefs

- `msvcrt!_wcsupr` at `0x1800015e6`
- `msvcrt!_wcsupr` at `0x1800015e6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800015dc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800015dc`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180001582`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000159b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180001582`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000159b`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800015cd`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800015cd`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800015af`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800015af`

## pseudocode

```c
int __fastcall W3_URL_INFO_KEY::Initialize(
        W3_URL_INFO_KEY *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6)
{
  STRU *v6; // rsi
  int result; // eax
  int v12; // ebx
  unsigned __int16 *Str; // rax

  v6 = (W3_URL_INFO_KEY *)((char *)this + 16);
  *((_DWORD *)this + 2) = a6;
  result = STRU::Copy((W3_URL_INFO_KEY *)((char *)this + 16), L"MACHINE/WEBROOT/APPHOST/", 0x18u);
  if ( result >= 0 )
  {
    result = STRU::Copy((W3_URL_INFO_KEY *)((char *)this + 304), a4, a5);
    if ( result >= 0 )
    {
      result = STRU::Append(v6, (W3_URL_INFO_KEY *)((char *)this + 304));
      if ( result >= 0 )
      {
        result = STRU::Append(v6, a2, a3);
        v12 = result;
        if ( result >= 0 )
        {
          Str = STRU::QueryStr(v6);
          _wcsupr(Str + 24);
          return v12;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001550  push    rbx
0x180001552  push    rbp
0x180001553  push    rsi
0x180001554  push    rdi
0x180001555  push    r14
0x180001557  sub     rsp, 20h
0x18000155b  mov     eax, [rsp+48h+arg_28]
0x18000155f  lea     rsi, [rcx+10h]
0x180001563  mov     [rcx+8], eax
0x180001566  mov     ebp, r8d
0x180001569  mov     r14, rdx
0x18000156c  mov     rbx, rcx
0x18000156f  mov     rcx, rsi
0x180001572  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x180001579  mov     r8d, 18h
0x18000157f  mov     rdi, r9
0x180001582  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180001588  test    eax, eax
0x18000158a  js      short loc_1800015B9
0x18000158c  mov     r8d, [rsp+48h+arg_20]
0x180001591  lea     rcx, [rbx+130h]
0x180001598  mov     rdx, rdi
0x18000159b  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800015a1  test    eax, eax
0x1800015a3  js      short loc_1800015B9
0x1800015a5  lea     rdx, [rbx+130h]
0x1800015ac  mov     rcx, rsi
0x1800015af  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800015b5  test    eax, eax
0x1800015b7  jns     short loc_1800015C4
0x1800015b9  add     rsp, 20h
0x1800015bd  pop     r14
0x1800015bf  pop     rdi
0x1800015c0  pop     rsi
0x1800015c1  pop     rbp
0x1800015c2  pop     rbx
0x1800015c3  retn
0x1800015c4  mov     r8d, ebp
0x1800015c7  mov     rdx, r14
0x1800015ca  mov     rcx, rsi
0x1800015cd  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x1800015d3  mov     ebx, eax
0x1800015d5  test    eax, eax
0x1800015d7  js      short loc_1800015B9
0x1800015d9  mov     rcx, rsi
0x1800015dc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800015e2  lea     rcx, [rax+30h]; String
0x1800015e6  call    cs:__imp__wcsupr
0x1800015ec  mov     eax, ebx
0x1800015ee  jmp     short loc_1800015B9
```
