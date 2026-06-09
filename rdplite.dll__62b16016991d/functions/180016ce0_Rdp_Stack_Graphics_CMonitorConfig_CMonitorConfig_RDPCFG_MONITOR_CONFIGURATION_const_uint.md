# Rdp::Stack::Graphics::CMonitorConfig::CMonitorConfig(_RDPCFG_MONITOR_CONFIGURATION const *,uint)

- ea: `0x180016ce0`
- end: `0x180017213`
- name: `??0CMonitorConfig@Graphics@Stack@Rdp@@QEAA@PEBU_RDPCFG_MONITOR_CONFIGURATION@@I@Z`
- size: `1331`
- prototype: `Rdp::Stack::Graphics::CMonitorConfig *__fastcall(Rdp::Stack::Graphics::CMonitorConfig *this, const struct _RDPCFG_MONITOR_CONFIGURATION *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180016304`

## callees

- `0x180004154`
- `0x18000cea4`
- `0x18000cef0`
- `0x180016a90`
- `0x180016ce0`
- `0x18001766c`
- `0x180017720`
- `0x1800177d0`
- `0x180017808`

## string_xrefs

- `0x180016e08`: `Unexpected RDPCFG_MONITORCONFIG structures detected`
- `0x180016e21`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfig.cpp`
- `0x180016e43`: `Unable to move to RDPCFG_MONITORCONFIG_STRUCT_HEADER because buffer is too small`
- `0x180016e7e`: `RDPCFG_MONITORCONFIG_STRUCT_HEADER structure has invalid size %d`
- `0x18001717c`: `Unable to cast to RDPCFG_MONITORCONFIG_MODE because buffer is too small`
- `0x18001712e`: `Unable to cast to RDPCFG_MONITORCONFIG_DISPLAY_MODE because buffer is too small`
- `0x1800170ef`: `Unable to cast to RDPCFG_MONITORCONFIG_SCALE_FACTOR because buffer is too small`
- `0x180017082`: `Physical size cannot be updated`
- `0x1800170ad`: `Unable to cast to RDPCFG_MONITORCONFIG_PHYSICAL_SIZE because buffer is too small`
- `0x180017025`: `Unable to cast to RDPCFG_MONITORCONFIG_COLORIMETRY because buffer is too small`
- `0x180016fdc`: `Unable to cast to RDPCFG_MONITORCONFIG_SDR_WHITE_LEVEL because buffer is too small`
- `0x180016f76`: `Monitor description cannot be updated`
- `0x180016f9e`: `Unable to cast to RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION because buffer is too small`
- `0x180016eff`: `Container info cannot be updated`
- `0x180016f27`: `Unable to cast to RDPCFG_MONITORCONFIG_CONTAINER_INFO because buffer is too small`
- `0x1800171b7`: `Unsupported MONITORCONFIG structure type`
- `0x1800171d6`: `Unable to move to next RDPCFG_MONITORCONFIG_STRUCT_HEADER because buffer is too small`

## pseudocode

```c
Rdp::Stack::Graphics::CMonitorConfig *__fastcall Rdp::Stack::Graphics::CMonitorConfig::CMonitorConfig(
        Rdp::Stack::Graphics::CMonitorConfig *this,
        const struct _RDPCFG_MONITOR_CONFIGURATION *a2)
{
  int v4; // esi
  unsigned int v5; // esi
  unsigned int *i; // rdi
  char *v8; // [rsp+28h] [rbp-60h]
  char *v9; // [rsp+28h] [rbp-60h]
  char *v10; // [rsp+30h] [rbp-58h]
  char *v11; // [rsp+30h] [rbp-58h]
  char *v12; // [rsp+30h] [rbp-58h]
  char *v13; // [rsp+30h] [rbp-58h]
  char *v14; // [rsp+30h] [rbp-58h]
  char *v15; // [rsp+30h] [rbp-58h]
  char *v16; // [rsp+30h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  Rdp::Utils::Com::ComObject<Rdp::Stack::Graphics::CMonitorConfig,Rdp::Stack::IMonitorConfig>::ComObject<Rdp::Stack::Graphics::CMonitorConfig,Rdp::Stack::IMonitorConfig>();
  *(_QWORD *)this = &Rdp::Stack::Graphics::CMonitorConfig::`vftable'{for `Rdp::Utils::Com::IUnknownBase'};
  *((_QWORD *)this + 10) = &Rdp::Stack::Graphics::CMonitorConfig::`vftable'{for `Rdp::Stack::IMonitorConfig'};
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *(_OWORD *)((char *)this + 184) = 0;
  memset_0((char *)this + 200, 0, 0x4Cu);
  *(_QWORD *)((char *)this + 276) = 0;
  *((_DWORD *)this + 71) = 0;
  *((_OWORD *)this + 18) = 0;
  *((_OWORD *)this + 19) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  v4 = *(_DWORD *)a2;
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 2);
  *((_WORD *)this + 54) = *((_WORD *)a2 + 6);
  *((_WORD *)this + 55) = *((_WORD *)a2 + 7);
  *((_BYTE *)this + 112) = *((_BYTE *)a2 + 16);
  *((_BYTE *)this + 113) = *((_BYTE *)a2 + 17);
  *((_BYTE *)this + 114) = *((_BYTE *)a2 + 18);
  *((_BYTE *)this + 115) = *((_BYTE *)a2 + 19);
  *((_BYTE *)this + 116) = *((_BYTE *)a2 + 20);
  *((_BYTE *)this + 117) = *((_BYTE *)a2 + 21);
  *((_BYTE *)this + 118) = *((_BYTE *)a2 + 22);
  *((_BYTE *)this + 119) = *((_BYTE *)a2 + 23);
  v5 = v4 - 24;
  if ( v5 )
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
      (const char *)0x80070057LL,
      *((_DWORD *)a2 + 1) == 3,
      (bool)"Unexpected RDPCFG_MONITORCONFIG structures detected",
      v10);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
      (const char *)0x8007007ALL,
      v5 < 8,
      (bool)"Unable to move to RDPCFG_MONITORCONFIG_STRUCT_HEADER because buffer is too small",
      v11);
    for ( i = (unsigned int *)((char *)a2 + 24); ; i = (unsigned int *)((char *)i + *i) )
    {
      LODWORD(v12) = *i;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
        (const char *)0x8007007ALL,
        v5 < *i,
        (bool)"RDPCFG_MONITORCONFIG_STRUCT_HEADER structure has invalid size %d",
        v12);
      switch ( i[1] )
      {
        case 1u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xA9,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x8007007ALL,
            *i != 44,
            (bool)"Unable to cast to RDPCFG_MONITORCONFIG_MODE because buffer is too small",
            v13);
          Rdp::Stack::Graphics::CMonitorConfig::SetMode(this, (const struct _RDPCFG_MONITORCONFIG_MODE *)i);
          break;
        case 2u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xB4,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x8007007ALL,
            *i != 48,
            (bool)"Unable to cast to RDPCFG_MONITORCONFIG_DISPLAY_MODE because buffer is too small",
            v13);
          *(_OWORD *)((char *)this + 120) = *(_OWORD *)i;
          *(_OWORD *)((char *)this + 136) = *((_OWORD *)i + 1);
          *(_OWORD *)((char *)this + 152) = *((_OWORD *)i + 2);
          *((_DWORD *)this + 25) |= 2u;
          break;
        case 3u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xBF,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x8007007ALL,
            *i != 16,
            (bool)"Unable to cast to RDPCFG_MONITORCONFIG_SCALE_FACTOR because buffer is too small",
            v13);
          *(_OWORD *)((char *)this + 168) = *(_OWORD *)i;
          *((_DWORD *)this + 25) |= 4u;
          break;
        case 4u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xCA,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x80070057LL,
            *((_DWORD *)a2 + 1) == 2,
            (bool)"Physical size cannot be updated",
            v13);
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xD0,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x8007007ALL,
            *i != 16,
            (bool)"Unable to cast to RDPCFG_MONITORCONFIG_PHYSICAL_SIZE because buffer is too small",
            v16);
          *(_OWORD *)((char *)this + 184) = *(_OWORD *)i;
          *((_DWORD *)this + 25) |= 8u;
          break;
        case 5u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xDB,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x8007007ALL,
            *i != 76,
            (bool)"Unable to cast to RDPCFG_MONITORCONFIG_COLORIMETRY because buffer is too small",
            v13);
          *(_OWORD *)((char *)this + 200) = *(_OWORD *)i;
          *(_OWORD *)((char *)this + 216) = *((_OWORD *)i + 1);
          *(_OWORD *)((char *)this + 232) = *((_OWORD *)i + 2);
          *(_OWORD *)((char *)this + 248) = *((_OWORD *)i + 3);
          *(_OWORD *)((char *)this + 260) = *(_OWORD *)(i + 15);
          *((_DWORD *)this + 25) |= 0x10u;
          break;
        case 6u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xE6,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x8007007ALL,
            *i != 12,
            (bool)"Unable to cast to RDPCFG_MONITORCONFIG_SDR_WHITE_LEVEL because buffer is too small",
            v13);
          *(_QWORD *)((char *)this + 276) = *(_QWORD *)i;
          *((_DWORD *)this + 71) = i[2];
          *((_DWORD *)this + 25) |= 0x20u;
          break;
        case 7u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xF1,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x80070057LL,
            *((_DWORD *)a2 + 1) == 2,
            (bool)"Monitor description cannot be updated",
            v13);
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xF7,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x8007007ALL,
            *i <= 0xC,
            (bool)"Unable to cast to RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION because buffer is too small",
            v15);
          Rdp::Stack::Graphics::CMonitorConfig::SetMonitorDescription(
            this,
            (const struct _RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION *)i);
          break;
        case 8u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x102,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x80070057LL,
            *((_DWORD *)a2 + 1) == 2,
            (bool)"Container info cannot be updated",
            v13);
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x108,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x8007007ALL,
            *i != 32,
            (bool)"Unable to cast to RDPCFG_MONITORCONFIG_CONTAINER_INFO because buffer is too small",
            v14);
          *((_OWORD *)this + 18) = *(_OWORD *)i;
          *((_OWORD *)this + 19) = *((_OWORD *)i + 1);
          *((_DWORD *)this + 25) |= 0x80u;
          break;
        default:
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x111,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
            (const char *)0x80070057LL,
            (int)"Unsupported MONITORCONFIG structure type",
            v8);
      }
      v5 -= *i;
      if ( !v5 )
        break;
      if ( v5 < 8 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x127,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
          (const char *)0xC0000023LL,
          (int)"Unable to move to next RDPCFG_MONITORCONFIG_STRUCT_HEADER because buffer is too small",
          v9);
    }
    Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig(this);
  }
  return this;
}

