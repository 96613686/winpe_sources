# tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x180006954`
- end: `0x180006b80`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `556`
- prototype: `__int64 __fastcall(tson *this, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180018680`
- `0x180018844`

## callees

- `0x180006864`
- `0x180006954`
- `0x180016954`
- `0x180017944`
- `0x18001807c`
- `0x180019308`
- `0x18001951c`

## pseudocode

```c
__int64 __fastcall tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        tson *this,
        __int64 a2,
        __int64 *a3)
{
  char v3; // r10
  __int64 v6; // rsi
  _BYTE *v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rdx
  char *v10; // rcx
  void **v11; // r14
  __int64 v12; // r12
  _BYTE *v13; // r15
  unsigned __int64 v14; // rbp
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // r14
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  char *v20; // rcx
  struct tson::output_archive *v21; // rsi
  __int64 v22; // rbp
  struct wil::StoredFailureInfo *v23; // r8
  unsigned __int64 v24; // rax

  v3 = *(_BYTE *)(a2 + 8);
  *(_QWORD *)this = *(_QWORD *)a2;
  *((_BYTE *)this + 8) = v3;
  v6 = *(_QWORD *)(a2 + 16);
  tson::output_archive::write_name(this, 0);
  v7 = (char *)this + 24;
  v8 = *((_QWORD *)this + 16);
  if ( v8 >= 0x19 )
  {
    *v7 = 1;
  }
  else
  {
    *(_DWORD *)&v7[4 * v8 + 4] = 0;
    v8 = ++*((_QWORD *)this + 16);
  }
  v9 = *(_QWORD *)(v6 + 16);
  if ( v8 )
  {
    v10 = (char *)this + 4 * v8 + 20;
  }
  else
  {
    *v7 = 1;
    v10 = (char *)this + 24;
  }
  *((_DWORD *)v10 + 1) = 2;
  if ( v9 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v9;
  v11 = *(void ***)v6;
  v12 = *(_QWORD *)v6 + 8LL * *(_QWORD *)(v6 + 16);
  if ( *(_QWORD *)v6 != v12 )
  {
    do
    {
      v13 = *v11;
      if ( *v11 )
      {
        v14 = -1;
        do
          ++v14;
        while ( v13[v14] );
      }
      else
      {
        v14 = 0;
      }
      if ( tson::output_archive::write_name(this, v13 == 0) )
      {
        v15 = *((_QWORD *)this + 18);
        if ( *(_QWORD *)(v15 + 2072) < *(_QWORD *)(v15 + 2080)
          || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
        {
          *(_BYTE *)(*(_QWORD *)(v15 + 2072))++ = 23;
        }
        tson::output_archive::write_string_bytes(this, v14, v13, v14);
      }
      ++v11;
    }
    while ( v11 != (void **)v12 );
  }
  tson::output_archive::finishNode(this);
  v16 = *a3;
  *((_BYTE *)this + 8) = *((_BYTE *)a3 + 8);
  *(_QWORD *)this = v16;
  v17 = a3[2];
  tson::output_archive::write_name(this, 0);
  v18 = *((_QWORD *)this + 16);
  if ( v18 >= 0x19 )
  {
    *v7 = 1;
  }
  else
  {
    *(_DWORD *)&v7[4 * v18 + 4] = 0;
    v18 = ++*((_QWORD *)this + 16);
  }
  v19 = *(_QWORD *)(v17 + 16);
  if ( v18 )
  {
    v20 = (char *)this + 4 * v18 + 20;
  }
  else
  {
    *v7 = 1;
    v20 = (char *)this + 24;
  }
  *((_DWORD *)v20 + 1) = 2;
  if ( v19 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v19;
  v21 = *(struct tson::output_archive **)v17;
  v22 = *(_QWORD *)v17 + 168LL * *(_QWORD *)(v17 + 16);
  while ( v21 != (struct tson::output_archive *)v22 )
  {
    tson::output_archive::write_name(this, 0);
    v24 = *((_QWORD *)this + 16);
    if ( v24 >= 0x19 )
    {
      *v7 = 1;
    }
    else
    {
      *(_DWORD *)&v7[4 * v24 + 4] = 0;
      ++*((_QWORD *)this + 16);
    }
    tson::save_nothrow(this, v21, v23);
    tson::output_archive::finishNode(this);
    v21 = (struct tson::output_archive *)((char *)v21 + 168);
  }
  tson::output_archive::finishNode(this);
  return tson::output_archive::process<tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(this);
}

```

