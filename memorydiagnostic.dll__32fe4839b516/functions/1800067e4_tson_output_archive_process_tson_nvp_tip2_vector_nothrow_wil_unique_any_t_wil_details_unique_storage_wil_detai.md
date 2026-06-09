# tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x1800067e4`
- end: `0x180006a05`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `545`
- prototype: `__int64 __fastcall(tson *this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180019660`
- `0x180019820`

## callees

- `0x1800066e4`
- `0x1800067e4`
- `0x18001758c`
- `0x1800189d0`
- `0x180019060`
- `0x18001a160`

## pseudocode

```c
__int64 __fastcall tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        tson *this,
        __int64 a2,
        __int64 *a3)
{
  char v3; // r10
  __int64 v6; // rsi
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // r14
  __int64 v10; // rax
  _QWORD *v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rsi
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  struct tson::output_archive *v18; // rdi
  __int64 v19; // rsi
  struct wil::StoredFailureInfo *v20; // r8
  unsigned __int64 v21; // rax
  __int128 v23; // [rsp+20h] [rbp-40h]
  __int128 v24; // [rsp+40h] [rbp-20h] BYREF
  __int64 v25; // [rsp+50h] [rbp-10h]

  v3 = *(_BYTE *)(a2 + 8);
  *(_QWORD *)this = *(_QWORD *)a2;
  *((_BYTE *)this + 8) = v3;
  v6 = *(_QWORD *)(a2 + 16);
  tson::output_archive::write_name(this, 0);
  v7 = *((_QWORD *)this + 16);
  if ( v7 >= 0x19 )
  {
    *((_BYTE *)this + 24) = 1;
  }
  else
  {
    *((_DWORD *)this + v7 + 7) = 0;
    v7 = ++*((_QWORD *)this + 16);
  }
  v8 = *(_QWORD *)(v6 + 16);
  v9 = 4;
  if ( v7 )
  {
    v10 = 4 * v7;
  }
  else
  {
    *((_BYTE *)this + 24) = 1;
    v10 = 4;
  }
  *(_DWORD *)((char *)this + v10 + 24) = 2;
  if ( v8 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v8;
  v11 = *(_QWORD **)v6;
  v12 = *(_QWORD *)v6 + 8LL * *(_QWORD *)(v6 + 16);
  while ( v11 != (_QWORD *)v12 )
  {
    *(_QWORD *)&v23 = *v11;
    if ( *v11 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_BYTE *)(*v11 + v13) );
      *((_QWORD *)&v23 + 1) = v13;
    }
    else
    {
      v23 = 0u;
    }
    v25 = 0;
    v24 = v23;
    tson::output_archive::saveValue(this, &v24);
    ++v11;
  }
  tson::output_archive::finishNode(this);
  v14 = *a3;
  *((_BYTE *)this + 8) = *((_BYTE *)a3 + 8);
  *(_QWORD *)this = v14;
  v15 = a3[2];
  tson::output_archive::write_name(this, 0);
  v16 = *((_QWORD *)this + 16);
  if ( v16 >= 0x19 )
  {
    *((_BYTE *)this + 24) = 1;
  }
  else
  {
    *((_DWORD *)this + v16 + 7) = 0;
    v16 = ++*((_QWORD *)this + 16);
  }
  v17 = *(_QWORD *)(v15 + 16);
  if ( v16 )
    v9 = 4 * v16;
  else
    *((_BYTE *)this + 24) = 1;
  *(_DWORD *)((char *)this + v9 + 24) = 2;
  if ( v17 > 0xFFFF && *((int *)this + 34) >= 0 )
    *((_DWORD *)this + 34) = -2147483637;
  *((_WORD *)this + 5) = v17;
  v18 = *(struct tson::output_archive **)v15;
  v19 = *(_QWORD *)v15 + 168LL * *(_QWORD *)(v15 + 16);
  while ( v18 != (struct tson::output_archive *)v19 )
  {
    tson::output_archive::write_name(this, 0);
    v21 = *((_QWORD *)this + 16);
    if ( v21 >= 0x19 )
    {
      *((_BYTE *)this + 24) = 1;
    }
    else
    {
      *((_DWORD *)this + v21 + 7) = 0;
      ++*((_QWORD *)this + 16);
    }
    tson::save_nothrow(this, v18, v20);
    tson::output_archive::finishNode(this);
    v18 = (struct tson::output_archive *)((char *)v18 + 168);
  }
  tson::output_archive::finishNode(this);
  return tson::output_archive::process<tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(this);
}

```

