# acmdStreamOpen

- ea: `0x1800025a0`
- end: `0x180002742`
- name: `acmdStreamOpen`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001cd0`

## callees

- `0x1800025a0`
- `0x1800028b8`
- `0x180002910`
- `0x180002988`

## pseudocode

```c
__int64 __fastcall acmdStreamOpen(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rsi
  __int16 v5; // bp
  __int64 v6; // rcx
  __int16 v7; // r9
  __int64 (__fastcall *v8)(int, int, int, int, int, int, int, __int64); // rcx
  __int64 (__fastcall *v10)(int, int, int, int, int, int); // rcx
  __int64 (__fastcall *v11)(int, int, int, int, int, int); // rdx

  v2 = *(_QWORD *)(a2 + 4);
  v4 = *(_QWORD *)(a2 + 12);
  if ( (unsigned int)adpcmIsValidFormat(v2) )
  {
    if ( !(unsigned int)pcmIsValidFormat(v4) )
      return 512;
    v5 = *(_WORD *)(v2 + 2);
    if ( v5 != *(_WORD *)(v4 + 2) || *(_DWORD *)(v2 + 4) != *(_DWORD *)(v4 + 4) )
      return 512;
    v6 = v2;
  }
  else
  {
    if ( !(unsigned int)pcmIsValidFormat(v2) )
      return 512;
    if ( !(unsigned int)adpcmIsValidFormat(v4) )
      return 512;
    v5 = *(_WORD *)(v2 + 2);
    if ( *(_WORD *)(v4 + 2) != v5 || *(_DWORD *)(v4 + 4) != *(_DWORD *)(v2 + 4) )
      return 512;
    v6 = v4;
  }
  if ( (unsigned int)adpcmIsMagicFormat(v6) )
  {
    if ( *(_WORD *)v2 == 2 )
    {
      if ( v7 == 1 )
      {
        v8 = adpcmDecode4Bit_M16;
        if ( *(_WORD *)(v4 + 14) == 8 )
          v8 = adpcmDecode4Bit_M08;
        goto LABEL_20;
      }
      if ( v7 == 2 )
      {
        v8 = adpcmDecode4Bit_S08;
        if ( *(_WORD *)(v4 + 14) != 8 )
          v8 = adpcmDecode4Bit_S16;
LABEL_20:
        *(_QWORD *)(a2 + 52) = v8;
        return 0;
      }
      return 512;
    }
    if ( *(_WORD *)v2 != 1 )
      return 512;
    if ( (*(_BYTE *)(a2 + 44) & 4) != 0 )
    {
      if ( v5 == 1 )
      {
        v10 = (__int64 (__fastcall *)(int, int, int, int, int, int))adpcmEncode4Bit_M16_FullPass;
        if ( *(_WORD *)(v2 + 14) == 8 )
          v10 = (__int64 (__fastcall *)(int, int, int, int, int, int))adpcmEncode4Bit_M08_FullPass;
        goto LABEL_38;
      }
      if ( v5 != 2 )
        return 512;
      v10 = (__int64 (__fastcall *)(int, int, int, int, int, int))adpcmEncode4Bit_S08_FullPass;
      v11 = (__int64 (__fastcall *)(int, int, int, int, int, int))adpcmEncode4Bit_S16_FullPass;
    }
    else
    {
      if ( v5 == 1 )
      {
        v10 = adpcmEncode4Bit_M08_OnePass;
        if ( *(_WORD *)(v2 + 14) != 8 )
          v10 = adpcmEncode4Bit_M16_OnePass;
        goto LABEL_38;
      }
      if ( v5 != 2 )
        return 512;
      v10 = adpcmEncode4Bit_S08_OnePass;
      v11 = adpcmEncode4Bit_S16_OnePass;
    }
    if ( *(_WORD *)(v2 + 14) != 8 )
      v10 = v11;
LABEL_38:
    *(_QWORD *)(a2 + 52) = v10;
    return 0;
  }
  return 512;
}

