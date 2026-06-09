# WriteKeyToStore

- ea: `0x180029004`
- end: `0x1800294dd`
- name: `WriteKeyToStore`
- size: `1241`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `7`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180011678`
- `0x180014dd0`
- `0x18002a0c0`
- `0x18002b460`
- `0x180033a10`
- `0x18003568c`
- `0x18005c514`

## callees

- `0x1800060e0`
- `0x180006744`
- `0x180008840`
- `0x1800090c0`
- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180010530`
- `0x1800128ac`
- `0x1800138f4`
- `0x18001e4cc`
- `0x1800201c0`
- `0x1800202c4`
- `0x180023ef8`
- `0x180029004`
- `0x180046eb0`
- `0x180047254`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029468`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029488`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002929a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002929a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800293b5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800293b5`

## string_xrefs

- `0x180029074`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180029108`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18002914b`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180029198`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x1800291e7`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180029266`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x1800292c3`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x1800293d7`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180029425`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall WriteKeyToStore(__int64 a1, int a2, int a3)
{
  __int64 v3; // r14
  int v5; // r12d
  _WORD *v7; // rsi
  int v8; // r15d
  unsigned int v9; // eax
  unsigned int LastError; // edi
  __int64 v11; // r9
  __int64 v12; // rcx
  LPCVOID v13; // r15
  DWORD v14; // r12d
  wchar_t *v15; // rax
  unsigned int v16; // eax
  unsigned int UserDirectory; // eax
  _WORD *v18; // rcx
  __int64 v19; // rax
  unsigned int NestedDirectories; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // r9d
  SECURITY_INFORMATION v24; // edx
  int v25; // eax
  ULONG SecurityDescriptorSize; // [rsp+40h] [rbp-30h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-2Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  _WORD *v30; // [rsp+50h] [rbp-20h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-18h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+60h] [rbp-10h] BYREF
  int v33; // [rsp+B0h] [rbp+40h]
  DWORD nNumberOfBytesToWrite; // [rsp+C8h] [rbp+58h] BYREF

  v3 = -1;
  v30 = 0;
  hFile = (HANDLE)-1LL;
  v5 = a3;
  v7 = 0;
  NumberOfBytesWritten = 0;
  v8 = 0;
  lpBuffer[0] = 0;
  nNumberOfBytesToWrite = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  v33 = 0;
  if ( !*(_QWORD *)(a1 + 240) )
  {
    v9 = ProtectPrivateKey(a1, a1 + 240, a1 + 248);
    LastError = v9;
    if ( v9 )
    {
      v11 = 1729;
LABEL_4:
      DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v11);
      goto LABEL_47;
    }
  }
  UpdateLastModifiedProperty(a1);
  DiagnosabilityUpdateProperties(a1);
  v9 = SerializeKeyForStorage(a1, lpBuffer, &nNumberOfBytesToWrite);
  LastError = v9;
  if ( v9 )
  {
    v11 = 1754;
    goto LABEL_4;
  }
  v12 = *(_QWORD *)(a1 + 224);
  if ( v12 )
    MSCryptFree(v12);
  v13 = lpBuffer[0];
  v14 = nNumberOfBytesToWrite;
  *(LPCVOID *)(a1 + 224) = lpBuffer[0];
  *(_DWORD *)(a1 + 232) = v14;
  if ( *(_QWORD *)(a1 + 16) )
    goto LABEL_15;
  v15 = (wchar_t *)SafeAllocaAllocateFromHeap(222);
  *(_QWORD *)(a1 + 16) = v15;
  if ( v15 )
  {
    v16 = AddMachineGuidAndAppContainerSidHashToContainerNameW(*(STRSAFE_PCNZWCH *)(a1 + 8), *(_DWORD *)(a1 + 528), v15);
    LastError = v16;
    if ( v16 )
    {
      DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1793);
      MSCryptFree(*(_QWORD *)(a1 + 16));
      *(_QWORD *)(a1 + 16) = 0;
      goto LABEL_12;
    }
LABEL_15:
    UserDirectory = GetUserDirectory(*(unsigned int *)(a1 + 32), *(_QWORD *)(a1 + 80) != 0, *(_QWORD *)(a1 + 72), &v30);
    LastError = UserDirectory;
    if ( UserDirectory )
    {
      DebugTraceError(UserDirectory, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1809);
      v7 = v30;
LABEL_45:
      v8 = v33;
      goto LABEL_46;
    }
    v18 = *(_WORD **)(a1 + 72);
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    v7 = v30;
    NestedDirectories = CreateNestedDirectories(v18, &v30[v19 + 1]);
    LastError = NestedDirectories;
    if ( NestedDirectories )
    {
      DebugTraceError(NestedDirectories, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1824);
      goto LABEL_45;
    }
    LastError = OpenFileInStorageArea(*(_DWORD *)(a1 + 32), 0x40000000u, v7, *(_WORD **)(a1 + 16), &hFile);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_aa991306b93132f591cbba2128657ece_Traceguids,
          (_DWORD)v7,
          *(_QWORD *)(a1 + 16));
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1839);
      v3 = (__int64)hFile;
      goto LABEL_45;
    }
    v3 = (__int64)hFile;
    if ( !WriteFile(hFile, v13, v14, &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1846);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_aa991306b93132f591cbba2128657ece_Traceguids,
          (_DWORD)v7,
          *(_QWORD *)(a1 + 16));
      KspCryptAuditKeyFileOperation(0, v22, a1, v7, *(_QWORD *)(a1 + 16), 2459, LastError);
      goto LABEL_31;
    }
    KspCryptAuditKeyFileOperation(1, v21, a1, v7, *(_QWORD *)(a1 + 16), 2459, 0);
    if ( a2 )
    {
      if ( *(_QWORD *)(a1 + 272) )
      {
        v24 = *(_DWORD *)(a1 + 268);
        v8 = 0;
        SecurityDescriptor = *(PSECURITY_DESCRIPTOR *)(a1 + 272);
        SecurityDescriptorSize = *(_DWORD *)(a1 + 280);
        *(_QWORD *)(a1 + 272) = 0;
      }
      else
      {
        v24 = 0;
        if ( *(_DWORD *)(a1 + 32) )
        {
          if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                  L"D:P(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)",
                  1u,
                  &SecurityDescriptor,
                  &SecurityDescriptorSize) )
          {
            LastError = GetLastError();
            DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1904);
LABEL_31:
            v8 = 0;
            goto LABEL_46;
          }
          v24 = 4;
          v8 = 1;
          v33 = 1;
        }
        else
        {
          v8 = 0;
        }
      }
      if ( SecurityDescriptor )
      {
        v25 = SetSecurityOnKeyFile(a1, v24, SecurityDescriptor, v23);
        LastError = v25;
        if ( v25 < 0 )
        {
          DebugTraceError(
            (unsigned int)v25,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
            1930);
          goto LABEL_46;
        }
      }
    }
    if ( *(_DWORD *)(a1 + 148) )
      LastError = MarkPerBootKeyForDeletion(a1, v7);
    goto LABEL_45;
  }
  LastError = -2146893810;
  DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1781);
LABEL_12:
  v8 = 0;
LABEL_46:
  v5 = a3;
LABEL_47:
  if ( SecurityDescriptor )
  {
    if ( v8 )
      LocalFree(SecurityDescriptor);
    else
      MSCryptFree(SecurityDescriptor);
  }
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  if ( v7 )
    MSCryptFree(v7);
  EtwLogNCryptKeyWrite(
    *(_QWORD *)(a1 + 56),
    *(_QWORD *)(a1 + 8),
    *(_QWORD *)(a1 + 16),
    *(_DWORD *)(a1 + 564),
    v5,
    LastError);
  return LastError;
}

```

