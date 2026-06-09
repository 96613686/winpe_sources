# UlConfigLogging

- ea: `0x1400fd240`
- end: `0x1400fdc83`
- name: `UlConfigLogging`
- size: `2627`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d4f08`
- `0x1400d7828`

## callees

- `0x1400172ac`
- `0x140017370`
- `0x1400176a0`
- `0x14006293c`
- `0x1400fbec8`
- `0x1400fc000`
- `0x1400fd240`
- `0x1400feb08`
- `0x1400ffd7c`
- `0x1400fffec`
- `0x14010015c`
- `0x140100548`
- `0x140101878`
- `0x140101f5c`
- `0x140167810`
- `0x140167c40`
- `0x1401c49c4`
- `0x1401cec8c`
- `0x1401cf17c`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x1400fd544`
- `ntoskrnl!IoGetRequestorProcess` at `0x1400fd544`
- `ntoskrnl!SeCreateClientSecurity` at `0x1400fd64e`
- `ntoskrnl!SeCreateClientSecurity` at `0x1400fd64e`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400fdc06`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400fdc06`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400fdc37`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400fdc37`
- `ntoskrnl!IoIs32bitProcess` at `0x1400fd334`
- `ntoskrnl!IoIs32bitProcess` at `0x1400fd334`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fda16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fdaf4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fda16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fdaf4`
- `ntoskrnl!ExAllocatePool3` at `0x1400fd5d9`
- `ntoskrnl!ExAllocatePool3` at `0x1400fd5d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fdc17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fdc17`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400fda0a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400fdae8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400fda0a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400fdae8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400fd964`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400fd964`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fd94c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fd94c`

## pseudocode

