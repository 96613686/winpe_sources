# FLAC__metadata_object_vorbiscomment_append_comment

- ea: `0x180004db0`
- end: `0x180004eef`
- name: `FLAC__metadata_object_vorbiscomment_append_comment`
- size: `319`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003490`
- `0x180005100`

## callees

- `0x180004db0`
- `0x1800052c0`
- `0x180005610`
- `0x1800057f0`
- `0x18000cdc0`
- `0x180016b24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004ec6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004ec6`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180004ea6`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180004ea6`

## pseudocode

```c
__int64 __fastcall FLAC__metadata_object_vorbiscomment_append_comment(__int64 a1, unsigned int *a2, int a3)
{
  __int64 v3; // rbp
  unsigned __int64 v5; // r14
  unsigned int v7; // ebx
  __int64 v8; // r15
  int v10; // edx
  __int64 v11; // r9
  __int128 v12; // xmm6
  __int64 v13; // rax
  __int64 v14; // rsi
  void *v15; // r15
  __int64 v16; // rax
  __int128 v17; // [rsp+20h] [rbp-58h] BYREF

  v3 = *((_QWORD *)a2 + 1);
  v5 = *a2;
  v7 = a2[1];
  v8 = *(unsigned int *)(a1 + 32);
  if ( !(unsigned int)FLAC__format_vorbiscomment_entry_is_legal(v3, v5)
    || !(unsigned int)FLAC__metadata_object_vorbiscomment_resize_comments(a1, (unsigned int)(*(_DWORD *)(a1 + 32) + 1)) )
  {
    return 0;
  }
  v10 = *(_DWORD *)(a1 + 32);
  v11 = *(_QWORD *)(a1 + 40);
  v12 = *(_OWORD *)(v11 + 16LL * (unsigned int)(v10 - 1));
  memmove_0(
    (void *)(v11 + 16LL * (unsigned int)(v8 + 1)),
    (const void *)(16 * v8 + v11),
    16LL * (unsigned int)(v10 + ~(_DWORD)v8));
  v13 = *(_QWORD *)(a1 + 40);
  *(_QWORD *)&v17 = __PAIR64__(v7, v5);
  *((_QWORD *)&v17 + 1) = v3;
  *(_OWORD *)(v13 + 16 * v8) = v12;
  if ( !(unsigned int)FLAC__format_vorbiscomment_entry_is_legal(v3, (unsigned int)v5) )
    return 0;
  v14 = *(_QWORD *)(a1 + 40) + 16 * v8;
  v15 = *(void **)(v14 + 8);
  if ( !v3 )
  {
LABEL_12:
    *(_OWORD *)v14 = v17;
    goto LABEL_13;
  }
  if ( !a3 )
  {
    if ( v5 + 1 < v5 )
      return 0;
    v16 = _o_realloc(v3, v5 + 1);
    if ( !v16 )
      return 0;
    *(_BYTE *)(v5 + v16) = 0;
    *((_QWORD *)&v17 + 1) = v16;
    goto LABEL_12;
  }
  if ( !(unsigned int)copy_vcentry_(v14, (const void **)&v17) )
    return 0;
LABEL_13:
  free(v15);
  vorbiscomment_calculate_length_(a1);
  return 1;
}

