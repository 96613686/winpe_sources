# UlSetConfigGroupProperty

- ea: `0x1400d4f08`
- end: `0x1400d5763`
- name: `UlSetConfigGroupProperty`
- size: `2139`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config`

## callers

- `0x1400f33c0`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x140061dd8`
- `0x140074468`
- `0x140074ad8`
- `0x1400868f0`
- `0x1400869c0`
- `0x14009620c`
- `0x1400a1f50`
- `0x1400a94d8`
- `0x1400d4f08`
- `0x1400d6378`
- `0x1400d7f4c`
- `0x1400e7f8c`
- `0x1400eeb94`
- `0x1400fd240`
- `0x140142df4`
- `0x140146c38`
- `0x140167810`
- `0x140167c40`
- `0x1401c8dac`
- `0x1401c8e0c`
- `0x1401c9510`
- `0x1401d9e44`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400d5082`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d50fc`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d5082`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d50fc`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d56cc`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d56cc`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d4fba`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d4fba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d56d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d56d8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d4fa7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d4fa7`

## pseudocode

```c
__int64 __fastcall UlSetConfigGroupProperty(IRP *a1, __int64 a2, __int64 a3, int a4, int *a5, int a6)
{
  __int64 v10; // rbx
  __int64 ObjectFromOpaqueId; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rsi
  char v16; // r12
  unsigned int v17; // ebx
  int v18; // edi
  BOOLEAN v19; // al
  char v20; // r9
  char v21; // r10
  int v22; // ebx
  unsigned int v23; // edx
  char v24; // cl
  __int16 v25; // ax
  volatile signed __int32 *v26; // r15
  BOOLEAN v27; // al
  unsigned __int64 v28; // r10
  int v29; // edx
  ULONG_PTR v30; // rdx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int started; // eax
  __int64 v35; // r14
  __int64 v36; // rax
  int v37; // eax
  char v38; // cl
  __int64 v39; // rdx
  int v40; // eax
  ULONG_PTR BugCheckParameter2; // [rsp+58h] [rbp-81h] BYREF
  __int64 v44; // [rsp+60h] [rbp-79h]
  unsigned int v45; // [rsp+68h] [rbp-71h]
  int v46[4]; // [rsp+70h] [rbp-69h]
  _OWORD v47[5]; // [rsp+80h] [rbp-59h] BYREF

  v44 = a2;
  *(_QWORD *)v46 = a3;
  BugCheckParameter2 = 0;
  memset(v47, 0, sizeof(v47));
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqiLqL(1028, 124, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, a1, a2, a3, a4, a5, a6);
  v10 = *(_QWORD *)(a2 + 56);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v10 + 1368));
  ObjectFromOpaqueId = UxGetObjectFromOpaqueId(
                         a3,
                         2,
                         (unsigned int)UlReferenceServerSession,
                         (unsigned int)UlValidateConfigGroup,
                         a2);
  v15 = ObjectFromOpaqueId;
  if ( !ObjectFromOpaqueId || *(_DWORD *)ObjectFromOpaqueId != 1245932629 )
  {
    v18 = -1073741811;
    goto LABEL_96;
  }
  v16 = 1;
  v17 = *(_DWORD *)(*(_QWORD *)(ObjectFromOpaqueId + 48) + 16LL);
  v45 = v17;
  if ( (_WORD)v17 == 1 )
  {
    LODWORD(v13) = HIWORD(v17);
    if ( !HIWORD(v17) )
    {
      v18 = -1073741637;
      goto LABEL_96;
    }
  }
  v18 = 0;
  if ( a4 > 9 )
  {
    switch ( a4 )
    {
      case 10:
        started = UlCaptureChannelBindConfig(
                    *(_QWORD *)(v44 + 56),
                    (int)a5,
                    0,
                    (int)ObjectFromOpaqueId + 384,
                    a1,
                    a1->RequestorMode);
        goto LABEL_89;
      case 11:
        *(_QWORD *)&v47[0] = *(_QWORD *)a5;
        started = UlpNotifyEdgePolicyChange(ObjectFromOpaqueId, v47);
        goto LABEL_89;
      case 12:
        *(_QWORD *)&v47[0] = *(_QWORD *)a5;
        started = UlScStartCounters(ObjectFromOpaqueId, v47);
        goto LABEL_89;
      case 15:
        *(_QWORD *)&v47[0] = *(_QWORD *)a5;
        v13 = HIDWORD(*(_QWORD *)&v47[0]);
        if ( BYTE4(v47[0]) >= 2u )
          goto LABEL_82;
        *(_QWORD *)(ObjectFromOpaqueId + 448) = *(_QWORD *)&v47[0];
        if ( (xmmword_1401A2CA0 & 0x10) == 0 )
          goto LABEL_90;
        v39 = 125;
        break;
      default:
        LODWORD(v13) = a4 - 16;
        if ( a4 == 16 )
          goto LABEL_44;
        LODWORD(v13) = a4 - 18;
        if ( a4 != 18 )
        {
          if ( a4 == 19 && UxKirBrHttpQuerySocketTtl )
          {
            v37 = *a5;
            DWORD1(v47[0]) = a5[1];
            v38 = *((_BYTE *)a5 + 8);
            LODWORD(v47[0]) = v37;
            BYTE8(v47[0]) = v38;
            *(_WORD *)((char *)v47 + 9) = *(_WORD *)((char *)a5 + 9);
            BYTE11(v47[0]) = *((_BYTE *)a5 + 11);
            LODWORD(v13) = a5[3];
            HIDWORD(v47[0]) = v13;
            *(_DWORD *)(v15 + 464) = v37;
            *(_DWORD *)(v15 + 468) = DWORD1(v47[0]);
            *(_QWORD *)(v15 + 472) = *((_QWORD *)&v47[0] + 1);
            if ( (xmmword_1401A2CA0 & 0x10) != 0 )
              WPP_SF_ili(v47[0] & 1, v12, v14, *(_QWORD *)(v15 + 8), v47[0] & 1, *((_QWORD *)&v47[0] + 1));
            goto LABEL_90;
          }
          goto LABEL_82;
        }
        if ( UxKirHttpBugFix2605 )
        {
          LODWORD(v13) = v44;
          if ( !*(_BYTE *)(*(_QWORD *)(v44 + 56) + 8736LL) )
          {
            v18 = -1073741637;
            goto LABEL_90;
          }
        }
        *(_QWORD *)&v47[0] = *(_QWORD *)a5;
        v13 = HIDWORD(*(_QWORD *)&v47[0]);
        if ( BYTE4(v47[0]) >= 2u )
        {
LABEL_82:
          v18 = -1073741811;
          goto LABEL_90;
        }
        *(_QWORD *)(ObjectFromOpaqueId + 456) = *(_QWORD *)&v47[0];
        if ( (xmmword_1401A2CA0 & 0x10) == 0 )
          goto LABEL_90;
        v39 = 126;
        break;
    }
    WPP_SF_ill(BYTE4(v47[0]), v39, v14, *(_QWORD *)(ObjectFromOpaqueId + 8), v47[0] & 1, BYTE4(v47[0]));
    goto LABEL_90;
  }
  switch ( a4 )
  {
    case 9:
      v36 = *(_QWORD *)a5;
      *(_QWORD *)&v47[0] = *(_QWORD *)a5;
      if ( (v47[0] & 1) == 0 )
        v36 = 0;
      *(_QWORD *)(v15 + 292) = v36;
      goto LABEL_90;
    case 0:
      goto LABEL_17;
    case 1:
      started = UlConfigLogging(ObjectFromOpaqueId + 120, ObjectFromOpaqueId, a5, a1);
      goto LABEL_89;
  }
  if ( a4 != 2 )
  {
    if ( a4 == 3 )
    {
      v33 = *a5;
      DWORD1(v47[0]) = a5[1];
      *((_QWORD *)&v47[0] + 1) = *((_QWORD *)a5 + 1);
      LOWORD(v47[1]) = *((_WORD *)a5 + 8);
      LODWORD(v13) = *((unsigned __int16 *)a5 + 9);
      WORD1(v47[1]) = *((_WORD *)a5 + 9);
      LODWORD(v47[0]) = v33;
      if ( (v33 & 1) != 0 )
      {
        *(_DWORD *)(v15 + 272) = v33;
        *(_DWORD *)(v15 + 276) = DWORD1(v47[0]);
        *(_QWORD *)(v15 + 280) = *((_QWORD *)&v47[0] + 1);
        *(_DWORD *)(v15 + 288) = v47[1];
      }
      else
      {
        *(_OWORD *)(v15 + 272) = 0;
        *(_DWORD *)(v15 + 288) = 0;
      }
      goto LABEL_90;
    }
    if ( a4 != 5 )
    {
      LODWORD(v13) = a4 - 7;
      if ( a4 == 7 )
      {
        v26 = 0;
        v27 = IoIs32bitProcess(a1);
        LODWORD(v13) = *a5;
        LODWORD(v47[0]) = *a5;
        if ( v27 )
        {
          v28 = (unsigned int)a5[1];
          *((_QWORD *)&v47[0] + 1) = v28;
        }
        else
        {
          DWORD1(v47[0]) = a5[1];
          *((_QWORD *)&v47[0] + 1) = *((_QWORD *)a5 + 1);
          v28 = *((_QWORD *)&v47[0] + 1);
        }
        v29 = *(_DWORD *)(v15 + 64);
        if ( (v29 & 1) != 0 && *(_QWORD *)(v15 + 72) )
          v26 = *(volatile signed __int32 **)(v15 + 72);
        if ( (v13 & 1) != 0 )
        {
          v18 = UlReferenceRequestQueueByHandle((HANDLE)v28, &BugCheckParameter2);
          if ( v18 < 0 )
            goto LABEL_90;
          v30 = BugCheckParameter2;
          if ( *(_WORD *)(BugCheckParameter2 + 276) != (_WORD)v17
            || (LODWORD(v13) = HIWORD(v45), *(_WORD *)(BugCheckParameter2 + 278) != HIWORD(v45)) )
          {
            v31 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2);
            if ( UxDebugCheckRefcount && v31 <= -1 )
              UlBugCheckEx(3u, v30, 0xAu, v31);
            if ( !v31 )
              UlFreeRequestQueue((PVOID)BugCheckParameter2);
            v18 = -1073741735;
            goto LABEL_90;
          }
          *(_DWORD *)(v15 + 64) |= 1u;
          LODWORD(v13) = BugCheckParameter2;
          *(_QWORD *)(v15 + 72) = BugCheckParameter2;
        }
        else
        {
          *(_QWORD *)(v15 + 72) = 0;
          *(_DWORD *)(v15 + 64) = v29 & 0xFFFFFFFE;
        }
        if ( v26 )
        {
          v32 = _InterlockedDecrement(v26);
          if ( UxDebugCheckRefcount && v32 <= -1 )
            UlBugCheckEx(3u, (ULONG_PTR)v26, 0xAu, v32);
          if ( !v32 )
            UlFreeRequestQueue((PVOID)v26);
        }
        goto LABEL_90;
      }
      if ( a4 == 8 )
      {
LABEL_17:
        v19 = IoIs32bitProcess(a1);
        v20 = *((_BYTE *)a5 + 9);
        v21 = *((_BYTE *)a5 + 10);
        v22 = *a5;
        v23 = a5[1];
        v24 = *((_BYTE *)a5 + 11);
        BYTE8(v47[0]) = *((_BYTE *)a5 + 8);
        BYTE9(v47[0]) = v20;
        BYTE10(v47[0]) = v21;
        *(_QWORD *)&v47[0] = __PAIR64__(v23, v22);
        if ( v19 )
        {
          *((_QWORD *)&v47[2] + 1) = (unsigned int)a5[6];
          LOWORD(v47[2]) = *((_WORD *)a5 + 10);
          *((_QWORD *)&v47[1] + 1) = (unsigned int)a5[4];
          LOWORD(v47[1]) = *((_WORD *)a5 + 6);
          *((_QWORD *)&v47[3] + 1) = (unsigned int)a5[8];
          v25 = *((_WORD *)a5 + 14);
        }
        else
        {
          *((_QWORD *)&v47[2] + 1) = *((_QWORD *)a5 + 5);
          LOWORD(v47[2]) = *((_WORD *)a5 + 16);
          *((_QWORD *)&v47[1] + 1) = *((_QWORD *)a5 + 3);
          LOWORD(v47[1]) = *((_WORD *)a5 + 8);
          *((_QWORD *)&v47[3] + 1) = *((_QWORD *)a5 + 7);
          v25 = *((_WORD *)a5 + 24);
        }
        LOWORD(v47[3]) = v25;
        v47[4] = 0;
        if ( a4 != 8 )
          v24 = 0;
        BYTE11(v47[0]) = v24;
        v35 = *(_QWORD *)(v44 + 56);
        v18 = UlVerifyAuthConfig(v35, v47);
        if ( v18 < 0 )
          goto LABEL_90;
        if ( (v22 & 1) != 0 )
        {
          started = UlCopyAuthConfig(v35, (int)v15 + 304, (unsigned int)v47, 0, 0, a1->RequestorMode);
          goto LABEL_89;
        }
        UlFreeAuthConfig(v15 + 304, 0);
LABEL_90:
        UlEventSetConfigGroupProperty(v13, v46[0], a4, v18, a1);
        if ( (xmmword_1401A2CA0 & 0x10) != 0 )
          WPP_SF_Dd(1028, 128, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)v18, a4);
        if ( v18 >= 0 && v16 )
          UlFlushCacheByConfigGroup(v15);
LABEL_96:
        if ( a4 != 2 )
          goto LABEL_98;
        goto LABEL_97;
      }
      goto LABEL_82;
    }
    *(_QWORD *)&v47[0] = *(_QWORD *)a5;
    v13 = HIDWORD(*(_QWORD *)&v47[0]);
    if ( DWORD1(v47[0]) > 1 )
      goto LABEL_82;
    if ( *(_DWORD *)(ObjectFromOpaqueId + 60) != DWORD1(v47[0]) )
    {
      *(_QWORD *)(ObjectFromOpaqueId + 56) = *(_QWORD *)&v47[0];
      goto LABEL_90;
    }
LABEL_44:
    v16 = 0;
    goto LABEL_90;
  }
  v18 = UlCaptureQosParameter(a1);
  if ( v18 >= 0 )
  {
    if ( !LODWORD(v47[0]) )
    {
      started = UlQosConfigureFlowCharacteristics(v15 + 80, (char *)v47 + 4);
LABEL_89:
      v18 = started;
      goto LABEL_90;
    }
    if ( LODWORD(v47[0]) == 1 )
    {
      started = UlSetConnectionsProperty(v15, (char *)v47 + 4);
      goto LABEL_89;
    }
    v18 = -1073741811;
  }
LABEL_97:
  *(_QWORD *)&v47[0] = 0;
  DWORD2(v47[0]) = 0;
LABEL_98:
  if ( v15 )
  {
    v40 = _InterlockedDecrement((volatile signed __int32 *)(v15 + 4));
    if ( UxDebugCheckRefcount && v40 <= -1 )
      UlBugCheckEx(3u, v15 + 4, 0xBu, v40);
    if ( !v40 )
      UlFreeConfigGroup((PVOID)v15);
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(v44 + 56) + 1368LL));
  KeLeaveCriticalRegion();
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 129, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)v18);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400d4f08  push    rbp
0x1400d4f0a  push    rbx
0x1400d4f0b  push    rsi
0x1400d4f0c  push    rdi
0x1400d4f0d  push    r12
0x1400d4f0f  push    r13
0x1400d4f11  push    r14
0x1400d4f13  push    r15
0x1400d4f15  lea     rbp, [rsp-0Fh]
0x1400d4f1a  sub     rsp, 0E8h
0x1400d4f21  mov     rax, cs:__security_cookie
0x1400d4f28  xor     rax, rsp
0x1400d4f2b  mov     [rbp+47h+var_50], rax
0x1400d4f2f  mov     r14, [rbp+47h+arg_20]
0x1400d4f33  mov     rdi, rdx
0x1400d4f36  mov     [rbp+47h+var_C0], rdx
0x1400d4f3a  mov     rsi, r8
0x1400d4f3d  xor     edx, edx; Val
0x1400d4f3f  mov     qword ptr [rbp+47h+var_B0], r8
0x1400d4f43  mov     rbx, rcx
0x1400d4f46  mov     [rsp+120h+Irp], rcx
0x1400d4f4b  lea     rcx, [rbp+47h+var_A0]; void *
0x1400d4f4f  mov     [rsp+120h+BugCheckParameter2], 0
0x1400d4f58  mov     r13d, r9d
0x1400d4f5b  lea     r8d, [rdx+50h]; Size
0x1400d4f5f  call    memset
0x1400d4f64  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d4f6b  mov     r15d, [rbp+47h+arg_28]
0x1400d4f6f  jz      short loc_1400D4FA3
0x1400d4f71  mov     [rsp+120h+var_E0], r15d
0x1400d4f76  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400d4f7d  mov     [rsp+120h+var_E8], r14
0x1400d4f82  mov     edx, 7Ch ; '|'
0x1400d4f87  mov     [rsp+120h+var_F0], r13d
0x1400d4f8c  mov     ecx, 404h
0x1400d4f91  mov     qword ptr [rsp+120h+var_F8], rsi
0x1400d4f96  mov     r9, rbx
0x1400d4f99  mov     [rsp+120h+var_100], rdi
0x1400d4f9e  call    WPP_SF_qqiLqL
0x1400d4fa3  mov     rbx, [rdi+38h]
0x1400d4fa7  call    cs:__imp_KeEnterCriticalRegion
0x1400d4fae  nop     dword ptr [rax+rax+00h]
0x1400d4fb3  mov     rcx, [rbx+558h]
0x1400d4fba  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d4fc1  nop     dword ptr [rax+rax+00h]
0x1400d4fc6  lea     r9, UlValidateConfigGroup
0x1400d4fcd  mov     [rsp+120h+var_100], rdi
0x1400d4fd2  lea     r8, UlReferenceServerSession
0x1400d4fd9  mov     edx, 2
0x1400d4fde  mov     rcx, rsi
0x1400d4fe1  call    UxGetObjectFromOpaqueId
0x1400d4fe6  mov     rsi, rax
0x1400d4fe9  test    rax, rax
0x1400d4fec  jz      loc_1400D5679
0x1400d4ff2  cmp     dword ptr [rax], 4A436C55h
0x1400d4ff8  jnz     loc_1400D5679
0x1400d4ffe  mov     rbx, [rax+30h]
0x1400d5002  mov     r12d, 1
0x1400d5008  mov     ebx, [rbx+10h]
0x1400d500b  mov     [rbp+47h+var_B8], ebx
0x1400d500e  cmp     r12w, bx
0x1400d5012  jnz     short loc_1400D502A
0x1400d5014  mov     ecx, ebx
0x1400d5016  xor     eax, eax
0x1400d5018  shr     ecx, 10h
0x1400d501b  cmp     ax, cx
0x1400d501e  jnz     short loc_1400D502A
0x1400d5020  mov     edi, 0C00000BBh
0x1400d5025  jmp     loc_1400D567E
0x1400d502a  xor     edi, edi
0x1400d502c  cmp     r13d, 9
0x1400d5030  jg      loc_1400D543A
0x1400d5036  jz      loc_1400D541F
0x1400d503c  mov     ecx, r13d
0x1400d503f  test    r13d, r13d
0x1400d5042  jz      short loc_1400D507A
0x1400d5044  sub     ecx, r12d
0x1400d5047  jz      loc_1400D5365
0x1400d504d  sub     ecx, r12d
0x1400d5050  jz      loc_1400D530E
0x1400d5056  sub     ecx, r12d
0x1400d5059  jz      loc_1400D5259
0x1400d505f  sub     ecx, 2
0x1400d5062  jz      loc_1400D522C
0x1400d5068  sub     ecx, 2
0x1400d506b  jz      loc_1400D50F4
0x1400d5071  cmp     ecx, r12d
0x1400d5074  jnz     loc_1400D5588
0x1400d507a  mov     r15, [rsp+120h+Irp]
0x1400d507f  mov     rcx, r15; Irp
0x1400d5082  call    cs:__imp_IoIs32bitProcess
0x1400d5089  nop     dword ptr [rax+rax+00h]
0x1400d508e  mov     r8b, [r14+8]
0x1400d5092  mov     r9b, [r14+9]
0x1400d5096  mov     r10b, [r14+0Ah]
0x1400d509a  mov     ebx, [r14]
0x1400d509d  mov     edx, [r14+4]
0x1400d50a1  movzx   ecx, byte ptr [r14+0Bh]
0x1400d50a6  mov     byte ptr [rbp+47h+var_98], r8b
0x1400d50aa  mov     byte ptr [rbp+47h+var_98+1], r9b
0x1400d50ae  mov     byte ptr [rbp+47h+var_98+2], r10b
0x1400d50b2  mov     dword ptr [rbp+47h+var_A0], ebx
0x1400d50b5  mov     dword ptr [rbp+47h+var_A0+4], edx
0x1400d50b8  test    al, al
0x1400d50ba  jz      loc_1400D537E
0x1400d50c0  mov     eax, [r14+18h]
0x1400d50c4  mov     [rbp+47h+var_78], rax
0x1400d50c8  movzx   eax, word ptr [r14+14h]
0x1400d50cd  mov     [rbp+47h+var_80], ax
0x1400d50d1  mov     eax, [r14+10h]
0x1400d50d5  mov     [rbp+47h+var_88], rax
0x1400d50d9  movzx   eax, word ptr [r14+0Ch]
0x1400d50de  mov     [rbp+47h+var_90], ax
0x1400d50e2  mov     eax, [r14+20h]
0x1400d50e6  mov     [rbp+47h+var_68], rax
0x1400d50ea  movzx   eax, word ptr [r14+1Ch]
0x1400d50ef  jmp     loc_1400D53AD
0x1400d50f4  mov     rcx, [rsp+120h+Irp]; Irp
0x1400d50f9  xor     r15d, r15d
0x1400d50fc  call    cs:__imp_IoIs32bitProcess
0x1400d5103  nop     dword ptr [rax+rax+00h]
0x1400d5108  mov     ecx, [r14]
0x1400d510b  mov     dword ptr [rbp+47h+var_A0], ecx
0x1400d510e  test    al, al
0x1400d5110  jz      short loc_1400D511C
0x1400d5112  mov     r10d, [r14+4]
0x1400d5116  mov     [rbp+47h+var_98], r10
0x1400d511a  jmp     short loc_1400D514A
0x1400d511c  mov     eax, [r14+4]
0x1400d5120  mov     dword ptr [rbp+47h+var_A0+4], eax
0x1400d5123  mov     al, [r14+8]
0x1400d5127  mov     byte ptr [rbp+47h+var_98], al
0x1400d512a  mov     al, [r14+9]
0x1400d512e  mov     byte ptr [rbp+47h+var_98+1], al
0x1400d5131  mov     al, [r14+0Ah]
0x1400d5135  mov     byte ptr [rbp+47h+var_98+2], al
0x1400d5138  mov     al, [r14+0Bh]
0x1400d513c  mov     byte ptr [rbp+47h+var_98+3], al
0x1400d513f  mov     eax, [r14+0Ch]
0x1400d5143  mov     dword ptr [rbp+47h+var_98+4], eax
0x1400d5146  mov     r10, [rbp+47h+var_98]
0x1400d514a  mov     edx, [rsi+40h]
0x1400d514d  test    r12b, dl
0x1400d5150  jz      short loc_1400D515D
0x1400d5152  mov     rax, [rsi+48h]
0x1400d5156  test    rax, rax
0x1400d5159  cmovnz  r15, rax
0x1400d515d  test    r12b, cl
0x1400d5160  jz      loc_1400D51E8
0x1400d5166  lea     rax, [rsp+120h+BugCheckParameter2]
0x1400d516b  mov     r9d, 7
0x1400d5171  mov     r8d, r12d
0x1400d5174  mov     [rsp+120h+var_100], rax; PVOID
0x1400d5179  mov     rcx, r10; Handle
0x1400d517c  call    UlReferenceRequestQueueByHandle
0x1400d5181  mov     edi, eax
0x1400d5183  test    eax, eax
0x1400d5185  js      loc_1400D5626
0x1400d518b  mov     rdx, [rsp+120h+BugCheckParameter2]; BugCheckParameter2
0x1400d5190  cmp     [rdx+114h], bx
0x1400d5197  jnz     short loc_1400D51B5
0x1400d5199  movzx   ecx, word ptr [rbp+47h+var_B8+2]
0x1400d519d  cmp     [rdx+116h], cx
0x1400d51a4  jnz     short loc_1400D51B5
0x1400d51a6  or      [rsi+40h], r12d
0x1400d51aa  mov     rcx, [rsp+120h+BugCheckParameter2]
0x1400d51af  mov     [rsi+48h], rcx
0x1400d51b3  jmp     short loc_1400D51F2
0x1400d51b5  or      eax, 0FFFFFFFFh
0x1400d51b8  lock xadd [rdx], eax
0x1400d51bc  dec     eax
0x1400d51be  cmp     cs:UxDebugCheckRefcount, 0
0x1400d51c5  jz      short loc_1400D51D0
0x1400d51c7  cmp     eax, 0FFFFFFFFh
0x1400d51ca  jle     loc_1400D5729
0x1400d51d0  test    eax, eax
0x1400d51d2  jnz     short loc_1400D51DE
0x1400d51d4  mov     rcx, [rsp+120h+BugCheckParameter2]; P
0x1400d51d9  call    UlFreeRequestQueue
0x1400d51de  mov     edi, 0C0000059h
0x1400d51e3  jmp     loc_1400D5626
0x1400d51e8  and     edx, 0FFFFFFFEh
0x1400d51eb  mov     [rsi+48h], rdi
0x1400d51ef  mov     [rsi+40h], edx
0x1400d51f2  test    r15, r15
0x1400d51f5  jz      loc_1400D5626
0x1400d51fb  or      eax, 0FFFFFFFFh
0x1400d51fe  lock xadd [r15], eax
0x1400d5203  dec     eax
0x1400d5205  cmp     cs:UxDebugCheckRefcount, 0
0x1400d520c  jz      short loc_1400D5217
0x1400d520e  cmp     eax, 0FFFFFFFFh
0x1400d5211  jle     loc_1400D573B
0x1400d5217  test    eax, eax
0x1400d5219  jnz     loc_1400D5626
0x1400d521f  mov     rcx, r15; P
0x1400d5222  call    UlFreeRequestQueue
0x1400d5227  jmp     loc_1400D5626
0x1400d522c  mov     rax, [r14]
0x1400d522f  mov     rcx, rax
0x1400d5232  mov     [rbp+47h+var_A0], rax
0x1400d5236  shr     rcx, 20h
0x1400d523a  cmp     ecx, r12d
0x1400d523d  ja      loc_1400D5588
0x1400d5243  cmp     [rsi+3Ch], ecx
0x1400d5246  jz      short loc_1400D5251
0x1400d5248  mov     [rsi+38h], rax
0x1400d524c  jmp     loc_1400D5626
0x1400d5251  xor     r12b, r12b
0x1400d5254  jmp     loc_1400D5626
0x1400d5259  mov     ecx, [r14+4]
0x1400d525d  mov     eax, [r14]
0x1400d5260  mov     dword ptr [rbp+47h+var_A0+4], ecx
0x1400d5263  mov     cl, [r14+8]
0x1400d5267  mov     byte ptr [rbp+47h+var_98], cl
0x1400d526a  mov     cl, [r14+9]
0x1400d526e  mov     byte ptr [rbp+47h+var_98+1], cl
0x1400d5271  mov     cl, [r14+0Ah]
0x1400d5275  mov     byte ptr [rbp+47h+var_98+2], cl
0x1400d5278  mov     cl, [r14+0Bh]
0x1400d527c  mov     byte ptr [rbp+47h+var_98+3], cl
0x1400d527f  mov     ecx, [r14+0Ch]
0x1400d5283  mov     dword ptr [rbp+47h+var_98+4], ecx
0x1400d5286  movzx   ecx, word ptr [r14+10h]
0x1400d528b  mov     [rbp+47h+var_90], cx
0x1400d528f  movzx   ecx, word ptr [r14+12h]
0x1400d5294  mov     [rbp+47h+var_8E], cx
0x1400d5298  mov     dword ptr [rbp+47h+var_A0], eax
0x1400d529b  test    r12b, al
0x1400d529e  jz      short loc_1400D52F7
0x1400d52a0  mov     [rsi+110h], eax
0x1400d52a6  mov     eax, dword ptr [rbp+47h+var_A0+4]
0x1400d52a9  mov     [rsi+114h], eax
0x1400d52af  mov     al, byte ptr [rbp+47h+var_98]
0x1400d52b2  mov     [rsi+118h], al
0x1400d52b8  mov     al, byte ptr [rbp+47h+var_98+1]
0x1400d52bb  mov     [rsi+119h], al
0x1400d52c1  mov     al, byte ptr [rbp+47h+var_98+2]
0x1400d52c4  mov     [rsi+11Ah], al
0x1400d52ca  mov     al, byte ptr [rbp+47h+var_98+3]
0x1400d52cd  mov     [rsi+11Bh], al
0x1400d52d3  mov     eax, dword ptr [rbp+47h+var_98+4]
0x1400d52d6  mov     [rsi+11Ch], eax
0x1400d52dc  movzx   eax, [rbp+47h+var_90]
0x1400d52e0  mov     [rsi+120h], ax
0x1400d52e7  movzx   eax, [rbp+47h+var_8E]
0x1400d52eb  mov     [rsi+122h], ax
0x1400d52f2  jmp     loc_1400D5626
0x1400d52f7  xorps   xmm0, xmm0
0x1400d52fa  xor     eax, eax
0x1400d52fc  movups  xmmword ptr [rsi+110h], xmm0
0x1400d5303  mov     [rsi+120h], eax
0x1400d5309  jmp     loc_1400D5626
0x1400d530e  mov     rcx, [rsp+120h+Irp]; Irp
0x1400d5313  lea     r9, [rbp+47h+var_A0]
0x1400d5317  mov     r8d, r15d
0x1400d531a  mov     rdx, r14
0x1400d531d  call    UlCaptureQosParameter
0x1400d5322  mov     edi, eax
0x1400d5324  test    eax, eax
0x1400d5326  js      loc_1400D5684
0x1400d532c  mov     eax, dword ptr [rbp+47h+var_A0]
0x1400d532f  test    eax, eax
0x1400d5331  jnz     short loc_1400D5345
0x1400d5333  lea     rcx, [rsi+50h]
0x1400d5337  lea     rdx, [rbp+47h+var_A0+4]
0x1400d533b  call    UlQosConfigureFlowCharacteristics
0x1400d5340  jmp     loc_1400D5624
0x1400d5345  cmp     eax, r12d
0x1400d5348  jnz     short loc_1400D535B
0x1400d534a  lea     rdx, [rbp+47h+var_A0+4]
0x1400d534e  mov     rcx, rsi
0x1400d5351  call    UlSetConnectionsProperty
0x1400d5356  jmp     loc_1400D5624
0x1400d535b  mov     edi, 0C000000Dh
0x1400d5360  jmp     loc_1400D5684
0x1400d5365  mov     r9, [rsp+120h+Irp]
0x1400d536a  lea     rcx, [rsi+78h]
0x1400d536e  mov     r8, r14
0x1400d5371  mov     rdx, rsi
0x1400d5374  call    UlConfigLogging
0x1400d5379  jmp     loc_1400D5624
0x1400d537e  mov     rax, [r14+28h]
0x1400d5382  mov     [rbp+47h+var_78], rax
0x1400d5386  movzx   eax, word ptr [r14+20h]
0x1400d538b  mov     [rbp+47h+var_80], ax
0x1400d538f  mov     rax, [r14+18h]
0x1400d5393  mov     [rbp+47h+var_88], rax
0x1400d5397  movzx   eax, word ptr [r14+10h]
0x1400d539c  mov     [rbp+47h+var_90], ax
0x1400d53a0  mov     rax, [r14+38h]
0x1400d53a4  mov     [rbp+47h+var_68], rax
0x1400d53a8  movzx   eax, word ptr [r14+30h]
0x1400d53ad  mov     [rbp+47h+var_70], ax
0x1400d53b1  lea     rdx, [rbp+47h+var_A0]
0x1400d53b5  xor     eax, eax
0x1400d53b7  xorps   xmm0, xmm0
0x1400d53ba  cmp     r13d, 8
0x1400d53be  movdqa  [rbp+47h+var_60], xmm0
0x1400d53c3  cmovnz  ecx, eax
  ... truncated ...
```
