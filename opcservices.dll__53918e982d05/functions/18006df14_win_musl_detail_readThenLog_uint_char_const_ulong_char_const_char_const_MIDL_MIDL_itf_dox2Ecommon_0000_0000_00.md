# win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)

- ea: `0x18006df14`
- end: `0x18006e073`
- name: `??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z`
- size: `351`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002e7a0`
- `0x18006be28`
- `0x18006d350`
- `0x18006d7f8`
- `0x18006e1e8`
- `0x18006e530`
- `0x180097a84`

## callees

- `0x18002db70`
- `0x18006df14`
- `0x1800b6f0c`
- `0x1800cd6fc`
- `0x180110bcc`
- `0x1801178f0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18006df6b`
- `msvcrt!memmove_s` at `0x18006df6b`

## string_xrefs

- `0x18006e02a`: `win_musl::detail::vector_read`

## pseudocode

```c
__int64 __fastcall win_musl::detail::readThenLog<unsigned int>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int *a5,
        __int64 a6)
{
  __int64 v6; // rsi
  char *v7; // rbx
  char *v8; // rcx
  char *v9; // rdx
  __int128 v11; // xmm0
  unsigned int Destination[3]; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = *a5;
  v7 = (char *)*((_QWORD *)a5 + 1);
  if ( (unsigned int)v6 < 4 )
  {
    v11 = *(_OWORD *)a5;
    *(_DWORD *)(a6 + 4) = a5[1];
    *(_DWORD *)a6 = v6;
    *(_QWORD *)(a6 + 8) = v7;
    v13 = v11;
    win_musl::detail::ThrowReadError(a1, a2, a3, a4, 4, &v13);
  }
  Destination[0] = 0;
  memmove_s(Destination, 4u, v7, 4u);
  if ( !v7 || (v8 = v7 + 4, v9 = &v7[v6], &v7[v6] == v7 + 4) )
  {
    v13 = 0u;
  }
  else
  {
    if ( v7 > v8 || v8 > v9 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *((_QWORD *)&v13 + 1) = v7 + 4;
    *(_QWORD *)&v13 = (unsigned int)((_DWORD)v9 - (_DWORD)v8);
  }
  *(_OWORD *)a6 = v13;
  return Destination[0];
}

```

## disassembly

```asm
0x18006df14  push    rbp
0x18006df16  push    rbx
0x18006df17  push    rsi
0x18006df18  push    rdi
0x18006df19  lea     rbp, [rsp-18h]
0x18006df1e  sub     rsp, 118h
0x18006df25  mov     rax, cs:__security_cookie
0x18006df2c  xor     rax, rsp
0x18006df2f  mov     [rbp+30h+var_30], rax
0x18006df33  mov     r10, [rbp+30h+arg_20]
0x18006df37  mov     r11d, 4
0x18006df3d  mov     rdi, [rbp+30h+arg_28]
0x18006df41  mov     esi, [r10]
0x18006df44  mov     eax, [r10+4]
0x18006df48  mov     rbx, [r10+8]
0x18006df4c  cmp     esi, r11d
0x18006df4f  jb      loc_18006DFF6
0x18006df55  mov     r9d, r11d; SourceSize
0x18006df58  mov     [rsp+130h+Destination], 0
0x18006df60  mov     r8, rbx; Source
0x18006df63  lea     rcx, [rsp+130h+Destination]; Destination
0x18006df68  mov     edx, r11d; DestinationSize
0x18006df6b  call    cs:__imp_memmove_s
0x18006df71  test    rbx, rbx
0x18006df74  jz      short loc_18006DFE2
0x18006df76  lea     rcx, [rbx+4]
0x18006df7a  lea     rdx, [rbx+rsi]
0x18006df7e  cmp     rdx, rcx
0x18006df81  jz      short loc_18006DFE2
0x18006df83  cmp     rbx, rcx
0x18006df86  ja      loc_18006E01E
0x18006df8c  cmp     rcx, rdx
0x18006df8f  ja      loc_18006E01E
0x18006df95  sub     edx, ecx
0x18006df97  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x18006df9c  xor     eax, eax
0x18006df9e  mov     dword ptr [rsp+130h+var_E0], edx
0x18006dfa2  mov     dword ptr [rsp+130h+var_E0+4], eax
0x18006dfa6  movups  xmm0, [rsp+130h+var_E0]
0x18006dfab  mov     [rsp+130h+var_F0], 0FFh
0x18006dfb2  mov     eax, 0FF00h
0x18006dfb7  movdqu  xmmword ptr [rdi], xmm0
0x18006dfbb  cmp     [rsp+130h+var_F0], ax
0x18006dfc0  jz      loc_18006E064
0x18006dfc6  mov     eax, [rsp+130h+Destination]
0x18006dfca  mov     rcx, [rbp+30h+var_30]
0x18006dfce  xor     rcx, rsp; StackCookie
0x18006dfd1  call    __security_check_cookie
0x18006dfd6  add     rsp, 118h
0x18006dfdd  pop     rdi
0x18006dfde  pop     rsi
0x18006dfdf  pop     rbx
0x18006dfe0  pop     rbp
0x18006dfe1  retn
0x18006dfe2  mov     qword ptr [rsp+130h+var_E0], 0
0x18006dfeb  mov     qword ptr [rsp+130h+var_E0+8], 0
0x18006dff4  jmp     short loc_18006DFA6
0x18006dff6  movaps  xmm0, xmmword ptr [r10]
0x18006dffa  mov     [rdi+4], eax
0x18006dffd  lea     rax, [rsp+130h+var_E0]
0x18006e002  mov     qword ptr [rsp+130h+var_108], rax
0x18006e007  mov     [rsp+130h+var_110], r11d
0x18006e00c  mov     [rdi], esi
0x18006e00e  mov     [rdi+8], rbx
0x18006e012  movdqa  [rsp+130h+var_E0], xmm0
0x18006e018  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18006e01e  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x18006e025  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x18006e02a  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x18006e031  mov     [rsp+130h+var_108], 80070057h; unsigned int
0x18006e039  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x18006e040  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18006e045  mov     [rsp+130h+var_110], 0ABh; unsigned int
0x18006e04d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006e052  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006e059  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18006e05e  call    _CxxThrowException_0
0x18006e064  lea     rcx, [rsp+130h+Destination]
0x18006e069  call    ??$ByteSwap@I@detail@win_musl@@YAXPEAI_K@Z; win_musl::detail::ByteSwap<uint>(uint *,unsigned __int64)
0x18006e06e  jmp     loc_18006DFC6
```