```

## disassembly

```asm
0x180016ce0  mov     [rsp+arg_0], rcx
0x180016ce5  push    rbx
0x180016ce6  push    rbp
0x180016ce7  push    rsi
0x180016ce8  push    rdi
0x180016ce9  push    r12
0x180016ceb  push    r13
0x180016ced  push    r14
0x180016cef  push    r15
0x180016cf1  sub     rsp, 48h
0x180016cf5  mov     r14, rdx
0x180016cf8  mov     rbx, rcx
0x180016cfb  call    ??0?$ComObject@VCMonitorConfig@Graphics@Stack@Rdp@@UIMonitorConfig@34@@Com@Utils@Rdp@@IEAA@XZ; Rdp::Utils::Com::ComObject<Rdp::Stack::Graphics::CMonitorConfig,Rdp::Stack::IMonitorConfig>::ComObject<Rdp::Stack::Graphics::CMonitorConfig,Rdp::Stack::IMonitorConfig>(void)
0x180016d00  nop
0x180016d01  lea     rax, ??_7CMonitorConfig@Graphics@Stack@Rdp@@6BIUnknownBase@Com@Utils@3@@; const Rdp::Stack::Graphics::CMonitorConfig::`vftable'{for `Rdp::Utils::Com::IUnknownBase'}
0x180016d08  mov     [rbx], rax
0x180016d0b  lea     rax, ??_7CMonitorConfig@Graphics@Stack@Rdp@@6BIMonitorConfig@23@@; const Rdp::Stack::Graphics::CMonitorConfig::`vftable'{for `Rdp::Stack::IMonitorConfig'}
0x180016d12  mov     [rbx+50h], rax
0x180016d16  xor     edi, edi
0x180016d18  mov     [rbx+58h], rdi
0x180016d1c  mov     [rbx+60h], rdi
0x180016d20  xorps   xmm0, xmm0
0x180016d23  movups  xmmword ptr [rbx+68h], xmm0
0x180016d27  xorps   xmm1, xmm1
0x180016d2a  movups  xmmword ptr [rbx+78h], xmm1
0x180016d2e  movups  xmmword ptr [rbx+88h], xmm1
0x180016d35  movups  xmmword ptr [rbx+98h], xmm1
0x180016d3c  movups  xmmword ptr [rbx+0A8h], xmm0
0x180016d43  movups  xmmword ptr [rbx+0B8h], xmm1
0x180016d4a  lea     rbp, [rbx+0C8h]
0x180016d51  xor     edx, edx; Val
0x180016d53  lea     r8d, [rdi+4Ch]; Size
0x180016d57  mov     rcx, rbp; void *
0x180016d5a  call    memset_0
0x180016d5f  xor     eax, eax
0x180016d61  mov     [rbx+114h], rax
0x180016d68  mov     [rbx+11Ch], eax
0x180016d6e  xorps   xmm0, xmm0
0x180016d71  movups  xmmword ptr [rbx+120h], xmm0
0x180016d78  movups  xmmword ptr [rbx+130h], xmm0
0x180016d7f  mov     [rbx+140h], rdi
0x180016d86  mov     [rbx+148h], rdi
0x180016d8d  mov     [rbx+150h], rdi
0x180016d94  mov     [rbx+158h], rdi
0x180016d9b  mov     esi, [r14]
0x180016d9e  mov     eax, [r14+8]
0x180016da2  mov     [rbx+68h], eax
0x180016da5  movzx   eax, word ptr [r14+0Ch]
0x180016daa  mov     [rbx+6Ch], ax
0x180016dae  movzx   eax, word ptr [r14+0Eh]
0x180016db3  mov     [rbx+6Eh], ax
0x180016db7  mov     al, [r14+10h]
0x180016dbb  mov     [rbx+70h], al
0x180016dbe  mov     al, [r14+11h]
0x180016dc2  mov     [rbx+71h], al
0x180016dc5  mov     al, [r14+12h]
0x180016dc9  mov     [rbx+72h], al
0x180016dcc  mov     al, [r14+13h]
0x180016dd0  mov     [rbx+73h], al
0x180016dd3  mov     al, [r14+14h]
0x180016dd7  mov     [rbx+74h], al
0x180016dda  mov     al, [r14+15h]
0x180016dde  mov     [rbx+75h], al
0x180016de1  mov     al, [r14+16h]
0x180016de5  mov     [rbx+76h], al
0x180016de8  mov     al, [r14+17h]
0x180016dec  mov     [rbx+77h], al
0x180016def  add     esi, 0FFFFFFE8h
0x180016df2  jz      loc_1800171FF
0x180016df8  cmp     dword ptr [r14+4], 3
0x180016dfd  setz    al
0x180016e00  mov     rcx, [rsp+88h]; this
0x180016e08  lea     rdx, aUnexpectedRdpc; "Unexpected RDPCFG_MONITORCONFIG structu"...
0x180016e0f  mov     [rsp+88h+var_60], rdx; bool
0x180016e14  mov     [rsp+88h+var_68], al; char
0x180016e18  mov     r13d, 80070057h
0x180016e1e  mov     r9d, r13d; char *
0x180016e21  lea     r15, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180016e28  mov     r8, r15; unsigned int
0x180016e2b  mov     edx, 89h; void *
0x180016e30  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016e35  cmp     esi, 8
0x180016e38  setb    al
0x180016e3b  mov     rcx, [rsp+88h]; this
0x180016e43  lea     rdx, aUnableToMoveTo_0; "Unable to move to RDPCFG_MONITORCONFIG_"...
0x180016e4a  mov     [rsp+88h+var_60], rdx; bool
0x180016e4f  mov     [rsp+88h+var_68], al; char
0x180016e53  lea     r12d, [r13+23h]
0x180016e57  mov     r9d, r12d; char *
0x180016e5a  mov     r8, r15; unsigned int
0x180016e5d  mov     edx, 92h; void *
0x180016e62  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016e67  lea     rdi, [r14+18h]
0x180016e6b  mov     eax, [rdi]
0x180016e6d  cmp     esi, eax
0x180016e6f  setb    dl
0x180016e72  mov     rcx, [rsp+88h]; this
0x180016e7a  mov     dword ptr [rsp+88h+var_58], eax; char *
0x180016e7e  lea     rax, aRdpcfgMonitorc_1; "RDPCFG_MONITORCONFIG_STRUCT_HEADER stru"...
0x180016e85  mov     [rsp+88h+var_60], rax; char *
0x180016e8a  mov     [rsp+88h+var_68], dl; char
0x180016e8e  mov     r9d, r12d; char *
0x180016e91  mov     r8, r15; unsigned int
0x180016e94  mov     edx, 9Fh; void *
0x180016e99  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016e9e  mov     ecx, [rdi+4]
0x180016ea1  sub     ecx, 1
0x180016ea4  mov     r8, r15; unsigned int
0x180016ea7  jz      loc_18001716E
0x180016ead  sub     ecx, 1
0x180016eb0  jz      loc_180017120
0x180016eb6  sub     ecx, 1
0x180016eb9  jz      loc_1800170E1
0x180016ebf  sub     ecx, 1
0x180016ec2  jz      loc_180017072
0x180016ec8  sub     ecx, 1
0x180016ecb  jz      loc_180017017
0x180016ed1  sub     ecx, 1
0x180016ed4  jz      loc_180016FCE
0x180016eda  sub     ecx, 1
0x180016edd  mov     r9d, r13d; char *
0x180016ee0  jz      loc_180016F66
0x180016ee6  cmp     ecx, 1
0x180016ee9  mov     rcx, [rsp+88h]; this
0x180016ef1  jnz     loc_1800171B7
0x180016ef7  cmp     dword ptr [r14+4], 2
0x180016efc  setz    al
0x180016eff  lea     rdx, aContainerInfoC; "Container info cannot be updated"
0x180016f06  mov     [rsp+88h+var_60], rdx; bool
0x180016f0b  mov     [rsp+88h+var_68], al; char
0x180016f0f  mov     edx, 102h; void *
0x180016f14  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016f19  cmp     dword ptr [rdi], 20h ; ' '
0x180016f1c  setnz   al
0x180016f1f  mov     rcx, [rsp+88h]; this
0x180016f27  lea     rdx, aUnableToCastTo_2; "Unable to cast to RDPCFG_MONITORCONFIG_"...
0x180016f2e  mov     [rsp+88h+var_60], rdx; bool
0x180016f33  mov     [rsp+88h+var_68], al; char
0x180016f37  mov     r9d, r12d; char *
0x180016f3a  mov     r8, r15; unsigned int
0x180016f3d  mov     edx, 108h; void *
0x180016f42  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016f47  movups  xmm0, xmmword ptr [rdi]
0x180016f4a  movups  xmmword ptr [rbx+120h], xmm0
0x180016f51  movups  xmm1, xmmword ptr [rdi+10h]
0x180016f55  movups  xmmword ptr [rbx+130h], xmm1
0x180016f5c  bts     dword ptr [rbx+64h], 7
0x180016f61  jmp     loc_1800171A4
0x180016f66  cmp     dword ptr [r14+4], 2
0x180016f6b  setz    al
0x180016f6e  mov     rcx, [rsp+88h]; this
0x180016f76  lea     rdx, aMonitorDescrip; "Monitor description cannot be updated"
0x180016f7d  mov     [rsp+88h+var_60], rdx; bool
0x180016f82  mov     [rsp+88h+var_68], al; char
0x180016f86  mov     edx, 0F1h; void *
0x180016f8b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016f90  cmp     dword ptr [rdi], 0Ch
0x180016f93  setbe   al
0x180016f96  mov     rcx, [rsp+88h]; this
0x180016f9e  lea     rdx, aUnableToCastTo_6; "Unable to cast to RDPCFG_MONITORCONFIG_"...
0x180016fa5  mov     [rsp+88h+var_60], rdx; bool
0x180016faa  mov     [rsp+88h+var_68], al; char
0x180016fae  mov     r9d, r12d; char *
0x180016fb1  mov     r8, r15; unsigned int
0x180016fb4  mov     edx, 0F7h; void *
0x180016fb9  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016fbe  mov     rdx, rdi; struct _RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION *
0x180016fc1  mov     rcx, rbx; this
0x180016fc4  call    ?SetMonitorDescription@CMonitorConfig@Graphics@Stack@Rdp@@AEAAXAEBU_RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION@@@Z; Rdp::Stack::Graphics::CMonitorConfig::SetMonitorDescription(_RDPCFG_MONITORCONFIG_MONITOR_DESCRIPTION const &)
0x180016fc9  jmp     loc_1800171A4
0x180016fce  cmp     dword ptr [rdi], 0Ch
0x180016fd1  setnz   al
0x180016fd4  mov     rcx, [rsp+88h]; this
0x180016fdc  lea     rdx, aUnableToCastTo_1; "Unable to cast to RDPCFG_MONITORCONFIG_"...
0x180016fe3  mov     [rsp+88h+var_60], rdx; bool
0x180016fe8  mov     [rsp+88h+var_68], al; char
0x180016fec  mov     r9d, r12d; char *
0x180016fef  mov     edx, 0E6h; void *
0x180016ff4  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016ff9  movsd   xmm0, qword ptr [rdi]
0x180016ffd  movsd   qword ptr [rbx+114h], xmm0
0x180017005  mov     eax, [rdi+8]
0x180017008  mov     [rbx+11Ch], eax
0x18001700e  or      dword ptr [rbx+64h], 20h
0x180017012  jmp     loc_1800171A4
0x180017017  cmp     dword ptr [rdi], 4Ch ; 'L'
0x18001701a  setnz   al
0x18001701d  mov     rcx, [rsp+88h]; this
0x180017025  lea     rdx, aUnableToCastTo; "Unable to cast to RDPCFG_MONITORCONFIG_"...
0x18001702c  mov     [rsp+88h+var_60], rdx; bool
0x180017031  mov     [rsp+88h+var_68], al; char
0x180017035  mov     r9d, r12d; char *
0x180017038  mov     edx, 0DBh; void *
0x18001703d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180017042  movups  xmm0, xmmword ptr [rdi]
0x180017045  movups  xmmword ptr [rbp+0], xmm0
0x180017049  movups  xmm1, xmmword ptr [rdi+10h]
0x18001704d  movups  xmmword ptr [rbp+10h], xmm1
0x180017051  movups  xmm0, xmmword ptr [rdi+20h]
0x180017055  movups  xmmword ptr [rbp+20h], xmm0
0x180017059  movups  xmm1, xmmword ptr [rdi+30h]
0x18001705d  movups  xmmword ptr [rbp+30h], xmm1
0x180017061  movups  xmm0, xmmword ptr [rdi+3Ch]
0x180017065  movups  xmmword ptr [rbp+3Ch], xmm0
0x180017069  or      dword ptr [rbx+64h], 10h
0x18001706d  jmp     loc_1800171A4
0x180017072  cmp     dword ptr [r14+4], 2
0x180017077  setz    al
0x18001707a  mov     rcx, [rsp+88h]; this
0x180017082  lea     rdx, aPhysicalSizeCa; "Physical size cannot be updated"
0x180017089  mov     [rsp+88h+var_60], rdx; bool
0x18001708e  mov     [rsp+88h+var_68], al; char
0x180017092  mov     r9d, r13d; char *
0x180017095  mov     edx, 0CAh; void *
0x18001709a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001709f  cmp     dword ptr [rdi], 10h
0x1800170a2  setnz   al
0x1800170a5  mov     rcx, [rsp+88h]; this
0x1800170ad  lea     rdx, aUnableToCastTo_0; "Unable to cast to RDPCFG_MONITORCONFIG_"...
0x1800170b4  mov     [rsp+88h+var_60], rdx; bool
0x1800170b9  mov     [rsp+88h+var_68], al; char
0x1800170bd  mov     r9d, r12d; char *
0x1800170c0  mov     r8, r15; unsigned int
0x1800170c3  mov     edx, 0D0h; void *
0x1800170c8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800170cd  movups  xmm0, xmmword ptr [rdi]
0x1800170d0  movdqu  xmmword ptr [rbx+0B8h], xmm0
0x1800170d8  or      dword ptr [rbx+64h], 8
0x1800170dc  jmp     loc_1800171A4
0x1800170e1  cmp     dword ptr [rdi], 10h
0x1800170e4  setnz   al
0x1800170e7  mov     rcx, [rsp+88h]; this
0x1800170ef  lea     rdx, aUnableToCastTo_4; "Unable to cast to RDPCFG_MONITORCONFIG_"...
0x1800170f6  mov     [rsp+88h+var_60], rdx; bool
0x1800170fb  mov     [rsp+88h+var_68], al; char
0x1800170ff  mov     r9d, r12d; char *
0x180017102  mov     edx, 0BFh; void *
0x180017107  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001710c  movups  xmm0, xmmword ptr [rdi]
0x18001710f  movdqu  xmmword ptr [rbx+0A8h], xmm0
0x180017117  or      dword ptr [rbx+64h], 4
0x18001711b  jmp     loc_1800171A4
0x180017120  cmp     dword ptr [rdi], 30h ; '0'
0x180017123  setnz   al
0x180017126  mov     rcx, [rsp+88h]; this
0x18001712e  lea     rdx, aUnableToCastTo_5; "Unable to cast to RDPCFG_MONITORCONFIG_"...
0x180017135  mov     [rsp+88h+var_60], rdx; bool
0x18001713a  mov     [rsp+88h+var_68], al; char
0x18001713e  mov     r9d, r12d; char *
0x180017141  mov     edx, 0B4h; void *
0x180017146  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001714b  movups  xmm0, xmmword ptr [rdi]
0x18001714e  movups  xmmword ptr [rbx+78h], xmm0
0x180017152  movups  xmm1, xmmword ptr [rdi+10h]
0x180017156  movups  xmmword ptr [rbx+88h], xmm1
0x18001715d  movups  xmm0, xmmword ptr [rdi+20h]
0x180017161  movups  xmmword ptr [rbx+98h], xmm0
0x180017168  or      dword ptr [rbx+64h], 2
0x18001716c  jmp     short loc_1800171A4
0x18001716e  cmp     dword ptr [rdi], 2Ch ; ','
0x180017171  setnz   al
0x180017174  mov     rcx, [rsp+88h]; this
0x18001717c  lea     rdx, aUnableToCastTo_3; "Unable to cast to RDPCFG_MONITORCONFIG_"...
0x180017183  mov     [rsp+88h+var_60], rdx; char *
0x180017188  mov     [rsp+88h+var_68], al; char
0x18001718c  mov     r9d, r12d; char *
0x18001718f  mov     edx, 0A9h; void *
0x180017194  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180017199  mov     rdx, rdi; struct _RDPCFG_MONITORCONFIG_MODE *
0x18001719c  mov     rcx, rbx; this
0x18001719f  call    ?SetMode@CMonitorConfig@Graphics@Stack@Rdp@@AEAAXAEBU_RDPCFG_MONITORCONFIG_MODE@@@Z; Rdp::Stack::Graphics::CMonitorConfig::SetMode(_RDPCFG_MONITORCONFIG_MODE const &)
0x1800171a4  sub     esi, [rdi]
0x1800171a6  jz      short loc_1800171F6
0x1800171a8  cmp     esi, 8
0x1800171ab  jb      short loc_1800171CE
0x1800171ad  mov     eax, [rdi]
0x1800171af  add     rdi, rax
0x1800171b2  jmp     loc_180016E6B
0x1800171b7  lea     rax, aUnsupportedMon; "Unsupported MONITORCONFIG structure typ"...
0x1800171be  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800171c3  mov     edx, 111h; void *
0x1800171c8  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800171ce  mov     rcx, [rsp+88h]; this
0x1800171d6  lea     rax, aUnableToMoveTo; "Unable to move to next RDPCFG_MONITORCO"...
0x1800171dd  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800171e2  mov     r9d, 0C0000023h; char *
0x1800171e8  mov     r8, r15; unsigned int
0x1800171eb  mov     edx, 127h; void *
0x1800171f0  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800171f6  mov     rcx, rbx; this
0x1800171f9  call    ?ValidateAndFixMonitorConfig@CMonitorConfig@Graphics@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig(void)
0x1800171fe  nop
0x1800171ff  mov     rax, rbx
0x180017202  add     rsp, 48h
0x180017206  pop     r15
0x180017208  pop     r14
0x18001720a  pop     r13
0x18001720c  pop     r12
0x18001720e  pop     rdi
0x18001720f  pop     rsi
  ... truncated ...
```
