# std::_Uninitialized_copy<Schema::Containers::Definition::RegistryMakeValue *,Schema::Containers::Definition::RegistryMakeValue *,std::allocator<Schema::Containers::Definition::RegistryMakeValue>>(Schema::Containers::Definition::RegistryMakeValue *,Schema::Containers::Definition::RegistryMakeValue *,Schema::Containers::Definition::RegistryMakeValue *,std::allocator<Schema::Containers::Definition::RegistryMakeValue> &)

- ea: `0x18001d9d0`
- end: `0x18001db65`
- name: `??$_Uninitialized_copy@PEAURegistryMakeValue@Definition@Containers@Schema@@PEAU1234@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryMakeValue@Definition@Containers@Schema@@PEAU1234@00AEAV?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@0@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config`

## callers

- `0x18001ca60`

## callees

- `0x180002af4`
- `0x180003620`
- `0x180004c40`
- `0x18000be08`
- `0x1800120b0`
- `0x18001d9d0`
- `0x18001e53c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Uninitialized_copy<Schema::Containers::Definition::RegistryMakeValue *,Schema::Containers::Definition::RegistryMakeValue *,std::allocator<Schema::Containers::Definition::RegistryMakeValue>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 i; // rbp
  size_t v6; // rbx
  void *v7; // rax
  void *v8; // rcx
  _QWORD *v9; // rax
  char *v10; // rdi
  const void *v11; // rdx
  size_t v12; // rbx
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  for ( i = a1; i != a2; i += 152 )
  {
    v14 = a3;
    std::wstring::wstring(a3, i);
    std::wstring::wstring(a3 + 32, i + 32);
    *(_BYTE *)(a3 + 64) = *(_BYTE *)(i + 64);
    *(_DWORD *)(a3 + 72) = *(_DWORD *)(i + 72);
    *(_BYTE *)(a3 + 76) = *(_BYTE *)(i + 76);
    std::wstring::wstring(a3 + 80, i + 80);
    *(_BYTE *)(a3 + 112) = *(_BYTE *)(i + 112);
    *(_QWORD *)(a3 + 120) = 0;
    *(_QWORD *)(a3 + 128) = 0;
    *(_QWORD *)(a3 + 136) = 0;
    v6 = *(_QWORD *)(i + 128) - *(_QWORD *)(i + 120);
    if ( v6 )
    {
      if ( v6 > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength();
      if ( v6 < 0x1000 )
      {
        v9 = operator new(v6);
      }
      else
      {
        if ( v6 + 39 < v6 )
          __scrt_throw_std_bad_array_new_length();
        v7 = operator new(v6 + 39);
        v8 = v7;
        if ( !v7 )
          __fastfail(5u);
        v9 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v8;
      }
      *(_QWORD *)(a3 + 120) = v9;
      *(_QWORD *)(a3 + 128) = v9;
      *(_QWORD *)(a3 + 136) = (char *)v9 + v6;
      v10 = *(char **)(a3 + 120);
      v11 = *(const void **)(i + 120);
      v12 = *(_QWORD *)(i + 128) - (_QWORD)v11;
      memmove_0(v10, v11, v12);
      *(_QWORD *)(a3 + 128) = &v10[v12];
      v14 = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v14);
    }
    *(_BYTE *)(a3 + 144) = *(_BYTE *)(i + 144);
    a3 += 152;
  }
  return a3;
}

```

## disassembly

