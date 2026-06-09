# PsmReferenceBrokeredExecution

- ea: `0x18000abf0`
- end: `0x18000b1ca`
- name: `PsmReferenceBrokeredExecution`
- size: `1498`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800092b4`
- `0x180009b40`
- `0x18000a750`
- `0x18000abf0`
- `0x18000b1d0`
- `0x18000b3d8`
- `0x18000b4d8`
- `0x18000b894`
- `0x18000cb34`
- `0x18000cce0`
- `0x18000defc`
- `0x18000e2cc`
- `0x18000e3d0`
- `0x18000eff0`
- `0x180010228`
- `0x18001067c`
- `0x180011448`
- `0x180013d68`
- `0x180014c34`
- `0x180014d74`
- `0x18001720c`
- `0x1800179d8`
- `0x180019c30`
- `0x180019e3c`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001ea9c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000b006`
- `ntdll!RtlFreeHeap` at `0x18000b006`
- `ntdll!RtlCopySid` at `0x18000ad26`
- `ntdll!RtlCopySid` at `0x18000ad26`
- `ntdll!RtlAllocateHeap` at `0x18000af18`
- `ntdll!RtlAllocateHeap` at `0x18000af18`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000adce`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000adce`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000adf1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000adf1`

## pseudocode

```c
__int64 __fastcall PsmReferenceBrokeredExecution(
        void *a1,
        unsigned int a2,
        const wchar_t *a3,
        unsigned int a4,
        __int64 a5,
        unsigned __int8 a6,
        unsigned int a7,
        _QWORD *a8)
{
  __int64 v10; // rdi
  __int64 *v11; // r14
  int v12; // r15d
  __int64 v13; // rbx
  __int64 v14; // rdx
  const wchar_t *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rcx
  int *v18; // rax
  const wchar_t *v19; // rdx
  char *pSid; // rsi
  int *v21; // rcx
  PSID v22; // r8
  __int64 ManagerContext; // rax
  __int64 v24; // r8
  char *v25; // r12
  __int64 UserContext; // rsi
  int v27; // eax
  int v28; // ebx
  __int64 v29; // r15
  signed __int32 v30; // eax
  int v32; // eax
  unsigned int v33; // r13d
  int v34; // ebx
  __int64 v35; // rcx
  _QWORD *Heap; // r15
  int v37; // eax
  __int64 v38; // rdx
  _QWORD *v39; // rcx
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  char v43[8]; // [rsp+28h] [rbp-D8h]
  int v44; // [rsp+30h] [rbp-D0h]
  __int64 *v45; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+40h] [rbp-C0h] BYREF
  char v47[4]; // [rsp+48h] [rbp-B8h]
  unsigned int v48; // [rsp+4Ch] [rbp-B4h]
  PSID SourceSid; // [rsp+50h] [rbp-B0h]
  _QWORD *v50; // [rsp+58h] [rbp-A8h]
  unsigned int v51; // [rsp+60h] [rbp-A0h]
  int v52; // [rsp+64h] [rbp-9Ch]
  int v53[116]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE DestinationSid[72]; // [rsp+238h] [rbp+138h] BYREF

  SourceSid = a1;
  v48 = a4;
  *(_DWORD *)v47 = a2;
  v50 = a8;
  v46 = 0;
  v10 = 0;
  v45 = 0;
  v11 = 0;
  switch ( a4 )
  {
    case 1u:
      v12 = 0;
      v44 = 0;
      break;
    case 2u:
      v12 = 8;
      v44 = 1;
      break;
    case 3u:
      v12 = 4;
      v44 = 2;
      break;
    default:
      __int2c();
      return (unsigned int)-1073741811;
  }
  v13 = 232;
  if ( !a3 )
    goto LABEL_55;
  v14 = 232;
  v15 = a3;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = (232 - v14) & -(__int64)(v14 != 0);
  if ( !v14 )
