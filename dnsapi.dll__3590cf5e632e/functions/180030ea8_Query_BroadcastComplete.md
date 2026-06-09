# Query_BroadcastComplete

- ea: `0x180030ea8`
- end: `0x1800317cc`
- name: `Query_BroadcastComplete`
- size: `2340`
- prototype: ``
- caller_count: `8`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x18001c000`
- `0x180030aec`
- `0x180047f4c`
- `0x18004853c`
- `0x180048944`
- `0x18004a55c`
- `0x18004a910`
- `0x180052f10`

## callees

- `0x180023940`
- `0x18002e894`
- `0x180030a94`
- `0x180030ea8`
- `0x1800317e0`
- `0x180031e0c`
- `0x18003229c`
- `0x180032348`
- `0x180047ad4`
- `0x180047f4c`
- `0x18005dc0c`
- `0x180063ccc`
- `0x180063e94`
- `0x180063ed0`
- `0x180073f3c`
- `0x180083954`
- `0x1800d1afc`
- `0x1800d1bb4`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800dfa80`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031210`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031210`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003122d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003122d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030f63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030f63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030fd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030fd2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180030fb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180030fb0`

## string_xrefs

- `0x180031042`: `Query_BroadcastComplete`
- `0x18003105f`: `Query_BroadcastComplete`
- `0x18003107c`: `Query_BroadcastComplete`
- `0x180031253`: `Query_BroadcastComplete`
- `0x180031265`: `Query_BroadcastComplete`
- `0x180031286`: `Query_BroadcastComplete`
- `0x1800312a8`: `Query_BroadcastComplete`

## pseudocode

```c
__int64 __fastcall Query_BroadcastComplete(_QWORD *a1, int a2)
{
  int v3; // r15d
  unsigned int v4; // ebx
  int v5; // r8d
  unsigned int *v6; // r14
  _QWORD *v7; // r13
  unsigned int *v8; // rdi
  int v9; // edx
  BOOL v10; // ecx
  char *v11; // rsi
  int v12; // ebx
  _DWORD *v13; // r15
  __int64 v14; // rbx
  signed __int32 v16; // eax
  __int64 v17; // rdx
  signed __int32 v18; // ett
  int v19; // ebx
  int v20; // eax
  signed __int32 v21; // ebx
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rdx
  int v25; // ebx
  void *v26; // rcx
  unsigned int *v27; // rbx
  void *v28; // rcx
  int CancelNode; // ebx
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // edx
  const char *v35; // r9
  int v36; // ebx
  int v37; // eax
  const char *v38; // r9
  LPVOID v39; // [rsp+40h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v41; // [rsp+50h] [rbp-10h] BYREF
  unsigned int *v42; // [rsp+58h] [rbp-8h] BYREF

  v3 = a2;
  v39 = 0;
  v41 = 0;
  lpMem = 0;
  v42 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qD(1035, 323, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, a1, a2);
  v4 = differentiateBroadcastQueries(a1, &v41, &v39, &lpMem);
  if ( !v4 )
  {
    v6 = (unsigned int *)v39;
    v7 = lpMem;
    v8 = (unsigned int *)v41;
    v9 = a1 == lpMem;
    LODWORD(lpMem) = v9;
    v10 = a1 == v39;
    LODWORD(v39) = v10;
    if ( v6 )
    {
      if ( !v41 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_(1035, 324, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids);
        v11 = (char *)v6;
        if ( !v3 )
          Trace_LogNetBiosQueryStats(0, 0, 0, 1, 0, v6[876]);
        goto LABEL_15;
      }
    }
    else if ( !v41 )
    {
LABEL_43:
      v19 = 0;
      if ( !v10 )
      {
LABEL_44:
        if ( v9 )
        {
          if ( !v3 && !v7[120] )
          {
            v3 = 9002;
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            {
              WPP_SF_d(1035, 328, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, 9002);
              v9 = (int)lpMem;
            }
          }
          *((_DWORD *)v7 + 127) = v3;
        }
        v20 = (int)v39;
        if ( !(_DWORD)v39 && !v3 )
          goto LABEL_67;
        if ( !v19 )
        {
LABEL_47:
          v21 = _InterlockedIncrement((volatile signed __int32 *)v8 + 294);
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          {
            if ( v20 )
            {
              v38 = "NetBios";
            }
            else
            {
              v38 = "mDNS";
              if ( !(_DWORD)lpMem )
                v38 = "LLMNR";
            }
            WPP_SF_sql(v10, v9, v5, (_DWORD)v38, (__int64)a1, v21);
          }
          if ( (!v7 || !v6) && v21 != 3 )
            goto LABEL_97;
          if ( !v7 )
            goto LABEL_54;
          if ( v6 && v21 != 4 )
          {
LABEL_97:
            v4 = 9506;
LABEL_22:
            if ( v7 )
              DeRefQueryBlobEx(v7);
            if ( v8 )
              DeRefQueryBlobEx(v8);
            if ( v6 )
              DeRefQueryBlobEx(v6);
            goto LABEL_28;
          }
          v22 = 1;
          if ( *((_DWORD *)v7 + 127) )
LABEL_54:
            v22 = 0;
          if ( !v6 || (v23 = 1, v6[127]) )
            v23 = 0;
          if ( !v8 || v8[127] || v22 || (v24 = 1, v23) )
            v24 = 0;
          if ( !v8[295] && (v8[196] & 4) != 0 )
            DnsTraceLlmnrCompletion(v8[127], v24, 0);
          if ( v8[127] )
          {
            Query_GetCompletedNetBiosMdns(v8, v7, v6, &v42);
            v27 = v42;
            if ( v42 )
            {
              if ( v42 == v6 && (unsigned int)Query_ActiveLearningModeCall(v8, 1) )
                DnsTraceNetBiosCompletion(v6[127], 0, v6[876]);
              if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_q(1035, 333, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v8);
              v28 = (void *)*((_QWORD *)v8 + 120);
              if ( v28 )
                Dns_RecordListFree(v28);
              *((_QWORD *)v8 + 120) = 0;
              if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_q(1035, 334, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v27);
              *((_QWORD *)v8 + 120) = *((_QWORD *)v27 + 120);
              *((_QWORD *)v27 + 120) = 0;
              v8[127] = v27[127];
              *((_QWORD *)v8 + 66) = *((_QWORD *)v27 + 66) & 0xFFFFFFFFFFFFFDF3uLL
                                   | *((_QWORD *)v8 + 66)
                                   & (*((_QWORD *)v27 + 66) | 0xFFFFFFFFFFFFFDFFuLL)
                                   & 0xFFFFFFFFFFFFFFF3uLL;
            }
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 46));
          *((_QWORD *)v8 + 22) = 0;
          *((_QWORD *)v8 + 21) = 0;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 46));
          if ( v7 )
          {
            v7[21] = 0;
            DeRefQueryBlobEx(v8);
            DeRefQueryBlobEx(v7);
          }
          if ( v6 )
          {
            *((_QWORD *)v6 + 128) = 0;
            *((_QWORD *)v6 + 21) = 0;
            DeRefQueryBlobEx(v8);
            DeRefQueryBlobEx(v6);
          }
          v11 = (char *)v8;
          goto LABEL_15;
        }
        if ( (_DWORD)v39 )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_S(1035, 329, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, a1[30]);
          CancelNode = Query_CancelNode(v7);
          if ( (int)Query_CancelNode(v8) <= CancelNode )
          {
LABEL_102:
            v26 = v7;
            goto LABEL_72;
          }
        }
        else
        {
LABEL_67:
          if ( !v9 )
          {
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_S(1035, 331, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, a1[30]);
            v36 = Query_CancelNode(v7);
            v37 = Query_CancelNode(v6);
            v26 = v6;
            if ( v37 > v36 )
              goto LABEL_72;
            goto LABEL_102;
          }
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_S(1035, 330, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, a1[30]);
          v25 = Query_CancelNode(v8);
          if ( (int)Query_CancelNode(v6) > v25 )
          {
            v26 = v6;
            goto LABEL_72;
          }
        }
        v26 = v8;
