# Rdp::Stack::Graphics::CGrfxPipeline::OpenPropertyStore(IPropertyStore * *)

- ea: `0x18000b2c0`
- end: `0x18000b464`
- name: `?OpenPropertyStore@CGrfxPipeline@Graphics@Stack@Rdp@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(Rdp::Stack::Graphics::CGrfxPipeline *__hidden this, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b2c0`
- `0x18000cf28`
- `0x18000d590`
- `0x18000db64`
- `0x18000dbf4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b32a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b40f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b32a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b40f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000b39e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000b39e`

## string_xrefs

- `0x18000b3a9`: `Failed to create property store`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CGrfxPipeline::OpenPropertyStore(void **this, struct IPropertyStore **a2)
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
      &WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
        (const char *)0x80004003LL,
        v19);
    v10 = (struct IPropertyStore **)(this + 3);
    if ( !this[3] )
    {
      wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(this + 3);
      v11 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, this + 3);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
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
        &WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids,
        v15);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA1,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18000b2c0  mov     [rsp+arg_0], rbx
0x18000b2c5  mov     [rsp+arg_10], rsi
0x18000b2ca  push    rdi
0x18000b2cb  push    r12
0x18000b2cd  push    r13
0x18000b2cf  push    r14
0x18000b2d1  push    r15
0x18000b2d3  sub     rsp, 50h
0x18000b2d7  mov     r14, rdx
0x18000b2da  mov     r13, rcx
0x18000b2dd  lea     r12, WPP_GLOBAL_Control
0x18000b2e4  mov     rax, cs:WPP_GLOBAL_Control
0x18000b2eb  mov     bl, 1
0x18000b2ed  cmp     rax, r12
0x18000b2f0  jz      short loc_18000B302
0x18000b2f2  test    [rax+1Ch], bl
0x18000b2f5  jz      short loc_18000B302
0x18000b2f7  cmp     byte ptr [rax+19h], 4
0x18000b2fb  jb      short loc_18000B302
0x18000b2fd  mov     dil, bl
0x18000b300  jmp     short loc_18000B305
0x18000b302  xor     dil, dil
0x18000b305  lea     rax, WPP_RECORDER_INITIALIZED
0x18000b30c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000b313  setnz   sil
0x18000b317  test    dil, dil
0x18000b31a  jnz     short loc_18000B32A
0x18000b31c  test    sil, sil
0x18000b31f  jnz     short loc_18000B32A
0x18000b321  lea     r15, WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids
0x18000b328  jmp     short loc_18000B361
0x18000b32a  call    cs:__imp_GetCurrentThreadId
0x18000b330  mov     dword ptr [rsp+78h+var_38], eax; char
0x18000b334  lea     r15, WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids
0x18000b33b  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x18000b340  mov     [rsp+78h+var_48], 0Ah; __int16
0x18000b347  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b34e  mov     r9, [rcx+28h]; int
0x18000b352  mov     r8b, sil; int
0x18000b355  mov     dl, dil; int
0x18000b358  mov     rcx, [rcx+10h]; int
0x18000b35c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000b361  mov     rcx, [rsp+78h]; this
0x18000b366  test    r14, r14
0x18000b369  jnz     short loc_18000B382
0x18000b36b  mov     r9d, 80004003h; char *
0x18000b371  lea     r8, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000b378  mov     edx, 8Dh; void *
0x18000b37d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b382  lea     rdi, [r13+18h]
0x18000b386  cmp     qword ptr [rdi], 0
0x18000b38a  jnz     short loc_18000B3C9
0x18000b38c  mov     rcx, rdi
0x18000b38f  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18000b394  mov     rdx, rdi; ppv
0x18000b397  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000b39e  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000b3a4  mov     rcx, [rsp+78h]; this
0x18000b3a9  lea     rdx, aFailedToCreate_5; "Failed to create property store"
0x18000b3b0  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18000b3b5  mov     r9d, eax; char *
0x18000b3b8  lea     r8, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000b3bf  mov     edx, 98h; void *
0x18000b3c4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000b3c9  mov     rcx, [rdi]
0x18000b3cc  mov     [r14], rcx
0x18000b3cf  mov     rax, [rcx]
0x18000b3d2  mov     rax, [rax+8]
0x18000b3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3db  mov     rax, cs:WPP_GLOBAL_Control
0x18000b3e2  cmp     rax, r12
0x18000b3e5  jz      short loc_18000B3F2
0x18000b3e7  test    [rax+1Ch], bl
0x18000b3ea  jz      short loc_18000B3F2
0x18000b3ec  cmp     byte ptr [rax+19h], 4
0x18000b3f0  jnb     short loc_18000B3F4
0x18000b3f2  xor     bl, bl
0x18000b3f4  lea     rax, WPP_RECORDER_INITIALIZED
0x18000b3fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000b402  setnz   dil
0x18000b406  test    bl, bl
0x18000b408  jnz     short loc_18000B40F
0x18000b40a  test    dil, dil
0x18000b40d  jz      short loc_18000B43E
0x18000b40f  call    cs:__imp_GetCurrentThreadId
0x18000b415  mov     dword ptr [rsp+78h+var_38], eax; char
0x18000b419  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x18000b41e  mov     [rsp+78h+var_48], 0Bh; __int16
0x18000b425  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b42c  mov     r9, [rcx+28h]; int
0x18000b430  mov     r8b, dil; int
0x18000b433  mov     dl, bl; int
0x18000b435  mov     rcx, [rcx+10h]; int
0x18000b439  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000b43e  xor     eax, eax
0x18000b440  jmp     short loc_18000B449
0x18000b442  mov     eax, [rsp+78h+arg_8]
0x18000b449  lea     r11, [rsp+78h+var_28]
0x18000b44e  mov     rbx, [r11+30h]
0x18000b452  mov     rsi, [r11+40h]
0x18000b456  mov     rsp, r11
0x18000b459  pop     r15
0x18000b45b  pop     r14
0x18000b45d  pop     r13
0x18000b45f  pop     r12
0x18000b461  pop     rdi
0x18000b462  retn
```
