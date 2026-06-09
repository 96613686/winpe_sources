# PerfDiagDm::GetRundownPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,void *)

- ea: `0x1800335b8`
- end: `0x180033907`
- name: `?GetRundownPath@PerfDiagDm@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAX@Z`
- size: `847`
- prototype: `__int64 __fastcall(const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ae878`

## callees

- `0x180016988`
- `0x18001769c`
- `0x18001890c`
- `0x180019370`
- `0x18001a598`
- `0x18002b1b0`
- `0x1800335b8`
- `0x180033a00`
- `0x1800442ec`
- `0x1800ae71c`
- `0x1800aed70`
- `0x1800cf032`

## import_xrefs

- `msvcrt!malloc` at `0x180033685`
- `msvcrt!malloc` at `0x180033685`
- `msvcrt!free` at `0x18003369b`
- `msvcrt!free` at `0x180033768`
- `msvcrt!free` at `0x1800337a7`
- `msvcrt!free` at `0x180033808`
- `msvcrt!free` at `0x18003387c`
- `msvcrt!free` at `0x1800338b7`
- `msvcrt!free` at `0x1800338d9`
- `msvcrt!free` at `0x18003369b`
- `msvcrt!free` at `0x180033768`
- `msvcrt!free` at `0x1800337a7`
- `msvcrt!free` at `0x180033808`
- `msvcrt!free` at `0x18003387c`
- `msvcrt!free` at `0x1800338b7`
- `msvcrt!free` at `0x1800338d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033660`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033660`
- `ADVAPI32!EnableTrace` at `0x18003383a`
- `ADVAPI32!EnableTrace` at `0x18003383a`
- `ADVAPI32!StartTraceW` at `0x1800337e3`
- `ADVAPI32!StartTraceW` at `0x1800337e3`
- `ADVAPI32!ControlTraceW` at `0x180033854`
- `ADVAPI32!ControlTraceW` at `0x180033854`
- `wdi!WdiGetInstanceFilePath` at `0x1800335dd`
- `wdi!WdiGetInstanceFilePath` at `0x180033616`
- `wdi!WdiGetInstanceFilePath` at `0x1800335dd`
- `wdi!WdiGetInstanceFilePath` at `0x180033616`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PerfDiagDm::GetRundownPath(const unsigned __int16 **a1, __int64 a2)
{
  __int64 result; // rax
  __int64 BufferSetLength; // rax
  DWORD CurrentThreadId; // eax
  char *v7; // rax
  char *v8; // rbx
  int v9; // esi
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  int v12; // edi
  const WCHAR *v13; // rdi
  int v14; // esi
  signed int started; // eax
  unsigned int v16; // esi
  signed int v17; // r14d
  signed int v18; // eax
  ULONG64 TraceHandle[2]; // [rsp+30h] [rbp-48h] BYREF
  ATL::CAtlException *v20; // [rsp+40h] [rbp-38h] BYREF
  void **v21; // [rsp+48h] [rbp-30h] BYREF
  int v22; // [rsp+50h] [rbp-28h]
  int v23; // [rsp+54h] [rbp-24h]
  int v24; // [rsp+58h] [rbp-20h]
  int v25; // [rsp+90h] [rbp+18h] BYREF
  LPCWSTR InstanceName; // [rsp+98h] [rbp+20h] BYREF

  v25 = 0;
  result = WdiGetInstanceFilePath(a2, 0, &v25);
  if ( (int)result < 0 )
    return result;
  if ( !v25 )
    return 2147500037LL;
  try
  {
    BufferSetLength = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength();
    result = WdiGetInstanceFilePath(a2, BufferSetLength, &v25);
    if ( (int)result >= 0 )
    {
      if ( !v25 )
        return 2147500037LL;
      ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)(v25 - 1));
      ATL::CSimpleStringT<unsigned short,0>::Append(a1, L"\\krundown.etl");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&InstanceName);
      CurrentThreadId = GetCurrentThreadId();
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &InstanceName,
        L"ckclrundown_%x",
        CurrentThreadId);
      v7 = (char *)malloc(0x488u);
      v8 = v7;
      TraceHandle[1] = (ULONG64)v7;
      if ( !v7 )
      {
        free(0);
        ATL::CStringData::Release((ATL::CStringData *)(InstanceName - 12));
        return 2147942414LL;
      }
      memset_0(v7, 0, 0x488u);
      *(_DWORD *)v8 = 1160;
      *((_DWORD *)v8 + 11) = 0x20000;
      *(_OWORD *)(v8 + 24) = CKCLRundownLoggerGuid;
      *((_DWORD *)v8 + 10) = 1;
      *((_DWORD *)v8 + 16) |= 0x80u;
      *((_DWORD *)v8 + 28) = 120;
      *((_DWORD *)v8 + 29) = 640;
      v21 = &PerfDiagDm::CKernelRundownBufferConfig::`vftable';
      v9 = 64;
      v22 = 64;
      v23 = 16;
      v24 = 256;
      if ( (int)Performance::RegistryTransferable<PerfDiagDm::CKernelRundownBufferConfig>::readWriteImpl(&v21, 0) >= 0 )
      {
        v9 = v22;
      }
      else
      {
        v23 = 16;
        v24 = 256;
      }
      *((_DWORD *)v8 + 12) = v9;
      *((_DWORD *)v8 + 13) = v23;
      *((_DWORD *)v8 + 14) = v24;
      v12 = StringCbCopyW((unsigned __int16 *)v8 + 60, v10, *a1);
      if ( v12 < 0 )
      {
        free(v8);
        ATL::CStringData::Release((ATL::CStringData *)(InstanceName - 12));
        return (unsigned int)v12;
      }
      v13 = InstanceName;
      v14 = StringCbCopyW((unsigned __int16 *)v8 + 320, v11, InstanceName);
      if ( v14 < 0 )
      {
        free(v8);
        ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
        return (unsigned int)v14;
      }
      ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
        &v21,
        PerfDiagDm::g_spCKCLRundownCriticalSection);
      TraceHandle[0] = 0;
      started = StartTraceW(TraceHandle, v13, (PEVENT_TRACE_PROPERTIES)v8);
      v16 = started;
      if ( started )
      {
        if ( started > 0 )
          v16 = (unsigned __int16)started | 0x80070000;
LABEL_19:
        ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v21);
        free(v8);
        ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
        return v16;
      }
      v17 = EnableTrace(1u, 8u, 0, &KernelRundownGuid, TraceHandle[0]);
      v18 = ControlTraceW(TraceHandle[0], v13, (PEVENT_TRACE_PROPERTIES)v8, 1u);
      v16 = v18;
      if ( v17 )
      {
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v21);
        free(v8);
        ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
        return (unsigned int)v17;
      }
      if ( v18 && v18 != 234 )
      {
        if ( v18 > 0 )
          v16 = (unsigned __int16)v18 | 0x80070000;
        goto LABEL_19;
      }
      ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v21);
      free(v8);
      ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
      result = 0;
    }
  }
  catch ( ATL::CAtlException *v20 )
  {
    return *(unsigned int *)v20;
  }
  BufferSetLength = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength();
}

