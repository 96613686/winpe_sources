# read_metadata_

- ea: `0x1800099d0`
- end: `0x18000a140`
- name: `read_metadata_`
- size: `1904`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800059e0`
- `0x180006d30`
- `0x180006e10`
- `0x180006ee0`
- `0x180006f80`
- `0x180007e50`

## callees

- `0x180001e80`
- `0x1800028ac`
- `0x180006400`
- `0x1800099d0`
- `0x18000a150`
- `0x18000a490`
- `0x18000a770`
- `0x18000a9a0`
- `0x180011660`
- `0x180011670`
- `0x1800116a0`
- `0x180011950`
- `0x180011b50`
- `0x1800122f0`
- `0x180012390`
- `0x180012510`
- `0x180016b18`
- `0x180056010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009bc9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009fe9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a022`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a070`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a099`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a0a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a0bf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009bc9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009fe9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a022`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a070`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a099`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a0a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a0bf`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009e74`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009ef2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009e74`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009ef2`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180009bb3`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180009bd6`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180009bb3`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180009bd6`

## pseudocode

```c
__int64 __fastcall read_metadata_(__int64 a1)
{
  __int64 v2; // rcx
  BOOL v3; // r15d
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // r8
  void (__fastcall *v7)(__int64, __int64, _QWORD); // rax
  __int64 v8; // rsi
  unsigned int v9; // r8d
  __int64 v10; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  void *v14; // r14
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rsi
  __int64 v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rsi
  __int64 v21; // r8
  void (__fastcall *v22)(__int64, __int64, _QWORD); // rax
  unsigned int v23; // r14d
  BOOL v24; // r13d
  unsigned __int64 v25; // r15
  __int64 v26; // rbx
  __int64 v27; // rcx
  bool v28; // zf
  int metadata_picture; // esi
  void *v30; // rax
  __int64 v31; // rax
  __int64 v32; // r8
  void (__fastcall *v33)(__int64, _DWORD *, _QWORD); // rax
  void **v34; // rcx
  unsigned int v35; // r8d
  unsigned int v36; // ebx
  unsigned int v37; // r8d
  void **v38; // rdx
  unsigned int v39; // ebx
  void *v40; // rcx
  BOOL v41; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int Size; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int Size_4; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  int v45; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v46[3]; // [rsp+40h] [rbp-C0h] BYREF
  char v47[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  void **Buf2; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h]
  void *v50; // [rsp+60h] [rbp-A0h]
  void **v51; // [rsp+68h] [rbp-98h]
  void **v52; // [rsp+80h] [rbp-80h]
  unsigned int v53; // [rsp+E4h] [rbp-1Ch]
  void **v54; // [rsp+E8h] [rbp-18h]

  if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                        &v45,
                        (unsigned int)FLAC__STREAM_METADATA_IS_LAST_LEN) )
    return 0;
  v2 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL);
  v3 = v45 != 0;
  v41 = v3;
  if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(v2, &Size_4, (unsigned int)FLAC__STREAM_METADATA_TYPE_LEN)
    || !(unsigned int)FLAC__bitreader_read_raw_uint32(
                        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                        &Size,
                        (unsigned int)FLAC__STREAM_METADATA_LENGTH_LEN) )
  {
    return 0;
  }
  v4 = Size_4;
  if ( !Size_4 )
  {
    if ( (unsigned int)read_metadata_streaminfo_(a1, v3, Size) )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 456LL) = 1;
      v5 = *(_QWORD *)(a1 + 8);
      if ( !*(_QWORD *)(v5 + 520) && !*(_QWORD *)(v5 + 528) )
        *(_DWORD *)(v5 + 5120) = 0;
      v6 = *(_QWORD *)(a1 + 8);
      if ( !*(_DWORD *)(v6 + 5128) )
      {
        if ( *(_DWORD *)(v6 + 816) )
        {
          v7 = *(void (__fastcall **)(__int64, __int64, _QWORD))(v6 + 56);
          if ( v7 )
            v7(a1, v6 + 464, *(_QWORD *)(v6 + 72));
        }
      }
      goto LABEL_98;
    }
    return 0;
  }
  v8 = *(_QWORD *)(a1 + 8);
  if ( Size_4 != 3 )
  {
    v23 = Size;
    LODWORD(v44) = *(_DWORD *)(v8 + 4LL * Size_4 + 816);
    v24 = v44 == 0;
    memset_0(v47, 0, 0xA4u);
    v46[1] = v3;
    v46[0] = v4;
    v46[2] = v23;
    if ( v4 == 2 )
    {
      if ( !(unsigned int)FLAC__bitreader_read_byte_block_aligned_no_crc(
                            *(_QWORD *)(v8 + 88),
                            &Buf2,
                            (unsigned int)FLAC__STREAM_METADATA_APPLICATION_ID_LEN >> 3) )
        return 0;
      if ( v23 < (unsigned int)FLAC__STREAM_METADATA_APPLICATION_ID_LEN >> 3 )
        goto LABEL_24;
      v8 = *(_QWORD *)(a1 + 8);
      v23 -= (unsigned int)FLAC__STREAM_METADATA_APPLICATION_ID_LEN >> 3;
      v25 = *(_QWORD *)(v8 + 1336);
      if ( v25 )
      {
        v26 = 0;
        while ( memcmp_0(
                  (const void *)(*(_QWORD *)(v8 + 1328)
                               + ((unsigned __int64)(unsigned int)FLAC__STREAM_METADATA_APPLICATION_ID_LEN >> 3) * v26),
                  &Buf2,
                  (unsigned __int64)(unsigned int)FLAC__STREAM_METADATA_APPLICATION_ID_LEN >> 3) )
        {
          if ( ++v26 >= v25 )
            goto LABEL_42;
        }
        v24 = v44 != 0;
      }
LABEL_42:
      v3 = v41;
    }
    v27 = *(_QWORD *)(v8 + 88);
    if ( v24 )
    {
      v28 = (unsigned int)FLAC__bitreader_skip_byte_block_aligned_no_crc(v27, v23) == 0;
    }
    else
    {
      metadata_picture = 1;
      FLAC__bitreader_set_limit(v27, 8 * v23);
      switch ( Size_4 )
      {
        case 0u:
        case 3u:
          break;
        case 1u:
          metadata_picture = FLAC__bitreader_skip_byte_block_aligned_no_crc(
                               *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                               v23) != 0;
          break;
        case 2u:
          if ( v23 )
          {
            v30 = malloc(v23);
            Block = v30;
            goto LABEL_50;
          }
          Block = 0;
          break;
        case 4u:
          metadata_picture = read_metadata_vorbiscomment_(a1, (unsigned int *)&Buf2, v23) != 0;
          break;
        case 5u:
          metadata_picture = read_metadata_cuesheet_(a1, &Buf2) != 0;
          break;
        case 6u:
          metadata_picture = read_metadata_picture_(a1, (__int64)&Buf2);
          break;
        default:
          if ( v23 )
          {
            v30 = malloc(v23);
            Buf2 = (void **)v30;
LABEL_50:
            if ( v30 )
            {
              metadata_picture = FLAC__bitreader_read_byte_block_aligned_no_crc(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                   v30,
                                   v23) != 0;
            }
            else
            {
              metadata_picture = 0;
              **(_DWORD **)a1 = 8;
            }
          }
          else
          {
            Buf2 = 0;
          }
          break;
      }
      if ( (unsigned int)FLAC__bitreader_limit_remaining(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL)) )
      {
        v31 = *(_QWORD *)(a1 + 8);
        if ( !*(_DWORD *)(v31 + 5128) )
        {
          *(_DWORD *)(v31 + 8936) = 1;
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(a1 + 8) + 64LL))(
            a1,
            4,
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL));
        }
        if ( **(_DWORD **)a1 == 1 )
          **(_DWORD **)a1 = 2;
        metadata_picture = 0;
        FLAC__bitreader_remove_limit(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL));
      }
      else
      {
        FLAC__bitreader_remove_limit(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL));
        if ( metadata_picture )
        {
          v32 = *(_QWORD *)(a1 + 8);
          if ( !*(_DWORD *)(v32 + 5128) )
          {
            v33 = *(void (__fastcall **)(__int64, _DWORD *, _QWORD))(v32 + 56);
            if ( v33 )
              v33(a1, v46, *(_QWORD *)(v32 + 72));
          }
        }
      }
      switch ( Size_4 )
      {
        case 1u:
          goto LABEL_96;
        case 2u:
          v34 = (void **)Block;
          goto LABEL_94;
        case 4u:
          if ( Block )
            free(Block);
          v35 = (unsigned int)v50;
          v34 = v51;
          if ( (_DWORD)v50 )
          {
            v36 = 0;
            do
            {
              if ( v34[2 * v36 + 1] )
              {
                free(v34[2 * v36 + 1]);
                v34 = v51;
                v35 = (unsigned int)v50;
              }
              ++v36;
            }
            while ( v36 < v35 );
          }
          goto LABEL_94;
        case 5u:
          v37 = v53;
          v38 = v54;
          if ( !v53 )
            goto LABEL_86;
          if ( !v54 )
            goto LABEL_96;
          v39 = 0;
          do
          {
            v40 = v38[5 * v39 + 4];
            if ( v40 )
            {
              free(v40);
              v38 = v54;
              v37 = v53;
            }
            ++v39;
          }
          while ( v39 < v37 );
LABEL_86:
          if ( !v38 )
            goto LABEL_96;
          v34 = v38;
LABEL_95:
          free(v34);
LABEL_96:
          v28 = metadata_picture == 0;
          break;
        case 6u:
          if ( Block )
            free(Block);
          if ( v50 )
            free(v50);
          v34 = v52;
          goto LABEL_94;
        default:
          v34 = Buf2;
LABEL_94:
          if ( v34 )
            goto LABEL_95;
          goto LABEL_96;
      }
    }
    if ( !v28 )
      goto LABEL_98;
    return 0;
  }
  *(_DWORD *)(v8 + 460) = 0;
  v9 = Size;
  if ( Size )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 640LL) = 3;
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 644LL) = v3;
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 648LL) = v9;
    v10 = *(_QWORD *)(a1 + 8);
    if ( v9 != 18 * (v9 / 0x12) )
    {
      FLAC__bitreader_limit_invalidate(*(_QWORD *)(v10 + 88));
      return 0;
    }
    *(_DWORD *)(v10 + 656) = v9 / 0x12;
    v12 = *(_QWORD *)(a1 + 8);
    v13 = *(unsigned int *)(v12 + 656);
    v14 = *(void **)(v12 + 664);
    if ( *(_DWORD *)(v12 + 656) )
    {
      v15 = 24 * v13;
      v16 = _o_realloc(*(_QWORD *)(v12 + 664), 24 * v13);
      v17 = v16;
      if ( v15 && !v16 )
        free(v14);
    }
    else
    {
      v17 = _o_realloc(*(_QWORD *)(v12 + 664), 0);
    }
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 664LL) = v17;
    if ( v17 )
    {
      v18 = *(_QWORD *)(a1 + 8);
      if ( !*(_DWORD *)(v18 + 656) )
      {
LABEL_31:
        *(_DWORD *)(v18 + 460) = 1;
        v21 = *(_QWORD *)(a1 + 8);
        if ( !*(_DWORD *)(v21 + 5128) )
        {
          if ( *(_DWORD *)(v21 + 828) )
          {
            v22 = *(void (__fastcall **)(__int64, __int64, _QWORD))(v21 + 56);
            if ( v22 )
              v22(a1, v21 + 640, *(_QWORD *)(v21 + 72));
          }
        }
        goto LABEL_98;
      }
      v19 = 0;
      while ( (unsigned int)FLAC__bitreader_read_raw_uint64(
                              *(_QWORD *)(v18 + 88),
                              &v44,
                              (unsigned int)FLAC__STREAM_METADATA_SEEKPOINT_SAMPLE_NUMBER_LEN) )
      {
        v20 = 24LL * v19;
        *(_QWORD *)(v20 + *(_QWORD *)(*(_QWORD *)(a1 + 8) + 664LL)) = v44;
        if ( !(unsigned int)FLAC__bitreader_read_raw_uint64(
                              *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                              &v44,
                              (unsigned int)FLAC__STREAM_METADATA_SEEKPOINT_STREAM_OFFSET_LEN) )
          break;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 664LL) + v20 + 8) = v44;
        if ( !(unsigned int)FLAC__bitreader_read_raw_uint32(
                              *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                              &v41,
                              (unsigned int)FLAC__STREAM_METADATA_SEEKPOINT_FRAME_SAMPLES_LEN) )
          break;
        ++v19;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 664LL) + v20 + 16) = v41;
        v18 = *(_QWORD *)(a1 + 8);
        if ( v19 >= *(_DWORD *)(v18 + 656) )
          goto LABEL_31;
      }
      return 0;
    }
LABEL_24:
    **(_DWORD **)a1 = 8;
    return 0;
  }
LABEL_98:
  if ( v3 )
  {
    if ( !(unsigned int)FLAC__stream_decoder_get_decode_position(a1, *(_QWORD *)(a1 + 8) + 8896LL) )
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8896LL) = 0;
    **(_DWORD **)a1 = 2;
  }
  return 1;
}

```

