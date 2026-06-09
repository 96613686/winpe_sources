# win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)

- ea: `0x18006dda8`
- end: `0x18006df0d`
- name: `??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z`
- size: `357`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001d7d8`
- `0x180020c18`
- `0x18006be28`
- `0x18006d7f8`

## callees

- `0x18002db70`
- `0x18006dda8`
- `0x1800cd6fc`
- `0x180110bcc`
- `0x1801178f0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18006ddfe`
- `msvcrt!memmove_s` at `0x18006ddfe`

## string_xrefs

- `0x18006debe`: `win_musl::detail::vector_read`

## pseudocode

```c
__int64 __fastcall win_musl::detail::readThenLog<unsigned short>(
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
  char v12; // cl
  unsigned __int16 Destination; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v14; // [rsp+44h] [rbp-BCh]
  __int128 v15; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = *a5;
  v7 = (char *)*((_QWORD *)a5 + 1);
  if ( (unsigned int)v6 < 2 )
  {
    v11 = *(_OWORD *)a5;
    *(_DWORD *)(a6 + 4) = a5[1];
    *(_DWORD *)a6 = v6;
    *(_QWORD *)(a6 + 8) = v7;
    v15 = v11;
    win_musl::detail::ThrowReadError(a1, a2, a3, a4, 2, &v15);
  }
  Destination = 0;
  memmove_s(&Destination, 2u, v7, 2u);
  if ( !v7 || (v8 = v7 + 2, v9 = &v7[v6], &v7[v6] == v7 + 2) )
  {
    v15 = 0u;
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
    *((_QWORD *)&v15 + 1) = v7 + 2;
    *(_QWORD *)&v15 = (unsigned int)((_DWORD)v9 - (_DWORD)v8);
  }
  v14 = 255;
  *(_OWORD *)a6 = v15;
  if ( v14 == -256 )
  {
    v12 = Destination;
    LOBYTE(Destination) = HIBYTE(Destination);
    HIBYTE(Destination) = v12;
  }
  return Destination;
}

```

## disassembly

```asm
0x18006dda8  push    rbp
0x18006ddaa  push    rbx
0x18006ddab  push    rsi
0x18006ddac  push    rdi
0x18006ddad  lea     rbp, [rsp-18h]
0x18006ddb2  sub     rsp, 118h
0x18006ddb9  mov     rax, cs:__security_cookie
0x18006ddc0  xor     rax, rsp
0x18006ddc3  mov     [rbp+30h+var_30], rax
0x18006ddc7  mov     r10, [rbp+30h+arg_20]
0x18006ddcb  mov     r11d, 2
0x18006ddd1  mov     rdi, [rbp+30h+arg_28]
0x18006ddd5  mov     esi, [r10]
0x18006ddd8  mov     eax, [r10+4]
0x18006dddc  mov     rbx, [r10+8]
0x18006dde0  cmp     esi, r11d
0x18006dde3  jb      loc_18006DE8A
0x18006dde9  xor     eax, eax
0x18006ddeb  lea     rcx, [rsp+130h+Destination]; Destination
0x18006ddf0  mov     r9d, r11d; SourceSize
0x18006ddf3  mov     [rsp+130h+Destination], ax
0x18006ddf8  mov     r8, rbx; Source
0x18006ddfb  mov     edx, r11d; DestinationSize
0x18006ddfe  call    cs:__imp_memmove_s
0x18006de04  test    rbx, rbx
0x18006de07  jz      short loc_18006DE76
0x18006de09  lea     rcx, [rbx+2]
0x18006de0d  lea     rdx, [rbx+rsi]
0x18006de11  cmp     rdx, rcx
0x18006de14  jz      short loc_18006DE76
0x18006de16  cmp     rbx, rcx
0x18006de19  ja      loc_18006DEB2
0x18006de1f  cmp     rcx, rdx
0x18006de22  ja      loc_18006DEB2
0x18006de28  sub     edx, ecx
0x18006de2a  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x18006de2f  xor     eax, eax
0x18006de31  mov     dword ptr [rsp+130h+var_E0], edx
0x18006de35  mov     dword ptr [rsp+130h+var_E0+4], eax
0x18006de39  movups  xmm0, [rsp+130h+var_E0]
0x18006de3e  mov     [rsp+130h+var_EC], 0FFh
0x18006de45  mov     eax, 0FF00h
0x18006de4a  movdqu  xmmword ptr [rdi], xmm0
0x18006de4e  cmp     [rsp+130h+var_EC], ax
0x18006de53  jz      loc_18006DEF8
0x18006de59  movzx   eax, [rsp+130h+Destination]
0x18006de5e  mov     rcx, [rbp+30h+var_30]
0x18006de62  xor     rcx, rsp; StackCookie
0x18006de65  call    __security_check_cookie
0x18006de6a  add     rsp, 118h
0x18006de71  pop     rdi
0x18006de72  pop     rsi
0x18006de73  pop     rbx
0x18006de74  pop     rbp
0x18006de75  retn
0x18006de76  mov     qword ptr [rsp+130h+var_E0], 0
0x18006de7f  mov     qword ptr [rsp+130h+var_E0+8], 0
0x18006de88  jmp     short loc_18006DE39
0x18006de8a  movaps  xmm0, xmmword ptr [r10]
0x18006de8e  mov     [rdi+4], eax
0x18006de91  lea     rax, [rsp+130h+var_E0]
0x18006de96  mov     qword ptr [rsp+130h+var_108], rax
0x18006de9b  mov     [rsp+130h+var_110], r11d
0x18006dea0  mov     [rdi], esi
0x18006dea2  mov     [rdi+8], rbx
0x18006dea6  movdqa  [rsp+130h+var_E0], xmm0
0x18006deac  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18006deb2  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x18006deb9  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x18006debe  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x18006dec5  mov     [rsp+130h+var_108], 80070057h; unsigned int
0x18006decd  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x18006ded4  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18006ded9  mov     [rsp+130h+var_110], 0ABh; unsigned int
0x18006dee1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006dee6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006deed  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18006def2  call    _CxxThrowException_0
0x18006def8  mov     cl, byte ptr [rsp+130h+Destination]
0x18006defc  mov     al, byte ptr [rsp+130h+Destination+1]
0x18006df00  mov     byte ptr [rsp+130h+Destination], al
0x18006df04  mov     byte ptr [rsp+130h+Destination+1], cl
0x18006df08  jmp     loc_18006DE59
```
