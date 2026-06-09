# std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>(void)

- ea: `0x1800062ec`
- end: `0x180006381`
- name: `??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(__int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800065c0`
- `0x180007828`
- `0x180007c80`
- `0x180007f80`
- `0x18000ad36`
- `0x18000ad4c`
- `0x18000ad74`
- `0x18000aff5`

## callees

- `0x1800018f0`
- `0x180006260`
- `0x1800062ec`

## pseudocode

```c
void __fastcall std::vector<std::wstring>::~vector<std::wstring>(__int64 a1)
{
  char **v1; // rbx
  char **v3; // rsi
  char **v4; // rax
  unsigned __int64 v5; // rdx
  char **v6; // rcx

  v1 = *(char ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(char ***)(a1 + 8);
    while ( v1 != v3 )
    {
      std::wstring::~wstring(v1);
      v1 += 4;
    }
    v4 = *(char ***)a1;
    v5 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v5 < 0x1000 )
    {
      v6 = *(char ***)a1;
    }
    else
    {
      v6 = (char **)*(v4 - 1);
      if ( (unsigned __int64)((char *)v4 - (char *)v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800062ec  mov     [rsp+arg_0], rbx
0x1800062f1  mov     [rsp+arg_8], rsi
0x1800062f6  push    rdi
0x1800062f7  sub     rsp, 20h
0x1800062fb  mov     rbx, [rcx]
0x1800062fe  mov     rdi, rcx
0x180006301  test    rbx, rbx
0x180006304  jz      short loc_180006371
0x180006306  mov     rsi, [rcx+8]
0x18000630a  jmp     short loc_180006318
0x18000630c  mov     rcx, rbx
0x18000630f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006314  add     rbx, 20h ; ' '
0x180006318  cmp     rbx, rsi
0x18000631b  jnz     short loc_18000630C
0x18000631d  mov     rax, [rdi]
0x180006320  mov     rdx, [rdi+10h]
0x180006324  sub     rdx, rax
0x180006327  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x18000632b  cmp     rdx, 1000h
0x180006332  jb      short loc_180006352
0x180006334  mov     rcx, [rax-8]
0x180006338  sub     rax, rcx
0x18000633b  sub     rax, 8
0x18000633f  cmp     rax, 1Fh
0x180006343  ja      short loc_18000634B
0x180006345  add     rdx, 27h ; '''
0x180006349  jmp     short loc_180006355
0x18000634b  mov     ecx, 5
0x180006350  int     29h; Win8: RtlFailFast(ecx)
0x180006352  mov     rcx, rax; void *
0x180006355  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000635a  mov     qword ptr [rdi], 0
0x180006361  mov     qword ptr [rdi+8], 0
0x180006369  mov     qword ptr [rdi+10h], 0
0x180006371  mov     rbx, [rsp+28h+arg_0]
0x180006376  mov     rsi, [rsp+28h+arg_8]
0x18000637b  add     rsp, 20h
0x18000637f  pop     rdi
0x180006380  retn
```