## disassembly

```asm
0x180006954  mov     [rsp+arg_18], r9
0x180006959  push    rbx
0x18000695a  push    rbp
0x18000695b  push    rsi
0x18000695c  push    rdi
0x18000695d  push    r12
0x18000695f  push    r13
0x180006961  push    r14
0x180006963  push    r15
0x180006965  sub     rsp, 48h
0x180006969  mov     r10b, [rdx+8]
0x18000696d  mov     r15, r9
0x180006970  mov     rax, [rdx]
0x180006973  mov     r13, r8
0x180006976  mov     [rcx], rax
0x180006979  mov     rdi, rcx
0x18000697c  mov     [rcx+8], r10b
0x180006980  mov     rsi, [rdx+10h]
0x180006984  xor     edx, edx; bool
0x180006986  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000698b  lea     rbx, [rdi+18h]
0x18000698f  mov     rax, [rbx+68h]
0x180006993  cmp     rax, 19h
0x180006997  jnb     short loc_1800069AB
0x180006999  mov     dword ptr [rbx+rax*4+4], 0
0x1800069a1  inc     qword ptr [rbx+68h]
0x1800069a5  mov     rax, [rbx+68h]
0x1800069a9  jmp     short loc_1800069AE
0x1800069ab  mov     byte ptr [rbx], 1
0x1800069ae  mov     rdx, [rsi+10h]
0x1800069b2  test    rax, rax
0x1800069b5  jz      short loc_1800069C1
0x1800069b7  lea     rcx, [rbx-4]
0x1800069bb  lea     rcx, [rcx+rax*4]
0x1800069bf  jmp     short loc_1800069C7
0x1800069c1  mov     byte ptr [rbx], 1
0x1800069c4  mov     rcx, rbx
0x1800069c7  mov     dword ptr [rcx+4], 2
0x1800069ce  cmp     rdx, 0FFFFh
0x1800069d5  jbe     short loc_1800069EA
0x1800069d7  cmp     dword ptr [rdi+88h], 0
0x1800069de  jl      short loc_1800069EA
0x1800069e0  mov     dword ptr [rdi+88h], 8000000Bh
0x1800069ea  mov     [rdi+0Ah], dx
0x1800069ee  mov     r14, [rsi]
0x1800069f1  mov     rax, [rsi+10h]
0x1800069f5  lea     r12, [r14+rax*8]
0x1800069f9  cmp     r14, r12
0x1800069fc  jz      loc_180006A89
0x180006a02  mov     r15, [r14]
0x180006a05  test    r15, r15
0x180006a08  jz      short loc_180006A1A
0x180006a0a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006a0e  inc     rbp
0x180006a11  cmp     byte ptr [r15+rbp], 0
0x180006a16  jnz     short loc_180006A0E
0x180006a18  jmp     short loc_180006A1C
0x180006a1a  xor     ebp, ebp
0x180006a1c  test    r15, r15
0x180006a1f  mov     rcx, rdi; this
0x180006a22  setz    dl; bool
0x180006a25  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x180006a2a  test    al, al
0x180006a2c  jz      short loc_180006A78
0x180006a2e  mov     rsi, [rdi+90h]
0x180006a35  mov     rax, [rsi+820h]
0x180006a3c  cmp     [rsi+818h], rax
0x180006a43  jb      short loc_180006A56
0x180006a45  mov     edx, 1; unsigned __int64
0x180006a4a  mov     rcx, rsi; this
0x180006a4d  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180006a52  test    al, al
0x180006a54  jz      short loc_180006A67
0x180006a56  mov     rax, [rsi+818h]
0x180006a5d  mov     byte ptr [rax], 17h
0x180006a60  inc     qword ptr [rsi+818h]
0x180006a67  mov     r9, rbp; unsigned __int64
0x180006a6a  mov     r8, r15; void *
0x180006a6d  mov     rdx, rbp; unsigned __int64
0x180006a70  mov     rcx, rdi; this
0x180006a73  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x180006a78  add     r14, 8
0x180006a7c  cmp     r14, r12
0x180006a7f  jnz     short loc_180006A02
0x180006a81  mov     r15, [rsp+88h+arg_18]
0x180006a89  mov     rcx, rdi; this
0x180006a8c  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x180006a91  mov     cl, [r13+8]
0x180006a95  xor     edx, edx; bool
0x180006a97  mov     rax, [r13+0]
0x180006a9b  mov     [rdi+8], cl
0x180006a9e  mov     rcx, rdi; this
0x180006aa1  mov     [rdi], rax
0x180006aa4  mov     r14, [r13+10h]
0x180006aa8  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x180006aad  mov     rax, [rbx+68h]
0x180006ab1  cmp     rax, 19h
0x180006ab5  jnb     short loc_180006AC9
0x180006ab7  mov     dword ptr [rbx+rax*4+4], 0
0x180006abf  inc     qword ptr [rbx+68h]
0x180006ac3  mov     rax, [rbx+68h]
0x180006ac7  jmp     short loc_180006ACC
0x180006ac9  mov     byte ptr [rbx], 1
0x180006acc  mov     rdx, [r14+10h]
0x180006ad0  test    rax, rax
0x180006ad3  jz      short loc_180006ADF
0x180006ad5  lea     rcx, [rbx-4]
0x180006ad9  lea     rcx, [rcx+rax*4]
0x180006add  jmp     short loc_180006AE5
0x180006adf  mov     byte ptr [rbx], 1
0x180006ae2  mov     rcx, rbx
0x180006ae5  mov     dword ptr [rcx+4], 2
0x180006aec  cmp     rdx, 0FFFFh
0x180006af3  jbe     short loc_180006B08
0x180006af5  cmp     dword ptr [rdi+88h], 0
0x180006afc  jl      short loc_180006B08
0x180006afe  mov     dword ptr [rdi+88h], 8000000Bh
0x180006b08  mov     [rdi+0Ah], dx
0x180006b0c  imul    rbp, [r14+10h], 0A8h
0x180006b14  mov     rsi, [r14]
0x180006b17  add     rbp, rsi
0x180006b1a  jmp     short loc_180006B58
0x180006b1c  xor     edx, edx; bool
0x180006b1e  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x180006b23  mov     rax, [rbx+68h]
0x180006b27  cmp     rax, 19h
0x180006b2b  jnb     short loc_180006B3B
0x180006b2d  mov     dword ptr [rbx+rax*4+4], 0
0x180006b35  inc     qword ptr [rbx+68h]
0x180006b39  jmp     short loc_180006B3E
0x180006b3b  mov     byte ptr [rbx], 1
0x180006b3e  mov     rdx, rsi; struct tson::output_archive *
0x180006b41  mov     rcx, rdi; this
0x180006b44  call    ?save_nothrow@tson@@YAXAEAVoutput_archive@1@AEAVStoredFailureInfo@wil@@@Z; tson::save_nothrow(tson::output_archive &,wil::StoredFailureInfo &)
0x180006b49  mov     rcx, rdi; this
0x180006b4c  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x180006b51  add     rsi, 0A8h
0x180006b58  mov     rcx, rdi; this
0x180006b5b  cmp     rsi, rbp
0x180006b5e  jnz     short loc_180006B1C
0x180006b60  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x180006b65  mov     rdx, r15
0x180006b68  mov     rcx, rdi; this
0x180006b6b  add     rsp, 48h
0x180006b6f  pop     r15
0x180006b71  pop     r14
0x180006b73  pop     r13
0x180006b75  pop     r12
0x180006b77  pop     rdi
0x180006b78  pop     rsi
0x180006b79  pop     rbp
0x180006b7a  pop     rbx
0x180006b7b  jmp     ??$process@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
```
