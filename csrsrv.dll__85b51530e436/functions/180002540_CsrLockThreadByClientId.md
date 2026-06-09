# CsrLockThreadByClientId

- ea: `0x180002540`
- end: `0x18000283f`
- name: `CsrLockThreadByClientId`
- size: `767`
- prototype: `__int64 __fastcall(void *, void *, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002540`
- `0x180002850`
- `0x180002a00`

## import_xrefs

- `ntdll!NtClose` at `0x180002764`
- `ntdll!NtClose` at `0x1800027f7`
- `ntdll!NtClose` at `0x18000282e`
- `ntdll!NtClose` at `0x180002764`
- `ntdll!NtClose` at `0x1800027f7`
- `ntdll!NtClose` at `0x18000282e`
- `ntdll!RtlEnterCriticalSection` at `0x180002585`
- `ntdll!RtlEnterCriticalSection` at `0x180002585`
- `ntdll!RtlLeaveCriticalSection` at `0x1800026fe`
- `ntdll!RtlLeaveCriticalSection` at `0x180002750`
- `ntdll!RtlLeaveCriticalSection` at `0x180002779`
- `ntdll!RtlLeaveCriticalSection` at `0x180002790`
- `ntdll!RtlLeaveCriticalSection` at `0x1800027ad`
- `ntdll!RtlLeaveCriticalSection` at `0x1800026fe`
- `ntdll!RtlLeaveCriticalSection` at `0x180002750`
- `ntdll!RtlLeaveCriticalSection` at `0x180002779`
- `ntdll!RtlLeaveCriticalSection` at `0x180002790`
- `ntdll!RtlLeaveCriticalSection` at `0x1800027ad`
- `ntdll!NtOpenThread` at `0x18000266a`
- `ntdll!NtOpenThread` at `0x18000266a`
- `ntdll!NtSetInformationThread` at `0x1800027dd`
- `ntdll!NtSetInformationThread` at `0x18000281e`
- `ntdll!NtSetInformationThread` at `0x1800027dd`
- `ntdll!NtSetInformationThread` at `0x18000281e`
- `ntdll!NtOpenThreadToken` at `0x180002737`
- `ntdll!NtOpenThreadToken` at `0x180002737`

## pseudocode

