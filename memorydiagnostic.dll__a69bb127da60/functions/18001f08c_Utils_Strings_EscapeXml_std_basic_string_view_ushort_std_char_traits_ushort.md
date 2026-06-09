# Utils::Strings::EscapeXml(std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18001f08c`
- end: `0x18001f1bc`
- name: `?EscapeXml@Strings@Utils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@4@@Z`
- size: `304`
- prototype: `_QWORD *__fastcall(_QWORD *Src, unsigned __int16 **, __int64, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001f1c4`

## callees

- `0x18001e88c`
- `0x18001e9a8`
- `0x18001eeb8`
- `0x18001f08c`

## pseudocode

```c
_QWORD *__fastcall Utils::Strings::EscapeXml(_QWORD *Src, unsigned __int16 **a2, __int64 a3, const char *a4)
{
  _QWORD *v5; // rbx
  unsigned __int16 *v6; // rsi
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rsi
  wchar_t *v10; // rdx
  unsigned __int64 v11; // rcx
  _QWORD *v12; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = Src;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 7;
  *(_WORD *)Src = 0;
  v6 = a2[1];
  if ( v6 )
  {
    try
    {
      v7 = 2LL * (_QWORD)v6;
      if ( v7 > 7 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(Src);
        v5[2] = 0;
      }
      v8 = *a2;
      v9 = &v8[v7 / 2];
      while ( 1 )
      {
        if ( v8 == v9 )
          goto LABEL_29;
        a4 = (const char *)*v8;
        if ( (_WORD)a4 == 38 )
          break;
        switch ( (_WORD)a4 )
        {
          case '<':
            v10 = L"&lt;";
            goto LABEL_17;
          case '>':
            v10 = L"&gt;";
            goto LABEL_17;
          case '\'':
            v10 = L"&apos;";
            goto LABEL_17;
          case '"':
            v10 = L"&quot;";
            goto LABEL_17;
        }
        v11 = v5[2];
        if ( v11 >= v5[3] )
        {
          std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v5);
        }
        else
        {
          v5[2] = v11 + 1;
          if ( v5[3] <= 7u )
            v12 = v5;
          else
            v12 = (_QWORD *)*v5;
          *((_WORD *)v12 + v11) = (_WORD)a4;
          *((_WORD *)v12 + v11 + 1) = 0;
        }
LABEL_24:
        ++v8;
      }
      v10 = L"&amp;";
LABEL_17:
      std::wstring::operator+=(v5, v10);
      goto LABEL_24;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x49,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\utils.cpp",
        a4);
      return Src;
    }
LABEL_29:
    ;
  }
  return v5;
}

```

## disassembly

```asm
0x18001f08c  mov     rax, rsp
0x18001f08f  mov     [rax+10h], rbx
0x18001f093  mov     [rax+18h], rsi
0x18001f097  mov     [rax+8], rcx
0x18001f09b  push    rdi
0x18001f09c  sub     rsp, 30h
0x18001f0a0  mov     rdi, rdx
0x18001f0a3  mov     rbx, rcx
0x18001f0a6  mov     dword ptr [rax-18h], 0
0x18001f0ad  xorps   xmm0, xmm0
0x18001f0b0  movups  xmmword ptr [rcx], xmm0
0x18001f0b3  mov     qword ptr [rcx+10h], 0
0x18001f0bb  mov     qword ptr [rcx+18h], 7
0x18001f0c3  xor     eax, eax
0x18001f0c5  mov     [rcx], ax
0x18001f0c8  mov     [rsp+38h+var_18], 1
0x18001f0d0  mov     rsi, [rdx+8]
0x18001f0d4  test    rsi, rsi
0x18001f0d7  jz      loc_18001F1A1
0x18001f0dd  add     rsi, rsi
0x18001f0e0  cmp     rsi, 7
0x18001f0e4  jbe     short loc_18001F0F6
0x18001f0e6  mov     rdx, rsi
0x18001f0e9  call    ??$_Reallocate_grow_by@V_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(unsigned __int64,_lambda_7f96eb1dcf99da5daec8c2467d2d5499_)
0x18001f0ee  mov     qword ptr [rbx+10h], 0
0x18001f0f6  mov     rdi, [rdi]
0x18001f0f9  add     rsi, rdi
0x18001f0fc  cmp     rdi, rsi
0x18001f0ff  jz      loc_18001F1A1
0x18001f105  movzx   r9d, word ptr [rdi]
0x18001f109  cmp     r9w, 26h ; '&'
0x18001f10e  jnz     short loc_18001F119
0x18001f110  lea     rdx, aAmp; "&amp;"
0x18001f117  jmp     short loc_18001F157
0x18001f119  cmp     r9w, 3Ch ; '<'
0x18001f11e  jnz     short loc_18001F129
0x18001f120  lea     rdx, aLt; "&lt;"
0x18001f127  jmp     short loc_18001F157
0x18001f129  cmp     r9w, 3Eh ; '>'
0x18001f12e  jnz     short loc_18001F139
0x18001f130  lea     rdx, aGt; "&gt;"
0x18001f137  jmp     short loc_18001F157
0x18001f139  cmp     r9w, 27h ; '''
0x18001f13e  jnz     short loc_18001F149
0x18001f140  lea     rdx, aApos; "&apos;"
0x18001f147  jmp     short loc_18001F157
0x18001f149  cmp     r9w, 22h ; '"'
0x18001f14e  jnz     short loc_18001F161
0x18001f150  lea     rdx, aQuot; "&quot;"
0x18001f157  mov     rcx, rbx; Src
0x18001f15a  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18001f15f  jmp     short loc_18001F198
0x18001f161  mov     rcx, [rbx+10h]
0x18001f165  cmp     rcx, [rbx+18h]
0x18001f169  jnb     short loc_18001F190
0x18001f16b  lea     rax, [rcx+1]
0x18001f16f  mov     [rbx+10h], rax
0x18001f173  cmp     qword ptr [rbx+18h], 7
0x18001f178  jbe     short loc_18001F17F
0x18001f17a  mov     rdx, [rbx]
0x18001f17d  jmp     short loc_18001F182
0x18001f17f  mov     rdx, rbx
0x18001f182  mov     [rdx+rcx*2], r9w
0x18001f187  xor     eax, eax
0x18001f189  mov     [rdx+rcx*2+2], ax
0x18001f18e  jmp     short loc_18001F198
0x18001f190  mov     rcx, rbx; Src
0x18001f193  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18001f198  add     rdi, 2
0x18001f19c  jmp     loc_18001F0FC
0x18001f1a1  jmp     short loc_18001F1A8
0x18001f1a3  mov     rbx, [rsp+38h+arg_0]
0x18001f1a8  mov     rax, rbx
0x18001f1ab  mov     rbx, [rsp+38h+arg_8]
0x18001f1b0  mov     rsi, [rsp+38h+arg_10]
0x18001f1b5  add     rsp, 30h
0x18001f1b9  pop     rdi
0x18001f1ba  retn
```
