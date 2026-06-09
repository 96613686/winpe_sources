# VirtualTouchpadControllerProxy::ConfigureVirtualTouchpad(void)

- ea: `0x1800d31a0`
- end: `0x1800d37bb`
- name: `?ConfigureVirtualTouchpad@VirtualTouchpadControllerProxy@@AEAAXXZ`
- size: `1563`
- prototype: `void __fastcall(VirtualTouchpadControllerProxy *__hidden this)`
- caller_count: `4`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180157b90`
- `0x180157e40`
- `0x180157e60`
- `0x180158090`

## callees

- `0x180052888`
- `0x180061c60`
- `0x18007349c`
- `0x180073e70`
- `0x18007f6d0`
- `0x18008dcac`
- `0x18008e194`
- `0x1800af59c`
- `0x1800affe0`
- `0x1800b1a88`
- `0x1800d31a0`
- `0x1800f08d8`
- `0x1800f0990`
- `0x180107558`
- `0x180157448`
- `0x180157554`
- `0x1801576b8`
- `0x180157970`
- `0x1801579a0`
- `0x1801579d0`
- `0x1801587bc`
- `0x180158e44`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800d3421`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800d3421`
- `win32u!NtMITConfigureVirtualTouchpad` at `0x1800d36c2`
- `win32u!NtMITConfigureVirtualTouchpad` at `0x1800d36c2`

## string_xrefs

- `0x1800d32cb`: `onecoreuap\windows\moderncore\inputv2\components\attachableinputobject\system\virtualtouchpadcontroller\server\virtualtouchpadcontrollerproxy.cpp`
- `0x1800d32f7`: `onecoreuap\windows\moderncore\inputv2\components\attachableinputobject\system\virtualtouchpadcontroller\server\virtualtouchpadcontrollerproxy.cpp`
- `0x1800d3318`: `onecoreuap\windows\moderncore\inputv2\components\attachableinputobject\system\virtualtouchpadcontroller\server\virtualtouchpadcontrollerproxy.cpp`
- `0x1800d36d3`: `onecoreuap\windows\moderncore\inputv2\components\attachableinputobject\system\virtualtouchpadcontroller\server\virtualtouchpadcontrollerproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall VirtualTouchpadControllerProxy::ConfigureVirtualTouchpad(VirtualTouchpadControllerProxy *this)
{
  BamoAnimationTargetClientProxy *v2; // r12
  int *v3; // rdi
  unsigned __int64 v4; // rsi
  int *v5; // r14
  int v6; // r15d
  int v7; // eax
  int v8; // eax
  const char *v9; // r9
  _BYTE *v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  float v13; // xmm6_4
  __int64 v14; // rax
  float v15; // xmm7_4
  int v16; // r8d
  float v17; // xmm8_4
  int v18; // edx
  int v19; // ecx
  float v20; // xmm2_4
  float v21; // xmm1_4
  int v22; // edx
  float v23; // xmm3_4
  double *Data; // rax
  float v25; // xmm2_4
  float v26; // xmm3_4
  float v27; // xmm0_4
  float v28; // xmm1_4
  const struct Windows::UI::Internal::Input::PhysicalClickZone *PrimaryClickZone; // rax
  float v30; // xmm3_4
  float v31; // xmm2_4
  float v32; // xmm0_4
  float v33; // xmm1_4
  const struct Windows::UI::Internal::Input::PhysicalClickZone *SecondaryClickZone; // rax
  float v35; // xmm2_4
  float v36; // xmm1_4
  float v37; // xmm0_4
  float v38; // xmm6_4
  unsigned int *v39; // rsi
  const char *v40; // r9
  __int64 v41; // rcx
  int v42; // r14d
  const struct Windows::UI::Internal::Input::PhysicalClickZone *v43; // r14
  const struct Windows::UI::Internal::Input::PhysicalClickZone *v44; // r15
  const struct Windows::UI::Internal::Input::GestureAnimationData *v45; // rax
  int v46; // [rsp+28h] [rbp-E0h]
  int v47; // [rsp+38h] [rbp-D0h]
  int v48; // [rsp+3Ch] [rbp-CCh]
  char v49[8]; // [rsp+48h] [rbp-C0h] BYREF
  __m128 v50; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v51; // [rsp+68h] [rbp-A0h]
  unsigned __int128 v52; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 v53; // [rsp+88h] [rbp-80h]
  unsigned __int64 v54; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v55; // [rsp+A0h] [rbp-68h]
  int *v56; // [rsp+A8h] [rbp-60h]
  _BYTE v57[24]; // [rsp+B0h] [rbp-58h] BYREF
  char v58; // [rsp+C8h] [rbp-40h]
  _OWORD v59[9]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v60; // [rsp+168h] [rbp+60h]
  __m128 v61; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+210h] [rbp+108h]

  v2 = (VirtualTouchpadControllerProxy *)((char *)this + 8);
  if ( !BamoMagnifierControllerProxy::GetGesturesEnabled((VirtualTouchpadControllerProxy *)((char *)this + 8))
    || !*((_BYTE *)this + 208) )
  {
    return;
  }
  memset_0(v59, 0, 0x98u);
  v3 = (int *)((char *)this + 252);
  *(_OWORD *)((char *)this + 252) = v59[0];
  *(_OWORD *)((char *)this + 268) = v59[1];
  *(_OWORD *)((char *)this + 284) = v59[2];
  *(_OWORD *)((char *)this + 300) = v59[3];
  *(_OWORD *)((char *)this + 316) = v59[4];
  *(_OWORD *)((char *)this + 332) = v59[5];
  *(_OWORD *)((char *)this + 348) = v59[6];
  *(_OWORD *)((char *)this + 364) = v59[7];
  *(_OWORD *)((char *)this + 380) = v59[8];
  *(_QWORD *)((char *)this + 396) = v60;
  v47 = 0;
  v48 = 0;
  LODWORD(v4) = 0;
  LODWORD(v5) = 0;
  v6 = 1;
  if ( !*((_BYTE *)this + 228) || (v7 = 1, !*((_BYTE *)this + 240)) )
    v7 = 0;
  *v3 = v7;
  if ( v7 )
  {
    v58 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 51) + 40LL))(*((_QWORD *)this + 51), v57);
    if ( v8 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\components\\attachableinputobject\\system\\virtualtouchp"
                      "adcontroller\\server\\virtualtouchpadcontrollerproxy.cpp",
        (const char *)(unsigned int)v8,
        v46);
    v10 = v57;
    if ( v58 != 1 )
      v10 = 0;
    if ( !v10 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xD7,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\components\\attachableinputobject\\system\\virtualtouchp"
                      "adcontroller\\server\\virtualtouchpadcontrollerproxy.cpp",
        v9);
    if ( *(_DWORD *)v10 != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\components\\attachableinputobject\\system\\virtualtouchp"
                      "adcontroller\\server\\virtualtouchpadcontrollerproxy.cpp",
        v9);
    v11 = *((_QWORD *)v10 + 1);
    v61.m128_u64[0] = *(_QWORD *)((char *)this + 212);
    v4 = *(_QWORD *)(v11 + 16);
    gsl::details::extent_type<-1>::extent_type<-1>(&v50, *(unsigned int *)(v11 + 12));
    v12 = v50.m128_u64[0];
    if ( v50.m128_u64[0] != -1 && (v4 || !v50.m128_u64[0]) )
    {
      v5 = (int *)(v4 + 200 * v50.m128_u64[0]);
      v50.m128_u64[0] = v4;
      v50.m128_u64[1] = v4 + 200 * v12;
      v51 = v50.m128_u64[1];
      v52 = __PAIR128__(v50.m128_u64[1], v4);
      v53 = v4;
      std::find_if_gsl::details::span_iterator_INPUT_SPACE_REGION___lambda_5a6d5614be38f35cab22f0a533907b2a___(
        &v54,
        &v52,
        &v50,
        &v61);
      if ( v54 == v4 && (int *)v55 == v5 )
      {
        if ( v56 == v5 )
        {
          v6 = 0;
          LODWORD(v4) = 0;
          LODWORD(v5) = 0;
LABEL_27:
          *v3 = v6;
          std::_Variant_base<std::monostate,InputConfigContextMessage,DisplayOcclusionContextMessage,VirtualTouchpadContextMessage,MIT_WIN32K_INPUTDESKTOP_STATE_MESSAGE>::_Destroy(v57);
          goto LABEL_28;
        }
        if ( v54 && v55 && v54 <= (unsigned __int64)v56 && (unsigned __int64)v56 < v55 )
        {
          v47 = *v56;
          v48 = v56[1];
          LODWORD(v4) = v56[2];
          LODWORD(v5) = v56[3];
          goto LABEL_27;
        }
      }
    }
    _o_terminate();