## disassembly

```asm
0x1800067e4  mov     rax, rsp
0x1800067e7  mov     [rax+8], rbx
0x1800067eb  mov     [rax+10h], rsi
0x1800067ef  mov     [rax+18h], rdi
0x1800067f3  mov     [rax+20h], r12
0x1800067f7  push    rbp
0x1800067f8  push    r14
0x1800067fa  push    r15
0x1800067fc  mov     rbp, rsp
0x1800067ff  sub     rsp, 60h
0x180006803  mov     r10b, [rdx+8]
0x180006807  mov     r12, r9
0x18000680a  mov     rax, [rdx]
0x18000680d  mov     r15, r8
0x180006810  mov     [rcx], rax
0x180006813  mov     rbx, rcx
0x180006816  mov     [rcx+8], r10b
0x18000681a  mov     rsi, [rdx+10h]
0x18000681e  xor     edx, edx; bool
0x180006820  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x180006825  mov     rax, [rbx+80h]
0x18000682c  cmp     rax, 19h
0x180006830  jnb     short loc_180006847
0x180006832  and     dword ptr [rbx+rax*4+1Ch], 0
0x180006837  inc     qword ptr [rbx+80h]
0x18000683e  mov     rax, [rbx+80h]
0x180006845  jmp     short loc_18000684B
0x180006847  mov     byte ptr [rbx+18h], 1
0x18000684b  mov     rcx, [rsi+10h]
0x18000684f  mov     r14d, 4
0x180006855  test    rax, rax
0x180006858  jz      short loc_180006860
0x18000685a  shl     rax, 2
0x18000685e  jmp     short loc_180006867
0x180006860  mov     byte ptr [rbx+18h], 1
0x180006864  mov     rax, r14
0x180006867  mov     dword ptr [rbx+rax+18h], 2
0x18000686f  cmp     rcx, 0FFFFh
0x180006876  jbe     short loc_18000688B
0x180006878  cmp     dword ptr [rbx+88h], 0
0x18000687f  jl      short loc_18000688B
0x180006881  mov     dword ptr [rbx+88h], 8000000Bh
0x18000688b  mov     [rbx+0Ah], cx
0x18000688f  mov     rdi, [rsi]
0x180006892  mov     rax, [rsi+10h]
0x180006896  lea     rsi, [rdi+rax*8]
0x18000689a  jmp     short loc_1800068F2
0x18000689c  mov     rax, [rdi]
0x18000689f  mov     qword ptr [rbp+var_40], rax
0x1800068a3  test    rax, rax
0x1800068a6  jz      short loc_1800068BB
0x1800068a8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800068ac  inc     rcx
0x1800068af  cmp     byte ptr [rax+rcx], 0
0x1800068b3  jnz     short loc_1800068AC
0x1800068b5  mov     qword ptr [rbp+var_40+8], rcx
0x1800068b9  jmp     short loc_1800068C0
0x1800068bb  and     qword ptr [rbp+var_40+8], 0
0x1800068c0  movups  xmm0, [rbp+var_40]
0x1800068c4  xor     eax, eax
0x1800068c6  mov     byte ptr [rbp+var_30], 0
0x1800068ca  mov     dword ptr [rbp+var_30+1], eax
0x1800068cd  lea     rdx, [rbp+var_20]
0x1800068d1  mov     word ptr [rbp+var_30+5], ax
0x1800068d5  mov     rcx, rbx
0x1800068d8  mov     byte ptr [rbp+var_30+7], al
0x1800068db  movsd   xmm1, [rbp+var_30]
0x1800068e0  movsd   [rbp+var_10], xmm1
0x1800068e5  movaps  [rbp+var_20], xmm0
0x1800068e9  call    ?saveValue@output_archive@tson@@QEAAXUansistring_tag@2@@Z; tson::output_archive::saveValue(tson::ansistring_tag)
0x1800068ee  add     rdi, 8
0x1800068f2  cmp     rdi, rsi
0x1800068f5  jnz     short loc_18000689C
0x1800068f7  mov     rcx, rbx; this
0x1800068fa  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x1800068ff  mov     cl, [r15+8]
0x180006903  xor     edx, edx; bool
0x180006905  mov     rax, [r15]
0x180006908  mov     [rbx+8], cl
0x18000690b  mov     rcx, rbx; this
0x18000690e  mov     [rbx], rax
0x180006911  mov     rsi, [r15+10h]
0x180006915  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000691a  mov     rax, [rbx+80h]
0x180006921  cmp     rax, 19h
0x180006925  jnb     short loc_18000693C
0x180006927  and     dword ptr [rbx+rax*4+1Ch], 0
0x18000692c  inc     qword ptr [rbx+80h]
0x180006933  mov     rax, [rbx+80h]
0x18000693a  jmp     short loc_180006940
0x18000693c  mov     byte ptr [rbx+18h], 1
0x180006940  mov     rcx, [rsi+10h]
0x180006944  test    rax, rax
0x180006947  jz      short loc_180006953
0x180006949  lea     r14, ds:0[rax*4]
0x180006951  jmp     short loc_180006957
0x180006953  mov     byte ptr [rbx+18h], 1
0x180006957  mov     dword ptr [rbx+r14+18h], 2
0x180006960  cmp     rcx, 0FFFFh
0x180006967  jbe     short loc_18000697C
0x180006969  cmp     dword ptr [rbx+88h], 0
0x180006970  jl      short loc_18000697C
0x180006972  mov     dword ptr [rbx+88h], 8000000Bh
0x18000697c  mov     [rbx+0Ah], cx
0x180006980  mov     rdi, [rsi]
0x180006983  imul    rsi, [rsi+10h], 0A8h
0x18000698b  add     rsi, rdi
0x18000698e  jmp     short loc_1800069D0
0x180006990  xor     edx, edx; bool
0x180006992  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x180006997  mov     rax, [rbx+80h]
0x18000699e  cmp     rax, 19h
0x1800069a2  jnb     short loc_1800069B2
0x1800069a4  and     dword ptr [rbx+rax*4+1Ch], 0
0x1800069a9  inc     qword ptr [rbx+80h]
0x1800069b0  jmp     short loc_1800069B6
0x1800069b2  mov     byte ptr [rbx+18h], 1
0x1800069b6  mov     rdx, rdi; struct tson::output_archive *
0x1800069b9  mov     rcx, rbx; this
0x1800069bc  call    ?save_nothrow@tson@@YAXAEAVoutput_archive@1@AEAVStoredFailureInfo@wil@@@Z; tson::save_nothrow(tson::output_archive &,wil::StoredFailureInfo &)
0x1800069c1  mov     rcx, rbx; this
0x1800069c4  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x1800069c9  add     rdi, 0A8h
0x1800069d0  mov     rcx, rbx; this
0x1800069d3  cmp     rdi, rsi
0x1800069d6  jnz     short loc_180006990
0x1800069d8  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x1800069dd  mov     rdx, r12
0x1800069e0  mov     rcx, rbx; this
0x1800069e3  lea     r11, [rsp+60h+var_s0]
0x1800069e8  mov     rbx, [r11+20h]
0x1800069ec  mov     rsi, [r11+28h]
0x1800069f0  mov     rdi, [r11+30h]
0x1800069f4  mov     r12, [r11+38h]
0x1800069f8  mov     rsp, r11
0x1800069fb  pop     r15
0x1800069fd  pop     r14
0x1800069ff  pop     rbp
0x180006a00  jmp     ??$process@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
```
