# GetSecurityOnKeyFile

- ea: `0x180004f8c`
- end: `0x180005288`
- name: `GetSecurityOnKeyFile`
- size: `764`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180032c10`

## callees

- `0x180004c04`
- `0x180004f8c`
- `0x1800060e0`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x180025534`
- `0x18004679c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051db`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005089`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005134`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005089`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005134`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800051cb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800051cb`

## string_xrefs

- `0x180004fd4`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000501b`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180005052`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x1800050f1`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000517a`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x1800051ef`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall GetSecurityOnKeyFile(__int64 a1, SECURITY_INFORMATION a2, _QWORD *a3, DWORD *a4)
{
  const WCHAR *v4; // rsi
  DWORD LastError; // ebx
  DWORD UserDirectory; // eax
  __int64 v10; // r9
  DWORD KeyFileFullPath; // eax
  int v12; // edx
  void *v13; // r14
  DWORD v14; // eax
  PSECURITY_DESCRIPTOR v15; // rdi
  DWORD v16; // eax
  __int64 v17; // r9
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-18h] BYREF
  void *Src; // [rsp+50h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-8h] BYREF
  DWORD nLengthNeeded; // [rsp+90h] [rbp+30h] BYREF
  _QWORD *v24; // [rsp+A0h] [rbp+40h]

  v24 = a3;
  v4 = 0;
  Src = 0;
  lpFileName = 0;
  pSecurityDescriptor = 0;
  nLengthNeeded = 0;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    LastError = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 4657);
    return LastError;
  }
  UserDirectory = GetUserDirectory(*(unsigned int *)(a1 + 32), *(_QWORD *)(a1 + 80) != 0, *(_WORD **)(a1 + 72), &Src);
  LastError = UserDirectory;
  if ( !UserDirectory )
  {
    KeyFileFullPath = GetKeyFileFullPath(Src, *(_WORD **)(a1 + 16), &lpFileName);
    LastError = KeyFileFullPath;
    if ( KeyFileFullPath )
    {
      DebugTraceError(KeyFileFullPath, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 4681);
      v4 = lpFileName;
      goto LABEL_29;
    }
    v4 = lpFileName;
    if ( !GetFileSecurityW(lpFileName, a2, 0, 0, &nLengthNeeded) )
    {
      UserDirectory = GetLastError();
      LastError = UserDirectory;
      if ( UserDirectory != 122 )
      {
        v10 = 4700;
        goto LABEL_5;
      }
    }
    v13 = (void *)SafeAllocaAllocateFromHeap(nLengthNeeded);
    if ( !v13 )
    {
      LastError = -2146893810;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
          101);
      goto LABEL_29;
    }
    if ( !GetFileSecurityW(v4, a2, v13, nLengthNeeded, &nLengthNeeded) )
    {
      LastError = GetLastError();
LABEL_28:
      MSCryptFree(v13);
      goto LABEL_29;
    }
    nLengthNeeded = 0;
    v14 = ConvertContainerSecurityDescriptor(v13);
    LastError = v14;
    if ( v14 )
    {
      DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 4734);
      goto LABEL_28;
    }
    v15 = pSecurityDescriptor;
    if ( (a2 & 4) != 0 )
    {
      LODWORD(pSecurityDescriptor) = 0;
      LODWORD(lpFileName) = 0;
      pDacl = 0;
      if ( !GetSecurityDescriptorDacl(v15, (LPBOOL)&pSecurityDescriptor, &pDacl, (LPBOOL)&lpFileName) )
      {
        v16 = GetLastError();
        LastError = v16;
        v17 = 4751;
LABEL_22:
        DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v17);
        goto LABEL_28;
      }
      if ( (_DWORD)pSecurityDescriptor )
      {
        if ( pDacl )
        {
          v16 = CheckAndChangeAccessMasks(pDacl);
          LastError = v16;
          if ( v16 )
          {
            v17 = 4760;
            goto LABEL_22;
          }
        }
      }
    }
    *v24 = v15;
    LastError = 0;
    *a4 = nLengthNeeded;
    goto LABEL_28;
  }
  v10 = 4671;
LABEL_5:
  DebugTraceError(UserDirectory, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v10);
LABEL_29:
  if ( Src )
    MSCryptFree(Src);
  if ( v4 )
    MSCryptFree(v4);
  return LastError;
}

