# Compress

- ea: `0x1800028e0`
- end: `0x180002d96`
- name: `Compress`
- size: `1206`
- prototype: `HRESULT __stdcall(PVOID context, const BYTE *input_buffer, LONG input_buffer_size, PBYTE output_buffer, LONG output_buffer_size, PLONG input_used, PLONG output_used, INT compression_level)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180001c40`
- `0x1800028e0`
- `0x180002da0`
- `0x180003710`
- `0x180004fb0`
- `0x1800059dc`
- `0x180005bf0`
- `0x180006644`
- `0x180006808`
- `0x18000689c`
- `0x180006ac9`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000298c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000298c`

## pseudocode

```c
HRESULT __stdcall Compress(
        PVOID context,
        const BYTE *input_buffer,
        LONG input_buffer_size,
        PBYTE output_buffer,
        LONG output_buffer_size,
        PLONG input_used,
        PLONG output_used,
        INT compression_level)
{
  PLONG v8; // r12
  PLONG v9; // r13
  int v10; // r15d
  HRESULT result; // eax
  LPVOID v15; // rax
  unsigned __int64 v16; // r9
  __int64 v17; // rbp
  int v18; // ecx
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // r11
  __int64 v23; // rax
  __int64 v24; // rcx
  char v25; // al
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  bool v29; // zf
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  size_t v33; // rbx
  int v34; // eax
  const BYTE *v35; // r13
  int v36; // edi
  __int64 EncoderWindow; // rax
  char *v38; // r8
  int v39; // r10d
  int v40; // ecx
  unsigned int v41; // ecx
  char v42; // al
  __int64 v43; // rbx
  __int64 v44; // rax
  unsigned int v45; // [rsp+30h] [rbp-58h]
  unsigned int v46; // [rsp+34h] [rbp-54h]
  __int64 v47; // [rsp+40h] [rbp-48h]
  __int64 v48; // [rsp+48h] [rbp-40h]
  int v49; // [rsp+90h] [rbp+8h]
  int v51; // [rsp+A8h] [rbp+20h]
  INT compression_levela; // [rsp+C8h] [rbp+40h]

  v51 = (int)output_buffer;
  v8 = input_used;
  v9 = output_used;
  v10 = (int)output_buffer;
  *input_used = 0;
  *output_used = 0;
  if ( (unsigned int)compression_level > 0xA )
    return -2147024809;
  *((_QWORD *)context + 5) = output_buffer;
  *((_QWORD *)context + 6) = &output_buffer[output_buffer_size];
  *((_QWORD *)context + 7) = &output_buffer[output_buffer_size - 16];
  if ( *((_OWORD *)context + 5) == 0 && !*((_QWORD *)context + 12) )
  {
    if ( compression_level > 3 )
    {
      if ( compression_level == 10 )
      {
        v15 = HeapAlloc(g_hHeap, 0, 0x87A88u);
        *((_QWORD *)context + 11) = v15;
        if ( v15 )
        {
          OptimalEncoderReset(context);
          goto LABEL_10;
        }
      }
      else if ( (unsigned int)StdEncoderInit() )
      {
        goto LABEL_10;
      }
      return -2147024882;
    }
    if ( !(unsigned int)FastEncoderInit() )
      return -2147024882;
  }
LABEL_10:
  v16 = 0x180000000uLL;
  v17 = *((_QWORD *)context + 12);
  v48 = *((_QWORD *)context + 10);
  if ( v17 || *((_QWORD *)context + 10) )
  {
    v18 = dword_18000787C[4 * compression_level];
    v19 = (unsigned int)dword_180007870[4 * compression_level];
    v20 = (unsigned int)dword_180007878[4 * compression_level];
    v21 = dword_180007874[4 * compression_level];
  }
  else
  {
    v21 = 0;
    v19 = 0;
    v20 = 0;
    v18 = 0;
  }
  compression_levela = v21;
  v45 = v19;
  v46 = v20;
  v49 = v18;
  if ( output_buffer_size < 512 )
    return -2147024809;
  v22 = *((_QWORD *)context + 11);
  v47 = v22;
  if ( *((_DWORD *)context + 29) && !*((_DWORD *)context + 30) )
  {
    v23 = *((_QWORD *)context + 5);
    *(_DWORD *)(v23 + 1) = 2187;
    v16 = 4;
    *(_WORD *)(v23 + 5) = 0;
    *(_BYTE *)(v23 + 7) = 0;
    v24 = v23 + 1;
    *(_BYTE *)v23 = 31;
    v25 = 2;
    if ( compression_level != 10 )
      v25 = 4;
    *(_BYTE *)(v24 + 7) = v25;
    v26 = v24 + 9;
    *(_BYTE *)(v24 + 8) = 0;
    v18 = v49;
    *((_QWORD *)context + 5) = v26;
    v21 = compression_levela;
    *((_DWORD *)context + 30) = 1;
  }
  if ( !*(_DWORD *)context )
  {
    v27 = *((_QWORD *)context + 5);
    goto LABEL_31;
  }
  if ( v17 )
  {
LABEL_48:
    v35 = input_buffer;
    while ( 1 )
    {
      if ( input_buffer_size <= 0 )
      {
        if ( *((_DWORD *)context + 8) >= *((_DWORD *)context + 9) )
          goto LABEL_71;
        v21 = compression_levela;
      }
      v36 = 2 * *((_DWORD *)context + 18) - *((_DWORD *)context + 9);
      if ( input_buffer_size < v36 )
        v36 = input_buffer_size;
      if ( v36 > 0 )
      {
        *v8 += v36;
        if ( *((_DWORD *)context + 29) )
        {
          EncoderWindow = GetEncoderWindow(context, v19, v35, v16);
          v40 = *((_DWORD *)context + 31);
          v16 = EncoderWindow + *((int *)context + 9);
          *((_DWORD *)context + 32) += v36;
          v41 = ~v40;
          do
          {
            v42 = *v38++;
            *(_BYTE *)v16++ = v42;
            v41 = g_CrcTable[(unsigned __int8)(v41 ^ *(v38 - 1))] ^ (v41 >> 8);
            --v39;
          }
          while ( v39 );
          v8 = input_used;
          *((_DWORD *)context + 31) = ~v41;
          v43 = v36;
        }
        else
        {
          v43 = v36;
          v44 = GetEncoderWindow(context, v19, v20, v16);
          memcpy_0((void *)(v44 + *((int *)context + 9)), v35, v36);
          v22 = v47;
        }
        v18 = v49;
        v35 += v43;
        v19 = v45;
        input_buffer_size -= v36;
        *((_DWORD *)context + 9) += v36;
        v20 = v46;
        v21 = compression_levela;
      }
      if ( v22 )
      {
        OptimalEncoderDeflate(context, v19, v20, v16);
      }
      else if ( v48 )
      {
        StdEncoderDeflate((_DWORD)context, v18, v21, v19, v20);
      }
      else
      {
        if ( !v17 )
          goto LABEL_68;
        FastEncoderDeflate((_DWORD)context, v18, v21, v19, v20);
      }
      v22 = v47;
LABEL_68:
      if ( !*(_DWORD *)context )
      {
        v18 = v49;
        v19 = v45;
        v20 = v46;
        v21 = compression_levela;
        if ( v17 )
          continue;
        v18 = v49;
        if ( (__int64)(*((_QWORD *)context + 6) - *((_QWORD *)context + 5)) < 512 )
          continue;
      }
LABEL_71:
      v10 = v51;
      v9 = output_used;
LABEL_72:
      result = 0;
      goto LABEL_73;
    }
  }
  OutputBlock(context, v19, v20, v16);
  if ( *(_DWORD *)context )
  {
    LODWORD(v27) = *((_DWORD *)context + 10);
    goto LABEL_29;
  }
  v27 = *((_QWORD *)context + 5);
  if ( *((_QWORD *)context + 6) - v27 < 512 )
  {
LABEL_29:
    *output_used = v27 - v10;
    goto LABEL_72;
  }
  v22 = v47;
  v21 = compression_levela;
LABEL_31:
  v28 = v27;
  if ( input_buffer_size )
  {
    if ( !*((_DWORD *)context + 26) )
      goto LABEL_47;
  }
  else
  {
    v28 = v27;
  }
  if ( *((_DWORD *)context + 8) < *((_DWORD *)context + 9) )
  {
    v21 = compression_levela;
LABEL_47:
    v20 = v46;
    v19 = v45;
    v18 = v49;
    goto LABEL_48;
  }
  v29 = *((_DWORD *)context + 7) == 0;
  *((_DWORD *)context + 26) = 1;
  if ( !v29 )
  {
    FlushRecordingBuffer(context, v28);
    OutputBlock(context, v30, v31, v32);
    if ( *(_DWORD *)context )
      goto LABEL_72;
    v28 = *((_QWORD *)context + 5);
  }
  if ( v17 && !*(_DWORD *)(v17 + 37644) )
  {
    v33 = g_FastEncoderTreeLength;
    *(_DWORD *)(v17 + 37644) = 1;
    memcpy_0(*((void **)context + 5), g_FastEncoderTreeStructureData, v33);
    v34 = g_FastEncoderPostTreeBitbuf;
    *((_QWORD *)context + 5) += v33;
    v28 = *((_QWORD *)context + 5);
    *((_DWORD *)context + 16) = v34;
    *((_DWORD *)context + 17) = g_FastEncoderPostTreeBitcount;
  }
  if ( !*((_DWORD *)context + 27) )
  {
    if ( (unsigned __int64)(v28 + 8) >= *((_QWORD *)context + 6) )
      goto LABEL_72;
    markFinalBlock(context);
    *((_DWORD *)context + 27) = 1;
  }
  result = 1;
LABEL_73:
  *v9 = *((_DWORD *)context + 10) - v10;
  return result;
}

