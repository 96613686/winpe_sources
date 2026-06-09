# CngEncryptMemoryEx

- ea: `0x180017d10`
- end: `0x1800182c4`
- name: `CngEncryptMemoryEx`
- size: `1460`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800302f0`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x1800174d0`
- `0x180017630`
- `0x180017b84`
- `0x180017d10`
- `0x1800182d0`
- `0x1800194d0`
- `0x180022480`
- `0x180022580`
- `0x180023968`
- `0x180024500`
- `0x1800564d0`
- `0x180056b60`
- `0x180067604`
- `0x1800a4260`
- `0x1800a4380`
- `0x1800a4890`

## import_xrefs

- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x180017f19`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x180017f19`
- `ntoskrnl!ZwQueryInformationProcess` at `0x180018108`
- `ntoskrnl!ZwQueryInformationProcess` at `0x180018108`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180017f43`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180018048`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180017f43`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180018048`
- `ntoskrnl!PsGetCurrentProcess` at `0x18001811f`
- `ntoskrnl!PsGetCurrentProcess` at `0x18001811f`
- `ntoskrnl!SeUnlockSubjectContext` at `0x180017f30`
- `ntoskrnl!SeUnlockSubjectContext` at `0x180018035`
- `ntoskrnl!SeUnlockSubjectContext` at `0x180017f30`
- `ntoskrnl!SeUnlockSubjectContext` at `0x180018035`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x18001812e`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x18001812e`
- `ntoskrnl!SeLockSubjectContext` at `0x180017ef1`
- `ntoskrnl!SeLockSubjectContext` at `0x180017ef1`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180017ede`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180017ede`

## string_xrefs