```c
__int64 __fastcall UlConfigLogging(__int64 a1, __int64 a2, int *a3, IRP *a4)
{
  int LoggingConfig; // ebx
  struct _SECURITY_CLIENT_CONTEXT *v8; // r12
  __int64 Current; // r13
  BOOLEAN v10; // al
  __int64 v11; // r8
  int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // rax
  KPROCESSOR_MODE RequestorMode; // si
  const wchar_t *v16; // rsi
  IRP *v17; // r14
  PETHREAD Thread; // rbx
  PEPROCESS RequestorProcess; // rax
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  struct _SECURITY_CLIENT_CONTEXT *Pool3; // rax
  unsigned __int16 v24; // ax
  __int64 v25; // rcx
  _OWORD *v26; // r14
  const wchar_t *v27; // r8
  const wchar_t *v28; // rdx
  int v29; // r9d
  char v30; // r14
  const wchar_t *v31; // rdx
  char v32; // si
  int v34; // [rsp+20h] [rbp-188h]
  __int64 v35; // [rsp+30h] [rbp-178h]
  ULONG v36; // [rsp+5Ch] [rbp-14Ch] BYREF
  IRP *v37; // [rsp+60h] [rbp-148h]
  int v38; // [rsp+68h] [rbp-140h]
  _OWORD v39[7]; // [rsp+70h] [rbp-138h] BYREF
  int v40; // [rsp+E0h] [rbp-C8h]
  __int128 v41; // [rsp+E8h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+F8h] [rbp-B0h]
  struct _SECURITY_CLIENT_CONTEXT *v43; // [rsp+100h] [rbp-A8h]
  PSECURITY_DESCRIPTOR v44; // [rsp+108h] [rbp-A0h] BYREF
  __int128 v45; // [rsp+110h] [rbp-98h] BYREF
  __int64 v46; // [rsp+120h] [rbp-88h]
  __int64 v47; // [rsp+128h] [rbp-80h]
  __int64 v48; // [rsp+130h] [rbp-78h]
  IRP *v49; // [rsp+138h] [rbp-70h]
  __int64 v50; // [rsp+140h] [rbp-68h]
  __int64 v51; // [rsp+148h] [rbp-60h]
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+150h] [rbp-58h] BYREF

  v37 = a4;
  v50 = a2;
  v48 = a1;
  v51 = a2;
  v49 = a4;
  LoggingConfig = 0;
  v41 = 0;
  v42 = 0;
  memset(v39, 0, sizeof(v39));
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v8 = 0;
  v43 = 0;
  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  LOWORD(v36) = 0;
  Current = UxPodGetCurrent();
  v47 = Current;
  v38 = *(_DWORD *)a1 & 1;
  v40 = v38;
  memset(v39, 0, sizeof(v39));
  v10 = IoIs32bitProcess(a4);
  v12 = *a3;
  v13 = (unsigned int)a3[1];
  LODWORD(v39[0]) = *a3;
  DWORD1(v39[0]) = v13;
  if ( v10 )
  {
    LOWORD(v36) = *((_WORD *)a3 + 6);
    WORD4(v39[0]) = v36;
    WORD5(v39[0]) = v36;
    *(_QWORD *)&v39[1] = (unsigned int)a3[2];
    LOWORD(v36) = *((_WORD *)a3 + 7);
    LOWORD(v39[2]) = v36;
    WORD1(v39[2]) = v36;
    *((_QWORD *)&v39[2] + 1) = (unsigned int)a3[4];
    *((_QWORD *)&v39[3] + 1) = *(_QWORD *)(a3 + 5);
    *(_QWORD *)&v39[4] = (unsigned int)a3[7];
    *((_QWORD *)&v39[4] + 1) = *((_QWORD *)a3 + 4);
    LODWORD(v39[5]) = a3[10];
    v14 = (unsigned int)a3[11];
  }
  else
  {
    LOWORD(v36) = *((_WORD *)a3 + 8);
    WORD4(v39[0]) = v36;
    WORD5(v39[0]) = v36;
    *(_QWORD *)&v39[1] = *((_QWORD *)a3 + 1);
    LOWORD(v36) = *((_WORD *)a3 + 9);
    LOWORD(v39[2]) = v36;
    WORD1(v39[2]) = v36;
    *((_QWORD *)&v39[2] + 1) = *((_QWORD *)a3 + 3);
    *((_QWORD *)&v39[3] + 1) = *((_QWORD *)a3 + 4);
    v39[4] = *(_OWORD *)(a3 + 10);
    LODWORD(v39[5]) = a3[14];
    v14 = *((_QWORD *)a3 + 8);
  }
  *((_QWORD *)&v39[5] + 1) = v14;
  RequestorMode = a4->RequestorMode;
  BYTE8(v39[6]) = RequestorMode;
  if ( (v39[0] & 1) != 0 )
  {
    LoggingConfig = UlpVerifyLoggingInfo(v39);
    if ( LoggingConfig < 0 )
    {
      v16 = &word_140185488;
      v17 = v37;
      LOBYTE(v12) = 0;
      goto LABEL_62;
    }
    if ( (_BYTE)v38 )
    {
      if ( DWORD2(v39[3]) && DWORD2(v39[3]) != 3 )
      {
        LoggingConfig = -1073741637;
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
    }
    else if ( DWORD2(v39[3]) == 3 )
    {
      LoggingConfig = -1073741637;
      v16 = &word_140185488;
      v17 = v37;
      LOBYTE(v12) = 0;
      goto LABEL_62;
    }
    Thread = a4->Tail.Overlay.Thread;
    RequestorProcess = IoGetRequestorProcess(a4);
    LOBYTE(v20) = RequestorMode;
    v22 = UlThreadAdminCheck(v21, Thread, RequestorProcess, v20);
    LoggingConfig = v22;
    if ( (BYTE4(v39[0]) & 0x10) != 0 )
    {
      if ( v22 < 0 )
      {
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      if ( *((_QWORD *)&v39[5] + 1) )
      {
        LoggingConfig = -1073741811;
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
    }
    else if ( v22 < 0 )
    {
      Pool3 = (struct _SECURITY_CLIENT_CONTEXT *)ExAllocatePool3(66, 72, 1396927573, UxLowPriorityPool, 1);
      v8 = Pool3;
      v43 = Pool3;
      if ( !Pool3 )
      {
        LoggingConfig = -1073741670;
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      ClientSecurityQos.Length = 12;
      ClientSecurityQos.ImpersonationLevel = SecurityDelegation;
      *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 1;
      LoggingConfig = SeCreateClientSecurity(KeGetCurrentThread(), &ClientSecurityQos, 0, Pool3);
      if ( LoggingConfig < 0 )
      {
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      *(_QWORD *)&v39[6] = v8;
    }
    v12 = DWORD2(v39[5]);
    if ( *((_QWORD *)&v39[5] + 1) )
    {
      LOBYTE(v13) = a4->RequestorMode;
      LoggingConfig = UlpCaptureSecurityDescriptor(*((__int64 *)&v39[5] + 1), v13, &v44, &v36);
      if ( LoggingConfig < 0 )
      {
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      *((_QWORD *)&v39[5] + 1) = v44;
    }
    if ( DWORD2(v39[3]) != 4 )
    {
      v24 = WORD4(v39[0]);
      if ( !WORD4(v39[0]) || DWORD2(v39[3]) )
      {
        *((_QWORD *)&v39[0] + 1) = 0;
        *(_QWORD *)&v39[1] = 0;
        v24 = 0;
      }
      if ( v24 > 0x208u )
      {
        LoggingConfig = -1073741811;
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      LOBYTE(v13) = a4->RequestorMode;
      LoggingConfig = UxCaptureUnicodeString((char *)v39 + 8, v13, &v45);
      if ( LoggingConfig < 0 )
      {
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      if ( LOWORD(v39[2]) > 0x208u )
      {
        LoggingConfig = -1073741811;
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      LOBYTE(v13) = a4->RequestorMode;
      LoggingConfig = UxCaptureUnicodeString(&v39[2], v13, &v41);
      if ( LoggingConfig < 0 )
      {
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      if ( !(_WORD)v41 )
      {
        LoggingConfig = -1073741811;
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      LOBYTE(v13) = 1;
      if ( !(unsigned __int8)UlIsValidLogDirectory(&v41, v13, 0) )
      {
        LoggingConfig = -1073741811;
        v16 = &word_140185488;
        v17 = v37;
        LOBYTE(v12) = 0;
        goto LABEL_62;
      }
      v39[2] = v41;
      *(_QWORD *)&v39[3] = v42;
      *(_OWORD *)((char *)v39 + 8) = v45;
      *((_QWORD *)&v39[1] + 1) = v46;
    }
  }
  v17 = v37;
  LOBYTE(v12) = 0;
  if ( LoggingConfig < 0 )
    goto LABEL_61;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(Current + 4104, 0);
  v26 = (_OWORD *)(a1 + 8);
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 )
  {
    if ( (v39[0] & 1) == 0 )
      goto LABEL_51;
    LoggingConfig = UlpCreateLoggingConfig(Current, a1, v50, v39);
    if ( LoggingConfig >= 0 )
      goto LABEL_50;
    goto LABEL_60;
  }
  if ( (v39[0] & 1) == 0 )
  {
    UlpCleanupLoggingConfig(Current, a1);
    goto LABEL_51;
  }
  LoggingConfig = UlpModifyLoggingConfig(v25, a1, v39);
  if ( LoggingConfig < 0 )
  {
LABEL_60:
    v17 = v37;
    LOBYTE(v12) = 1;
LABEL_61:
    v16 = &word_140185488;
    goto LABEL_62;
  }
  UlpCleanupLoggingInfo((void *)(a1 + 8));
LABEL_50:
  *v26 = v39[0];
  *(_OWORD *)(a1 + 24) = v39[1];
  *(_OWORD *)(a1 + 40) = v39[2];
  *(_OWORD *)(a1 + 56) = v39[3];
  *(_OWORD *)(a1 + 72) = v39[4];
  *(_OWORD *)(a1 + 88) = v39[5];
  *(_OWORD *)(a1 + 104) = v39[6];
LABEL_51:
  ExReleasePushLockExclusiveEx(Current + 4104, 0);
  KeLeaveCriticalRegion();
  v16 = &word_140185488;
  if ( *(char *)(Current + 1762) >= 0 )
  {
    v30 = v38;
  }
  else
  {
    v27 = &word_140185488;
    if ( *(_QWORD *)(a1 + 24) )
      v27 = *(const wchar_t **)(a1 + 24);
    v28 = &word_140185488;
    if ( *(_QWORD *)(a1 + 48) )
      v28 = *(const wchar_t **)(a1 + 48);
    v29 = *(_DWORD *)v26 & 1;
    v30 = v38;
    McTemplateK0qqqqzzq_EtwWriteTransfer(
      Current + 1688,
      (_DWORD)v28,
      (_DWORD)v27,
      v29,
      v34,
      v38,
      *(_DWORD *)(a1 + 64),
      (__int64)v28,
      (__int64)v27,
      *(_DWORD *)(a1 + 128));
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_LLLLZZL(
      a1 + 16,
      a1 + 40,
      v11,
      *(_DWORD *)(a1 + 8) & 1,
      v34,
      v30,
      *(_DWORD *)(a1 + 64),
      a1 + 40,
      a1 + 16,
      *(_DWORD *)(a1 + 128));
  v17 = v37;
  LOBYTE(v12) = 0;
LABEL_62:
  if ( (_BYTE)v12 )
  {
    ExReleasePushLockExclusiveEx(Current + 4104, 0);
    KeLeaveCriticalRegion();
  }
  if ( LoggingConfig < 0 )
  {
    if ( (*(_BYTE *)(Current + 1762) & 0x40) != 0 )
    {
      v31 = &word_140185488;
      if ( *((_QWORD *)&v45 + 1) )
        v31 = (const wchar_t *)*((_QWORD *)&v45 + 1);
      if ( *((_QWORD *)&v41 + 1) )
        v16 = (const wchar_t *)*((_QWORD *)&v41 + 1);
      v35 = (__int64)v16;
      v32 = v38;
      McTemplateK0qqqzzq_EtwWriteTransfer(
        Current + 1688,
        (_DWORD)v31,
        v11,
        LoggingConfig,
        v34,
        v38,
        v35,
        (__int64)v31,
        *(_DWORD *)(a1 + 128));
    }
    else
    {
      v32 = v38;
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_dLLZZL(v12, v13, v11, LoggingConfig, v34, v32, (__int64)&v41, (__int64)&v45, *(_DWORD *)(a1 + 128));
    if ( v8 )
    {
      SeDeleteClientSecurity(*(_QWORD *)&v39[6]);
      ExFreePoolWithTag(v8, 0);
    }
    if ( v44 )
    {
      LOBYTE(v11) = 1;
      LOBYTE(v13) = v17->RequestorMode;
      SeReleaseSecurityDescriptor(v44, v13, v11);
    }
    UxFreeCapturedUnicodeString(&v41);
    UxFreeCapturedUnicodeString(&v45);
  }
  return (unsigned int)LoggingConfig;
}

```

