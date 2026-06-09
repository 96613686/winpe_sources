# CResourceCandidate::_CreateStream(Microsoft::Resources::Runtime::CResolvedInstanceInternal *,IStream * *)

- ea: `0x18003a354`
- end: `0x18003a670`
- name: `?_CreateStream@CResourceCandidate@@SAJPEAVCResolvedInstanceInternal@Runtime@Resources@Microsoft@@PEAPEAUIStream@@@Z`
- size: `796`
- prototype: `static int(struct Microsoft::Resources::Runtime::CResolvedInstanceInternal *, struct IStream **)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180079ac0`
- `0x18008cdc0`

## callees

- `0x18000d25c`
- `0x18002c8d0`
- `0x180039ec8`
- `0x180039ef0`
- `0x18003a354`
- `0x18003aa8c`
- `0x18003ae3c`
- `0x18003ae58`
- `0x18003b174`
- `0x18003baa4`
- `0x18003bb0c`
- `0x18003bccc`
- `0x180084154`
- `0x18008bb80`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a657`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a657`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a665`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a665`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800c23e7`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800c23e7`
- `SHCORE!__imp_SHCreateMemoryStreamOnSharedBuffer` at `0x18003a48b`
- `SHCORE!__imp_SHCreateMemoryStreamOnSharedBuffer` at `0x18003a48b`

## string_xrefs

