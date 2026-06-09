# std::vector<Schema::Containers::Definition::RegistryHiveStack,std::allocator<Schema::Containers::Definition::RegistryHiveStack>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18001ee70`
- end: `0x18001ef08`
- name: `??1_Reallocation_guard@?$vector@URegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@QEAA@XZ`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18001c314`

## callees

- `0x180002ee4`
- `0x1800051b0`
- `0x18001ee70`
- `0x180021b68`
- `0x180021cd4`
- `0x180021d98`

## pseudocode

```c
void __fastcall std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rsi
  __int64 i; // rdi
  __int64 v4; // rax
  void *v5; // rcx

  if ( a1[1] )
  {
    v2 = a1[4];
    for ( i = a1[3]; i != v2; i += 104 )
    {
      std::vector<std::wstring>::_Tidy(i + 80);
      std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy((char **)(i + 56));
      std::vector<Schema::Containers::Definition::RegistryLayer>::_Tidy((char **)(i + 32));
      std::wstring::~wstring(i);
    }
    v4 = a1[1];
    if ( (unsigned __int64)(104LL * a1[2]) < 0x1000 )
    {
      v5 = (void *)a1[1];
    }
    else
    {
      v5 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
  }
}

```

## disassembly

```asm
0x18001ee70  mov     [rsp+arg_0], rbx
0x18001ee75  mov     [rsp+arg_8], rsi
0x18001ee7a  push    rdi
0x18001ee7b  sub     rsp, 20h
0x18001ee7f  cmp     qword ptr [rcx+8], 0
0x18001ee84  mov     rbx, rcx
0x18001ee87  jz      short loc_18001EEF7
0x18001ee89  mov     rsi, [rcx+20h]
0x18001ee8d  mov     rdi, [rcx+18h]
0x18001ee91  jmp     short loc_18001EEBA
0x18001ee93  lea     rcx, [rdi+50h]
0x18001ee97  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001ee9c  lea     rcx, [rdi+38h]
0x18001eea0  call    ?_Tidy@?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(void)
0x18001eea5  lea     rcx, [rdi+20h]
0x18001eea9  call    ?_Tidy@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryLayer>::_Tidy(void)
0x18001eeae  mov     rcx, rdi
0x18001eeb1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eeb6  add     rdi, 68h ; 'h'
0x18001eeba  cmp     rdi, rsi
0x18001eebd  jnz     short loc_18001EE93
0x18001eebf  imul    rdx, [rbx+10h], 68h ; 'h'; unsigned __int64
0x18001eec4  mov     rax, [rbx+8]
0x18001eec8  cmp     rdx, 1000h
0x18001eecf  jb      short loc_18001EEEF
0x18001eed1  mov     rcx, [rax-8]
0x18001eed5  sub     rax, rcx
0x18001eed8  sub     rax, 8
0x18001eedc  cmp     rax, 1Fh
0x18001eee0  ja      short loc_18001EEE8
0x18001eee2  add     rdx, 27h ; '''
0x18001eee6  jmp     short loc_18001EEF2
0x18001eee8  mov     ecx, 5
0x18001eeed  int     29h; Win8: RtlFailFast(ecx)
0x18001eeef  mov     rcx, rax; void *
0x18001eef2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eef7  mov     rbx, [rsp+28h+arg_0]
0x18001eefc  mov     rsi, [rsp+28h+arg_8]
0x18001ef01  add     rsp, 20h
0x18001ef05  pop     rdi
0x18001ef06  retn
```
