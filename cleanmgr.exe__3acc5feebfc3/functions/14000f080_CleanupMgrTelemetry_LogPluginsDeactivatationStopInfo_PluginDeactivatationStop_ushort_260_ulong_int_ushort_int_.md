# CleanupMgrTelemetry::LogPluginsDeactivatationStopInfo<PluginDeactivatationStop * &,ushort (&)[260],ulong &,int &,ushort,int &,int &,double &,uint &>(PluginDeactivatationStop * &,ushort (&)[260],ulong &,int &,ushort &&,int &,int &,double &,uint &)

- ea: `0x14000f080`
- end: `0x14000f14e`
- name: `??$LogPluginsDeactivatationStopInfo@AEAPEAUPluginDeactivatationStop@@AEAY0BAE@GAEAKAEAHGAEAHAEAHAEANAEAI@CleanupMgrTelemetry@@SAXAEAPEAUPluginDeactivatationStop@@AEAY0BAE@GAEAKAEAH$$QEAG33AEANAEAI@Z`
- size: `206`
- prototype: `void __fastcall(struct PluginDeactivatationStop **, const unsigned __int16 *, unsigned int *, _DWORD *, unsigned __int16 *, int *, int *, double *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140012248`
- `0x140013530`

## callees

- `0x14000f080`
- `0x14000fc94`
- `0x14000fe8c`
- `0x1400128bc`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::LogPluginsDeactivatationStopInfo<PluginDeactivatationStop * &,unsigned short (&)[260],unsigned long &,int &,unsigned short,int &,int &,double &,unsigned int &>(
        struct PluginDeactivatationStop **a1,
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
    CleanupMgrTelemetry::LogPluginsDeactivatationStopInfo_(
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
0x14000f080  push    rbx
0x14000f082  push    rsi
0x14000f083  push    rdi
0x14000f084  push    r14
0x14000f086  sub     rsp, 58h
0x14000f08a  mov     rbx, r9
0x14000f08d  mov     rdi, r8
0x14000f090  mov     rsi, rdx
0x14000f093  mov     r14, rcx
0x14000f096  call    ?IsEnabled@CleanupMgrTelemetry@@SA_NE_K@Z; CleanupMgrTelemetry::IsEnabled(uchar,unsigned __int64)
0x14000f09b  test    al, al
0x14000f09d  jz      loc_14000F144
0x14000f0a3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8fbe5f91c6458a74708d73c673943f43_@@CA@XZ; _lambda_8fbe5f91c6458a74708d73c673943f43_::_lambda_invoker_cdecl_(void)
0x14000f0aa  call    ?get@?$static_lazy@VCleanupMgrTelemetry@@@details@wil@@QEAAPEAVCleanupMgrTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CleanupMgrTelemetry>::get(void (*)(void))
0x14000f0af  mov     rax, [rsp+78h+arg_38]
0x14000f0b7  xor     r10d, r10d
0x14000f0ba  movsd   xmm1, cs:__real@43e0000000000000
0x14000f0c2  movsd   xmm0, qword ptr [rax]
0x14000f0c6  comisd  xmm0, xmm1
0x14000f0ca  jb      short loc_14000F0E3
0x14000f0cc  subsd   xmm0, xmm1
0x14000f0d0  comisd  xmm0, xmm1
0x14000f0d4  jnb     short loc_14000F0E3
0x14000f0d6  mov     rax, 8000000000000000h
0x14000f0e0  mov     r10, rax
0x14000f0e3  mov     rax, [rsp+78h+arg_40]
0x14000f0eb  mov     r9d, [rdi]; unsigned int
0x14000f0ee  cvttsd2si rdx, xmm0
0x14000f0f3  mov     ecx, [rax]
0x14000f0f5  mov     rax, [rsp+78h+arg_30]
0x14000f0fd  mov     [rsp+78h+var_30], ecx; unsigned int
0x14000f101  mov     ecx, [rax]
0x14000f103  mov     rax, [rsp+78h+arg_28]
0x14000f10b  add     rdx, r10
0x14000f10e  cmp     dword ptr [rbx], 0
0x14000f111  mov     [rsp+78h+var_38], rdx; unsigned __int64
0x14000f116  mov     rdx, [r14]; struct PluginDeactivatationStop *
0x14000f119  setnz   r8b
0x14000f11d  mov     [rsp+78h+var_40], ecx; int
0x14000f121  mov     ecx, [rax]
0x14000f123  mov     rax, [rsp+78h+arg_20]
0x14000f12b  mov     [rsp+78h+var_48], ecx; int
0x14000f12f  movzx   ecx, word ptr [rax]; this
0x14000f132  mov     [rsp+78h+var_50], cx; unsigned __int16
0x14000f137  mov     [rsp+78h+var_58], r8b; bool
0x14000f13c  mov     r8, rsi; unsigned __int16 *
0x14000f13f  call    ?LogPluginsDeactivatationStopInfo_@CleanupMgrTelemetry@@QEAAXPEAUPluginDeactivatationStop@@PEBGK_NGHH_KI@Z; CleanupMgrTelemetry::LogPluginsDeactivatationStopInfo_(PluginDeactivatationStop *,ushort const *,ulong,bool,ushort,int,int,unsigned __int64,uint)
0x14000f144  add     rsp, 58h
0x14000f148  pop     r14
0x14000f14a  pop     rdi
0x14000f14b  pop     rsi
0x14000f14c  pop     rbx
0x14000f14d  retn
```
