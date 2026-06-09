# SREffectRenderPassDx12::CDSRProvider::CacheVariantInfo(IDSRDevice *)

- ea: `0x1800b5c54`
- end: `0x1800b6143`
- name: `?CacheVariantInfo@CDSRProvider@SREffectRenderPassDx12@@IEAAJPEAUIDSRDevice@@@Z`
- size: `1263`
- prototype: `__int64 __fastcall(SREffectRenderPassDx12::CDSRProvider *__hidden this, struct IDSRDevice *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180068718`

## callees

- `0x18000c6b0`
- `0x180014750`
- `0x18001c7a4`
- `0x180067d2c`
- `0x18006989c`
- `0x180075fa0`
- `0x180076f20`
- `0x180091e70`
- `0x1800b50d0`
- `0x1800b5308`
- `0x1800b5c54`
- `0x1800bcb9c`
- `0x1800cb010`

## import_xrefs

- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabase` at `0x1800b5dc1`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabase` at `0x1800b5dc1`

## string_xrefs

- `0x1800b5ccb`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b5d65`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b5dd5`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b5fde`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b5cb7`: `Variant cache already initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SREffectRenderPassDx12::CDSRProvider::CacheVariantInfo(
        SREffectRenderPassDx12::CDSRProvider *this,
        struct IDSRDevice *a2)
{
  __int64 *v4; // rbx
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned int v10; // eax
  CModule *v11; // rcx
  unsigned __int64 v12; // r14
  _QWORD *v13; // rdi
  int DirectXDatabase; // eax
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // esi
  int v18; // eax
  __int128 v19; // xmm1
  __int128 v20; // xmm2
  __int128 v21; // xmm3
  __int128 v22; // xmm4
  __int128 v23; // xmm5
  __int128 v24; // xmm6
  __int128 v25; // xmm7
  __int128 v26; // xmm8
  __int128 v27; // xmm9
  __int128 v28; // xmm10
  __int128 v29; // xmm11
  __int64 v30; // rcx
  __int64 v31; // rdi
  __int64 v32; // rax
  int v33; // eax
  int v34; // [rsp+28h] [rbp-E0h]
  const char *v35; // [rsp+30h] [rbp-D8h]
  __int64 v36; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int64 v37; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v38[2]; // [rsp+60h] [rbp-A8h]
  __int128 v39; // [rsp+70h] [rbp-98h]
  _OWORD v40[11]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v41; // [rsp+138h] [rbp+30h]
  __int64 v42; // [rsp+148h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]

  v4 = (__int64 *)((char *)this + 72);
  if ( *((_QWORD *)this + 10) != *((_QWORD *)this + 9) )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2E2,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Variant cache already initialized",
      v35);
    return 2147549183LL;
  }
  v36 = 0;
  v6 = (**(__int64 (__fastcall ***)(struct IDSRDevice *, GUID *, __int64 *))a2)(
         a2,
         &GUID_6069f18a_2f9c_4e9c_afec_6a419387d914,
         &v36);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (unsigned int)v6;
    v9 = 741;
    goto LABEL_9;
  }
  v10 = (*(__int64 (__fastcall **)(struct IDSRDevice *))(*(_QWORD *)a2 + 24LL))(a2);
  v12 = v10;
  if ( !v10 )
  {
    if ( *(&g_AutoSRConfig + 6) )
      DebugPrint("No DSR variants available");
    CModule::RecordJournalImpl(v11, -2147023728, "No DSR variants available");
    v7 = -2147023728;
    v8 = 2147943568LL;
    v9 = 750;
    goto LABEL_9;
  }
  if ( *(&g_AutoSRConfig + 6) )
    DebugPrint("%d DSR variants available", v10);
  v13 = (_QWORD *)((char *)this + 96);
  *((_QWORD *)this + 12) = 0x8000000000000000uLL;
  v34 = (_DWORD)this + 96;
  DirectXDatabase = QueryDirectXDatabase(16, 0, 0, 0);
  if ( DirectXDatabase < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2F5,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)(unsigned int)DirectXDatabase,
      (int)v13);
  v37 = 0;
  if ( (unsigned int)CompatValueImpl("AutoSR.ModelPkgPrefOverride", &v37, 0) )
    *v13 = v37;
  if ( *v13 == 0x8000000000000000uLL )
    *v13 = 0;
  if ( *(&g_AutoSRConfig + 6) )
    DebugPrint(
      "Package preference data: Version %d.%d.%d, Model ID %d, Revision %d",
      *(_DWORD *)v13 & 0xF,
      (unsigned __int8)(*(_DWORD *)v13 >> 4),
      (unsigned __int8)(*(_DWORD *)v13 >> 12),
      (unsigned __int8)(*(_DWORD *)v13 >> 20),
      *(_DWORD *)v13 >> 28);
  v15 = 0x4EC4EC4EC4EC4EC5LL * ((v4[1] - *v4) >> 4);
  if ( v12 < v15 )
  {
    v16 = *v4 + 208 * v12;
LABEL_26:
    v4[1] = v16;
    goto LABEL_27;
  }
  if ( v12 > v15 )
  {
    if ( v12 <= 0x4EC4EC4EC4EC4EC5LL * ((v4[2] - *v4) >> 4) )
    {
      v16 = std::_Uninitialized_value_construct_n<std::allocator<SREffectRenderPassDx12::SRVariantInfo>>(
              v4[1],
              v12 - v15);
      goto LABEL_26;
    }
    std::vector<SREffectRenderPassDx12::SRVariantInfo>::_Resize_reallocate<std::_Value_init_tag>(v4, v12);
  }
LABEL_27:
  v17 = 0;
  if ( !(_DWORD)v12 )
  {
LABEL_45:
    v7 = 0;
    goto LABEL_46;
  }
  while ( 1 )
  {
    memset_0(v40, 0, 0xC8u);
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, _OWORD *))(*(_QWORD *)v36 + 40LL))(v36, v17, v40);
    v7 = v18;
    if ( v18 < 0 )
      break;
    v19 = v40[1];
    v20 = v40[2];
    v21 = v40[3];
    v22 = v40[4];
    v23 = v40[5];
    v24 = v40[6];
    v25 = v40[7];
    v26 = v40[8];
    v27 = v40[9];
    v28 = v40[10];
    v29 = v41;
    v30 = v42;
    v31 = 208LL * v17;
    v32 = *v4;
    *(_OWORD *)(v31 + v32) = v40[0];
    *(_OWORD *)(v31 + v32 + 16) = v19;
    *(_OWORD *)(v31 + v32 + 32) = v20;
    *(_OWORD *)(v31 + v32 + 48) = v21;
    *(_OWORD *)(v31 + v32 + 64) = v22;
    *(_OWORD *)(v31 + v32 + 80) = v23;
    *(_OWORD *)(v31 + v32 + 96) = v24;
    *(_OWORD *)(v31 + v32 + 112) = v25;
    *(_OWORD *)(v31 + v32 + 128) = v26;
    *(_OWORD *)(v31 + v32 + 144) = v27;
    *(_OWORD *)(v31 + v32 + 160) = v28;
    *(_OWORD *)(v31 + v32 + 176) = v29;
    *(_QWORD *)(v31 + v32 + 192) = v30;
    *(_OWORD *)v38 = 0;
    v39 = 0;
    v34 = 0;
    v33 = (*(__int64 (__fastcall **)(struct IDSRDevice *, _QWORD, __int64, _QWORD))(*(_QWORD *)a2 + 40LL))(
            a2,
            v17,
            v42,
            (unsigned int)v41);
    if ( v33 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x310,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
        (const char *)(unsigned int)v33,
        0);
    if ( HIDWORD(v38[0]) && HIDWORD(v38[0]) < HIDWORD(v42) && HIDWORD(v38[1]) && DWORD1(v39) )
    {
      *(_DWORD *)(v31 + *v4 + 200) = HIDWORD(v38[1]);
      *(_DWORD *)(v31 + *v4 + 204) = DWORD1(v39);
      if ( (unsigned int)qword_18010BFE8 >= *(_DWORD *)(v31 + *v4 + 200) )
        LODWORD(qword_18010BFE8) = *(_DWORD *)(v31 + *v4 + 200);
      if ( HIDWORD(qword_18010BFE8) <= *(_DWORD *)(v31 + *v4 + 204) )
        HIDWORD(qword_18010BFE8) = *(_DWORD *)(v31 + *v4 + 204);
    }
    else
    {
      if ( *(&g_AutoSRConfig + 6) )
        DebugPrint(
          "Invalid source size settings { %d/%d/%d } for variant %d, using default values",
          HIDWORD(v38[1]),
          HIDWORD(v38[0]),
          DWORD1(v39),
          v17);
      *(_QWORD *)(v31 + *v4 + 200) = qword_18010BFE8;
    }
    if ( *(&g_AutoSRConfig + 6) )
      DebugPrint(
        "Enumerated variant %d: ID %d, Revision %d, OptimalTargetSize (%d, %d), SrcH range [%d, %d]",
        v17,
        SHIBYTE(v40[0]),
        DWORD1(v41),
        v42,
        HIDWORD(v42),
        *(_DWORD *)(v31 + *v4 + 200),
        *(_DWORD *)(v31 + *v4 + 204));
    if ( ++v17 >= (unsigned int)v12 )
      goto LABEL_45;
  }
  v8 = (unsigned int)v18;
  v9 = 777;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
    (const char *)v8,
    v34);
LABEL_46:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  return v7;
}

```

