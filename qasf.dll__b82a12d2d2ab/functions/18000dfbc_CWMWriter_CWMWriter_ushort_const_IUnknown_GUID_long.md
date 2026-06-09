# CWMWriter::CWMWriter(ushort const *,IUnknown *,_GUID,long *)

- ea: `0x18000dfbc`
- end: `0x18000e1f8`
- name: `??0CWMWriter@@QEAA@PEBGPEAUIUnknown@@U_GUID@@PEAJ@Z`
- size: `572`
- prototype: `CWMWriter *__fastcall(CWMWriter *__hidden this, const unsigned __int16 *, struct IUnknown *, struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000f3c0`

## callees

- `0x18000dfbc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000e0e6`
- `KERNEL32!InitializeCriticalSection` at `0x18000e0e6`

## pseudocode

```c
CWMWriter *__fastcall CWMWriter::CWMWriter(
        CWMWriter *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        struct _GUID *a4,
        int *a5)
{
  __int128 v6; // xmm0
  struct _RTL_CRITICAL_SECTION *v7; // rcx

  _InterlockedAdd(&CBaseObject::m_cObjects, 1u);
  v6 = (__int128)*a4;
  *((_QWORD *)this + 7) = 0;
  *(_QWORD *)this = &CWMWriter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CWMWriter::`vftable'{for `IBaseFilter'};
  if ( !a3 )
    a3 = (struct IUnknown *)this;
  *((_QWORD *)this + 1) = a3;
  *((_QWORD *)this + 4) = &CMediaWrapperFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 15) = &CWMWriter::`vftable'{for `IMediaSeeking'};
  *((_QWORD *)this + 16) = &CWMWriter::`vftable'{for `IAMFilterMiscFlags'};
  *((_QWORD *)this + 17) = &CWMWriter::`vftable'{for `IFileSinkFilter2'};
  *((_QWORD *)this + 18) = &CWMWriter::`vftable'{for `ISpecifyPropertyPages'};
  *((_QWORD *)this + 19) = &CWMWriter::`vftable'{for `IConfigAsfWriter2'};
  *((_QWORD *)this + 20) = &CWMWriter::`vftable'{for `CPersistStream'};
  *((_QWORD *)this + 22) = &CWMWriter::`vftable'{for `IWMHeaderInfo'};
  *((_QWORD *)this + 23) = &CWMWriter::`vftable'{for `IServiceProvider'};
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_OWORD *)this + 4) = v6;
  *((_QWORD *)this + 24) = &CWMWriter::`vftable'{for `IWMWriterPreprocess'};
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 240);
  *((_QWORD *)this + 10) = v7;
  *((_QWORD *)this + 25) = &CWMWriter::`vftable'{for `IWMStatusCallback'};
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 1;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_DWORD *)this + 53) = 1;
  *((_DWORD *)this + 54) = 1;
  *((_DWORD *)this + 55) = 1;
  *((_DWORD *)this + 58) = 0;
  InitializeCriticalSection(v7);
  *((_DWORD *)this + 70) = 0;
  *((_QWORD *)this + 36) = 0;
  *(IID *)((char *)this + 364) = WMProfile_V80_256Video;
  *(_QWORD *)((char *)this + 300) = 0;
  *((_DWORD *)this + 77) = 1;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_DWORD *)this + 90) = -1;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_DWORD *)this + 106) = 0;
  *((_QWORD *)this + 54) = 10;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_DWORD *)this + 116) = 0;
  *((_QWORD *)this + 59) = 10;
  *((_QWORD *)this + 60) = 0;
  *((_DWORD *)this + 95) = 1;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  if ( *a5 >= 0 )
    *((_QWORD *)this + 28) = 0;
  return this;
}

