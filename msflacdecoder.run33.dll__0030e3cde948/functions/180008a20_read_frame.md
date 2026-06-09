# read_frame_

- ea: `0x180008a20`
- end: `0x1800091e5`
- name: `read_frame_`
- size: `1989`
- prototype: ``
- caller_count: `6`
- callee_count: `15`
- tags: ``

## callers

- `0x1800059e0`
- `0x180006d30`
- `0x180006e10`
- `0x180006f80`
- `0x180007d90`
- `0x180007e50`

## callees

- `0x180001e80`
- `0x180008000`
- `0x180008a20`
- `0x1800091f0`
- `0x18000aee0`
- `0x18000c8e0`
- `0x18000ca90`
- `0x180011430`
- `0x180011450`
- `0x180011540`
- `0x180011640`
- `0x180011950`
- `0x180012310`
- `0x180012330`
- `0x180056010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180008efa`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180008efa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000900f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000904f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000915f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000900f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000904f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000915f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008f07`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008f07`

## pseudocode

```c
__int64 __fastcall read_frame_(int **a1, _DWORD *a2, unsigned int a3)
{
  int *v6; // rcx
  unsigned __int16 v7; // r8
  unsigned __int64 v8; // rdx
  int v9; // esi
  int *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // r8
  int v13; // ecx
  int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // eax
  int subframe; // eax
  int v18; // edx
  int *v20; // rax
  __int64 v21; // rbx
  unsigned int v22; // eax
  int *v23; // rax
  int crc16; // ebx
  int *v25; // r8
  unsigned int v26; // esi
  unsigned int v27; // r9d
  unsigned int v28; // edx
  int v29; // ecx
  int *v30; // rax
  int *v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned __int64 v34; // rdx
  unsigned int v35; // esi
  int *v36; // r8
  size_t v37; // rcx
  unsigned int v38; // ebx
  int v39; // r9d
  unsigned int v40; // edx
  void *v41; // rax
  unsigned int v42; // ebx
  unsigned int v43; // edx
  int *v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  unsigned int i; // ebx
  void *v48; // rcx
  unsigned int k; // ebx
  void *v50; // rcx
  int *v51; // rax
  int v52; // ecx
  unsigned int v53; // ebx
  unsigned int j; // edx
  void *v55; // rcx
  int *v56; // r8
  unsigned int (__fastcall *v57)(int **, __int64, _QWORD); // rax
  __int64 v58; // rdx
  int v59; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v60[3]; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int v61; // [rsp+30h] [rbp-D0h] BYREF
  int v62; // [rsp+34h] [rbp-CCh]
  unsigned int v63; // [rsp+38h] [rbp-C8h]
  __int64 v64; // [rsp+3Ch] [rbp-C4h]
  int v65; // [rsp+44h] [rbp-BCh]
  __int64 v66; // [rsp+48h] [rbp-B8h]
  __int64 v67; // [rsp+50h] [rbp-B0h]
  _DWORD v68[896]; // [rsp+58h] [rbp-A8h]
  __int16 v69; // [rsp+E58h] [rbp+D58h]
  void *Block; // [rsp+E60h] [rbp+D60h] BYREF
  __int128 v71; // [rsp+E68h] [rbp+D68h]
  __int128 v72; // [rsp+E78h] [rbp+D78h]
  __int128 v73; // [rsp+E88h] [rbp+D88h]
  __int64 v74; // [rsp+E98h] [rbp+D98h]

  *a2 = 0;
  a1[1][58] = 0;
  _mm_lfence();
  v6 = a1[1];
  v7 = FLAC__crc16_table[*((unsigned __int8 *)v6 + 5048)];
  v8 = *((unsigned __int8 *)v6 + 5049) ^ ((unsigned __int64)v7 >> 8);
  v9 = ((unsigned __int8)v7 << 8) ^ FLAC__crc16_table[v8];
  FLAC__bitreader_reset_read_crc16(
    *((_QWORD *)v6 + 11),
    (unsigned __int16)(((unsigned __int8)v7 << 8) ^ FLAC__crc16_table[v8]));
  if ( !(unsigned int)read_frame_header_(a1) )
    return 0;
  if ( **a1 == 2 )
    return 1;
  if ( !(unsigned int)allocate_output_(a1, (unsigned int)a1[1][338], (unsigned int)a1[1][340], (unsigned int)a1[1][342]) )
    return 0;
  v10 = a1[1];
  if ( v10[340] )
  {
    v11 = 0;
    while ( 1 )
    {
      v12 = (unsigned int)v10[342];
      v13 = v10[341] - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          if ( v14 == 1 )
          {
            v15 = v12 + 1;
            if ( v11 != 1 )
              v15 = v12;
            v12 = v15;
          }
        }
        else
        {
          v16 = v12 + 1;
          if ( v11 )
            v16 = v12;
          v12 = v16;
        }
      }
      else if ( v11 == 1 )
      {
        v12 = (unsigned int)(v12 + 1);
      }
      subframe = read_subframe_(a1, v11, v12, a3);
      v18 = **a1;
      if ( !subframe )
        break;
      if ( v18 != 3 )
        goto LABEL_23;
      v10 = a1[1];
      if ( ++v11 >= v10[340] )
        goto LABEL_24;
    }
    if ( v18 != 4 )
      return 0;
    goto LABEL_30;
  }
LABEL_23:
  if ( **a1 == 4 )
    goto LABEL_30;
LABEL_24:
  if ( !(unsigned int)FLAC__bitreader_is_consumed_byte_aligned(*((_QWORD *)a1[1] + 11)) )
  {
    v20 = a1[1];
    v59 = 0;
    v21 = *((_QWORD *)v20 + 11);
    v22 = FLAC__bitreader_bits_left_for_byte_alignment(v21);
    if ( (unsigned int)FLAC__bitreader_read_raw_uint32(v21, &v59, v22) )
    {
      if ( v59 )
      {
        v23 = a1[1];
        if ( !v23[1282] )
        {
          v23[2234] = 1;
          (*((void (__fastcall **)(int **, _QWORD, _QWORD))a1[1] + 8))(a1, 0, *((_QWORD *)a1[1] + 9));
        }
        **a1 = 2;
      }
      goto LABEL_30;
    }
    return 0;
  }
LABEL_30:
  if ( **a1 != 3 )
    goto LABEL_35;
  crc16 = (unsigned __int16)FLAC__bitreader_get_read_crc16(*((_QWORD *)a1[1] + 11));
  if ( (unsigned int)FLAC__bitreader_read_raw_uint32(
                       *((_QWORD *)a1[1] + 11),
                       v60,
                       (unsigned int)FLAC__FRAME_FOOTER_CRC_LEN) )
  {
    v9 = crc16;
LABEL_35:
    if ( **a1 == 3 )
    {
      if ( v9 == v60[0] )
      {
        if ( a3 )
        {
          undo_channel_coding(a1);
          v25 = a1[1];
          if ( v25[340] )
          {
            v26 = 0;
            do
            {
              v27 = v25[338];
              if ( v27 )
              {
                v28 = 0;
                while ( 1 )
                {
                  v29 = *(_DWORD *)(*(_QWORD *)&v25[2 * v26 + 24] + 4LL * v28);
                  if ( v29 < (int)0x80000000 >> (32 - *((_BYTE *)v25 + 1368))
                    || v29 > 0x7FFFFFFF >> (32 - *((_BYTE *)v25 + 1368)) )
                  {
                    break;
                  }
                  if ( ++v28 >= v27 )
                    goto LABEL_49;
                }
                if ( !v25[1282] )
                {
                  v25[2234] = 1;
                  (*((void (__fastcall **)(int **, __int64, _QWORD))a1[1] + 8))(a1, 5, *((_QWORD *)a1[1] + 9));
                }
                **a1 = 2;
              }
LABEL_49:
              v25 = a1[1];
              ++v26;
            }
            while ( v26 < v25[340] );
          }
        }
      }
      else
      {
        v30 = a1[1];
        if ( !v30[1282] )
        {
          v30[2234] = 1;
          (*((void (__fastcall **)(int **, __int64, _QWORD))a1[1] + 8))(a1, 2, *((_QWORD *)a1[1] + 9));
        }
        **a1 = 2;
      }
    }
    goto LABEL_54;
  }
  if ( **a1 != 4 )
    return 0;
LABEL_54:
  v31 = a1[1];
  if ( v31[2222] )
  {
    if ( **a1 == 3 && !v31[1282] )
    {
      if ( a3 )
      {
        v32 = *((_QWORD *)v31 + 660);
        v33 = (unsigned int)v31[1314];
        v34 = *((_QWORD *)v31 + 172);
        if ( v32 + v33 < v34 )
        {
          v35 = v34 - v32 - v33;
          if ( !v31[2234] )
          {
            v31[2234] = 1;
            (*((void (__fastcall **)(int **, __int64, _QWORD))a1[1] + 8))(a1, 6, *((_QWORD *)a1[1] + 9));
          }
          v36 = a1[1];
          if ( v36[1315] == v36[339] && v36[1316] == v36[340] && v36[1318] == v36[342] )
          {
            v37 = (unsigned int)v36[1314];
            if ( (unsigned int)v37 >= 0x10 )
            {
              Block = 0;
              v74 = 0;
              v71 = 0;
              v61 = v37;
              v38 = 0;
              v72 = 0;
              v73 = 0;
              v39 = v36[1315];
              v62 = v39;
              v40 = v36[1316];
              v63 = v40;
              v64 = *(_QWORD *)(v36 + 1317);
              v65 = v36[1319];
              v66 = *((_QWORD *)v36 + 660);
              v67 = *((_QWORD *)v36 + 661);
              v69 = 0;
              if ( v40 )
              {
                while ( 1 )
                {
                  v41 = v37 ? calloc(v37, 4u) : malloc(1u);
                  v40 = v63;
                  *(&Block + v38) = v41;
                  if ( !v41 )
                    break;
                  if ( ++v38 >= v40 )
                  {
                    v39 = v62;
                    LODWORD(v37) = v61;
                    goto LABEL_73;
                  }
                  v37 = v61;
                }
                for ( i = 0; i < v40; ++i )
                {
                  v48 = *(&Block + i);
                  if ( v48 )
                  {
                    free(v48);
                    v40 = v63;
                  }
                }
LABEL_89:
                **a1 = 8;
                return 0;
              }
LABEL_73:
              if ( v35 > 5 * v39 )
                v35 = 5 * v39;
              v42 = 50 * v37;
              if ( v35 <= 50 * (int)v37 )
                v42 = v35;
              if ( v42 )
              {
                while ( 1 )
                {
                  v43 = 0;
                  v66 += (unsigned int)v37;
                  v44 = *a1;
                  if ( v42 < (unsigned int)v37 )
                    LODWORD(v37) = v42;
                  v61 = v37;
                  v42 -= v37;
                  v44[6] = v37;
                  *((_QWORD *)a1[1] + 56) = v66 + v61;
                  if ( v63 )
                  {
                    do
                    {
                      v45 = v43++;
                      v46 = 112 * v45;
                      v68[v46] = 0;
                      *(_QWORD *)&v68[v46 + 2] = 0;
                      v68[v46 + 110] = 0;
                    }
                    while ( v43 < v63 );
                  }
                  if ( (unsigned int)write_audio_frame_to_client_(a1, &v61, &Block) )
                    break;
                  if ( !v42 )
                  {
                    v40 = v63;
                    goto LABEL_91;
                  }
                  LODWORD(v37) = v61;
                }
                v53 = 0;
                **a1 = 7;
                for ( j = v63; v53 < j; ++v53 )
                {
                  v55 = *(&Block + v53);
                  if ( v55 )
                  {
                    free(v55);
                    j = v63;
                  }
                }
                return 0;
              }
LABEL_91:
              for ( k = 0; k < v40; ++k )
              {
                v50 = *(&Block + k);
                if ( v50 )
                {
                  free(v50);
                  v40 = v63;
                }
              }
            }
          }
        }
      }
    }
  }
  a1[1][2234] = 0;
  if ( ((**a1 - 2) & 0xFFFFFFFD) != 0 )
  {
    *a2 = 1;
    v51 = a1[1];
    v52 = v51[111];
    if ( v52 )
      v51[110] = v52;
    (*a1)[2] = a1[1][340];
    (*a1)[3] = a1[1][341];
    (*a1)[4] = a1[1][342];
    (*a1)[5] = a1[1][339];
    (*a1)[6] = a1[1][338];
    *((_QWORD *)a1[1] + 56) = *((_QWORD *)a1[1] + 172) + (unsigned int)a1[1][338];
    if ( a3 && (unsigned int)write_audio_frame_to_client_(a1, a1[1] + 338, a1[1] + 24) )
    {
      **a1 = 7;
      return 0;
    }
  }
  else if ( !(unsigned int)FLAC__bitreader_rewind_to_after_last_seen_framesync(*((_QWORD *)a1[1] + 11)) )
  {
    v56 = a1[1];
    v57 = (unsigned int (__fastcall *)(int **, __int64, _QWORD))*((_QWORD *)v56 + 2);
    if ( v57 )
    {
      v58 = *((_QWORD *)v56 + 1113);
      if ( v58 )
      {
        if ( v57(a1, v58, *((_QWORD *)v56 + 9)) == 1 )
        {
          **a1 = 6;
          return 0;
        }
        if ( !(unsigned int)FLAC__bitreader_clear(*((_QWORD *)a1[1] + 11)) )
          goto LABEL_89;
      }
    }
  }
  **a1 = 2;
  return 1;
}

```