## disassembly

```asm
0x1800b5c54  mov     rax, rsp
0x1800b5c57  mov     [rax+18h], rbx
0x1800b5c5b  push    rbp
0x1800b5c5c  push    rsi
0x1800b5c5d  push    rdi
0x1800b5c5e  push    r14
0x1800b5c60  push    r15
0x1800b5c62  lea     rbp, [rax-0E8h]
0x1800b5c69  sub     rsp, 1C0h
0x1800b5c70  movaps  xmmword ptr [rax-38h], xmm6
0x1800b5c74  movaps  xmmword ptr [rax-48h], xmm7
0x1800b5c78  movaps  xmmword ptr [rax-58h], xmm8
0x1800b5c7d  movaps  xmmword ptr [rax-68h], xmm9
0x1800b5c82  movaps  xmmword ptr [rax-78h], xmm10
0x1800b5c87  movaps  xmmword ptr [rax-88h], xmm11
0x1800b5c8f  mov     rax, cs:__security_cookie
0x1800b5c96  xor     rax, rsp
0x1800b5c99  mov     [rbp+0E0h+var_90], rax
0x1800b5c9d  mov     r15, rdx
0x1800b5ca0  mov     rsi, rcx
0x1800b5ca3  lea     rbx, [rcx+48h]
0x1800b5ca7  mov     rax, [rbx+8]
0x1800b5cab  cmp     rax, [rbx]
0x1800b5cae  jz      short loc_1800B5CE3
0x1800b5cb0  mov     rcx, [rbp+0E8h]; this
0x1800b5cb7  lea     rax, aVariantCacheAl; "Variant cache already initialized"
0x1800b5cbe  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x1800b5cc3  mov     ebx, 8000FFFFh
0x1800b5cc8  mov     r9d, ebx; char *
0x1800b5ccb  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b5cd2  mov     edx, 2E2h; void *
0x1800b5cd7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800b5cdc  mov     eax, ebx
0x1800b5cde  jmp     loc_1800B60F4
0x1800b5ce3  mov     [rsp+1E0h+var_198], 0
0x1800b5cec  mov     rax, [rdx]
0x1800b5cef  lea     r8, [rsp+1E0h+var_198]
0x1800b5cf4  lea     rdx, _GUID_6069f18a_2f9c_4e9c_afec_6a419387d914
0x1800b5cfb  mov     rcx, r15
0x1800b5cfe  mov     rax, [rax]
0x1800b5d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5d06  mov     edi, eax
0x1800b5d08  test    eax, eax
0x1800b5d0a  jns     short loc_1800B5D16
0x1800b5d0c  mov     r9d, eax
0x1800b5d0f  mov     edx, 2E5h
0x1800b5d14  jmp     short loc_1800B5D5E
0x1800b5d16  mov     rax, [r15]
0x1800b5d19  mov     rcx, r15
0x1800b5d1c  mov     rax, [rax+18h]
0x1800b5d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5d25  mov     r14d, eax
0x1800b5d28  test    eax, eax
0x1800b5d2a  jnz     short loc_1800B5D76
0x1800b5d2c  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, al; AutoSRConfig g_AutoSRConfig
0x1800b5d32  jz      short loc_1800B5D40
0x1800b5d34  lea     rcx, aNoDsrVariantsA; "No DSR variants available"
0x1800b5d3b  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800b5d40  lea     r8, aNoDsrVariantsA; "No DSR variants available"
0x1800b5d47  mov     edx, 80070490h; unsigned int
0x1800b5d4c  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800b5d51  mov     edi, 80070490h
0x1800b5d56  mov     r9d, edi; char *
0x1800b5d59  mov     edx, 2EEh; void *
0x1800b5d5e  mov     rcx, [rbp+0E8h]; this
0x1800b5d65  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b5d6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5d71  jmp     loc_1800B60E8
0x1800b5d76  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x1800b5d7d  jz      short loc_1800B5D8E
0x1800b5d7f  mov     edx, r14d
0x1800b5d82  lea     rcx, aDDsrVariantsAv; "%d DSR variants available"
0x1800b5d89  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800b5d8e  lea     rdi, [rsi+60h]
0x1800b5d92  mov     rsi, 8000000000000000h
0x1800b5d9c  mov     [rdi], rsi
0x1800b5d9f  mov     dword ptr [rsp+1E0h+var_1A0], 8
0x1800b5da7  lea     rax, [rsp+1E0h+var_1A0]
0x1800b5dac  mov     [rsp+1E0h+var_1B8], rax
0x1800b5db1  mov     qword ptr [rsp+1E0h+var_1C0], rdi; int
0x1800b5db6  xor     r9d, r9d
0x1800b5db9  xor     r8d, r8d
0x1800b5dbc  xor     edx, edx
0x1800b5dbe  lea     ecx, [rdx+10h]
0x1800b5dc1  call    cs:__imp_QueryDirectXDatabase
0x1800b5dc7  mov     rcx, [rbp+0E8h]; this
0x1800b5dce  test    eax, eax
0x1800b5dd0  jns     short loc_1800B5DE6
0x1800b5dd2  mov     r9d, eax; char *
0x1800b5dd5  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b5ddc  mov     edx, 2F5h; void *
0x1800b5de1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b5de6  mov     [rsp+1E0h+var_190], 0
0x1800b5def  xor     r8d, r8d; bool
0x1800b5df2  lea     rdx, [rsp+1E0h+var_190]; unsigned __int64 *
0x1800b5df7  lea     rcx, aAutosrModelpkg; "AutoSR.ModelPkgPrefOverride"
0x1800b5dfe  call    ?CompatValueImpl@@YAHPEBDPEA_K_N@Z; CompatValueImpl(char const *,unsigned __int64 *,bool)
0x1800b5e03  test    eax, eax
0x1800b5e05  jz      short loc_1800B5E0F
0x1800b5e07  mov     rax, [rsp+1E0h+var_190]
0x1800b5e0c  mov     [rdi], rax
0x1800b5e0f  cmp     [rdi], rsi
0x1800b5e12  jnz     short loc_1800B5E1B
0x1800b5e14  mov     qword ptr [rdi], 0
0x1800b5e1b  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x1800b5e22  jz      short loc_1800B5E5F
0x1800b5e24  mov     edx, [rdi]
0x1800b5e26  mov     r10d, edx
0x1800b5e29  shr     r10d, 1Ch
0x1800b5e2d  mov     eax, edx
0x1800b5e2f  shr     eax, 14h
0x1800b5e32  movzx   ecx, al
0x1800b5e35  mov     eax, edx
0x1800b5e37  shr     eax, 0Ch
0x1800b5e3a  movzx   r9d, al
0x1800b5e3e  mov     eax, edx
0x1800b5e40  shr     eax, 4
0x1800b5e43  movzx   r8d, al
0x1800b5e47  and     edx, 0Fh
0x1800b5e4a  mov     dword ptr [rsp+1E0h+var_1B8], r10d
0x1800b5e4f  mov     [rsp+1E0h+var_1C0], ecx
0x1800b5e53  lea     rcx, aPackagePrefere; "Package preference data: Version %d.%d."...
0x1800b5e5a  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800b5e5f  mov     rcx, [rbx+8]
0x1800b5e63  sub     rcx, [rbx]
0x1800b5e66  sar     rcx, 4
0x1800b5e6a  mov     r8, 4EC4EC4EC4EC4EC5h
0x1800b5e74  imul    rcx, r8
0x1800b5e78  mov     rdx, r14
0x1800b5e7b  cmp     r14, rcx
0x1800b5e7e  jnb     short loc_1800B5E8C
0x1800b5e80  imul    rax, rdx, 0D0h
0x1800b5e87  add     rax, [rbx]
0x1800b5e8a  jmp     short loc_1800B5EB8
0x1800b5e8c  jbe     short loc_1800B5EBC
0x1800b5e8e  mov     rax, [rbx+10h]
0x1800b5e92  sub     rax, [rbx]
0x1800b5e95  sar     rax, 4
0x1800b5e99  imul    rax, r8
0x1800b5e9d  cmp     rdx, rax
0x1800b5ea0  jbe     short loc_1800B5EAC
0x1800b5ea2  mov     rcx, rbx
0x1800b5ea5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@USRVariantInfo@SREffectRenderPassDx12@@V?$allocator@USRVariantInfo@SREffectRenderPassDx12@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<SREffectRenderPassDx12::SRVariantInfo>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800b5eaa  jmp     short loc_1800B5EBC
0x1800b5eac  sub     rdx, rcx
0x1800b5eaf  mov     rcx, [rbx+8]
0x1800b5eb3  call    ??$_Uninitialized_value_construct_n@V?$allocator@USRVariantInfo@SREffectRenderPassDx12@@@std@@@std@@YAPEAUSRVariantInfo@SREffectRenderPassDx12@@PEAU12@_KAEAV?$allocator@USRVariantInfo@SREffectRenderPassDx12@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<SREffectRenderPassDx12::SRVariantInfo>>(SREffectRenderPassDx12::SRVariantInfo *,unsigned __int64,std::allocator<SREffectRenderPassDx12::SRVariantInfo> &)
0x1800b5eb8  mov     [rbx+8], rax
0x1800b5ebc  xor     esi, esi
0x1800b5ebe  test    r14d, r14d
0x1800b5ec1  jz      loc_1800B60E6
0x1800b5ec7  xor     edx, edx; Val
0x1800b5ec9  mov     r8d, 0C8h; Size
0x1800b5ecf  lea     rcx, [rbp+0E0h+var_160]; void *
0x1800b5ed3  call    memset_0
0x1800b5ed8  mov     rcx, [rsp+1E0h+var_198]
0x1800b5edd  mov     rax, [rcx]
0x1800b5ee0  lea     r8, [rbp+0E0h+var_160]
0x1800b5ee4  mov     edx, esi
0x1800b5ee6  mov     rax, [rax+28h]
0x1800b5eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5eef  mov     edi, eax
0x1800b5ef1  test    eax, eax
0x1800b5ef3  js      loc_1800B6135
0x1800b5ef9  movups  xmm0, [rbp+0E0h+var_160]
0x1800b5efd  movups  xmm1, [rbp+0E0h+var_150]
0x1800b5f01  movups  xmm2, [rbp+0E0h+var_140]
0x1800b5f05  movups  xmm3, [rbp+0E0h+var_130]
0x1800b5f09  movups  xmm4, [rbp+0E0h+var_120]
0x1800b5f0d  movups  xmm5, [rbp+0E0h+var_110]
0x1800b5f11  movups  xmm6, [rbp+0E0h+var_100]
0x1800b5f15  movups  xmm7, [rbp+0E0h+var_F0]
0x1800b5f19  movups  xmm8, [rbp+0E0h+var_E0]
0x1800b5f1e  movups  xmm9, [rbp+0E0h+var_D0]
0x1800b5f23  movups  xmm10, [rbp+0E0h+var_C0]
0x1800b5f28  movups  xmm11, [rbp+0E0h+var_B0]
0x1800b5f2d  mov     rcx, [rbp+0E0h+var_A0]
0x1800b5f31  mov     eax, esi
0x1800b5f33  imul    rdi, rax, 0D0h
0x1800b5f3a  mov     rax, [rbx]
0x1800b5f3d  movups  xmmword ptr [rdi+rax], xmm0
0x1800b5f41  movups  xmmword ptr [rdi+rax+10h], xmm1
0x1800b5f46  movups  xmmword ptr [rdi+rax+20h], xmm2
0x1800b5f4b  movups  xmmword ptr [rdi+rax+30h], xmm3
0x1800b5f50  movups  xmmword ptr [rdi+rax+40h], xmm4
0x1800b5f55  movups  xmmword ptr [rdi+rax+50h], xmm5
0x1800b5f5a  movups  xmmword ptr [rdi+rax+60h], xmm6
0x1800b5f5f  movups  xmmword ptr [rdi+rax+70h], xmm7
0x1800b5f64  movups  xmmword ptr [rdi+rax+80h], xmm8
0x1800b5f6d  movups  xmmword ptr [rdi+rax+90h], xmm9
0x1800b5f76  movups  xmmword ptr [rdi+rax+0A0h], xmm10
0x1800b5f7f  movups  xmmword ptr [rdi+rax+0B0h], xmm11
0x1800b5f88  mov     [rdi+rax+0C0h], rcx
0x1800b5f90  xorps   xmm0, xmm0
0x1800b5f93  movups  xmmword ptr [rsp+1E0h+var_190+8], xmm0
0x1800b5f98  movups  xmmword ptr [rsp+1E0h+var_180+8], xmm0
0x1800b5f9d  mov     rax, [r15]
0x1800b5fa0  lea     rcx, [rsp+1E0h+var_190+8]
0x1800b5fa5  mov     qword ptr [rsp+1E0h+var_1B0], rcx
0x1800b5faa  mov     dword ptr [rsp+1E0h+var_1B8], 0
0x1800b5fb2  mov     [rsp+1E0h+var_1C0], 0; int
0x1800b5fba  mov     r9d, dword ptr [rbp+0E0h+var_B0]
0x1800b5fbe  mov     r8, [rbp+0E0h+var_A0]
0x1800b5fc2  mov     edx, esi
0x1800b5fc4  mov     rcx, r15
0x1800b5fc7  mov     rax, [rax+28h]
0x1800b5fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5fd0  mov     rcx, [rbp+0E8h]; this
0x1800b5fd7  test    eax, eax
0x1800b5fd9  jns     short loc_1800B5FEF
0x1800b5fdb  mov     r9d, eax; char *
0x1800b5fde  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b5fe5  mov     edx, 310h; void *
0x1800b5fea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b5fef  mov     r9d, dword ptr [rsp+1E0h+var_180+0Ch]
0x1800b5ff4  mov     edx, dword ptr [rsp+1E0h+var_180+4]
0x1800b5ff8  mov     r8d, dword ptr [rsp+1E0h+var_190+0Ch]
0x1800b5ffd  test    r8d, r8d
0x1800b6000  jz      short loc_1800B605B
0x1800b6002  cmp     r8d, dword ptr [rbp+0E0h+var_A0+4]
0x1800b6006  jnb     short loc_1800B605B
0x1800b6008  test    edx, edx
0x1800b600a  jz      short loc_1800B605B
0x1800b600c  test    r9d, r9d
0x1800b600f  jz      short loc_1800B605B
0x1800b6011  mov     rax, [rbx]
0x1800b6014  mov     [rdi+rax+0C8h], edx
0x1800b601b  mov     rcx, [rbx]
0x1800b601e  mov     eax, dword ptr [rsp+1E0h+var_180+0Ch]
0x1800b6022  mov     [rdi+rcx+0CCh], eax
0x1800b6029  mov     rax, [rbx]
0x1800b602c  mov     ecx, [rdi+rax+0C8h]
0x1800b6033  cmp     dword ptr cs:qword_18010BFE8, ecx
0x1800b6039  jb      short loc_1800B6041
0x1800b603b  mov     dword ptr cs:qword_18010BFE8, ecx
0x1800b6041  mov     rax, [rbx]
0x1800b6044  mov     ecx, [rdi+rax+0CCh]
0x1800b604b  cmp     dword ptr cs:qword_18010BFE8+4, ecx
0x1800b6051  ja      short loc_1800B6094
0x1800b6053  mov     dword ptr cs:qword_18010BFE8+4, ecx
0x1800b6059  jmp     short loc_1800B6094
0x1800b605b  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x1800b6062  jz      short loc_1800B6074
0x1800b6064  mov     [rsp+1E0h+var_1C0], esi
0x1800b6068  lea     rcx, aInvalidSourceS; "Invalid source size settings { %d/%d/%d"...
0x1800b606f  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800b6074  mov     rcx, [rbx]
0x1800b6077  mov     eax, dword ptr cs:qword_18010BFE8
0x1800b607d  mov     [rdi+rcx+0C8h], eax
0x1800b6084  mov     rcx, [rbx]
0x1800b6087  mov     eax, dword ptr cs:qword_18010BFE8+4
0x1800b608d  mov     [rdi+rcx+0CCh], eax
0x1800b6094  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x1800b609b  jz      short loc_1800B60DB
0x1800b609d  mov     rcx, [rbx]
0x1800b60a0  movsx   r8d, byte ptr [rbp+0E0h+var_160+0Fh]
0x1800b60a5  mov     eax, [rdi+rcx+0CCh]
0x1800b60ac  mov     [rsp+1E0h+var_1A8], eax
0x1800b60b0  mov     eax, [rdi+rcx+0C8h]
0x1800b60b7  mov     [rsp+1E0h+var_1B0], eax
0x1800b60bb  mov     eax, dword ptr [rbp+0E0h+var_A0+4]
0x1800b60be  mov     dword ptr [rsp+1E0h+var_1B8], eax
0x1800b60c2  mov     eax, dword ptr [rbp+0E0h+var_A0]
0x1800b60c5  mov     [rsp+1E0h+var_1C0], eax
0x1800b60c9  mov     r9d, dword ptr [rbp+0E0h+var_B0+4]
0x1800b60cd  mov     edx, esi
0x1800b60cf  lea     rcx, aEnumeratedVari; "Enumerated variant %d: ID %d, Revision "...
0x1800b60d6  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800b60db  inc     esi
0x1800b60dd  cmp     esi, r14d
0x1800b60e0  jb      loc_1800B5EC7
0x1800b60e6  xor     edi, edi
0x1800b60e8  lea     rcx, [rsp+1E0h+var_198]
0x1800b60ed  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b60f2  mov     eax, edi
0x1800b60f4  mov     rcx, [rbp+0E0h+var_90]
0x1800b60f8  xor     rcx, rsp; StackCookie
0x1800b60fb  call    __security_check_cookie
0x1800b6100  lea     r11, [rsp+1E0h+var_20]
0x1800b6108  mov     rbx, [r11+40h]
0x1800b610c  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b6111  movaps  xmm7, xmmword ptr [r11-20h]
0x1800b6116  movaps  xmm8, xmmword ptr [r11-30h]
0x1800b611b  movaps  xmm9, xmmword ptr [r11-40h]
0x1800b6120  movaps  xmm10, xmmword ptr [r11-50h]
0x1800b6125  movaps  xmm11, xmmword ptr [r11-60h]
0x1800b612a  mov     rsp, r11
0x1800b612d  pop     r15
0x1800b612f  pop     r14
0x1800b6131  pop     rdi
0x1800b6132  pop     rsi
0x1800b6133  pop     rbp
0x1800b6134  retn
0x1800b6135  mov     r9d, eax
0x1800b6138  mov     edx, 309h
0x1800b613d  jmp     loc_1800B5D5E
```