LABEL_72:
        Query_CancelNode(v26);
        v20 = (int)v39;
        goto LABEL_47;
      }
      if ( v3 )
        goto LABEL_87;
      if ( !*((_QWORD *)v6 + 120) )
      {
        v3 = v6[127];
        if ( !v3 )
        {
          v6[127] = 9002;
          v3 = 9002;
        }
        goto LABEL_87;
      }
      if ( *((_DWORD *)v41 + 875) )
      {
LABEL_87:
        v6[127] = v3;
        goto LABEL_44;
      }
      v30 = *((_QWORD *)v6 + 33);
      if ( (v30 & 0x4000) != 0 )
      {
        if ( (v30 & 0x400000000000LL) == 0 )
          goto LABEL_87;
        if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
          goto LABEL_107;
        v31 = private_StringForRecordType(*((unsigned __int16 *)v6 + 128));
        v34 = 327;
      }
      else
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        {
LABEL_107:
          v19 = 1;
          goto LABEL_87;
        }
        v31 = private_StringForRecordType(*((unsigned __int16 *)v6 + 128));
        v34 = 326;
      }
      v35 = "UNKNOWN";
      if ( v31 )
        LODWORD(v35) = v31;
      WPP_SF_sqqq(v32, v34, v33, (_DWORD)v35, (__int64)v6, (__int64)v8, (__int64)v7);
      v9 = (int)lpMem;
      goto LABEL_107;
    }
    if ( !*((_DWORD *)v41 + 294) )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_(1035, 325, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids);
      v11 = (char *)v8;
      v12 = v3 == 0;
      AcquireSRWLockExclusive(&g_rwTelemetryLock);
      v13 = g_pTlmDnsStats;
      if ( g_pTlmDnsStats )
      {
        *((_DWORD *)g_pTlmDnsStats + 180772) += v12;
        ++v13[180774];
        ++v13[180775];
        v13[180773] += v12;
        if ( !g_DnsIsCache )
          MicrosoftTelemetryAssertTriggeredNoArgs(0);
        v14 = *((_QWORD *)v13 + 90392);
        if ( GetTickCount64() - v14 >= 0x2932E00 )
          UploadAllDnsStatistics(v13);
      }
      ReleaseSRWLockExclusive(&g_rwTelemetryLock);
