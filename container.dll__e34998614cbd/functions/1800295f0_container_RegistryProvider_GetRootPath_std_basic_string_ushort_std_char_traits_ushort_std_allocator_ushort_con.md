# container::RegistryProvider::GetRootPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800295f0`
- end: `0x1800296a0`
- name: `?GetRootPath@RegistryProvider@container@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@0@Z`
- size: `176`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000df80`
- `0x180029bc0`

## callees

- `0x180002ad0`
- `0x1800051b0`
- `0x18000be30`
- `0x1800227ec`
- `0x180022c94`
- `0x1800295f0`

## string_xrefs

- `0x18002964b`: `\Registry\WC\Silo`

## pseudocode

```c
__int64 __fastcall container::RegistryProvider::GetRootPath(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rcx
  _BYTE v7[32]; // [rsp+50h] [rbp-38h] BYREF

  v5 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v5) < 0x11 )
    std::_Xlen_string();
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::wstring(v7, a2, a3, L"\\Registry\\WC\\Silo", 17, a2, v5);
  std::operator+<unsigned short>(a1, v7, a3);
  std::wstring::~wstring(v7);
  return a1;
}

```

## disassembly

```asm
0x1800295f0  mov     [rsp+arg_18], rbx
0x1800295f5  push    rdi
0x1800295f6  sub     rsp, 80h
0x1800295fd  mov     rax, cs:__security_cookie
0x180029604  xor     rax, rsp
0x180029607  mov     [rsp+88h+var_18], rax
0x18002960c  mov     rdi, r8
0x18002960f  mov     rbx, rcx
0x180029612  mov     [rsp+88h+var_40], rcx
0x180029617  mov     rcx, [rdx+10h]
0x18002961b  mov     rax, 7FFFFFFFFFFFFFFEh
0x180029625  sub     rax, rcx
0x180029628  cmp     rax, 11h
0x18002962c  jb      short loc_18002969A
0x18002962e  cmp     qword ptr [rdx+18h], 7
0x180029633  jbe     short loc_180029638
0x180029635  mov     rdx, [rdx]
0x180029638  mov     [rsp+88h+var_58], rcx
0x18002963d  mov     [rsp+88h+var_60], rdx
0x180029642  mov     [rsp+88h+var_68], 11h
0x18002964b  lea     r9, aRegistryWcSilo; "\\Registry\\WC\\Silo"
0x180029652  lea     rcx, [rsp+88h+var_38]
0x180029657  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002965c  nop
0x18002965d  mov     r8, rdi
0x180029660  lea     rdx, [rsp+88h+var_38]
0x180029665  mov     rcx, rbx
0x180029668  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18002966d  nop
0x18002966e  lea     rcx, [rsp+88h+var_38]
0x180029673  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029678  mov     rax, rbx
0x18002967b  mov     rcx, [rsp+88h+var_18]
0x180029680  xor     rcx, rsp; StackCookie
0x180029683  call    __security_check_cookie
0x180029688  mov     rbx, [rsp+88h+arg_18]
0x180029690  add     rsp, 80h
0x180029697  pop     rdi
0x180029698  retn
0x18002969a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
