# Rdp::Stack::Graphics::CMonitorConfig::OpenPropertyStore(IPropertyStore * *)

- ea: `0x1800174c0`
- end: `0x180017664`
- name: `?OpenPropertyStore@CMonitorConfig@Graphics@Stack@Rdp@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(Rdp::Stack::Graphics::CMonitorConfig *__hidden this, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000cf28`
- `0x18000d590`
- `0x18000db64`
- `0x18000dbf4`
- `0x1800174c0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001752a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001760f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001752a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001760f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001759e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001759e`

## string_xrefs

- `0x1800175a9`: `Failed to create property store`
- `0x180017571`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfig.cpp`
- `0x1800175b8`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfig.cpp`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CMonitorConfig::OpenPropertyStore(void **this, struct IPropertyStore **a2)
{
  char v4; // bl
  bool v5; // di
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  struct IPropertyStore **v10; // rdi
  unsigned int v11; // eax
  struct IPropertyStore *v12; // rcx
  const char *v13; // r9
  bool v14; // di
  char v15; // al
  int v16; // r8d
  int v17; // edx
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-58h]
  const char *v20; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v19,
      (int)v20,
      10,
      &WPP_87a35347404335db2d53aef7446eb746_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
        (const char *)0x80004003LL,
        v19);
    v10 = (struct IPropertyStore **)(this + 1);
    if ( !this[1] )
    {
      wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(this + 1);
      v11 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, this + 1);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1CB,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
        (const char *)v11,
        (int)"Failed to create property store",
        v20);
    }
    v12 = *v10;
    *a2 = *v10;
    ((void (__fastcall *)(struct IPropertyStore *))v12->lpVtbl->AddRef)(v12);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = GetCurrentThreadId();
      LOBYTE(v16) = v14;
      LOBYTE(v17) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v19,
        (int)v20,
        11,
        &WPP_87a35347404335db2d53aef7446eb746_Traceguids,
        v15);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1D4,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800174c0  mov     [rsp+arg_0], rbx
0x1800174c5  mov     [rsp+arg_10], rsi
0x1800174ca  push    rdi
0x1800174cb  push    r12
0x1800174cd  push    r13
0x1800174cf  push    r14
0x1800174d1  push    r15
0x1800174d3  sub     rsp, 50h
0x1800174d7  mov     r14, rdx
0x1800174da  mov     r13, rcx
0x1800174dd  lea     r12, WPP_GLOBAL_Control
0x1800174e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800174eb  mov     bl, 1
0x1800174ed  cmp     rax, r12
0x1800174f0  jz      short loc_180017502
0x1800174f2  test    [rax+1Ch], bl
0x1800174f5  jz      short loc_180017502
0x1800174f7  cmp     byte ptr [rax+19h], 4
0x1800174fb  jb      short loc_180017502
0x1800174fd  mov     dil, bl
0x180017500  jmp     short loc_180017505
0x180017502  xor     dil, dil
0x180017505  lea     rax, WPP_RECORDER_INITIALIZED
0x18001750c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180017513  setnz   sil
0x180017517  test    dil, dil
0x18001751a  jnz     short loc_18001752A
0x18001751c  test    sil, sil
0x18001751f  jnz     short loc_18001752A
0x180017521  lea     r15, WPP_87a35347404335db2d53aef7446eb746_Traceguids
0x180017528  jmp     short loc_180017561
0x18001752a  call    cs:__imp_GetCurrentThreadId
0x180017530  mov     dword ptr [rsp+78h+var_38], eax; char
0x180017534  lea     r15, WPP_87a35347404335db2d53aef7446eb746_Traceguids
0x18001753b  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x180017540  mov     [rsp+78h+var_48], 0Ah; __int16
0x180017547  mov     rcx, cs:WPP_GLOBAL_Control
0x18001754e  mov     r9, [rcx+28h]; int
0x180017552  mov     r8b, sil; int
0x180017555  mov     dl, dil; int
0x180017558  mov     rcx, [rcx+10h]; int
0x18001755c  call    WPP_RECORDER_AND_TRACE_SF_D
0x180017561  mov     rcx, [rsp+78h]; this
0x180017566  test    r14, r14
0x180017569  jnz     short loc_180017582
0x18001756b  mov     r9d, 80004003h; char *
0x180017571  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180017578  mov     edx, 1C0h; void *
0x18001757d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017582  lea     rdi, [r13+8]
0x180017586  cmp     qword ptr [rdi], 0
0x18001758a  jnz     short loc_1800175C9
0x18001758c  mov     rcx, rdi
0x18001758f  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x180017594  mov     rdx, rdi; ppv
0x180017597  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001759e  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800175a4  mov     rcx, [rsp+78h]; this
0x1800175a9  lea     rdx, aFailedToCreate_5; "Failed to create property store"
0x1800175b0  mov     qword ptr [rsp+78h+var_58], rdx; int
0x1800175b5  mov     r9d, eax; char *
0x1800175b8  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800175bf  mov     edx, 1CBh; void *
0x1800175c4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800175c9  mov     rcx, [rdi]
0x1800175cc  mov     [r14], rcx
0x1800175cf  mov     rax, [rcx]
0x1800175d2  mov     rax, [rax+8]
0x1800175d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175db  mov     rax, cs:WPP_GLOBAL_Control
0x1800175e2  cmp     rax, r12
0x1800175e5  jz      short loc_1800175F2
0x1800175e7  test    [rax+1Ch], bl
0x1800175ea  jz      short loc_1800175F2
0x1800175ec  cmp     byte ptr [rax+19h], 4
0x1800175f0  jnb     short loc_1800175F4
0x1800175f2  xor     bl, bl
0x1800175f4  lea     rax, WPP_RECORDER_INITIALIZED
0x1800175fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180017602  setnz   dil
0x180017606  test    bl, bl
0x180017608  jnz     short loc_18001760F
0x18001760a  test    dil, dil
0x18001760d  jz      short loc_18001763E
0x18001760f  call    cs:__imp_GetCurrentThreadId
0x180017615  mov     dword ptr [rsp+78h+var_38], eax; char
0x180017619  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x18001761e  mov     [rsp+78h+var_48], 0Bh; __int16
0x180017625  mov     rcx, cs:WPP_GLOBAL_Control
0x18001762c  mov     r9, [rcx+28h]; int
0x180017630  mov     r8b, dil; int
0x180017633  mov     dl, bl; int
0x180017635  mov     rcx, [rcx+10h]; int
0x180017639  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001763e  xor     eax, eax
0x180017640  jmp     short loc_180017649
0x180017642  mov     eax, [rsp+78h+arg_8]
0x180017649  lea     r11, [rsp+78h+var_28]
0x18001764e  mov     rbx, [r11+30h]
0x180017652  mov     rsi, [r11+40h]
0x180017656  mov     rsp, r11
0x180017659  pop     r15
0x18001765b  pop     r14
0x18001765d  pop     r13
0x18001765f  pop     r12
0x180017661  pop     rdi
0x180017662  retn
```
