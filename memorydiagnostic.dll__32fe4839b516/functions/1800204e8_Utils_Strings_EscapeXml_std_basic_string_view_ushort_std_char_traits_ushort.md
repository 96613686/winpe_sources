# Utils::Strings::EscapeXml(std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x1800204e8`
- end: `0x180020616`
- name: `?EscapeXml@Strings@Utils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@4@@Z`
- size: `302`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002061c`

## callees

- `0x18001fc48`
- `0x18001fedc`
- `0x1800202e4`
- `0x1800204e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Utils::Strings::EscapeXml(_QWORD *Src, unsigned __int16 **a2, __int64 a3, const char *a4)
{
  _QWORD *v5; // rbx
  unsigned __int16 *v6; // rsi
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rsi
  wchar_t *v10; // rdx
  unsigned __int64 v11; // rcx
  _QWORD *v12; // rax
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
          goto LABEL_28;
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
          v12 = v5;
          if ( v5[3] > 7u )
            v12 = (_QWORD *)*v5;
          *((_WORD *)v12 + v11) = (_WORD)a4;
          *((_WORD *)v12 + v11 + 1) = 0;
        }
LABEL_23:
        ++v8;
      }
      v10 = L"&amp;";
LABEL_17:
      std::wstring::operator+=(v5, v10);
      goto LABEL_23;
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
LABEL_28:
    ;
  }
  return v5;
}

```

## disassembly

```asm
0x1800204e8  mov     rax, rsp
0x1800204eb  mov     [rax+10h], rbx
0x1800204ef  mov     [rax+18h], rsi
0x1800204f3  mov     [rax+20h], rdi
0x1800204f7  mov     [rax+8], rcx
0x1800204fb  push    r14
0x1800204fd  sub     rsp, 30h
0x180020501  mov     rdi, rdx
0x180020504  mov     rbx, rcx
0x180020507  xor     r14d, r14d
0x18002050a  mov     [rax-18h], r14d
0x18002050e  xorps   xmm0, xmm0
0x180020511  movups  xmmword ptr [rcx], xmm0
0x180020514  mov     [rcx+10h], r14
0x180020518  mov     qword ptr [rcx+18h], 7
0x180020520  mov     [rcx], r14w
0x180020524  mov     dword ptr [rax-18h], 1
0x18002052b  mov     rsi, [rdx+8]
0x18002052f  test    rsi, rsi
0x180020532  jz      loc_1800205F5
0x180020538  add     rsi, rsi
0x18002053b  cmp     rsi, 7
0x18002053f  jbe     short loc_18002054D
0x180020541  mov     rdx, rsi
0x180020544  call    ??$_Reallocate_grow_by@V_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(unsigned __int64,_lambda_7f96eb1dcf99da5daec8c2467d2d5499_)
0x180020549  mov     [rbx+10h], r14
0x18002054d  mov     rdi, [rdi]
0x180020550  add     rsi, rdi
0x180020553  cmp     rdi, rsi
0x180020556  jz      loc_1800205F5
0x18002055c  movzx   r9d, word ptr [rdi]
0x180020560  cmp     r9w, 26h ; '&'
0x180020565  jnz     short loc_180020570
0x180020567  lea     rdx, aAmp; "&amp;"
0x18002056e  jmp     short loc_1800205AE
0x180020570  cmp     r9w, 3Ch ; '<'
0x180020575  jnz     short loc_180020580
0x180020577  lea     rdx, aLt; "&lt;"
0x18002057e  jmp     short loc_1800205AE
0x180020580  cmp     r9w, 3Eh ; '>'
0x180020585  jnz     short loc_180020590
0x180020587  lea     rdx, aGt; "&gt;"
0x18002058e  jmp     short loc_1800205AE
0x180020590  cmp     r9w, 27h ; '''
0x180020595  jnz     short loc_1800205A0
0x180020597  lea     rdx, aApos; "&apos;"
0x18002059e  jmp     short loc_1800205AE
0x1800205a0  cmp     r9w, 22h ; '"'
0x1800205a5  jnz     short loc_1800205B8
0x1800205a7  lea     rdx, aQuot; "&quot;"
0x1800205ae  mov     rcx, rbx; Src
0x1800205b1  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1800205b6  jmp     short loc_1800205EC
0x1800205b8  mov     rcx, [rbx+10h]
0x1800205bc  cmp     rcx, [rbx+18h]
0x1800205c0  jnb     short loc_1800205E4
0x1800205c2  lea     rax, [rcx+1]
0x1800205c6  mov     [rbx+10h], rax
0x1800205ca  mov     rax, rbx
0x1800205cd  cmp     qword ptr [rbx+18h], 7
0x1800205d2  jbe     short loc_1800205D7
0x1800205d4  mov     rax, [rbx]
0x1800205d7  mov     [rax+rcx*2], r9w
0x1800205dc  mov     [rax+rcx*2+2], r14w
0x1800205e2  jmp     short loc_1800205EC
0x1800205e4  mov     rcx, rbx; Src
0x1800205e7  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800205ec  add     rdi, 2
0x1800205f0  jmp     loc_180020553
0x1800205f5  jmp     short loc_1800205FC
0x1800205f7  mov     rbx, [rsp+38h+arg_0]
0x1800205fc  mov     rax, rbx
0x1800205ff  mov     rbx, [rsp+38h+arg_8]
0x180020604  mov     rsi, [rsp+38h+arg_10]
0x180020609  mov     rdi, [rsp+38h+arg_18]
0x18002060e  add     rsp, 30h
0x180020612  pop     r14
0x180020614  retn
```
