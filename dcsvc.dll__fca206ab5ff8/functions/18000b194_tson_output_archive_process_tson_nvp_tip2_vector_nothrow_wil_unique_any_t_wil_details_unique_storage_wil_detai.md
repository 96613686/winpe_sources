# tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x18000b194`
- end: `0x18000b482`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `750`
- prototype: `void __fastcall(tson *this, __int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000dce4`

## callees

- `0x18000b194`
- `0x18000ce60`
- `0x18000d160`
- `0x18000d260`
- `0x18000d8fc`
- `0x18000e224`
- `0x18000e438`

## pseudocode

```c
void __fastcall tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        tson *this,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  char v4; // r10
  __int64 *v5; // r15
  __int64 v8; // rsi
  _BYTE *v9; // rbx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rdx
  char *v12; // rcx
  void **v13; // r14
  __int64 v14; // r12
  _BYTE *v15; // r15
  unsigned __int64 v16; // rbp
  __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v19; // r14
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rdx
  char *v22; // rcx
  struct tson::output_archive *v23; // rsi
  __int64 v24; // rbp
  struct wil::StoredFailureInfo *v25; // r8
  unsigned __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // r14
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rdx
  char *v31; // rcx
  struct tson::output_archive *v32; // rsi
  __int64 v33; // rbp
  struct tip2::test_flag *v34; // r8
  unsigned __int64 v35; // rax

  v4 = *(_BYTE *)(a2 + 8);
  v5 = a4;
  *(_QWORD *)this = *(_QWORD *)a2;
  *((_BYTE *)this + 8) = v4;
  v8 = *(_QWORD *)(a2 + 16);
  tson::output_archive::write_name(this, 0);
  v9 = (char *)this + 24;
  v10 = *((_QWORD *)this + 16);
  if ( v10 >= 0x19 )
  {
    *v9 = 1;
  }
  else
  {
    *(_DWORD *)&v9[4 * v10 + 4] = 0;
    v10 = ++*((_QWORD *)this + 16);
  }
  v11 = *(_QWORD *)(v8 + 16);
  if ( v10 )
  {
    v12 = (char *)this + 4 * v10 + 20;
  }
  else
  {
    *v9 = 1;
    v12 = (char *)this + 24;
  }
  *((_DWORD *)v12 + 1) = 2;
  if ( v11 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v11;
  v13 = *(void ***)v8;
  v14 = *(_QWORD *)v8 + 8LL * *(_QWORD *)(v8 + 16);
  if ( *(_QWORD *)v8 != v14 )
  {
    do
    {
      v15 = *v13;
      if ( *v13 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
      }
      else
      {
        v16 = 0;
      }
      if ( tson::output_archive::write_name(this, v15 == 0) )
      {
        v17 = *((_QWORD *)this + 18);
        if ( *(_QWORD *)(v17 + 2072) < *(_QWORD *)(v17 + 2080)
          || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
        {
          *(_BYTE *)(*(_QWORD *)(v17 + 2072))++ = 23;
        }
        tson::output_archive::write_string_bytes(this, v16, v15, v16);
      }
      ++v13;
    }
    while ( v13 != (void **)v14 );
    v5 = a4;
  }
  tson::output_archive::finishNode(this);
  v18 = *a3;
  *((_BYTE *)this + 8) = *((_BYTE *)a3 + 8);
  *(_QWORD *)this = v18;
  v19 = a3[2];
  tson::output_archive::write_name(this, 0);
  v20 = *((_QWORD *)this + 16);
  if ( v20 >= 0x19 )
  {
    *v9 = 1;
  }
  else
  {
    *(_DWORD *)&v9[4 * v20 + 4] = 0;
    v20 = ++*((_QWORD *)this + 16);
  }
  v21 = *(_QWORD *)(v19 + 16);
  if ( v20 )
  {
    v22 = (char *)this + 4 * v20 + 20;
  }
  else
  {
    *v9 = 1;
    v22 = (char *)this + 24;
  }
  *((_DWORD *)v22 + 1) = 2;
  if ( v21 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v21;
  v23 = *(struct tson::output_archive **)v19;
  v24 = *(_QWORD *)v19 + 168LL * *(_QWORD *)(v19 + 16);
  while ( v23 != (struct tson::output_archive *)v24 )
  {
    tson::output_archive::write_name(this, 0);
    v26 = *((_QWORD *)this + 16);
    if ( v26 >= 0x19 )
    {
      *v9 = 1;
    }
    else
    {
      *(_DWORD *)&v9[4 * v26 + 4] = 0;
      ++*((_QWORD *)this + 16);
    }
    tson::save_nothrow(this, v23, v25);
    tson::output_archive::finishNode(this);
    v23 = (struct tson::output_archive *)((char *)v23 + 168);
  }
  tson::output_archive::finishNode(this);
  v27 = *v5;
  *((_BYTE *)this + 8) = *((_BYTE *)v5 + 8);
  *(_QWORD *)this = v27;
  v28 = v5[2];
  tson::output_archive::write_name(this, 0);
  v29 = *((_QWORD *)this + 16);
  if ( v29 >= 0x19 )
  {
    *v9 = 1;
  }
  else
  {
    *(_DWORD *)&v9[4 * v29 + 4] = 0;
    v29 = ++*((_QWORD *)this + 16);
  }
  v30 = *(_QWORD *)(v28 + 16);
  if ( v29 )
  {
    v31 = (char *)this + 4 * v29 + 20;
  }
  else
  {
    *v9 = 1;
    v31 = (char *)this + 24;
  }
  *((_DWORD *)v31 + 1) = 2;
  if ( v30 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v30;
  v32 = *(struct tson::output_archive **)v28;
  v33 = *(_QWORD *)v28 + 104LL * *(_QWORD *)(v28 + 16);
  while ( v32 != (struct tson::output_archive *)v33 )
  {
    tson::output_archive::write_name(this, 0);
    v35 = *((_QWORD *)this + 16);
    if ( v35 >= 0x19 )
    {
      *v9 = 1;
    }
    else
    {
      *(_DWORD *)&v9[4 * v35 + 4] = 0;
      ++*((_QWORD *)this + 16);
    }
    tson::save_nothrow(this, v32, v34);
    tson::output_archive::finishNode(this);
    v32 = (struct tson::output_archive *)((char *)v32 + 104);
  }
  tson::output_archive::finishNode(this);
}

```