LABEL_55:
    LODWORD(v16) = 0;
  memset_0(v53, 0, 0x218u);
  v51 = a2;
  v52 = 2 * v16 + 2;
  v17 = 2147483646;
  v18 = v53;
  v19 = a3;
  do
  {
    if ( !v17 )
      break;
    if ( !*v19 )
      break;
    *(_WORD *)v18 = *v19++;
    v18 = (int *)((char *)v18 + 2);
    --v17;
    --v13;
  }
  while ( v13 );
  pSid = (char *)SourceSid;
  v21 = (int *)((char *)v18 - 2);
  v22 = SourceSid;
  if ( v13 )
    v21 = v18;
  *(_WORD *)v21 = 0;
  RtlCopySid(0x44u, DestinationSid, v22);
  DestinationSid[68] = a6;
  ManagerContext = PsmpFindOrCreateManagerContext(a6, v51);
  v25 = (char *)ManagerContext;
  if ( !ManagerContext )
  {
    v28 = -1073741823;
    goto LABEL_24;
  }
  UserContext = PsmpFindOrCreateUserContext(ManagerContext, v51, DestinationSid);
  if ( UserContext )
  {
    v27 = PsmpAllocateOrLookupApplicationStruct((int)v25, UserContext, (int)v53, v12, 0, (__int64)&v46);
    v10 = v46;
    v28 = v27;
    if ( v27 >= 0 && (PsmpQueryUsageInfoEnabled == 1 || PsmpE3Enabled) )
    {
      v46 = 0;
      PsmpAllocateOrLookupAppUsageInfo(v10, (__int64)v53, (signed __int32 **)&v46);
    }
    v29 = *(_QWORD *)(UserContext + 56);
    RtlAcquireSRWLockExclusive(v29 + 8);
    v30 = _InterlockedDecrement((volatile signed __int32 *)UserContext);
    if ( v30 == -1 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else if ( (v30 & 0x7FFFFFFF) == 0 )
    {
      v38 = *(_QWORD *)(UserContext + 8);
      if ( *(_QWORD *)(v38 + 8) != UserContext + 8 || (v39 = *(_QWORD **)(UserContext + 16), *v39 != UserContext + 8) )
        __fastfail(3u);
      *v39 = v38;
      *(_QWORD *)(v38 + 8) = v39;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)UserContext);
    }
    RtlReleaseSRWLockExclusive(v29 + 8);
  }
  else
  {
    v28 = -1073741823;
  }
  PsmpDereferenceManagerContext(v25);
  if ( v28 < 0 )
  {
    pSid = (char *)SourceSid;
LABEL_24:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      *(_DWORD *)v43 = *(_DWORD *)v47;
      WPP_SF_S_sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xEu, v24, a3, pSid, *(_QWORD *)v43);
    }
    goto LABEL_25;
  }
  v32 = PsmpSetApplicationType(v10, ((a7 >> 1) & 1) == 0, (a7 >> 2) & 1, 0);
  v28 = v32;
  if ( v32 < 0 )
  {
    v40 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_25;
    v41 = 15;
LABEL_64:
    WPP_SF_iD(v40[2], v41, &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids, *(_QWORD *)(v10 + 96), v32);
    goto LABEL_25;
  }
  v32 = PsmpInitializePolicyForApplication(v10);
  v28 = v32;
  if ( v32 < 0 )
  {
    v40 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_25;
    v41 = 16;
    goto LABEL_64;
  }
  v32 = PsmpSuppressApplicationSandbox(v10, 0);
  v28 = v32;
  if ( v32 >= 0 )
  {
    v33 = v48;
    if ( v48 == 2 )
    {
      v28 = PsmpFindOrCreateHostJobContext(v10, a5, &v45);
      if ( v28 < 0 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_ii(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
            *(_QWORD *)(v10 + 96),
            a5);
        v11 = v45;
        goto LABEL_40;
      }
      v11 = v45;
    }
    PsmpSetAntiStarvationTimer(v10);
    v34 = v44;
    v35 = *(int *)(v10 + 120) + 2LL * dword_18003FE74;
    if ( (a7 & 1) != 0 )
    {
      ++HIDWORD(PsmpCounters[5 * v35]);
      v34 = v44 | 4;
      PsmpBeginTimeCriticalTask(v10);
    }
    else
    {
      ++LODWORD(PsmpCounters[5 * v35]);
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
    if ( Heap )
    {
      PsmpReferenceApplication(v10);
      if ( v11 )
        PsmpReferenceHostContext(v11);
      *Heap = v10;
      Heap[1] = v11;
      *((_DWORD *)Heap + 4) = v34;
      v37 = PsmpBeginWorkItemExecution(v10, v33, v11, 0);
      v28 = v37;
      if ( v37 >= 0 )
      {
        v28 = 0;
        *v50 = Heap;
        goto LABEL_40;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_iLL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
          *(_QWORD *)(v10 + 96),
          v33,
          v37);
      PsmpInternalWorkItemReferenceDestroy(Heap);
    }
    else
    {
      v28 = -1073741801;
    }
    PsmpCancelAntiStarvationTimer(v10, 0);
    v42 = *(int *)(v10 + 120) + 2LL * dword_18003FE74;
    if ( (a7 & 1) != 0 )
    {
      --HIDWORD(PsmpCounters[5 * v42]);
      PsmpEndTimeCriticalTask(v10);
    }
    else
    {
      --LODWORD(PsmpCounters[5 * v42]);
    }
LABEL_40:
    if ( v11 )
      PsmpDereferenceHostContext(v11, 0);
    goto LABEL_25;
  }
  v40 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v41 = 17;
    goto LABEL_64;
  }
