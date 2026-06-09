# Rdp::Stack::Graphics::CMonitorConfig::SetMode(_RDPCFG_MONITORCONFIG_MODE const &)

- ea: `0x18001766c`
- end: `0x18001771a`
- name: `?SetMode@CMonitorConfig@Graphics@Stack@Rdp@@AEAAXAEBU_RDPCFG_MONITORCONFIG_MODE@@@Z`
- size: `174`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CMonitorConfig *this, const struct _RDPCFG_MONITORCONFIG_MODE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016ce0`

## callees

- `0x18000cea4`
- `0x1800168ec`
- `0x18001766c`

## string_xrefs

- `0x180017689`: `onecoreuap\termsrv\rdp_bin\win\rdplite\GrfxPipeline/MonitorConfig.h`

## pseudocode

```c
void __fastcall Rdp::Stack::Graphics::CMonitorConfig::SetMode(
        Rdp::Stack::Graphics::CMonitorConfig *this,
        const struct _RDPCFG_MONITORCONFIG_MODE *a2)
{
  char *v2; // rbx
  _OWORD *v5; // rdx
  const char *v6; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = (char *)this + 320;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x95,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\GrfxPipeline/MonitorConfig.h",
    (const char *)0x8007006FLL,
    (unsigned __int64)(0x2E8BA2E8BA2E8BA3LL * ((__int64)(*((_QWORD *)this + 41) - *((_QWORD *)this + 40)) >> 2)) >= 0x10,
    (bool)"Exceeded number of supported monitor modes",
    v6);
  v5 = (_OWORD *)*((_QWORD *)v2 + 1);
  if ( v5 == *((_OWORD **)v2 + 2) )
  {
    std::vector<_RDPCFG_MONITORCONFIG_MODE>::_Emplace_reallocate<_RDPCFG_MONITORCONFIG_MODE const &>(v2, v5, a2);
  }
  else
  {
    *v5 = *(_OWORD *)a2;
    v5[1] = *((_OWORD *)a2 + 1);
    *(_OWORD *)((char *)v5 + 28) = *(_OWORD *)((char *)a2 + 28);
    *((_QWORD *)v2 + 1) += 44LL;
  }
  *((_DWORD *)this + 25) |= 1u;
}

```

## disassembly

```asm
0x18001766c  mov     [rsp+arg_0], rbx
0x180017671  mov     [rsp+arg_8], rsi
0x180017676  push    rdi; char *
0x180017677  sub     rsp, 30h
0x18001767b  lea     rbx, [rcx+140h]
0x180017682  mov     rsi, rcx
0x180017685  mov     rax, [rbx+8]
0x180017689  lea     r8, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180017690  sub     rax, [rbx]
0x180017693  mov     rdi, rdx
0x180017696  sar     rax, 2
0x18001769a  lea     rdx, aExceededNumber; "Exceeded number of supported monitor mo"...
0x1800176a1  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x1800176a6  mov     rcx, 2E8BA2E8BA2E8BA3h
0x1800176b0  imul    rax, rcx
0x1800176b4  mov     rcx, [rsp+38h]; this
0x1800176b9  mov     r9d, 8007006Fh; char *
0x1800176bf  cmp     rax, 10h
0x1800176c3  mov     edx, 95h; void *
0x1800176c8  setnb   al
0x1800176cb  mov     [rsp+38h+var_18], al; char
0x1800176cf  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800176d4  mov     rdx, [rbx+8]
0x1800176d8  cmp     rdx, [rbx+10h]
0x1800176dc  jz      short loc_1800176FB
0x1800176de  movups  xmm0, xmmword ptr [rdi]
0x1800176e1  movups  xmmword ptr [rdx], xmm0
0x1800176e4  movups  xmm1, xmmword ptr [rdi+10h]
0x1800176e8  movups  xmmword ptr [rdx+10h], xmm1
0x1800176ec  movups  xmm0, xmmword ptr [rdi+1Ch]
0x1800176f0  movups  xmmword ptr [rdx+1Ch], xmm0
0x1800176f4  add     qword ptr [rbx+8], 2Ch ; ','
0x1800176f9  jmp     short loc_180017706
0x1800176fb  mov     r8, rdi
0x1800176fe  mov     rcx, rbx
0x180017701  call    ??$_Emplace_reallocate@AEBU_RDPCFG_MONITORCONFIG_MODE@@@?$vector@U_RDPCFG_MONITORCONFIG_MODE@@V?$allocator@U_RDPCFG_MONITORCONFIG_MODE@@@std@@@std@@AEAAPEAU_RDPCFG_MONITORCONFIG_MODE@@QEAU2@AEBU2@@Z; std::vector<_RDPCFG_MONITORCONFIG_MODE>::_Emplace_reallocate<_RDPCFG_MONITORCONFIG_MODE const &>(_RDPCFG_MONITORCONFIG_MODE * const,_RDPCFG_MONITORCONFIG_MODE const &)
0x180017706  or      dword ptr [rsi+64h], 1
0x18001770a  mov     rsi, [rsp+38h+arg_8]
0x18001770f  mov     rbx, [rsp+38h+arg_0]
0x180017714  add     rsp, 30h
0x180017718  pop     rdi
0x180017719  retn
```
