# tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x180066208`
- end: `0x180066543`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `827`
- prototype: `__int64 __fastcall(tson *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006a300`

## callees

- `0x1800059a8`
- `0x18000e3e4`
- `0x180063114`
- `0x1800659b0`
- `0x180066208`
- `0x18006a080`
- `0x18006ae8c`
- `0x18006b9b0`
- `0x18006bbd4`
- `0x18006cfdc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006636f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066480`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006636f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066480`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800662ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006635b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006646c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800662ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006635b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006646c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800662fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800662fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800663b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800663b3`

## pseudocode

```c
void __fastcall tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        tson *this,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  char v4; // r10
  _QWORD *v8; // r14
  unsigned __int64 v9; // rdi
  __int64 v10; // rbx
  char *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  _WORD *v15; // rdx
  unsigned __int16 v16; // cx
  unsigned __int64 v17; // rax
  __int64 v18; // rbp
  HANDLE ProcessHeap; // rax
  _QWORD *v20; // r15
  char v21; // al
  _QWORD *v22; // rcx
  void *v23; // rcx
  _QWORD *v24; // rdi
  HANDLE v25; // rax
  void *v26; // rcx
  __int64 v27; // rax
  void **v28; // r14
  __int64 v29; // rbx
  char *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned __int16 *v33; // rcx
  _WORD *v34; // rdx
  unsigned __int16 v35; // cx
  void *v36; // rdi
  HANDLE v37; // rax
  struct wil::StoredFailureInfo *v38; // r8
  __int64 v39; // rax
  _BYTE v40[152]; // [rsp+20h] [rbp-F8h] BYREF
  __int64 v41; // [rsp+B8h] [rbp-60h]
  __int64 v42; // [rsp+C0h] [rbp-58h]
  void *v43; // [rsp+120h] [rbp+8h] BYREF

  v4 = *(_BYTE *)(a2 + 8);
  *((_QWORD *)this + 2) = *(_QWORD *)a2;
  *((_BYTE *)this + 24) = v4;
  v8 = *(_QWORD **)(a2 + 16);
  tson::input_archive::startNode(this);
  v9 = 0;
  v10 = 0;
  if ( !*((_BYTE *)this + 25) )
  {
    v11 = (char *)this + 32;
    v12 = *((_QWORD *)this + 17);
    if ( v12 )
      v11 = &v11[4 * v12 - 4];
    else
      *v11 = 1;
    if ( *((_DWORD *)v11 + 1) != 1 && *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147023267;
    v13 = *(_QWORD *)this;
    v14 = *(unsigned __int16 **)(*(_QWORD *)this + 8LL);
    v15 = v14 + 1;
    if ( (unsigned __int64)(v14 + 1) > *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      v16 = 0;
      *(_BYTE *)(v13 + 24) = 1;
    }
    else
    {
      v16 = *v14;
      *(_QWORD *)(v13 + 8) = v15;
    }
    v10 = v16;
  }
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(v8);
  while ( v10 )
  {
    v43 = 0;
    --v10;
    tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
      this,
      &v43);
    v17 = v8[1];
    if ( v8[2] < v17 )
      goto LABEL_30;
    if ( v17 )
    {
      v18 = 2 * v17;
      if ( 2 * v17 <= v17 )
        goto LABEL_27;
    }
    else
    {
      v18 = 10;
    }
    ProcessHeap = GetProcessHeap();
    v9 = 0;
    v20 = HeapAlloc(ProcessHeap, 0, 8 * v18);
    if ( !v20 )
    {
      v21 = 0;
      goto LABEL_28;
    }
    if ( *v8 )
    {
      if ( v8[2] )
      {
        do
        {
          v22 = (_QWORD *)*v8;
          v20[v9] = *(_QWORD *)(*v8 + 8 * v9);
          v22[v9] = 0;
          v23 = *(void **)(*v8 + 8 * v9);
          if ( v23 )
            CoTaskMemFree(v23);
          ++v9;
        }
        while ( v9 < v8[2] );
      }
      v24 = (_QWORD *)*v8;
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v24);
      v9 = 0;
    }
    *v8 = v20;
    v8[1] = v18;
LABEL_27:
    v21 = 1;
LABEL_28:
    if ( v21 )
    {
LABEL_30:
      *(_QWORD *)(*v8 + 8LL * v8[2]) = v43;
      v26 = 0;
      ++v8[2];
      goto LABEL_31;
    }
    v26 = v43;
LABEL_31:
    if ( v26 )
      CoTaskMemFree(v26);
  }
  tson::input_archive::finishNode(this);
  v27 = *a3;
  *((_BYTE *)this + 24) = *((_BYTE *)a3 + 8);
  *((_QWORD *)this + 2) = v27;
  v28 = (void **)a3[2];
  tson::input_archive::startNode(this);
  v29 = 0;
  if ( !*((_BYTE *)this + 25) )
  {
    v30 = (char *)this + 32;
    v31 = *((_QWORD *)this + 17);
    if ( v31 )
      v30 = &v30[4 * v31 - 4];
    else
      *v30 = 1;
    if ( *((_DWORD *)v30 + 1) != 1 && *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147023267;
    v32 = *(_QWORD *)this;
    v33 = *(unsigned __int16 **)(*(_QWORD *)this + 8LL);
    v34 = v33 + 1;
    if ( (unsigned __int64)(v33 + 1) > *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      v35 = 0;
      *(_BYTE *)(v32 + 24) = 1;
    }
    else
    {
      v35 = *v33;
      *(_QWORD *)(v32 + 8) = v34;
    }
    v29 = v35;
  }
  if ( *v28 )
  {
    if ( v28[2] )
    {
      do
        wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)((char *)*v28 + 168 * v9++));
      while ( v9 < (unsigned __int64)v28[2] );
    }
    v36 = *v28;
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v36);
    *v28 = 0;
  }
  v28[1] = 0;
  for ( v28[2] = 0; v29; --v29 )
  {
    v41 = 0;
    v42 = 0;
    memset_0(v40, 0, sizeof(v40));
    tson::input_archive::startNode(this);
    tson::load_nothrow(this, (struct tson::input_archive *)v40, v38);
    tson::input_archive::finishNode(this);
    tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(v28, v40);
    wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)v40);
  }
  tson::input_archive::finishNode(this);
  v39 = *a4;
  *((_BYTE *)this + 24) = *((_BYTE *)a4 + 8);
  *((_QWORD *)this + 2) = v39;
  tson::input_archive::startNode(this);
  tson::load_nothrow<tip2::test_flag>(this);
  tson::input_archive::finishNode(this);
}

```

