# RemoveDuplicates<std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x14000df20`
- end: `0x14000e01b`
- name: `??$RemoveDuplicates@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `251`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000eeb8`

## callees

- `0x140005020`
- `0x140005a04`
- `0x14000dc4c`
- `0x14000df20`

## pseudocode

```c
void __fastcall RemoveDuplicates<std::vector<std::wstring>>(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 i; // rdi
  __int64 j; // rsi
  const wchar_t *v5; // rdx
  size_t v6; // r8
  const wchar_t *v7; // rcx
  __int64 k; // r14
  const wchar_t *v9; // rdx
  size_t v10; // r8
  const wchar_t *v11; // rcx
  __int64 v12; // rsi
  __int64 v13; // rdi

  v1 = a1[1];
  for ( i = *a1; i != v1; i += 32 )
  {
    for ( j = i + 32; j != v1; j += 32 )
    {
      v5 = (const wchar_t *)i;
      if ( *(_QWORD *)(i + 24) > 7u )
        v5 = *(const wchar_t **)i;
      v6 = *(_QWORD *)(j + 16);
      if ( *(_QWORD *)(j + 24) <= 7u )
        v7 = (const wchar_t *)j;
      else
        v7 = *(const wchar_t **)j;
      if ( v6 == *(_QWORD *)(i + 16) && (!v6 || !wmemcmp(v7, v5, v6)) )
        break;
    }
    if ( j != v1 )
    {
      for ( k = j + 32; k != v1; k += 32 )
      {
        if ( *(_QWORD *)(i + 24) <= 7u )
          v9 = (const wchar_t *)i;
        else
          v9 = *(const wchar_t **)i;
        v10 = *(_QWORD *)(k + 16);
        if ( *(_QWORD *)(k + 24) <= 7u )
          v11 = (const wchar_t *)k;
        else
          v11 = *(const wchar_t **)k;
        if ( v10 != *(_QWORD *)(i + 16) || v10 && wmemcmp(v11, v9, v10) )
        {
          std::wstring::operator=(j, k);
          j += 32;
        }
      }
    }
    v1 = j;
  }
  v12 = a1[1];
  if ( v1 != v12 )
  {
    v13 = v1;
    do
    {
      std::wstring::~wstring(v13);
      v13 += 32;
    }
    while ( v13 != v12 );
    a1[1] = v1;
  }
}

```

## disassembly

```asm
0x14000df20  push    rbx
0x14000df22  push    rbp
0x14000df23  push    rsi
0x14000df24  push    rdi
0x14000df25  push    r14
0x14000df27  push    r15
0x14000df29  sub     rsp, 28h
0x14000df2d  mov     rbx, [rcx+8]
0x14000df31  mov     r15, rcx
0x14000df34  mov     rdi, [rcx]
0x14000df37  cmp     rdi, rbx
0x14000df3a  jz      loc_14000DFED
0x14000df40  lea     rbp, [rdi+20h]
0x14000df44  mov     rsi, rbp
0x14000df47  cmp     rbp, rbx
0x14000df4a  jz      short loc_14000DF89
0x14000df4c  cmp     qword ptr [rdi+18h], 7
0x14000df51  mov     rdx, rdi
0x14000df54  jbe     short loc_14000DF59
0x14000df56  mov     rdx, [rdi]; S2
0x14000df59  cmp     qword ptr [rsi+18h], 7
0x14000df5e  mov     r8, [rsi+10h]; N
0x14000df62  jbe     short loc_14000DF69
0x14000df64  mov     rcx, [rsi]
0x14000df67  jmp     short loc_14000DF6C
0x14000df69  mov     rcx, rsi; S1
0x14000df6c  cmp     r8, [rdi+10h]
0x14000df70  jnz     short loc_14000DF80
0x14000df72  test    r8, r8
0x14000df75  jz      short loc_14000DF89
0x14000df77  call    wmemcmp
0x14000df7c  test    eax, eax
0x14000df7e  jz      short loc_14000DF89
0x14000df80  add     rsi, 20h ; ' '
0x14000df84  cmp     rsi, rbx
0x14000df87  jnz     short loc_14000DF4C
0x14000df89  cmp     rsi, rbx
0x14000df8c  jz      short loc_14000DFE2
0x14000df8e  lea     r14, [rsi+20h]
0x14000df92  jmp     short loc_14000DFDD
0x14000df94  cmp     qword ptr [rdi+18h], 7
0x14000df99  jbe     short loc_14000DFA0
0x14000df9b  mov     rdx, [rdi]
0x14000df9e  jmp     short loc_14000DFA3
0x14000dfa0  mov     rdx, rdi; S2
0x14000dfa3  cmp     qword ptr [r14+18h], 7
0x14000dfa8  mov     r8, [r14+10h]; N
0x14000dfac  jbe     short loc_14000DFB3
0x14000dfae  mov     rcx, [r14]
0x14000dfb1  jmp     short loc_14000DFB6
0x14000dfb3  mov     rcx, r14; S1
0x14000dfb6  cmp     r8, [rdi+10h]
0x14000dfba  jnz     short loc_14000DFCA
0x14000dfbc  test    r8, r8
0x14000dfbf  jz      short loc_14000DFD9
0x14000dfc1  call    wmemcmp
0x14000dfc6  test    eax, eax
0x14000dfc8  jz      short loc_14000DFD9
0x14000dfca  mov     rdx, r14
0x14000dfcd  mov     rcx, rsi
0x14000dfd0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000dfd5  add     rsi, 20h ; ' '
0x14000dfd9  add     r14, 20h ; ' '
0x14000dfdd  cmp     r14, rbx
0x14000dfe0  jnz     short loc_14000DF94
0x14000dfe2  mov     rbx, rsi
0x14000dfe5  mov     rdi, rbp
0x14000dfe8  jmp     loc_14000DF37
0x14000dfed  mov     rsi, [r15+8]
0x14000dff1  cmp     rbx, rsi
0x14000dff4  jz      short loc_14000E00E
0x14000dff6  mov     rdi, rbx
0x14000dff9  mov     rcx, rdi
0x14000dffc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e001  add     rdi, 20h ; ' '
0x14000e005  cmp     rdi, rsi
0x14000e008  jnz     short loc_14000DFF9
0x14000e00a  mov     [r15+8], rbx
0x14000e00e  add     rsp, 28h
0x14000e012  pop     r15
0x14000e014  pop     r14
0x14000e016  pop     rdi
0x14000e017  pop     rsi
0x14000e018  pop     rbp
0x14000e019  pop     rbx
0x14000e01a  retn
```
