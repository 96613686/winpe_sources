# web::json::value::at(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140007630`
- end: `0x14000771c`
- name: `?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `236`
- prototype: `wchar_t *__fastcall(_QWORD *, __int64)`
- caller_count: `12`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140038e24`
- `0x140038f3c`
- `0x1400393ec`
- `0x14003a898`
- `0x14003a9d8`
- `0x14003aba0`
- `0x14003adc4`
- `0x14003b25c`
- `0x14003b424`
- `0x14003b63c`
- `0x14003b8bc`
- `0x14003ba84`

## callees

- `0x140002f60`
- `0x140003b64`
- `0x140006470`
- `0x140007630`
- `0x140007880`
- `0x140022f0c`
- `0x14003e010`

## pseudocode

```c
wchar_t *__fastcall web::json::value::at(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rsi
  wchar_t *v4; // rcx
  wchar_t *v5; // rbx
  wchar_t *v6; // rdx
  const wchar_t *v7; // rax
  size_t v8; // r8
  bool v9; // dl
  int v10; // eax
  wchar_t *S2; // [rsp+20h] [rbp-58h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+28h] [rbp-50h] BYREF

  v3 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 168LL))(*a1);
  web::json::object::find_insert_location(v3, &S2, a2);
  v4 = *(wchar_t **)(v3 + 8);
  v5 = S2;
  if ( S2 == v4
    || (*((_QWORD *)S2 + 3) <= 7u ? (v6 = S2) : (v6 = *(wchar_t **)S2),
        *(_QWORD *)(a2 + 24) <= 7u ? (v7 = (const wchar_t *)a2) : (v7 = *(const wchar_t **)a2),
        (v8 = *(_QWORD *)(a2 + 16), v8 == *((_QWORD *)S2 + 2))
      ? (v8
       ? (v10 = wmemcmp(v7, v6, v8), v4 = *(wchar_t **)(v3 + 8), v9 = v10 != 0)
       : (v9 = 0))
      : (v9 = 1),
        v9 || v5 == v4) )
  {
    web::json::json_exception::json_exception((web::json::json_exception *)pExceptionObject, "Key not found");
    throw (web::json::json_exception *)pExceptionObject;
  }
  return v5 + 16;
}

```

## disassembly

```asm
0x140007630  mov     [rsp+arg_10], rbx
0x140007635  mov     [rsp+arg_18], rsi
0x14000763a  push    rdi
0x14000763b  sub     rsp, 70h
0x14000763f  mov     rax, cs:__security_cookie
0x140007646  xor     rax, rsp
0x140007649  mov     [rsp+78h+var_18], rax
0x14000764e  mov     rcx, [rcx]
0x140007651  mov     rdi, rdx
0x140007654  mov     rax, [rcx]
0x140007657  mov     rax, [rax+0A8h]
0x14000765e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007663  mov     r8, rdi
0x140007666  lea     rdx, [rsp+78h+S2]
0x14000766b  mov     rcx, rax
0x14000766e  mov     rsi, rax
0x140007671  call    ?find_insert_location@object@json@web@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; web::json::object::find_insert_location(std::wstring const &)
0x140007676  mov     rcx, [rsi+8]
0x14000767a  mov     rbx, [rsp+78h+S2]
0x14000767f  cmp     rbx, rcx
0x140007682  jz      short loc_1400076F9
0x140007684  cmp     qword ptr [rbx+18h], 7
0x140007689  jbe     short loc_140007690
0x14000768b  mov     rdx, [rbx]
0x14000768e  jmp     short loc_140007693
0x140007690  mov     rdx, rbx; S2
0x140007693  cmp     qword ptr [rdi+18h], 7
0x140007698  jbe     short loc_14000769F
0x14000769a  mov     rax, [rdi]
0x14000769d  jmp     short loc_1400076A2
0x14000769f  mov     rax, rdi
0x1400076a2  mov     r8, [rdi+10h]; N
0x1400076a6  cmp     r8, [rbx+10h]
0x1400076aa  jz      short loc_1400076B3
0x1400076ac  mov     edx, 1
0x1400076b1  jmp     short loc_1400076CD
0x1400076b3  test    r8, r8
0x1400076b6  jnz     short loc_1400076BC
0x1400076b8  xor     edx, edx
0x1400076ba  jmp     short loc_1400076CD
0x1400076bc  mov     rcx, rax; S1
0x1400076bf  call    wmemcmp
0x1400076c4  mov     rcx, [rsi+8]
0x1400076c8  test    eax, eax
0x1400076ca  setnz   dl
0x1400076cd  test    dl, dl
0x1400076cf  jnz     short loc_1400076F9
0x1400076d1  cmp     rbx, rcx
0x1400076d4  jz      short loc_1400076F9
0x1400076d6  lea     rax, [rbx+20h]
0x1400076da  mov     rcx, [rsp+78h+var_18]
0x1400076df  xor     rcx, rsp; StackCookie
0x1400076e2  call    __security_check_cookie
0x1400076e7  lea     r11, [rsp+78h+var_8]
0x1400076ec  mov     rbx, [r11+20h]
0x1400076f0  mov     rsi, [r11+28h]
0x1400076f4  mov     rsp, r11
0x1400076f7  pop     rdi
0x1400076f8  retn
0x1400076f9  lea     rdx, aKeyNotFound; "Key not found"
0x140007700  lea     rcx, [rsp+78h+pExceptionObject]; this
0x140007705  call    ??0json_exception@json@web@@QEAA@QEBD@Z; web::json::json_exception::json_exception(char const * const)
0x14000770a  lea     rdx, _TI2?AVjson_exception@json@web@@; pThrowInfo
0x140007711  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x140007716  call    _CxxThrowException_0
```
