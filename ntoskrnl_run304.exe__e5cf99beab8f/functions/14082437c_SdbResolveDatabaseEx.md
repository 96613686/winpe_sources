# SdbResolveDatabaseEx

- ea: `0x14082437c`
- end: `0x1408246b9`
- name: `SdbResolveDatabaseEx`
- size: `829`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140824034`

## callees

- `0x1403f4770`
- `0x1403f4830`
- `0x1406daa70`
- `0x140823e94`
- `0x140824284`
- `0x140824354`
- `0x14082437c`
- `0x140825a70`
- `0x140825cf4`
- `0x140826204`
- `0x1408262f4`
- `0x140979890`
- `0x14097b68c`
- `0x14097d158`

## string_xrefs

- `0x140824518`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x1408244ea`: `Failed to allocate %ld bytes for key path`
- `0x140824446`: `SdbGetPathSystemSdb failed.`
- `0x140824646`: `SdbGetPathCustomSdb failed to get the database path.`
- `0x140824566`: `Failed to open Key "%ws" [%x]`

## pseudocode

```c
__int64 __fastcall SdbResolveDatabaseEx(__int64 a1, _QWORD *a2, int *a3, int *a4, _WORD *a5, int a6)
{
  __int64 i; // rdx
  _QWORD *v11; // r9
  __int64 v12; // rcx
  unsigned int v13; // eax
  int v14; // r15d
  int v15; // r12d
  __int64 v16; // rbx
  int v17; // eax
  int v19; // eax
  __int64 v20; // rcx
  wchar_t *v21; // r15
  unsigned int v22; // r12d
  wchar_t *v23; // rax
  int v24; // eax
  __int64 v25; // rdx
  int UInt32_UStr; // eax
  int v27; // eax
  HANDLE v28; // rcx
  int v29; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-30h] BYREF
  UNICODE_STRING Destination; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+50h] [rbp-18h] BYREF

  a6 = 0;
  v29 = 0;
  Handle = 0;
  Destination = 0;
  Source = 0;
  if ( !a5 )
    return 0;
  *a5 = 0;
  for ( i = 0; (unsigned int)i < 6; i = (unsigned int)(i + 1) )
  {
    v11 = *(&off_140E0D810 + 3 * (int)i);
    v12 = *v11 - *a2;
    if ( *v11 == *a2 )
      v12 = v11[1] - a2[1];
    if ( !v12 )
    {
      v13 = *((_DWORD *)&off_140E0D810 + 6 * (int)i + 4);
      v14 = *((_DWORD *)&off_140E0D810 + 6 * (int)i + 2);
      a6 = v14;
      if ( v13 )
      {
        v15 = *((_DWORD *)&off_140E0D810 + 6 * (int)i + 3);
        if ( (unsigned int)SdbGetPathSystemSdb(a5, i, v13, a1 + 584) )
        {
          v16 = -1;
          do
            ++v16;
          while ( a5[v16] );
        }
        else
        {
          LODWORD(v16) = 0;
          AslLogCallPrintf(1, (unsigned int)"SdbResolveDatabaseEx", 2353, (unsigned int)"SdbGetPathSystemSdb failed.");
        }
        if ( a3 )
          *a3 = v14;
        if ( a4 )
        {
          v17 = SdbGuestTargetPlatformFlagsToRuntimePlatformFlags(31);
          *a4 = v17;
          if ( v15 )
            *a4 = v17 & 0x1B;
        }
        return (unsigned int)v16;
      }
      break;
    }
  }
  LODWORD(v16) = 0;
  v19 = AslGuidToString_UStr(&Source, a2);
  if ( v19 < 0 )
  {
    v21 = 0;
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbResolveDatabaseEx",
      2376,
      (unsigned int)"Failed to convert guid to string [%x]",
      v19);
    goto LABEL_38;
  }
  v22 = Source.Length + 184;
  v23 = (wchar_t *)AslAlloc(v20, v22);
  v21 = v23;
  if ( !v23 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbResolveDatabaseEx",
      2397,
      (unsigned int)"Failed to allocate %ld bytes for key path",
      v22);
    goto LABEL_38;
  }
  Destination.MaximumLength = v22;
  Destination.Buffer = v23;
  Destination.Length = 0;
  RtlAppendUnicodeToString(
    &Destination,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
  RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeStringToString(&Destination, &Source);
  v24 = AslRegistryOpenKey_UStr(&Handle, &Destination);
  if ( v24 < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbResolveDatabaseEx",
      2413,
      (unsigned int)"Failed to open Key \"%ws\" [%x]",
      Destination.Buffer,
      v24);
    goto LABEL_38;
  }
  if ( a3 )
  {
    UInt32_UStr = AslRegistryGetUInt32_UStr(&a6, Handle, &g_ustrDatabaseType);
    if ( UInt32_UStr < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbResolveDatabaseEx",
        2425,
        (unsigned int)"Failed to get database type [%x]",
        UInt32_UStr);
      *a3 = 0;
      goto LABEL_38;
    }
    *a3 = a6 & 0x7FFFFFFF;
  }
  if ( a4 )
  {
    v27 = AslRegistryGetUInt32_UStr(&v29, Handle, L".0");
    if ( v27 < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbResolveDatabaseEx",
        2441,
        (unsigned int)"Failed to get runtime platform [%x]",
        v27);
      *a4 = 0;
      goto LABEL_38;
    }
    *a4 = v29;
  }
  if ( (unsigned int)SdbGetPathCustomSdb(a5, v25, a2, a1 + 584) )
  {
    v16 = -1;
    do
      ++v16;
    while ( a5[v16] );
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbResolveDatabaseEx",
      2450,
      (unsigned int)"SdbGetPathCustomSdb failed to get the database path.");
  }
LABEL_38:
  v28 = Handle;
  if ( Handle )
    ZwClose(Handle);
  if ( v21 )
    AslFree(v28, v21);
  if ( Source.Buffer )
    AslUnicodeStringFree(&Source);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14082437c  mov     [rsp-40h+arg_0], rcx
0x140824381  push    rbp
0x140824382  push    rbx
0x140824383  push    rsi
0x140824384  push    rdi
0x140824385  push    r12
0x140824387  push    r13
0x140824389  push    r14
0x14082438b  push    r15
0x14082438d  mov     rbp, rsp
0x140824390  sub     rsp, 68h
0x140824394  mov     rsi, [rbp+arg_20]
0x140824398  xor     r12d, r12d
0x14082439b  mov     [rbp+arg_28], r12d
0x14082439f  xorps   xmm0, xmm0
0x1408243a2  mov     [rbp+var_38], r12d
0x1408243a6  xorps   xmm1, xmm1
0x1408243a9  mov     [rbp+Handle], r12
0x1408243ad  mov     rdi, r9
0x1408243b0  mov     r14, r8
0x1408243b3  mov     r13, rdx
0x1408243b6  mov     r10, rcx
0x1408243b9  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x1408243bd  movups  xmmword ptr [rbp+Source.Length], xmm1
0x1408243c1  test    rsi, rsi
0x1408243c4  jz      loc_1408246A5
0x1408243ca  mov     [rsi], r12w
0x1408243ce  lea     r11, off_140E0D810
0x1408243d5  mov     edx, r12d
0x1408243d8  cmp     edx, 6
0x1408243db  jnb     loc_140824491
0x1408243e1  movsxd  rax, edx
0x1408243e4  lea     r8, [rax+rax*2]
0x1408243e8  mov     r9, [r11+r8*8]
0x1408243ec  mov     rcx, [r9]
0x1408243ef  sub     rcx, [r13+0]
0x1408243f3  jnz     short loc_1408243FD
0x1408243f5  mov     rcx, [r9+8]
0x1408243f9  sub     rcx, [r13+8]
0x1408243fd  test    rcx, rcx
0x140824400  jz      short loc_140824406
0x140824402  inc     edx
0x140824404  jmp     short loc_1408243D8
0x140824406  mov     eax, [r11+r8*8+10h]
0x14082440b  mov     r15d, [r11+r8*8+8]
0x140824410  mov     [rbp+arg_28], r15d
0x140824414  test    eax, eax
0x140824416  jz      short loc_140824491
0x140824418  mov     r12d, [r11+r8*8+0Ch]
0x14082441d  lea     r9, [r10+248h]
0x140824424  mov     r8d, eax
0x140824427  mov     rcx, rsi
0x14082442a  call    SdbGetPathSystemSdb
0x14082442f  xor     r13d, r13d
0x140824432  test    eax, eax
0x140824434  jz      short loc_140824446
0x140824436  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14082443a  inc     rbx
0x14082443d  cmp     [rsi+rbx*2], r13w
0x140824442  jnz     short loc_14082443A
0x140824444  jmp     short loc_140824467
0x140824446  lea     r9, aSdbgetpathsyst; "SdbGetPathSystemSdb failed."
0x14082444d  mov     r8d, 931h
0x140824453  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14082445a  mov     ecx, 1
0x14082445f  mov     ebx, r13d
0x140824462  call    AslLogCallPrintf
0x140824467  test    r14, r14
0x14082446a  jz      short loc_14082446F
0x14082446c  mov     [r14], r15d
0x14082446f  test    rdi, rdi
0x140824472  jz      short loc_14082448A
0x140824474  mov     ecx, 1Fh
0x140824479  call    SdbGuestTargetPlatformFlagsToRuntimePlatformFlags
0x14082447e  mov     [rdi], eax
0x140824480  test    r12d, r12d
0x140824483  jz      short loc_14082448A
0x140824485  and     eax, 1Bh
0x140824488  mov     [rdi], eax
0x14082448a  mov     eax, ebx
0x14082448c  jmp     loc_1408246A7
0x140824491  mov     rdx, r13
0x140824494  lea     rcx, [rbp+Source]
0x140824498  mov     ebx, r12d
0x14082449b  call    AslGuidToString_UStr
0x1408244a0  test    eax, eax
0x1408244a2  jns     short loc_1408244CE
0x1408244a4  lea     r9, aFailedToConver_2; "Failed to convert guid to string [%x]"
0x1408244ab  mov     dword ptr [rsp+68h+var_48], eax
0x1408244af  mov     r8d, 948h
0x1408244b5  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1408244bc  mov     ecx, 1
0x1408244c1  mov     r15, r12
0x1408244c4  call    AslLogCallPrintf
0x1408244c9  jmp     loc_140824672
0x1408244ce  movzx   r12d, [rbp+Source.Length]
0x1408244d3  add     r12d, 0B8h
0x1408244da  mov     edx, r12d
0x1408244dd  call    AslAlloc
0x1408244e2  mov     r15, rax
0x1408244e5  test    rax, rax
0x1408244e8  jnz     short loc_140824513
0x1408244ea  lea     r9, aFailedToAlloca_7; "Failed to allocate %ld bytes for key pa"...
0x1408244f1  mov     dword ptr [rsp+68h+var_48], r12d
0x1408244f6  mov     r8d, 95Dh
0x1408244fc  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x140824503  lea     ecx, [rax+1]
0x140824506  call    AslLogCallPrintf
0x14082450b  xor     r12d, r12d
0x14082450e  jmp     loc_140824672
0x140824513  mov     [rbp+Destination.MaximumLength], r12w
0x140824518  lea     rdx, aRegistryMachin_139; "\\Registry\\Machine\\Software\\Microsof"...
0x14082451f  xor     r12d, r12d
0x140824522  mov     [rbp+Destination.Buffer], rax
0x140824526  lea     rcx, [rbp+Destination]; Destination
0x14082452a  mov     [rbp+Destination.Length], r12w
0x14082452f  call    RtlAppendUnicodeToString
0x140824534  lea     rdx, asc_1400211EC; "\\"
0x14082453b  lea     rcx, [rbp+Destination]; Destination
0x14082453f  call    RtlAppendUnicodeToString
0x140824544  lea     rdx, [rbp+Source]; Source
0x140824548  lea     rcx, [rbp+Destination]; Destination
0x14082454c  call    RtlAppendUnicodeStringToString
0x140824551  lea     rdx, [rbp+Destination]
0x140824555  lea     rcx, [rbp+Handle]
0x140824559  call    AslRegistryOpenKey_UStr
0x14082455e  test    eax, eax
0x140824560  jns     short loc_140824592
0x140824562  mov     [rsp+68h+var_40], eax
0x140824566  lea     r9, aFailedToOpenKe; "Failed to open Key \"%ws\" [%x]"
0x14082456d  mov     rax, [rbp+Destination.Buffer]
0x140824571  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x140824578  mov     r8d, 96Dh
0x14082457e  mov     [rsp+68h+var_48], rax
0x140824583  lea     ecx, [r12+1]
0x140824588  call    AslLogCallPrintf
0x14082458d  jmp     loc_140824672
0x140824592  test    r14, r14
0x140824595  jz      short loc_1408245E3
0x140824597  mov     rdx, [rbp+Handle]
0x14082459b  lea     r8, g_ustrDatabaseType
0x1408245a2  lea     rcx, [rbp+arg_28]
0x1408245a6  call    AslRegistryGetUInt32_UStr
0x1408245ab  test    eax, eax
0x1408245ad  jns     short loc_1408245D9
0x1408245af  lea     r9, aFailedToGetDat_0; "Failed to get database type [%x]"
0x1408245b6  mov     dword ptr [rsp+68h+var_48], eax
0x1408245ba  mov     r8d, 979h
0x1408245c0  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1408245c7  mov     ecx, 1
0x1408245cc  call    AslLogCallPrintf
0x1408245d1  mov     [r14], r12d
0x1408245d4  jmp     loc_140824672
0x1408245d9  mov     eax, [rbp+arg_28]
0x1408245dc  btr     eax, 1Fh
0x1408245e0  mov     [r14], eax
0x1408245e3  test    rdi, rdi
0x1408245e6  jz      short loc_14082462C
0x1408245e8  mov     rdx, [rbp+Handle]
0x1408245ec  lea     r8, g_ustrRuntimePlatform; ".0"
0x1408245f3  lea     rcx, [rbp+var_38]
0x1408245f7  call    AslRegistryGetUInt32_UStr
0x1408245fc  test    eax, eax
0x1408245fe  jns     short loc_140824627
0x140824600  lea     r9, aFailedToGetRun; "Failed to get runtime platform [%x]"
0x140824607  mov     dword ptr [rsp+68h+var_48], eax
0x14082460b  mov     r8d, 989h
0x140824611  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x140824618  mov     ecx, 1
0x14082461d  call    AslLogCallPrintf
0x140824622  mov     [rdi], r12d
0x140824625  jmp     short loc_140824672
0x140824627  mov     eax, [rbp+var_38]
0x14082462a  mov     [rdi], eax
0x14082462c  mov     r9, [rbp+arg_0]
0x140824630  mov     r8, r13
0x140824633  add     r9, 248h
0x14082463a  mov     rcx, rsi
0x14082463d  call    SdbGetPathCustomSdb
0x140824642  test    eax, eax
0x140824644  jnz     short loc_140824664
0x140824646  lea     r9, aSdbgetpathcust; "SdbGetPathCustomSdb failed to get the d"...
0x14082464d  mov     r8d, 992h
0x140824653  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14082465a  lea     ecx, [rax+1]
0x14082465d  call    AslLogCallPrintf
0x140824662  jmp     short loc_140824672
0x140824664  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140824668  inc     rbx
0x14082466b  cmp     [rsi+rbx*2], r12w
0x140824670  jnz     short loc_140824668
0x140824672  mov     rcx, [rbp+Handle]; Handle
0x140824676  test    rcx, rcx
0x140824679  jz      short loc_140824680
0x14082467b  call    ZwClose
0x140824680  test    r15, r15
0x140824683  jz      short loc_14082468D
0x140824685  mov     rdx, r15
0x140824688  call    AslFree
0x14082468d  cmp     [rbp+Source.Buffer], r12
0x140824691  jz      loc_14082448A
0x140824697  lea     rcx, [rbp+Source]
0x14082469b  call    AslUnicodeStringFree
0x1408246a0  jmp     loc_14082448A
0x1408246a5  xor     eax, eax
0x1408246a7  add     rsp, 68h
0x1408246ab  pop     r15
0x1408246ad  pop     r14
0x1408246af  pop     r13
0x1408246b1  pop     r12
0x1408246b3  pop     rdi
0x1408246b4  pop     rsi
0x1408246b5  pop     rbx
0x1408246b6  pop     rbp
0x1408246b7  retn
```
