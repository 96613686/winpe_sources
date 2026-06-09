# CleanupMgrTelemetry::LogPluginsDeactivatationStartInfo<PluginDeactivatationStart * &,ushort (&)[260],ulong &,int &,ushort,int &,int &,double &,uint &>(PluginDeactivatationStart * &,ushort (&)[260],ulong &,int &,ushort &&,int &,int &,double &,uint &)

- ea: `0x14000efac`
- end: `0x14000f07a`
- name: `??$LogPluginsDeactivatationStartInfo@AEAPEAUPluginDeactivatationStart@@AEAY0BAE@GAEAKAEAHGAEAHAEAHAEANAEAI@CleanupMgrTelemetry@@SAXAEAPEAUPluginDeactivatationStart@@AEAY0BAE@GAEAKAEAH$$QEAG33AEANAEAI@Z`
- size: `206`
- prototype: `void __fastcall(struct PluginDeactivatationStart **, const unsigned __int16 *, unsigned int *, _DWORD *, unsigned __int16 *, int *, int *, double *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140012248`
- `0x140013530`

## callees

- `0x14000efac`
- `0x14000fc94`
- `0x14000fd68`
- `0x1400128bc`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::LogPluginsDeactivatationStartInfo<PluginDeactivatationStart * &,unsigned short (&)[260],unsigned long &,int &,unsigned short,int &,int &,double &,unsigned int &>(
        struct PluginDeactivatationStart **a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        _DWORD *a4,
        unsigned __int16 *a5,
        int *a6,
        int *a7,
        double *a8,
        unsigned int *a9)
{
  __int64 v13; // rcx
  unsigned __int64 v14; // r10
  double v15; // xmm0_8

  if ( CleanupMgrTelemetry::IsEnabled((unsigned __int8)a1, (unsigned __int64)a2) )
  {
    wil::details::static_lazy<CleanupMgrTelemetry>::get(
      v13,
      _lambda_8fbe5f91c6458a74708d73c673943f43_::_lambda_invoker_cdecl_);
    v14 = 0;
    v15 = *a8;
    if ( *a8 >= 9.223372036854776e18 )
    {
      v15 = v15 - 9.223372036854776e18;
      if ( v15 < 9.223372036854776e18 )
        v14 = 0x8000000000000000uLL;
    }
    CleanupMgrTelemetry::LogPluginsDeactivatationStartInfo_(
      (CleanupMgrTelemetry *)*a5,
      *a1,
      a2,
      *a3,
      *a4 != 0,
      *a5,
      *a6,
      *a7,
      v14 + (unsigned int)(int)v15,
      *a9);
  }
}

```

## disassembly

```asm
0x14000efac  push    rbx
0x14000efae  push    rsi
0x14000efaf  push    rdi
0x14000efb0  push    r14
0x14000efb2  sub     rsp, 58h
0x14000efb6  mov     rbx, r9
0x14000efb9  mov     rdi, r8
0x14000efbc  mov     rsi, rdx
0x14000efbf  mov     r14, rcx
0x14000efc2  call    ?IsEnabled@CleanupMgrTelemetry@@SA_NE_K@Z; CleanupMgrTelemetry::IsEnabled(uchar,unsigned __int64)
0x14000efc7  test    al, al
0x14000efc9  jz      loc_14000F070
0x14000efcf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8fbe5f91c6458a74708d73c673943f43_@@CA@XZ; _lambda_8fbe5f91c6458a74708d73c673943f43_::_lambda_invoker_cdecl_(void)
0x14000efd6  call    ?get@?$static_lazy@VCleanupMgrTelemetry@@@details@wil@@QEAAPEAVCleanupMgrTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CleanupMgrTelemetry>::get(void (*)(void))
0x14000efdb  mov     rax, [rsp+78h+arg_38]
0x14000efe3  xor     r10d, r10d
0x14000efe6  movsd   xmm1, cs:__real@43e0000000000000
0x14000efee  movsd   xmm0, qword ptr [rax]
0x14000eff2  comisd  xmm0, xmm1
0x14000eff6  jb      short loc_14000F00F
0x14000eff8  subsd   xmm0, xmm1
0x14000effc  comisd  xmm0, xmm1
0x14000f000  jnb     short loc_14000F00F
0x14000f002  mov     rax, 8000000000000000h
0x14000f00c  mov     r10, rax
0x14000f00f  mov     rax, [rsp+78h+arg_40]
0x14000f017  mov     r9d, [rdi]; unsigned int
0x14000f01a  cvttsd2si rdx, xmm0
0x14000f01f  mov     ecx, [rax]
0x14000f021  mov     rax, [rsp+78h+arg_30]
0x14000f029  mov     [rsp+78h+var_30], ecx; unsigned int
0x14000f02d  mov     ecx, [rax]
0x14000f02f  mov     rax, [rsp+78h+arg_28]
0x14000f037  add     rdx, r10
0x14000f03a  cmp     dword ptr [rbx], 0
0x14000f03d  mov     [rsp+78h+var_38], rdx; unsigned __int64
0x14000f042  mov     rdx, [r14]; struct PluginDeactivatationStart *
0x14000f045  setnz   r8b
0x14000f049  mov     [rsp+78h+var_40], ecx; int
0x14000f04d  mov     ecx, [rax]
0x14000f04f  mov     rax, [rsp+78h+arg_20]
0x14000f057  mov     [rsp+78h+var_48], ecx; int
0x14000f05b  movzx   ecx, word ptr [rax]; this
0x14000f05e  mov     [rsp+78h+var_50], cx; unsigned __int16
0x14000f063  mov     [rsp+78h+var_58], r8b; bool
0x14000f068  mov     r8, rsi; unsigned __int16 *
0x14000f06b  call    ?LogPluginsDeactivatationStartInfo_@CleanupMgrTelemetry@@QEAAXPEAUPluginDeactivatationStart@@PEBGK_NGHH_KI@Z; CleanupMgrTelemetry::LogPluginsDeactivatationStartInfo_(PluginDeactivatationStart *,ushort const *,ulong,bool,ushort,int,int,unsigned __int64,uint)
0x14000f070  add     rsp, 58h
0x14000f074  pop     r14
0x14000f076  pop     rdi
0x14000f077  pop     rsi
0x14000f078  pop     rbx
0x14000f079  retn
```
