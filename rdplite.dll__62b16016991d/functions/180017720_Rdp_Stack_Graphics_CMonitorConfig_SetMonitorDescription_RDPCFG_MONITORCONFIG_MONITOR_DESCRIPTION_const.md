# Rdp::Stack::Graphics::CMonitorConfig::SetMonitorDescription(_RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION const &)

- ea: `0x180017720`
- end: `0x1800177c8`
- name: `?SetMonitorDescription@CMonitorConfig@Graphics@Stack@Rdp@@AEAAXAEBU_RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION@@@Z`
- size: `168`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CMonitorConfig *this, const struct _RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180016ce0`

## callees

- `0x180003b10`
- `0x18000cea4`
- `0x1800130dc`
- `0x1800135a0`
- `0x180017720`
- `0x180028340`

## string_xrefs

- `0x180017735`: `onecoreuap\termsrv\rdp_bin\win\rdplite\GrfxPipeline/MonitorConfig.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Graphics::CMonitorConfig::SetMonitorDescription(
        Rdp::Stack::Graphics::CMonitorConfig *this,
        const struct _RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION *a2)
{
  Rdp::Stack::Graphics::CMonitorConfig *v4; // rax
  void **v5; // rbx
  void *v6; // rdx
  void *v7; // rcx
  const char *v8; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v10; // [rsp+40h] [rbp+8h] BYREF

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xA7,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\GrfxPipeline/MonitorConfig.h",
    (const char *)0x8007006FLL,
    *(_DWORD *)a2 > 0x7FF4u,
    (bool)"Exceeded maximum allowed monitor description size",
    v8);
  v4 = (Rdp::Stack::Graphics::CMonitorConfig *)std::make_unique<unsigned char [0],0>(&v10, *(unsigned int *)a2);
  v5 = (void **)((char *)this + 344);
  if ( (Rdp::Stack::Graphics::CMonitorConfig *)((char *)this + 344) != v4 )
  {
    v6 = *(void **)v4;
    *(_QWORD *)v4 = 0;
    v7 = *v5;
    *v5 = v6;
    if ( v7 )
      operator delete(v7);
  }
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v10);
  memcpy_0(*v5, a2, *(unsigned int *)a2);
  *((_DWORD *)this + 25) |= 0x40u;
}

```

## disassembly

```asm
0x180017720  mov     [rsp+arg_8], rbx
0x180017725  mov     [rsp+arg_10], rsi
0x18001772a  push    rdi; char *
0x18001772b  sub     rsp, 30h
0x18001772f  cmp     dword ptr [rdx], 7FF4h
0x180017735  lea     r8, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001773c  mov     rdi, rdx
0x18001773f  mov     rsi, rcx
0x180017742  mov     rcx, [rsp+38h]; this
0x180017747  lea     rdx, aExceededMaximu; "Exceeded maximum allowed monitor descri"...
0x18001774e  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x180017753  setnbe  al
0x180017756  mov     edx, 0A7h; void *
0x18001775b  mov     [rsp+38h+var_18], al; char
0x18001775f  mov     r9d, 8007006Fh; char *
0x180017765  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001776a  mov     edx, [rdi]
0x18001776c  lea     rcx, [rsp+38h+arg_0]
0x180017771  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180017776  lea     rbx, [rsi+158h]
0x18001777d  cmp     rbx, rax
0x180017780  jz      short loc_18001779C
0x180017782  mov     rdx, [rax]
0x180017785  mov     qword ptr [rax], 0
0x18001778c  mov     rcx, [rbx]; Block
0x18001778f  mov     [rbx], rdx
0x180017792  test    rcx, rcx
0x180017795  jz      short loc_18001779C
0x180017797  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001779c  lea     rcx, [rsp+38h+arg_0]
0x1800177a1  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1800177a6  mov     r8d, [rdi]; Size
0x1800177a9  mov     rdx, rdi; Src
0x1800177ac  mov     rcx, [rbx]; void *
0x1800177af  call    memcpy_0
0x1800177b4  or      dword ptr [rsi+64h], 40h
0x1800177b8  mov     rsi, [rsp+38h+arg_10]
0x1800177bd  mov     rbx, [rsp+38h+arg_8]
0x1800177c2  add     rsp, 30h
0x1800177c6  pop     rdi
0x1800177c7  retn
```
