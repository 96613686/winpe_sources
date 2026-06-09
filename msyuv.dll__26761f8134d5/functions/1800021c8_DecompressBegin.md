# DecompressBegin

- ea: `0x1800021c8`
- end: `0x18000229b`
- name: `DecompressBegin`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`

## callees

- `0x1800021c8`
- `0x1800022a4`
- `0x1800023bc`
- `0x180002764`
- `0x180002864`
- `0x1800029d0`

## pseudocode

```c
__int64 __fastcall DecompressBegin(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int16 v7; // ax
  __int64 v8; // rax

  result = DecompressQuery(a1, a2, a3);
  if ( !(_DWORD)result )
  {
    if ( *(_DWORD *)(a2 + 16) != *(_DWORD *)(a1 + 4) )
    {
      if ( !*(_QWORD *)(a1 + 8) )
        goto LABEL_6;
      DecompressEnd(a1);
    }
    if ( *(_QWORD *)(a1 + 8) )
      return 0;
LABEL_6:
    if ( *(_DWORD *)(a2 + 16) != 844715353 && *(_DWORD *)(a2 + 16) != 1431918169 && *(_DWORD *)(a2 + 16) != 1498831189 )
      return 4294967294LL;
    v7 = *(_WORD *)(a3 + 14);
    switch ( v7 )
    {
      case 8:
        v8 = 0;
        break;
      case 16:
        if ( *(_DWORD *)(a1 + 16) )
          v8 = BuildUYVYToRGB565(a1);
        else
          v8 = BuildUYVYToRGB555(a1);
        break;
      case 24:
      case 32:
        v8 = BuildUYVYToRGB32(a1);
        break;
      default:
        return 4294967294LL;
    }
    *(_QWORD *)(a1 + 8) = v8;
    if ( *(_WORD *)(a3 + 14) != 8 && !v8 )
      return 4294967293LL;
    *(_DWORD *)(a1 + 4) = *(_DWORD *)(a2 + 16);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800021c8  mov     [rsp+arg_0], rbx
0x1800021cd  mov     [rsp+arg_8], rsi
0x1800021d2  push    rdi
0x1800021d3  sub     rsp, 20h
0x1800021d7  mov     rsi, r8
0x1800021da  mov     rdi, rdx
0x1800021dd  mov     rbx, rcx
0x1800021e0  call    DecompressQuery
0x1800021e5  test    eax, eax
0x1800021e7  jnz     loc_18000228B
0x1800021ed  mov     eax, [rbx+4]
0x1800021f0  cmp     [rdi+10h], eax
0x1800021f3  jz      short loc_180002204
0x1800021f5  cmp     qword ptr [rbx+8], 0
0x1800021fa  jz      short loc_18000220B
0x1800021fc  mov     rcx, rbx
0x1800021ff  call    DecompressEnd
0x180002204  cmp     qword ptr [rbx+8], 0
0x180002209  jnz     short loc_180002289
0x18000220b  cmp     dword ptr [rdi+10h], 32595559h
0x180002212  jz      short loc_180002226
0x180002214  cmp     dword ptr [rdi+10h], 55595659h
0x18000221b  jz      short loc_180002226
0x18000221d  cmp     dword ptr [rdi+10h], 59565955h
0x180002224  jnz     short loc_180002242
0x180002226  movzx   eax, word ptr [rsi+0Eh]
0x18000222a  cmp     ax, 8
0x18000222e  jz      short loc_18000226A
0x180002230  cmp     ax, 10h
0x180002234  jz      short loc_180002253
0x180002236  cmp     ax, 18h
0x18000223a  jz      short loc_180002249
0x18000223c  cmp     ax, 20h ; ' '
0x180002240  jz      short loc_180002249
0x180002242  mov     eax, 0FFFFFFFEh
0x180002247  jmp     short loc_18000228B
0x180002249  mov     rcx, rbx
0x18000224c  call    BuildUYVYToRGB32
0x180002251  jmp     short loc_18000226C
0x180002253  cmp     dword ptr [rbx+10h], 0
0x180002257  mov     rcx, rbx
0x18000225a  jz      short loc_180002263
0x18000225c  call    BuildUYVYToRGB565
0x180002261  jmp     short loc_18000226C
0x180002263  call    BuildUYVYToRGB555
0x180002268  jmp     short loc_18000226C
0x18000226a  xor     eax, eax
0x18000226c  mov     [rbx+8], rax
0x180002270  cmp     word ptr [rsi+0Eh], 8
0x180002275  jz      short loc_180002283
0x180002277  test    rax, rax
0x18000227a  jnz     short loc_180002283
0x18000227c  mov     eax, 0FFFFFFFDh
0x180002281  jmp     short loc_18000228B
0x180002283  mov     eax, [rdi+10h]
0x180002286  mov     [rbx+4], eax
0x180002289  xor     eax, eax
0x18000228b  mov     rbx, [rsp+28h+arg_0]
0x180002290  mov     rsi, [rsp+28h+arg_8]
0x180002295  add     rsp, 20h
0x180002299  pop     rdi
0x18000229a  retn
```
