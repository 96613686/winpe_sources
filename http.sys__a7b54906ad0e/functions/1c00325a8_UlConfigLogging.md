# UlConfigLogging

- ea: `0x1c00325a8`
- end: `0x1c0032ff4`
- name: `UlConfigLogging`
- size: `2636`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1c0109cb4`
- `0x1c010ca60`

## callees

- `0x1c0001038`
- `0x1c001864c`
- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c0031cc4`
- `0x1c0031e08`
- `0x1c00325a8`
- `0x1c00338b4`
- `0x1c0033c2c`
- `0x1c003478c`
- `0x1c0098164`
- `0x1c0098574`
- `0x1c00a14ac`
- `0x1c00a2b80`
- `0x1c011f454`
- `0x1c011f6cc`
- `0x1c011f7b8`
- `0x1c012d8e8`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x1c0032882`
- `ntoskrnl!IoGetRequestorProcess` at `0x1c0032882`
- `ntoskrnl!SeTokenType` at `0x1c0032f3f`
- `ntoskrnl!SeTokenType` at `0x1c0032f3f`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1c0032f5c`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1c0032f5c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1c0032f74`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1c0032f74`
- `ntoskrnl!SeCreateClientSecurity` at `0x1c0032982`
- `ntoskrnl!SeCreateClientSecurity` at `0x1c0032982`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c0032fa8`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c0032fa8`
- `ntoskrnl!IoIs32bitProcess` at `0x1c003267a`
- `ntoskrnl!IoIs32bitProcess` at `0x1c003267a`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0032911`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0032911`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0032f87`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0032f87`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0032ce4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0032e3f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0032ce4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0032e3f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0032c3e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0032c3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0032cf0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0032e4b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0032cf0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0032e4b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0032c26`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0032c26`

## pseudocode

