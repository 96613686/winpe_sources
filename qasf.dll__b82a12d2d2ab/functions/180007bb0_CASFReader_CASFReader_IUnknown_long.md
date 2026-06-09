# CASFReader::CASFReader(IUnknown *,long *)

- ea: `0x180007bb0`
- end: `0x180007e0e`
- name: `??0CASFReader@@QEAA@PEAUIUnknown@@PEAJ@Z`
- size: `606`
- prototype: `CASFReader *__fastcall(CASFReader *__hidden this, struct IUnknown *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800090f0`

## callees

- `0x180001020`
- `0x18000770c`
- `0x180007bb0`
- `0x18001f010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180007c74`
- `KERNEL32!InitializeCriticalSection` at `0x180007c81`
- `KERNEL32!InitializeCriticalSection` at `0x180007c74`
- `KERNEL32!InitializeCriticalSection` at `0x180007c81`

## pseudocode

```c
CASFReader *__fastcall CASFReader::CASFReader(CASFReader *this, struct IUnknown *a2, int *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rcx

  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 10) = 0;
  if ( !a2 )
    a2 = (struct IUnknown *)this;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = a2;
  *((_DWORD *)this + 4) = 0;
  *(_QWORD *)this = &CASFReader::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CASFReader::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CMediaWrapperFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 15) = &CASFReader::`vftable'{for `IFileSourceFilter'};
  *((_QWORD *)this + 16) = &CASFReader::`vftable'{for `IAMExtendedSeeking'};
  *((_QWORD *)this + 17) = &CASFReader::`vftable'{for `IWMHeaderInfo'};
  *((_QWORD *)this + 18) = &CASFReader::`vftable'{for `IWMReaderAdvanced2'};
  *((GUID *)this + 4) = CLSID_WMAsfReader;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 160);
  *((_QWORD *)this + 19) = &CASFReader::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 10) = v5;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 1;
  InitializeCriticalSection(v5);
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 5);
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_DWORD *)this + 74) = 0;
  *((_QWORD *)this + 38) = 10;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 31) = 0x3FF0000000000000LL;
  *((_QWORD *)this + 30) = 0;
  *((_DWORD *)this + 80) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 84) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 98) = 0;
  *((_QWORD *)this + 50) = 0;
  CAMEvent::CAMEvent((CASFReader *)((char *)this + 408), 0, 0);
  *((_DWORD *)this + 104) = 0;
  CAMEvent::CAMEvent((CASFReader *)((char *)this + 424), 0, 0);
  CAMEvent::CAMEvent((CASFReader *)((char *)this + 432), 1, 0);
  *((_DWORD *)this + 111) = -1;
  *((_QWORD *)this + 56) = 0;
  *((_DWORD *)this + 114) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  v6 = operator new(0x30u);
  v7 = v6;
  if ( v6 )
  {
    _InterlockedIncrement(&CBaseObject::m_cObjects);
    v6[1] = v6;
    *((_DWORD *)v6 + 4) = 0;
    *v6 = &CASFReaderCallback::`vftable'{for `CUnknown'};
    v6[3] = &CASFReaderCallback::`vftable'{for `IWMReaderCallback'};
    v6[4] = &CASFReaderCallback::`vftable'{for `IWMReaderCallbackAdvanced'};
    v6[5] = this;
  }
  else
  {
    v7 = 0;
  }
  v8 = (unsigned __int64)(v7 + 3) & -(__int64)(v7 != 0);
  *((_QWORD *)this + 47) = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  else
    *a3 = -2147024882;
  return this;
}

