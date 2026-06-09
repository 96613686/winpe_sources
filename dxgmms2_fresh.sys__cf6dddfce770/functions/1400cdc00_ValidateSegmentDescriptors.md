# ValidateSegmentDescriptors

- ea: `0x1400cdc00`
- end: `0x1400ce0b2`
- name: `ValidateSegmentDescriptors`
- size: `1202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400cba0c`

## callees

- `0x140004268`
- `0x1400cdc00`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400cdfcf`
- `watchdog!WdLogSingleEntry3` at `0x1400cdfcf`
- `watchdog!WdLogSingleEntry2` at `0x1400cdcc7`
- `watchdog!WdLogSingleEntry2` at `0x1400cdd69`
- `watchdog!WdLogSingleEntry2` at `0x1400cdda0`
- `watchdog!WdLogSingleEntry2` at `0x1400cddd0`
- `watchdog!WdLogSingleEntry2` at `0x1400cdee1`
- `watchdog!WdLogSingleEntry2` at `0x1400ce008`
- `watchdog!WdLogSingleEntry2` at `0x1400ce06c`
- `watchdog!WdLogSingleEntry2` at `0x1400cdcc7`
- `watchdog!WdLogSingleEntry2` at `0x1400cdd69`
- `watchdog!WdLogSingleEntry2` at `0x1400cdda0`
- `watchdog!WdLogSingleEntry2` at `0x1400cddd0`
- `watchdog!WdLogSingleEntry2` at `0x1400cdee1`
- `watchdog!WdLogSingleEntry2` at `0x1400ce008`
- `watchdog!WdLogSingleEntry2` at `0x1400ce06c`
- `watchdog!WdLogSingleEntry0` at `0x1400cddfa`
- `watchdog!WdLogSingleEntry0` at `0x1400cdf4c`
- `watchdog!WdLogSingleEntry0` at `0x1400cddfa`
- `watchdog!WdLogSingleEntry0` at `0x1400cdf4c`
- `watchdog!WdLogSingleEntry1` at `0x1400cde3c`
- `watchdog!WdLogSingleEntry1` at `0x1400cde73`
- `watchdog!WdLogSingleEntry1` at `0x1400cdeaa`
- `watchdog!WdLogSingleEntry1` at `0x1400cdf0e`
- `watchdog!WdLogSingleEntry1` at `0x1400cdf89`
- `watchdog!WdLogSingleEntry1` at `0x1400cde3c`
- `watchdog!WdLogSingleEntry1` at `0x1400cde73`
- `watchdog!WdLogSingleEntry1` at `0x1400cdeaa`
- `watchdog!WdLogSingleEntry1` at `0x1400cdf0e`
- `watchdog!WdLogSingleEntry1` at `0x1400cdf89`

## string_xrefs

- `0x1400ce01e`: `Invalid value for DXGK_SEGMENTDESCRIPTOR5[%u]::SegmentType (%u)`
- `0x1400cdfe5`: `Invalid value for DXGK_SEGMENTDESCRIPTOR5[%u]::Flags. Value (%u) cannot contain the bits (%u), or set reserved bits`
- `0x1400cddb6`: `DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64u) must be page aligned`
- `0x1400cdde6`: `DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64u) cannot be 0`
- `0x1400cdcdd`: `DXGK_SEGMENTDESCRIPTOR5[%u]::SlabSize cannot exceed 128MB (DXGK_PAGESIZE_128MB)`
- `0x1400cdef7`: `DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64u) must be zero for system memory segments`
- `0x1400cde4d`: `The CpuVisible flag cannot be set when SupportsCpuHostAperture is set. pSegmentDescriptor #%d`
- `0x1400cde84`: `The CPU host aperture is not yet supported in PBMM. pSegmentDescriptor #%d`

## pseudocode