```c
__int64 __fastcall UlConfigLogging(__int64 a1, __int64 a2, int *a3, IRP *a4)
{
  __int64 Current; // r13
  _OWORD *v8; // r14
  BOOLEAN v9; // al
  __int64 v10; // r8
  int v11; // r9d
  int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // rax
  KPROCESSOR_MODE RequestorMode; // si
  NTSTATUS LoggingConfig; // ebx
  int *v17; // rsi
  char v18; // al
  PEPROCESS RequestorProcess; // rax
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  unsigned __int16 v23; // ax
  __int64 v24; // rcx
  int *v25; // rdx
  int *v26; // rcx
  int v27; // r8d
  int *v28; // rcx
  TOKEN_TYPE v29; // eax
  void *v30; // rcx
  int v32; // [rsp+20h] [rbp-1B8h]
  char v33; // [rsp+54h] [rbp-184h]
  _BYTE v34[12]; // [rsp+64h] [rbp-174h]
  _OWORD v35[7]; // [rsp+70h] [rbp-168h] BYREF
  int v36; // [rsp+E0h] [rbp-F8h] BYREF
  __int64 v37; // [rsp+E8h] [rbp-F0h] BYREF
  __int128 v38; // [rsp+F0h] [rbp-E8h] BYREF
  __int64 v39; // [rsp+100h] [rbp-D8h]
  __int64 v40; // [rsp+108h] [rbp-D0h]
  __int64 v41; // [rsp+110h] [rbp-C8h]
  IRP *v42; // [rsp+118h] [rbp-C0h]
  __int64 v43; // [rsp+120h] [rbp-B8h]
  __int128 v44; // [rsp+128h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+138h] [rbp-A0h]
  __int64 v46; // [rsp+140h] [rbp-98h]
  __int128 v47; // [rsp+148h] [rbp-90h] BYREF
  __int64 v48; // [rsp+158h] [rbp-80h]
  char v49; // [rsp+160h] [rbp-78h]
  int v50; // [rsp+161h] [rbp-77h]
  __int16 v51; // [rsp+165h] [rbp-73h]
  char v52; // [rsp+167h] [rbp-71h]
  __int128 v53; // [rsp+168h] [rbp-70h] BYREF
  __int64 v54; // [rsp+178h] [rbp-60h]
  char v55; // [rsp+180h] [rbp-58h]
  int v56; // [rsp+181h] [rbp-57h]
  __int16 v57; // [rsp+185h] [rbp-53h]
  char v58; // [rsp+187h] [rbp-51h]
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+188h] [rbp-50h] BYREF

  v43 = a2;
  v41 = a1;
  v46 = a2;
  v42 = a4;
  v38 = 0;
  v39 = 0;
  v37 = 0;
  v36 = 0;
  v44 = 0;
  v45 = 0;
  *(_DWORD *)&v34[8] = 0;
  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  Current = UxPodGetCurrent();
  v40 = Current;
  LODWORD(v8) = *(_DWORD *)a1 & 1;
  v33 = (char)v8;
  *(_QWORD *)v34 = (unsigned int)v8;
  memset(v35, 0, sizeof(v35));
  v9 = IoIs32bitProcess(a4);
  v12 = *a3;
  v13 = (unsigned int)a3[1];
  LODWORD(v35[0]) = *a3;
  DWORD1(v35[0]) = v13;
  if ( v9 )
  {
    WORD4(v35[0]) = *((_WORD *)a3 + 6);
    WORD5(v35[0]) = WORD4(v35[0]);
    *(_QWORD *)&v35[1] = (unsigned int)a3[2];
    LOWORD(v35[2]) = *((_WORD *)a3 + 7);
    WORD1(v35[2]) = v35[2];
    *((_QWORD *)&v35[2] + 1) = (unsigned int)a3[4];
    *((_QWORD *)&v35[3] + 1) = *(_QWORD *)(a3 + 5);
    *(_QWORD *)&v35[4] = (unsigned int)a3[7];
    *((_QWORD *)&v35[4] + 1) = *((_QWORD *)a3 + 4);
    LODWORD(v35[5]) = a3[10];
    v14 = (unsigned int)a3[11];
  }
  else
  {
    WORD4(v35[0]) = *((_WORD *)a3 + 8);
    WORD5(v35[0]) = WORD4(v35[0]);
    *(_QWORD *)&v35[1] = *((_QWORD *)a3 + 1);
    LOWORD(v35[2]) = *((_WORD *)a3 + 9);
    WORD1(v35[2]) = v35[2];
    *((_QWORD *)&v35[2] + 1) = *((_QWORD *)a3 + 3);
    *((_QWORD *)&v35[3] + 1) = *((_QWORD *)a3 + 4);
    v35[4] = *(_OWORD *)(a3 + 10);
    LODWORD(v35[5]) = a3[14];
    v14 = *((_QWORD *)a3 + 8);
  }
  *((_QWORD *)&v35[5] + 1) = v14;
  RequestorMode = a4->RequestorMode;
  BYTE8(v35[6]) = RequestorMode;
  if ( (v35[0] & 1) != 0 )
  {
    LoggingConfig = UlpVerifyLoggingInfo(v35);
    if ( LoggingConfig < 0 )
    {
      v17 = &dword_1C005F6B4;
      v18 = 0;
      goto LABEL_66;
    }
    if ( (_BYTE)v8 )
    {
      if ( DWORD2(v35[3]) && DWORD2(v35[3]) != 3 )
      {
        LoggingConfig = -1073741637;
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
    }
    else if ( DWORD2(v35[3]) == 3 )
    {
      LoggingConfig = -1073741637;
      v17 = &dword_1C005F6B4;
      v18 = 0;
      goto LABEL_66;
    }
    RequestorProcess = IoGetRequestorProcess(a4);
    LOBYTE(v20) = RequestorMode;
    v22 = UlThreadAdminCheck(v21, a4->Tail.Overlay.Thread, RequestorProcess, v20);
    LoggingConfig = v22;
    if ( (BYTE4(v35[0]) & 0x10) != 0 )
    {
      if ( v22 < 0 )
      {
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      if ( *((_QWORD *)&v35[5] + 1) )
      {
        LoggingConfig = -1073741811;
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
    }
    else if ( v22 < 0 )
    {
      *(_QWORD *)&v34[4] = ExAllocatePoolWithTagPriority((POOL_TYPE)512, 0x48u, 0x53436C55u, LowPoolPriority);
      if ( !*(_QWORD *)&v34[4] )
      {
        LoggingConfig = -1073741670;
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      ClientSecurityQos.Length = 12;
      ClientSecurityQos.ImpersonationLevel = SecurityDelegation;
      *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 1;
      LoggingConfig = SeCreateClientSecurity(
                        KeGetCurrentThread(),
                        &ClientSecurityQos,
                        0,
                        *(PSECURITY_CLIENT_CONTEXT *)&v34[4]);
      if ( LoggingConfig < 0 )
      {
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      *(_QWORD *)&v35[6] = *(_QWORD *)&v34[4];
    }
    v12 = DWORD2(v35[5]);
    if ( *((_QWORD *)&v35[5] + 1) )
    {
      LOBYTE(v13) = a4->RequestorMode;
      LoggingConfig = UlpCaptureSecurityDescriptor(*((_QWORD *)&v35[5] + 1), v13, &v37, &v36);
      if ( LoggingConfig < 0 )
      {
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      *((_QWORD *)&v35[5] + 1) = v37;
    }
    if ( DWORD2(v35[3]) != 4 )
    {
      v23 = WORD4(v35[0]);
      if ( !WORD4(v35[0]) || DWORD2(v35[3]) )
      {
        *((_QWORD *)&v35[0] + 1) = 0;
        *(_QWORD *)&v35[1] = 0;
        v23 = 0;
      }
      if ( v23 > 0x208u )
      {
        LoggingConfig = -1073741811;
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      LOBYTE(v13) = a4->RequestorMode;
      LoggingConfig = UxCaptureUnicodeString((char *)v35 + 8, v13, &v44);
      if ( LoggingConfig < 0 )
      {
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      if ( LOWORD(v35[2]) > 0x208u )
      {
        LoggingConfig = -1073741811;
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      LOBYTE(v13) = a4->RequestorMode;
      LoggingConfig = UxCaptureUnicodeString(&v35[2], v13, &v38);
      if ( LoggingConfig < 0 )
      {
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      if ( !(_WORD)v38 )
      {
        LoggingConfig = -1073741811;
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      LOBYTE(v13) = 1;
      if ( !(unsigned __int8)UlIsValidLogDirectory(&v38, v13, 0) )
      {
        LoggingConfig = -1073741811;
        v17 = &dword_1C005F6B4;
        v18 = 0;
        goto LABEL_66;
      }
      v35[2] = v38;
      *(_QWORD *)&v35[3] = v39;
      *(_OWORD *)((char *)v35 + 8) = v44;
      *((_QWORD *)&v35[1] + 1) = v45;
    }
  }
  else
  {
    LoggingConfig = 0;
  }
  v18 = 0;
  if ( LoggingConfig < 0 )
    goto LABEL_65;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(Current + 3912, 0);
  v8 = (_OWORD *)(a1 + 8);
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 )
  {
    if ( (v35[0] & 1) == 0 )
      goto LABEL_52;
    LoggingConfig = UlpCreateLoggingConfig(Current, a1, v43, v35);
    if ( LoggingConfig >= 0 )
      goto LABEL_51;
    goto LABEL_64;
  }
  if ( (v35[0] & 1) == 0 )
  {
    UlpCleanupLoggingConfig(Current, a1);
    goto LABEL_52;
  }
  LoggingConfig = UlpModifyLoggingConfig(v24, a1, v35);
  if ( LoggingConfig < 0 )
  {
LABEL_64:
    LOBYTE(v8) = v33;
    v18 = 1;
LABEL_65:
    v17 = &dword_1C005F6B4;
    goto LABEL_66;
  }
  UlpCleanupLoggingInfo((void *)(a1 + 8));
LABEL_51:
  *v8 = v35[0];
  *(_OWORD *)(a1 + 24) = v35[1];
  *(_OWORD *)(a1 + 40) = v35[2];
  *(_OWORD *)(a1 + 56) = v35[3];
  *(_OWORD *)(a1 + 72) = v35[4];
  *(_OWORD *)(a1 + 88) = v35[5];
  *(_OWORD *)(a1 + 104) = v35[6];
LABEL_52:
  ExReleasePushLockExclusiveEx(Current + 3912, 0);
  KeLeaveCriticalRegion();
  v17 = &dword_1C005F6B4;
  if ( *(_BYTE *)(Current + 1568) )
  {
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v48 = Current;
    v47 = 0;
    v49 = 0;
    v25 = &dword_1C005F6B4;
    if ( *(_QWORD *)(a1 + 24) )
      v25 = *(int **)(a1 + 24);
    v26 = &dword_1C005F6B4;
    if ( *(_QWORD *)(a1 + 48) )
      v26 = *(int **)(a1 + 48);
    McTemplateK0qqqqzzq_UlEtwWriteEventWrapper((_DWORD)v26, (_DWORD)v25, (unsigned int)&v47, *(_DWORD *)v8 & 1);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x400) != 0 )
  {
    v27 = *(_DWORD *)v8 & 1;
    LOBYTE(v8) = v33;
    WPP_SF_LLLLZZL(a1 + 16, a1 + 40, v27, v11, v33, *(_DWORD *)(a1 + 64), a1 + 40, a1 + 16, *(_DWORD *)(a1 + 128));
  }
  else
  {
    LOBYTE(v8) = v33;
  }
  v18 = 0;
LABEL_66:
  if ( v18 )
  {
    ExReleasePushLockExclusiveEx(Current + 3912, 0);
    KeLeaveCriticalRegion();
  }
  if ( LoggingConfig < 0 )
  {
    if ( *(_BYTE *)(Current + 1568) )
    {
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v54 = Current;
      v53 = 0;
      v55 = 0;
      v28 = &dword_1C005F6B4;
      if ( *((_QWORD *)&v44 + 1) )
        v28 = (int *)*((_QWORD *)&v44 + 1);
      if ( *((_QWORD *)&v38 + 1) )
        v17 = (int *)*((_QWORD *)&v38 + 1);
      McTemplateK0qqqzzq_UlEtwWriteEventWrapper(
        (_DWORD)v28,
        v13,
        (unsigned int)&v53,
        LoggingConfig,
        v32,
        (char)v8,
        (__int64)v17,
        (__int64)v28,
        *(_DWORD *)(a1 + 128));
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x400) != 0 )
      WPP_SF_dLLZZL(v12, v13, LoggingConfig, v11, (char)v8, (__int64)&v38, (__int64)&v44, *(_DWORD *)(a1 + 128));
    if ( *(_QWORD *)&v34[4] )
    {
      v29 = SeTokenType(*(PACCESS_TOKEN *)(*(_QWORD *)&v35[6] + 16LL));
      v30 = *(void **)(*(_QWORD *)&v35[6] + 16LL);
      if ( v29 == TokenPrimary )
        PsDereferencePrimaryToken(v30);
      else
        PsDereferenceImpersonationToken(v30);
      ExFreePoolWithTag(*(PVOID *)&v34[4], 0);
    }
    if ( v37 )
    {
      LOBYTE(v10) = 1;
      LOBYTE(v13) = a4->RequestorMode;
      SeReleaseSecurityDescriptor(v37, v13, v10);
    }
    UxFreeCapturedUnicodeString(&v38);
    UxFreeCapturedUnicodeString(&v44);
  }
  return (unsigned int)LoggingConfig;
}

```