LABEL_32:
    v13 = *((double *)this + 29);
    v14 = std::optional<tagINPUT_TRANSFORM>::value((char *)this + 144);
    v61.m128_f32[0] = (float)v47;
    v61.m128_f32[1] = (float)v48;
    v61.m128_f32[2] = (float)((int)v4 - v47);
    v61.m128_f32[3] = (float)((int)v5 - v48);
    v50 = v61;
    CInputTransform::ScreenRectToRelative(&v61, &v50, v14);
    *((_OWORD *)this + 17) = *((_OWORD *)this + 9);
    *((_OWORD *)this + 18) = *((_OWORD *)this + 10);
    *((_OWORD *)this + 19) = *((_OWORD *)this + 11);
    *((_OWORD *)this + 20) = *((_OWORD *)this + 12);
    v15 = v61.m128_f32[1];
    v16 = (int)v61.m128_f32[1];
    v17 = v61.m128_f32[0];
    v18 = (int)(float)(v61.m128_f32[2] + v61.m128_f32[0]);
    v19 = (int)(float)(v61.m128_f32[3] + v61.m128_f32[1]);
    *((_DWORD *)this + 64) = (int)v61.m128_f32[0];
    *((_DWORD *)this + 65) = v16;
    *((_DWORD *)this + 66) = v18;
    *((_DWORD *)this + 67) = v19;
    v20 = (float)(v61.m128_f32[0] - v17) * v13;
    v21 = (float)(_mm_shuffle_ps(v61, v61, 85).m128_f32[0] - v15) * v13;
    v22 = (int)(float)((float)(_mm_shuffle_ps(v61, v61, 170).m128_f32[0] * v13) + v20);
    v23 = (float)(_mm_shuffle_ps(v61, v61, 255).m128_f32[0] * v13) + v21;
    *((_DWORD *)this + 84) = (int)v20;
    *((_DWORD *)this + 85) = (int)v21;
    *((_DWORD *)this + 86) = v22;
    *((_DWORD *)this + 87) = (int)v23;
    Data = (double *)BamoAnimationTargetClientProxy::GetData(v2);
    v25 = (float)(0.0 - v17) * v13;
    v26 = (float)(0.0 - v15) * v13;
    v27 = (float)((float)*Data * v13) + v25;
    v28 = (float)((float)Data[1] * v13) + v26;
    *((_DWORD *)this + 88) = (int)v25;
    *((_DWORD *)this + 89) = (int)v26;
    *((_DWORD *)this + 90) = (int)v27;
    *((_DWORD *)this + 91) = (int)v28;
    *((_DWORD *)this + 92) = BamoVirtualTouchpadControllerProxy::GetTypingDefensesEnabled(v2);
    PrimaryClickZone = BamoVirtualTouchpadControllerProxy::GetPrimaryClickZone(v2);
    if ( *(_BYTE *)PrimaryClickZone )
    {
      v30 = (float)(*((float *)PrimaryClickZone + 1) - v17) * v13;
      v31 = (float)(*((float *)PrimaryClickZone + 2) - v15) * v13;
      v32 = (float)(v13 * *((float *)PrimaryClickZone + 3)) + v30;
      v33 = (float)(v13 * *((float *)PrimaryClickZone + 4)) + v31;
      *((_DWORD *)this + 93) = (int)v30;
      *((_DWORD *)this + 94) = (int)v31;
      *((_DWORD *)this + 95) = (int)v32;
      *((_DWORD *)this + 96) = (int)v33;
    }
    SecondaryClickZone = BamoVirtualTouchpadControllerProxy::GetSecondaryClickZone(v2);
    if ( *(_BYTE *)SecondaryClickZone )
    {
      v35 = (float)(*((float *)SecondaryClickZone + 1) - v17) * v13;
      v36 = (float)(*((float *)SecondaryClickZone + 2) - v15) * v13;
      v37 = (float)(v13 * *((float *)SecondaryClickZone + 3)) + v35;
      v38 = (float)(v13 * *((float *)SecondaryClickZone + 4)) + v36;
      *((_DWORD *)this + 97) = (int)v35;
      *((_DWORD *)this + 98) = (int)v36;
      *((_DWORD *)this + 99) = (int)v37;
      *((_DWORD *)this + 100) = (int)v38;
    }
    goto LABEL_36;
  }