## disassembly

```asm
0x18000b194  mov     [rsp+arg_18], r9
0x18000b199  push    rbx
0x18000b19a  push    rbp
0x18000b19b  push    rsi
0x18000b19c  push    rdi
0x18000b19d  push    r12
0x18000b19f  push    r13
0x18000b1a1  push    r14
0x18000b1a3  push    r15
0x18000b1a5  sub     rsp, 48h
0x18000b1a9  mov     r10b, [rdx+8]
0x18000b1ad  mov     r15, r9
0x18000b1b0  mov     rax, [rdx]
0x18000b1b3  mov     r13, r8
0x18000b1b6  mov     [rcx], rax
0x18000b1b9  mov     rdi, rcx
0x18000b1bc  mov     [rcx+8], r10b
0x18000b1c0  mov     rsi, [rdx+10h]
0x18000b1c4  xor     edx, edx; bool
0x18000b1c6  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000b1cb  lea     rbx, [rdi+18h]
0x18000b1cf  mov     rax, [rbx+68h]
0x18000b1d3  cmp     rax, 19h
0x18000b1d7  jnb     short loc_18000B1EB
0x18000b1d9  mov     dword ptr [rbx+rax*4+4], 0
0x18000b1e1  inc     qword ptr [rbx+68h]
0x18000b1e5  mov     rax, [rbx+68h]
0x18000b1e9  jmp     short loc_18000B1EE
0x18000b1eb  mov     byte ptr [rbx], 1
0x18000b1ee  mov     rdx, [rsi+10h]
0x18000b1f2  test    rax, rax
0x18000b1f5  jz      short loc_18000B201
0x18000b1f7  lea     rcx, [rbx-4]
0x18000b1fb  lea     rcx, [rcx+rax*4]
0x18000b1ff  jmp     short loc_18000B207
0x18000b201  mov     byte ptr [rbx], 1
0x18000b204  mov     rcx, rbx
0x18000b207  mov     dword ptr [rcx+4], 2
0x18000b20e  cmp     rdx, 0FFFFh
0x18000b215  jbe     short loc_18000B22A
0x18000b217  cmp     dword ptr [rdi+88h], 0
0x18000b21e  jl      short loc_18000B22A
0x18000b220  mov     dword ptr [rdi+88h], 8000000Bh
0x18000b22a  mov     [rdi+0Ah], dx
0x18000b22e  mov     r14, [rsi]
0x18000b231  mov     rax, [rsi+10h]
0x18000b235  lea     r12, [r14+rax*8]
0x18000b239  cmp     r14, r12
0x18000b23c  jz      loc_18000B2C9
0x18000b242  mov     r15, [r14]
0x18000b245  test    r15, r15
0x18000b248  jz      short loc_18000B25A
0x18000b24a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b24e  inc     rbp
0x18000b251  cmp     byte ptr [r15+rbp], 0
0x18000b256  jnz     short loc_18000B24E
0x18000b258  jmp     short loc_18000B25C
0x18000b25a  xor     ebp, ebp
0x18000b25c  test    r15, r15
0x18000b25f  mov     rcx, rdi; this
0x18000b262  setz    dl; bool
0x18000b265  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000b26a  test    al, al
0x18000b26c  jz      short loc_18000B2B8
0x18000b26e  mov     rsi, [rdi+90h]
0x18000b275  mov     rax, [rsi+820h]
0x18000b27c  cmp     [rsi+818h], rax
0x18000b283  jb      short loc_18000B296
0x18000b285  mov     edx, 1; unsigned __int64
0x18000b28a  mov     rcx, rsi; this
0x18000b28d  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000b292  test    al, al
0x18000b294  jz      short loc_18000B2A7
0x18000b296  mov     rax, [rsi+818h]
0x18000b29d  mov     byte ptr [rax], 17h
0x18000b2a0  inc     qword ptr [rsi+818h]
0x18000b2a7  mov     r9, rbp; unsigned __int64
0x18000b2aa  mov     r8, r15; void *
0x18000b2ad  mov     rdx, rbp; unsigned __int64
0x18000b2b0  mov     rcx, rdi; this
0x18000b2b3  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x18000b2b8  add     r14, 8
0x18000b2bc  cmp     r14, r12
0x18000b2bf  jnz     short loc_18000B242
0x18000b2c1  mov     r15, [rsp+88h+arg_18]
0x18000b2c9  mov     rcx, rdi; this
0x18000b2cc  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000b2d1  mov     cl, [r13+8]
0x18000b2d5  xor     edx, edx; bool
0x18000b2d7  mov     rax, [r13+0]
0x18000b2db  mov     [rdi+8], cl
0x18000b2de  mov     rcx, rdi; this
0x18000b2e1  mov     [rdi], rax
0x18000b2e4  mov     r14, [r13+10h]
0x18000b2e8  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000b2ed  mov     rax, [rbx+68h]
0x18000b2f1  cmp     rax, 19h
0x18000b2f5  jnb     short loc_18000B309
0x18000b2f7  mov     dword ptr [rbx+rax*4+4], 0
0x18000b2ff  inc     qword ptr [rbx+68h]
0x18000b303  mov     rax, [rbx+68h]
0x18000b307  jmp     short loc_18000B30C
0x18000b309  mov     byte ptr [rbx], 1
0x18000b30c  mov     rdx, [r14+10h]
0x18000b310  test    rax, rax
0x18000b313  jz      short loc_18000B31F
0x18000b315  lea     rcx, [rbx-4]
0x18000b319  lea     rcx, [rcx+rax*4]
0x18000b31d  jmp     short loc_18000B325
0x18000b31f  mov     byte ptr [rbx], 1
0x18000b322  mov     rcx, rbx
0x18000b325  mov     dword ptr [rcx+4], 2
0x18000b32c  cmp     rdx, 0FFFFh
0x18000b333  jbe     short loc_18000B348
0x18000b335  cmp     dword ptr [rdi+88h], 0
0x18000b33c  jl      short loc_18000B348
0x18000b33e  mov     dword ptr [rdi+88h], 8000000Bh
0x18000b348  mov     [rdi+0Ah], dx
0x18000b34c  imul    rbp, [r14+10h], 0A8h
0x18000b354  mov     rsi, [r14]
0x18000b357  add     rbp, rsi
0x18000b35a  jmp     short loc_18000B398
0x18000b35c  xor     edx, edx; bool
0x18000b35e  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000b363  mov     rax, [rbx+68h]
0x18000b367  cmp     rax, 19h
0x18000b36b  jnb     short loc_18000B37B
0x18000b36d  mov     dword ptr [rbx+rax*4+4], 0
0x18000b375  inc     qword ptr [rbx+68h]
0x18000b379  jmp     short loc_18000B37E
0x18000b37b  mov     byte ptr [rbx], 1
0x18000b37e  mov     rdx, rsi; struct tson::output_archive *
0x18000b381  mov     rcx, rdi; this
0x18000b384  call    ?save_nothrow@tson@@YAXAEAVoutput_archive@1@AEAVStoredFailureInfo@wil@@@Z; tson::save_nothrow(tson::output_archive &,wil::StoredFailureInfo &)
0x18000b389  mov     rcx, rdi; this
0x18000b38c  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000b391  add     rsi, 0A8h
0x18000b398  mov     rcx, rdi; this
0x18000b39b  cmp     rsi, rbp
0x18000b39e  jnz     short loc_18000B35C
0x18000b3a0  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000b3a5  mov     cl, [r15+8]
0x18000b3a9  xor     edx, edx; bool
0x18000b3ab  mov     rax, [r15]
0x18000b3ae  mov     [rdi+8], cl
0x18000b3b1  mov     rcx, rdi; this
0x18000b3b4  mov     [rdi], rax
0x18000b3b7  mov     r14, [r15+10h]
0x18000b3bb  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000b3c0  mov     rax, [rbx+68h]
0x18000b3c4  cmp     rax, 19h
0x18000b3c8  jnb     short loc_18000B3DC
0x18000b3ca  mov     dword ptr [rbx+rax*4+4], 0
0x18000b3d2  inc     qword ptr [rbx+68h]
0x18000b3d6  mov     rax, [rbx+68h]
0x18000b3da  jmp     short loc_18000B3DF
0x18000b3dc  mov     byte ptr [rbx], 1
0x18000b3df  mov     rdx, [r14+10h]
0x18000b3e3  test    rax, rax
0x18000b3e6  jz      short loc_18000B3F2
0x18000b3e8  lea     rcx, [rbx-4]
0x18000b3ec  lea     rcx, [rcx+rax*4]
0x18000b3f0  jmp     short loc_18000B3F8
0x18000b3f2  mov     byte ptr [rbx], 1
0x18000b3f5  mov     rcx, rbx
0x18000b3f8  mov     dword ptr [rcx+4], 2
0x18000b3ff  cmp     rdx, 0FFFFh
0x18000b406  jbe     short loc_18000B41B
0x18000b408  cmp     dword ptr [rdi+88h], 0
0x18000b40f  jl      short loc_18000B41B
0x18000b411  mov     dword ptr [rdi+88h], 8000000Bh
0x18000b41b  mov     [rdi+0Ah], dx
0x18000b41f  imul    rbp, [r14+10h], 68h ; 'h'
0x18000b424  mov     rsi, [r14]
0x18000b427  add     rbp, rsi
0x18000b42a  jmp     short loc_18000B465
0x18000b42c  xor     edx, edx; bool
0x18000b42e  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000b433  mov     rax, [rbx+68h]
0x18000b437  cmp     rax, 19h
0x18000b43b  jnb     short loc_18000B44B
0x18000b43d  mov     dword ptr [rbx+rax*4+4], 0
0x18000b445  inc     qword ptr [rbx+68h]
0x18000b449  jmp     short loc_18000B44E
0x18000b44b  mov     byte ptr [rbx], 1
0x18000b44e  mov     rdx, rsi; struct tson::output_archive *
0x18000b451  mov     rcx, rdi; this
0x18000b454  call    ?save_nothrow@tson@@YAXAEAVoutput_archive@1@AEAUtest_flag@tip2@@@Z; tson::save_nothrow(tson::output_archive &,tip2::test_flag &)
0x18000b459  mov     rcx, rdi; this
0x18000b45c  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000b461  add     rsi, 68h ; 'h'
0x18000b465  mov     rcx, rdi; this
0x18000b468  cmp     rsi, rbp
0x18000b46b  jnz     short loc_18000B42C
0x18000b46d  add     rsp, 48h
0x18000b471  pop     r15
0x18000b473  pop     r14
0x18000b475  pop     r13
0x18000b477  pop     r12
0x18000b479  pop     rdi
0x18000b47a  pop     rsi
0x18000b47b  pop     rbp
0x18000b47c  pop     rbx
0x18000b47d  jmp     ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
```
