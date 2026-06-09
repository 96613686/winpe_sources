# CMJPEGDX11Allocator::D3DDeviceOpen(DXVAVideoDesc &,DXVAConfiguration const &,bool,bool,bool)

- ea: `0x1800434f0`
- end: `0x1800436e8`
- name: `?D3DDeviceOpen@CMJPEGDX11Allocator@@UEAAJAEAUDXVAVideoDesc@@AEBUDXVAConfiguration@@_N22@Z`
- size: `504`
- prototype: `int(CMJPEGDX11Allocator *__hidden this, struct DXVAVideoDesc *, const struct DXVAConfiguration *, bool, bool, bool)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180024220`
- `0x18003e634`
- `0x1800434cc`
- `0x1800434f0`
- `0x180043dd0`
- `0x180050aa0`
- `0x180054780`
- `0x18006ef8f`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180043597`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180043597`

## pseudocode

```c
int __fastcall CMJPEGDX11Allocator::D3DDeviceOpen(
        CMJPEGDX11Allocator *this,
        struct DXVAVideoDesc *a2,
        const struct DXVAConfiguration *a3,
        bool a4,
        bool a5,
        bool a6)
{
  unsigned int v6; // eax
  unsigned int v8; // ecx
  const void *v11; // rax
  int result; // eax
  __int64 v13; // r8
  int v14; // ebx
  __int64 v15; // rax
  GUID v16; // xmm5
  GUID v17; // xmm4
  GUID v18; // xmm3
  __int128 v19; // xmm2
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  struct CDXVABufferTracker *v22; // [rsp+50h] [rbp-B0h] BYREF
  char *v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  D3D11_VIDEO_DECODER_CONFIG v25; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[128]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v27[3]; // [rsp+160h] [rbp+60h] BYREF
  int v28; // [rsp+190h] [rbp+90h]

  v28 = 0;
  v6 = *((_DWORD *)a2 + 8);
  v8 = *((_DWORD *)this + 75);
  v22 = 0;
  if ( v6 <= v8 )
    v6 = v8;
  *((_DWORD *)a2 + 8) = v6;
  memset(v27, 0, sizeof(v27));
  if ( a5
    || (v11 = (const void *)(*(__int64 (__fastcall **)(CMJPEGDX11Allocator *, struct DXVAVideoDesc *, const struct DXVAConfiguration *))(*(_QWORD *)this + 256LL))(
                              this,
                              a2,
                              a3),
        (result = memcmp_0(a2, v11, 0x34u)) != 0) )
  {
    AcquireSRWLockShared((PSRWLOCK)this + 7);
    v23 = (char *)this + 56;
    utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindFirst<utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindFirstFull,_GUID>(
      (char *)this + 16,
      &v24,
      (char *)a2 + 12);
    if ( v24 )
    {
      v15 = utl::unordered_map<_GUID,DXVAConfiguration,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::at(
              (char *)this + 16,
              v13);
      v16 = *(GUID *)(v15 + 16);
      v17 = *(GUID *)(v15 + 32);
      v18 = *(GUID *)(v15 + 48);
      v19 = *(_OWORD *)(v15 + 64);
      v20 = *(_OWORD *)(v15 + 80);
      v21 = *(_OWORD *)(v15 + 96);
      LODWORD(v15) = *(_DWORD *)(v15 + 112);
      *(GUID *)((char *)this + 168) = v16;
      *(_DWORD *)&v25.ConfigMinRenderTargetBuffCount = v15;
      *(GUID *)((char *)this + 184) = v17;
      *(GUID *)((char *)this + 200) = v18;
      *(_OWORD *)((char *)this + 216) = v19;
      *(_OWORD *)((char *)this + 232) = v20;
      *(_OWORD *)((char *)this + 248) = v21;
      *((_DWORD *)this + 66) = v15;
      v25.guidConfigBitstreamEncryption = v16;
      v25.guidConfigMBcontrolEncryption = v17;
      v25.guidConfigResidDiffEncryption = v18;
      *(_OWORD *)&v25.ConfigBitstreamRaw = v19;
      *(_OWORD *)&v25.ConfigResid8Subtraction = v20;
      *(_OWORD *)&v25.ConfigResidDiffAccelerator = v21;
      v14 = CDX11DecodeCore::D3DDeviceOpen(
              (CMJPEGDX11Allocator *)((char *)this + 104),
              a2,
              (const struct DXVAParams_tag *)v26,
              &v25,
              a4,
              a5,
              a6,
              0,
              (struct DXVAVideoDesc *)v27,
              &v22);
      if ( v14 >= 0 )
      {
        v14 = CDXVAFrameManagerGenericDecode::SetNewOutputSamples(
                *((CDXVAFrameManagerGenericDecode **)this + 12),
                v22,
                *((_DWORD *)a2 + 8),
                0,
                *(_DWORD *)a2,
                *((_DWORD *)a2 + 1));
        if ( v14 >= 0 )
        {
          *((_DWORD *)this + 133) = 0;
          *((_BYTE *)this + 8) = 1;
        }
      }
    }
    else
    {
      v14 = -1072875836;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x1800434f0  mov     [rsp-8+arg_10], rbx
0x1800434f5  push    rbp
0x1800434f6  push    rsi
0x1800434f7  push    rdi
0x1800434f8  push    r14
0x1800434fa  push    r15
0x1800434fc  lea     rbp, [rsp-0A0h]
0x180043504  sub     rsp, 1A0h
0x18004350b  mov     rax, cs:__security_cookie
0x180043512  xor     rax, rsp
0x180043515  mov     [rbp+0C0h+var_28], rax
0x18004351c  mov     r14b, [rbp+0C0h+arg_20]
0x180043523  xor     eax, eax
0x180043525  xorps   xmm0, xmm0
0x180043528  mov     [rbp+0C0h+var_30], eax
0x18004352e  mov     eax, [rdx+20h]
0x180043531  mov     rdi, rcx
0x180043534  mov     ecx, [rcx+12Ch]
0x18004353a  mov     r15b, r9b
0x18004353d  cmp     eax, ecx
0x18004353f  mov     [rsp+1C0h+var_170], 0
0x180043548  mov     rsi, rdx
0x18004354b  cmovbe  eax, ecx
0x18004354e  mov     [rdx+20h], eax
0x180043551  movups  [rbp+0C0h+var_60], xmm0
0x180043555  movups  [rbp+0C0h+var_50], xmm0
0x180043559  movups  [rbp+0C0h+var_40], xmm0
0x180043560  test    r14b, r14b
0x180043563  jnz     short loc_180043590
0x180043565  mov     rax, [rdi]
0x180043568  mov     rcx, rdi
0x18004356b  mov     rax, [rax+100h]
0x180043572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043577  mov     r8d, 34h ; '4'; Size
0x18004357d  mov     rdx, rax; Buf2
0x180043580  mov     rcx, rsi; Buf1
0x180043583  call    memcmp_0
0x180043588  test    eax, eax
0x18004358a  jz      loc_1800436C2
0x180043590  lea     rbx, [rdi+38h]
0x180043594  mov     rcx, rbx; SRWLock
0x180043597  call    cs:__imp_AcquireSRWLockShared
0x18004359d  lea     r8, [rsi+0Ch]
0x1800435a1  mov     [rsp+1C0h+var_168], rbx
0x1800435a6  lea     rdx, [rsp+1C0h+var_160]
0x1800435ab  lea     rcx, [rdi+10h]
0x1800435af  call    ??$_FindFirst@U_FindFirstFull@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@U_GUID@@@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEBA?AU_FindFirstFull@01@AEBU_GUID@@@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindFirst<utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindFirstFull,_GUID>(_GUID const &)
0x1800435b4  cmp     [rsp+1C0h+var_160], 0
0x1800435ba  jnz     short loc_1800435C6
0x1800435bc  mov     ebx, 0C00D36C4h
0x1800435c1  jmp     loc_1800436B6
0x1800435c6  mov     rdx, r8
0x1800435c9  lea     rcx, [rdi+10h]
0x1800435cd  call    ?at@?$unordered_map@U_GUID@@UDXVAConfiguration@@U?$hash@U_GUID@@@utl@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@4@@utl@@QEAAAEAUDXVAConfiguration@@AEBU_GUID@@@Z; utl::unordered_map<_GUID,DXVAConfiguration,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::at(_GUID const &)
0x1800435d2  lea     rcx, [rdi+68h]; this
0x1800435d6  mov     rdx, rsi; struct DXVAVideoDesc *
0x1800435d9  lea     r9, [rsp+1C0h+var_150]; struct D3D11_VIDEO_DECODER_CONFIG *
0x1800435de  lea     r8, [rbp+0C0h+var_E0]; struct DXVAParams_tag *
0x1800435e2  movups  xmm5, xmmword ptr [rax+10h]
0x1800435e6  movups  xmm4, xmmword ptr [rax+20h]
0x1800435ea  movups  xmm3, xmmword ptr [rax+30h]
0x1800435ee  movups  xmm2, xmmword ptr [rax+40h]
0x1800435f2  movups  xmm1, xmmword ptr [rax+50h]
0x1800435f6  movups  xmm0, xmmword ptr [rax+60h]
0x1800435fa  mov     eax, [rax+70h]
0x1800435fd  movups  xmmword ptr [rdi+0A8h], xmm5
0x180043604  mov     dword ptr [rbp+0C0h+var_150.ConfigMinRenderTargetBuffCount], eax
0x180043607  movups  xmmword ptr [rdi+0B8h], xmm4
0x18004360e  movups  xmmword ptr [rdi+0C8h], xmm3
0x180043615  movups  xmmword ptr [rdi+0D8h], xmm2
0x18004361c  movups  xmmword ptr [rdi+0E8h], xmm1
0x180043623  movups  xmmword ptr [rdi+0F8h], xmm0
0x18004362a  mov     [rdi+108h], eax
0x180043630  lea     rax, [rsp+1C0h+var_170]
0x180043635  mov     [rsp+1C0h+var_178], rax; struct CDXVABufferTracker **
0x18004363a  lea     rax, [rbp+0C0h+var_60]
0x18004363e  mov     [rsp+1C0h+var_180], rax; struct DXVAVideoDesc *
0x180043643  mov     al, [rbp+0C0h+arg_28]
0x180043649  mov     [rsp+1C0h+var_188], 0; bool
0x18004364e  mov     [rsp+1C0h+var_190], al; bool
0x180043652  mov     [rsp+1C0h+var_198], r14b; bool
0x180043657  mov     [rsp+1C0h+var_1A0], r15b; bool
0x18004365c  movaps  xmmword ptr [rsp+1C0h+var_150.guidConfigBitstreamEncryption.Data1], xmm5
0x180043661  movaps  xmmword ptr [rbp+0C0h+var_150.guidConfigMBcontrolEncryption.Data1], xmm4
0x180043665  movaps  xmmword ptr [rbp+0C0h+var_150.guidConfigResidDiffEncryption.Data1], xmm3
0x180043669  movaps  xmmword ptr [rbp+0C0h+var_150.ConfigBitstreamRaw], xmm2
0x18004366d  movaps  xmmword ptr [rbp+0C0h+var_150.ConfigResid8Subtraction], xmm1
0x180043671  movaps  xmmword ptr [rbp+0C0h+var_150.ConfigResidDiffAccelerator], xmm0
0x180043675  call    ?D3DDeviceOpen@CDX11DecodeCore@@UEAAJAEBUDXVAVideoDesc@@PEBUDXVAParams_tag@@AEBUD3D11_VIDEO_DECODER_CONFIG@@_N333AEAU2@PEAPEAVCDXVABufferTracker@@@Z; CDX11DecodeCore::D3DDeviceOpen(DXVAVideoDesc const &,DXVAParams_tag const *,D3D11_VIDEO_DECODER_CONFIG const &,bool,bool,bool,bool,DXVAVideoDesc &,CDXVABufferTracker * *)
0x18004367a  mov     ebx, eax
0x18004367c  test    eax, eax
0x18004367e  js      short loc_1800436B6
0x180043680  mov     eax, [rsi+4]
0x180043683  xor     r9d, r9d; unsigned __int8
0x180043686  mov     r8d, [rsi+20h]; unsigned int
0x18004368a  mov     rdx, [rsp+1C0h+var_170]; struct CDXVABufferTracker *
0x18004368f  mov     rcx, [rdi+60h]; this
0x180043693  mov     dword ptr [rsp+1C0h+var_198], eax; unsigned int
0x180043697  mov     eax, [rsi]
0x180043699  mov     dword ptr [rsp+1C0h+var_1A0], eax; unsigned int
0x18004369d  call    ?SetNewOutputSamples@CDXVAFrameManagerGenericDecode@@UEAAJPEAVCDXVABufferTracker@@KEII@Z; CDXVAFrameManagerGenericDecode::SetNewOutputSamples(CDXVABufferTracker *,ulong,uchar,uint,uint)
0x1800436a2  mov     ebx, eax
0x1800436a4  test    eax, eax
0x1800436a6  js      short loc_1800436B6
0x1800436a8  mov     dword ptr [rdi+214h], 0
0x1800436b2  mov     byte ptr [rdi+8], 1
0x1800436b6  lea     rcx, [rsp+1C0h+var_168]
0x1800436bb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800436c0  mov     eax, ebx
0x1800436c2  mov     rcx, [rbp+0C0h+var_28]
0x1800436c9  xor     rcx, rsp; StackCookie
0x1800436cc  call    __security_check_cookie
0x1800436d1  mov     rbx, [rsp+1C0h+arg_10]
0x1800436d9  add     rsp, 1A0h
0x1800436e0  pop     r15
0x1800436e2  pop     r14
0x1800436e4  pop     rdi
0x1800436e5  pop     rsi
0x1800436e6  pop     rbp
0x1800436e7  retn
```
