# std::vector<Schema::Containers::Definition::RegistryMakeKey,std::allocator<Schema::Containers::Definition::RegistryMakeKey>>::_Tidy(void)

- ea: `0x180021d98`
- end: `0x180021e62`
- name: `?_Tidy@?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ`
- size: `202`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180012e70`
- `0x180012f40`
- `0x180015f70`
- `0x180016110`
- `0x180017410`
- `0x18001c314`
- `0x18001c7e4`
- `0x18001ee70`
- `0x18001efa8`
- `0x180021c04`
- `0x180021d98`

## callees

- `0x180002ee4`
- `0x1800051b0`
- `0x180021d98`
- `0x180021e68`

## pseudocode

```c
void __fastcall std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(char **a1)
{
  char *v1; // rbx
  char *v3; // rsi
  char *v4; // rcx
  char *v5; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::vector<Schema::Containers::Definition::RegistryMakeValue>::_Tidy(v1 + 88);
      std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(v1 + 64);
      std::wstring::~wstring(v1 + 32);
      std::wstring::~wstring(v1);
      v1 += 120;
    }
    v4 = *a1;
    if ( (unsigned __int64)(8 * ((a1[2] - *a1) >> 3)) < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v5 - 8) > 0x1F )
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
0x180021d98  mov     [rsp+arg_0], rbx
0x180021d9d  mov     [rsp+arg_8], rsi
0x180021da2  push    rdi
0x180021da3  sub     rsp, 20h
0x180021da7  mov     rbx, [rcx]
0x180021daa  mov     rdi, rcx
0x180021dad  test    rbx, rbx
0x180021db0  jz      loc_180021E51
0x180021db6  mov     rsi, [rcx+8]
0x180021dba  jmp     short loc_180021DE3
0x180021dbc  lea     rcx, [rbx+58h]
0x180021dc0  call    ?_Tidy@?$vector@URegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryMakeValue>::_Tidy(void)
0x180021dc5  lea     rcx, [rbx+40h]
0x180021dc9  call    ?_Tidy@?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(void)
0x180021dce  lea     rcx, [rbx+20h]
0x180021dd2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021dd7  mov     rcx, rbx
0x180021dda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021ddf  add     rbx, 78h ; 'x'
0x180021de3  cmp     rbx, rsi
0x180021de6  jnz     short loc_180021DBC
0x180021de8  mov     rcx, [rdi]
0x180021deb  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x180021df5  mov     rax, [rdi+10h]
0x180021df9  sub     rax, rcx
0x180021dfc  sar     rax, 3
0x180021e00  imul    rax, rdx
0x180021e04  imul    rdx, rax, 78h ; 'x'; unsigned __int64
0x180021e08  cmp     rdx, 1000h
0x180021e0f  jb      short loc_180021E2F
0x180021e11  mov     rax, [rcx-8]
0x180021e15  sub     rcx, rax
0x180021e18  sub     rcx, 8
0x180021e1c  cmp     rcx, 1Fh
0x180021e20  ja      short loc_180021E28
0x180021e22  add     rdx, 27h ; '''
0x180021e26  jmp     short loc_180021E32
0x180021e28  mov     ecx, 5
0x180021e2d  int     29h; Win8: RtlFailFast(ecx)
0x180021e2f  mov     rax, rcx
0x180021e32  mov     rcx, rax; void *
0x180021e35  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021e3a  mov     qword ptr [rdi], 0
0x180021e41  mov     qword ptr [rdi+8], 0
0x180021e49  mov     qword ptr [rdi+10h], 0
0x180021e51  mov     rbx, [rsp+28h+arg_0]
0x180021e56  mov     rsi, [rsp+28h+arg_8]
0x180021e5b  add     rsp, 20h
0x180021e5f  pop     rdi
0x180021e60  retn
```
