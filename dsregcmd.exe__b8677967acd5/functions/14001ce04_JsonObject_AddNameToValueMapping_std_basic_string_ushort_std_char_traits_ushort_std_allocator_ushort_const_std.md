# JsonObject::AddNameToValueMapping(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14001ce04`
- end: `0x14001ce80`
- name: `?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140029854`
- `0x14002a154`

## callees

- `0x140001814`
- `0x14001c644`
- `0x14001ce04`
- `0x14001ce88`

## string_xrefs

- `0x14001ce1c`: `onecore\ds\security\dsreg\win32\adal.native\json.cpp`

## pseudocode

```c
__int64 __fastcall JsonObject::AddNameToValueMapping(__int64 a1, __int64 a2, __int64 a3)
{
  _DWORD *v6; // rax
  _DWORD *v7; // rbx

  v6 = operator new(0x40u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\json.cpp");
  v7 = v6;
  if ( v6 )
  {
    v6[2] = 3;
    *(_QWORD *)v6 = &JsonPrimitive::`vftable';
    *((_BYTE *)v6 + 16) = 0;
    *((_QWORD *)v6 + 3) = 0;
    std::wstring::wstring(v6 + 8, a3);
  }
  else
  {
    v7 = 0;
  }
  return JsonObject::AddNameToValueMapping(a1, a2, v7);
}

```

## disassembly

```asm
0x14001ce04  push    rbx
0x14001ce06  push    rbp
0x14001ce07  push    rsi
0x14001ce08  push    rdi
0x14001ce09  sub     rsp, 28h
0x14001ce0d  mov     rbp, r8
0x14001ce10  mov     rdi, rdx
0x14001ce13  mov     rsi, rcx
0x14001ce16  mov     r9d, 49h ; 'I'; int
0x14001ce1c  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14001ce23  lea     edx, [r9-48h]; int
0x14001ce27  lea     ecx, [rdx+3Fh]; unsigned __int64
0x14001ce2a  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14001ce2f  mov     rbx, rax
0x14001ce32  mov     [rsp+48h+arg_18], rax
0x14001ce37  test    rax, rax
0x14001ce3a  jz      short loc_14001CE68
0x14001ce3c  mov     dword ptr [rax+8], 3
0x14001ce43  lea     rax, ??_7JsonPrimitive@@6B@; const JsonPrimitive::`vftable'
0x14001ce4a  mov     [rbx], rax
0x14001ce4d  mov     byte ptr [rbx+10h], 0
0x14001ce51  mov     qword ptr [rbx+18h], 0
0x14001ce59  lea     rcx, [rbx+20h]
0x14001ce5d  mov     rdx, rbp
0x14001ce60  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001ce65  nop
0x14001ce66  jmp     short loc_14001CE6A
0x14001ce68  xor     ebx, ebx
0x14001ce6a  mov     r8, rbx
0x14001ce6d  mov     rdx, rdi
0x14001ce70  mov     rcx, rsi
0x14001ce73  add     rsp, 28h
0x14001ce77  pop     rdi
0x14001ce78  pop     rsi
0x14001ce79  pop     rbp
0x14001ce7a  pop     rbx
0x14001ce7b  jmp     ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@Z; JsonObject::AddNameToValueMapping(std::wstring const &,JsonValue const *)
```
