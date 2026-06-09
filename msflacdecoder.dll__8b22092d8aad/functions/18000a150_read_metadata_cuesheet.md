# read_metadata_cuesheet_

- ea: `0x18000a150`
- end: `0x18000a489`
- name: `read_metadata_cuesheet_`
- size: `825`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800099d0`

## callees

- `0x1800028ac`
- `0x18000a150`
- `0x180011660`
- `0x1800116a0`
- `0x180011950`
- `0x180011b50`
- `0x1800123b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000a240`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000a3bb`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000a240`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000a3bb`

## pseudocode

```c
__int64 __fastcall read_metadata_cuesheet_(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  void *v5; // rax
  __int64 v7; // r14
  __int64 v8; // rsi
  void *v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // rbp
  size_t Count; // [rsp+60h] [rbp+8h] BYREF

  memset_0((void *)a2, 0, 0xA0u);
  if ( (unsigned int)FLAC__bitreader_read_byte_block_aligned_no_crc(
                       *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                       a2,
                       (unsigned int)FLAC__STREAM_METADATA_CUESHEET_MEDIA_CATALOG_NUMBER_LEN >> 3) )
  {
    if ( (unsigned int)FLAC__bitreader_read_raw_uint64(
                         *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                         a2 + 136,
                         (unsigned int)FLAC__STREAM_METADATA_CUESHEET_LEAD_IN_LEN) )
    {
      if ( (unsigned int)FLAC__bitreader_read_raw_uint32(
                           *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                           &Count,
                           (unsigned int)FLAC__STREAM_METADATA_CUESHEET_IS_CD_LEN) )
      {
        *(_DWORD *)(a2 + 144) = Count != 0;
        if ( (unsigned int)FLAC__bitreader_skip_bits_no_crc(
                             *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                             (unsigned int)FLAC__STREAM_METADATA_CUESHEET_RESERVED_LEN) )
        {
          if ( (unsigned int)FLAC__bitreader_read_raw_uint32(
                               *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                               &Count,
                               (unsigned int)FLAC__STREAM_METADATA_CUESHEET_NUM_TRACKS_LEN) )
          {
            v4 = Count;
            *(_DWORD *)(a2 + 148) = Count;
            if ( v4 )
            {
              v5 = calloc(v4, 0x28u);
              *(_QWORD *)(a2 + 152) = v5;
              if ( !v5 )
              {
LABEL_8:
                **(_DWORD **)a1 = 8;
                return 0;
              }
              v7 = 0;
              if ( !*(_DWORD *)(a2 + 148) )
                return 1;
              while ( 1 )
              {
                v8 = *(_QWORD *)(a2 + 152) + 40 * v7;
                if ( !(unsigned int)FLAC__bitreader_read_raw_uint64(
                                      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                      v8,
                                      (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_OFFSET_LEN) )
                  break;
                if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                                      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                      &Count,
                                      (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_NUMBER_LEN) )
                  break;
                *(_BYTE *)(v8 + 8) = Count;
                if ( !(unsigned int)FLAC__bitreader_read_byte_block_aligned_no_crc(
                                      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                      v8 + 9,
                                      (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_ISRC_LEN >> 3) )
                  break;
                if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                                      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                      &Count,
                                      (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_TYPE_LEN) )
                  break;
                *(_DWORD *)(v8 + 24) = Count & 1 | *(_DWORD *)(v8 + 24) & 0xFFFFFFFE;
                if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                                      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                      &Count,
                                      (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_PRE_EMPHASIS_LEN) )
                  break;
                *(_DWORD *)(v8 + 24) = *(_DWORD *)(v8 + 24) & 0xFFFFFFFD | (2 * (Count & 1));
                if ( !(unsigned int)FLAC__bitreader_skip_bits_no_crc(
                                      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                      (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_RESERVED_LEN)
                  || !(unsigned int)FLAC__bitreader_read_raw_uint32(
                                      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                      &Count,
                                      (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_NUM_INDICES_LEN) )
                {
                  break;
                }
                *(_BYTE *)(v8 + 28) = Count;
                if ( (_BYTE)Count )
                {
                  v9 = calloc((unsigned __int8)Count, 0x10u);
                  *(_QWORD *)(v8 + 32) = v9;
                  if ( !v9 )
                    goto LABEL_8;
                  v10 = 0;
                  if ( *(_BYTE *)(v8 + 28) )
                  {
                    do
                    {
                      v11 = *(_QWORD *)(v8 + 32) + 16LL * v10;
                      if ( !(unsigned int)FLAC__bitreader_read_raw_uint64(
                                            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                            v11,
                                            (unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_OFFSET_LEN) )
                        return 0;
                      if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                                            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                            &Count,
                                            (unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_NUMBER_LEN) )
                        return 0;
                      *(_BYTE *)(v11 + 8) = Count;
                      if ( !(unsigned int)FLAC__bitreader_skip_bits_no_crc(
                                            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                            (unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_RESERVED_LEN) )
                        return 0;
                    }
                    while ( ++v10 < *(unsigned __int8 *)(v8 + 28) );
                  }
                }
                v7 = (unsigned int)(v7 + 1);
                if ( (unsigned int)v7 >= *(_DWORD *)(a2 + 148) )
                  return 1;
              }
            }
            else
            {
              FLAC__bitreader_limit_invalidate(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL));
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a150  push    rbx
0x18000a152  push    rbp
0x18000a153  push    rsi
0x18000a154  push    rdi
0x18000a155  push    r14
0x18000a157  push    r15
0x18000a159  sub     rsp, 28h
0x18000a15d  mov     r15, rdx
0x18000a160  mov     rdi, rcx
0x18000a163  mov     rcx, r15; void *
0x18000a166  xor     edx, edx; Val
0x18000a168  mov     r8d, 0A0h; Size
0x18000a16e  call    memset_0
0x18000a173  mov     rcx, [rdi+8]
0x18000a177  mov     rdx, r15
0x18000a17a  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_MEDIA_CATALOG_NUMBER_LEN
0x18000a181  shr     r8d, 3
0x18000a185  mov     rcx, [rcx+58h]
0x18000a189  call    FLAC__bitreader_read_byte_block_aligned_no_crc
0x18000a18e  test    eax, eax
0x18000a190  jz      loc_18000A47A
0x18000a196  mov     rcx, [rdi+8]
0x18000a19a  lea     rdx, [r15+88h]
0x18000a1a1  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_LEAD_IN_LEN
0x18000a1a8  mov     rcx, [rcx+58h]
0x18000a1ac  call    FLAC__bitreader_read_raw_uint64
0x18000a1b1  test    eax, eax
0x18000a1b3  jz      loc_18000A47A
0x18000a1b9  mov     rcx, [rdi+8]
0x18000a1bd  lea     rdx, [rsp+58h+Count]
0x18000a1c2  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_IS_CD_LEN
0x18000a1c9  mov     rcx, [rcx+58h]
0x18000a1cd  call    FLAC__bitreader_read_raw_uint32
0x18000a1d2  test    eax, eax
0x18000a1d4  jz      loc_18000A47A
0x18000a1da  xor     eax, eax
0x18000a1dc  cmp     dword ptr [rsp+58h+Count], eax
0x18000a1e0  setnz   al
0x18000a1e3  mov     [r15+90h], eax
0x18000a1ea  mov     rcx, [rdi+8]
0x18000a1ee  mov     edx, cs:FLAC__STREAM_METADATA_CUESHEET_RESERVED_LEN
0x18000a1f4  mov     rcx, [rcx+58h]
0x18000a1f8  call    FLAC__bitreader_skip_bits_no_crc
0x18000a1fd  test    eax, eax
0x18000a1ff  jz      loc_18000A47A
0x18000a205  mov     rcx, [rdi+8]
0x18000a209  lea     rdx, [rsp+58h+Count]
0x18000a20e  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_NUM_TRACKS_LEN
0x18000a215  mov     rcx, [rcx+58h]
0x18000a219  call    FLAC__bitreader_read_raw_uint32
0x18000a21e  test    eax, eax
0x18000a220  jz      loc_18000A47A
0x18000a226  mov     eax, dword ptr [rsp+58h+Count]
0x18000a22a  mov     [r15+94h], eax
0x18000a231  test    eax, eax
0x18000a233  jz      loc_18000A46D
0x18000a239  mov     ecx, eax; Count
0x18000a23b  mov     edx, 28h ; '('; Size
0x18000a240  call    cs:__imp_calloc
0x18000a246  mov     [r15+98h], rax
0x18000a24d  test    rax, rax
0x18000a250  jnz     short loc_18000A26A
0x18000a252  mov     rax, [rdi]
0x18000a255  mov     dword ptr [rax], 8
0x18000a25b  xor     eax, eax
0x18000a25d  add     rsp, 28h
0x18000a261  pop     r15
0x18000a263  pop     r14
0x18000a265  pop     rdi
0x18000a266  pop     rsi
0x18000a267  pop     rbp
0x18000a268  pop     rbx
0x18000a269  retn
0x18000a26a  xor     r14d, r14d
0x18000a26d  cmp     [r15+94h], r14d
0x18000a274  jbe     loc_18000A45B
0x18000a27a  nop     word ptr [rax+rax+00h]
0x18000a280  mov     rax, [r15+98h]
0x18000a287  lea     rcx, [r14+r14*4]
0x18000a28b  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_OFFSET_LEN
0x18000a292  lea     rsi, [rax+rcx*8]
0x18000a296  mov     rcx, [rdi+8]
0x18000a29a  mov     rdx, rsi
0x18000a29d  mov     rcx, [rcx+58h]
0x18000a2a1  call    FLAC__bitreader_read_raw_uint64
0x18000a2a6  test    eax, eax
0x18000a2a8  jz      loc_18000A47A
0x18000a2ae  mov     rcx, [rdi+8]
0x18000a2b2  lea     rdx, [rsp+58h+Count]
0x18000a2b7  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_NUMBER_LEN
0x18000a2be  mov     rcx, [rcx+58h]
0x18000a2c2  call    FLAC__bitreader_read_raw_uint32
0x18000a2c7  test    eax, eax
0x18000a2c9  jz      loc_18000A47A
0x18000a2cf  movzx   eax, byte ptr [rsp+58h+Count]
0x18000a2d4  lea     rdx, [rsi+9]
0x18000a2d8  mov     [rsi+8], al
0x18000a2db  mov     rcx, [rdi+8]
0x18000a2df  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_ISRC_LEN
0x18000a2e6  shr     r8d, 3
0x18000a2ea  mov     rcx, [rcx+58h]
0x18000a2ee  call    FLAC__bitreader_read_byte_block_aligned_no_crc
0x18000a2f3  test    eax, eax
0x18000a2f5  jz      loc_18000A47A
0x18000a2fb  mov     rcx, [rdi+8]
0x18000a2ff  lea     rdx, [rsp+58h+Count]
0x18000a304  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_TYPE_LEN
0x18000a30b  mov     rcx, [rcx+58h]
0x18000a30f  call    FLAC__bitreader_read_raw_uint32
0x18000a314  test    eax, eax
0x18000a316  jz      loc_18000A47A
0x18000a31c  mov     ecx, [rsi+18h]
0x18000a31f  lea     rdx, [rsp+58h+Count]
0x18000a324  mov     eax, dword ptr [rsp+58h+Count]
0x18000a328  and     ecx, 0FFFFFFFEh
0x18000a32b  and     eax, 1
0x18000a32e  or      ecx, eax
0x18000a330  mov     [rsi+18h], ecx
0x18000a333  mov     rcx, [rdi+8]
0x18000a337  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_PRE_EMPHASIS_LEN
0x18000a33e  mov     rcx, [rcx+58h]
0x18000a342  call    FLAC__bitreader_read_raw_uint32
0x18000a347  test    eax, eax
0x18000a349  jz      loc_18000A47A
0x18000a34f  mov     ecx, dword ptr [rsp+58h+Count]
0x18000a353  mov     eax, [rsi+18h]
0x18000a356  and     ecx, 1
0x18000a359  add     ecx, ecx
0x18000a35b  and     eax, 0FFFFFFFDh
0x18000a35e  or      ecx, eax
0x18000a360  mov     [rsi+18h], ecx
0x18000a363  mov     rcx, [rdi+8]
0x18000a367  mov     edx, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_RESERVED_LEN
0x18000a36d  mov     rcx, [rcx+58h]
0x18000a371  call    FLAC__bitreader_skip_bits_no_crc
0x18000a376  test    eax, eax
0x18000a378  jz      loc_18000A47A
0x18000a37e  mov     rcx, [rdi+8]
0x18000a382  lea     rdx, [rsp+58h+Count]
0x18000a387  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_NUM_INDICES_LEN
0x18000a38e  mov     rcx, [rcx+58h]
0x18000a392  call    FLAC__bitreader_read_raw_uint32
0x18000a397  test    eax, eax
0x18000a399  jz      loc_18000A47A
0x18000a39f  movzx   eax, byte ptr [rsp+58h+Count]
0x18000a3a4  mov     [rsi+1Ch], al
0x18000a3a7  movzx   eax, byte ptr [rsp+58h+Count]
0x18000a3ac  test    al, al
0x18000a3ae  jz      loc_18000A44B
0x18000a3b4  mov     ecx, eax; Count
0x18000a3b6  mov     edx, 10h; Size
0x18000a3bb  call    cs:__imp_calloc
0x18000a3c1  mov     [rsi+20h], rax
0x18000a3c5  test    rax, rax
0x18000a3c8  jz      loc_18000A252
0x18000a3ce  xor     ebx, ebx
0x18000a3d0  cmp     [rsi+1Ch], bl
0x18000a3d3  jbe     short loc_18000A44B
0x18000a3d5  nop     word ptr [rax+rax+00000000h]
0x18000a3e0  mov     rcx, [rdi+8]
0x18000a3e4  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_INDEX_OFFSET_LEN
0x18000a3eb  mov     ebp, ebx
0x18000a3ed  shl     rbp, 4
0x18000a3f1  add     rbp, [rsi+20h]
0x18000a3f5  mov     rcx, [rcx+58h]
0x18000a3f9  mov     rdx, rbp
0x18000a3fc  call    FLAC__bitreader_read_raw_uint64
0x18000a401  test    eax, eax
0x18000a403  jz      short loc_18000A47A
0x18000a405  mov     rcx, [rdi+8]
0x18000a409  lea     rdx, [rsp+58h+Count]
0x18000a40e  mov     r8d, cs:FLAC__STREAM_METADATA_CUESHEET_INDEX_NUMBER_LEN
0x18000a415  mov     rcx, [rcx+58h]
0x18000a419  call    FLAC__bitreader_read_raw_uint32
0x18000a41e  test    eax, eax
0x18000a420  jz      short loc_18000A47A
0x18000a422  movzx   eax, byte ptr [rsp+58h+Count]
0x18000a427  mov     [rbp+8], al
0x18000a42a  mov     rcx, [rdi+8]
0x18000a42e  mov     edx, cs:FLAC__STREAM_METADATA_CUESHEET_INDEX_RESERVED_LEN
0x18000a434  mov     rcx, [rcx+58h]
0x18000a438  call    FLAC__bitreader_skip_bits_no_crc
0x18000a43d  test    eax, eax
0x18000a43f  jz      short loc_18000A47A
0x18000a441  movzx   eax, byte ptr [rsi+1Ch]
0x18000a445  inc     ebx
0x18000a447  cmp     ebx, eax
0x18000a449  jb      short loc_18000A3E0
0x18000a44b  inc     r14d
0x18000a44e  cmp     r14d, [r15+94h]
0x18000a455  jb      loc_18000A280
0x18000a45b  mov     eax, 1
0x18000a460  add     rsp, 28h
0x18000a464  pop     r15
0x18000a466  pop     r14
0x18000a468  pop     rdi
0x18000a469  pop     rsi
0x18000a46a  pop     rbp
0x18000a46b  pop     rbx
0x18000a46c  retn
0x18000a46d  mov     rcx, [rdi+8]
0x18000a471  mov     rcx, [rcx+58h]
0x18000a475  call    FLAC__bitreader_limit_invalidate
0x18000a47a  xor     eax, eax
0x18000a47c  add     rsp, 28h
0x18000a480  pop     r15
0x18000a482  pop     r14
0x18000a484  pop     rdi
0x18000a485  pop     rsi
0x18000a486  pop     rbp
0x18000a487  pop     rbx
0x18000a488  retn
```
