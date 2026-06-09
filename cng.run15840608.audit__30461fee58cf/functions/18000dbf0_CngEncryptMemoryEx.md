# CngEncryptMemoryEx

- ea: `0x18000dbf0`
- end: `0x18000e1a4`
- name: `CngEncryptMemoryEx`
- size: `1460`
- prototype: `__int64 __fastcall(char *, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800261c0`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18000d3b0`
- `0x18000d510`
- `0x18000da64`
- `0x18000dbf0`
- `0x18000e1b0`
- `0x18000f3b0`
- `0x180018350`
- `0x180018450`
- `0x180019838`
- `0x18001a3d0`
- `0x18004c3d0`
- `0x18004ca60`
- `0x18005d434`
- `0x18009d820`
- `0x18009d920`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x18000ddf9`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x18000ddf9`
- `ntoskrnl!ZwQueryInformationProcess` at `0x18000dfe8`
- `ntoskrnl!ZwQueryInformationProcess` at `0x18000dfe8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18000de23`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18000df28`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18000de23`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18000df28`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000dfff`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000dfff`
- `ntoskrnl!SeUnlockSubjectContext` at `0x18000de10`
- `ntoskrnl!SeUnlockSubjectContext` at `0x18000df15`
- `ntoskrnl!SeUnlockSubjectContext` at `0x18000de10`
- `ntoskrnl!SeUnlockSubjectContext` at `0x18000df15`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x18000e00e`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x18000e00e`
- `ntoskrnl!SeLockSubjectContext` at `0x18000ddd1`
- `ntoskrnl!SeLockSubjectContext` at `0x18000ddd1`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18000ddbe`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18000ddbe`

## string_xrefs