```

## disassembly

```asm
0x1800028e0  mov     [rsp+arg_18], r9
0x1800028e5  mov     [rsp+Src], rdx
0x1800028ea  push    rbx
0x1800028eb  push    rsi
0x1800028ec  push    r12
0x1800028ee  push    r13
0x1800028f0  push    r14
0x1800028f2  push    r15
0x1800028f4  sub     rsp, 58h
0x1800028f8  mov     r12, [rsp+88h+input_used]
0x180002900  xor     r10d, r10d
0x180002903  mov     r13, [rsp+88h+output_used]
0x18000290b  mov     r15, r9
0x18000290e  movsxd  rbx, [rsp+88h+compression_level]
0x180002916  mov     r14d, r8d
0x180002919  mov     rsi, rcx
0x18000291c  mov     [r12], r10d
0x180002920  mov     [r13+0], r10d
0x180002924  cmp     ebx, 0Ah
0x180002927  ja      loc_180002D8C
0x18000292d  mov     [rsp+88h+var_38], rdi
0x180002932  movsxd  rdi, [rsp+88h+output_buffer_size]
0x18000293a  mov     [rcx+28h], r9
0x18000293e  lea     rax, [r9+rdi]
0x180002942  mov     [rcx+30h], rax
0x180002946  add     rax, 0FFFFFFFFFFFFFFF0h
0x18000294a  mov     [rcx+38h], rax
0x18000294e  cmp     [rcx+50h], r10
0x180002952  jnz     short loc_1800029A6
0x180002954  cmp     [rcx+58h], r10
0x180002958  jnz     short loc_1800029A6
0x18000295a  cmp     [rcx+60h], r10
0x18000295e  jnz     short loc_1800029A6
0x180002960  cmp     ebx, 3
0x180002963  jg      short loc_180002978
0x180002965  call    FastEncoderInit
0x18000296a  test    eax, eax
0x18000296c  jnz     short loc_1800029A3
0x18000296e  mov     eax, 8007000Eh
0x180002973  jmp     loc_180002A3C
0x180002978  cmp     ebx, 0Ah
0x18000297b  jnz     short loc_1800029EF
0x18000297d  mov     rcx, cs:g_hHeap; hHeap
0x180002984  xor     edx, edx; dwFlags
0x180002986  mov     r8d, 87A88h; dwBytes
0x18000298c  call    cs:__imp_HeapAlloc
0x180002992  mov     [rsi+58h], rax
0x180002996  test    rax, rax
0x180002999  jz      short loc_1800029F8
0x18000299b  mov     rcx, rsi
0x18000299e  call    OptimalEncoderReset
0x1800029a3  xor     r10d, r10d
0x1800029a6  mov     rax, [rsi+50h]
0x1800029aa  lea     r9, cs:180000000h
0x1800029b1  mov     [rsp+88h+arg_10], rbp
0x1800029b9  mov     rbp, [rsi+60h]
0x1800029bd  mov     [rsp+88h+var_40], rax
0x1800029c2  test    rbp, rbp
0x1800029c5  jz      short loc_1800029FF
0x1800029c7  mov     rax, rbx
0x1800029ca  add     rax, rax
0x1800029cd  mov     ecx, ds:rva dword_18000787C[r9+rax*8]
0x1800029d5  mov     edx, ds:rva dword_180007870[r9+rax*8]
0x1800029dd  mov     r8d, ds:rva dword_180007878[r9+rax*8]
0x1800029e5  mov     eax, ds:rva dword_180007874[r9+rax*8]
0x1800029ed  jmp     short loc_180002A10
0x1800029ef  call    StdEncoderInit
0x1800029f4  test    eax, eax
0x1800029f6  jnz     short loc_1800029A3
0x1800029f8  mov     eax, 8007000Eh
0x1800029fd  jmp     short loc_180002A3C
0x1800029ff  test    rax, rax
0x180002a02  jnz     short loc_1800029C7
0x180002a04  mov     eax, r10d
0x180002a07  mov     edx, r10d
0x180002a0a  mov     r8d, r10d
0x180002a0d  mov     ecx, r10d
0x180002a10  mov     [rsp+88h+compression_level], eax
0x180002a17  mov     [rsp+88h+var_58], edx
0x180002a1b  mov     [rsp+88h+var_54], r8d
0x180002a20  mov     [rsp+88h+arg_0], ecx
0x180002a27  cmp     edi, 200h
0x180002a2d  jge     short loc_180002A50
0x180002a2f  mov     eax, 80070057h
0x180002a34  mov     rbp, [rsp+88h+arg_10]
0x180002a3c  mov     rdi, [rsp+88h+var_38]
0x180002a41  add     rsp, 58h
0x180002a45  pop     r15
0x180002a47  pop     r14
0x180002a49  pop     r13
0x180002a4b  pop     r12
0x180002a4d  pop     rsi
0x180002a4e  pop     rbx
0x180002a4f  retn
0x180002a50  cmp     dword ptr [rsi+74h], 0
0x180002a54  mov     r11, [rsi+58h]
0x180002a58  mov     [rsp+88h+var_48], r11
0x180002a5d  mov     [rsp+88h+var_50], r10d
0x180002a62  jz      short loc_180002ABC
0x180002a64  cmp     dword ptr [rsi+78h], 0
0x180002a68  jnz     short loc_180002ABC
0x180002a6a  mov     rax, [rsi+28h]
0x180002a6e  cmp     ebx, 0Ah
0x180002a71  mov     dword ptr [rax+1], 88Bh
0x180002a78  mov     r9d, 4
0x180002a7e  mov     word ptr [rax+5], 0
0x180002a84  mov     byte ptr [rax+7], 0
0x180002a88  lea     rcx, [rax+1]
0x180002a8c  mov     byte ptr [rax], 1Fh
0x180002a8f  mov     eax, 2
0x180002a94  cmovnz  eax, r9d
0x180002a98  mov     [rcx+7], al
0x180002a9b  lea     rax, [rcx+9]
0x180002a9f  mov     byte ptr [rcx+8], 0
0x180002aa3  mov     ecx, [rsp+88h+arg_0]
0x180002aaa  mov     [rsi+28h], rax
0x180002aae  mov     eax, [rsp+88h+compression_level]
0x180002ab5  mov     dword ptr [rsi+78h], 1
0x180002abc  cmp     dword ptr [rsi], 0
0x180002abf  jz      short loc_180002B06
0x180002ac1  test    rbp, rbp
0x180002ac4  jnz     loc_180002BE6
0x180002aca  mov     rcx, rsi
0x180002acd  call    OutputBlock
0x180002ad2  cmp     [rsi], ebp
0x180002ad4  jnz     short loc_180002AF7
0x180002ad6  mov     rcx, [rsi+28h]
0x180002ada  mov     rax, [rsi+30h]
0x180002ade  sub     rax, rcx
0x180002ae1  cmp     rax, 200h
0x180002ae7  jl      short loc_180002AFA
0x180002ae9  mov     r11, [rsp+88h+var_48]
0x180002aee  mov     eax, [rsp+88h+compression_level]
0x180002af5  jmp     short loc_180002B0A
0x180002af7  mov     ecx, [rsi+28h]
0x180002afa  sub     ecx, r15d
0x180002afd  mov     [r13+0], ecx
0x180002b01  jmp     loc_180002D79
0x180002b06  mov     rcx, [rsi+28h]
0x180002b0a  mov     rdx, rcx
0x180002b0d  test    r14d, r14d
0x180002b10  jz      short loc_180002B1D
0x180002b12  cmp     dword ptr [rsi+68h], 0
0x180002b16  jnz     short loc_180002B20
0x180002b18  jmp     loc_180002BD6
0x180002b1d  mov     rdx, rcx
0x180002b20  mov     eax, [rsi+24h]
0x180002b23  cmp     [rsi+20h], eax
0x180002b26  jl      loc_180002BCF
0x180002b2c  cmp     dword ptr [rsi+1Ch], 0
0x180002b30  mov     dword ptr [rsi+68h], 1
0x180002b37  jz      short loc_180002B56
0x180002b39  mov     rcx, rsi
0x180002b3c  call    FlushRecordingBuffer
0x180002b41  mov     rcx, rsi
0x180002b44  call    OutputBlock
0x180002b49  cmp     dword ptr [rsi], 0
0x180002b4c  jnz     loc_180002D79
0x180002b52  mov     rdx, [rsi+28h]
0x180002b56  test    rbp, rbp
0x180002b59  jz      short loc_180002BA2
0x180002b5b  cmp     dword ptr [rbp+930Ch], 0
0x180002b62  jnz     short loc_180002BA2
0x180002b64  movsxd  rbx, cs:g_FastEncoderTreeLength
0x180002b6b  lea     rdx, g_FastEncoderTreeStructureData; Src
0x180002b72  mov     dword ptr [rbp+930Ch], 1
0x180002b7c  mov     r8, rbx; Size
0x180002b7f  mov     rcx, [rsi+28h]; void *
0x180002b83  call    memcpy_0
0x180002b88  mov     eax, cs:g_FastEncoderPostTreeBitbuf
0x180002b8e  add     [rsi+28h], rbx
0x180002b92  mov     rdx, [rsi+28h]
0x180002b96  mov     [rsi+40h], eax
0x180002b99  mov     eax, cs:g_FastEncoderPostTreeBitcount
0x180002b9f  mov     [rsi+44h], eax
0x180002ba2  cmp     dword ptr [rsi+6Ch], 0
0x180002ba6  jnz     short loc_180002BC5
0x180002ba8  lea     rax, [rdx+8]
0x180002bac  cmp     rax, [rsi+30h]
0x180002bb0  jnb     loc_180002D79
0x180002bb6  mov     rcx, rsi
0x180002bb9  call    markFinalBlock
0x180002bbe  mov     dword ptr [rsi+6Ch], 1
0x180002bc5  mov     eax, 1
0x180002bca  jmp     loc_180002D7D
0x180002bcf  mov     eax, [rsp+88h+compression_level]
0x180002bd6  mov     r8d, [rsp+88h+var_54]
0x180002bdb  mov     edx, [rsp+88h+var_58]
0x180002bdf  mov     ecx, [rsp+88h+arg_0]
0x180002be6  mov     r13, [rsp+88h+Src]
0x180002bee  mov     r15, [rsp+88h+var_40]
0x180002bf3  test    r14d, r14d
0x180002bf6  jg      short loc_180002C0B
0x180002bf8  mov     eax, [rsi+24h]
0x180002bfb  cmp     [rsi+20h], eax
0x180002bfe  jge     loc_180002D69
0x180002c04  mov     eax, [rsp+88h+compression_level]
0x180002c0b  mov     edi, [rsi+48h]
0x180002c0e  add     edi, edi
0x180002c10  sub     edi, [rsi+24h]
0x180002c13  cmp     r14d, edi
0x180002c16  cmovl   edi, r14d
0x180002c1a  test    edi, edi
0x180002c1c  jle     loc_180002CDE
0x180002c22  add     [r12], edi
0x180002c26  mov     rcx, rsi
0x180002c29  cmp     dword ptr [rsi+74h], 0
0x180002c2d  jz      short loc_180002C9F
0x180002c2f  mov     r10d, edi
0x180002c32  mov     r8, r13
0x180002c35  call    GetEncoderWindow
0x180002c3a  movsxd  r9, dword ptr [rsi+24h]
0x180002c3e  lea     r12, cs:180000000h
0x180002c45  mov     ecx, [rsi+7Ch]
0x180002c48  add     r9, rax
0x180002c4b  add     [rsi+80h], edi
0x180002c51  not     ecx
0x180002c53  nop     dword ptr [rax+00h]
0x180002c57  nop     word ptr [rax+rax+00000000h]
0x180002c60  movzx   eax, byte ptr [r8]
0x180002c64  lea     r8, [r8+1]
0x180002c68  mov     [r9], al
0x180002c6b  lea     r9, [r9+1]
0x180002c6f  movzx   edx, byte ptr [r8-1]
0x180002c74  mov     eax, ecx
0x180002c76  xor     rdx, rax
0x180002c79  shr     ecx, 8
0x180002c7c  movzx   eax, dl
0x180002c7f  xor     ecx, ds:rva g_CrcTable[r12+rax*4]
0x180002c87  add     r10d, 0FFFFFFFFh
0x180002c8b  jnz     short loc_180002C60
0x180002c8d  mov     r12, [rsp+88h+input_used]
0x180002c95  not     ecx
0x180002c97  mov     [rsi+7Ch], ecx
0x180002c9a  movsxd  rbx, edi
0x180002c9d  jmp     short loc_180002CBE
0x180002c9f  movsxd  rbx, edi
0x180002ca2  call    GetEncoderWindow
0x180002ca7  movsxd  rcx, dword ptr [rsi+24h]
0x180002cab  mov     r8, rbx; Size
0x180002cae  add     rcx, rax; void *
0x180002cb1  mov     rdx, r13; Src
0x180002cb4  call    memcpy_0
0x180002cb9  mov     r11, [rsp+88h+var_48]
0x180002cbe  mov     ecx, [rsp+88h+arg_0]
0x180002cc5  add     r13, rbx
0x180002cc8  mov     edx, [rsp+88h+var_58]
0x180002ccc  sub     r14d, edi
0x180002ccf  add     [rsi+24h], edi
0x180002cd2  mov     r8d, [rsp+88h+var_54]
0x180002cd7  mov     eax, [rsp+88h+compression_level]
0x180002cde  test    r11, r11
0x180002ce1  jz      short loc_180002CED
0x180002ce3  mov     rcx, rsi
0x180002ce6  call    OptimalEncoderDeflate
0x180002ceb  jmp     short loc_180002D23
0x180002ced  test    r15, r15
0x180002cf0  jz      short loc_180002D09
0x180002cf2  mov     r9d, edx
0x180002cf5  mov     [rsp+88h+var_68], r8d
0x180002cfa  mov     edx, ecx
0x180002cfc  mov     r8d, eax
0x180002cff  mov     rcx, rsi
0x180002d02  call    StdEncoderDeflate
0x180002d07  jmp     short loc_180002D23
0x180002d09  test    rbp, rbp
0x180002d0c  jz      short loc_180002D28
0x180002d0e  mov     r9d, edx
0x180002d11  mov     [rsp+88h+var_68], r8d
0x180002d16  mov     edx, ecx
0x180002d18  mov     r8d, eax
0x180002d1b  mov     rcx, rsi
0x180002d1e  call    FastEncoderDeflate
0x180002d23  mov     r11, [rsp+88h+var_48]
0x180002d28  cmp     dword ptr [rsi], 0
0x180002d2b  jnz     short loc_180002D69
0x180002d2d  mov     ecx, [rsp+88h+arg_0]
0x180002d34  mov     edx, [rsp+88h+var_58]
0x180002d38  mov     r8d, [rsp+88h+var_54]
0x180002d3d  mov     eax, [rsp+88h+compression_level]
0x180002d44  test    rbp, rbp
0x180002d47  jnz     loc_180002BF3
0x180002d4d  mov     rcx, [rsi+30h]
0x180002d51  sub     rcx, [rsi+28h]
0x180002d55  cmp     rcx, 200h
0x180002d5c  mov     ecx, [rsp+88h+arg_0]
0x180002d63  jl      loc_180002BF3
0x180002d69  mov     r15, [rsp+88h+arg_18]
0x180002d71  mov     r13, [rsp+88h+output_used]
0x180002d79  mov     eax, [rsp+88h+var_50]
0x180002d7d  mov     ecx, [rsi+28h]
0x180002d80  sub     ecx, r15d
0x180002d83  mov     [r13+0], ecx
0x180002d87  jmp     loc_180002A34
0x180002d8c  mov     eax, 80070057h
0x180002d91  jmp     loc_180002A41
```