```c
char __fastcall ValidateSegmentDescriptors(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned __int16 v6; // bp
  __int16 v7; // r11
  unsigned __int16 i; // r10
  __int64 v9; // rbx
  __int64 v10; // rdi
  int v11; // ecx
  unsigned int v12; // edx
  unsigned int v13; // eax
  __int64 v14; // r8
  int v15; // ecx
  int v16; // r8d
  const wchar_t *v17; // r9
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rdi
  int v21; // ecx
  int v22; // r8d
  int v23; // ecx
  int v24; // r8d
  int v25; // ecx
  int v26; // r8d
  int v27; // ecx
  int v28; // r8d
  unsigned __int16 v30; // r11
  __int64 v31; // rdi
  __int64 v32; // rbx
  int v33; // ecx
  int v34; // r8d
  __int64 v35; // [rsp+28h] [rbp-60h]
  __int64 v36; // [rsp+30h] [rbp-58h]

  v6 = -1;
  v7 = -1;
  for ( i = 0; i < a3; ++i )
  {
    v9 = i;
    v10 = 104LL * i;
    v11 = *(_DWORD *)(v10 + a2 + 96);
    if ( v11 > 1 )
    {
      WdLogSingleEntry2(1, i, *(int *)(v10 + a2 + 96));
      WdLogGlobalForLineNumber = 198;
      v17 = L"Invalid value for DXGK_SEGMENTDESCRIPTOR5[%u]::SegmentType (%u)";
      v18 = *(int *)(v10 + a2 + 96);
LABEL_39:
      v36 = 0;
LABEL_40:
      v35 = v18;
      goto LABEL_41;
    }
    v12 = *(_DWORD *)(v10 + a2);
    if ( (v12 & 0x40902B) != 0 || v12 >= 0x800000 )
    {
      WdLogSingleEntry3(1, i, *(unsigned int *)(v10 + a2), 4231211);
      WdLogGlobalForLineNumber = 213;
      v17 = L"Invalid value for DXGK_SEGMENTDESCRIPTOR5[%u]::Flags. Value (%u) cannot contain the bits (%u), or set reserved bits";
      v18 = *(unsigned int *)(v10 + a2);
      v36 = 4231211;
      goto LABEL_40;
    }
    v13 = *(_DWORD *)(v10 + a2 + 92);
    if ( v13 > 1 )
    {
      WdLogSingleEntry1(1, *(unsigned int *)(v10 + a2 + 92));
      WdLogGlobalForLineNumber = 224;
      DxgkLogInternalTriageEvent(
        v27,
        0x40000,
        v28,
        (unsigned int)L"Too many UEFI Frame Buffer Ranges specified in a segment. Maximum allowed is 1. Driver reported %d",
        *(unsigned int *)(v10 + a2 + 92),
        0,
        0,
        0);
      return 0;
    }
    if ( v13 )
    {
      if ( v6 != 0xFFFF )
      {
        v20 = i + 1LL;
        v9 = v6 + 1LL;
        WdLogSingleEntry2(1, v9, v20);
        v17 = L"Only one segment can have UEFI Frame Buffer Ranges, driver reported at segment ID %d and %d";
        v36 = 0;
        v35 = v20;
        WdLogGlobalForLineNumber = 237;
        goto LABEL_41;
      }
      v6 = i;
    }
    if ( v11 == 1 )
    {
      if ( !i )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 252;
        DxgkLogInternalTriageEvent(
          v21,
          0x40000,
          v22,
          (unsigned int)L"Segment with SegmentType=DXGK_SEGMENTTYPE_LOCAL cannot be segment 0",
          252,
          0,
          0,
          0);
        return 0;
      }
      v14 = *(_QWORD *)(v10 + a2 + 16);
      if ( !v14 )
      {
        WdLogSingleEntry2(1, i, 0);
        WdLogGlobalForLineNumber = 261;
        v17 = L"DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64u) cannot be 0";
        v18 = *(_QWORD *)(v10 + a2 + 16);
        goto LABEL_39;
      }
      if ( (v14 & 0xFFF) != 0 )
      {
        WdLogSingleEntry2(1, i, v14);
        WdLogGlobalForLineNumber = 270;
        v17 = L"DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64u) must be page aligned";
        v18 = *(_QWORD *)(v10 + a2 + 16);
        goto LABEL_39;
      }
      if ( *(int *)(v10 + a2 + 100) > 15 )
      {
        WdLogSingleEntry2(1, i, *(int *)(v10 + a2 + 100));
        WdLogGlobalForLineNumber = 279;
        v17 = L"DXGK_SEGMENTDESCRIPTOR5[%u]::SlabSize cannot exceed 128MB (DXGK_PAGESIZE_128MB)";
        v18 = *(int *)(v10 + a2 + 100);
        goto LABEL_39;
      }
    }
    else
    {
      if ( i )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 288;
        DxgkLogInternalTriageEvent(
          v25,
          0x40000,
          v26,
          (unsigned int)L"Segment with SegmentType=DXGK_SEGMENTTYPE_LOCAL must be segment 0",
          288,
          0,
          0,
          0);
        return 0;
      }
      if ( *(_DWORD *)(v10 + a2 + 100) != -1 )
      {
        WdLogSingleEntry1(1, *(int *)(v10 + a2 + 100));
        WdLogGlobalForLineNumber = 296;
        DxgkLogInternalTriageEvent(
          v23,
          0x40000,
          v24,
          (unsigned int)L"System memory segments must specify SlabSize=DXGK_PAGESIZE_UNKNOWN",
          *(int *)(v10 + a2 + 100),
          0,
          0,
          0);
        return 0;
      }
      v19 = *(_QWORD *)(v10 + a2 + 16);
      if ( v19 )
      {
        WdLogSingleEntry2(1, 0, v19);
        WdLogGlobalForLineNumber = 305;
        v17 = L"DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64u) must be zero for system memory segments";
        v18 = *(_QWORD *)(v10 + a2 + 16);
        goto LABEL_39;
      }
      v7 = 0;
    }
    if ( (v12 & 0x80u) == 0 && (v12 & 0x300) != 0
      || (*(_DWORD *)(v10 + a2) & 0x200) != 0 && (*(_DWORD *)(v10 + a2) & 0x100) != 0 )
    {
      WdLogSingleEntry1(1, i);
      v17 = L"Invalid flags specified for segment #%d";
      v36 = 0;
      v35 = 0;
      WdLogGlobalForLineNumber = 322;
      goto LABEL_41;
    }
    if ( (v12 & 0x2000) != 0 )
    {
      if ( (v12 & 4) != 0 )
      {
        WdLogSingleEntry1(1, i);
        v17 = L"The CpuVisible flag cannot be set when SupportsCpuHostAperture is set. pSegmentDescriptor #%d";
        v36 = 0;
        v35 = 0;
        WdLogGlobalForLineNumber = 332;
      }
      else
      {
        WdLogSingleEntry1(1, i);
        v17 = L"The CPU host aperture is not yet supported in PBMM. pSegmentDescriptor #%d";
        v36 = 0;
        v35 = 0;
        WdLogGlobalForLineNumber = 342;
      }
LABEL_41:
      DxgkLogInternalTriageEvent(v15, 0x40000, v16, (_DWORD)v17, v9, v35, v36, 0);
      return 0;
    }
  }
  if ( a4 )
  {
    v30 = v7 + 1;
    if ( a4 != v30 )
    {
      v31 = a4;
      v32 = v30;
      WdLogSingleEntry2(1, a4, v30);
      WdLogGlobalForLineNumber = 357;
      DxgkLogInternalTriageEvent(
        v33,
        0x40000,
        v34,
        (unsigned int)L"PagingBufferSegmentId (%u) must be 0 (contiguous physical memory), or the system memory segment (%u)",
        v31,
        v32,
        0,
        0);
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400cdc00  push    rbx
0x1400cdc02  push    rbp
0x1400cdc03  push    rsi
0x1400cdc04  push    rdi
0x1400cdc05  push    r12
0x1400cdc07  push    r14
0x1400cdc09  push    r15
0x1400cdc0b  sub     rsp, 50h
0x1400cdc0f  xor     r15d, r15d
0x1400cdc12  mov     r14d, r8d
0x1400cdc15  mov     r8d, 0FFFFh
0x1400cdc1b  mov     rsi, rdx
0x1400cdc1e  movzx   ebp, r8w
0x1400cdc22  movzx   r11d, r8w
0x1400cdc26  mov     r10d, r15d
0x1400cdc29  lea     r12d, [r15+1]
0x1400cdc2d  movzx   eax, r10w
0x1400cdc31  cmp     eax, r14d
0x1400cdc34  jnb     loc_1400CE04C
0x1400cdc3a  movzx   ebx, r10w
0x1400cdc3e  imul    rdi, rbx, 68h ; 'h'
0x1400cdc42  movsxd  rcx, dword ptr [rdi+rsi+60h]
0x1400cdc47  cmp     ecx, r12d
0x1400cdc4a  jg      loc_1400CDFFF
0x1400cdc50  mov     edx, [rdi+rsi]
0x1400cdc53  test    edx, 40902Bh
0x1400cdc59  jnz     loc_1400CDFC0
0x1400cdc5f  cmp     edx, 800000h
0x1400cdc65  jnb     loc_1400CDFC0
0x1400cdc6b  mov     eax, [rdi+rsi+5Ch]
0x1400cdc6f  cmp     eax, r12d
0x1400cdc72  ja      loc_1400CDF83
0x1400cdc78  test    eax, eax
0x1400cdc7a  jz      short loc_1400CDC8A
0x1400cdc7c  cmp     bp, r8w
0x1400cdc80  jnz     loc_1400CDD56
0x1400cdc86  movzx   ebp, r10w
0x1400cdc8a  cmp     ecx, r12d
0x1400cdc8d  jnz     short loc_1400CDCEE
0x1400cdc8f  test    r10w, r10w
0x1400cdc93  jz      loc_1400CDDF7
0x1400cdc99  mov     r8, [rdi+rsi+10h]
0x1400cdc9e  test    r8, r8
0x1400cdca1  jz      loc_1400CDDC7
0x1400cdca7  test    r8, 0FFFh
0x1400cdcae  jnz     loc_1400CDD9A
0x1400cdcb4  movsxd  rax, dword ptr [rdi+rsi+64h]
0x1400cdcb9  cmp     eax, 0Fh
0x1400cdcbc  jle     short loc_1400CDD17
0x1400cdcbe  mov     r8, rax
0x1400cdcc1  mov     rdx, rbx
0x1400cdcc4  mov     ecx, r12d
0x1400cdcc7  call    cs:__imp_WdLogSingleEntry2
0x1400cdcce  nop     dword ptr [rax+rax+00h]
0x1400cdcd3  mov     cs:WdLogGlobalForLineNumber, 117h
0x1400cdcdd  lea     r9, aDxgkSegmentdes_2; "DXGK_SEGMENTDESCRIPTOR5[%u]::SlabSize c"...
0x1400cdce4  movsxd  rax, dword ptr [rdi+rsi+64h]
0x1400cdce9  jmp     loc_1400CE02A
0x1400cdcee  test    r10w, r10w
0x1400cdcf2  jnz     loc_1400CDF49
0x1400cdcf8  movsxd  rax, dword ptr [rdi+rsi+64h]
0x1400cdcfd  cmp     eax, 0FFFFFFFFh
0x1400cdd00  jnz     loc_1400CDF08
0x1400cdd06  mov     r8, [rdi+rsi+10h]
0x1400cdd0b  test    r8, r8
0x1400cdd0e  jnz     loc_1400CDEDB
0x1400cdd14  mov     r11d, r15d
0x1400cdd17  test    dl, dl
0x1400cdd19  js      short loc_1400CDD27
0x1400cdd1b  test    edx, 300h
0x1400cdd21  jnz     loc_1400CDEA4
0x1400cdd27  bt      edx, 9
0x1400cdd2b  setb    cl
0x1400cdd2e  bt      edx, 8
0x1400cdd32  setb    al
0x1400cdd35  test    al, cl
0x1400cdd37  jnz     loc_1400CDEA4
0x1400cdd3d  bt      edx, 0Dh
0x1400cdd41  jb      loc_1400CDE31
0x1400cdd47  add     r10w, r12w
0x1400cdd4b  mov     r8d, 0FFFFh
0x1400cdd51  jmp     loc_1400CDC2D
0x1400cdd56  lea     rdi, [rbx+1]
0x1400cdd5a  mov     ecx, r12d
0x1400cdd5d  movzx   ebx, bp
0x1400cdd60  mov     r8, rdi
0x1400cdd63  inc     rbx
0x1400cdd66  mov     rdx, rbx
0x1400cdd69  call    cs:__imp_WdLogSingleEntry2
0x1400cdd70  nop     dword ptr [rax+rax+00h]
0x1400cdd75  mov     [rsp+88h+var_50], r15
0x1400cdd7a  lea     r9, aOnlyOneSegment; "Only one segment can have UEFI Frame Bu"...
0x1400cdd81  mov     [rsp+88h+var_58], r15
0x1400cdd86  mov     [rsp+88h+var_60], rdi
0x1400cdd8b  mov     cs:WdLogGlobalForLineNumber, 0EDh
0x1400cdd95  jmp     loc_1400CE039
0x1400cdd9a  mov     rdx, rbx
0x1400cdd9d  mov     ecx, r12d
0x1400cdda0  call    cs:__imp_WdLogSingleEntry2
0x1400cdda7  nop     dword ptr [rax+rax+00h]
0x1400cddac  mov     cs:WdLogGlobalForLineNumber, 10Eh
0x1400cddb6  lea     r9, aDxgkSegmentdes_1; "DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64"...
0x1400cddbd  mov     rax, [rdi+rsi+10h]
0x1400cddc2  jmp     loc_1400CE02A
0x1400cddc7  xor     r8d, r8d
0x1400cddca  mov     rdx, rbx
0x1400cddcd  mov     ecx, r12d
0x1400cddd0  call    cs:__imp_WdLogSingleEntry2
0x1400cddd7  nop     dword ptr [rax+rax+00h]
0x1400cdddc  mov     cs:WdLogGlobalForLineNumber, 105h
0x1400cdde6  lea     r9, aDxgkSegmentdes_0; "DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64"...
0x1400cdded  mov     rax, [rdi+rsi+10h]
0x1400cddf2  jmp     loc_1400CE02A
0x1400cddf7  mov     ecx, r12d
0x1400cddfa  call    cs:__imp_WdLogSingleEntry0
0x1400cde01  nop     dword ptr [rax+rax+00h]
0x1400cde06  mov     [rsp+88h+var_50], r15
0x1400cde0b  lea     r9, aSegmentWithSeg; "Segment with SegmentType=DXGK_SEGMENTTY"...
0x1400cde12  mov     eax, 0FCh
0x1400cde17  mov     [rsp+88h+var_58], r15
0x1400cde1c  mov     [rsp+88h+var_60], r15
0x1400cde21  mov     cs:WdLogGlobalForLineNumber, eax
0x1400cde27  mov     [rsp+88h+var_68], rax
0x1400cde2c  jmp     loc_1400CE03E
0x1400cde31  test    dl, 4
0x1400cde34  jz      short loc_1400CDE6D
0x1400cde36  mov     rdx, rbx
0x1400cde39  mov     ecx, r12d
0x1400cde3c  call    cs:__imp_WdLogSingleEntry1
0x1400cde43  nop     dword ptr [rax+rax+00h]
0x1400cde48  mov     [rsp+88h+var_50], r15
0x1400cde4d  lea     r9, aTheCpuvisibleF; "The CpuVisible flag cannot be set when "...
0x1400cde54  mov     [rsp+88h+var_58], r15
0x1400cde59  mov     [rsp+88h+var_60], r15
0x1400cde5e  mov     cs:WdLogGlobalForLineNumber, 14Ch
0x1400cde68  jmp     loc_1400CE039
0x1400cde6d  mov     rdx, rbx
0x1400cde70  mov     ecx, r12d
0x1400cde73  call    cs:__imp_WdLogSingleEntry1
0x1400cde7a  nop     dword ptr [rax+rax+00h]
0x1400cde7f  mov     [rsp+88h+var_50], r15
0x1400cde84  lea     r9, aTheCpuHostAper; "The CPU host aperture is not yet suppor"...
0x1400cde8b  mov     [rsp+88h+var_58], r15
0x1400cde90  mov     [rsp+88h+var_60], r15
0x1400cde95  mov     cs:WdLogGlobalForLineNumber, 156h
0x1400cde9f  jmp     loc_1400CE039
0x1400cdea4  mov     rdx, rbx
0x1400cdea7  mov     ecx, r12d
0x1400cdeaa  call    cs:__imp_WdLogSingleEntry1
0x1400cdeb1  nop     dword ptr [rax+rax+00h]
0x1400cdeb6  mov     [rsp+88h+var_50], r15
0x1400cdebb  lea     r9, aInvalidFlagsSp; "Invalid flags specified for segment #%d"
0x1400cdec2  mov     [rsp+88h+var_58], r15
0x1400cdec7  mov     [rsp+88h+var_60], r15
0x1400cdecc  mov     cs:WdLogGlobalForLineNumber, 142h
0x1400cded6  jmp     loc_1400CE039
0x1400cdedb  mov     rdx, rbx
0x1400cdede  mov     ecx, r12d
0x1400cdee1  call    cs:__imp_WdLogSingleEntry2
0x1400cdee8  nop     dword ptr [rax+rax+00h]
0x1400cdeed  mov     cs:WdLogGlobalForLineNumber, 131h
0x1400cdef7  lea     r9, aDxgkSegmentdes; "DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64"...
0x1400cdefe  mov     rax, [rdi+rsi+10h]
0x1400cdf03  jmp     loc_1400CE02A
0x1400cdf08  mov     rdx, rax
0x1400cdf0b  mov     ecx, r12d
0x1400cdf0e  call    cs:__imp_WdLogSingleEntry1
0x1400cdf15  nop     dword ptr [rax+rax+00h]
0x1400cdf1a  mov     [rsp+88h+var_50], r15
0x1400cdf1f  lea     r9, aSystemMemorySe; "System memory segments must specify Sla"...
0x1400cdf26  mov     [rsp+88h+var_58], r15
0x1400cdf2b  mov     cs:WdLogGlobalForLineNumber, 128h
0x1400cdf35  movsxd  rax, dword ptr [rdi+rsi+64h]
0x1400cdf3a  mov     [rsp+88h+var_60], r15
0x1400cdf3f  mov     [rsp+88h+var_68], rax
0x1400cdf44  jmp     loc_1400CE03E
0x1400cdf49  mov     ecx, r12d
0x1400cdf4c  call    cs:__imp_WdLogSingleEntry0
0x1400cdf53  nop     dword ptr [rax+rax+00h]
0x1400cdf58  mov     [rsp+88h+var_50], r15
0x1400cdf5d  lea     r9, aSegmentWithSeg_0; "Segment with SegmentType=DXGK_SEGMENTTY"...
0x1400cdf64  mov     eax, 120h
0x1400cdf69  mov     [rsp+88h+var_58], r15
0x1400cdf6e  mov     [rsp+88h+var_60], r15
0x1400cdf73  mov     cs:WdLogGlobalForLineNumber, eax
0x1400cdf79  mov     [rsp+88h+var_68], rax
0x1400cdf7e  jmp     loc_1400CE03E
0x1400cdf83  mov     rdx, rax
0x1400cdf86  mov     ecx, r12d
0x1400cdf89  call    cs:__imp_WdLogSingleEntry1
0x1400cdf90  nop     dword ptr [rax+rax+00h]
0x1400cdf95  mov     [rsp+88h+var_50], r15
0x1400cdf9a  lea     r9, aTooManyUefiFra; "Too many UEFI Frame Buffer Ranges speci"...
0x1400cdfa1  mov     [rsp+88h+var_58], r15
0x1400cdfa6  mov     cs:WdLogGlobalForLineNumber, 0E0h
0x1400cdfb0  mov     eax, [rdi+rsi+5Ch]
0x1400cdfb4  mov     [rsp+88h+var_60], r15
0x1400cdfb9  mov     [rsp+88h+var_68], rax
0x1400cdfbe  jmp     short loc_1400CE03E
0x1400cdfc0  mov     r8, rdx
0x1400cdfc3  mov     r9d, 40902Bh
0x1400cdfc9  mov     rdx, rbx
0x1400cdfcc  mov     ecx, r12d
0x1400cdfcf  call    cs:__imp_WdLogSingleEntry3
0x1400cdfd6  nop     dword ptr [rax+rax+00h]
0x1400cdfdb  mov     cs:WdLogGlobalForLineNumber, 0D5h
0x1400cdfe5  lea     r9, aInvalidValueFo_0; "Invalid value for DXGK_SEGMENTDESCRIPTO"...
0x1400cdfec  mov     eax, [rdi+rsi]
0x1400cdfef  mov     [rsp+88h+var_50], r15
0x1400cdff4  mov     [rsp+88h+var_58], 40902Bh
0x1400cdffd  jmp     short loc_1400CE034
0x1400cdfff  mov     r8, rcx
0x1400ce002  mov     rdx, rbx
0x1400ce005  mov     ecx, r12d
0x1400ce008  call    cs:__imp_WdLogSingleEntry2
0x1400ce00f  nop     dword ptr [rax+rax+00h]
0x1400ce014  mov     cs:WdLogGlobalForLineNumber, 0C6h
0x1400ce01e  lea     r9, aInvalidValueFo; "Invalid value for DXGK_SEGMENTDESCRIPTO"...
0x1400ce025  movsxd  rax, dword ptr [rdi+rsi+60h]
0x1400ce02a  mov     [rsp+88h+var_50], r15
0x1400ce02f  mov     [rsp+88h+var_58], r15
0x1400ce034  mov     [rsp+88h+var_60], rax
0x1400ce039  mov     [rsp+88h+var_68], rbx
0x1400ce03e  mov     edx, 40000h
0x1400ce043  call    DxgkLogInternalTriageEvent
0x1400ce048  xor     al, al
0x1400ce04a  jmp     short loc_1400CE0A2
0x1400ce04c  test    r9d, r9d
0x1400ce04f  jz      short loc_1400CE09F
0x1400ce051  add     r11w, r12w
0x1400ce055  movzx   eax, r11w
0x1400ce059  cmp     r9d, eax
0x1400ce05c  jz      short loc_1400CE09F
0x1400ce05e  mov     r8d, eax
0x1400ce061  mov     edx, r9d
0x1400ce064  mov     ecx, r12d
0x1400ce067  mov     edi, r9d
0x1400ce06a  mov     ebx, eax
0x1400ce06c  call    cs:__imp_WdLogSingleEntry2
0x1400ce073  nop     dword ptr [rax+rax+00h]
0x1400ce078  mov     [rsp+88h+var_50], r15
0x1400ce07d  lea     r9, aPagingbufferse; "PagingBufferSegmentId (%u) must be 0 (c"...
0x1400ce084  mov     [rsp+88h+var_58], r15
0x1400ce089  mov     [rsp+88h+var_60], rbx
0x1400ce08e  mov     [rsp+88h+var_68], rdi
0x1400ce093  mov     cs:WdLogGlobalForLineNumber, 165h
0x1400ce09d  jmp     short loc_1400CE03E
0x1400ce09f  mov     al, r12b
0x1400ce0a2  add     rsp, 50h
0x1400ce0a6  pop     r15
0x1400ce0a8  pop     r14
0x1400ce0aa  pop     r12
0x1400ce0ac  pop     rdi
0x1400ce0ad  pop     rsi
0x1400ce0ae  pop     rbp
0x1400ce0af  pop     rbx
0x1400ce0b0  retn
```
