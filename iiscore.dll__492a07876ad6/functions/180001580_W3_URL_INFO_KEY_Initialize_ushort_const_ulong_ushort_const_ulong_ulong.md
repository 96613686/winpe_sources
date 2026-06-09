# W3_URL_INFO_KEY::Initialize(ushort const *,ulong,ushort const *,ulong,ulong)

- ea: `0x180001580`
- end: `0x180001645`
- name: `?Initialize@W3_URL_INFO_KEY@@QEAAJPEBGK0KK@Z`
- size: `197`
- prototype: `__int64 __fastcall(W3_URL_INFO_KEY *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002db0`
- `0x180022a10`

## callees

- `0x180001580`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180001635`
- `msvcrt!_wcsupr` at `0x180001635`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001625`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001625`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800015b2`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800015d1`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800015b2`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800015d1`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180001610`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180001610`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800015eb`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800015eb`

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
0x180001580  push    rbx
0x180001582  push    rbp
0x180001583  push    rsi
0x180001584  push    rdi
0x180001585  push    r14
0x180001587  sub     rsp, 20h
0x18000158b  mov     eax, [rsp+48h+arg_28]
0x18000158f  lea     rsi, [rcx+10h]
0x180001593  mov     [rcx+8], eax
0x180001596  mov     ebp, r8d
0x180001599  mov     r14, rdx
0x18000159c  mov     rbx, rcx
0x18000159f  mov     rcx, rsi
0x1800015a2  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x1800015a9  mov     r8d, 18h
0x1800015af  mov     rdi, r9
0x1800015b2  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800015b9  nop     dword ptr [rax+rax+00h]
0x1800015be  test    eax, eax
0x1800015c0  js      short loc_1800015FB
0x1800015c2  mov     r8d, [rsp+48h+arg_20]
0x1800015c7  lea     rcx, [rbx+130h]
0x1800015ce  mov     rdx, rdi
0x1800015d1  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800015d8  nop     dword ptr [rax+rax+00h]
0x1800015dd  test    eax, eax
0x1800015df  js      short loc_1800015FB
0x1800015e1  lea     rdx, [rbx+130h]
0x1800015e8  mov     rcx, rsi
0x1800015eb  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800015f2  nop     dword ptr [rax+rax+00h]
0x1800015f7  test    eax, eax
0x1800015f9  jns     short loc_180001607
0x1800015fb  add     rsp, 20h
0x1800015ff  pop     r14
0x180001601  pop     rdi
0x180001602  pop     rsi
0x180001603  pop     rbp
0x180001604  pop     rbx
0x180001605  retn
0x180001607  mov     r8d, ebp
0x18000160a  mov     rdx, r14
0x18000160d  mov     rcx, rsi
0x180001610  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180001617  nop     dword ptr [rax+rax+00h]
0x18000161c  mov     ebx, eax
0x18000161e  test    eax, eax
0x180001620  js      short loc_1800015FB
0x180001622  mov     rcx, rsi
0x180001625  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000162c  nop     dword ptr [rax+rax+00h]
0x180001631  lea     rcx, [rax+30h]; String
0x180001635  call    cs:__imp__wcsupr
0x18000163c  nop     dword ptr [rax+rax+00h]
0x180001641  mov     eax, ebx
0x180001643  jmp     short loc_1800015FB
```
