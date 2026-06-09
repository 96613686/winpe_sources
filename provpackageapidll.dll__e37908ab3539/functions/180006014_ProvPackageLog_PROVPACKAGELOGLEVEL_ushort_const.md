# ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)

- ea: `0x180006014`
- end: `0x1800060db`
- name: `?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ`
- size: `199`
- prototype: `void(unsigned int, const wchar_t *, ...)`
- caller_count: `80`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180005b70`
- `0x180005c30`
- `0x180005cc0`
- `0x180005e10`
- `0x180006790`
- `0x1800068b8`
- `0x180006dd0`
- `0x180006f10`
- `0x180007040`
- `0x180007190`
- `0x180007370`
- `0x18000741c`
- `0x180007710`
- `0x1800077b0`
- `0x180007850`
- `0x1800078e8`
- `0x180007c30`
- `0x180007cd0`
- `0x180007d50`
- `0x180007ee0`
- `0x180007f78`
- `0x1800088dc`
- `0x180008b9c`
- `0x180008d24`
- `0x18000907c`
- `0x180009740`
- `0x180009b30`
- `0x180009c30`
- `0x180009d40`
- `0x180009e40`
- `0x180009f40`
- `0x18000a040`
- `0x18000a1e0`
- `0x18000a2e0`
- `0x18000a3c0`
- `0x18000a5b0`
- `0x18000b7b0`
- `0x18000ce20`
- `0x18000ce90`
- `0x18000d010`
- `0x18000d0c4`
- `0x18000d350`
- `0x18000d708`
- `0x18000da5c`
- `0x18000e060`
- `0x18000e1cc`
- `0x18000e328`
- `0x18000e4b0`
- `0x18000e7b0`
- `0x18000e948`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x1800021ec`
- `0x1800022a0`
- `0x180006014`
- `0x180019010`

## pseudocode

```c
void ProvPackageLog(unsigned int a1, const wchar_t *a2, ...)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rax
  wchar_t *v5; // rax
  wchar_t *v6; // rbx
  const struct std::nothrow_t *v7; // rdx
  __int64 v8; // [rsp+0h] [rbp-68h] BYREF
  wchar_t *v9; // [rsp+30h] [rbp-38h]
  wchar_t *v10; // [rsp+38h] [rbp-30h]
  va_list va; // [rsp+80h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( qword_1800263C8 )
  {
    v9 = 0;
    v3 = vscwprintf(a2, va) + 1;
    v4 = 2 * v3;
    if ( !is_mul_ok(v3, 2u) )
      v4 = -1;
    v5 = (wchar_t *)operator new[](v4, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    v9 = v5;
    v10 = v5;
    if ( v5 )
    {
      vsnwprintf_s(v5, v3, v3, a2, va);
      try
      {
        (**(void (__fastcall ***)(__int64, _QWORD, void *))qword_1800263C8)(qword_1800263C8, a1, v6);
      }
      catch ( ... )
      {
        v7 = (const struct std::nothrow_t *)&v8;
        v6 = v9;
      }
      operator delete(v6, v7);
    }
  }
}

```

## disassembly

```asm
0x180006014  mov     r11, rsp
0x180006017  mov     [r11+10h], rdx
0x18000601b  mov     [r11+18h], r8
0x18000601f  mov     [r11+20h], r9
0x180006023  push    rbx
0x180006024  push    rsi
0x180006025  push    rdi
0x180006026  push    r14
0x180006028  sub     rsp, 48h
0x18000602c  mov     rax, rdx
0x18000602f  mov     esi, ecx
0x180006031  cmp     cs:qword_1800263C8, 0
0x180006039  jz      loc_1800060D1
0x18000603f  mov     qword ptr [r11-38h], 0
0x180006047  lea     r14, [r11+18h]
0x18000604b  mov     rdx, r14; ArgList
0x18000604e  mov     rcx, rax; Format
0x180006051  call    _vscwprintf
0x180006056  inc     eax
0x180006058  movsxd  rdi, eax
0x18000605b  mov     eax, 2
0x180006060  mul     rdi
0x180006063  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000606a  cmovb   rax, rcx
0x18000606e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006075  mov     rcx, rax; unsigned __int64
0x180006078  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000607d  mov     rbx, rax
0x180006080  mov     [rsp+68h+var_38], rax
0x180006085  mov     [rsp+68h+var_30], rax
0x18000608a  test    rax, rax
0x18000608d  jnz     short loc_180006091
0x18000608f  jmp     short loc_1800060D1
0x180006091  mov     [rsp+68h+ArgList], r14; ArgList
0x180006096  mov     r9, [rsp+68h+Format]; Format
0x18000609b  mov     r8, rdi; MaxCount
0x18000609e  mov     rdx, rdi; BufferCount
0x1800060a1  mov     rcx, rbx; Buffer
0x1800060a4  call    _vsnwprintf_s
0x1800060a9  nop
0x1800060aa  mov     rcx, cs:qword_1800263C8
0x1800060b1  mov     rax, [rcx]
0x1800060b4  mov     r8, rbx
0x1800060b7  mov     edx, esi
0x1800060b9  mov     rax, [rax]
0x1800060bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c1  nop
0x1800060c2  jmp     short loc_1800060C9
0x1800060c4  mov     rbx, [rsp+68h+var_38]
0x1800060c9  mov     rcx, rbx; void *
0x1800060cc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800060d1  add     rsp, 48h
0x1800060d5  pop     r14
0x1800060d7  pop     rdi
0x1800060d8  pop     rsi
0x1800060d9  pop     rbx
0x1800060da  retn
```
