# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x180005c80`
- end: `0x180005d45`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `197`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180009504`
- `0x18000b3e0`
- `0x1800121a0`
- `0x1800145d0`
- `0x180019d80`

## callees

- `0x180005c00`
- `0x180005c80`
- `0x1800163d4`
- `0x180021ffc`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rax
  __int64 v7; // rbx
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  size_t v13; // rbx
  __int64 v14; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  a1[3] = 7;
  if ( a3 > 7 )
  {
    v9 = a3 | 7;
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v3 = a3 | 7;
      if ( v9 < 0xA )
        v3 = 10;
    }
    v14 = v3;
    v10 = std::wstring::_Allocate_for_capacity<0>(v9, &v14);
    v11 = v14;
    a1[2] = a3;
    v12 = v10;
    a1[3] = v11;
    v13 = 2 * a3;
    *a1 = v10;
    memcpy_0(v10, a2, v13);
    result = 0;
    *(_WORD *)((char *)v12 + v13) = 0;
  }
  else
  {
    a1[2] = a3;
    v7 = 2 * a3;
    memcpy_0(a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)a1 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005c80  mov     [rsp+arg_8], rbx
0x180005c85  mov     [rsp+arg_10], rbp
0x180005c8a  mov     [rsp+arg_18], rsi
0x180005c8f  push    rdi
0x180005c90  sub     rsp, 20h
0x180005c94  mov     rax, 7FFFFFFFFFFFFFFEh
0x180005c9e  mov     rbx, r8
0x180005ca1  mov     rbp, rdx
0x180005ca4  mov     rsi, rcx
0x180005ca7  cmp     r8, rax
0x180005caa  ja      loc_180005D3F
0x180005cb0  mov     qword ptr [rcx+18h], 7
0x180005cb8  cmp     rbx, 7
0x180005cbc  ja      short loc_180005CD5
0x180005cbe  mov     [rcx+10h], rbx
0x180005cc2  add     rbx, rbx
0x180005cc5  mov     r8, rbx; Size
0x180005cc8  call    memcpy_0
0x180005ccd  xor     eax, eax
0x180005ccf  mov     [rbx+rsi], ax
0x180005cd3  jmp     short loc_180005D29
0x180005cd5  mov     rcx, rbx
0x180005cd8  or      rcx, 7
0x180005cdc  cmp     rcx, rax
0x180005cdf  ja      short loc_180005CF0
0x180005ce1  mov     edx, 0Ah
0x180005ce6  mov     rax, rcx
0x180005ce9  cmp     rcx, rdx
0x180005cec  cmovb   rax, rdx
0x180005cf0  lea     rdx, [rsp+28h+arg_0]
0x180005cf5  mov     [rsp+28h+arg_0], rax
0x180005cfa  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180005cff  mov     rcx, [rsp+28h+arg_0]
0x180005d04  mov     rdx, rbp; Src
0x180005d07  mov     [rsi+10h], rbx
0x180005d0b  mov     rdi, rax
0x180005d0e  mov     [rsi+18h], rcx
0x180005d12  add     rbx, rbx
0x180005d15  mov     rcx, rax; void *
0x180005d18  mov     [rsi], rax
0x180005d1b  mov     r8, rbx; Size
0x180005d1e  call    memcpy_0
0x180005d23  xor     eax, eax
0x180005d25  mov     [rbx+rdi], ax
0x180005d29  mov     rbx, [rsp+28h+arg_8]
0x180005d2e  mov     rbp, [rsp+28h+arg_10]
0x180005d33  mov     rsi, [rsp+28h+arg_18]
0x180005d38  add     rsp, 20h
0x180005d3c  pop     rdi
0x180005d3d  retn
0x180005d3f  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
