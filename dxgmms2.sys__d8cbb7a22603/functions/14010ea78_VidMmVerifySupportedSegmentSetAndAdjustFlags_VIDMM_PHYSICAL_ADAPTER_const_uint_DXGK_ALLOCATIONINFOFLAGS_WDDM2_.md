# VidMmVerifySupportedSegmentSetAndAdjustFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *,unsigned __int64,unsigned __int64,bool,_VIDMM_VERIFY_SUPPORTED_SEGMENT *)

- ea: `0x14010ea78`
- end: `0x14010ee8b`
- name: `?VidMmVerifySupportedSegmentSetAndAdjustFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IPEAU_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0@@_K2_NPEAU_VIDMM_VERIFY_SUPPORTED_SEGMENT@@@Z`
- size: `1043`
- prototype: `bool __usercall@<al>(const struct VIDMM_PHYSICAL_ADAPTER *@<rcx>, unsigned int@<edx>, struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *@<r8>, unsigned __int64@<r9>, unsigned __int64, bool, struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400b4cd8`
- `0x140127964`

## callees

- `0x140004268`
- `0x14010ea78`
- `0x14010efbc`
- `0x14010f010`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010eca7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010eca7`
- `watchdog!WdLogSingleEntry0` at `0x14010ebb4`
- `watchdog!WdLogSingleEntry0` at `0x14010ebdb`
- `watchdog!WdLogSingleEntry0` at `0x14010ec3c`
- `watchdog!WdLogSingleEntry0` at `0x14010ec63`
- `watchdog!WdLogSingleEntry0` at `0x14010ece4`
- `watchdog!WdLogSingleEntry0` at `0x14010ed0b`
- `watchdog!WdLogSingleEntry0` at `0x14010ed77`
- `watchdog!WdLogSingleEntry0` at `0x14010ed99`
- `watchdog!WdLogSingleEntry0` at `0x14010edbb`
- `watchdog!WdLogSingleEntry0` at `0x14010eddd`
- `watchdog!WdLogSingleEntry0` at `0x14010ee11`
- `watchdog!WdLogSingleEntry0` at `0x14010ee3b`
- `watchdog!WdLogSingleEntry0` at `0x14010ee6e`
- `watchdog!WdLogSingleEntry0` at `0x14010ebb4`
- `watchdog!WdLogSingleEntry0` at `0x14010ebdb`
- `watchdog!WdLogSingleEntry0` at `0x14010ec3c`
- `watchdog!WdLogSingleEntry0` at `0x14010ec63`
- `watchdog!WdLogSingleEntry0` at `0x14010ece4`
- `watchdog!WdLogSingleEntry0` at `0x14010ed0b`
- `watchdog!WdLogSingleEntry0` at `0x14010ed77`
- `watchdog!WdLogSingleEntry0` at `0x14010ed99`
- `watchdog!WdLogSingleEntry0` at `0x14010edbb`
- `watchdog!WdLogSingleEntry0` at `0x14010eddd`
- `watchdog!WdLogSingleEntry0` at `0x14010ee11`
- `watchdog!WdLogSingleEntry0` at `0x14010ee3b`
- `watchdog!WdLogSingleEntry0` at `0x14010ee6e`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010ec9b`

## string_xrefs

- `0x14010ebc5`: `Cached allocations must only support cache coherent segments on adapters which have cache coherent aperture segments available`
- `0x14010ec4d`: `Cached allocations must only support aperture segments on adapters which do not have any cache coherent aperture segments`
- `0x14010ee22`: `Shareable can only be used in combination with CpuVisible if the supported segment set contains exclusively aperture segments`
- `0x14010ee7f`: `Context allocations can only be used in combination with CpuVisible if the supported segment set contains exclusively aperture segment`

## pseudocode

