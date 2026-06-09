# tson::output_archive::write_type(bool,tson::details::archive_marker)

- ea: `0x14002cf70`
- end: `0x14002d4d9`
- name: `?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z`
- size: `1385`
- prototype: ``
- caller_count: `15`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140005948`
- `0x140005d50`
- `0x140005fb0`
- `0x14002c114`
- `0x14002c528`
- `0x14002c6b0`
- `0x14002cab0`
- `0x14002cb70`
- `0x14002cbc8`
- `0x14002cd84`
- `0x140061890`
- `0x1400a6c80`
- `0x14010c364`
- `0x14010c450`
- `0x14012c908`

## callees

- `0x14002cf70`
- `0x14002d5b0`
- `0x14002e858`
- `0x1400a6c3c`
- `0x140104bd2`
- `0x140104cc8`
- `0x140104ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d164`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d30e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d43b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d453`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d4a5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d4bf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d164`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d30e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d43b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d453`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d4a5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d4bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d2b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d34d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d2b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002d34d`

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
    memcpy_s_0(v34, DestinationSize, v36, v37);
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
      memcpy_s_0(v47, v46, v49, v50);
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
      memcpy_s_0(v40, v39, v42, v43);
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
0x14002cf70  mov     [rsp+arg_18], rbx
0x14002cf75  push    rsi
0x14002cf76  push    r12
0x14002cf78  push    r13
0x14002cf7a  push    r14
0x14002cf7c  push    r15
0x14002cf7e  sub     rsp, 20h
0x14002cf82  lea     rbx, [rcx+18h]
0x14002cf86  movzx   r12d, r8b
0x14002cf8a  mov     rax, [rbx+68h]
0x14002cf8e  movzx   r15d, dl
0x14002cf92  mov     rsi, rcx
0x14002cf95  test    rax, rax
0x14002cf98  jz      loc_14002D424
0x14002cf9e  lea     rbx, [rbx+rax*4]
0x14002cfa2  add     rbx, 0FFFFFFFFFFFFFFFCh
0x14002cfa6  mov     eax, [rbx+4]
0x14002cfa9  xor     r13d, r13d
0x14002cfac  mov     [rsp+48h+arg_8], rbp
0x14002cfb1  mov     r14d, 1
0x14002cfb7  mov     [rsp+48h+arg_10], rdi
0x14002cfbc  cmp     eax, 2
0x14002cfbf  jz      loc_14002D17A
0x14002cfc5  test    eax, eax
0x14002cfc7  jnz     short loc_14002CFF5
0x14002cfc9  mov     [rbx+4], r14d
0x14002cfcd  mov     rbp, [rcx+90h]
0x14002cfd4  mov     rdx, [rbp+820h]
0x14002cfdb  mov     rcx, [rbp+818h]
0x14002cfe2  cmp     rcx, rdx
0x14002cfe5  jnb     loc_14002D219
0x14002cfeb  mov     [rcx], r14b
0x14002cfee  inc     qword ptr [rbp+818h]
0x14002cff5  mov     [rsi+10h], r13
0x14002cff9  cmp     dword ptr [rbx+4], 3
0x14002cffd  jz      loc_14002D0EA
0x14002d003  test    r15b, r15b
0x14002d006  jnz     loc_14002D131
0x14002d00c  cmp     qword ptr [rsi], 0
0x14002d010  jz      loc_14002D3DB
0x14002d016  mov     rdi, [rsi+90h]
0x14002d01d  mov     rax, [rdi+818h]
0x14002d024  sub     rax, [rdi+810h]
0x14002d02b  mov     [rsi+10h], rax
0x14002d02f  mov     rdx, [rdi+820h]
0x14002d036  mov     rcx, [rdi+818h]
0x14002d03d  cmp     rcx, rdx
0x14002d040  jnb     loc_14002D335
0x14002d046  mov     byte ptr [rcx], 5
0x14002d049  inc     qword ptr [rdi+818h]
0x14002d050  mov     rbx, [rsi+90h]
0x14002d057  mov     rax, [rbx+820h]
0x14002d05e  cmp     [rbx+818h], rax
0x14002d065  jnb     loc_14002D47E
0x14002d06b  mov     rcx, [rbx+818h]
0x14002d072  movzx   eax, byte ptr [rsi+8]
0x14002d076  mov     [rcx], al
0x14002d078  inc     qword ptr [rbx+818h]
0x14002d07f  mov     rbx, [rsi+90h]
0x14002d086  movzx   edi, byte ptr [rsi+8]
0x14002d08a  mov     r15, [rsi]
0x14002d08d  mov     rax, [rbx+820h]
0x14002d094  sub     rax, [rbx+818h]
0x14002d09b  cmp     rax, rdi
0x14002d09e  jb      loc_14002D3AB
0x14002d0a4  test    rdi, rdi
0x14002d0a7  jz      short loc_14002D0E0
0x14002d0a9  mov     rcx, [rbx+818h]; void *
0x14002d0b0  test    rcx, rcx
0x14002d0b3  jz      loc_14002D164
0x14002d0b9  mov     rbp, [rbx+820h]
0x14002d0c0  sub     rbp, rcx
0x14002d0c3  test    r15, r15
0x14002d0c6  jz      loc_14002D496
0x14002d0cc  cmp     rbp, rdi
0x14002d0cf  jb      loc_14002D496
0x14002d0d5  mov     r8, rdi; Size
0x14002d0d8  mov     rdx, r15; Src
0x14002d0db  call    memcpy_0
0x14002d0e0  add     [rbx+818h], rdi
0x14002d0e7  mov     [rsi], r13
0x14002d0ea  mov     rdi, [rsi+90h]
0x14002d0f1  mov     rax, [rdi+820h]
0x14002d0f8  mov     rcx, [rdi+818h]
0x14002d0ff  cmp     rcx, rax
0x14002d102  jnb     loc_14002D29C
0x14002d108  mov     [rcx], r12b
0x14002d10b  inc     qword ptr [rdi+818h]
0x14002d112  mov     al, 1
0x14002d114  mov     rdi, [rsp+48h+arg_10]
0x14002d119  mov     rbp, [rsp+48h+arg_8]
0x14002d11e  mov     rbx, [rsp+48h+arg_18]
0x14002d123  add     rsp, 20h
0x14002d127  pop     r15
0x14002d129  pop     r14
0x14002d12b  pop     r13
0x14002d12d  pop     r12
0x14002d12f  pop     rsi
0x14002d130  retn
0x14002d131  mov     rbx, [rsi+90h]
0x14002d138  mov     [rsi], r13
0x14002d13b  mov     rax, [rbx+820h]
0x14002d142  cmp     [rbx+818h], rax
0x14002d149  jnb     loc_14002D3C3
0x14002d14f  mov     rax, [rbx+818h]
0x14002d156  mov     byte ptr [rax], 6
0x14002d159  inc     qword ptr [rbx+818h]
0x14002d160  xor     al, al
0x14002d162  jmp     short loc_14002D114
0x14002d164  call    cs:__imp__o__errno
0x14002d16a  mov     dword ptr [rax], 16h
0x14002d170  call    _invalid_parameter_noinfo
0x14002d175  jmp     loc_14002D0E0
0x14002d17a  mov     dword ptr [rbx+4], 3
0x14002d181  mov     rdi, [rcx+90h]
0x14002d188  mov     rax, [rdi+820h]
0x14002d18f  cmp     [rdi+818h], rax
0x14002d196  jnb     loc_14002D3EE
0x14002d19c  mov     rax, [rdi+818h]
0x14002d1a3  mov     byte ptr [rax], 3
0x14002d1a6  inc     qword ptr [rdi+818h]
0x14002d1ad  mov     rdi, [rsi+90h]
0x14002d1b4  mov     rax, [rdi+820h]
0x14002d1bb  sub     rax, [rdi+818h]
0x14002d1c2  cmp     rax, 2
0x14002d1c6  jb      loc_14002D406
0x14002d1cc  mov     rcx, [rdi+818h]; void *
0x14002d1d3  test    rcx, rcx
0x14002d1d6  jz      loc_14002D30E
0x14002d1dc  mov     r13, [rdi+820h]
0x14002d1e3  lea     rbp, [rsi+0Ah]
0x14002d1e7  sub     r13, rcx
0x14002d1ea  test    rbp, rbp
0x14002d1ed  jz      loc_14002D42C
0x14002d1f3  cmp     r13, 2
0x14002d1f7  jb      loc_14002D42C
0x14002d1fd  movzx   eax, word ptr [rbp+0]
0x14002d201  mov     [rcx], ax
0x14002d204  xor     r13d, r13d
0x14002d207  add     qword ptr [rdi+818h], 2
0x14002d20f  mov     [rbp+0], r13w
0x14002d214  jmp     loc_14002CFF5
0x14002d219  sub     rdx, [rbp+810h]
0x14002d220  mov     rax, r14
0x14002d223  cmp     rdx, rax
0x14002d226  cmova   rax, rdx
0x14002d22a  add     rax, rax
0x14002d22d  mov     rcx, rax; cb
0x14002d230  mov     [rsp+48h+DestinationSize], rax
0x14002d235  call    cs:__imp_CoTaskMemAlloc
0x14002d23b  mov     r13, rax
0x14002d23e  test    rax, rax
0x14002d241  jz      loc_14002D469
0x14002d247  mov     r8, [rbp+810h]; Source
0x14002d24e  mov     rcx, rax; Destination
0x14002d251  mov     rdi, [rbp+818h]
0x14002d258  mov     rdx, [rsp+48h+DestinationSize]; DestinationSize
0x14002d25d  sub     rdi, r8
0x14002d260  mov     r9, rdi; SourceSize
0x14002d263  call    memcpy_s_0
0x14002d268  mov     rdx, r13
0x14002d26b  mov     rcx, rbp
0x14002d26e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14002d273  mov     rax, [rsp+48h+DestinationSize]
0x14002d278  lea     rcx, [rdi+r13]
0x14002d27c  add     rax, r13
0x14002d27f  mov     [rbp+810h], r13
0x14002d286  mov     [rbp+820h], rax
0x14002d28d  xor     r13d, r13d
0x14002d290  mov     [rbp+818h], rcx
0x14002d297  jmp     loc_14002CFEB
0x14002d29c  sub     rax, [rdi+810h]
0x14002d2a3  cmp     rax, r14
0x14002d2a6  cmova   r14, rax
0x14002d2aa  add     r14, r14
0x14002d2ad  mov     rcx, r14; cb
0x14002d2b0  call    cs:__imp_CoTaskMemAlloc
0x14002d2b6  mov     rsi, rax
0x14002d2b9  test    rax, rax
0x14002d2bc  jz      loc_14002D4D0
0x14002d2c2  mov     r8, [rdi+810h]; Source
0x14002d2c9  mov     rdx, r14; DestinationSize
0x14002d2cc  mov     rbx, [rdi+818h]
0x14002d2d3  mov     rcx, rax; Destination
0x14002d2d6  sub     rbx, r8
0x14002d2d9  mov     r9, rbx; SourceSize
0x14002d2dc  call    memcpy_s_0
0x14002d2e1  mov     rdx, rsi
0x14002d2e4  mov     rcx, rdi
0x14002d2e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14002d2ec  lea     rcx, [rbx+rsi]
0x14002d2f0  mov     [rdi+810h], rsi
0x14002d2f7  lea     rax, [r14+rsi]
0x14002d2fb  mov     [rdi+818h], rcx
0x14002d302  mov     [rdi+820h], rax
0x14002d309  jmp     loc_14002D108
0x14002d30e  call    cs:__imp__o__errno
0x14002d314  mov     dword ptr [rax], 16h
0x14002d31a  call    _invalid_parameter_noinfo
0x14002d31f  add     qword ptr [rdi+818h], 2
0x14002d327  lea     rbp, [rsi+0Ah]
0x14002d32b  mov     [rbp+0], r13w
0x14002d330  jmp     loc_14002CFF5
0x14002d335  sub     rdx, [rdi+810h]
0x14002d33c  mov     rax, r14
0x14002d33f  cmp     rdx, rax
0x14002d342  cmova   rax, rdx
0x14002d346  lea     r15, [rax+rax]
0x14002d34a  mov     rcx, r15; cb
0x14002d34d  call    cs:__imp_CoTaskMemAlloc
0x14002d353  mov     rbp, rax
0x14002d356  test    rax, rax
0x14002d359  jz      loc_14002D475
0x14002d35f  mov     r8, [rdi+810h]; Source
0x14002d366  mov     rdx, r15; DestinationSize
0x14002d369  mov     rbx, [rdi+818h]
0x14002d370  mov     rcx, rax; Destination
0x14002d373  sub     rbx, r8
0x14002d376  mov     r9, rbx; SourceSize
0x14002d379  call    memcpy_s_0
0x14002d37e  mov     rdx, rbp
0x14002d381  mov     rcx, rdi
0x14002d384  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14002d389  lea     rcx, [rbx+rbp]
0x14002d38d  mov     [rdi+810h], rbp
0x14002d394  lea     rax, [r15+rbp]
0x14002d398  mov     [rdi+818h], rcx
0x14002d39f  mov     [rdi+820h], rax
0x14002d3a6  jmp     loc_14002D046
0x14002d3ab  mov     rdx, rdi; unsigned __int64
0x14002d3ae  mov     rcx, rbx; this
0x14002d3b1  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d3b6  test    al, al
0x14002d3b8  jnz     loc_14002D0A4
0x14002d3be  jmp     loc_14002D0E7
0x14002d3c3  mov     rdx, r14; unsigned __int64
0x14002d3c6  mov     rcx, rbx; this
0x14002d3c9  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d3ce  test    al, al
0x14002d3d0  jnz     loc_14002D14F
0x14002d3d6  jmp     loc_14002D160
0x14002d3db  lea     rax, asc_1401EC0BC; "-"
0x14002d3e2  mov     [rsi+8], r14b
0x14002d3e6  mov     [rsi], rax
0x14002d3e9  jmp     loc_14002D016
0x14002d3ee  mov     rdx, r14; unsigned __int64
0x14002d3f1  mov     rcx, rdi; this
0x14002d3f4  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d3f9  test    al, al
0x14002d3fb  jnz     loc_14002D19C
0x14002d401  jmp     loc_14002D1AD
0x14002d406  mov     edx, 2; unsigned __int64
0x14002d40b  mov     rcx, rdi; this
0x14002d40e  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d413  test    al, al
0x14002d415  jnz     loc_14002D1CC
0x14002d41b  lea     rbp, [rsi+0Ah]
0x14002d41f  jmp     loc_14002D20F
0x14002d424  mov     byte ptr [rbx], 1
0x14002d427  jmp     loc_14002CFA6
0x14002d42c  mov     r8, r13; Size
0x14002d42f  xor     edx, edx; Val
0x14002d431  call    memset_0
0x14002d436  test    rbp, rbp
0x14002d439  jnz     short loc_14002D449
0x14002d43b  call    cs:__imp__o__errno
0x14002d441  mov     dword ptr [rax], 16h
0x14002d447  jmp     short loc_14002D45F
0x14002d449  cmp     r13, 2
0x14002d44d  jnb     loc_14002D204
0x14002d453  call    cs:__imp__o__errno
0x14002d459  mov     dword ptr [rax], 22h ; '"'
0x14002d45f  call    _invalid_parameter_noinfo
0x14002d464  jmp     loc_14002D204
0x14002d469  mov     [rbp+8], r14b
0x14002d46d  xor     r13d, r13d
0x14002d470  jmp     loc_14002CFF5
0x14002d475  mov     [rdi+8], r14b
0x14002d479  jmp     loc_14002D050
0x14002d47e  mov     rdx, r14; unsigned __int64
0x14002d481  mov     rcx, rbx; this
0x14002d484  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14002d489  test    al, al
0x14002d48b  jz      loc_14002D07F
0x14002d491  jmp     loc_14002D06B
0x14002d496  mov     r8, rbp; Size
0x14002d499  xor     edx, edx; Val
0x14002d49b  call    memset_0
0x14002d4a0  test    r15, r15
0x14002d4a3  jnz     short loc_14002D4B6
0x14002d4a5  call    cs:__imp__o__errno
0x14002d4ab  mov     dword ptr [rax], 16h
0x14002d4b1  jmp     loc_14002D170
0x14002d4b6  cmp     rbp, rdi
0x14002d4b9  jnb     loc_14002D0E0
0x14002d4bf  call    cs:__imp__o__errno
0x14002d4c5  mov     dword ptr [rax], 22h ; '"'
0x14002d4cb  jmp     loc_14002D170
0x14002d4d0  mov     byte ptr [rdi+8], 1
0x14002d4d4  jmp     loc_14002D112
  ... truncated ...
```
