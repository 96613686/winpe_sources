# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::_Tidy(void)

- ea: `0x140006e90`
- end: `0x140006f62`
- name: `?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAXXZ`
- size: `210`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140006580`
- `0x140006be0`

## callees

- `0x140003244`
- `0x140006e90`
- `0x140013df8`
- `0x14003e010`

## pseudocode

```c
__int64 __fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Tidy(char **a1)
{
  char *v1; // rbx
  char *i; // rsi
  __int64 v4; // rcx
  char *v5; // r8
  char *v6; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( *a1 )
  {
    for ( i = a1[1]; v1 != i; v1 += 40 )
    {
      v4 = *((_QWORD *)v1 + 4);
      if ( v4 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 192LL))(v4, 1);
      std::wstring::_Tidy_deallocate(v1);
    }
    v5 = *a1;
    if ( (unsigned __int64)(40 * ((a1[2] - *a1) / 40)) < 0x1000 )
    {
      v6 = *a1;
    }
    else
    {
      v6 = (char *)*((_QWORD *)v5 - 1);
      if ( (unsigned __int64)(v5 - v6 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v6);
    result = 0;
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140006e90  mov     [rsp+arg_8], rbx
0x140006e95  push    rdi
0x140006e96  sub     rsp, 20h
0x140006e9a  mov     rbx, [rcx]
0x140006e9d  mov     rdi, rcx
0x140006ea0  test    rbx, rbx
0x140006ea3  jz      loc_140006F57
0x140006ea9  mov     [rsp+28h+arg_0], rsi
0x140006eae  mov     rsi, [rcx+8]
0x140006eb2  cmp     rbx, rsi
0x140006eb5  jz      short loc_140006EE5
0x140006eb7  mov     rcx, [rbx+20h]
0x140006ebb  test    rcx, rcx
0x140006ebe  jz      short loc_140006ED4
0x140006ec0  mov     rax, [rcx]
0x140006ec3  mov     edx, 1
0x140006ec8  mov     rax, [rax+0C0h]
0x140006ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ed4  mov     rcx, rbx
0x140006ed7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140006edc  add     rbx, 28h ; '('
0x140006ee0  cmp     rbx, rsi
0x140006ee3  jnz     short loc_140006EB7
0x140006ee5  mov     r8, [rdi]
0x140006ee8  mov     rax, 6666666666666667h
0x140006ef2  mov     rcx, [rdi+10h]
0x140006ef6  mov     rsi, [rsp+28h+arg_0]
0x140006efb  sub     rcx, r8
0x140006efe  imul    rcx
0x140006f01  sar     rdx, 4
0x140006f05  mov     rax, rdx
0x140006f08  shr     rax, 3Fh
0x140006f0c  add     rdx, rax
0x140006f0f  lea     rax, [rdx+rdx*4]
0x140006f13  lea     rdx, ds:0[rax*8]
0x140006f1b  cmp     rdx, 1000h
0x140006f22  jb      short loc_140006F42
0x140006f24  mov     rcx, [r8-8]
0x140006f28  sub     r8, rcx
0x140006f2b  sub     r8, 8
0x140006f2f  cmp     r8, 1Fh
0x140006f33  ja      short loc_140006F3B
0x140006f35  add     rdx, 27h ; '''
0x140006f39  jmp     short loc_140006F45
0x140006f3b  mov     ecx, 5
0x140006f40  int     29h; Win8: RtlFailFast(ecx)
0x140006f42  mov     rcx, r8; Block
0x140006f45  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006f4a  xor     eax, eax
0x140006f4c  mov     [rdi], rax
0x140006f4f  mov     [rdi+8], rax
0x140006f53  mov     [rdi+10h], rax
0x140006f57  mov     rbx, [rsp+28h+arg_8]
0x140006f5c  add     rsp, 20h
0x140006f60  pop     rdi
0x140006f61  retn
```
