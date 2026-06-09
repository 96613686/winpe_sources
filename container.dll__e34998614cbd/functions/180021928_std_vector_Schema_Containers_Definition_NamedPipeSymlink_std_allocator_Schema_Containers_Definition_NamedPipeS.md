# std::vector<Schema::Containers::Definition::NamedPipeSymlink,std::allocator<Schema::Containers::Definition::NamedPipeSymlink>>::_Tidy(void)

- ea: `0x180021928`
- end: `0x1800219c7`
- name: `?_Tidy@?$vector@UNamedPipeSymlink@Definition@Containers@Schema@@V?$allocator@UNamedPipeSymlink@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ`
- size: `159`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x180015110`
- `0x180015200`
- `0x1800154c0`
- `0x180016b70`
- `0x180016cb0`
- `0x1800171d0`
- `0x18001f538`
- `0x1800224a0`
- `0x180023900`
- `0x180032d44`
- `0x180032df2`

## callees

- `0x180002ee4`
- `0x1800051b0`
- `0x180021928`

## pseudocode

```c
void __fastcall std::vector<Schema::Containers::Definition::NamedPipeSymlink>::_Tidy(char **a1)
{
  char *v1; // rbx
  char *v3; // rsi
  char *v4; // rax
  char *v5; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::wstring::~wstring(v1 + 32);
      std::wstring::~wstring(v1);
      v1 += 64;
    }
    v4 = *a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFC0uLL) < 0x1000 )
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
0x180021928  mov     [rsp+arg_0], rbx
0x18002192d  mov     [rsp+arg_8], rsi
0x180021932  push    rdi
0x180021933  sub     rsp, 20h
0x180021937  mov     rbx, [rcx]
0x18002193a  mov     rdi, rcx
0x18002193d  test    rbx, rbx
0x180021940  jz      short loc_1800219B6
0x180021942  mov     rsi, [rcx+8]
0x180021946  jmp     short loc_18002195D
0x180021948  lea     rcx, [rbx+20h]
0x18002194c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021951  mov     rcx, rbx
0x180021954  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021959  add     rbx, 40h ; '@'
0x18002195d  cmp     rbx, rsi
0x180021960  jnz     short loc_180021948
0x180021962  mov     rax, [rdi]
0x180021965  mov     rdx, [rdi+10h]
0x180021969  sub     rdx, rax
0x18002196c  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x180021970  cmp     rdx, 1000h
0x180021977  jb      short loc_180021997
0x180021979  mov     rcx, [rax-8]
0x18002197d  sub     rax, rcx
0x180021980  sub     rax, 8
0x180021984  cmp     rax, 1Fh
0x180021988  ja      short loc_180021990
0x18002198a  add     rdx, 27h ; '''
0x18002198e  jmp     short loc_18002199A
0x180021990  mov     ecx, 5
0x180021995  int     29h; Win8: RtlFailFast(ecx)
0x180021997  mov     rcx, rax; void *
0x18002199a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002199f  mov     qword ptr [rdi], 0
0x1800219a6  mov     qword ptr [rdi+8], 0
0x1800219ae  mov     qword ptr [rdi+10h], 0
0x1800219b6  mov     rbx, [rsp+28h+arg_0]
0x1800219bb  mov     rsi, [rsp+28h+arg_8]
0x1800219c0  add     rsp, 20h
0x1800219c4  pop     rdi
0x1800219c5  retn
```