LABEL_15:
      Query_DeRefBlobLearningModeTimer(v8);
      if ( (*((_DWORD *)v11 + 196) & 0x44) != 0 )
        Trace_LogMulticastQueryStats(*((_DWORD *)v11 + 127) == 0);
      _InterlockedOr((volatile signed __int32 *)v11 + 196, 0x100u);
      if ( *((_DWORD *)v11 + 119) )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_q(1035, 335, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v11);
        NetworkQuery_ProcessComplete(v11);
      }
      else
      {
        if ( !*((_QWORD *)v11 + 141) )
          goto LABEL_94;
        _m_prefetchw(v11 + 784);
        v16 = *((_DWORD *)v11 + 196);
        v17 = 512;
        do
        {
          v18 = v16;
          v16 = _InterlockedCompareExchange((volatile signed __int32 *)v11 + 196, v16 | 0x200, v16);
        }
        while ( v18 != v16 );
        if ( (v16 & 0x200) != 0 )
        {
LABEL_94:
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_q(1035, 337, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v11);
        }
        else
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_q(1035, 336, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v11);
          (*((void (__fastcall **)(char *, __int64))v11 + 141))(v11, v17);
        }
      }
      v4 = 0;
      goto LABEL_22;
    }
    goto LABEL_43;
  }
