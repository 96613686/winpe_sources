# ShellGesturesProcessor::OnHitTest(HitTestInfo *,InputContext *,ContextualProcessorInitialState *)

- ea: `0x180009a70`
- end: `0x18000a0ce`
- name: `?OnHitTest@ShellGesturesProcessor@@UEAAJPEAUHitTestInfo@@PEAVInputContext@@PEAUContextualProcessorInitialState@@@Z`
- size: `1630`
- prototype: `__int64 __fastcall(ShellGesturesProcessor *__hidden this, struct HitTestInfo *, struct InputContext *, struct ContextualProcessorInitialState *)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009a70`
- `0x18000a194`
- `0x18000a25c`
- `0x18000a2b8`
- `0x18000ae18`
- `0x18000b6c0`
- `0x180012b74`
- `0x18003e0d8`
- `0x180087524`
- `0x180088118`
- `0x18008e194`
- `0x1800a43dc`
- `0x1800a48d0`
- `0x1800ab148`
- `0x1800ab3d8`
- `0x1800e27dc`
- `0x1800f08d8`
- `0x1800f0990`
- `0x18016e81c`
- `0x18016e89c`
- `0x18016e940`
- `0x18016ead4`
- `0x18016fe9c`
- `0x180170054`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180009ee3`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180009f16`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180009ee3`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180009f16`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!GetPointerDeviceRects` at `0x180009df3`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!GetPointerDeviceRects` at `0x180009df3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ShellGesturesProcessor::OnHitTest(
        ShellGesturesProcessor *this,
        struct HitTestInfo *a2,
        struct InputContext *a3,
        struct ContextualProcessorInitialState *a4)
{
  unsigned int v7; // r13d
  int v8; // eax
  int v9; // edi
  char v10; // r15
  __int64 v11; // rcx
  const char *v12; // r9
  std::_Ref_count_base **v13; // rbx
  __int64 v14; // rdi
  std::_Ref_count_base *v15; // rsi
  __int64 v17; // rdx
  _QWORD *v18; // rdi
  _QWORD *v19; // r12
  __int64 v20; // r8
  __int64 v21; // rbx
  char v22; // al
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rbx
  std::_Ref_count_base *v26; // r15
  std::_Ref_count_base *v27; // rax
  std::_Ref_count_base *v28; // rcx
  std::_Ref_count_base **v29; // rax
  std::_Ref_count_base *v30; // rcx
  __int64 v31; // rcx
  unsigned __int64 v32; // rbx
  __int64 v33; // r15
  const char *v34; // r9
  _BYTE *v35; // r8
  UINT v36; // edx
  UINT v37; // ecx
  ShellGesturesClientProxy *v38; // rdi
  __int64 v39; // r8
  __int64 v40; // rcx
  char v41; // al
  ShellGesturesClientProxy **p_pvParam; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 pvParam; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+38h] [rbp-C8h] BYREF
  struct InputContext *v48; // [rsp+40h] [rbp-C0h]
  struct ContextualProcessorInitialState *v49; // [rsp+48h] [rbp-B8h]
  std::_Ref_count_base *v50[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v51; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v52[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h]
  _BYTE v54[80]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v49 = a4;
  v48 = a3;
  *(_DWORD *)a4 = 0;
  v7 = 0;
  LODWORD(v47) = 0;
  v8 = *(_DWORD *)a2 & 0x80;
  if ( (*(_BYTE *)a2 & 8) == 0 || v8 )
  {
    if ( (*(_DWORD *)a2 & 0x1000000) != 0 )
    {
      v7 = 0x1000000;
      LODWORD(v47) = 0x1000000;
      v9 = 0x1000000;
    }
    else
    {
      v9 = 0;
      if ( (*(_BYTE *)a2 & 0x10) != 0 && !v8 )
      {
        v7 = 16;
        LODWORD(v47) = 16;
        v9 = 16;
      }
    }
  }
  else
  {
    v7 = 8;
    LODWORD(v47) = 8;
    v9 = 8;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClickToDoPenEdgy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ClickToDoPenEdgy>::GetImpl'::`2'::impl)
    || v9 != 16 )
  {
    v10 = 1;
    memset_0(v54, 0, 0x44u);
    memset(v52, 0, sizeof(v52));
    v53 = 0;
    if ( v9 == 0x1000000 )
    {
      v13 = (std::_Ref_count_base **)((char *)a4 + 8);
      v14 = 0;
      if ( *v13 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x12D,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\shellgestures\\proce"
                        "ssor\\shellgesturesprocessor.cpp",
          v12);
      ShellGesturesProcessor::TraceClients();
    }
    else
    {
      if ( ((v9 - 8) & 0xFFFFFFF7) != 0 || (*((_BYTE *)a2 + 32) & 4) == 0 )
        return 0;
      v13 = (std::_Ref_count_base **)((char *)a4 + 8);
      if ( *v13 )
      {
        v14 = 0;
      }
      else
      {
        ShellGesturesProcessor::TraceClients();
        if ( v9 == 8 )
        {
          v14 = 0;
          LODWORD(pvParam) = 0;
          if ( !SystemParametersInfoW(0x2030u, 0, &pvParam, 0) || !(_DWORD)pvParam )
            v10 = 0;
          v35 = v54;
          v36 = 68;
          v37 = 146;
        }
        else
        {
          v14 = 0;
          v10 = 0;
          v35 = v52;
          v36 = 40;
          v37 = 148;
        }
        SystemParametersInfoW(v37, v36, v35, 0);
      }
    }
    v15 = *v13;
    if ( *v13 )
    {
      if ( *((_BYTE *)v15 + 16) && !*((_QWORD *)v15 + 31) )
      {
        if ( *((_QWORD *)v15 + 32) )
        {
          v47 = 0;
          v44 = *(_QWORD *)(*((_QWORD *)v48 + 22) + 104LL);
          v26 = *(std::_Ref_count_base **)(v44 - 24);
          v27 = *(std::_Ref_count_base **)(v44 - 16);
          v50[0] = v27;
          while ( v26 != v27 )
          {
            InputSite::GetAttachedObject<IShellGesturesClientProxy,ShellGesturesClientProxy>(*(_QWORD *)v26, &pvParam);
            v25 = pvParam;
            if ( pvParam )
            {
              LOBYTE(v24) = 1;
              if ( (unsigned __int8)ShellGesturesClientProxy::HandlesInput(
                                      pvParam,
                                      *(unsigned int *)a2,
                                      v24,
                                      *((unsigned int *)a2 + 13)) )
              {
                if ( (unsigned __int8)ShouldSelectClient<ShellGesturesClientProxy>(v25)
                  && !(unsigned __int8)lambda_c192c8e12fd8d97ede3f075e8e800885_::operator()(v45, v25, a2) )
                {
                  Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::operator=(&v47, &pvParam);
                  Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease(&pvParam);
                  v14 = v47;
                  break;
                }
              }
            }
            Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease(&pvParam);
            v26 = (std::_Ref_count_base *)((char *)v26 + 8);
            v27 = v50[0];
          }
          if ( v14 != *((_QWORD *)v15 + 32) )
            Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease((char *)v15 + 256);
          Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease(&v47);
        }
        if ( !*((_QWORD *)v15 + 31) )
        {
          v23 = *((_QWORD *)v15 + 33);
          if ( v23 )
          {
            if ( (unsigned __int8)lambda_c192c8e12fd8d97ede3f075e8e800885_::operator()(v11, v23, a2) )
              Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease((char *)v15 + 264);
          }
        }
      }
    }
    else
    {
      v29 = (std::_Ref_count_base **)Microsoft::WRL::Details::Make<ShellGesturesProcessor::Context,>(&pvParam);
      v30 = *v29;
      *v29 = 0;
      v50[0] = *v13;
      *v13 = v30;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v50);
      v31 = pvParam;
      if ( pvParam )
      {
        pvParam = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v15 = *v13;
      if ( v7 == 8 )
        ShellGesturesRecognizer::ConfigureTouch(
          (std::_Ref_count_base *)((char *)v15 + 24),
          (const struct tagTOUCH_GESTURE_SETTINGS *)v54);
      v51 = 0;
      LODWORD(pvParam) = ShellGesturesProcessor::GetAllEdgyLocationsFromRegistrations(
                           this,
                           *(_QWORD *)((char *)a2 + 44),
                           v7,
                           v54,
                           v52);
      if ( (_DWORD)pvParam )
      {
        *(_OWORD *)v50 = 0;
        if ( !(unsigned int)GetPointerDeviceRects(*((unsigned int *)a2 + 1), &v51, v50) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x191,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\shellgestures\\pro"
                          "cessor\\shellgesturesprocessor.cpp",
            v34);
        *((_BYTE *)v15 + 416) = 0;
        std::_Optional_construct_base<ShellGesturesProcessor::EdgyContext>::_Construct<tagRECT &,enum ShellEdgyRecognizer::EdgyLocation &,enum InputType &>(
          (char *)v15 + 272,
          &v51,
          &pvParam,
          &v47);
        v7 = v47;
      }
      if ( v10 )
      {
        v47 = 0;
        pvParam = 0;
        v32 = qword_180243928;
        v33 = qword_180243928 + qword_180243930;
        while ( v32 != v33 )
        {
          v38 = *(ShellGesturesClientProxy **)(*((_QWORD *)Src + ((qword_180243920 - 1) & (v32 >> 1))) + 8 * (v32 & 1));
          if ( ShellGesturesClientProxy::IsDetachedFromTree(v38) )
          {
            LOBYTE(v39) = 1;
            if ( (unsigned __int8)ShellGesturesClientProxy::HandlesInput(
                                    v38,
                                    *(unsigned int *)a2,
                                    v39,
                                    *((unsigned int *)a2 + 13)) )
            {
              if ( (unsigned __int8)ShouldSelectClient<ShellGesturesClientProxy>(v38)
                && !(unsigned __int8)lambda_c192c8e12fd8d97ede3f075e8e800885_::operator()(v40, v38, a2) )
              {
                v41 = IsShellClient<ShellGesturesClientProxy>(v38);
                p_pvParam = (ShellGesturesClientProxy **)&v47;
                if ( v41 )
                  p_pvParam = (ShellGesturesClientProxy **)&pvParam;
                *p_pvParam = v38;
              }
            }
          }
          ++v32;
        }
        v17 = pvParam;
        if ( v47 )
          v17 = v47;
        Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::operator=((char *)v15 + 264, v17);
        v11 = *(_QWORD *)(*((_QWORD *)v48 + 22) + 104LL);
        v18 = *(_QWORD **)(v11 - 24);
        v19 = *(_QWORD **)(v11 - 16);
        while ( v18 != v19 )
        {
          InputSite::GetAttachedObject<IShellGesturesClientProxy,ShellGesturesClientProxy>(*v18, &pvParam);
          v21 = pvParam;
          if ( pvParam )
          {
            LOBYTE(v20) = 1;
            if ( (unsigned __int8)ShellGesturesClientProxy::HandlesInput(
                                    pvParam,
                                    *(unsigned int *)a2,
                                    v20,
                                    *((unsigned int *)a2 + 13)) )
            {
              if ( (unsigned __int8)ShouldSelectClient<ShellGesturesClientProxy>(v21)
                && !(unsigned __int8)lambda_c192c8e12fd8d97ede3f075e8e800885_::operator()(v43, v21, a2) )
              {
                Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::operator=((char *)v15 + 256, &pvParam);
                Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease(&pvParam);
                break;
              }
            }
          }
          Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease(&pvParam);
          ++v18;
        }
        if ( *((_QWORD *)v15 + 33) || (v22 = 0, *((_QWORD *)v15 + 32)) )
          v22 = 1;
        *((_BYTE *)v15 + 16) = v22;
      }
    }
    if ( ((v7 - 8) & 0xFFFFFFF7) != 0 )
    {
      *(_DWORD *)v49 = 2;
    }
    else
    {
      ShellGesturesProcessor::TryFindResumableAnimationTarget(v11, v50, a2, *((_QWORD *)v48 + 22));
      v28 = v50[1];
      if ( v50[1] && *((_DWORD *)v50[1] + 2) )
      {
        std::optional<ShellGesturesProcessor::HandlerContext>::emplace<unsigned int &,tagPOINT &>((std::_Ref_count_base *)((char *)v15 + 424));
        std::weak_ptr<GestureHandler>::operator=((char *)v15 + 440, v50);
        *(_DWORD *)v49 = 2;
        v28 = v50[1];
      }
      else if ( *((_BYTE *)v15 + 416) || *((_BYTE *)v15 + 16) )
      {
        *(_DWORD *)v49 = 1;
      }
      if ( v28 )
        std::_Ref_count_base::_Decwref(v28);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009a70  push    rbp
0x180009a72  push    rbx
0x180009a73  push    rsi
0x180009a74  push    rdi
0x180009a75  push    r12
0x180009a77  push    r13
0x180009a79  push    r14
0x180009a7b  push    r15
0x180009a7d  lea     rbp, [rsp-8]
0x180009a82  sub     rsp, 108h
0x180009a89  mov     rax, cs:__security_cookie
0x180009a90  xor     rax, rsp
0x180009a93  mov     [rbp+40h+var_50], rax
0x180009a97  mov     rbx, r9
0x180009a9a  mov     [rsp+140h+var_F8], rbx
0x180009a9f  mov     [rsp+140h+var_100], r8
0x180009aa4  mov     r14, rdx
0x180009aa7  mov     r12, rcx
0x180009aaa  mov     dword ptr [r9], 0
0x180009ab1  xor     r13d, r13d
0x180009ab4  mov     dword ptr [rsp+140h+var_108], r13d
0x180009ab9  mov     eax, [rdx]
0x180009abb  and     eax, 80h
0x180009ac0  lea     esi, [r13+10h]
0x180009ac4  mov     ecx, 1000000h
0x180009ac9  test    byte ptr [rdx], 8
0x180009acc  jnz     loc_180009E75
0x180009ad2  test    [rdx], ecx
0x180009ad4  jnz     loc_180009E8E
0x180009ada  xor     edi, edi
0x180009adc  test    [rdx], sil
0x180009adf  jnz     loc_180009E9C
0x180009ae5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ClickToDoPenEdgy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ClickToDoPenEdgy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClickToDoPenEdgy> `wil::Feature<__WilFeatureTraits_Feature_ClickToDoPenEdgy>::GetImpl(void)'::`2'::impl
0x180009aec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ClickToDoPenEdgy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClickToDoPenEdgy>::__private_IsEnabled(void)
0x180009af1  test    al, al
0x180009af3  jnz     short loc_180009AF9
0x180009af5  cmp     edi, esi
0x180009af7  jz      short loc_180009B71
0x180009af9  mov     r15b, 1
0x180009afc  mov     esi, 44h ; 'D'
0x180009b01  mov     r8d, esi; Size
0x180009b04  xor     edx, edx; Val
0x180009b06  lea     rcx, [rbp+40h+var_A0]; void *
0x180009b0a  call    memset_0
0x180009b0f  xorps   xmm0, xmm0
0x180009b12  xor     eax, eax
0x180009b14  movups  [rsp+140h+var_D0], xmm0
0x180009b19  movups  [rbp+40h+var_C0], xmm0
0x180009b1d  mov     [rbp+40h+var_B0], rax
0x180009b21  cmp     edi, 1000000h
0x180009b27  jnz     short loc_180009B93
0x180009b29  add     rbx, 8
0x180009b2d  mov     rcx, [rbp+48h]; this
0x180009b31  xor     edi, edi
0x180009b33  cmp     [rbx], rdi
0x180009b36  jnz     loc_180009EB2
0x180009b3c  call    ?TraceClients@ShellGesturesProcessor@@CAXXZ; ShellGesturesProcessor::TraceClients(void)
0x180009b41  mov     rsi, [rbx]
0x180009b44  test    rsi, rsi
0x180009b47  jz      loc_180009D2B
0x180009b4d  cmp     [rsi+10h], dil
0x180009b51  jnz     loc_180009C4B
0x180009b57  lea     eax, [r13-8]
0x180009b5b  test    eax, 0FFFFFFF7h
0x180009b60  jz      loc_180009E2A
0x180009b66  mov     rax, [rsp+140h+var_F8]
0x180009b6b  mov     dword ptr [rax], 2
0x180009b71  xor     eax, eax
0x180009b73  mov     rcx, [rbp+40h+var_50]
0x180009b77  xor     rcx, rsp; StackCookie
0x180009b7a  call    __security_check_cookie
0x180009b7f  add     rsp, 108h
0x180009b86  pop     r15
0x180009b88  pop     r14
0x180009b8a  pop     r13
0x180009b8c  pop     r12
0x180009b8e  pop     rdi
0x180009b8f  pop     rsi
0x180009b90  pop     rbx
0x180009b91  pop     rbp
0x180009b92  retn
0x180009b93  lea     eax, [rdi-8]
0x180009b96  test    eax, 0FFFFFFF7h
0x180009b9b  jnz     short loc_180009B71
0x180009b9d  test    byte ptr [r14+20h], 4
0x180009ba2  jz      short loc_180009B71
0x180009ba4  add     rbx, 8
0x180009ba8  cmp     qword ptr [rbx], 0
0x180009bac  jz      loc_180009EC4
0x180009bb2  xor     edi, edi
0x180009bb4  jmp     short loc_180009B41
0x180009bb6  cmp     rbx, r15
0x180009bb9  jnz     loc_180009F36
0x180009bbf  mov     rdx, [rsp+140h+pvParam]
0x180009bc4  mov     rax, [rsp+140h+var_108]
0x180009bc9  test    rax, rax
0x180009bcc  cmovnz  rdx, rax
0x180009bd0  lea     r15, [rsi+108h]
0x180009bd7  mov     rcx, r15
0x180009bda  call    ??4?$ComPtr@VShellGesturesClientProxy@@@WRL@Microsoft@@QEAAAEAV012@PEAVShellGesturesClientProxy@@@Z; Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::operator=(ShellGesturesClientProxy *)
0x180009bdf  mov     rcx, [rsp+140h+var_100]
0x180009be4  mov     rax, [rcx+0B0h]
0x180009beb  mov     rcx, [rax+68h]
0x180009bef  mov     rdi, [rcx-18h]
0x180009bf3  mov     r12, [rcx-10h]
0x180009bf7  cmp     rdi, r12
0x180009bfa  jz      short loc_180009C28
0x180009bfc  lea     rdx, [rsp+140h+pvParam]
0x180009c01  mov     rcx, [rdi]
0x180009c04  call    ??$GetAttachedObject@UIShellGesturesClientProxy@@VShellGesturesClientProxy@@@InputSite@@QEAA?AV?$ComPtr@VShellGesturesClientProxy@@@WRL@Microsoft@@XZ; InputSite::GetAttachedObject<IShellGesturesClientProxy,ShellGesturesClientProxy>(void)
0x180009c09  nop
0x180009c0a  mov     rbx, [rsp+140h+pvParam]
0x180009c0f  test    rbx, rbx
0x180009c12  jnz     loc_180009FBE
0x180009c18  lea     rcx, [rsp+140h+pvParam]
0x180009c1d  call    ?InternalRelease@?$ComPtr@VShellGesturesClientProxy@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease(void)
0x180009c22  add     rdi, 8
0x180009c26  jmp     short loc_180009BF7
0x180009c28  xor     edi, edi
0x180009c2a  cmp     [r15], rdi
0x180009c2d  jnz     loc_18000A01C
0x180009c33  cmp     [rsi+100h], rdi
0x180009c3a  mov     al, dil
0x180009c3d  jnz     loc_18000A01C
0x180009c43  mov     [rsi+10h], al
0x180009c46  jmp     loc_180009B57
0x180009c4b  cmp     [rsi+0F8h], rdi
0x180009c52  jnz     loc_180009B57
0x180009c58  lea     r12, [rsi+100h]
0x180009c5f  cmp     [r12], rdi
0x180009c63  jnz     loc_18000A023
0x180009c69  cmp     [rsi+0F8h], rdi
0x180009c70  jnz     loc_180009B57
0x180009c76  lea     rbx, [rsi+108h]
0x180009c7d  mov     rdx, [rbx]
0x180009c80  test    rdx, rdx
0x180009c83  jz      loc_180009B57
0x180009c89  mov     r8, r14
0x180009c8c  call    _lambda_c192c8e12fd8d97ede3f075e8e800885___operator__
0x180009c91  test    al, al
0x180009c93  jz      loc_180009B57
0x180009c99  mov     rcx, rbx
0x180009c9c  call    ?InternalRelease@?$ComPtr@VShellGesturesClientProxy@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease(void)
0x180009ca1  jmp     loc_180009B57
0x180009ca6  lea     rdx, [rsp+140h+pvParam]
0x180009cab  mov     rcx, [r15]
0x180009cae  call    ??$GetAttachedObject@UIShellGesturesClientProxy@@VShellGesturesClientProxy@@@InputSite@@QEAA?AV?$ComPtr@VShellGesturesClientProxy@@@WRL@Microsoft@@XZ; InputSite::GetAttachedObject<IShellGesturesClientProxy,ShellGesturesClientProxy>(void)
0x180009cb3  nop
0x180009cb4  mov     rbx, [rsp+140h+pvParam]
0x180009cb9  test    rbx, rbx
0x180009cbc  jnz     loc_18000A04F
0x180009cc2  lea     rcx, [rsp+140h+pvParam]
0x180009cc7  call    ?InternalRelease@?$ComPtr@VShellGesturesClientProxy@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ShellGesturesClientProxy>::InternalRelease(void)
0x180009ccc  add     r15, 8
0x180009cd0  mov     rax, [rsp+140h+var_F0]
0x180009cd5  jmp     loc_18000A045
0x180009cda  cmp     [rcx+8], edi
0x180009cdd  jz      loc_180009E52
0x180009ce3  lea     rbx, [rsi+1A8h]
0x180009cea  lea     r8, [r14+2Ch]
0x180009cee  lea     rdx, [r14+28h]
0x180009cf2  mov     rcx, rbx; this
0x180009cf5  call    ??$emplace@AEAIAEAUtagPOINT@@@?$optional@UHandlerContext@ShellGesturesProcessor@@@std@@QEAAAEAUHandlerContext@ShellGesturesProcessor@@AEAIAEAUtagPOINT@@@Z; std::optional<ShellGesturesProcessor::HandlerContext>::emplace<uint &,tagPOINT &>(uint &,tagPOINT &)
0x180009cfa  lea     rcx, [rbx+10h]
0x180009cfe  lea     rdx, [rsp+140h+var_F0]
0x180009d03  call    ??4?$weak_ptr@VGestureHandler@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::weak_ptr<GestureHandler>::operator=(std::weak_ptr<GestureHandler> &&)
0x180009d08  mov     rax, [rsp+140h+var_F8]
0x180009d0d  mov     dword ptr [rax], 2
0x180009d13  mov     rcx, [rsp+140h+var_F0+8]; this
0x180009d18  test    rcx, rcx
0x180009d1b  jz      loc_180009B71
0x180009d21  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180009d26  jmp     loc_180009B71
0x180009d2b  lea     rcx, [rsp+140h+pvParam]
0x180009d30  call    ??$Make@UContext@ShellGesturesProcessor@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@UContext@ShellGesturesProcessor@@@12@XZ; Microsoft::WRL::Details::Make<ShellGesturesProcessor::Context,>(void)
0x180009d35  mov     rcx, [rax]
0x180009d38  mov     [rax], rdi
0x180009d3b  mov     rax, [rbx]
0x180009d3e  mov     [rsp+140h+var_F0], rax
0x180009d43  mov     [rbx], rcx
0x180009d46  lea     rcx, [rsp+140h+var_F0]
0x180009d4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180009d50  nop
0x180009d51  mov     rcx, [rsp+140h+pvParam]
0x180009d56  test    rcx, rcx
0x180009d59  jz      short loc_180009D6D
0x180009d5b  mov     [rsp+140h+pvParam], rdi
0x180009d60  mov     rax, [rcx]
0x180009d63  mov     rax, [rax+10h]
0x180009d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d6c  nop
0x180009d6d  mov     rsi, [rbx]
0x180009d70  cmp     r13d, 8
0x180009d74  jnz     short loc_180009D83
0x180009d76  lea     rcx, [rsi+18h]; this
0x180009d7a  lea     rdx, [rbp+40h+var_A0]; struct tagTOUCH_GESTURE_SETTINGS *
0x180009d7e  call    ?ConfigureTouch@ShellGesturesRecognizer@@QEAAXPEBUtagTOUCH_GESTURE_SETTINGS@@@Z; ShellGesturesRecognizer::ConfigureTouch(tagTOUCH_GESTURE_SETTINGS const *)
0x180009d83  xorps   xmm0, xmm0
0x180009d86  movups  [rsp+140h+var_E0], xmm0
0x180009d8b  lea     rax, [rsp+140h+var_D0]
0x180009d90  mov     [rsp+140h+var_120], rax
0x180009d95  lea     r9, [rbp+40h+var_A0]
0x180009d99  mov     r8d, r13d
0x180009d9c  mov     rdx, [r14+2Ch]
0x180009da0  mov     rcx, r12
0x180009da3  call    ?GetAllEdgyLocationsFromRegistrations@ShellGesturesProcessor@@AEAA?AW4EdgyLocation@ShellEdgyRecognizer@@UtagPOINT@@W4InputType@@QEAUtagTOUCH_GESTURE_SETTINGS@@QEAUtagPEN_PARAMETERS@@@Z; ShellGesturesProcessor::GetAllEdgyLocationsFromRegistrations(tagPOINT,InputType,tagTOUCH_GESTURE_SETTINGS * const,tagPEN_PARAMETERS * const)
0x180009da8  mov     dword ptr [rsp+140h+pvParam], eax
0x180009dac  test    eax, eax
0x180009dae  jnz     short loc_180009DD9
0x180009db0  test    r15b, r15b
0x180009db3  jz      loc_180009B57
0x180009db9  mov     [rsp+140h+var_108], rdi
0x180009dbe  mov     [rsp+140h+pvParam], rdi
0x180009dc3  mov     rbx, cs:qword_180243928
0x180009dca  mov     r15, cs:qword_180243930
0x180009dd1  add     r15, rbx
0x180009dd4  jmp     loc_180009BB6
0x180009dd9  xorps   xmm0, xmm0
0x180009ddc  movups  xmmword ptr [rsp+140h+var_F0], xmm0
0x180009de1  mov     rbx, [rbp+48h]
0x180009de5  mov     ecx, [r14+4]
0x180009de9  lea     r8, [rsp+140h+var_F0]
0x180009dee  lea     rdx, [rsp+140h+var_E0]
0x180009df3  call    cs:__imp_GetPointerDeviceRects
0x180009df9  test    eax, eax
0x180009dfb  jz      loc_180009F21
0x180009e01  lea     rcx, [rsi+110h]
0x180009e08  mov     [rcx+90h], dil
0x180009e0f  lea     r9, [rsp+140h+var_108]
0x180009e14  lea     r8, [rsp+140h+pvParam]
0x180009e19  lea     rdx, [rsp+140h+var_E0]
0x180009e1e  call    ??$_Construct@AEAUtagRECT@@AEAW4EdgyLocation@ShellEdgyRecognizer@@AEAW4InputType@@@?$_Optional_construct_base@UEdgyContext@ShellGesturesProcessor@@@std@@QEAAAEAUEdgyContext@ShellGesturesProcessor@@AEAUtagRECT@@AEAW4EdgyLocation@ShellEdgyRecognizer@@AEAW4InputType@@@Z; std::_Optional_construct_base<ShellGesturesProcessor::EdgyContext>::_Construct<tagRECT &,ShellEdgyRecognizer::EdgyLocation &,InputType &>(tagRECT &,ShellEdgyRecognizer::EdgyLocation &,InputType &)
0x180009e23  mov     r13d, dword ptr [rsp+140h+var_108]
0x180009e28  jmp     short loc_180009DB0
0x180009e2a  mov     rax, [rsp+140h+var_100]
0x180009e2f  mov     r9, [rax+0B0h]
0x180009e36  mov     r8, r14
0x180009e39  lea     rdx, [rsp+140h+var_F0]
0x180009e3e  call    ?TryFindResumableAnimationTarget@ShellGesturesProcessor@@AEAA?AV?$weak_ptr@VGestureHandler@@@std@@PEAUHitTestInfo@@PEAUHitTestResult@@@Z; ShellGesturesProcessor::TryFindResumableAnimationTarget(HitTestInfo *,HitTestResult *)
0x180009e43  nop
0x180009e44  mov     rcx, [rsp+140h+var_F0+8]
0x180009e49  test    rcx, rcx
0x180009e4c  jnz     loc_180009CDA
0x180009e52  cmp     [rsi+1A0h], dil
0x180009e59  jnz     short loc_180009E65
0x180009e5b  cmp     [rsi+10h], dil
0x180009e5f  jz      loc_180009D18
0x180009e65  mov     rax, [rsp+140h+var_F8]
0x180009e6a  mov     dword ptr [rax], 1
0x180009e70  jmp     loc_180009D18
0x180009e75  test    eax, eax
0x180009e77  jnz     loc_180009AD2
0x180009e7d  lea     r13d, [rax+8]
0x180009e81  mov     dword ptr [rsp+140h+var_108], r13d
0x180009e86  mov     edi, r13d
0x180009e89  jmp     loc_180009AE5
0x180009e8e  mov     r13d, ecx
0x180009e91  mov     dword ptr [rsp+140h+var_108], ecx
0x180009e95  mov     edi, ecx
0x180009e97  jmp     loc_180009AE5
0x180009e9c  test    eax, eax
0x180009e9e  jnz     loc_180009AE5
0x180009ea4  mov     r13d, esi
0x180009ea7  mov     dword ptr [rsp+140h+var_108], esi
0x180009eab  mov     edi, esi
0x180009ead  jmp     loc_180009AE5
0x180009eb2  lea     r8, aOnecoreuapWind_213; "onecoreuap\\windows\\moderncore\\inputv"...
0x180009eb9  mov     edx, 12Dh; void *
0x180009ebe  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009ec4  call    ?TraceClients@ShellGesturesProcessor@@CAXXZ; ShellGesturesProcessor::TraceClients(void)
0x180009ec9  xor     r9d, r9d; fWinIni
0x180009ecc  cmp     edi, 8
0x180009ecf  jnz     short loc_180009F06
0x180009ed1  xor     edi, edi
0x180009ed3  mov     dword ptr [rsp+140h+pvParam], edi
0x180009ed7  lea     r8, [rsp+140h+pvParam]; pvParam
0x180009edc  xor     edx, edx; uiParam
0x180009ede  mov     ecx, 2030h; uiAction
0x180009ee3  call    cs:__imp_SystemParametersInfoW
0x180009ee9  test    eax, eax
0x180009eeb  jz      short loc_180009EF3
0x180009eed  cmp     dword ptr [rsp+140h+pvParam], edi
0x180009ef1  jnz     short loc_180009EF6
0x180009ef3  mov     r15b, dil
0x180009ef6  xor     r9d, r9d
0x180009ef9  lea     r8, [rbp+40h+var_A0]
0x180009efd  mov     edx, esi
0x180009eff  mov     ecx, 92h
0x180009f04  jmp     short loc_180009F16
0x180009f06  xor     edi, edi
0x180009f08  mov     r15b, dil
0x180009f0b  lea     r8, [rsp+140h+var_D0]; pvParam
0x180009f10  lea     edx, [rdi+28h]; uiParam
0x180009f13  lea     ecx, [rdx+6Ch]; uiAction
0x180009f16  call    cs:__imp_SystemParametersInfoW
0x180009f1c  jmp     loc_180009B41
0x180009f21  lea     r8, aOnecoreuapWind_213; "onecoreuap\\windows\\moderncore\\inputv"...
0x180009f28  mov     edx, 191h; void *
0x180009f2d  mov     rcx, rbx; this
0x180009f30  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
  ... truncated ...
```
