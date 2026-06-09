# FLAC__metadata_object_vorbiscomment_replace_comment

- ea: `0x180005100`
- end: `0x1800052ba`
- name: `FLAC__metadata_object_vorbiscomment_replace_comment`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003a80`

## callees

- `0x180004db0`
- `0x180004f00`
- `0x180005100`
- `0x180005610`
- `0x1800057f0`
- `0x1800058c0`
- `0x18000cdc0`
- `0x180016b00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000521d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000521d`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800051f4`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800051f4`

## pseudocode

```c
__int64 __fastcall FLAC__metadata_object_vorbiscomment_replace_comment(
        __int64 a1,
        unsigned int *a2,
        int a3,
        unsigned int a4)
{
  const void *v4; // rbp
  unsigned int v6; // esi
  void *v9; // rax
  unsigned int v10; // esi
  int entry_from; // r15d
  __m128i v12; // xmm0
  const void *v13; // r13
  __int64 v14; // rbp
  void *v15; // rax
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  __int128 v19; // xmm0
  __int64 v20; // rdx
  __int64 v21; // rbp
  int v22; // ebx
  unsigned __int32 v23; // [rsp+20h] [rbp-58h]
  _OWORD v24[4]; // [rsp+30h] [rbp-48h] BYREF
  void *Block; // [rsp+88h] [rbp+10h]

  v4 = (const void *)*((_QWORD *)a2 + 1);
  v6 = *a2;
  if ( !(unsigned int)FLAC__format_vorbiscomment_entry_is_legal(v4, *a2) )
    return 0;
  v9 = memchr_0(v4, 61, v6);
  if ( !v9 )
    return 0;
  v10 = (_DWORD)v9 - (_DWORD)v4;
  entry_from = vorbiscomment_find_entry_from_(a1, 0, v4, (unsigned int)((_DWORD)v9 - (_DWORD)v4));
  v12 = *(__m128i *)a2;
  v24[0] = *(_OWORD *)a2;
  if ( entry_from < 0 )
    return FLAC__metadata_object_vorbiscomment_append_comment(a1, v24, a4);
  v23 = v12.m128i_i32[0];
  v13 = v4;
  if ( !(unsigned int)FLAC__format_vorbiscomment_entry_is_legal(v4, (unsigned int)_mm_cvtsi128_si32(v12)) )
    return 0;
  v14 = 16LL * (unsigned int)entry_from + *(_QWORD *)(a1 + 40);
  v15 = *(void **)(v14 + 8);
  Block = v15;
  if ( v13 )
  {
    if ( a4 )
    {
      if ( !(unsigned int)copy_vcentry_(v14, (const void **)v24) )
        return 0;
    }
    else
    {
      v17 = v12.m128i_u32[0] + 1LL;
      if ( v17 < v12.m128i_u32[0] )
        return 0;
      v18 = _o_realloc(v13, v17);
      if ( !v18 )
        return 0;
      *((_QWORD *)&v24[0] + 1) = v18;
      v19 = v24[0];
      *(_BYTE *)(v23 + v18) = 0;
      *(_OWORD *)v14 = v19;
    }
    v15 = Block;
  }
  else
  {
    *(_OWORD *)v14 = *(_OWORD *)a2;
  }
  free(v15);
  vorbiscomment_calculate_length_(a1);
  *(_OWORD *)a2 = *(_OWORD *)(*(_QWORD *)(a1 + 40) + 16LL * (unsigned int)entry_from);
  if ( a3 )
  {
    v20 = (unsigned int)(entry_from + 1);
    if ( (unsigned int)v20 < *(_DWORD *)(a1 + 32) )
    {
      v21 = *((_QWORD *)a2 + 1);
      v22 = vorbiscomment_find_entry_from_(a1, v20, v21, v10);
      if ( v22 >= 0 )
      {
        while ( (unsigned int)FLAC__metadata_object_vorbiscomment_delete_comment(a1, (unsigned int)v22) )
        {
          if ( (unsigned int)v22 < *(_DWORD *)(a1 + 32) )
          {
            v22 = vorbiscomment_find_entry_from_(a1, (unsigned int)v22, v21, v10);
            if ( v22 >= 0 )
              continue;
          }
          return 1;
        }
        return 0;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180005100  mov     [rsp+arg_0], rbx
0x180005105  mov     [rsp+arg_10], r8d
0x18000510a  push    rbp
0x18000510b  push    rsi
0x18000510c  push    rdi
0x18000510d  push    r12
0x18000510f  push    r13
0x180005111  push    r14
0x180005113  push    r15
0x180005115  sub     rsp, 40h
0x180005119  mov     rbp, [rdx+8]
0x18000511d  mov     rbx, rdx
0x180005120  mov     esi, [rdx]
0x180005122  mov     rdi, rcx
0x180005125  mov     edx, esi
0x180005127  mov     rcx, rbp
0x18000512a  mov     r14d, r9d
0x18000512d  call    FLAC__format_vorbiscomment_entry_is_legal
0x180005132  test    eax, eax
0x180005134  jz      loc_1800051C9
0x18000513a  mov     r8d, esi; MaxCount
0x18000513d  mov     edx, 3Dh ; '='; Val
0x180005142  mov     rcx, rbp; Buf
0x180005145  call    memchr_0
0x18000514a  mov     rsi, rax
0x18000514d  test    rax, rax
0x180005150  jz      short loc_1800051C9
0x180005152  sub     esi, ebp
0x180005154  mov     r8, rbp
0x180005157  mov     r9d, esi
0x18000515a  xor     edx, edx
0x18000515c  mov     rcx, rdi
0x18000515f  call    vorbiscomment_find_entry_from_
0x180005164  mov     r15d, eax
0x180005167  movups  xmm0, xmmword ptr [rbx]
0x18000516a  movaps  [rsp+78h+var_48], xmm0
0x18000516f  test    eax, eax
0x180005171  js      loc_1800052A5
0x180005177  movd    edx, xmm0
0x18000517b  mov     rcx, rbp
0x18000517e  movss   [rsp+78h+var_58], xmm0
0x180005184  mov     r13, rbp
0x180005187  call    FLAC__format_vorbiscomment_entry_is_legal
0x18000518c  test    eax, eax
0x18000518e  jz      short loc_1800051C9
0x180005190  mov     rbp, [rdi+28h]
0x180005194  mov     r12d, r15d
0x180005197  shl     r12, 4
0x18000519b  add     rbp, r12
0x18000519e  mov     rax, [rbp+8]
0x1800051a2  mov     [rsp+78h+Block], rax
0x1800051aa  test    r13, r13
0x1800051ad  jz      loc_180005299
0x1800051b3  test    r14d, r14d
0x1800051b6  jz      short loc_1800051E3
0x1800051b8  lea     rdx, [rsp+78h+var_48]
0x1800051bd  mov     rcx, rbp
0x1800051c0  call    copy_vcentry_
0x1800051c5  test    eax, eax
0x1800051c7  jnz     short loc_180005212
0x1800051c9  xor     eax, eax
0x1800051cb  mov     rbx, [rsp+78h+arg_0]
0x1800051d3  add     rsp, 40h
0x1800051d7  pop     r15
0x1800051d9  pop     r14
0x1800051db  pop     r13
0x1800051dd  pop     r12
0x1800051df  pop     rdi
0x1800051e0  pop     rsi
0x1800051e1  pop     rbp
0x1800051e2  retn
0x1800051e3  mov     r14d, [rsp+78h+var_58]
0x1800051e8  lea     rdx, [r14+1]
0x1800051ec  cmp     rdx, r14
0x1800051ef  jb      short loc_1800051C9
0x1800051f1  mov     rcx, r13
0x1800051f4  call    cs:__imp__o_realloc
0x1800051fa  test    rax, rax
0x1800051fd  jz      short loc_1800051C9
0x1800051ff  mov     qword ptr [rsp+78h+var_48+8], rax
0x180005204  movaps  xmm0, [rsp+78h+var_48]
0x180005209  mov     byte ptr [r14+rax], 0
0x18000520e  movups  xmmword ptr [rbp+0], xmm0
0x180005212  mov     rax, [rsp+78h+Block]
0x18000521a  mov     rcx, rax; Block
0x18000521d  call    cs:__imp_free
0x180005223  mov     rcx, rdi
0x180005226  call    vorbiscomment_calculate_length_
0x18000522b  cmp     [rsp+78h+arg_10], 0
0x180005233  mov     r11, [rdi+28h]
0x180005237  movups  xmm0, xmmword ptr [r11+r12]
0x18000523c  movups  xmmword ptr [rbx], xmm0
0x18000523f  jz      short loc_18000528F
0x180005241  lea     edx, [r15+1]
0x180005245  cmp     edx, [rdi+20h]
0x180005248  jnb     short loc_18000528F
0x18000524a  mov     rbp, [rbx+8]
0x18000524e  mov     r9d, esi
0x180005251  mov     r8, rbp
0x180005254  mov     rcx, rdi
0x180005257  call    vorbiscomment_find_entry_from_
0x18000525c  mov     ebx, eax
0x18000525e  test    eax, eax
0x180005260  js      short loc_18000528F
0x180005262  mov     edx, ebx
0x180005264  mov     rcx, rdi
0x180005267  call    FLAC__metadata_object_vorbiscomment_delete_comment
0x18000526c  test    eax, eax
0x18000526e  jz      loc_1800051C9
0x180005274  cmp     ebx, [rdi+20h]
0x180005277  jnb     short loc_18000528F
0x180005279  mov     r9d, esi
0x18000527c  mov     r8, rbp
0x18000527f  mov     edx, ebx
0x180005281  mov     rcx, rdi
0x180005284  call    vorbiscomment_find_entry_from_
0x180005289  mov     ebx, eax
0x18000528b  test    eax, eax
0x18000528d  jns     short loc_180005262
0x18000528f  mov     eax, 1
0x180005294  jmp     loc_1800051CB
0x180005299  movups  xmm0, xmmword ptr [rbx]
0x18000529c  movups  xmmword ptr [rbp+0], xmm0
0x1800052a0  jmp     loc_18000521A
0x1800052a5  mov     r8d, r14d
0x1800052a8  lea     rdx, [rsp+78h+var_48]
0x1800052ad  mov     rcx, rdi
0x1800052b0  call    FLAC__metadata_object_vorbiscomment_append_comment
0x1800052b5  jmp     loc_1800051CB
```