```

## disassembly

```asm
0x180004db0  push    rbx
0x180004db2  push    rbp
0x180004db3  push    rdi
0x180004db4  push    r12
0x180004db6  push    r14
0x180004db8  push    r15
0x180004dba  sub     rsp, 48h
0x180004dbe  mov     rbp, [rdx+8]
0x180004dc2  mov     rdi, rcx
0x180004dc5  mov     r14d, [rdx]
0x180004dc8  mov     r12d, r8d
0x180004dcb  mov     ebx, [rdx+4]
0x180004dce  mov     edx, r14d
0x180004dd1  mov     r15d, [rcx+20h]
0x180004dd5  mov     rcx, rbp
0x180004dd8  call    FLAC__format_vorbiscomment_entry_is_legal
0x180004ddd  test    eax, eax
0x180004ddf  jnz     short loc_180004DF1
0x180004de1  xor     eax, eax
0x180004de3  add     rsp, 48h
0x180004de7  pop     r15
0x180004de9  pop     r14
0x180004deb  pop     r12
0x180004ded  pop     rdi
0x180004dee  pop     rbp
0x180004def  pop     rbx
0x180004df0  retn
0x180004df1  mov     edx, [rdi+20h]
0x180004df4  mov     rcx, rdi
0x180004df7  inc     edx
0x180004df9  call    FLAC__metadata_object_vorbiscomment_resize_comments
0x180004dfe  test    eax, eax
0x180004e00  jz      short loc_180004DE1
0x180004e02  mov     edx, [rdi+20h]
0x180004e05  mov     r8d, r15d
0x180004e08  mov     r9, [rdi+28h]
0x180004e0c  not     r8d
0x180004e0f  mov     [rsp+78h+arg_0], rsi
0x180004e17  add     r8d, edx
0x180004e1a  movaps  [rsp+78h+var_48], xmm6
0x180004e1f  mov     rsi, r15
0x180004e22  lea     ecx, [rdx-1]
0x180004e25  shl     rsi, 4
0x180004e29  add     rcx, rcx
0x180004e2c  shl     r8, 4; Size
0x180004e30  lea     rdx, [rsi+r9]; Src
0x180004e34  movups  xmm6, xmmword ptr [r9+rcx*8]
0x180004e39  lea     ecx, [r15+1]
0x180004e3d  shl     rcx, 4
0x180004e41  add     rcx, r9; void *
0x180004e44  call    memmove_0
0x180004e49  mov     rax, [rdi+28h]
0x180004e4d  mov     edx, r14d
0x180004e50  mov     rcx, rbp
0x180004e53  mov     dword ptr [rsp+78h+var_58], r14d
0x180004e58  mov     dword ptr [rsp+78h+var_58+4], ebx
0x180004e5c  mov     qword ptr [rsp+78h+var_58+8], rbp
0x180004e61  movups  xmmword ptr [rax+rsi], xmm6
0x180004e65  call    FLAC__format_vorbiscomment_entry_is_legal
0x180004e6a  movaps  xmm6, [rsp+78h+var_48]
0x180004e6f  test    eax, eax
0x180004e71  jz      short loc_180004E96
0x180004e73  add     rsi, [rdi+28h]
0x180004e77  mov     r15, [rsi+8]
0x180004e7b  test    rbp, rbp
0x180004e7e  jz      short loc_180004EBB
0x180004e80  test    r12d, r12d
0x180004e83  jz      short loc_180004E9A
0x180004e85  lea     rdx, [rsp+78h+var_58]
0x180004e8a  mov     rcx, rsi
0x180004e8d  call    copy_vcentry_
0x180004e92  test    eax, eax
0x180004e94  jnz     short loc_180004EC3
0x180004e96  xor     eax, eax
0x180004e98  jmp     short loc_180004ED9
0x180004e9a  lea     rdx, [r14+1]
0x180004e9e  cmp     rdx, r14
0x180004ea1  jb      short loc_180004E96
0x180004ea3  mov     rcx, rbp
0x180004ea6  call    cs:__imp__o_realloc
0x180004eac  test    rax, rax
0x180004eaf  jz      short loc_180004E96
0x180004eb1  mov     byte ptr [r14+rax], 0
0x180004eb6  mov     qword ptr [rsp+78h+var_58+8], rax
0x180004ebb  movaps  xmm0, [rsp+78h+var_58]
0x180004ec0  movups  xmmword ptr [rsi], xmm0
0x180004ec3  mov     rcx, r15; Block
0x180004ec6  call    cs:__imp_free
0x180004ecc  mov     rcx, rdi
0x180004ecf  call    vorbiscomment_calculate_length_
0x180004ed4  mov     eax, 1
0x180004ed9  mov     rsi, [rsp+78h+arg_0]
0x180004ee1  add     rsp, 48h
0x180004ee5  pop     r15
0x180004ee7  pop     r14
0x180004ee9  pop     r12
0x180004eeb  pop     rdi
0x180004eec  pop     rbp
0x180004eed  pop     rbx
0x180004eee  retn
```
