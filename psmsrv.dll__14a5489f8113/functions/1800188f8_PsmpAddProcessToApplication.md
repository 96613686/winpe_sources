# PsmpAddProcessToApplication

- ea: `0x1800188f8`
- end: `0x180018e91`
- name: `PsmpAddProcessToApplication`
- size: `1433`
- prototype: `__int64 __fastcall(__int64, __int64, int, void *, void *, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800184a0`

## callees

- `0x18000a750`
- `0x18000a8d0`
- `0x18000d378`
- `0x18000defc`
- `0x18000e9a0`
- `0x180010b40`
- `0x180017ca4`
- `0x1800188f8`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001dab8`
- `0x18001ed2c`
- `0x18001efd4`

## import_xrefs

- `ntdll!RtlSidDominates` at `0x180018b3b`
- `ntdll!RtlSidDominates` at `0x180018b3b`
- `ntdll!NtAssignProcessToJobObject` at `0x180018baa`
- `ntdll!NtAssignProcessToJobObject` at `0x180018c32`
- `ntdll!NtAssignProcessToJobObject` at `0x180018baa`
- `ntdll!NtAssignProcessToJobObject` at `0x180018c32`
- `ntdll!NtQueryInformationJobObject` at `0x180018aeb`
- `ntdll!NtQueryInformationJobObject` at `0x180018aeb`
- `ntdll!NtSetInformationJobObject` at `0x180018b86`
- `ntdll!NtSetInformationJobObject` at `0x180018b86`
- `ntdll!NtResetEvent` at `0x180018d88`
- `ntdll!NtResetEvent` at `0x180018d88`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001899e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001899e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018e50`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018e50`
- `ntdll!NtQueryInformationToken` at `0x180018b1b`
- `ntdll!NtQueryInformationToken` at `0x180018b1b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180018c04`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180018c04`

## pseudocode