- `0x18000df95`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`
- `0x18000e088`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`
- `0x18000e164`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`
- `0x18000e186`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`
- `0x18009f7ea`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`

## pseudocode

```c
__int64 __fastcall CngEncryptMemoryEx(char *a1, unsigned int a2, int a3, int a4)
{
  __int64 v5; // r14
  int v8; // edx
  int v9; // edi
  _BYTE *v10; // r13
  _BYTE *v11; // rsi
  unsigned int v12; // r8d
  PACCESS_TOKEN ClientToken; // rax
  char *v14; // rdi
  PACCESS_TOKEN PrimaryToken; // rcx
  unsigned __int8 *p_AuthenticationId; // rdx
  __int64 v18; // r9
  unsigned int v19; // ebx
  int v20; // edx
  NTSTATUS v21; // eax
  unsigned int v22; // r15d
  struct _KPROCESS *CurrentProcess; // rax
  LONGLONG TimeQuadPart; // rax
  int v25; // eax
  unsigned int v26; // esi
  __int64 ProcessInformation; // [rsp+40h] [rbp-C0h] BYREF
  _LUID AuthenticationId; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v30[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v31[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v32[496]; // [rsp+D0h] [rbp-30h] BYREF
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE Buf2[24]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v35; // [rsp+2F8h] [rbp+1F8h] BYREF

  v5 = a2;
  memset(v32, 0, sizeof(v32));
  if ( (v5 & 0xF) != 0 )
  {
    v9 = 0;
    if ( (v5 & 7) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v8,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\encmem.cxx",
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\encmem.cxx",
          121);
      return 3221225485LL;
    }
  }
  else
  {
    v9 = 1;
  }
  if ( !InitializedMemory )
  {
    v25 = CngEncryptMemoryInitialize();
    v26 = v25;
    if ( v25 < 0 )
    {
      DebugTraceError(
        (unsigned int)v25,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\encmem.cxx",
        131);
      return v26;
    }
  }
  if ( a4 == 1 )
  {
    if ( v9 )
    {
      v10 = &g_AESKey;
      goto LABEL_7;
    }
    v11 = &g_DES3Key;
LABEL_13:
    ClientToken = (PACCESS_TOKEN)WPP_MAIN_CB.DeviceQueue.1;
    *(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C *)&v35 = WPP_MAIN_CB.DeviceQueue.1;
    v14 = &a1[v5 & 0xFFFFFFFFFFFFFFF8uLL];
    if ( a3 )
    {
      SubjectContext.ClientToken = (PACCESS_TOKEN)WPP_MAIN_CB.DeviceQueue.1;
      if ( a1 < v14 )
      {
        do
        {
          SubjectContext.ClientToken = (PACCESS_TOKEN)((__int64)SubjectContext.ClientToken ^ *(_QWORD *)a1);
          SymCrypt3DesEncrypt(v11, &SubjectContext, &SubjectContext);
          *(_QWORD *)a1 = SubjectContext.ClientToken;
          a1 += 8;
        }
        while ( a1 < v14 );
        ClientToken = SubjectContext.ClientToken;
      }
      *(_QWORD *)&v35 = ClientToken;
      memset(&SubjectContext, 0, sizeof(SubjectContext));
    }
    else
    {
      for ( *(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C *)&v29[0] = WPP_MAIN_CB.DeviceQueue.1;
            a1 < v14;
            *(_QWORD *)&v29[0] = *(_QWORD *)&v30[0] )
      {
        *(_QWORD *)&v30[0] = *(_QWORD *)a1;
        SymCrypt3DesDecrypt(v11, v30, v31);
        *(_QWORD *)a1 = *(_QWORD *)&v29[0] ^ *(_QWORD *)&v31[0];
        a1 += 8;
        ClientToken = *(PACCESS_TOKEN *)&v30[0];
      }
      *(_QWORD *)&v35 = ClientToken;
      SymCryptWipeAsm(v29, 96);
    }
    goto LABEL_16;
  }
  v10 = v32;
  v11 = v32;
  if ( !a4 )
  {
    LODWORD(ProcessInformation) = 0;
    v21 = ZwQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessCookie, &ProcessInformation, 4u, 0);
    v22 = v21;
    if ( v21 < 0 )
    {
      DebugTraceError(
        (unsigned int)v21,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\encmem.cxx",
        160);
      return v22;
    }
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(CurrentProcess);
    p_AuthenticationId = Buf2;
    *(_DWORD *)Buf2 = ProcessInformation;
    v12 = 12;
    *(_QWORD *)&Buf2[4] = TimeQuadPart;
    goto LABEL_40;
  }
  if ( a4 != 4 && a4 != 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v8,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\encmem.cxx",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\encmem.cxx",
        49);
    return 3221225485LL;
  }
  AuthenticationId = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.ClientToken;
  if ( SubjectContext.ClientToken )
  {
    if ( SubjectContext.ImpersonationLevel <= SecurityIdentification )
    {
      v19 = -1073741659;
      SeUnlockSubjectContext(&SubjectContext);
      SeReleaseSubjectContext(&SubjectContext);
      goto LABEL_34;
    }
  }
  else
  {
    PrimaryToken = SubjectContext.PrimaryToken;
  }
  LODWORD(ProcessInformation) = SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  if ( (int)ProcessInformation >= 0 )
  {
    if ( a4 != 4 )
    {
      p_AuthenticationId = (unsigned __int8 *)&AuthenticationId;
      if ( v9 )
      {
        v29[0] = *(_OWORD *)&WPP_MAIN_CB.Dpc.DpcListEntry.Next;
        v29[1] = *(_OWORD *)&WPP_MAIN_CB.Dpc.DeferredRoutine;
        v30[0] = *(_OWORD *)&WPP_MAIN_CB.Dpc.SystemArgument1;
        v30[1] = *(_OWORD *)&WPP_MAIN_CB.Dpc.DpcData;
        v31[0] = *(_OWORD *)&WPP_MAIN_CB.SecurityDescriptor;
        v31[1] = WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
        v31[2] = *(_OWORD *)&WPP_MAIN_CB.SectorSize;
        v31[3] = *(_OWORD *)&WPP_MAIN_CB.Reserved;
        SymCryptSha1Append(v29, &AuthenticationId, 8);
        SymCryptSha1Result(v29, Buf2);
        LOBYTE(v18) = 1;
        SymCryptAesExpandKeyInternal(v32, Buf2, 16, v18);
        SymCryptWipeAsm(Buf2, 20);
        goto LABEL_7;
      }
      v12 = 8;
      goto LABEL_12;
    }
    *(_QWORD *)Buf2 = 999;
    ProcessInformation = 994;
    if ( !a3 && memcmp(&AuthenticationId, Buf2, 8u) )
    {
      DebugTraceError(
        3221225506LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\encmem.cxx",
        265);
      return 3221225506LL;
    }
    v12 = 8;
    p_AuthenticationId = (unsigned __int8 *)&ProcessInformation;
LABEL_40:
    if ( v9 )
    {
      GenerateAESKey((struct _SYMCRYPT_AES_EXPANDED_KEY *)v32, p_AuthenticationId, v12);
LABEL_7:
      v35 = *(_OWORD *)&WPP_MAIN_CB.DeviceQueue.Busy;
      if ( a3 )
      {
        SymCryptAesCbcEncrypt((_DWORD)v10, (unsigned int)&v35, (_DWORD)a1, (_DWORD)a1, v5);
      }
      else if ( (g_SymCryptCpuFeaturesNotPresent & 6) != 0 )
      {
        SymCryptAesCbcDecryptAsm((_DWORD)v10, (unsigned int)&v35, (_DWORD)a1, (_DWORD)a1, v5);
      }
      else
      {
        SymCryptAesCbcDecryptXmm((_DWORD)v10, (unsigned int)&v35, (_DWORD)a1, (_DWORD)a1, v5);
      }
LABEL_16:
      SymCryptWipeAsm(v32, 496);
      return 0;
    }
LABEL_12:
    GenerateKey((struct _SYMCRYPT_3DES_EXPANDED_KEY *)v32, p_AuthenticationId, v12);
    goto LABEL_13;
  }
  v19 = ProcessInformation;
