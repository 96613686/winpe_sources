# read_metadata_picture_

- ea: `0x18000a490`
- end: `0x18000a75b`
- name: `read_metadata_picture_`
- size: `715`
- prototype: `_BOOL8 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800099d0`

## callees

- `0x18000a490`
- `0x180011660`
- `0x180011670`
- `0x1800116a0`
- `0x180011950`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a54f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a5fb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a701`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a54f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a5fb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a701`

## pseudocode

```c
_BOOL8 __fastcall read_metadata_picture_(__int64 a1, __int64 a2)
{
  unsigned int v4; // edx
  unsigned int v5; // eax
  size_t v7; // rcx
  void *v8; // rax
  void *v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // eax
  size_t v12; // rcx
  void *v13; // rax
  void *v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rdx
  size_t v18; // rcx
  void *v19; // rax
  __int64 v20; // r8
  unsigned int v21; // [rsp+30h] [rbp+8h] BYREF

  if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(__int64 **)(*(_QWORD *)(a1 + 8) + 88LL),
                        &v21,
                        FLAC__STREAM_METADATA_PICTURE_TYPE_LEN) )
    return 0;
  v4 = 0;
  if ( v21 < 0x15 )
    v4 = v21;
  *(_DWORD *)a2 = v4;
  if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(__int64 **)(*(_QWORD *)(a1 + 8) + 88LL),
                        &v21,
                        FLAC__STREAM_METADATA_PICTURE_MIME_TYPE_LENGTH_LEN) )
    return 0;
  v5 = FLAC__bitreader_limit_remaining(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL));
  if ( v5 < v21 )
    goto LABEL_6;
  v7 = v21 + 1LL;
  if ( v7 < v21 )
  {
    *(_QWORD *)(a2 + 8) = 0;
    **(_DWORD **)a1 = 8;
    return 0;
  }
  v8 = malloc(v7);
  *(_QWORD *)(a2 + 8) = v8;
  v9 = v8;
  if ( !v8 )
    goto LABEL_11;
  v10 = v21;
  if ( v21 )
  {
    if ( !(unsigned int)FLAC__bitreader_read_byte_block_aligned_no_crc(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL), v9, v21) )
      return 0;
    v10 = v21;
  }
  *(_BYTE *)(v10 + *(_QWORD *)(a2 + 8)) = 0;
  if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(__int64 **)(*(_QWORD *)(a1 + 8) + 88LL),
                        &v21,
                        FLAC__STREAM_METADATA_PICTURE_DESCRIPTION_LENGTH_LEN) )
    return 0;
  v11 = FLAC__bitreader_limit_remaining(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL));
  if ( v11 < v21 )
  {
LABEL_6:
    FLAC__bitreader_limit_invalidate(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL));
    return 0;
  }
  v12 = v21 + 1LL;
  if ( v12 < v21 )
  {
    *(_QWORD *)(a2 + 16) = 0;
LABEL_11:
    **(_DWORD **)a1 = 8;
    return 0;
  }
  v13 = malloc(v12);
  *(_QWORD *)(a2 + 16) = v13;
  v14 = v13;
  if ( !v13 )
    goto LABEL_11;
  v15 = v21;
  if ( v21 )
  {
    if ( !(unsigned int)FLAC__bitreader_read_byte_block_aligned_no_crc(
                          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                          v14,
                          v21) )
      return 0;
    v15 = v21;
  }
  *(_BYTE *)(v15 + *(_QWORD *)(a2 + 16)) = 0;
  if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(__int64 **)(*(_QWORD *)(a1 + 8) + 88LL),
                        (_DWORD *)(a2 + 24),
                        FLAC__STREAM_METADATA_PICTURE_WIDTH_LEN)
    || !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(__int64 **)(*(_QWORD *)(a1 + 8) + 88LL),
                        (_DWORD *)(a2 + 28),
                        FLAC__STREAM_METADATA_PICTURE_HEIGHT_LEN)
    || !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(__int64 **)(*(_QWORD *)(a1 + 8) + 88LL),
                        (_DWORD *)(a2 + 32),
                        FLAC__STREAM_METADATA_PICTURE_DEPTH_LEN)
    || !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(__int64 **)(*(_QWORD *)(a1 + 8) + 88LL),
                        (_DWORD *)(a2 + 36),
                        FLAC__STREAM_METADATA_PICTURE_COLORS_LEN)
    || !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(__int64 **)(*(_QWORD *)(a1 + 8) + 88LL),
                        (_DWORD *)(a2 + 40),
                        FLAC__STREAM_METADATA_PICTURE_DATA_LENGTH_LEN) )
  {
    return 0;
  }
  v16 = FLAC__bitreader_limit_remaining(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL));
  v17 = *(unsigned int *)(a2 + 40);
  if ( v16 < (unsigned int)v17 )
    goto LABEL_6;
  v18 = v17 + 1;
  if ( (_DWORD)v17 )
    v18 = *(unsigned int *)(a2 + 40);
  v19 = malloc(v18);
  *(_QWORD *)(a2 + 48) = v19;
  if ( !v19 )
    goto LABEL_11;
  v20 = *(unsigned int *)(a2 + 40);
  return !(_DWORD)v20
      || (unsigned int)FLAC__bitreader_read_byte_block_aligned_no_crc(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL), v19, v20) != 0;
}

```