## disassembly

```asm
0x180066208  push    rbx
0x18006620a  push    rbp
0x18006620b  push    rsi
0x18006620c  push    rdi
0x18006620d  push    r12
0x18006620f  push    r13
0x180066211  push    r14
0x180066213  push    r15
0x180066215  sub     rsp, 0D8h
0x18006621c  mov     r10b, [rdx+8]
0x180066220  mov     r13, r9
0x180066223  mov     rax, [rdx]
0x180066226  mov     r12, r8
0x180066229  mov     [rcx+10h], rax
0x18006622d  mov     rsi, rcx
0x180066230  mov     [rcx+18h], r10b
0x180066234  mov     r14, [rdx+10h]
0x180066238  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18006623d  xor     edi, edi
0x18006623f  mov     ebx, edi
0x180066241  cmp     [rsi+19h], dil
0x180066245  jnz     short loc_180066296
0x180066247  lea     rax, [rsi+20h]
0x18006624b  mov     rcx, [rax+68h]
0x18006624f  test    rcx, rcx
0x180066252  jz      short loc_18006625E
0x180066254  lea     rax, [rax+rcx*4]
0x180066258  add     rax, 0FFFFFFFFFFFFFFFCh
0x18006625c  jmp     short loc_180066261
0x18006625e  mov     byte ptr [rax], 1
0x180066261  cmp     dword ptr [rax+4], 1
0x180066265  jz      short loc_180066273
0x180066267  cmp     [rsi+8], edi
0x18006626a  jl      short loc_180066273
0x18006626c  mov     dword ptr [rsi+8], 8007065Dh
0x180066273  mov     rax, [rsi]
0x180066276  mov     rcx, [rax+8]
0x18006627a  lea     rdx, [rcx+2]
0x18006627e  cmp     rdx, [rax+10h]
0x180066282  ja      short loc_18006628D
0x180066284  movzx   ecx, word ptr [rcx]
0x180066287  mov     [rax+8], rdx
0x18006628b  jmp     short loc_180066293
0x18006628d  mov     ecx, edi
0x18006628f  mov     byte ptr [rax+18h], 1
0x180066293  movzx   ebx, cx
0x180066296  mov     rcx, r14
0x180066299  call    ?clear@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAAXXZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(void)
0x18006629e  jmp     loc_1800663BF
0x1800662a3  lea     rdx, [rsp+118h+arg_0]
0x1800662ab  mov     [rsp+118h+arg_0], rdi
0x1800662b3  dec     rbx
0x1800662b6  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x1800662bb  mov     rax, [r14+8]
0x1800662bf  cmp     [r14+10h], rax
0x1800662c3  jb      loc_180066394
0x1800662c9  test    rax, rax
0x1800662cc  jz      short loc_1800662DD
0x1800662ce  lea     rbp, [rax+rax]
0x1800662d2  cmp     rbp, rax
0x1800662d5  jbe     loc_180066384
0x1800662db  jmp     short loc_1800662E2
0x1800662dd  mov     ebp, 0Ah
0x1800662e2  lea     rdi, ds:0[rbp*8]
0x1800662ea  call    cs:__imp_GetProcessHeap
0x1800662f1  nop     dword ptr [rax+rax+00h]
0x1800662f6  mov     r8, rdi; dwBytes
0x1800662f9  xor     edx, edx; dwFlags
0x1800662fb  mov     rcx, rax; hHeap
0x1800662fe  call    cs:__imp_HeapAlloc
0x180066305  nop     dword ptr [rax+rax+00h]
0x18006630a  xor     edi, edi
0x18006630c  mov     r15, rax
0x18006630f  test    rax, rax
0x180066312  jnz     short loc_180066319
0x180066314  mov     al, dil
0x180066317  jmp     short loc_180066386
0x180066319  cmp     [r14], rdi
0x18006631c  jz      short loc_18006637D
0x18006631e  cmp     [r14+10h], rdi
0x180066322  jbe     short loc_180066358
0x180066324  mov     rcx, [r14]
0x180066327  mov     rax, [rcx+rdi*8]
0x18006632b  mov     [r15+rdi*8], rax
0x18006632f  mov     qword ptr [rcx+rdi*8], 0
0x180066337  mov     rax, [r14]
0x18006633a  mov     rcx, [rax+rdi*8]; pv
0x18006633e  test    rcx, rcx
0x180066341  jz      short loc_18006634F
0x180066343  call    cs:__imp_CoTaskMemFree
0x18006634a  nop     dword ptr [rax+rax+00h]
0x18006634f  inc     rdi
0x180066352  cmp     rdi, [r14+10h]
0x180066356  jb      short loc_180066324
0x180066358  mov     rdi, [r14]
0x18006635b  call    cs:__imp_GetProcessHeap
0x180066362  nop     dword ptr [rax+rax+00h]
0x180066367  mov     r8, rdi; lpMem
0x18006636a  xor     edx, edx; dwFlags
0x18006636c  mov     rcx, rax; hHeap
0x18006636f  call    cs:__imp_HeapFree
0x180066376  nop     dword ptr [rax+rax+00h]
0x18006637b  xor     edi, edi
0x18006637d  mov     [r14], r15
0x180066380  mov     [r14+8], rbp
0x180066384  mov     al, 1
0x180066386  test    al, al
0x180066388  jnz     short loc_180066394
0x18006638a  mov     rcx, [rsp+118h+arg_0]
0x180066392  jmp     short loc_1800663AE
0x180066394  mov     rdx, [r14+10h]
0x180066398  mov     rcx, [r14]
0x18006639b  mov     rax, [rsp+118h+arg_0]
0x1800663a3  mov     [rcx+rdx*8], rax
0x1800663a7  mov     rcx, rdi; pv
0x1800663aa  inc     qword ptr [r14+10h]
0x1800663ae  test    rcx, rcx
0x1800663b1  jz      short loc_1800663BF
0x1800663b3  call    cs:__imp_CoTaskMemFree
0x1800663ba  nop     dword ptr [rax+rax+00h]
0x1800663bf  mov     rcx, rsi; this
0x1800663c2  test    rbx, rbx
0x1800663c5  jnz     loc_1800662A3
0x1800663cb  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x1800663d0  mov     cl, [r12+8]
0x1800663d5  mov     rax, [r12]
0x1800663d9  mov     [rsi+18h], cl
0x1800663dc  mov     rcx, rsi; this
0x1800663df  mov     [rsi+10h], rax
0x1800663e3  mov     r14, [r12+10h]
0x1800663e8  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x1800663ed  mov     rbx, rdi
0x1800663f0  cmp     [rsi+19h], dil
0x1800663f4  jnz     short loc_180066445
0x1800663f6  lea     rax, [rsi+20h]
0x1800663fa  mov     rcx, [rax+68h]
0x1800663fe  test    rcx, rcx
0x180066401  jz      short loc_18006640D
0x180066403  lea     rax, [rax+rcx*4]
0x180066407  add     rax, 0FFFFFFFFFFFFFFFCh
0x18006640b  jmp     short loc_180066410
0x18006640d  mov     byte ptr [rax], 1
0x180066410  cmp     dword ptr [rax+4], 1
0x180066414  jz      short loc_180066422
0x180066416  cmp     [rsi+8], edi
0x180066419  jl      short loc_180066422
0x18006641b  mov     dword ptr [rsi+8], 8007065Dh
0x180066422  mov     rax, [rsi]
0x180066425  mov     rcx, [rax+8]
0x180066429  lea     rdx, [rcx+2]
0x18006642d  cmp     rdx, [rax+10h]
0x180066431  ja      short loc_18006643C
0x180066433  movzx   ecx, word ptr [rcx]
0x180066436  mov     [rax+8], rdx
0x18006643a  jmp     short loc_180066442
0x18006643c  mov     ecx, edi
0x18006643e  mov     byte ptr [rax+18h], 1
0x180066442  movzx   ebx, cx
0x180066445  cmp     [r14], rdi
0x180066448  jz      short loc_180066491
0x18006644a  cmp     qword ptr [r14+10h], 0
0x18006644f  jbe     short loc_180066469
0x180066451  imul    rcx, rdi, 0A8h
0x180066458  add     rcx, [r14]; this
0x18006645b  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180066460  inc     rdi
0x180066463  cmp     rdi, [r14+10h]
0x180066467  jb      short loc_180066451
0x180066469  mov     rdi, [r14]
0x18006646c  call    cs:__imp_GetProcessHeap
0x180066473  nop     dword ptr [rax+rax+00h]
0x180066478  mov     r8, rdi; lpMem
0x18006647b  xor     edx, edx; dwFlags
0x18006647d  mov     rcx, rax; hHeap
0x180066480  call    cs:__imp_HeapFree
0x180066487  nop     dword ptr [rax+rax+00h]
0x18006648c  xor     edi, edi
0x18006648e  mov     [r14], rdi
0x180066491  mov     [r14+8], rdi
0x180066495  mov     [r14+10h], rdi
0x180066499  test    rbx, rbx
0x18006649c  jz      short loc_1800664FA
0x18006649e  xor     edx, edx; Val
0x1800664a0  mov     [rsp+118h+var_60], rdi
0x1800664a8  mov     r8d, 98h; Size
0x1800664ae  mov     [rsp+118h+var_58], rdi
0x1800664b6  lea     rcx, [rsp+118h+var_F8]; void *
0x1800664bb  call    memset_0
0x1800664c0  mov     rcx, rsi; this
0x1800664c3  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x1800664c8  lea     rdx, [rsp+118h+var_F8]; struct tson::input_archive *
0x1800664cd  mov     rcx, rsi; this
0x1800664d0  call    ?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAVStoredFailureInfo@wil@@@Z; tson::load_nothrow(tson::input_archive &,wil::StoredFailureInfo &)
0x1800664d5  mov     rcx, rsi; this
0x1800664d8  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x1800664dd  lea     rdx, [rsp+118h+var_F8]
0x1800664e2  mov     rcx, r14
0x1800664e5  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x1800664ea  lea     rcx, [rsp+118h+var_F8]; this
0x1800664ef  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x1800664f4  sub     rbx, 1
0x1800664f8  jnz     short loc_18006649E
0x1800664fa  mov     rcx, rsi; this
0x1800664fd  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180066502  mov     cl, [r13+8]
0x180066506  mov     rax, [r13+0]
0x18006650a  mov     [rsi+18h], cl
0x18006650d  mov     rcx, rsi; this
0x180066510  mov     [rsi+10h], rax
0x180066514  mov     rbx, [r13+10h]
0x180066518  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18006651d  mov     rdx, rbx
0x180066520  mov     rcx, rsi; this
0x180066523  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x180066528  mov     rcx, rsi; this
0x18006652b  add     rsp, 0D8h
0x180066532  pop     r15
0x180066534  pop     r14
0x180066536  pop     r13
0x180066538  pop     r12
0x18006653a  pop     rdi
0x18006653b  pop     rsi
0x18006653c  pop     rbp
0x18006653d  pop     rbx
0x18006653e  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
