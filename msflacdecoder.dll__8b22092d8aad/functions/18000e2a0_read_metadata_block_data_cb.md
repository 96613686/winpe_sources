# read_metadata_block_data_cb_

- ea: `0x18000e2a0`
- end: `0x18000e588`
- name: `read_metadata_block_data_cb_`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000da40`

## callees

- `0x180001e80`
- `0x18000e2a0`
- `0x18000e590`
- `0x18000ea90`
- `0x18000ee30`
- `0x18000f010`
- `0x180056010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e46c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e51c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e46c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e51c`

## pseudocode

```c
__int64 __fastcall read_metadata_block_data_cb_(
        __int64 a1,
        __int64 (__fastcall *a2)(_BYTE *, __int64, __int64, __int64),
        __int64 (__fastcall *a3)(__int64, _QWORD, __int64),
        __int64 a4)
{
  unsigned int v7; // edx
  __int128 v8; // xmm0
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  unsigned int v16; // ecx
  int v17; // edx
  unsigned __int64 v18; // rcx
  unsigned int v19; // ebx
  int v20; // eax
  unsigned int v21; // ecx
  unsigned int v23; // r14d
  __int64 v24; // rdi
  __int64 v25; // r15
  unsigned int v26; // r14d
  _BYTE *v27; // rax
  size_t v28; // r14
  _BYTE *v29; // rax
  _BYTE v30[18]; // [rsp+30h] [rbp-68h] BYREF
  __int128 v31; // [rsp+42h] [rbp-56h]

  switch ( *(_DWORD *)a4 )
  {
    case 0:
      if ( a2(v30, 1, 34, a1) != 34 )
        return 6;
      v7 = v30[12];
      v8 = v31;
      v9 = v30[3];
      *(_DWORD *)(a4 + 16) = v30[1] | (v30[0] << 8);
      v10 = v9 | (v30[2] << 8);
      v11 = v30[5];
      *(_DWORD *)(a4 + 20) = v10;
      v12 = v30[6] | ((v11 | (v30[4] << 8)) << 8);
      v13 = v30[8];
      *(_DWORD *)(a4 + 24) = v12;
      v14 = v30[9] | ((v13 | (v30[7] << 8)) << 8);
      v15 = v30[11];
      *(_DWORD *)(a4 + 28) = v14;
      *(_DWORD *)(a4 + 32) = (v7 >> 4) | (16 * (v15 | (v30[10] << 8)));
      v16 = v30[13];
      *(_DWORD *)(a4 + 36) = ((v7 >> 1) & 7) + 1;
      v17 = ((v16 >> 4) | (16 * (v7 & 1))) + 1;
      v18 = v30[14] | ((unsigned __int64)(v16 & 0xF) << 8);
      *(_DWORD *)(a4 + 40) = v17;
      *(_QWORD *)(a4 + 48) = v30[17] | ((v30[16] | ((v30[15] | (v18 << 8)) << 8)) << 8);
      v19 = 0;
      *(_OWORD *)(a4 + 56) = v8;
      return v19;
    case 1:
      v20 = a3(a1, *(unsigned int *)(a4 + 8), 1);
      v21 = 7;
      if ( !v20 )
        return 0;
      return v21;
    case 2:
      v23 = *(_DWORD *)(a4 + 8);
      v24 = (unsigned int)FLAC__STREAM_METADATA_APPLICATION_ID_LEN >> 3;
      v25 = a4 + 16;
      if ( a2((_BYTE *)(a4 + 16), 1, v24, a1) != v24 || v23 < (unsigned int)v24 )
        return 6;
      v19 = 0;
      v26 = v23 - v24;
      if ( v26 )
      {
        v27 = malloc(v26);
        *(_QWORD *)(v25 + 8) = v27;
        if ( v27 )
        {
          if ( a2(v27, 1, v26, a1) != v26 )
            return 6;
        }
        else
        {
          return 11;
        }
      }
      else
      {
        *(_QWORD *)(v25 + 8) = 0;
      }
      return v19;
    case 3:
      return read_metadata_block_data_seektable_cb_(a1, a2, a4 + 16, *(unsigned int *)(a4 + 8));
    case 4:
      return read_metadata_block_data_vorbis_comment_cb_(a1, (_DWORD)a2, (_DWORD)a3, (int)a4 + 16, *(_DWORD *)(a4 + 8));
    case 5:
      return read_metadata_block_data_cuesheet_cb_(a1, a2, a4 + 16);
    case 6:
      return read_metadata_block_data_picture_cb_(a1, a2, a4 + 16);
    default:
      v19 = 0;
      if ( *(_DWORD *)(a4 + 8) )
      {
        v28 = *(unsigned int *)(a4 + 8);
        v29 = malloc(v28);
        *(_QWORD *)(a4 + 16) = v29;
        if ( v29 )
        {
          if ( a2(v29, 1, v28, a1) != v28 )
            return 6;
        }
        else
        {
          return 11;
        }
      }
      else
      {
        *(_QWORD *)(a4 + 16) = 0;
      }
      return v19;
  }
}

