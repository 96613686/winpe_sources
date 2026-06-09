# EventManParser::ValueMapType(void)

- ea: `0x180011b30`
- end: `0x180011eb3`
- name: `?ValueMapType@EventManParser@@AEAA?AV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@XZ`
- size: `899`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180038a44`

## callees

- `0x180011b30`
- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001ed1c`
- `0x1800207e4`
- `0x18002e528`
- `0x180032c1c`
- `0x180035858`
- `0x180037e80`
- `0x180038cc4`
- `0x18003bbbc`
- `0x18003c084`
- `0x18003cb38`
- `0x18004c010`

## string_xrefs

- `0x180011d2c`: `MoveToFirstAttribute`
- `0x180011d52`: `MoveToNextAttribute`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall EventManParser::ValueMapType(XmlReader *this, __int64 *a2)
{
  _QWORD *v4; // rax
  int v5; // r15d
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdi
  wchar_t *v9; // r14
  wchar_t *v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  int v15; // ecx
  __int64 v17; // rdi
  __int64 *v18; // rax
  _QWORD *v19; // rdx
  __int64 v20; // rcx
  size_t N; // [rsp+B0h] [rbp+40h] BYREF
  __int64 *v22; // [rsp+B8h] [rbp+48h]
  wchar_t *S2; // [rsp+C0h] [rbp+50h] BYREF

  v22 = a2;
  v4 = operator new(0x88u);
  N = (size_t)v4;
  *(_OWORD *)v4 = 0;
  v4[2] = 0;
  v4[3] = 7;
  *(_WORD *)v4 = 0;
  *((_OWORD *)v4 + 2) = 0;
  v4[6] = 0;
  v4[7] = 7;
  *((_WORD *)v4 + 16) = 0;
  *((_OWORD *)v4 + 4) = 0;
  v4[10] = 0;
  v4[11] = 7;
  *((_WORD *)v4 + 32) = 0;
  v5 = 1;
  *((_DWORD *)v4 + 24) = 1;
  v4[13] = 0;
  v4[14] = 0;
  v4[15] = 0;
  v4[16] = 0;
  *a2 = (__int64)v4;
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 64LL))(*(_QWORD *)this);
  if ( v6 < 0 )
    XmlReader::ThrowError(this, "MoveToFirstAttribute", v6);
  if ( !v6 )
  {
    while ( 1 )
    {
      S2 = 0;
      LODWORD(N) = 0;
      v7 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, size_t *))(**(_QWORD **)this + 96LL))(
             *(_QWORD *)this,
             &S2,
             &N);
      if ( v7 < 0 )
        XmlReader::ThrowError(this, "GetQualifiedName", v7);
      v8 = (unsigned int)N;
      v9 = S2;
      if ( (unsigned int)N == 4 && !wmemcmp(L"name", S2, 4u) )
        break;
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"symbol", 6, v9, v8) )
      {
        v10 = *(wchar_t **)XmlReader::GetValue(this);
        v11 = *a2;
LABEL_10:
        std::wstring::_Assign<wchar_t>(v11, v10);
      }
      v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 72LL))(*(_QWORD *)this);
      if ( v13 < 0 )
        XmlReader::ThrowError(this, "MoveToNextAttribute", v13);
      if ( v13 )
        goto LABEL_13;
    }
    S2 = 0;
    LODWORD(N) = 0;
    v12 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, size_t *))(**(_QWORD **)this + 128LL))(
            *(_QWORD *)this,
            &S2,
            &N);
    if ( v12 < 0 )
      XmlReader::ThrowError(this, "GetValue", v12);
    v11 = *a2 + 32;
    v10 = S2;
    goto LABEL_10;
  }
LABEL_13:
  if ( !*(_QWORD *)(*a2 + 48) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  v14 = *(_QWORD *)this;
  LODWORD(N) = 0;
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 88LL))(v14);
  if ( v15 < 0 )
    goto LABEL_16;
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) )
  {
    v15 = 1;
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v14 + 48LL))(v14, &N);
    if ( v15 )
    {
LABEL_16:
      v5 = N;
      goto LABEL_17;
    }
    v5 = N;
    v15 = N == 15;
  }