LABEL_25:
  if ( v10 )
    PsmpDereferenceApplicationEx(v10, 0);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x18000abf0  mov     [rsp-8+arg_8], rbx
0x18000abf5  push    rbp
0x18000abf6  push    rsi
0x18000abf7  push    rdi
0x18000abf8  push    r12
0x18000abfa  push    r13
0x18000abfc  push    r14
0x18000abfe  push    r15
0x18000ac00  lea     rbp, [rsp-190h]
0x18000ac08  sub     rsp, 290h
0x18000ac0f  mov     rax, cs:__security_cookie
0x18000ac16  xor     rax, rsp
0x18000ac19  mov     [rbp+1C0h+var_40], rax
0x18000ac20  mov     rax, [rbp+1C0h+arg_38]
0x18000ac27  xor     r10d, r10d
0x18000ac2a  mov     r13, r8
0x18000ac2d  mov     [rsp+2C0h+SourceSid], rcx
0x18000ac32  mov     r8d, r9d
0x18000ac35  mov     [rsp+2C0h+var_274], r9d
0x18000ac3a  mov     r12d, edx
0x18000ac3d  mov     dword ptr [rsp+2C0h+var_278], edx
0x18000ac41  lea     ecx, [r10+1]
0x18000ac45  mov     [rsp+2C0h+var_268], rax
0x18000ac4a  mov     [rsp+2C0h+var_280], r10
0x18000ac4f  mov     edi, r10d
0x18000ac52  mov     [rsp+2C0h+var_288], r10
0x18000ac57  mov     r14d, r10d
0x18000ac5a  sub     r8d, ecx
0x18000ac5d  jnz     loc_18000AF9A
0x18000ac63  mov     r15d, r10d
0x18000ac66  mov     [rsp+2C0h+var_290], r10d
0x18000ac6b  mov     ebx, 0E8h
0x18000ac70  test    r13, r13
0x18000ac73  jz      loc_18000B03C
0x18000ac79  mov     edx, ebx
0x18000ac7b  mov     rax, r13
0x18000ac7e  cmp     [rax], r10w
0x18000ac82  jz      short loc_18000AC8D
0x18000ac84  add     rax, 2
0x18000ac88  sub     rdx, rcx
0x18000ac8b  jnz     short loc_18000AC7E
0x18000ac8d  mov     rcx, rbx
0x18000ac90  mov     rax, rdx
0x18000ac93  sub     rcx, rdx
0x18000ac96  neg     rax
0x18000ac99  sbb     rsi, rsi
0x18000ac9c  and     rsi, rcx
0x18000ac9f  test    rdx, rdx
0x18000aca2  jz      loc_18000B03C
0x18000aca8  xor     edx, edx; Val
0x18000acaa  lea     rcx, [rsp+2C0h+var_258]; void *
0x18000acaf  mov     r8d, 218h; Size
0x18000acb5  call    memset_0
0x18000acba  lea     eax, ds:2[rsi*2]
0x18000acc1  mov     [rsp+2C0h+var_260], r12d
0x18000acc6  mov     [rsp+2C0h+var_25C], eax
0x18000acca  mov     ecx, 7FFFFFFEh
0x18000accf  lea     rax, [rsp+2C0h+var_258]
0x18000acd4  mov     rdx, r13
0x18000acd7  xor     r9d, r9d
0x18000acda  test    rcx, rcx
0x18000acdd  jz      short loc_18000AD03
0x18000acdf  movzx   r8d, word ptr [rdx]
0x18000ace3  test    r8w, r8w
0x18000ace7  jz      short loc_18000AD03
0x18000ace9  mov     [rax], r8w
0x18000aced  add     rdx, 2
0x18000acf1  mov     r8d, 1
0x18000acf7  add     rax, 2
0x18000acfb  sub     rcx, r8
0x18000acfe  sub     rbx, r8
0x18000ad01  jnz     short loc_18000ACDA
0x18000ad03  mov     rsi, [rsp+2C0h+SourceSid]
0x18000ad08  lea     rcx, [rax-2]
0x18000ad0c  test    rbx, rbx
0x18000ad0f  lea     rdx, [rbp+1C0h+DestinationSid]; DestinationSid
0x18000ad16  mov     r8, rsi; SourceSid
0x18000ad19  cmovnz  rcx, rax
0x18000ad1d  mov     [rcx], r9w
0x18000ad21  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000ad26  call    cs:__imp_RtlCopySid
0x18000ad2c  movzx   ecx, [rbp+1C0h+arg_28]
0x18000ad33  mov     edx, [rsp+2C0h+var_260]
0x18000ad37  mov     [rbp+1C0h+var_44], cl
0x18000ad3d  call    PsmpFindOrCreateManagerContext
0x18000ad42  mov     r12, rax
0x18000ad45  test    rax, rax
0x18000ad48  jz      loc_18000AF87
0x18000ad4e  mov     edx, [rsp+2C0h+var_260]
0x18000ad52  lea     r8, [rbp+1C0h+DestinationSid]
0x18000ad59  mov     rcx, rax
0x18000ad5c  call    PsmpFindOrCreateUserContext
0x18000ad61  mov     rsi, rax
0x18000ad64  test    rax, rax
0x18000ad67  jz      loc_18000B044
0x18000ad6d  lea     rax, [rsp+2C0h+var_280]
0x18000ad72  mov     r9d, r15d; int
0x18000ad75  mov     qword ptr [rsp+2C0h+var_298], rax; __int64
0x18000ad7a  lea     r8, [rsp+2C0h+var_258]; int
0x18000ad7f  mov     rdx, rsi; int
0x18000ad82  mov     [rsp+2C0h+pSid], rdi; SourceHandle
0x18000ad87  mov     rcx, r12; int
0x18000ad8a  call    PsmpAllocateOrLookupApplicationStruct
0x18000ad8f  mov     rdi, [rsp+2C0h+var_280]
0x18000ad94  mov     ebx, eax
0x18000ad96  test    eax, eax
0x18000ad98  js      short loc_18000ADC6
0x18000ad9a  movzx   eax, cs:PsmpQueryUsageInfoEnabled
0x18000ada1  mov     ecx, 1
0x18000ada6  cmp     ax, cx
0x18000ada9  jnz     loc_18000B04E
0x18000adaf  lea     r8, [rsp+2C0h+var_280]
0x18000adb4  mov     [rsp+2C0h+var_280], r14
0x18000adb9  lea     rdx, [rsp+2C0h+var_258]
0x18000adbe  mov     rcx, rdi
0x18000adc1  call    PsmpAllocateOrLookupAppUsageInfo
0x18000adc6  mov     r15, [rsi+38h]
0x18000adca  lea     rcx, [r15+8]
0x18000adce  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000add4  or      eax, 0FFFFFFFFh
0x18000add7  lock xadd [rsi], eax
0x18000addb  dec     eax
0x18000addd  cmp     eax, 0FFFFFFFFh
0x18000ade0  jz      short loc_18000AE54
0x18000ade2  test    eax, 7FFFFFFFh
0x18000ade7  jz      loc_18000AFD7
0x18000aded  lea     rcx, [r15+8]
0x18000adf1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000adf7  mov     rcx, r12; P
0x18000adfa  call    PsmpDereferenceManagerContext
0x18000adff  test    ebx, ebx
0x18000ae01  jns     short loc_18000AE5B
0x18000ae03  mov     rsi, [rsp+2C0h+SourceSid]
0x18000ae08  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae0f  test    byte ptr [rcx+1Ch], 2
0x18000ae13  jnz     loc_18000B060
0x18000ae19  test    rdi, rdi
0x18000ae1c  jz      short loc_18000AE28
0x18000ae1e  xor     edx, edx
0x18000ae20  mov     rcx, rdi
0x18000ae23  call    PsmpDereferenceApplicationEx
0x18000ae28  mov     eax, ebx
0x18000ae2a  mov     rcx, [rbp+1C0h+var_40]
0x18000ae31  xor     rcx, rsp; StackCookie
0x18000ae34  call    __security_check_cookie
0x18000ae39  mov     rbx, [rsp+2C0h+arg_8]
0x18000ae41  add     rsp, 290h
0x18000ae48  pop     r15
0x18000ae4a  pop     r14
0x18000ae4c  pop     r13
0x18000ae4e  pop     r12
0x18000ae50  pop     rdi
0x18000ae51  pop     rsi
0x18000ae52  pop     rbp
0x18000ae53  retn
0x18000ae54  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ae59  jmp     short loc_18000ADED
0x18000ae5b  mov     r12d, [rbp+1C0h+arg_30]
0x18000ae62  mov     r15d, 1
0x18000ae68  mov     edx, r12d
0x18000ae6b  mov     r8d, r12d
0x18000ae6e  shr     edx, 1
0x18000ae70  xor     r9d, r9d
0x18000ae73  not     edx
0x18000ae75  shr     r8d, 2
0x18000ae79  and     edx, r15d
0x18000ae7c  and     r8d, r15d
0x18000ae7f  mov     rcx, rdi
0x18000ae82  call    PsmpSetApplicationType
0x18000ae87  mov     ebx, eax
0x18000ae89  test    eax, eax
0x18000ae8b  js      loc_18000B08D
0x18000ae91  mov     rcx, rdi
0x18000ae94  call    PsmpInitializePolicyForApplication
0x18000ae99  mov     ebx, eax
0x18000ae9b  test    eax, eax
0x18000ae9d  js      loc_18000B0D1
0x18000aea3  xor     edx, edx
0x18000aea5  mov     rcx, rdi
0x18000aea8  call    PsmpSuppressApplicationSandbox
0x18000aead  mov     ebx, eax
0x18000aeaf  test    eax, eax
0x18000aeb1  js      loc_18000B0F3
0x18000aeb7  mov     r13d, [rsp+2C0h+var_274]
0x18000aebc  cmp     r13d, 2
0x18000aec0  jz      loc_18000AFAC
0x18000aec6  mov     rcx, rdi
0x18000aec9  call    PsmpSetAntiStarvationTimer
0x18000aece  movsxd  rax, dword ptr [rdi+78h]
0x18000aed2  lea     rsi, PsmpCounters
0x18000aed9  movsxd  rcx, cs:dword_18003FE74
0x18000aee0  mov     ebx, [rsp+2C0h+var_290]
0x18000aee4  lea     rcx, [rax+rcx*2]
0x18000aee8  lea     rax, [rcx+rcx*4]
0x18000aeec  and     r12d, r15d
0x18000aeef  jz      loc_18000AF91
0x18000aef5  add     [rsi+rax*8+4], r15d
0x18000aefa  or      ebx, 4
0x18000aefd  mov     rcx, rdi
0x18000af00  call    PsmpBeginTimeCriticalTask
0x18000af05  mov     rcx, gs:60h
0x18000af0e  xor     edx, edx; Flags
0x18000af10  mov     rcx, [rcx+30h]; HeapHandle
0x18000af14  lea     r8d, [rdx+18h]; Size
0x18000af18  call    cs:__imp_RtlAllocateHeap
0x18000af1e  mov     r15, rax
0x18000af21  test    rax, rax
0x18000af24  jz      loc_18000B14B
0x18000af2a  mov     rcx, rdi
0x18000af2d  call    PsmpReferenceApplication
0x18000af32  test    r14, r14
0x18000af35  jz      short loc_18000AF3F
0x18000af37  mov     rcx, r14
0x18000af3a  call    PsmpReferenceHostContext
0x18000af3f  mov     [r15], rdi
0x18000af42  mov     [r15+8], r14
0x18000af46  mov     [r15+10h], ebx
0x18000af4a  xor     r9d, r9d
0x18000af4d  mov     r8, r14
0x18000af50  mov     edx, r13d
0x18000af53  mov     rcx, rdi
0x18000af56  call    PsmpBeginWorkItemExecution
0x18000af5b  mov     ebx, eax
0x18000af5d  test    eax, eax
0x18000af5f  js      loc_18000B152
0x18000af65  mov     rax, [rsp+2C0h+var_268]
0x18000af6a  xor     ebx, ebx
0x18000af6c  mov     [rax], r15
0x18000af6f  test    r14, r14
0x18000af72  jz      loc_18000AE19
0x18000af78  xor     edx, edx
0x18000af7a  mov     rcx, r14
0x18000af7d  call    PsmpDereferenceHostContext
0x18000af82  jmp     loc_18000AE19
0x18000af87  mov     ebx, 0C0000001h
0x18000af8c  jmp     loc_18000AE08
0x18000af91  add     [rsi+rax*8], r15d
0x18000af95  jmp     loc_18000AF05
0x18000af9a  sub     r8d, ecx
0x18000af9d  jnz     short loc_18000B018
0x18000af9f  lea     r15d, [r8+8]
0x18000afa3  mov     [rsp+2C0h+var_290], ecx
0x18000afa7  jmp     loc_18000AC6B
0x18000afac  mov     rsi, [rbp+1C0h+arg_20]
0x18000afb3  lea     r8, [rsp+2C0h+var_288]
0x18000afb8  mov     rdx, rsi
0x18000afbb  mov     rcx, rdi
0x18000afbe  call    PsmpFindOrCreateHostJobContext
0x18000afc3  mov     ebx, eax
0x18000afc5  test    eax, eax
0x18000afc7  js      loc_18000B110
0x18000afcd  mov     r14, [rsp+2C0h+var_288]
0x18000afd2  jmp     loc_18000AEC6
0x18000afd7  lea     rax, [rsi+8]
0x18000afdb  mov     rdx, [rax]
0x18000afde  cmp     [rdx+8], rax
0x18000afe2  jnz     short loc_18000B011
0x18000afe4  mov     rcx, [rax+8]
0x18000afe8  cmp     [rcx], rax
0x18000afeb  jnz     short loc_18000B011
0x18000afed  mov     [rcx], rdx
0x18000aff0  mov     r8, rsi; P
0x18000aff3  mov     [rdx+8], rcx
0x18000aff7  xor     edx, edx; Flags
0x18000aff9  mov     rcx, gs:60h
0x18000b002  mov     rcx, [rcx+30h]; HeapHandle
0x18000b006  call    cs:__imp_RtlFreeHeap
0x18000b00c  jmp     loc_18000ADED
0x18000b011  mov     ecx, 3
0x18000b016  int     29h; Win8: RtlFailFast(ecx)
0x18000b018  cmp     r8d, ecx
0x18000b01b  jz      short loc_18000B029
0x18000b01d  int     2Ch; Windows NT - assertion failure
0x18000b01f  mov     ebx, 0C000000Dh
0x18000b024  jmp     loc_18000AE28
0x18000b029  mov     r15d, 4
0x18000b02f  mov     [rsp+2C0h+var_290], 2
0x18000b037  jmp     loc_18000AC6B
0x18000b03c  mov     rsi, r10
0x18000b03f  jmp     loc_18000ACA8
0x18000b044  mov     ebx, 0C0000001h
0x18000b049  jmp     loc_18000ADF7
0x18000b04e  cmp     cs:PsmpE3Enabled, r14b
0x18000b055  jz      loc_18000ADC6
0x18000b05b  jmp     loc_18000ADAF
0x18000b060  cmp     byte ptr [rcx+19h], 2
0x18000b064  jb      loc_18000AE19
0x18000b06a  mov     eax, dword ptr [rsp+2C0h+var_278]
0x18000b06e  mov     edx, 0Eh
0x18000b073  mov     rcx, [rcx+10h]; LoggerHandle
0x18000b077  mov     r9, r13
0x18000b07a  mov     dword ptr [rsp+2C0h+var_298], eax; char
0x18000b07e  mov     [rsp+2C0h+pSid], rsi; pSid
0x18000b083  call    WPP_SF_S_sid_d
0x18000b088  jmp     loc_18000AE19
0x18000b08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b094  test    byte ptr [rcx+1Ch], 2
0x18000b098  jz      loc_18000AE19
0x18000b09e  cmp     byte ptr [rcx+19h], 2
0x18000b0a2  jb      loc_18000AE19
  ... truncated ...
```
