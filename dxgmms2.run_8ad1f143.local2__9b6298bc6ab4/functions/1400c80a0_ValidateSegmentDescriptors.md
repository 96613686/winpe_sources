# ValidateSegmentDescriptors

- ea: `0x1400c80a0`
- end: `0x1400c8552`
- name: `ValidateSegmentDescriptors`
- size: `1202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400c5eac`

## callees

- `0x1400045ec`
- `0x1400c80a0`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400c846f`
- `watchdog!WdLogSingleEntry3` at `0x1400c846f`
- `watchdog!WdLogSingleEntry2` at `0x1400c8167`
- `watchdog!WdLogSingleEntry2` at `0x1400c8209`
- `watchdog!WdLogSingleEntry2` at `0x1400c8240`
- `watchdog!WdLogSingleEntry2` at `0x1400c8270`
- `watchdog!WdLogSingleEntry2` at `0x1400c8381`
- `watchdog!WdLogSingleEntry2` at `0x1400c84a8`
- `watchdog!WdLogSingleEntry2` at `0x1400c850c`
- `watchdog!WdLogSingleEntry2` at `0x1400c8167`
- `watchdog!WdLogSingleEntry2` at `0x1400c8209`
- `watchdog!WdLogSingleEntry2` at `0x1400c8240`
- `watchdog!WdLogSingleEntry2` at `0x1400c8270`
- `watchdog!WdLogSingleEntry2` at `0x1400c8381`
- `watchdog!WdLogSingleEntry2` at `0x1400c84a8`
- `watchdog!WdLogSingleEntry2` at `0x1400c850c`
- `watchdog!WdLogSingleEntry0` at `0x1400c829a`
- `watchdog!WdLogSingleEntry0` at `0x1400c83ec`
- `watchdog!WdLogSingleEntry0` at `0x1400c829a`
- `watchdog!WdLogSingleEntry0` at `0x1400c83ec`
- `watchdog!WdLogSingleEntry1` at `0x1400c82dc`
- `watchdog!WdLogSingleEntry1` at `0x1400c8313`
- `watchdog!WdLogSingleEntry1` at `0x1400c834a`
- `watchdog!WdLogSingleEntry1` at `0x1400c83ae`
- `watchdog!WdLogSingleEntry1` at `0x1400c8429`
- `watchdog!WdLogSingleEntry1` at `0x1400c82dc`
- `watchdog!WdLogSingleEntry1` at `0x1400c8313`
- `watchdog!WdLogSingleEntry1` at `0x1400c834a`
- `watchdog!WdLogSingleEntry1` at `0x1400c83ae`
- `watchdog!WdLogSingleEntry1` at `0x1400c8429`

## string_xrefs

- `0x1400c8485`: `Invalid value for DXGK_SEGMENTDESCRIPTOR5[%u]::Flags. Value (%u) cannot contain the bits (%u), or set reserved bits`
- `0x1400c84be`: `Invalid value for DXGK_SEGMENTDESCRIPTOR5[%u]::SegmentType (%u)`
- `0x1400c8286`: `DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64u) cannot be 0`
- `0x1400c817d`: `DXGK_SEGMENTDESCRIPTOR5[%u]::SlabSize cannot exceed 128MB (DXGK_PAGESIZE_128MB)`
- `0x1400c8256`: `DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64u) must be page aligned`
- `0x1400c8397`: `DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64u) must be zero for system memory segments`
- `0x1400c8324`: `The CPU host aperture is not yet supported in PBMM. pSegmentDescriptor #%d`
- `0x1400c82ed`: `The CpuVisible flag cannot be set when SupportsCpuHostAperture is set. pSegmentDescriptor #%d`

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
0x1400c80a0  push    rbx
0x1400c80a2  push    rbp
0x1400c80a3  push    rsi
0x1400c80a4  push    rdi
0x1400c80a5  push    r12
0x1400c80a7  push    r14
0x1400c80a9  push    r15
0x1400c80ab  sub     rsp, 50h
0x1400c80af  xor     r15d, r15d
0x1400c80b2  mov     r14d, r8d
0x1400c80b5  mov     r8d, 0FFFFh
0x1400c80bb  mov     rsi, rdx
0x1400c80be  movzx   ebp, r8w
0x1400c80c2  movzx   r11d, r8w
0x1400c80c6  mov     r10d, r15d
0x1400c80c9  lea     r12d, [r15+1]
0x1400c80cd  movzx   eax, r10w
0x1400c80d1  cmp     eax, r14d
0x1400c80d4  jnb     loc_1400C84EC
0x1400c80da  movzx   ebx, r10w
0x1400c80de  imul    rdi, rbx, 68h ; 'h'
0x1400c80e2  movsxd  rcx, dword ptr [rdi+rsi+60h]
0x1400c80e7  cmp     ecx, r12d
0x1400c80ea  jg      loc_1400C849F
0x1400c80f0  mov     edx, [rdi+rsi]
0x1400c80f3  test    edx, 40902Bh
0x1400c80f9  jnz     loc_1400C8460
0x1400c80ff  cmp     edx, 800000h
0x1400c8105  jnb     loc_1400C8460
0x1400c810b  mov     eax, [rdi+rsi+5Ch]
0x1400c810f  cmp     eax, r12d
0x1400c8112  ja      loc_1400C8423
0x1400c8118  test    eax, eax
0x1400c811a  jz      short loc_1400C812A
0x1400c811c  cmp     bp, r8w
0x1400c8120  jnz     loc_1400C81F6
0x1400c8126  movzx   ebp, r10w
0x1400c812a  cmp     ecx, r12d
0x1400c812d  jnz     short loc_1400C818E
0x1400c812f  test    r10w, r10w
0x1400c8133  jz      loc_1400C8297
0x1400c8139  mov     r8, [rdi+rsi+10h]
0x1400c813e  test    r8, r8
0x1400c8141  jz      loc_1400C8267
0x1400c8147  test    r8, 0FFFh
0x1400c814e  jnz     loc_1400C823A
0x1400c8154  movsxd  rax, dword ptr [rdi+rsi+64h]
0x1400c8159  cmp     eax, 0Fh
0x1400c815c  jle     short loc_1400C81B7
0x1400c815e  mov     r8, rax
0x1400c8161  mov     rdx, rbx
0x1400c8164  mov     ecx, r12d
0x1400c8167  call    cs:__imp_WdLogSingleEntry2
0x1400c816e  nop     dword ptr [rax+rax+00h]
0x1400c8173  mov     cs:WdLogGlobalForLineNumber, 117h
0x1400c817d  lea     r9, aDxgkSegmentdes_2; "DXGK_SEGMENTDESCRIPTOR5[%u]::SlabSize c"...
0x1400c8184  movsxd  rax, dword ptr [rdi+rsi+64h]
0x1400c8189  jmp     loc_1400C84CA
0x1400c818e  test    r10w, r10w
0x1400c8192  jnz     loc_1400C83E9
0x1400c8198  movsxd  rax, dword ptr [rdi+rsi+64h]
0x1400c819d  cmp     eax, 0FFFFFFFFh
0x1400c81a0  jnz     loc_1400C83A8
0x1400c81a6  mov     r8, [rdi+rsi+10h]
0x1400c81ab  test    r8, r8
0x1400c81ae  jnz     loc_1400C837B
0x1400c81b4  mov     r11d, r15d
0x1400c81b7  test    dl, dl
0x1400c81b9  js      short loc_1400C81C7
0x1400c81bb  test    edx, 300h
0x1400c81c1  jnz     loc_1400C8344
0x1400c81c7  bt      edx, 9
0x1400c81cb  setb    cl
0x1400c81ce  bt      edx, 8
0x1400c81d2  setb    al
0x1400c81d5  test    al, cl
0x1400c81d7  jnz     loc_1400C8344
0x1400c81dd  bt      edx, 0Dh
0x1400c81e1  jb      loc_1400C82D1
0x1400c81e7  add     r10w, r12w
0x1400c81eb  mov     r8d, 0FFFFh
0x1400c81f1  jmp     loc_1400C80CD
0x1400c81f6  lea     rdi, [rbx+1]
0x1400c81fa  mov     ecx, r12d
0x1400c81fd  movzx   ebx, bp
0x1400c8200  mov     r8, rdi
0x1400c8203  inc     rbx
0x1400c8206  mov     rdx, rbx
0x1400c8209  call    cs:__imp_WdLogSingleEntry2
0x1400c8210  nop     dword ptr [rax+rax+00h]
0x1400c8215  mov     [rsp+88h+var_50], r15
0x1400c821a  lea     r9, aOnlyOneSegment; "Only one segment can have UEFI Frame Bu"...
0x1400c8221  mov     [rsp+88h+var_58], r15
0x1400c8226  mov     [rsp+88h+var_60], rdi
0x1400c822b  mov     cs:WdLogGlobalForLineNumber, 0EDh
0x1400c8235  jmp     loc_1400C84D9
0x1400c823a  mov     rdx, rbx
0x1400c823d  mov     ecx, r12d
0x1400c8240  call    cs:__imp_WdLogSingleEntry2
0x1400c8247  nop     dword ptr [rax+rax+00h]
0x1400c824c  mov     cs:WdLogGlobalForLineNumber, 10Eh
0x1400c8256  lea     r9, aDxgkSegmentdes_1; "DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64"...
0x1400c825d  mov     rax, [rdi+rsi+10h]
0x1400c8262  jmp     loc_1400C84CA
0x1400c8267  xor     r8d, r8d
0x1400c826a  mov     rdx, rbx
0x1400c826d  mov     ecx, r12d
0x1400c8270  call    cs:__imp_WdLogSingleEntry2
0x1400c8277  nop     dword ptr [rax+rax+00h]
0x1400c827c  mov     cs:WdLogGlobalForLineNumber, 105h
0x1400c8286  lea     r9, aDxgkSegmentdes_0; "DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64"...
0x1400c828d  mov     rax, [rdi+rsi+10h]
0x1400c8292  jmp     loc_1400C84CA
0x1400c8297  mov     ecx, r12d
0x1400c829a  call    cs:__imp_WdLogSingleEntry0
0x1400c82a1  nop     dword ptr [rax+rax+00h]
0x1400c82a6  mov     [rsp+88h+var_50], r15
0x1400c82ab  lea     r9, aSegmentWithSeg; "Segment with SegmentType=DXGK_SEGMENTTY"...
0x1400c82b2  mov     eax, 0FCh
0x1400c82b7  mov     [rsp+88h+var_58], r15
0x1400c82bc  mov     [rsp+88h+var_60], r15
0x1400c82c1  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c82c7  mov     [rsp+88h+var_68], rax
0x1400c82cc  jmp     loc_1400C84DE
0x1400c82d1  test    dl, 4
0x1400c82d4  jz      short loc_1400C830D
0x1400c82d6  mov     rdx, rbx
0x1400c82d9  mov     ecx, r12d
0x1400c82dc  call    cs:__imp_WdLogSingleEntry1
0x1400c82e3  nop     dword ptr [rax+rax+00h]
0x1400c82e8  mov     [rsp+88h+var_50], r15
0x1400c82ed  lea     r9, aTheCpuvisibleF; "The CpuVisible flag cannot be set when "...
0x1400c82f4  mov     [rsp+88h+var_58], r15
0x1400c82f9  mov     [rsp+88h+var_60], r15
0x1400c82fe  mov     cs:WdLogGlobalForLineNumber, 14Ch
0x1400c8308  jmp     loc_1400C84D9
0x1400c830d  mov     rdx, rbx
0x1400c8310  mov     ecx, r12d
0x1400c8313  call    cs:__imp_WdLogSingleEntry1
0x1400c831a  nop     dword ptr [rax+rax+00h]
0x1400c831f  mov     [rsp+88h+var_50], r15
0x1400c8324  lea     r9, aTheCpuHostAper; "The CPU host aperture is not yet suppor"...
0x1400c832b  mov     [rsp+88h+var_58], r15
0x1400c8330  mov     [rsp+88h+var_60], r15
0x1400c8335  mov     cs:WdLogGlobalForLineNumber, 156h
0x1400c833f  jmp     loc_1400C84D9
0x1400c8344  mov     rdx, rbx
0x1400c8347  mov     ecx, r12d
0x1400c834a  call    cs:__imp_WdLogSingleEntry1
0x1400c8351  nop     dword ptr [rax+rax+00h]
0x1400c8356  mov     [rsp+88h+var_50], r15
0x1400c835b  lea     r9, aInvalidFlagsSp; "Invalid flags specified for segment #%d"
0x1400c8362  mov     [rsp+88h+var_58], r15
0x1400c8367  mov     [rsp+88h+var_60], r15
0x1400c836c  mov     cs:WdLogGlobalForLineNumber, 142h
0x1400c8376  jmp     loc_1400C84D9
0x1400c837b  mov     rdx, rbx
0x1400c837e  mov     ecx, r12d
0x1400c8381  call    cs:__imp_WdLogSingleEntry2
0x1400c8388  nop     dword ptr [rax+rax+00h]
0x1400c838d  mov     cs:WdLogGlobalForLineNumber, 131h
0x1400c8397  lea     r9, aDxgkSegmentdes; "DXGK_SEGMENTDESCRIPTOR5[%u]::Size (%I64"...
0x1400c839e  mov     rax, [rdi+rsi+10h]
0x1400c83a3  jmp     loc_1400C84CA
0x1400c83a8  mov     rdx, rax
0x1400c83ab  mov     ecx, r12d
0x1400c83ae  call    cs:__imp_WdLogSingleEntry1
0x1400c83b5  nop     dword ptr [rax+rax+00h]
0x1400c83ba  mov     [rsp+88h+var_50], r15
0x1400c83bf  lea     r9, aSystemMemorySe; "System memory segments must specify Sla"...
0x1400c83c6  mov     [rsp+88h+var_58], r15
0x1400c83cb  mov     cs:WdLogGlobalForLineNumber, 128h
0x1400c83d5  movsxd  rax, dword ptr [rdi+rsi+64h]
0x1400c83da  mov     [rsp+88h+var_60], r15
0x1400c83df  mov     [rsp+88h+var_68], rax
0x1400c83e4  jmp     loc_1400C84DE
0x1400c83e9  mov     ecx, r12d
0x1400c83ec  call    cs:__imp_WdLogSingleEntry0
0x1400c83f3  nop     dword ptr [rax+rax+00h]
0x1400c83f8  mov     [rsp+88h+var_50], r15
0x1400c83fd  lea     r9, aSegmentWithSeg_0; "Segment with SegmentType=DXGK_SEGMENTTY"...
0x1400c8404  mov     eax, 120h
0x1400c8409  mov     [rsp+88h+var_58], r15
0x1400c840e  mov     [rsp+88h+var_60], r15
0x1400c8413  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c8419  mov     [rsp+88h+var_68], rax
0x1400c841e  jmp     loc_1400C84DE
0x1400c8423  mov     rdx, rax
0x1400c8426  mov     ecx, r12d
0x1400c8429  call    cs:__imp_WdLogSingleEntry1
0x1400c8430  nop     dword ptr [rax+rax+00h]
0x1400c8435  mov     [rsp+88h+var_50], r15
0x1400c843a  lea     r9, aTooManyUefiFra; "Too many UEFI Frame Buffer Ranges speci"...
0x1400c8441  mov     [rsp+88h+var_58], r15
0x1400c8446  mov     cs:WdLogGlobalForLineNumber, 0E0h
0x1400c8450  mov     eax, [rdi+rsi+5Ch]
0x1400c8454  mov     [rsp+88h+var_60], r15
0x1400c8459  mov     [rsp+88h+var_68], rax
0x1400c845e  jmp     short loc_1400C84DE
0x1400c8460  mov     r8, rdx
0x1400c8463  mov     r9d, 40902Bh
0x1400c8469  mov     rdx, rbx
0x1400c846c  mov     ecx, r12d
0x1400c846f  call    cs:__imp_WdLogSingleEntry3
0x1400c8476  nop     dword ptr [rax+rax+00h]
0x1400c847b  mov     cs:WdLogGlobalForLineNumber, 0D5h
0x1400c8485  lea     r9, aInvalidValueFo_0; "Invalid value for DXGK_SEGMENTDESCRIPTO"...
0x1400c848c  mov     eax, [rdi+rsi]
0x1400c848f  mov     [rsp+88h+var_50], r15
0x1400c8494  mov     [rsp+88h+var_58], 40902Bh
0x1400c849d  jmp     short loc_1400C84D4
0x1400c849f  mov     r8, rcx
0x1400c84a2  mov     rdx, rbx
0x1400c84a5  mov     ecx, r12d
0x1400c84a8  call    cs:__imp_WdLogSingleEntry2
0x1400c84af  nop     dword ptr [rax+rax+00h]
0x1400c84b4  mov     cs:WdLogGlobalForLineNumber, 0C6h
0x1400c84be  lea     r9, aInvalidValueFo; "Invalid value for DXGK_SEGMENTDESCRIPTO"...
0x1400c84c5  movsxd  rax, dword ptr [rdi+rsi+60h]
0x1400c84ca  mov     [rsp+88h+var_50], r15
0x1400c84cf  mov     [rsp+88h+var_58], r15
0x1400c84d4  mov     [rsp+88h+var_60], rax
0x1400c84d9  mov     [rsp+88h+var_68], rbx
0x1400c84de  mov     edx, 40000h
0x1400c84e3  call    DxgkLogInternalTriageEvent
0x1400c84e8  xor     al, al
0x1400c84ea  jmp     short loc_1400C8542
0x1400c84ec  test    r9d, r9d
0x1400c84ef  jz      short loc_1400C853F
0x1400c84f1  add     r11w, r12w
0x1400c84f5  movzx   eax, r11w
0x1400c84f9  cmp     r9d, eax
0x1400c84fc  jz      short loc_1400C853F
0x1400c84fe  mov     r8d, eax
0x1400c8501  mov     edx, r9d
0x1400c8504  mov     ecx, r12d
0x1400c8507  mov     edi, r9d
0x1400c850a  mov     ebx, eax
0x1400c850c  call    cs:__imp_WdLogSingleEntry2
0x1400c8513  nop     dword ptr [rax+rax+00h]
0x1400c8518  mov     [rsp+88h+var_50], r15
0x1400c851d  lea     r9, aPagingbufferse; "PagingBufferSegmentId (%u) must be 0 (c"...
0x1400c8524  mov     [rsp+88h+var_58], r15
0x1400c8529  mov     [rsp+88h+var_60], rbx
0x1400c852e  mov     [rsp+88h+var_68], rdi
0x1400c8533  mov     cs:WdLogGlobalForLineNumber, 165h
0x1400c853d  jmp     short loc_1400C84DE
0x1400c853f  mov     al, r12b
0x1400c8542  add     rsp, 50h
0x1400c8546  pop     r15
0x1400c8548  pop     r14
0x1400c854a  pop     r12
0x1400c854c  pop     rdi
0x1400c854d  pop     rsi
0x1400c854e  pop     rbp
0x1400c854f  pop     rbx
0x1400c8550  retn
```
