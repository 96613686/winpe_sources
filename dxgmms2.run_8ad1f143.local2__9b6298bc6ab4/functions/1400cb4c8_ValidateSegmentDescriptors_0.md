# ValidateSegmentDescriptors_0

- ea: `0x1400cb4c8`
- end: `0x1400cb7da`
- name: `ValidateSegmentDescriptors_0`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400c9520`

## callees

- `0x1400045ec`
- `0x1400cb4c8`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400cb6ca`
- `watchdog!WdLogSingleEntry3` at `0x1400cb6ca`
- `watchdog!WdLogSingleEntry2` at `0x1400cb60e`
- `watchdog!WdLogSingleEntry2` at `0x1400cb70c`
- `watchdog!WdLogSingleEntry2` at `0x1400cb78b`
- `watchdog!WdLogSingleEntry2` at `0x1400cb60e`
- `watchdog!WdLogSingleEntry2` at `0x1400cb70c`
- `watchdog!WdLogSingleEntry2` at `0x1400cb78b`
- `watchdog!WdLogSingleEntry1` at `0x1400cb590`
- `watchdog!WdLogSingleEntry1` at `0x1400cb64b`
- `watchdog!WdLogSingleEntry1` at `0x1400cb673`
- `watchdog!WdLogSingleEntry1` at `0x1400cb69b`
- `watchdog!WdLogSingleEntry1` at `0x1400cb747`
- `watchdog!WdLogSingleEntry1` at `0x1400cb590`
- `watchdog!WdLogSingleEntry1` at `0x1400cb64b`
- `watchdog!WdLogSingleEntry1` at `0x1400cb673`
- `watchdog!WdLogSingleEntry1` at `0x1400cb69b`
- `watchdog!WdLogSingleEntry1` at `0x1400cb747`
- `dxgkrnl!DpiGetDriverVersion` at `0x1400cb4f0`
- `dxgkrnl!DpiGetDriverVersion` at `0x1400cb4f0`

## string_xrefs

- `0x1400cb6db`: `AperturePreservedDuringStandby flag cannot be specified unless DXGK_FEATURE_EXTENDED_SEGMENT_FLAGS Version (%u) >= %u. pSegmentDescriptor #%d`
- `0x1400cb659`: `The Aperture and CpuVisible flags cannot be set when SupportsCpuHostAperture is set. pSegmentDescriptor #%d`
- `0x1400cb681`: `AperturePreservedDuringStandby flag must also specify PreservedDuringStandby. pSegmentDescriptor #%d`
- `0x1400cb6a9`: `AperturePreservedDuringStandby flag must also specify Aperture. pSegmentDescriptor #%d`

## pseudocode