```c
__int64 __fastcall CsrLockThreadByClientId(void *a1, void *a2, __int64 *a3)
{
  __int64 *v5; // rcx
  __int64 i; // rax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 ProcessByClientId; // rax
  __int64 v11; // rbx
  ACCESS_MASK v12; // edi
  NTSTATUS v13; // edi
  int Thread; // ebx
  __int64 *v15; // rdx
  __int64 j; // rcx
  __int64 v17; // rax
  NTSTATUS v18; // esi
  _CLIENT_ID ClientId; // [rsp+20h] [rbp-50h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+A0h] [rbp+30h] BYREF
  void *ThreadHandle; // [rsp+A8h] [rbp+38h] BYREF
  __int64 ThreadInformation; // [rsp+B8h] [rbp+48h] BYREF

  ClientId.UniqueThread = a1;
  ClientId.UniqueProcess = a2;
  TokenHandle = 0;
  ThreadInformation = 0;
  ThreadHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlEnterCriticalSection(&CsrProcessStructureLock);
  v5 = &CsrThreadHashTable[2 * (((unsigned __int64)ClientId.UniqueThread >> 2) & 0x3FF)];
  for ( i = *v5; (__int64 *)i != v5; i = *(_QWORD *)i )
  {
    v7 = i - 24;
    if ( *(HANDLE *)(i + 24) == ClientId.UniqueThread && *(HANDLE *)(v7 + 40) == ClientId.UniqueProcess )
    {
      if ( (*(_BYTE *)(v7 + 72) & 4) != 0 )
      {
        RtlLeaveCriticalSection(&CsrProcessStructureLock);
        return (unsigned int)-1073741823;
      }
      else
      {
        v8 = 0;
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 76));
        *a3 = v7;
      }
      return v8;
    }
  }
  ProcessByClientId = CsrLocateProcessByClientId(a2);
  v11 = ProcessByClientId;
  if ( !ProcessByClientId )
  {
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    return 3221225473LL;
  }
  v12 = 0x1FFFFF;
  if ( (*(_DWORD *)(ProcessByClientId + 92) & 0x2000) != 0 )
    v12 = 1055744;
  if ( !HIDWORD(KeGetPcr()->NtTib.Self[107].Self) )
  {
    TokenHandle = 0;
    goto LABEL_14;
  }
  v18 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &TokenHandle);
  if ( v18 < 0 )
  {
LABEL_29:
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    return (unsigned int)v18;
  }
  ThreadInformation = 0;
  v18 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  if ( v18 < 0 )
  {
    NtClose(TokenHandle);
    goto LABEL_29;
  }
LABEL_14:
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = NtOpenThread(&ThreadHandle, v12, &ObjectAttributes, &ClientId);
  if ( TokenHandle )
  {
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    NtClose(TokenHandle);
  }
  if ( v13 < 0 )
  {
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    return (unsigned int)v13;
  }
  else
  {
    Thread = CsrCreateThread(v11, ThreadHandle, (__int128 *)&ClientId, 0);
    if ( Thread < 0 )
    {
      NtClose(ThreadHandle);
    }
    else
    {
      v15 = &CsrThreadHashTable[2 * (((unsigned __int64)ClientId.UniqueThread >> 2) & 0x3FF)];
      for ( j = *v15; (__int64 *)j != v15; j = *(_QWORD *)j )
      {
        v17 = j - 24;
        if ( *(HANDLE *)(j + 24) == ClientId.UniqueThread && *(HANDLE *)(v17 + 40) == ClientId.UniqueProcess )
        {
          if ( (*(_BYTE *)(v17 + 72) & 4) == 0 )
          {
            Thread = 0;
            _InterlockedIncrement((volatile signed __int32 *)(v17 + 76));
            *a3 = v17;
            return (unsigned int)Thread;
          }
          break;
        }
      }
      Thread = -1073741823;
    }
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    return (unsigned int)Thread;
  }
}

```

## disassembly