- `0x18003a4ca`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcecandidate.cpp`
- `0x18003a4e5`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcecandidate.cpp`
- `0x18003a542`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcecandidate.cpp`
- `0x1800c23fb`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcecandidate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CResourceCandidate::_CreateStream(
        struct Microsoft::Resources::Runtime::CResolvedInstanceInternal *a1,
        struct IStream **a2)
{
  __int64 v4; // rcx
  unsigned int inited; // ebx
  int v6; // ecx
  int IsValid; // eax
  void *v8; // rcx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  HRESULT v16; // eax
  __int64 v17; // rdx
  int v18; // edi
  void *v19; // rbx
  HANDLE ProcessHeap; // rax
  int pstmTemplate; // [rsp+20h] [rbp-60h]
  int pstmTemplatea; // [rsp+20h] [rbp-60h]
  __int64 v23; // [rsp+40h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-38h] BYREF
  void **v25; // [rsp+50h] [rbp-30h] BYREF
  void *v26; // [rsp+58h] [rbp-28h] BYREF
  int v27; // [rsp+60h] [rbp-20h]
  void *v28; // [rsp+68h] [rbp-18h]
  int v29; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  LPCWSTR pszFile; // [rsp+C8h] [rbp+48h] BYREF
  int v32; // [rsp+D0h] [rbp+50h]
  int v33; // [rsp+D8h] [rbp+58h] BYREF

  *a2 = 0;
  v32 = 0;
  v4 = *((_QWORD *)a1 + 3);
  if ( !v4 )
  {
    inited = -554696695;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28E,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\resourcemap.cpp",
      (const char *)0xDEF00009LL,
      pstmTemplate);
    goto LABEL_35;
  }
  pstmTemplatea = 0;
  inited = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v4 + 72LL))(
             v4,
             *((unsigned int *)a1 + 8),
             0,
             0);
  if ( (inited & 0x80000000) != 0 )
  {
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresolvedinstanceinternal.cpp",
      (const char *)inited,
      pstmTemplatea);
    v14 = 112;
    goto LABEL_17;
  }
  if ( (unsigned __int8)Microsoft::Resources::MrmEnvironment::IsPathResourceValueType((unsigned int)v32) )
  {
    pszFile = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszFile,
      0);
    v16 = CResourceCandidate::_ToValueStringByType(a1, v32, (unsigned __int16 **)&pszFile);
    inited = v16;
    if ( v16 >= 0 )
    {
      v16 = SHCreateStreamOnFileEx(pszFile, 0, 0x80u, 0, 0, a2);
      inited = v16;
      if ( v16 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszFile);
        return 0;
      }
      v17 = 123;
    }
    else
    {
      v17 = 121;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcecandidate.cpp",
      (const char *)(unsigned int)v16,
      pstmTemplatea);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszFile);
    return inited;
  }
  if ( v6 != 2 )
  {
    inited = -2147009779;
    v14 = 163;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcecandidate.cpp",
      (const char *)inited,
      pstmTemplatea);
    return inited;
  }
  lpMem = 0;
  LOBYTE(pszFile) = 0;
  IsValid = Microsoft::Resources::Runtime::CResolvedInstanceInternal::IsValid(a1);
  inited = IsValid;
  if ( IsValid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresolvedinstanceinternal.cpp",
      (const char *)(unsigned int)IsValid,
      0);
    goto LABEL_23;
  }
  v25 = &Microsoft::Resources::BlobResult::`vftable';
  v27 = 0;
  v26 = 0;
  v29 = 0;
  v28 = 0;
  if ( !Microsoft::Resources::ResourceCandidateResult::TryGetBlobValue(
          (struct Microsoft::Resources::Runtime::CResolvedInstanceInternal *)((char *)a1 + 24),
          (struct Microsoft::Resources::BlobResult *)&v25) )
  {
    inited = -2147467259;
    v15 = 43;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresolvedinstanceinternal.cpp",
      (const char *)inited,
      0);
    v25 = &Microsoft::Resources::BlobResult::`vftable';
    DefBlobResult_Clear(&v26);
LABEL_23:
    v14 = 135;
    goto LABEL_17;
  }
  if ( (unsigned int)DefBlobResult_GetType(&v26) == 1 )
  {
    v18 = v27;
    if ( (v28 != v26 || (v26 || !v27) && (v27 || !v26)) && v26 && v27 )
    {
      lpMem = v26;
      inited = DefBlobResult_InitEmpty(&v26, 0);
      if ( (inited & 0x80000000) == 0 )
      {
        LOBYTE(pszFile) = 1;
        v9 = v18;
        goto LABEL_11;
      }
    }
    else
    {
      inited = -2147024809;
    }
    v15 = 53;
    goto LABEL_22;
  }
  v8 = v28;
  if ( v28 == v26 && (!v26 && v27 || !v27 && v26) )
  {
    v9 = 0;
    v8 = 0;
  }
  else
  {
    v9 = v29;
  }
  lpMem = v8;
LABEL_11:
  v25 = &Microsoft::Resources::BlobResult::`vftable';
  DefBlobResult_Clear(&v26);
  v23 = 0;
  v33 = v9;
  Microsoft::WRL::ComPtr<StreamBufferHelper>::InternalRelease(&v23);
  v10 = Microsoft::WRL::Details::MakeAndInitialize<StreamBufferHelper,StreamBufferHelper,void const * &,unsigned int,bool &>(
          &v23,
          &lpMem,
          &v33,
          &pszFile);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = SHCreateMemoryStreamOnSharedBuffer(v23, *(unsigned int *)(v23 + 56), a2);
    inited = v12;
    if ( v12 >= 0 )
    {
      if ( v23 )
      {
        v23 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release();
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcecandidate.cpp",
      (const char *)(unsigned int)v12,
      0);
    if ( v23 )
    {
      v23 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release();
    }
    return inited;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x99,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcecandidate.cpp",
    (const char *)(unsigned int)v10,
    0);
  if ( v23 )
  {
    v23 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release();
  }
  if ( (_BYTE)pszFile )
  {
    v19 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v19);
  }
  return v11;
}

