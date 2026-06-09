# read_metadata_block_data_cuesheet_track_cb_

- ea: `0x18000e770`
- end: `0x18000ea8a`
- name: `read_metadata_block_data_cuesheet_track_cb_`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e590`

## callees

- `0x180001e80`
- `0x18000e770`
- `0x180056010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000ea4f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000ea4f`

## pseudocode

```c
__int64 __fastcall read_metadata_block_data_cuesheet_track_cb_(
        __int64 a1,
        __int64 (__fastcall *a2)(_BYTE *, __int64, unsigned __int64, __int64),
        __int64 a3)
{
  unsigned int v4; // edi
  __int64 v7; // rcx
  unsigned __int8 *v8; // rdx
  unsigned int i; // r8d
  __int64 v10; // rax
  unsigned int v11; // edi
  char v12; // cl
  char *v13; // rdx
  unsigned int j; // r8d
  char v15; // al
  unsigned int v16; // ecx
  unsigned int v17; // edi
  unsigned __int8 v18; // cl
  unsigned __int8 *v19; // rdx
  unsigned int k; // r8d
  unsigned __int8 v21; // al
  unsigned int v22; // esi
  unsigned int v23; // edi
  __int64 v24; // rax
  unsigned __int8 *v25; // rdx
  unsigned int m; // r8d
  __int64 v27; // rcx
  unsigned int v28; // edi
  char v29; // cl
  char *v30; // rdx
  unsigned int n; // r8d
  char v32; // al
  void *v34; // rax
  _BYTE v35[32]; // [rsp+30h] [rbp-68h] BYREF

  v4 = (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_OFFSET_LEN >> 3;
  if ( a2(v35, 1, (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_OFFSET_LEN >> 3, a1) == (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_OFFSET_LEN >> 3 )
  {
    v7 = 0;
    v8 = v35;
    for ( i = 0; i < v4; v7 = v10 | (v7 << 8) )
    {
      v10 = *v8++;
      ++i;
    }
    *(_QWORD *)a3 = v7;
    v11 = (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_NUMBER_LEN >> 3;
    if ( a2(v35, 1, (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_NUMBER_LEN >> 3, a1) == (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_NUMBER_LEN >> 3 )
    {
      v12 = 0;
      v13 = v35;
      for ( j = 0; j < v11; v12 = v15 )
      {
        v15 = *v13++;
        ++j;
      }
      *(_BYTE *)(a3 + 8) = v12;
      if ( a2(
             (_BYTE *)(a3 + 9),
             1,
             (unsigned __int64)(unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_ISRC_LEN >> 3,
             a1) == (unsigned __int64)(unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_ISRC_LEN >> 3
        && a2(
             v35,
             1,
             (unsigned __int64)(unsigned int)(FLAC__STREAM_METADATA_CUESHEET_TRACK_TYPE_LEN
                                            + FLAC__STREAM_METADATA_CUESHEET_TRACK_PRE_EMPHASIS_LEN
                                            + FLAC__STREAM_METADATA_CUESHEET_TRACK_RESERVED_LEN) >> 3,
             a1) == (unsigned __int64)(unsigned int)(FLAC__STREAM_METADATA_CUESHEET_TRACK_TYPE_LEN
                                                   + FLAC__STREAM_METADATA_CUESHEET_TRACK_PRE_EMPHASIS_LEN
                                                   + FLAC__STREAM_METADATA_CUESHEET_TRACK_RESERVED_LEN) >> 3 )
      {
        v16 = *(_DWORD *)(a3 + 24) & 0xFFFFFFFE | (v35[0] >> 7);
        *(_DWORD *)(a3 + 24) = v16 ^ ((unsigned __int8)v16 ^ (v35[0] >> 5)) & 2;
        v17 = (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_NUM_INDICES_LEN >> 3;
        if ( a2(v35, 1, (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_NUM_INDICES_LEN >> 3, a1) == (unsigned int)FLAC__STREAM_METADATA_CUESHEET_TRACK_NUM_INDICES_LEN >> 3 )
        {
          v18 = 0;
          v19 = v35;
          for ( k = 0; k < v17; v18 = v21 )
          {
            v21 = *v19++;
            ++k;
          }
          *(_BYTE *)(a3 + 28) = v18;
          if ( v18 )
          {
            v34 = calloc(v18, 0x10u);
            *(_QWORD *)(a3 + 32) = v34;
            if ( !v34 )
              return 11;
          }
          else
          {
            *(_QWORD *)(a3 + 32) = 0;
          }
          v22 = 0;
          if ( !*(_BYTE *)(a3 + 28) )
            return 0;
          while ( 1 )
          {
            v23 = (unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_OFFSET_LEN >> 3;
            if ( a2(v35, 1, (unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_OFFSET_LEN >> 3, a1) != (unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_OFFSET_LEN >> 3 )
              break;
            v24 = 0;
            v25 = v35;
            for ( m = 0; m < v23; v24 = v27 | (v24 << 8) )
            {
              v27 = *v25++;
              ++m;
            }
            *(_QWORD *)(*(_QWORD *)(a3 + 32) + 16LL * v22) = v24;
            v28 = (unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_NUMBER_LEN >> 3;
            if ( a2(v35, 1, (unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_NUMBER_LEN >> 3, a1) != (unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_NUMBER_LEN >> 3 )
              break;
            v29 = 0;
            v30 = v35;
            for ( n = 0; n < v28; v29 = v32 )
            {
              v32 = *v30++;
              ++n;
            }
            *(_BYTE *)(*(_QWORD *)(a3 + 32) + 16LL * v22 + 8) = v29;
            if ( a2(v35, 1, (unsigned __int64)(unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_RESERVED_LEN >> 3, a1) != (unsigned __int64)(unsigned int)FLAC__STREAM_METADATA_CUESHEET_INDEX_RESERVED_LEN >> 3 )
              break;
            if ( ++v22 >= *(unsigned __int8 *)(a3 + 28) )
              return 0;
          }
        }
      }
    }
  }
  return 6;
}

```

## disassembly

```asm
0x18000e770  push    rbx
0x18000e772  push    rbp
0x18000e773  push    rsi
0x18000e774  push    rdi
0x18000e775  push    r12
0x18000e777  push    r14
0x18000e779  push    r15
0x18000e77b  sub     rsp, 60h
0x18000e77f  mov     rax, cs:__security_cookie
0x18000e786  xor     rax, rsp
0x18000e789  mov     [rsp+98h+var_48], rax
0x18000e78e  mov     edi, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_OFFSET_LEN
0x18000e794  mov     r12, rdx
0x18000e797  shr     edi, 3
0x18000e79a  mov     r14, r8
0x18000e79d  mov     rbp, rcx
0x18000e7a0  mov     r8d, edi
0x18000e7a3  mov     r9, rcx
0x18000e7a6  mov     ebx, edi
0x18000e7a8  mov     edx, 1
0x18000e7ad  lea     rcx, [rsp+98h+var_68]
0x18000e7b2  mov     rax, r12
0x18000e7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7ba  cmp     rax, rbx
0x18000e7bd  jnz     loc_18000EA69
0x18000e7c3  xor     ecx, ecx
0x18000e7c5  lea     rdx, [rsp+98h+var_68]
0x18000e7ca  xor     r8d, r8d
0x18000e7cd  test    edi, edi
0x18000e7cf  jz      short loc_18000E7E7
0x18000e7d1  movzx   eax, byte ptr [rdx]
0x18000e7d4  lea     rdx, [rdx+1]
0x18000e7d8  shl     rcx, 8
0x18000e7dc  inc     r8d
0x18000e7df  or      rcx, rax
0x18000e7e2  cmp     r8d, edi
0x18000e7e5  jb      short loc_18000E7D1
0x18000e7e7  mov     [r14], rcx
0x18000e7ea  mov     r9, rbp
0x18000e7ed  mov     edi, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_NUMBER_LEN
0x18000e7f3  lea     rcx, [rsp+98h+var_68]
0x18000e7f8  shr     edi, 3
0x18000e7fb  mov     edx, 1
0x18000e800  mov     r8d, edi
0x18000e803  mov     rax, r12
0x18000e806  mov     ebx, edi
0x18000e808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e80d  cmp     rax, rbx
0x18000e810  jnz     loc_18000EA69
0x18000e816  xor     ecx, ecx
0x18000e818  lea     rdx, [rsp+98h+var_68]
0x18000e81d  xor     r8d, r8d
0x18000e820  test    edi, edi
0x18000e822  jz      short loc_18000E844
0x18000e824  nop     dword ptr [rax+00h]
0x18000e828  nop     dword ptr [rax+rax+00000000h]
0x18000e830  movzx   eax, byte ptr [rdx]
0x18000e833  lea     rdx, [rdx+1]
0x18000e837  shl     ecx, 8
0x18000e83a  inc     r8d
0x18000e83d  or      ecx, eax
0x18000e83f  cmp     r8d, edi
0x18000e842  jb      short loc_18000E830
0x18000e844  mov     [r14+8], cl
0x18000e848  mov     r9, rbp
0x18000e84b  mov     ebx, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_ISRC_LEN
0x18000e851  lea     rcx, [r14+9]
0x18000e855  shr     rbx, 3
0x18000e859  mov     edx, 1
0x18000e85e  mov     r8, rbx
0x18000e861  mov     rax, r12
0x18000e864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e869  cmp     rax, rbx
0x18000e86c  jnz     loc_18000EA69
0x18000e872  mov     ebx, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_RESERVED_LEN
0x18000e878  lea     rcx, [rsp+98h+var_68]
0x18000e87d  add     ebx, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_PRE_EMPHASIS_LEN
0x18000e883  mov     r9, rbp
0x18000e886  add     ebx, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_TYPE_LEN
0x18000e88c  mov     edx, 1
0x18000e891  shr     rbx, 3
0x18000e895  mov     rax, r12
0x18000e898  mov     r8, rbx
0x18000e89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a0  cmp     rax, rbx
0x18000e8a3  jnz     loc_18000EA69
0x18000e8a9  movzx   edx, [rsp+98h+var_68]
0x18000e8ae  mov     r9, rbp
0x18000e8b1  mov     eax, [r14+18h]
0x18000e8b5  mov     ecx, edx
0x18000e8b7  shr     edx, 5
0x18000e8ba  and     eax, 0FFFFFFFEh
0x18000e8bd  shr     ecx, 7
0x18000e8c0  or      ecx, eax
0x18000e8c2  mov     rax, r12
0x18000e8c5  xor     edx, ecx
0x18000e8c7  and     edx, 2
0x18000e8ca  xor     edx, ecx
0x18000e8cc  lea     rcx, [rsp+98h+var_68]
0x18000e8d1  mov     [r14+18h], edx
0x18000e8d5  mov     edx, 1
0x18000e8da  mov     edi, cs:FLAC__STREAM_METADATA_CUESHEET_TRACK_NUM_INDICES_LEN
0x18000e8e0  shr     edi, 3
0x18000e8e3  mov     r8d, edi
0x18000e8e6  mov     ebx, edi
0x18000e8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ed  cmp     rax, rbx
0x18000e8f0  jnz     loc_18000EA69
0x18000e8f6  xor     ecx, ecx
0x18000e8f8  lea     rdx, [rsp+98h+var_68]
0x18000e8fd  xor     r8d, r8d
0x18000e900  test    edi, edi
0x18000e902  jz      short loc_18000E924
0x18000e904  nop     dword ptr [rax+00h]
0x18000e908  nop     dword ptr [rax+rax+00000000h]
0x18000e910  movzx   eax, byte ptr [rdx]
0x18000e913  lea     rdx, [rdx+1]
0x18000e917  shl     ecx, 8
0x18000e91a  inc     r8d
0x18000e91d  or      ecx, eax
0x18000e91f  cmp     r8d, edi
0x18000e922  jb      short loc_18000E910
0x18000e924  mov     [r14+1Ch], cl
0x18000e928  test    cl, cl
0x18000e92a  jnz     loc_18000EA47
0x18000e930  mov     qword ptr [r14+20h], 0
0x18000e938  xor     esi, esi
0x18000e93a  cmp     [r14+1Ch], sil
0x18000e93e  jbe     loc_18000EA43
0x18000e944  nop     dword ptr [rax+00h]
0x18000e948  nop     dword ptr [rax+rax+00000000h]
0x18000e950  mov     edi, cs:FLAC__STREAM_METADATA_CUESHEET_INDEX_OFFSET_LEN
0x18000e956  lea     rcx, [rsp+98h+var_68]
0x18000e95b  shr     edi, 3
0x18000e95e  mov     r9, rbp
0x18000e961  mov     r8d, edi
0x18000e964  mov     edx, 1
0x18000e969  mov     rax, r12
0x18000e96c  mov     ebx, edi
0x18000e96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e973  cmp     rax, rbx
0x18000e976  jnz     loc_18000EA69
0x18000e97c  xor     eax, eax
0x18000e97e  lea     rdx, [rsp+98h+var_68]
0x18000e983  xor     r8d, r8d
0x18000e986  test    edi, edi
0x18000e988  jz      short loc_18000E9A6
0x18000e98a  nop     word ptr [rax+rax+00h]
0x18000e990  movzx   ecx, byte ptr [rdx]
0x18000e993  lea     rdx, [rdx+1]
0x18000e997  shl     rax, 8
0x18000e99b  inc     r8d
0x18000e99e  or      rax, rcx
0x18000e9a1  cmp     r8d, edi
0x18000e9a4  jb      short loc_18000E990
0x18000e9a6  mov     rcx, [r14+20h]
0x18000e9aa  mov     r9, rbp
0x18000e9ad  mov     r15d, esi
0x18000e9b0  mov     edx, 1
0x18000e9b5  add     r15, r15
0x18000e9b8  mov     [rcx+r15*8], rax
0x18000e9bc  lea     rcx, [rsp+98h+var_68]
0x18000e9c1  mov     edi, cs:FLAC__STREAM_METADATA_CUESHEET_INDEX_NUMBER_LEN
0x18000e9c7  mov     rax, r12
0x18000e9ca  shr     edi, 3
0x18000e9cd  mov     r8d, edi
0x18000e9d0  mov     ebx, edi
0x18000e9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d7  cmp     rax, rbx
0x18000e9da  jnz     loc_18000EA69
0x18000e9e0  xor     ecx, ecx
0x18000e9e2  lea     rdx, [rsp+98h+var_68]
0x18000e9e7  xor     r8d, r8d
0x18000e9ea  test    edi, edi
0x18000e9ec  jz      short loc_18000EA04
0x18000e9ee  xchg    ax, ax
0x18000e9f0  movzx   eax, byte ptr [rdx]
0x18000e9f3  lea     rdx, [rdx+1]
0x18000e9f7  shl     ecx, 8
0x18000e9fa  inc     r8d
0x18000e9fd  or      ecx, eax
0x18000e9ff  cmp     r8d, edi
0x18000ea02  jb      short loc_18000E9F0
0x18000ea04  mov     rax, [r14+20h]
0x18000ea08  mov     r9, rbp
0x18000ea0b  mov     edx, 1
0x18000ea10  mov     [rax+r15*8+8], cl
0x18000ea15  lea     rcx, [rsp+98h+var_68]
0x18000ea1a  mov     ebx, cs:FLAC__STREAM_METADATA_CUESHEET_INDEX_RESERVED_LEN
0x18000ea20  mov     rax, r12
0x18000ea23  shr     rbx, 3
0x18000ea27  mov     r8, rbx
0x18000ea2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea2f  cmp     rax, rbx
0x18000ea32  jnz     short loc_18000EA69
0x18000ea34  movzx   eax, byte ptr [r14+1Ch]
0x18000ea39  inc     esi
0x18000ea3b  cmp     esi, eax
0x18000ea3d  jb      loc_18000E950
0x18000ea43  xor     eax, eax
0x18000ea45  jmp     short loc_18000EA6E
0x18000ea47  movzx   ecx, cl; Count
0x18000ea4a  mov     edx, 10h; Size
0x18000ea4f  call    cs:__imp_calloc
0x18000ea55  mov     [r14+20h], rax
0x18000ea59  test    rax, rax
0x18000ea5c  jnz     loc_18000E938
0x18000ea62  mov     eax, 0Bh
0x18000ea67  jmp     short loc_18000EA6E
0x18000ea69  mov     eax, 6
0x18000ea6e  mov     rcx, [rsp+98h+var_48]
0x18000ea73  xor     rcx, rsp; StackCookie
0x18000ea76  call    __security_check_cookie
0x18000ea7b  add     rsp, 60h
0x18000ea7f  pop     r15
0x18000ea81  pop     r14
0x18000ea83  pop     r12
0x18000ea85  pop     rdi
0x18000ea86  pop     rsi
0x18000ea87  pop     rbp
0x18000ea88  pop     rbx
0x18000ea89  retn
```
