# InputSiteManager::GetInputSiteFromInputSinkData(LegacyInputSinkData &&,bool)

- ea: `0x1800188a0`
- end: `0x180018ca5`
- name: `?GetInputSiteFromInputSinkData@InputSiteManager@@AEAA?AV?$ComPtr@VInputSite@@@WRL@Microsoft@@$$QEAVLegacyInputSinkData@@_N@Z`
- size: `1029`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018804`
- `0x180023fb0`

## callees

- `0x18000d58c`
- `0x18001277c`
- `0x180013e14`
- `0x180016e70`
- `0x1800188a0`
- `0x1800262bc`
- `0x180033ce0`
- `0x1800886d0`
- `0x1800af59c`
- `0x1800af5cc`
- `0x1800f0990`
- `0x18012fcf0`
- `0x1801547e8`
- `0x1801ce010`

## import_xrefs

- `win32u!NtQueryCompositionInputQueueAndTransform` at `0x1800189ef`
- `win32u!NtQueryCompositionInputQueueAndTransform` at `0x1800189ef`
- `win32u!NtQueryCompositionInputSinkLuid` at `0x180018918`
- `win32u!NtQueryCompositionInputSinkLuid` at `0x180018918`

## string_xrefs

- `0x180018c93`: `onecoreuap\windows\moderncore\inputv2\components\inputsitemanager\server\legacyinputsinkdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall InputSiteManager::GetInputSiteFromInputSinkData(_QWORD *a1, _QWORD *a2, _BYTE *a3, char a4)
{
  _DWORD *v8; // rax
  __m128i *i; // r15
  __int64 v10; // rdx
  _BYTE *v11; // rdi
  _BYTE *v12; // r14
  __int128 v13; // xmm1
  __int64 v14; // rax
  void *v15; // rdi
  char **v16; // rdx
  char *v17; // rcx
  __int64 v18; // rdi
  __int64 *DuplicatedInputSinkHandle; // rax
  char *v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+28h] [rbp-D8h]
  HANDLE TargetHandle[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+48h] [rbp-B8h] BYREF
  char v26; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v27[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  char v29; // [rsp+80h] [rbp-80h]
  char v30; // [rsp+8Ch] [rbp-74h]
  char v31; // [rsp+91h] [rbp-6Fh]
  char v32; // [rsp+9Ch] [rbp-64h]
  char v33; // [rsp+D8h] [rbp-28h]
  char v34; // [rsp+118h] [rbp+18h]
  char v35; // [rsp+158h] [rbp+58h]
  char v36; // [rsp+198h] [rbp+98h]
  char v37; // [rsp+1D8h] [rbp+D8h]
  char v38; // [rsp+220h] [rbp+120h]
  __int128 v39; // [rsp+228h] [rbp+128h] BYREF
  __int128 v40; // [rsp+238h] [rbp+138h]
  __int128 v41; // [rsp+248h] [rbp+148h]
  __int64 v42; // [rsp+258h] [rbp+158h]
  _OWORD v43[4]; // [rsp+260h] [rbp+160h] BYREF
  _DWORD v44[6]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v45; // [rsp+2B8h] [rbp+1B8h]
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v27[2] = a2;
  v22 = 0;
  v44[0] = 0;
  if ( a3[36] )
  {
    v8 = a3 + 28;
  }
  else
  {
    v21 = 0;
    if ( a3[8] >= 2u )
      std::_Throw_bad_variant_access();
    NtQueryCompositionInputSinkLuid(*(_QWORD *)a3, &v21);
    v8 = a3 + 28;
    *(_QWORD *)(a3 + 28) = v21;
    if ( !a3[36] )
      a3[36] = 1;
  }
  v44[2] = *v8;
  v44[3] = v8[1];
  v44[4] = 1;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  for ( i = &si128; i != (__m128i *)&v26; i = (__m128i *)((char *)i + 4) )
  {
    v10 = i->m128i_u32[0];
    switch ( (_DWORD)v10 )
    {
      case 1:
        v11 = a3 + 40;
        goto LABEL_9;
      case 2:
        v11 = a3 + 104;
LABEL_9:
        v12 = v11;
        if ( v11[56] )
          goto LABEL_13;
        goto LABEL_10;
      case 3:
        v11 = a3 + 168;
        goto LABEL_9;
      case 4:
        v11 = a3 + 232;
        goto LABEL_9;
    }
    if ( (_DWORD)v10 != 5 )
      wil::details::in1diag3::FailFast_UnexpectedMsg(
        retaddr,
        (void *)0xB7,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\components\\inputsitemanager\\server\\legacyinputsinkdata.cpp",
        "Invalid input type provided.",
        v21);
    v11 = a3 + 296;
    v12 = a3 + 296;
LABEL_10:
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    memset(v43, 0, sizeof(v43));
    if ( a3[8] > 1u )
      std::_Throw_bad_variant_access();
    NtQueryCompositionInputQueueAndTransform(*(_QWORD *)a3, v10, &v39, v43);
    v13 = v40;
    *(_OWORD *)v12 = v39;
    *((_OWORD *)v12 + 1) = v13;
    *(_QWORD *)&v13 = v42;
    *((_OWORD *)v12 + 2) = v41;
    *((_QWORD *)v12 + 6) = v13;
    if ( !v11[56] )
      v11[56] = 1;
LABEL_13:
    if ( (unsigned int)(*(_DWORD *)v11 - 2) <= 1 )
    {
      v14 = *((_QWORD *)v11 + 1);
      goto LABEL_15;
    }
  }
  LODWORD(v14) = 0;
LABEL_15:
  v45 = (unsigned int)v14;
  v15 = (void *)(((unsigned int)v14 != 0) + 1LL);
  TargetHandle[0] = v15;
  TargetHandle[1] = v44;
  InputSiteManager::GetInputSiteFromIds(a1, a2, TargetHandle);
  v22 = 1;
  if ( !*a2 && a4 )
  {
    v27[0] = v15;
    v27[1] = v44;
    v24 = 0;
    TargetHandle[0] = a1;
    Microsoft::WRL::Details::Make<InputSite,gsl::span<InputSiteId,-1> &,unsigned long &,InputSiteManager *>(
      &v21,
      v27,
      &v24,
      TargetHandle);
    v22 = 5;
    TargetHandle[0] = v21;
    v16 = (char **)a1[8];
    if ( v16 == (char **)a1[9] )
    {
      std::vector<InputSite *>::_Emplace_reallocate<InputSite *>(a1 + 7, v16, TargetHandle);
    }
    else
    {
      *v16 = v21;
      a1[8] += 8LL;
    }
    Microsoft::WRL::ComPtr<InputSite>::operator=(a2, &v21);
    v22 = 1;
    v17 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  v18 = *a2;
  if ( *a2 && !*(_BYTE *)(v18 + 480) )
  {
    if ( a3[8] == 1 )
    {
      InputSite::SetLegacyInputSinkData(*a2, a3);
    }
    else
    {
      DuplicatedInputSinkHandle = (__int64 *)LegacyInputSinkData::GetDuplicatedInputSinkHandle(
                                               (LegacyInputSinkData *)a3,
                                               TargetHandle);
      v28 = *DuplicatedInputSinkHandle;
      *DuplicatedInputSinkHandle = 0;
      v29 = 1;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      InputSite::SetLegacyInputSinkData(v18, &v28);
      std::_Deleted_copy_assign<std::_Variant_destroy_layer_<void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>>,void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>>::~_Deleted_copy_assign<std::_Variant_destroy_layer_<void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>>,void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>>(&v28);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>(TargetHandle);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800188a0  mov     [rsp-8+arg_18], rbx
0x1800188a5  mov     [rsp-8+arg_8], rdx
0x1800188aa  push    rbp
0x1800188ab  push    rsi
0x1800188ac  push    rdi
0x1800188ad  push    r12
0x1800188af  push    r13
0x1800188b1  push    r14
0x1800188b3  push    r15
0x1800188b5  lea     rbp, [rsp-1D0h]
0x1800188bd  sub     rsp, 2D0h
0x1800188c4  mov     rax, cs:__security_cookie
0x1800188cb  xor     rax, rsp
0x1800188ce  mov     [rbp+200h+var_40], rax
0x1800188d5  movzx   r12d, r9b
0x1800188d9  mov     rsi, r8
0x1800188dc  mov     rbx, rdx
0x1800188df  mov     r13, rcx
0x1800188e2  mov     [rsp+300h+var_290], rdx
0x1800188e7  xor     r14d, r14d
0x1800188ea  mov     [rsp+300h+var_2D8], r14d
0x1800188ef  mov     [rbp+200h+var_60], r14d
0x1800188f6  cmp     [r8+24h], r14b
0x1800188fa  jnz     loc_180018B94
0x180018900  mov     [rsp+300h+var_2E0], r14; char *
0x180018905  cmp     byte ptr [r8+8], 2
0x18001890a  jnb     loc_180018B88
0x180018910  lea     rdx, [rsp+300h+var_2E0]
0x180018915  mov     rcx, [r8]
0x180018918  call    cs:__imp_NtQueryCompositionInputSinkLuid
0x18001891e  lea     rax, [rsi+1Ch]
0x180018922  mov     rcx, [rsp+300h+var_2E0]
0x180018927  mov     [rax], rcx
0x18001892a  cmp     [rax+8], r14b
0x18001892e  jnz     short loc_180018934
0x180018930  mov     byte ptr [rax+8], 1
0x180018934  mov     ecx, [rax]
0x180018936  mov     [rbp+200h+var_58], ecx
0x18001893c  mov     ecx, [rax+4]
0x18001893f  mov     [rbp+200h+var_54], ecx
0x180018945  mov     [rbp+200h+var_50], 1
0x18001894f  movdqa  xmm0, cs:__xmm@00000004000000030000000200000001
0x180018957  movdqu  [rsp+300h+var_2B8], xmm0
0x18001895d  lea     r15, [rsp+300h+var_2B8]
0x180018962  lea     rax, [rsp+300h+var_2A8]
0x180018967  cmp     r15, rax
0x18001896a  jz      loc_180018B66
0x180018970  mov     edx, [r15]
0x180018973  cmp     edx, 1
0x180018976  jnz     loc_180018BB0
0x18001897c  lea     rdi, [rsi+28h]
0x180018980  movzx   eax, byte ptr [rdi+38h]
0x180018984  test    al, al
0x180018986  setz    cl
0x180018989  mov     r14, rdi
0x18001898c  test    cl, cl
0x18001898e  jz      loc_180018B71
0x180018994  xorps   xmm0, xmm0
0x180018997  xor     eax, eax
0x180018999  movups  [rbp+200h+var_D8], xmm0
0x1800189a0  movups  [rbp+200h+var_C8], xmm0
0x1800189a7  movups  [rbp+200h+var_B8], xmm0
0x1800189ae  mov     [rbp+200h+var_A8], rax
0x1800189b5  xorps   xmm1, xmm1
0x1800189b8  movups  [rbp+200h+var_A0], xmm1
0x1800189bf  movups  [rbp+200h+var_90], xmm1
0x1800189c6  movups  [rbp+200h+var_80], xmm1
0x1800189cd  movups  [rbp+200h+var_70], xmm1
0x1800189d4  cmp     byte ptr [rsi+8], 1
0x1800189d8  ja      loc_180018B8E
0x1800189de  lea     r9, [rbp+200h+var_A0]
0x1800189e5  lea     r8, [rbp+200h+var_D8]
0x1800189ec  mov     rcx, [rsi]
0x1800189ef  call    cs:__imp_NtQueryCompositionInputQueueAndTransform
0x1800189f5  movups  xmm0, [rbp+200h+var_D8]
0x1800189fc  movups  xmm1, [rbp+200h+var_C8]
0x180018a03  movups  xmmword ptr [r14], xmm0
0x180018a07  movups  xmmword ptr [r14+10h], xmm1
0x180018a0c  movups  xmm0, [rbp+200h+var_B8]
0x180018a13  movsd   xmm1, [rbp+200h+var_A8]
0x180018a1b  movups  xmmword ptr [r14+20h], xmm0
0x180018a20  movsd   qword ptr [r14+30h], xmm1
0x180018a26  cmp     byte ptr [rdi+38h], 0
0x180018a2a  jnz     short loc_180018A30
0x180018a2c  mov     byte ptr [rdi+38h], 1
0x180018a30  mov     eax, [rdi]
0x180018a32  sub     eax, 2
0x180018a35  cmp     eax, 1
0x180018a38  ja      loc_180018B7F
0x180018a3e  mov     rax, [rdi+8]
0x180018a42  xor     r14d, r14d
0x180018a45  mov     eax, eax
0x180018a47  mov     [rbp+200h+var_48], rax
0x180018a4e  mov     rdi, r14
0x180018a51  test    rax, rax
0x180018a54  setnz   dil
0x180018a58  inc     rdi
0x180018a5b  mov     [rsp+300h+TargetHandle], rdi
0x180018a60  lea     rax, [rbp+200h+var_60]
0x180018a67  mov     [rsp+300h+var_2C8], rax
0x180018a6c  lea     r8, [rsp+300h+TargetHandle]
0x180018a71  mov     rdx, rbx
0x180018a74  mov     rcx, r13
0x180018a77  call    ?GetInputSiteFromIds@InputSiteManager@@AEAA?AV?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$span@UInputSiteId@@$0?0@gsl@@@Z; InputSiteManager::GetInputSiteFromIds(gsl::span<InputSiteId,-1>)
0x180018a7c  mov     [rsp+300h+var_2D8], 1
0x180018a84  cmp     qword ptr [rbx], 0
0x180018a88  jnz     loc_180018B28
0x180018a8e  test    r12b, r12b
0x180018a91  jz      loc_180018B28
0x180018a97  mov     [rsp+300h+var_2A0], rdi
0x180018a9c  lea     rax, [rbp+200h+var_60]
0x180018aa3  mov     [rsp+300h+var_298], rax
0x180018aa8  mov     [rsp+300h+var_2C0], r14d
0x180018aad  mov     [rsp+300h+TargetHandle], r13
0x180018ab2  lea     r9, [rsp+300h+TargetHandle]
0x180018ab7  lea     r8, [rsp+300h+var_2C0]
0x180018abc  lea     rdx, [rsp+300h+var_2A0]
0x180018ac1  lea     rcx, [rsp+300h+var_2E0]
0x180018ac6  call    ??$Make@VInputSite@@AEAV?$span@UInputSiteId@@$0?0@gsl@@AEAKPEAVInputSiteManager@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VInputSite@@@12@AEAV?$span@UInputSiteId@@$0?0@gsl@@AEAK$$QEAPEAVInputSiteManager@@@Z; Microsoft::WRL::Details::Make<InputSite,gsl::span<InputSiteId,-1> &,ulong &,InputSiteManager *>(gsl::span<InputSiteId,-1> &,ulong &,InputSiteManager * &&)
0x180018acb  mov     [rsp+300h+var_2D8], 5
0x180018ad3  lea     rcx, [r13+38h]
0x180018ad7  mov     rax, [rsp+300h+var_2E0]
0x180018adc  mov     [rsp+300h+TargetHandle], rax
0x180018ae1  mov     rdx, [rcx+8]
0x180018ae5  cmp     rdx, [rcx+10h]
0x180018ae9  jz      loc_180018C62
0x180018aef  mov     [rdx], rax
0x180018af2  add     qword ptr [rcx+8], 8
0x180018af7  lea     rdx, [rsp+300h+var_2E0]
0x180018afc  mov     rcx, rbx
0x180018aff  call    ??4?$ComPtr@VInputSite@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<InputSite>::operator=(Microsoft::WRL::ComPtr<InputSite> &&)
0x180018b04  mov     [rsp+300h+var_2D8], 1
0x180018b0c  mov     rcx, [rsp+300h+var_2E0]
0x180018b11  test    rcx, rcx
0x180018b14  jz      short loc_180018B28
0x180018b16  mov     [rsp+300h+var_2E0], r14
0x180018b1b  mov     rax, [rcx]
0x180018b1e  mov     rax, [rax+10h]
0x180018b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b27  nop
0x180018b28  mov     rdi, [rbx]
0x180018b2b  test    rdi, rdi
0x180018b2e  jz      short loc_180018B39
0x180018b30  cmp     byte ptr [rdi+1E0h], 0
0x180018b37  jz      short loc_180018B9D
0x180018b39  mov     rax, rbx
0x180018b3c  mov     rcx, [rbp+200h+var_40]
0x180018b43  xor     rcx, rsp; StackCookie
0x180018b46  call    __security_check_cookie
0x180018b4b  mov     rbx, [rsp+300h+arg_18]
0x180018b53  add     rsp, 2D0h
0x180018b5a  pop     r15
0x180018b5c  pop     r14
0x180018b5e  pop     r13
0x180018b60  pop     r12
0x180018b62  pop     rdi
0x180018b63  pop     rsi
0x180018b64  pop     rbp
0x180018b65  retn
0x180018b66  xor     r14d, r14d
0x180018b69  mov     eax, r14d
0x180018b6c  jmp     loc_180018A45
0x180018b71  test    al, al
0x180018b73  jnz     loc_180018A30
0x180018b79  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x180018b7f  add     r15, 4
0x180018b83  jmp     loc_180018962
0x180018b88  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x180018b8e  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x180018b94  lea     rax, [r8+1Ch]
0x180018b98  jmp     loc_180018934
0x180018b9d  cmp     byte ptr [rsi+8], 1
0x180018ba1  jnz     short loc_180018BD9
0x180018ba3  mov     rdx, rsi
0x180018ba6  mov     rcx, rdi
0x180018ba9  call    ?SetLegacyInputSinkData@InputSite@@QEAAX$$QEAVLegacyInputSinkData@@@Z; InputSite::SetLegacyInputSinkData(LegacyInputSinkData &&)
0x180018bae  jmp     short loc_180018B39
0x180018bb0  mov     ecx, edx
0x180018bb2  sub     ecx, 2
0x180018bb5  jz      loc_180018C59
0x180018bbb  sub     ecx, 1
0x180018bbe  jz      loc_180018C4D
0x180018bc4  sub     ecx, 1
0x180018bc7  jnz     loc_180018C71
0x180018bcd  lea     rdi, [rsi+0E8h]
0x180018bd4  jmp     loc_180018980
0x180018bd9  lea     rdx, [rsp+300h+TargetHandle]; lpTargetHandle
0x180018bde  mov     rcx, rsi; this
0x180018be1  call    ?GetDuplicatedInputSinkHandle@LegacyInputSinkData@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?NtCloseCompositionInputSink@@YAJ0@Z@details@wil@@@details@wil@@@wil@@XZ; LegacyInputSinkData::GetDuplicatedInputSinkHandle(void)
0x180018be6  mov     rcx, rax
0x180018be9  mov     rax, [rax]
0x180018bec  mov     [rsp+300h+var_288], rax
0x180018bf1  mov     [rcx], r14
0x180018bf4  mov     [rbp+200h+var_280], 1
0x180018bf8  mov     [rbp+200h+var_274], 0
0x180018bfc  mov     [rbp+200h+var_26F], 0
0x180018c00  mov     [rbp+200h+var_264], 0
0x180018c04  mov     [rbp+200h+var_228], 0
0x180018c08  mov     [rbp+200h+var_1E8], 0
0x180018c0c  mov     [rbp+200h+var_1A8], 0
0x180018c10  mov     [rbp+200h+var_168], 0
0x180018c17  mov     [rbp+200h+var_128], 0
0x180018c1e  mov     [rbp+200h+var_E0], 0
0x180018c25  lea     rdx, [rsp+300h+var_288]
0x180018c2a  mov     rcx, rdi
0x180018c2d  call    ?SetLegacyInputSinkData@InputSite@@QEAAX$$QEAVLegacyInputSinkData@@@Z; InputSite::SetLegacyInputSinkData(LegacyInputSinkData &&)
0x180018c32  nop
0x180018c33  lea     rcx, [rsp+300h+var_288]
0x180018c38  call    ??1?$_Deleted_copy_assign@U?$_Variant_destroy_layer_@PEAXV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?NtCloseCompositionInputSink@@YAJ0@Z@details@wil@@@details@wil@@@wil@@@std@@PEAXV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?NtCloseCompositionInputSink@@YAJ0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::_Deleted_copy_assign<std::_Variant_destroy_layer_<void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>>>,void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>>>::~_Deleted_copy_assign<std::_Variant_destroy_layer_<void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>>>,void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>>>(void)
0x180018c3d  nop
0x180018c3e  lea     rcx, [rsp+300h+TargetHandle]
0x180018c43  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?NtCloseCompositionInputSink@@YAJ0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>>(void)
0x180018c48  jmp     loc_180018B39
0x180018c4d  lea     rdi, [rsi+0A8h]
0x180018c54  jmp     loc_180018980
0x180018c59  lea     rdi, [rsi+68h]
0x180018c5d  jmp     loc_180018980
0x180018c62  lea     r8, [rsp+300h+TargetHandle]
0x180018c67  call    ??$_Emplace_reallocate@PEAVInputSite@@@?$vector@PEAVInputSite@@V?$allocator@PEAVInputSite@@@std@@@std@@AEAAPEAPEAVInputSite@@QEAPEAV2@$$QEAPEAV2@@Z; std::vector<InputSite *>::_Emplace_reallocate<InputSite *>(InputSite * * const,InputSite * &&)
0x180018c6c  jmp     loc_180018AF7
0x180018c71  cmp     ecx, 1
0x180018c74  jnz     short loc_180018C85
0x180018c76  lea     rdi, [rsi+128h]
0x180018c7d  mov     r14, rdi
0x180018c80  jmp     loc_180018994
0x180018c85  mov     rcx, [rbp+208h]; this
0x180018c8c  lea     r9, aInvalidInputTy; "Invalid input type provided."
0x180018c93  lea     r8, aOnecoreuapWind_124; "onecoreuap\\windows\\moderncore\\inputv"...
0x180018c9a  mov     edx, 0B7h; void *
0x180018c9f  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
```
