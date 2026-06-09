# TLMString<192,64,32767>::GrowString(uint)

- ea: `0x180002d80`
- end: `0x180002eae`
- name: `?GrowString@?$TLMString@$0MA@$0EA@$0HPPP@@@EEAAXI@Z`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003970`
- `0x180004f60`
- `0x1800071c0`

## callees

- `0x180002d80`
- `0x180010b38`
- `0x180011135`
- `0x18001e194`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002e74`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002e74`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180002e05`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180002e05`

## string_xrefs

- `0x180002dad`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180002e18`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall TLMString<192,64,32767>::GrowString(__int64 a1, unsigned int a2)
{
  unsigned int v2; // ebx
  unsigned int v4; // ecx
  unsigned __int64 v5; // rax
  __int64 v6; // rcx
  void *v7; // rsi
  unsigned int v8; // eax
  unsigned __int64 v9; // rax
  unsigned int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  v2 = a2;
  if ( a2 > *(_DWORD *)(a1 + 16) )
  {
    if ( a2 > 0x7FFF )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0xCE,
        v10);
    v4 = 64;
    if ( *(_DWORD *)(a1 + 16) < 0x40u )
      v4 = *(_DWORD *)(a1 + 16);
    if ( a2 % v4 )
      v2 = v4 - a2 % v4 + a2;
    v5 = 2LL * v2;
    if ( v5 > 0xFFFFFFFF )
    {
      pExceptionObject = -2147024362;
      throw (long *)&pExceptionObject;
    }
    v6 = *(_QWORD *)(a1 + 8);
    if ( v6 == a1 + 24 )
      v6 = 0;
    v7 = (void *)_o_realloc(v6, (unsigned int)v5);
    if ( !v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0xCE,
        v10);
    v8 = *(_DWORD *)(a1 + 20);
    if ( v8 + 1 < v8 || (v9 = 2LL * (v8 + 1), v9 > 0xFFFFFFFF) )
    {
      free(v7);
      pExceptionObject = -2147024362;
      throw (long *)&pExceptionObject;
    }
    if ( *(_QWORD *)(a1 + 8) == a1 + 24 )
      memcpy_0(v7, (const void *)(a1 + 24), (unsigned int)v9);
    *(_QWORD *)(a1 + 8) = v7;
    *(_DWORD *)(a1 + 16) = v2;
  }
}

```

## disassembly

```asm
0x180002d80  mov     [rsp+arg_0], rbx
0x180002d85  mov     [rsp+arg_10], rbp
0x180002d8a  push    rsi
0x180002d8b  push    rdi
0x180002d8c  push    r14; unsigned int
0x180002d8e  sub     rsp, 20h
0x180002d92  mov     ebx, edx
0x180002d94  mov     rdi, rcx
0x180002d97  cmp     edx, [rcx+10h]
0x180002d9a  jbe     loc_180002E5E
0x180002da0  cmp     edx, 7FFFh
0x180002da6  jbe     short loc_180002DC4
0x180002da8  mov     rcx, [rsp+38h]; this
0x180002dad  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x180002db4  mov     r9d, 0CEh; char *
0x180002dba  lea     edx, [r9+4Bh]; void *
0x180002dbe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180002dc4  mov     ecx, 40h ; '@'
0x180002dc9  mov     eax, ebx
0x180002dcb  cmp     [rdi+10h], ecx
0x180002dce  cmovb   ecx, [rdi+10h]
0x180002dd2  xor     edx, edx
0x180002dd4  div     ecx
0x180002dd6  test    edx, edx
0x180002dd8  jz      short loc_180002DDE
0x180002dda  sub     ecx, edx
0x180002ddc  add     ebx, ecx
0x180002dde  mov     eax, ebx
0x180002de0  mov     r14d, 0FFFFFFFFh
0x180002de6  add     rax, rax
0x180002de9  cmp     rax, r14
0x180002dec  ja      loc_180002E94
0x180002df2  mov     rcx, [rdi+8]
0x180002df6  lea     rbp, [rdi+18h]
0x180002dfa  mov     edx, eax
0x180002dfc  xor     eax, eax
0x180002dfe  cmp     rcx, rbp
0x180002e01  cmovz   rcx, rax
0x180002e05  call    cs:__imp__o_realloc
0x180002e0b  mov     rsi, rax
0x180002e0e  test    rax, rax
0x180002e11  jnz     short loc_180002E2F
0x180002e13  mov     rcx, [rsp+38h]; this
0x180002e18  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x180002e1f  mov     r9d, 0CEh; char *
0x180002e25  lea     edx, [r9+62h]; void *
0x180002e29  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180002e2f  mov     eax, [rdi+14h]
0x180002e32  lea     ecx, [rax+1]
0x180002e35  cmp     ecx, eax
0x180002e37  jb      short loc_180002E71
0x180002e39  mov     eax, ecx
0x180002e3b  add     rax, rax
0x180002e3e  cmp     rax, r14
0x180002e41  ja      short loc_180002E71
0x180002e43  cmp     [rdi+8], rbp
0x180002e47  jnz     short loc_180002E57
0x180002e49  mov     r8d, eax; Size
0x180002e4c  mov     rdx, rbp; Src
0x180002e4f  mov     rcx, rsi; void *
0x180002e52  call    memcpy_0
0x180002e57  mov     [rdi+8], rsi
0x180002e5b  mov     [rdi+10h], ebx
0x180002e5e  mov     rbx, [rsp+38h+arg_0]
0x180002e63  mov     rbp, [rsp+38h+arg_10]
0x180002e68  add     rsp, 20h
0x180002e6c  pop     r14
0x180002e6e  pop     rdi
0x180002e6f  pop     rsi
0x180002e70  retn
0x180002e71  mov     rcx, rsi; Block
0x180002e74  call    cs:__imp_free
0x180002e7a  lea     rdx, _TI1J; pThrowInfo
0x180002e81  mov     [rsp+38h+pExceptionObject], 80070216h
0x180002e89  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180002e8e  call    _CxxThrowException_0
0x180002e94  lea     rdx, _TI1J; pThrowInfo
0x180002e9b  mov     [rsp+38h+pExceptionObject], 80070216h
0x180002ea3  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180002ea8  call    _CxxThrowException_0
```