## disassembly

```asm
0x1400fd240  push    rbx
0x1400fd242  push    rsi
0x1400fd243  push    rdi
0x1400fd244  push    r12
0x1400fd246  push    r13
0x1400fd248  push    r14
0x1400fd24a  push    r15
0x1400fd24c  sub     rsp, 170h
0x1400fd253  mov     rax, cs:__security_cookie
0x1400fd25a  xor     rax, rsp
0x1400fd25d  mov     [rsp+1A8h+var_48], rax
0x1400fd265  mov     r14, r9
0x1400fd268  mov     [rsp+1A8h+var_148], r9
0x1400fd26d  mov     rsi, r8
0x1400fd270  mov     rax, rdx
0x1400fd273  mov     [rsp+1A8h+var_68], rdx
0x1400fd27b  mov     r15, rcx
0x1400fd27e  mov     [rsp+1A8h+var_78], rcx
0x1400fd286  mov     [rsp+1A8h+var_60], rdx
0x1400fd28e  mov     [rsp+1A8h+var_70], r9
0x1400fd296  xor     edi, edi
0x1400fd298  mov     ebx, edi
0x1400fd29a  xorps   xmm0, xmm0
0x1400fd29d  xor     eax, eax
0x1400fd29f  movups  [rsp+1A8h+var_C0], xmm0
0x1400fd2a7  mov     [rsp+1A8h+var_B0], rax
0x1400fd2af  xor     edx, edx; Val
0x1400fd2b1  lea     r8d, [rdi+70h]; Size
0x1400fd2b5  lea     rcx, [rsp+1A8h+var_138]; void *
0x1400fd2ba  call    memset
0x1400fd2bf  mov     [rsp+1A8h+var_A0], rdi
0x1400fd2c7  xorps   xmm0, xmm0
0x1400fd2ca  xor     eax, eax
0x1400fd2cc  movups  [rsp+1A8h+var_98], xmm0
0x1400fd2d4  mov     [rsp+1A8h+var_88], rax
0x1400fd2dc  mov     r12d, edi
0x1400fd2df  mov     [rsp+1A8h+var_A8], rdi
0x1400fd2e7  mov     qword ptr [rsp+1A8h+ClientSecurityQos.Length], rax
0x1400fd2ef  mov     dword ptr [rsp+1A8h+ClientSecurityQos.ContextTrackingMode], eax
0x1400fd2f6  mov     word ptr [rsp+1A8h+var_14C], di
0x1400fd2fb  mov     [rsp+1A8h+var_158], al
0x1400fd2ff  call    UxPodGetCurrent
0x1400fd304  mov     r13, rax
0x1400fd307  mov     [rsp+1A8h+var_80], rax
0x1400fd30f  mov     eax, [r15]
0x1400fd312  and     eax, 1
0x1400fd315  mov     [rsp+1A8h+var_140], eax
0x1400fd319  mov     [rsp+1A8h+var_C8], eax
0x1400fd320  xor     edx, edx; Val
0x1400fd322  lea     r8d, [rdi+70h]; Size
0x1400fd326  lea     rcx, [rsp+1A8h+var_138]; void *
0x1400fd32b  call    memset
0x1400fd330  nop
0x1400fd331  mov     rcx, r14; Irp
0x1400fd334  call    cs:__imp_IoIs32bitProcess
0x1400fd33b  nop     dword ptr [rax+rax+00h]
0x1400fd340  mov     ecx, [rsi]
0x1400fd342  mov     edx, [rsi+4]
0x1400fd345  mov     dword ptr [rsp+1A8h+var_138], ecx
0x1400fd349  mov     dword ptr [rsp+1A8h+var_138+4], edx
0x1400fd34d  test    al, al
0x1400fd34f  jz      loc_1400FD3F4
0x1400fd355  movzx   eax, word ptr [rsi+0Ch]
0x1400fd359  mov     word ptr [rsp+1A8h+var_14C], ax
0x1400fd35e  movzx   eax, word ptr [rsp+1A8h+var_14C]
0x1400fd363  mov     word ptr [rsp+1A8h+var_138+8], ax
0x1400fd368  mov     word ptr [rsp+1A8h+var_138+0Ah], ax
0x1400fd36d  mov     eax, [rsi+8]
0x1400fd370  mov     qword ptr [rsp+1A8h+var_128], rax
0x1400fd378  movzx   eax, word ptr [rsi+0Eh]
0x1400fd37c  mov     word ptr [rsp+1A8h+var_14C], ax
0x1400fd381  movzx   eax, word ptr [rsp+1A8h+var_14C]
0x1400fd386  mov     word ptr [rsp+1A8h+var_118], ax
0x1400fd38e  mov     word ptr [rsp+1A8h+var_118+2], ax
0x1400fd396  mov     eax, [rsi+10h]
0x1400fd399  mov     qword ptr [rsp+1A8h+var_118+8], rax
0x1400fd3a1  mov     eax, [rsi+14h]
0x1400fd3a4  mov     dword ptr [rsp+1A8h+var_108+8], eax
0x1400fd3ab  mov     eax, [rsi+18h]
0x1400fd3ae  mov     dword ptr [rsp+1A8h+var_108+0Ch], eax
0x1400fd3b5  mov     eax, [rsi+1Ch]
0x1400fd3b8  mov     qword ptr [rsp+1A8h+var_F8], rax
0x1400fd3c0  movzx   eax, word ptr [rsi+20h]
0x1400fd3c4  mov     word ptr [rsp+1A8h+var_F8+8], ax
0x1400fd3cc  movzx   eax, word ptr [rsi+22h]
0x1400fd3d0  mov     word ptr [rsp+1A8h+var_F8+0Ah], ax
0x1400fd3d8  mov     eax, [rsi+24h]
0x1400fd3db  mov     dword ptr [rsp+1A8h+var_F8+0Ch], eax
0x1400fd3e2  mov     eax, [rsi+28h]
0x1400fd3e5  mov     dword ptr [rsp+1A8h+var_E8], eax
0x1400fd3ec  mov     eax, [rsi+2Ch]
0x1400fd3ef  jmp     loc_1400FD492
0x1400fd3f4  movzx   eax, word ptr [rsi+10h]
0x1400fd3f8  mov     word ptr [rsp+1A8h+var_14C], ax
0x1400fd3fd  movzx   eax, word ptr [rsp+1A8h+var_14C]
0x1400fd402  mov     word ptr [rsp+1A8h+var_138+8], ax
0x1400fd407  mov     word ptr [rsp+1A8h+var_138+0Ah], ax
0x1400fd40c  mov     rax, [rsi+8]
0x1400fd410  mov     qword ptr [rsp+1A8h+var_128], rax
0x1400fd418  movzx   eax, word ptr [rsi+12h]
0x1400fd41c  mov     word ptr [rsp+1A8h+var_14C], ax
0x1400fd421  movzx   eax, word ptr [rsp+1A8h+var_14C]
0x1400fd426  mov     word ptr [rsp+1A8h+var_118], ax
0x1400fd42e  mov     word ptr [rsp+1A8h+var_118+2], ax
0x1400fd436  mov     rax, [rsi+18h]
0x1400fd43a  mov     qword ptr [rsp+1A8h+var_118+8], rax
0x1400fd442  mov     eax, [rsi+20h]
0x1400fd445  mov     dword ptr [rsp+1A8h+var_108+8], eax
0x1400fd44c  mov     eax, [rsi+24h]
0x1400fd44f  mov     dword ptr [rsp+1A8h+var_108+0Ch], eax
0x1400fd456  mov     rax, [rsi+28h]
0x1400fd45a  mov     qword ptr [rsp+1A8h+var_F8], rax
0x1400fd462  movzx   eax, word ptr [rsi+30h]
0x1400fd466  mov     word ptr [rsp+1A8h+var_F8+8], ax
0x1400fd46e  movzx   eax, word ptr [rsi+32h]
0x1400fd472  mov     word ptr [rsp+1A8h+var_F8+0Ah], ax
0x1400fd47a  mov     eax, [rsi+34h]
0x1400fd47d  mov     dword ptr [rsp+1A8h+var_F8+0Ch], eax
0x1400fd484  mov     eax, [rsi+38h]
0x1400fd487  mov     dword ptr [rsp+1A8h+var_E8], eax
0x1400fd48e  mov     rax, [rsi+40h]
0x1400fd492  mov     qword ptr [rsp+1A8h+var_E8+8], rax
0x1400fd49a  mov     sil, [r14+40h]
0x1400fd49e  mov     byte ptr [rsp+1A8h+var_D8+8], sil
0x1400fd4a6  test    byte ptr [rsp+1A8h+var_138], 1
0x1400fd4ab  jz      loc_1400FD8BA
0x1400fd4b1  lea     rcx, [rsp+1A8h+var_138]
0x1400fd4b6  call    UlpVerifyLoggingInfo
0x1400fd4bb  mov     ebx, eax
0x1400fd4bd  mov     [rsp+1A8h+var_154], eax
0x1400fd4c1  test    eax, eax
0x1400fd4c3  jns     short loc_1400FD4DA
0x1400fd4c5  lea     rsi, word_140185488
0x1400fd4cc  mov     r14, [rsp+1A8h+var_148]
0x1400fd4d1  mov     cl, [rsp+1A8h+var_158]
0x1400fd4d5  jmp     loc_1400FDADB
0x1400fd4da  cmp     byte ptr [rsp+1A8h+var_140], dil
0x1400fd4df  jz      short loc_1400FD512
0x1400fd4e1  cmp     dword ptr [rsp+1A8h+var_108+8], edi
0x1400fd4e8  jz      short loc_1400FD53A
0x1400fd4ea  cmp     dword ptr [rsp+1A8h+var_108+8], 3
0x1400fd4f2  jz      short loc_1400FD53A
0x1400fd4f4  mov     ebx, 0C00000BBh
0x1400fd4f9  mov     [rsp+1A8h+var_154], ebx
0x1400fd4fd  lea     rsi, word_140185488
0x1400fd504  mov     r14, [rsp+1A8h+var_148]
0x1400fd509  mov     cl, [rsp+1A8h+var_158]
0x1400fd50d  jmp     loc_1400FDADB
0x1400fd512  cmp     dword ptr [rsp+1A8h+var_108+8], 3
0x1400fd51a  jnz     short loc_1400FD53A
0x1400fd51c  mov     ebx, 0C00000BBh
0x1400fd521  mov     [rsp+1A8h+var_154], ebx
0x1400fd525  lea     rsi, word_140185488
0x1400fd52c  mov     r14, [rsp+1A8h+var_148]
0x1400fd531  mov     cl, [rsp+1A8h+var_158]
0x1400fd535  jmp     loc_1400FDADB
0x1400fd53a  mov     rbx, [r14+98h]
0x1400fd541  mov     rcx, r14; Irp
0x1400fd544  call    cs:__imp_IoGetRequestorProcess
0x1400fd54b  nop     dword ptr [rax+rax+00h]
0x1400fd550  mov     r8, rax
0x1400fd553  mov     r9b, sil
0x1400fd556  mov     rdx, rbx
0x1400fd559  call    UlThreadAdminCheck
0x1400fd55e  mov     ebx, eax
0x1400fd560  mov     [rsp+1A8h+var_154], eax
0x1400fd564  test    byte ptr [rsp+1A8h+var_138+4], 10h
0x1400fd569  jz      short loc_1400FD5B4
0x1400fd56b  mov     [rsp+1A8h+var_154], eax
0x1400fd56f  test    eax, eax
0x1400fd571  jns     short loc_1400FD588
0x1400fd573  lea     rsi, word_140185488
0x1400fd57a  mov     r14, [rsp+1A8h+var_148]
0x1400fd57f  mov     cl, [rsp+1A8h+var_158]
0x1400fd583  jmp     loc_1400FDADB
0x1400fd588  cmp     qword ptr [rsp+1A8h+var_E8+8], rdi
0x1400fd590  jz      loc_1400FD681
0x1400fd596  mov     ebx, 0C000000Dh
0x1400fd59b  mov     [rsp+1A8h+var_154], ebx
0x1400fd59f  lea     rsi, word_140185488
0x1400fd5a6  mov     r14, [rsp+1A8h+var_148]
0x1400fd5ab  mov     cl, [rsp+1A8h+var_158]
0x1400fd5af  jmp     loc_1400FDADB
0x1400fd5b4  test    eax, eax
0x1400fd5b6  jns     loc_1400FD681
0x1400fd5bc  mov     [rsp+1A8h+var_188], 1
0x1400fd5c4  lea     r9, UxLowPriorityPool
0x1400fd5cb  mov     edx, 48h ; 'H'
0x1400fd5d0  lea     ecx, [rdx-6]
0x1400fd5d3  mov     r8d, 53436C55h
0x1400fd5d9  call    cs:__imp_ExAllocatePool3
0x1400fd5e0  nop     dword ptr [rax+rax+00h]
0x1400fd5e5  mov     r12, rax
0x1400fd5e8  mov     [rsp+1A8h+var_A8], rax
0x1400fd5f0  test    rax, rax
0x1400fd5f3  jnz     short loc_1400FD613
0x1400fd5f5  mov     ebx, 0C000009Ah
0x1400fd5fa  mov     [rsp+1A8h+var_154], ebx
0x1400fd5fe  lea     rsi, word_140185488
0x1400fd605  mov     r14, [rsp+1A8h+var_148]
0x1400fd60a  mov     cl, [rsp+1A8h+var_158]
0x1400fd60e  jmp     loc_1400FDADB
0x1400fd613  mov     [rsp+1A8h+var_154], edi
0x1400fd617  mov     [rsp+1A8h+ClientSecurityQos.Length], 0Ch
0x1400fd622  mov     [rsp+1A8h+ClientSecurityQos.ImpersonationLevel], 3
0x1400fd62d  mov     word ptr [rsp+1A8h+ClientSecurityQos.ContextTrackingMode], 1
0x1400fd637  mov     rcx, gs:188h; ClientThread
0x1400fd640  mov     r9, r12; ClientContext
0x1400fd643  xor     r8d, r8d; RemoteSession
0x1400fd646  lea     rdx, [rsp+1A8h+ClientSecurityQos]; ClientSecurityQos
0x1400fd64e  call    cs:__imp_SeCreateClientSecurity
0x1400fd655  nop     dword ptr [rax+rax+00h]
0x1400fd65a  mov     ebx, eax
0x1400fd65c  mov     [rsp+1A8h+var_154], eax
0x1400fd660  test    eax, eax
0x1400fd662  jns     short loc_1400FD679
0x1400fd664  lea     rsi, word_140185488
0x1400fd66b  mov     r14, [rsp+1A8h+var_148]
0x1400fd670  mov     cl, [rsp+1A8h+var_158]
0x1400fd674  jmp     loc_1400FDADB
0x1400fd679  mov     qword ptr [rsp+1A8h+var_D8], r12
0x1400fd681  mov     rcx, qword ptr [rsp+1A8h+var_E8+8]
0x1400fd689  test    rcx, rcx
0x1400fd68c  jz      short loc_1400FD6D3
0x1400fd68e  lea     r9, [rsp+1A8h+var_14C]
0x1400fd693  lea     r8, [rsp+1A8h+var_A0]
0x1400fd69b  mov     dl, [r14+40h]
0x1400fd69f  call    UlpCaptureSecurityDescriptor
0x1400fd6a4  mov     ebx, eax
0x1400fd6a6  mov     [rsp+1A8h+var_154], eax
0x1400fd6aa  test    eax, eax
0x1400fd6ac  jns     short loc_1400FD6C3
0x1400fd6ae  lea     rsi, word_140185488
0x1400fd6b5  mov     r14, [rsp+1A8h+var_148]
0x1400fd6ba  mov     cl, [rsp+1A8h+var_158]
0x1400fd6be  jmp     loc_1400FDADB
0x1400fd6c3  mov     rax, [rsp+1A8h+var_A0]
0x1400fd6cb  mov     qword ptr [rsp+1A8h+var_E8+8], rax
0x1400fd6d3  cmp     dword ptr [rsp+1A8h+var_108+8], 4
0x1400fd6db  jz      loc_1400FD8BA
0x1400fd6e1  movzx   eax, word ptr [rsp+1A8h+var_138+8]
0x1400fd6e6  test    ax, ax
0x1400fd6e9  jz      short loc_1400FD6F4
0x1400fd6eb  cmp     dword ptr [rsp+1A8h+var_108+8], edi
0x1400fd6f2  jz      short loc_1400FD70E
0x1400fd6f4  xorps   xmm0, xmm0
0x1400fd6f7  movups  [rsp+1A8h+var_138+8], xmm0
0x1400fd6fc  mov     word ptr [rsp+1A8h+var_138+0Ah], di
0x1400fd701  mov     qword ptr [rsp+1A8h+var_128], rdi
0x1400fd709  movzx   eax, word ptr [rsp+1A8h+var_138+8]
0x1400fd70e  mov     esi, 208h
0x1400fd713  cmp     ax, si
0x1400fd716  jbe     short loc_1400FD736
0x1400fd718  mov     ebx, 0C000000Dh
0x1400fd71d  mov     [rsp+1A8h+var_154], ebx
0x1400fd721  lea     rsi, word_140185488
0x1400fd728  mov     r14, [rsp+1A8h+var_148]
0x1400fd72d  mov     cl, [rsp+1A8h+var_158]
0x1400fd731  jmp     loc_1400FDADB
0x1400fd736  lea     r8, [rsp+1A8h+var_98]
0x1400fd73e  mov     dl, [r14+40h]
0x1400fd742  lea     rcx, [rsp+1A8h+var_138+8]
0x1400fd747  call    UxCaptureUnicodeString
0x1400fd74c  mov     ebx, eax
0x1400fd74e  mov     [rsp+1A8h+var_154], eax
0x1400fd752  test    eax, eax
0x1400fd754  jns     short loc_1400FD76B
0x1400fd756  lea     rsi, word_140185488
0x1400fd75d  mov     r14, [rsp+1A8h+var_148]
0x1400fd762  mov     cl, [rsp+1A8h+var_158]
0x1400fd766  jmp     loc_1400FDADB
0x1400fd76b  cmp     word ptr [rsp+1A8h+var_118], si
0x1400fd773  jbe     short loc_1400FD793
0x1400fd775  mov     ebx, 0C000000Dh
0x1400fd77a  mov     [rsp+1A8h+var_154], ebx
0x1400fd77e  lea     rsi, word_140185488
0x1400fd785  mov     r14, [rsp+1A8h+var_148]
0x1400fd78a  mov     cl, [rsp+1A8h+var_158]
0x1400fd78e  jmp     loc_1400FDADB
0x1400fd793  lea     r8, [rsp+1A8h+var_C0]
0x1400fd79b  mov     dl, [r14+40h]
0x1400fd79f  lea     rcx, [rsp+1A8h+var_118]
0x1400fd7a7  call    UxCaptureUnicodeString
0x1400fd7ac  mov     ebx, eax
0x1400fd7ae  mov     [rsp+1A8h+var_154], eax
0x1400fd7b2  test    eax, eax
0x1400fd7b4  jns     short loc_1400FD7CB
0x1400fd7b6  lea     rsi, word_140185488
0x1400fd7bd  mov     r14, [rsp+1A8h+var_148]
0x1400fd7c2  mov     cl, [rsp+1A8h+var_158]
0x1400fd7c6  jmp     loc_1400FDADB
0x1400fd7cb  cmp     word ptr [rsp+1A8h+var_C0], di
0x1400fd7d3  jnz     short loc_1400FD7F3
0x1400fd7d5  mov     ebx, 0C000000Dh
0x1400fd7da  mov     [rsp+1A8h+var_154], ebx
0x1400fd7de  lea     rsi, word_140185488
0x1400fd7e5  mov     r14, [rsp+1A8h+var_148]
0x1400fd7ea  mov     cl, [rsp+1A8h+var_158]
0x1400fd7ee  jmp     loc_1400FDADB
0x1400fd7f3  xor     r8d, r8d
  ... truncated ...
```
