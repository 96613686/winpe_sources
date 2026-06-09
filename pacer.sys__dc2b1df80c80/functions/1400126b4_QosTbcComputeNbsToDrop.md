# QosTbcComputeNbsToDrop

- ea: `0x1400126b4`
- end: `0x1400127ab`
- name: `QosTbcComputeNbsToDrop`
- size: `247`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007260`
- `0x14000bdf4`

## callees

- `0x140012654`
- `0x1400126b4`

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
0x1400126b4  mov     [rsp+arg_0], rbx
0x1400126b9  mov     [rsp+arg_8], rsi
0x1400126be  push    rdi
0x1400126bf  sub     rsp, 20h
0x1400126c3  xor     edi, edi
0x1400126c5  mov     esi, edx
0x1400126c7  cmp     dword ptr [rcx+14Ch], 1
0x1400126ce  mov     rbx, rcx
0x1400126d1  jnz     short loc_1400126E8
0x1400126d3  mov     eax, [rcx+128h]
0x1400126d9  cmp     rax, [rcx+118h]
0x1400126e0  cmovle  esi, edi
0x1400126e3  jmp     loc_140012798
0x1400126e8  mov     esi, edi
0x1400126ea  call    QosTbcComputeDropRate
0x1400126ef  mov     r10d, eax
0x1400126f2  test    eax, eax
0x1400126f4  jz      loc_140012798
0x1400126fa  cmp     [rbx+174h], edi
0x140012700  ja      loc_140012798
0x140012706  mov     r9d, [rbx+19Ch]
0x14001270d  mov     r11d, 1Fh
0x140012713  mov     eax, [rbx+17Ch]
0x140012719  cmp     r9d, 0Fh
0x14001271d  jb      short loc_140012736
0x14001271f  lea     ecx, [r9-1]
0x140012723  cmp     ecx, r11d
0x140012726  lea     r8d, [r11-1Eh]
0x14001272a  cmova   ecx, r11d
0x14001272e  xor     edx, edx
0x140012730  shl     r8d, cl
0x140012733  div     r8d
0x140012736  cmp     r10d, eax
0x140012739  jbe     short loc_140012798
0x14001273b  mov     ecx, [rbx+1A0h]
0x140012741  test    cl, 8
0x140012744  jnz     short loc_140012787
0x140012746  cmp     r9d, r11d
0x140012749  jz      short loc_140012787
0x14001274b  mov     rax, [rbx+120h]
0x140012752  mov     r9d, 4
0x140012758  mov     r8, [rbx+118h]
0x14001275f  lea     rax, [rax+rax*2]
0x140012763  cqo
0x140012765  idiv    r9
0x140012768  cmp     r8, rax
0x14001276b  jl      short loc_140012787
0x14001276d  and     ecx, 0FFFFFFEFh
0x140012770  mov     [rbx+188h], r8
0x140012777  or      ecx, 28h
0x14001277a  mov     [rbx+194h], rdi
0x140012781  mov     [rbx+1A0h], ecx
0x140012787  mov     ecx, [rbx+178h]
0x14001278d  mov     esi, 1
0x140012792  mov     [rbx+174h], ecx
0x140012798  mov     rbx, [rsp+28h+arg_0]
0x14001279d  mov     eax, esi
0x14001279f  mov     rsi, [rsp+28h+arg_8]
0x1400127a4  add     rsp, 20h
0x1400127a8  pop     rdi
0x1400127a9  retn
```