```c
bool __fastcall VidMmVerifySupportedSegmentSetAndAdjustFlags(
        const struct VIDMM_PHYSICAL_ADAPTER *a1,
        unsigned int a2,
        struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        bool a6,
        struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *a7)
{
  int v7; // ebx
  int v12; // r15d
  struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *v13; // rdi
  UINT Value; // ecx
  bool result; // al
  __int64 v16; // rax
  int v17; // r8d
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rax
  const wchar_t *v21; // r9
  __int64 v22; // rcx
  unsigned int i; // edx
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rax

  v7 = a2 & ~*((_DWORD *)a1 + 24);
  if ( (a3->Value & 0x40000) != 0 && v7 )
  {
    WdLogSingleEntry0(1);
    v20 = 14153;
    v21 = L"CpuVisibleOnDemand allocations only support aperture segments";
    goto LABEL_19;
  }
  v12 = a2 & *((_DWORD *)a1 + 24);
  if ( (a3->Value & 0x20000) != 0 )
  {
    if ( VidMmCheckAllSegmentsAllFlags(a1, a2, (struct _DXGK_SEGMENTFLAGS)0x10000) )
    {
      if ( v12 )
      {
        WdLogSingleEntry0(1);
        v20 = 14202;
        v21 = L"HardwareProtected allocations in aperture segments are not supported";
        goto LABEL_19;
      }
      for ( i = a2; i; i &= ~(1 << v24) )
      {
        _BitScanForward((unsigned int *)&v24, i);
        v25 = *(_QWORD *)(*((_QWORD *)a1 + 318) + 8 * v24);
        v26 = v25 + 56;
        if ( !v25 )
          v26 = 48;
        if ( a4 > *(_QWORD *)v26 )
        {
          WdLogSingleEntry0(1);
          v20 = 14218;
          v21 = L"HardwareProtected allocation size is greater than a supported segment VPR range size";
          goto LABEL_19;
        }
        v27 = v25 + 64;
        if ( !v25 )
          v27 = 56;
        if ( (*(_DWORD *)v27 & 0x20) != 0 )
        {
          WdLogSingleEntry0(1);
          v20 = 14224;
          v21 = L"HardwareProtected allocations are not supported in pitch aligned segments";
          goto LABEL_19;
        }
      }
    }
    else
    {
      v22 = *(unsigned int *)(*((_QWORD *)a1 + 8) + 16LL);
      if ( (v22 & 0x10) == 0 )
      {
        WdLogSingleEntry0(1);
        v20 = 14194;
        v21 = L"HardwareProtected allocations must be in segments which support VPR";
        goto LABEL_19;
      }
      if ( g_IsInternalReleaseOrDbg )
      {
        WdLogNewEntry5_WdTrace(v22);
        WdLogGlobalForLineNumber = 14173;
      }
      if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 7) + 24LL) + 420LL) != 1297040209 )
        a3->Value &= ~0x20000u;
    }
  }
  if ( VidMmCheckAnySegmentAllFlags(a1, a2, (struct _DXGK_SEGMENTFLAGS)32) )
  {
    if ( !a5 )
    {
      WdLogSingleEntry0(1);
      v20 = 14245;
      v21 = L"Must specified PitchAlignedSize on allocation supported in PitchedAlign segment";
      goto LABEL_19;
    }
    if ( a5 < a4 )
    {
      WdLogSingleEntry0(1);
      v20 = 14251;
      v21 = L"PitchAlignedSize must be greater or equal to Size";
      goto LABEL_19;
    }
    v13 = a7;
    *(_DWORD *)a7 |= 4u;
  }
  else
  {
    v13 = a7;
    *(_DWORD *)a7 &= ~4u;
  }
  if ( (a3->Value & 0x800004) == 4 )
  {
    v16 = *((_QWORD *)a1 + 7);
    if ( *(_BYTE *)(v16 + 3202) )
    {
      if ( !VidMmCheckAllSegmentsAllFlags(a1, a2, (struct _DXGK_SEGMENTFLAGS)16) )
      {
        WdLogSingleEntry0((unsigned int)(v17 - 15));
        v20 = 14287;
        v21 = L"Cached allocations must only support cache coherent segments on adapters which have cache coherent apertur"
               "e segments available";
        goto LABEL_19;
      }
    }
    else if ( (*(_DWORD *)(*(_QWORD *)(v16 + 24) + 444LL) & 8) == 0 && v7 )
    {
      WdLogSingleEntry0(1);
      v20 = 14295;
      v21 = L"Cached allocations must only support aperture segments on adapters which do not have any cache coherent aperture segments";
      goto LABEL_19;
    }
  }
  Value = a3->Value;
  if ( (a3->Value & 0x20000001) == 0x20000001 && v7 && (Value & 0x200) == 0 )
  {
    WdLogSingleEntry0(1);
    v20 = 14310;
    v21 = L"Shareable can only be used in combination with CpuVisible if the supported segment set contains exclusively aperture segments";
  }
  else if ( (Value & 0x100000) != 0 && v7 )
  {
    WdLogSingleEntry0(1);
    v20 = 14320;
    v21 = L"Cross adapter allocations must use only aperture segment";
  }
  else if ( (Value & 0x4000) != 0 && v7 )
  {
    WdLogSingleEntry0(1);
    v20 = 14329;
    v21 = L"History buffer can only be allocated from an aperture segment";
  }
  else
  {
    if ( !a6 || (Value & 1) == 0 || !v7 )
    {
      result = 1;
      *(_DWORD *)v13 = (v12 != 0 ? 2 : 0) | *(_DWORD *)v13 & 0xFFFFFFFC | (v7 == 0);
      return result;
    }
    WdLogSingleEntry0(1);
    v20 = 14343;
    v21 = L"Context allocations can only be used in combination with CpuVisible if the supported segment set contains excl"
           "usively aperture segment";
  }
LABEL_19:
  WdLogGlobalForLineNumber = v20;
  DxgkLogInternalTriageEvent(v18, 0x40000, v19, (_DWORD)v21, v20, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x14010ea78  push    rbx
0x14010ea7a  push    rbp
0x14010ea7b  push    rsi
0x14010ea7c  push    rdi
0x14010ea7d  push    r12
0x14010ea7f  push    r13
0x14010ea81  push    r14
0x14010ea83  push    r15
0x14010ea85  sub     rsp, 58h
0x14010ea89  mov     r15d, [rcx+60h]
0x14010ea8d  xor     r12d, r12d
0x14010ea90  mov     eax, [r8]
0x14010ea93  mov     ebx, r15d
0x14010ea96  not     ebx
0x14010ea98  mov     r13d, 40000h
0x14010ea9e  and     ebx, edx
0x14010eaa0  mov     rdi, r9
0x14010eaa3  mov     r14, r8
0x14010eaa6  mov     ebp, edx
0x14010eaa8  mov     rsi, rcx
0x14010eaab  test    r13d, eax
0x14010eaae  jnz     loc_14010EC56
0x14010eab4  and     r15d, ebp
0x14010eab7  bt      eax, 11h
0x14010eabb  jb      loc_14010EC80
0x14010eac1  mov     r8d, 20h ; ' '; struct _DXGK_SEGMENTFLAGS
0x14010eac7  mov     edx, ebp; unsigned int
0x14010eac9  mov     rcx, rsi; struct VIDMM_PHYSICAL_ADAPTER *
0x14010eacc  call    ?VidMmCheckAnySegmentAllFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IU_DXGK_SEGMENTFLAGS@@@Z; VidMmCheckAnySegmentAllFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_SEGMENTFLAGS)
0x14010ead1  test    al, al
0x14010ead3  jnz     loc_14010EB5D
0x14010ead9  mov     rdi, [rsp+98h+arg_30]
0x14010eae1  and     dword ptr [rdi], 0FFFFFFFBh
0x14010eae4  mov     eax, [r14]
0x14010eae7  and     eax, 800004h
0x14010eaec  cmp     eax, 4
0x14010eaef  jz      loc_14010EB87
0x14010eaf5  mov     ecx, [r14]
0x14010eaf8  mov     edx, 20000001h
0x14010eafd  mov     eax, ecx
0x14010eaff  and     eax, edx
0x14010eb01  cmp     eax, edx
0x14010eb03  jz      loc_14010EDFA
0x14010eb09  bt      ecx, 14h
0x14010eb0d  jb      loc_14010EBCE
0x14010eb13  bt      ecx, 0Eh
0x14010eb17  jb      loc_14010EE2E
0x14010eb1d  cmp     [rsp+98h+arg_28], r12b
0x14010eb25  jnz     loc_14010EE58
0x14010eb2b  mov     eax, [rdi]
0x14010eb2d  test    ebx, ebx
0x14010eb2f  mov     ecx, r12d
0x14010eb32  setz    cl
0x14010eb35  and     eax, 0FFFFFFFEh
0x14010eb38  or      ecx, eax
0x14010eb3a  and     ecx, 0FFFFFFFDh
0x14010eb3d  neg     r15d
0x14010eb40  sbb     eax, eax
0x14010eb42  and     eax, 2
0x14010eb45  or      ecx, eax
0x14010eb47  mov     al, 1
0x14010eb49  mov     [rdi], ecx
0x14010eb4b  add     rsp, 58h
0x14010eb4f  pop     r15
0x14010eb51  pop     r14
0x14010eb53  pop     r13
0x14010eb55  pop     r12
0x14010eb57  pop     rdi
0x14010eb58  pop     rsi
0x14010eb59  pop     rbp
0x14010eb5a  pop     rbx
0x14010eb5b  retn
0x14010eb5d  mov     rax, [rsp+98h+arg_20]
0x14010eb65  test    rax, rax
0x14010eb68  jz      loc_14010EDB6
0x14010eb6e  cmp     rax, rdi
0x14010eb71  jb      loc_14010EDD8
0x14010eb77  mov     rdi, [rsp+98h+arg_30]
0x14010eb7f  or      dword ptr [rdi], 4
0x14010eb82  jmp     loc_14010EAE4
0x14010eb87  mov     rax, [rsi+38h]
0x14010eb8b  cmp     [rax+0C82h], r12b
0x14010eb92  jz      loc_14010EC1C
0x14010eb98  mov     r8d, 10h; struct _DXGK_SEGMENTFLAGS
0x14010eb9e  mov     edx, ebp; unsigned int
0x14010eba0  mov     rcx, rsi; struct VIDMM_PHYSICAL_ADAPTER *
0x14010eba3  call    ?VidMmCheckAllSegmentsAllFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IU_DXGK_SEGMENTFLAGS@@@Z; VidMmCheckAllSegmentsAllFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_SEGMENTFLAGS)
0x14010eba8  test    al, al
0x14010ebaa  jnz     loc_14010EAF5
0x14010ebb0  lea     ecx, [r8-0Fh]
0x14010ebb4  call    cs:__imp_WdLogSingleEntry0
0x14010ebbb  nop     dword ptr [rax+rax+00h]
0x14010ebc0  mov     eax, 37CFh
0x14010ebc5  lea     r9, aCachedAllocati_0; "Cached allocations must only support ca"...
0x14010ebcc  jmp     short loc_14010EBF3
0x14010ebce  test    ebx, ebx
0x14010ebd0  jz      loc_14010EB13
0x14010ebd6  mov     ecx, 1
0x14010ebdb  call    cs:__imp_WdLogSingleEntry0
0x14010ebe2  nop     dword ptr [rax+rax+00h]
0x14010ebe7  mov     eax, 37F0h
0x14010ebec  lea     r9, aCrossAdapterAl_0; "Cross adapter allocations must use only"...
0x14010ebf3  mov     [rsp+98h+var_60], r12
0x14010ebf8  mov     edx, r13d
0x14010ebfb  mov     [rsp+98h+var_68], r12
0x14010ec00  mov     [rsp+98h+var_70], r12
0x14010ec05  mov     [rsp+98h+var_78], rax
0x14010ec0a  mov     cs:WdLogGlobalForLineNumber, eax
0x14010ec10  call    DxgkLogInternalTriageEvent
0x14010ec15  xor     al, al
0x14010ec17  jmp     loc_14010EB4B
0x14010ec1c  mov     rax, [rax+18h]
0x14010ec20  mov     ecx, [rax+1BCh]
0x14010ec26  test    cl, 8
0x14010ec29  jnz     loc_14010EAF5
0x14010ec2f  test    ebx, ebx
0x14010ec31  jz      loc_14010EAF5
0x14010ec37  mov     ecx, 1
0x14010ec3c  call    cs:__imp_WdLogSingleEntry0
0x14010ec43  nop     dword ptr [rax+rax+00h]
0x14010ec48  mov     eax, 37D7h
0x14010ec4d  lea     r9, aCachedAllocati; "Cached allocations must only support ap"...
0x14010ec54  jmp     short loc_14010EBF3
0x14010ec56  test    ebx, ebx
0x14010ec58  jz      loc_14010EAB4
0x14010ec5e  mov     ecx, 1
0x14010ec63  call    cs:__imp_WdLogSingleEntry0
0x14010ec6a  nop     dword ptr [rax+rax+00h]
0x14010ec6f  mov     eax, 3749h
0x14010ec74  lea     r9, aCpuvisibleonde_0; "CpuVisibleOnDemand allocations only sup"...
0x14010ec7b  jmp     loc_14010EBF3
0x14010ec80  mov     r8d, 10000h; struct _DXGK_SEGMENTFLAGS
0x14010ec86  call    ?VidMmCheckAllSegmentsAllFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IU_DXGK_SEGMENTFLAGS@@@Z; VidMmCheckAllSegmentsAllFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_SEGMENTFLAGS)
0x14010ec8b  test    al, al
0x14010ec8d  jnz     short loc_14010ED01
0x14010ec8f  mov     rax, [rsi+40h]
0x14010ec93  mov     ecx, [rax+10h]
0x14010ec96  test    cl, 10h
0x14010ec99  jz      short loc_14010ECDF
0x14010ec9b  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14010eca2  cmp     [rax], r12b
0x14010eca5  jz      short loc_14010ECBD
0x14010eca7  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14010ecae  nop     dword ptr [rax+rax+00h]
0x14010ecb3  mov     cs:WdLogGlobalForLineNumber, 375Dh
0x14010ecbd  mov     rax, [rsi+38h]
0x14010ecc1  mov     rcx, [rax+18h]
0x14010ecc5  cmp     dword ptr [rcx+1A4h], 4D4F4351h
0x14010eccf  jz      loc_14010EAC1
0x14010ecd5  btr     dword ptr [r14], 11h
0x14010ecda  jmp     loc_14010EAC1
0x14010ecdf  mov     ecx, 1
0x14010ece4  call    cs:__imp_WdLogSingleEntry0
0x14010eceb  nop     dword ptr [rax+rax+00h]
0x14010ecf0  mov     eax, 3772h
0x14010ecf5  lea     r9, aHardwareprotec_1; "HardwareProtected allocations must be i"...
0x14010ecfc  jmp     loc_14010EBF3
0x14010ed01  test    r15d, r15d
0x14010ed04  jz      short loc_14010ED28
0x14010ed06  mov     ecx, 1
0x14010ed0b  call    cs:__imp_WdLogSingleEntry0
0x14010ed12  nop     dword ptr [rax+rax+00h]
0x14010ed17  mov     eax, 377Ah
0x14010ed1c  lea     r9, aHardwareprotec_3; "HardwareProtected allocations in apertu"...
0x14010ed23  jmp     loc_14010EBF3
0x14010ed28  mov     edx, ebp
0x14010ed2a  test    edx, edx
0x14010ed2c  jz      loc_14010EAC1
0x14010ed32  mov     rax, [rsi+9F0h]
0x14010ed39  mov     ecx, 30h ; '0'
0x14010ed3e  bsf     r9d, edx
0x14010ed42  mov     r8, [rax+r9*8]
0x14010ed46  test    r8, r8
0x14010ed49  lea     rax, [r8+38h]
0x14010ed4d  cmovz   rax, rcx
0x14010ed51  cmp     rdi, [rax]
0x14010ed54  ja      short loc_14010ED94
0x14010ed56  test    r8, r8
0x14010ed59  lea     rax, [r8+40h]
0x14010ed5d  mov     ecx, 38h ; '8'
0x14010ed62  cmovz   rax, rcx
0x14010ed66  mov     eax, [rax]
0x14010ed68  test    al, 20h
0x14010ed6a  jnz     short loc_14010ED72
0x14010ed6c  btr     edx, r9d
0x14010ed70  jmp     short loc_14010ED2A
0x14010ed72  mov     ecx, 1
0x14010ed77  call    cs:__imp_WdLogSingleEntry0
0x14010ed7e  nop     dword ptr [rax+rax+00h]
0x14010ed83  mov     eax, 3790h
0x14010ed88  lea     r9, aHardwareprotec; "HardwareProtected allocations are not s"...
0x14010ed8f  jmp     loc_14010EBF3
0x14010ed94  mov     ecx, 1
0x14010ed99  call    cs:__imp_WdLogSingleEntry0
0x14010eda0  nop     dword ptr [rax+rax+00h]
0x14010eda5  mov     eax, 378Ah
0x14010edaa  lea     r9, aHardwareprotec_0; "HardwareProtected allocation size is gr"...
0x14010edb1  jmp     loc_14010EBF3
0x14010edb6  mov     ecx, 1
0x14010edbb  call    cs:__imp_WdLogSingleEntry0
0x14010edc2  nop     dword ptr [rax+rax+00h]
0x14010edc7  mov     eax, 37A5h
0x14010edcc  lea     r9, aMustSpecifiedP; "Must specified PitchAlignedSize on allo"...
0x14010edd3  jmp     loc_14010EBF3
0x14010edd8  mov     ecx, 1
0x14010eddd  call    cs:__imp_WdLogSingleEntry0
0x14010ede4  nop     dword ptr [rax+rax+00h]
0x14010ede9  mov     eax, 37ABh
0x14010edee  lea     r9, aPitchalignedsi; "PitchAlignedSize must be greater or equ"...
0x14010edf5  jmp     loc_14010EBF3
0x14010edfa  test    ebx, ebx
0x14010edfc  jz      loc_14010EB09
0x14010ee02  bt      ecx, 9
0x14010ee06  jb      loc_14010EB09
0x14010ee0c  mov     ecx, 1
0x14010ee11  call    cs:__imp_WdLogSingleEntry0
0x14010ee18  nop     dword ptr [rax+rax+00h]
0x14010ee1d  mov     eax, 37E6h
0x14010ee22  lea     r9, aShareableCanOn; "Shareable can only be used in combinati"...
0x14010ee29  jmp     loc_14010EBF3
0x14010ee2e  test    ebx, ebx
0x14010ee30  jz      loc_14010EB1D
0x14010ee36  mov     ecx, 1
0x14010ee3b  call    cs:__imp_WdLogSingleEntry0
0x14010ee42  nop     dword ptr [rax+rax+00h]
0x14010ee47  mov     eax, 37F9h
0x14010ee4c  lea     r9, aHistoryBufferC; "History buffer can only be allocated fr"...
0x14010ee53  jmp     loc_14010EBF3
0x14010ee58  test    cl, 1
0x14010ee5b  jz      loc_14010EB2B
0x14010ee61  test    ebx, ebx
0x14010ee63  jz      loc_14010EB2B
0x14010ee69  mov     ecx, 1
0x14010ee6e  call    cs:__imp_WdLogSingleEntry0
0x14010ee75  nop     dword ptr [rax+rax+00h]
0x14010ee7a  mov     eax, 3807h
0x14010ee7f  lea     r9, aContextAllocat; "Context allocations can only be used in"...
0x14010ee86  jmp     loc_14010EBF3
```