## disassembly

```asm
0x1800099d0  push    rbp
0x1800099d2  push    rbx
0x1800099d3  push    rsi
0x1800099d4  push    rdi
0x1800099d5  push    r12
0x1800099d7  push    r13
0x1800099d9  push    r14
0x1800099db  push    r15
0x1800099dd  lea     rbp, [rsp-8]
0x1800099e2  sub     rsp, 108h
0x1800099e9  mov     rax, cs:__security_cookie
0x1800099f0  xor     rax, rsp
0x1800099f3  mov     [rbp+40h+var_50], rax
0x1800099f7  mov     r8d, cs:FLAC__STREAM_METADATA_IS_LAST_LEN
0x1800099fe  lea     rdx, [rsp+140h+var_108]
0x180009a03  mov     rdi, rcx
0x180009a06  mov     rcx, [rcx+8]
0x180009a0a  mov     rcx, [rcx+58h]
0x180009a0e  call    FLAC__bitreader_read_raw_uint32
0x180009a13  test    eax, eax
0x180009a15  jz      loc_180009B67
0x180009a1b  mov     rcx, [rdi+8]
0x180009a1f  lea     rdx, [rsp+140h+Size+4]
0x180009a24  mov     r8d, cs:FLAC__STREAM_METADATA_TYPE_LEN
0x180009a2b  xor     r12d, r12d
0x180009a2e  cmp     [rsp+140h+var_108], r12d
0x180009a33  mov     r15d, r12d
0x180009a36  mov     rcx, [rcx+58h]
0x180009a3a  setnz   r15b
0x180009a3e  mov     [rsp+140h+var_120], r15d
0x180009a43  call    FLAC__bitreader_read_raw_uint32
0x180009a48  test    eax, eax
0x180009a4a  jz      loc_180009B67
0x180009a50  mov     rcx, [rdi+8]
0x180009a54  lea     rdx, [rsp+140h+Size]
0x180009a59  mov     r8d, cs:FLAC__STREAM_METADATA_LENGTH_LEN
0x180009a60  mov     rcx, [rcx+58h]
0x180009a64  call    FLAC__bitreader_read_raw_uint32
0x180009a69  test    eax, eax
0x180009a6b  jz      loc_180009B67
0x180009a71  mov     ebx, dword ptr [rsp+140h+Size+4]
0x180009a75  test    ebx, ebx
0x180009a77  jnz     loc_180009B03
0x180009a7d  mov     r8d, dword ptr [rsp+140h+Size]
0x180009a82  mov     edx, r15d
0x180009a85  mov     rcx, rdi
0x180009a88  call    read_metadata_streaminfo_
0x180009a8d  test    eax, eax
0x180009a8f  jz      loc_180009B67
0x180009a95  mov     rax, [rdi+8]
0x180009a99  mov     dword ptr [rax+1C8h], 1
0x180009aa3  mov     rax, [rdi+8]
0x180009aa7  cmp     [rax+208h], r12
0x180009aae  jnz     short loc_180009AC0
0x180009ab0  cmp     [rax+210h], r12
0x180009ab7  jnz     short loc_180009AC0
0x180009ab9  mov     [rax+1400h], r12d
0x180009ac0  mov     r8, [rdi+8]
0x180009ac4  cmp     [r8+1408h], r12d
0x180009acb  jnz     loc_18000A0CD
0x180009ad1  cmp     [r8+330h], r12d
0x180009ad8  jz      loc_18000A0CD
0x180009ade  mov     rax, [r8+38h]
0x180009ae2  test    rax, rax
0x180009ae5  jz      loc_18000A0CD
0x180009aeb  lea     rdx, [r8+1D0h]
0x180009af2  mov     rcx, rdi
0x180009af5  mov     r8, [r8+48h]
0x180009af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009afe  jmp     loc_18000A0CD
0x180009b03  mov     rsi, [rdi+8]
0x180009b07  cmp     ebx, 3
0x180009b0a  jnz     loc_180009D28
0x180009b10  mov     [rsi+1CCh], r12d
0x180009b17  mov     r8d, dword ptr [rsp+140h+Size]
0x180009b1c  test    r8d, r8d
0x180009b1f  jz      loc_18000A0CD
0x180009b25  mov     rax, [rdi+8]
0x180009b29  mov     [rax+280h], ebx
0x180009b2f  mov     rax, [rdi+8]
0x180009b33  mov     [rax+284h], r15d
0x180009b3a  mov     rax, [rdi+8]
0x180009b3e  mov     [rax+288h], r8d
0x180009b45  mov     eax, 38E38E39h
0x180009b4a  mov     rcx, [rdi+8]
0x180009b4e  mul     r8d
0x180009b51  shr     edx, 2
0x180009b54  lea     eax, [rdx+rdx*8]
0x180009b57  add     eax, eax
0x180009b59  cmp     r8d, eax
0x180009b5c  jz      short loc_180009B89
0x180009b5e  mov     rcx, [rcx+58h]
0x180009b62  call    FLAC__bitreader_limit_invalidate
0x180009b67  xor     eax, eax
0x180009b69  mov     rcx, [rbp+40h+var_50]
0x180009b6d  xor     rcx, rsp; StackCookie
0x180009b70  call    __security_check_cookie
0x180009b75  add     rsp, 108h
0x180009b7c  pop     r15
0x180009b7e  pop     r14
0x180009b80  pop     r13
0x180009b82  pop     r12
0x180009b84  pop     rdi
0x180009b85  pop     rsi
0x180009b86  pop     rbx
0x180009b87  pop     rbp
0x180009b88  retn
0x180009b89  mov     [rcx+290h], edx
0x180009b8f  mov     rax, [rdi+8]
0x180009b93  mov     ecx, [rax+290h]
0x180009b99  mov     r14, [rax+298h]
0x180009ba0  test    rcx, rcx
0x180009ba3  jz      short loc_180009BD1
0x180009ba5  lea     rbx, [rcx+rcx*2]
0x180009ba9  mov     rcx, r14
0x180009bac  shl     rbx, 3
0x180009bb0  mov     rdx, rbx
0x180009bb3  call    cs:__imp__o_realloc
0x180009bb9  mov     rsi, rax
0x180009bbc  test    rbx, rbx
0x180009bbf  jz      short loc_180009BDF
0x180009bc1  test    rax, rax
0x180009bc4  jnz     short loc_180009BDF
0x180009bc6  mov     rcx, r14; Block
0x180009bc9  call    cs:__imp_free
0x180009bcf  jmp     short loc_180009BDF
0x180009bd1  xor     edx, edx
0x180009bd3  mov     rcx, r14
0x180009bd6  call    cs:__imp__o_realloc
0x180009bdc  mov     rsi, rax
0x180009bdf  mov     rcx, [rdi+8]
0x180009be3  mov     [rcx+298h], rsi
0x180009bea  test    rsi, rsi
0x180009bed  jnz     short loc_180009BFD
0x180009bef  mov     rax, [rdi]
0x180009bf2  mov     dword ptr [rax], 8
0x180009bf8  jmp     loc_180009B67
0x180009bfd  mov     rax, [rdi+8]
0x180009c01  cmp     [rax+290h], r12d
0x180009c08  jbe     loc_180009CDB
0x180009c0e  mov     ebx, r12d
0x180009c11  nop     dword ptr [rax+00h]
0x180009c15  nop     word ptr [rax+rax+00000000h]
0x180009c20  mov     r8d, cs:FLAC__STREAM_METADATA_SEEKPOINT_SAMPLE_NUMBER_LEN
0x180009c27  lea     rdx, [rsp+140h+var_110]
0x180009c2c  mov     rcx, [rax+58h]
0x180009c30  call    FLAC__bitreader_read_raw_uint64
0x180009c35  test    eax, eax
0x180009c37  jz      loc_180009B67
0x180009c3d  mov     eax, ebx
0x180009c3f  lea     rdx, [rsp+140h+var_110]
0x180009c44  lea     rcx, [rax+rax*2]
0x180009c48  mov     rax, [rdi+8]
0x180009c4c  lea     rsi, ds:0[rcx*8]
0x180009c54  mov     rcx, [rax+298h]
0x180009c5b  mov     rax, [rsp+140h+var_110]
0x180009c60  mov     [rsi+rcx], rax
0x180009c64  mov     rcx, [rdi+8]
0x180009c68  mov     r8d, cs:FLAC__STREAM_METADATA_SEEKPOINT_STREAM_OFFSET_LEN
0x180009c6f  mov     rcx, [rcx+58h]
0x180009c73  call    FLAC__bitreader_read_raw_uint64
0x180009c78  test    eax, eax
0x180009c7a  jz      loc_180009B67
0x180009c80  mov     rax, [rdi+8]
0x180009c84  lea     rdx, [rsp+140h+var_120]
0x180009c89  mov     rcx, [rax+298h]
0x180009c90  mov     rax, [rsp+140h+var_110]
0x180009c95  mov     [rcx+rsi+8], rax
0x180009c9a  mov     rcx, [rdi+8]
0x180009c9e  mov     r8d, cs:FLAC__STREAM_METADATA_SEEKPOINT_FRAME_SAMPLES_LEN
0x180009ca5  mov     rcx, [rcx+58h]
0x180009ca9  call    FLAC__bitreader_read_raw_uint32
0x180009cae  test    eax, eax
0x180009cb0  jz      loc_180009B67
0x180009cb6  mov     rax, [rdi+8]
0x180009cba  inc     ebx
0x180009cbc  mov     rcx, [rax+298h]
0x180009cc3  mov     eax, [rsp+140h+var_120]
0x180009cc7  mov     [rcx+rsi+10h], eax
0x180009ccb  mov     rax, [rdi+8]
0x180009ccf  cmp     ebx, [rax+290h]
0x180009cd5  jb      loc_180009C20
0x180009cdb  mov     dword ptr [rax+1CCh], 1
0x180009ce5  mov     r8, [rdi+8]
0x180009ce9  cmp     [r8+1408h], r12d
0x180009cf0  jnz     loc_18000A0CD
0x180009cf6  cmp     [r8+33Ch], r12d
0x180009cfd  jz      loc_18000A0CD
0x180009d03  mov     rax, [r8+38h]
0x180009d07  test    rax, rax
0x180009d0a  jz      loc_18000A0CD
0x180009d10  lea     rdx, [r8+280h]
0x180009d17  mov     rcx, rdi
0x180009d1a  mov     r8, [r8+48h]
0x180009d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d23  jmp     loc_18000A0CD
0x180009d28  mov     eax, [rsi+rbx*4+330h]
0x180009d2f  lea     rcx, [rsp+140h+var_F4]; void *
0x180009d34  mov     r14d, dword ptr [rsp+140h+Size]
0x180009d39  test    eax, eax
0x180009d3b  mov     r13d, r12d
0x180009d3e  mov     dword ptr [rsp+140h+var_110], eax
0x180009d42  setz    r13b
0x180009d46  mov     r8d, 0A4h; Size
0x180009d4c  xor     edx, edx; Val
0x180009d4e  call    memset_0
0x180009d53  mov     [rsp+140h+var_FC], r15d
0x180009d58  mov     [rsp+140h+var_100], ebx
0x180009d5c  mov     [rsp+140h+var_F8], r14d
0x180009d61  cmp     ebx, 2
0x180009d64  jnz     loc_180009DF3
0x180009d6a  mov     r8d, cs:FLAC__STREAM_METADATA_APPLICATION_ID_LEN
0x180009d71  lea     rdx, [rsp+140h+Buf2]
0x180009d76  mov     rcx, [rsi+58h]
0x180009d7a  shr     r8d, 3
0x180009d7e  call    FLAC__bitreader_read_byte_block_aligned_no_crc
0x180009d83  test    eax, eax
0x180009d85  jz      loc_180009B67
0x180009d8b  mov     r12d, cs:FLAC__STREAM_METADATA_APPLICATION_ID_LEN
0x180009d92  mov     eax, r12d
0x180009d95  shr     eax, 3
0x180009d98  cmp     r14d, eax
0x180009d9b  jb      loc_180009BEF
0x180009da1  mov     rsi, [rdi+8]
0x180009da5  sub     r14d, eax
0x180009da8  mov     r15, [rsi+538h]
0x180009daf  test    r15, r15
0x180009db2  jz      short loc_180009DEB
0x180009db4  xor     ebx, ebx
0x180009db6  nop     word ptr [rax+rax+00000000h]
0x180009dc0  mov     r8, r12
0x180009dc3  lea     rdx, [rsp+140h+Buf2]; Buf2
0x180009dc8  shr     r8, 3; Size
0x180009dcc  mov     rcx, rbx
0x180009dcf  imul    rcx, r8
0x180009dd3  add     rcx, [rsi+530h]; Buf1
0x180009dda  call    memcmp_0
0x180009ddf  test    eax, eax
0x180009de1  jz      short loc_180009E0B
0x180009de3  inc     rbx
0x180009de6  cmp     rbx, r15
0x180009de9  jb      short loc_180009DC0
0x180009deb  xor     r12d, r12d
0x180009dee  mov     r15d, [rsp+140h+var_120]
0x180009df3  mov     rcx, [rsi+58h]
0x180009df7  test    r13d, r13d
0x180009dfa  jz      short loc_180009E1C
0x180009dfc  mov     edx, r14d
0x180009dff  call    FLAC__bitreader_skip_byte_block_aligned_no_crc
0x180009e04  test    eax, eax
0x180009e06  jmp     loc_18000A0C7
0x180009e0b  xor     r12d, r12d
0x180009e0e  cmp     dword ptr [rsp+140h+var_110], r12d
0x180009e13  mov     r13d, r12d
0x180009e16  setnz   r13b
0x180009e1a  jmp     short loc_180009DEE
0x180009e1c  lea     edx, ds:0[r14*8]
0x180009e24  mov     esi, 1
0x180009e29  call    FLAC__bitreader_set_limit
0x180009e2e  mov     eax, dword ptr [rsp+140h+Size+4]
0x180009e32  lea     rbx, __ImageBase
0x180009e39  cmp     eax, 6; switch 7 cases
0x180009e3c  ja      def_180009E4C; jumptable 0000000180009E4C default case
0x180009e42  mov     eax, ds:(jpt_180009E4C - 180000000h)[rbx+rax*4]
0x180009e49  add     rax, rbx
0x180009e4c  jmp     rax; switch jump
0x180009e4e  mov     rcx, [rdi+8]; jumptable 0000000180009E4C case 1
0x180009e52  mov     edx, r14d
0x180009e55  mov     rcx, [rcx+58h]
0x180009e59  call    FLAC__bitreader_skip_byte_block_aligned_no_crc
0x180009e5e  test    eax, eax
0x180009e60  mov     esi, r12d
0x180009e63  setnz   sil
0x180009e67  jmp     loc_180009F22; jumptable 0000000180009E4C cases 0,3
0x180009e6c  test    r14d, r14d; jumptable 0000000180009E4C case 2
0x180009e6f  jz      short loc_180009E95
0x180009e71  mov     ecx, r14d; Size
0x180009e74  call    cs:__imp_malloc
0x180009e7a  mov     [rsp+140h+Block], rax
0x180009e7f  test    rax, rax
0x180009e82  jnz     short loc_180009EFF
0x180009e84  mov     rax, [rdi]
0x180009e87  mov     esi, r12d
0x180009e8a  mov     dword ptr [rax], 8
0x180009e90  jmp     loc_180009F22; jumptable 0000000180009E4C cases 0,3
0x180009e95  mov     [rsp+140h+Block], r12
0x180009e9a  jmp     loc_180009F22; jumptable 0000000180009E4C cases 0,3
0x180009e9f  mov     r8d, r14d; jumptable 0000000180009E4C case 4
0x180009ea2  lea     rdx, [rsp+140h+Buf2]
0x180009ea7  mov     rcx, rdi
0x180009eaa  call    read_metadata_vorbiscomment_
0x180009eaf  test    eax, eax
0x180009eb1  mov     esi, r12d
0x180009eb4  setnz   sil
0x180009eb8  jmp     short loc_180009F22; jumptable 0000000180009E4C cases 0,3
0x180009eba  lea     rdx, [rsp+140h+Buf2]; jumptable 0000000180009E4C case 5
0x180009ebf  mov     rcx, rdi
0x180009ec2  call    read_metadata_cuesheet_
0x180009ec7  test    eax, eax
0x180009ec9  mov     esi, r12d
  ... truncated ...
```