LABEL_17:
  if ( v15 < 0 )
    XmlReader::ThrowError(this, "FirstChild", v15);
  if ( !v15 && (v5 == 1 || XmlReader::NextChildElement(this)) )
  {
    do
    {
      XmlReader::GetLocalName(this);
      if ( (unsigned __int8)EventManParser::ElementMatches(this) )
      {
        v17 = *a2;
        v18 = (__int64 *)EventManParser::ValueMapValueType(this);
        v19 = *(_QWORD **)(v17 + 112);
        if ( v19 == *(_QWORD **)(v17 + 120) )
        {
          std::vector<std::unique_ptr<FILTER_ENTRY>>::_Emplace_reallocate<std::unique_ptr<FILTER_ENTRY>>(
            v17 + 104,
            v19,
            v18);
        }
        else
        {
          v20 = *v18;
          *v18 = 0;
          *v19 = v20;
          *(_QWORD *)(v17 + 112) += 8LL;
        }
        std::unique_ptr<FILTER_ENTRY>::~unique_ptr<FILTER_ENTRY>(&N);
      }
    }
    while ( XmlReader::NextChildElement(this) );
  }
  if ( *(_QWORD *)(*a2 + 104) == *(_QWORD *)(*a2 + 112) )
    EventManParser::ErrorWithFormatMessage(this, -1073221829, L"map");
  return a2;
}

