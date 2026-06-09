# SdbResolveDatabaseEx

- ea: `0x1800ac6f4`
- end: `0x1800aca4f`
- name: `SdbResolveDatabaseEx`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a7bd4`

## callees

- `0x180041774`
- `0x18004281c`
- `0x180042c48`
- `0x1800715f0`
- `0x1800a76ec`
- `0x1800ac624`
- `0x1800ac6f4`
- `0x1800c0674`
- `0x1800c0820`
- `0x1800c0cf4`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x1800ac8b6`
- `ntdll!RtlAppendUnicodeToString` at `0x1800ac8c7`
- `ntdll!RtlAppendUnicodeToString` at `0x1800ac8b6`
- `ntdll!RtlAppendUnicodeToString` at `0x1800ac8c7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800ac8d5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800ac8d5`
- `ntdll!RtlAllocateHeap` at `0x1800ac863`
- `ntdll!RtlAllocateHeap` at `0x1800ac863`
- `ntdll!ZwClose` at `0x1800aca04`
- `ntdll!ZwClose` at `0x1800aca04`

## string_xrefs

- `0x1800ac7ba`: `SdbGetPathSystemSdb failed.`
- `0x1800ac89f`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x1800ac871`: `Failed to allocate %ld bytes for key path`
- `0x1800ac8f0`: `Failed to open Key "%ws" [%x]`
- `0x1800ac9cf`: `SdbGetPathCustomSdb failed to get the database path.`

## pseudocode

```c
__int64 __fastcall SdbResolveDatabaseEx(__int64 a1, _QWORD *a2, int *a3, int *a4, _WORD *a5, int a6)
{
  int *v7; // r14
  unsigned int i; // ecx
  __int64 v11; // rax
  int v12; // r15d
  int v13; // r12d
  __int64 v14; // rbx
  int v15; // eax
  int v17; // eax
  WCHAR *v18; // r15
  unsigned int v19; // r13d
  WCHAR *Heap; // rax
  NTSTATUS v21; // eax
  __int64 v22; // rdx
  int UInt32_UStr; // eax
  int v24; // eax
  int v25; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+50h] [rbp-18h] BYREF

  a6 = 0;
  v25 = 0;
  Handle = 0;
  v7 = a3;
  Destination = 0;
  Source = 0;
  if ( !a5 )
    return 0;
  *a5 = 0;
  for ( i = 0; i < 6; ++i )
  {
    a3 = (int *)*(&off_180108190 + 3 * (int)i);
    v11 = *(_QWORD *)a3 - *a2;
    if ( *(_QWORD *)a3 == *a2 )
      v11 = *((_QWORD *)a3 + 1) - a2[1];
    if ( !v11 )
    {
      a3 = (int *)*((unsigned int *)&off_180108190 + 6 * (int)i + 4);
      v12 = *((_DWORD *)&off_180108190 + 6 * (int)i + 2);
      a6 = v12;
      if ( (_DWORD)a3 )
      {
        v13 = *((_DWORD *)&off_180108190 + 6 * (int)i + 3);
        if ( (unsigned int)SdbGetPathSystemSdb(a5, 3LL * (int)i, a3, a1 + 584) )
        {
          v14 = -1;
          do
            ++v14;
          while ( a5[v14] );
        }
        else
        {
          LODWORD(v14) = 0;
          AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2353, "SdbGetPathSystemSdb failed.");
        }
        if ( v7 )
          *v7 = v12;
        if ( a4 )
        {
          v15 = SdbGuestTargetPlatformFlagsToRuntimePlatformFlags(31);
          *a4 = v15;
          if ( v13 )
            *a4 = v15 & 0x1B;
        }
        return (unsigned int)v14;
      }
      break;
    }
  }
  LODWORD(v14) = 0;
  v17 = AslGuidToString_UStr(&Source, a2, a3, a1);
  if ( v17 < 0 )
  {
    v18 = 0;
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2376, "Failed to convert guid to string [%x]", v17);
    goto LABEL_38;
  }
  v19 = Source.Length + 184;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v19);
  v18 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2397, "Failed to allocate %ld bytes for key path", v19);
    goto LABEL_38;
  }
  Destination.MaximumLength = v19;
  Destination.Buffer = Heap;
  Destination.Length = 0;
  RtlAppendUnicodeToString(
    &Destination,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
  RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeStringToString(&Destination, &Source);
  v21 = AslRegistryOpenKey_UStr(&Handle, &Destination);
  if ( v21 < 0 )
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2413, "Failed to open Key \"%ws\" [%x]", Destination.Buffer, v21);
    goto LABEL_38;
  }
  if ( v7 )
  {
    UInt32_UStr = AslRegistryGetUInt32_UStr(&a6, Handle, &g_ustrDatabaseType);
    if ( UInt32_UStr < 0 )
    {
      AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2425, "Failed to get database type [%x]", UInt32_UStr);
      *v7 = 0;
      goto LABEL_38;
    }
    *v7 = a6 & 0x7FFFFFFF;
  }
  if ( a4 )
  {
    v24 = AslRegistryGetUInt32_UStr(&v25, Handle, L".0");
    if ( v24 < 0 )
    {
      AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2441, "Failed to get runtime platform [%x]", v24);
      *a4 = 0;
      goto LABEL_38;
    }
    *a4 = v25;
  }
  if ( (unsigned int)SdbGetPathCustomSdb(a5, v22, a2, a1 + 584) )
  {
    v14 = -1;
    do
      ++v14;
    while ( a5[v14] );
  }
  else
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2450, "SdbGetPathCustomSdb failed to get the database path.");
  }