```c
char __fastcall ValidateSegmentDescriptors_0(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v5; // r15
  __int64 v7; // r14
  unsigned int DriverVersion; // r11d
  char v9; // r10
  unsigned int v10; // r9d
  unsigned int v11; // edi
  char result; // al
  __int64 v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // ecx
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // rax
  const wchar_t *v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rbx
  int v23; // ecx
  int v24; // r8d
  __int64 v25; // rbx
  int v26; // r8d
  int v27; // ecx
  int v28; // r8d
  int v29; // ecx
  int v30; // r8d

  v5 = a4;
  v7 = a3;
  DriverVersion = DpiGetDriverVersion(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 216LL));
  v9 = 0;
  v10 = 0;
  v11 = 0;
  result = 1;
  while ( v11 < (unsigned int)v7 )
  {
    v13 = 104LL * v11;
    if ( DriverVersion >= 0x7005 )
    {
      v14 = *(_DWORD *)(v13 + a2 + 92);
      if ( v14 > 1 )
      {
        WdLogSingleEntry1(1, *(unsigned int *)(v13 + a2 + 92));
        WdLogGlobalForLineNumber = 141;
        v20 = L"Too many UEFI Frame Buffer Ranges specified in a segment. Maximum allowed is 1. Driver reported %d";
        v19 = *(unsigned int *)(v13 + a2 + 92);
        goto LABEL_31;
      }
      if ( v14 )
      {
        if ( v9 )
        {
          v22 = v10;
          WdLogSingleEntry2(1, v10, v11);
          WdLogGlobalForLineNumber = 153;
          DxgkLogInternalTriageEvent(
            v23,
            0x40000,
            v24,
            (unsigned int)L"Only one segment can have UEFI Frame Buffer Ranges, driver reported at segment %d and %d",
            v22,
            v11,
            0,
            0);
          return 0;
        }
        v10 = v11;
        v9 = 1;
      }
    }
    else
    {
      *(_DWORD *)(v13 + a2 + 92) = 0;
    }
    v15 = *(_QWORD *)(v13 + a2 + 16);
    if ( (v15 & 0xFFF) != 0 )
    {
      WdLogSingleEntry2(1, v11, v15);
      WdLogGlobalForLineNumber = 168;
      DxgkLogInternalTriageEvent(
        v27,
        0x40000,
        v28,
        (unsigned int)L"Segment %u size (%I64u) must be page aligned",
        v11,
        *(_QWORD *)(v13 + a2 + 16),
        0,
        0);
      return 0;
    }
    v16 = *(_DWORD *)(v13 + a2);
    if ( v16 >= 0x800000 || (v16 & 2) != 0 )
    {
LABEL_14:
      WdLogSingleEntry1(1, v11);
      v19 = v11;
      v20 = L"Invalid flags specified for segment #%d";
      WdLogGlobalForLineNumber = 184;
LABEL_31:
      DxgkLogInternalTriageEvent(v17, 0x40000, v18, (_DWORD)v20, v19, 0, 0, 0);
      return 0;
    }
    if ( (v16 & 0x80u) != 0 )
    {
      if ( (*(_DWORD *)(v13 + a2) & 0x300) == 0x300 )
        goto LABEL_14;
    }
    else if ( (v16 & 0x300) != 0 )
    {
      goto LABEL_14;
    }
    if ( (v16 & 0x2000) != 0 && (v16 & 5) != 0 )
    {
      WdLogSingleEntry1(1, v11);
      v19 = v11;
      v20 = L"The Aperture and CpuVisible flags cannot be set when SupportsCpuHostAperture is set. pSegmentDescriptor #%d";
      WdLogGlobalForLineNumber = 192;
      goto LABEL_31;
    }
    if ( (v16 & 0x400000) != 0 )
    {
      v21 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 5158LL);
      result = 1;
      if ( !(_WORD)v21 )
      {
        v25 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 5158LL);
        WdLogSingleEntry3(1, v21, 1, v11);
        WdLogGlobalForLineNumber = 203;
        DxgkLogInternalTriageEvent(
          1,
          0x40000,
          v26,
          (unsigned int)L"AperturePreservedDuringStandby flag cannot be specified unless DXGK_FEATURE_EXTENDED_SEGMENT_FLA"
                         "GS Version (%u) >= %u. pSegmentDescriptor #%d",
          v25,
          1,
          v11,
          0);
        return 0;
      }
      if ( (v16 & 1) == 0 )
      {
        WdLogSingleEntry1(1, v11);
        v19 = v11;
        v20 = L"AperturePreservedDuringStandby flag must also specify Aperture. pSegmentDescriptor #%d";
        WdLogGlobalForLineNumber = 209;
        goto LABEL_31;
      }
      if ( (v16 & 0x80u) == 0 )
      {
        WdLogSingleEntry1(1, v11);
        v19 = v11;
        v20 = L"AperturePreservedDuringStandby flag must also specify PreservedDuringStandby. pSegmentDescriptor #%d";
        WdLogGlobalForLineNumber = 215;
        goto LABEL_31;
      }
    }
    else
    {
      result = 1;
    }
    ++v11;
  }
  if ( (unsigned int)v5 <= (unsigned int)v7 )
    return result;
  WdLogSingleEntry2(1, v5, v7);
  WdLogGlobalForLineNumber = 225;
  DxgkLogInternalTriageEvent(
    v29,
    0x40000,
    v30,
    (unsigned int)L"PagingBufferSegmentId (%u) must be less than or equal to the segment count (%u)",
    v5,
    v7,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x1400cb4c8  push    rbx
0x1400cb4ca  push    rbp
0x1400cb4cb  push    rsi
0x1400cb4cc  push    rdi
0x1400cb4cd  push    r12
0x1400cb4cf  push    r13
0x1400cb4d1  push    r14
0x1400cb4d3  push    r15
0x1400cb4d5  sub     rsp, 58h
0x1400cb4d9  mov     r13, rcx
0x1400cb4dc  mov     r15d, r9d
0x1400cb4df  mov     rcx, [rcx+18h]
0x1400cb4e3  mov     rbp, rdx
0x1400cb4e6  mov     r14d, r8d
0x1400cb4e9  mov     rcx, [rcx+0D8h]
0x1400cb4f0  call    cs:__imp_DpiGetDriverVersion
0x1400cb4f7  nop     dword ptr [rax+rax+00h]
0x1400cb4fc  xor     r12d, r12d
0x1400cb4ff  mov     edx, 300h
0x1400cb504  mov     r11d, eax
0x1400cb507  mov     r10b, r12b
0x1400cb50a  mov     r9d, r12d
0x1400cb50d  mov     edi, r12d
0x1400cb510  lea     eax, [r12+1]
0x1400cb515  cmp     edi, r14d
0x1400cb518  jnb     loc_1400CB77E
0x1400cb51e  mov     esi, edi
0x1400cb520  imul    rbx, rsi, 68h ; 'h'
0x1400cb524  cmp     r11d, 7005h
0x1400cb52b  jnb     short loc_1400CB534
0x1400cb52d  mov     [rbx+rbp+5Ch], r12d
0x1400cb532  jmp     short loc_1400CB55F
0x1400cb534  mov     eax, [rbx+rbp+5Ch]
0x1400cb538  mov     ecx, 1
0x1400cb53d  cmp     eax, ecx
0x1400cb53f  ja      loc_1400CB744
0x1400cb545  test    eax, eax
0x1400cb547  jz      short loc_1400CB55C
0x1400cb549  test    r10b, r10b
0x1400cb54c  jnz     loc_1400CB605
0x1400cb552  mov     eax, ecx
0x1400cb554  mov     r9d, edi
0x1400cb557  mov     r10b, al
0x1400cb55a  jmp     short loc_1400CB55F
0x1400cb55c  mov     rax, rcx
0x1400cb55f  mov     r8, [rbx+rbp+10h]
0x1400cb564  test    r8, 0FFFh
0x1400cb56b  jnz     loc_1400CB707
0x1400cb571  mov     ecx, [rbx+rbp]
0x1400cb574  cmp     ecx, 800000h
0x1400cb57a  jnb     short loc_1400CB589
0x1400cb57c  test    cl, 2
0x1400cb57f  jnz     short loc_1400CB589
0x1400cb581  test    cl, cl
0x1400cb583  js      short loc_1400CB5B4
0x1400cb585  test    edx, ecx
0x1400cb587  jz      short loc_1400CB5BC
0x1400cb589  mov     edx, edi
0x1400cb58b  mov     ecx, 1
0x1400cb590  call    cs:__imp_WdLogSingleEntry1
0x1400cb597  nop     dword ptr [rax+rax+00h]
0x1400cb59c  mov     eax, edi
0x1400cb59e  lea     r9, aInvalidFlagsSp; "Invalid flags specified for segment #%d"
0x1400cb5a5  mov     cs:WdLogGlobalForLineNumber, 0B8h
0x1400cb5af  jmp     loc_1400CB768
0x1400cb5b4  mov     eax, ecx
0x1400cb5b6  and     eax, edx
0x1400cb5b8  cmp     eax, edx
0x1400cb5ba  jz      short loc_1400CB589
0x1400cb5bc  bt      ecx, 0Dh
0x1400cb5c0  jnb     short loc_1400CB5C7
0x1400cb5c2  test    cl, 5
0x1400cb5c5  jnz     short loc_1400CB644
0x1400cb5c7  bt      ecx, 16h
0x1400cb5cb  jnb     short loc_1400CB5FE
0x1400cb5cd  mov     rax, [r13+18h]
0x1400cb5d1  movzx   edx, word ptr [rax+1426h]
0x1400cb5d8  mov     eax, 1
0x1400cb5dd  cmp     dx, ax
0x1400cb5e0  jb      loc_1400CB6BF
0x1400cb5e6  test    al, cl
0x1400cb5e8  jz      loc_1400CB697
0x1400cb5ee  test    cl, cl
0x1400cb5f0  jns     short loc_1400CB66F
0x1400cb5f2  mov     edx, 300h
0x1400cb5f7  add     edi, eax
0x1400cb5f9  jmp     loc_1400CB515
0x1400cb5fe  mov     eax, 1
0x1400cb603  jmp     short loc_1400CB5F7
0x1400cb605  mov     r8, rsi
0x1400cb608  mov     edx, r9d
0x1400cb60b  mov     ebx, r9d
0x1400cb60e  call    cs:__imp_WdLogSingleEntry2
0x1400cb615  nop     dword ptr [rax+rax+00h]
0x1400cb61a  mov     [rsp+98h+var_60], r12
0x1400cb61f  lea     r9, aOnlyOneSegment_0; "Only one segment can have UEFI Frame Bu"...
0x1400cb626  mov     [rsp+98h+var_68], r12
0x1400cb62b  mov     [rsp+98h+var_70], rsi
0x1400cb630  mov     [rsp+98h+var_78], rbx
0x1400cb635  mov     cs:WdLogGlobalForLineNumber, 99h
0x1400cb63f  jmp     loc_1400CB7BC
0x1400cb644  mov     edx, edi
0x1400cb646  mov     ecx, 1
0x1400cb64b  call    cs:__imp_WdLogSingleEntry1
0x1400cb652  nop     dword ptr [rax+rax+00h]
0x1400cb657  mov     eax, edi
0x1400cb659  lea     r9, aTheApertureAnd; "The Aperture and CpuVisible flags canno"...
0x1400cb660  mov     cs:WdLogGlobalForLineNumber, 0C0h
0x1400cb66a  jmp     loc_1400CB768
0x1400cb66f  mov     edx, edi
0x1400cb671  mov     ecx, eax
0x1400cb673  call    cs:__imp_WdLogSingleEntry1
0x1400cb67a  nop     dword ptr [rax+rax+00h]
0x1400cb67f  mov     eax, edi
0x1400cb681  lea     r9, aAperturepreser; "AperturePreservedDuringStandby flag mus"...
0x1400cb688  mov     cs:WdLogGlobalForLineNumber, 0D7h
0x1400cb692  jmp     loc_1400CB768
0x1400cb697  mov     edx, edi
0x1400cb699  mov     ecx, eax
0x1400cb69b  call    cs:__imp_WdLogSingleEntry1
0x1400cb6a2  nop     dword ptr [rax+rax+00h]
0x1400cb6a7  mov     eax, edi
0x1400cb6a9  lea     r9, aAperturepreser_0; "AperturePreservedDuringStandby flag mus"...
0x1400cb6b0  mov     cs:WdLogGlobalForLineNumber, 0D1h
0x1400cb6ba  jmp     loc_1400CB768
0x1400cb6bf  mov     r9d, edi
0x1400cb6c2  mov     r8, rax
0x1400cb6c5  mov     ecx, eax
0x1400cb6c7  mov     rbx, rdx
0x1400cb6ca  call    cs:__imp_WdLogSingleEntry3
0x1400cb6d1  nop     dword ptr [rax+rax+00h]
0x1400cb6d6  mov     [rsp+98h+var_60], r12
0x1400cb6db  lea     r9, aAperturepreser_1; "AperturePreservedDuringStandby flag can"...
0x1400cb6e2  mov     eax, edi
0x1400cb6e4  mov     ecx, 1
0x1400cb6e9  mov     [rsp+98h+var_68], rax
0x1400cb6ee  mov     [rsp+98h+var_70], rcx
0x1400cb6f3  mov     [rsp+98h+var_78], rbx
0x1400cb6f8  mov     cs:WdLogGlobalForLineNumber, 0CBh
0x1400cb702  jmp     loc_1400CB7BC
0x1400cb707  mov     rdx, rsi
0x1400cb70a  mov     ecx, eax
0x1400cb70c  call    cs:__imp_WdLogSingleEntry2
0x1400cb713  nop     dword ptr [rax+rax+00h]
0x1400cb718  mov     [rsp+98h+var_60], r12
0x1400cb71d  lea     r9, aSegmentUSizeI6; "Segment %u size (%I64u) must be page al"...
0x1400cb724  mov     [rsp+98h+var_68], r12
0x1400cb729  mov     cs:WdLogGlobalForLineNumber, 0A8h
0x1400cb733  mov     rax, [rbx+rbp+10h]
0x1400cb738  mov     [rsp+98h+var_70], rax
0x1400cb73d  mov     [rsp+98h+var_78], rsi
0x1400cb742  jmp     short loc_1400CB7BC
0x1400cb744  mov     rdx, rax
0x1400cb747  call    cs:__imp_WdLogSingleEntry1
0x1400cb74e  nop     dword ptr [rax+rax+00h]
0x1400cb753  mov     cs:WdLogGlobalForLineNumber, 8Dh
0x1400cb75d  lea     r9, aTooManyUefiFra; "Too many UEFI Frame Buffer Ranges speci"...
0x1400cb764  mov     eax, [rbx+rbp+5Ch]
0x1400cb768  mov     [rsp+98h+var_60], r12
0x1400cb76d  mov     [rsp+98h+var_68], r12
0x1400cb772  mov     [rsp+98h+var_70], r12
0x1400cb777  mov     [rsp+98h+var_78], rax
0x1400cb77c  jmp     short loc_1400CB7BC
0x1400cb77e  cmp     r15d, r14d
0x1400cb781  jbe     short loc_1400CB7C8
0x1400cb783  mov     r8, r14
0x1400cb786  mov     rdx, r15
0x1400cb789  mov     ecx, eax
0x1400cb78b  call    cs:__imp_WdLogSingleEntry2
0x1400cb792  nop     dword ptr [rax+rax+00h]
0x1400cb797  mov     [rsp+98h+var_60], r12
0x1400cb79c  lea     r9, aPagingbufferse_1; "PagingBufferSegmentId (%u) must be less"...
0x1400cb7a3  mov     [rsp+98h+var_68], r12
0x1400cb7a8  mov     [rsp+98h+var_70], r14
0x1400cb7ad  mov     [rsp+98h+var_78], r15
0x1400cb7b2  mov     cs:WdLogGlobalForLineNumber, 0E1h
0x1400cb7bc  mov     edx, 40000h
0x1400cb7c1  call    DxgkLogInternalTriageEvent
0x1400cb7c6  xor     al, al
0x1400cb7c8  add     rsp, 58h
0x1400cb7cc  pop     r15
0x1400cb7ce  pop     r14
0x1400cb7d0  pop     r13
0x1400cb7d2  pop     r12
0x1400cb7d4  pop     rdi
0x1400cb7d5  pop     rsi
0x1400cb7d6  pop     rbp
0x1400cb7d7  pop     rbx
0x1400cb7d8  retn
```