## disassembly

```asm
0x180029004  mov     [rsp-38h+arg_8], rbx
0x180029009  mov     [rsp-38h+arg_10], r8d
0x18002900e  push    rbp
0x18002900f  push    rsi
0x180029010  push    rdi
0x180029011  push    r12
0x180029013  push    r13
0x180029015  push    r14
0x180029017  push    r15
0x180029019  mov     rbp, rsp
0x18002901c  sub     rsp, 70h
0x180029020  xor     eax, eax
0x180029022  or      r14, 0FFFFFFFFFFFFFFFFh
0x180029026  mov     r13d, edx
0x180029029  mov     [rbp+var_20], rax
0x18002902d  lea     rdx, [rcx+0F0h]
0x180029034  mov     [rbp+hFile], r14
0x180029038  mov     r12d, r8d
0x18002903b  mov     rbx, rcx
0x18002903e  mov     esi, eax
0x180029040  mov     [rbp+NumberOfBytesWritten], eax
0x180029043  mov     r15d, eax
0x180029046  mov     [rbp+lpBuffer], rax
0x18002904a  mov     [rbp+nNumberOfBytesToWrite], eax
0x18002904d  mov     [rbp+SecurityDescriptor], rax
0x180029051  mov     [rbp+SecurityDescriptorSize], eax
0x180029054  mov     [rbp+arg_0], eax
0x180029057  cmp     [rdx], rax
0x18002905a  jnz     short loc_18002908E
0x18002905c  lea     r8, [rcx+0F8h]
0x180029063  call    ProtectPrivateKey
0x180029068  mov     edi, eax
0x18002906a  test    eax, eax
0x18002906c  jz      short loc_18002908E
0x18002906e  mov     r9d, 6C1h
0x180029074  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002907b  mov     ecx, eax
0x18002907d  lea     rdx, aStatus; "Status"
0x180029084  call    DebugTraceError
0x180029089  jmp     loc_18002945A
0x18002908e  mov     rcx, rbx
0x180029091  call    UpdateLastModifiedProperty
0x180029096  mov     rcx, rbx
0x180029099  call    DiagnosabilityUpdateProperties
0x18002909e  lea     r8, [rbp+nNumberOfBytesToWrite]
0x1800290a2  mov     rcx, rbx
0x1800290a5  lea     rdx, [rbp+lpBuffer]
0x1800290a9  call    SerializeKeyForStorage
0x1800290ae  mov     edi, eax
0x1800290b0  test    eax, eax
0x1800290b2  jz      short loc_1800290BC
0x1800290b4  mov     r9d, 6DAh
0x1800290ba  jmp     short loc_180029074
0x1800290bc  mov     rcx, [rbx+0E0h]
0x1800290c3  xor     edi, edi
0x1800290c5  test    rcx, rcx
0x1800290c8  jz      short loc_1800290CF
0x1800290ca  call    MSCryptFree
0x1800290cf  mov     r15, [rbp+lpBuffer]
0x1800290d3  mov     r12d, [rbp+nNumberOfBytesToWrite]
0x1800290d7  mov     [rbx+0E0h], r15
0x1800290de  mov     [rbx+0E8h], r12d
0x1800290e5  cmp     [rbx+10h], rdi
0x1800290e9  jnz     loc_180029171
0x1800290ef  mov     ecx, 0DEh
0x1800290f4  call    SafeAllocaAllocateFromHeap
0x1800290f9  mov     [rbx+10h], rax
0x1800290fd  test    rax, rax
0x180029100  jnz     short loc_18002912D
0x180029102  mov     r9d, 6F5h
0x180029108  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002910f  lea     rdx, aStatus; "Status"
0x180029116  mov     ecx, 8009000Eh
0x18002911b  mov     edi, 8009000Eh
0x180029120  call    DebugTraceError
0x180029125  mov     r15d, esi
0x180029128  jmp     loc_180029456
0x18002912d  mov     edx, [rbx+210h]
0x180029133  mov     r8, rax
0x180029136  mov     rcx, [rbx+8]; pszSrc
0x18002913a  call    AddMachineGuidAndAppContainerSidHashToContainerNameW
0x18002913f  mov     edi, eax
0x180029141  test    eax, eax
0x180029143  jz      short loc_18002916F
0x180029145  mov     r9d, 701h
0x18002914b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180029152  lea     rdx, aStatus; "Status"
0x180029159  mov     ecx, eax
0x18002915b  call    DebugTraceError
0x180029160  mov     rcx, [rbx+10h]
0x180029164  call    MSCryptFree
0x180029169  mov     [rbx+10h], rsi
0x18002916d  jmp     short loc_180029125
0x18002916f  xor     edi, edi
0x180029171  cmp     [rbx+50h], rdi
0x180029175  lea     r9, [rbp+var_20]
0x180029179  mov     r8, [rbx+48h]
0x18002917d  mov     edx, edi
0x18002917f  mov     ecx, [rbx+20h]
0x180029182  setnz   dl
0x180029185  call    GetUserDirectory
0x18002918a  xor     edx, edx
0x18002918c  mov     edi, eax
0x18002918e  test    eax, eax
0x180029190  jz      short loc_1800291B6
0x180029192  mov     r9d, 711h
0x180029198  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002919f  lea     rdx, aStatus; "Status"
0x1800291a6  mov     ecx, eax
0x1800291a8  call    DebugTraceError
0x1800291ad  mov     rsi, [rbp+var_20]
0x1800291b1  jmp     loc_180029452
0x1800291b6  mov     rcx, [rbx+48h]; Src
0x1800291ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800291be  inc     rax
0x1800291c1  cmp     [rcx+rax*2], dx
0x1800291c5  jnz     short loc_1800291BE
0x1800291c7  mov     rsi, [rbp+var_20]
0x1800291cb  inc     rax
0x1800291ce  mov     r8d, [rbx+20h]
0x1800291d2  lea     rdx, [rsi+rax*2]; void *
0x1800291d6  call    CreateNestedDirectories
0x1800291db  mov     edi, eax
0x1800291dd  test    eax, eax
0x1800291df  jz      short loc_180029201
0x1800291e1  mov     r9d, 720h
0x1800291e7  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800291ee  lea     rdx, aStatus; "Status"
0x1800291f5  mov     ecx, eax
0x1800291f7  call    DebugTraceError
0x1800291fc  jmp     loc_180029452
0x180029201  mov     r9, [rbx+10h]
0x180029205  lea     rax, [rbp+hFile]
0x180029209  mov     ecx, [rbx+20h]
0x18002920c  mov     r8, rsi
0x18002920f  mov     edx, 40000000h
0x180029214  mov     [rsp+70h+lpOverlapped], rax
0x180029219  call    OpenFileInStorageArea
0x18002921e  mov     edi, eax
0x180029220  xor     eax, eax
0x180029222  test    edi, edi
0x180029224  jz      short loc_180029284
0x180029226  mov     rcx, cs:WPP_GLOBAL_Control
0x18002922d  lea     rax, WPP_GLOBAL_Control
0x180029234  cmp     rcx, rax
0x180029237  jz      short loc_180029260
0x180029239  test    byte ptr [rcx+1Ch], 1
0x18002923d  jz      short loc_180029260
0x18002923f  mov     rax, [rbx+10h]
0x180029243  lea     r8, WPP_aa991306b93132f591cbba2128657ece_Traceguids
0x18002924a  mov     rcx, [rcx+10h]
0x18002924e  mov     edx, 11h
0x180029253  mov     r9, rsi
0x180029256  mov     [rsp+70h+lpOverlapped], rax
0x18002925b  call    WPP_SF_SS
0x180029260  mov     r9d, 72Fh
0x180029266  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002926d  lea     rdx, aStatus; "Status"
0x180029274  mov     ecx, edi
0x180029276  call    DebugTraceError
0x18002927b  mov     r14, [rbp+hFile]
0x18002927f  jmp     loc_180029452
0x180029284  mov     r14, [rbp+hFile]
0x180029288  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002928c  mov     rcx, r14; hFile
0x18002928f  mov     [rsp+70h+lpOverlapped], rax; lpOverlapped
0x180029294  mov     r8d, r12d; nNumberOfBytesToWrite
0x180029297  mov     rdx, r15; lpBuffer
0x18002929a  call    cs:__imp_WriteFile
0x1800292a1  nop     dword ptr [rax+rax+00h]
0x1800292a6  xor     r12d, r12d
0x1800292a9  test    eax, eax
0x1800292ab  jnz     loc_18002933E
0x1800292b1  call    cs:__imp_GetLastError
0x1800292b8  nop     dword ptr [rax+rax+00h]
0x1800292bd  mov     r9d, 736h
0x1800292c3  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800292ca  mov     ecx, eax
0x1800292cc  lea     rdx, aStatus; "Status"
0x1800292d3  mov     edi, eax
0x1800292d5  call    DebugTraceError
0x1800292da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292e1  lea     rax, WPP_GLOBAL_Control
0x1800292e8  cmp     rcx, rax
0x1800292eb  jz      short loc_180029314
0x1800292ed  test    byte ptr [rcx+1Ch], 1
0x1800292f1  jz      short loc_180029314
0x1800292f3  mov     rax, [rbx+10h]
0x1800292f7  lea     edx, [r12+12h]
0x1800292fc  mov     rcx, [rcx+10h]
0x180029300  lea     r8, WPP_aa991306b93132f591cbba2128657ece_Traceguids
0x180029307  mov     r9, rsi
0x18002930a  mov     [rsp+70h+lpOverlapped], rax
0x18002930f  call    WPP_SF_SS
0x180029314  mov     rax, [rbx+10h]
0x180029318  mov     r9, rsi
0x18002931b  mov     [rsp+70h+var_40], edi
0x18002931f  mov     r8, rbx
0x180029322  mov     [rsp+70h+var_48], 99Bh
0x18002932a  xor     ecx, ecx
0x18002932c  mov     [rsp+70h+lpOverlapped], rax
0x180029331  call    KspCryptAuditKeyFileOperation
0x180029336  mov     r15d, r12d
0x180029339  jmp     loc_180029456
0x18002933e  mov     rax, [rbx+10h]
0x180029342  mov     r9, rsi
0x180029345  mov     [rsp+70h+var_40], r12d
0x18002934a  mov     r8, rbx
0x18002934d  mov     [rsp+70h+var_48], 99Bh
0x180029355  mov     ecx, 1
0x18002935a  mov     [rsp+70h+lpOverlapped], rax
0x18002935f  call    KspCryptAuditKeyFileOperation
0x180029364  test    r13d, r13d
0x180029367  jz      loc_18002943C
0x18002936d  mov     rax, [rbx+110h]
0x180029374  test    rax, rax
0x180029377  jz      short loc_180029398
0x180029379  mov     edx, [rbx+10Ch]
0x18002937f  mov     r15d, r12d
0x180029382  mov     [rbp+SecurityDescriptor], rax
0x180029386  mov     eax, [rbx+118h]
0x18002938c  mov     [rbp+SecurityDescriptorSize], eax
0x18002938f  mov     [rbx+110h], r12
0x180029396  jmp     short loc_180029405
0x180029398  mov     edx, r12d
0x18002939b  cmp     [rbx+20h], r12d
0x18002939f  jz      short loc_180029402
0x1800293a1  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800293a5  mov     edx, 1; StringSDRevision
0x1800293aa  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800293ae  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)"
0x1800293b5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800293bc  nop     dword ptr [rax+rax+00h]
0x1800293c1  test    eax, eax
0x1800293c3  jnz     short loc_1800293F3
0x1800293c5  call    cs:__imp_GetLastError
0x1800293cc  nop     dword ptr [rax+rax+00h]
0x1800293d1  mov     r9d, 770h
0x1800293d7  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800293de  mov     ecx, eax
0x1800293e0  lea     rdx, aStatus; "Status"
0x1800293e7  mov     edi, eax
0x1800293e9  call    DebugTraceError
0x1800293ee  jmp     loc_180029336
0x1800293f3  mov     edx, 4
0x1800293f8  lea     r15d, [rdx-3]
0x1800293fc  mov     [rbp+arg_0], r15d
0x180029400  jmp     short loc_180029405
0x180029402  mov     r15d, edx
0x180029405  mov     rcx, [rbp+SecurityDescriptor]
0x180029409  test    rcx, rcx
0x18002940c  jz      short loc_18002943C
0x18002940e  mov     r8, rcx
0x180029411  mov     rcx, rbx
0x180029414  call    SetSecurityOnKeyFile
0x180029419  mov     edi, eax
0x18002941b  test    eax, eax
0x18002941d  jns     short loc_18002943C
0x18002941f  mov     r9d, 78Ah
0x180029425  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002942c  lea     rdx, aStatus; "Status"
0x180029433  mov     ecx, eax
0x180029435  call    DebugTraceError
0x18002943a  jmp     short loc_180029456
0x18002943c  cmp     [rbx+94h], r12d
0x180029443  jz      short loc_180029452
0x180029445  mov     rdx, rsi
0x180029448  mov     rcx, rbx
0x18002944b  call    MarkPerBootKeyForDeletion
0x180029450  mov     edi, eax
0x180029452  mov     r15d, [rbp+arg_0]
0x180029456  mov     r12d, [rbp+arg_10]
0x18002945a  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18002945e  test    rcx, rcx
0x180029461  jz      short loc_18002947F
0x180029463  test    r15d, r15d
0x180029466  jz      short loc_180029476
0x180029468  call    cs:__imp_LocalFree
0x18002946f  nop     dword ptr [rax+rax+00h]
0x180029474  jmp     short loc_18002947F
0x180029476  mov     rcx, [rbp+SecurityDescriptor]
0x18002947a  call    MSCryptFree
0x18002947f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180029483  jz      short loc_180029494
0x180029485  mov     rcx, r14; hObject
0x180029488  call    cs:__imp_CloseHandle
0x18002948f  nop     dword ptr [rax+rax+00h]
0x180029494  test    rsi, rsi
0x180029497  jz      short loc_1800294A1
0x180029499  mov     rcx, rsi
0x18002949c  call    MSCryptFree
0x1800294a1  mov     r9d, [rbx+234h]
0x1800294a8  mov     r8, [rbx+10h]
0x1800294ac  mov     rdx, [rbx+8]
0x1800294b0  mov     rcx, [rbx+38h]
0x1800294b4  mov     [rsp+70h+var_48], edi
0x1800294b8  mov     dword ptr [rsp+70h+lpOverlapped], r12d
0x1800294bd  call    EtwLogNCryptKeyWrite
0x1800294c2  mov     rbx, [rsp+70h+arg_8]
0x1800294ca  mov     eax, edi
  ... truncated ...
```