```

## disassembly

```asm
0x1800025a0  push    rbx
0x1800025a2  push    rbp
0x1800025a3  push    rsi
0x1800025a4  push    rdi
0x1800025a5  sub     rsp, 28h
0x1800025a9  mov     rbx, [rdx+4]
0x1800025ad  mov     rdi, rdx
0x1800025b0  mov     rsi, [rdx+0Ch]
0x1800025b4  mov     rcx, rbx
0x1800025b7  call    adpcmIsValidFormat
0x1800025bc  test    eax, eax
0x1800025be  jz      short loc_1800025F4
0x1800025c0  mov     rcx, rsi
0x1800025c3  call    pcmIsValidFormat
0x1800025c8  test    eax, eax
0x1800025ca  jz      loc_180002734
0x1800025d0  movzx   ebp, word ptr [rbx+2]
0x1800025d4  movzx   r9d, word ptr [rsi+2]
0x1800025d9  cmp     bp, r9w
0x1800025dd  jnz     loc_180002734
0x1800025e3  mov     eax, [rsi+4]
0x1800025e6  cmp     [rbx+4], eax
0x1800025e9  jnz     loc_180002734
0x1800025ef  mov     rcx, rbx
0x1800025f2  jmp     short loc_180002636
0x1800025f4  mov     rcx, rbx
0x1800025f7  call    pcmIsValidFormat
0x1800025fc  test    eax, eax
0x1800025fe  jz      loc_180002734
0x180002604  mov     rcx, rsi
0x180002607  call    adpcmIsValidFormat
0x18000260c  test    eax, eax
0x18000260e  jz      loc_180002734
0x180002614  movzx   r9d, word ptr [rsi+2]
0x180002619  movzx   ebp, word ptr [rbx+2]
0x18000261d  cmp     r9w, bp
0x180002621  jnz     loc_180002734
0x180002627  mov     eax, [rbx+4]
0x18000262a  cmp     [rsi+4], eax
0x18000262d  jnz     loc_180002734
0x180002633  mov     rcx, rsi
0x180002636  call    adpcmIsMagicFormat
0x18000263b  test    eax, eax
0x18000263d  jz      loc_180002734
0x180002643  cmp     word ptr [rbx], 2
0x180002647  jnz     short loc_18000269C
0x180002649  movzx   ecx, r9w
0x18000264d  sub     ecx, 1
0x180002650  jz      short loc_180002676
0x180002652  cmp     ecx, 1
0x180002655  jnz     loc_180002734
0x18000265b  lea     eax, [rcx+7]
0x18000265e  cmp     ax, [rsi+0Eh]
0x180002662  lea     rcx, adpcmDecode4Bit_S08
0x180002669  lea     rdx, adpcmDecode4Bit_S16
0x180002670  cmovnz  rcx, rdx
0x180002674  jmp     short loc_180002691
0x180002676  mov     eax, 8
0x18000267b  lea     rcx, adpcmDecode4Bit_M16
0x180002682  cmp     ax, [rsi+0Eh]
0x180002686  lea     rdx, adpcmDecode4Bit_M08
0x18000268d  cmovz   rcx, rdx
0x180002691  mov     [rdi+34h], rcx
0x180002695  xor     eax, eax
0x180002697  jmp     loc_180002739
0x18000269c  cmp     word ptr [rbx], 1
0x1800026a0  jnz     loc_180002734
0x1800026a6  test    byte ptr [rdi+2Ch], 4
0x1800026aa  movzx   ecx, bp
0x1800026ad  jz      short loc_1800026F3
0x1800026af  sub     ecx, 1
0x1800026b2  jz      short loc_1800026D6
0x1800026b4  cmp     ecx, 1
0x1800026b7  jnz     short loc_180002734
0x1800026b9  lea     rcx, adpcmEncode4Bit_S08_FullPass
0x1800026c0  lea     rdx, adpcmEncode4Bit_S16_FullPass
0x1800026c7  mov     eax, 8
0x1800026cc  cmp     ax, [rbx+0Eh]
0x1800026d0  cmovnz  rcx, rdx
0x1800026d4  jmp     short loc_180002726
0x1800026d6  mov     eax, 8
0x1800026db  lea     rcx, adpcmEncode4Bit_M16_FullPass
0x1800026e2  cmp     ax, [rbx+0Eh]
0x1800026e6  lea     rdx, adpcmEncode4Bit_M08_FullPass
0x1800026ed  cmovz   rcx, rdx
0x1800026f1  jmp     short loc_180002726
0x1800026f3  sub     ecx, 1
0x1800026f6  jz      short loc_18000270D
0x1800026f8  cmp     ecx, 1
0x1800026fb  jnz     short loc_180002734
0x1800026fd  lea     rcx, adpcmEncode4Bit_S08_OnePass
0x180002704  lea     rdx, adpcmEncode4Bit_S16_OnePass
0x18000270b  jmp     short loc_1800026C7
0x18000270d  mov     eax, 8
0x180002712  lea     rcx, adpcmEncode4Bit_M08_OnePass
0x180002719  cmp     ax, [rbx+0Eh]
0x18000271d  jz      short loc_180002726
0x18000271f  lea     rcx, adpcmEncode4Bit_M16_OnePass
0x180002726  mov     eax, 34h ; '4'
0x18000272b  mov     [rdi+rax], rcx
0x18000272f  jmp     loc_180002695
0x180002734  mov     eax, 200h
0x180002739  add     rsp, 28h
0x18000273d  pop     rdi
0x18000273e  pop     rsi
0x18000273f  pop     rbp
0x180002740  pop     rbx
0x180002741  retn
```
