# std::vector<Schema::Containers::Definition::ObjectSymlink,std::allocator<Schema::Containers::Definition::ObjectSymlink>>::_Tidy(void)

- ea: `0x180021aa0`
- end: `0x180021b61`
- name: `?_Tidy@?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ`
- size: `193`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x180012d50`
- `0x1800153e0`
- `0x180015d20`
- `0x180016c00`
- `0x180017290`
- `0x18001bbc8`
- `0x18001ecb0`
- `0x18001f48c`
- `0x1800219d0`
- `0x1800224a0`

## callees

- `0x180002ee4`
- `0x1800051b0`
- `0x180021aa0`

## pseudocode

```c
void __fastcall std::vector<Schema::Containers::Definition::ObjectSymlink>::_Tidy(char **a1)
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
      std::wstring::~wstring(v1 + 72);
      std::wstring::~wstring(v1 + 32);
      std::wstring::~wstring(v1);
      v1 += 112;
    }
    v4 = *a1;
    if ( (unsigned __int64)(16 * ((a1[2] - *a1) >> 4)) < 0x1000 )
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
0x180021aa0  mov     [rsp+arg_0], rbx
0x180021aa5  mov     [rsp+arg_8], rsi
0x180021aaa  push    rdi
0x180021aab  sub     rsp, 20h
0x180021aaf  mov     rbx, [rcx]
0x180021ab2  mov     rdi, rcx
0x180021ab5  test    rbx, rbx
0x180021ab8  jz      loc_180021B50
0x180021abe  mov     rsi, [rcx+8]
0x180021ac2  jmp     short loc_180021AE2
0x180021ac4  lea     rcx, [rbx+48h]
0x180021ac8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021acd  lea     rcx, [rbx+20h]
0x180021ad1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021ad6  mov     rcx, rbx
0x180021ad9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021ade  add     rbx, 70h ; 'p'
0x180021ae2  cmp     rbx, rsi
0x180021ae5  jnz     short loc_180021AC4
0x180021ae7  mov     rcx, [rdi]
0x180021aea  mov     rdx, 6DB6DB6DB6DB6DB7h
0x180021af4  mov     rax, [rdi+10h]
0x180021af8  sub     rax, rcx
0x180021afb  sar     rax, 4
0x180021aff  imul    rax, rdx
0x180021b03  imul    rdx, rax, 70h ; 'p'; unsigned __int64
0x180021b07  cmp     rdx, 1000h
0x180021b0e  jb      short loc_180021B2E
0x180021b10  mov     rax, [rcx-8]
0x180021b14  sub     rcx, rax
0x180021b17  sub     rcx, 8
0x180021b1b  cmp     rcx, 1Fh
0x180021b1f  ja      short loc_180021B27
0x180021b21  add     rdx, 27h ; '''
0x180021b25  jmp     short loc_180021B31
0x180021b27  mov     ecx, 5
0x180021b2c  int     29h; Win8: RtlFailFast(ecx)
0x180021b2e  mov     rax, rcx
0x180021b31  mov     rcx, rax; void *
0x180021b34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021b39  mov     qword ptr [rdi], 0
0x180021b40  mov     qword ptr [rdi+8], 0
0x180021b48  mov     qword ptr [rdi+10h], 0
0x180021b50  mov     rbx, [rsp+28h+arg_0]
0x180021b55  mov     rsi, [rsp+28h+arg_8]
0x180021b5a  add     rsp, 20h
0x180021b5e  pop     rdi
0x180021b5f  retn
```
