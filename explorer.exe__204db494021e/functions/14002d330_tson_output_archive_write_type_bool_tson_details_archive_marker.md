# tson::output_archive::write_type(bool,tson::details::archive_marker)

- ea: `0x14002d330`
- end: `0x14002d8bd`
- name: `?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z`
- size: `1421`
- prototype: ``
- caller_count: `15`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140017064`
- `0x14001746c`
- `0x1400176cc`
- `0x14002c498`
- `0x14002c8c4`
- `0x14002ca44`
- `0x14002ce48`
- `0x14002cf14`
- `0x14002cf6c`
- `0x14002d138`
- `0x140064880`
- `0x1400acda4`
- `0x140116654`
- `0x140116744`
- `0x1401384dc`

## callees

- `0x14002d330`
- `0x14002d9b0`
- `0x14002ecbc`
- `0x1400aacd8`
- `0x14010ec86`
- `0x14010ed78`
- `0x14010ed90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d525`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d6e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d81a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d838`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d89d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d525`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d6e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d81a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d838`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d89d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d5fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d67d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d726`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d5fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d67d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d726`

## pseudocode

```c
char __fastcall tson::output_archive::write_type(__int64 a1, char a2, char a3)
{
  __int64 v3; // rbx
  __int64 v5; // rax
  int v8; // eax
  __int64 v9; // r14
  __int64 v10; // rbp
  unsigned __int64 v11; // rdx
  char *v12; // rcx
  __int64 v13; // rdi
  unsigned __int64 v14; // rdx
  char *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rbx
  size_t v18; // rdi
  const void *v19; // r15
  void *v20; // rcx
  size_t v21; // rbp
  __int64 v22; // rdi
  unsigned __int64 v23; // rax
  char *v24; // rcx
  tson::write_buffer *v26; // rbx
  __int64 v27; // rdi
  __int64 v28; // rdi
  _WORD *v29; // rcx
  _WORD *v30; // rbp
  unsigned __int64 v31; // r13
  unsigned __int64 v32; // rdx
  __int64 v33; // rax
  char *v34; // rax
  char *v35; // r13
  const void *v36; // r8
  rsize_t v37; // rdi
  unsigned __int64 v38; // rax
  __int64 v39; // r14
  char *v40; // rax
  char *v41; // rsi
  const void *v42; // r8
  rsize_t v43; // rbx
  unsigned __int64 v44; // rdx
  __int64 v45; // rax
  rsize_t v46; // r15
  char *v47; // rax
  char *v48; // rbp
  const void *v49; // r8
  rsize_t v50; // rbx
  rsize_t DestinationSize; // [rsp+50h] [rbp+8h]

  v3 = a1 + 24;
  v5 = *(_QWORD *)(a1 + 128);
  if ( v5 )
    v3 = v3 + 4 * v5 - 4;
  else
    *(_BYTE *)v3 = 1;
  v8 = *(_DWORD *)(v3 + 4);
  v9 = 1;
  if ( v8 == 2 )
  {
    *(_DWORD *)(v3 + 4) = 3;
    v27 = *(_QWORD *)(a1 + 144);
    if ( *(_QWORD *)(v27 + 2072) < *(_QWORD *)(v27 + 2080)
      || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v27 + 2072))++ = 3;
    }
    v28 = *(_QWORD *)(a1 + 144);
    if ( *(_QWORD *)(v28 + 2080) - *(_QWORD *)(v28 + 2072) < 2u
      && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 2u) )
    {
      v30 = (_WORD *)(a1 + 10);
      goto LABEL_39;
    }
    v29 = *(_WORD **)(v28 + 2072);
    if ( !v29 )
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      *(_QWORD *)(v28 + 2072) += 2LL;
      *(_WORD *)(a1 + 10) = 0;
      goto LABEL_7;
    }
    v30 = (_WORD *)(a1 + 10);
    v31 = *(_QWORD *)(v28 + 2080) - (_QWORD)v29;
    if ( a1 != -10 && v31 >= 2 )
    {
      *v29 = *v30;
LABEL_38:
      *(_QWORD *)(v28 + 2072) += 2LL;
LABEL_39:
      *v30 = 0;
      goto LABEL_7;
    }
    memset_0(v29, 0, *(_QWORD *)(v28 + 2080) - (_QWORD)v29);
    if ( a1 == -10 )
    {
      *(_DWORD *)_o__errno() = 22;
    }
    else
    {
      if ( v31 >= 2 )
        goto LABEL_38;
      *(_DWORD *)_o__errno() = 34;
    }
    invalid_parameter_noinfo();
    goto LABEL_38;
  }
  if ( v8 )
    goto LABEL_7;
  *(_DWORD *)(v3 + 4) = 1;
  v10 = *(_QWORD *)(a1 + 144);
  v11 = *(_QWORD *)(v10 + 2080);
  v12 = *(char **)(v10 + 2072);
  if ( (unsigned __int64)v12 < v11 )
    goto LABEL_6;
  v32 = v11 - *(_QWORD *)(v10 + 2064);
  v33 = 1;
  if ( v32 > 1 )
    v33 = v32;
  DestinationSize = 2 * v33;
  v34 = (char *)CoTaskMemAlloc(2 * v33);
  v35 = v34;
  if ( v34 )
  {
    v36 = *(const void **)(v10 + 2064);
    v37 = *(_QWORD *)(v10 + 2072) - (_QWORD)v36;
    memcpy_s(v34, DestinationSize, v36, v37);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      v10,
      v35);
    v12 = &v35[v37];
    *(_QWORD *)(v10 + 2064) = v35;
    *(_QWORD *)(v10 + 2080) = &v35[DestinationSize];
    *(_QWORD *)(v10 + 2072) = &v35[v37];
LABEL_6:
    *v12 = 1;
    ++*(_QWORD *)(v10 + 2072);
    goto LABEL_7;
  }
  *(_BYTE *)(v10 + 8) = 1;
LABEL_7:
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_DWORD *)(v3 + 4) == 3 )
    goto LABEL_23;
  if ( !a2 )
  {
    if ( !*(_QWORD *)a1 )
    {
      *(_BYTE *)(a1 + 8) = 1;
      *(_QWORD *)a1 = "-";
    }
    v13 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(v13 + 2072) - *(_QWORD *)(v13 + 2064);
    v14 = *(_QWORD *)(v13 + 2080);
    v15 = *(char **)(v13 + 2072);
    if ( (unsigned __int64)v15 >= v14 )
    {
      v44 = v14 - *(_QWORD *)(v13 + 2064);
      v45 = 1;
      if ( v44 > 1 )
        v45 = v44;
      v46 = 2 * v45;
      v47 = (char *)CoTaskMemAlloc(2 * v45);
      v48 = v47;
      if ( !v47 )
      {
        *(_BYTE *)(v13 + 8) = 1;
        goto LABEL_13;
      }
      v49 = *(const void **)(v13 + 2064);
      v50 = *(_QWORD *)(v13 + 2072) - (_QWORD)v49;
      memcpy_s(v47, v46, v49, v50);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        v13,
        v48);
      v15 = &v48[v50];
      *(_QWORD *)(v13 + 2064) = v48;
      *(_QWORD *)(v13 + 2072) = &v48[v50];
      *(_QWORD *)(v13 + 2080) = &v48[v46];
    }
    *v15 = 5;
    ++*(_QWORD *)(v13 + 2072);
LABEL_13:
    v16 = *(_QWORD *)(a1 + 144);
    if ( *(_QWORD *)(v16 + 2072) < *(_QWORD *)(v16 + 2080)
      || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v16 + 2072))++ = *(_BYTE *)(a1 + 8);
    }
    v17 = *(_QWORD *)(a1 + 144);
    v18 = *(unsigned __int8 *)(a1 + 8);
    v19 = *(const void **)a1;
    if ( *(_QWORD *)(v17 + 2080) - *(_QWORD *)(v17 + 2072) < v18
      && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), *(unsigned __int8 *)(a1 + 8)) )
    {
      goto LABEL_22;
    }
    if ( v18 )
    {
      v20 = *(void **)(v17 + 2072);
      if ( !v20 )
        goto LABEL_29;
      v21 = *(_QWORD *)(v17 + 2080) - (_QWORD)v20;
      if ( v19 && v21 >= v18 )
      {
        memcpy_0(v20, v19, v18);
        goto LABEL_21;
      }
      memset_0(v20, 0, *(_QWORD *)(v17 + 2080) - (_QWORD)v20);
      if ( v19 )
      {
        if ( v21 >= v18 )
          goto LABEL_21;
        *(_DWORD *)_o__errno() = 34;
      }
      else
      {
LABEL_29:
        *(_DWORD *)_o__errno() = 22;
      }
      invalid_parameter_noinfo();
    }
LABEL_21:
    *(_QWORD *)(v17 + 2072) += v18;
LABEL_22:
    *(_QWORD *)a1 = 0;
LABEL_23:
    v22 = *(_QWORD *)(a1 + 144);
    v23 = *(_QWORD *)(v22 + 2080);
    v24 = *(char **)(v22 + 2072);
    if ( (unsigned __int64)v24 >= v23 )
    {
      v38 = v23 - *(_QWORD *)(v22 + 2064);
      if ( v38 > 1 )
        v9 = v38;
      v39 = 2 * v9;
      v40 = (char *)CoTaskMemAlloc(v39);
      v41 = v40;
      if ( !v40 )
      {
        *(_BYTE *)(v22 + 8) = 1;
        return 1;
      }
      v42 = *(const void **)(v22 + 2064);
      v43 = *(_QWORD *)(v22 + 2072) - (_QWORD)v42;
      memcpy_s(v40, v39, v42, v43);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        v22,
        v41);
      v24 = &v41[v43];
      *(_QWORD *)(v22 + 2064) = v41;
      *(_QWORD *)(v22 + 2072) = &v41[v43];
      *(_QWORD *)(v22 + 2080) = &v41[v39];
    }
    *v24 = a3;
    ++*(_QWORD *)(v22 + 2072);
    return 1;
  }
  v26 = *(tson::write_buffer **)(a1 + 144);
  *(_QWORD *)a1 = 0;
  if ( *((_QWORD *)v26 + 259) < *((_QWORD *)v26 + 260) || tson::write_buffer::reserve(v26, 1u) )
    *(_BYTE *)(*((_QWORD *)v26 + 259))++ = 6;
  return 0;
}

```

