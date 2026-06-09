# ValidateSegmentDescriptors_0

- ea: `0x1400d13d8`
- end: `0x1400d16ea`
- name: `ValidateSegmentDescriptors_0`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400cf3ac`

## callees

- `0x140004268`
- `0x1400d13d8`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400d15da`
- `watchdog!WdLogSingleEntry3` at `0x1400d15da`
- `watchdog!WdLogSingleEntry2` at `0x1400d151e`
- `watchdog!WdLogSingleEntry2` at `0x1400d161c`
- `watchdog!WdLogSingleEntry2` at `0x1400d169b`
- `watchdog!WdLogSingleEntry2` at `0x1400d151e`
- `watchdog!WdLogSingleEntry2` at `0x1400d161c`
- `watchdog!WdLogSingleEntry2` at `0x1400d169b`
- `watchdog!WdLogSingleEntry1` at `0x1400d14a0`
- `watchdog!WdLogSingleEntry1` at `0x1400d155b`
- `watchdog!WdLogSingleEntry1` at `0x1400d1583`
- `watchdog!WdLogSingleEntry1` at `0x1400d15ab`
- `watchdog!WdLogSingleEntry1` at `0x1400d1657`
- `watchdog!WdLogSingleEntry1` at `0x1400d14a0`
- `watchdog!WdLogSingleEntry1` at `0x1400d155b`
- `watchdog!WdLogSingleEntry1` at `0x1400d1583`
- `watchdog!WdLogSingleEntry1` at `0x1400d15ab`
- `watchdog!WdLogSingleEntry1` at `0x1400d1657`
- `dxgkrnl!DpiGetDriverVersion` at `0x1400d1400`
- `dxgkrnl!DpiGetDriverVersion` at `0x1400d1400`

## string_xrefs

