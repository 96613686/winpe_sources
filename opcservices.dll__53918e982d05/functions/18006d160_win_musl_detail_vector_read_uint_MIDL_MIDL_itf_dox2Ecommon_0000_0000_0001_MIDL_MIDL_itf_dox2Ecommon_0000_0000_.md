# win_musl::detail::vector_read<uint>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)

- ea: `0x18006d160`
- end: `0x18006d287`
- name: `??$vector_read@I@detail@win_musl@@YAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z`
- size: `295`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800323ec`
- `0x18006c4a0`
- `0x18006cbd0`

## callees

- `0x18002db70`
- `0x18006d160`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18006d1b5`
- `msvcrt!memmove_s` at `0x18006d1b5`

## string_xrefs

- `0x18006d24d`: `win_musl::detail::vector_read`

## pseudocode

```c
__int64 __fastcall win_musl::detail::vector_read<unsigned int>(unsigned int *a1, _OWORD *a2, _BYTE *a3)
{
  __int64 v3; // rbp
  char *v6; // rdi
  char *v7; // rcx
  char *v8; // rdx
  __int64 result; // rax
  unsigned int Destination; // [rsp+40h] [rbp-F8h] BYREF
  __int128 v11; // [rsp+48h] [rbp-F0h]
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-D8h] BYREF

  v3 = *a1;
  if ( (unsigned int)v3 < 4 )
  {
    result = 0;
    *a2 = *(_OWORD *)a1;
    *a3 = 1;
  }
  else
  {
    v6 = (char *)*((_QWORD *)a1 + 1);
    Destination = 0;
    memmove_s(&Destination, 4u, v6, 4u);
    if ( !v6 || (v7 = v6 + 4, v8 = &v6[v3], &v6[v3] == v6 + 4) )
    {
      v11 = 0u;
    }
    else
    {
      if ( v6 > v7 || v7 > v8 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0xABu,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expres"
                                                  "sion (vector_begin(vector) + sizeof(T))");
        throw (SplException::THResultException *)pExceptionObject;
      }
      *((_QWORD *)&v11 + 1) = v6 + 4;
      *(_QWORD *)&v11 = (unsigned int)((_DWORD)v8 - (_DWORD)v7);
    }
    *a2 = v11;
    if ( a3 )
      *a3 = 0;
    return Destination;
  }
  return result;
}

```

## disassembly

```asm
0x18006d160  mov     r11, rsp
0x18006d163  push    rbx
0x18006d164  push    rbp
0x18006d165  push    rsi
0x18006d166  sub     rsp, 120h
0x18006d16d  mov     rax, cs:__security_cookie
0x18006d174  xor     rax, rsp
0x18006d177  mov     [rsp+138h+var_38], rax
0x18006d17f  mov     ebp, [rcx]
0x18006d181  mov     rbx, r8
0x18006d184  mov     rsi, rdx
0x18006d187  cmp     ebp, 4
0x18006d18a  jb      loc_18006D233
0x18006d190  mov     [r11-20h], rdi
0x18006d194  mov     r9d, 4; SourceSize
0x18006d19a  mov     rdi, [rcx+8]
0x18006d19e  mov     edx, r9d; DestinationSize
0x18006d1a1  mov     [r11-28h], r14
0x18006d1a5  lea     rcx, [rsp+138h+Destination]; Destination
0x18006d1aa  xor     r14d, r14d
0x18006d1ad  mov     r8, rdi; Source
0x18006d1b0  mov     [rsp+138h+Destination], r14d
0x18006d1b5  call    cs:__imp_memmove_s
0x18006d1bb  test    rdi, rdi
0x18006d1be  jz      short loc_18006D227
0x18006d1c0  lea     rcx, [rdi+4]
0x18006d1c4  lea     rdx, [rdi+rbp]
0x18006d1c8  cmp     rdx, rcx
0x18006d1cb  jz      short loc_18006D227
0x18006d1cd  cmp     rdi, rcx
0x18006d1d0  ja      short loc_18006D241
0x18006d1d2  cmp     rcx, rdx
0x18006d1d5  ja      short loc_18006D241
0x18006d1d7  sub     edx, ecx
0x18006d1d9  mov     qword ptr [rsp+138h+var_F0+8], rcx
0x18006d1de  xor     eax, eax
0x18006d1e0  mov     dword ptr [rsp+138h+var_F0], edx
0x18006d1e4  mov     dword ptr [rsp+138h+var_F0+4], eax
0x18006d1e8  movups  xmm0, [rsp+138h+var_F0]
0x18006d1ed  movups  xmmword ptr [rsi], xmm0
0x18006d1f0  test    rbx, rbx
0x18006d1f3  jz      short loc_18006D1F8
0x18006d1f5  mov     [rbx], r14b
0x18006d1f8  mov     eax, [rsp+138h+Destination]
0x18006d1fc  mov     rdi, [rsp+138h+var_20]
0x18006d204  mov     r14, [rsp+138h+var_28]
0x18006d20c  mov     rcx, [rsp+138h+var_38]
0x18006d214  xor     rcx, rsp; StackCookie
0x18006d217  call    __security_check_cookie
0x18006d21c  add     rsp, 120h
0x18006d223  pop     rsi
0x18006d224  pop     rbp
0x18006d225  pop     rbx
0x18006d226  retn
0x18006d227  mov     qword ptr [rsp+138h+var_F0], r14
0x18006d22c  mov     qword ptr [rsp+138h+var_F0+8], r14
0x18006d231  jmp     short loc_18006D1E8
0x18006d233  movaps  xmm0, xmmword ptr [rcx]
0x18006d236  xor     eax, eax
0x18006d238  movups  xmmword ptr [rdx], xmm0
0x18006d23b  mov     byte ptr [r8], 1
0x18006d23f  jmp     short loc_18006D20C
0x18006d241  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x18006d248  mov     [rsp+138h+var_108], rax; struct win_musl::TStringEllipseBase *
0x18006d24d  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x18006d254  mov     [rsp+138h+var_110], 80070057h; unsigned int
0x18006d25c  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x18006d263  lea     rcx, [rsp+138h+pExceptionObject]; this
0x18006d268  mov     [rsp+138h+var_118], 0ABh; unsigned int
0x18006d270  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006d275  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006d27c  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18006d281  call    _CxxThrowException_0
```
