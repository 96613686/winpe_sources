# std::vector<Schema::Containers::Definition::ObjectDirectory,std::allocator<Schema::Containers::Definition::ObjectDirectory>>::_Tidy(void)

- ea: `0x1800219d0`
- end: `0x180021a9a`
- name: `?_Tidy@?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ`
- size: `202`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x180012d50`
- `0x1800153e0`
- `0x180015d20`
- `0x180016c00`
- `0x180017230`
- `0x18001bbc8`
- `0x18001ecb0`
- `0x18001f48c`
- `0x1800219d0`
- `0x1800224a0`

## callees

- `0x180002ee4`
- `0x1800051b0`
- `0x1800219d0`
- `0x180021aa0`

## pseudocode

```c
void __fastcall std::vector<Schema::Containers::Definition::ObjectDirectory>::_Tidy(char **a1)
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
      std::vector<Schema::Containers::Definition::ObjectDirectory>::_Tidy(v1 + 96);
      std::vector<Schema::Containers::Definition::ObjectSymlink>::_Tidy(v1 + 72);
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
0x1800219d0  mov     [rsp+arg_0], rbx
0x1800219d5  mov     [rsp+arg_8], rsi
0x1800219da  push    rdi
0x1800219db  sub     rsp, 20h
0x1800219df  mov     rbx, [rcx]
0x1800219e2  mov     rdi, rcx
0x1800219e5  test    rbx, rbx
0x1800219e8  jz      loc_180021A89
0x1800219ee  mov     rsi, [rcx+8]
0x1800219f2  jmp     short loc_180021A1B
0x1800219f4  lea     rcx, [rbx+60h]
0x1800219f8  call    ?_Tidy@?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::ObjectDirectory>::_Tidy(void)
0x1800219fd  lea     rcx, [rbx+48h]
0x180021a01  call    ?_Tidy@?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::ObjectSymlink>::_Tidy(void)
0x180021a06  lea     rcx, [rbx+20h]
0x180021a0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021a0f  mov     rcx, rbx
0x180021a12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021a17  add     rbx, 78h ; 'x'
0x180021a1b  cmp     rbx, rsi
0x180021a1e  jnz     short loc_1800219F4
0x180021a20  mov     rcx, [rdi]
0x180021a23  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x180021a2d  mov     rax, [rdi+10h]
0x180021a31  sub     rax, rcx
0x180021a34  sar     rax, 3
0x180021a38  imul    rax, rdx
0x180021a3c  imul    rdx, rax, 78h ; 'x'; unsigned __int64
0x180021a40  cmp     rdx, 1000h
0x180021a47  jb      short loc_180021A67
0x180021a49  mov     rax, [rcx-8]
0x180021a4d  sub     rcx, rax
0x180021a50  sub     rcx, 8
0x180021a54  cmp     rcx, 1Fh
0x180021a58  ja      short loc_180021A60
0x180021a5a  add     rdx, 27h ; '''
0x180021a5e  jmp     short loc_180021A6A
0x180021a60  mov     ecx, 5
0x180021a65  int     29h; Win8: RtlFailFast(ecx)
0x180021a67  mov     rax, rcx
0x180021a6a  mov     rcx, rax; void *
0x180021a6d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021a72  mov     qword ptr [rdi], 0
0x180021a79  mov     qword ptr [rdi+8], 0
0x180021a81  mov     qword ptr [rdi+10h], 0
0x180021a89  mov     rbx, [rsp+28h+arg_0]
0x180021a8e  mov     rsi, [rsp+28h+arg_8]
0x180021a93  add     rsp, 20h
0x180021a97  pop     rdi
0x180021a98  retn
```