## disassembly

```asm
0x1c00325a8  mov     r11, rsp
0x1c00325ab  push    rbx
0x1c00325ac  push    rsi
0x1c00325ad  push    rdi
0x1c00325ae  push    r12
0x1c00325b0  push    r13
0x1c00325b2  push    r14
0x1c00325b4  push    r15
0x1c00325b6  sub     rsp, 1A0h
0x1c00325bd  mov     rax, cs:__security_cookie
0x1c00325c4  xor     rax, rsp
0x1c00325c7  mov     [rsp+1D8h+var_40], rax
0x1c00325cf  mov     r12, r9
0x1c00325d2  mov     rbx, r8
0x1c00325d5  mov     [rsp+1D8h+var_B8], rdx
0x1c00325dd  mov     r15, rcx
0x1c00325e0  mov     [rsp+1D8h+var_C8], rcx
0x1c00325e8  mov     [rsp+1D8h+var_98], rdx
0x1c00325f0  mov     [rsp+1D8h+var_C0], r9
0x1c00325f8  xor     edi, edi
0x1c00325fa  mov     [rsp+1D8h+var_180], edi
0x1c00325fe  xorps   xmm0, xmm0
0x1c0032601  xor     eax, eax
0x1c0032603  movups  [rsp+1D8h+var_E8], xmm0
0x1c003260b  mov     [r11-0D8h], rax
0x1c0032612  mov     [r11-0F0h], rdi
0x1c0032619  mov     [rsp+1D8h+var_F8], edi
0x1c0032620  movups  [rsp+1D8h+var_B0], xmm0
0x1c0032628  mov     [r11-0A0h], rax
0x1c003262f  mov     [rsp+1D8h+ClientContext], rdi
0x1c0032634  mov     [r11-50h], rax
0x1c0032638  mov     [r11-48h], eax
0x1c003263c  mov     [rsp+1D8h+var_17C], di
0x1c0032641  mov     [rsp+1D8h+var_188], al
0x1c0032645  call    UxPodGetCurrent
0x1c003264a  mov     r13, rax
0x1c003264d  mov     [rsp+1D8h+var_D0], rax
0x1c0032655  mov     r14d, [r15]
0x1c0032658  and     r14d, 1
0x1c003265c  mov     [rsp+1D8h+var_184], r14d
0x1c0032661  mov     [rsp+1D8h+var_174], r14d
0x1c0032666  xor     edx, edx; Val
0x1c0032668  lea     r8d, [rdi+70h]; Size
0x1c003266c  lea     rcx, [rsp+1D8h+var_168]; void *
0x1c0032671  call    memset
0x1c0032676  nop
0x1c0032677  mov     rcx, r12; Irp
0x1c003267a  call    cs:__imp_IoIs32bitProcess
0x1c0032681  nop     dword ptr [rax+rax+00h]
0x1c0032686  mov     ecx, [rbx]
0x1c0032688  mov     edx, [rbx+4]
0x1c003268b  mov     dword ptr [rsp+1D8h+var_168], ecx
0x1c003268f  mov     dword ptr [rsp+1D8h+var_168+4], edx
0x1c0032693  test    al, al
0x1c0032695  jz      loc_1C003273A
0x1c003269b  movzx   eax, word ptr [rbx+0Ch]
0x1c003269f  mov     [rsp+1D8h+var_17C], ax
0x1c00326a4  movzx   eax, [rsp+1D8h+var_17C]
0x1c00326a9  mov     word ptr [rsp+1D8h+var_168+8], ax
0x1c00326ae  mov     word ptr [rsp+1D8h+var_168+0Ah], ax
0x1c00326b3  mov     eax, [rbx+8]
0x1c00326b6  mov     [rsp+80h], rax
0x1c00326be  movzx   eax, word ptr [rbx+0Eh]
0x1c00326c2  mov     [rsp+1D8h+var_17C], ax
0x1c00326c7  movzx   eax, [rsp+1D8h+var_17C]
0x1c00326cc  mov     word ptr [rsp+1D8h+var_148], ax
0x1c00326d4  mov     word ptr [rsp+1D8h+var_148+2], ax
0x1c00326dc  mov     eax, [rbx+10h]
0x1c00326df  mov     qword ptr [rsp+1D8h+var_148+8], rax
0x1c00326e7  mov     eax, [rbx+14h]
0x1c00326ea  mov     dword ptr [rsp+1D8h+var_138+8], eax
0x1c00326f1  mov     eax, [rbx+18h]
0x1c00326f4  mov     dword ptr [rsp+1D8h+var_138+0Ch], eax
0x1c00326fb  mov     eax, [rbx+1Ch]
0x1c00326fe  mov     qword ptr [rsp+1D8h+var_128], rax
0x1c0032706  movzx   eax, word ptr [rbx+20h]
0x1c003270a  mov     word ptr [rsp+1D8h+var_128+8], ax
0x1c0032712  movzx   eax, word ptr [rbx+22h]
0x1c0032716  mov     word ptr [rsp+1D8h+var_128+0Ah], ax
0x1c003271e  mov     eax, [rbx+24h]
0x1c0032721  mov     dword ptr [rsp+1D8h+var_128+0Ch], eax
0x1c0032728  mov     eax, [rbx+28h]
0x1c003272b  mov     dword ptr [rsp+1D8h+var_118], eax
0x1c0032732  mov     eax, [rbx+2Ch]
0x1c0032735  jmp     loc_1C00327D8
0x1c003273a  movzx   eax, word ptr [rbx+10h]
0x1c003273e  mov     [rsp+1D8h+var_17C], ax
0x1c0032743  movzx   eax, [rsp+1D8h+var_17C]
0x1c0032748  mov     word ptr [rsp+1D8h+var_168+8], ax
0x1c003274d  mov     word ptr [rsp+1D8h+var_168+0Ah], ax
0x1c0032752  mov     rax, [rbx+8]
0x1c0032756  mov     [rsp+80h], rax
0x1c003275e  movzx   eax, word ptr [rbx+12h]
0x1c0032762  mov     [rsp+1D8h+var_17C], ax
0x1c0032767  movzx   eax, [rsp+1D8h+var_17C]
0x1c003276c  mov     word ptr [rsp+1D8h+var_148], ax
0x1c0032774  mov     word ptr [rsp+1D8h+var_148+2], ax
0x1c003277c  mov     rax, [rbx+18h]
0x1c0032780  mov     qword ptr [rsp+1D8h+var_148+8], rax
0x1c0032788  mov     eax, [rbx+20h]
0x1c003278b  mov     dword ptr [rsp+1D8h+var_138+8], eax
0x1c0032792  mov     eax, [rbx+24h]
0x1c0032795  mov     dword ptr [rsp+1D8h+var_138+0Ch], eax
0x1c003279c  mov     rax, [rbx+28h]
0x1c00327a0  mov     qword ptr [rsp+1D8h+var_128], rax
0x1c00327a8  movzx   eax, word ptr [rbx+30h]
0x1c00327ac  mov     word ptr [rsp+1D8h+var_128+8], ax
0x1c00327b4  movzx   eax, word ptr [rbx+32h]
0x1c00327b8  mov     word ptr [rsp+1D8h+var_128+0Ah], ax
0x1c00327c0  mov     eax, [rbx+34h]
0x1c00327c3  mov     dword ptr [rsp+1D8h+var_128+0Ch], eax
0x1c00327ca  mov     eax, [rbx+38h]
0x1c00327cd  mov     dword ptr [rsp+1D8h+var_118], eax
0x1c00327d4  mov     rax, [rbx+40h]
0x1c00327d8  mov     qword ptr [rsp+1D8h+var_118+8], rax
0x1c00327e0  mov     sil, [r12+40h]
0x1c00327e5  mov     byte ptr [rsp+1D8h+var_108+8], sil
0x1c00327ed  test    byte ptr [rsp+1D8h+var_168], 1
0x1c00327f2  jz      loc_1C0032BA9
0x1c00327f8  lea     rcx, [rsp+1D8h+var_168]
0x1c00327fd  call    UlpVerifyLoggingInfo
0x1c0032802  mov     ebx, eax
0x1c0032804  mov     [rsp+1D8h+var_180], eax
0x1c0032808  test    eax, eax
0x1c003280a  jns     short loc_1C0032821
0x1c003280c  lea     rsi, dword_1C005F6B4
0x1c0032813  mov     r14d, [rsp+1D8h+var_184]
0x1c0032818  mov     al, [rsp+1D8h+var_188]
0x1c003281c  jmp     loc_1C0032E32
0x1c0032821  test    r14b, r14b
0x1c0032824  jz      short loc_1C0032857
0x1c0032826  cmp     dword ptr [rsp+1D8h+var_138+8], edi
0x1c003282d  jz      short loc_1C003287F
0x1c003282f  cmp     dword ptr [rsp+1D8h+var_138+8], 3
0x1c0032837  jz      short loc_1C003287F
0x1c0032839  mov     ebx, 0C00000BBh
0x1c003283e  mov     [rsp+1D8h+var_180], ebx
0x1c0032842  lea     rsi, dword_1C005F6B4
0x1c0032849  mov     r14d, [rsp+1D8h+var_184]
0x1c003284e  mov     al, [rsp+1D8h+var_188]
0x1c0032852  jmp     loc_1C0032E32
0x1c0032857  cmp     dword ptr [rsp+1D8h+var_138+8], 3
0x1c003285f  jnz     short loc_1C003287F
0x1c0032861  mov     ebx, 0C00000BBh
0x1c0032866  mov     [rsp+1D8h+var_180], ebx
0x1c003286a  lea     rsi, dword_1C005F6B4
0x1c0032871  mov     r14d, [rsp+1D8h+var_184]
0x1c0032876  mov     al, [rsp+1D8h+var_188]
0x1c003287a  jmp     loc_1C0032E32
0x1c003287f  mov     rcx, r12; Irp
0x1c0032882  call    cs:__imp_IoGetRequestorProcess
0x1c0032889  nop     dword ptr [rax+rax+00h]
0x1c003288e  mov     r8, rax
0x1c0032891  mov     r9b, sil
0x1c0032894  mov     rdx, [r12+98h]
0x1c003289c  call    UlThreadAdminCheck
0x1c00328a1  mov     ebx, eax
0x1c00328a3  mov     [rsp+1D8h+var_180], eax
0x1c00328a7  test    byte ptr [rsp+1D8h+var_168+4], 10h
0x1c00328ac  jz      short loc_1C00328F7
0x1c00328ae  mov     [rsp+1D8h+var_180], eax
0x1c00328b2  test    eax, eax
0x1c00328b4  jns     short loc_1C00328CB
0x1c00328b6  lea     rsi, dword_1C005F6B4
0x1c00328bd  mov     r14d, [rsp+1D8h+var_184]
0x1c00328c2  mov     al, [rsp+1D8h+var_188]
0x1c00328c6  jmp     loc_1C0032E32
0x1c00328cb  cmp     qword ptr [rsp+1D8h+var_118+8], rdi
0x1c00328d3  jz      loc_1C00329BA
0x1c00328d9  mov     ebx, 0C000000Dh
0x1c00328de  mov     [rsp+1D8h+var_180], ebx
0x1c00328e2  lea     rsi, dword_1C005F6B4
0x1c00328e9  mov     r14d, [rsp+1D8h+var_184]
0x1c00328ee  mov     al, [rsp+1D8h+var_188]
0x1c00328f2  jmp     loc_1C0032E32
0x1c00328f7  test    eax, eax
0x1c00328f9  jns     loc_1C00329BA
0x1c00328ff  xor     r9d, r9d; Priority
0x1c0032902  lea     edx, [r9+48h]; NumberOfBytes
0x1c0032906  mov     ecx, 200h; PoolType
0x1c003290b  mov     r8d, 53436C55h; Tag
0x1c0032911  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c0032918  nop     dword ptr [rax+rax+00h]
0x1c003291d  mov     [rsp+1D8h+ClientContext], rax
0x1c0032922  test    rax, rax
0x1c0032925  jnz     short loc_1C0032945
0x1c0032927  mov     ebx, 0C000009Ah
0x1c003292c  mov     [rsp+1D8h+var_180], ebx
0x1c0032930  lea     rsi, dword_1C005F6B4
0x1c0032937  mov     r14d, [rsp+1D8h+var_184]
0x1c003293c  mov     al, [rsp+1D8h+var_188]
0x1c0032940  jmp     loc_1C0032E32
0x1c0032945  mov     [rsp+1D8h+var_180], edi
0x1c0032949  mov     [rsp+1D8h+ClientSecurityQos.Length], 0Ch
0x1c0032954  mov     [rsp+1D8h+ClientSecurityQos.ImpersonationLevel], 3
0x1c003295f  mov     word ptr [rsp+1D8h+ClientSecurityQos.ContextTrackingMode], 1
0x1c0032969  mov     rcx, gs:188h; ClientThread
0x1c0032972  mov     r9, [rsp+1D8h+ClientContext]; ClientContext
0x1c0032977  xor     r8d, r8d; RemoteSession
0x1c003297a  lea     rdx, [rsp+1D8h+ClientSecurityQos]; ClientSecurityQos
0x1c0032982  call    cs:__imp_SeCreateClientSecurity
0x1c0032989  nop     dword ptr [rax+rax+00h]
0x1c003298e  mov     ebx, eax
0x1c0032990  mov     [rsp+1D8h+var_180], eax
0x1c0032994  test    eax, eax
0x1c0032996  jns     short loc_1C00329AD
0x1c0032998  lea     rsi, dword_1C005F6B4
0x1c003299f  mov     r14d, [rsp+1D8h+var_184]
0x1c00329a4  mov     al, [rsp+1D8h+var_188]
0x1c00329a8  jmp     loc_1C0032E32
0x1c00329ad  mov     rax, [rsp+1D8h+ClientContext]
0x1c00329b2  mov     qword ptr [rsp+1D8h+var_108], rax
0x1c00329ba  mov     rcx, qword ptr [rsp+1D8h+var_118+8]
0x1c00329c2  test    rcx, rcx
0x1c00329c5  jz      short loc_1C0032A10
0x1c00329c7  lea     r9, [rsp+1D8h+var_F8]
0x1c00329cf  lea     r8, [rsp+1D8h+var_F0]
0x1c00329d7  mov     dl, [r12+40h]
0x1c00329dc  call    UlpCaptureSecurityDescriptor
0x1c00329e1  mov     ebx, eax
0x1c00329e3  mov     [rsp+1D8h+var_180], eax
0x1c00329e7  test    eax, eax
0x1c00329e9  jns     short loc_1C0032A00
0x1c00329eb  lea     rsi, dword_1C005F6B4
0x1c00329f2  mov     r14d, [rsp+1D8h+var_184]
0x1c00329f7  mov     al, [rsp+1D8h+var_188]
0x1c00329fb  jmp     loc_1C0032E32
0x1c0032a00  mov     rax, [rsp+1D8h+var_F0]
0x1c0032a08  mov     qword ptr [rsp+1D8h+var_118+8], rax
0x1c0032a10  cmp     dword ptr [rsp+1D8h+var_138+8], 4
0x1c0032a18  jz      loc_1C0032BAD
0x1c0032a1e  movzx   eax, word ptr [rsp+1D8h+var_168+8]
0x1c0032a23  test    ax, ax
0x1c0032a26  jz      short loc_1C0032A31
0x1c0032a28  cmp     dword ptr [rsp+1D8h+var_138+8], edi
0x1c0032a2f  jz      short loc_1C0032A4B
0x1c0032a31  xorps   xmm0, xmm0
0x1c0032a34  movups  [rsp+1D8h+var_168+8], xmm0
0x1c0032a39  mov     word ptr [rsp+1D8h+var_168+0Ah], di
0x1c0032a3e  mov     [rsp+80h], rdi
0x1c0032a46  movzx   eax, word ptr [rsp+1D8h+var_168+8]
0x1c0032a4b  mov     esi, 208h
0x1c0032a50  cmp     ax, si
0x1c0032a53  jbe     short loc_1C0032A73
0x1c0032a55  mov     ebx, 0C000000Dh
0x1c0032a5a  mov     [rsp+1D8h+var_180], ebx
0x1c0032a5e  lea     rsi, dword_1C005F6B4
0x1c0032a65  mov     r14d, [rsp+1D8h+var_184]
0x1c0032a6a  mov     al, [rsp+1D8h+var_188]
0x1c0032a6e  jmp     loc_1C0032E32
0x1c0032a73  lea     r8, [rsp+1D8h+var_B0]
0x1c0032a7b  mov     dl, [r12+40h]
0x1c0032a80  lea     rcx, [rsp+1D8h+var_168+8]
0x1c0032a85  call    UxCaptureUnicodeString
0x1c0032a8a  mov     ebx, eax
0x1c0032a8c  mov     [rsp+1D8h+var_180], eax
0x1c0032a90  test    eax, eax
0x1c0032a92  jns     short loc_1C0032AA9
0x1c0032a94  lea     rsi, dword_1C005F6B4
0x1c0032a9b  mov     r14d, [rsp+1D8h+var_184]
0x1c0032aa0  mov     al, [rsp+1D8h+var_188]
0x1c0032aa4  jmp     loc_1C0032E32
0x1c0032aa9  cmp     word ptr [rsp+1D8h+var_148], si
0x1c0032ab1  jbe     short loc_1C0032AD1
0x1c0032ab3  mov     ebx, 0C000000Dh
0x1c0032ab8  mov     [rsp+1D8h+var_180], ebx
0x1c0032abc  lea     rsi, dword_1C005F6B4
0x1c0032ac3  mov     r14d, [rsp+1D8h+var_184]
0x1c0032ac8  mov     al, [rsp+1D8h+var_188]
0x1c0032acc  jmp     loc_1C0032E32
0x1c0032ad1  lea     r8, [rsp+1D8h+var_E8]
0x1c0032ad9  mov     dl, [r12+40h]
0x1c0032ade  lea     rcx, [rsp+1D8h+var_148]
0x1c0032ae6  call    UxCaptureUnicodeString
0x1c0032aeb  mov     ebx, eax
0x1c0032aed  mov     [rsp+1D8h+var_180], eax
0x1c0032af1  test    eax, eax
0x1c0032af3  jns     short loc_1C0032B0A
0x1c0032af5  lea     rsi, dword_1C005F6B4
0x1c0032afc  mov     r14d, [rsp+1D8h+var_184]
0x1c0032b01  mov     al, [rsp+1D8h+var_188]
0x1c0032b05  jmp     loc_1C0032E32
0x1c0032b0a  cmp     word ptr [rsp+1D8h+var_E8], di
0x1c0032b12  jnz     short loc_1C0032B32
0x1c0032b14  mov     ebx, 0C000000Dh
0x1c0032b19  mov     [rsp+1D8h+var_180], ebx
0x1c0032b1d  lea     rsi, dword_1C005F6B4
0x1c0032b24  mov     r14d, [rsp+1D8h+var_184]
0x1c0032b29  mov     al, [rsp+1D8h+var_188]
0x1c0032b2d  jmp     loc_1C0032E32
0x1c0032b32  xor     r8d, r8d
0x1c0032b35  mov     dl, 1
0x1c0032b37  lea     rcx, [rsp+1D8h+var_E8]
0x1c0032b3f  call    UlIsValidLogDirectory
0x1c0032b44  test    al, al
0x1c0032b46  jnz     short loc_1C0032B66
0x1c0032b48  mov     ebx, 0C000000Dh
0x1c0032b4d  mov     [rsp+1D8h+var_180], ebx
0x1c0032b51  lea     rsi, dword_1C005F6B4
0x1c0032b58  mov     r14d, [rsp+1D8h+var_184]
  ... truncated ...
```
