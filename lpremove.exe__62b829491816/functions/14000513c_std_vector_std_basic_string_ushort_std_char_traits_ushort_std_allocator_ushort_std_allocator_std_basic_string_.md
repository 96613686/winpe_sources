# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::~vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(void)

- ea: `0x14000513c`
- end: `0x1400051d1`
- name: `??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(__int64)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140006a50`
- `0x14000c36c`
- `0x14000eac8`
- `0x14000eeb8`
- `0x14000f530`
- `0x140010393`
- `0x1400103b7`
- `0x1400103db`
- `0x14001043e`
- `0x1400105bd`

## callees

- `0x1400021b4`
- `0x140005020`
- `0x14000513c`

## pseudocode

```c
void __fastcall std::vector<std::wstring>::~vector<std::wstring>(__int64 a1)
{
  char **v1; // rbx
  char **v3; // rsi
  char **v4; // rax
  char **v5; // rcx

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
    if ( ((*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFE0uLL) < 0x1000 )
    {
      v5 = *(char ***)a1;
    }
    else
    {
      v5 = (char **)*(v4 - 1);
      if ( (unsigned __int64)((char *)v4 - (char *)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x14000513c  mov     [rsp+arg_0], rbx
0x140005141  mov     [rsp+arg_8], rsi
0x140005146  push    rdi
0x140005147  sub     rsp, 20h
0x14000514b  mov     rbx, [rcx]
0x14000514e  mov     rdi, rcx
0x140005151  test    rbx, rbx
0x140005154  jz      short loc_1400051C1
0x140005156  mov     rsi, [rcx+8]
0x14000515a  jmp     short loc_140005168
0x14000515c  mov     rcx, rbx
0x14000515f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140005164  add     rbx, 20h ; ' '
0x140005168  cmp     rbx, rsi
0x14000516b  jnz     short loc_14000515C
0x14000516d  mov     rax, [rdi]
0x140005170  mov     rdx, [rdi+10h]
0x140005174  sub     rdx, rax
0x140005177  and     rdx, 0FFFFFFFFFFFFFFE0h
0x14000517b  cmp     rdx, 1000h
0x140005182  jb      short loc_1400051A2
0x140005184  mov     rcx, [rax-8]
0x140005188  sub     rax, rcx
0x14000518b  sub     rax, 8
0x14000518f  cmp     rax, 1Fh
0x140005193  ja      short loc_14000519B
0x140005195  add     rdx, 27h ; '''
0x140005199  jmp     short loc_1400051A5
0x14000519b  mov     ecx, 5
0x1400051a0  int     29h; Win8: RtlFailFast(ecx)
0x1400051a2  mov     rcx, rax; Block
0x1400051a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400051aa  mov     qword ptr [rdi], 0
0x1400051b1  mov     qword ptr [rdi+8], 0
0x1400051b9  mov     qword ptr [rdi+10h], 0
0x1400051c1  mov     rbx, [rsp+28h+arg_0]
0x1400051c6  mov     rsi, [rsp+28h+arg_8]
0x1400051cb  add     rsp, 20h
0x1400051cf  pop     rdi
0x1400051d0  retn
```
