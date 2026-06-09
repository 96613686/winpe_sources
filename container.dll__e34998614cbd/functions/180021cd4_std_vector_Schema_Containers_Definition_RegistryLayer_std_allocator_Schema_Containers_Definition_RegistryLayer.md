# std::vector<Schema::Containers::Definition::RegistryLayer,std::allocator<Schema::Containers::Definition::RegistryLayer>>::_Tidy(void)

- ea: `0x180021cd4`
- end: `0x180021d90`
- name: `?_Tidy@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ`
- size: `188`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180012e70`
- `0x180015f70`
- `0x1800173b0`
- `0x18001c314`
- `0x18001ee70`
- `0x180021c04`

## callees

- `0x180002ee4`
- `0x1800051b0`
- `0x180021cd4`

## pseudocode

```c
void __fastcall std::vector<Schema::Containers::Definition::RegistryLayer>::_Tidy(char **a1)
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
      std::wstring::~wstring(v1 + 32);
      std::wstring::~wstring(v1);
      v1 += 96;
    }
    v4 = *a1;
    if ( (unsigned __int64)(32 * ((a1[2] - *a1) >> 5)) < 0x1000 )
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
0x180021cd4  mov     [rsp+arg_0], rbx
0x180021cd9  mov     [rsp+arg_8], rsi
0x180021cde  push    rdi
0x180021cdf  sub     rsp, 20h
0x180021ce3  mov     rbx, [rcx]
0x180021ce6  mov     rdi, rcx
0x180021ce9  test    rbx, rbx
0x180021cec  jz      loc_180021D7F
0x180021cf2  mov     rsi, [rcx+8]
0x180021cf6  jmp     short loc_180021D0D
0x180021cf8  lea     rcx, [rbx+20h]
0x180021cfc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021d01  mov     rcx, rbx
0x180021d04  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021d09  add     rbx, 60h ; '`'
0x180021d0d  cmp     rbx, rsi
0x180021d10  jnz     short loc_180021CF8
0x180021d12  mov     rcx, [rdi]
0x180021d15  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180021d1f  mov     rax, [rdi+10h]
0x180021d23  sub     rax, rcx
0x180021d26  sar     rax, 5
0x180021d2a  imul    rax, rdx
0x180021d2e  lea     rdx, [rax+rax*2]
0x180021d32  shl     rdx, 5; unsigned __int64
0x180021d36  cmp     rdx, 1000h
0x180021d3d  jb      short loc_180021D5D
0x180021d3f  mov     rax, [rcx-8]
0x180021d43  sub     rcx, rax
0x180021d46  sub     rcx, 8
0x180021d4a  cmp     rcx, 1Fh
0x180021d4e  ja      short loc_180021D56
0x180021d50  add     rdx, 27h ; '''
0x180021d54  jmp     short loc_180021D60
0x180021d56  mov     ecx, 5
0x180021d5b  int     29h; Win8: RtlFailFast(ecx)
0x180021d5d  mov     rax, rcx
0x180021d60  mov     rcx, rax; void *
0x180021d63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021d68  mov     qword ptr [rdi], 0
0x180021d6f  mov     qword ptr [rdi+8], 0
0x180021d77  mov     qword ptr [rdi+10h], 0
0x180021d7f  mov     rbx, [rsp+28h+arg_0]
0x180021d84  mov     rsi, [rsp+28h+arg_8]
0x180021d89  add     rsp, 20h
0x180021d8d  pop     rdi
0x180021d8e  retn
```