```

## disassembly

```asm
0x18000dfbc  mov     [rsp+arg_0], rbx
0x18000dfc1  mov     [rsp+arg_8], rsi
0x18000dfc6  push    rdi
0x18000dfc7  sub     rsp, 20h
0x18000dfcb  mov     rbx, rcx
0x18000dfce  mov     edi, 1
0x18000dfd3  lock add cs:?m_cObjects@CBaseObject@@0JA, edi; long CBaseObject::m_cObjects
0x18000dfda  movups  xmm0, xmmword ptr [r9]
0x18000dfde  xor     esi, esi
0x18000dfe0  lea     rax, ??_7CWMWriter@@6BCUnknown@@@; const CWMWriter::`vftable'{for `CUnknown'}
0x18000dfe7  mov     [rcx+38h], rsi
0x18000dfeb  test    r8, r8
0x18000dfee  mov     [rbx], rax
0x18000dff1  lea     rax, ??_7CWMWriter@@6BIBaseFilter@@@; const CWMWriter::`vftable'{for `IBaseFilter'}
0x18000dff8  mov     [rbx+18h], rax
0x18000dffc  cmovz   r8, rcx
0x18000e000  mov     [rcx+8], r8
0x18000e004  lea     rax, ??_7CMediaWrapperFilter@@6BIAMovieSetup@@@; const CMediaWrapperFilter::`vftable'{for `IAMovieSetup'}
0x18000e00b  mov     [rbx+20h], rax
0x18000e00f  lea     rax, ??_7CWMWriter@@6BIMediaSeeking@@@; const CWMWriter::`vftable'{for `IMediaSeeking'}
0x18000e016  mov     [rbx+78h], rax
0x18000e01a  lea     rax, ??_7CWMWriter@@6BIAMFilterMiscFlags@@@; const CWMWriter::`vftable'{for `IAMFilterMiscFlags'}
0x18000e021  mov     [rbx+80h], rax
0x18000e028  lea     rax, ??_7CWMWriter@@6BIFileSinkFilter2@@@; const CWMWriter::`vftable'{for `IFileSinkFilter2'}
0x18000e02f  mov     [rbx+88h], rax
0x18000e036  lea     rax, ??_7CWMWriter@@6BISpecifyPropertyPages@@@; const CWMWriter::`vftable'{for `ISpecifyPropertyPages'}
0x18000e03d  mov     [rbx+90h], rax
0x18000e044  lea     rax, ??_7CWMWriter@@6BIConfigAsfWriter2@@@; const CWMWriter::`vftable'{for `IConfigAsfWriter2'}
0x18000e04b  mov     [rbx+98h], rax
0x18000e052  lea     rax, ??_7CWMWriter@@6BCPersistStream@@@; const CWMWriter::`vftable'{for `CPersistStream'}
0x18000e059  mov     [rbx+0A0h], rax
0x18000e060  lea     rax, ??_7CWMWriter@@6BIWMHeaderInfo@@@; const CWMWriter::`vftable'{for `IWMHeaderInfo'}
0x18000e067  mov     [rbx+0B0h], rax
0x18000e06e  lea     rax, ??_7CWMWriter@@6BIServiceProvider@@@; const CWMWriter::`vftable'{for `IServiceProvider'}
0x18000e075  mov     [rbx+0B8h], rax
0x18000e07c  lea     rax, ??_7CWMWriter@@6BIWMWriterPreprocess@@@; const CWMWriter::`vftable'{for `IWMWriterPreprocess'}
0x18000e083  mov     [rcx+10h], esi
0x18000e086  mov     [rcx+28h], esi
0x18000e089  mov     [rcx+30h], rsi
0x18000e08d  movdqu  xmmword ptr [rcx+40h], xmm0
0x18000e092  mov     [rbx+0C0h], rax
0x18000e099  add     rcx, 0F0h; lpCriticalSection
0x18000e0a0  lea     rax, ??_7CWMWriter@@6BIWMStatusCallback@@@; const CWMWriter::`vftable'{for `IWMStatusCallback'}
0x18000e0a7  mov     [rbx+50h], rcx
0x18000e0ab  mov     [rbx+0C8h], rax
0x18000e0b2  mov     [rbx+58h], rsi
0x18000e0b6  mov     [rbx+60h], rsi
0x18000e0ba  mov     [rbx+68h], rsi
0x18000e0be  mov     [rbx+70h], edi
0x18000e0c1  mov     [rbx+0A8h], rsi
0x18000e0c8  mov     [rbx+0D0h], esi
0x18000e0ce  mov     [rbx+0D4h], edi
0x18000e0d4  mov     [rbx+0D8h], edi
0x18000e0da  mov     [rbx+0DCh], edi
0x18000e0e0  mov     [rbx+0E8h], esi
0x18000e0e6  call    cs:__imp_InitializeCriticalSection
0x18000e0ec  movups  xmm0, xmmword ptr cs:WMProfile_V80_256Video.Data1
0x18000e0f3  mov     [rbx+118h], esi
0x18000e0f9  mov     [rbx+120h], rsi
0x18000e100  movdqu  xmmword ptr [rbx+16Ch], xmm0
0x18000e108  mov     [rbx+12Ch], rsi
0x18000e10f  mov     [rbx+134h], edi
0x18000e115  mov     [rbx+138h], rsi
0x18000e11c  mov     [rbx+140h], rsi
0x18000e123  mov     [rbx+148h], rsi
0x18000e12a  mov     [rbx+150h], rsi
0x18000e131  mov     [rbx+158h], rsi
0x18000e138  mov     [rbx+160h], rsi
0x18000e13f  mov     dword ptr [rbx+168h], 0FFFFFFFFh
0x18000e149  mov     [rbx+198h], rsi
0x18000e150  mov     [rbx+1A0h], rsi
0x18000e157  mov     [rbx+1A8h], esi
0x18000e15d  mov     qword ptr [rbx+1B0h], 0Ah
0x18000e168  mov     [rbx+1B8h], rsi
0x18000e16f  mov     [rbx+1C0h], rsi
0x18000e176  mov     [rbx+1C8h], rsi
0x18000e17d  mov     [rbx+1D0h], esi
0x18000e183  mov     qword ptr [rbx+1D8h], 0Ah
0x18000e18e  mov     [rbx+1E0h], rsi
0x18000e195  mov     [rbx+17Ch], edi
0x18000e19b  mov     [rbx+180h], rsi
0x18000e1a2  mov     [rbx+188h], rsi
0x18000e1a9  mov     [rbx+190h], rsi
0x18000e1b0  mov     [rbx+1E8h], rsi
0x18000e1b7  mov     [rbx+1F0h], rsi
0x18000e1be  mov     [rbx+1F8h], rsi
0x18000e1c5  mov     [rbx+200h], rsi
0x18000e1cc  mov     [rbx+208h], rsi
0x18000e1d3  mov     rax, [rsp+28h+arg_20]
0x18000e1d8  cmp     [rax], esi
0x18000e1da  jl      short loc_18000E1E5
0x18000e1dc  xor     eax, eax
0x18000e1de  mov     [rbx+0E0h], rax
0x18000e1e5  mov     rsi, [rsp+28h+arg_8]
0x18000e1ea  mov     rax, rbx
0x18000e1ed  mov     rbx, [rsp+28h+arg_0]
0x18000e1f2  add     rsp, 20h
0x18000e1f6  pop     rdi
0x18000e1f7  retn
```
