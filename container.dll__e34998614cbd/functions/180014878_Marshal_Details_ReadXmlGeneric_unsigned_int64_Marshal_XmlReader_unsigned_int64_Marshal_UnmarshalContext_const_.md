# Marshal::Details::ReadXmlGeneric<unsigned __int64,>(Marshal::XmlReader &,unsigned __int64 *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)

- ea: `0x180014878`
- end: `0x180014923`
- name: `??$ReadXmlGeneric@_K$$V@Details@Marshal@@YA_NAEAUXmlReader@1@PEA_KAEBVUnmarshalContext@1@U?$integral_constant@_N$00@std@@@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180016580`

## callees

- `0x180002ad0`
- `0x180003650`
- `0x1800051b0`
- `0x180014878`
- `0x18001fa24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x1800148c3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x1800148c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Marshal::Details::ReadXmlGeneric<unsigned __int64,>(_BYTE *a1, unsigned __int64 *a2, __int64 a3)
{
  char *XmlString; // rax
  unsigned __int64 v5; // rax
  char result; // al
  int pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  wchar_t *EndPtr; // [rsp+28h] [rbp-50h] BYREF
  unsigned int v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 v10; // [rsp+38h] [rbp-40h]
  char Src[32]; // [rsp+40h] [rbp-38h] BYREF

  try
  {
    v10 = a3;
    XmlString = Marshal::Details::GetXmlString(Src, a1);
    EndPtr = 0;
    if ( *((_QWORD *)XmlString + 3) > 7u )
      XmlString = *(char **)XmlString;
    v5 = wcstoull((const wchar_t *)XmlString, &EndPtr, 0);
    if ( *EndPtr )
    {
      pExceptionObject = 2;
      throw (Marshal::UnmarshalError *)&pExceptionObject;
    }
    *a2 = v5;
    std::wstring::~wstring(Src);
    result = 1;
  }
  catch ( Marshal::UnmarshalError v9 )
  {
    Marshal::UnmarshalContext::ReportError(v10, v9);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180014878  mov     [rsp+arg_18], rbx
0x18001487d  push    rdi
0x18001487e  sub     rsp, 70h
0x180014882  mov     rax, cs:__security_cookie
0x180014889  xor     rax, rsp
0x18001488c  mov     [rsp+78h+var_18], rax
0x180014891  mov     rbx, rdx
0x180014894  mov     [rsp+78h+var_40], r8
0x180014899  mov     rdx, rcx
0x18001489c  lea     rcx, [rsp+78h+Src]; Src
0x1800148a1  call    ?GetXmlString@Details@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUXmlReader@2@@Z; Marshal::Details::GetXmlString(Marshal::XmlReader &)
0x1800148a6  nop
0x1800148a7  xor     edi, edi
0x1800148a9  mov     [rsp+78h+EndPtr], rdi
0x1800148ae  cmp     qword ptr [rax+18h], 7
0x1800148b3  jbe     short loc_1800148B8
0x1800148b5  mov     rax, [rax]
0x1800148b8  xor     r8d, r8d; Radix
0x1800148bb  lea     rdx, [rsp+78h+EndPtr]; EndPtr
0x1800148c0  mov     rcx, rax; String
0x1800148c3  call    cs:__imp_wcstoull
0x1800148ca  nop     dword ptr [rax+rax+00h]
0x1800148cf  mov     rcx, [rsp+78h+EndPtr]
0x1800148d4  cmp     [rcx], di
0x1800148d7  jnz     short loc_180014908
0x1800148d9  mov     [rbx], rax
0x1800148dc  lea     rcx, [rsp+78h+Src]
0x1800148e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800148e6  mov     al, 1
0x1800148e8  jmp     short loc_1800148EC
0x1800148ea  xor     al, al
0x1800148ec  mov     rcx, [rsp+78h+var_18]
0x1800148f1  xor     rcx, rsp; StackCookie
0x1800148f4  call    __security_check_cookie
0x1800148f9  mov     rbx, [rsp+78h+arg_18]
0x180014901  add     rsp, 70h
0x180014905  pop     rdi
0x180014906  retn
0x180014908  mov     [rsp+78h+pExceptionObject], 2
0x180014910  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x180014917  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001491c  call    _CxxThrowException_0
```
