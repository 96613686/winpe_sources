# QosTbcComputeNbsToDrop

- ea: `0x140015258`
- end: `0x14001534f`
- name: `QosTbcComputeNbsToDrop`
- size: `247`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400093fc`
- `0x1400097f8`

## callees

- `0x1400151f8`
- `0x140015258`

## pseudocode

```c
__int64 __fastcall QosTbcComputeNbsToDrop(__int64 a1, unsigned int a2)
{
  unsigned int v4; // r10d
  unsigned int v5; // r9d
  unsigned int v6; // eax
  char v7; // cl
  int v8; // ecx
  __int64 v9; // r8

  if ( *(_DWORD *)(a1 + 332) == 1 )
  {
    if ( *(unsigned int *)(a1 + 296) <= *(__int64 *)(a1 + 280) )
      return 0;
  }
  else
  {
    a2 = 0;
    v4 = QosTbcComputeDropRate();
    if ( v4 && !*(_DWORD *)(a1 + 372) )
    {
      v5 = *(_DWORD *)(a1 + 412);
      v6 = *(_DWORD *)(a1 + 380);
      if ( v5 >= 0xF )
      {
        v7 = v5 - 1;
        if ( v5 - 1 > 0x1F )
          v7 = 31;
        v6 /= (unsigned int)(1 << v7);
      }
      if ( v4 > v6 )
      {
        v8 = *(_DWORD *)(a1 + 416);
        if ( (v8 & 8) == 0 && v5 != 31 )
        {
          v9 = *(_QWORD *)(a1 + 280);
          if ( v9 >= 3LL * *(_QWORD *)(a1 + 288) / 4 )
          {
            *(_QWORD *)(a1 + 392) = v9;
            *(_QWORD *)(a1 + 404) = 0;
            *(_DWORD *)(a1 + 416) = v8 & 0xFFFFFFC7 | 0x28;
          }
        }
        a2 = 1;
        *(_DWORD *)(a1 + 372) = *(_DWORD *)(a1 + 376);
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140015258  mov     [rsp+arg_0], rbx
0x14001525d  mov     [rsp+arg_8], rsi
0x140015262  push    rdi
0x140015263  sub     rsp, 20h
0x140015267  xor     edi, edi
0x140015269  mov     esi, edx
0x14001526b  cmp     dword ptr [rcx+14Ch], 1
0x140015272  mov     rbx, rcx
0x140015275  jnz     short loc_14001528C
0x140015277  mov     eax, [rcx+128h]
0x14001527d  cmp     rax, [rcx+118h]
0x140015284  cmovle  esi, edi
0x140015287  jmp     loc_14001533C
0x14001528c  mov     esi, edi
0x14001528e  call    QosTbcComputeDropRate
0x140015293  mov     r10d, eax
0x140015296  test    eax, eax
0x140015298  jz      loc_14001533C
0x14001529e  cmp     [rbx+174h], edi
0x1400152a4  ja      loc_14001533C
0x1400152aa  mov     r9d, [rbx+19Ch]
0x1400152b1  mov     r11d, 1Fh
0x1400152b7  mov     eax, [rbx+17Ch]
0x1400152bd  cmp     r9d, 0Fh
0x1400152c1  jb      short loc_1400152DA
0x1400152c3  lea     ecx, [r9-1]
0x1400152c7  cmp     ecx, r11d
0x1400152ca  lea     r8d, [r11-1Eh]
0x1400152ce  cmova   ecx, r11d
0x1400152d2  xor     edx, edx
0x1400152d4  shl     r8d, cl
0x1400152d7  div     r8d
0x1400152da  cmp     r10d, eax
0x1400152dd  jbe     short loc_14001533C
0x1400152df  mov     ecx, [rbx+1A0h]
0x1400152e5  test    cl, 8
0x1400152e8  jnz     short loc_14001532B
0x1400152ea  cmp     r9d, r11d
0x1400152ed  jz      short loc_14001532B
0x1400152ef  mov     rax, [rbx+120h]
0x1400152f6  mov     r9d, 4
0x1400152fc  mov     r8, [rbx+118h]
0x140015303  lea     rax, [rax+rax*2]
0x140015307  cqo
0x140015309  idiv    r9
0x14001530c  cmp     r8, rax
0x14001530f  jl      short loc_14001532B
0x140015311  and     ecx, 0FFFFFFEFh
0x140015314  mov     [rbx+188h], r8
0x14001531b  or      ecx, 28h
0x14001531e  mov     [rbx+194h], rdi
0x140015325  mov     [rbx+1A0h], ecx
0x14001532b  mov     ecx, [rbx+178h]
0x140015331  mov     esi, 1
0x140015336  mov     [rbx+174h], ecx
0x14001533c  mov     rbx, [rsp+28h+arg_0]
0x140015341  mov     eax, esi
0x140015343  mov     rsi, [rsp+28h+arg_8]
0x140015348  add     rsp, 20h
0x14001534c  pop     rdi
0x14001534d  retn
```
