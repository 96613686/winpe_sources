# PsmpSetApplicationCache

- ea: `0x18000191c`
- end: `0x180001fc3`
- name: `PsmpSetApplicationCache`
- size: `1703`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002000`
- `0x18002bc50`

## callees

- `0x1800017b0`
- `0x18000191c`
- `0x1800093d0`
- `0x180009b40`
- `0x18000d010`
- `0x18000db88`
- `0x18000defc`
- `0x180015dd4`
- `0x1800179d8`
- `0x180017ca4`
- `0x18001ea3c`
- `0x18001ec88`
- `0x180022b2c`
- `0x1800238b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180001a95`
- `ntdll!RtlFreeHeap` at `0x180001eac`
- `ntdll!RtlFreeHeap` at `0x180001a95`
- `ntdll!RtlFreeHeap` at `0x180001eac`
- `ntdll!NtCreateEvent` at `0x180001b85`
- `ntdll!NtCreateEvent` at `0x180001bd3`
- `ntdll!NtCreateEvent` at `0x180001b85`
- `ntdll!NtCreateEvent` at `0x180001bd3`
- `ntdll!NtDuplicateObject` at `0x180001c4f`
- `ntdll!NtDuplicateObject` at `0x180001c89`
- `ntdll!NtDuplicateObject` at `0x180001cb9`
- `ntdll!NtDuplicateObject` at `0x180001ef1`
- `ntdll!NtDuplicateObject` at `0x180001f16`
- `ntdll!NtDuplicateObject` at `0x180001f40`
- `ntdll!NtDuplicateObject` at `0x180001c4f`
- `ntdll!NtDuplicateObject` at `0x180001c89`
- `ntdll!NtDuplicateObject` at `0x180001cb9`
- `ntdll!NtDuplicateObject` at `0x180001ef1`
- `ntdll!NtDuplicateObject` at `0x180001f16`
- `ntdll!NtDuplicateObject` at `0x180001f40`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800019a0`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800019a0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001a4a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001b64`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001cd7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001ce4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001d13`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001e61`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001f54`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001a4a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001b64`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001cd7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001ce4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001d13`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001e61`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001f54`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001a9f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001b96`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001c02`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001d4c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001d92`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001d9c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001eb6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001f73`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001a9f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001b96`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001c02`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001d4c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001d92`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001d9c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001eb6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001f73`
- `ntdll!RtlAcquireSRWLockShared` at `0x180001984`
- `ntdll!RtlAcquireSRWLockShared` at `0x180001984`

## pseudocode