```

## disassembly

```asm
0x1800335b8  mov     rax, rsp
0x1800335bb  mov     [rax+8], rbx
0x1800335bf  push    rsi
0x1800335c0  push    rdi
0x1800335c1  push    r14
0x1800335c3  sub     rsp, 60h
0x1800335c7  mov     rbx, rdx
0x1800335ca  mov     rdi, rcx
0x1800335cd  mov     dword ptr [rax+18h], 0
0x1800335d4  lea     r8, [rax+18h]
0x1800335d8  xor     edx, edx
0x1800335da  mov     rcx, rbx
0x1800335dd  call    cs:__imp_WdiGetInstanceFilePath
0x1800335e3  test    eax, eax
0x1800335e5  js      loc_1800338F5
0x1800335eb  mov     edx, [rsp+78h+arg_10]
0x1800335f2  test    edx, edx
0x1800335f4  jnz     short loc_180033600
0x1800335f6  mov     eax, 80004005h
0x1800335fb  jmp     loc_1800338F5
0x180033600  mov     rcx, rdi
0x180033603  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x180033608  lea     r8, [rsp+78h+arg_10]
0x180033610  mov     rdx, rax
0x180033613  mov     rcx, rbx
0x180033616  call    cs:__imp_WdiGetInstanceFilePath
0x18003361c  test    eax, eax
0x18003361e  js      loc_1800338F5
0x180033624  mov     edx, [rsp+78h+arg_10]
0x18003362b  test    edx, edx
0x18003362d  jnz     short loc_180033639
0x18003362f  mov     eax, 80004005h
0x180033634  jmp     loc_1800338F5
0x180033639  dec     edx
0x18003363b  mov     rcx, rdi
0x18003363e  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180033643  lea     rdx, aKrundownEtl; "\\krundown.etl"
0x18003364a  mov     rcx, rdi
0x18003364d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180033652  lea     rcx, [rsp+78h+InstanceName]
0x18003365a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003365f  nop
0x180033660  call    cs:__imp_GetCurrentThreadId
0x180033666  mov     r8d, eax
0x180033669  lea     rdx, aCkclrundownX; "ckclrundown_%x"
0x180033670  lea     rcx, [rsp+78h+InstanceName]
0x180033678  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18003367d  nop
0x18003367e  mov     esi, 488h
0x180033683  mov     ecx, esi; Size
0x180033685  call    cs:__imp_malloc
0x18003368b  mov     rbx, rax
0x18003368e  mov     [rsp+78h+var_40], rax
0x180033693  test    rax, rax
0x180033696  jnz     short loc_1800336BD
0x180033698  mov     rcx, rax; Block
0x18003369b  call    cs:__imp_free
0x1800336a1  nop
0x1800336a2  mov     rcx, [rsp+78h+InstanceName]
0x1800336aa  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800336ae  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800336b3  mov     eax, 8007000Eh
0x1800336b8  jmp     loc_1800338F5
0x1800336bd  mov     r8, rsi; Size
0x1800336c0  xor     edx, edx; Val
0x1800336c2  mov     rcx, rbx; void *
0x1800336c5  call    memset_0
0x1800336ca  mov     [rbx], esi
0x1800336cc  mov     dword ptr [rbx+2Ch], 20000h
0x1800336d3  movups  xmm0, cs:CKCLRundownLoggerGuid
0x1800336da  movdqu  xmmword ptr [rbx+18h], xmm0
0x1800336df  mov     dword ptr [rbx+28h], 1
0x1800336e6  bts     dword ptr [rbx+40h], 7
0x1800336eb  mov     dword ptr [rbx+70h], 78h ; 'x'
0x1800336f2  mov     dword ptr [rbx+74h], 280h
0x1800336f9  lea     rax, ??_7CKernelRundownBufferConfig@PerfDiagDm@@6B@; const PerfDiagDm::CKernelRundownBufferConfig::`vftable'
0x180033700  mov     [rsp+78h+var_30], rax
0x180033705  mov     esi, 40h ; '@'
0x18003370a  mov     [rsp+78h+var_28], esi
0x18003370e  lea     r14d, [rsi-30h]
0x180033712  mov     [rsp+78h+var_24], r14d
0x180033717  mov     [rsp+78h+var_20], 100h
0x18003371f  xor     edx, edx
0x180033721  lea     rcx, [rsp+78h+var_30]
0x180033726  call    ?readWriteImpl@?$RegistryTransferable@VCKernelRundownBufferConfig@PerfDiagDm@@@Performance@@AEAAJ_N@Z; Performance::RegistryTransferable<PerfDiagDm::CKernelRundownBufferConfig>::readWriteImpl(bool)
0x18003372b  test    eax, eax
0x18003372d  jns     short loc_18003373E
0x18003372f  mov     [rsp+78h+var_24], r14d
0x180033734  mov     [rsp+78h+var_20], 100h
0x18003373c  jmp     short loc_180033742
0x18003373e  mov     esi, [rsp+78h+var_28]
0x180033742  mov     [rbx+30h], esi
0x180033745  mov     eax, [rsp+78h+var_24]
0x180033749  mov     [rbx+34h], eax
0x18003374c  mov     eax, [rsp+78h+var_20]
0x180033750  mov     [rbx+38h], eax
0x180033753  lea     rcx, [rbx+78h]; unsigned __int16 *
0x180033757  mov     r8, [rdi]; unsigned __int16 *
0x18003375a  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003375f  mov     edi, eax
0x180033761  test    eax, eax
0x180033763  jns     short loc_180033787
0x180033765  mov     rcx, rbx; Block
0x180033768  call    cs:__imp_free
0x18003376e  nop
0x18003376f  mov     rcx, [rsp+78h+InstanceName]
0x180033777  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003377b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180033780  mov     eax, edi
0x180033782  jmp     loc_1800338F5
0x180033787  lea     rcx, [rbx+280h]; unsigned __int16 *
0x18003378e  mov     rdi, [rsp+78h+InstanceName]
0x180033796  mov     r8, rdi; unsigned __int16 *
0x180033799  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003379e  mov     esi, eax
0x1800337a0  test    eax, eax
0x1800337a2  jns     short loc_1800337BE
0x1800337a4  mov     rcx, rbx; Block
0x1800337a7  call    cs:__imp_free
0x1800337ad  nop
0x1800337ae  lea     rcx, [rdi-18h]; this
0x1800337b2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800337b7  mov     eax, esi
0x1800337b9  jmp     loc_1800338F5
0x1800337be  mov     rdx, cs:?g_spCKCLRundownCriticalSection@PerfDiagDm@@3V?$CAtlGlobalPtr@VCComAutoCriticalSection@ATL@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<ATL::CComAutoCriticalSection> PerfDiagDm::g_spCKCLRundownCriticalSection
0x1800337c5  lea     rcx, [rsp+78h+var_30]
0x1800337ca  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800337cf  mov     [rsp+78h+TraceHandle], 0
0x1800337d8  mov     r8, rbx; Properties
0x1800337db  mov     rdx, rdi; InstanceName
0x1800337de  lea     rcx, [rsp+78h+TraceHandle]; TraceHandle
0x1800337e3  call    cs:__imp_StartTraceW
0x1800337e9  mov     esi, eax
0x1800337eb  test    eax, eax
0x1800337ed  jz      short loc_18003381F
0x1800337ef  jle     short loc_1800337FA
0x1800337f1  movzx   esi, ax
0x1800337f4  or      esi, 80070000h
0x1800337fa  lea     rcx, [rsp+78h+var_30]
0x1800337ff  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180033804  nop
0x180033805  mov     rcx, rbx; Block
0x180033808  call    cs:__imp_free
0x18003380e  nop
0x18003380f  lea     rcx, [rdi-18h]; this
0x180033813  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180033818  mov     eax, esi
0x18003381a  jmp     loc_1800338F5
0x18003381f  mov     rax, [rsp+78h+TraceHandle]
0x180033824  mov     [rsp+78h+var_58], rax; TraceHandle
0x180033829  lea     r9, KernelRundownGuid; ControlGuid
0x180033830  xor     r8d, r8d; EnableLevel
0x180033833  lea     edx, [r8+8]; EnableFlag
0x180033837  lea     ecx, [rdx-7]; Enable
0x18003383a  call    cs:__imp_EnableTrace
0x180033840  mov     r14d, eax
0x180033843  mov     r9d, 1; ControlCode
0x180033849  mov     r8, rbx; Properties
0x18003384c  mov     rdx, rdi; InstanceName
0x18003384f  mov     rcx, [rsp+78h+TraceHandle]; TraceHandle
0x180033854  call    cs:__imp_ControlTraceW
0x18003385a  mov     esi, eax
0x18003385c  test    r14d, r14d
0x18003385f  jz      short loc_180033891
0x180033861  jle     short loc_18003386E
0x180033863  movzx   r14d, r14w
0x180033867  or      r14d, 80070000h
0x18003386e  lea     rcx, [rsp+78h+var_30]
0x180033873  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180033878  nop
0x180033879  mov     rcx, rbx; Block
0x18003387c  call    cs:__imp_free
0x180033882  nop
0x180033883  lea     rcx, [rdi-18h]; this
0x180033887  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003388c  mov     eax, r14d
0x18003388f  jmp     short loc_1800338F5
0x180033891  test    eax, eax
0x180033893  jz      short loc_1800338CB
0x180033895  cmp     eax, 0EAh
0x18003389a  jz      short loc_1800338CB
0x18003389c  test    eax, eax
0x18003389e  jle     short loc_1800338A9
0x1800338a0  movzx   esi, ax
0x1800338a3  or      esi, 80070000h
0x1800338a9  lea     rcx, [rsp+78h+var_30]
0x1800338ae  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800338b3  nop
0x1800338b4  mov     rcx, rbx; Block
0x1800338b7  call    cs:__imp_free
0x1800338bd  nop
0x1800338be  lea     rcx, [rdi-18h]; this
0x1800338c2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800338c7  mov     eax, esi
0x1800338c9  jmp     short loc_1800338F5
0x1800338cb  lea     rcx, [rsp+78h+var_30]
0x1800338d0  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800338d5  nop
0x1800338d6  mov     rcx, rbx; Block
0x1800338d9  call    cs:__imp_free
0x1800338df  nop
0x1800338e0  lea     rcx, [rdi-18h]; this
0x1800338e4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800338e9  nop
0x1800338ea  xor     eax, eax
0x1800338ec  jmp     short loc_1800338F5
0x1800338ee  mov     eax, [rsp+78h+arg_10]
0x1800338f5  mov     rbx, [rsp+78h+arg_0]
0x1800338fd  add     rsp, 60h
0x180033901  pop     r14
0x180033903  pop     rdi
0x180033904  pop     rsi
0x180033905  retn
```
