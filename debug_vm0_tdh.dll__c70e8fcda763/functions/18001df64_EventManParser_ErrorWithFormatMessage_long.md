# EventManParser::ErrorWithFormatMessage(long,...)

- ea: `0x18001df64`
- end: `0x18001e095`
- name: `?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ`
- size: `305`
- prototype: `void(EventManParser *__hidden this, int, ...)`
- caller_count: `25`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180011b30`
- `0x18001d638`
- `0x18001d810`
- `0x18002c2fc`
- `0x18003479c`
- `0x180034974`
- `0x180034e18`
- `0x1800355ac`
- `0x180035aa0`
- `0x180035e08`
- `0x180036e08`
- `0x180037ff0`
- `0x180038300`
- `0x180038570`
- `0x1800386fc`
- `0x180038a44`
- `0x180038e20`
- `0x180039780`
- `0x180039878`
- `0x180039a80`
- `0x180039cdc`
- `0x18003b29c`
- `0x18003b4dc`
- `0x18003b7e0`
- `0x18003c084`

## callees

- `0x18001bf3c`
- `0x18001df64`
- `0x1800207c0`
- `0x18002149c`
- `0x180037178`
- `0x180037e18`
- `0x180037e4c`
- `0x18004c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void EventManParser::ErrorWithFormatMessage(EventManParser *this, __int64 a2, ...)
{
  unsigned int LinePosition; // ebx
  unsigned int LineNumber; // eax
  void (__fastcall *v5)(__int128 *, _QWORD, _QWORD, _QWORD, unsigned int); // rsi
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int128 *v8; // rcx
  __int128 v9; // [rsp+40h] [rbp-51h] BYREF
  __m128i si128; // [rsp+50h] [rbp-41h]
  void **pExceptionObject; // [rsp+68h] [rbp-29h] BYREF
  __int128 v12; // [rsp+70h] [rbp-21h]
  __int128 v13; // [rsp+80h] [rbp-11h]
  __m128i v14; // [rsp+90h] [rbp-1h]
  int v15; // [rsp+A0h] [rbp+Fh]
  unsigned int v16; // [rsp+A4h] [rbp+13h]
  unsigned int v17; // [rsp+A8h] [rbp+17h]
  int v18; // [rsp+100h] [rbp+6Fh]
  va_list va; // [rsp+108h] [rbp+77h] BYREF

  va_start(va, a2);
  v18 = a2;
  FormatErrorMessageV(&v9, a2, va);
  if ( v18 < 0 && *((_BYTE *)this + 64) )
  {
    LinePosition = XmlReader::GetLinePosition(this);
    LineNumber = XmlReader::GetLineNumber(this);
    v12 = 0;
    pExceptionObject = &ManparseException::`vftable';
    v13 = v9;
    v14 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v9) = 0;
    v15 = v18;
    v16 = LineNumber;
    v17 = LinePosition;
    throw (ManparseException *)&pExceptionObject;
  }
  if ( *((int *)this + 17) >= 0 )
    *((_DWORD *)this + 17) = v18;
  v5 = (void (__fastcall *)(__int128 *, _QWORD, _QWORD, _QWORD, unsigned int))*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = XmlReader::GetLinePosition(this);
    v7 = XmlReader::GetLineNumber(this);
    v8 = &v9;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v8 = (__int128 *)v9;
    v5(v8, (unsigned int)v18, *((_QWORD *)this + 9), v7, v6);
  }
  std::string::_Tidy_deallocate(&v9);
}

```

## disassembly

```asm
0x18001df64  mov     rax, rsp
0x18001df67  mov     [rax+10h], edx
0x18001df6a  mov     [rax+18h], r8
0x18001df6e  mov     [rax+20h], r9
0x18001df72  push    rbp
0x18001df73  push    rbx
0x18001df74  push    rsi
0x18001df75  push    rdi
0x18001df76  lea     rbp, [rax-5Fh]
0x18001df7a  sub     rsp, 0C8h
0x18001df81  mov     rax, cs:__security_cookie
0x18001df88  xor     rax, rsp
0x18001df8b  mov     [rbp+57h+var_30], rax
0x18001df8f  mov     rdi, rcx
0x18001df92  mov     [rbp+57h+var_B0], 0
0x18001df9a  lea     r8, [rbp+57h+arg_10]
0x18001df9e  lea     rcx, [rbp+57h+var_A8]
0x18001dfa2  call    ?FormatErrorMessageV@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@JPEAD@Z; FormatErrorMessageV(long,char *)
0x18001dfa7  nop
0x18001dfa8  mov     eax, [rbp+57h+arg_8]
0x18001dfab  test    eax, eax
0x18001dfad  jns     short loc_18001E02B
0x18001dfaf  cmp     byte ptr [rdi+40h], 0
0x18001dfb3  jz      short loc_18001E02B
0x18001dfb5  mov     rcx, rdi; this
0x18001dfb8  call    ?GetLinePosition@XmlReader@@QEBAIXZ; XmlReader::GetLinePosition(void)
0x18001dfbd  mov     ebx, eax
0x18001dfbf  mov     rcx, rdi; this
0x18001dfc2  call    ?GetLineNumber@XmlReader@@QEBAIXZ; XmlReader::GetLineNumber(void)
0x18001dfc7  mov     edx, [rbp+57h+arg_8]
0x18001dfca  xorps   xmm0, xmm0
0x18001dfcd  movups  [rbp+57h+var_78], xmm0
0x18001dfd1  lea     rcx, ??_7ManparseException@@6B@; const ManparseException::`vftable'
0x18001dfd8  mov     [rbp+57h+pExceptionObject], rcx
0x18001dfdc  movups  [rbp+57h+var_68], xmm0
0x18001dfe0  mov     rcx, qword ptr [rbp+57h+var_A8]
0x18001dfe4  mov     qword ptr [rbp+57h+var_68], rcx
0x18001dfe8  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x18001dfec  mov     qword ptr [rbp+57h+var_68+8], rcx
0x18001dff0  mov     rcx, qword ptr [rbp+57h+var_98]
0x18001dff4  mov     qword ptr [rbp+57h+var_58], rcx
0x18001dff8  mov     rcx, qword ptr [rbp+57h+var_98+8]
0x18001dffc  mov     qword ptr [rbp+57h+var_58+8], rcx
0x18001e000  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18001e008  movdqu  [rbp+57h+var_98], xmm0
0x18001e00d  mov     byte ptr [rbp+57h+var_A8], 0
0x18001e011  mov     [rbp+57h+var_48], edx
0x18001e014  mov     [rbp+57h+var_44], eax
0x18001e017  mov     [rbp+57h+var_40], ebx
0x18001e01a  lea     rdx, _TI2?AVManparseException@@; pThrowInfo
0x18001e021  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001e025  call    _CxxThrowException_0
0x18001e02b  cmp     dword ptr [rdi+44h], 0
0x18001e02f  jl      short loc_18001E034
0x18001e031  mov     [rdi+44h], eax
0x18001e034  mov     rsi, [rdi+38h]
0x18001e038  test    rsi, rsi
0x18001e03b  jz      short loc_18001E074
0x18001e03d  mov     rcx, rdi; this
0x18001e040  call    ?GetLinePosition@XmlReader@@QEBAIXZ; XmlReader::GetLinePosition(void)
0x18001e045  mov     ebx, eax
0x18001e047  mov     rcx, rdi; this
0x18001e04a  call    ?GetLineNumber@XmlReader@@QEBAIXZ; XmlReader::GetLineNumber(void)
0x18001e04f  lea     rcx, [rbp+57h+var_A8]
0x18001e053  cmp     qword ptr [rbp+57h+var_98+8], 0Fh
0x18001e058  cmova   rcx, qword ptr [rbp+57h+var_A8]
0x18001e05d  mov     [rsp+20h], ebx
0x18001e061  mov     r9d, eax
0x18001e064  mov     r8, [rdi+48h]
0x18001e068  mov     edx, [rbp+57h+arg_8]
0x18001e06b  mov     rax, rsi
0x18001e06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e073  nop
0x18001e074  lea     rcx, [rbp+57h+var_A8]
0x18001e078  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001e07d  mov     rcx, [rbp+57h+var_30]
0x18001e081  xor     rcx, rsp; StackCookie
0x18001e084  call    __security_check_cookie
0x18001e089  add     rsp, 0C8h
0x18001e090  pop     rdi
0x18001e091  pop     rsi
0x18001e092  pop     rbx
0x18001e093  pop     rbp
0x18001e094  retn
```