LABEL_28:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 338, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180030ea8  mov     [rsp-38h+arg_10], rbx
0x180030ead  push    rbp
0x180030eae  push    rsi
0x180030eaf  push    rdi
0x180030eb0  push    r12
0x180030eb2  push    r13
0x180030eb4  push    r14
0x180030eb6  push    r15
0x180030eb8  mov     rbp, rsp
0x180030ebb  sub     rsp, 60h
0x180030ebf  mov     rsi, rcx
0x180030ec2  mov     r15d, edx
0x180030ec5  xor     ecx, ecx
0x180030ec7  mov     [rbp+var_20], rcx
0x180030ecb  mov     [rbp+var_10], rcx
0x180030ecf  mov     [rbp+lpMem], rcx
0x180030ed3  mov     [rbp+var_8], rcx
0x180030ed7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180030ede  jnz     loc_180031558
0x180030ee4  lea     r9, [rbp+lpMem]
0x180030ee8  mov     rcx, rsi
0x180030eeb  lea     r8, [rbp+var_20]
0x180030eef  lea     rdx, [rbp+var_10]
0x180030ef3  call    differentiateBroadcastQueries
0x180030ef8  mov     ebx, eax
0x180030efa  test    eax, eax
0x180030efc  jnz     loc_180031091
0x180030f02  mov     r14, [rbp+var_20]
0x180030f06  xor     edx, edx
0x180030f08  mov     r13, [rbp+lpMem]
0x180030f0c  mov     rdi, [rbp+var_10]
0x180030f10  cmp     rsi, r13
0x180030f13  setz    dl
0x180030f16  xor     ecx, ecx
0x180030f18  cmp     rsi, r14
0x180030f1b  mov     dword ptr [rbp+lpMem], edx
0x180030f1e  setz    cl
0x180030f21  mov     dword ptr [rbp+var_20], ecx
0x180030f24  test    r14, r14
0x180030f27  jnz     loc_1800310B9
0x180030f2d  test    rdi, rdi
0x180030f30  jz      loc_180031159
0x180030f36  mov     eax, [rdi+498h]
0x180030f3c  test    eax, eax
0x180030f3e  jnz     loc_180031159
0x180030f44  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180030f4b  jnz     loc_1800315D2
0x180030f51  xor     ebx, ebx
0x180030f53  lea     rcx, g_rwTelemetryLock; SRWLock
0x180030f5a  test    r15d, r15d
0x180030f5d  mov     rsi, rdi
0x180030f60  setz    bl
0x180030f63  call    cs:__imp_AcquireSRWLockExclusive
0x180030f6a  nop     dword ptr [rax+rax+00h]
0x180030f6f  mov     r15, cs:g_pTlmDnsStats
0x180030f76  xor     ecx, ecx
0x180030f78  test    r15, r15
0x180030f7b  jz      short loc_180030FCB
0x180030f7d  add     [r15+0B0890h], ebx
0x180030f84  lea     r12d, [rcx+1]
0x180030f88  add     [r15+0B0898h], r12d
0x180030f8f  add     [r15+0B089Ch], r12d
0x180030f96  add     [r15+0B0894h], ebx
0x180030f9d  cmp     cs:g_DnsIsCache, ecx
0x180030fa3  jz      loc_180031406
0x180030fa9  mov     rbx, [r15+0B08C0h]
0x180030fb0  call    cs:__imp_GetTickCount64
0x180030fb7  nop     dword ptr [rax+rax+00h]
0x180030fbc  sub     rax, rbx
0x180030fbf  cmp     rax, 2932E00h
0x180030fc5  jnb     loc_1800314BF
0x180030fcb  lea     rcx, g_rwTelemetryLock; SRWLock
0x180030fd2  call    cs:__imp_ReleaseSRWLockExclusive
0x180030fd9  nop     dword ptr [rax+rax+00h]
0x180030fde  xor     r15d, r15d
0x180030fe1  mov     rcx, rdi; lpMem
0x180030fe4  call    Query_DeRefBlobLearningModeTimer
0x180030fe9  mov     eax, [rsi+310h]
0x180030fef  test    al, 44h
0x180030ff1  jz      short loc_180031005
0x180030ff3  cmp     [rsi+1FCh], r15d
0x180030ffa  mov     ecx, r15d
0x180030ffd  setz    cl
0x180031000  call    Trace_LogMulticastQueryStats
0x180031005  lock or dword ptr [rsi+310h], 100h
0x180031010  cmp     [rsi+1DCh], r15d
0x180031017  jz      loc_180031103
0x18003101d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180031024  jnz     loc_1800317AE
0x18003102a  mov     rcx, rsi; lpMem
0x18003102d  call    NetworkQuery_ProcessComplete
0x180031032  mov     ebx, r15d
0x180031035  mov     esi, 13h
0x18003103a  test    r13, r13
0x18003103d  jz      short loc_180031057
0x18003103f  mov     r9d, esi
0x180031042  lea     rdx, aQueryBroadcast; "Query_BroadcastComplete"
0x180031049  mov     r8d, 28E8h
0x18003104f  mov     rcx, r13; lpMem
0x180031052  call    DeRefQueryBlobEx
0x180031057  test    rdi, rdi
0x18003105a  jz      short loc_180031074
0x18003105c  mov     r9d, esi
0x18003105f  lea     rdx, aQueryBroadcast; "Query_BroadcastComplete"
0x180031066  mov     r8d, 28EEh
0x18003106c  mov     rcx, rdi; lpMem
0x18003106f  call    DeRefQueryBlobEx
0x180031074  test    r14, r14
0x180031077  jz      short loc_180031091
0x180031079  mov     r9d, esi
0x18003107c  lea     rdx, aQueryBroadcast; "Query_BroadcastComplete"
0x180031083  mov     r8d, 28F4h
0x180031089  mov     rcx, r14; lpMem
0x18003108c  call    DeRefQueryBlobEx
0x180031091  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180031098  jnz     loc_180031599
0x18003109e  mov     eax, ebx
0x1800310a0  mov     rbx, [rsp+60h+arg_10]
0x1800310a8  add     rsp, 60h
0x1800310ac  pop     r15
0x1800310ae  pop     r14
0x1800310b0  pop     r13
0x1800310b2  pop     r12
0x1800310b4  pop     rdi
0x1800310b5  pop     rsi
0x1800310b6  pop     rbp
0x1800310b7  retn
0x1800310b9  test    rdi, rdi
0x1800310bc  jnz     loc_180030F36
0x1800310c2  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800310c9  jnz     loc_1800315B7
0x1800310cf  mov     rsi, r14
0x1800310d2  test    r15d, r15d
0x1800310d5  jnz     loc_180030FDE
0x1800310db  mov     eax, [r14+0DB0h]
0x1800310e2  xor     r15d, r15d
0x1800310e5  mov     dword ptr [rsp+60h+var_38], eax
0x1800310e9  xor     r8d, r8d
0x1800310ec  xor     edx, edx
0x1800310ee  mov     dword ptr [rsp+60h+var_40], r15d
0x1800310f3  xor     ecx, ecx
0x1800310f5  lea     r9d, [r15+1]
0x1800310f9  call    Trace_LogNetBiosQueryStats
0x1800310fe  jmp     loc_180030FE1
0x180031103  cmp     [rsi+468h], r15
0x18003110a  jz      loc_18003144A
0x180031110  prefetchw byte ptr [rsi+310h]
0x180031117  mov     eax, [rsi+310h]
0x18003111d  mov     edx, 200h
0x180031122  mov     ecx, eax
0x180031124  or      ecx, edx
0x180031126  lock cmpxchg [rsi+310h], ecx
0x18003112e  jnz     short loc_180031122
0x180031130  test    edx, eax
0x180031132  jnz     loc_18003144A
0x180031138  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18003113f  jnz     loc_18003157B
0x180031145  mov     rax, [rsi+468h]
0x18003114c  mov     rcx, rsi
0x18003114f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031154  jmp     loc_180031032
0x180031159  xor     ebx, ebx
0x18003115b  lea     r12d, [rbx+1]
0x18003115f  test    ecx, ecx
0x180031161  jnz     loc_1800313F1
0x180031167  test    edx, edx
0x180031169  jnz     loc_180031310
0x18003116f  mov     eax, dword ptr [rbp+var_20]
0x180031172  test    eax, eax
0x180031174  jz      loc_1800312C5
0x18003117a  xor     r15d, r15d
0x18003117d  test    ebx, ebx
0x18003117f  jnz     loc_180031488
0x180031185  mov     ebx, r12d
0x180031188  lock xadd [rdi+498h], ebx
0x180031190  add     ebx, r12d
0x180031193  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18003119a  jnz     loc_18003170F
0x1800311a0  test    r13, r13
0x1800311a3  jz      loc_180031475
0x1800311a9  test    r14, r14
0x1800311ac  jz      loc_180031475
0x1800311b2  test    r13, r13
0x1800311b5  jz      short loc_1800311D1
0x1800311b7  test    r14, r14
0x1800311ba  jz      short loc_1800311C5
0x1800311bc  cmp     ebx, 4
0x1800311bf  jnz     loc_18003147E
0x1800311c5  mov     ecx, r12d
0x1800311c8  cmp     [r13+1FCh], r15d
0x1800311cf  jz      short loc_1800311D4
0x1800311d1  mov     ecx, r15d
0x1800311d4  test    r14, r14
0x1800311d7  jnz     loc_180031435
0x1800311dd  mov     eax, r15d
0x1800311e0  test    rdi, rdi
0x1800311e3  jnz     loc_180031410
0x1800311e9  mov     edx, r15d
0x1800311ec  cmp     [rdi+49Ch], r15d
0x1800311f3  jz      loc_1800313D0
0x1800311f9  cmp     [rdi+1FCh], r15d
0x180031200  jnz     loc_180031325
0x180031206  lea     rbx, [rdi+0B8h]
0x18003120d  mov     rcx, rbx; lpCriticalSection
0x180031210  call    cs:__imp_EnterCriticalSection
0x180031217  nop     dword ptr [rax+rax+00h]
0x18003121c  mov     [rdi+0B0h], r15
0x180031223  mov     rcx, rbx; lpCriticalSection
0x180031226  mov     [rdi+0A8h], r15
0x18003122d  call    cs:__imp_LeaveCriticalSection
0x180031234  nop     dword ptr [rax+rax+00h]
0x180031239  mov     ebx, 0Eh
0x18003123e  test    r13, r13
0x180031241  jz      short loc_18003127A
0x180031243  mov     r9d, ebx
0x180031246  mov     [r13+0A8h], r15
0x18003124d  mov     r8d, 28B4h
0x180031253  lea     rdx, aQueryBroadcast; "Query_BroadcastComplete"
0x18003125a  mov     rcx, rdi; lpMem
0x18003125d  call    DeRefQueryBlobEx
0x180031262  mov     r9d, ebx
0x180031265  lea     rdx, aQueryBroadcast; "Query_BroadcastComplete"
0x18003126c  mov     r8d, 28B5h
0x180031272  mov     rcx, r13; lpMem
0x180031275  call    DeRefQueryBlobEx
0x18003127a  test    r14, r14
0x18003127d  jz      short loc_1800312BD
0x18003127f  mov     [r14+400h], r15
0x180031286  lea     rdx, aQueryBroadcast; "Query_BroadcastComplete"
0x18003128d  mov     r9d, ebx
0x180031290  mov     [r14+0A8h], r15
0x180031297  mov     r8d, 28BDh
0x18003129d  mov     rcx, rdi; lpMem
0x1800312a0  call    DeRefQueryBlobEx
0x1800312a5  mov     r9d, ebx
0x1800312a8  lea     rdx, aQueryBroadcast; "Query_BroadcastComplete"
0x1800312af  mov     r8d, 28BEh
0x1800312b5  mov     rcx, r14; lpMem
0x1800312b8  call    DeRefQueryBlobEx
0x1800312bd  mov     rsi, rdi
0x1800312c0  jmp     loc_180030FE1
0x1800312c5  test    r15d, r15d
0x1800312c8  jnz     loc_18003117A
0x1800312ce  xor     r15d, r15d
0x1800312d1  test    edx, edx
0x1800312d3  jz      loc_1800316C7
0x1800312d9  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800312e0  jnz     loc_18003169D
0x1800312e6  mov     rcx, rdi; lpMem
0x1800312e9  call    Query_CancelNode
0x1800312ee  mov     rcx, r14; lpMem
0x1800312f1  mov     ebx, eax
0x1800312f3  call    Query_CancelNode
0x1800312f8  cmp     eax, ebx
0x1800312fa  jg      loc_1800316BF
0x180031300  mov     rcx, rdi; lpMem
0x180031303  call    Query_CancelNode
0x180031308  mov     eax, dword ptr [rbp+var_20]
0x18003130b  jmp     loc_180031185
0x180031310  test    r15d, r15d
0x180031313  jz      loc_180031516
0x180031319  mov     [r13+1FCh], r15d
0x180031320  jmp     loc_18003116F
0x180031325  lea     r9, [rbp+var_8]
0x180031329  mov     r8, r14
0x18003132c  mov     rdx, r13
0x18003132f  mov     rcx, rdi
0x180031332  call    Query_GetCompletedNetBiosMdns
0x180031337  mov     rbx, [rbp+var_8]
0x18003133b  test    rbx, rbx
0x18003133e  jz      loc_180031206
0x180031344  cmp     rbx, r14
0x180031347  jz      loc_180031745
0x18003134d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180031354  jnz     loc_180031772
0x18003135a  mov     rcx, [rdi+3C0h]; lpMem
0x180031361  test    rcx, rcx
0x180031364  jnz     loc_1800314CC
0x18003136a  mov     [rdi+3C0h], r15
0x180031371  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180031378  jnz     loc_180031790
0x18003137e  mov     rax, [rbx+3C0h]
0x180031385  mov     [rdi+3C0h], rax
0x18003138c  mov     [rbx+3C0h], r15
0x180031393  mov     eax, [rbx+1FCh]
0x180031399  mov     [rdi+1FCh], eax
0x18003139f  mov     rcx, [rbx+210h]
0x1800313a6  mov     rax, rcx
0x1800313a9  and     rcx, 0FFFFFFFFFFFFFDF3h
0x1800313b0  or      rax, 0FFFFFFFFFFFFFDFFh
0x1800313b6  and     rax, [rdi+210h]
0x1800313bd  and     rax, 0FFFFFFFFFFFFFFF3h
0x1800313c1  or      rax, rcx
0x1800313c4  mov     [rdi+210h], rax
0x1800313cb  jmp     loc_180031206
0x1800313d0  mov     eax, [rdi+310h]
0x1800313d6  test    al, 4
0x1800313d8  jz      loc_1800311F9
0x1800313de  mov     ecx, [rdi+1FCh]
0x1800313e4  xor     r8d, r8d
  ... truncated ...
```
