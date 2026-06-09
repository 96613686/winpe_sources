# Rdp::Stack::Driver::CDriverControl3::OpenPropertyStore(IPropertyStore * *)

- ea: `0x1800143c0`
- end: `0x180014564`
- name: `?OpenPropertyStore@CDriverControl3@Driver@Stack@Rdp@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(Rdp::Stack::Driver::CDriverControl3 *__hidden this, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000cf28`
- `0x18000d590`
- `0x18000db64`
- `0x18000dbf4`
- `0x1800143c0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001442a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001450f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001442a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001450f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001449e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001449e`

## string_xrefs

- `0x1800144a9`: `Failed to create property store`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Driver::CDriverControl3::OpenPropertyStore(void **this, struct IPropertyStore **a2)
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
      12,
      &WPP_a030594cf1f33de86aa1e387072882dd_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
        (const char *)0x80004003LL,
        v19);
    v10 = (struct IPropertyStore **)(this + 1);
    if ( !this[1] )
    {
      wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(this + 1);
      v11 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, this + 1);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x128,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
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
        13,
        &WPP_a030594cf1f33de86aa1e387072882dd_Traceguids,
        v15);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x131,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800143c0  mov     [rsp+arg_0], rbx
0x1800143c5  mov     [rsp+arg_10], rsi
0x1800143ca  push    rdi
0x1800143cb  push    r12
0x1800143cd  push    r13
0x1800143cf  push    r14
0x1800143d1  push    r15
0x1800143d3  sub     rsp, 50h
0x1800143d7  mov     r14, rdx
0x1800143da  mov     r13, rcx
0x1800143dd  lea     r12, WPP_GLOBAL_Control
0x1800143e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800143eb  mov     bl, 1
0x1800143ed  cmp     rax, r12
0x1800143f0  jz      short loc_180014402
0x1800143f2  test    [rax+1Ch], bl
0x1800143f5  jz      short loc_180014402
0x1800143f7  cmp     byte ptr [rax+19h], 4
0x1800143fb  jb      short loc_180014402
0x1800143fd  mov     dil, bl
0x180014400  jmp     short loc_180014405
0x180014402  xor     dil, dil
0x180014405  lea     rax, WPP_RECORDER_INITIALIZED
0x18001440c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180014413  setnz   sil
0x180014417  test    dil, dil
0x18001441a  jnz     short loc_18001442A
0x18001441c  test    sil, sil
0x18001441f  jnz     short loc_18001442A
0x180014421  lea     r15, WPP_a030594cf1f33de86aa1e387072882dd_Traceguids
0x180014428  jmp     short loc_180014461
0x18001442a  call    cs:__imp_GetCurrentThreadId
0x180014430  mov     dword ptr [rsp+78h+var_38], eax; char
0x180014434  lea     r15, WPP_a030594cf1f33de86aa1e387072882dd_Traceguids
0x18001443b  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x180014440  mov     [rsp+78h+var_48], 0Ch; __int16
0x180014447  mov     rcx, cs:WPP_GLOBAL_Control
0x18001444e  mov     r9, [rcx+28h]; int
0x180014452  mov     r8b, sil; int
0x180014455  mov     dl, dil; int
0x180014458  mov     rcx, [rcx+10h]; int
0x18001445c  call    WPP_RECORDER_AND_TRACE_SF_D
0x180014461  mov     rcx, [rsp+78h]; this
0x180014466  test    r14, r14
0x180014469  jnz     short loc_180014482
0x18001446b  mov     r9d, 80004003h; char *
0x180014471  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180014478  mov     edx, 11Dh; void *
0x18001447d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014482  lea     rdi, [r13+8]
0x180014486  cmp     qword ptr [rdi], 0
0x18001448a  jnz     short loc_1800144C9
0x18001448c  mov     rcx, rdi
0x18001448f  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x180014494  mov     rdx, rdi; ppv
0x180014497  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001449e  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800144a4  mov     rcx, [rsp+78h]; this
0x1800144a9  lea     rdx, aFailedToCreate_5; "Failed to create property store"
0x1800144b0  mov     qword ptr [rsp+78h+var_58], rdx; int
0x1800144b5  mov     r9d, eax; char *
0x1800144b8  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800144bf  mov     edx, 128h; void *
0x1800144c4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800144c9  mov     rcx, [rdi]
0x1800144cc  mov     [r14], rcx
0x1800144cf  mov     rax, [rcx]
0x1800144d2  mov     rax, [rax+8]
0x1800144d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144db  mov     rax, cs:WPP_GLOBAL_Control
0x1800144e2  cmp     rax, r12
0x1800144e5  jz      short loc_1800144F2
0x1800144e7  test    [rax+1Ch], bl
0x1800144ea  jz      short loc_1800144F2
0x1800144ec  cmp     byte ptr [rax+19h], 4
0x1800144f0  jnb     short loc_1800144F4
0x1800144f2  xor     bl, bl
0x1800144f4  lea     rax, WPP_RECORDER_INITIALIZED
0x1800144fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180014502  setnz   dil
0x180014506  test    bl, bl
0x180014508  jnz     short loc_18001450F
0x18001450a  test    dil, dil
0x18001450d  jz      short loc_18001453E
0x18001450f  call    cs:__imp_GetCurrentThreadId
0x180014515  mov     dword ptr [rsp+78h+var_38], eax; char
0x180014519  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x18001451e  mov     [rsp+78h+var_48], 0Dh; __int16
0x180014525  mov     rcx, cs:WPP_GLOBAL_Control
0x18001452c  mov     r9, [rcx+28h]; int
0x180014530  mov     r8b, dil; int
0x180014533  mov     dl, bl; int
0x180014535  mov     rcx, [rcx+10h]; int
0x180014539  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001453e  xor     eax, eax
0x180014540  jmp     short loc_180014549
0x180014542  mov     eax, [rsp+78h+arg_8]
0x180014549  lea     r11, [rsp+78h+var_28]
0x18001454e  mov     rbx, [r11+30h]
0x180014552  mov     rsi, [r11+40h]
0x180014556  mov     rsp, r11
0x180014559  pop     r15
0x18001455b  pop     r14
0x18001455d  pop     r13
0x18001455f  pop     r12
0x180014561  pop     rdi
0x180014562  retn
```
