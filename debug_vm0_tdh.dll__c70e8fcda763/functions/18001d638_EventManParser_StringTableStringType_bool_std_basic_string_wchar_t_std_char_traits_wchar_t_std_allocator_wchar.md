# EventManParser::StringTableStringType(bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *)

- ea: `0x18001d638`
- end: `0x18001d807`
- name: `?StringTableStringType@EventManParser@@AEAAX_NPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z`
- size: `463`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18003b29c`

## callees

- `0x18001d638`
- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18001ed1c`
- `0x18002f910`
- `0x18003899c`
- `0x18003c908`

## pseudocode

```c
void __fastcall EventManParser::StringTableStringType(XmlReader *this, char a2, _QWORD *a3, _QWORD *a4)
{
  bool v4; // r12
  bool v5; // r14
  _QWORD *v7; // rdi
  _WORD *v10; // rcx
  _WORD *v11; // rcx
  __int64 v12; // r15
  _WORD *v13; // rcx
  unsigned __int64 v14; // rdx
  bool v15; // cc
  _QWORD *v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-48h] BYREF
  __int64 v18; // [rsp+28h] [rbp-40h]
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  __int64 v20; // [rsp+38h] [rbp-30h]
  __int128 v21; // [rsp+40h] [rbp-28h] BYREF
  __int128 v22; // [rsp+50h] [rbp-18h] BYREF

  v4 = 0;
  a3[2] = 0;
  v5 = 0;
  v7 = a3;
  if ( a3[3] <= 7u )
    v10 = a3;
  else
    v10 = (_WORD *)*a3;
  *v10 = 0;
  a4[2] = 0;
  if ( a4[3] <= 7u )
    v11 = a4;
  else
    v11 = (_WORD *)*a4;
  *v11 = 0;
  if ( !XmlReader::FirstAttribute(this) )
    goto LABEL_24;
  do
  {
    XmlReader::GetQualifiedName(this, &v17);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"id", 2, v17, v18) )
    {
      XmlReader::GetValue(this, &v21);
      v4 = *((_QWORD *)&v21 + 1) != 0;
      v22 = v21;
      MakeStringRef(&v22, v7);
    }
    else if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"value", 5, v17, v18) )
    {
      XmlReader::GetValue(this, &v19);
      v12 = v20;
      v5 = v20 != 0;
      if ( a2 )
      {
        a4[2] = 0;
        if ( a4[3] <= 7u )
          v13 = a4;
        else
          v13 = (_WORD *)*a4;
        *v13 = 0;
        std::wstring::reserve(a4, v12 + 1);
        std::wstring::_Assign<wchar_t>(a4, v19);
        v14 = a4[2];
        if ( v14 >= a4[3] )
        {
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(a4);
        }
        else
        {
          v15 = a4[3] <= 7u;
          a4[2] = v14 + 1;
          if ( v15 )
            v16 = a4;
          else
            v16 = (_QWORD *)*a4;
          *(_DWORD *)((char *)v16 + 2 * v14) = 32;
        }
      }
      else
      {
        std::wstring::_Assign<wchar_t>(a4, v19);
      }
    }
  }
  while ( XmlReader::NextAttribute(this) );
  if ( !v4 )
LABEL_24:
    EventManParser::ErrorWithFormatMessage(this, -1073221740);
  if ( !v5 )
  {
    if ( v7[3] > 7u )
      v7 = (_QWORD *)*v7;
    EventManParser::ErrorWithFormatMessage(this, -1073221739, v7);
  }
}

```

## disassembly