```c
__int64 __fastcall PsmpAddProcessToApplication(
        __int64 a1,
        __int64 a2,
        int a3,
        void *a4,
        void *a5,
        __int64 a6,
        _BYTE *a7)
{
  __int64 v7; // r12
  __int64 HostJobContext; // r13
  NTSTATUS v11; // edi
  __int64 v12; // r8
  __int64 v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r14d
  int v17; // edi
  int v18; // r15d
  char v19; // r15
  int v20; // eax
  int v21; // r12d
  __int64 v22; // rbx
  __int64 v23; // rdi
  DWORD ProcessId; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rax
  int v28; // ecx
  __int64 v29; // rdx
  void *v30; // rcx
  char inserted; // di
  signed __int32 v32; // eax
  signed __int32 v33; // ett
  int v34; // eax
  _BYTE v36[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+34h] [rbp-CCh]
  HANDLE JobHandle; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+44h] [rbp-BCh]
  HANDLE ProcessHandle; // [rsp+48h] [rbp-B8h]
  __int64 v42; // [rsp+50h] [rbp-B0h]
  HANDLE TokenHandle; // [rsp+58h] [rbp-A8h]
  __int64 v44; // [rsp+60h] [rbp-A0h]
  _BYTE *v45; // [rsp+68h] [rbp-98h]
  __int64 v46; // [rsp+70h] [rbp-90h]
  _QWORD TokenInformation[12]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE JobInformation[16]; // [rsp+E0h] [rbp-20h] BYREF
  int v49; // [rsp+F0h] [rbp-10h]

  v7 = a6;
  TokenHandle = a5;
  v44 = a2;
  ProcessHandle = a4;
  v42 = a6;
  v45 = a7;
  v36[0] = 0;
  JobHandle = 0;
  memset_0(TokenInformation, 0, 0x58u);
  memset_0(JobInformation, 0, 0x98u);
  ReturnLength = 0;
  v46 = a1 + 328;
  HostJobContext = 0;
  RtlAcquireSRWLockExclusive(a1 + 328);
  if ( *(_DWORD *)(a1 + 7024) )
  {
    v11 = -1073741558;
    goto LABEL_99;
  }
  v40 = a3 & 8;
  if ( (a3 & 8) != 0 )
  {
    HostJobContext = PsmpFindHostJobContext(a1, a6);
    if ( !HostJobContext )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_iid(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v12, *(_QWORD *)(a1 + 96), a6, a3);
LABEL_8:
      v11 = -1073741823;
      goto LABEL_99;
    }
  }
  v11 = PsmpCreateAndInitializeHostJob(a1, a3, a6, HostJobContext, (__int64)&JobHandle, 0);
  if ( v11 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 35;
LABEL_13:
      WPP_SF_iid(v14[2], v15, v13, *(_QWORD *)(a1 + 96), v7, a3);
      goto LABEL_99;
    }
    goto LABEL_99;
  }
  v16 = 1;
  v17 = a3 & 4;
  v37 = v17;
  if ( (a3 & 4) != 0 )
  {
    v18 = *(_DWORD *)(a1 + 132) >> 11;
LABEL_16:
    v19 = v18 & 1;
    goto LABEL_21;
  }
  if ( (a3 & 8) != 0 )
  {
    v18 = *(_DWORD *)(HostJobContext + 84) >> 3;
    goto LABEL_16;
  }
  if ( (a3 & 0x40) != 0 )
  {
    v19 = (*(_DWORD *)(a1 + 132) & 0x2000) != 0;
LABEL_21:
    if ( v19 )
      goto LABEL_40;
    goto LABEL_26;
  }
  if ( (*(_DWORD *)(a1 + 132) & 0x400) != 0 )
  {
    v19 = 1;
    goto LABEL_40;
  }
  v19 = 0;
LABEL_26:
  NtQueryInformationJobObject(JobHandle, JobObjectExtendedLimitInformation, JobInformation, 0x98u, 0);
  if ( (a3 & 4) != 0 )
  {
    v20 = v49 | 0x2000;
LABEL_32:
    v49 = v20;
    goto LABEL_33;
  }
  v11 = NtQueryInformationToken(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x58u, &ReturnLength);
  if ( v11 < 0 )
    goto LABEL_99;
  v11 = RtlSidDominates(TokenInformation[0], PsmpMediumLabel, v36);
  if ( v11 < 0 )
    goto LABEL_99;
  v20 = v49;
  v17 = v37;
  if ( v36[0] )
  {
    v20 = v49 | 0x800;
    goto LABEL_32;
  }
LABEL_33:
  if ( (a3 & 0x20) != 0 )
  {
    v20 |= 0x1800u;
    v49 = v20;
  }
  if ( v20 )
  {
    v11 = NtSetInformationJobObject(JobHandle, JobObjectExtendedLimitInformation, JobInformation, 0x98u);
    if ( v11 < 0 )
      goto LABEL_99;
    v17 = v37;
  }
  if ( v17 || (v11 = NtAssignProcessToJobObject(*(HANDLE *)(a1 + 184), ProcessHandle), v11 >= 0) )
  {
LABEL_40:
    if ( (a3 & 1) == 0 )
    {
      v21 = *(_DWORD *)(a1 + 344);
      if ( (unsigned int)(v21 - 5) <= 1 || v21 == 4 && (a3 & 0xC) != 0 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = *(_QWORD *)(a1 + 96);
          v23 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          ProcessId = GetProcessId(ProcessHandle);
          WPP_SF_iDL(v23, v25, v26, v22, ProcessId, v21);
        }
        goto LABEL_8;
      }
      v7 = v42;
    }
    v11 = NtAssignProcessToJobObject(JobHandle, ProcessHandle);
    if ( v11 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 37;
        goto LABEL_13;
      }
      goto LABEL_99;
    }
    if ( v19 )
    {
      if ( (a3 & 0x4C) != 0 )
        goto LABEL_91;
    }
    else
    {
      v27 = v44;
      if ( (*(_BYTE *)(v44 + 541) & 2) != 0 && (*(_DWORD *)(a1 + 128) & 0x100000) == 0 )
        _interlockedbittestandset((volatile signed __int32 *)(a1 + 128), 0x14u);
      if ( (*(_BYTE *)(v27 + 541) & 1) != 0 && (*(_DWORD *)(a1 + 128) & 0x200000) == 0 )
        _interlockedbittestandset((volatile signed __int32 *)(a1 + 128), 0x15u);
      if ( (a3 & 0x4C) != 0 )
      {
        if ( !v37 )
        {
          if ( (a3 & 0x40) != 0 )
          {
            _interlockedbittestandset((volatile signed __int32 *)(a1 + 132), 0xDu);
            goto LABEL_92;
          }
          _interlockedbittestandset((volatile signed __int32 *)(HostJobContext + 84), 3u);
LABEL_94:
          if ( (a3 & 0x10) != 0 )
          {
            if ( v40 )
              _interlockedbittestandset((volatile signed __int32 *)(HostJobContext + 84), 2u);
            else
              _interlockedbittestandset((volatile signed __int32 *)(a1 + 132), 9u);
          }
          v11 = 0;
          goto LABEL_99;
        }
        if ( byte_18003FE7D && (unsigned int)(*(_DWORD *)(a1 + 344) - 1) <= 1 && !*(_DWORD *)(a1 + 164) )
        {
          LOBYTE(v13) = 1;
          PsmpEnableDisablePrioritySandbox(a1, 0, v13);
        }
        _interlockedbittestandset((volatile signed __int32 *)(a1 + 132), 0xBu);
LABEL_91:
        if ( (a3 & 0x40) != 0 )
        {
LABEL_92:
          if ( !_interlockedbittestandset((volatile signed __int32 *)(a1 + 132), 0xEu) )
            PsmpReferenceApplication(a1);
          goto LABEL_94;
        }
        goto LABEL_94;
      }
      v28 = *(_DWORD *)(a1 + 344);
      if ( ((v28 - 1) & 0xFFFFFFFC) != 0 || v28 == 3 )
      {
        v29 = 0;
        v16 = -25;
      }
      else if ( (*(_BYTE *)(a1 + 128) & 0x20) != 0 )
      {
        v29 = 4;
      }
      else
      {
        v16 = 0;
        v29 = 5;
      }
      _interlockedbittestandset((volatile signed __int32 *)(a1 + 132), 0xAu);
      PsmpSetApplicationExecutionState(a1, v29, v16);
    }
    if ( !_interlockedbittestandset((volatile signed __int32 *)(a1 + 128), 2u) )
    {
      v30 = *(void **)(a1 + 224);
      if ( v30 )
        NtResetEvent(v30, 0);
      PsmpReferenceApplication(a1);
      if ( (*(_DWORD *)(a1 + 132) & 0x1000) != 0 )
      {
        inserted = 0;
      }
      else
      {
        _m_prefetchw((const void *)(a1 + 128));
        v32 = *(_DWORD *)(a1 + 128);
        do
        {
          v33 = v32;
          v32 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 128), v32 | 0x400, v32);
        }
        while ( v33 != v32 );
        v34 = v32 & 0x402;
        if ( v34 )
        {
          inserted = 0;
          if ( v34 == 2 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_i(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              80,
              &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
              *(_QWORD *)(a1 + 96));
        }
        else
        {
          inserted = PsmpInsertNewApplication(a1);
        }
      }
      *v45 = inserted;
    }
    goto LABEL_91;
  }
LABEL_99:
  RtlReleaseSRWLockExclusive(v46);
  if ( HostJobContext )
    PsmpDereferenceHostContext(HostJobContext, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800188f8  mov     [rsp-8+arg_8], rbx
0x1800188fd  push    rbp
0x1800188fe  push    rsi
0x1800188ff  push    rdi
0x180018900  push    r12
0x180018902  push    r13
0x180018904  push    r14
0x180018906  push    r15
0x180018908  lea     rbp, [rsp-90h]
0x180018910  sub     rsp, 190h
0x180018917  mov     rax, cs:__security_cookie
0x18001891e  xor     rax, rsp
0x180018921  mov     [rbp+0C0h+var_40], rax
0x180018928  mov     rax, [rbp+0C0h+arg_20]
0x18001892f  xor     edi, edi
0x180018931  mov     r12, [rbp+0C0h+arg_28]
0x180018938  mov     esi, r8d
0x18001893b  mov     [rsp+1C0h+TokenHandle], rax
0x180018940  mov     rbx, rcx
0x180018943  mov     rax, [rbp+0C0h+arg_30]
0x18001894a  lea     rcx, [rbp+0C0h+TokenInformation]; void *
0x18001894e  mov     [rsp+1C0h+var_160], rdx
0x180018953  lea     r8d, [rdi+58h]; Size
0x180018957  xor     edx, edx; Val
0x180018959  mov     [rsp+1C0h+ProcessHandle], r9
0x18001895e  mov     [rsp+1C0h+var_170], r12
0x180018963  mov     [rsp+1C0h+var_158], rax
0x180018968  mov     [rsp+1C0h+var_190], dil
0x18001896d  mov     [rsp+1C0h+JobHandle], rdi
0x180018972  call    memset_0
0x180018977  xor     edx, edx; Val
0x180018979  lea     rcx, [rbp+0C0h+JobInformation]; void *
0x18001897d  mov     r8d, 98h; Size
0x180018983  call    memset_0
0x180018988  lea     rax, [rbx+148h]
0x18001898f  mov     [rsp+1C0h+var_180], edi
0x180018993  mov     rcx, rax
0x180018996  mov     [rsp+1C0h+var_150], rax
0x18001899b  mov     r13d, edi
0x18001899e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800189a4  cmp     [rbx+1B70h], edi
0x1800189aa  jbe     short loc_1800189B6
0x1800189ac  mov     edi, 0C000010Ah
0x1800189b1  jmp     loc_180018E4B
0x1800189b6  mov     r15d, esi
0x1800189b9  and     r15d, 8
0x1800189bd  mov     [rsp+1C0h+var_17C], r15d
0x1800189c2  jz      short loc_180018A0D
0x1800189c4  mov     rdx, r12
0x1800189c7  mov     rcx, rbx
0x1800189ca  call    PsmpFindHostJobContext
0x1800189cf  mov     r13, rax
0x1800189d2  test    rax, rax
0x1800189d5  jnz     short loc_180018A0D
0x1800189d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189de  test    byte ptr [rcx+1Ch], 2
0x1800189e2  jz      short loc_180018A03
0x1800189e4  cmp     byte ptr [rcx+19h], 2
0x1800189e8  jb      short loc_180018A03
0x1800189ea  mov     r9, [rbx+60h]
0x1800189ee  lea     edx, [rax+22h]
0x1800189f1  mov     rcx, [rcx+10h]
0x1800189f5  mov     dword ptr [rsp+1C0h+var_198], esi
0x1800189f9  mov     [rsp+1C0h+ReturnLength], r12
0x1800189fe  call    WPP_SF_iid
0x180018a03  mov     edi, 0C0000001h
0x180018a08  jmp     loc_180018E4B
0x180018a0d  lea     rax, [rsp+1C0h+JobHandle]
0x180018a12  mov     [rsp+1C0h+var_198], rdi
0x180018a17  mov     r9, r13
0x180018a1a  mov     [rsp+1C0h+ReturnLength], rax
0x180018a1f  mov     r8, r12
0x180018a22  mov     edx, esi
0x180018a24  mov     rcx, rbx
0x180018a27  call    PsmpCreateAndInitializeHostJob
0x180018a2c  mov     edi, eax
0x180018a2e  test    eax, eax
0x180018a30  jns     short loc_180018A6D
0x180018a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a39  test    byte ptr [rcx+1Ch], 2
0x180018a3d  jz      loc_180018E4B
0x180018a43  cmp     byte ptr [rcx+19h], 2
0x180018a47  jb      loc_180018E4B
0x180018a4d  mov     edx, 23h ; '#'
0x180018a52  mov     r9, [rbx+60h]
0x180018a56  mov     rcx, [rcx+10h]
0x180018a5a  mov     dword ptr [rsp+1C0h+var_198], esi
0x180018a5e  mov     [rsp+1C0h+ReturnLength], r12
0x180018a63  call    WPP_SF_iid
0x180018a68  jmp     loc_180018E4B
0x180018a6d  mov     edi, esi
0x180018a6f  mov     r14d, 1
0x180018a75  and     edi, 4
0x180018a78  mov     [rsp+1C0h+var_18C], edi
0x180018a7c  jz      short loc_180018A8E
0x180018a7e  mov     r15d, [rbx+84h]
0x180018a85  shr     r15d, 0Bh
0x180018a89  and     r15b, r14b
0x180018a8c  jmp     short loc_180018AB2
0x180018a8e  test    r15d, r15d
0x180018a91  jz      short loc_180018A9D
0x180018a93  mov     r15d, [r13+54h]
0x180018a97  shr     r15d, 3
0x180018a9b  jmp     short loc_180018A89
0x180018a9d  mov     eax, [rbx+84h]
0x180018aa3  test    sil, 40h
0x180018aa7  jz      short loc_180018ABD
0x180018aa9  shr     eax, 0Dh
0x180018aac  and     al, r14b
0x180018aaf  mov     r15b, al
0x180018ab2  test    r15b, r15b
0x180018ab5  jnz     loc_180018BBA
0x180018abb  jmp     short loc_180018ACE
0x180018abd  bt      eax, 0Ah
0x180018ac1  jnb     short loc_180018ACB
0x180018ac3  mov     r15b, r14b
0x180018ac6  jmp     loc_180018BBA
0x180018acb  xor     r15b, r15b
0x180018ace  mov     rcx, [rsp+1C0h+JobHandle]; JobHandle
0x180018ad3  lea     r8, [rbp+0C0h+JobInformation]; JobInformation
0x180018ad7  mov     r9d, 98h; JobInformationLength
0x180018add  mov     [rsp+1C0h+ReturnLength], 0; ReturnLength
0x180018ae6  mov     edx, 9; JobInformationClass
0x180018aeb  call    cs:__imp_NtQueryInformationJobObject
0x180018af1  test    edi, edi
0x180018af3  jz      short loc_180018AFE
0x180018af5  mov     eax, [rbp+0C0h+var_D0]
0x180018af8  bts     eax, 0Dh
0x180018afc  jmp     short loc_180018B5D
0x180018afe  mov     rcx, [rsp+1C0h+TokenHandle]; TokenHandle
0x180018b03  lea     rax, [rsp+1C0h+var_180]
0x180018b08  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180018b0e  mov     [rsp+1C0h+ReturnLength], rax; ReturnLength
0x180018b13  lea     r8, [rbp+0C0h+TokenInformation]; TokenInformation
0x180018b17  lea     edx, [r9-3Fh]; TokenInformationClass
0x180018b1b  call    cs:__imp_NtQueryInformationToken
0x180018b21  mov     edi, eax
0x180018b23  test    eax, eax
0x180018b25  js      loc_180018E4B
0x180018b2b  mov     rcx, [rbp+0C0h+TokenInformation]
0x180018b2f  lea     r8, [rsp+1C0h+var_190]
0x180018b34  lea     rdx, PsmpMediumLabel
0x180018b3b  call    cs:__imp_RtlSidDominates
0x180018b41  mov     edi, eax
0x180018b43  test    eax, eax
0x180018b45  js      loc_180018E4B
0x180018b4b  cmp     [rsp+1C0h+var_190], 0
0x180018b50  mov     eax, [rbp+0C0h+var_D0]
0x180018b53  mov     edi, [rsp+1C0h+var_18C]
0x180018b57  jz      short loc_180018B60
0x180018b59  bts     eax, 0Bh
0x180018b5d  mov     [rbp+0C0h+var_D0], eax
0x180018b60  test    sil, 20h
0x180018b64  jz      short loc_180018B6E
0x180018b66  or      eax, 1800h
0x180018b6b  mov     [rbp+0C0h+var_D0], eax
0x180018b6e  test    eax, eax
0x180018b70  jz      short loc_180018B9A
0x180018b72  mov     rcx, [rsp+1C0h+JobHandle]; JobHandle
0x180018b77  lea     r8, [rbp+0C0h+JobInformation]; JobInformation
0x180018b7b  mov     r9d, 98h; JobInformationLength
0x180018b81  mov     edx, 9; JobInformationClass
0x180018b86  call    cs:__imp_NtSetInformationJobObject
0x180018b8c  mov     edi, eax
0x180018b8e  test    eax, eax
0x180018b90  js      loc_180018E4B
0x180018b96  mov     edi, [rsp+1C0h+var_18C]
0x180018b9a  test    edi, edi
0x180018b9c  jnz     short loc_180018BBA
0x180018b9e  mov     rdx, [rsp+1C0h+ProcessHandle]; ProcessHandle
0x180018ba3  mov     rcx, [rbx+0B8h]; JobHandle
0x180018baa  call    cs:__imp_NtAssignProcessToJobObject
0x180018bb0  mov     edi, eax
0x180018bb2  test    eax, eax
0x180018bb4  js      loc_180018E4B
0x180018bba  test    r14b, sil
0x180018bbd  jnz     short loc_180018C28
0x180018bbf  mov     r12d, [rbx+158h]
0x180018bc6  lea     eax, [r12-5]
0x180018bcb  cmp     eax, r14d
0x180018bce  jbe     short loc_180018BDC
0x180018bd0  cmp     r12d, 4
0x180018bd4  jnz     short loc_180018C23
0x180018bd6  test    sil, 0Ch
0x180018bda  jz      short loc_180018C23
0x180018bdc  mov     rdi, cs:WPP_GLOBAL_Control
0x180018be3  test    byte ptr [rdi+1Ch], 2
0x180018be7  jz      loc_180018A03
0x180018bed  cmp     byte ptr [rdi+19h], 2
0x180018bf1  jb      loc_180018A03
0x180018bf7  mov     rcx, [rsp+1C0h+ProcessHandle]; Process
0x180018bfc  mov     rbx, [rbx+60h]
0x180018c00  mov     rdi, [rdi+10h]
0x180018c04  call    cs:__imp_GetProcessId
0x180018c0a  mov     r9, rbx
0x180018c0d  mov     dword ptr [rsp+1C0h+var_198], r12d
0x180018c12  mov     rcx, rdi
0x180018c15  mov     dword ptr [rsp+1C0h+ReturnLength], eax
0x180018c19  call    WPP_SF_iDL
0x180018c1e  jmp     loc_180018A03
0x180018c23  mov     r12, [rsp+1C0h+var_170]
0x180018c28  mov     rdx, [rsp+1C0h+ProcessHandle]; ProcessHandle
0x180018c2d  mov     rcx, [rsp+1C0h+JobHandle]; JobHandle
0x180018c32  call    cs:__imp_NtAssignProcessToJobObject
0x180018c38  mov     edi, eax
0x180018c3a  test    eax, eax
0x180018c3c  jns     short loc_180018C63
0x180018c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c45  test    byte ptr [rcx+1Ch], 2
0x180018c49  jz      loc_180018E4B
0x180018c4f  cmp     byte ptr [rcx+19h], 2
0x180018c53  jb      loc_180018E4B
0x180018c59  mov     edx, 25h ; '%'
0x180018c5e  jmp     loc_180018A52
0x180018c63  test    r15b, r15b
0x180018c66  jnz     loc_180018D61
0x180018c6c  mov     rax, [rsp+1C0h+var_160]
0x180018c71  test    byte ptr [rax+21Dh], 2
0x180018c78  jz      short loc_180018C8F
0x180018c7a  test    dword ptr [rbx+80h], 100000h
0x180018c84  jnz     short loc_180018C8F
0x180018c86  lock bts dword ptr [rbx+80h], 14h
0x180018c8f  test    [rax+21Dh], r14b
0x180018c96  jz      short loc_180018CAD
0x180018c98  test    dword ptr [rbx+80h], 200000h
0x180018ca2  jnz     short loc_180018CAD
0x180018ca4  lock bts dword ptr [rbx+80h], 15h
0x180018cad  test    sil, 4Ch
0x180018cb1  jnz     short loc_180018CFF
0x180018cb3  mov     ecx, [rbx+158h]
0x180018cb9  lea     eax, [rcx-1]
0x180018cbc  test    eax, 0FFFFFFFCh
0x180018cc1  jnz     short loc_180018CE1
0x180018cc3  cmp     ecx, 3
0x180018cc6  jz      short loc_180018CE1
0x180018cc8  test    byte ptr [rbx+80h], 20h
0x180018ccf  jz      short loc_180018CD8
0x180018cd1  mov     edx, 4
0x180018cd6  jmp     short loc_180018CE9
0x180018cd8  xor     r14d, r14d
0x180018cdb  lea     edx, [r14+5]
0x180018cdf  jmp     short loc_180018CE9
0x180018ce1  xor     edx, edx
0x180018ce3  mov     r14d, 0FFFFFFE7h
0x180018ce9  lock bts dword ptr [rbx+84h], 0Ah
0x180018cf2  mov     r8d, r14d
0x180018cf5  mov     rcx, rbx
0x180018cf8  call    PsmpSetApplicationExecutionState
0x180018cfd  jmp     short loc_180018D6B
0x180018cff  cmp     [rsp+1C0h+var_18C], 0
0x180018d04  jz      short loc_180018D41
0x180018d06  cmp     cs:byte_18003FE7D, 0
0x180018d0d  jz      short loc_180018D33
0x180018d0f  mov     eax, [rbx+158h]
0x180018d15  sub     eax, r14d
0x180018d18  cmp     eax, r14d
0x180018d1b  ja      short loc_180018D33
0x180018d1d  cmp     dword ptr [rbx+0A4h], 0
0x180018d24  jnz     short loc_180018D33
0x180018d26  mov     r8b, r14b
0x180018d29  xor     edx, edx
0x180018d2b  mov     rcx, rbx
0x180018d2e  call    PsmpEnableDisablePrioritySandbox
0x180018d33  lock bts dword ptr [rbx+84h], 0Bh
0x180018d3c  jmp     loc_180018E11
0x180018d41  test    sil, 40h
0x180018d45  jz      short loc_180018D55
0x180018d47  lock bts dword ptr [rbx+84h], 0Dh
0x180018d50  jmp     loc_180018E17
0x180018d55  lock bts dword ptr [r13+54h], 3
0x180018d5c  jmp     loc_180018E2A
0x180018d61  test    sil, 4Ch
0x180018d65  jnz     loc_180018E11
0x180018d6b  lock bts dword ptr [rbx+80h], 2
0x180018d74  jb      loc_180018E11
0x180018d7a  mov     rcx, [rbx+0E0h]; EventHandle
0x180018d81  test    rcx, rcx
0x180018d84  jz      short loc_180018D8E
0x180018d86  xor     edx, edx; NumberOfWaitingThreads
0x180018d88  call    cs:__imp_NtResetEvent
0x180018d8e  mov     rcx, rbx
0x180018d91  call    PsmpReferenceApplication
0x180018d96  test    dword ptr [rbx+84h], 1000h
0x180018da0  jz      short loc_180018DA7
0x180018da2  xor     dil, dil
0x180018da5  jmp     short loc_180018E09
0x180018da7  prefetchw byte ptr [rbx+80h]
0x180018dae  mov     eax, [rbx+80h]
0x180018db4  mov     ecx, eax
0x180018db6  bts     ecx, 0Ah
0x180018dba  lock cmpxchg [rbx+80h], ecx
0x180018dc2  jnz     short loc_180018DB4
0x180018dc4  and     eax, 402h
0x180018dc9  jnz     short loc_180018DD8
0x180018dcb  mov     rcx, rbx
0x180018dce  call    PsmpInsertNewApplication
0x180018dd3  mov     dil, al
0x180018dd6  jmp     short loc_180018E09
0x180018dd8  xor     dil, dil
0x180018ddb  cmp     eax, 2
  ... truncated ...
```
