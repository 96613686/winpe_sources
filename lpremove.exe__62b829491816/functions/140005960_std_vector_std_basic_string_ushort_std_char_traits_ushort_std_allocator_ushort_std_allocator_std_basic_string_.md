# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x140005960`
- end: `0x1400059df`
- name: `??1_Reallocation_guard@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140004390`
- `0x14000e3b8`
- `0x14000f8d0`
- `0x14001046a`
- `0x1400106cf`

## callees

- `0x1400021b4`
- `0x140005020`
- `0x140005960`

## pseudocode

```c
void __fastcall std::vector<std::wstring>::_Reallocation_guard::~_Reallocation_guard(_QWORD *a1)
{
  char **v2; // rsi
  char **i; // rdi
  __int64 v4; // rax
  void *v5; // rcx

  if ( a1[1] )
  {
    v2 = (char **)a1[4];
    for ( i = (char **)a1[3]; i != v2; i += 4 )
      std::wstring::~wstring(i);
    v4 = a1[1];
    if ( (unsigned __int64)(32LL * a1[2]) < 0x1000 )
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
0x140005960  mov     [rsp+arg_0], rbx
0x140005965  mov     [rsp+arg_8], rsi
0x14000596a  push    rdi
0x14000596b  sub     rsp, 20h
0x14000596f  cmp     qword ptr [rcx+8], 0
0x140005974  mov     rbx, rcx
0x140005977  jz      short loc_1400059CF
0x140005979  mov     rsi, [rcx+20h]
0x14000597d  mov     rdi, [rcx+18h]
0x140005981  jmp     short loc_14000598F
0x140005983  mov     rcx, rdi
0x140005986  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000598b  add     rdi, 20h ; ' '
0x14000598f  cmp     rdi, rsi
0x140005992  jnz     short loc_140005983
0x140005994  mov     rdx, [rbx+10h]
0x140005998  mov     rax, [rbx+8]
0x14000599c  shl     rdx, 5
0x1400059a0  cmp     rdx, 1000h
0x1400059a7  jb      short loc_1400059C7
0x1400059a9  mov     rcx, [rax-8]
0x1400059ad  sub     rax, rcx
0x1400059b0  sub     rax, 8
0x1400059b4  cmp     rax, 1Fh
0x1400059b8  ja      short loc_1400059C0
0x1400059ba  add     rdx, 27h ; '''
0x1400059be  jmp     short loc_1400059CA
0x1400059c0  mov     ecx, 5
0x1400059c5  int     29h; Win8: RtlFailFast(ecx)
0x1400059c7  mov     rcx, rax; Block
0x1400059ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400059cf  mov     rbx, [rsp+28h+arg_0]
0x1400059d4  mov     rsi, [rsp+28h+arg_8]
0x1400059d9  add     rsp, 20h
0x1400059dd  pop     rdi
0x1400059de  retn
```
