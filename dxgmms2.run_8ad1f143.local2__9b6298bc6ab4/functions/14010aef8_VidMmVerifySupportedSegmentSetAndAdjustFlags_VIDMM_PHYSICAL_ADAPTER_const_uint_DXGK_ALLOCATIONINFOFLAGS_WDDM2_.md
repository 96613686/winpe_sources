# VidMmVerifySupportedSegmentSetAndAdjustFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *,unsigned __int64,unsigned __int64,bool,_VIDMM_VERIFY_SUPPORTED_SEGMENT *)

- ea: `0x14010aef8`
- end: `0x14010b30b`
- name: `?VidMmVerifySupportedSegmentSetAndAdjustFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IPEAU_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0@@_K2_NPEAU_VIDMM_VERIFY_SUPPORTED_SEGMENT@@@Z`
- size: `1043`
- prototype: `bool __usercall@<al>(const struct VIDMM_PHYSICAL_ADAPTER *@<rcx>, unsigned int@<edx>, struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *@<r8>, unsigned __int64@<r9>, unsigned __int64, bool, struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140105808`
- `0x1401232c8`

## callees

- `0x1400045ec`
- `0x14010aef8`
- `0x14010b43c`
- `0x14010b490`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010b127`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010b127`
- `watchdog!WdLogSingleEntry0` at `0x14010b034`
- `watchdog!WdLogSingleEntry0` at `0x14010b05b`
- `watchdog!WdLogSingleEntry0` at `0x14010b0bc`
- `watchdog!WdLogSingleEntry0` at `0x14010b0e3`
- `watchdog!WdLogSingleEntry0` at `0x14010b164`
- `watchdog!WdLogSingleEntry0` at `0x14010b18b`
- `watchdog!WdLogSingleEntry0` at `0x14010b1f7`
- `watchdog!WdLogSingleEntry0` at `0x14010b219`
- `watchdog!WdLogSingleEntry0` at `0x14010b23b`
- `watchdog!WdLogSingleEntry0` at `0x14010b25d`
- `watchdog!WdLogSingleEntry0` at `0x14010b291`
- `watchdog!WdLogSingleEntry0` at `0x14010b2bb`
- `watchdog!WdLogSingleEntry0` at `0x14010b2ee`
- `watchdog!WdLogSingleEntry0` at `0x14010b034`
- `watchdog!WdLogSingleEntry0` at `0x14010b05b`
- `watchdog!WdLogSingleEntry0` at `0x14010b0bc`
- `watchdog!WdLogSingleEntry0` at `0x14010b0e3`
- `watchdog!WdLogSingleEntry0` at `0x14010b164`
- `watchdog!WdLogSingleEntry0` at `0x14010b18b`
- `watchdog!WdLogSingleEntry0` at `0x14010b1f7`
- `watchdog!WdLogSingleEntry0` at `0x14010b219`
- `watchdog!WdLogSingleEntry0` at `0x14010b23b`
- `watchdog!WdLogSingleEntry0` at `0x14010b25d`
- `watchdog!WdLogSingleEntry0` at `0x14010b291`
- `watchdog!WdLogSingleEntry0` at `0x14010b2bb`
- `watchdog!WdLogSingleEntry0` at `0x14010b2ee`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010b11b`

## string_xrefs

- `0x14010b045`: `Cached allocations must only support cache coherent segments on adapters which have cache coherent aperture segments available`
- `0x14010b0cd`: `Cached allocations must only support aperture segments on adapters which do not have any cache coherent aperture segments`
- `0x14010b2a2`: `Shareable can only be used in combination with CpuVisible if the supported segment set contains exclusively aperture segments`
- `0x14010b2ff`: `Context allocations can only be used in combination with CpuVisible if the supported segment set contains exclusively aperture segment`

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
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned int i; // edx
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // rax

  v7 = a2 & ~*((_DWORD *)a1 + 24);
  if ( (a3->Value & 0x40000) != 0 && v7 )
  {
    WdLogSingleEntry0(1);
    v20 = 13981;
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
        v20 = 14030;
        v21 = L"HardwareProtected allocations in aperture segments are not supported";
        goto LABEL_19;
      }
      for ( i = a2; i; i &= ~(1 << v25) )
      {
        _BitScanForward((unsigned int *)&v25, i);
        v26 = *(_QWORD *)(*((_QWORD *)a1 + 285) + 8 * v25);
        v27 = v26 + 56;
        if ( !v26 )
          v27 = 48;
        if ( a4 > *(_QWORD *)v27 )
        {
          WdLogSingleEntry0(1);
          v20 = 14046;
          v21 = L"HardwareProtected allocation size is greater than a supported segment VPR range size";
          goto LABEL_19;
        }
        v28 = v26 + 64;
        if ( !v26 )
          v28 = 56;
        if ( (*(_DWORD *)v28 & 0x20) != 0 )
        {
          WdLogSingleEntry0(1);
          v20 = 14052;
          v21 = L"HardwareProtected allocations are not supported in pitch aligned segments";
          goto LABEL_19;
        }
      }
    }
    else
    {
      v23 = *(unsigned int *)(*((_QWORD *)a1 + 8) + 16LL);
      if ( (v23 & 0x10) == 0 )
      {
        WdLogSingleEntry0(1);
        v20 = 14022;
        v21 = L"HardwareProtected allocations must be in segments which support VPR";
        goto LABEL_19;
      }
      if ( g_IsInternalReleaseOrDbg )
      {
        WdLogNewEntry5_WdTrace(v23, v22);
        WdLogGlobalForLineNumber = 14001;
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
      v20 = 14073;
      v21 = L"Must specified PitchAlignedSize on allocation supported in PitchedAlign segment";
      goto LABEL_19;
    }
    if ( a5 < a4 )
    {
      WdLogSingleEntry0(1);
      v20 = 14079;
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
        v20 = 14115;
        v21 = L"Cached allocations must only support cache coherent segments on adapters which have cache coherent apertur"
               "e segments available";
        goto LABEL_19;
      }
    }
    else if ( (*(_DWORD *)(*(_QWORD *)(v16 + 24) + 444LL) & 8) == 0 && v7 )
    {
      WdLogSingleEntry0(1);
      v20 = 14123;
      v21 = L"Cached allocations must only support aperture segments on adapters which do not have any cache coherent aperture segments";
      goto LABEL_19;
    }
  }
  Value = a3->Value;
  if ( (a3->Value & 0x20000001) == 0x20000001 && v7 && (Value & 0x200) == 0 )
  {
    WdLogSingleEntry0(1);
    v20 = 14138;
    v21 = L"Shareable can only be used in combination with CpuVisible if the supported segment set contains exclusively aperture segments";
  }
  else if ( (Value & 0x100000) != 0 && v7 )
  {
    WdLogSingleEntry0(1);
    v20 = 14148;
    v21 = L"Cross adapter allocations must use only aperture segment";
  }
  else if ( (Value & 0x4000) != 0 && v7 )
  {
    WdLogSingleEntry0(1);
    v20 = 14157;
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
    v20 = 14171;
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
0x14010aef8  push    rbx
0x14010aefa  push    rbp
0x14010aefb  push    rsi
0x14010aefc  push    rdi
0x14010aefd  push    r12
0x14010aeff  push    r13
0x14010af01  push    r14
0x14010af03  push    r15
0x14010af05  sub     rsp, 58h
0x14010af09  mov     r15d, [rcx+60h]
0x14010af0d  xor     r12d, r12d
0x14010af10  mov     eax, [r8]
0x14010af13  mov     ebx, r15d
0x14010af16  not     ebx
0x14010af18  mov     r13d, 40000h
0x14010af1e  and     ebx, edx
0x14010af20  mov     rdi, r9
0x14010af23  mov     r14, r8
0x14010af26  mov     ebp, edx
0x14010af28  mov     rsi, rcx
0x14010af2b  test    r13d, eax
0x14010af2e  jnz     loc_14010B0D6
0x14010af34  and     r15d, ebp
0x14010af37  bt      eax, 11h
0x14010af3b  jb      loc_14010B100
0x14010af41  mov     r8d, 20h ; ' '; struct _DXGK_SEGMENTFLAGS
0x14010af47  mov     edx, ebp; unsigned int
0x14010af49  mov     rcx, rsi; struct VIDMM_PHYSICAL_ADAPTER *
0x14010af4c  call    ?VidMmCheckAnySegmentAllFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IU_DXGK_SEGMENTFLAGS@@@Z; VidMmCheckAnySegmentAllFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_SEGMENTFLAGS)
0x14010af51  test    al, al
0x14010af53  jnz     loc_14010AFDD
0x14010af59  mov     rdi, [rsp+98h+arg_30]
0x14010af61  and     dword ptr [rdi], 0FFFFFFFBh
0x14010af64  mov     eax, [r14]
0x14010af67  and     eax, 800004h
0x14010af6c  cmp     eax, 4
0x14010af6f  jz      loc_14010B007
0x14010af75  mov     ecx, [r14]
0x14010af78  mov     edx, 20000001h
0x14010af7d  mov     eax, ecx
0x14010af7f  and     eax, edx
0x14010af81  cmp     eax, edx
0x14010af83  jz      loc_14010B27A
0x14010af89  bt      ecx, 14h
0x14010af8d  jb      loc_14010B04E
0x14010af93  bt      ecx, 0Eh
0x14010af97  jb      loc_14010B2AE
0x14010af9d  cmp     [rsp+98h+arg_28], r12b
0x14010afa5  jnz     loc_14010B2D8
0x14010afab  mov     eax, [rdi]
0x14010afad  test    ebx, ebx
0x14010afaf  mov     ecx, r12d
0x14010afb2  setz    cl
0x14010afb5  and     eax, 0FFFFFFFEh
0x14010afb8  or      ecx, eax
0x14010afba  and     ecx, 0FFFFFFFDh
0x14010afbd  neg     r15d
0x14010afc0  sbb     eax, eax
0x14010afc2  and     eax, 2
0x14010afc5  or      ecx, eax
0x14010afc7  mov     al, 1
0x14010afc9  mov     [rdi], ecx
0x14010afcb  add     rsp, 58h
0x14010afcf  pop     r15
0x14010afd1  pop     r14
0x14010afd3  pop     r13
0x14010afd5  pop     r12
0x14010afd7  pop     rdi
0x14010afd8  pop     rsi
0x14010afd9  pop     rbp
0x14010afda  pop     rbx
0x14010afdb  retn
0x14010afdd  mov     rax, [rsp+98h+arg_20]
0x14010afe5  test    rax, rax
0x14010afe8  jz      loc_14010B236
0x14010afee  cmp     rax, rdi
0x14010aff1  jb      loc_14010B258
0x14010aff7  mov     rdi, [rsp+98h+arg_30]
0x14010afff  or      dword ptr [rdi], 4
0x14010b002  jmp     loc_14010AF64
0x14010b007  mov     rax, [rsi+38h]
0x14010b00b  cmp     [rax+0C82h], r12b
0x14010b012  jz      loc_14010B09C
0x14010b018  mov     r8d, 10h; struct _DXGK_SEGMENTFLAGS
0x14010b01e  mov     edx, ebp; unsigned int
0x14010b020  mov     rcx, rsi; struct VIDMM_PHYSICAL_ADAPTER *
0x14010b023  call    ?VidMmCheckAllSegmentsAllFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IU_DXGK_SEGMENTFLAGS@@@Z; VidMmCheckAllSegmentsAllFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_SEGMENTFLAGS)
0x14010b028  test    al, al
0x14010b02a  jnz     loc_14010AF75
0x14010b030  lea     ecx, [r8-0Fh]
0x14010b034  call    cs:__imp_WdLogSingleEntry0
0x14010b03b  nop     dword ptr [rax+rax+00h]
0x14010b040  mov     eax, 3723h
0x14010b045  lea     r9, aCachedAllocati_0; "Cached allocations must only support ca"...
0x14010b04c  jmp     short loc_14010B073
0x14010b04e  test    ebx, ebx
0x14010b050  jz      loc_14010AF93
0x14010b056  mov     ecx, 1
0x14010b05b  call    cs:__imp_WdLogSingleEntry0
0x14010b062  nop     dword ptr [rax+rax+00h]
0x14010b067  mov     eax, 3744h
0x14010b06c  lea     r9, aCrossAdapterAl_0; "Cross adapter allocations must use only"...
0x14010b073  mov     [rsp+98h+var_60], r12
0x14010b078  mov     edx, r13d
0x14010b07b  mov     [rsp+98h+var_68], r12
0x14010b080  mov     [rsp+98h+var_70], r12
0x14010b085  mov     [rsp+98h+var_78], rax
0x14010b08a  mov     cs:WdLogGlobalForLineNumber, eax
0x14010b090  call    DxgkLogInternalTriageEvent
0x14010b095  xor     al, al
0x14010b097  jmp     loc_14010AFCB
0x14010b09c  mov     rax, [rax+18h]
0x14010b0a0  mov     ecx, [rax+1BCh]
0x14010b0a6  test    cl, 8
0x14010b0a9  jnz     loc_14010AF75
0x14010b0af  test    ebx, ebx
0x14010b0b1  jz      loc_14010AF75
0x14010b0b7  mov     ecx, 1
0x14010b0bc  call    cs:__imp_WdLogSingleEntry0
0x14010b0c3  nop     dword ptr [rax+rax+00h]
0x14010b0c8  mov     eax, 372Bh
0x14010b0cd  lea     r9, aCachedAllocati; "Cached allocations must only support ap"...
0x14010b0d4  jmp     short loc_14010B073
0x14010b0d6  test    ebx, ebx
0x14010b0d8  jz      loc_14010AF34
0x14010b0de  mov     ecx, 1
0x14010b0e3  call    cs:__imp_WdLogSingleEntry0
0x14010b0ea  nop     dword ptr [rax+rax+00h]
0x14010b0ef  mov     eax, 369Dh
0x14010b0f4  lea     r9, aCpuvisibleonde_0; "CpuVisibleOnDemand allocations only sup"...
0x14010b0fb  jmp     loc_14010B073
0x14010b100  mov     r8d, 10000h; struct _DXGK_SEGMENTFLAGS
0x14010b106  call    ?VidMmCheckAllSegmentsAllFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IU_DXGK_SEGMENTFLAGS@@@Z; VidMmCheckAllSegmentsAllFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_SEGMENTFLAGS)
0x14010b10b  test    al, al
0x14010b10d  jnz     short loc_14010B181
0x14010b10f  mov     rax, [rsi+40h]
0x14010b113  mov     ecx, [rax+10h]
0x14010b116  test    cl, 10h
0x14010b119  jz      short loc_14010B15F
0x14010b11b  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14010b122  cmp     [rax], r12b
0x14010b125  jz      short loc_14010B13D
0x14010b127  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14010b12e  nop     dword ptr [rax+rax+00h]
0x14010b133  mov     cs:WdLogGlobalForLineNumber, 36B1h
0x14010b13d  mov     rax, [rsi+38h]
0x14010b141  mov     rcx, [rax+18h]
0x14010b145  cmp     dword ptr [rcx+1A4h], 4D4F4351h
0x14010b14f  jz      loc_14010AF41
0x14010b155  btr     dword ptr [r14], 11h
0x14010b15a  jmp     loc_14010AF41
0x14010b15f  mov     ecx, 1
0x14010b164  call    cs:__imp_WdLogSingleEntry0
0x14010b16b  nop     dword ptr [rax+rax+00h]
0x14010b170  mov     eax, 36C6h
0x14010b175  lea     r9, aHardwareprotec_1; "HardwareProtected allocations must be i"...
0x14010b17c  jmp     loc_14010B073
0x14010b181  test    r15d, r15d
0x14010b184  jz      short loc_14010B1A8
0x14010b186  mov     ecx, 1
0x14010b18b  call    cs:__imp_WdLogSingleEntry0
0x14010b192  nop     dword ptr [rax+rax+00h]
0x14010b197  mov     eax, 36CEh
0x14010b19c  lea     r9, aHardwareprotec_3; "HardwareProtected allocations in apertu"...
0x14010b1a3  jmp     loc_14010B073
0x14010b1a8  mov     edx, ebp
0x14010b1aa  test    edx, edx
0x14010b1ac  jz      loc_14010AF41
0x14010b1b2  mov     rax, [rsi+8E8h]
0x14010b1b9  mov     ecx, 30h ; '0'
0x14010b1be  bsf     r9d, edx
0x14010b1c2  mov     r8, [rax+r9*8]
0x14010b1c6  test    r8, r8
0x14010b1c9  lea     rax, [r8+38h]
0x14010b1cd  cmovz   rax, rcx
0x14010b1d1  cmp     rdi, [rax]
0x14010b1d4  ja      short loc_14010B214
0x14010b1d6  test    r8, r8
0x14010b1d9  lea     rax, [r8+40h]
0x14010b1dd  mov     ecx, 38h ; '8'
0x14010b1e2  cmovz   rax, rcx
0x14010b1e6  mov     eax, [rax]
0x14010b1e8  test    al, 20h
0x14010b1ea  jnz     short loc_14010B1F2
0x14010b1ec  btr     edx, r9d
0x14010b1f0  jmp     short loc_14010B1AA
0x14010b1f2  mov     ecx, 1
0x14010b1f7  call    cs:__imp_WdLogSingleEntry0
0x14010b1fe  nop     dword ptr [rax+rax+00h]
0x14010b203  mov     eax, 36E4h
0x14010b208  lea     r9, aHardwareprotec; "HardwareProtected allocations are not s"...
0x14010b20f  jmp     loc_14010B073
0x14010b214  mov     ecx, 1
0x14010b219  call    cs:__imp_WdLogSingleEntry0
0x14010b220  nop     dword ptr [rax+rax+00h]
0x14010b225  mov     eax, 36DEh
0x14010b22a  lea     r9, aHardwareprotec_0; "HardwareProtected allocation size is gr"...
0x14010b231  jmp     loc_14010B073
0x14010b236  mov     ecx, 1
0x14010b23b  call    cs:__imp_WdLogSingleEntry0
0x14010b242  nop     dword ptr [rax+rax+00h]
0x14010b247  mov     eax, 36F9h
0x14010b24c  lea     r9, aMustSpecifiedP; "Must specified PitchAlignedSize on allo"...
0x14010b253  jmp     loc_14010B073
0x14010b258  mov     ecx, 1
0x14010b25d  call    cs:__imp_WdLogSingleEntry0
0x14010b264  nop     dword ptr [rax+rax+00h]
0x14010b269  mov     eax, 36FFh
0x14010b26e  lea     r9, aPitchalignedsi; "PitchAlignedSize must be greater or equ"...
0x14010b275  jmp     loc_14010B073
0x14010b27a  test    ebx, ebx
0x14010b27c  jz      loc_14010AF89
0x14010b282  bt      ecx, 9
0x14010b286  jb      loc_14010AF89
0x14010b28c  mov     ecx, 1
0x14010b291  call    cs:__imp_WdLogSingleEntry0
0x14010b298  nop     dword ptr [rax+rax+00h]
0x14010b29d  mov     eax, 373Ah
0x14010b2a2  lea     r9, aShareableCanOn; "Shareable can only be used in combinati"...
0x14010b2a9  jmp     loc_14010B073
0x14010b2ae  test    ebx, ebx
0x14010b2b0  jz      loc_14010AF9D
0x14010b2b6  mov     ecx, 1
0x14010b2bb  call    cs:__imp_WdLogSingleEntry0
0x14010b2c2  nop     dword ptr [rax+rax+00h]
0x14010b2c7  mov     eax, 374Dh
0x14010b2cc  lea     r9, aHistoryBufferC; "History buffer can only be allocated fr"...
0x14010b2d3  jmp     loc_14010B073
0x14010b2d8  test    cl, 1
0x14010b2db  jz      loc_14010AFAB
0x14010b2e1  test    ebx, ebx
0x14010b2e3  jz      loc_14010AFAB
0x14010b2e9  mov     ecx, 1
0x14010b2ee  call    cs:__imp_WdLogSingleEntry0
0x14010b2f5  nop     dword ptr [rax+rax+00h]
0x14010b2fa  mov     eax, 375Bh
0x14010b2ff  lea     r9, aContextAllocat; "Context allocations can only be used in"...
0x14010b306  jmp     loc_14010B073
```