```asm
0x18001d9d0  mov     rax, rsp
0x18001d9d3  mov     [rax+10h], rbx
0x18001d9d7  mov     [rax+18h], rbp
0x18001d9db  push    rsi
0x18001d9dc  push    rdi
0x18001d9dd  push    r14
0x18001d9df  sub     rsp, 40h
0x18001d9e3  mov     rsi, r8
0x18001d9e6  mov     r14, rdx
0x18001d9e9  mov     rbp, rcx
0x18001d9ec  mov     [rax-38h], r8
0x18001d9f0  mov     [rax-30h], r8
0x18001d9f4  mov     [rax-28h], r9
0x18001d9f8  cmp     rcx, rdx
0x18001d9fb  jz      loc_18001DB3B
0x18001da01  mov     [rsp+58h+arg_0], rsi
0x18001da06  mov     rdx, rbp
0x18001da09  mov     rcx, rsi
0x18001da0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001da11  nop
0x18001da12  lea     rdx, [rbp+20h]
0x18001da16  lea     rcx, [rsi+20h]
0x18001da1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001da1f  mov     al, [rbp+40h]
0x18001da22  mov     [rsi+40h], al
0x18001da25  mov     eax, [rbp+48h]
0x18001da28  mov     [rsi+48h], eax
0x18001da2b  mov     al, [rbp+4Ch]
0x18001da2e  mov     [rsi+4Ch], al
0x18001da31  lea     rdx, [rbp+50h]
0x18001da35  lea     rcx, [rsi+50h]
0x18001da39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001da3e  mov     al, [rbp+70h]
0x18001da41  mov     [rsi+70h], al
0x18001da44  mov     qword ptr [rsi+78h], 0
0x18001da4c  mov     qword ptr [rsi+80h], 0
0x18001da57  mov     qword ptr [rsi+88h], 0
0x18001da62  mov     rbx, [rbp+80h]
0x18001da69  sub     rbx, [rbp+78h]
0x18001da6d  jz      loc_18001DB13
0x18001da73  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001da7d  cmp     rbx, rax
0x18001da80  ja      loc_18001DB5F
0x18001da86  cmp     rbx, 1000h
0x18001da8d  jb      short loc_18001DABB
0x18001da8f  lea     rcx, [rbx+27h]; Size
0x18001da93  cmp     rcx, rbx
0x18001da96  jbe     loc_18001DB59
0x18001da9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001daa1  mov     rcx, rax
0x18001daa4  test    rax, rax
0x18001daa7  jz      loc_18001DB52
0x18001daad  add     rax, 27h ; '''
0x18001dab1  and     rax, 0FFFFFFFFFFFFFFE0h
0x18001dab5  mov     [rax-8], rcx
0x18001dab9  jmp     short loc_18001DAC3
0x18001dabb  mov     rcx, rbx; Size
0x18001dabe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dac3  mov     [rsi+78h], rax
0x18001dac7  mov     [rsi+80h], rax
0x18001dace  add     rax, rbx
0x18001dad1  mov     [rsi+88h], rax
0x18001dad8  mov     rdi, [rsi+78h]
0x18001dadc  mov     rdx, [rbp+78h]; Src
0x18001dae0  mov     rbx, [rbp+80h]
0x18001dae7  sub     rbx, rdx
0x18001daea  mov     r8, rbx; Size
0x18001daed  mov     rcx, rdi; void *
0x18001daf0  call    memmove_0
0x18001daf5  lea     rax, [rbx+rdi]
0x18001daf9  mov     [rsi+80h], rax
0x18001db00  mov     [rsp+58h+arg_0], 0
0x18001db09  lea     rcx, [rsp+58h+arg_0]
0x18001db0e  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18001db13  mov     al, [rbp+90h]
0x18001db19  mov     [rsi+90h], al
0x18001db1f  add     rsi, 98h
0x18001db26  mov     [rsp+58h+var_30], rsi
0x18001db2b  add     rbp, 98h
0x18001db32  cmp     rbp, r14
0x18001db35  jnz     loc_18001DA01
0x18001db3b  mov     rax, rsi
0x18001db3e  mov     rbx, [rsp+58h+arg_8]
0x18001db43  mov     rbp, [rsp+58h+arg_10]
0x18001db48  add     rsp, 40h
0x18001db4c  pop     r14
0x18001db4e  pop     rdi
0x18001db4f  pop     rsi
0x18001db50  retn
0x18001db52  mov     ecx, 5
0x18001db57  int     29h; Win8: RtlFailFast(ecx)
0x18001db59  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18001db5f  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
```
