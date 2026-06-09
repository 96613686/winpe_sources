# web::json::details::CreateException<web::json::details::JSON_Parser<ushort>::Token>(web::json::details::JSON_Parser<ushort>::Token const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140008540`
- end: `0x14000861c`
- name: `??$CreateException@UToken@?$JSON_Parser@G@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@G@012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `220`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140008af0`

## callees

- `0x140003b64`
- `0x140008ce0`
- `0x140008d60`
- `0x140008d90`
- `0x14000c820`
- `0x14001e8f4`
- `0x14001ecc0`
- `0x14002d8dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall __noreturn web::json::details::CreateException<web::json::details::JSON_Parser<unsigned short>::Token>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  _BYTE Src[32]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+40h] [rbp-48h] BYREF

  std::string::string(Src, "* Line ");
  v4 = std::to_string(pExceptionObject, *(_QWORD *)(a1 + 40));
  std::string::operator+=(Src, v4);
  std::string::~string(pExceptionObject);
  std::string::operator+=(Src, ", Column ");
  v5 = std::to_string(pExceptionObject, *(_QWORD *)(a1 + 48));
  std::string::operator+=(Src, v5);
  std::string::~string(pExceptionObject);
  std::string::operator+=(Src, " Syntax error: ");
  v6 = utility::conversions::to_utf8string(pExceptionObject, a2);
  std::string::operator+=(Src, v6);
  std::string::~string(pExceptionObject);
  web::json::json_exception::json_exception(pExceptionObject, Src);
  throw (web::json::json_exception *)pExceptionObject;
}

```

## disassembly

```asm
0x140008540  mov     [rsp+arg_10], rbx
0x140008545  push    rdi
0x140008546  sub     rsp, 80h
0x14000854d  mov     rdi, rdx
0x140008550  mov     rbx, rcx
0x140008553  lea     rdx, aLine; "* Line "
0x14000855a  lea     rcx, [rsp+88h+Src]
0x14000855f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140008564  nop
0x140008565  mov     rdx, [rbx+28h]
0x140008569  lea     rcx, [rsp+88h+pExceptionObject]
0x14000856e  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K@Z; std::to_string(unsigned __int64)
0x140008573  nop
0x140008574  mov     rdx, rax
0x140008577  lea     rcx, [rsp+88h+Src]
0x14000857c  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator+=(std::string const &)
0x140008581  nop
0x140008582  lea     rcx, [rsp+88h+pExceptionObject]
0x140008587  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000858c  lea     rdx, aColumn; ", Column "
0x140008593  lea     rcx, [rsp+88h+Src]; Src
0x140008598  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x14000859d  mov     rdx, [rbx+30h]
0x1400085a1  lea     rcx, [rsp+88h+pExceptionObject]
0x1400085a6  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K@Z; std::to_string(unsigned __int64)
0x1400085ab  nop
0x1400085ac  mov     rdx, rax
0x1400085af  lea     rcx, [rsp+88h+Src]
0x1400085b4  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator+=(std::string const &)
0x1400085b9  nop
0x1400085ba  lea     rcx, [rsp+88h+pExceptionObject]
0x1400085bf  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400085c4  lea     rdx, aSyntaxError; " Syntax error: "
0x1400085cb  lea     rcx, [rsp+88h+Src]; Src
0x1400085d0  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x1400085d5  mov     rdx, rdi
0x1400085d8  lea     rcx, [rsp+88h+pExceptionObject]
0x1400085dd  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x1400085e2  nop
0x1400085e3  mov     rdx, rax
0x1400085e6  lea     rcx, [rsp+88h+Src]
0x1400085eb  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator+=(std::string const &)
0x1400085f0  nop
0x1400085f1  lea     rcx, [rsp+88h+pExceptionObject]
0x1400085f6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400085fb  lea     rdx, [rsp+88h+Src]
0x140008600  lea     rcx, [rsp+88h+pExceptionObject]
0x140008605  call    ??0json_exception@json@web@@QEAA@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::json::json_exception::json_exception(std::string &&)
0x14000860a  lea     rdx, _TI2?AVjson_exception@json@web@@; pThrowInfo
0x140008611  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x140008616  call    _CxxThrowException_0
```
