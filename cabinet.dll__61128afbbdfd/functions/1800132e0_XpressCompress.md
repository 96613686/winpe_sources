# XpressCompress

- ea: `0x1800132e0`
- end: `0x1800133ae`
- name: `XpressCompress`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800132e0`
- `0x18001b625`

## import_xrefs

- `ntdll!RtlCompressBuffer` at `0x180013353`
- `ntdll!RtlCompressBuffer` at `0x180013353`

## pseudocode

```c
__int64 __fastcall XpressCompress(__int64 a1, UCHAR *a2, size_t a3, UCHAR *a4, unsigned __int64 a5, __int64 *a6)
{
  __int64 v7; // r8
  __int16 v11; // cx
  ULONG CompressedBufferSize; // edx
  __int64 result; // rax
  ULONG v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = 0;
  v7 = 0x40000000;
  if ( a3 > 0x40000000 )
  {
    result = 111;
    goto LABEL_8;
  }
  if ( !a5 )
  {
    result = 122;
    v7 = a3;
    goto LABEL_8;
  }
  v11 = *(_WORD *)(a1 + 2);
  CompressedBufferSize = a3 - 1;
  if ( a5 < a3 - 1 )
    CompressedBufferSize = a5;
  if ( !RtlCompressBuffer(*(_WORD *)a1 | v11, a2, a3, a4, CompressedBufferSize, 0, &v14, *(PVOID *)(a1 + 32)) )
  {
    v7 = v14;
LABEL_10:
    result = 0;
    goto LABEL_8;
  }
  v7 = a3;
  if ( a5 >= a3 )
  {
    memcpy_0(a4, a2, a3);
    v7 = a3;
    goto LABEL_10;
  }
  result = 122;
LABEL_8:
  *a6 = v7;
  return result;
}

```

## disassembly

```asm
0x1800132e0  mov     r11, rsp
0x1800132e3  mov     [r11+10h], rbx
0x1800132e7  mov     [r11+18h], rbp
0x1800132eb  push    rsi
0x1800132ec  sub     rsp, 40h
0x1800132f0  mov     rbx, r8
0x1800132f3  mov     [rsp+48h+arg_0], 0
0x1800132fb  mov     r8d, 40000000h
0x180013301  mov     rsi, r9
0x180013304  mov     rbp, rdx
0x180013307  mov     rax, rcx
0x18001330a  cmp     rbx, r8
0x18001330d  ja      loc_180013397
0x180013313  cmp     [rsp+48h+arg_20], 0
0x180013319  jz      short loc_18001338D
0x18001331b  movzx   ecx, word ptr [rcx+2]
0x18001331f  lea     rdx, [rbx-1]
0x180013323  cmp     [rsp+48h+arg_20], rdx
0x180013328  mov     r8d, ebx; UncompressedBufferSize
0x18001332b  cmovb   rdx, [rsp+48h+arg_20]
0x180013331  or      cx, [rax]; CompressionFormatAndEngine
0x180013334  mov     rax, [rax+20h]
0x180013338  mov     [r11-10h], rax
0x18001333c  lea     rax, [r11+8]
0x180013340  mov     [r11-18h], rax
0x180013344  mov     [rsp+48h+UncompressedChunkSize], 0; UncompressedChunkSize
0x18001334c  mov     [rsp+48h+CompressedBufferSize], edx; CompressedBufferSize
0x180013350  mov     rdx, rbp; UncompressedBuffer
0x180013353  call    cs:__imp_RtlCompressBuffer
0x180013359  test    eax, eax
0x18001335b  jz      short loc_180013384
0x18001335d  mov     r8, rbx; Size
0x180013360  cmp     [rsp+48h+arg_20], rbx
0x180013365  jnb     short loc_18001339E
0x180013367  mov     eax, 7Ah ; 'z'
0x18001336c  mov     rcx, [rsp+48h+arg_28]
0x180013371  mov     [rcx], r8
0x180013374  mov     rbx, [rsp+48h+arg_8]
0x180013379  mov     rbp, [rsp+48h+arg_10]
0x18001337e  add     rsp, 40h
0x180013382  pop     rsi
0x180013383  retn
0x180013384  mov     r8d, [rsp+48h+arg_0]
0x180013389  xor     eax, eax
0x18001338b  jmp     short loc_18001336C
0x18001338d  mov     eax, 7Ah ; 'z'
0x180013392  mov     r8, rbx
0x180013395  jmp     short loc_18001336C
0x180013397  mov     eax, 6Fh ; 'o'
0x18001339c  jmp     short loc_18001336C
0x18001339e  mov     rdx, rbp; Src
0x1800133a1  mov     rcx, rsi; void *
0x1800133a4  call    memcpy_0
0x1800133a9  mov     r8, rbx
0x1800133ac  jmp     short loc_180013389
```
