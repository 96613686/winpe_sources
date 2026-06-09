# MDnsProbeAnnounceTask::Probe(void)

- ea: `0x18001a9c4`
- end: `0x18001ad64`
- name: `?Probe@MDnsProbeAnnounceTask@@CAJXZ`
- size: `928`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x18001a37c`

## callees

- `0x1800100d8`
- `0x18001a9c4`
- `0x18001ad6c`
- `0x18001ae98`
- `0x18001af74`
- `0x18003ae2c`
- `0x180046a64`
- `0x180046ec0`
- `0x180047818`
- `0x180086700`
- `0x180086b1c`
- `0x180088044`
- `0x18008841c`
- `0x1800888d4`

## import_xrefs

- `ntdll!RtlRandom` at `0x18001ab45`
- `ntdll!RtlRandom` at `0x18001ab45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ab68`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ab68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ab1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ab1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aaf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aaf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001abfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001abfc`

## pseudocode

```c
__int64 MDnsProbeAnnounceTask::Probe(void)
{
  int v0; // edx
  int v1; // ecx
  int v2; // r8d
  unsigned __int16 **LeafNames; // r14
  unsigned int v4; // r15d
  int v5; // edx
  int v6; // ecx
  int v7; // r8d
  char v8; // bl
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  unsigned int v12; // esi
  MDnsTree *v13; // rcx
  __int64 j; // r12
  ULONG v15; // eax
  unsigned int v16; // edi
  __int64 k; // rbx
  __int64 i; // rbx
  DWORD CurrentProcessId; // eax
  DWORD v21; // eax
  struct _DnsMessageBuf *v22; // rbx
  int v23; // r13d
  __int64 v24; // rcx
  int v25; // [rsp+28h] [rbp-B1h]
  unsigned int v26; // [rsp+40h] [rbp-99h] BYREF
  struct _DnsMessageBuf *v27; // [rsp+48h] [rbp-91h] BYREF
  __int64 v28; // [rsp+50h] [rbp-89h] BYREF
  unsigned __int64 v29; // [rsp+58h] [rbp-81h]
  int v30; // [rsp+60h] [rbp-79h] BYREF
  __int64 v31; // [rsp+68h] [rbp-71h]
  unsigned __int64 v32; // [rsp+70h] [rbp-69h]
  int v33; // [rsp+78h] [rbp-61h]
  int v34; // [rsp+80h] [rbp-59h]
  _BYTE v35[64]; // [rsp+A0h] [rbp-39h] BYREF

  memset_0(v35, 0, sizeof(v35));
  memset_0(&v30, 0, 0x40u);
  LeafNames = 0;
  v4 = 0;
  v27 = 0;
  v26 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qdSd(v1, v0, v2, (unsigned int)v35, 2, (__int64)&WideCharStr, 1);
  memset_0(v35, 0, sizeof(v35));
  DnsAddr_BuildFromIp4(v35);
  v28 = 767;
  v29 = 0xFB00000000000000uLL;
  v8 = BYTE1(xmmword_1800AB5A0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_qdSd(v6, v5, v7, (unsigned int)&v30, 23, (__int64)&WideCharStr, 1);
    v8 = BYTE1(xmmword_1800AB5A0);
  }
  memset_0(&v30, 0, 0x40u);
  if ( (v8 & 8) != 0 )
  {
    WPP_SF_q_IPV6_DD(v10, v9, v11, (unsigned int)&v30, (__int64)&v28, v25, 20);
    v8 = BYTE1(xmmword_1800AB5A0);
  }
  memset_0(&v30, 0, 0x40u);
  v31 = v28;
  v32 = v29;
  v30 = -384565225;
  v33 = 0;
  v34 = 28;
  if ( (v8 & 8) != 0 )
    WPP_SF_(1035, 14, WPP_c1b4b8e4fea931768401a909cc10c664_Traceguids);
  v12 = 0;
  _InterlockedExchange(&MDnsProbeAnnounceTask::s_fProbeInProgress, 1);
  while ( 1 )
  {
    if ( v12 >= 3 )
    {
      v16 = 0;
      goto LABEL_20;
    }
    if ( LeafNames )
    {
      for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
        operator delete(LeafNames[i]);
      operator delete(LeafNames);
      LeafNames = 0;
    }
    EnterCriticalSection(&g_csMdnsTree);
    if ( !g_MDnsTree )
      break;
    LeafNames = MDnsTree::GetLeafNames(v13, &v26);
    LeaveCriticalSection(&g_csMdnsTree);
    v4 = v26;
    _InterlockedExchange(&MDnsProbeAnnounceTask::s_fProbeConflictDetected, 0);
    for ( j = 0; (unsigned int)j < v4; j = (unsigned int)(j + 1) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v21 = MDnsProbeAnnounceTask::Dns_MulticastCreateProbeMessage(
              v4 - j,
              &LeafNames[j],
              (__int64)&v27,
              CurrentProcessId,
              &v27);
      v16 = v21;
      if ( v21 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 23, WPP_f1363454a052307e4f87df134c372536_Traceguids, v21);
        goto LABEL_20;
      }
      v22 = v27;
      v16 = MDnsSendMessageOnAllInterfaces(v27, v35);
      v23 = MDnsSendMessageOnAllInterfaces(v22, &v30);
      Packet_FreeMsgBuf(v22);
      if ( v16 && v23 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_Dd(v24, 24, WPP_f1363454a052307e4f87df134c372536_Traceguids, v16, v23);
        goto LABEL_20;
      }
    }
    v15 = RtlRandom(&g_randSeed);
    if ( !WaitForSingleObject(MDnsProbeAnnounceTask::s_hProbeAnnounceStop, v15 % 0xFA) )
    {
      v16 = 1223;
      goto LABEL_20;
    }
    if ( MDnsProbeAnnounceTask::s_fProbeConflictDetected )
      v12 = 0;
    ++v12;
  }
  v16 = 5023;
  LeaveCriticalSection(&g_csMdnsTree);
LABEL_20:
  for ( k = 0; (unsigned int)k < v4; k = (unsigned int)(k + 1) )
    operator delete(LeafNames[k]);
  operator delete(LeafNames);
  _InterlockedExchange(&MDnsProbeAnnounceTask::s_fProbeInProgress, 0);
  return v16;
}

```

