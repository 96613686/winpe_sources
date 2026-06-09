# JsonObject::GetJsonDataAsString(ushort const *)

- ea: `0x14001cf60`
- end: `0x14001d063`
- name: `?GetJsonDataAsString@JsonObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `259`
- prototype: `__m128i *__fastcall(__int64, __m128i *, _WORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000d384`
- `0x140024cc0`

## callees

- `0x140001b60`
- `0x140003044`
- `0x1400032ec`
- `0x14001ca24`
- `0x14001cf60`
- `0x14001d2d4`
- `0x14001d36c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__m128i *__fastcall JsonObject::GetJsonDataAsString(__int64 a1, __m128i *a2, _WORD *a3)
{
  __int64 ValueForName; // rbx
  __m128i si128; // xmm1
  __m128i v7; // xmm2
  __int64 StringValue; // rax
  __m128i v10; // [rsp+30h] [rbp-50h] BYREF
  __m128i v11; // [rsp+40h] [rbp-40h] BYREF
  char *v12[4]; // [rsp+50h] [rbp-30h] BYREF

  std::wstring::wstring(&v10, a3);
  ValueForName = JsonObject::GetValueForName(a1, &v10);
  std::wstring::~wstring((char **)&v10);
  if ( ValueForName )
  {
    v10 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v7 = si128;
    v11 = si128;
    v10.m128i_i16[0] = 0;
    if ( (unsigned int)(*(_DWORD *)(ValueForName + 8) - 3) <= 2 )
    {
      StringValue = JsonPrimitive::GetStringValue(ValueForName, v12);
      std::wstring::operator=(&v10, StringValue);
      std::wstring::~wstring(v12);
      v7 = _mm_loadu_si128(&v11);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    a2[1].m128i_i64[0] = 0;
    a2[1].m128i_i64[1] = 0;
    *a2 = v10;
    a2[1] = v7;
    v11 = si128;
    v10.m128i_i16[0] = 0;
    std::wstring::~wstring((char **)&v10);
  }
  else
  {
    std::wstring::wstring(a2, &dword_14003353C);
  }
  return a2;
}

```

## disassembly

```asm
0x14001cf60  push    rbp
0x14001cf62  push    rbx
0x14001cf63  push    rdi
0x14001cf64  mov     rbp, rsp
0x14001cf67  sub     rsp, 80h
0x14001cf6e  mov     rax, cs:__security_cookie
0x14001cf75  xor     rax, rsp
0x14001cf78  mov     [rbp+var_10], rax
0x14001cf7c  mov     rdi, rdx
0x14001cf7f  mov     rbx, rcx
0x14001cf82  mov     [rbp+var_58], rdx
0x14001cf86  mov     rdx, r8
0x14001cf89  lea     rcx, [rbp+var_50]
0x14001cf8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14001cf92  lea     rdx, [rbp+var_50]
0x14001cf96  mov     rcx, rbx
0x14001cf99  call    ?GetValueForName@JsonObject@@QEBAPEBVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; JsonObject::GetValueForName(std::wstring const &)
0x14001cf9e  mov     rbx, rax
0x14001cfa1  lea     rcx, [rbp+var_50]
0x14001cfa5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cfaa  test    rbx, rbx
0x14001cfad  jnz     short loc_14001CFC3
0x14001cfaf  lea     rdx, dword_14003353C
0x14001cfb6  mov     rcx, rdi
0x14001cfb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14001cfbe  jmp     loc_14001D049
0x14001cfc3  xorps   xmm0, xmm0
0x14001cfc6  movups  [rbp+var_50], xmm0
0x14001cfca  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14001cfd2  movdqa  xmm2, xmm1
0x14001cfd6  movdqu  [rbp+var_40], xmm1
0x14001cfdb  xor     eax, eax
0x14001cfdd  mov     word ptr [rbp+var_50], ax
0x14001cfe1  mov     eax, [rbx+8]
0x14001cfe4  sub     eax, 3
0x14001cfe7  cmp     eax, 2
0x14001cfea  ja      short loc_14001D01A
0x14001cfec  lea     rdx, [rbp+var_30]
0x14001cff0  mov     rcx, rbx
0x14001cff3  call    ?GetStringValue@JsonPrimitive@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; JsonPrimitive::GetStringValue(void)
0x14001cff8  mov     rdx, rax
0x14001cffb  lea     rcx, [rbp+var_50]
0x14001cfff  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14001d004  lea     rcx, [rbp+var_30]
0x14001d008  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001d00d  movdqu  xmm2, [rbp+var_40]
0x14001d012  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14001d01a  mov     qword ptr [rdi+10h], 0
0x14001d022  mov     qword ptr [rdi+18h], 0
0x14001d02a  movups  xmm0, [rbp+var_50]
0x14001d02e  movups  xmmword ptr [rdi], xmm0
0x14001d031  movups  xmmword ptr [rdi+10h], xmm2
0x14001d035  movdqu  [rbp+var_40], xmm1
0x14001d03a  xor     eax, eax
0x14001d03c  mov     word ptr [rbp+var_50], ax
0x14001d040  lea     rcx, [rbp+var_50]
0x14001d044  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001d049  mov     rax, rdi
0x14001d04c  mov     rcx, [rbp+var_10]
0x14001d050  xor     rcx, rsp; StackCookie
0x14001d053  call    __security_check_cookie
0x14001d058  add     rsp, 80h
0x14001d05f  pop     rdi
0x14001d060  pop     rbx
0x14001d061  pop     rbp
0x14001d062  retn
```
