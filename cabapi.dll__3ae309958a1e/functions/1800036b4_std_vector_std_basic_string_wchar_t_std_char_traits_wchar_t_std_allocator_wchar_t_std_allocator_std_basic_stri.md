# std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>(void)

- ea: `0x1800036b4`
- end: `0x180003749`
- name: `??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(__int64)`
- caller_count: `13`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006d20`
- `0x180006fb0`
- `0x180007340`
- `0x180007490`
- `0x1800076f0`
- `0x180008c24`
- `0x180008d80`
- `0x180009b60`
- `0x180010124`
- `0x180014036`
- `0x18001405a`
- `0x18001406c`
- `0x180014132`

## callees

- `0x180001564`
- `0x180003648`
- `0x1800036b4`

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
0x1800036b4  mov     [rsp+arg_8], rbx
0x1800036b9  mov     [rsp+arg_10], rsi
0x1800036be  push    rdi
0x1800036bf  sub     rsp, 20h
0x1800036c3  mov     rbx, [rcx]
0x1800036c6  mov     rdi, rcx
0x1800036c9  test    rbx, rbx
0x1800036cc  jz      short loc_180003739
0x1800036ce  mov     rsi, [rcx+8]
0x1800036d2  jmp     short loc_1800036E0
0x1800036d4  mov     rcx, rbx
0x1800036d7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800036dc  add     rbx, 20h ; ' '
0x1800036e0  cmp     rbx, rsi
0x1800036e3  jnz     short loc_1800036D4
0x1800036e5  mov     rax, [rdi]
0x1800036e8  mov     rdx, [rdi+10h]
0x1800036ec  sub     rdx, rax
0x1800036ef  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x1800036f3  cmp     rdx, 1000h
0x1800036fa  jb      short loc_18000371A
0x1800036fc  mov     rcx, [rax-8]
0x180003700  sub     rax, rcx
0x180003703  sub     rax, 8
0x180003707  cmp     rax, 1Fh
0x18000370b  ja      short loc_180003713
0x18000370d  add     rdx, 27h ; '''
0x180003711  jmp     short loc_18000371D
0x180003713  mov     ecx, 5
0x180003718  int     29h; Win8: RtlFailFast(ecx)
0x18000371a  mov     rcx, rax; void *
0x18000371d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003722  mov     qword ptr [rdi], 0
0x180003729  mov     qword ptr [rdi+8], 0
0x180003731  mov     qword ptr [rdi+10h], 0
0x180003739  mov     rbx, [rsp+28h+arg_8]
0x18000373e  mov     rsi, [rsp+28h+arg_10]
0x180003743  add     rsp, 20h
0x180003747  pop     rdi
0x180003748  retn
```
