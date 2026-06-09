# Rdp::Stack::Graphics::CGrfxPipeline::SetMonitorLayout(uint,tagTS_MONITOR_DEF *,tagTS_MONITOR_ATTRIBUTES *,tagTS_MONITOR_VAIL_ATTRIBUTES *)

- ea: `0x18000c0f0`
- end: `0x18000c409`
- name: `?SetMonitorLayout@CGrfxPipeline@Graphics@Stack@Rdp@@EEAAJIPEAUtagTS_MONITOR_DEF@@PEAUtagTS_MONITOR_ATTRIBUTES@@PEAUtagTS_MONITOR_VAIL_ATTRIBUTES@@@Z`
- size: `793`
- prototype: `__int64 __fastcall(struct IPropertyStore **this, unsigned int, struct tagTS_MONITOR_DEF *, struct tagTS_MONITOR_ATTRIBUTES *, struct tagTS_MONITOR_VAIL_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003714`
- `0x1800049b8`
- `0x180007b28`
- `0x180009a78`
- `0x180009ab0`
- `0x180009bc0`
- `0x18000a0e4`
- `0x18000b578`
- `0x18000c0f0`
- `0x18000da14`
- `0x18000dabc`
- `0x18000dbf4`
- `0x180016b1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c167`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c356`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c167`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c356`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Stack::Graphics::CGrfxPipeline::SetMonitorLayout(
        struct IPropertyStore **this,
        unsigned int a2,
        struct tagTS_MONITOR_DEF *a3,
        struct tagTS_MONITOR_ATTRIBUTES *a4,
        struct tagTS_MONITOR_VAIL_ATTRIBUTES *a5)
{
  __int64 v5; // r14
  char v7; // di
  bool v8; // bl
  bool v9; // si
  char CurrentThreadId; // al
  int v11; // r8d
  int v12; // edx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 i; // rbx
  _QWORD *j; // rsi
  _QWORD *v17; // r14
  const char *v18; // r9
  bool v19; // bl
  char v20; // al
  int v21; // r8d
  int v22; // edx
  __int64 result; // rax
  int v24; // [rsp+20h] [rbp-B8h]
  int v25; // [rsp+28h] [rbp-B0h]
  __int64 v26; // [rsp+50h] [rbp-88h] BYREF
  __int128 v27; // [rsp+58h] [rbp-80h] BYREF
  __int128 v28; // [rsp+68h] [rbp-70h] BYREF
  __int64 v29; // [rsp+78h] [rbp-60h]
  __int128 v30; // [rsp+80h] [rbp-58h] BYREF
  __int64 v31; // [rsp+90h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v5 = a2;
  v7 = 1;
  v8 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v11) = v9;
    LOBYTE(v12) = v8;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v24,
      v25,
      16,
      &WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids,
      CurrentThreadId);
  }
  v28 = 0;
  v29 = 0;
  try
  {
    std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::reserve();
    for ( i = 0; (unsigned int)i < (unsigned int)v5; i = (unsigned int)(i + 1) )
    {
      *(_QWORD *)&v27 = operator new(0x160u);
      v13 = Rdp::Stack::Graphics::CMonitorConfig::CMonitorConfig(
              (Rdp::Stack::Graphics::CMonitorConfig *)v27,
              i,
              (struct tagTS_MONITOR_DEF *)((char *)a3 + 20 * i),
              (struct tagTS_MONITOR_ATTRIBUTES *)((char *)a4 + 20 * i),
              (struct tagTS_MONITOR_VAIL_ATTRIBUTES *)((char *)a5 + 540 * (unsigned int)i),
              this[2]);
      wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
        &v26,
        (v13 + 80) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64));
      if ( *((_QWORD *)&v28 + 1) == v29 )
      {
        std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(
          &v28,
          *((_QWORD *)&v28 + 1),
          &v26);
      }
      else
      {
        v14 = v26;
        v26 = 0;
        **((_QWORD **)&v28 + 1) = v14;
        *((_QWORD *)&v28 + 1) += 8LL;
      }
      wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v26);
    }
    v30 = 0;
    v31 = 0;
    std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::reserve(&v30, v5);
    v17 = (_QWORD *)*((_QWORD *)&v28 + 1);
    for ( j = (_QWORD *)v28; j != v17; ++j )
    {
      *(_QWORD *)&v27 = 1;
      *((_QWORD *)&v27 + 1) = *j;
      if ( *((_QWORD *)&v30 + 1) == v31 )
      {
        std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Emplace_reallocate<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>(
          &v30,
          *((_QWORD *)&v30 + 1),
          &v27);
      }
      else
      {
        **((_OWORD **)&v30 + 1) = v27;
        *((_QWORD *)&v30 + 1) += 16LL;
      }
    }
    Rdp::Stack::Graphics::CGrfxPipeline::ProcessMonitorConfig(
      (__int64)(this - 11),
      0,
      (const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO **)&v30);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v7 = 0;
    }
    v19 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = GetCurrentThreadId();
      LOBYTE(v21) = v19;
      LOBYTE(v22) = v7;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        v21,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v24,
        v25,
        17,
        &WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids,
        v20);
    }
    if ( (_QWORD)v30 )
    {
      std::_Deallocate<16>(v30, (v31 - v30) & 0xFFFFFFFFFFFFFFF0uLL);
      v30 = 0;
      v31 = 0;
    }
    if ( (_QWORD)v28 )
    {
      std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
        v28,
        *((_QWORD *)&v28 + 1));
      std::_Deallocate<16>(v28, (v29 - v28) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x210,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x18000c0f0  mov     [rsp+arg_18], r9
0x18000c0f5  mov     [rsp+arg_10], r8
0x18000c0fa  push    rbx
0x18000c0fb  push    rsi
0x18000c0fc  push    rdi
0x18000c0fd  push    r12
0x18000c0ff  push    r13
0x18000c101  push    r14
0x18000c103  push    r15
0x18000c105  sub     rsp, 0A0h
0x18000c10c  mov     r14d, edx
0x18000c10f  mov     r13, rcx
0x18000c112  lea     rcx, WPP_GLOBAL_Control
0x18000c119  mov     rax, cs:WPP_GLOBAL_Control
0x18000c120  mov     edi, 1
0x18000c125  cmp     rax, rcx
0x18000c128  jz      short loc_18000C13B
0x18000c12a  test    [rax+1Ch], dil
0x18000c12e  jz      short loc_18000C13B
0x18000c130  cmp     byte ptr [rax+19h], 4
0x18000c134  jb      short loc_18000C13B
0x18000c136  mov     bl, dil
0x18000c139  jmp     short loc_18000C13D
0x18000c13b  xor     bl, bl
0x18000c13d  lea     rax, WPP_RECORDER_INITIALIZED
0x18000c144  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000c14b  setnz   sil
0x18000c14f  test    bl, bl
0x18000c151  jnz     short loc_18000C167
0x18000c153  test    sil, sil
0x18000c156  jnz     short loc_18000C167
0x18000c158  mov     r15d, 10h
0x18000c15e  lea     r12, WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids
0x18000c165  jmp     short loc_18000C1A2
0x18000c167  call    cs:__imp_GetCurrentThreadId
0x18000c16d  mov     r15d, 10h
0x18000c173  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18000c177  lea     r12, WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids
0x18000c17e  mov     [rsp+0D8h+MessageGuid], r12; MessageGuid
0x18000c183  mov     [rsp+0D8h+var_A8], r15w; __int16
0x18000c189  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c190  mov     r9, [rcx+28h]; int
0x18000c194  mov     r8b, sil; int
0x18000c197  mov     dl, bl; int
0x18000c199  mov     rcx, [rcx+10h]; int
0x18000c19d  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000c1a2  xorps   xmm0, xmm0
0x18000c1a5  movdqu  [rsp+0D8h+var_70], xmm0
0x18000c1ab  mov     [rsp+0D8h+var_60], 0
0x18000c1b4  mov     rdx, r14
0x18000c1b7  lea     rcx, [rsp+0D8h+var_70]
0x18000c1bc  call    ?reserve@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAX_K@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::reserve(unsigned __int64)
0x18000c1c1  xor     ebx, ebx
0x18000c1c3  cmp     ebx, r14d
0x18000c1c6  jnb     loc_18000C27F
0x18000c1cc  mov     ecx, 160h; Size
0x18000c1d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c1d6  mov     qword ptr [rsp+0D8h+var_80], rax
0x18000c1db  mov     ecx, ebx
0x18000c1dd  lea     rdx, [rbx+rbx*4]
0x18000c1e1  imul    r10, rcx, 21Ch
0x18000c1e8  add     r10, [rsp+0D8h+arg_20]
0x18000c1f0  mov     rcx, [rsp+0D8h+arg_18]
0x18000c1f8  lea     r9, [rcx+rdx*4]; struct tagTS_MONITOR_ATTRIBUTES *
0x18000c1fc  mov     rcx, [rsp+0D8h+arg_10]
0x18000c204  lea     r8, [rcx+rdx*4]; struct tagTS_MONITOR_DEF *
0x18000c208  mov     rcx, [r13+10h]
0x18000c20c  mov     [rsp+0D8h+var_B0], rcx; struct IPropertyStore *
0x18000c211  mov     [rsp+0D8h+var_B8], r10; struct tagTS_MONITOR_VAIL_ATTRIBUTES *
0x18000c216  mov     edx, ebx; unsigned int
0x18000c218  mov     rcx, rax; this
0x18000c21b  call    ??0CMonitorConfig@Graphics@Stack@Rdp@@QEAA@IAEBUtagTS_MONITOR_DEF@@AEBUtagTS_MONITOR_ATTRIBUTES@@AEBUtagTS_MONITOR_VAIL_ATTRIBUTES@@PEAUIPropertyStore@@@Z; Rdp::Stack::Graphics::CMonitorConfig::CMonitorConfig(uint,tagTS_MONITOR_DEF const &,tagTS_MONITOR_ATTRIBUTES const &,tagTS_MONITOR_VAIL_ATTRIBUTES const &,IPropertyStore *)
0x18000c220  nop
0x18000c221  lea     rcx, [rax+50h]
0x18000c225  neg     rax
0x18000c228  sbb     rdx, rdx
0x18000c22b  and     rdx, rcx
0x18000c22e  lea     rcx, [rsp+0D8h+var_88]
0x18000c233  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18000c238  nop
0x18000c239  mov     rdx, qword ptr [rsp+0D8h+var_70+8]
0x18000c23e  cmp     rdx, [rsp+0D8h+var_60]
0x18000c243  jz      short loc_18000C25E
0x18000c245  mov     rax, [rsp+0D8h+var_88]
0x18000c24a  mov     [rsp+0D8h+var_88], 0
0x18000c253  mov     [rdx], rax
0x18000c256  add     qword ptr [rsp+0D8h+var_70+8], 8
0x18000c25c  jmp     short loc_18000C26E
0x18000c25e  lea     r8, [rsp+0D8h+var_88]
0x18000c263  lea     rcx, [rsp+0D8h+var_70]
0x18000c268  call    ??$_Emplace_reallocate@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> &&)
0x18000c26d  nop
0x18000c26e  lea     rcx, [rsp+0D8h+var_88]
0x18000c273  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18000c278  add     ebx, edi
0x18000c27a  jmp     loc_18000C1C3
0x18000c27f  xorps   xmm0, xmm0
0x18000c282  movdqu  [rsp+0D8h+var_58], xmm0
0x18000c28b  mov     [rsp+0D8h+var_48], 0
0x18000c297  mov     rdx, r14
0x18000c29a  lea     rcx, [rsp+0D8h+var_58]
0x18000c2a2  call    ?reserve@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@QEAAX_K@Z; std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::reserve(unsigned __int64)
0x18000c2a7  mov     rsi, qword ptr [rsp+0D8h+var_70]
0x18000c2ac  mov     r14, qword ptr [rsp+0D8h+var_70+8]
0x18000c2b1  lea     rbx, [rsp+0D8h+var_58]
0x18000c2b9  cmp     rsi, r14
0x18000c2bc  jz      short loc_18000C307
0x18000c2be  mov     qword ptr [rsp+0D8h+var_80], 1
0x18000c2c7  mov     rax, [rsi]
0x18000c2ca  mov     qword ptr [rsp+0D8h+var_80+8], rax
0x18000c2cf  mov     rdx, qword ptr [rsp+0D8h+var_58+8]
0x18000c2d7  cmp     rdx, [rsp+0D8h+var_48]
0x18000c2df  jz      short loc_18000C2F4
0x18000c2e1  movups  xmm0, [rsp+0D8h+var_80]
0x18000c2e6  movdqu  xmmword ptr [rdx], xmm0
0x18000c2ea  add     qword ptr [rsp+0D8h+var_58+8], r15
0x18000c2f2  jmp     short loc_18000C301
0x18000c2f4  lea     r8, [rsp+0D8h+var_80]
0x18000c2f9  mov     rcx, rbx
0x18000c2fc  call    ??$_Emplace_reallocate@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@AEAAPEAURDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@QEAU234@$$QEAU234@@Z; std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Emplace_reallocate<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>(Rdp::Stack::RDPLITE_MONITORCONFIG_INFO * const,Rdp::Stack::RDPLITE_MONITORCONFIG_INFO &&)
0x18000c301  add     rsi, 8
0x18000c305  jmp     short loc_18000C2B9
0x18000c307  lea     rcx, [r13-58h]
0x18000c30b  lea     r8, [rsp+0D8h+var_58]
0x18000c313  xor     edx, edx
0x18000c315  call    ?ProcessMonitorConfig@CGrfxPipeline@Graphics@Stack@Rdp@@QEAAJ_NAEBV?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@@Z; Rdp::Stack::Graphics::CGrfxPipeline::ProcessMonitorConfig(bool,std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO> const &)
0x18000c31a  mov     rax, cs:WPP_GLOBAL_Control
0x18000c321  lea     rcx, WPP_GLOBAL_Control
0x18000c328  cmp     rax, rcx
0x18000c32b  jz      short loc_18000C339
0x18000c32d  test    [rax+1Ch], dil
0x18000c331  jz      short loc_18000C339
0x18000c333  cmp     byte ptr [rax+19h], 4
0x18000c337  jnb     short loc_18000C33C
0x18000c339  xor     dil, dil
0x18000c33c  lea     rax, WPP_RECORDER_INITIALIZED
0x18000c343  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000c34a  setnz   bl
0x18000c34d  test    dil, dil
0x18000c350  jnz     short loc_18000C356
0x18000c352  test    bl, bl
0x18000c354  jz      short loc_18000C387
0x18000c356  call    cs:__imp_GetCurrentThreadId
0x18000c35c  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18000c360  mov     [rsp+0D8h+MessageGuid], r12; MessageGuid
0x18000c365  mov     [rsp+0D8h+var_A8], 11h; __int16
0x18000c36c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c373  mov     r9, [rcx+28h]; int
0x18000c377  mov     r8b, bl; int
0x18000c37a  mov     dl, dil; int
0x18000c37d  mov     rcx, [rcx+10h]; int
0x18000c381  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000c386  nop
0x18000c387  mov     rcx, qword ptr [rsp+0D8h+var_58]
0x18000c38f  test    rcx, rcx
0x18000c392  jz      short loc_18000C3C0
0x18000c394  mov     rdx, [rsp+0D8h+var_48]
0x18000c39c  sub     rdx, rcx
0x18000c39f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000c3a3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c3a8  xorps   xmm0, xmm0
0x18000c3ab  movdqu  [rsp+0D8h+var_58], xmm0
0x18000c3b4  mov     [rsp+0D8h+var_48], 0
0x18000c3c0  mov     rcx, qword ptr [rsp+0D8h+var_70]
0x18000c3c5  test    rcx, rcx
0x18000c3c8  jz      short loc_18000C3EA
0x18000c3ca  mov     rdx, qword ptr [rsp+0D8h+var_70+8]
0x18000c3cf  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x18000c3d4  mov     rcx, qword ptr [rsp+0D8h+var_70]
0x18000c3d9  mov     rdx, [rsp+0D8h+var_60]
0x18000c3de  sub     rdx, rcx
0x18000c3e1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000c3e5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c3ea  xor     eax, eax
0x18000c3ec  jmp     short loc_18000C3F5
0x18000c3ee  mov     eax, [rsp+0D8h+arg_8]
0x18000c3f5  add     rsp, 0A0h
0x18000c3fc  pop     r15
0x18000c3fe  pop     r14
0x18000c400  pop     r13
0x18000c402  pop     r12
0x18000c404  pop     rdi
0x18000c405  pop     rsi
0x18000c406  pop     rbx
0x18000c407  retn
```
