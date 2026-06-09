# win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)

- ea: `0x18006d010`
- end: `0x18006d156`
- name: `??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z`
- size: `326`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006bc18`
- `0x18006be28`
- `0x18006cbd0`
- `0x18006e1e8`
- `0x180097a84`

## callees

- `0x18002db70`
- `0x18006d010`
- `0x1800cd6fc`
- `0x180110f58`
- `0x1801178f0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18006d060`
- `msvcrt!memmove_s` at `0x18006d060`

## string_xrefs

- `0x18006d10d`: `win_musl::detail::vector_read`

## pseudocode

```c
__int64 __fastcall win_musl::detail::vector_read<unsigned __int64>(unsigned int *a1, _OWORD *a2, _BYTE *a3)
{
  __int64 v3; // r14
  char *v6; // rbx
  char *v7; // rcx
  char *v8; // rdx
  __int64 result; // rax
  __int64 Destination; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v11; // [rsp+50h] [rbp-B0h]
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = *a1;
  if ( (unsigned int)v3 < 8 )
  {
    result = 0;
    *a2 = *(_OWORD *)a1;
    *a3 = 1;
  }
  else
  {
    v6 = (char *)*((_QWORD *)a1 + 1);
    Destination = 0;
    memmove_s(&Destination, 8u, v6, 8u);
    if ( !v6 || (v7 = v6 + 8, v8 = &v6[v3], &v6[v3] == v6 + 8) )
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
      *((_QWORD *)&v11 + 1) = v6 + 8;
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
0x18006d010  push    rbp
0x18006d012  push    rbx
0x18006d013  push    rsi
0x18006d014  push    rdi
0x18006d015  push    r14
0x18006d017  lea     rbp, [rsp-10h]
0x18006d01c  sub     rsp, 110h
0x18006d023  mov     rax, cs:__security_cookie
0x18006d02a  xor     rax, rsp
0x18006d02d  mov     [rbp+30h+var_30], rax
0x18006d031  mov     r14d, [rcx]
0x18006d034  mov     rsi, rdx
0x18006d037  mov     edx, 8; DestinationSize
0x18006d03c  mov     rdi, r8
0x18006d03f  cmp     r14d, edx
0x18006d042  jb      loc_18006D0F2
0x18006d048  mov     rbx, [rcx+8]
0x18006d04c  mov     r9d, edx; SourceSize
0x18006d04f  mov     r8, rbx; Source
0x18006d052  mov     [rsp+130h+Destination], 0
0x18006d05b  lea     rcx, [rsp+130h+Destination]; Destination
0x18006d060  call    cs:__imp_memmove_s
0x18006d066  test    rbx, rbx
0x18006d069  jz      short loc_18006D0DE
0x18006d06b  lea     rcx, [rbx+8]
0x18006d06f  lea     rdx, [rbx+r14]
0x18006d073  cmp     rdx, rcx
0x18006d076  jz      short loc_18006D0DE
0x18006d078  cmp     rbx, rcx
0x18006d07b  ja      loc_18006D101
0x18006d081  cmp     rcx, rdx
0x18006d084  ja      short loc_18006D101
0x18006d086  sub     edx, ecx
0x18006d088  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x18006d08d  xor     eax, eax
0x18006d08f  mov     dword ptr [rsp+130h+var_E0], edx
0x18006d093  mov     dword ptr [rsp+130h+var_E0+4], eax
0x18006d097  movups  xmm0, [rsp+130h+var_E0]
0x18006d09c  movdqu  xmmword ptr [rsi], xmm0
0x18006d0a0  test    rdi, rdi
0x18006d0a3  jz      short loc_18006D0A8
0x18006d0a5  mov     byte ptr [rdi], 0
0x18006d0a8  mov     [rsp+130h+var_F0], 0FFh
0x18006d0af  mov     eax, 0FF00h
0x18006d0b4  cmp     [rsp+130h+var_F0], ax
0x18006d0b9  jz      loc_18006D147
0x18006d0bf  mov     rax, [rsp+130h+Destination]
0x18006d0c4  mov     rcx, [rbp+30h+var_30]
0x18006d0c8  xor     rcx, rsp; StackCookie
0x18006d0cb  call    __security_check_cookie
0x18006d0d0  add     rsp, 110h
0x18006d0d7  pop     r14
0x18006d0d9  pop     rdi
0x18006d0da  pop     rsi
0x18006d0db  pop     rbx
0x18006d0dc  pop     rbp
0x18006d0dd  retn
0x18006d0de  mov     qword ptr [rsp+130h+var_E0], 0
0x18006d0e7  mov     qword ptr [rsp+130h+var_E0+8], 0
0x18006d0f0  jmp     short loc_18006D097
0x18006d0f2  movaps  xmm0, xmmword ptr [rcx]
0x18006d0f5  xor     eax, eax
0x18006d0f7  movdqu  xmmword ptr [rsi], xmm0
0x18006d0fb  mov     byte ptr [r8], 1
0x18006d0ff  jmp     short loc_18006D0C4
0x18006d101  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x18006d108  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x18006d10d  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x18006d114  mov     [rsp+130h+var_108], 80070057h; unsigned int
0x18006d11c  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x18006d123  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18006d128  mov     [rsp+130h+var_110], 0ABh; unsigned int
0x18006d130  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006d135  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006d13c  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18006d141  call    _CxxThrowException_0
0x18006d147  lea     rcx, [rsp+130h+Destination]
0x18006d14c  call    ??$ByteSwap@_K@detail@win_musl@@YAXPEA_K_K@Z; win_musl::detail::ByteSwap<unsigned __int64>(unsigned __int64 *,unsigned __int64)
0x18006d151  jmp     loc_18006D0BF
```
