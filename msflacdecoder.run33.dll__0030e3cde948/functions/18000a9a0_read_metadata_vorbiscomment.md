# read_metadata_vorbiscomment_

- ea: `0x18000a9a0`
- end: `0x18000ac18`
- name: `read_metadata_vorbiscomment_`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800099d0`

## callees

- `0x1800028ac`
- `0x18000a9a0`
- `0x1800102f0`
- `0x180011660`
- `0x1800116a0`
- `0x180011e60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ab8f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000abae`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ab8f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000abae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000aa21`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ab1f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000aa21`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ab1f`

## pseudocode

```c
__int64 __fastcall read_metadata_vorbiscomment_(__int64 a1, unsigned int *a2, unsigned int a3)
{
  __int64 v6; // rcx
  unsigned __int64 v7; // rdi
  unsigned int v8; // ebp
  unsigned int *v9; // rsi
  void *v10; // rax
  __int64 v11; // rax
  unsigned int v12; // r14d
  __int64 v13; // rdi
  __int64 v14; // rax
  unsigned int v15; // ebp
  unsigned __int64 v16; // r12
  void *v17; // rax
  int byte_block_aligned_no_crc; // eax
  __int64 v19; // rdx

  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL);
  if ( a3 < 8 )
  {
    FLAC__bitreader_limit_invalidate(v6);
    return 0;
  }
  if ( (unsigned int)FLAC__bitreader_read_uint32_little_endian(v6) )
  {
    v7 = *a2;
    v8 = a3 - 8;
    if ( v8 < (unsigned int)v7 )
    {
      *a2 = 0;
      v9 = a2 + 4;
      *((_QWORD *)a2 + 1) = 0;
LABEL_27:
      if ( !v8 )
        return 1;
      if ( !*v9 )
      {
        free(*((void **)a2 + 3));
        *((_QWORD *)a2 + 3) = 0;
      }
LABEL_30:
      FLAC__bitreader_limit_invalidate(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL));
      return 0;
    }
    if ( v7 + 1 < v7 )
    {
      *((_QWORD *)a2 + 1) = 0;
      **(_DWORD **)a1 = 8;
      return 0;
    }
    v10 = malloc(v7 + 1);
    *((_QWORD *)a2 + 1) = v10;
    if ( !v10 )
    {
LABEL_15:
      **(_DWORD **)a1 = 8;
      return 0;
    }
    if ( !(unsigned int)FLAC__bitreader_read_byte_block_aligned_no_crc(
                          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                          v10,
                          *a2) )
      return 0;
    v9 = a2 + 4;
    *(_BYTE *)(*a2 + *((_QWORD *)a2 + 1)) = 0;
    if ( !(unsigned int)FLAC__bitreader_read_uint32_little_endian(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL)) )
      return 0;
    if ( *v9 > 0x186A0 )
    {
      *v9 = 0;
      return 0;
    }
    v8 -= v7;
    if ( !*v9 )
      goto LABEL_27;
    v11 = safe_malloc_mul_2op_p(*v9, 16);
    *((_QWORD *)a2 + 3) = v11;
    if ( !v11 )
    {
      *v9 = 0;
      goto LABEL_15;
    }
    v12 = 0;
    if ( !*v9 )
      goto LABEL_27;
    while ( 1 )
    {
      v13 = 16LL * v12;
      *(_DWORD *)(v13 + *((_QWORD *)a2 + 3)) = 0;
      *(_QWORD *)(v13 + *((_QWORD *)a2 + 3) + 8) = 0;
      if ( v8 < 4 )
        goto LABEL_26;
      if ( !(unsigned int)FLAC__bitreader_read_uint32_little_endian(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL)) )
        goto LABEL_35;
      v14 = *((_QWORD *)a2 + 3);
      v15 = v8 - 4;
      v16 = *(unsigned int *)(v13 + v14);
      if ( v15 < (unsigned int)v16 )
      {
        *v9 = v12;
        goto LABEL_30;
      }
      if ( v16 + 1 < v16 )
        break;
      v17 = malloc(v16 + 1);
      *(_QWORD *)(v13 + *((_QWORD *)a2 + 3) + 8) = v17;
      if ( !v17 )
        goto LABEL_34;
      v8 = v15 - v16;
      memset_0(*(void **)(v13 + *((_QWORD *)a2 + 3) + 8), 0, *(unsigned int *)(v13 + *((_QWORD *)a2 + 3)));
      byte_block_aligned_no_crc = FLAC__bitreader_read_byte_block_aligned_no_crc(
                                    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL),
                                    *(_QWORD *)(v13 + *((_QWORD *)a2 + 3) + 8),
                                    *(unsigned int *)(v13 + *((_QWORD *)a2 + 3)));
      v19 = *((_QWORD *)a2 + 3);
      if ( !byte_block_aligned_no_crc )
      {
        free(*(void **)(v13 + v19 + 8));
        *(_QWORD *)(v13 + *((_QWORD *)a2 + 3) + 8) = 0;
LABEL_26:
        *v9 = v12;
        goto LABEL_27;
      }
      ++v12;
      *(_BYTE *)(*(unsigned int *)(v13 + v19) + *(_QWORD *)(v13 + v19 + 8)) = 0;
      if ( v12 >= *v9 )
        goto LABEL_27;
    }
    *(_QWORD *)(v13 + v14 + 8) = 0;
LABEL_34:
    **(_DWORD **)a1 = 8;
LABEL_35:
    *v9 = v12;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a9a0  push    rbx
0x18000a9a2  push    rbp
0x18000a9a3  push    r15
0x18000a9a5  sub     rsp, 30h
0x18000a9a9  mov     rax, [rcx+8]
0x18000a9ad  mov     r15, rcx
0x18000a9b0  mov     ebp, r8d
0x18000a9b3  mov     rbx, rdx
0x18000a9b6  mov     rcx, [rax+58h]
0x18000a9ba  cmp     r8d, 8
0x18000a9be  jb      loc_18000AC08
0x18000a9c4  mov     [rsp+48h+arg_0], rsi
0x18000a9c9  mov     [rsp+48h+arg_8], rdi
0x18000a9ce  mov     [rsp+48h+arg_10], r12
0x18000a9d3  mov     [rsp+48h+var_20], r13
0x18000a9d8  mov     [rsp+48h+var_28], r14
0x18000a9dd  call    FLAC__bitreader_read_uint32_little_endian
0x18000a9e2  test    eax, eax
0x18000a9e4  jz      loc_18000ABC5
0x18000a9ea  mov     edi, [rbx]
0x18000a9ec  add     ebp, 0FFFFFFF8h
0x18000a9ef  xor     r13d, r13d
0x18000a9f2  cmp     ebp, edi
0x18000a9f4  jnb     short loc_18000AA06
0x18000a9f6  mov     [rbx], r13d
0x18000a9f9  lea     rsi, [rbx+10h]
0x18000a9fd  mov     [rbx+8], r13
0x18000aa01  jmp     loc_18000ABA1
0x18000aa06  lea     rcx, [rdi+1]; Size
0x18000aa0a  cmp     rcx, rdi
0x18000aa0d  jnb     short loc_18000AA21
0x18000aa0f  mov     [rbx+8], r13
0x18000aa13  mov     rax, [r15]
0x18000aa16  mov     dword ptr [rax], 8
0x18000aa1c  jmp     loc_18000ABC5
0x18000aa21  call    cs:__imp_malloc
0x18000aa27  mov     [rbx+8], rax
0x18000aa2b  test    rax, rax
0x18000aa2e  jz      short loc_18000AAA5
0x18000aa30  mov     rcx, [r15+8]
0x18000aa34  mov     rdx, rax
0x18000aa37  mov     r8d, [rbx]
0x18000aa3a  mov     rcx, [rcx+58h]
0x18000aa3e  call    FLAC__bitreader_read_byte_block_aligned_no_crc
0x18000aa43  test    eax, eax
0x18000aa45  jz      loc_18000ABC5
0x18000aa4b  mov     ecx, [rbx]
0x18000aa4d  lea     rsi, [rbx+10h]
0x18000aa51  mov     rax, [rbx+8]
0x18000aa55  mov     rdx, rsi
0x18000aa58  mov     [rcx+rax], r13b
0x18000aa5c  mov     rcx, [r15+8]
0x18000aa60  mov     rcx, [rcx+58h]
0x18000aa64  call    FLAC__bitreader_read_uint32_little_endian
0x18000aa69  test    eax, eax
0x18000aa6b  jz      loc_18000ABC5
0x18000aa71  mov     eax, [rsi]
0x18000aa73  cmp     eax, 186A0h
0x18000aa78  jbe     short loc_18000AA82
0x18000aa7a  mov     [rsi], r13d
0x18000aa7d  jmp     loc_18000ABC5
0x18000aa82  sub     ebp, edi
0x18000aa84  test    eax, eax
0x18000aa86  jz      loc_18000ABA1
0x18000aa8c  mov     rcx, rax
0x18000aa8f  mov     edx, 10h
0x18000aa94  call    safe_malloc_mul_2op_p
0x18000aa99  mov     [rbx+18h], rax
0x18000aa9d  test    rax, rax
0x18000aaa0  jnz     short loc_18000AAB3
0x18000aaa2  mov     [rsi], r13d
0x18000aaa5  mov     rax, [r15]
0x18000aaa8  mov     dword ptr [rax], 8
0x18000aaae  jmp     loc_18000ABC5
0x18000aab3  mov     r14d, r13d
0x18000aab6  cmp     [rsi], r13d
0x18000aab9  jbe     loc_18000ABA1
0x18000aabf  nop
0x18000aac0  mov     rax, [rbx+18h]
0x18000aac4  mov     edi, r14d
0x18000aac7  shl     rdi, 4
0x18000aacb  mov     [rdi+rax], r13d
0x18000aacf  mov     rax, [rbx+18h]
0x18000aad3  mov     [rdi+rax+8], r13
0x18000aad8  cmp     ebp, 4
0x18000aadb  jb      loc_18000AB9E
0x18000aae1  mov     rcx, [r15+8]
0x18000aae5  mov     rdx, [rbx+18h]
0x18000aae9  add     rdx, rdi
0x18000aaec  mov     rcx, [rcx+58h]
0x18000aaf0  call    FLAC__bitreader_read_uint32_little_endian
0x18000aaf5  test    eax, eax
0x18000aaf7  jz      loc_18000ABF7
0x18000aafd  mov     rax, [rbx+18h]
0x18000ab01  add     ebp, 0FFFFFFFCh
0x18000ab04  mov     r12d, [rdi+rax]
0x18000ab08  cmp     ebp, r12d
0x18000ab0b  jb      loc_18000ABFC
0x18000ab11  lea     rcx, [r12+1]; Size
0x18000ab16  cmp     rcx, r12
0x18000ab19  jb      loc_18000ABE9
0x18000ab1f  call    cs:__imp_malloc
0x18000ab25  mov     rcx, [rbx+18h]
0x18000ab29  mov     [rdi+rcx+8], rax
0x18000ab2e  test    rax, rax
0x18000ab31  jz      loc_18000ABEE
0x18000ab37  mov     rax, [rbx+18h]
0x18000ab3b  xor     edx, edx; Val
0x18000ab3d  sub     ebp, r12d
0x18000ab40  mov     r8d, [rdi+rax]; Size
0x18000ab44  mov     rcx, [rdi+rax+8]; void *
0x18000ab49  call    memset_0
0x18000ab4e  mov     rax, [rbx+18h]
0x18000ab52  mov     rcx, [r15+8]
0x18000ab56  mov     r8d, [rdi+rax]
0x18000ab5a  mov     rdx, [rdi+rax+8]
0x18000ab5f  mov     rcx, [rcx+58h]
0x18000ab63  call    FLAC__bitreader_read_byte_block_aligned_no_crc
0x18000ab68  mov     rdx, [rbx+18h]
0x18000ab6c  test    eax, eax
0x18000ab6e  jz      short loc_18000AB8A
0x18000ab70  mov     ecx, [rdi+rdx]
0x18000ab73  inc     r14d
0x18000ab76  mov     rax, [rdi+rdx+8]
0x18000ab7b  mov     [rcx+rax], r13b
0x18000ab7f  cmp     r14d, [rsi]
0x18000ab82  jb      loc_18000AAC0
0x18000ab88  jmp     short loc_18000ABA1
0x18000ab8a  mov     rcx, [rdi+rdx+8]; Block
0x18000ab8f  call    cs:__imp_free
0x18000ab95  mov     rax, [rbx+18h]
0x18000ab99  mov     [rdi+rax+8], r13
0x18000ab9e  mov     [rsi], r14d
0x18000aba1  test    ebp, ebp
0x18000aba3  jz      short loc_18000AC01
0x18000aba5  cmp     dword ptr [rsi], 1
0x18000aba8  jnb     short loc_18000ABB8
0x18000abaa  mov     rcx, [rbx+18h]; Block
0x18000abae  call    cs:__imp_free
0x18000abb4  mov     [rbx+18h], r13
0x18000abb8  mov     rcx, [r15+8]
0x18000abbc  mov     rcx, [rcx+58h]
0x18000abc0  call    FLAC__bitreader_limit_invalidate
0x18000abc5  xor     eax, eax
0x18000abc7  mov     r13, [rsp+48h+var_20]
0x18000abcc  mov     r12, [rsp+48h+arg_10]
0x18000abd1  mov     rdi, [rsp+48h+arg_8]
0x18000abd6  mov     rsi, [rsp+48h+arg_0]
0x18000abdb  mov     r14, [rsp+48h+var_28]
0x18000abe0  add     rsp, 30h
0x18000abe4  pop     r15
0x18000abe6  pop     rbp
0x18000abe7  pop     rbx
0x18000abe8  retn
0x18000abe9  mov     [rdi+rax+8], r13
0x18000abee  mov     rax, [r15]
0x18000abf1  mov     dword ptr [rax], 8
0x18000abf7  mov     [rsi], r14d
0x18000abfa  jmp     short loc_18000ABC5
0x18000abfc  mov     [rsi], r14d
0x18000abff  jmp     short loc_18000ABB8
0x18000ac01  mov     eax, 1
0x18000ac06  jmp     short loc_18000ABC7
0x18000ac08  call    FLAC__bitreader_limit_invalidate
0x18000ac0d  xor     eax, eax
0x18000ac0f  add     rsp, 30h
0x18000ac13  pop     r15
0x18000ac15  pop     rbp
0x18000ac16  pop     rbx
0x18000ac17  retn
```