## disassembly

```asm
0x14002d330  mov     [rsp+arg_18], rbx
0x14002d335  push    rsi
0x14002d336  push    r12
0x14002d338  push    r13
0x14002d33a  push    r14
0x14002d33c  push    r15
0x14002d33e  sub     rsp, 20h
0x14002d342  lea     rbx, [rcx+18h]
0x14002d346  movzx   r12d, r8b
0x14002d34a  mov     rax, [rbx+68h]
0x14002d34e  movzx   r15d, dl
0x14002d352  mov     rsi, rcx
0x14002d355  test    rax, rax
0x14002d358  jz      loc_14002D803
0x14002d35e  lea     rbx, [rbx+rax*4]
0x14002d362  add     rbx, 0FFFFFFFFFFFFFFFCh
0x14002d366  mov     eax, [rbx+4]
0x14002d369  xor     r13d, r13d
0x14002d36c  mov     [rsp+48h+arg_8], rbp
0x14002d371  mov     r14d, 1
0x14002d377  mov     [rsp+48h+arg_10], rdi
0x14002d37c  cmp     eax, 2
0x14002d37f  jz      loc_14002D541
0x14002d385  test    eax, eax
0x14002d387  jnz     short loc_14002D3B5
0x14002d389  mov     [rbx+4], r14d
0x14002d38d  mov     rbp, [rcx+90h]
0x14002d394  mov     rdx, [rbp+820h]
0x14002d39b  mov     rcx, [rbp+818h]
0x14002d3a2  cmp     rcx, rdx
0x14002d3a5  jnb     loc_14002D5E0
0x14002d3ab  mov     [rcx], r14b
0x14002d3ae  inc     qword ptr [rbp+818h]
0x14002d3b5  mov     [rsi+10h], r13
0x14002d3b9  cmp     dword ptr [rbx+4], 3
0x14002d3bd  jz      loc_14002D4AA
0x14002d3c3  test    r15b, r15b
0x14002d3c6  jnz     loc_14002D4F2
0x14002d3cc  cmp     qword ptr [rsi], 0
0x14002d3d0  jz      loc_14002D7BA
0x14002d3d6  mov     rdi, [rsi+90h]
0x14002d3dd  mov     rax, [rdi+818h]
0x14002d3e4  sub     rax, [rdi+810h]
0x14002d3eb  mov     [rsi+10h], rax
0x14002d3ef  mov     rdx, [rdi+820h]
0x14002d3f6  mov     rcx, [rdi+818h]
0x14002d3fd  cmp     rcx, rdx
0x14002d400  jnb     loc_14002D70E
0x14002d406  mov     byte ptr [rcx], 5
0x14002d409  inc     qword ptr [rdi+818h]
0x14002d410  mov     rbx, [rsi+90h]
0x14002d417  mov     rax, [rbx+820h]
0x14002d41e  cmp     [rbx+818h], rax
0x14002d425  jnb     loc_14002D869
0x14002d42b  mov     rcx, [rbx+818h]
0x14002d432  movzx   eax, byte ptr [rsi+8]
0x14002d436  mov     [rcx], al
0x14002d438  inc     qword ptr [rbx+818h]
0x14002d43f  mov     rbx, [rsi+90h]
0x14002d446  movzx   edi, byte ptr [rsi+8]
0x14002d44a  mov     r15, [rsi]
0x14002d44d  mov     rax, [rbx+820h]
0x14002d454  sub     rax, [rbx+818h]
0x14002d45b  cmp     rax, rdi
0x14002d45e  jb      loc_14002D78A
0x14002d464  test    rdi, rdi
0x14002d467  jz      short loc_14002D4A0
0x14002d469  mov     rcx, [rbx+818h]; void *
0x14002d470  test    rcx, rcx
0x14002d473  jz      loc_14002D525
0x14002d479  mov     rbp, [rbx+820h]
0x14002d480  sub     rbp, rcx
0x14002d483  test    r15, r15
0x14002d486  jz      loc_14002D881
0x14002d48c  cmp     rbp, rdi
0x14002d48f  jb      loc_14002D881
0x14002d495  mov     r8, rdi; Size
0x14002d498  mov     rdx, r15; Src
0x14002d49b  call    memcpy_0
0x14002d4a0  add     [rbx+818h], rdi
0x14002d4a7  mov     [rsi], r13
0x14002d4aa  mov     rdi, [rsi+90h]
0x14002d4b1  mov     rax, [rdi+820h]
0x14002d4b8  mov     rcx, [rdi+818h]
0x14002d4bf  cmp     rcx, rax
0x14002d4c2  jnb     loc_14002D669
0x14002d4c8  mov     [rcx], r12b
0x14002d4cb  inc     qword ptr [rdi+818h]
0x14002d4d2  mov     al, 1
0x14002d4d4  mov     rdi, [rsp+48h+arg_10]
0x14002d4d9  mov     rbp, [rsp+48h+arg_8]
0x14002d4de  mov     rbx, [rsp+48h+arg_18]
0x14002d4e3  add     rsp, 20h
0x14002d4e7  pop     r15
0x14002d4e9  pop     r14
0x14002d4eb  pop     r13
0x14002d4ed  pop     r12
0x14002d4ef  pop     rsi
0x14002d4f0  retn
0x14002d4f2  mov     rbx, [rsi+90h]
0x14002d4f9  mov     [rsi], r13
0x14002d4fc  mov     rax, [rbx+820h]
0x14002d503  cmp     [rbx+818h], rax
0x14002d50a  jnb     loc_14002D7A2
0x14002d510  mov     rax, [rbx+818h]
0x14002d517  mov     byte ptr [rax], 6
0x14002d51a  inc     qword ptr [rbx+818h]
0x14002d521  xor     al, al
0x14002d523  jmp     short loc_14002D4D4
0x14002d525  call    cs:__imp__o__errno
0x14002d52c  nop     dword ptr [rax+rax+00h]
0x14002d531  mov     dword ptr [rax], 16h
0x14002d537  call    _invalid_parameter_noinfo
0x14002d53c  jmp     loc_14002D4A0
0x14002d541  mov     dword ptr [rbx+4], 3
0x14002d548  mov     rdi, [rcx+90h]
0x14002d54f  mov     rax, [rdi+820h]
0x14002d556  cmp     [rdi+818h], rax
0x14002d55d  jnb     loc_14002D7CD
0x14002d563  mov     rax, [rdi+818h]
0x14002d56a  mov     byte ptr [rax], 3
0x14002d56d  inc     qword ptr [rdi+818h]
0x14002d574  mov     rdi, [rsi+90h]
0x14002d57b  mov     rax, [rdi+820h]
0x14002d582  sub     rax, [rdi+818h]
0x14002d589  cmp     rax, 2
0x14002d58d  jb      loc_14002D7E5
0x14002d593  mov     rcx, [rdi+818h]; void *
0x14002d59a  test    rcx, rcx
0x14002d59d  jz      loc_14002D6E1
0x14002d5a3  mov     r13, [rdi+820h]
0x14002d5aa  lea     rbp, [rsi+0Ah]
0x14002d5ae  sub     r13, rcx
0x14002d5b1  test    rbp, rbp
0x14002d5b4  jz      loc_14002D80B
0x14002d5ba  cmp     r13, 2
0x14002d5be  jb      loc_14002D80B
0x14002d5c4  movzx   eax, word ptr [rbp+0]
0x14002d5c8  mov     [rcx], ax
0x14002d5cb  xor     r13d, r13d
0x14002d5ce  add     qword ptr [rdi+818h], 2
0x14002d5d6  mov     [rbp+0], r13w
0x14002d5db  jmp     loc_14002D3B5
0x14002d5e0  sub     rdx, [rbp+810h]
0x14002d5e7  mov     rax, r14
0x14002d5ea  cmp     rdx, rax
0x14002d5ed  cmova   rax, rdx
0x14002d5f1  add     rax, rax
0x14002d5f4  mov     rcx, rax; cb
0x14002d5f7  mov     [rsp+48h+DestinationSize], rax
0x14002d5fc  call    cs:__imp_CoTaskMemAlloc
0x14002d603  nop     dword ptr [rax+rax+00h]
0x14002d608  mov     r13, rax
0x14002d60b  test    rax, rax
0x14002d60e  jz      loc_14002D854
0x14002d614  mov     r8, [rbp+810h]; Source
0x14002d61b  mov     rcx, rax; Destination
0x14002d61e  mov     rdi, [rbp+818h]
0x14002d625  mov     rdx, [rsp+48h+DestinationSize]; DestinationSize
0x14002d62a  sub     rdi, r8
0x14002d62d  mov     r9, rdi; SourceSize
0x14002d630  call    memcpy_s
0x14002d635  mov     rdx, r13
0x14002d638  mov     rcx, rbp
0x14002d63b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14002d640  mov     rax, [rsp+48h+DestinationSize]
0x14002d645  lea     rcx, [rdi+r13]
0x14002d649  add     rax, r13
0x14002d64c  mov     [rbp+810h], r13
0x14002d653  mov     [rbp+820h], rax
0x14002d65a  xor     r13d, r13d
0x14002d65d  mov     [rbp+818h], rcx
0x14002d664  jmp     loc_14002D3AB
0x14002d669  sub     rax, [rdi+810h]
0x14002d670  cmp     rax, r14
0x14002d673  cmova   r14, rax
0x14002d677  add     r14, r14
0x14002d67a  mov     rcx, r14; cb
0x14002d67d  call    cs:__imp_CoTaskMemAlloc
0x14002d684  nop     dword ptr [rax+rax+00h]
0x14002d689  mov     rsi, rax
0x14002d68c  test    rax, rax
0x14002d68f  jz      loc_14002D8B4
0x14002d695  mov     r8, [rdi+810h]; Source
0x14002d69c  mov     rdx, r14; DestinationSize
0x14002d69f  mov     rbx, [rdi+818h]
0x14002d6a6  mov     rcx, rax; Destination
0x14002d6a9  sub     rbx, r8
0x14002d6ac  mov     r9, rbx; SourceSize
0x14002d6af  call    memcpy_s
0x14002d6b4  mov     rdx, rsi
0x14002d6b7  mov     rcx, rdi
0x14002d6ba  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14002d6bf  lea     rcx, [rbx+rsi]
0x14002d6c3  mov     [rdi+810h], rsi
0x14002d6ca  lea     rax, [r14+rsi]
0x14002d6ce  mov     [rdi+818h], rcx
0x14002d6d5  mov     [rdi+820h], rax
0x14002d6dc  jmp     loc_14002D4C8
0x14002d6e1  call    cs:__imp__o__errno
0x14002d6e8  nop     dword ptr [rax+rax+00h]
0x14002d6ed  mov     dword ptr [rax], 16h
0x14002d6f3  call    _invalid_parameter_noinfo
0x14002d6f8  add     qword ptr [rdi+818h], 2
0x14002d700  lea     rbp, [rsi+0Ah]
0x14002d704  mov     [rbp+0], r13w
0x14002d709  jmp     loc_14002D3B5
0x14002d70e  sub     rdx, [rdi+810h]
0x14002d715  mov     rax, r14
0x14002d718  cmp     rdx, rax
0x14002d71b  cmova   rax, rdx
0x14002d71f  lea     r15, [rax+rax]
0x14002d723  mov     rcx, r15; cb
0x14002d726  call    cs:__imp_CoTaskMemAlloc
0x14002d72d  nop     dword ptr [rax+rax+00h]
0x14002d732  mov     rbp, rax
0x14002d735  test    rax, rax
0x14002d738  jz      loc_14002D860
0x14002d73e  mov     r8, [rdi+810h]; Source
0x14002d745  mov     rdx, r15; DestinationSize
0x14002d748  mov     rbx, [rdi+818h]
0x14002d74f  mov     rcx, rax; Destination
0x14002d752  sub     rbx, r8
0x14002d755  mov     r9, rbx; SourceSize
0x14002d758  call    memcpy_s
0x14002d75d  mov     rdx, rbp
0x14002d760  mov     rcx, rdi
0x14002d763  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14002d768  lea     rcx, [rbx+rbp]
0x14002d76c  mov     [rdi+810h], rbp
0x14002d773  lea     rax, [r15+rbp]
0x14002d777  mov     [rdi+818h], rcx
0x14002d77e  mov     [rdi+820h], rax
0x14002d785  jmp     loc_14002D406
0x14002d78a  mov     rdx, rdi; unsigned __int64
0x14002d78d  mov     rcx, rbx; this
0x14002d790  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d795  test    al, al
0x14002d797  jnz     loc_14002D464
0x14002d79d  jmp     loc_14002D4A7
0x14002d7a2  mov     rdx, r14; unsigned __int64
0x14002d7a5  mov     rcx, rbx; this
0x14002d7a8  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d7ad  test    al, al
0x14002d7af  jnz     loc_14002D510
0x14002d7b5  jmp     loc_14002D521
0x14002d7ba  lea     rax, asc_1401E9FD4; "-"
0x14002d7c1  mov     [rsi+8], r14b
0x14002d7c5  mov     [rsi], rax
0x14002d7c8  jmp     loc_14002D3D6
0x14002d7cd  mov     rdx, r14; unsigned __int64
0x14002d7d0  mov     rcx, rdi; this
0x14002d7d3  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d7d8  test    al, al
0x14002d7da  jnz     loc_14002D563
0x14002d7e0  jmp     loc_14002D574
0x14002d7e5  mov     edx, 2; unsigned __int64
0x14002d7ea  mov     rcx, rdi; this
0x14002d7ed  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d7f2  test    al, al
0x14002d7f4  jnz     loc_14002D593
0x14002d7fa  lea     rbp, [rsi+0Ah]
0x14002d7fe  jmp     loc_14002D5D6
0x14002d803  mov     byte ptr [rbx], 1
0x14002d806  jmp     loc_14002D366
0x14002d80b  mov     r8, r13; Size
0x14002d80e  xor     edx, edx; Val
0x14002d810  call    memset_0
0x14002d815  test    rbp, rbp
0x14002d818  jnz     short loc_14002D82E
0x14002d81a  call    cs:__imp__o__errno
0x14002d821  nop     dword ptr [rax+rax+00h]
0x14002d826  mov     dword ptr [rax], 16h
0x14002d82c  jmp     short loc_14002D84A
0x14002d82e  cmp     r13, 2
0x14002d832  jnb     loc_14002D5CB
0x14002d838  call    cs:__imp__o__errno
0x14002d83f  nop     dword ptr [rax+rax+00h]
0x14002d844  mov     dword ptr [rax], 22h ; '"'
0x14002d84a  call    _invalid_parameter_noinfo
0x14002d84f  jmp     loc_14002D5CB
0x14002d854  mov     [rbp+8], r14b
0x14002d858  xor     r13d, r13d
0x14002d85b  jmp     loc_14002D3B5
0x14002d860  mov     [rdi+8], r14b
0x14002d864  jmp     loc_14002D410
0x14002d869  mov     rdx, r14; unsigned __int64
0x14002d86c  mov     rcx, rbx; this
0x14002d86f  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d874  test    al, al
0x14002d876  jz      loc_14002D43F
0x14002d87c  jmp     loc_14002D42B
0x14002d881  mov     r8, rbp; Size
0x14002d884  xor     edx, edx; Val
0x14002d886  call    memset_0
0x14002d88b  test    r15, r15
0x14002d88e  jz      loc_14002D525
0x14002d894  cmp     rbp, rdi
0x14002d897  jnb     loc_14002D4A0
0x14002d89d  call    cs:__imp__o__errno
  ... truncated ...
```
