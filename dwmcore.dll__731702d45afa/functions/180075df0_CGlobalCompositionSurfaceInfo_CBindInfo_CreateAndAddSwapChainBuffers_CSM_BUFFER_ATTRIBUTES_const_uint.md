# CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(CSM_BUFFER_ATTRIBUTES const &,uint)

- ea: `0x180075df0`
- end: `0x180076135`
- name: `?CreateAndAddSwapChainBuffers@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@I@Z`
- size: `837`
- prototype: `__int64 __fastcall(CGlobalCompositionSurfaceInfo::CBindInfo *__hidden this, const struct CSM_BUFFER_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800759f4`

## callees

- `0x180025650`
- `0x180026eac`
- `0x180050270`
- `0x180075df0`
- `0x18007613c`
- `0x1800768d8`
- `0x180076bac`
- `0x180077418`
- `0x180077564`
- `0x1800d32c0`
- `0x18012d74c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075f92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075f92`
- `win32u!NtOpenCompositionSurfaceRealizationInfo` at `0x180075e80`
- `win32u!NtOpenCompositionSurfaceRealizationInfo` at `0x180075e80`

## pseudocode

```c
__int64 __fastcall CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(
        CGlobalCompositionSurfaceInfo::CBindInfo *this,
        const struct CSM_BUFFER_ATTRIBUTES *a2,
        unsigned int a3)
{
  __int64 *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // r9
  int v10; // eax
  __int64 v11; // r9
  int v12; // eax
  unsigned int v13; // edi
  unsigned __int64 v14; // r8
  unsigned int i; // r12d
  __int64 v16; // rdx
  __int64 v17; // r13
  int v18; // eax
  struct ISwapChainRealization *v19; // rbx
  unsigned int j; // ebx
  void *v21; // rcx
  __int64 v23; // rcx
  unsigned __int64 v24; // [rsp+30h] [rbp-48h]
  struct ISwapChainRealization *v25; // [rsp+38h] [rbp-40h] BYREF
  __int128 v26; // [rsp+40h] [rbp-38h] BYREF
  __int64 v27; // [rsp+50h] [rbp-28h]
  __int128 v28; // [rsp+58h] [rbp-20h] BYREF
  bool v29; // [rsp+C0h] [rbp+48h]
  unsigned int v31; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v32; // [rsp+D8h] [rbp+60h]

  v31 = a3;
  v27 = 0;
  v26 = 0;
  if ( a3 )
    std::vector<CSM_REALIZATION_INFO>::_Resize_reallocate<std::_Value_init_tag>(&v26, a3);
  v4 = (__int64 *)((char *)this + 72);
  v5 = 0;
  v28 = 0;
  if ( &v28 == (__int128 *)((char *)this + 72) )
  {
    v7 = *((_QWORD *)&v28 + 1);
    v6 = v28;
  }
  else
  {
    v6 = *v4;
    *v4 = 0;
    v7 = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = 0;
    v5 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = 0;
  }
  v8 = *(_QWORD *)this;
  v9 = v26;
  *((_BYTE *)this + 183) = 0;
  v32 = v7;
  v10 = NtOpenCompositionSurfaceRealizationInfo(*(_QWORD *)(v8 + 32), (char *)this + 24, &v31, v9);
  if ( v10 < 0 )
  {
    v13 = v10 | 0x10000000;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D46A0, 4u, v10 | 0x10000000, 0x64Cu, 0);
    goto LABEL_26;
  }
  if ( v31 <= 1 && *((_DWORD *)this + 8) != 3 )
  {
    v13 = 0;
    v29 = 0;
    LOBYTE(v11) = 0;
LABEL_10:
    v14 = 0;
    v24 = 0;
    for ( i = 0; i < v31; ++i )
    {
      v16 = 5LL * i;
      v17 = v26 + 40LL * i;
      if ( *(_QWORD *)(v17 + 24) )
      {
        while ( 1 )
        {
          if ( v14 >= (v7 - v6) >> 3 )
          {
            LOBYTE(v11) = v29;
            goto LABEL_15;
          }
          v19 = *(struct ISwapChainRealization **)(v6 + 8 * v14);
          *(_QWORD *)(v6 + 8 * v14) = 0;
          v25 = v19;
          v24 = v14 + 1;
          if ( (*(__int64 (__fastcall **)(struct ISwapChainRealization *, __int64, unsigned __int64, __int64))(*(_QWORD *)v19 + 248LL))(
                 v19,
                 v16,
                 v14 + 1,
                 v11) == *(_QWORD *)(v17 + 24) )
            break;
          wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v25);
          v14 = v24;
          v7 = v32;
        }
        if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x8000000) != 0 )
          McTemplateU0x_EventWriteTransfer(v23, CompSurfInfo_ReuseRealization);
        (*(void (__fastcall **)(struct ISwapChainRealization *, __int64))(*(_QWORD *)v19 + 96LL))(v19, v17);
      }
      else
      {
LABEL_15:
        v25 = 0;
        v18 = CGlobalCompositionSurfaceInfo::CBindInfo::CreateNewRealization(
                (struct CDecodeBitmap **)this,
                a2,
                (const struct CSM_REALIZATION_INFO *)v17,
                v11,
                &v25);
        v13 = v18;
        if ( v18 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D46A0, 4u, v18, 0x689u, 0);
          if ( v25 )
            (*(void (__fastcall **)(struct ISwapChainRealization *))(*(_QWORD *)v25 + 16LL))(v25);
          goto LABEL_22;
        }
        v19 = v25;
        *(_QWORD *)(v17 + 8) = 0;
      }
      CGlobalCompositionSurfaceInfo::CBindInfo::AddRealization(this, v19);
      if ( v19 )
        (*(void (__fastcall **)(struct ISwapChainRealization *))(*(_QWORD *)v19 + 16LL))(v19);
      v14 = v24;
      v7 = v32;
      LOBYTE(v11) = v29;
    }
    if ( v31 > 1 )
      CGlobalCompositionSurfaceInfo::CBindInfo::EnsureHDRMetaData(this);
    goto LABEL_22;
  }
  v29 = 1;
  v12 = CGlobalCompositionSurfaceInfo::CBindInfo::EnsureDecodeBitmap(this);
  v13 = v12;
  if ( v12 >= 0 )
  {
    LOBYTE(v11) = 1;
    goto LABEL_10;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D46A0, 4u, v12, 0x653u, 0);
LABEL_22:
  for ( j = 0; j < v31; ++j )
  {
    v21 = *(void **)(v26 + 40LL * j + 8);
    if ( v21 )
      CloseHandle(v21);
  }
LABEL_26:
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(v6, v32);
    std::_Deallocate<16>(v6, (v5 - v6) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  if ( (_QWORD)v26 )
    std::_Deallocate<16>(v26, 8 * ((v27 - (__int64)v26) >> 3));
  return v13;
}

```

