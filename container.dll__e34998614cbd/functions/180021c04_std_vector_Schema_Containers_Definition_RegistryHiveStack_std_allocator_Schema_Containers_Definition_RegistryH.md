# std::vector<Schema::Containers::Definition::RegistryHiveStack,std::allocator<Schema::Containers::Definition::RegistryHiveStack>>::_Tidy(void)

- ea: `0x180021c04`
- end: `0x180021cce`
- name: `?_Tidy@?$vector@URegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ`
- size: `202`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x1800154c0`
- `0x180016cb0`
- `0x180017350`
- `0x18001f538`
- `0x1800224a0`

## callees

- `0x180002ee4`
- `0x1800051b0`
- `0x180021b68`
- `0x180021c04`
- `0x180021cd4`
- `0x180021d98`

## pseudocode

```c
void __fastcall std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Tidy(char ***a1)
{
  char **v1; // rbx
  char **v3; // rsi
  char **v4; // rcx
  char **v5; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::vector<std::wstring>::_Tidy(v1 + 10);
      std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(v1 + 7);
      std::vector<Schema::Containers::Definition::RegistryLayer>::_Tidy(v1 + 4);
      std::wstring::~wstring(v1);
      v1 += 13;
    }
    v4 = *a1;
    if ( (unsigned __int64)(8 * (a1[2] - *a1)) < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char **)*(v4 - 1);
      if ( (unsigned __int64)((char *)v4 - (char *)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180021c04  mov     [rsp+arg_0], rbx
0x180021c09  mov     [rsp+arg_8], rsi
0x180021c0e  push    rdi
0x180021c0f  sub     rsp, 20h
0x180021c13  mov     rbx, [rcx]
0x180021c16  mov     rdi, rcx
0x180021c19  test    rbx, rbx
0x180021c1c  jz      loc_180021CBD
0x180021c22  mov     rsi, [rcx+8]
0x180021c26  jmp     short loc_180021C4F
0x180021c28  lea     rcx, [rbx+50h]
0x180021c2c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180021c31  lea     rcx, [rbx+38h]
0x180021c35  call    ?_Tidy@?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(void)
0x180021c3a  lea     rcx, [rbx+20h]
0x180021c3e  call    ?_Tidy@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryLayer>::_Tidy(void)
0x180021c43  mov     rcx, rbx
0x180021c46  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021c4b  add     rbx, 68h ; 'h'
0x180021c4f  cmp     rbx, rsi
0x180021c52  jnz     short loc_180021C28
0x180021c54  mov     rcx, [rdi]
0x180021c57  mov     rdx, 4EC4EC4EC4EC4EC5h
0x180021c61  mov     rax, [rdi+10h]
0x180021c65  sub     rax, rcx
0x180021c68  sar     rax, 3
0x180021c6c  imul    rax, rdx
0x180021c70  imul    rdx, rax, 68h ; 'h'; unsigned __int64
0x180021c74  cmp     rdx, 1000h
0x180021c7b  jb      short loc_180021C9B
0x180021c7d  mov     rax, [rcx-8]
0x180021c81  sub     rcx, rax
0x180021c84  sub     rcx, 8
0x180021c88  cmp     rcx, 1Fh
0x180021c8c  ja      short loc_180021C94
0x180021c8e  add     rdx, 27h ; '''
0x180021c92  jmp     short loc_180021C9E
0x180021c94  mov     ecx, 5
0x180021c99  int     29h; Win8: RtlFailFast(ecx)
0x180021c9b  mov     rax, rcx
0x180021c9e  mov     rcx, rax; void *
0x180021ca1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021ca6  mov     qword ptr [rdi], 0
0x180021cad  mov     qword ptr [rdi+8], 0
0x180021cb5  mov     qword ptr [rdi+10h], 0
0x180021cbd  mov     rbx, [rsp+28h+arg_0]
0x180021cc2  mov     rsi, [rsp+28h+arg_8]
0x180021cc7  add     rsp, 20h
0x180021ccb  pop     rdi
0x180021ccc  retn
```
