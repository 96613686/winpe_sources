# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::json_value::json_value(nlohmann::detail::value_t)

- ea: `0x18001a674`
- end: `0x18001a803`
- name: `??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z`
- size: `399`
- prototype: ``
- caller_count: `13`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180012cec`
- `0x180013e58`
- `0x180015218`
- `0x180017598`
- `0x180017730`
- `0x1800178d0`
- `0x180017b94`
- `0x180018df4`
- `0x18001b560`
- `0x18001b694`
- `0x18001fb28`
- `0x180025448`
- `0x18002b264`

## callees

- `0x180002490`
- `0x18000289c`
- `0x180002f04`
- `0x180019fb8`
- `0x18001a674`
- `0x1800227b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
        _QWORD *a1,
        char a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  char v7; // [rsp+20h] [rbp-78h] BYREF
  char *v8; // [rsp+60h] [rbp-38h]
  _QWORD *v9; // [rsp+68h] [rbp-30h]

  switch ( a2 )
  {
    case 0:
      goto LABEL_18;
    case 1:
      v4 = operator new(0x10u);
      v8 = &v7;
      v9 = v4;
      *v4 = 0;
      v4[1] = 0;
      v5 = operator new(0x50u);
      *v5 = v5;
      v5[1] = v5;
      v5[2] = v5;
      *((_WORD *)v5 + 12) = 257;
      *v4 = v5;
      goto LABEL_17;
    case 2:
      v3 = operator new(0x18u);
      *v3 = 0;
      v3[1] = 0;
      v3[2] = 0;
      goto LABEL_15;
    case 3:
      v4 = operator new(0x20u);
      v8 = &v7;
      v9 = v4;
      std::string::string(v4, &word_1800321F2);
LABEL_17:
      *a1 = v4;
      return a1;
    case 4:
      *(_BYTE *)a1 = 0;
      return a1;
    case 5:
    case 6:
    case 7:
LABEL_18:
      *a1 = 0;
      return a1;
    case 8:
      v3 = operator new(0x20u);
      *v3 = 0;
      v3[1] = 0;
      v3[2] = 0;
      *((_WORD *)v3 + 12) = 0;
LABEL_15:
      *a1 = v3;
      return a1;
  }
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18001a674  mov     [rsp+arg_8], rbx
0x18001a679  mov     [rsp+arg_10], rsi
0x18001a67e  push    rdi
0x18001a67f  sub     rsp, 90h
0x18001a686  mov     rax, cs:__security_cookie
0x18001a68d  xor     rax, rsp
0x18001a690  mov     [rsp+98h+var_18], rax
0x18001a698  mov     rdi, rcx
0x18001a69b  movzx   ecx, dl
0x18001a69e  xor     esi, esi
0x18001a6a0  test    dl, dl
0x18001a6a2  jz      loc_18001A7A5
0x18001a6a8  sub     ecx, 1
0x18001a6ab  jz      loc_18001A75F
0x18001a6b1  sub     ecx, 1
0x18001a6b4  jz      loc_18001A745
0x18001a6ba  sub     ecx, 1
0x18001a6bd  jz      short loc_18001A717
0x18001a6bf  sub     ecx, 1
0x18001a6c2  jz      short loc_18001A70F
0x18001a6c4  sub     ecx, 1
0x18001a6c7  jz      loc_18001A7A5
0x18001a6cd  sub     ecx, 1
0x18001a6d0  jz      loc_18001A7A5
0x18001a6d6  sub     ecx, 1
0x18001a6d9  jz      loc_18001A7A5
0x18001a6df  cmp     ecx, 1
0x18001a6e2  jz      short loc_18001A6F4
0x18001a6e4  mov     [rdi], rsi
0x18001a6e7  test    dl, dl
0x18001a6e9  jz      loc_18001A7D0
0x18001a6ef  jmp     loc_18001A7A8
0x18001a6f4  mov     ecx, 20h ; ' '; Size
0x18001a6f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a6fe  mov     [rax], rsi
0x18001a701  mov     [rax+8], rsi
0x18001a705  mov     [rax+10h], rsi
0x18001a709  mov     [rax+18h], si
0x18001a70d  jmp     short loc_18001A75A
0x18001a70f  mov     [rdi], sil
0x18001a712  jmp     loc_18001A7A8
0x18001a717  mov     ecx, 20h ; ' '; Size
0x18001a71c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a721  mov     rbx, rax
0x18001a724  lea     rax, [rsp+98h+var_78]
0x18001a729  mov     [rsp+98h+var_38], rax
0x18001a72e  mov     [rsp+98h+var_30], rbx
0x18001a733  lea     rdx, word_1800321F2
0x18001a73a  mov     rcx, rbx
0x18001a73d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001a742  nop
0x18001a743  jmp     short loc_18001A7A0
0x18001a745  mov     ecx, 18h; Size
0x18001a74a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a74f  mov     [rax], rsi
0x18001a752  mov     [rax+8], rsi
0x18001a756  mov     [rax+10h], rsi
0x18001a75a  mov     [rdi], rax
0x18001a75d  jmp     short loc_18001A7A8
0x18001a75f  mov     ecx, 10h; Size
0x18001a764  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a769  mov     rbx, rax
0x18001a76c  lea     rax, [rsp+98h+var_78]
0x18001a771  mov     [rsp+98h+var_38], rax
0x18001a776  mov     [rsp+98h+var_30], rbx
0x18001a77b  mov     [rbx], rsi
0x18001a77e  mov     [rbx+8], rsi
0x18001a782  mov     ecx, 50h ; 'P'; Size
0x18001a787  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a78c  mov     [rax], rax
0x18001a78f  mov     [rax+8], rax
0x18001a793  mov     [rax+10h], rax
0x18001a797  mov     word ptr [rax+18h], 101h
0x18001a79d  mov     [rbx], rax
0x18001a7a0  mov     [rdi], rbx
0x18001a7a3  jmp     short loc_18001A7A8
0x18001a7a5  mov     [rdi], rsi
0x18001a7a8  mov     rax, rdi
0x18001a7ab  mov     rcx, [rsp+98h+var_18]
0x18001a7b3  xor     rcx, rsp; StackCookie
0x18001a7b6  call    __security_check_cookie
0x18001a7bb  lea     r11, [rsp+98h+var_8]
0x18001a7c3  mov     rbx, [r11+18h]
0x18001a7c7  mov     rsi, [r11+20h]
0x18001a7cb  mov     rsp, r11
0x18001a7ce  pop     rdi
0x18001a7cf  retn
0x18001a7d0  lea     rdx, a961c151d2e87f2; "961c151d2e87f2686a955a9be24d316f1362bf2"...
0x18001a7d7  lea     rcx, [rsp+98h+var_38]
0x18001a7dc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001a7e1  nop
0x18001a7e2  lea     r8, [rsp+98h+var_38]
0x18001a7e7  lea     rcx, [rsp+98h+pExceptionObject]
0x18001a7ec  call    ?create@other_error@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::other_error::create(int,std::string const &)
0x18001a7f1  lea     rdx, _TI3?AVother_error@detail@nlohmann@@; pThrowInfo
0x18001a7f8  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001a7fd  call    _CxxThrowException_0
```