```asm
0x18001d638  push    rbp
0x18001d63a  push    rbx
0x18001d63b  push    rsi
0x18001d63c  push    rdi
0x18001d63d  push    r12
0x18001d63f  push    r13
0x18001d641  push    r14
0x18001d643  push    r15
0x18001d645  mov     rbp, rsp
0x18001d648  sub     rsp, 68h
0x18001d64c  xor     r12b, r12b
0x18001d64f  mov     qword ptr [r8+10h], 0
0x18001d657  xor     r14b, r14b
0x18001d65a  mov     rbx, r9
0x18001d65d  cmp     qword ptr [r8+18h], 7
0x18001d662  mov     rdi, r8
0x18001d665  mov     r13b, dl
0x18001d668  mov     rsi, rcx
0x18001d66b  jbe     short loc_18001D672
0x18001d66d  mov     rcx, [r8]
0x18001d670  jmp     short loc_18001D675
0x18001d672  mov     rcx, rdi
0x18001d675  xor     eax, eax
0x18001d677  mov     [rcx], ax
0x18001d67a  mov     [r9+10h], rax
0x18001d67e  cmp     qword ptr [r9+18h], 7
0x18001d683  jbe     short loc_18001D68A
0x18001d685  mov     rcx, [r9]
0x18001d688  jmp     short loc_18001D68D
0x18001d68a  mov     rcx, rbx
0x18001d68d  mov     [rcx], ax
0x18001d690  mov     rcx, rsi; this
0x18001d693  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x18001d698  test    al, al
0x18001d69a  jz      loc_18001D7CA
0x18001d6a0  lea     rdx, [rbp+var_48]
0x18001d6a4  mov     rcx, rsi; this
0x18001d6a7  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x18001d6ac  mov     r9, [rbp+var_40]
0x18001d6b0  lea     rcx, aId; "id"
0x18001d6b7  mov     r8, [rbp+var_48]
0x18001d6bb  mov     edx, 2
0x18001d6c0  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18001d6c5  test    al, al
0x18001d6c7  jz      short loc_18001D6F8
0x18001d6c9  lea     rdx, [rbp+var_28]
0x18001d6cd  mov     rcx, rsi; this
0x18001d6d0  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18001d6d5  cmp     qword ptr [rbp+var_28+8], 0
0x18001d6da  lea     rcx, [rbp+var_18]
0x18001d6de  movaps  xmm0, [rbp+var_28]
0x18001d6e2  mov     rdx, rdi
0x18001d6e5  setnz   r12b
0x18001d6e9  movdqa  [rbp+var_18], xmm0
0x18001d6ee  call    ?MakeStringRef@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; MakeStringRef(std::wstring_view,std::wstring *)
0x18001d6f3  jmp     loc_18001D7B5
0x18001d6f8  mov     r9, [rbp+var_40]
0x18001d6fc  lea     rcx, aValue; "value"
0x18001d703  mov     r8, [rbp+var_48]
0x18001d707  mov     edx, 5
0x18001d70c  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18001d711  test    al, al
0x18001d713  jz      loc_18001D7B5
0x18001d719  lea     rdx, [rbp+var_38]
0x18001d71d  mov     rcx, rsi; this
0x18001d720  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18001d725  mov     r15, [rbp+var_30]
0x18001d729  test    r15, r15
0x18001d72c  setnz   r14b
0x18001d730  test    r13b, r13b
0x18001d733  jnz     short loc_18001D746
0x18001d735  mov     rdx, [rbp+var_38]
0x18001d739  mov     r8, r15
0x18001d73c  mov     rcx, rbx
0x18001d73f  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001d744  jmp     short loc_18001D7B5
0x18001d746  mov     qword ptr [rbx+10h], 0
0x18001d74e  cmp     qword ptr [rbx+18h], 7
0x18001d753  jbe     short loc_18001D75A
0x18001d755  mov     rcx, [rbx]
0x18001d758  jmp     short loc_18001D75D
0x18001d75a  mov     rcx, rbx
0x18001d75d  xor     eax, eax
0x18001d75f  lea     rdx, [r15+1]
0x18001d763  mov     [rcx], ax
0x18001d766  mov     rcx, rbx
0x18001d769  call    ?reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x18001d76e  mov     rdx, [rbp+var_38]
0x18001d772  mov     r8, r15
0x18001d775  mov     rcx, rbx
0x18001d778  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001d77d  mov     rdx, [rbx+10h]
0x18001d781  cmp     rdx, [rbx+18h]
0x18001d785  jnb     short loc_18001D7A7
0x18001d787  cmp     qword ptr [rbx+18h], 7
0x18001d78c  lea     rax, [rdx+1]
0x18001d790  mov     [rbx+10h], rax
0x18001d794  jbe     short loc_18001D79B
0x18001d796  mov     rcx, [rbx]
0x18001d799  jmp     short loc_18001D79E
0x18001d79b  mov     rcx, rbx
0x18001d79e  mov     dword ptr [rcx+rdx*2], 20h ; ' '
0x18001d7a5  jmp     short loc_18001D7B5
0x18001d7a7  mov     r9d, 20h ; ' '
0x18001d7ad  mov     rcx, rbx; Src
0x18001d7b0  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001d7b5  mov     rcx, rsi; this
0x18001d7b8  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x18001d7bd  test    al, al
0x18001d7bf  jnz     loc_18001D6A0
0x18001d7c5  test    r12b, r12b
0x18001d7c8  jnz     short loc_18001D7D7
0x18001d7ca  mov     edx, 0C007EF94h; int
0x18001d7cf  mov     rcx, rsi; this
0x18001d7d2  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18001d7d7  test    r14b, r14b
0x18001d7da  jnz     short loc_18001D7F6
0x18001d7dc  cmp     qword ptr [rdi+18h], 7
0x18001d7e1  jbe     short loc_18001D7E6
0x18001d7e3  mov     rdi, [rdi]
0x18001d7e6  mov     r8, rdi
0x18001d7e9  mov     edx, 0C007EF95h; int
0x18001d7ee  mov     rcx, rsi; this
0x18001d7f1  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18001d7f6  add     rsp, 68h
0x18001d7fa  pop     r15
0x18001d7fc  pop     r14
0x18001d7fe  pop     r13
0x18001d800  pop     r12
0x18001d802  pop     rdi
0x18001d803  pop     rsi
0x18001d804  pop     rbx
0x18001d805  pop     rbp
0x18001d806  retn
```
