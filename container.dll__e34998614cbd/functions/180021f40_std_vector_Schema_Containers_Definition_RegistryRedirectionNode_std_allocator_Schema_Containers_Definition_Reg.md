# std::vector<Schema::Containers::Definition::RegistryRedirectionNode,std::allocator<Schema::Containers::Definition::RegistryRedirectionNode>>::_Tidy(void)

- ea: `0x180021f40`
- end: `0x180022001`
- name: `?_Tidy@?$vector@URegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ`
- size: `193`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800154c0`
- `0x180016cb0`
- `0x1800174d0`
- `0x18001f538`
- `0x1800224a0`

## callees

- `0x180002ee4`
- `0x1800051b0`
- `0x180021f40`

## pseudocode

```c
void __fastcall std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Tidy(char **a1)
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
      std::wstring::~wstring(v1 + 64);
      std::wstring::~wstring(v1 + 32);
      std::wstring::~wstring(v1);
      v1 += 104;
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
0x180021f40  mov     [rsp+arg_0], rbx
0x180021f45  mov     [rsp+arg_8], rsi
0x180021f4a  push    rdi
0x180021f4b  sub     rsp, 20h
0x180021f4f  mov     rbx, [rcx]
0x180021f52  mov     rdi, rcx
0x180021f55  test    rbx, rbx
0x180021f58  jz      loc_180021FF0
0x180021f5e  mov     rsi, [rcx+8]
0x180021f62  jmp     short loc_180021F82
0x180021f64  lea     rcx, [rbx+40h]
0x180021f68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021f6d  lea     rcx, [rbx+20h]
0x180021f71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021f76  mov     rcx, rbx
0x180021f79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021f7e  add     rbx, 68h ; 'h'
0x180021f82  cmp     rbx, rsi
0x180021f85  jnz     short loc_180021F64
0x180021f87  mov     rcx, [rdi]
0x180021f8a  mov     rdx, 4EC4EC4EC4EC4EC5h
0x180021f94  mov     rax, [rdi+10h]
0x180021f98  sub     rax, rcx
0x180021f9b  sar     rax, 3
0x180021f9f  imul    rax, rdx
0x180021fa3  imul    rdx, rax, 68h ; 'h'; unsigned __int64
0x180021fa7  cmp     rdx, 1000h
0x180021fae  jb      short loc_180021FCE
0x180021fb0  mov     rax, [rcx-8]
0x180021fb4  sub     rcx, rax
0x180021fb7  sub     rcx, 8
0x180021fbb  cmp     rcx, 1Fh
0x180021fbf  ja      short loc_180021FC7
0x180021fc1  add     rdx, 27h ; '''
0x180021fc5  jmp     short loc_180021FD1
0x180021fc7  mov     ecx, 5
0x180021fcc  int     29h; Win8: RtlFailFast(ecx)
0x180021fce  mov     rax, rcx
0x180021fd1  mov     rcx, rax; void *
0x180021fd4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021fd9  mov     qword ptr [rdi], 0
0x180021fe0  mov     qword ptr [rdi+8], 0
0x180021fe8  mov     qword ptr [rdi+10h], 0
0x180021ff0  mov     rbx, [rsp+28h+arg_0]
0x180021ff5  mov     rsi, [rsp+28h+arg_8]
0x180021ffa  add     rsp, 20h
0x180021ffe  pop     rdi
0x180021fff  retn
```