LABEL_38:
  if ( Handle )
    ZwClose(Handle);
  if ( v18 )
    AslFree(NtCurrentPeb()->ProcessHeap, v18);
  if ( Source.Buffer )
    AslUnicodeStringFree(&Source);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800ac6f4  mov     [rsp-40h+arg_0], rcx
0x1800ac6f9  push    rbp
0x1800ac6fa  push    rbx
0x1800ac6fb  push    rsi
0x1800ac6fc  push    rdi
0x1800ac6fd  push    r12
0x1800ac6ff  push    r13
0x1800ac701  push    r14
0x1800ac703  push    r15
0x1800ac705  mov     rbp, rsp
0x1800ac708  sub     rsp, 68h
0x1800ac70c  mov     rsi, [rbp+arg_20]
0x1800ac710  xor     r13d, r13d
0x1800ac713  mov     [rbp+arg_28], r13d
0x1800ac717  xorps   xmm0, xmm0
0x1800ac71a  mov     [rbp+var_38], r13d
0x1800ac71e  xorps   xmm1, xmm1
0x1800ac721  mov     [rbp+Handle], r13
0x1800ac725  mov     rdi, r9
0x1800ac728  mov     r14, r8
0x1800ac72b  mov     r12, rdx
0x1800ac72e  mov     r9, rcx
0x1800ac731  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x1800ac735  movups  xmmword ptr [rbp+Source.Length], xmm1
0x1800ac739  test    rsi, rsi
0x1800ac73c  jz      loc_1800ACA3C
0x1800ac742  mov     [rsi], r13w
0x1800ac746  lea     r10, off_180108190
0x1800ac74d  mov     ecx, r13d
0x1800ac750  cmp     ecx, 6
0x1800ac753  jnb     loc_1800AC805
0x1800ac759  movsxd  rax, ecx
0x1800ac75c  lea     rdx, [rax+rax*2]
0x1800ac760  mov     r8, [r10+rdx*8]
0x1800ac764  mov     rax, [r8]
0x1800ac767  sub     rax, [r12]
0x1800ac76b  jnz     short loc_1800AC776
0x1800ac76d  mov     rax, [r8+8]
0x1800ac771  sub     rax, [r12+8]
0x1800ac776  test    rax, rax
0x1800ac779  jz      short loc_1800AC77F
0x1800ac77b  inc     ecx
0x1800ac77d  jmp     short loc_1800AC750
0x1800ac77f  mov     r8d, [r10+rdx*8+10h]
0x1800ac784  mov     r15d, [r10+rdx*8+8]
0x1800ac789  mov     [rbp+arg_28], r15d
0x1800ac78d  test    r8d, r8d
0x1800ac790  jz      short loc_1800AC805
0x1800ac792  mov     r12d, [r10+rdx*8+0Ch]
0x1800ac797  add     r9, 248h
0x1800ac79e  mov     rcx, rsi
0x1800ac7a1  call    SdbGetPathSystemSdb
0x1800ac7a6  test    eax, eax
0x1800ac7a8  jz      short loc_1800AC7BA
0x1800ac7aa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ac7ae  inc     rbx
0x1800ac7b1  cmp     [rsi+rbx*2], r13w
0x1800ac7b6  jnz     short loc_1800AC7AE
0x1800ac7b8  jmp     short loc_1800AC7DB
0x1800ac7ba  lea     r9, aSdbgetpathsyst_0; "SdbGetPathSystemSdb failed."
0x1800ac7c1  mov     r8d, 931h
0x1800ac7c7  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1800ac7ce  mov     ecx, 1
0x1800ac7d3  mov     ebx, r13d
0x1800ac7d6  call    AslLogCallPrintf
0x1800ac7db  test    r14, r14
0x1800ac7de  jz      short loc_1800AC7E3
0x1800ac7e0  mov     [r14], r15d
0x1800ac7e3  test    rdi, rdi
0x1800ac7e6  jz      short loc_1800AC7FE
0x1800ac7e8  mov     ecx, 1Fh
0x1800ac7ed  call    SdbGuestTargetPlatformFlagsToRuntimePlatformFlags
0x1800ac7f2  mov     [rdi], eax
0x1800ac7f4  test    r12d, r12d
0x1800ac7f7  jz      short loc_1800AC7FE
0x1800ac7f9  and     eax, 1Bh
0x1800ac7fc  mov     [rdi], eax
0x1800ac7fe  mov     eax, ebx
0x1800ac800  jmp     loc_1800ACA3E
0x1800ac805  mov     rdx, r12
0x1800ac808  lea     rcx, [rbp+Source]
0x1800ac80c  mov     ebx, r13d
0x1800ac80f  call    AslGuidToString_UStr
0x1800ac814  test    eax, eax
0x1800ac816  jns     short loc_1800AC842
0x1800ac818  lea     r9, aFailedToConver_0; "Failed to convert guid to string [%x]"
0x1800ac81f  mov     dword ptr [rsp+68h+var_48], eax
0x1800ac823  mov     r8d, 948h
0x1800ac829  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1800ac830  mov     ecx, 1
0x1800ac835  mov     r15, r13
0x1800ac838  call    AslLogCallPrintf
0x1800ac83d  jmp     loc_1800AC9FB
0x1800ac842  mov     rcx, gs:60h
0x1800ac84b  mov     edx, 8; Flags
0x1800ac850  movzx   r13d, [rbp+Source.Length]
0x1800ac855  add     r13d, 0B8h
0x1800ac85c  mov     r8d, r13d; Size
0x1800ac85f  mov     rcx, [rcx+30h]; HeapHandle
0x1800ac863  call    cs:__imp_RtlAllocateHeap
0x1800ac869  mov     r15, rax
0x1800ac86c  test    rax, rax
0x1800ac86f  jnz     short loc_1800AC89A
0x1800ac871  lea     r9, aFailedToAlloca_8; "Failed to allocate %ld bytes for key pa"...
0x1800ac878  mov     dword ptr [rsp+68h+var_48], r13d
0x1800ac87d  mov     r8d, 95Dh
0x1800ac883  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1800ac88a  lea     ecx, [rax+1]
0x1800ac88d  call    AslLogCallPrintf
0x1800ac892  xor     r13d, r13d
0x1800ac895  jmp     loc_1800AC9FB
0x1800ac89a  mov     [rbp+Destination.MaximumLength], r13w
0x1800ac89f  lea     rdx, Source; "\\Registry\\Machine\\Software\\Microsof"...
0x1800ac8a6  xor     r13d, r13d
0x1800ac8a9  mov     [rbp+Destination.Buffer], rax
0x1800ac8ad  lea     rcx, [rbp+Destination]; Destination
0x1800ac8b1  mov     [rbp+Destination.Length], r13w
0x1800ac8b6  call    cs:__imp_RtlAppendUnicodeToString
0x1800ac8bc  lea     rdx, pszSrch; "\\"
0x1800ac8c3  lea     rcx, [rbp+Destination]; Destination
0x1800ac8c7  call    cs:__imp_RtlAppendUnicodeToString
0x1800ac8cd  lea     rdx, [rbp+Source]; Source
0x1800ac8d1  lea     rcx, [rbp+Destination]; Destination
0x1800ac8d5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800ac8db  lea     rdx, [rbp+Destination]
0x1800ac8df  lea     rcx, [rbp+Handle]
0x1800ac8e3  call    AslRegistryOpenKey_UStr
0x1800ac8e8  test    eax, eax
0x1800ac8ea  jns     short loc_1800AC91B
0x1800ac8ec  mov     [rsp+68h+var_40], eax
0x1800ac8f0  lea     r9, aFailedToOpenKe; "Failed to open Key \"%ws\" [%x]"
0x1800ac8f7  mov     rax, [rbp+Destination.Buffer]
0x1800ac8fb  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1800ac902  mov     r8d, 96Dh
0x1800ac908  mov     [rsp+68h+var_48], rax
0x1800ac90d  lea     ecx, [r13+1]
0x1800ac911  call    AslLogCallPrintf
0x1800ac916  jmp     loc_1800AC9FB
0x1800ac91b  test    r14, r14
0x1800ac91e  jz      short loc_1800AC96C
0x1800ac920  mov     rdx, [rbp+Handle]
0x1800ac924  lea     r8, g_ustrDatabaseType
0x1800ac92b  lea     rcx, [rbp+arg_28]
0x1800ac92f  call    AslRegistryGetUInt32_UStr
0x1800ac934  test    eax, eax
0x1800ac936  jns     short loc_1800AC962
0x1800ac938  lea     r9, aFailedToGetDat_0; "Failed to get database type [%x]"
0x1800ac93f  mov     dword ptr [rsp+68h+var_48], eax
0x1800ac943  mov     r8d, 979h
0x1800ac949  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1800ac950  mov     ecx, 1
0x1800ac955  call    AslLogCallPrintf
0x1800ac95a  mov     [r14], r13d
0x1800ac95d  jmp     loc_1800AC9FB
0x1800ac962  mov     eax, [rbp+arg_28]
0x1800ac965  btr     eax, 1Fh
0x1800ac969  mov     [r14], eax
0x1800ac96c  test    rdi, rdi
0x1800ac96f  jz      short loc_1800AC9B5
0x1800ac971  mov     rdx, [rbp+Handle]
0x1800ac975  lea     r8, g_ustrRuntimePlatform; ".0"
0x1800ac97c  lea     rcx, [rbp+var_38]
0x1800ac980  call    AslRegistryGetUInt32_UStr
0x1800ac985  test    eax, eax
0x1800ac987  jns     short loc_1800AC9B0
0x1800ac989  lea     r9, aFailedToGetRun; "Failed to get runtime platform [%x]"
0x1800ac990  mov     dword ptr [rsp+68h+var_48], eax
0x1800ac994  mov     r8d, 989h
0x1800ac99a  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1800ac9a1  mov     ecx, 1
0x1800ac9a6  call    AslLogCallPrintf
0x1800ac9ab  mov     [rdi], r13d
0x1800ac9ae  jmp     short loc_1800AC9FB
0x1800ac9b0  mov     eax, [rbp+var_38]
0x1800ac9b3  mov     [rdi], eax
0x1800ac9b5  mov     r9, [rbp+arg_0]
0x1800ac9b9  mov     r8, r12
0x1800ac9bc  add     r9, 248h
0x1800ac9c3  mov     rcx, rsi
0x1800ac9c6  call    SdbGetPathCustomSdb
0x1800ac9cb  test    eax, eax
0x1800ac9cd  jnz     short loc_1800AC9ED
0x1800ac9cf  lea     r9, aSdbgetpathcust; "SdbGetPathCustomSdb failed to get the d"...
0x1800ac9d6  mov     r8d, 992h
0x1800ac9dc  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1800ac9e3  lea     ecx, [rax+1]
0x1800ac9e6  call    AslLogCallPrintf
0x1800ac9eb  jmp     short loc_1800AC9FB
0x1800ac9ed  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ac9f1  inc     rbx
0x1800ac9f4  cmp     [rsi+rbx*2], r13w
0x1800ac9f9  jnz     short loc_1800AC9F1
0x1800ac9fb  mov     rcx, [rbp+Handle]; Handle
0x1800ac9ff  test    rcx, rcx
0x1800aca02  jz      short loc_1800ACA0A
0x1800aca04  call    cs:__imp_ZwClose
0x1800aca0a  test    r15, r15
0x1800aca0d  jz      short loc_1800ACA24
0x1800aca0f  mov     rcx, gs:60h
0x1800aca18  mov     rdx, r15
0x1800aca1b  mov     rcx, [rcx+30h]
0x1800aca1f  call    AslFree
0x1800aca24  cmp     [rbp+Source.Buffer], r13
0x1800aca28  jz      loc_1800AC7FE
0x1800aca2e  lea     rcx, [rbp+Source]
0x1800aca32  call    AslUnicodeStringFree
0x1800aca37  jmp     loc_1800AC7FE
0x1800aca3c  xor     eax, eax
0x1800aca3e  add     rsp, 68h
0x1800aca42  pop     r15
0x1800aca44  pop     r14
0x1800aca46  pop     r13
0x1800aca48  pop     r12
0x1800aca4a  pop     rdi
0x1800aca4b  pop     rsi
0x1800aca4c  pop     rbx
0x1800aca4d  pop     rbp
0x1800aca4e  retn
```
