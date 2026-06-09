# UlSetConfigGroupProperty

- ea: `0x1400d4fe8`
- end: `0x1400d5813`
- name: `UlSetConfigGroupProperty`
- size: `2091`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config`

## callers

- `0x1400f3390`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x140061df8`
- `0x140074488`
- `0x140074af8`
- `0x140086910`
- `0x1400869e0`
- `0x14009622c`
- `0x1400a1f70`
- `0x1400a94f8`
- `0x1400d4fe8`
- `0x1400d6428`
- `0x1400d7ffc`
- `0x1400e7f4c`
- `0x1400eeb64`
- `0x1400fd210`
- `0x140142d04`
- `0x140146b48`
- `0x140167700`
- `0x140167b40`
- `0x1401c8dac`
- `0x1401c8e0c`
- `0x1401c9510`
- `0x1401d9e44`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400d5162`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d51dc`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d5162`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d51dc`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d57b6`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d57b6`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d509a`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d509a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d57c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d57c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d5087`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d5087`

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
  unsigned int v44; // [rsp+60h] [rbp-79h]
  __int64 v45; // [rsp+68h] [rbp-71h]
  int v46[4]; // [rsp+70h] [rbp-69h]
  _OWORD v47[5]; // [rsp+80h] [rbp-59h] BYREF

  v45 = a2;
  *(_QWORD *)v46 = a3;
  BugCheckParameter2 = 0;
  memset(v47, 0, sizeof(v47));
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqiLqL(1028, 124, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, a1, a2, a3, a4, a5, a6);
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
    goto LABEL_95;
  }
  v16 = 1;
  v17 = *(_DWORD *)(*(_QWORD *)(ObjectFromOpaqueId + 48) + 16LL);
  v44 = v17;
  if ( (_WORD)v17 == 1 )
  {
    LODWORD(v13) = HIWORD(v17);
    if ( !HIWORD(v17) )
    {
      v18 = -1073741637;
      goto LABEL_95;
    }
  }
  v18 = 0;
  if ( a4 > 9 )
  {
    switch ( a4 )
    {
      case 10:
        started = UlCaptureChannelBindConfig(
                    *(_QWORD *)(v45 + 56),
                    (int)a5,
                    0,
                    (int)ObjectFromOpaqueId + 384,
                    a1,
                    a1->RequestorMode);
        goto LABEL_88;
      case 11:
        *(_QWORD *)&v47[0] = *(_QWORD *)a5;
        started = UlpNotifyEdgePolicyChange(ObjectFromOpaqueId, v47);
        goto LABEL_88;
      case 12:
        *(_QWORD *)&v47[0] = *(_QWORD *)a5;
        started = UlScStartCounters(ObjectFromOpaqueId, v47);
        goto LABEL_88;
      case 15:
        *(_QWORD *)&v47[0] = *(_QWORD *)a5;
        v13 = HIDWORD(*(_QWORD *)&v47[0]);
        if ( BYTE4(v47[0]) >= 2u )
          goto LABEL_81;
        *(_QWORD *)(ObjectFromOpaqueId + 448) = *(_QWORD *)&v47[0];
        if ( (xmmword_1401A2CA0 & 0x10) == 0 )
          goto LABEL_89;
        v39 = 125;
        break;
      default:
        LODWORD(v13) = a4 - 16;
        if ( a4 == 16 )
          goto LABEL_46;
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
            goto LABEL_89;
          }
          goto LABEL_81;
        }
        *(_QWORD *)&v47[0] = *(_QWORD *)a5;
        v13 = HIDWORD(*(_QWORD *)&v47[0]);
        if ( BYTE4(v47[0]) >= 2u )
        {
LABEL_81:
          v18 = -1073741811;
          goto LABEL_89;
        }
        *(_QWORD *)(ObjectFromOpaqueId + 456) = *(_QWORD *)&v47[0];
        if ( (xmmword_1401A2CA0 & 0x10) == 0 )
          goto LABEL_89;
        v39 = 126;
        break;
    }
    WPP_SF_ill(BYTE4(v47[0]), v39, v14, *(_QWORD *)(ObjectFromOpaqueId + 8), v47[0] & 1, BYTE4(v47[0]));
    goto LABEL_89;
  }
  switch ( a4 )
  {
    case 9:
      v36 = *(_QWORD *)a5;
      *(_QWORD *)&v47[0] = *(_QWORD *)a5;
      if ( (v47[0] & 1) == 0 )
        v36 = 0;
      *(_QWORD *)(v15 + 292) = v36;
      goto LABEL_89;
    case 0:
      goto LABEL_17;
    case 1:
      started = UlConfigLogging(ObjectFromOpaqueId + 120, ObjectFromOpaqueId, a5, a1);
      goto LABEL_88;
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
      goto LABEL_89;
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
            goto LABEL_89;
          v30 = BugCheckParameter2;
          if ( *(_WORD *)(BugCheckParameter2 + 276) != (_WORD)v17
            || (LODWORD(v13) = HIWORD(v44), *(_WORD *)(BugCheckParameter2 + 278) != HIWORD(v44)) )
          {
            v31 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2);
            if ( UxDebugCheckRefcount && v31 <= -1 )
              UlBugCheckEx(3u, v30, 0xAu, v31);
            if ( !v31 )
              UlFreeRequestQueue((PVOID)BugCheckParameter2);
            v18 = -1073741735;
            goto LABEL_89;
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
        goto LABEL_89;
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
        v35 = *(_QWORD *)(v45 + 56);
        v18 = UlVerifyAuthConfig(v35, v47);
        if ( v18 < 0 )
          goto LABEL_89;
        if ( (v22 & 1) != 0 )
        {
          started = UlCopyAuthConfig(v35, (int)v15 + 304, (unsigned int)v47, 0, 0, a1->RequestorMode);
          goto LABEL_88;
        }
        UlFreeAuthConfig(v15 + 304, 0);
LABEL_89:
        UlEventSetConfigGroupProperty(v13, v46[0], a4, v18, a1);
        if ( (xmmword_1401A2CA0 & 0x10) != 0 )
          WPP_SF_Dd(1028, 128, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)v18, a4);
        if ( v18 >= 0 && v16 )
          UlFlushCacheByConfigGroup(v15);
LABEL_95:
        if ( a4 != 2 )
          goto LABEL_97;
        goto LABEL_96;
      }
      goto LABEL_81;
    }
    *(_QWORD *)&v47[0] = *(_QWORD *)a5;
    v13 = HIDWORD(*(_QWORD *)&v47[0]);
    if ( DWORD1(v47[0]) > 1 )
      goto LABEL_81;
    if ( *(_DWORD *)(ObjectFromOpaqueId + 60) != DWORD1(v47[0]) )
    {
      *(_QWORD *)(ObjectFromOpaqueId + 56) = *(_QWORD *)&v47[0];
      goto LABEL_89;
    }
LABEL_46:
    v16 = 0;
    goto LABEL_89;
  }
  v18 = UlCaptureQosParameter(a1);
  if ( v18 >= 0 )
  {
    if ( !LODWORD(v47[0]) )
    {
      started = UlQosConfigureFlowCharacteristics(v15 + 80, (char *)v47 + 4);
LABEL_88:
      v18 = started;
      goto LABEL_89;
    }
    if ( LODWORD(v47[0]) == 1 )
    {
      started = UlSetConnectionsProperty(v15, (char *)v47 + 4);
      goto LABEL_88;
    }
    v18 = -1073741811;
  }
LABEL_96:
  *(_QWORD *)&v47[0] = 0;
  DWORD2(v47[0]) = 0;
LABEL_97:
  if ( v15 )
  {
    v40 = _InterlockedDecrement((volatile signed __int32 *)(v15 + 4));
    if ( UxDebugCheckRefcount && v40 <= -1 )
      UlBugCheckEx(3u, v15 + 4, 0xBu, v40);
    if ( !v40 )
      UlFreeConfigGroup((PVOID)v15);
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(v45 + 56) + 1368LL));
  KeLeaveCriticalRegion();
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 129, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)v18);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400d4fe8  push    rbp
0x1400d4fea  push    rbx
0x1400d4feb  push    rsi
0x1400d4fec  push    rdi
0x1400d4fed  push    r12
0x1400d4fef  push    r13
0x1400d4ff1  push    r14
0x1400d4ff3  push    r15
0x1400d4ff5  lea     rbp, [rsp-0Fh]
0x1400d4ffa  sub     rsp, 0E8h
0x1400d5001  mov     rax, cs:__security_cookie
0x1400d5008  xor     rax, rsp
0x1400d500b  mov     [rbp+47h+var_50], rax
0x1400d500f  mov     r14, [rbp+47h+arg_20]
0x1400d5013  mov     rdi, rdx
0x1400d5016  mov     [rbp+47h+var_B8], rdx
0x1400d501a  mov     rsi, r8
0x1400d501d  xor     edx, edx; Val
0x1400d501f  mov     qword ptr [rbp+47h+var_B0], r8
0x1400d5023  mov     rbx, rcx
0x1400d5026  mov     [rsp+120h+Irp], rcx
0x1400d502b  lea     rcx, [rbp+47h+var_A0]; void *
0x1400d502f  mov     [rsp+120h+BugCheckParameter2], 0
0x1400d5038  mov     r13d, r9d
0x1400d503b  lea     r8d, [rdx+50h]; Size
0x1400d503f  call    memset
0x1400d5044  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d504b  mov     r15d, [rbp+47h+arg_28]
0x1400d504f  jz      short loc_1400D5083
0x1400d5051  mov     [rsp+120h+var_E0], r15d
0x1400d5056  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400d505d  mov     [rsp+120h+var_E8], r14
0x1400d5062  mov     edx, 7Ch ; '|'
0x1400d5067  mov     [rsp+120h+var_F0], r13d
0x1400d506c  mov     ecx, 404h
0x1400d5071  mov     qword ptr [rsp+120h+var_F8], rsi
0x1400d5076  mov     r9, rbx
0x1400d5079  mov     [rsp+120h+var_100], rdi
0x1400d507e  call    WPP_SF_qqiLqL
0x1400d5083  mov     rbx, [rdi+38h]
0x1400d5087  call    cs:__imp_KeEnterCriticalRegion
0x1400d508e  nop     dword ptr [rax+rax+00h]
0x1400d5093  mov     rcx, [rbx+558h]
0x1400d509a  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d50a1  nop     dword ptr [rax+rax+00h]
0x1400d50a6  lea     r9, UlValidateConfigGroup
0x1400d50ad  mov     [rsp+120h+var_100], rdi
0x1400d50b2  lea     r8, UlReferenceServerSession
0x1400d50b9  mov     edx, 2
0x1400d50be  mov     rcx, rsi
0x1400d50c1  call    UxGetObjectFromOpaqueId
0x1400d50c6  mov     rsi, rax
0x1400d50c9  test    rax, rax
0x1400d50cc  jz      loc_1400D5755
0x1400d50d2  cmp     dword ptr [rax], 4A436C55h
0x1400d50d8  jnz     loc_1400D5755
0x1400d50de  mov     rbx, [rax+30h]
0x1400d50e2  mov     r12d, 1
0x1400d50e8  mov     ebx, [rbx+10h]
0x1400d50eb  mov     [rbp+47h+var_C0], ebx
0x1400d50ee  cmp     r12w, bx
0x1400d50f2  jnz     short loc_1400D510A
0x1400d50f4  mov     ecx, ebx
0x1400d50f6  xor     eax, eax
0x1400d50f8  shr     ecx, 10h
0x1400d50fb  cmp     ax, cx
0x1400d50fe  jnz     short loc_1400D510A
0x1400d5100  mov     edi, 0C00000BBh
0x1400d5105  jmp     loc_1400D575A
0x1400d510a  xor     edi, edi
0x1400d510c  cmp     r13d, 9
0x1400d5110  jg      loc_1400D553A
0x1400d5116  jz      loc_1400D551F
0x1400d511c  mov     ecx, r13d
0x1400d511f  test    r13d, r13d
0x1400d5122  jz      short loc_1400D515A
0x1400d5124  sub     ecx, r12d
0x1400d5127  jz      loc_1400D5465
0x1400d512d  sub     ecx, r12d
0x1400d5130  jz      loc_1400D540E
0x1400d5136  sub     ecx, r12d
0x1400d5139  jz      loc_1400D5359
0x1400d513f  sub     ecx, 2
0x1400d5142  jz      loc_1400D532C
0x1400d5148  sub     ecx, 2
0x1400d514b  jz      loc_1400D51D4
0x1400d5151  cmp     ecx, r12d
0x1400d5154  jnz     loc_1400D5664
0x1400d515a  mov     r15, [rsp+120h+Irp]
0x1400d515f  mov     rcx, r15; Irp
0x1400d5162  call    cs:__imp_IoIs32bitProcess
0x1400d5169  nop     dword ptr [rax+rax+00h]
0x1400d516e  mov     r8b, [r14+8]
0x1400d5172  mov     r9b, [r14+9]
0x1400d5176  mov     r10b, [r14+0Ah]
0x1400d517a  mov     ebx, [r14]
0x1400d517d  mov     edx, [r14+4]
0x1400d5181  movzx   ecx, byte ptr [r14+0Bh]
0x1400d5186  mov     byte ptr [rbp+47h+var_98], r8b
0x1400d518a  mov     byte ptr [rbp+47h+var_98+1], r9b
0x1400d518e  mov     byte ptr [rbp+47h+var_98+2], r10b
0x1400d5192  mov     dword ptr [rbp+47h+var_A0], ebx
0x1400d5195  mov     dword ptr [rbp+47h+var_A0+4], edx
0x1400d5198  test    al, al
0x1400d519a  jz      loc_1400D547E
0x1400d51a0  mov     eax, [r14+18h]
0x1400d51a4  mov     [rbp+47h+var_78], rax
0x1400d51a8  movzx   eax, word ptr [r14+14h]
0x1400d51ad  mov     [rbp+47h+var_80], ax
0x1400d51b1  mov     eax, [r14+10h]
0x1400d51b5  mov     [rbp+47h+var_88], rax
0x1400d51b9  movzx   eax, word ptr [r14+0Ch]
0x1400d51be  mov     [rbp+47h+var_90], ax
0x1400d51c2  mov     eax, [r14+20h]
0x1400d51c6  mov     [rbp+47h+var_68], rax
0x1400d51ca  movzx   eax, word ptr [r14+1Ch]
0x1400d51cf  jmp     loc_1400D54AD
0x1400d51d4  mov     rcx, [rsp+120h+Irp]; Irp
0x1400d51d9  xor     r15d, r15d
0x1400d51dc  call    cs:__imp_IoIs32bitProcess
0x1400d51e3  nop     dword ptr [rax+rax+00h]
0x1400d51e8  mov     ecx, [r14]
0x1400d51eb  mov     dword ptr [rbp+47h+var_A0], ecx
0x1400d51ee  test    al, al
0x1400d51f0  jz      short loc_1400D51FC
0x1400d51f2  mov     r10d, [r14+4]
0x1400d51f6  mov     [rbp+47h+var_98], r10
0x1400d51fa  jmp     short loc_1400D522A
0x1400d51fc  mov     eax, [r14+4]
0x1400d5200  mov     dword ptr [rbp+47h+var_A0+4], eax
0x1400d5203  mov     al, [r14+8]
0x1400d5207  mov     byte ptr [rbp+47h+var_98], al
0x1400d520a  mov     al, [r14+9]
0x1400d520e  mov     byte ptr [rbp+47h+var_98+1], al
0x1400d5211  mov     al, [r14+0Ah]
0x1400d5215  mov     byte ptr [rbp+47h+var_98+2], al
0x1400d5218  mov     al, [r14+0Bh]
0x1400d521c  mov     byte ptr [rbp+47h+var_98+3], al
0x1400d521f  mov     eax, [r14+0Ch]
0x1400d5223  mov     dword ptr [rbp+47h+var_98+4], eax
0x1400d5226  mov     r10, [rbp+47h+var_98]
0x1400d522a  mov     edx, [rsi+40h]
0x1400d522d  test    r12b, dl
0x1400d5230  jz      short loc_1400D523D
0x1400d5232  mov     rax, [rsi+48h]
0x1400d5236  test    rax, rax
0x1400d5239  cmovnz  r15, rax
0x1400d523d  test    r12b, cl
0x1400d5240  jz      loc_1400D52D6
0x1400d5246  lea     rax, [rsp+120h+BugCheckParameter2]
0x1400d524b  mov     r9d, 7
0x1400d5251  mov     r8d, r12d
0x1400d5254  mov     [rsp+120h+var_100], rax; PVOID
0x1400d5259  mov     rcx, r10; Handle
0x1400d525c  call    UlReferenceRequestQueueByHandle
0x1400d5261  mov     edi, eax
0x1400d5263  test    eax, eax
0x1400d5265  js      loc_1400D5702
0x1400d526b  mov     rdx, [rsp+120h+BugCheckParameter2]; BugCheckParameter2
0x1400d5270  cmp     [rdx+114h], bx
0x1400d5277  jnz     short loc_1400D5295
0x1400d5279  movzx   ecx, word ptr [rbp+47h+var_C0+2]
0x1400d527d  cmp     [rdx+116h], cx
0x1400d5284  jnz     short loc_1400D5295
0x1400d5286  or      [rsi+40h], r12d
0x1400d528a  mov     rcx, [rsp+120h+BugCheckParameter2]
0x1400d528f  mov     [rsi+48h], rcx
0x1400d5293  jmp     short loc_1400D52E0
0x1400d5295  or      eax, 0FFFFFFFFh
0x1400d5298  lock xadd [rdx], eax
0x1400d529c  dec     eax
0x1400d529e  cmp     cs:UxDebugCheckRefcount, 0
0x1400d52a5  jz      short loc_1400D52BE
0x1400d52a7  cmp     eax, 0FFFFFFFFh
0x1400d52aa  jg      short loc_1400D52BE
0x1400d52ac  mov     ecx, 3; BugCheckParameter1
0x1400d52b1  movsxd  r9, eax; BugCheckParameter4
0x1400d52b4  lea     r8d, [rcx+7]; BugCheckParameter3
0x1400d52b8  call    UlBugCheckEx
0x1400d52be  test    eax, eax
0x1400d52c0  jnz     short loc_1400D52CC
0x1400d52c2  mov     rcx, [rsp+120h+BugCheckParameter2]; P
0x1400d52c7  call    UlFreeRequestQueue
0x1400d52cc  mov     edi, 0C0000059h
0x1400d52d1  jmp     loc_1400D5702
0x1400d52d6  and     edx, 0FFFFFFFEh
0x1400d52d9  mov     [rsi+48h], rdi
0x1400d52dd  mov     [rsi+40h], edx
0x1400d52e0  test    r15, r15
0x1400d52e3  jz      loc_1400D5702
0x1400d52e9  or      eax, 0FFFFFFFFh
0x1400d52ec  lock xadd [r15], eax
0x1400d52f1  dec     eax
0x1400d52f3  cmp     cs:UxDebugCheckRefcount, 0
0x1400d52fa  jz      short loc_1400D5317
0x1400d52fc  cmp     eax, 0FFFFFFFFh
0x1400d52ff  jg      short loc_1400D5317
0x1400d5301  mov     r8d, 0Ah; BugCheckParameter3
0x1400d5307  movsxd  r9, eax; BugCheckParameter4
0x1400d530a  mov     rdx, r15; BugCheckParameter2
0x1400d530d  lea     ecx, [r8-7]; BugCheckParameter1
0x1400d5311  call    UlBugCheckEx
0x1400d5317  test    eax, eax
0x1400d5319  jnz     loc_1400D5702
0x1400d531f  mov     rcx, r15; P
0x1400d5322  call    UlFreeRequestQueue
0x1400d5327  jmp     loc_1400D5702
0x1400d532c  mov     rax, [r14]
0x1400d532f  mov     rcx, rax
0x1400d5332  mov     [rbp+47h+var_A0], rax
0x1400d5336  shr     rcx, 20h
0x1400d533a  cmp     ecx, r12d
0x1400d533d  ja      loc_1400D5664
0x1400d5343  cmp     [rsi+3Ch], ecx
0x1400d5346  jz      short loc_1400D5351
0x1400d5348  mov     [rsi+38h], rax
0x1400d534c  jmp     loc_1400D5702
0x1400d5351  xor     r12b, r12b
0x1400d5354  jmp     loc_1400D5702
0x1400d5359  mov     ecx, [r14+4]
0x1400d535d  mov     eax, [r14]
0x1400d5360  mov     dword ptr [rbp+47h+var_A0+4], ecx
0x1400d5363  mov     cl, [r14+8]
0x1400d5367  mov     byte ptr [rbp+47h+var_98], cl
0x1400d536a  mov     cl, [r14+9]
0x1400d536e  mov     byte ptr [rbp+47h+var_98+1], cl
0x1400d5371  mov     cl, [r14+0Ah]
0x1400d5375  mov     byte ptr [rbp+47h+var_98+2], cl
0x1400d5378  mov     cl, [r14+0Bh]
0x1400d537c  mov     byte ptr [rbp+47h+var_98+3], cl
0x1400d537f  mov     ecx, [r14+0Ch]
0x1400d5383  mov     dword ptr [rbp+47h+var_98+4], ecx
0x1400d5386  movzx   ecx, word ptr [r14+10h]
0x1400d538b  mov     [rbp+47h+var_90], cx
0x1400d538f  movzx   ecx, word ptr [r14+12h]
0x1400d5394  mov     [rbp+47h+var_8E], cx
0x1400d5398  mov     dword ptr [rbp+47h+var_A0], eax
0x1400d539b  test    r12b, al
0x1400d539e  jz      short loc_1400D53F7
0x1400d53a0  mov     [rsi+110h], eax
0x1400d53a6  mov     eax, dword ptr [rbp+47h+var_A0+4]
0x1400d53a9  mov     [rsi+114h], eax
0x1400d53af  mov     al, byte ptr [rbp+47h+var_98]
0x1400d53b2  mov     [rsi+118h], al
0x1400d53b8  mov     al, byte ptr [rbp+47h+var_98+1]
0x1400d53bb  mov     [rsi+119h], al
0x1400d53c1  mov     al, byte ptr [rbp+47h+var_98+2]
0x1400d53c4  mov     [rsi+11Ah], al
0x1400d53ca  mov     al, byte ptr [rbp+47h+var_98+3]
0x1400d53cd  mov     [rsi+11Bh], al
0x1400d53d3  mov     eax, dword ptr [rbp+47h+var_98+4]
0x1400d53d6  mov     [rsi+11Ch], eax
0x1400d53dc  movzx   eax, [rbp+47h+var_90]
0x1400d53e0  mov     [rsi+120h], ax
0x1400d53e7  movzx   eax, [rbp+47h+var_8E]
0x1400d53eb  mov     [rsi+122h], ax
0x1400d53f2  jmp     loc_1400D5702
0x1400d53f7  xorps   xmm0, xmm0
0x1400d53fa  xor     eax, eax
0x1400d53fc  movups  xmmword ptr [rsi+110h], xmm0
0x1400d5403  mov     [rsi+120h], eax
0x1400d5409  jmp     loc_1400D5702
0x1400d540e  mov     rcx, [rsp+120h+Irp]; Irp
0x1400d5413  lea     r9, [rbp+47h+var_A0]
0x1400d5417  mov     r8d, r15d
0x1400d541a  mov     rdx, r14
0x1400d541d  call    UlCaptureQosParameter
0x1400d5422  mov     edi, eax
0x1400d5424  test    eax, eax
0x1400d5426  js      loc_1400D5760
0x1400d542c  mov     eax, dword ptr [rbp+47h+var_A0]
0x1400d542f  test    eax, eax
0x1400d5431  jnz     short loc_1400D5445
0x1400d5433  lea     rcx, [rsi+50h]
0x1400d5437  lea     rdx, [rbp+47h+var_A0+4]
0x1400d543b  call    UlQosConfigureFlowCharacteristics
0x1400d5440  jmp     loc_1400D5700
0x1400d5445  cmp     eax, r12d
0x1400d5448  jnz     short loc_1400D545B
0x1400d544a  lea     rdx, [rbp+47h+var_A0+4]
0x1400d544e  mov     rcx, rsi
0x1400d5451  call    UlSetConnectionsProperty
0x1400d5456  jmp     loc_1400D5700
0x1400d545b  mov     edi, 0C000000Dh
0x1400d5460  jmp     loc_1400D5760
0x1400d5465  mov     r9, [rsp+120h+Irp]
0x1400d546a  lea     rcx, [rsi+78h]
0x1400d546e  mov     r8, r14
0x1400d5471  mov     rdx, rsi
0x1400d5474  call    UlConfigLogging
0x1400d5479  jmp     loc_1400D5700
0x1400d547e  mov     rax, [r14+28h]
0x1400d5482  mov     [rbp+47h+var_78], rax
0x1400d5486  movzx   eax, word ptr [r14+20h]
0x1400d548b  mov     [rbp+47h+var_80], ax
0x1400d548f  mov     rax, [r14+18h]
0x1400d5493  mov     [rbp+47h+var_88], rax
0x1400d5497  movzx   eax, word ptr [r14+10h]
0x1400d549c  mov     [rbp+47h+var_90], ax
0x1400d54a0  mov     rax, [r14+38h]
  ... truncated ...
```