## disassembly

```asm
0x180008a20  mov     [rsp-8+arg_10], rbx
0x180008a25  mov     [rsp-8+arg_18], rsi
0x180008a2a  push    rbp
0x180008a2b  push    rdi
0x180008a2c  push    r12
0x180008a2e  push    r14
0x180008a30  push    r15
0x180008a32  lea     rbp, [rsp-0DB0h]
0x180008a3a  sub     rsp, 0EB0h
0x180008a41  mov     rax, cs:__security_cookie
0x180008a48  xor     rax, rsp
0x180008a4b  mov     [rbp+0DD0h+var_30], rax
0x180008a52  xor     r12d, r12d
0x180008a55  mov     r14d, r8d
0x180008a58  mov     [rdx], r12d
0x180008a5b  mov     r15, rdx
0x180008a5e  mov     rax, [rcx+8]
0x180008a62  mov     rdi, rcx
0x180008a65  mov     [rax+0E8h], r12d
0x180008a6c  lfence
0x180008a6f  mov     rcx, [rcx+8]
0x180008a73  lea     r9, FLAC__crc16_table
0x180008a7a  movzx   eax, byte ptr [rcx+13B8h]
0x180008a81  movzx   r8d, word ptr [r9+rax*2]
0x180008a86  movzx   eax, byte ptr [rcx+13B9h]
0x180008a8d  mov     edx, r8d
0x180008a90  mov     rcx, [rcx+58h]
0x180008a94  shr     rdx, 8
0x180008a98  xor     rdx, rax
0x180008a9b  movzx   eax, r8b
0x180008a9f  shl     eax, 8
0x180008aa2  movzx   esi, word ptr [r9+rdx*2]
0x180008aa7  xor     esi, eax
0x180008aa9  movzx   edx, si
0x180008aac  call    FLAC__bitreader_reset_read_crc16
0x180008ab1  mov     rcx, rdi
0x180008ab4  call    read_frame_header_
0x180008ab9  test    eax, eax
0x180008abb  jz      loc_180008B86
0x180008ac1  mov     rax, [rdi]
0x180008ac4  cmp     dword ptr [rax], 2
0x180008ac7  jz      loc_1800091DB
0x180008acd  mov     rdx, [rdi+8]
0x180008ad1  mov     rcx, rdi
0x180008ad4  mov     r9d, [rdx+558h]
0x180008adb  mov     r8d, [rdx+550h]
0x180008ae2  mov     edx, [rdx+548h]
0x180008ae8  call    allocate_output_
0x180008aed  test    eax, eax
0x180008aef  jz      loc_180008B86
0x180008af5  mov     rcx, [rdi+8]
0x180008af9  cmp     [rcx+550h], r12d
0x180008b00  jbe     loc_180008BB3
0x180008b06  mov     ebx, r12d
0x180008b09  nop     dword ptr [rax+00000000h]
0x180008b10  mov     r8d, [rcx+558h]
0x180008b17  mov     ecx, [rcx+554h]
0x180008b1d  sub     ecx, 1
0x180008b20  jz      short loc_180008B4A
0x180008b22  sub     ecx, 1
0x180008b25  jz      short loc_180008B3B
0x180008b27  cmp     ecx, 1
0x180008b2a  jnz     short loc_180008B52
0x180008b2c  lea     eax, [r8+1]
0x180008b30  cmp     ebx, ecx
0x180008b32  cmovnz  eax, r8d
0x180008b36  mov     r8d, eax
0x180008b39  jmp     short loc_180008B52
0x180008b3b  lea     eax, [r8+1]
0x180008b3f  test    ebx, ebx
0x180008b41  cmovnz  eax, r8d
0x180008b45  mov     r8d, eax
0x180008b48  jmp     short loc_180008B52
0x180008b4a  cmp     ebx, 1
0x180008b4d  jnz     short loc_180008B52
0x180008b4f  inc     r8d
0x180008b52  mov     r9d, r14d
0x180008b55  mov     edx, ebx
0x180008b57  mov     rcx, rdi
0x180008b5a  call    read_subframe_
0x180008b5f  mov     rcx, [rdi]
0x180008b62  mov     edx, [rcx]
0x180008b64  test    eax, eax
0x180008b66  jz      short loc_180008B7D
0x180008b68  cmp     edx, 3
0x180008b6b  jnz     short loc_180008BB3
0x180008b6d  mov     rcx, [rdi+8]
0x180008b71  inc     ebx
0x180008b73  cmp     ebx, [rcx+550h]
0x180008b79  jb      short loc_180008B10
0x180008b7b  jmp     short loc_180008BBB
0x180008b7d  cmp     edx, 4
0x180008b80  jz      loc_180008C36
0x180008b86  xor     eax, eax
0x180008b88  mov     rcx, [rbp+0DD0h+var_30]
0x180008b8f  xor     rcx, rsp; StackCookie
0x180008b92  call    __security_check_cookie
0x180008b97  lea     r11, [rsp+0ED0h+var_20]
0x180008b9f  mov     rbx, [r11+40h]
0x180008ba3  mov     rsi, [r11+48h]
0x180008ba7  mov     rsp, r11
0x180008baa  pop     r15
0x180008bac  pop     r14
0x180008bae  pop     r12
0x180008bb0  pop     rdi
0x180008bb1  pop     rbp
0x180008bb2  retn
0x180008bb3  mov     rax, [rdi]
0x180008bb6  cmp     dword ptr [rax], 4
0x180008bb9  jz      short loc_180008C36
0x180008bbb  mov     rcx, [rdi+8]
0x180008bbf  mov     rcx, [rcx+58h]
0x180008bc3  call    FLAC__bitreader_is_consumed_byte_aligned
0x180008bc8  test    eax, eax
0x180008bca  jnz     short loc_180008C36
0x180008bcc  mov     rax, [rdi+8]
0x180008bd0  mov     [rsp+0ED0h+var_EB0], r12d
0x180008bd5  mov     rcx, rax
0x180008bd8  mov     rcx, [rax+58h]
0x180008bdc  mov     rbx, [rax+58h]
0x180008be0  call    FLAC__bitreader_bits_left_for_byte_alignment
0x180008be5  mov     r8d, eax
0x180008be8  lea     rdx, [rsp+0ED0h+var_EB0]
0x180008bed  mov     rcx, rbx
0x180008bf0  call    FLAC__bitreader_read_raw_uint32
0x180008bf5  test    eax, eax
0x180008bf7  jz      short loc_180008B86
0x180008bf9  cmp     [rsp+0ED0h+var_EB0], r12d
0x180008bfe  jz      short loc_180008C36
0x180008c00  mov     rax, [rdi+8]
0x180008c04  cmp     [rax+1408h], r12d
0x180008c0b  jnz     short loc_180008C2D
0x180008c0d  mov     dword ptr [rax+22E8h], 1
0x180008c17  xor     edx, edx
0x180008c19  mov     r8, [rdi+8]
0x180008c1d  mov     rcx, rdi
0x180008c20  mov     rax, [r8+40h]
0x180008c24  mov     r8, [r8+48h]
0x180008c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c2d  mov     rax, [rdi]
0x180008c30  mov     dword ptr [rax], 2
0x180008c36  mov     rax, [rdi]
0x180008c39  cmp     dword ptr [rax], 3
0x180008c3c  jnz     short loc_180008C7E
0x180008c3e  mov     rcx, [rdi+8]
0x180008c42  mov     rcx, [rcx+58h]
0x180008c46  call    FLAC__bitreader_get_read_crc16
0x180008c4b  mov     rcx, [rdi+8]
0x180008c4f  lea     rdx, [rsp+0ED0h+var_EAC]
0x180008c54  mov     r8d, cs:FLAC__FRAME_FOOTER_CRC_LEN
0x180008c5b  movzx   ebx, ax
0x180008c5e  mov     rcx, [rcx+58h]
0x180008c62  call    FLAC__bitreader_read_raw_uint32
0x180008c67  test    eax, eax
0x180008c69  jnz     short loc_180008C7C
0x180008c6b  mov     rax, [rdi]
0x180008c6e  cmp     dword ptr [rax], 4
0x180008c71  jnz     loc_180008B86
0x180008c77  jmp     loc_180008D90
0x180008c7c  mov     esi, ebx
0x180008c7e  mov     rax, [rdi]
0x180008c81  cmp     dword ptr [rax], 3
0x180008c84  jnz     loc_180008D90
0x180008c8a  cmp     esi, [rsp+0ED0h+var_EAC]
0x180008c8e  jnz     loc_180008D57
0x180008c94  test    r14d, r14d
0x180008c97  jz      loc_180008D90
0x180008c9d  mov     rcx, rdi
0x180008ca0  call    undo_channel_coding
0x180008ca5  mov     r8, [rdi+8]
0x180008ca9  cmp     [r8+550h], r12d
0x180008cb0  jbe     loc_180008D90
0x180008cb6  mov     esi, r12d
0x180008cb9  nop     dword ptr [rax+00000000h]
0x180008cc0  mov     r9d, [r8+548h]
0x180008cc7  test    r9d, r9d
0x180008cca  jz      short loc_180008D42
0x180008ccc  mov     ecx, 20h ; ' '
0x180008cd1  mov     eax, esi
0x180008cd3  sub     ecx, [r8+558h]
0x180008cda  mov     r11d, 80000000h
0x180008ce0  sar     r11d, cl
0x180008ce3  mov     r10d, 7FFFFFFFh
0x180008ce9  sar     r10d, cl
0x180008cec  mov     edx, r12d
0x180008cef  mov     rbx, [r8+rax*8+60h]
0x180008cf4  mov     eax, edx
0x180008cf6  mov     ecx, [rbx+rax*4]
0x180008cf9  cmp     ecx, r11d
0x180008cfc  jl      short loc_180008D0C
0x180008cfe  cmp     ecx, r10d
0x180008d01  jg      short loc_180008D0C
0x180008d03  inc     edx
0x180008d05  cmp     edx, r9d
0x180008d08  jb      short loc_180008CF4
0x180008d0a  jmp     short loc_180008D42
0x180008d0c  cmp     [r8+1408h], r12d
0x180008d13  jnz     short loc_180008D39
0x180008d15  mov     dword ptr [r8+22E8h], 1
0x180008d20  mov     edx, 5
0x180008d25  mov     r8, [rdi+8]
0x180008d29  mov     rcx, rdi
0x180008d2c  mov     rax, [r8+40h]
0x180008d30  mov     r8, [r8+48h]
0x180008d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d39  mov     rax, [rdi]
0x180008d3c  mov     dword ptr [rax], 2
0x180008d42  mov     r8, [rdi+8]
0x180008d46  inc     esi
0x180008d48  cmp     esi, [r8+550h]
0x180008d4f  jb      loc_180008CC0
0x180008d55  jmp     short loc_180008D90
0x180008d57  mov     rax, [rdi+8]
0x180008d5b  cmp     [rax+1408h], r12d
0x180008d62  jnz     short loc_180008D87
0x180008d64  mov     dword ptr [rax+22E8h], 1
0x180008d6e  mov     edx, 2
0x180008d73  mov     r8, [rdi+8]
0x180008d77  mov     rcx, rdi
0x180008d7a  mov     rax, [r8+40h]
0x180008d7e  mov     r8, [r8+48h]
0x180008d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d87  mov     rax, [rdi]
0x180008d8a  mov     dword ptr [rax], 2
0x180008d90  mov     rcx, [rdi+8]
0x180008d94  cmp     [rcx+22B8h], r12d
0x180008d9b  jz      loc_18000905F
0x180008da1  mov     rax, [rdi]
0x180008da4  cmp     dword ptr [rax], 3
0x180008da7  jnz     loc_18000905F
0x180008dad  cmp     [rcx+1408h], r12d
0x180008db4  jnz     loc_18000905F
0x180008dba  test    r14d, r14d
0x180008dbd  jz      loc_18000905F
0x180008dc3  mov     r8, [rcx+14A0h]
0x180008dca  mov     r9d, [rcx+1488h]
0x180008dd1  mov     rdx, [rcx+560h]
0x180008dd8  lea     rax, [r8+r9]
0x180008ddc  cmp     rax, rdx
0x180008ddf  jnb     loc_18000905F
0x180008de5  sub     edx, r8d
0x180008de8  sub     edx, r9d
0x180008deb  mov     esi, edx
0x180008ded  cmp     [rcx+22E8h], r12d
0x180008df4  jnz     short loc_180008E19
0x180008df6  mov     dword ptr [rcx+22E8h], 1
0x180008e00  mov     edx, 6
0x180008e05  mov     r8, [rdi+8]
0x180008e09  mov     rcx, rdi
0x180008e0c  mov     rax, [r8+40h]
0x180008e10  mov     r8, [r8+48h]
0x180008e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e19  mov     r8, [rdi+8]
0x180008e1d  mov     eax, [r8+54Ch]
0x180008e24  cmp     [r8+148Ch], eax
0x180008e2b  jnz     loc_18000905F
0x180008e31  mov     eax, [r8+550h]
0x180008e38  cmp     [r8+1490h], eax
0x180008e3f  jnz     loc_18000905F
0x180008e45  mov     eax, [r8+558h]
0x180008e4c  cmp     [r8+1498h], eax
0x180008e53  jnz     loc_18000905F
0x180008e59  mov     ecx, [r8+1488h]; Count
0x180008e60  cmp     ecx, 10h
0x180008e63  jb      loc_18000905F
0x180008e69  mov     [rbp+0DD0h+Block], r12
0x180008e70  xor     eax, eax
0x180008e72  mov     [rbp+0DD0h+var_38], rax
0x180008e79  xorps   xmm0, xmm0
0x180008e7c  movups  [rbp+0DD0h+var_68], xmm0
0x180008e83  mov     [rsp+0ED0h+var_EA0], ecx
0x180008e87  mov     ebx, r12d
0x180008e8a  movups  [rbp+0DD0h+var_58], xmm0
0x180008e91  movups  [rbp+0DD0h+var_48], xmm0
0x180008e98  mov     r9d, [r8+148Ch]
0x180008e9f  mov     [rsp+0ED0h+var_E9C], r9d
0x180008ea4  mov     edx, [r8+1490h]
0x180008eab  mov     [rsp+0ED0h+var_E98], edx
0x180008eaf  movsd   xmm0, qword ptr [r8+1494h]
0x180008eb8  movsd   [rsp+0ED0h+var_E94], xmm0
0x180008ebe  mov     eax, [r8+149Ch]
0x180008ec5  mov     [rsp+0ED0h+var_E8C], eax
0x180008ec9  mov     rax, [r8+14A0h]
0x180008ed0  mov     [rsp+0ED0h+var_E88], rax
0x180008ed5  mov     rax, [r8+14A8h]
0x180008edc  mov     [rsp+0ED0h+var_E80], rax
0x180008ee1  mov     [rbp+0DD0h+var_78], r12w
0x180008ee9  test    edx, edx
0x180008eeb  jz      short loc_180008F3C
0x180008eed  nop     dword ptr [rax]
0x180008ef0  test    rcx, rcx
0x180008ef3  jz      short loc_180008F02
0x180008ef5  mov     edx, 4; Size
0x180008efa  call    cs:__imp_calloc
0x180008f00  jmp     short loc_180008F0D
0x180008f02  mov     ecx, 1; Size
0x180008f07  call    cs:__imp_malloc
0x180008f0d  mov     edx, [rsp+0ED0h+var_E98]
0x180008f11  mov     rcx, rax
0x180008f14  mov     eax, ebx
  ... truncated ...
```