## disassembly

```asm
0x18000a490  mov     [rsp+arg_8], rbx
0x18000a495  mov     [rsp+arg_10], rsi
0x18000a49a  push    rdi
0x18000a49b  sub     rsp, 20h
0x18000a49f  mov     r8d, cs:FLAC__STREAM_METADATA_PICTURE_TYPE_LEN
0x18000a4a6  mov     rbx, rcx
0x18000a4a9  mov     rcx, [rcx+8]
0x18000a4ad  mov     rdi, rdx
0x18000a4b0  lea     rdx, [rsp+28h+arg_0]
0x18000a4b5  mov     rcx, [rcx+58h]
0x18000a4b9  call    FLAC__bitreader_read_raw_uint32
0x18000a4be  test    eax, eax
0x18000a4c0  jz      short loc_18000A50F
0x18000a4c2  xor     edx, edx
0x18000a4c4  cmp     [rsp+28h+arg_0], 15h
0x18000a4c9  cmovb   edx, [rsp+28h+arg_0]
0x18000a4ce  mov     [rdi], edx
0x18000a4d0  lea     rdx, [rsp+28h+arg_0]
0x18000a4d5  mov     rcx, [rbx+8]
0x18000a4d9  mov     r8d, cs:FLAC__STREAM_METADATA_PICTURE_MIME_TYPE_LENGTH_LEN
0x18000a4e0  mov     rcx, [rcx+58h]
0x18000a4e4  call    FLAC__bitreader_read_raw_uint32
0x18000a4e9  test    eax, eax
0x18000a4eb  jz      short loc_18000A50F
0x18000a4ed  mov     rcx, [rbx+8]
0x18000a4f1  mov     rcx, [rcx+58h]
0x18000a4f5  call    FLAC__bitreader_limit_remaining
0x18000a4fa  mov     ecx, [rsp+28h+arg_0]
0x18000a4fe  cmp     eax, ecx
0x18000a500  jnb     short loc_18000A521
0x18000a502  mov     rcx, [rbx+8]
0x18000a506  mov     rcx, [rcx+58h]
0x18000a50a  call    FLAC__bitreader_limit_invalidate
0x18000a50f  xor     eax, eax
0x18000a511  mov     rbx, [rsp+28h+arg_8]
0x18000a516  mov     rsi, [rsp+28h+arg_10]
0x18000a51b  add     rsp, 20h
0x18000a51f  pop     rdi
0x18000a520  retn
0x18000a521  mov     rax, rcx
0x18000a524  inc     rcx; Size
0x18000a527  cmp     rcx, rax
0x18000a52a  jnb     short loc_18000A54F
0x18000a52c  mov     qword ptr [rdi+8], 0
0x18000a534  mov     rax, [rbx]
0x18000a537  mov     dword ptr [rax], 8
0x18000a53d  xor     eax, eax
0x18000a53f  mov     rbx, [rsp+28h+arg_8]
0x18000a544  mov     rsi, [rsp+28h+arg_10]
0x18000a549  add     rsp, 20h
0x18000a54d  pop     rdi
0x18000a54e  retn
0x18000a54f  call    cs:__imp_malloc
0x18000a555  mov     [rdi+8], rax
0x18000a559  mov     rdx, rax
0x18000a55c  test    rax, rax
0x18000a55f  jnz     short loc_18000A57C
0x18000a561  mov     rax, [rbx]
0x18000a564  mov     dword ptr [rax], 8
0x18000a56a  xor     eax, eax
0x18000a56c  mov     rbx, [rsp+28h+arg_8]
0x18000a571  mov     rsi, [rsp+28h+arg_10]
0x18000a576  add     rsp, 20h
0x18000a57a  pop     rdi
0x18000a57b  retn
0x18000a57c  mov     eax, [rsp+28h+arg_0]
0x18000a580  test    eax, eax
0x18000a582  jz      short loc_18000A5A0
0x18000a584  mov     rcx, [rbx+8]
0x18000a588  mov     r8d, eax
0x18000a58b  mov     rcx, [rcx+58h]
0x18000a58f  call    FLAC__bitreader_read_byte_block_aligned_no_crc
0x18000a594  test    eax, eax
0x18000a596  jz      loc_18000A50F
0x18000a59c  mov     eax, [rsp+28h+arg_0]
0x18000a5a0  mov     ecx, eax
0x18000a5a2  lea     rdx, [rsp+28h+arg_0]
0x18000a5a7  mov     rax, [rdi+8]
0x18000a5ab  mov     byte ptr [rcx+rax], 0
0x18000a5af  mov     rcx, [rbx+8]
0x18000a5b3  mov     r8d, cs:FLAC__STREAM_METADATA_PICTURE_DESCRIPTION_LENGTH_LEN
0x18000a5ba  mov     rcx, [rcx+58h]
0x18000a5be  call    FLAC__bitreader_read_raw_uint32
0x18000a5c3  test    eax, eax
0x18000a5c5  jz      loc_18000A50F
0x18000a5cb  mov     rcx, [rbx+8]
0x18000a5cf  mov     rcx, [rcx+58h]
0x18000a5d3  call    FLAC__bitreader_limit_remaining
0x18000a5d8  mov     ecx, [rsp+28h+arg_0]
0x18000a5dc  cmp     eax, ecx
0x18000a5de  jb      loc_18000A502
0x18000a5e4  mov     eax, ecx
0x18000a5e6  inc     rcx; Size
0x18000a5e9  cmp     rcx, rax
0x18000a5ec  jnb     short loc_18000A5FB
0x18000a5ee  mov     qword ptr [rdi+10h], 0
0x18000a5f6  jmp     loc_18000A561
0x18000a5fb  call    cs:__imp_malloc
0x18000a601  mov     [rdi+10h], rax
0x18000a605  mov     rdx, rax
0x18000a608  test    rax, rax
0x18000a60b  jz      loc_18000A561
0x18000a611  mov     eax, [rsp+28h+arg_0]
0x18000a615  test    eax, eax
0x18000a617  jz      short loc_18000A635
0x18000a619  mov     rcx, [rbx+8]
0x18000a61d  mov     r8d, eax
0x18000a620  mov     rcx, [rcx+58h]
0x18000a624  call    FLAC__bitreader_read_byte_block_aligned_no_crc
0x18000a629  test    eax, eax
0x18000a62b  jz      loc_18000A50F
0x18000a631  mov     eax, [rsp+28h+arg_0]
0x18000a635  mov     ecx, eax
0x18000a637  lea     rdx, [rdi+18h]
0x18000a63b  mov     rax, [rdi+10h]
0x18000a63f  mov     byte ptr [rcx+rax], 0
0x18000a643  mov     rcx, [rbx+8]
0x18000a647  mov     r8d, cs:FLAC__STREAM_METADATA_PICTURE_WIDTH_LEN
0x18000a64e  mov     rcx, [rcx+58h]
0x18000a652  call    FLAC__bitreader_read_raw_uint32
0x18000a657  test    eax, eax
0x18000a659  jz      loc_18000A50F
0x18000a65f  mov     rcx, [rbx+8]
0x18000a663  lea     rdx, [rdi+1Ch]
0x18000a667  mov     r8d, cs:FLAC__STREAM_METADATA_PICTURE_HEIGHT_LEN
0x18000a66e  mov     rcx, [rcx+58h]
0x18000a672  call    FLAC__bitreader_read_raw_uint32
0x18000a677  test    eax, eax
0x18000a679  jz      loc_18000A50F
0x18000a67f  mov     rcx, [rbx+8]
0x18000a683  lea     rdx, [rdi+20h]
0x18000a687  mov     r8d, cs:FLAC__STREAM_METADATA_PICTURE_DEPTH_LEN
0x18000a68e  mov     rcx, [rcx+58h]
0x18000a692  call    FLAC__bitreader_read_raw_uint32
0x18000a697  test    eax, eax
0x18000a699  jz      loc_18000A50F
0x18000a69f  mov     rcx, [rbx+8]
0x18000a6a3  lea     rdx, [rdi+24h]
0x18000a6a7  mov     r8d, cs:FLAC__STREAM_METADATA_PICTURE_COLORS_LEN
0x18000a6ae  mov     rcx, [rcx+58h]
0x18000a6b2  call    FLAC__bitreader_read_raw_uint32
0x18000a6b7  test    eax, eax
0x18000a6b9  jz      loc_18000A50F
0x18000a6bf  mov     rcx, [rbx+8]
0x18000a6c3  lea     rdx, [rdi+28h]
0x18000a6c7  mov     r8d, cs:FLAC__STREAM_METADATA_PICTURE_DATA_LENGTH_LEN
0x18000a6ce  mov     rcx, [rcx+58h]
0x18000a6d2  call    FLAC__bitreader_read_raw_uint32
0x18000a6d7  test    eax, eax
0x18000a6d9  jz      loc_18000A50F
0x18000a6df  mov     rcx, [rbx+8]
0x18000a6e3  mov     rcx, [rcx+58h]
0x18000a6e7  call    FLAC__bitreader_limit_remaining
0x18000a6ec  mov     edx, [rdi+28h]
0x18000a6ef  cmp     eax, edx
0x18000a6f1  jb      loc_18000A502
0x18000a6f7  test    edx, edx
0x18000a6f9  lea     rcx, [rdx+1]
0x18000a6fd  cmovnz  rcx, rdx; Size
0x18000a701  call    cs:__imp_malloc
0x18000a707  mov     [rdi+30h], rax
0x18000a70b  test    rax, rax
0x18000a70e  jz      loc_18000A561
0x18000a714  mov     r8d, [rdi+28h]
0x18000a718  test    r8d, r8d
0x18000a71b  jz      short loc_18000A746
0x18000a71d  mov     rcx, [rbx+8]
0x18000a721  mov     rdx, rax
0x18000a724  mov     rcx, [rcx+58h]
0x18000a728  call    FLAC__bitreader_read_byte_block_aligned_no_crc
0x18000a72d  xor     ecx, ecx
0x18000a72f  test    eax, eax
0x18000a731  setnz   cl
0x18000a734  mov     eax, ecx
0x18000a736  mov     rbx, [rsp+28h+arg_8]
0x18000a73b  mov     rsi, [rsp+28h+arg_10]
0x18000a740  add     rsp, 20h
0x18000a744  pop     rdi
0x18000a745  retn
0x18000a746  mov     rbx, [rsp+28h+arg_8]
0x18000a74b  mov     eax, 1
0x18000a750  mov     rsi, [rsp+28h+arg_10]
0x18000a755  add     rsp, 20h
0x18000a759  pop     rdi
0x18000a75a  retn
```