```

## disassembly

```asm
0x18000e2a0  push    rbx
0x18000e2a2  push    rbp
0x18000e2a3  push    rsi
0x18000e2a4  push    rdi
0x18000e2a5  push    r14
0x18000e2a7  sub     rsp, 70h
0x18000e2ab  mov     rax, cs:__security_cookie
0x18000e2b2  xor     rax, rsp
0x18000e2b5  mov     [rsp+98h+var_40], rax
0x18000e2ba  movsxd  rax, dword ptr [r9]
0x18000e2bd  mov     rdi, r9
0x18000e2c0  mov     r10, r8
0x18000e2c3  mov     rbp, rdx
0x18000e2c6  mov     rsi, rcx
0x18000e2c9  cmp     eax, 6; switch 7 cases
0x18000e2cc  ja      def_18000E2E3; jumptable 000000018000E2E3 default case
0x18000e2d2  lea     rdx, __ImageBase
0x18000e2d9  mov     ecx, ds:(jpt_18000E2E3 - 180000000h)[rdx+rax*4]
0x18000e2e0  add     rcx, rdx
0x18000e2e3  jmp     rcx; switch jump
0x18000e2e5  mov     r9, rsi; jumptable 000000018000E2E3 case 0
0x18000e2e8  lea     rcx, [rsp+98h+var_68]
0x18000e2ed  mov     edx, 1
0x18000e2f2  mov     r8d, 22h ; '"'
0x18000e2f8  mov     rax, rbp
0x18000e2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e300  cmp     rax, 22h ; '"'
0x18000e304  jnz     loc_18000E54D
0x18000e30a  movzx   eax, [rsp+98h+var_67]
0x18000e30f  movzx   ecx, [rsp+98h+var_68]
0x18000e314  movzx   edx, [rsp+98h+var_5C]
0x18000e319  movups  xmm0, [rsp+98h+var_56]
0x18000e31e  shl     ecx, 8
0x18000e321  or      ecx, eax
0x18000e323  movzx   eax, [rsp+98h+var_65]
0x18000e328  mov     [rdi+10h], ecx
0x18000e32b  movzx   ecx, [rsp+98h+var_66]
0x18000e330  shl     ecx, 8
0x18000e333  or      ecx, eax
0x18000e335  movzx   eax, [rsp+98h+var_63]
0x18000e33a  mov     [rdi+14h], ecx
0x18000e33d  movzx   ecx, [rsp+98h+var_64]
0x18000e342  shl     ecx, 8
0x18000e345  or      ecx, eax
0x18000e347  movzx   eax, [rsp+98h+var_62]
0x18000e34c  shl     ecx, 8
0x18000e34f  or      ecx, eax
0x18000e351  movzx   eax, [rsp+98h+var_60]
0x18000e356  mov     [rdi+18h], ecx
0x18000e359  movzx   ecx, [rsp+98h+var_61]
0x18000e35e  shl     ecx, 8
0x18000e361  or      ecx, eax
0x18000e363  movzx   eax, [rsp+98h+var_5F]
0x18000e368  shl     ecx, 8
0x18000e36b  or      ecx, eax
0x18000e36d  movzx   eax, [rsp+98h+var_5D]
0x18000e372  mov     [rdi+1Ch], ecx
0x18000e375  movzx   ecx, [rsp+98h+var_5E]
0x18000e37a  shl     ecx, 8
0x18000e37d  or      ecx, eax
0x18000e37f  mov     eax, edx
0x18000e381  shr     eax, 4
0x18000e384  shl     ecx, 4
0x18000e387  or      ecx, eax
0x18000e389  mov     eax, edx
0x18000e38b  mov     [rdi+20h], ecx
0x18000e38e  and     edx, 1
0x18000e391  movzx   ecx, [rsp+98h+var_5B]
0x18000e396  shr     eax, 1
0x18000e398  and     eax, 7
0x18000e39b  shl     edx, 4
0x18000e39e  inc     eax
0x18000e3a0  mov     [rdi+24h], eax
0x18000e3a3  mov     eax, ecx
0x18000e3a5  and     ecx, 0Fh
0x18000e3a8  shr     eax, 4
0x18000e3ab  shl     rcx, 8
0x18000e3af  or      edx, eax
0x18000e3b1  movzx   eax, [rsp+98h+var_5A]
0x18000e3b6  inc     edx
0x18000e3b8  or      rcx, rax
0x18000e3bb  mov     [rdi+28h], edx
0x18000e3be  movzx   eax, [rsp+98h+var_59]
0x18000e3c3  shl     rcx, 8
0x18000e3c7  or      rcx, rax
0x18000e3ca  movzx   eax, [rsp+98h+var_58]
0x18000e3cf  shl     rcx, 8
0x18000e3d3  or      rcx, rax
0x18000e3d6  movzx   eax, [rsp+98h+var_57]
0x18000e3db  shl     rcx, 8
0x18000e3df  or      rcx, rax
0x18000e3e2  mov     [rdi+30h], rcx
0x18000e3e6  xor     ebx, ebx
0x18000e3e8  movups  xmmword ptr [rdi+38h], xmm0
0x18000e3ec  jmp     loc_18000E552
0x18000e3f1  mov     edx, [r9+8]; jumptable 000000018000E2E3 case 1
0x18000e3f5  mov     r8d, 1
0x18000e3fb  mov     rcx, rsi
0x18000e3fe  mov     rax, r10
0x18000e401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e406  xor     ebx, ebx
0x18000e408  mov     ecx, 7
0x18000e40d  test    eax, eax
0x18000e40f  cmovz   ecx, ebx
0x18000e412  mov     eax, ecx
0x18000e414  jmp     loc_18000E554
0x18000e419  mov     eax, cs:FLAC__STREAM_METADATA_APPLICATION_ID_LEN; jumptable 000000018000E2E3 case 2
0x18000e41f  mov     edx, 1
0x18000e424  mov     r14d, [r9+8]
0x18000e428  shr     eax, 3
0x18000e42b  mov     edi, eax
0x18000e42d  mov     r8d, eax
0x18000e430  mov     rax, rbp
0x18000e433  mov     [rsp+98h+var_30], r15
0x18000e438  lea     r15, [r9+10h]
0x18000e43c  mov     r9, rsi
0x18000e43f  mov     rcx, r15
0x18000e442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e447  cmp     rax, rdi
0x18000e44a  jnz     short loc_18000E4A5
0x18000e44c  cmp     r14d, edi
0x18000e44f  jb      short loc_18000E4A5
0x18000e451  xor     ebx, ebx
0x18000e453  sub     r14d, edi
0x18000e456  jnz     short loc_18000E466
0x18000e458  mov     [r15+8], rbx
0x18000e45c  mov     r15, [rsp+98h+var_30]
0x18000e461  jmp     loc_18000E552
0x18000e466  mov     ecx, r14d; Size
0x18000e469  mov     edi, r14d
0x18000e46c  call    cs:__imp_malloc
0x18000e472  mov     [r15+8], rax
0x18000e476  test    rax, rax
0x18000e479  jnz     short loc_18000E48A
0x18000e47b  mov     r15, [rsp+98h+var_30]
0x18000e480  mov     ebx, 0Bh
0x18000e485  jmp     loc_18000E552
0x18000e48a  mov     rcx, rax
0x18000e48d  mov     r9, rsi
0x18000e490  mov     rax, rbp
0x18000e493  mov     r8, rdi
0x18000e496  mov     edx, 1
0x18000e49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4a0  cmp     rax, rdi
0x18000e4a3  jz      short loc_18000E4AA
0x18000e4a5  mov     ebx, 6
0x18000e4aa  mov     r15, [rsp+98h+var_30]
0x18000e4af  jmp     loc_18000E552
0x18000e4b4  lea     r8, [r9+10h]; jumptable 000000018000E2E3 case 3
0x18000e4b8  mov     rdx, rbp
0x18000e4bb  mov     r9d, [r9+8]
0x18000e4bf  mov     rcx, rsi
0x18000e4c2  call    read_metadata_block_data_seektable_cb_
0x18000e4c7  jmp     loc_18000E554
0x18000e4cc  mov     eax, [rdi+8]; jumptable 000000018000E2E3 case 4
0x18000e4cf  add     r9, 10h
0x18000e4d3  mov     rdx, rbp
0x18000e4d6  mov     [rsp+98h+var_78], eax
0x18000e4da  mov     rcx, rsi
0x18000e4dd  call    read_metadata_block_data_vorbis_comment_cb_
0x18000e4e2  jmp     short loc_18000E554
0x18000e4e4  lea     r8, [r9+10h]; jumptable 000000018000E2E3 case 5
0x18000e4e8  mov     rdx, rbp
0x18000e4eb  mov     rcx, rsi
0x18000e4ee  call    read_metadata_block_data_cuesheet_cb_
0x18000e4f3  jmp     short loc_18000E554
0x18000e4f5  lea     r8, [r9+10h]; jumptable 000000018000E2E3 case 6
0x18000e4f9  mov     rdx, rbp
0x18000e4fc  mov     rcx, rsi
0x18000e4ff  call    read_metadata_block_data_picture_cb_
0x18000e504  jmp     short loc_18000E554
0x18000e506  mov     eax, [r9+8]; jumptable 000000018000E2E3 default case
0x18000e50a  xor     ebx, ebx
0x18000e50c  test    eax, eax
0x18000e50e  jnz     short loc_18000E516
0x18000e510  mov     [r9+10h], rbx
0x18000e514  jmp     short loc_18000E552
0x18000e516  mov     rcx, rax; Size
0x18000e519  mov     r14, rax
0x18000e51c  call    cs:__imp_malloc
0x18000e522  mov     [rdi+10h], rax
0x18000e526  test    rax, rax
0x18000e529  jnz     short loc_18000E532
0x18000e52b  mov     ebx, 0Bh
0x18000e530  jmp     short loc_18000E552
0x18000e532  mov     rcx, rax
0x18000e535  mov     r9, rsi
0x18000e538  mov     rax, rbp
0x18000e53b  mov     r8, r14
0x18000e53e  mov     edx, 1
0x18000e543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e548  cmp     rax, r14
0x18000e54b  jz      short loc_18000E552
0x18000e54d  mov     ebx, 6
0x18000e552  mov     eax, ebx
0x18000e554  mov     rcx, [rsp+98h+var_40]
0x18000e559  xor     rcx, rsp; StackCookie
0x18000e55c  call    __security_check_cookie
0x18000e561  add     rsp, 70h
0x18000e565  pop     r14
0x18000e567  pop     rdi
0x18000e568  pop     rsi
0x18000e569  pop     rbp
0x18000e56a  pop     rbx
0x18000e56b  retn
```