```

## disassembly

```asm
0x180007bb0  mov     [rsp+arg_0], rbx
0x180007bb5  mov     [rsp+arg_8], rsi
0x180007bba  push    rdi
0x180007bbb  sub     rsp, 20h
0x180007bbf  mov     rdi, r8
0x180007bc2  mov     rbx, rcx
0x180007bc5  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180007bcc  xor     esi, esi
0x180007bce  lea     rax, ??_7CASFReader@@6BCUnknown@@@; const CASFReader::`vftable'{for `CUnknown'}
0x180007bd5  mov     [rcx+38h], rsi
0x180007bd9  test    rdx, rdx
0x180007bdc  mov     [rcx+28h], esi
0x180007bdf  cmovz   rdx, rcx
0x180007be3  mov     [rcx+30h], rsi
0x180007be7  mov     [rcx+8], rdx
0x180007beb  mov     [rcx+10h], esi
0x180007bee  movups  xmm0, xmmword ptr cs:CLSID_WMAsfReader.Data1
0x180007bf5  mov     [rbx], rax
0x180007bf8  lea     rax, ??_7CASFReader@@6BIBaseFilter@@@; const CASFReader::`vftable'{for `IBaseFilter'}
0x180007bff  mov     [rbx+18h], rax
0x180007c03  lea     rax, ??_7CMediaWrapperFilter@@6BIAMovieSetup@@@; const CMediaWrapperFilter::`vftable'{for `IAMovieSetup'}
0x180007c0a  mov     [rbx+20h], rax
0x180007c0e  lea     rax, ??_7CASFReader@@6BIFileSourceFilter@@@; const CASFReader::`vftable'{for `IFileSourceFilter'}
0x180007c15  mov     [rbx+78h], rax
0x180007c19  lea     rax, ??_7CASFReader@@6BIAMExtendedSeeking@@@; const CASFReader::`vftable'{for `IAMExtendedSeeking'}
0x180007c20  mov     [rbx+80h], rax
0x180007c27  lea     rax, ??_7CASFReader@@6BIWMHeaderInfo@@@; const CASFReader::`vftable'{for `IWMHeaderInfo'}
0x180007c2e  mov     [rbx+88h], rax
0x180007c35  lea     rax, ??_7CASFReader@@6BIWMReaderAdvanced2@@@; const CASFReader::`vftable'{for `IWMReaderAdvanced2'}
0x180007c3c  mov     [rbx+90h], rax
0x180007c43  lea     rax, ??_7CASFReader@@6BIServiceProvider@@@; const CASFReader::`vftable'{for `IServiceProvider'}
0x180007c4a  movdqu  xmmword ptr [rcx+40h], xmm0
0x180007c4f  add     rcx, 0A0h; lpCriticalSection
0x180007c56  mov     [rbx+98h], rax
0x180007c5d  mov     [rbx+50h], rcx
0x180007c61  mov     [rbx+58h], rsi
0x180007c65  mov     [rbx+60h], rsi
0x180007c69  mov     [rbx+68h], rsi
0x180007c6d  mov     dword ptr [rbx+70h], 1
0x180007c74  call    cs:__imp_InitializeCriticalSection
0x180007c7a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180007c81  call    cs:__imp_InitializeCriticalSection
0x180007c87  mov     rax, 3FF0000000000000h
0x180007c91  mov     [rbx+100h], rsi
0x180007c98  mov     [rbx+108h], rsi
0x180007c9f  lea     rcx, [rbx+198h]; this
0x180007ca6  mov     [rbx+118h], rsi
0x180007cad  xor     r8d, r8d; int *
0x180007cb0  mov     [rbx+120h], rsi
0x180007cb7  xor     edx, edx; int
0x180007cb9  mov     [rbx+128h], esi
0x180007cbf  mov     qword ptr [rbx+130h], 0Ah
0x180007cca  mov     [rbx+138h], rsi
0x180007cd1  mov     [rbx+0F8h], rax
0x180007cd8  mov     [rbx+0F0h], rsi
0x180007cdf  mov     [rbx+140h], esi
0x180007ce5  mov     [rbx+148h], rsi
0x180007cec  mov     [rbx+150h], esi
0x180007cf2  mov     [rbx+158h], rsi
0x180007cf9  mov     [rbx+160h], rsi
0x180007d00  mov     [rbx+168h], rsi
0x180007d07  mov     [rbx+170h], rsi
0x180007d0e  mov     [rbx+178h], rsi
0x180007d15  mov     [rbx+180h], rsi
0x180007d1c  mov     [rbx+188h], esi
0x180007d22  mov     [rbx+190h], rsi
0x180007d29  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x180007d2e  lea     rcx, [rbx+1A8h]; this
0x180007d35  mov     [rbx+1A0h], esi
0x180007d3b  xor     r8d, r8d; int *
0x180007d3e  xor     edx, edx; int
0x180007d40  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x180007d45  lea     rcx, [rbx+1B0h]; this
0x180007d4c  xor     r8d, r8d; int *
0x180007d4f  lea     edx, [rsi+1]; int
0x180007d52  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x180007d57  lea     ecx, [rsi+30h]; Size
0x180007d5a  mov     dword ptr [rbx+1BCh], 0FFFFFFFFh
0x180007d64  mov     [rbx+1C0h], rsi
0x180007d6b  mov     [rbx+1C8h], esi
0x180007d71  mov     [rbx+1D0h], rsi
0x180007d78  mov     [rbx+1D8h], rsi
0x180007d7f  mov     [rbx+1E0h], rsi
0x180007d86  mov     [rbx+1E8h], rsi
0x180007d8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007d92  mov     rcx, rax
0x180007d95  test    rax, rax
0x180007d98  jz      short loc_180007DCE
0x180007d9a  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180007da1  mov     [rax+8], rax
0x180007da5  mov     [rax+10h], esi
0x180007da8  lea     rax, ??_7CASFReaderCallback@@6BCUnknown@@@; const CASFReaderCallback::`vftable'{for `CUnknown'}
0x180007daf  mov     [rcx], rax
0x180007db2  lea     rax, ??_7CASFReaderCallback@@6BIWMReaderCallback@@@; const CASFReaderCallback::`vftable'{for `IWMReaderCallback'}
0x180007db9  mov     [rcx+18h], rax
0x180007dbd  lea     rax, ??_7CASFReaderCallback@@6BIWMReaderCallbackAdvanced@@@; const CASFReaderCallback::`vftable'{for `IWMReaderCallbackAdvanced'}
0x180007dc4  mov     [rcx+20h], rax
0x180007dc8  mov     [rcx+28h], rbx
0x180007dcc  jmp     short loc_180007DD1
0x180007dce  mov     rcx, rsi
0x180007dd1  lea     rax, [rcx+18h]
0x180007dd5  neg     rcx
0x180007dd8  sbb     rcx, rcx
0x180007ddb  and     rcx, rax
0x180007dde  mov     [rbx+178h], rcx
0x180007de5  jnz     short loc_180007DEF
0x180007de7  mov     dword ptr [rdi], 8007000Eh
0x180007ded  jmp     short loc_180007DFB
0x180007def  mov     rax, [rcx]
0x180007df2  mov     rax, [rax+8]
0x180007df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dfb  mov     rsi, [rsp+28h+arg_8]
0x180007e00  mov     rax, rbx
0x180007e03  mov     rbx, [rsp+28h+arg_0]
0x180007e08  add     rsp, 20h
0x180007e0c  pop     rdi
0x180007e0d  retn
```
