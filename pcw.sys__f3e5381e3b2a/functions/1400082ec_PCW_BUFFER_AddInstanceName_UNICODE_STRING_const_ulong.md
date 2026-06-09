# _PCW_BUFFER::AddInstanceName(_UNICODE_STRING const *,ulong)

- ea: `0x1400082ec`
- end: `0x1400083db`
- name: `?AddInstanceName@_PCW_BUFFER@@QEAAJPEBU_UNICODE_STRING@@K@Z`
- size: `239`
- prototype: `__int64 __fastcall(_PCW_BUFFER *__hidden this, const struct _UNICODE_STRING *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140008b6c`
- `0x14000da40`

## callees

- `0x140001370`
- `0x1400082ec`
- `0x140008ee8`
- `0x140008fb0`
- `0x140008fd0`

## pseudocode

```c
__int64 __fastcall _PCW_BUFFER::AddInstanceName(_PCW_BUFFER *this, const struct _UNICODE_STRING *a2, int a3)
{
  const struct _UNICODE_STRING *v4; // rcx
  __int64 result; // rax
  char *v8; // rbx
  __int16 v9; // [rsp+20h] [rbp-48h] BYREF
  void *v10; // [rsp+28h] [rbp-40h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF
  int v12; // [rsp+38h] [rbp-30h]

  v10 = 0;
  v11 = 0;
  v4 = (const struct _UNICODE_STRING *)*((_QWORD *)this + 5);
  v12 = 0;
  if ( !PcwpWildcardMatch(v4, a2) )
    return 0;
  LODWORD(v11) = (a2->Length + 19) & 0xFFFFFFF8;
  result = _PCW_BUFFER::ReserveSpaceVoid(this, &v10, v11);
  if ( (int)result < 0 )
    return result;
  v8 = (char *)v10;
  if ( !v10 )
    return 0;
  HIDWORD(v11) = a3;
  v9 = 0;
  result = PcwpWriteToUserBuffer(v10, &v11, 8u);
  if ( (int)result >= 0 )
  {
    result = PcwpWriteToUserBuffer(v8 + 8, a2->Buffer, a2->Length);
    if ( (int)result >= 0 )
    {
      result = PcwpWriteToUserBuffer(&v8[2 * ((unsigned __int64)a2->Length >> 1) + 8], &v9, 2u);
      if ( (int)result >= 0 )
      {
        ++*((_DWORD *)this + 6);
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400082ec  mov     [rsp+arg_18], rbx
0x1400082f1  push    rbp
0x1400082f2  push    rsi
0x1400082f3  push    rdi
0x1400082f4  sub     rsp, 50h
0x1400082f8  mov     rax, cs:__security_cookie
0x1400082ff  xor     rax, rsp
0x140008302  mov     [rsp+68h+var_28], rax
0x140008307  xor     eax, eax
0x140008309  mov     [rsp+68h+var_40], 0
0x140008312  mov     rdi, rcx
0x140008315  mov     [rsp+68h+var_38], rax
0x14000831a  mov     rcx, [rcx+28h]; struct _UNICODE_STRING *
0x14000831e  mov     ebp, r8d
0x140008321  mov     [rsp+68h+var_30], eax
0x140008325  mov     rsi, rdx
0x140008328  call    ?PcwpWildcardMatch@@YA_NPEBU_UNICODE_STRING@@0@Z; PcwpWildcardMatch(_UNICODE_STRING const *,_UNICODE_STRING const *)
0x14000832d  test    al, al
0x14000832f  jz      loc_1400083BB
0x140008335  movzx   r8d, word ptr [rsi]
0x140008339  lea     rdx, [rsp+68h+var_40]; void **
0x14000833e  add     r8d, 13h
0x140008342  mov     rcx, rdi; this
0x140008345  and     r8d, 0FFFFFFF8h; unsigned int
0x140008349  mov     dword ptr [rsp+68h+var_38], r8d
0x14000834e  call    ?ReserveSpaceVoid@_PCW_BUFFER@@AEAAJPEAPEAXK@Z; _PCW_BUFFER::ReserveSpaceVoid(void * *,ulong)
0x140008353  test    eax, eax
0x140008355  js      short loc_1400083BD
0x140008357  mov     rbx, [rsp+68h+var_40]
0x14000835c  test    rbx, rbx
0x14000835f  jz      short loc_1400083BB
0x140008361  xor     eax, eax
0x140008363  mov     dword ptr [rsp+68h+var_38+4], ebp
0x140008367  lea     rdx, [rsp+68h+var_38]; void *
0x14000836c  mov     [rsp+68h+var_48], ax
0x140008371  mov     rcx, rbx; void *
0x140008374  lea     r8d, [rax+8]; unsigned int
0x140008378  call    ?PcwpWriteToUserBuffer@@YAJPEAXPEBXK@Z; PcwpWriteToUserBuffer(void *,void const *,ulong)
0x14000837d  test    eax, eax
0x14000837f  js      short loc_1400083BD
0x140008381  movzx   r8d, word ptr [rsi]; unsigned int
0x140008385  lea     rcx, [rbx+8]; void *
0x140008389  mov     rdx, [rsi+8]; void *
0x14000838d  call    ?PcwpWriteToUserBuffer@@YAJPEAXPEBXK@Z; PcwpWriteToUserBuffer(void *,void const *,ulong)
0x140008392  test    eax, eax
0x140008394  js      short loc_1400083BD
0x140008396  movzx   eax, word ptr [rsi]
0x140008399  lea     rdx, [rsp+68h+var_48]; void *
0x14000839e  shr     rax, 1
0x1400083a1  mov     r8d, 2; unsigned int
0x1400083a7  add     rax, 4
0x1400083ab  lea     rcx, [rbx+rax*2]; void *
0x1400083af  call    ?PcwpWriteToUserBuffer@@YAJPEAXPEBXK@Z; PcwpWriteToUserBuffer(void *,void const *,ulong)
0x1400083b4  test    eax, eax
0x1400083b6  js      short loc_1400083BD
0x1400083b8  inc     dword ptr [rdi+18h]
0x1400083bb  xor     eax, eax
0x1400083bd  mov     rcx, [rsp+68h+var_28]
0x1400083c2  xor     rcx, rsp; StackCookie
0x1400083c5  call    __security_check_cookie
0x1400083ca  mov     rbx, [rsp+68h+arg_18]
0x1400083d2  add     rsp, 50h
0x1400083d6  pop     rdi
0x1400083d7  pop     rsi
0x1400083d8  pop     rbp
0x1400083d9  retn
```
