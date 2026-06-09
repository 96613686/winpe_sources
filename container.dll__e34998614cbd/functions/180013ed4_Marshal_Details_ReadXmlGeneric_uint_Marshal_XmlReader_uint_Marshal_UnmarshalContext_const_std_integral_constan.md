# Marshal::Details::ReadXmlGeneric<uint,>(Marshal::XmlReader &,uint *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)

- ea: `0x180013ed4`
- end: `0x180013f97`
- name: `??$ReadXmlGeneric@I$$V@Details@Marshal@@YA_NAEAUXmlReader@1@PEAIAEBVUnmarshalContext@1@U?$integral_constant@_N$00@std@@@Z`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180014a90`
- `0x180014aa0`

## callees

- `0x180002ad0`
- `0x180003650`
- `0x1800051b0`
- `0x180013ed4`
- `0x18001fa24`
- `0x1800208b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x180013f20`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x180013f20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Marshal::Details::ReadXmlGeneric<unsigned int,>(_BYTE *a1, _DWORD *a2, __int64 a3)
{
  char *XmlString; // rax
  unsigned __int64 v6; // rax
  char v7; // bl
  char result; // al
  int pExceptionObject; // [rsp+20h] [rbp-68h] BYREF
  wchar_t *EndPtr; // [rsp+28h] [rbp-60h] BYREF
  unsigned int v11; // [rsp+30h] [rbp-58h] BYREF
  __int64 v12; // [rsp+38h] [rbp-50h]
  char Src[32]; // [rsp+40h] [rbp-48h] BYREF

  v12 = a3;
  try
  {
    XmlString = Marshal::Details::GetXmlString(Src, a1);
    EndPtr = 0;
    if ( *((_QWORD *)XmlString + 3) > 7u )
      XmlString = *(char **)XmlString;
    v6 = wcstoull((const wchar_t *)XmlString, &EndPtr, 0);
    if ( *EndPtr )
    {
      pExceptionObject = 2;
      throw (Marshal::UnmarshalError *)&pExceptionObject;
    }
    if ( (unsigned int)v6 == v6 )
    {
      *a2 = v6;
      v7 = 1;
    }
    else
    {
      Marshal::UnmarshalContext::ReportError(a3, 4);
      v7 = 0;
    }
    std::wstring::~wstring(Src);
    result = v7;
  }
  catch ( Marshal::UnmarshalError v11 )
  {
    Marshal::UnmarshalContext::ReportError(v12, v11);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013ed4  push    rbx
0x180013ed6  push    rsi
0x180013ed7  push    rdi
0x180013ed8  sub     rsp, 70h
0x180013edc  mov     rax, cs:__security_cookie
0x180013ee3  xor     rax, rsp
0x180013ee6  mov     [rsp+88h+var_28], rax
0x180013eeb  mov     rbx, r8
0x180013eee  mov     rdi, rdx
0x180013ef1  mov     [rsp+88h+var_50], rbx
0x180013ef6  mov     rdx, rcx
0x180013ef9  lea     rcx, [rsp+88h+Src]; Src
0x180013efe  call    ?GetXmlString@Details@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUXmlReader@2@@Z; Marshal::Details::GetXmlString(Marshal::XmlReader &)
0x180013f03  nop
0x180013f04  xor     esi, esi
0x180013f06  mov     [rsp+88h+EndPtr], rsi
0x180013f0b  cmp     qword ptr [rax+18h], 7
0x180013f10  jbe     short loc_180013F15
0x180013f12  mov     rax, [rax]
0x180013f15  xor     r8d, r8d; Radix
0x180013f18  lea     rdx, [rsp+88h+EndPtr]; EndPtr
0x180013f1d  mov     rcx, rax; String
0x180013f20  call    cs:__imp_wcstoull
0x180013f27  nop     dword ptr [rax+rax+00h]
0x180013f2c  mov     rdx, rax
0x180013f2f  mov     rcx, [rsp+88h+EndPtr]
0x180013f34  cmp     [rcx], si
0x180013f37  jnz     short loc_180013F7C
0x180013f39  mov     eax, edx
0x180013f3b  cmp     rax, rdx
0x180013f3e  jz      short loc_180013F52
0x180013f40  mov     edx, 4
0x180013f45  mov     rcx, rbx
0x180013f48  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x180013f4d  mov     bl, sil
0x180013f50  jmp     short loc_180013F56
0x180013f52  mov     [rdi], eax
0x180013f54  mov     bl, 1
0x180013f56  lea     rcx, [rsp+88h+Src]
0x180013f5b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013f60  mov     al, bl
0x180013f62  jmp     short loc_180013F66
0x180013f64  xor     al, al
0x180013f66  mov     rcx, [rsp+88h+var_28]
0x180013f6b  xor     rcx, rsp; StackCookie
0x180013f6e  call    __security_check_cookie
0x180013f73  add     rsp, 70h
0x180013f77  pop     rdi
0x180013f78  pop     rsi
0x180013f79  pop     rbx
0x180013f7a  retn
0x180013f7c  mov     [rsp+88h+pExceptionObject], 2
0x180013f84  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x180013f8b  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180013f90  call    _CxxThrowException_0
```
