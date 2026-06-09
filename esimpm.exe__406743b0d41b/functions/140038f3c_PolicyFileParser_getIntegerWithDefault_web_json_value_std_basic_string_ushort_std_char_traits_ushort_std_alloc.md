# PolicyFileParser::getIntegerWithDefault(web::json::value,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,uint)

- ea: `0x140038f3c`
- end: `0x140038fec`
- name: `?getIntegerWithDefault@PolicyFileParser@@YAIVvalue@json@web@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400393ec`

## callees

- `0x140002f60`
- `0x140007590`
- `0x140007630`
- `0x140013df8`
- `0x140038f3c`
- `0x14003e010`

## pseudocode

```c
__int64 __fastcall PolicyFileParser::getIntegerWithDefault(_QWORD *a1, __int64 a2, unsigned int a3)
{
  web::json::value *v6; // rax
  __int64 v7; // rcx

  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 8LL))(*a1) )
  {
    v6 = (web::json::value *)web::json::value::at(a1, a2);
    a3 = web::json::value::as_integer(v6);
    v7 = *a1;
    if ( *a1 )
      goto LABEL_5;
  }
  else
  {
    v7 = *a1;
    if ( *a1 )
LABEL_5:
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 192LL))(v7, 1);
  }
  std::wstring::_Tidy_deallocate(a2);
  return a3;
}

```

## disassembly

```asm
0x140038f3c  mov     r11, rsp
0x140038f3f  mov     [r11+18h], rbx
0x140038f43  mov     [r11+20h], rsi
0x140038f47  push    rdi
0x140038f48  sub     rsp, 40h
0x140038f4c  mov     rax, cs:__security_cookie
0x140038f53  xor     rax, rsp
0x140038f56  mov     [rsp+48h+var_18], rax
0x140038f5b  mov     edi, r8d
0x140038f5e  mov     rsi, rdx
0x140038f61  mov     rbx, rcx
0x140038f64  mov     [r11-28h], rcx
0x140038f68  mov     [r11-20h], rdx
0x140038f6c  mov     rcx, [rcx]
0x140038f6f  mov     rax, [rcx]
0x140038f72  mov     rax, [rax+8]
0x140038f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f7b  test    al, al
0x140038f7d  jz      short loc_140038FA8
0x140038f7f  mov     rdx, rsi
0x140038f82  mov     rcx, rbx
0x140038f85  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x140038f8a  mov     rcx, rax; this
0x140038f8d  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x140038f92  mov     edi, eax
0x140038f94  mov     rcx, [rbx]
0x140038f97  test    rcx, rcx
0x140038f9a  jz      short loc_140038FC5
0x140038f9c  mov     rdx, [rcx]
0x140038f9f  mov     rax, [rdx+0C0h]
0x140038fa6  jmp     short loc_140038FBA
0x140038fa8  mov     rcx, [rbx]
0x140038fab  test    rcx, rcx
0x140038fae  jz      short loc_140038FC5
0x140038fb0  mov     rax, [rcx]
0x140038fb3  mov     rax, [rax+0C0h]
0x140038fba  mov     edx, 1
0x140038fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038fc4  nop
0x140038fc5  mov     rcx, rsi
0x140038fc8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140038fcd  mov     eax, edi
0x140038fcf  mov     rcx, [rsp+48h+var_18]
0x140038fd4  xor     rcx, rsp; StackCookie
0x140038fd7  call    __security_check_cookie
0x140038fdc  mov     rbx, [rsp+48h+arg_10]
0x140038fe1  mov     rsi, [rsp+48h+arg_18]
0x140038fe6  add     rsp, 40h
0x140038fea  pop     rdi
0x140038feb  retn
```
