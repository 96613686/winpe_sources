# SdbResolveDatabaseEx

- ea: `0x1408262ec`
- end: `0x140826629`
- name: `SdbResolveDatabaseEx`
- size: `829`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140825fa4`

## callees

- `0x140388690`
- `0x140388750`
- `0x1406dd5c0`
- `0x140825e04`
- `0x1408261f4`
- `0x1408262c4`
- `0x1408262ec`
- `0x1408279e0`
- `0x140827c64`
- `0x140828174`
- `0x140828264`
- `0x1408bf658`
- `0x1408c14bc`
- `0x1408c2f88`

## string_xrefs

- `0x1408263b6`: `SdbGetPathSystemSdb failed.`
- `0x1408265b6`: `SdbGetPathCustomSdb failed to get the database path.`
- `0x1408264d6`: `Failed to open Key "%ws" [%x]`
- `0x14082645a`: `Failed to allocate %ld bytes for key path`
- `0x140826488`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`

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
0x1408262ec  mov     [rsp-40h+arg_0], rcx
0x1408262f1  push    rbp
0x1408262f2  push    rbx
0x1408262f3  push    rsi
0x1408262f4  push    rdi
0x1408262f5  push    r12
0x1408262f7  push    r13
0x1408262f9  push    r14
0x1408262fb  push    r15
0x1408262fd  mov     rbp, rsp
0x140826300  sub     rsp, 68h
0x140826304  mov     rsi, [rbp+arg_20]
0x140826308  xor     r12d, r12d
0x14082630b  mov     [rbp+arg_28], r12d
0x14082630f  xorps   xmm0, xmm0
0x140826312  mov     [rbp+var_38], r12d
0x140826316  xorps   xmm1, xmm1
0x140826319  mov     [rbp+Handle], r12
0x14082631d  mov     rdi, r9
0x140826320  mov     r14, r8
0x140826323  mov     r13, rdx
0x140826326  mov     r10, rcx
0x140826329  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x14082632d  movups  xmmword ptr [rbp+Source.Length], xmm1
0x140826331  test    rsi, rsi
0x140826334  jz      loc_140826615
0x14082633a  mov     [rsi], r12w
0x14082633e  lea     r11, off_140E0D810
0x140826345  mov     edx, r12d
0x140826348  cmp     edx, 6
0x14082634b  jnb     loc_140826401
0x140826351  movsxd  rax, edx
0x140826354  lea     r8, [rax+rax*2]
0x140826358  mov     r9, [r11+r8*8]
0x14082635c  mov     rcx, [r9]
0x14082635f  sub     rcx, [r13+0]
0x140826363  jnz     short loc_14082636D
0x140826365  mov     rcx, [r9+8]
0x140826369  sub     rcx, [r13+8]
0x14082636d  test    rcx, rcx
0x140826370  jz      short loc_140826376
0x140826372  inc     edx
0x140826374  jmp     short loc_140826348
0x140826376  mov     eax, [r11+r8*8+10h]
0x14082637b  mov     r15d, [r11+r8*8+8]
0x140826380  mov     [rbp+arg_28], r15d
0x140826384  test    eax, eax
0x140826386  jz      short loc_140826401
0x140826388  mov     r12d, [r11+r8*8+0Ch]
0x14082638d  lea     r9, [r10+248h]
0x140826394  mov     r8d, eax
0x140826397  mov     rcx, rsi
0x14082639a  call    SdbGetPathSystemSdb
0x14082639f  xor     r13d, r13d
0x1408263a2  test    eax, eax
0x1408263a4  jz      short loc_1408263B6
0x1408263a6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1408263aa  inc     rbx
0x1408263ad  cmp     [rsi+rbx*2], r13w
0x1408263b2  jnz     short loc_1408263AA
0x1408263b4  jmp     short loc_1408263D7
0x1408263b6  lea     r9, aSdbgetpathsyst; "SdbGetPathSystemSdb failed."
0x1408263bd  mov     r8d, 931h
0x1408263c3  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1408263ca  mov     ecx, 1
0x1408263cf  mov     ebx, r13d
0x1408263d2  call    AslLogCallPrintf
0x1408263d7  test    r14, r14
0x1408263da  jz      short loc_1408263DF
0x1408263dc  mov     [r14], r15d
0x1408263df  test    rdi, rdi
0x1408263e2  jz      short loc_1408263FA
0x1408263e4  mov     ecx, 1Fh
0x1408263e9  call    SdbGuestTargetPlatformFlagsToRuntimePlatformFlags
0x1408263ee  mov     [rdi], eax
0x1408263f0  test    r12d, r12d
0x1408263f3  jz      short loc_1408263FA
0x1408263f5  and     eax, 1Bh
0x1408263f8  mov     [rdi], eax
0x1408263fa  mov     eax, ebx
0x1408263fc  jmp     loc_140826617
0x140826401  mov     rdx, r13
0x140826404  lea     rcx, [rbp+Source]
0x140826408  mov     ebx, r12d
0x14082640b  call    AslGuidToString_UStr
0x140826410  test    eax, eax
0x140826412  jns     short loc_14082643E
0x140826414  lea     r9, aFailedToConver_2; "Failed to convert guid to string [%x]"
0x14082641b  mov     dword ptr [rsp+68h+var_48], eax
0x14082641f  mov     r8d, 948h
0x140826425  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14082642c  mov     ecx, 1
0x140826431  mov     r15, r12
0x140826434  call    AslLogCallPrintf
0x140826439  jmp     loc_1408265E2
0x14082643e  movzx   r12d, [rbp+Source.Length]
0x140826443  add     r12d, 0B8h
0x14082644a  mov     edx, r12d
0x14082644d  call    AslAlloc
0x140826452  mov     r15, rax
0x140826455  test    rax, rax
0x140826458  jnz     short loc_140826483
0x14082645a  lea     r9, aFailedToAlloca_7; "Failed to allocate %ld bytes for key pa"...
0x140826461  mov     dword ptr [rsp+68h+var_48], r12d
0x140826466  mov     r8d, 95Dh
0x14082646c  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x140826473  lea     ecx, [rax+1]
0x140826476  call    AslLogCallPrintf
0x14082647b  xor     r12d, r12d
0x14082647e  jmp     loc_1408265E2
0x140826483  mov     [rbp+Destination.MaximumLength], r12w
0x140826488  lea     rdx, aRegistryMachin_139; "\\Registry\\Machine\\Software\\Microsof"...
0x14082648f  xor     r12d, r12d
0x140826492  mov     [rbp+Destination.Buffer], rax
0x140826496  lea     rcx, [rbp+Destination]; Destination
0x14082649a  mov     [rbp+Destination.Length], r12w
0x14082649f  call    RtlAppendUnicodeToString
0x1408264a4  lea     rdx, asc_1400211F4; "\\"
0x1408264ab  lea     rcx, [rbp+Destination]; Destination
0x1408264af  call    RtlAppendUnicodeToString
0x1408264b4  lea     rdx, [rbp+Source]; Source
0x1408264b8  lea     rcx, [rbp+Destination]; Destination
0x1408264bc  call    RtlAppendUnicodeStringToString
0x1408264c1  lea     rdx, [rbp+Destination]
0x1408264c5  lea     rcx, [rbp+Handle]
0x1408264c9  call    AslRegistryOpenKey_UStr
0x1408264ce  test    eax, eax
0x1408264d0  jns     short loc_140826502
0x1408264d2  mov     [rsp+68h+var_40], eax
0x1408264d6  lea     r9, aFailedToOpenKe; "Failed to open Key \"%ws\" [%x]"
0x1408264dd  mov     rax, [rbp+Destination.Buffer]
0x1408264e1  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1408264e8  mov     r8d, 96Dh
0x1408264ee  mov     [rsp+68h+var_48], rax
0x1408264f3  lea     ecx, [r12+1]
0x1408264f8  call    AslLogCallPrintf
0x1408264fd  jmp     loc_1408265E2
0x140826502  test    r14, r14
0x140826505  jz      short loc_140826553
0x140826507  mov     rdx, [rbp+Handle]
0x14082650b  lea     r8, g_ustrDatabaseType
0x140826512  lea     rcx, [rbp+arg_28]
0x140826516  call    AslRegistryGetUInt32_UStr
0x14082651b  test    eax, eax
0x14082651d  jns     short loc_140826549
0x14082651f  lea     r9, aFailedToGetDat_0; "Failed to get database type [%x]"
0x140826526  mov     dword ptr [rsp+68h+var_48], eax
0x14082652a  mov     r8d, 979h
0x140826530  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x140826537  mov     ecx, 1
0x14082653c  call    AslLogCallPrintf
0x140826541  mov     [r14], r12d
0x140826544  jmp     loc_1408265E2
0x140826549  mov     eax, [rbp+arg_28]
0x14082654c  btr     eax, 1Fh
0x140826550  mov     [r14], eax
0x140826553  test    rdi, rdi
0x140826556  jz      short loc_14082659C
0x140826558  mov     rdx, [rbp+Handle]
0x14082655c  lea     r8, g_ustrRuntimePlatform; ".0"
0x140826563  lea     rcx, [rbp+var_38]
0x140826567  call    AslRegistryGetUInt32_UStr
0x14082656c  test    eax, eax
0x14082656e  jns     short loc_140826597
0x140826570  lea     r9, aFailedToGetRun; "Failed to get runtime platform [%x]"
0x140826577  mov     dword ptr [rsp+68h+var_48], eax
0x14082657b  mov     r8d, 989h
0x140826581  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x140826588  mov     ecx, 1
0x14082658d  call    AslLogCallPrintf
0x140826592  mov     [rdi], r12d
0x140826595  jmp     short loc_1408265E2
0x140826597  mov     eax, [rbp+var_38]
0x14082659a  mov     [rdi], eax
0x14082659c  mov     r9, [rbp+arg_0]
0x1408265a0  mov     r8, r13
0x1408265a3  add     r9, 248h
0x1408265aa  mov     rcx, rsi
0x1408265ad  call    SdbGetPathCustomSdb
0x1408265b2  test    eax, eax
0x1408265b4  jnz     short loc_1408265D4
0x1408265b6  lea     r9, aSdbgetpathcust; "SdbGetPathCustomSdb failed to get the d"...
0x1408265bd  mov     r8d, 992h
0x1408265c3  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1408265ca  lea     ecx, [rax+1]
0x1408265cd  call    AslLogCallPrintf
0x1408265d2  jmp     short loc_1408265E2
0x1408265d4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1408265d8  inc     rbx
0x1408265db  cmp     [rsi+rbx*2], r12w
0x1408265e0  jnz     short loc_1408265D8
0x1408265e2  mov     rcx, [rbp+Handle]; Handle
0x1408265e6  test    rcx, rcx
0x1408265e9  jz      short loc_1408265F0
0x1408265eb  call    ZwClose
0x1408265f0  test    r15, r15
0x1408265f3  jz      short loc_1408265FD
0x1408265f5  mov     rdx, r15
0x1408265f8  call    AslFree
0x1408265fd  cmp     [rbp+Source.Buffer], r12
0x140826601  jz      loc_1408263FA
0x140826607  lea     rcx, [rbp+Source]
0x14082660b  call    AslUnicodeStringFree
0x140826610  jmp     loc_1408263FA
0x140826615  xor     eax, eax
0x140826617  add     rsp, 68h
0x14082661b  pop     r15
0x14082661d  pop     r14
0x14082661f  pop     r13
0x140826621  pop     r12
0x140826623  pop     rdi
0x140826624  pop     rsi
0x140826625  pop     rbx
0x140826626  pop     rbp
0x140826627  retn
```