```c
__int64 __fastcall PsmpSetApplicationCache(int *a1, void *a2, WCHAR *a3, _QWORD *a4, __int64 a5, __int64 a6)
{
  __int64 v6; // r13
  void *v7; // r15
  _QWORD *Application; // rdi
  int *v10; // r12
  __int64 *UserContext; // rsi
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v17; // r9
  __int64 v18; // rbx
  __int64 v19; // rdx
  __int64 **v20; // r8
  __int64 v21; // r14
  int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rcx
  HANDLE *v25; // r15
  BOOLEAN InitialState; // cl
  NTSTATUS v27; // eax
  void *v28; // r12
  bool v29; // zf
  int v30; // eax
  _QWORD *v31; // r15
  __int64 v32; // rcx
  _QWORD *v33; // rax
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r8
  int v37; // eax
  __int64 v38; // rdi
  __int64 v39; // rcx
  __int64 **v40; // rdx
  __int64 v41; // [rsp+48h] [rbp-59h] BYREF
  HANDLE SourceHandle; // [rsp+50h] [rbp-51h] BYREF
  HANDLE v43; // [rsp+58h] [rbp-49h] BYREF
  void *TargetHandle; // [rsp+60h] [rbp-41h] BYREF
  __int64 v45; // [rsp+68h] [rbp-39h]
  __int64 v46; // [rsp+70h] [rbp-31h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-29h] BYREF
  __int64 v51; // [rsp+110h] [rbp+6Fh] BYREF

  v6 = a5;
  v7 = a2;
  Application = a4;
  v43 = 0;
  TargetHandle = 0;
  v10 = a1;
  SourceHandle = 0;
  UserContext = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a4 )
  {
    v12 = *(_QWORD *)(a5 + 56);
    RtlAcquireSRWLockShared(v12 + 8);
    UserContext = PsmpFindUserContext(v12, *v10, v7);
    RtlReleaseSRWLockShared(v12 + 8, v13, v14, v15);
    if ( !UserContext )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF__sid_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0x3Cu,
          &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
          (char *)v7,
          *v10);
      return 3221225524LL;
    }
    v17 = -1;
    do
      ++v17;
    while ( a3[v17] );
    Application = PsmpFindApplication(0, (__int64)UserContext, a3, 2 * v17 + 2);
    if ( !Application )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids, a3);
      v18 = UserContext[7];
      RtlAcquireSRWLockExclusive(v18 + 8);
      if ( !PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
        goto LABEL_17;
      v19 = UserContext[1];
      if ( *(__int64 **)(v19 + 8) == UserContext + 1 )
      {
        v20 = (__int64 **)UserContext[2];
        if ( *v20 == UserContext + 1 )
        {
          *v20 = (__int64 *)v19;
          *(_QWORD *)(v19 + 8) = v20;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
LABEL_17:
          RtlReleaseSRWLockExclusive(v18 + 8);
          return 3221225524LL;
        }
      }
LABEL_79:
      __fastfail(3u);
    }
  }
  v21 = a6;
  if ( a6 )
  {
    if ( !Application[24] )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_i(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
          Application[12]);
      goto LABEL_23;
    }
    if ( (*((_DWORD *)Application + 33) & 0x1000) != 0 )
    {
LABEL_23:
      v22 = -1073741772;
      goto LABEL_60;
    }
    v23 = Application[10];
    v24 = Application[11];
    v45 = v23;
    v51 = v23;
    v46 = v24;
    v41 = v24;
    if ( !Application[27] || (v25 = (HANDLE *)(Application + 28), !Application[28]) || !v23 || !v24 )
    {
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      RtlAcquireSRWLockExclusive(Application + 41);
      InitialState = 0;
      if ( !Application[27] )
      {
        v27 = NtCreateEvent((PHANDLE)Application + 27, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
        InitialState = 0;
        v22 = v27;
        if ( v27 < 0 )
          goto LABEL_31;
      }
      if ( !Application[28] )
      {
        if ( (Application[16] & 4) == 0 && !*((_DWORD *)Application + 34) )
          InitialState = 1;
        v22 = NtCreateEvent((PHANDLE)Application + 28, 0x1F0003u, &ObjectAttributes, NotificationEvent, InitialState);
        if ( v22 < 0 )
          goto LABEL_31;
      }
      v22 = PsmpAllocateTcNotify((__int64)Application, &v51);
      if ( v22 >= 0 )
      {
        v22 = PsmpAllocateWorkItemNotify((__int64)Application, &v41);
        RtlReleaseSRWLockExclusive(Application + 41);
        if ( v22 >= 0 )
        {
          v25 = (HANDLE *)(Application + 28);
          v45 = v51;
          v46 = v41;
          goto LABEL_40;
        }
      }
      else
      {
LABEL_31:
        RtlReleaseSRWLockExclusive(Application + 41);
      }
LABEL_59:
      v7 = a2;
      goto LABEL_60;
    }
LABEL_40:
    v28 = *(void **)(v6 + 16);
    v22 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, (HANDLE)Application[24], v28, &TargetHandle, 4u, 0, 0);
    if ( v22 >= 0 )
    {
      v22 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, (HANDLE)Application[27], v28, &v43, 0x100000u, 0, 0);
      if ( v22 >= 0 )
      {
        v22 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, *v25, v28, &SourceHandle, 0x100000u, 0, 0);
        if ( v22 >= 0 )
        {
          LOBYTE(v51) = 0;
          v22 = 0;
          RtlAcquireSRWLockExclusive(v6 + 8);
          RtlAcquireSRWLockExclusive(Application + 41);
          v29 = (Application[16] & 2) == 0;
          v30 = *((_DWORD *)Application + 86);
          LODWORD(v41) = v30;
          if ( v29 )
          {
            if ( (unsigned int)(v30 - 5) <= 1 )
            {
              v22 = -1073741772;
            }
            else
            {
              RtlAcquireSRWLockExclusive(Application[39] + 48LL);
              v31 = Application + 840;
              v32 = Application[840];
              if ( *(_QWORD **)(v32 + 8) != Application + 840 )
                goto LABEL_79;
              v33 = (_QWORD *)Application[841];
              if ( (_QWORD *)*v33 != v31 )
                goto LABEL_79;
              *v33 = v32;
              *(_QWORD *)(v32 + 8) = v33;
              RtlReleaseSRWLockExclusive(Application[39] + 48LL);
              v34 = *(_QWORD **)(v6 + 40);
              if ( *v34 != v6 + 32 )
                goto LABEL_79;
              *v31 = v6 + 32;
              Application[841] = v34;
              *v34 = v31;
              *(_QWORD *)(v6 + 40) = v31;
              _interlockedbittestandset((volatile signed __int32 *)Application + 32, 1u);
              LOBYTE(v51) = 1;
            }
          }
          RtlReleaseSRWLockExclusive(Application + 41);
          RtlReleaseSRWLockExclusive(v6 + 8);
          if ( v22 >= 0 )
          {
            *(_QWORD *)(v21 + 24) = SourceHandle;
            *(_QWORD *)(v21 + 16) = v43;
            *(_QWORD *)(v21 + 8) = TargetHandle;
            *(_QWORD *)(v21 + 32) = v45;
            *(_QWORD *)(v21 + 40) = v46;
            if ( (_BYTE)v51 )
              PsmpReferenceApplication((__int64)Application);
            *(_DWORD *)(v21 + 4) = 0;
            if ( (Application[16] & 0x100000) != 0 )
              *(_DWORD *)(v21 + 4) = 2;
            v37 = PsmpConvertInternalApplicationState((unsigned int)v41, v35, v36);
            *(_DWORD *)v21 = v37;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              WPP_SF_iD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                63,
                &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
                Application[12],
                v37);
            goto LABEL_58;
          }
          NtDuplicateObject(v28, SourceHandle, 0, 0, 0, 0, 1u);
        }
        NtDuplicateObject(v28, v43, 0, 0, 0, 0, 1u);
      }
      NtDuplicateObject(v28, TargetHandle, 0, 0, 0, 0, 1u);
    }
LABEL_58:
    v10 = a1;
    goto LABEL_59;
  }
  v22 = -1073741823;
  RtlAcquireSRWLockExclusive(v6 + 8);
  if ( (Application[16] & 2) != 0 )
  {
    v22 = 0;
    PsmpDeleteCacheEntry((__int64)Application, 0);
  }
  RtlReleaseSRWLockExclusive(v6 + 8);
  if ( v22 >= 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_i(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
        Application[12]);
    PsmpDereferenceApplicationEx((__int64)Application, 0);
  }
LABEL_60:
  if ( a3 && v10 && v7 )
  {
    PsmpDereferenceApplicationEx((__int64)Application, 0);
    v38 = UserContext[7];
    RtlAcquireSRWLockExclusive(v38 + 8);
    if ( PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
    {
      v39 = UserContext[1];
      if ( *(__int64 **)(v39 + 8) != UserContext + 1 )
        goto LABEL_79;
      v40 = (__int64 **)UserContext[2];
      if ( *v40 != UserContext + 1 )
        goto LABEL_79;
      *v40 = (__int64 *)v39;
      *(_QWORD *)(v39 + 8) = v40;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
    }
    RtlReleaseSRWLockExclusive(v38 + 8);
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18000191c  mov     rax, rsp
0x18000191f  mov     [rax+18h], r8
0x180001923  mov     [rax+10h], rdx
0x180001927  mov     [rax+8], rcx
0x18000192b  push    rbp
0x18000192c  push    rbx
0x18000192d  push    rsi
0x18000192e  push    rdi
0x18000192f  push    r12
0x180001931  push    r13
0x180001933  push    r14
0x180001935  push    r15
0x180001937  lea     rbp, [rax-4Fh]
0x18000193b  sub     rsp, 0A8h
0x180001942  mov     r13, [rbp+47h+arg_20]
0x180001946  xorps   xmm0, xmm0
0x180001949  mov     r15, rdx
0x18000194c  xor     eax, eax
0x18000194e  xor     edx, edx
0x180001950  mov     rdi, r9
0x180001953  mov     [rbp+47h+var_90], rdx
0x180001957  mov     r14, r8
0x18000195a  mov     [rbp+47h+TargetHandle], rdx
0x18000195e  mov     r12, rcx
0x180001961  mov     [rbp+47h+SourceHandle], rdx
0x180001965  mov     esi, edx
0x180001967  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x18000196b  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x18000196f  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x180001973  test    r9, r9
0x180001976  jnz     loc_180001AAA
0x18000197c  mov     rbx, [r13+38h]
0x180001980  lea     rcx, [rbx+8]
0x180001984  call    cs:__imp_RtlAcquireSRWLockShared
0x18000198a  mov     edx, [r12]
0x18000198e  mov     r8, r15
0x180001991  mov     rcx, rbx
0x180001994  call    PsmpFindUserContext
0x180001999  lea     rcx, [rbx+8]
0x18000199d  mov     rsi, rax
0x1800019a0  call    cs:__imp_RtlReleaseSRWLockShared
0x1800019a6  xor     eax, eax
0x1800019a8  test    rsi, rsi
0x1800019ab  jnz     short loc_1800019E8
0x1800019ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019b4  test    byte ptr [rcx+1Ch], 2
0x1800019b8  jz      short loc_1800019DE
0x1800019ba  cmp     byte ptr [rcx+19h], 2
0x1800019be  jb      short loc_1800019DE
0x1800019c0  mov     eax, [r12]
0x1800019c4  lea     edx, [rdi+3Ch]
0x1800019c7  mov     rcx, [rcx+10h]; LoggerHandle
0x1800019cb  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x1800019d2  mov     r9, r15
0x1800019d5  mov     dword ptr [rsp+0E0h+InitialState], eax; char
0x1800019d9  call    WPP_SF__sid_d
0x1800019de  mov     eax, 0C0000034h
0x1800019e3  jmp     loc_180001EBE
0x1800019e8  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800019ec  inc     r9
0x1800019ef  cmp     [r14+r9*2], ax
0x1800019f4  jnz     short loc_1800019EC
0x1800019f6  lea     r9, ds:2[r9*2]
0x1800019fe  mov     r8, r14
0x180001a01  mov     rdx, rsi
0x180001a04  xor     ecx, ecx
0x180001a06  call    PsmpFindApplication
0x180001a0b  xor     edx, edx
0x180001a0d  mov     rdi, rax
0x180001a10  test    rax, rax
0x180001a13  jnz     loc_180001AAA
0x180001a19  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a20  test    byte ptr [rcx+1Ch], 2
0x180001a24  jz      short loc_180001A42
0x180001a26  cmp     byte ptr [rcx+19h], 2
0x180001a2a  jb      short loc_180001A42
0x180001a2c  mov     rcx, [rcx+10h]
0x180001a30  lea     edx, [rax+3Dh]
0x180001a33  mov     r9, r14
0x180001a36  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180001a3d  call    WPP_SF_S
0x180001a42  mov     rbx, [rsi+38h]
0x180001a46  lea     rcx, [rbx+8]
0x180001a4a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001a50  xor     edx, edx
0x180001a52  mov     rcx, rsi
0x180001a55  call    PsmpDereferenceObjectEx
0x180001a5a  test    al, al
0x180001a5c  jz      short loc_180001A9B
0x180001a5e  lea     rax, [rsi+8]
0x180001a62  mov     rdx, [rax]
0x180001a65  cmp     [rdx+8], rax
0x180001a69  jnz     loc_180001FBC
0x180001a6f  mov     r8, [rax+8]
0x180001a73  cmp     [r8], rax
0x180001a76  jnz     loc_180001FBC
0x180001a7c  mov     [r8], rdx
0x180001a7f  mov     [rdx+8], r8
0x180001a83  mov     r8, rsi; P
0x180001a86  mov     rcx, gs:60h
0x180001a8f  xor     edx, edx; Flags
0x180001a91  mov     rcx, [rcx+30h]; HeapHandle
0x180001a95  call    cs:__imp_RtlFreeHeap
0x180001a9b  lea     rcx, [rbx+8]
0x180001a9f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001aa5  jmp     loc_1800019DE
0x180001aaa  mov     r14, [rbp+47h+arg_28]
0x180001aae  test    r14, r14
0x180001ab1  jz      loc_180001F4B
0x180001ab7  cmp     [rdi+0C0h], rdx
0x180001abe  jnz     short loc_180001AF6
0x180001ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ac7  test    byte ptr [rcx+1Ch], 2
0x180001acb  jz      short loc_180001AEC
0x180001acd  cmp     byte ptr [rcx+19h], 3
0x180001ad1  jb      short loc_180001AEC
0x180001ad3  mov     r9, [rdi+60h]
0x180001ad7  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180001ade  mov     rcx, [rcx+10h]
0x180001ae2  mov     edx, 3Eh ; '>'
0x180001ae7  call    WPP_SF_i
0x180001aec  mov     ebx, 0C0000034h
0x180001af1  jmp     loc_180001E3E
0x180001af6  test    dword ptr [rdi+84h], 1000h
0x180001b00  jnz     short loc_180001AEC
0x180001b02  mov     rax, [rdi+50h]
0x180001b06  lea     rbx, [rdi+0D8h]
0x180001b0d  mov     rcx, [rdi+58h]
0x180001b11  mov     [rbp+47h+var_80], rax
0x180001b15  mov     [rbp+47h+arg_18], rax
0x180001b19  mov     [rbp+47h+var_78], rcx
0x180001b1d  mov     [rbp+47h+var_A0], rcx
0x180001b21  cmp     [rbx], rdx
0x180001b24  jz      short loc_180001B40
0x180001b26  lea     r15, [rdi+0E0h]
0x180001b2d  cmp     [r15], rdx
0x180001b30  jz      short loc_180001B40
0x180001b32  test    rax, rax
0x180001b35  jz      short loc_180001B40
0x180001b37  test    rcx, rcx
0x180001b3a  jnz     loc_180001C29
0x180001b40  xorps   xmm0, xmm0
0x180001b43  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x180001b4a  lea     r15, [rdi+148h]
0x180001b51  mov     [rbp+47h+ObjectAttributes.RootDirectory], rdx
0x180001b55  mov     rcx, r15
0x180001b58  mov     [rbp+47h+ObjectAttributes.Attributes], edx
0x180001b5b  mov     [rbp+47h+ObjectAttributes.ObjectName], rdx
0x180001b5f  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x180001b64  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001b6a  xor     ecx, ecx
0x180001b6c  cmp     [rbx], rcx
0x180001b6f  jnz     short loc_180001BA1
0x180001b71  mov     [rsp+0E0h+InitialState], cl; InitialState
0x180001b75  lea     r9d, [rcx+1]; EventType
0x180001b79  mov     rcx, rbx; EventHandle
0x180001b7c  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180001b80  mov     edx, 1F0003h; DesiredAccess
0x180001b85  call    cs:__imp_NtCreateEvent
0x180001b8b  xor     ecx, ecx
0x180001b8d  mov     ebx, eax
0x180001b8f  test    eax, eax
0x180001b91  jns     short loc_180001BA1
0x180001b93  mov     rcx, r15
0x180001b96  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001b9c  jmp     loc_180001E3A
0x180001ba1  lea     rax, [rdi+0E0h]
0x180001ba8  cmp     [rax], rcx
0x180001bab  jnz     short loc_180001BDF
0x180001bad  test    byte ptr [rdi+80h], 4
0x180001bb4  jnz     short loc_180001BC0
0x180001bb6  cmp     [rdi+88h], ecx
0x180001bbc  jnz     short loc_180001BC0
0x180001bbe  mov     cl, 1
0x180001bc0  mov     [rsp+0E0h+InitialState], cl; InitialState
0x180001bc4  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180001bc8  mov     rcx, rax; EventHandle
0x180001bcb  xor     r9d, r9d; EventType
0x180001bce  mov     edx, 1F0003h; DesiredAccess
0x180001bd3  call    cs:__imp_NtCreateEvent
0x180001bd9  mov     ebx, eax
0x180001bdb  test    eax, eax
0x180001bdd  js      short loc_180001B93
0x180001bdf  lea     rdx, [rbp+47h+arg_18]
0x180001be3  mov     rcx, rdi
0x180001be6  call    PsmpAllocateTcNotify
0x180001beb  mov     ebx, eax
0x180001bed  test    eax, eax
0x180001bef  js      short loc_180001B93
0x180001bf1  lea     rdx, [rbp+47h+var_A0]
0x180001bf5  mov     rcx, rdi
0x180001bf8  call    PsmpAllocateWorkItemNotify
0x180001bfd  mov     rcx, r15
0x180001c00  mov     ebx, eax
0x180001c02  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001c08  xor     edx, edx
0x180001c0a  test    ebx, ebx
0x180001c0c  js      loc_180001E3A
0x180001c12  mov     rax, [rbp+47h+arg_18]
0x180001c16  lea     r15, [rdi+0E0h]
0x180001c1d  mov     [rbp+47h+var_80], rax
0x180001c21  mov     rax, [rbp+47h+var_A0]
0x180001c25  mov     [rbp+47h+var_78], rax
0x180001c29  mov     r12, [r13+10h]
0x180001c2d  lea     r9, [rbp+47h+TargetHandle]; TargetHandle
0x180001c31  mov     [rsp+30h], edx; Options
0x180001c35  mov     r8, r12; TargetProcessHandle
0x180001c38  mov     [rsp+0E0h+HandleAttributes], edx; HandleAttributes
0x180001c3c  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180001c40  mov     rdx, [rdi+0C0h]; SourceHandle
0x180001c47  mov     dword ptr [rsp+0E0h+InitialState], 4; DesiredAccess
0x180001c4f  call    cs:__imp_NtDuplicateObject
0x180001c55  mov     ebx, eax
0x180001c57  test    eax, eax
0x180001c59  js      loc_180001E36
0x180001c5f  mov     rdx, [rdi+0D8h]; SourceHandle
0x180001c66  lea     r9, [rbp+47h+var_90]; TargetHandle
0x180001c6a  mov     dword ptr [rsp+30h], 0; Options
0x180001c72  mov     r8, r12; TargetProcessHandle
0x180001c75  mov     [rsp+0E0h+HandleAttributes], 0; HandleAttributes
0x180001c7d  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180001c81  mov     dword ptr [rsp+0E0h+InitialState], 100000h; DesiredAccess
0x180001c89  call    cs:__imp_NtDuplicateObject
0x180001c8f  mov     ebx, eax
0x180001c91  xor     eax, eax
0x180001c93  test    ebx, ebx
0x180001c95  js      loc_180001F1E
0x180001c9b  mov     rdx, [r15]; SourceHandle
0x180001c9e  lea     r9, [rbp+47h+SourceHandle]; TargetHandle
0x180001ca2  mov     [rsp+30h], eax; Options
0x180001ca6  mov     r8, r12; TargetProcessHandle
0x180001ca9  mov     [rsp+0E0h+HandleAttributes], eax; HandleAttributes
0x180001cad  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180001cb1  mov     dword ptr [rsp+0E0h+InitialState], 100000h; DesiredAccess
0x180001cb9  call    cs:__imp_NtDuplicateObject
0x180001cbf  xor     r15d, r15d
0x180001cc2  mov     ebx, eax
0x180001cc4  test    eax, eax
0x180001cc6  js      loc_180001EF7
0x180001ccc  lea     rcx, [r13+8]
0x180001cd0  mov     byte ptr [rbp+47h+arg_18], r15b
0x180001cd4  mov     ebx, r15d
0x180001cd7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001cdd  lea     rcx, [rdi+148h]
0x180001ce4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001cea  test    byte ptr [rdi+80h], 2
0x180001cf1  mov     eax, [rdi+158h]
0x180001cf7  mov     dword ptr [rbp+47h+var_A0], eax
0x180001cfa  jnz     loc_180001D85
0x180001d00  add     eax, 0FFFFFFFBh
0x180001d03  cmp     eax, 1
0x180001d06  jbe     short loc_180001D80
0x180001d08  mov     rcx, [rdi+138h]
0x180001d0f  add     rcx, 30h ; '0'
0x180001d13  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001d19  lea     r15, [rdi+1A40h]
0x180001d20  mov     rcx, [r15]
0x180001d23  cmp     [rcx+8], r15
0x180001d27  jnz     loc_180001FBC
0x180001d2d  mov     rax, [r15+8]
0x180001d31  cmp     [rax], r15
0x180001d34  jnz     loc_180001FBC
0x180001d3a  mov     [rax], rcx
0x180001d3d  mov     [rcx+8], rax
0x180001d41  mov     rcx, [rdi+138h]
0x180001d48  add     rcx, 30h ; '0'
0x180001d4c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001d52  lea     rax, [r13+20h]
0x180001d56  mov     rcx, [rax+8]
0x180001d5a  cmp     [rcx], rax
0x180001d5d  jnz     loc_180001FBC
0x180001d63  mov     [r15], rax
0x180001d66  mov     [r15+8], rcx
0x180001d6a  mov     [rcx], r15
0x180001d6d  mov     [rax+8], r15
0x180001d71  lock bts dword ptr [rdi+80h], 1
0x180001d7a  mov     byte ptr [rbp+47h+arg_18], 1
0x180001d7e  jmp     short loc_180001D85
0x180001d80  mov     ebx, 0C0000034h
0x180001d85  lea     rcx, [rdi+148h]
0x180001d8c  mov     r15d, 8
0x180001d92  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001d98  lea     rcx, [r15+r13]
0x180001d9c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001da2  xor     r15d, r15d
0x180001da5  test    ebx, ebx
0x180001da7  js      loc_180001ED2
0x180001dad  mov     rax, [rbp+47h+SourceHandle]
0x180001db1  mov     [r14+18h], rax
0x180001db5  mov     rax, [rbp+47h+var_90]
0x180001db9  mov     [r14+10h], rax
0x180001dbd  mov     rax, [rbp+47h+TargetHandle]
0x180001dc1  mov     [r14+8], rax
0x180001dc5  mov     rax, [rbp+47h+var_80]
0x180001dc9  mov     [r14+20h], rax
0x180001dcd  mov     rax, [rbp+47h+var_78]
0x180001dd1  mov     [r14+28h], rax
0x180001dd5  cmp     byte ptr [rbp+47h+arg_18], r15b
0x180001dd9  jz      short loc_180001DE3
0x180001ddb  mov     rcx, rdi
  ... truncated ...
```