```asm
0x180002540  push    rbp
0x180002542  push    rbx
0x180002543  push    r12
0x180002545  push    r14
0x180002547  push    r15
0x180002549  mov     rbp, rsp
0x18000254c  sub     rsp, 70h
0x180002550  xorps   xmm0, xmm0
0x180002553  mov     [rbp+ClientId.UniqueThread], rcx
0x180002557  xor     r15d, r15d
0x18000255a  mov     [rbp+ClientId.UniqueProcess], rdx
0x18000255e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180002562  xor     eax, eax
0x180002564  mov     [rbp+TokenHandle], r15
0x180002568  lea     rcx, CsrProcessStructureLock; CriticalSection
0x18000256f  mov     [rbp+ThreadInformation], r15
0x180002573  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180002577  mov     r14, r8
0x18000257a  mov     [rbp+ThreadHandle], r15
0x18000257e  mov     rbx, rdx
0x180002581  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180002585  call    cs:__imp_RtlEnterCriticalSection
0x18000258c  nop     dword ptr [rax+rax+00h]
0x180002591  mov     r8, [rbp+ClientId.UniqueThread]
0x180002595  lea     r12, CsrThreadHashTable
0x18000259c  mov     r9, [rbp+ClientId.UniqueProcess]
0x1800025a0  mov     rcx, r8
0x1800025a3  shr     rcx, 2
0x1800025a7  and     ecx, 3FFh
0x1800025ad  shl     rcx, 4
0x1800025b1  add     rcx, r12
0x1800025b4  mov     rax, [rcx]
0x1800025b7  cmp     rax, rcx
0x1800025ba  jz      short loc_1800025F5
0x1800025bc  cmp     [rax+18h], r8
0x1800025c0  lea     rdx, [rax-18h]
0x1800025c4  jz      short loc_1800025CB
0x1800025c6  mov     rax, [rax]
0x1800025c9  jmp     short loc_1800025B7
0x1800025cb  cmp     [rdx+28h], r9
0x1800025cf  jnz     short loc_1800025C6
0x1800025d1  test    byte ptr [rdx+48h], 4
0x1800025d5  jnz     loc_180002789
0x1800025db  mov     ebx, r15d
0x1800025de  lock inc dword ptr [rdx+4Ch]
0x1800025e2  mov     [r14], rdx
0x1800025e5  mov     eax, ebx
0x1800025e7  add     rsp, 70h
0x1800025eb  pop     r15
0x1800025ed  pop     r14
0x1800025ef  pop     r12
0x1800025f1  pop     rbx
0x1800025f2  pop     rbp
0x1800025f3  retn
0x1800025f5  mov     rcx, rbx
0x1800025f8  call    CsrLocateProcessByClientId
0x1800025fd  mov     rbx, rax
0x180002600  test    rax, rax
0x180002603  jz      loc_1800027A6
0x180002609  test    dword ptr [rax+5Ch], 2000h
0x180002610  mov     eax, 101C00h
0x180002615  mov     [rsp+70h+var_8], rsi
0x18000261a  mov     [rsp+70h+var_10], rdi
0x18000261f  mov     edi, 1FFFFFh
0x180002624  cmovnz  edi, eax
0x180002627  mov     rax, gs:30h
0x180002630  cmp     [rax+179Ch], r15d
0x180002637  jnz     loc_180002724
0x18000263d  mov     [rbp+TokenHandle], r15
0x180002641  xorps   xmm0, xmm0
0x180002644  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000264b  lea     r9, [rbp+ClientId]; ClientId
0x18000264f  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x180002653  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180002657  mov     [rbp+ObjectAttributes.Attributes], r15d
0x18000265b  mov     edx, edi; DesiredAccess
0x18000265d  mov     [rbp+ObjectAttributes.ObjectName], r15
0x180002661  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x180002665  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000266a  call    cs:__imp_NtOpenThread
0x180002671  nop     dword ptr [rax+rax+00h]
0x180002676  mov     edi, eax
0x180002678  cmp     [rbp+TokenHandle], r15
0x18000267c  jnz     loc_180002808
0x180002682  test    edi, edi
0x180002684  js      loc_180002772
0x18000268a  mov     rdx, [rbp+ThreadHandle]
0x18000268e  lea     r8, [rbp+ClientId]
0x180002692  xor     r9d, r9d
0x180002695  mov     rcx, rbx
0x180002698  call    CsrCreateThread
0x18000269d  mov     ebx, eax
0x18000269f  test    eax, eax
0x1800026a1  js      loc_180002760
0x1800026a7  mov     r8, [rbp+ClientId.UniqueThread]
0x1800026ab  mov     r9, [rbp+ClientId.UniqueProcess]
0x1800026af  mov     rdx, r8
0x1800026b2  shr     rdx, 2
0x1800026b6  and     edx, 3FFh
0x1800026bc  shl     rdx, 4
0x1800026c0  add     rdx, r12
0x1800026c3  mov     rcx, [rdx]
0x1800026c6  cmp     rcx, rdx
0x1800026c9  jz      short loc_1800026F2
0x1800026cb  cmp     [rcx+18h], r8
0x1800026cf  lea     rax, [rcx-18h]
0x1800026d3  jz      short loc_1800026DA
0x1800026d5  mov     rcx, [rcx]
0x1800026d8  jmp     short loc_1800026C6
0x1800026da  cmp     [rax+28h], r9
0x1800026de  jnz     short loc_1800026D5
0x1800026e0  test    byte ptr [rax+48h], 4
0x1800026e4  jnz     short loc_1800026F2
0x1800026e6  mov     ebx, r15d
0x1800026e9  lock inc dword ptr [rax+4Ch]
0x1800026ed  mov     [r14], rax
0x1800026f0  jmp     short loc_18000270A
0x1800026f2  mov     ebx, 0C0000001h
0x1800026f7  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800026fe  call    cs:__imp_RtlLeaveCriticalSection
0x180002705  nop     dword ptr [rax+rax+00h]
0x18000270a  mov     eax, ebx
0x18000270c  mov     rsi, [rsp+70h+var_8]
0x180002711  mov     rdi, [rsp+70h+var_10]
0x180002716  add     rsp, 70h
0x18000271a  pop     r15
0x18000271c  pop     r14
0x18000271e  pop     r12
0x180002720  pop     rbx
0x180002721  pop     rbp
0x180002722  retn
0x180002724  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180002728  mov     r8b, 1; OpenAsSelf
0x18000272b  mov     edx, 4; DesiredAccess
0x180002730  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180002737  call    cs:__imp_NtOpenThreadToken
0x18000273e  nop     dword ptr [rax+rax+00h]
0x180002743  mov     esi, eax
0x180002745  test    eax, eax
0x180002747  jns     short loc_1800027C3
0x180002749  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002750  call    cs:__imp_RtlLeaveCriticalSection
0x180002757  nop     dword ptr [rax+rax+00h]
0x18000275c  mov     eax, esi
0x18000275e  jmp     short loc_18000270C
0x180002760  mov     rcx, [rbp+ThreadHandle]; Handle
0x180002764  call    cs:__imp_NtClose
0x18000276b  nop     dword ptr [rax+rax+00h]
0x180002770  jmp     short loc_1800026F7
0x180002772  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002779  call    cs:__imp_RtlLeaveCriticalSection
0x180002780  nop     dword ptr [rax+rax+00h]
0x180002785  mov     eax, edi
0x180002787  jmp     short loc_18000270C
0x180002789  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002790  call    cs:__imp_RtlLeaveCriticalSection
0x180002797  nop     dword ptr [rax+rax+00h]
0x18000279c  mov     ebx, 0C0000001h
0x1800027a1  jmp     loc_1800025E5
0x1800027a6  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800027ad  call    cs:__imp_RtlLeaveCriticalSection
0x1800027b4  nop     dword ptr [rax+rax+00h]
0x1800027b9  mov     eax, 0C0000001h
0x1800027be  jmp     loc_180002716
0x1800027c3  mov     r9d, 8; ThreadInformationLength
0x1800027c9  mov     [rbp+ThreadInformation], r15
0x1800027cd  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x1800027d1  mov     edx, 5; ThreadInformationClass
0x1800027d6  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800027dd  call    cs:__imp_NtSetInformationThread
0x1800027e4  nop     dword ptr [rax+rax+00h]
0x1800027e9  mov     esi, eax
0x1800027eb  test    eax, eax
0x1800027ed  jns     loc_180002641
0x1800027f3  mov     rcx, [rbp+TokenHandle]; Handle
0x1800027f7  call    cs:__imp_NtClose
0x1800027fe  nop     dword ptr [rax+rax+00h]
0x180002803  jmp     loc_180002749
0x180002808  mov     r9d, 8; ThreadInformationLength
0x18000280e  lea     r8, [rbp+TokenHandle]; ThreadInformation
0x180002812  mov     edx, 5; ThreadInformationClass
0x180002817  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000281e  call    cs:__imp_NtSetInformationThread
0x180002825  nop     dword ptr [rax+rax+00h]
0x18000282a  mov     rcx, [rbp+TokenHandle]; Handle
0x18000282e  call    cs:__imp_NtClose
0x180002835  nop     dword ptr [rax+rax+00h]
0x18000283a  jmp     loc_180002682
```
