# std::basic_stringbuf<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringbuf<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1400063a0`
- end: `0x14000648a`
- name: `??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ`
- size: `234`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140007044`
- `0x140007150`
- `0x14000718c`
- `0x14000eafc`

## callees

- `0x140002578`
- `0x1400063a0`

## import_xrefs

- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140006483`

## pseudocode

```c
__int64 __fastcall std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(__int64 a1)
{
  bool v1; // zf
  __int64 v3; // rdx
  __int64 v4; // rdx
  char **v5; // rax
  char *v6; // rcx
  unsigned __int64 v7; // rdx
  char *v8; // rax

  v1 = (*(_BYTE *)(a1 + 112) & 1) == 0;
  *(_QWORD *)a1 = &std::basic_stringbuf<unsigned short>::`vftable';
  if ( !v1 )
  {
    v3 = **(_QWORD **)(a1 + 64);
    if ( v3 )
      v4 = v3 + 2LL * **(int **)(a1 + 88);
    else
      v4 = **(_QWORD **)(a1 + 56) + 2LL * **(int **)(a1 + 80);
    v5 = *(char ***)(a1 + 24);
    v6 = *v5;
    v7 = 2 * ((v4 - (__int64)*v5) >> 1);
    if ( v7 < 0x1000 )
    {
      v8 = *v5;
    }
    else
    {
      v8 = (char *)*((_QWORD *)v6 - 1);
      if ( (unsigned __int64)(v6 - v8 - 8) > 0x1F )
        __fastfail(5u);
      v7 += 39LL;
    }
    operator delete(v8, v7);
  }
  **(_QWORD **)(a1 + 24) = 0;
  **(_QWORD **)(a1 + 56) = 0;
  **(_DWORD **)(a1 + 80) = 0;
  **(_QWORD **)(a1 + 32) = 0;
  **(_QWORD **)(a1 + 64) = 0;
  **(_DWORD **)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 112) &= ~1u;
  *(_QWORD *)(a1 + 104) = 0;
  return std::basic_streambuf<unsigned short>::~basic_streambuf<unsigned short,std::char_traits<unsigned short>>(a1);
}

```

## disassembly

```asm
0x1400063a0  mov     [rsp+arg_0], rbx
0x1400063a5  push    rdi
0x1400063a6  sub     rsp, 20h
0x1400063aa  test    byte ptr [rcx+70h], 1
0x1400063ae  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x1400063b5  mov     [rcx], rax
0x1400063b8  mov     rbx, rcx
0x1400063bb  jz      short loc_14000642A
0x1400063bd  mov     rax, [rcx+40h]
0x1400063c1  mov     rdx, [rax]
0x1400063c4  test    rdx, rdx
0x1400063c7  jz      short loc_1400063D6
0x1400063c9  mov     rax, [rcx+58h]
0x1400063cd  movsxd  rcx, dword ptr [rax]
0x1400063d0  lea     rdx, [rdx+rcx*2]
0x1400063d4  jmp     short loc_1400063E8
0x1400063d6  mov     rax, [rcx+50h]
0x1400063da  movsxd  rdx, dword ptr [rax]
0x1400063dd  mov     rax, [rcx+38h]
0x1400063e1  mov     rcx, [rax]
0x1400063e4  lea     rdx, [rcx+rdx*2]
0x1400063e8  mov     rax, [rbx+18h]
0x1400063ec  mov     rcx, [rax]
0x1400063ef  sub     rdx, rcx
0x1400063f2  sar     rdx, 1
0x1400063f5  add     rdx, rdx; unsigned __int64
0x1400063f8  cmp     rdx, 1000h
0x1400063ff  jb      short loc_14000641F
0x140006401  mov     rax, [rcx-8]
0x140006405  sub     rcx, rax
0x140006408  sub     rcx, 8
0x14000640c  cmp     rcx, 1Fh
0x140006410  ja      short loc_140006418
0x140006412  add     rdx, 27h ; '''
0x140006416  jmp     short loc_140006422
0x140006418  mov     ecx, 5
0x14000641d  int     29h; Win8: RtlFailFast(ecx)
0x14000641f  mov     rax, rcx
0x140006422  mov     rcx, rax; void *
0x140006425  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000642a  mov     rax, [rbx+18h]
0x14000642e  mov     rcx, rbx
0x140006431  mov     qword ptr [rax], 0
0x140006438  mov     rax, [rbx+38h]
0x14000643c  mov     qword ptr [rax], 0
0x140006443  mov     rax, [rbx+50h]
0x140006447  mov     dword ptr [rax], 0
0x14000644d  mov     rax, [rbx+20h]
0x140006451  mov     qword ptr [rax], 0
0x140006458  mov     rax, [rbx+40h]
0x14000645c  mov     qword ptr [rax], 0
0x140006463  mov     rax, [rbx+58h]
0x140006467  mov     dword ptr [rax], 0
0x14000646d  and     dword ptr [rbx+70h], 0FFFFFFFEh
0x140006471  mov     qword ptr [rbx+68h], 0
0x140006479  mov     rbx, [rsp+28h+arg_0]
0x14000647e  add     rsp, 20h
0x140006482  pop     rdi
0x140006483  jmp     cs:__imp_??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_streambuf<ushort>::~basic_streambuf<ushort,std::char_traits<ushort>>(void)
```
