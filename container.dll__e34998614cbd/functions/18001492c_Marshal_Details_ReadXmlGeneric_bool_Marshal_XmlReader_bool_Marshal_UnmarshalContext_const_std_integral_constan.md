# Marshal::Details::ReadXmlGeneric<bool,>(Marshal::XmlReader &,bool *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)

- ea: `0x18001492c`
- end: `0x180014a7f`
- name: `??$ReadXmlGeneric@_N$$V@Details@Marshal@@YA_NAEAUXmlReader@1@PEA_NAEBVUnmarshalContext@1@U?$integral_constant@_N$00@std@@@Z`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016590`

## callees

- `0x180002ad0`
- `0x180003650`
- `0x1800051b0`
- `0x18001492c`
- `0x18001fa24`
- `0x180021058`
- `0x180022094`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Marshal::Details::ReadXmlGeneric<bool,>(_BYTE *a1, char *a2, __int64 a3)
{
  char *XmlString; // rax
  char *v6; // rbx
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  char v10; // di
  int v11; // eax
  char result; // al
  int pExceptionObject; // [rsp+20h] [rbp-88h] BYREF
  const wchar_t *v14; // [rsp+30h] [rbp-78h] BYREF
  __int64 v15; // [rsp+38h] [rbp-70h]
  const wchar_t *v16; // [rsp+40h] [rbp-68h] BYREF
  __int64 v17; // [rsp+48h] [rbp-60h]
  unsigned int v18; // [rsp+50h] [rbp-58h] BYREF
  __int64 v19; // [rsp+58h] [rbp-50h]
  char Src[32]; // [rsp+60h] [rbp-48h] BYREF

  try
  {
    v19 = a3;
    XmlString = Marshal::Details::GetXmlString(Src, a1);
    v6 = XmlString;
    if ( *((_QWORD *)XmlString + 3) <= 7u )
      v7 = (const wchar_t *)XmlString;
    else
      v7 = *(const wchar_t **)XmlString;
    v8 = *((_QWORD *)XmlString + 2);
    if ( v8 == 4 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 2) != 0 )
      {
        v14 = L"true";
        v15 = 4;
        v16 = v7;
        v17 = 4;
        v9 = Marshal::Details::StringCompareCaseInsensitive(&v16, &v14);
      }
      else
      {
        v9 = wmemcmp(v7, L"true", 4u);
      }
      v10 = 0;
      if ( !v9 )
      {
        v10 = 1;
LABEL_20:
        *a2 = v10;
        std::wstring::~wstring(Src);
        return 1;
      }
      v8 = *((_QWORD *)v6 + 2);
    }
    else
    {
      v10 = 0;
    }
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(char **)v6;
    if ( v8 != 5
      || ((*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 2) == 0
        ? (v11 = wmemcmp((const wchar_t *)v6, L"false", 5u))
        : (v16 = L"false",
           v17 = 5,
           v14 = (const wchar_t *)v6,
           v15 = 5,
           v11 = Marshal::Details::StringCompareCaseInsensitive(&v14, &v16)),
          v11) )
    {
      pExceptionObject = 9;
      throw (Marshal::UnmarshalError *)&pExceptionObject;
    }
    goto LABEL_20;
  }
  catch ( Marshal::UnmarshalError v18 )
  {
    Marshal::UnmarshalContext::ReportError(v19, v18);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001492c  mov     [rsp+arg_18], rbx
0x180014931  push    rsi
0x180014932  push    rdi
0x180014933  push    r14
0x180014935  sub     rsp, 90h
0x18001493c  mov     rax, cs:__security_cookie
0x180014943  xor     rax, rsp
0x180014946  mov     [rsp+0A8h+var_28], rax
0x18001494e  mov     rsi, r8
0x180014951  mov     r14, rdx
0x180014954  mov     [rsp+0A8h+var_50], r8
0x180014959  mov     rdx, rcx
0x18001495c  lea     rcx, [rsp+0A8h+Src]; Src
0x180014961  call    ?GetXmlString@Details@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUXmlReader@2@@Z; Marshal::Details::GetXmlString(Marshal::XmlReader &)
0x180014966  mov     rbx, rax
0x180014969  cmp     qword ptr [rax+18h], 7
0x18001496e  jbe     short loc_180014975
0x180014970  mov     rcx, [rax]
0x180014973  jmp     short loc_180014978
0x180014975  mov     rcx, rbx; S1
0x180014978  mov     rax, [rax+10h]
0x18001497c  mov     r8d, 4; N
0x180014982  cmp     rax, r8
0x180014985  jnz     short loc_1800149D3
0x180014987  mov     rax, [rsi+8]
0x18001498b  lea     rdx, aTrue; "true"
0x180014992  test    byte ptr [rax+18h], 2
0x180014996  jz      short loc_1800149BD
0x180014998  mov     [rsp+0A8h+var_78], rdx
0x18001499d  mov     [rsp+0A8h+var_70], r8
0x1800149a2  mov     [rsp+0A8h+var_68], rcx
0x1800149a7  mov     [rsp+0A8h+var_60], r8
0x1800149ac  lea     rdx, [rsp+0A8h+var_78]
0x1800149b1  lea     rcx, [rsp+0A8h+var_68]
0x1800149b6  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800149bb  jmp     short loc_1800149C2
0x1800149bd  call    wmemcmp
0x1800149c2  xor     edi, edi
0x1800149c4  test    eax, eax
0x1800149c6  jz      short loc_1800149CE
0x1800149c8  mov     rax, [rbx+10h]
0x1800149cc  jmp     short loc_1800149D5
0x1800149ce  mov     dil, 1
0x1800149d1  jmp     short loc_180014A2C
0x1800149d3  xor     edi, edi
0x1800149d5  cmp     qword ptr [rbx+18h], 7
0x1800149da  jbe     short loc_1800149DF
0x1800149dc  mov     rbx, [rbx]
0x1800149df  mov     r8d, 5; N
0x1800149e5  cmp     rax, r8
0x1800149e8  jnz     short loc_180014A64
0x1800149ea  mov     rax, [rsi+8]
0x1800149ee  lea     rdx, aFalse; "false"
0x1800149f5  test    byte ptr [rax+18h], 2
0x1800149f9  jz      short loc_180014A20
0x1800149fb  mov     [rsp+0A8h+var_68], rdx
0x180014a00  mov     [rsp+0A8h+var_60], r8
0x180014a05  mov     [rsp+0A8h+var_78], rbx
0x180014a0a  mov     [rsp+0A8h+var_70], r8
0x180014a0f  lea     rdx, [rsp+0A8h+var_68]
0x180014a14  lea     rcx, [rsp+0A8h+var_78]
0x180014a19  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x180014a1e  jmp     short loc_180014A28
0x180014a20  mov     rcx, rbx; S1
0x180014a23  call    wmemcmp
0x180014a28  test    eax, eax
0x180014a2a  jnz     short loc_180014A64
0x180014a2c  mov     [r14], dil
0x180014a2f  lea     rcx, [rsp+0A8h+Src]
0x180014a34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014a39  mov     al, 1
0x180014a3b  jmp     short loc_180014A3F
0x180014a3d  xor     al, al
0x180014a3f  mov     rcx, [rsp+0A8h+var_28]
0x180014a47  xor     rcx, rsp; StackCookie
0x180014a4a  call    __security_check_cookie
0x180014a4f  mov     rbx, [rsp+0A8h+arg_18]
0x180014a57  add     rsp, 90h
0x180014a5e  pop     r14
0x180014a60  pop     rdi
0x180014a61  pop     rsi
0x180014a62  retn
0x180014a64  mov     [rsp+0A8h+pExceptionObject], 9
0x180014a6c  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x180014a73  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180014a78  call    _CxxThrowException_0
```