- `0x1800180b5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`
- `0x1800181a8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`
- `0x180018284`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`
- `0x1800182a6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`
- `0x1800a6588`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\encmem.cxx`

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
0x180017d10  mov     [rsp-8+arg_10], rbx
0x180017d15  push    rbp
0x180017d16  push    rsi
0x180017d17  push    rdi
0x180017d18  push    r12
0x180017d1a  push    r13
0x180017d1c  push    r14
0x180017d1e  push    r15
0x180017d20  lea     rbp, [rsp-210h]
0x180017d28  sub     rsp, 310h
0x180017d2f  mov     rax, cs:__security_cookie
0x180017d36  xor     rax, rsp
0x180017d39  mov     [rbp+240h+var_38], rax
0x180017d40  mov     r12d, r8d
0x180017d43  mov     r14d, edx
0x180017d46  mov     rbx, rcx
0x180017d49  xor     edx, edx; Val
0x180017d4b  mov     r8d, 1F0h; Size
0x180017d51  lea     rcx, [rbp+240h+var_270]; void *
0x180017d55  mov     r15d, r9d
0x180017d58  call    memset
0x180017d5d  xor     r13d, r13d
0x180017d60  test    r14b, 0Fh
0x180017d64  jnz     loc_180018056
0x180017d6a  mov     edi, 1
0x180017d6f  cmp     cs:?InitializedMemory@@3JA, r13d; long InitializedMemory
0x180017d76  jz      loc_18001826F
0x180017d7c  cmp     r15d, 1
0x180017d80  jnz     loc_180017EA2
0x180017d86  test    edi, edi
0x180017d88  jz      short loc_180017DD5
0x180017d8a  lea     r13, ?g_AESKey@@3U_SYMCRYPT_AES_EXPANDED_KEY@@A; _SYMCRYPT_AES_EXPANDED_KEY g_AESKey
0x180017d91  lea     rdx, [rbp+240h+var_48]
0x180017d98  mov     rcx, r14
0x180017d9b  mov     [rsp+340h+ReturnLength], rcx
0x180017da0  mov     r9, rbx
0x180017da3  mov     r8, rbx
0x180017da6  mov     rcx, r13
0x180017da9  movups  xmm0, xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x180017db0  movups  [rbp+240h+var_48], xmm0
0x180017db7  test    r12d, r12d
0x180017dba  jnz     loc_18001816E
0x180017dc0  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x180017dc6  test    al, 6
0x180017dc8  jnz     loc_1800181D2
0x180017dce  call    SymCryptAesCbcDecryptXmm
0x180017dd3  jmp     short loc_180017E32
0x180017dd5  lea     rsi, ?g_DES3Key@@3U_SYMCRYPT_3DES_EXPANDED_KEY@@A; _SYMCRYPT_3DES_EXPANDED_KEY g_DES3Key
0x180017ddc  jmp     short loc_180017DF0
0x180017dde  mov     r8d, 8; unsigned int
0x180017de4  lea     rcx, [rbp+240h+var_270]; struct _SYMCRYPT_3DES_EXPANDED_KEY *
0x180017de8  call    ?GenerateKey@@YAXPEAU_SYMCRYPT_3DES_EXPANDED_KEY@@PEAEK@Z; GenerateKey(_SYMCRYPT_3DES_EXPANDED_KEY *,uchar *,ulong)
0x180017ded  xor     r13d, r13d
0x180017df0  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x180017df7  mov     rcx, r14
0x180017dfa  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180017dfe  mov     qword ptr [rbp+240h+var_48], rax
0x180017e05  lea     rdi, [rcx+rbx]
0x180017e09  test    r12d, r12d
0x180017e0c  jnz     short loc_180017E6D
0x180017e0e  mov     qword ptr [rsp+340h+var_2F0], rax
0x180017e13  cmp     rbx, rdi
0x180017e16  jb      loc_1800181E0
0x180017e1c  mov     edx, 60h ; '`'
0x180017e21  mov     qword ptr [rbp+240h+var_48], rax
0x180017e28  lea     rcx, [rsp+340h+var_2F0]
0x180017e2d  call    SymCryptWipeAsm
0x180017e32  mov     edx, 1F0h
0x180017e37  lea     rcx, [rbp+240h+var_270]
0x180017e3b  call    SymCryptWipeAsm
0x180017e40  xor     eax, eax
0x180017e42  mov     rcx, [rbp+240h+var_38]
0x180017e49  xor     rcx, rsp; StackCookie
0x180017e4c  call    __security_check_cookie
0x180017e51  mov     rbx, [rsp+340h+arg_10]
0x180017e59  add     rsp, 310h
0x180017e60  pop     r15
0x180017e62  pop     r14
0x180017e64  pop     r13
0x180017e66  pop     r12
0x180017e68  pop     rdi
0x180017e69  pop     rsi
0x180017e6a  pop     rbp
0x180017e6b  retn
0x180017e6d  mov     [rbp+240h+SubjectContext.ClientToken], rax
0x180017e74  cmp     rbx, rdi
0x180017e77  jb      loc_180018223
0x180017e7d  mov     qword ptr [rbp+240h+var_48], rax
0x180017e84  mov     [rbp+240h+SubjectContext.ClientToken], r13
0x180017e8b  mov     qword ptr [rbp+240h+SubjectContext.ImpersonationLevel], r13
0x180017e92  mov     [rbp+240h+SubjectContext.PrimaryToken], r13
0x180017e99  mov     [rbp+240h+SubjectContext.ProcessAuditId], r13
0x180017ea0  jmp     short loc_180017E32
0x180017ea2  lea     r13, [rbp+240h+var_270]
0x180017ea6  lea     rsi, [rbp+240h+var_270]
0x180017eaa  test    r15d, r15d
0x180017ead  jz      loc_1800180E0
0x180017eb3  cmp     r15d, 4
0x180017eb7  jnz     loc_180018178
0x180017ebd  xorps   xmm0, xmm0
0x180017ec0  mov     qword ptr [rsp+340h+AuthenticationId.LowPart], 0
0x180017ec9  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x180017ed0  movups  xmmword ptr [rbp+240h+SubjectContext.ClientToken], xmm0
0x180017ed7  movups  xmmword ptr [rbp+240h+SubjectContext.PrimaryToken], xmm0
0x180017ede  call    cs:__imp_SeCaptureSubjectContext
0x180017ee5  nop     dword ptr [rax+rax+00h]
0x180017eea  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x180017ef1  call    cs:__imp_SeLockSubjectContext
0x180017ef8  nop     dword ptr [rax+rax+00h]
0x180017efd  mov     rcx, [rbp+240h+SubjectContext.ClientToken]
0x180017f04  test    rcx, rcx
0x180017f07  jnz     loc_18001801C
0x180017f0d  mov     rcx, [rbp+240h+SubjectContext.PrimaryToken]; Token
0x180017f14  lea     rdx, [rsp+340h+AuthenticationId]; AuthenticationId
0x180017f19  call    cs:__imp_SeQueryAuthenticationIdToken
0x180017f20  nop     dword ptr [rax+rax+00h]
0x180017f25  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x180017f2c  mov     dword ptr [rsp+340h+ProcessInformation], eax
0x180017f30  call    cs:__imp_SeUnlockSubjectContext
0x180017f37  nop     dword ptr [rax+rax+00h]
0x180017f3c  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x180017f43  call    cs:__imp_SeReleaseSubjectContext
0x180017f4a  nop     dword ptr [rax+rax+00h]
0x180017f4f  cmp     dword ptr [rsp+340h+ProcessInformation], 0
0x180017f54  jl      loc_180018092
0x180017f5a  cmp     r15d, 4
0x180017f5e  jz      loc_1800A654E
0x180017f64  lea     rdx, [rsp+340h+AuthenticationId]; unsigned __int8 *
0x180017f69  test    edi, edi
0x180017f6b  jz      loc_180017DDE
0x180017f71  movaps  xmm0, xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x180017f78  lea     rcx, [rsp+340h+var_2F0]
0x180017f7d  movaps  xmm1, xmmword ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x180017f84  mov     r8d, 8
0x180017f8a  movaps  [rsp+340h+var_2F0], xmm0
0x180017f8f  movaps  xmm0, xmmword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x180017f96  movaps  [rsp+340h+var_2E0], xmm1
0x180017f9b  movaps  xmm1, xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcData
0x180017fa2  movaps  [rsp+340h+var_2D0], xmm0
0x180017fa7  movaps  xmm0, xmmword ptr cs:WPP_MAIN_CB.SecurityDescriptor
0x180017fae  movaps  [rbp+240h+var_2C0], xmm1
0x180017fb2  movaps  xmm1, xmmword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x180017fb9  movaps  [rbp+240h+var_2B0], xmm0
0x180017fbd  movaps  xmm0, xmmword ptr cs:WPP_MAIN_CB.SectorSize
0x180017fc4  movaps  [rbp+240h+var_2A0], xmm1
0x180017fc8  movaps  xmm1, xmmword ptr cs:WPP_MAIN_CB.Reserved
0x180017fcf  movaps  [rbp+240h+var_290], xmm0
0x180017fd3  movaps  [rbp+240h+var_280], xmm1
0x180017fd7  call    SymCryptSha1Append
0x180017fdc  lea     rdx, [rbp+240h+Buf2]
0x180017fe3  lea     rcx, [rsp+340h+var_2F0]
0x180017fe8  call    SymCryptSha1Result
0x180017fed  mov     r9b, 1
0x180017ff0  lea     rdx, [rbp+240h+Buf2]
0x180017ff7  mov     r8d, 10h
0x180017ffd  lea     rcx, [rbp+240h+var_270]
0x180018001  call    SymCryptAesExpandKeyInternal
0x180018006  mov     edx, 14h
0x18001800b  lea     rcx, [rbp+240h+Buf2]
0x180018012  call    SymCryptWipeAsm
0x180018017  jmp     loc_180017D91
0x18001801c  cmp     [rbp+240h+SubjectContext.ImpersonationLevel], 1
0x180018023  jg      loc_180017F14
0x180018029  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x180018030  mov     ebx, 0C00000A5h
0x180018035  call    cs:__imp_SeUnlockSubjectContext
0x18001803c  nop     dword ptr [rax+rax+00h]
0x180018041  lea     rcx, [rbp+240h+SubjectContext]; SubjectContext
0x180018048  call    cs:__imp_SeReleaseSubjectContext
0x18001804f  nop     dword ptr [rax+rax+00h]
0x180018054  jmp     short loc_180018096
0x180018056  mov     edi, r13d
0x180018059  test    r14b, 7
0x18001805d  jz      loc_180017D6F
0x180018063  mov     rcx, cs:WPP_GLOBAL_Control
0x18001806a  lea     rax, WPP_GLOBAL_Control
0x180018071  cmp     rcx, rax
0x180018074  jz      loc_1800181C8
0x18001807a  mov     eax, [rcx+2Ch]
0x18001807d  test    al, 1
0x18001807f  jz      loc_1800181C8
0x180018085  mov     [rsp+340h+var_310], 79h ; 'y'
0x18001808d  jmp     loc_1800181A4
0x180018092  mov     ebx, dword ptr [rsp+340h+ProcessInformation]
0x180018096  mov     rcx, cs:WPP_GLOBAL_Control
0x18001809d  lea     rax, WPP_GLOBAL_Control
0x1800180a4  cmp     rcx, rax
0x1800180a7  jz      short loc_1800180D9
0x1800180a9  mov     edx, [rcx+2Ch]
0x1800180ac  test    dl, 1
0x1800180af  jz      short loc_1800180D9
0x1800180b1  mov     rcx, [rcx+18h]
0x1800180b5  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800180bc  mov     [rsp+340h+var_310], 0F7h
0x1800180c4  lea     r9, aStatus; "Status"
0x1800180cb  mov     [rsp+340h+var_318], r8
0x1800180d0  mov     dword ptr [rsp+340h+ReturnLength], ebx
0x1800180d4  call    WPP_SF_sDsd
0x1800180d9  mov     eax, ebx
0x1800180db  jmp     loc_180017E42
0x1800180e0  mov     r9d, 4; ProcessInformationLength
0x1800180e6  mov     dword ptr [rsp+340h+ProcessInformation], 0
0x1800180ee  lea     r8, [rsp+340h+ProcessInformation]; ProcessInformation
0x1800180f3  mov     [rsp+340h+ReturnLength], 0; ReturnLength
0x1800180fc  mov     edx, 24h ; '$'; ProcessInformationClass
0x180018101  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180018108  call    cs:__imp_ZwQueryInformationProcess
0x18001810f  nop     dword ptr [rax+rax+00h]
0x180018114  mov     r15d, eax
0x180018117  test    eax, eax
0x180018119  js      loc_1800182A0
0x18001811f  call    cs:__imp_PsGetCurrentProcess
0x180018126  nop     dword ptr [rax+rax+00h]
0x18001812b  mov     rcx, rax; Process
0x18001812e  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x180018135  nop     dword ptr [rax+rax+00h]
0x18001813a  mov     ecx, dword ptr [rsp+340h+ProcessInformation]
0x18001813e  lea     rdx, [rbp+240h+Buf2]; unsigned __int8 *
0x180018145  mov     dword ptr [rbp+240h+Buf2], ecx
0x18001814b  mov     r8d, 0Ch; unsigned int
0x180018151  mov     [rbp+240h+Buf2+4], rax
0x180018158  lea     rcx, [rbp+240h+var_270]; struct _SYMCRYPT_AES_EXPANDED_KEY *
0x18001815c  test    edi, edi
0x18001815e  jz      loc_180017DE8
0x180018164  call    ?GenerateAESKey@@YAXPEAU_SYMCRYPT_AES_EXPANDED_KEY@@PEAEK@Z; GenerateAESKey(_SYMCRYPT_AES_EXPANDED_KEY *,uchar *,ulong)
0x180018169  jmp     loc_180017D91
0x18001816e  call    SymCryptAesCbcEncrypt
0x180018173  jmp     loc_180017E32
0x180018178  cmp     r15d, 2
0x18001817c  jz      loc_180017EBD
0x180018182  mov     rcx, cs:WPP_GLOBAL_Control
0x180018189  lea     rax, WPP_GLOBAL_Control
0x180018190  cmp     rcx, rax
0x180018193  jz      short loc_1800181C8
0x180018195  mov     eax, [rcx+2Ch]
0x180018198  test    al, 1
0x18001819a  jz      short loc_1800181C8
0x18001819c  mov     [rsp+340h+var_310], 131h
0x1800181a4  mov     rcx, [rcx+18h]
0x1800181a8  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800181af  mov     [rsp+340h+var_318], r8
0x1800181b4  lea     r9, aStatus; "Status"
0x1800181bb  mov     dword ptr [rsp+340h+ReturnLength], 0C000000Dh
0x1800181c3  call    WPP_SF_sDsd
0x1800181c8  mov     eax, 0C000000Dh
0x1800181cd  jmp     loc_180017E42
0x1800181d2  call    SymCryptAesCbcDecryptAsm
0x1800181d7  jmp     loc_180017E32
0x1800181e0  mov     rax, [rbx]
0x1800181e3  lea     r8, [rbp+240h+var_2B0]
0x1800181e7  lea     rdx, [rsp+340h+var_2D0]
0x1800181ec  mov     qword ptr [rsp+340h+var_2D0], rax
0x1800181f1  mov     rcx, rsi
0x1800181f4  call    SymCrypt3DesDecrypt
0x1800181f9  lea     rax, [rsp+340h+var_2F0]
0x1800181fe  lea     rcx, [rbp+240h+var_2B0]
0x180018202  mov     rcx, [rcx]
0x180018205  xor     rcx, [rax]
0x180018208  mov     [rbx], rcx
0x18001820b  add     rbx, 8
0x18001820f  mov     rax, qword ptr [rsp+340h+var_2D0]
0x180018214  mov     qword ptr [rsp+340h+var_2F0], rax
0x180018219  cmp     rbx, rdi
0x18001821c  jb      short loc_1800181E0
0x18001821e  jmp     loc_180017E1C
0x180018223  mov     rcx, [rbx]
0x180018226  lea     rax, [rbp+240h+SubjectContext]
0x18001822d  xor     rcx, [rax]
0x180018230  lea     rdx, [rbp+240h+SubjectContext]
0x180018237  mov     [rdx], rcx
0x18001823a  lea     r8, [rbp+240h+SubjectContext]
0x180018241  lea     rdx, [rbp+240h+SubjectContext]
0x180018248  mov     rcx, rsi
0x18001824b  call    SymCrypt3DesEncrypt
0x180018250  mov     rax, [rbp+240h+SubjectContext.ClientToken]
0x180018257  mov     [rbx], rax
0x18001825a  add     rbx, 8
0x18001825e  cmp     rbx, rdi
0x180018261  jb      short loc_180018223
0x180018263  mov     rax, [rbp+240h+SubjectContext.ClientToken]
0x18001826a  jmp     loc_180017E7D
0x18001826f  call    CngEncryptMemoryInitialize
0x180018274  mov     esi, eax
0x180018276  test    eax, eax
0x180018278  jns     loc_180017D7C
0x18001827e  mov     r9d, 83h
0x180018284  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001828b  lea     rdx, aStatus; "Status"
0x180018292  mov     ecx, eax
0x180018294  call    DebugTraceError
0x180018299  mov     eax, esi
0x18001829b  jmp     loc_180017E42
0x1800182a0  mov     r9d, 0A0h
0x1800182a6  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800182ad  lea     rdx, aStatus; "Status"
0x1800182b4  mov     ecx, r15d
0x1800182b7  call    DebugTraceError
0x1800182bc  mov     eax, r15d
0x1800182bf  jmp     loc_180017E42
0x1800a654e  mov     [rbp+240h+Buf2], 3E7h
  ... truncated ...
```