LABEL_28:
  if ( *v3 )
  {
    if ( !*((_BYTE *)this + 240) )
      std::_Throw_bad_optional_access();
    goto LABEL_32;
  }
LABEL_36:
  v39 = (unsigned int *)((char *)this + 248);
  if ( !(unsigned int)NtMITConfigureVirtualTouchpad((char *)this + 248, (char *)this + 252) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\components\\attachableinputobject\\system\\virtualtouchpad"
                    "controller\\server\\virtualtouchpadcontrollerproxy.cpp",
      v40);
  wil::EnterCriticalSection(v49, &VirtualTouchpadControllerProxy::s_lock);
  v42 = *v39;
  v61.m128_u64[0] = (unsigned __int64)this;
  if ( v42 )
    *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<VirtualTouchpadControllerProxy *,VPTP_ID,std::_Uhash_compare<VirtualTouchpadControllerProxy *,std::hash<VirtualTouchpadControllerProxy *>,std::equal_to<VirtualTouchpadControllerProxy *>>,std::allocator<std::pair<VirtualTouchpadControllerProxy * const,VPTP_ID>>,0>>::_Try_emplace<VirtualTouchpadControllerProxy *,>(
                             v41,
                             &v50,
                             &v61)
              + 24LL) = v42;
  else
    std::_Hash<std::_Umap_traits<VirtualTouchpadControllerProxy *,VPTP_ID,std::_Uhash_compare<VirtualTouchpadControllerProxy *,std::hash<VirtualTouchpadControllerProxy *>,std::equal_to<VirtualTouchpadControllerProxy *>>,std::allocator<std::pair<VirtualTouchpadControllerProxy * const,VPTP_ID>>,0>>::_Erase<VirtualTouchpadControllerProxy *>(
      v41,
      &v61);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v49);
  v43 = BamoVirtualTouchpadControllerProxy::GetSecondaryClickZone(v2);
  v44 = BamoVirtualTouchpadControllerProxy::GetPrimaryClickZone(v2);
  v45 = BamoAnimationTargetClientProxy::GetData(v2);
  if ( *((_BYTE *)this + 228) )
    v61 = *(__m128 *)((char *)this + 212);
  else
    v61 = 0;
  InputTraceLogging::VirtualTouchpad::VirtualTouchpadController(*v39, &v61, (char *)this + 252, v45, v44, v43);
}