LABEL_34:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v20 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v20 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v20,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\encmem.cxx",
        (unsigned int)"Status",
        v19,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\encmem.cxx",
        247);
  }
  return v19;
}

```

## disassembly

```asm
0x18000dbf0  mov     [rsp-8+arg_10], rbx
0x18000dbf5  push    rbp
0x18000dbf6  push    rsi
0x18000dbf7  push    rdi
0x18000dbf8  push    r12
0x18000dbfa  push    r13
0x18000dbfc  push    r14
0x18000dbfe  push    r15
0x18000dc00  lea     rbp, [rsp-210h]
0x18000dc08  sub     rsp, 310h
0x18000dc0f  mov     rax, cs:__security_cookie
0x18000dc16  xor     rax, rsp
0x18000dc19  mov     [rbp+240h+var_38], rax
0x18000dc20  mov     r12d, r8d
0x18000dc23  mov     r14d, edx
0x18000dc26  mov     rbx, rcx
0x18000dc29  xor     edx, edx; Val
0x18000dc2b  mov     r8d, 1F0h; Size
0x18000dc31  lea     rcx, [rbp+240h+var_270]; void *
0x18000dc35  mov     r15d, r9d
0x18000dc38  call    memset
0x18000dc3d  xor     r13d, r13d
0x18000dc40  test    r14b, 0Fh
0x18000dc44  jnz     loc_18000DF36
0x18000dc4a  mov     edi, 1
0x18000dc4f  cmp     cs:?InitializedMemory@@3JA, r13d; long InitializedMemory
0x18000dc56  jz      loc_18000E14F
0x18000dc5c  cmp     r15d, 1
0x18000dc60  jnz     loc_18000DD82
0x18000dc66  test    edi, edi
0x18000dc68  jz      short loc_18000DCB5
0x18000dc6a  lea     r13, ?g_AESKey@@3U_SYMCRYPT_AES_EXPANDED_KEY@@A; _SYMCRYPT_AES_EXPANDED_KEY g_AESKey
0x18000dc71  lea     rdx, [rbp+240h+var_48]
0x18000dc78  mov     rcx, r14
0x18000dc7b  mov     [rsp+340h+ReturnLength], rcx
0x18000dc80  mov     r9, rbx
0x18000dc83  mov     r8, rbx
0x18000dc86  mov     rcx, r13
0x18000dc89  movups  xmm0, xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x18000dc90  movups  [rbp+240h+var_48], xmm0
0x18000dc97  test    r12d, r12d
0x18000dc9a  jnz     loc_18000E04E
0x18000dca0  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x18000dca6  test    al, 6
0x18000dca8  jnz     loc_18000E0B2
0x18000dcae  call    SymCryptAesCbcDecryptXmm
0x18000dcb3  jmp     short loc_18000DD12
0x18000dcb5  lea     rsi, ?g_DES3Key@@3U_SYMCRYPT_3DES_EXPANDED_KEY@@A; _SYMCRYPT_3DES_EXPANDED_KEY g_DES3Key
0x18000dcbc  jmp     short loc_18000DCD0
0x18000dcbe  mov     r8d, 8; unsigned int
0x18000dcc4  lea     rcx, [rbp+240h+var_270]; struct _SYMCRYPT_3DES_EXPANDED_KEY *
0x18000dcc8  call    ?GenerateKey@@YAXPEAU_SYMCRYPT_3DES_EXPANDED_KEY@@PEAEK@Z; GenerateKey(_SYMCRYPT_3DES_EXPANDED_KEY *,uchar *,ulong)
0x18000dccd  xor     r13d, r13d
0x18000dcd0  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x18000dcd7  mov     rcx, r14
0x18000dcda  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000dcde  mov     qword ptr [rbp+240h+var_48], rax
0x18000dce5  lea     rdi, [rcx+rbx]
0x18000dce9  test    r12d, r12d
0x18000dcec  jnz     short loc_18000DD4D
0x18000dcee  mov     qword ptr [rsp+340h+var_2F0], rax
0x18000dcf3  cmp     rbx, rdi
0x18000dcf6  jb      loc_18000E0C0
0x18000dcfc  mov     edx, 60h ; '`'
0x18000dd01  mov     qword ptr [rbp+240h+var_48], rax
0x18000dd08  lea     rcx, [rsp+340h+var_2F0]
0x18000dd0d  call    SymCryptWipeAsm
0x18000dd12  mov     edx, 1F0h
0x18000dd17  lea     rcx, [rbp+240h+var_270]
0x18000dd1b  call    SymCryptWipeAsm
0x18000dd20  xor     eax, eax
0x18000dd22  mov     rcx, [rbp+240h+var_38]
0x18000dd29  xor     rcx, rsp; StackCookie
0x18000dd2c  call    __security_check_cookie
0x18000dd31  mov     rbx, [rsp+340h+arg_10]
0x18000dd39  add     rsp, 310h
0x18000dd40  pop     r15
0x18000dd42  pop     r14
0x18000dd44  pop     r13
0x18000dd46  pop     r12
0x18000dd48  pop     rdi
0x18000dd49  pop     rsi
0x18000dd4a  pop     rbp
0x18000dd4b  retn
0x18000dd4d  mov     [rbp+240h+SubjectContext.ClientToken], rax
0x18000dd54  cmp     rbx, rdi
0x18000dd57  jb      loc_18000E103
0x18000dd5d  mov     qword ptr [rbp+240h+var_48], rax
0x18000dd64  mov     [rbp+240h+SubjectContext.ClientToken], r13
0x18000dd6b  mov     qword ptr [rbp+240h+SubjectContext.ImpersonationLevel], r13
0x18000dd72  mov     [rbp+240h+SubjectContext.PrimaryToken], r13
0x18000dd79  mov     [rbp+240h+SubjectContext.ProcessAuditId], r13
0x18000dd80  jmp     short loc_18000DD12
0x18000dd82  lea     r13, [rbp+240h+var_270]
0x18000dd86  lea     rsi, [rbp+240h+var_270]
0x18000dd8a  test    r15d, r15d
0x18000dd8d  jz      loc_18000DFC0
0x18000dd93  cmp     r15d, 4
0x18000dd97  jnz     loc_18000E058
0x18000dd9d  xorps   xmm0, xmm0
0x18000dda0  mov     qword ptr [rsp+340h+AuthenticationId.LowPart], 0
0x18000dda9  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x18000ddb0  movups  xmmword ptr [rbp+240h+SubjectContext.ClientToken], xmm0
0x18000ddb7  movups  xmmword ptr [rbp+240h+SubjectContext.PrimaryToken], xmm0
0x18000ddbe  call    cs:__imp_SeCaptureSubjectContext
0x18000ddc5  nop     dword ptr [rax+rax+00h]
0x18000ddca  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x18000ddd1  call    cs:__imp_SeLockSubjectContext
0x18000ddd8  nop     dword ptr [rax+rax+00h]
0x18000dddd  mov     rcx, [rbp+240h+SubjectContext.ClientToken]
0x18000dde4  test    rcx, rcx
0x18000dde7  jnz     loc_18000DEFC
0x18000dded  mov     rcx, [rbp+240h+SubjectContext.PrimaryToken]; Token
0x18000ddf4  lea     rdx, [rsp+340h+AuthenticationId]; AuthenticationId
0x18000ddf9  call    cs:__imp_SeQueryAuthenticationIdToken
0x18000de00  nop     dword ptr [rax+rax+00h]
0x18000de05  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x18000de0c  mov     dword ptr [rsp+340h+ProcessInformation], eax
0x18000de10  call    cs:__imp_SeUnlockSubjectContext
0x18000de17  nop     dword ptr [rax+rax+00h]
0x18000de1c  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x18000de23  call    cs:__imp_SeReleaseSubjectContext
0x18000de2a  nop     dword ptr [rax+rax+00h]
0x18000de2f  cmp     dword ptr [rsp+340h+ProcessInformation], 0
0x18000de34  jl      loc_18000DF72
0x18000de3a  cmp     r15d, 4
0x18000de3e  jz      loc_18009F7B0
0x18000de44  lea     rdx, [rsp+340h+AuthenticationId]; unsigned __int8 *
0x18000de49  test    edi, edi
0x18000de4b  jz      loc_18000DCBE
0x18000de51  movaps  xmm0, xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x18000de58  lea     rcx, [rsp+340h+var_2F0]
0x18000de5d  movaps  xmm1, xmmword ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x18000de64  mov     r8d, 8
0x18000de6a  movaps  [rsp+340h+var_2F0], xmm0
0x18000de6f  movaps  xmm0, xmmword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x18000de76  movaps  [rsp+340h+var_2E0], xmm1
0x18000de7b  movaps  xmm1, xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcData
0x18000de82  movaps  [rsp+340h+var_2D0], xmm0
0x18000de87  movaps  xmm0, xmmword ptr cs:WPP_MAIN_CB.SecurityDescriptor
0x18000de8e  movaps  [rbp+240h+var_2C0], xmm1
0x18000de92  movaps  xmm1, xmmword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x18000de99  movaps  [rbp+240h+var_2B0], xmm0
0x18000de9d  movaps  xmm0, xmmword ptr cs:WPP_MAIN_CB.SectorSize
0x18000dea4  movaps  [rbp+240h+var_2A0], xmm1
0x18000dea8  movaps  xmm1, xmmword ptr cs:WPP_MAIN_CB.Reserved
0x18000deaf  movaps  [rbp+240h+var_290], xmm0
0x18000deb3  movaps  [rbp+240h+var_280], xmm1
0x18000deb7  call    SymCryptSha1Append
0x18000debc  lea     rdx, [rbp+240h+Buf2]
0x18000dec3  lea     rcx, [rsp+340h+var_2F0]
0x18000dec8  call    SymCryptSha1Result
0x18000decd  mov     r9b, 1
0x18000ded0  lea     rdx, [rbp+240h+Buf2]
0x18000ded7  mov     r8d, 10h
0x18000dedd  lea     rcx, [rbp+240h+var_270]
0x18000dee1  call    SymCryptAesExpandKeyInternal
0x18000dee6  mov     edx, 14h
0x18000deeb  lea     rcx, [rbp+240h+Buf2]
0x18000def2  call    SymCryptWipeAsm
0x18000def7  jmp     loc_18000DC71
0x18000defc  cmp     [rbp+240h+SubjectContext.ImpersonationLevel], 1
0x18000df03  jg      loc_18000DDF4
0x18000df09  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x18000df10  mov     ebx, 0C00000A5h
0x18000df15  call    cs:__imp_SeUnlockSubjectContext
0x18000df1c  nop     dword ptr [rax+rax+00h]
0x18000df21  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x18000df28  call    cs:__imp_SeReleaseSubjectContext
0x18000df2f  nop     dword ptr [rax+rax+00h]
0x18000df34  jmp     short loc_18000DF76
0x18000df36  mov     edi, r13d
0x18000df39  test    r14b, 7
0x18000df3d  jz      loc_18000DC4F
0x18000df43  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df4a  lea     rax, WPP_GLOBAL_Control
0x18000df51  cmp     rcx, rax
0x18000df54  jz      loc_18000E0A8
0x18000df5a  mov     eax, [rcx+2Ch]
0x18000df5d  test    al, 1
0x18000df5f  jz      loc_18000E0A8
0x18000df65  mov     [rsp+340h+var_310], 79h ; 'y'
0x18000df6d  jmp     loc_18000E084
0x18000df72  mov     ebx, dword ptr [rsp+340h+ProcessInformation]
0x18000df76  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df7d  lea     rax, WPP_GLOBAL_Control
0x18000df84  cmp     rcx, rax
0x18000df87  jz      short loc_18000DFB9
0x18000df89  mov     edx, [rcx+2Ch]
0x18000df8c  test    dl, 1
0x18000df8f  jz      short loc_18000DFB9
0x18000df91  mov     rcx, [rcx+18h]
0x18000df95  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000df9c  mov     [rsp+340h+var_310], 0F7h
0x18000dfa4  lea     r9, aStatus; "Status"
0x18000dfab  mov     [rsp+340h+var_318], r8
0x18000dfb0  mov     dword ptr [rsp+340h+ReturnLength], ebx
0x18000dfb4  call    WPP_SF_sDsd
0x18000dfb9  mov     eax, ebx
0x18000dfbb  jmp     loc_18000DD22
0x18000dfc0  mov     r9d, 4; ProcessInformationLength
0x18000dfc6  mov     dword ptr [rsp+340h+ProcessInformation], 0
0x18000dfce  lea     r8, [rsp+340h+ProcessInformation]; ProcessInformation
0x18000dfd3  mov     [rsp+340h+ReturnLength], 0; ReturnLength
0x18000dfdc  mov     edx, 24h ; '$'; ProcessInformationClass
0x18000dfe1  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000dfe8  call    cs:__imp_ZwQueryInformationProcess
0x18000dfef  nop     dword ptr [rax+rax+00h]
0x18000dff4  mov     r15d, eax
0x18000dff7  test    eax, eax
0x18000dff9  js      loc_18000E180
0x18000dfff  call    cs:__imp_PsGetCurrentProcess
0x18000e006  nop     dword ptr [rax+rax+00h]
0x18000e00b  mov     rcx, rax; Process
0x18000e00e  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x18000e015  nop     dword ptr [rax+rax+00h]
0x18000e01a  mov     ecx, dword ptr [rsp+340h+ProcessInformation]
0x18000e01e  lea     rdx, [rbp+240h+Buf2]; unsigned __int8 *
0x18000e025  mov     dword ptr [rbp+240h+Buf2], ecx
0x18000e02b  mov     r8d, 0Ch; unsigned int
0x18000e031  mov     [rbp+240h+Buf2+4], rax
0x18000e038  lea     rcx, [rbp+240h+var_270]; struct _SYMCRYPT_AES_EXPANDED_KEY *
0x18000e03c  test    edi, edi
0x18000e03e  jz      loc_18000DCC8
0x18000e044  call    ?GenerateAESKey@@YAXPEAU_SYMCRYPT_AES_EXPANDED_KEY@@PEAEK@Z; GenerateAESKey(_SYMCRYPT_AES_EXPANDED_KEY *,uchar *,ulong)
0x18000e049  jmp     loc_18000DC71
0x18000e04e  call    SymCryptAesCbcEncrypt
0x18000e053  jmp     loc_18000DD12
0x18000e058  cmp     r15d, 2
0x18000e05c  jz      loc_18000DD9D
0x18000e062  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e069  lea     rax, WPP_GLOBAL_Control
0x18000e070  cmp     rcx, rax
0x18000e073  jz      short loc_18000E0A8
0x18000e075  mov     eax, [rcx+2Ch]
0x18000e078  test    al, 1
0x18000e07a  jz      short loc_18000E0A8
0x18000e07c  mov     [rsp+340h+var_310], 131h
0x18000e084  mov     rcx, [rcx+18h]
0x18000e088  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e08f  mov     [rsp+340h+var_318], r8
0x18000e094  lea     r9, aStatus; "Status"
0x18000e09b  mov     dword ptr [rsp+340h+ReturnLength], 0C000000Dh
0x18000e0a3  call    WPP_SF_sDsd
0x18000e0a8  mov     eax, 0C000000Dh
0x18000e0ad  jmp     loc_18000DD22
0x18000e0b2  call    SymCryptAesCbcDecryptAsm
0x18000e0b7  jmp     loc_18000DD12
0x18000e0c0  mov     rax, [rbx]
0x18000e0c3  lea     r8, [rbp+240h+var_2B0]
0x18000e0c7  lea     rdx, [rsp+340h+var_2D0]
0x18000e0cc  mov     qword ptr [rsp+340h+var_2D0], rax
0x18000e0d1  mov     rcx, rsi
0x18000e0d4  call    SymCrypt3DesDecrypt
0x18000e0d9  lea     rax, [rsp+340h+var_2F0]
0x18000e0de  lea     rcx, [rbp+240h+var_2B0]
0x18000e0e2  mov     rcx, [rcx]
0x18000e0e5  xor     rcx, [rax]
0x18000e0e8  mov     [rbx], rcx
0x18000e0eb  add     rbx, 8
0x18000e0ef  mov     rax, qword ptr [rsp+340h+var_2D0]
0x18000e0f4  mov     qword ptr [rsp+340h+var_2F0], rax
0x18000e0f9  cmp     rbx, rdi
0x18000e0fc  jb      short loc_18000E0C0
0x18000e0fe  jmp     loc_18000DCFC
0x18000e103  mov     rcx, [rbx]
0x18000e106  lea     rax, [rbp+240h+SubjectContext]
0x18000e10d  xor     rcx, [rax]
0x18000e110  lea     rdx, [rbp+240h+SubjectContext]
0x18000e117  mov     [rdx], rcx
0x18000e11a  lea     r8, [rbp+240h+SubjectContext]
0x18000e121  lea     rdx, [rbp+240h+SubjectContext]
0x18000e128  mov     rcx, rsi
0x18000e12b  call    SymCrypt3DesEncrypt
0x18000e130  mov     rax, [rbp+240h+SubjectContext.ClientToken]
0x18000e137  mov     [rbx], rax
0x18000e13a  add     rbx, 8
0x18000e13e  cmp     rbx, rdi
0x18000e141  jb      short loc_18000E103
0x18000e143  mov     rax, [rbp+240h+SubjectContext.ClientToken]
0x18000e14a  jmp     loc_18000DD5D
0x18000e14f  call    CngEncryptMemoryInitialize
0x18000e154  mov     esi, eax
0x18000e156  test    eax, eax
0x18000e158  jns     loc_18000DC5C
0x18000e15e  mov     r9d, 83h
0x18000e164  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e16b  lea     rdx, aStatus; "Status"
0x18000e172  mov     ecx, eax
0x18000e174  call    DebugTraceError
0x18000e179  mov     eax, esi
0x18000e17b  jmp     loc_18000DD22
0x18000e180  mov     r9d, 0A0h
0x18000e186  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e18d  lea     rdx, aStatus; "Status"
0x18000e194  mov     ecx, r15d
0x18000e197  call    DebugTraceError
0x18000e19c  mov     eax, r15d
0x18000e19f  jmp     loc_18000DD22
0x18009f7b0  mov     [rbp+240h+Buf2], 3E7h
  ... truncated ...
```