```

## disassembly

```asm
0x180011b30  mov     [rsp-38h+arg_8], rdx
0x180011b35  push    rbp
0x180011b36  push    rbx
0x180011b37  push    rsi
0x180011b38  push    rdi
0x180011b39  push    r12
0x180011b3b  push    r14
0x180011b3d  push    r15
0x180011b3f  mov     rbp, rsp
0x180011b42  sub     rsp, 70h
0x180011b46  mov     rsi, rdx
0x180011b49  mov     rbx, rcx
0x180011b4c  xor     r12d, r12d
0x180011b4f  mov     [rbp+var_50], r12d
0x180011b53  mov     ecx, 88h; Size
0x180011b58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011b5d  mov     [rbp+N], rax
0x180011b61  xorps   xmm0, xmm0
0x180011b64  movups  xmmword ptr [rax], xmm0
0x180011b67  mov     [rax+10h], r12
0x180011b6b  mov     qword ptr [rax+18h], 7
0x180011b73  mov     [rax], r12w
0x180011b77  movups  xmmword ptr [rax+20h], xmm0
0x180011b7b  mov     [rax+30h], r12
0x180011b7f  mov     qword ptr [rax+38h], 7
0x180011b87  mov     [rax+20h], r12w
0x180011b8c  movups  xmmword ptr [rax+40h], xmm0
0x180011b90  mov     [rax+50h], r12
0x180011b94  mov     qword ptr [rax+58h], 7
0x180011b9c  mov     [rax+40h], r12w
0x180011ba1  mov     r15d, 1
0x180011ba7  mov     [rax+60h], r15d
0x180011bab  mov     [rax+68h], r12
0x180011baf  mov     [rax+70h], r12
0x180011bb3  mov     [rax+78h], r12
0x180011bb7  mov     [rax+80h], r12
0x180011bbe  mov     [rsi], rax
0x180011bc1  mov     [rbp+var_50], 3
0x180011bc8  mov     rcx, [rbx]
0x180011bcb  mov     rax, [rcx]
0x180011bce  mov     rax, [rax+40h]
0x180011bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bd7  test    eax, eax
0x180011bd9  js      loc_180011D29
0x180011bdf  jnz     loc_180011CBD
0x180011be5  mov     [rbp+S2], r12
0x180011be9  mov     dword ptr [rbp+N], r12d
0x180011bed  mov     rcx, [rbx]
0x180011bf0  mov     rax, [rcx]
0x180011bf3  lea     r8, [rbp+N]
0x180011bf7  lea     rdx, [rbp+S2]
0x180011bfb  mov     rax, [rax+60h]
0x180011bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c04  test    eax, eax
0x180011c06  js      loc_180011D62
0x180011c0c  mov     edi, dword ptr [rbp+N]
0x180011c0f  mov     r14, [rbp+S2]
0x180011c13  cmp     rdi, 4
0x180011c17  jnz     short loc_180011C2F
0x180011c19  mov     r8d, edi; N
0x180011c1c  mov     rdx, r14; S2
0x180011c1f  lea     rcx, aName_0; "name"
0x180011c26  call    wmemcmp
0x180011c2b  test    eax, eax
0x180011c2d  jz      short loc_180011C62
0x180011c2f  mov     r9, rdi
0x180011c32  mov     r8, r14
0x180011c35  mov     edx, 6
0x180011c3a  lea     rcx, aSymbol; "symbol"
0x180011c41  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180011c46  test    al, al
0x180011c48  jz      short loc_180011CA0
0x180011c4a  lea     rdx, [rbp+var_10]
0x180011c4e  mov     rcx, rbx; this
0x180011c51  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180011c56  mov     r8, [rax+8]
0x180011c5a  mov     rdx, [rax]
0x180011c5d  mov     rcx, [rsi]
0x180011c60  jmp     short loc_180011C9B
0x180011c62  mov     [rbp+S2], r12
0x180011c66  mov     dword ptr [rbp+N], r12d
0x180011c6a  mov     rcx, [rbx]
0x180011c6d  mov     rax, [rcx]
0x180011c70  lea     r8, [rbp+N]
0x180011c74  lea     rdx, [rbp+S2]
0x180011c78  mov     rax, [rax+80h]
0x180011c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c84  test    eax, eax
0x180011c86  js      loc_180011D3C
0x180011c8c  mov     r8d, dword ptr [rbp+N]
0x180011c90  mov     rcx, [rsi]
0x180011c93  add     rcx, 20h ; ' '
0x180011c97  mov     rdx, [rbp+S2]
0x180011c9b  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180011ca0  mov     rcx, [rbx]
0x180011ca3  mov     rax, [rcx]
0x180011ca6  mov     rax, [rax+48h]
0x180011caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011caf  test    eax, eax
0x180011cb1  js      loc_180011D4F
0x180011cb7  jz      loc_180011BE5
0x180011cbd  mov     rax, [rsi]
0x180011cc0  cmp     qword ptr [rax+30h], 0
0x180011cc5  jz      loc_180011D75
0x180011ccb  mov     rdi, [rbx]
0x180011cce  mov     dword ptr [rbp+N], r12d
0x180011cd2  mov     rax, [rdi]
0x180011cd5  mov     rcx, rdi
0x180011cd8  mov     rax, [rax+58h]
0x180011cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ce1  mov     ecx, eax
0x180011ce3  test    eax, eax
0x180011ce5  jns     loc_180011D8E
0x180011ceb  mov     r15d, dword ptr [rbp+N]
0x180011cef  test    ecx, ecx
0x180011cf1  js      loc_180011DDC
0x180011cf7  lea     r14, aMap; "map"
0x180011cfe  test    ecx, ecx
0x180011d00  jz      loc_180011DEF
0x180011d06  mov     rcx, [rsi]
0x180011d09  mov     rax, [rcx+70h]
0x180011d0d  cmp     [rcx+68h], rax
0x180011d11  jz      loc_180011E9D
0x180011d17  mov     rax, rsi
0x180011d1a  add     rsp, 70h
0x180011d1e  pop     r15
0x180011d20  pop     r14
0x180011d22  pop     r12
0x180011d24  pop     rdi
0x180011d25  pop     rsi
0x180011d26  pop     rbx
0x180011d27  pop     rbp
0x180011d28  retn
0x180011d29  mov     r8d, eax; int
0x180011d2c  lea     rdx, aMovetofirstatt; "MoveToFirstAttribute"
0x180011d33  mov     rcx, rbx; this
0x180011d36  call    ?ThrowError@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowError(char const *,long)
0x180011d3c  mov     r8d, eax; int
0x180011d3f  lea     rdx, aGetvalue; "GetValue"
0x180011d46  mov     rcx, rbx; this
0x180011d49  call    ?ThrowError@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowError(char const *,long)
0x180011d4f  mov     r8d, eax; int
0x180011d52  lea     rdx, aMovetonextattr; "MoveToNextAttribute"
0x180011d59  mov     rcx, rbx; this
0x180011d5c  call    ?ThrowError@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowError(char const *,long)
0x180011d62  mov     r8d, eax; int
0x180011d65  lea     rdx, aGetqualifiedna; "GetQualifiedName"
0x180011d6c  mov     rcx, rbx; this
0x180011d6f  call    ?ThrowError@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowError(char const *,long)
0x180011d75  lea     r8, aName_0; "name"
0x180011d7c  mov     edx, 0C007EF3Eh; int
0x180011d81  mov     rcx, rbx; this
0x180011d84  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180011d89  jmp     loc_180011CCB
0x180011d8e  mov     rax, [rdi]
0x180011d91  mov     rcx, rdi
0x180011d94  mov     rax, [rax+0A0h]
0x180011d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011da0  test    eax, eax
0x180011da2  jz      short loc_180011DAC
0x180011da4  mov     ecx, r15d
0x180011da7  jmp     loc_180011CEF
0x180011dac  mov     rax, [rdi]
0x180011daf  lea     rdx, [rbp+N]
0x180011db3  mov     rcx, rdi
0x180011db6  mov     rax, [rax+30h]
0x180011dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dbf  mov     ecx, eax
0x180011dc1  test    eax, eax
0x180011dc3  jnz     loc_180011CEB
0x180011dc9  mov     eax, r15d
0x180011dcc  mov     r15d, dword ptr [rbp+N]
0x180011dd0  cmp     r15d, 0Fh
0x180011dd4  cmovz   ecx, eax
0x180011dd7  jmp     loc_180011CEF
0x180011ddc  mov     r8d, ecx; int
0x180011ddf  lea     rdx, aFirstchild; "FirstChild"
0x180011de6  mov     rcx, rbx; this
0x180011de9  call    ?ThrowError@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowError(char const *,long)
0x180011def  cmp     r15d, 1
0x180011df3  jz      short loc_180011E05
0x180011df5  mov     rcx, rbx; this
0x180011df8  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x180011dfd  test    al, al
0x180011dff  jz      loc_180011D06
0x180011e05  lea     rdx, [rbp+var_30]
0x180011e09  mov     rcx, rbx; this
0x180011e0c  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x180011e11  movups  xmm0, [rbp+var_30]
0x180011e15  movups  xmm1, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x180011e1c  movaps  [rbp+var_20], xmm0
0x180011e20  movaps  [rbp+var_10], xmm1
0x180011e24  mov     [rbp+var_40], r14
0x180011e28  mov     [rbp+var_38], 3
0x180011e30  lea     r9, [rbp+var_20]
0x180011e34  lea     r8, [rbp+var_10]
0x180011e38  lea     rdx, [rbp+var_40]
0x180011e3c  mov     rcx, rbx; this
0x180011e3f  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x180011e44  test    al, al
0x180011e46  jz      short loc_180011E88
0x180011e48  mov     rdi, [rsi]
0x180011e4b  lea     rdx, [rbp+N]
0x180011e4f  mov     rcx, rbx; this
0x180011e52  call    ?ValueMapValueType@EventManParser@@AEAA?AV?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@std@@XZ; EventManParser::ValueMapValueType(void)
0x180011e57  nop
0x180011e58  mov     rdx, [rdi+70h]
0x180011e5c  cmp     rdx, [rdi+78h]
0x180011e60  jz      short loc_180011E72
0x180011e62  mov     rcx, [rax]
0x180011e65  mov     [rax], r12
0x180011e68  mov     [rdx], rcx
0x180011e6b  add     qword ptr [rdi+70h], 8
0x180011e70  jmp     short loc_180011E7F
0x180011e72  mov     r8, rax
0x180011e75  lea     rcx, [rdi+68h]
0x180011e79  call    ??$_Emplace_reallocate@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<FILTER_ENTRY>>::_Emplace_reallocate<std::unique_ptr<FILTER_ENTRY>>(std::unique_ptr<FILTER_ENTRY> * const,std::unique_ptr<FILTER_ENTRY> &&)
0x180011e7e  nop
0x180011e7f  lea     rcx, [rbp+N]
0x180011e83  call    ??1?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<FILTER_ENTRY>::~unique_ptr<FILTER_ENTRY>(void)
0x180011e88  mov     rcx, rbx; this
0x180011e8b  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x180011e90  test    al, al
0x180011e92  jnz     loc_180011E05
0x180011e98  jmp     loc_180011D06
0x180011e9d  mov     r8, r14
0x180011ea0  mov     edx, 0C007EF3Bh; int
0x180011ea5  mov     rcx, rbx; this
0x180011ea8  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180011ead  jmp     loc_180011D17
```