```

## disassembly

```asm
0x1800d31a0  mov     rax, rsp
0x1800d31a3  push    rbp
0x1800d31a4  push    rbx
0x1800d31a5  push    rsi
0x1800d31a6  push    rdi
0x1800d31a7  push    r12
0x1800d31a9  push    r13
0x1800d31ab  push    r14
0x1800d31ad  push    r15
0x1800d31af  lea     rbp, [rax-108h]
0x1800d31b6  sub     rsp, 1C8h
0x1800d31bd  movaps  xmmword ptr [rax-58h], xmm6
0x1800d31c1  movaps  xmmword ptr [rax-68h], xmm7
0x1800d31c5  movaps  xmmword ptr [rax-78h], xmm8
0x1800d31ca  mov     rax, cs:__security_cookie
0x1800d31d1  xor     rax, rsp
0x1800d31d4  mov     [rbp+100h+var_80], rax
0x1800d31db  mov     rbx, rcx
0x1800d31de  lea     r12, [rcx+8]
0x1800d31e2  mov     rcx, r12; this
0x1800d31e5  call    ?GetGesturesEnabled@BamoMagnifierControllerProxy@@UEAA_NXZ; BamoMagnifierControllerProxy::GetGesturesEnabled(void)
0x1800d31ea  test    al, al
0x1800d31ec  jz      loc_1800D3785
0x1800d31f2  lea     r13, [rbx+90h]
0x1800d31f9  cmp     byte ptr [r13+40h], 0
0x1800d31fe  jz      loc_1800D3785
0x1800d3204  xor     edx, edx; Val
0x1800d3206  mov     r8d, 98h; Size
0x1800d320c  lea     rcx, [rbp+100h+var_130]; void *
0x1800d3210  call    memset_0
0x1800d3215  lea     rdi, [rbx+0FCh]
0x1800d321c  movaps  xmm0, [rbp+100h+var_130]
0x1800d3220  movups  xmmword ptr [rdi], xmm0
0x1800d3223  movaps  xmm1, [rbp+100h+var_120]
0x1800d3227  movups  xmmword ptr [rdi+10h], xmm1
0x1800d322b  movaps  xmm0, [rbp+100h+var_110]
0x1800d322f  movups  xmmword ptr [rdi+20h], xmm0
0x1800d3233  movaps  xmm1, [rbp+100h+var_100]
0x1800d3237  movups  xmmword ptr [rdi+30h], xmm1
0x1800d323b  movaps  xmm0, [rbp+100h+var_F0]
0x1800d323f  movups  xmmword ptr [rdi+40h], xmm0
0x1800d3243  movaps  xmm1, [rbp+100h+var_E0]
0x1800d3247  movups  xmmword ptr [rdi+50h], xmm1
0x1800d324b  movaps  xmm0, [rbp+100h+var_D0]
0x1800d324f  movups  xmmword ptr [rdi+60h], xmm0
0x1800d3253  movaps  xmm1, [rbp+100h+var_C0]
0x1800d3257  movups  xmmword ptr [rdi+70h], xmm1
0x1800d325b  movaps  xmm0, [rbp+100h+var_B0]
0x1800d325f  movups  xmmword ptr [rdi+80h], xmm0
0x1800d3266  mov     rax, [rbp+100h+var_A0]
0x1800d326a  mov     [rdi+90h], rax
0x1800d3271  xor     ecx, ecx
0x1800d3273  mov     [rsp+200h+var_1D0], ecx
0x1800d3277  mov     [rsp+200h+var_1CC], ecx
0x1800d327b  mov     esi, ecx
0x1800d327d  mov     r14d, ecx
0x1800d3280  lea     r15d, [rcx+1]
0x1800d3284  cmp     [rbx+0E4h], cl
0x1800d328a  jz      short loc_1800D3297
0x1800d328c  cmp     [rbx+0F0h], cl
0x1800d3292  mov     eax, r15d
0x1800d3295  jnz     short loc_1800D3299
0x1800d3297  mov     eax, ecx
0x1800d3299  mov     [rdi], eax
0x1800d329b  test    eax, eax
0x1800d329d  jz      loc_1800D340B
0x1800d32a3  mov     [rbp+100h+var_140], cl
0x1800d32a6  mov     rcx, [rbx+198h]
0x1800d32ad  mov     rax, [rcx]
0x1800d32b0  lea     rdx, [rbp+100h+var_158]
0x1800d32b4  mov     rax, [rax+28h]
0x1800d32b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d32bd  mov     rcx, [rbp+108h]; this
0x1800d32c4  test    eax, eax
0x1800d32c6  jns     short loc_1800D32DD
0x1800d32c8  mov     r9d, eax; char *
0x1800d32cb  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800d32d2  mov     edx, 0D5h; void *
0x1800d32d7  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800d32dd  lea     rcx, [rbp+100h+var_158]
0x1800d32e1  xor     eax, eax
0x1800d32e3  cmp     [rbp+100h+var_140], r15b
0x1800d32e7  cmovnz  rcx, rax
0x1800d32eb  mov     rax, [rbp+108h]
0x1800d32f2  test    rcx, rcx
0x1800d32f5  jnz     short loc_1800D330C
0x1800d32f7  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800d32fe  mov     edx, 0D7h; void *
0x1800d3303  mov     rcx, rax; this
0x1800d3306  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d330c  mov     rax, [rbp+108h]
0x1800d3313  cmp     [rcx], r15d
0x1800d3316  jz      short loc_1800D332D
0x1800d3318  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800d331f  mov     edx, 0D8h; void *
0x1800d3324  mov     rcx, rax; this
0x1800d3327  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d332d  mov     rcx, [rcx+8]
0x1800d3331  mov     eax, [rbx+0D4h]
0x1800d3337  mov     dword ptr [rbp+100h+var_90], eax
0x1800d333a  mov     eax, [rbx+0D8h]
0x1800d3340  mov     dword ptr [rbp+100h+var_90+4], eax
0x1800d3343  mov     rsi, [rcx+10h]
0x1800d3347  mov     edx, [rcx+0Ch]
0x1800d334a  lea     rcx, [rsp+200h+var_1B8+8]
0x1800d334f  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x1800d3354  mov     rax, qword ptr [rsp+200h+var_1B8+8]
0x1800d3359  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d335d  jz      loc_1800D3421
0x1800d3363  test    rsi, rsi
0x1800d3366  jnz     short loc_1800D3371
0x1800d3368  test    rax, rax
0x1800d336b  jnz     loc_1800D3421
0x1800d3371  imul    r14, rax, 0C8h
0x1800d3378  add     r14, rsi
0x1800d337b  mov     qword ptr [rsp+200h+var_1B8+8], rsi
0x1800d3380  mov     [rsp+200h+var_1A8], r14
0x1800d3385  mov     [rsp+200h+var_1A0], r14
0x1800d338a  mov     [rsp+200h+var_190], rsi
0x1800d338f  mov     [rsp+200h+var_188], r14
0x1800d3394  mov     [rbp+100h+var_180], rsi
0x1800d3398  lea     r9, [rbp+100h+var_90]
0x1800d339c  lea     r8, [rsp+200h+var_1B8+8]
0x1800d33a1  lea     rdx, [rsp+200h+var_190]
0x1800d33a6  lea     rcx, [rbp+100h+var_170]
0x1800d33aa  call    std__find_if_gsl__details__span_iterator_INPUT_SPACE_REGION___lambda_5a6d5614be38f35cab22f0a533907b2a___
0x1800d33af  mov     rdx, [rbp+100h+var_170]
0x1800d33b3  cmp     rdx, rsi
0x1800d33b6  jnz     short loc_1800D3421
0x1800d33b8  mov     rcx, [rbp+100h+var_168]
0x1800d33bc  cmp     rcx, r14
0x1800d33bf  jnz     short loc_1800D3421
0x1800d33c1  mov     rax, [rbp+100h+var_160]
0x1800d33c5  cmp     rax, r14
0x1800d33c8  jnz     short loc_1800D33D5
0x1800d33ca  xor     r15d, r15d
0x1800d33cd  mov     esi, r15d
0x1800d33d0  mov     r14d, r15d
0x1800d33d3  jmp     short loc_1800D33FD
0x1800d33d5  test    rdx, rdx
0x1800d33d8  jz      short loc_1800D3421
0x1800d33da  test    rcx, rcx
0x1800d33dd  jz      short loc_1800D3421
0x1800d33df  cmp     rdx, rax
0x1800d33e2  ja      short loc_1800D3421
0x1800d33e4  cmp     rax, rcx
0x1800d33e7  jnb     short loc_1800D3421
0x1800d33e9  mov     ecx, [rax]
0x1800d33eb  mov     [rsp+200h+var_1D0], ecx
0x1800d33ef  mov     ecx, [rax+4]
0x1800d33f2  mov     [rsp+200h+var_1CC], ecx
0x1800d33f6  mov     esi, [rax+8]
0x1800d33f9  mov     r14d, [rax+0Ch]
0x1800d33fd  mov     [rdi], r15d
0x1800d3400  lea     rcx, [rbp+100h+var_158]
0x1800d3404  call    ?_Destroy@?$_Variant_base@Umonostate@std@@UInputConfigContextMessage@@UDisplayOcclusionContextMessage@@UVirtualTouchpadContextMessage@@UMIT_WIN32K_INPUTDESKTOP_STATE_MESSAGE@@@std@@QEAAXXZ; std::_Variant_base<std::monostate,InputConfigContextMessage,DisplayOcclusionContextMessage,VirtualTouchpadContextMessage,MIT_WIN32K_INPUTDESKTOP_STATE_MESSAGE>::_Destroy(void)
0x1800d3409  xor     ecx, ecx
0x1800d340b  cmp     [rdi], ecx
0x1800d340d  jz      loc_1800D36B5
0x1800d3413  cmp     [rbx+0F0h], cl
0x1800d3419  jnz     short loc_1800D3428
0x1800d341b  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x1800d3421  call    cs:__imp__o_terminate
0x1800d3427  nop
0x1800d3428  movsd   xmm6, qword ptr [rbx+0E8h]
0x1800d3430  cvtpd2ps xmm6, xmm6
0x1800d3434  mov     rcx, r13
0x1800d3437  call    ?value@?$optional@UtagINPUT_TRANSFORM@@@std@@QEGAAAEAUtagINPUT_TRANSFORM@@XZ; std::optional<tagINPUT_TRANSFORM>::value(void)
0x1800d343c  mov     ecx, [rsp+200h+var_1D0]
0x1800d3440  movd    xmm0, ecx
0x1800d3444  cvtdq2ps xmm0, xmm0
0x1800d3447  movss   dword ptr [rbp+100h+var_90], xmm0
0x1800d344c  mov     edx, [rsp+200h+var_1CC]
0x1800d3450  movd    xmm1, edx
0x1800d3454  cvtdq2ps xmm1, xmm1
0x1800d3457  movss   dword ptr [rbp+100h+var_90+4], xmm1
0x1800d345c  sub     esi, ecx
0x1800d345e  movd    xmm0, esi
0x1800d3462  cvtdq2ps xmm0, xmm0
0x1800d3465  movss   dword ptr [rbp+100h+var_90+8], xmm0
0x1800d346a  sub     r14d, edx
0x1800d346d  movd    xmm0, r14d
0x1800d3472  cvtdq2ps xmm0, xmm0
0x1800d3475  movss   dword ptr [rbp+100h+var_90+0Ch], xmm0
0x1800d347a  movups  xmm1, [rbp+100h+var_90]
0x1800d347e  movups  [rsp+200h+var_1B8+8], xmm1
0x1800d3483  mov     r8, rax
0x1800d3486  lea     rdx, [rsp+200h+var_1B8+8]
0x1800d348b  lea     rcx, [rbp+100h+var_90]
0x1800d348f  call    ?ScreenRectToRelative@CInputTransform@@SA?AUTransformedRect@@AEBU2@AEBUtagINPUT_TRANSFORM@@@Z; CInputTransform::ScreenRectToRelative(TransformedRect const &,tagINPUT_TRANSFORM const &)
0x1800d3494  movups  xmm0, xmmword ptr [r13+0]
0x1800d3499  movups  xmmword ptr [rbx+110h], xmm0
0x1800d34a0  movups  xmm1, xmmword ptr [r13+10h]
0x1800d34a5  movups  xmmword ptr [rbx+120h], xmm1
0x1800d34ac  movups  xmm0, xmmword ptr [r13+20h]
0x1800d34b1  movups  xmmword ptr [rbx+130h], xmm0
0x1800d34b8  movups  xmm1, xmmword ptr [r13+30h]
0x1800d34bd  movups  xmmword ptr [rbx+140h], xmm1
0x1800d34c4  movss   xmm7, dword ptr [rbp+100h+var_90+4]
0x1800d34c9  cvttss2si r8d, xmm7
0x1800d34ce  movss   xmm0, dword ptr [rbp+100h+var_90+8]
0x1800d34d3  movss   xmm8, dword ptr [rbp+100h+var_90]
0x1800d34d9  addss   xmm0, xmm8
0x1800d34de  cvttss2si edx, xmm0
0x1800d34e2  movss   xmm0, dword ptr [rbp+100h+var_90+0Ch]
0x1800d34e7  addss   xmm0, xmm7
0x1800d34eb  cvttss2si ecx, xmm0
0x1800d34ef  cvttss2si eax, xmm8
0x1800d34f4  mov     [rbx+100h], eax
0x1800d34fa  mov     [rbx+104h], r8d
0x1800d3501  mov     [rbx+108h], edx
0x1800d3507  mov     [rbx+10Ch], ecx
0x1800d350d  movups  xmm3, [rbp+100h+var_90]
0x1800d3511  movaps  xmm2, xmm3
0x1800d3514  subss   xmm2, xmm8
0x1800d3519  mulss   xmm2, xmm6
0x1800d351d  movaps  xmm1, xmm3
0x1800d3520  shufps  xmm1, xmm3, 55h ; 'U'
0x1800d3524  subss   xmm1, xmm7
0x1800d3528  mulss   xmm1, xmm6
0x1800d352c  movaps  xmm0, xmm3
0x1800d352f  shufps  xmm0, xmm3, 0AAh
0x1800d3533  mulss   xmm0, xmm6
0x1800d3537  addss   xmm0, xmm2
0x1800d353b  cvttss2si edx, xmm0
0x1800d353f  shufps  xmm3, xmm3, 0FFh
0x1800d3543  mulss   xmm3, xmm6
0x1800d3547  addss   xmm3, xmm1
0x1800d354b  cvttss2si ecx, xmm3
0x1800d354f  cvttss2si eax, xmm2
0x1800d3553  mov     [rbx+150h], eax
0x1800d3559  cvttss2si eax, xmm1
0x1800d355d  mov     [rbx+154h], eax
0x1800d3563  mov     [rbx+158h], edx
0x1800d3569  mov     [rbx+15Ch], ecx
0x1800d356f  mov     rcx, r12; this
0x1800d3572  call    ?GetData@BamoAnimationTargetClientProxy@@UEAAAEBUGestureAnimationData@Input@Internal@UI@Windows@@XZ; BamoAnimationTargetClientProxy::GetData(void)
0x1800d3577  xorps   xmm3, xmm3
0x1800d357a  xorps   xmm2, xmm2
0x1800d357d  subss   xmm2, xmm8
0x1800d3582  mulss   xmm2, xmm6
0x1800d3586  subss   xmm3, xmm7
0x1800d358a  mulss   xmm3, xmm6
0x1800d358e  movsd   xmm0, qword ptr [rax]
0x1800d3592  cvtpd2ps xmm0, xmm0
0x1800d3596  mulss   xmm0, xmm6
0x1800d359a  addss   xmm0, xmm2
0x1800d359e  cvttss2si edx, xmm0
0x1800d35a2  movsd   xmm1, qword ptr [rax+8]
0x1800d35a7  cvtpd2ps xmm1, xmm1
0x1800d35ab  mulss   xmm1, xmm6
0x1800d35af  addss   xmm1, xmm3
0x1800d35b3  cvttss2si ecx, xmm1
0x1800d35b7  cvttss2si eax, xmm2
0x1800d35bb  mov     [rbx+160h], eax
0x1800d35c1  cvttss2si eax, xmm3
0x1800d35c5  mov     [rbx+164h], eax
0x1800d35cb  mov     [rbx+168h], edx
0x1800d35d1  mov     [rbx+16Ch], ecx
0x1800d35d7  mov     rcx, r12; this
0x1800d35da  call    ?GetTypingDefensesEnabled@BamoVirtualTouchpadControllerProxy@@UEAA_NXZ; BamoVirtualTouchpadControllerProxy::GetTypingDefensesEnabled(void)
0x1800d35df  movzx   eax, al
0x1800d35e2  mov     [rbx+170h], eax
0x1800d35e8  mov     rcx, r12; this
0x1800d35eb  call    ?GetPrimaryClickZone@BamoVirtualTouchpadControllerProxy@@UEAAAEBUPhysicalClickZone@Input@Internal@UI@Windows@@XZ; BamoVirtualTouchpadControllerProxy::GetPrimaryClickZone(void)
0x1800d35f0  cmp     byte ptr [rax], 0
0x1800d35f3  jz      short loc_1800D3650
0x1800d35f5  movss   xmm3, dword ptr [rax+4]
0x1800d35fa  subss   xmm3, xmm8
0x1800d35ff  mulss   xmm3, xmm6
0x1800d3603  movss   xmm2, dword ptr [rax+8]
0x1800d3608  subss   xmm2, xmm7
0x1800d360c  mulss   xmm2, xmm6
0x1800d3610  movaps  xmm0, xmm6
0x1800d3613  mulss   xmm0, dword ptr [rax+0Ch]
0x1800d3618  addss   xmm0, xmm3
0x1800d361c  cvttss2si edx, xmm0
0x1800d3620  movaps  xmm1, xmm6
0x1800d3623  mulss   xmm1, dword ptr [rax+10h]
0x1800d3628  addss   xmm1, xmm2
0x1800d362c  cvttss2si ecx, xmm1
0x1800d3630  cvttss2si eax, xmm3
0x1800d3634  mov     [rbx+174h], eax
0x1800d363a  cvttss2si eax, xmm2
0x1800d363e  mov     [rbx+178h], eax
0x1800d3644  mov     [rbx+17Ch], edx
0x1800d364a  mov     [rbx+180h], ecx
0x1800d3650  mov     rcx, r12; this
0x1800d3653  call    ?GetSecondaryClickZone@BamoVirtualTouchpadControllerProxy@@UEAAAEBUPhysicalClickZone@Input@Internal@UI@Windows@@XZ; BamoVirtualTouchpadControllerProxy::GetSecondaryClickZone(void)
0x1800d3658  cmp     byte ptr [rax], 0
0x1800d365b  jz      short loc_1800D36B5
0x1800d365d  movss   xmm2, dword ptr [rax+4]
0x1800d3662  subss   xmm2, xmm8
0x1800d3667  mulss   xmm2, xmm6
0x1800d366b  movss   xmm1, dword ptr [rax+8]
0x1800d3670  subss   xmm1, xmm7
0x1800d3674  mulss   xmm1, xmm6
0x1800d3678  movaps  xmm0, xmm6
0x1800d367b  mulss   xmm0, dword ptr [rax+0Ch]
0x1800d3680  addss   xmm0, xmm2
  ... truncated ...
```
