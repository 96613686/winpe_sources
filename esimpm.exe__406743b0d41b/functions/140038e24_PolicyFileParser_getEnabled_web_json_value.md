# PolicyFileParser::getEnabled(web::json::value)

- ea: `0x140038e24`
- end: `0x140038f33`
- name: `?getEnabled@PolicyFileParser@@YA_NVvalue@json@web@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400393ec`

## callees

- `0x140002f60`
- `0x1400074b0`
- `0x140007630`
- `0x14000dd20`
- `0x140013df8`
- `0x140038e24`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall PolicyFileParser::getEnabled(_QWORD *a1)
{
  char v2; // bl
  wchar_t *v3; // rax
  char v4; // bl
  __int128 v6; // [rsp+28h] [rbp-30h] BYREF
  __int128 v7; // [rsp+38h] [rbp-20h]

  v6 = 0;
  v7 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v6, L"enabled", 7u);
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a1 + 8LL))(*a1, &v6);
  std::wstring::_Tidy_deallocate((char **)&v6);
  if ( v2 )
  {
    v6 = 0;
    v7 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v6, L"enabled", 7u);
    v3 = web::json::value::at(a1, (__int64)&v6);
    v4 = web::json::value::as_bool((web::json::value *)v3);
    std::wstring::_Tidy_deallocate((char **)&v6);
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 192LL))(*a1, 1);
    return v4;
  }
  else
  {
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 192LL))(*a1, 1);
    return 0;
  }
}

```

## disassembly

```asm
0x140038e24  mov     [rsp+arg_8], rbx
0x140038e29  push    rdi
0x140038e2a  sub     rsp, 50h
0x140038e2e  mov     rax, cs:__security_cookie
0x140038e35  xor     rax, rsp
0x140038e38  mov     [rsp+58h+var_10], rax
0x140038e3d  mov     rdi, rcx
0x140038e40  mov     [rsp+58h+var_38], rcx
0x140038e45  xorps   xmm0, xmm0
0x140038e48  movups  [rsp+58h+var_30], xmm0
0x140038e4d  xorps   xmm1, xmm1
0x140038e50  movdqu  [rsp+58h+var_20], xmm1
0x140038e56  mov     r8d, 7
0x140038e5c  lea     rdx, aEnabled_0; "enabled"
0x140038e63  lea     rcx, [rsp+58h+var_30]
0x140038e68  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140038e6d  nop
0x140038e6e  mov     rcx, [rdi]
0x140038e71  mov     rax, [rcx]
0x140038e74  lea     rdx, [rsp+58h+var_30]
0x140038e79  mov     rax, [rax+8]
0x140038e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038e82  mov     bl, al
0x140038e84  lea     rcx, [rsp+58h+var_30]
0x140038e89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140038e8e  test    bl, bl
0x140038e90  jz      short loc_140038EFD
0x140038e92  xorps   xmm0, xmm0
0x140038e95  movups  [rsp+58h+var_30], xmm0
0x140038e9a  xorps   xmm1, xmm1
0x140038e9d  movdqu  [rsp+58h+var_20], xmm1
0x140038ea3  mov     r8d, 7
0x140038ea9  lea     rdx, aEnabled_0; "enabled"
0x140038eb0  lea     rcx, [rsp+58h+var_30]
0x140038eb5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140038eba  nop
0x140038ebb  lea     rdx, [rsp+58h+var_30]
0x140038ec0  mov     rcx, rdi
0x140038ec3  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x140038ec8  mov     rcx, rax; this
0x140038ecb  call    ?as_bool@value@json@web@@QEBA_NXZ; web::json::value::as_bool(void)
0x140038ed0  mov     bl, al
0x140038ed2  lea     rcx, [rsp+58h+var_30]
0x140038ed7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140038edc  nop
0x140038edd  mov     rcx, [rdi]
0x140038ee0  test    rcx, rcx
0x140038ee3  jz      short loc_140038EF9
0x140038ee5  mov     rdx, [rcx]
0x140038ee8  mov     rax, [rdx+0C0h]
0x140038eef  mov     edx, 1
0x140038ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038ef9  mov     al, bl
0x140038efb  jmp     short loc_140038F1B
0x140038efd  mov     rcx, [rdi]
0x140038f00  test    rcx, rcx
0x140038f03  jz      short loc_140038F19
0x140038f05  mov     rax, [rcx]
0x140038f08  mov     edx, 1
0x140038f0d  mov     rax, [rax+0C0h]
0x140038f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f19  xor     al, al
0x140038f1b  mov     rcx, [rsp+58h+var_10]
0x140038f20  xor     rcx, rsp; StackCookie
0x140038f23  call    __security_check_cookie
0x140038f28  mov     rbx, [rsp+58h+arg_8]
0x140038f2d  add     rsp, 50h
0x140038f31  pop     rdi
0x140038f32  retn
```
