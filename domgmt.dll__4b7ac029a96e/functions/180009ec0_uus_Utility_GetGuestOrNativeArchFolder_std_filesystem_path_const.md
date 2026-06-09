# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x180009ec0`
- end: `0x180009f4d`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `141`
- prototype: `void *__fastcall(void *, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180009774`
- `0x180009d90`

## callees

- `0x180001ba0`
- `0x180007504`
- `0x180008d88`
- `0x180008f94`
- `0x180009ec0`

## pseudocode

```c
void *__fastcall uus::Utility::GetGuestOrNativeArchFolder(void *a1, struct std::filesystem::path *a2)
{
  __int64 v4; // rcx
  _BYTE v6[32]; // [rsp+38h] [rbp-30h] BYREF

  v4 = -1;
  do
    ++v4;
  while ( uus::Const::archX64[v4] );
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v6);
  std::filesystem::operator/(a1, a2, (std::filesystem *)v6);
  std::wstring::~wstring(v6);
  return a1;
}

```

## disassembly

```asm
0x180009ec0  mov     [rsp+arg_10], rbx
0x180009ec5  push    rdi
0x180009ec6  sub     rsp, 60h
0x180009eca  mov     rax, cs:__security_cookie
0x180009ed1  xor     rax, rsp
0x180009ed4  mov     [rsp+68h+var_10], rax
0x180009ed9  mov     rdi, rdx
0x180009edc  mov     rbx, rcx
0x180009edf  mov     [rsp+68h+var_48], rcx
0x180009ee4  xor     edx, edx
0x180009ee6  mov     rax, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x180009eed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009ef1  inc     rcx
0x180009ef4  cmp     [rax+rcx*2], dx
0x180009ef8  jnz     short loc_180009EF1
0x180009efa  mov     [rsp+68h+var_48], rax
0x180009eff  mov     [rsp+68h+var_40], rcx
0x180009f04  lea     rdx, [rsp+68h+var_48]
0x180009f09  lea     rcx, [rsp+68h+var_30]; void *
0x180009f0e  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180009f13  nop
0x180009f14  lea     r8, [rsp+68h+var_30]; this
0x180009f19  mov     rdx, rdi; struct std::filesystem::path *
0x180009f1c  mov     rcx, rbx; Src
0x180009f1f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180009f24  nop
0x180009f25  lea     rcx, [rsp+68h+var_30]
0x180009f2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009f2f  mov     rax, rbx
0x180009f32  mov     rcx, [rsp+68h+var_10]
0x180009f37  xor     rcx, rsp; StackCookie
0x180009f3a  call    __security_check_cookie
0x180009f3f  mov     rbx, [rsp+68h+arg_10]
0x180009f47  add     rsp, 60h
0x180009f4b  pop     rdi
0x180009f4c  retn
```