```

## disassembly

```asm
0x18003a354  push    rbp
0x18003a356  push    rbx
0x18003a357  push    rsi
0x18003a358  push    rdi
0x18003a359  push    r12
0x18003a35b  push    r14
0x18003a35d  push    r15
0x18003a35f  mov     rbp, rsp
0x18003a362  sub     rsp, 80h
0x18003a369  mov     r14, rdx
0x18003a36c  mov     rdi, rcx
0x18003a36f  xor     r15d, r15d
0x18003a372  mov     [rdx], r15
0x18003a375  mov     [rbp+arg_10], r15d
0x18003a379  mov     rcx, [rcx+18h]
0x18003a37d  test    rcx, rcx
0x18003a380  jz      loc_18003A5B2
0x18003a386  mov     rax, [rcx]
0x18003a389  lea     rdx, [rbp+arg_10]
0x18003a38d  mov     [rsp+80h+var_50], rdx
0x18003a392  mov     [rsp+80h+ppstm], r15
0x18003a397  mov     [rsp+80h+pstmTemplate], r15; int
0x18003a39c  xor     r9d, r9d
0x18003a39f  xor     r8d, r8d
0x18003a3a2  mov     edx, [rdi+20h]
0x18003a3a5  mov     rax, [rax+48h]
0x18003a3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3ae  mov     ebx, eax
0x18003a3b0  test    eax, eax
0x18003a3b2  js      loc_18003A5CF
0x18003a3b8  mov     ecx, [rbp+arg_10]
0x18003a3bb  call    ?IsPathResourceValueType@MrmEnvironment@Resources@Microsoft@@SA_NW4ResourceValueType@123@@Z; Microsoft::Resources::MrmEnvironment::IsPathResourceValueType(Microsoft::Resources::MrmEnvironment::ResourceValueType)
0x18003a3c0  test    al, al
0x18003a3c2  jnz     loc_18003A5F1
0x18003a3c8  cmp     ecx, 2
0x18003a3cb  jnz     loc_18003A4BD
0x18003a3d1  mov     [rbp+lpMem], r15
0x18003a3d5  mov     byte ptr [rbp+pszFile], r15b
0x18003a3d9  mov     rcx, rdi; this
0x18003a3dc  call    ?IsValid@CResolvedInstanceInternal@Runtime@Resources@Microsoft@@QEBAJXZ; Microsoft::Resources::Runtime::CResolvedInstanceInternal::IsValid(void)
0x18003a3e1  mov     ebx, eax
0x18003a3e3  test    eax, eax
0x18003a3e5  js      loc_18003A576
0x18003a3eb  lea     r12, ??_7BlobResult@Resources@Microsoft@@6B@; const Microsoft::Resources::BlobResult::`vftable'
0x18003a3f2  mov     [rbp+var_30], r12
0x18003a3f6  mov     [rbp+var_20], r15d
0x18003a3fa  mov     [rbp+var_28], r15
0x18003a3fe  mov     [rbp+var_10], r15d
0x18003a402  mov     [rbp+var_18], r15
0x18003a406  lea     rdx, [rbp+var_30]; struct Microsoft::Resources::BlobResult *
0x18003a40a  lea     rcx, [rdi+18h]; this
0x18003a40e  call    ?TryGetBlobValue@ResourceCandidateResult@Resources@Microsoft@@QEBA_NPEAVBlobResult@23@@Z; Microsoft::Resources::ResourceCandidateResult::TryGetBlobValue(Microsoft::Resources::BlobResult *)
0x18003a413  test    al, al
0x18003a415  jz      loc_18003A50A
0x18003a41b  lea     rcx, [rbp+var_28]
0x18003a41f  call    DefBlobResult_GetType
0x18003a424  cmp     eax, 1
0x18003a427  mov     rax, [rbp+var_28]
0x18003a42b  jz      loc_18003A623
0x18003a431  mov     rcx, [rbp+var_18]
0x18003a435  cmp     rcx, rax
0x18003a438  jz      loc_18003A590
0x18003a43e  mov     ebx, [rbp+var_10]
0x18003a441  mov     [rbp+lpMem], rcx
0x18003a445  mov     [rbp+var_30], r12
0x18003a449  lea     rcx, [rbp+var_28]
0x18003a44d  call    DefBlobResult_Clear
0x18003a452  mov     [rbp+var_40], r15
0x18003a456  mov     [rbp+arg_18], ebx
0x18003a459  lea     rcx, [rbp+var_40]
0x18003a45d  call    ?InternalRelease@?$ComPtr@VStreamBufferHelper@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<StreamBufferHelper>::InternalRelease(void)
0x18003a462  lea     r9, [rbp+pszFile]
0x18003a466  lea     r8, [rbp+arg_18]
0x18003a46a  lea     rdx, [rbp+lpMem]
0x18003a46e  lea     rcx, [rbp+var_40]
0x18003a472  call    ??$MakeAndInitialize@VStreamBufferHelper@@V1@AEAPEBXIAEA_N@Details@WRL@Microsoft@@YAJPEAPEAVStreamBufferHelper@@AEAPEBX$$QEAIAEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<StreamBufferHelper,StreamBufferHelper,void const * &,uint,bool &>(StreamBufferHelper * *,void const * &,uint &&,bool &)
0x18003a477  mov     edi, eax
0x18003a479  test    eax, eax
0x18003a47b  js      loc_18003A53B
0x18003a481  mov     rcx, [rbp+var_40]
0x18003a485  mov     r8, r14
0x18003a488  mov     edx, [rcx+38h]
0x18003a48b  call    cs:__imp_SHCreateMemoryStreamOnSharedBuffer
0x18003a491  mov     ebx, eax
0x18003a493  test    eax, eax
0x18003a495  js      short loc_18003A4DE
0x18003a497  mov     rcx, [rbp+var_40]
0x18003a49b  test    rcx, rcx
0x18003a49e  jz      short loc_18003A4A9
0x18003a4a0  mov     [rbp+var_40], r15
0x18003a4a4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release(void)
0x18003a4a9  xor     eax, eax
0x18003a4ab  add     rsp, 80h
0x18003a4b2  pop     r15
0x18003a4b4  pop     r14
0x18003a4b6  pop     r12
0x18003a4b8  pop     rdi
0x18003a4b9  pop     rsi
0x18003a4ba  pop     rbx
0x18003a4bb  pop     rbp
0x18003a4bc  retn
0x18003a4bd  mov     ebx, 80073B0Dh
0x18003a4c2  mov     edx, 0A3h; void *
0x18003a4c7  mov     r9d, ebx; char *
0x18003a4ca  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18003a4d1  mov     rcx, [rbp+38h]; this
0x18003a4d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a4da  mov     eax, ebx
0x18003a4dc  jmp     short loc_18003A4AB
0x18003a4de  mov     rcx, [rbp+38h]; this
0x18003a4e2  mov     r9d, ebx; char *
0x18003a4e5  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18003a4ec  mov     edx, 9Dh; void *
0x18003a4f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a4f6  mov     rcx, [rbp+var_40]
0x18003a4fa  test    rcx, rcx
0x18003a4fd  jz      short loc_18003A4DA
0x18003a4ff  mov     [rbp+var_40], r15
0x18003a503  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release(void)
0x18003a508  jmp     short loc_18003A4DA
0x18003a50a  mov     ebx, 80004005h
0x18003a50f  mov     edx, 2Bh ; '+'; void *
0x18003a514  mov     r9d, ebx; char *
0x18003a517  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18003a51e  mov     rcx, [rbp+38h]; this
0x18003a522  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a527  mov     [rbp+var_30], r12
0x18003a52b  lea     rcx, [rbp+var_28]
0x18003a52f  call    DefBlobResult_Clear
0x18003a534  mov     edx, 87h
0x18003a539  jmp     short loc_18003A4C7
0x18003a53b  mov     rcx, [rbp+38h]; this
0x18003a53f  mov     r9d, edi; char *
0x18003a542  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18003a549  mov     edx, 99h; void *
0x18003a54e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a553  mov     rcx, [rbp+var_40]
0x18003a557  test    rcx, rcx
0x18003a55a  jz      short loc_18003A565
0x18003a55c  mov     [rbp+var_40], r15
0x18003a560  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release(void)
0x18003a565  cmp     byte ptr [rbp+pszFile], r15b
0x18003a569  jnz     loc_18003A653
0x18003a56f  mov     eax, edi
0x18003a571  jmp     loc_18003A4AB
0x18003a576  mov     rcx, [rbp+38h]; this
0x18003a57a  mov     r9d, eax; char *
0x18003a57d  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18003a584  mov     edx, 28h ; '('; void *
0x18003a589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a58e  jmp     short loc_18003A534
0x18003a590  mov     edx, [rbp+var_20]
0x18003a593  test    rax, rax
0x18003a596  jz      loc_18003A646
0x18003a59c  test    edx, edx
0x18003a59e  jnz     loc_18003A43E
0x18003a5a4  test    rax, rax
0x18003a5a7  jz      loc_18003A43E
0x18003a5ad  jmp     loc_1800C246C
0x18003a5b2  mov     rcx, [rbp+38h]; this
0x18003a5b6  mov     ebx, 0DEF00009h
0x18003a5bb  mov     r9d, ebx; char *
0x18003a5be  lea     r8, aMinkernelMrtMr_20; "minkernel\\mrt\\mrm\\mrmmin\\resourcema"...
0x18003a5c5  mov     edx, 28Eh; void *
0x18003a5ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a5cf  mov     rcx, [rbp+38h]; this
0x18003a5d3  mov     r9d, ebx; char *
0x18003a5d6  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18003a5dd  mov     edx, 1FAh; void *
0x18003a5e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a5e7  mov     edx, 70h ; 'p'
0x18003a5ec  jmp     loc_18003A4C7
0x18003a5f1  mov     [rbp+pszFile], r15
0x18003a5f5  xor     edx, edx
0x18003a5f7  lea     rcx, [rbp+pszFile]
0x18003a5fb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003a600  lea     r8, [rbp+pszFile]; unsigned __int16 **
0x18003a604  mov     edx, [rbp+arg_10]; int
0x18003a607  mov     rcx, rdi; struct Microsoft::Resources::Runtime::CResolvedInstanceInternal *
0x18003a60a  call    ?_ToValueStringByType@CResourceCandidate@@CAJPEAVCResolvedInstanceInternal@Runtime@Resources@Microsoft@@HPEAPEAG@Z; CResourceCandidate::_ToValueStringByType(Microsoft::Resources::Runtime::CResolvedInstanceInternal *,int,ushort * *)
0x18003a60f  mov     ebx, eax
0x18003a611  test    eax, eax
0x18003a613  jns     loc_1800C23CE
0x18003a619  mov     edx, 79h ; 'y'
0x18003a61e  jmp     loc_1800C23F8
0x18003a623  mov     edi, [rbp+var_20]
0x18003a626  cmp     [rbp+var_18], rax
0x18003a62a  jnz     loc_1800C2433
0x18003a630  test    rax, rax
0x18003a633  jnz     loc_1800C242A
0x18003a639  test    edi, edi
0x18003a63b  jz      loc_1800C242A
0x18003a641  jmp     loc_1800C245D
0x18003a646  test    edx, edx
0x18003a648  jnz     loc_1800C246C
0x18003a64e  jmp     loc_18003A59C
0x18003a653  mov     rbx, [rbp+lpMem]
0x18003a657  call    cs:__imp_GetProcessHeap
0x18003a65d  mov     r8, rbx; lpMem
0x18003a660  xor     edx, edx; dwFlags
0x18003a662  mov     rcx, rax; hHeap
0x18003a665  call    cs:__imp_HeapFree
0x18003a66b  jmp     loc_18003A56F
0x1800c23ce  mov     [rsp+80h+ppstm], r14; ppstm
0x1800c23d3  mov     [rsp+80h+pstmTemplate], r15; int
0x1800c23d8  xor     r9d, r9d; fCreate
0x1800c23db  xor     edx, edx; grfMode
0x1800c23dd  mov     r8d, 80h; dwAttributes
0x1800c23e3  mov     rcx, [rbp+pszFile]; pszFile
0x1800c23e7  call    cs:__imp_SHCreateStreamOnFileEx
0x1800c23ed  mov     ebx, eax
0x1800c23ef  test    eax, eax
0x1800c23f1  jns     short loc_1800C241B
0x1800c23f3  mov     edx, 7Bh ; '{'; void *
0x1800c23f8  mov     r9d, eax; char *
0x1800c23fb  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x1800c2402  mov     rcx, [rbp+38h]; this
0x1800c2406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c240b  nop
0x1800c240c  lea     rcx, [rbp+pszFile]
0x1800c2410  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c2415  nop
0x1800c2416  jmp     loc_18003A4DA
0x1800c241b  lea     rcx, [rbp+pszFile]
0x1800c241f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c2424  nop
0x1800c2425  jmp     loc_18003A4A9
0x1800c242a  test    edi, edi
0x1800c242c  jnz     short loc_1800C2433
0x1800c242e  test    rax, rax
0x1800c2431  jnz     short loc_1800C245D
0x1800c2433  test    rax, rax
0x1800c2436  jz      short loc_1800C245D
0x1800c2438  test    edi, edi
0x1800c243a  jz      short loc_1800C245D
0x1800c243c  mov     [rbp+lpMem], rax
0x1800c2440  xor     edx, edx
0x1800c2442  lea     rcx, [rbp+var_28]
0x1800c2446  call    _DefBlobResult_InitEmpty
0x1800c244b  mov     ebx, eax
0x1800c244d  test    eax, eax
0x1800c244f  js      short loc_1800C2462
0x1800c2451  mov     byte ptr [rbp+pszFile], 1
0x1800c2455  mov     rbx, rdi
0x1800c2458  jmp     loc_18003A445
0x1800c245d  mov     ebx, 80070057h
0x1800c2462  mov     edx, 35h ; '5'
0x1800c2467  jmp     loc_18003A514
0x1800c246c  mov     rbx, r15
0x1800c246f  mov     rcx, r15
0x1800c2472  jmp     loc_18003A441
```