## disassembly

```asm
0x180075df0  mov     [rsp-40h+arg_10], r8d
0x180075df5  mov     [rsp-40h+arg_8], rdx
0x180075dfa  push    rbp
0x180075dfb  push    rbx
0x180075dfc  push    rsi
0x180075dfd  push    rdi
0x180075dfe  push    r12
0x180075e00  push    r13
0x180075e02  push    r14
0x180075e04  push    r15
0x180075e06  mov     rbp, rsp
0x180075e09  sub     rsp, 78h
0x180075e0d  xor     r13d, r13d
0x180075e10  mov     edx, r8d
0x180075e13  mov     [rbp+var_28], r13
0x180075e17  xorps   xmm0, xmm0
0x180075e1a  mov     rsi, rcx
0x180075e1d  movdqu  [rbp+var_38], xmm0
0x180075e22  test    r8d, r8d
0x180075e25  jz      short loc_180075E30
0x180075e27  lea     rcx, [rbp+var_38]
0x180075e2b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UCSM_REALIZATION_INFO@@V?$allocator@UCSM_REALIZATION_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<CSM_REALIZATION_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180075e30  lea     rax, [rsi+48h]
0x180075e34  xorps   xmm0, xmm0
0x180075e37  lea     rcx, [rbp+var_20]
0x180075e3b  mov     r14, r13
0x180075e3e  movdqu  [rbp+var_20], xmm0
0x180075e43  cmp     rcx, rax
0x180075e46  jz      loc_180076104
0x180075e4c  mov     r15, [rax]
0x180075e4f  mov     [rax], r13
0x180075e52  mov     rbx, [rax+8]
0x180075e56  mov     [rax+8], r13
0x180075e5a  mov     r14, [rax+10h]
0x180075e5e  mov     [rax+10h], r13
0x180075e62  mov     rcx, [rsi]
0x180075e65  lea     rdx, [rsi+18h]
0x180075e69  mov     r9, qword ptr [rbp+var_38]
0x180075e6d  lea     r8, [rbp+arg_10]
0x180075e71  mov     [rsi+0B7h], r13b
0x180075e78  mov     [rbp+arg_18], rbx
0x180075e7c  mov     rcx, [rcx+20h]
0x180075e80  call    cs:__imp_NtOpenCompositionSurfaceRealizationInfo
0x180075e86  mov     edi, eax
0x180075e88  test    eax, eax
0x180075e8a  js      loc_180076013
0x180075e90  cmp     [rbp+arg_10], 1
0x180075e94  ja      short loc_180075EA0
0x180075e96  cmp     dword ptr [rsi+20h], 3
0x180075e9a  jnz     loc_180076004
0x180075ea0  mov     rcx, rsi; this
0x180075ea3  mov     [rbp+arg_0], 1
0x180075ea7  call    ?EnsureDecodeBitmap@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJXZ; CGlobalCompositionSurfaceInfo::CBindInfo::EnsureDecodeBitmap(void)
0x180075eac  mov     edi, eax
0x180075eae  test    eax, eax
0x180075eb0  js      loc_180076087
0x180075eb6  mov     r9b, [rbp+arg_0]
0x180075eba  mov     r8, r13
0x180075ebd  mov     [rbp+var_48], r13
0x180075ec1  mov     r12d, r13d
0x180075ec4  cmp     r12d, [rbp+arg_10]
0x180075ec8  jnb     loc_180075F67
0x180075ece  mov     rax, qword ptr [rbp+var_38]
0x180075ed2  mov     ecx, r12d
0x180075ed5  lea     rdx, [rcx+rcx*4]
0x180075ed9  lea     r13, [rax+rdx*8]
0x180075edd  cmp     qword ptr [r13+18h], 0
0x180075ee2  jz      short loc_180075EFB
0x180075ee4  mov     rax, rbx
0x180075ee7  sub     rax, r15
0x180075eea  sar     rax, 3
0x180075eee  cmp     r8, rax
0x180075ef1  jb      loc_1800760B2
0x180075ef7  mov     r9b, [rbp+arg_0]; bool
0x180075efb  mov     rdx, [rbp+arg_8]; struct CSM_BUFFER_ATTRIBUTES *
0x180075eff  lea     rax, [rbp+var_40]
0x180075f03  mov     r8, r13; struct CSM_REALIZATION_INFO *
0x180075f06  mov     [rsp+78h+var_58], rax; struct ISwapChainRealization **
0x180075f0b  mov     rcx, rsi; this
0x180075f0e  mov     [rbp+var_40], 0
0x180075f16  call    ?CreateNewRealization@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@AEBUCSM_REALIZATION_INFO@@_NPEAPEAVISwapChainRealization@@@Z; CGlobalCompositionSurfaceInfo::CBindInfo::CreateNewRealization(CSM_BUFFER_ATTRIBUTES const &,CSM_REALIZATION_INFO const &,bool,ISwapChainRealization * *)
0x180075f1b  mov     edi, eax
0x180075f1d  test    eax, eax
0x180075f1f  js      loc_180076042
0x180075f25  mov     rbx, [rbp+var_40]
0x180075f29  mov     qword ptr [r13+8], 0
0x180075f31  mov     rdx, rbx; struct ISwapChainRealization *
0x180075f34  mov     rcx, rsi; this
0x180075f37  call    ?AddRealization@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAXPEAVISwapChainRealization@@@Z; CGlobalCompositionSurfaceInfo::CBindInfo::AddRealization(ISwapChainRealization *)
0x180075f3c  xor     r13d, r13d
0x180075f3f  test    rbx, rbx
0x180075f42  jz      short loc_180075F53
0x180075f44  mov     rax, [rbx]
0x180075f47  mov     rcx, rbx
0x180075f4a  mov     rax, [rax+10h]
0x180075f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f53  mov     r8, [rbp+var_48]
0x180075f57  inc     r12d
0x180075f5a  mov     rbx, [rbp+arg_18]
0x180075f5e  mov     r9b, [rbp+arg_0]
0x180075f62  jmp     loc_180075EC4
0x180075f67  cmp     [rbp+arg_10], 1
0x180075f6b  jbe     short loc_180075F75
0x180075f6d  mov     rcx, rsi; this
0x180075f70  call    ?EnsureHDRMetaData@CBindInfo@CGlobalCompositionSurfaceInfo@@QEAAJXZ; CGlobalCompositionSurfaceInfo::CBindInfo::EnsureHDRMetaData(void)
0x180075f75  mov     ebx, r13d
0x180075f78  cmp     [rbp+arg_10], r13d
0x180075f7c  jbe     short loc_180075F9F
0x180075f7e  mov     eax, ebx
0x180075f80  lea     rcx, [rax+rax*4]
0x180075f84  mov     rax, qword ptr [rbp+var_38]
0x180075f88  mov     rcx, [rax+rcx*8+8]; hObject
0x180075f8d  test    rcx, rcx
0x180075f90  jz      short loc_180075F98
0x180075f92  call    cs:__imp_CloseHandle
0x180075f98  inc     ebx
0x180075f9a  cmp     ebx, [rbp+arg_10]
0x180075f9d  jb      short loc_180075F7E
0x180075f9f  test    r15, r15
0x180075fa2  jz      short loc_180075FC2
0x180075fa4  mov     rdx, [rbp+arg_18]
0x180075fa8  mov     rcx, r15
0x180075fab  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x180075fb0  sub     r14, r15
0x180075fb3  mov     rcx, r15
0x180075fb6  and     r14, 0FFFFFFFFFFFFFFF8h
0x180075fba  mov     rdx, r14
0x180075fbd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180075fc2  mov     rcx, qword ptr [rbp+var_38]
0x180075fc6  test    rcx, rcx
0x180075fc9  jz      short loc_180075FF1
0x180075fcb  mov     rax, [rbp+var_28]
0x180075fcf  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x180075fd9  sub     rax, rcx
0x180075fdc  sar     rax, 3
0x180075fe0  imul    rax, rdx
0x180075fe4  lea     rdx, [rax+rax*4]
0x180075fe8  shl     rdx, 3
0x180075fec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180075ff1  mov     eax, edi
0x180075ff3  add     rsp, 78h
0x180075ff7  pop     r15
0x180075ff9  pop     r14
0x180075ffb  pop     r13
0x180075ffd  pop     r12
0x180075fff  pop     rdi
0x180076000  pop     rsi
0x180076001  pop     rbx
0x180076002  pop     rbp
0x180076003  retn
0x180076004  mov     edi, r13d
0x180076007  mov     [rbp+arg_0], r13b
0x18007600b  mov     r9b, r13b
0x18007600e  jmp     loc_180075EBA
0x180076013  mov     r8d, 4; unsigned int
0x180076019  mov     [rsp+78h+var_50], r13; void *
0x18007601e  bts     edi, 1Ch
0x180076022  mov     dword ptr [rsp+78h+var_58], 64Ch; unsigned int
0x18007602a  mov     r9d, edi; int
0x18007602d  lea     rdx, qword_1802D46A0; int *
0x180076034  lea     ecx, [r8+10h]; unsigned int
0x180076038  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18007603d  jmp     loc_180075F9F
0x180076042  xor     r13d, r13d
0x180076045  lea     rdx, qword_1802D46A0; int *
0x18007604c  mov     [rsp+78h+var_50], r13; void *
0x180076051  mov     r9d, eax; int
0x180076054  mov     dword ptr [rsp+78h+var_58], 689h; unsigned int
0x18007605c  lea     r8d, [r13+4]; unsigned int
0x180076060  lea     ecx, [r13+14h]; unsigned int
0x180076064  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180076069  mov     rcx, [rbp+var_40]
0x18007606d  test    rcx, rcx
0x180076070  jz      loc_180075F75
0x180076076  mov     rax, [rcx]
0x180076079  mov     rax, [rax+10h]
0x18007607d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076082  jmp     loc_180075F75
0x180076087  mov     r8d, 4; unsigned int
0x18007608d  mov     [rsp+78h+var_50], r13; void *
0x180076092  mov     r9d, eax; int
0x180076095  mov     dword ptr [rsp+78h+var_58], 653h; unsigned int
0x18007609d  lea     rdx, qword_1802D46A0; int *
0x1800760a4  lea     ecx, [r8+10h]; unsigned int
0x1800760a8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800760ad  jmp     loc_180075F75
0x1800760b2  mov     rbx, [r15+r8*8]
0x1800760b6  mov     qword ptr [r15+r8*8], 0
0x1800760be  mov     rcx, rbx
0x1800760c1  inc     r8
0x1800760c4  mov     [rbp+var_40], rbx
0x1800760c8  mov     [rbp+var_48], r8
0x1800760cc  mov     rax, [rbx]
0x1800760cf  mov     rax, [rax+0F8h]
0x1800760d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760db  mov     r8, [r13+18h]
0x1800760df  cmp     rax, r8
0x1800760e2  jnz     short loc_180076111
0x1800760e4  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+3, 8
0x1800760eb  jnz     short loc_180076127
0x1800760ed  mov     rax, [rbx]
0x1800760f0  mov     rdx, r13
0x1800760f3  mov     rcx, rbx
0x1800760f6  mov     rax, [rax+60h]
0x1800760fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760ff  jmp     loc_180075F31
0x180076104  mov     rbx, qword ptr [rbp+var_20+8]
0x180076108  mov     r15, qword ptr [rbp+var_20]
0x18007610c  jmp     loc_180075E62
0x180076111  lea     rcx, [rbp+var_40]
0x180076115  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18007611a  mov     r8, [rbp+var_48]
0x18007611e  mov     rbx, [rbp+arg_18]
0x180076122  jmp     loc_180075EE4
0x180076127  lea     rdx, CompSurfInfo_ReuseRealization
0x18007612e  call    McTemplateU0x_EventWriteTransfer
0x180076133  jmp     short loc_1800760ED
```