```

## disassembly

```asm
0x180004f8c  mov     [rsp-28h+arg_8], rbx
0x180004f91  mov     [rsp-28h+arg_18], rsi
0x180004f96  mov     [rsp-28h+arg_10], r8
0x180004f9b  push    rbp
0x180004f9c  push    rdi
0x180004f9d  push    r13
0x180004f9f  push    r14
0x180004fa1  push    r15
0x180004fa3  mov     rbp, rsp
0x180004fa6  sub     rsp, 60h
0x180004faa  xor     esi, esi
0x180004fac  mov     [rbp+Src], 0
0x180004fb4  mov     r13, r9
0x180004fb7  mov     r15d, edx
0x180004fba  mov     rdi, rcx
0x180004fbd  mov     [rbp+lpFileName], rsi
0x180004fc1  mov     [rbp+pSecurityDescriptor], rsi
0x180004fc5  mov     [rbp+nLengthNeeded], esi
0x180004fc8  cmp     [rcx+10h], rsi
0x180004fcc  jnz     short loc_180004FF6
0x180004fce  mov     r9d, 1231h
0x180004fd4  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004fdb  lea     rdx, aStatus; "Status"
0x180004fe2  mov     ecx, 80090026h
0x180004fe7  mov     ebx, 80090026h
0x180004fec  call    DebugTraceError
0x180004ff1  jmp     loc_18000526C
0x180004ff6  mov     r8, [rcx+48h]
0x180004ffa  lea     r9, [rbp+Src]
0x180004ffe  xor     edx, edx
0x180005000  cmp     [rcx+50h], rdx
0x180005004  mov     ecx, [rcx+20h]
0x180005007  setnz   dl
0x18000500a  call    GetUserDirectory
0x18000500f  mov     ebx, eax
0x180005011  test    eax, eax
0x180005013  jz      short loc_180005035
0x180005015  mov     r9d, 123Fh
0x18000501b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005022  mov     ecx, eax
0x180005024  lea     rdx, aStatus; "Status"
0x18000502b  call    DebugTraceError
0x180005030  jmp     loc_18000524F
0x180005035  mov     rdx, [rdi+10h]; void *
0x180005039  lea     r8, [rbp+lpFileName]
0x18000503d  mov     rcx, [rbp+Src]; Src
0x180005041  call    GetKeyFileFullPath
0x180005046  mov     ebx, eax
0x180005048  test    eax, eax
0x18000504a  jz      short loc_180005070
0x18000504c  mov     r9d, 1249h
0x180005052  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005059  lea     rdx, aStatus; "Status"
0x180005060  mov     ecx, eax
0x180005062  call    DebugTraceError
0x180005067  mov     rsi, [rbp+lpFileName]
0x18000506b  jmp     loc_18000524F
0x180005070  mov     rsi, [rbp+lpFileName]
0x180005074  lea     rax, [rbp+nLengthNeeded]
0x180005078  mov     rcx, rsi; lpFileName
0x18000507b  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180005080  xor     r9d, r9d; nLength
0x180005083  xor     r8d, r8d; pSecurityDescriptor
0x180005086  mov     edx, r15d; RequestedInformation
0x180005089  call    cs:__imp_GetFileSecurityW
0x180005090  nop     dword ptr [rax+rax+00h]
0x180005095  test    eax, eax
0x180005097  jnz     short loc_1800050B7
0x180005099  call    cs:__imp_GetLastError
0x1800050a0  nop     dword ptr [rax+rax+00h]
0x1800050a5  mov     ebx, eax
0x1800050a7  cmp     eax, 7Ah ; 'z'
0x1800050aa  jz      short loc_1800050B7
0x1800050ac  mov     r9d, 125Ch
0x1800050b2  jmp     loc_18000501B
0x1800050b7  mov     ecx, [rbp+nLengthNeeded]
0x1800050ba  call    SafeAllocaAllocateFromHeap
0x1800050bf  mov     r14, rax
0x1800050c2  test    rax, rax
0x1800050c5  jnz     short loc_18000511E
0x1800050c7  mov     ebx, 8009000Eh
0x1800050cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050d3  lea     rax, WPP_GLOBAL_Control
0x1800050da  cmp     rcx, rax
0x1800050dd  jz      loc_18000524F
0x1800050e3  test    byte ptr [rcx+1Ch], 1
0x1800050e7  jz      loc_18000524F
0x1800050ed  mov     rcx, [rcx+10h]
0x1800050f1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800050f8  mov     [rsp+60h+var_30], 1265h
0x180005100  lea     r9, aStatus; "Status"
0x180005107  mov     [rsp+60h+var_38], r8
0x18000510c  mov     dword ptr [rsp+60h+lpnLengthNeeded], 8009000Eh
0x180005114  call    WPP_SF_sDsd
0x180005119  jmp     loc_18000524F
0x18000511e  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180005122  lea     rax, [rbp+nLengthNeeded]
0x180005126  mov     r8, r14; pSecurityDescriptor
0x180005129  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000512e  mov     edx, r15d; RequestedInformation
0x180005131  mov     rcx, rsi; lpFileName
0x180005134  call    cs:__imp_GetFileSecurityW
0x18000513b  nop     dword ptr [rax+rax+00h]
0x180005140  test    eax, eax
0x180005142  jnz     short loc_180005157
0x180005144  call    cs:__imp_GetLastError
0x18000514b  nop     dword ptr [rax+rax+00h]
0x180005150  mov     ebx, eax
0x180005152  jmp     loc_180005247
0x180005157  lea     r8, [rbp+nLengthNeeded]
0x18000515b  mov     [rbp+nLengthNeeded], 0
0x180005162  lea     rdx, [rbp+pSecurityDescriptor]
0x180005166  mov     rcx, r14; AbsoluteSecurityDescriptor
0x180005169  call    ConvertContainerSecurityDescriptor
0x18000516e  mov     ebx, eax
0x180005170  test    eax, eax
0x180005172  jz      short loc_180005198
0x180005174  mov     r9d, 127Eh
0x18000517a  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005181  lea     rdx, aStatus; "Status"
0x180005188  mov     ecx, eax
0x18000518a  call    DebugTraceError
0x18000518f  mov     rdi, [rbp+pSecurityDescriptor]
0x180005193  jmp     loc_18000523A
0x180005198  mov     rdi, [rbp+pSecurityDescriptor]
0x18000519c  test    r15b, 4
0x1800051a0  jz      loc_180005228
0x1800051a6  lea     r9, [rbp+lpFileName]; lpbDaclDefaulted
0x1800051aa  mov     dword ptr [rbp+pSecurityDescriptor], 0
0x1800051b1  lea     r8, [rbp+pDacl]; pDacl
0x1800051b5  mov     dword ptr [rbp+lpFileName], 0
0x1800051bc  lea     rdx, [rbp+pSecurityDescriptor]; lpbDaclPresent
0x1800051c0  mov     [rbp+pDacl], 0
0x1800051c8  mov     rcx, rdi; pSecurityDescriptor
0x1800051cb  call    cs:__imp_GetSecurityDescriptorDacl
0x1800051d2  nop     dword ptr [rax+rax+00h]
0x1800051d7  test    eax, eax
0x1800051d9  jnz     short loc_180005206
0x1800051db  call    cs:__imp_GetLastError
0x1800051e2  nop     dword ptr [rax+rax+00h]
0x1800051e7  mov     ebx, eax
0x1800051e9  mov     r9d, 128Fh
0x1800051ef  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800051f6  mov     ecx, eax
0x1800051f8  lea     rdx, aStatus; "Status"
0x1800051ff  call    DebugTraceError
0x180005204  jmp     short loc_18000523A
0x180005206  cmp     dword ptr [rbp+pSecurityDescriptor], 0
0x18000520a  jz      short loc_180005228
0x18000520c  mov     rcx, [rbp+pDacl]; pAcl
0x180005210  test    rcx, rcx
0x180005213  jz      short loc_180005228
0x180005215  call    CheckAndChangeAccessMasks
0x18000521a  mov     ebx, eax
0x18000521c  test    eax, eax
0x18000521e  jz      short loc_180005228
0x180005220  mov     r9d, 1298h
0x180005226  jmp     short loc_1800051EF
0x180005228  mov     rax, [rbp+arg_10]
0x18000522c  mov     [rax], rdi
0x18000522f  xor     edi, edi
0x180005231  mov     eax, [rbp+nLengthNeeded]
0x180005234  xor     ebx, ebx
0x180005236  mov     [r13+0], eax
0x18000523a  test    rdi, rdi
0x18000523d  jz      short loc_180005247
0x18000523f  mov     rcx, rdi
0x180005242  call    MSCryptFree
0x180005247  mov     rcx, r14
0x18000524a  call    MSCryptFree
0x18000524f  cmp     [rbp+Src], 0
0x180005254  jz      short loc_18000525F
0x180005256  mov     rcx, [rbp+Src]
0x18000525a  call    MSCryptFree
0x18000525f  test    rsi, rsi
0x180005262  jz      short loc_18000526C
0x180005264  mov     rcx, rsi
0x180005267  call    MSCryptFree
0x18000526c  lea     r11, [rsp+60h+var_s0]
0x180005271  mov     eax, ebx
0x180005273  mov     rbx, [r11+38h]
0x180005277  mov     rsi, [r11+48h]
0x18000527b  mov     rsp, r11
0x18000527e  pop     r15
0x180005280  pop     r14
0x180005282  pop     r13
0x180005284  pop     rdi
0x180005285  pop     rbp
0x180005286  retn
```