## disassembly

```asm
0x18001a9c4  push    rbp
0x18001a9c6  push    rbx
0x18001a9c7  push    rsi
0x18001a9c8  push    rdi
0x18001a9c9  push    r12
0x18001a9cb  push    r13
0x18001a9cd  push    r14
0x18001a9cf  push    r15
0x18001a9d1  lea     rbp, [rsp-1Fh]
0x18001a9d6  sub     rsp, 0F8h
0x18001a9dd  mov     rax, cs:__security_cookie
0x18001a9e4  xor     rax, rsp
0x18001a9e7  mov     [rbp+57h+var_50], rax
0x18001a9eb  mov     edi, 40h ; '@'
0x18001a9f0  lea     rcx, [rbp+57h+var_90]; void *
0x18001a9f4  mov     r8d, edi; Size
0x18001a9f7  xor     edx, edx; Val
0x18001a9f9  call    memset_0
0x18001a9fe  mov     r8d, edi; Size
0x18001aa01  lea     rcx, [rbp+57h+var_D0]; void *
0x18001aa05  xor     edx, edx; Val
0x18001aa07  call    memset_0
0x18001aa0c  xor     r14d, r14d
0x18001aa0f  xor     r15d, r15d
0x18001aa12  mov     [rsp+130h+var_E8], r14
0x18001aa17  mov     [rsp+130h+var_F0], r15d
0x18001aa1c  mov     r13b, 8
0x18001aa1f  lea     rsi, WideCharStr
0x18001aa26  test    byte ptr cs:xmmword_1800AB5A0+1, r13b
0x18001aa2d  jnz     loc_18001ACD6
0x18001aa33  mov     r8, rdi; Size
0x18001aa36  lea     rcx, [rbp+57h+var_90]; void *
0x18001aa3a  xor     edx, edx; Val
0x18001aa3c  call    memset_0
0x18001aa41  mov     r12d, 0E914h
0x18001aa47  lea     rcx, [rbp+57h+var_90]; void *
0x18001aa4b  mov     r8d, r12d
0x18001aa4e  mov     edx, 0FB0000E0h
0x18001aa53  call    DnsAddr_BuildFromIp4
0x18001aa58  mov     rax, 0FB00000000000000h
0x18001aa62  mov     [rsp+130h+var_E0], 2FFh
0x18001aa6b  mov     [rsp+130h+var_D8], rax
0x18001aa70  mov     bl, byte ptr cs:xmmword_1800AB5A0+1
0x18001aa76  test    r13b, bl
0x18001aa79  jnz     loc_18001ACF9
0x18001aa7f  mov     r8, rdi; Size
0x18001aa82  lea     rcx, [rbp+57h+var_D0]; void *
0x18001aa86  xor     edx, edx; Val
0x18001aa88  call    memset_0
0x18001aa8d  test    r13b, bl
0x18001aa90  jnz     loc_18001AC98
0x18001aa96  mov     r8, rdi; Size
0x18001aa99  lea     rcx, [rbp+57h+var_D0]; void *
0x18001aa9d  xor     edx, edx; Val
0x18001aa9f  call    memset_0
0x18001aaa4  mov     rax, [rsp+130h+var_E0]
0x18001aaa9  mov     [rbp+57h+var_C8], rax
0x18001aaad  mov     rax, [rsp+130h+var_D8]
0x18001aab2  mov     [rbp+57h+var_C0], rax
0x18001aab6  mov     [rbp+57h+var_D0], 0E9140017h
0x18001aabd  mov     [rbp+57h+var_B8], r14d
0x18001aac1  mov     [rbp+57h+var_B0], 1Ch
0x18001aac8  test    r13b, bl
0x18001aacb  jnz     loc_18001ACBB
0x18001aad1  mov     eax, 1
0x18001aad6  xor     esi, esi
0x18001aad8  xchg    eax, cs:?s_fProbeInProgress@MDnsProbeAnnounceTask@@0HA; int MDnsProbeAnnounceTask::s_fProbeInProgress
0x18001aade  cmp     esi, 3
0x18001aae1  jnb     loc_18001AB88
0x18001aae7  test    r14, r14
0x18001aaea  jnz     loc_18001ABC3
0x18001aaf0  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001aaf7  call    cs:__imp_EnterCriticalSection
0x18001aafd  cmp     cs:?g_MDnsTree@@3PEAVMDnsTree@@EA, 0; MDnsTree * g_MDnsTree
0x18001ab05  jz      loc_18001AD4D
0x18001ab0b  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x18001ab10  call    ?GetLeafNames@MDnsTree@@QEAAPEAPEAGPEAK@Z; MDnsTree::GetLeafNames(ulong *)
0x18001ab15  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ab1c  mov     r14, rax
0x18001ab1f  call    cs:__imp_LeaveCriticalSection
0x18001ab25  mov     r15d, [rsp+130h+var_F0]
0x18001ab2a  xor     eax, eax
0x18001ab2c  xchg    eax, cs:?s_fProbeConflictDetected@MDnsProbeAnnounceTask@@0HA; int MDnsProbeAnnounceTask::s_fProbeConflictDetected
0x18001ab32  xor     r12d, r12d
0x18001ab35  cmp     r12d, r15d
0x18001ab38  jb      loc_18001ABFC
0x18001ab3e  lea     rcx, ?g_randSeed@@3KA; Seed
0x18001ab45  call    cs:__imp_RtlRandom
0x18001ab4b  mov     ecx, eax
0x18001ab4d  mov     eax, 10624DD3h
0x18001ab52  mul     ecx
0x18001ab54  shr     edx, 4
0x18001ab57  imul    eax, edx, 0FAh
0x18001ab5d  sub     ecx, eax
0x18001ab5f  mov     edx, ecx; dwMilliseconds
0x18001ab61  mov     rcx, cs:?s_hProbeAnnounceStop@MDnsProbeAnnounceTask@@0PEAXEA; hHandle
0x18001ab68  call    cs:__imp_WaitForSingleObject
0x18001ab6e  test    eax, eax
0x18001ab70  jz      loc_18001AC5E
0x18001ab76  xor     eax, eax
0x18001ab78  cmp     cs:?s_fProbeConflictDetected@MDnsProbeAnnounceTask@@0HA, eax; int MDnsProbeAnnounceTask::s_fProbeConflictDetected
0x18001ab7e  cmovnz  esi, eax
0x18001ab81  inc     esi
0x18001ab83  jmp     loc_18001AADE
0x18001ab88  xor     edi, edi
0x18001ab8a  xor     ebx, ebx
0x18001ab8c  test    r15d, r15d
0x18001ab8f  jnz     short loc_18001ABEA
0x18001ab91  mov     rcx, r14; void *
0x18001ab94  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ab99  xor     eax, eax
0x18001ab9b  xchg    eax, cs:?s_fProbeInProgress@MDnsProbeAnnounceTask@@0HA; int MDnsProbeAnnounceTask::s_fProbeInProgress
0x18001aba1  mov     eax, edi
0x18001aba3  mov     rcx, [rbp+57h+var_50]
0x18001aba7  xor     rcx, rsp; StackCookie
0x18001abaa  call    __security_check_cookie
0x18001abaf  add     rsp, 0F8h
0x18001abb6  pop     r15
0x18001abb8  pop     r14
0x18001abba  pop     r13
0x18001abbc  pop     r12
0x18001abbe  pop     rdi
0x18001abbf  pop     rsi
0x18001abc0  pop     rbx
0x18001abc1  pop     rbp
0x18001abc2  retn
0x18001abc3  xor     ebx, ebx
0x18001abc5  test    r15d, r15d
0x18001abc8  jz      short loc_18001ABDA
0x18001abca  mov     rcx, [r14+rbx*8]; void *
0x18001abce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001abd3  inc     ebx
0x18001abd5  cmp     ebx, r15d
0x18001abd8  jb      short loc_18001ABCA
0x18001abda  mov     rcx, r14; void *
0x18001abdd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001abe2  xor     r14d, r14d
0x18001abe5  jmp     loc_18001AAF0
0x18001abea  mov     rcx, [r14+rbx*8]; void *
0x18001abee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001abf3  inc     ebx
0x18001abf5  cmp     ebx, r15d
0x18001abf8  jnb     short loc_18001AB91
0x18001abfa  jmp     short loc_18001ABEA
0x18001abfc  call    cs:__imp_GetCurrentProcessId
0x18001ac02  mov     ecx, r15d
0x18001ac05  lea     r8, [rsp+130h+var_E8]; unsigned int
0x18001ac0a  sub     ecx, r12d; unsigned int
0x18001ac0d  mov     [rsp+130h+var_110], r8; struct _DnsMessageBuf **
0x18001ac12  lea     rdx, [r14+r12*8]; unsigned __int16 **
0x18001ac16  mov     r9d, eax; unsigned int
0x18001ac19  call    ?Dns_MulticastCreateProbeMessage@MDnsProbeAnnounceTask@@SAJKPEAPEAGKKPEAPEAU_DnsMessageBuf@@@Z; MDnsProbeAnnounceTask::Dns_MulticastCreateProbeMessage(ulong,ushort * *,ulong,ulong,_DnsMessageBuf * *)
0x18001ac1e  mov     edi, eax
0x18001ac20  test    eax, eax
0x18001ac22  jnz     loc_18001AD22
0x18001ac28  mov     rbx, [rsp+130h+var_E8]
0x18001ac2d  lea     rdx, [rbp+57h+var_90]
0x18001ac31  mov     rcx, rbx
0x18001ac34  call    MDnsSendMessageOnAllInterfaces
0x18001ac39  lea     rdx, [rbp+57h+var_D0]
0x18001ac3d  mov     rcx, rbx
0x18001ac40  mov     edi, eax
0x18001ac42  call    MDnsSendMessageOnAllInterfaces
0x18001ac47  mov     rcx, rbx; void *
0x18001ac4a  mov     r13d, eax
0x18001ac4d  call    Packet_FreeMsgBuf
0x18001ac52  test    edi, edi
0x18001ac54  jnz     short loc_18001AC68
0x18001ac56  inc     r12d
0x18001ac59  jmp     loc_18001AB35
0x18001ac5e  mov     edi, 4C7h
0x18001ac63  jmp     loc_18001AB8A
0x18001ac68  test    r13d, r13d
0x18001ac6b  jz      short loc_18001AC56
0x18001ac6d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001ac74  jz      loc_18001AB8A
0x18001ac7a  mov     edx, 18h
0x18001ac7f  mov     dword ptr [rsp+130h+var_110], r13d
0x18001ac84  mov     r9d, edi
0x18001ac87  lea     r8, WPP_f1363454a052307e4f87df134c372536_Traceguids
0x18001ac8e  call    WPP_SF_Dd
0x18001ac93  jmp     loc_18001AB8A
0x18001ac98  lea     rax, [rsp+130h+var_E0]
0x18001ac9d  mov     [rsp+130h+var_100], r12d
0x18001aca2  lea     r9, [rbp+57h+var_D0]
0x18001aca6  mov     [rsp+130h+var_110], rax
0x18001acab  call    WPP_SF_q_IPV6_DD
0x18001acb0  mov     bl, byte ptr cs:xmmword_1800AB5A0+1
0x18001acb6  jmp     loc_18001AA96
0x18001acbb  mov     edx, 0Eh
0x18001acc0  lea     r8, WPP_c1b4b8e4fea931768401a909cc10c664_Traceguids
0x18001acc7  mov     ecx, 40Bh
0x18001accc  call    WPP_SF_
0x18001acd1  jmp     loc_18001AAD1
0x18001acd6  mov     [rsp+130h+var_100], 1
0x18001acde  lea     r9, [rbp+57h+var_90]
0x18001ace2  mov     [rsp+130h+var_108], rsi
0x18001ace7  mov     dword ptr [rsp+130h+var_110], 2
0x18001acef  call    WPP_SF_qdSd
0x18001acf4  jmp     loc_18001AA33
0x18001acf9  mov     [rsp+130h+var_100], 1
0x18001ad01  lea     r9, [rbp+57h+var_D0]
0x18001ad05  mov     [rsp+130h+var_108], rsi
0x18001ad0a  mov     dword ptr [rsp+130h+var_110], 17h
0x18001ad12  call    WPP_SF_qdSd
0x18001ad17  mov     bl, byte ptr cs:xmmword_1800AB5A0+1
0x18001ad1d  jmp     loc_18001AA7F
0x18001ad22  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001ad29  jz      loc_18001AB8A
0x18001ad2f  mov     edx, 17h
0x18001ad34  lea     r8, WPP_f1363454a052307e4f87df134c372536_Traceguids
0x18001ad3b  mov     ecx, 40Bh
0x18001ad40  mov     r9d, eax
0x18001ad43  call    WPP_SF_d
0x18001ad48  jmp     loc_18001AB8A
0x18001ad4d  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ad54  mov     edi, 139Fh
0x18001ad59  call    cs:__imp_LeaveCriticalSection
0x18001ad5f  jmp     loc_18001AB8A
```