- `0x1400d15eb`: `AperturePreservedDuringStandby flag cannot be specified unless DXGK_FEATURE_EXTENDED_SEGMENT_FLAGS Version (%u) >= %u. pSegmentDescriptor #%d`
- `0x1400d1569`: `The Aperture and CpuVisible flags cannot be set when SupportsCpuHostAperture is set. pSegmentDescriptor #%d`
- `0x1400d1591`: `AperturePreservedDuringStandby flag must also specify PreservedDuringStandby. pSegmentDescriptor #%d`
- `0x1400d15b9`: `AperturePreservedDuringStandby flag must also specify Aperture. pSegmentDescriptor #%d`

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
      v21 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 5174LL);
      result = 1;
      if ( !(_WORD)v21 )
      {
        v25 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 5174LL);
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
0x1400d13d8  push    rbx
0x1400d13da  push    rbp
0x1400d13db  push    rsi
0x1400d13dc  push    rdi
0x1400d13dd  push    r12
0x1400d13df  push    r13
0x1400d13e1  push    r14
0x1400d13e3  push    r15
0x1400d13e5  sub     rsp, 58h
0x1400d13e9  mov     r13, rcx
0x1400d13ec  mov     r15d, r9d
0x1400d13ef  mov     rcx, [rcx+18h]
0x1400d13f3  mov     rbp, rdx
0x1400d13f6  mov     r14d, r8d
0x1400d13f9  mov     rcx, [rcx+0D8h]
0x1400d1400  call    cs:__imp_DpiGetDriverVersion
0x1400d1407  nop     dword ptr [rax+rax+00h]
0x1400d140c  xor     r12d, r12d
0x1400d140f  mov     edx, 300h
0x1400d1414  mov     r11d, eax
0x1400d1417  mov     r10b, r12b
0x1400d141a  mov     r9d, r12d
0x1400d141d  mov     edi, r12d
0x1400d1420  lea     eax, [r12+1]
0x1400d1425  cmp     edi, r14d
0x1400d1428  jnb     loc_1400D168E
0x1400d142e  mov     esi, edi
0x1400d1430  imul    rbx, rsi, 68h ; 'h'
0x1400d1434  cmp     r11d, 7005h
0x1400d143b  jnb     short loc_1400D1444
0x1400d143d  mov     [rbx+rbp+5Ch], r12d
0x1400d1442  jmp     short loc_1400D146F
0x1400d1444  mov     eax, [rbx+rbp+5Ch]
0x1400d1448  mov     ecx, 1
0x1400d144d  cmp     eax, ecx
0x1400d144f  ja      loc_1400D1654
0x1400d1455  test    eax, eax
0x1400d1457  jz      short loc_1400D146C
0x1400d1459  test    r10b, r10b
0x1400d145c  jnz     loc_1400D1515
0x1400d1462  mov     eax, ecx
0x1400d1464  mov     r9d, edi
0x1400d1467  mov     r10b, al
0x1400d146a  jmp     short loc_1400D146F
0x1400d146c  mov     rax, rcx
0x1400d146f  mov     r8, [rbx+rbp+10h]
0x1400d1474  test    r8, 0FFFh
0x1400d147b  jnz     loc_1400D1617
0x1400d1481  mov     ecx, [rbx+rbp]
0x1400d1484  cmp     ecx, 800000h
0x1400d148a  jnb     short loc_1400D1499
0x1400d148c  test    cl, 2
0x1400d148f  jnz     short loc_1400D1499
0x1400d1491  test    cl, cl
0x1400d1493  js      short loc_1400D14C4
0x1400d1495  test    edx, ecx
0x1400d1497  jz      short loc_1400D14CC
0x1400d1499  mov     edx, edi
0x1400d149b  mov     ecx, 1
0x1400d14a0  call    cs:__imp_WdLogSingleEntry1
0x1400d14a7  nop     dword ptr [rax+rax+00h]
0x1400d14ac  mov     eax, edi
0x1400d14ae  lea     r9, aInvalidFlagsSp; "Invalid flags specified for segment #%d"
0x1400d14b5  mov     cs:WdLogGlobalForLineNumber, 0B8h
0x1400d14bf  jmp     loc_1400D1678
0x1400d14c4  mov     eax, ecx
0x1400d14c6  and     eax, edx
0x1400d14c8  cmp     eax, edx
0x1400d14ca  jz      short loc_1400D1499
0x1400d14cc  bt      ecx, 0Dh
0x1400d14d0  jnb     short loc_1400D14D7
0x1400d14d2  test    cl, 5
0x1400d14d5  jnz     short loc_1400D1554
0x1400d14d7  bt      ecx, 16h
0x1400d14db  jnb     short loc_1400D150E
0x1400d14dd  mov     rax, [r13+18h]
0x1400d14e1  movzx   edx, word ptr [rax+1436h]
0x1400d14e8  mov     eax, 1
0x1400d14ed  cmp     dx, ax
0x1400d14f0  jb      loc_1400D15CF
0x1400d14f6  test    al, cl
0x1400d14f8  jz      loc_1400D15A7
0x1400d14fe  test    cl, cl
0x1400d1500  jns     short loc_1400D157F
0x1400d1502  mov     edx, 300h
0x1400d1507  add     edi, eax
0x1400d1509  jmp     loc_1400D1425
0x1400d150e  mov     eax, 1
0x1400d1513  jmp     short loc_1400D1507
0x1400d1515  mov     r8, rsi
0x1400d1518  mov     edx, r9d
0x1400d151b  mov     ebx, r9d
0x1400d151e  call    cs:__imp_WdLogSingleEntry2
0x1400d1525  nop     dword ptr [rax+rax+00h]
0x1400d152a  mov     [rsp+98h+var_60], r12
0x1400d152f  lea     r9, aOnlyOneSegment_0; "Only one segment can have UEFI Frame Bu"...
0x1400d1536  mov     [rsp+98h+var_68], r12
0x1400d153b  mov     [rsp+98h+var_70], rsi
0x1400d1540  mov     [rsp+98h+var_78], rbx
0x1400d1545  mov     cs:WdLogGlobalForLineNumber, 99h
0x1400d154f  jmp     loc_1400D16CC
0x1400d1554  mov     edx, edi
0x1400d1556  mov     ecx, 1
0x1400d155b  call    cs:__imp_WdLogSingleEntry1
0x1400d1562  nop     dword ptr [rax+rax+00h]
0x1400d1567  mov     eax, edi
0x1400d1569  lea     r9, aTheApertureAnd; "The Aperture and CpuVisible flags canno"...
0x1400d1570  mov     cs:WdLogGlobalForLineNumber, 0C0h
0x1400d157a  jmp     loc_1400D1678
0x1400d157f  mov     edx, edi
0x1400d1581  mov     ecx, eax
0x1400d1583  call    cs:__imp_WdLogSingleEntry1
0x1400d158a  nop     dword ptr [rax+rax+00h]
0x1400d158f  mov     eax, edi
0x1400d1591  lea     r9, aAperturepreser; "AperturePreservedDuringStandby flag mus"...
0x1400d1598  mov     cs:WdLogGlobalForLineNumber, 0D7h
0x1400d15a2  jmp     loc_1400D1678
0x1400d15a7  mov     edx, edi
0x1400d15a9  mov     ecx, eax
0x1400d15ab  call    cs:__imp_WdLogSingleEntry1
0x1400d15b2  nop     dword ptr [rax+rax+00h]
0x1400d15b7  mov     eax, edi
0x1400d15b9  lea     r9, aAperturepreser_0; "AperturePreservedDuringStandby flag mus"...
0x1400d15c0  mov     cs:WdLogGlobalForLineNumber, 0D1h
0x1400d15ca  jmp     loc_1400D1678
0x1400d15cf  mov     r9d, edi
0x1400d15d2  mov     r8, rax
0x1400d15d5  mov     ecx, eax
0x1400d15d7  mov     rbx, rdx
0x1400d15da  call    cs:__imp_WdLogSingleEntry3
0x1400d15e1  nop     dword ptr [rax+rax+00h]
0x1400d15e6  mov     [rsp+98h+var_60], r12
0x1400d15eb  lea     r9, aAperturepreser_1; "AperturePreservedDuringStandby flag can"...
0x1400d15f2  mov     eax, edi
0x1400d15f4  mov     ecx, 1
0x1400d15f9  mov     [rsp+98h+var_68], rax
0x1400d15fe  mov     [rsp+98h+var_70], rcx
0x1400d1603  mov     [rsp+98h+var_78], rbx
0x1400d1608  mov     cs:WdLogGlobalForLineNumber, 0CBh
0x1400d1612  jmp     loc_1400D16CC
0x1400d1617  mov     rdx, rsi
0x1400d161a  mov     ecx, eax
0x1400d161c  call    cs:__imp_WdLogSingleEntry2
0x1400d1623  nop     dword ptr [rax+rax+00h]
0x1400d1628  mov     [rsp+98h+var_60], r12
0x1400d162d  lea     r9, aSegmentUSizeI6; "Segment %u size (%I64u) must be page al"...
0x1400d1634  mov     [rsp+98h+var_68], r12
0x1400d1639  mov     cs:WdLogGlobalForLineNumber, 0A8h
0x1400d1643  mov     rax, [rbx+rbp+10h]
0x1400d1648  mov     [rsp+98h+var_70], rax
0x1400d164d  mov     [rsp+98h+var_78], rsi
0x1400d1652  jmp     short loc_1400D16CC
0x1400d1654  mov     rdx, rax
0x1400d1657  call    cs:__imp_WdLogSingleEntry1
0x1400d165e  nop     dword ptr [rax+rax+00h]
0x1400d1663  mov     cs:WdLogGlobalForLineNumber, 8Dh
0x1400d166d  lea     r9, aTooManyUefiFra; "Too many UEFI Frame Buffer Ranges speci"...
0x1400d1674  mov     eax, [rbx+rbp+5Ch]
0x1400d1678  mov     [rsp+98h+var_60], r12
0x1400d167d  mov     [rsp+98h+var_68], r12
0x1400d1682  mov     [rsp+98h+var_70], r12
0x1400d1687  mov     [rsp+98h+var_78], rax
0x1400d168c  jmp     short loc_1400D16CC
0x1400d168e  cmp     r15d, r14d
0x1400d1691  jbe     short loc_1400D16D8
0x1400d1693  mov     r8, r14
0x1400d1696  mov     rdx, r15
0x1400d1699  mov     ecx, eax
0x1400d169b  call    cs:__imp_WdLogSingleEntry2
0x1400d16a2  nop     dword ptr [rax+rax+00h]
0x1400d16a7  mov     [rsp+98h+var_60], r12
0x1400d16ac  lea     r9, aPagingbufferse_1; "PagingBufferSegmentId (%u) must be less"...
0x1400d16b3  mov     [rsp+98h+var_68], r12
0x1400d16b8  mov     [rsp+98h+var_70], r14
0x1400d16bd  mov     [rsp+98h+var_78], r15
0x1400d16c2  mov     cs:WdLogGlobalForLineNumber, 0E1h
0x1400d16cc  mov     edx, 40000h
0x1400d16d1  call    DxgkLogInternalTriageEvent
0x1400d16d6  xor     al, al
0x1400d16d8  add     rsp, 58h
0x1400d16dc  pop     r15
0x1400d16de  pop     r14
0x1400d16e0  pop     r13
0x1400d16e2  pop     r12
0x1400d16e4  pop     rdi
0x1400d16e5  pop     rsi
0x1400d16e6  pop     rbp
0x1400d16e7  pop     rbx
0x1400d16e8  retn
```
