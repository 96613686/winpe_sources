# UlConfigLogging

- ea: `0x1400fd210`
- end: `0x1400fdc53`
- name: `UlConfigLogging`
- size: `2627`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d4fe8`
- `0x1400d78d8`

## callees

- `0x1400172ac`
- `0x140017370`
- `0x1400176a0`
- `0x14006295c`
- `0x1400fbe98`
- `0x1400fbfd0`
- `0x1400fd210`
- `0x1400fead8`
- `0x1400ffd4c`
- `0x1400fffbc`
- `0x14010012c`
- `0x140100518`
- `0x140101848`
- `0x140101f2c`
- `0x140167700`
- `0x140167b40`
- `0x1401c49c4`
- `0x1401cec8c`
- `0x1401cf17c`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x1400fd514`
- `ntoskrnl!IoGetRequestorProcess` at `0x1400fd514`
- `ntoskrnl!SeCreateClientSecurity` at `0x1400fd61e`
- `ntoskrnl!SeCreateClientSecurity` at `0x1400fd61e`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400fdbd6`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400fdbd6`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400fdc07`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400fdc07`
- `ntoskrnl!IoIs32bitProcess` at `0x1400fd304`
- `ntoskrnl!IoIs32bitProcess` at `0x1400fd304`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fd9e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fdac4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fd9e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fdac4`
- `ntoskrnl!ExAllocatePool3` at `0x1400fd5a9`
- `ntoskrnl!ExAllocatePool3` at `0x1400fd5a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fdbe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fdbe7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400fd9da`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400fdab8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400fd9da`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400fdab8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400fd934`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400fd934`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fd91c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fd91c`

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
0x1400fd210  push    rbx
0x1400fd212  push    rsi
0x1400fd213  push    rdi
0x1400fd214  push    r12
0x1400fd216  push    r13
0x1400fd218  push    r14
0x1400fd21a  push    r15
0x1400fd21c  sub     rsp, 170h
0x1400fd223  mov     rax, cs:__security_cookie
0x1400fd22a  xor     rax, rsp
0x1400fd22d  mov     [rsp+1A8h+var_48], rax
0x1400fd235  mov     r14, r9
0x1400fd238  mov     [rsp+1A8h+var_148], r9
0x1400fd23d  mov     rsi, r8
0x1400fd240  mov     rax, rdx
0x1400fd243  mov     [rsp+1A8h+var_68], rdx
0x1400fd24b  mov     r15, rcx
0x1400fd24e  mov     [rsp+1A8h+var_78], rcx
0x1400fd256  mov     [rsp+1A8h+var_60], rdx
0x1400fd25e  mov     [rsp+1A8h+var_70], r9
0x1400fd266  xor     edi, edi
0x1400fd268  mov     ebx, edi
0x1400fd26a  xorps   xmm0, xmm0
0x1400fd26d  xor     eax, eax
0x1400fd26f  movups  [rsp+1A8h+var_C0], xmm0
0x1400fd277  mov     [rsp+1A8h+var_B0], rax
0x1400fd27f  xor     edx, edx; Val
0x1400fd281  lea     r8d, [rdi+70h]; Size
0x1400fd285  lea     rcx, [rsp+1A8h+var_138]; void *
0x1400fd28a  call    memset
0x1400fd28f  mov     [rsp+1A8h+var_A0], rdi
0x1400fd297  xorps   xmm0, xmm0
0x1400fd29a  xor     eax, eax
0x1400fd29c  movups  [rsp+1A8h+var_98], xmm0
0x1400fd2a4  mov     [rsp+1A8h+var_88], rax
0x1400fd2ac  mov     r12d, edi
0x1400fd2af  mov     [rsp+1A8h+var_A8], rdi
0x1400fd2b7  mov     qword ptr [rsp+1A8h+ClientSecurityQos.Length], rax
0x1400fd2bf  mov     dword ptr [rsp+1A8h+ClientSecurityQos.ContextTrackingMode], eax
0x1400fd2c6  mov     word ptr [rsp+1A8h+var_14C], di
0x1400fd2cb  mov     [rsp+1A8h+var_158], al
0x1400fd2cf  call    UxPodGetCurrent
0x1400fd2d4  mov     r13, rax
0x1400fd2d7  mov     [rsp+1A8h+var_80], rax
0x1400fd2df  mov     eax, [r15]
0x1400fd2e2  and     eax, 1
0x1400fd2e5  mov     [rsp+1A8h+var_140], eax
0x1400fd2e9  mov     [rsp+1A8h+var_C8], eax
0x1400fd2f0  xor     edx, edx; Val
0x1400fd2f2  lea     r8d, [rdi+70h]; Size
0x1400fd2f6  lea     rcx, [rsp+1A8h+var_138]; void *
0x1400fd2fb  call    memset
0x1400fd300  nop
0x1400fd301  mov     rcx, r14; Irp
0x1400fd304  call    cs:__imp_IoIs32bitProcess
0x1400fd30b  nop     dword ptr [rax+rax+00h]
0x1400fd310  mov     ecx, [rsi]
0x1400fd312  mov     edx, [rsi+4]
0x1400fd315  mov     dword ptr [rsp+1A8h+var_138], ecx
0x1400fd319  mov     dword ptr [rsp+1A8h+var_138+4], edx
0x1400fd31d  test    al, al
0x1400fd31f  jz      loc_1400FD3C4
0x1400fd325  movzx   eax, word ptr [rsi+0Ch]
0x1400fd329  mov     word ptr [rsp+1A8h+var_14C], ax
0x1400fd32e  movzx   eax, word ptr [rsp+1A8h+var_14C]
0x1400fd333  mov     word ptr [rsp+1A8h+var_138+8], ax
0x1400fd338  mov     word ptr [rsp+1A8h+var_138+0Ah], ax
0x1400fd33d  mov     eax, [rsi+8]
0x1400fd340  mov     qword ptr [rsp+1A8h+var_128], rax
0x1400fd348  movzx   eax, word ptr [rsi+0Eh]
0x1400fd34c  mov     word ptr [rsp+1A8h+var_14C], ax
0x1400fd351  movzx   eax, word ptr [rsp+1A8h+var_14C]
0x1400fd356  mov     word ptr [rsp+1A8h+var_118], ax
0x1400fd35e  mov     word ptr [rsp+1A8h+var_118+2], ax
0x1400fd366  mov     eax, [rsi+10h]
0x1400fd369  mov     qword ptr [rsp+1A8h+var_118+8], rax
0x1400fd371  mov     eax, [rsi+14h]
0x1400fd374  mov     dword ptr [rsp+1A8h+var_108+8], eax
0x1400fd37b  mov     eax, [rsi+18h]
0x1400fd37e  mov     dword ptr [rsp+1A8h+var_108+0Ch], eax
0x1400fd385  mov     eax, [rsi+1Ch]
0x1400fd388  mov     qword ptr [rsp+1A8h+var_F8], rax
0x1400fd390  movzx   eax, word ptr [rsi+20h]
0x1400fd394  mov     word ptr [rsp+1A8h+var_F8+8], ax
0x1400fd39c  movzx   eax, word ptr [rsi+22h]
0x1400fd3a0  mov     word ptr [rsp+1A8h+var_F8+0Ah], ax
0x1400fd3a8  mov     eax, [rsi+24h]
0x1400fd3ab  mov     dword ptr [rsp+1A8h+var_F8+0Ch], eax
0x1400fd3b2  mov     eax, [rsi+28h]
0x1400fd3b5  mov     dword ptr [rsp+1A8h+var_E8], eax
0x1400fd3bc  mov     eax, [rsi+2Ch]
0x1400fd3bf  jmp     loc_1400FD462
0x1400fd3c4  movzx   eax, word ptr [rsi+10h]
0x1400fd3c8  mov     word ptr [rsp+1A8h+var_14C], ax
0x1400fd3cd  movzx   eax, word ptr [rsp+1A8h+var_14C]
0x1400fd3d2  mov     word ptr [rsp+1A8h+var_138+8], ax
0x1400fd3d7  mov     word ptr [rsp+1A8h+var_138+0Ah], ax
0x1400fd3dc  mov     rax, [rsi+8]
0x1400fd3e0  mov     qword ptr [rsp+1A8h+var_128], rax
0x1400fd3e8  movzx   eax, word ptr [rsi+12h]
0x1400fd3ec  mov     word ptr [rsp+1A8h+var_14C], ax
0x1400fd3f1  movzx   eax, word ptr [rsp+1A8h+var_14C]
0x1400fd3f6  mov     word ptr [rsp+1A8h+var_118], ax
0x1400fd3fe  mov     word ptr [rsp+1A8h+var_118+2], ax
0x1400fd406  mov     rax, [rsi+18h]
0x1400fd40a  mov     qword ptr [rsp+1A8h+var_118+8], rax
0x1400fd412  mov     eax, [rsi+20h]
0x1400fd415  mov     dword ptr [rsp+1A8h+var_108+8], eax
0x1400fd41c  mov     eax, [rsi+24h]
0x1400fd41f  mov     dword ptr [rsp+1A8h+var_108+0Ch], eax
0x1400fd426  mov     rax, [rsi+28h]
0x1400fd42a  mov     qword ptr [rsp+1A8h+var_F8], rax
0x1400fd432  movzx   eax, word ptr [rsi+30h]
0x1400fd436  mov     word ptr [rsp+1A8h+var_F8+8], ax
0x1400fd43e  movzx   eax, word ptr [rsi+32h]
0x1400fd442  mov     word ptr [rsp+1A8h+var_F8+0Ah], ax
0x1400fd44a  mov     eax, [rsi+34h]
0x1400fd44d  mov     dword ptr [rsp+1A8h+var_F8+0Ch], eax
0x1400fd454  mov     eax, [rsi+38h]
0x1400fd457  mov     dword ptr [rsp+1A8h+var_E8], eax
0x1400fd45e  mov     rax, [rsi+40h]
0x1400fd462  mov     qword ptr [rsp+1A8h+var_E8+8], rax
0x1400fd46a  mov     sil, [r14+40h]
0x1400fd46e  mov     byte ptr [rsp+1A8h+var_D8+8], sil
0x1400fd476  test    byte ptr [rsp+1A8h+var_138], 1
0x1400fd47b  jz      loc_1400FD88A
0x1400fd481  lea     rcx, [rsp+1A8h+var_138]
0x1400fd486  call    UlpVerifyLoggingInfo
0x1400fd48b  mov     ebx, eax
0x1400fd48d  mov     [rsp+1A8h+var_154], eax
0x1400fd491  test    eax, eax
0x1400fd493  jns     short loc_1400FD4AA
0x1400fd495  lea     rsi, word_140185488
0x1400fd49c  mov     r14, [rsp+1A8h+var_148]
0x1400fd4a1  mov     cl, [rsp+1A8h+var_158]
0x1400fd4a5  jmp     loc_1400FDAAB
0x1400fd4aa  cmp     byte ptr [rsp+1A8h+var_140], dil
0x1400fd4af  jz      short loc_1400FD4E2
0x1400fd4b1  cmp     dword ptr [rsp+1A8h+var_108+8], edi
0x1400fd4b8  jz      short loc_1400FD50A
0x1400fd4ba  cmp     dword ptr [rsp+1A8h+var_108+8], 3
0x1400fd4c2  jz      short loc_1400FD50A
0x1400fd4c4  mov     ebx, 0C00000BBh
0x1400fd4c9  mov     [rsp+1A8h+var_154], ebx
0x1400fd4cd  lea     rsi, word_140185488
0x1400fd4d4  mov     r14, [rsp+1A8h+var_148]
0x1400fd4d9  mov     cl, [rsp+1A8h+var_158]
0x1400fd4dd  jmp     loc_1400FDAAB
0x1400fd4e2  cmp     dword ptr [rsp+1A8h+var_108+8], 3
0x1400fd4ea  jnz     short loc_1400FD50A
0x1400fd4ec  mov     ebx, 0C00000BBh
0x1400fd4f1  mov     [rsp+1A8h+var_154], ebx
0x1400fd4f5  lea     rsi, word_140185488
0x1400fd4fc  mov     r14, [rsp+1A8h+var_148]
0x1400fd501  mov     cl, [rsp+1A8h+var_158]
0x1400fd505  jmp     loc_1400FDAAB
0x1400fd50a  mov     rbx, [r14+98h]
0x1400fd511  mov     rcx, r14; Irp
0x1400fd514  call    cs:__imp_IoGetRequestorProcess
0x1400fd51b  nop     dword ptr [rax+rax+00h]
0x1400fd520  mov     r8, rax
0x1400fd523  mov     r9b, sil
0x1400fd526  mov     rdx, rbx
0x1400fd529  call    UlThreadAdminCheck
0x1400fd52e  mov     ebx, eax
0x1400fd530  mov     [rsp+1A8h+var_154], eax
0x1400fd534  test    byte ptr [rsp+1A8h+var_138+4], 10h
0x1400fd539  jz      short loc_1400FD584
0x1400fd53b  mov     [rsp+1A8h+var_154], eax
0x1400fd53f  test    eax, eax
0x1400fd541  jns     short loc_1400FD558
0x1400fd543  lea     rsi, word_140185488
0x1400fd54a  mov     r14, [rsp+1A8h+var_148]
0x1400fd54f  mov     cl, [rsp+1A8h+var_158]
0x1400fd553  jmp     loc_1400FDAAB
0x1400fd558  cmp     qword ptr [rsp+1A8h+var_E8+8], rdi
0x1400fd560  jz      loc_1400FD651
0x1400fd566  mov     ebx, 0C000000Dh
0x1400fd56b  mov     [rsp+1A8h+var_154], ebx
0x1400fd56f  lea     rsi, word_140185488
0x1400fd576  mov     r14, [rsp+1A8h+var_148]
0x1400fd57b  mov     cl, [rsp+1A8h+var_158]
0x1400fd57f  jmp     loc_1400FDAAB
0x1400fd584  test    eax, eax
0x1400fd586  jns     loc_1400FD651
0x1400fd58c  mov     [rsp+1A8h+var_188], 1
0x1400fd594  lea     r9, UxLowPriorityPool
0x1400fd59b  mov     edx, 48h ; 'H'
0x1400fd5a0  lea     ecx, [rdx-6]
0x1400fd5a3  mov     r8d, 53436C55h
0x1400fd5a9  call    cs:__imp_ExAllocatePool3
0x1400fd5b0  nop     dword ptr [rax+rax+00h]
0x1400fd5b5  mov     r12, rax
0x1400fd5b8  mov     [rsp+1A8h+var_A8], rax
0x1400fd5c0  test    rax, rax
0x1400fd5c3  jnz     short loc_1400FD5E3
0x1400fd5c5  mov     ebx, 0C000009Ah
0x1400fd5ca  mov     [rsp+1A8h+var_154], ebx
0x1400fd5ce  lea     rsi, word_140185488
0x1400fd5d5  mov     r14, [rsp+1A8h+var_148]
0x1400fd5da  mov     cl, [rsp+1A8h+var_158]
0x1400fd5de  jmp     loc_1400FDAAB
0x1400fd5e3  mov     [rsp+1A8h+var_154], edi
0x1400fd5e7  mov     [rsp+1A8h+ClientSecurityQos.Length], 0Ch
0x1400fd5f2  mov     [rsp+1A8h+ClientSecurityQos.ImpersonationLevel], 3
0x1400fd5fd  mov     word ptr [rsp+1A8h+ClientSecurityQos.ContextTrackingMode], 1
0x1400fd607  mov     rcx, gs:188h; ClientThread
0x1400fd610  mov     r9, r12; ClientContext
0x1400fd613  xor     r8d, r8d; RemoteSession
0x1400fd616  lea     rdx, [rsp+1A8h+ClientSecurityQos]; ClientSecurityQos
0x1400fd61e  call    cs:__imp_SeCreateClientSecurity
0x1400fd625  nop     dword ptr [rax+rax+00h]
0x1400fd62a  mov     ebx, eax
0x1400fd62c  mov     [rsp+1A8h+var_154], eax
0x1400fd630  test    eax, eax
0x1400fd632  jns     short loc_1400FD649
0x1400fd634  lea     rsi, word_140185488
0x1400fd63b  mov     r14, [rsp+1A8h+var_148]
0x1400fd640  mov     cl, [rsp+1A8h+var_158]
0x1400fd644  jmp     loc_1400FDAAB
0x1400fd649  mov     qword ptr [rsp+1A8h+var_D8], r12
0x1400fd651  mov     rcx, qword ptr [rsp+1A8h+var_E8+8]
0x1400fd659  test    rcx, rcx
0x1400fd65c  jz      short loc_1400FD6A3
0x1400fd65e  lea     r9, [rsp+1A8h+var_14C]
0x1400fd663  lea     r8, [rsp+1A8h+var_A0]
0x1400fd66b  mov     dl, [r14+40h]
0x1400fd66f  call    UlpCaptureSecurityDescriptor
0x1400fd674  mov     ebx, eax
0x1400fd676  mov     [rsp+1A8h+var_154], eax
0x1400fd67a  test    eax, eax
0x1400fd67c  jns     short loc_1400FD693
0x1400fd67e  lea     rsi, word_140185488
0x1400fd685  mov     r14, [rsp+1A8h+var_148]
0x1400fd68a  mov     cl, [rsp+1A8h+var_158]
0x1400fd68e  jmp     loc_1400FDAAB
0x1400fd693  mov     rax, [rsp+1A8h+var_A0]
0x1400fd69b  mov     qword ptr [rsp+1A8h+var_E8+8], rax
0x1400fd6a3  cmp     dword ptr [rsp+1A8h+var_108+8], 4
0x1400fd6ab  jz      loc_1400FD88A
0x1400fd6b1  movzx   eax, word ptr [rsp+1A8h+var_138+8]
0x1400fd6b6  test    ax, ax
0x1400fd6b9  jz      short loc_1400FD6C4
0x1400fd6bb  cmp     dword ptr [rsp+1A8h+var_108+8], edi
0x1400fd6c2  jz      short loc_1400FD6DE
0x1400fd6c4  xorps   xmm0, xmm0
0x1400fd6c7  movups  [rsp+1A8h+var_138+8], xmm0
0x1400fd6cc  mov     word ptr [rsp+1A8h+var_138+0Ah], di
0x1400fd6d1  mov     qword ptr [rsp+1A8h+var_128], rdi
0x1400fd6d9  movzx   eax, word ptr [rsp+1A8h+var_138+8]
0x1400fd6de  mov     esi, 208h
0x1400fd6e3  cmp     ax, si
0x1400fd6e6  jbe     short loc_1400FD706
0x1400fd6e8  mov     ebx, 0C000000Dh
0x1400fd6ed  mov     [rsp+1A8h+var_154], ebx
0x1400fd6f1  lea     rsi, word_140185488
0x1400fd6f8  mov     r14, [rsp+1A8h+var_148]
0x1400fd6fd  mov     cl, [rsp+1A8h+var_158]
0x1400fd701  jmp     loc_1400FDAAB
0x1400fd706  lea     r8, [rsp+1A8h+var_98]
0x1400fd70e  mov     dl, [r14+40h]
0x1400fd712  lea     rcx, [rsp+1A8h+var_138+8]
0x1400fd717  call    UxCaptureUnicodeString
0x1400fd71c  mov     ebx, eax
0x1400fd71e  mov     [rsp+1A8h+var_154], eax
0x1400fd722  test    eax, eax
0x1400fd724  jns     short loc_1400FD73B
0x1400fd726  lea     rsi, word_140185488
0x1400fd72d  mov     r14, [rsp+1A8h+var_148]
0x1400fd732  mov     cl, [rsp+1A8h+var_158]
0x1400fd736  jmp     loc_1400FDAAB
0x1400fd73b  cmp     word ptr [rsp+1A8h+var_118], si
0x1400fd743  jbe     short loc_1400FD763
0x1400fd745  mov     ebx, 0C000000Dh
0x1400fd74a  mov     [rsp+1A8h+var_154], ebx
0x1400fd74e  lea     rsi, word_140185488
0x1400fd755  mov     r14, [rsp+1A8h+var_148]
0x1400fd75a  mov     cl, [rsp+1A8h+var_158]
0x1400fd75e  jmp     loc_1400FDAAB
0x1400fd763  lea     r8, [rsp+1A8h+var_C0]
0x1400fd76b  mov     dl, [r14+40h]
0x1400fd76f  lea     rcx, [rsp+1A8h+var_118]
0x1400fd777  call    UxCaptureUnicodeString
0x1400fd77c  mov     ebx, eax
0x1400fd77e  mov     [rsp+1A8h+var_154], eax
0x1400fd782  test    eax, eax
0x1400fd784  jns     short loc_1400FD79B
0x1400fd786  lea     rsi, word_140185488
0x1400fd78d  mov     r14, [rsp+1A8h+var_148]
0x1400fd792  mov     cl, [rsp+1A8h+var_158]
0x1400fd796  jmp     loc_1400FDAAB
0x1400fd79b  cmp     word ptr [rsp+1A8h+var_C0], di
0x1400fd7a3  jnz     short loc_1400FD7C3
0x1400fd7a5  mov     ebx, 0C000000Dh
0x1400fd7aa  mov     [rsp+1A8h+var_154], ebx
0x1400fd7ae  lea     rsi, word_140185488
0x1400fd7b5  mov     r14, [rsp+1A8h+var_148]
0x1400fd7ba  mov     cl, [rsp+1A8h+var_158]
0x1400fd7be  jmp     loc_1400FDAAB
0x1400fd7c3  xor     r8d, r8d
  ... truncated ...
```
