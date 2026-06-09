# CMemoryDiagnosticHandler::Worker(void)

- ea: `0x18001ead0`
- end: `0x18001f106`
- name: `?Worker@CMemoryDiagnosticHandler@@EEAAJXZ`
- size: `1590`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001950`
- `0x180001a8c`
- `0x1800026b0`
- `0x180002b0c`
- `0x180002b4c`
- `0x18001b124`
- `0x18001b550`
- `0x18001ba68`
- `0x18001cee0`
- `0x18001d09c`
- `0x18001d530`
- `0x18001dd54`
- `0x18001e018`
- `0x18001e31c`
- `0x18001e670`
- `0x18001ead0`
- `0x18001f560`
- `0x18001f594`
- `0x18001f5dc`
- `0x18001f6d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001ed5e`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001ed5e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001eb1d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001eb1d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001eb54`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001eb54`
- `bcd!BcdCloseObject` at `0x18001ecd2`
- `bcd!BcdCloseObject` at `0x18001ecd2`
- `bcd!BcdOpenSystemStore` at `0x18001eb7a`
- `bcd!BcdOpenSystemStore` at `0x18001eb7a`
- `bcd!BcdOpenObject` at `0x18001ebc6`
- `bcd!BcdOpenObject` at `0x18001ebc6`
- `bcd!BcdGetElementData` at `0x18001ec0d`
- `bcd!BcdGetElementData` at `0x18001ec62`
- `bcd!BcdGetElementData` at `0x18001ec0d`
- `bcd!BcdGetElementData` at `0x18001ec62`
- `bcd!BcdCloseStore` at `0x18001ecee`
- `bcd!BcdCloseStore` at `0x18001ecee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMemoryDiagnosticHandler::Worker(CMemoryDiagnosticHandler *this)
{
  unsigned __int64 v2; // r12
  int v3; // eax
  int v4; // r14d
  __int64 *v5; // r15
  int ElementData; // eax
  const unsigned __int16 *v7; // rdx
  int v8; // ebx
  CMemoryDiagnosticHandler *v9; // r8
  __int64 v10; // rdx
  void *v11; // rdi
  int TriggerType; // ebx
  CMemoryDiagnosticHandler *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rax
  unsigned __int64 i; // rcx
  unsigned __int64 v18; // rbx
  __int64 v19; // r8
  CMemoryDiagnosticHandler *v20; // rcx
  __int64 v21; // rdx
  CMemoryDiagnosticHandler *v22; // rcx
  int v23; // eax
  CMemoryDiagnosticHandler *v24; // rcx
  __int64 v25; // r8
  int v26; // eax
  unsigned int v28; // [rsp+30h] [rbp-59h] BYREF
  int v29; // [rsp+34h] [rbp-55h] BYREF
  _BYTE v30[8]; // [rsp+38h] [rbp-51h] BYREF
  __int64 v31; // [rsp+40h] [rbp-49h] BYREF
  __int64 v32; // [rsp+48h] [rbp-41h] BYREF
  void *v33[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v34; // [rsp+60h] [rbp-29h]
  _BYTE v35[32]; // [rsp+70h] [rbp-19h] BYREF
  __int64 *v36; // [rsp+90h] [rbp+7h]
  int v37; // [rsp+98h] [rbp+Fh]
  int v38; // [rsp+9Ch] [rbp+13h]
  int *v39; // [rsp+A0h] [rbp+17h]
  int v40; // [rsp+A8h] [rbp+1Fh]
  int v41; // [rsp+ACh] [rbp+23h]

  v2 = 0;
  *(_OWORD *)v33 = 0;
  v34 = 0;
  v29 = 0;
  CMemoryDiagnosticHandler::InitializeSettings(this);
  AcquireSRWLockExclusive(&stru_180030E28);
  v3 = dword_180030E0C;
  if ( !dword_180030E0C )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180030050);
    v3 = dword_180030E0C;
  }
  dword_180030E0C = v3 + 1;
  ReleaseSRWLockExclusive(&stru_180030E28);
  v30[1] = 1;
  v4 = 0;
  v31 = 0;
  v32 = 0;
  v5 = 0;
  v28 = 0;
  ElementData = BcdOpenSystemStore(&v31);
  v8 = ElementData;
  if ( ElementData < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v10 = 62;
LABEL_20:
    WPP_SF_D(*((_QWORD *)v9 + 2), v10, v9, (unsigned int)ElementData);
    v9 = WPP_GLOBAL_Control;
LABEL_21:
    v4 = v8 | 0x10000000;
    if ( v8 >= 0 || !v5 )
      goto LABEL_25;
    operator delete(v5, (unsigned __int64)v7);
LABEL_24:
    v9 = WPP_GLOBAL_Control;
LABEL_25:
    v11 = v33[1];
    goto LABEL_26;
  }
  ElementData = BcdOpenObject(v31, &GUID_BAD_MEMORY_GROUP, &v32);
  v8 = ElementData;
  if ( ElementData < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v10 = 63;
    goto LABEL_20;
  }
  ElementData = BcdGetElementData(v32, 385875978, 0, &v28);
  v8 = ElementData;
  if ( ElementData == -1073741275 )
    goto LABEL_24;
  if ( ElementData != -1073741789 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v10 = 64;
    goto LABEL_20;
  }
  v5 = (__int64 *)operator new[](v28);
  ElementData = BcdGetElementData(v32, 385875978, v5, &v28);
  v8 = ElementData;
  if ( ElementData < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v10 = 66;
    goto LABEL_20;
  }
  v33[0] = v5;
  v11 = (void *)((unsigned __int64)v28 >> 3);
  v33[1] = v11;
  v2 = 1;
  v34 = 1;
  qsort(v5, (size_t)v11, 8u, CMemoryDiagnosticHandler::static_PageNumberCompare);
  v16 = *v5;
  for ( i = 1; i < (unsigned __int64)v11; ++i )
  {
    if ( v5[i] > (unsigned __int64)(v16 + 1) )
      v34 = ++v2;
    v16 = v5[i];
  }
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
    {
      WPP_SF_PP(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_GLOBAL_Control, v11, v2);
      v9 = WPP_GLOBAL_Control;
    }
    v18 = 0;
    if ( v11 )
    {
      do
      {
        if ( v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
        {
          WPP_SF_P(*((_QWORD *)v9 + 2), 68, v9, v5[v18]);
          v9 = WPP_GLOBAL_Control;
        }
        ++v18;
      }
      while ( v18 < (unsigned __int64)v11 );
    }
  }
LABEL_26:
  TriggerType = v4;
  if ( v32 )
  {
    BcdCloseObject(v32);
    v9 = WPP_GLOBAL_Control;
  }
  v13 = (CMemoryDiagnosticHandler *)v31;
  if ( v31 )
  {
    BcdCloseStore(v31);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v4 < 0 && v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
  {
    v14 = 10;
    v15 = (unsigned int)v4;
LABEL_86:
    WPP_SF_D(*((_QWORD *)v9 + 2), v14, v9, v15);
    goto LABEL_87;
  }
  TriggerType = v4;
  if ( v4 < 0 )
    goto LABEL_88;
  if ( (unsigned __int64)v11 >= *((unsigned int *)this + 15) || v2 >= 0x80 )
  {
    if ( v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v9 + 2), 85);
    v23 = CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(v13, L"RunFullMemoryDiagnostic");
    if ( v23 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, v25, (unsigned int)v23);
      }
    }
    v26 = CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(v24, L"ProcessMemoryDiagnosticEvents");
    TriggerType = v26;
    if ( v26 >= 0 )
      goto LABEL_87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v14 = 87;
      v15 = (unsigned int)v26;
      goto LABEL_86;
    }
  }
  else
  {
    TriggerType = CMemoryDiagnosticHandler::GetTriggerType(this);
    if ( TriggerType < 0 )
    {
LABEL_87:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_88;
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, v19, *((unsigned int *)this + 26));
    }
    if ( *((_DWORD *)this + 26) != 1 || (TriggerType = CMemoryDiagnosticHandler::EventScanCriteriaMet(this, &v29), v29) )
    {
      TriggerType = CMemoryDiagnosticHandler::UpdateLastScanTime(v20);
      if ( TriggerType >= 0 )
        goto LABEL_68;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90);
        v9 = WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)this + 26) != 1 )
      {
LABEL_68:
        TriggerType = CMemoryDiagnosticHandler::QueryBadPageList(
                        v22,
                        (unsigned __int64 **)this + 11,
                        (unsigned __int64 *)this + 10);
        if ( TriggerType >= 0 )
        {
          TriggerType = CMemoryDiagnosticHandler::StartMemoryTest(this, v7);
          if ( TriggerType >= 0 )
          {
            if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92);
            }
            TriggerType = CMemoryDiagnosticHandler::ProcessMemoryTestResults((unsigned __int64 **)this);
            if ( TriggerType >= 0 )
              CMemoryDiagnosticHandler::ReportMemoryTestTelemetry(this, (struct _BCD_BADMEM_LIST *)v33);
          }
        }
        goto LABEL_87;
      }
      if ( v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      {
        v21 = 91;
        goto LABEL_59;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v21 = 89;
LABEL_59:
        WPP_SF_(*((_QWORD *)v9 + 2), v21);
        goto LABEL_87;
      }
    }
  }
LABEL_88:
  if ( v33[0] )
  {
    operator delete(v33[0], (unsigned __int64)v7);
    v9 = WPP_GLOBAL_Control;
  }
  if ( TriggerType < 0 )
  {
    if ( (unsigned int)dword_180030050 > 5
      && (qword_180030060 & 0x400000000000LL) != 0
      && (qword_180030068 & 0x400000000000LL) == qword_180030068 )
    {
      v29 = TriggerType;
      v31 = 0x1000000;
      v39 = &v29;
      v40 = 4;
      v41 = 0;
      v36 = &v31;
      v37 = 8;
      v38 = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_180030050, &unk_18002B1C5, 0, 0, 4, v35);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)v9 + 2), 10, v9, (unsigned int)TriggerType);
  }
  wil::details::lambda_call__lambda_38394c3fcc9c391f39527cda130a4d23___::_lambda_call__lambda_38394c3fcc9c391f39527cda130a4d23___(v30);
  return (unsigned int)TriggerType;
}

```

## disassembly

```asm
0x18001ead0  mov     [rsp-8+arg_8], rbx
0x18001ead5  mov     [rsp-8+arg_10], rsi
0x18001eada  push    rbp
0x18001eadb  push    rdi
0x18001eadc  push    r12
0x18001eade  push    r14
0x18001eae0  push    r15
0x18001eae2  lea     rbp, [rsp-37h]
0x18001eae7  sub     rsp, 0C0h
0x18001eaee  mov     rax, cs:__security_cookie
0x18001eaf5  xor     rax, rsp
0x18001eaf8  mov     [rbp+57h+var_30], rax
0x18001eafc  mov     rsi, rcx
0x18001eaff  xorps   xmm0, xmm0
0x18001eb02  xor     r12d, r12d
0x18001eb05  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18001eb09  mov     [rbp+57h+var_80], r12
0x18001eb0d  and     dword ptr [rbp+57h+var_B0+4], r12d
0x18001eb11  call    ?InitializeSettings@CMemoryDiagnosticHandler@@AEAAXXZ; CMemoryDiagnosticHandler::InitializeSettings(void)
0x18001eb16  lea     rcx, stru_180030E28; SRWLock
0x18001eb1d  call    cs:__imp_AcquireSRWLockExclusive
0x18001eb24  nop     dword ptr [rax+rax+00h]
0x18001eb29  mov     eax, cs:dword_180030E0C
0x18001eb2f  test    eax, eax
0x18001eb31  jnz     short loc_18001EB45
0x18001eb33  lea     rcx, dword_180030050; CallbackContext
0x18001eb3a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001eb3f  mov     eax, cs:dword_180030E0C
0x18001eb45  inc     eax
0x18001eb47  mov     cs:dword_180030E0C, eax
0x18001eb4d  lea     rcx, stru_180030E28; SRWLock
0x18001eb54  call    cs:__imp_ReleaseSRWLockExclusive
0x18001eb5b  nop     dword ptr [rax+rax+00h]
0x18001eb60  mov     [rbp+57h+var_A7], 1
0x18001eb64  xor     r14d, r14d
0x18001eb67  and     [rbp+57h+var_A0], r14
0x18001eb6b  and     [rbp+57h+var_98], r14
0x18001eb6f  xor     r15d, r15d
0x18001eb72  and     dword ptr [rbp+57h+var_B0], r14d
0x18001eb76  lea     rcx, [rbp+57h+var_A0]
0x18001eb7a  call    cs:__imp_BcdOpenSystemStore
0x18001eb81  nop     dword ptr [rax+rax+00h]
0x18001eb86  mov     ebx, eax
0x18001eb88  lea     rdi, WPP_GLOBAL_Control
0x18001eb8f  test    eax, eax
0x18001eb91  jns     short loc_18001EBB7
0x18001eb93  mov     r8, cs:WPP_GLOBAL_Control
0x18001eb9a  cmp     r8, rdi
0x18001eb9d  jz      loc_18001ECA3
0x18001eba3  test    byte ptr [r8+1Ch], 1
0x18001eba8  jz      loc_18001ECA3
0x18001ebae  lea     edx, [r14+3Eh]
0x18001ebb2  jmp     loc_18001EC90
0x18001ebb7  lea     r8, [rbp+57h+var_98]
0x18001ebbb  lea     rdx, GUID_BAD_MEMORY_GROUP
0x18001ebc2  mov     rcx, [rbp+57h+var_A0]
0x18001ebc6  call    cs:__imp_BcdOpenObject
0x18001ebcd  nop     dword ptr [rax+rax+00h]
0x18001ebd2  mov     ebx, eax
0x18001ebd4  test    eax, eax
0x18001ebd6  jns     short loc_18001EBFD
0x18001ebd8  mov     r8, cs:WPP_GLOBAL_Control
0x18001ebdf  cmp     r8, rdi
0x18001ebe2  jz      loc_18001ECA3
0x18001ebe8  test    byte ptr [r8+1Ch], 1
0x18001ebed  jz      loc_18001ECA3
0x18001ebf3  mov     edx, 3Fh ; '?'
0x18001ebf8  jmp     loc_18001EC90
0x18001ebfd  lea     r9, [rbp+57h+var_B0]
0x18001ec01  xor     r8d, r8d
0x18001ec04  mov     edx, 1700000Ah
0x18001ec09  mov     rcx, [rbp+57h+var_98]
0x18001ec0d  call    cs:__imp_BcdGetElementData
0x18001ec14  nop     dword ptr [rax+rax+00h]
0x18001ec19  mov     ebx, eax
0x18001ec1b  cmp     eax, 0C0000225h
0x18001ec20  jz      loc_18001ECBB
0x18001ec26  cmp     eax, 0C0000023h
0x18001ec2b  jz      short loc_18001EC47
0x18001ec2d  mov     r8, cs:WPP_GLOBAL_Control
0x18001ec34  cmp     r8, rdi
0x18001ec37  jz      short loc_18001ECA3
0x18001ec39  test    byte ptr [r8+1Ch], 1
0x18001ec3e  jz      short loc_18001ECA3
0x18001ec40  mov     edx, 40h ; '@'
0x18001ec45  jmp     short loc_18001EC90
0x18001ec47  mov     ecx, dword ptr [rbp+57h+var_B0]; unsigned __int64
0x18001ec4a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001ec4f  mov     r15, rax
0x18001ec52  lea     r9, [rbp+57h+var_B0]
0x18001ec56  mov     r8, rax
0x18001ec59  mov     edx, 1700000Ah
0x18001ec5e  mov     rcx, [rbp+57h+var_98]
0x18001ec62  call    cs:__imp_BcdGetElementData
0x18001ec69  nop     dword ptr [rax+rax+00h]
0x18001ec6e  mov     ebx, eax
0x18001ec70  test    eax, eax
0x18001ec72  jns     loc_18001ED32
0x18001ec78  mov     r8, cs:WPP_GLOBAL_Control
0x18001ec7f  cmp     r8, rdi
0x18001ec82  jz      short loc_18001ECA3
0x18001ec84  test    byte ptr [r8+1Ch], 1
0x18001ec89  jz      short loc_18001ECA3
0x18001ec8b  mov     edx, 42h ; 'B'
0x18001ec90  mov     r9d, eax
0x18001ec93  mov     rcx, [r8+10h]
0x18001ec97  call    WPP_SF_D
0x18001ec9c  mov     r8, cs:WPP_GLOBAL_Control
0x18001eca3  or      ebx, 10000000h
0x18001eca9  mov     r14d, ebx
0x18001ecac  jge     short loc_18001ECC2
0x18001ecae  test    r15, r15
0x18001ecb1  jz      short loc_18001ECC2
0x18001ecb3  mov     rcx, r15; void *
0x18001ecb6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ecbb  mov     r8, cs:WPP_GLOBAL_Control
0x18001ecc2  mov     rdi, [rbp+57h+var_90+8]
0x18001ecc6  mov     ebx, r14d
0x18001ecc9  mov     rcx, [rbp+57h+var_98]
0x18001eccd  test    rcx, rcx
0x18001ecd0  jz      short loc_18001ECE5
0x18001ecd2  call    cs:__imp_BcdCloseObject
0x18001ecd9  nop     dword ptr [rax+rax+00h]
0x18001ecde  mov     r8, cs:WPP_GLOBAL_Control
0x18001ece5  mov     rcx, [rbp+57h+var_A0]
0x18001ece9  test    rcx, rcx
0x18001ecec  jz      short loc_18001ED01
0x18001ecee  call    cs:__imp_BcdCloseStore
0x18001ecf5  nop     dword ptr [rax+rax+00h]
0x18001ecfa  mov     r8, cs:WPP_GLOBAL_Control
0x18001ed01  test    r14d, r14d
0x18001ed04  jns     loc_18001EE11
0x18001ed0a  lea     r15, WPP_GLOBAL_Control
0x18001ed11  cmp     r8, r15
0x18001ed14  jz      loc_18001EE18
0x18001ed1a  test    byte ptr [r8+1Ch], 1
0x18001ed1f  jz      loc_18001EE18
0x18001ed25  mov     edx, 0Ah
0x18001ed2a  mov     r9d, ebx
0x18001ed2d  jmp     loc_18001EFF5
0x18001ed32  mov     [rbp+57h+var_90], r15
0x18001ed36  mov     edi, dword ptr [rbp+57h+var_B0]
0x18001ed39  shr     rdi, 3
0x18001ed3d  mov     [rbp+57h+var_90+8], rdi
0x18001ed41  mov     ebx, 1
0x18001ed46  mov     r12d, ebx
0x18001ed49  mov     [rbp+57h+var_80], rbx
0x18001ed4d  lea     r9, ?static_PageNumberCompare@CMemoryDiagnosticHandler@@CAHPEBX0@Z; CompareFunction
0x18001ed54  lea     r8d, [rbx+7]; SizeOfElements
0x18001ed58  mov     rdx, rdi; NumOfElements
0x18001ed5b  mov     rcx, r15; Base
0x18001ed5e  call    cs:__imp_qsort
0x18001ed65  nop     dword ptr [rax+rax+00h]
0x18001ed6a  mov     rax, [r15]
0x18001ed6d  mov     ecx, ebx
0x18001ed6f  cmp     rdi, rbx
0x18001ed72  jbe     short loc_18001ED90
0x18001ed74  inc     rax
0x18001ed77  cmp     [r15+rcx*8], rax
0x18001ed7b  jbe     short loc_18001ED84
0x18001ed7d  add     r12, rbx
0x18001ed80  mov     [rbp+57h+var_80], r12
0x18001ed84  mov     rax, [r15+rcx*8]
0x18001ed88  add     rcx, rbx
0x18001ed8b  cmp     rcx, rdi
0x18001ed8e  jb      short loc_18001ED74
0x18001ed90  mov     r8, cs:WPP_GLOBAL_Control
0x18001ed97  test    byte ptr [r8+1Ch], 4
0x18001ed9c  jz      loc_18001ECC6
0x18001eda2  lea     rax, WPP_GLOBAL_Control
0x18001eda9  cmp     r8, rax
0x18001edac  jz      short loc_18001EDCD
0x18001edae  mov     [rsp+0E0h+var_C0], r12
0x18001edb3  mov     r9, rdi
0x18001edb6  mov     rcx, [r8+10h]
0x18001edba  call    WPP_SF_PP
0x18001edbf  mov     r8, cs:WPP_GLOBAL_Control
0x18001edc6  lea     rax, WPP_GLOBAL_Control
0x18001edcd  xor     ebx, ebx
0x18001edcf  test    rdi, rdi
0x18001edd2  jz      loc_18001ECC6
0x18001edd8  cmp     r8, rax
0x18001eddb  jz      short loc_18001EE04
0x18001eddd  test    byte ptr [r8+1Ch], 4
0x18001ede2  jz      short loc_18001EE04
0x18001ede4  mov     edx, 44h ; 'D'
0x18001ede9  mov     r9, [r15+rbx*8]
0x18001eded  mov     rcx, [r8+10h]
0x18001edf1  call    WPP_SF_P
0x18001edf6  mov     r8, cs:WPP_GLOBAL_Control
0x18001edfd  lea     rax, WPP_GLOBAL_Control
0x18001ee04  inc     rbx
0x18001ee07  cmp     rbx, rdi
0x18001ee0a  jb      short loc_18001EDD8
0x18001ee0c  jmp     loc_18001ECC6
0x18001ee11  lea     r15, WPP_GLOBAL_Control
0x18001ee18  mov     ebx, r14d
0x18001ee1b  test    r14d, r14d
0x18001ee1e  js      loc_18001F005
0x18001ee24  mov     eax, [rsi+3Ch]
0x18001ee27  cmp     rdi, rax
0x18001ee2a  jnb     loc_18001EF7B
0x18001ee30  cmp     r12, 80h
0x18001ee37  jnb     loc_18001EF7B
0x18001ee3d  mov     rcx, rsi; this
0x18001ee40  call    ?GetTriggerType@CMemoryDiagnosticHandler@@AEAAJXZ; CMemoryDiagnosticHandler::GetTriggerType(void)
0x18001ee45  mov     ebx, eax
0x18001ee47  test    eax, eax
0x18001ee49  js      loc_18001EFFE
0x18001ee4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee56  cmp     rcx, r15
0x18001ee59  jz      short loc_18001EE73
0x18001ee5b  test    byte ptr [rcx+1Ch], 4
0x18001ee5f  jz      short loc_18001EE73
0x18001ee61  mov     edx, 58h ; 'X'
0x18001ee66  mov     r9d, [rsi+68h]
0x18001ee6a  mov     rcx, [rcx+10h]
0x18001ee6e  call    WPP_SF_D
0x18001ee73  cmp     dword ptr [rsi+68h], 1
0x18001ee77  jnz     short loc_18001EEBB
0x18001ee79  lea     rdx, [rbp+57h+var_B0+4]; int *
0x18001ee7d  mov     rcx, rsi; this
0x18001ee80  call    ?EventScanCriteriaMet@CMemoryDiagnosticHandler@@AEAAJPEAH@Z; CMemoryDiagnosticHandler::EventScanCriteriaMet(int *)
0x18001ee85  mov     ebx, eax
0x18001ee87  cmp     dword ptr [rbp+57h+var_B0+4], 0
0x18001ee8b  jnz     short loc_18001EEBB
0x18001ee8d  mov     r8, cs:WPP_GLOBAL_Control
0x18001ee94  cmp     r8, r15
0x18001ee97  jz      loc_18001F005
0x18001ee9d  test    byte ptr [r8+1Ch], 4
0x18001eea2  jz      loc_18001F005
0x18001eea8  mov     edx, 59h ; 'Y'
0x18001eead  mov     rcx, [r8+10h]
0x18001eeb1  call    WPP_SF_
0x18001eeb6  jmp     loc_18001EFFE
0x18001eebb  call    ?UpdateLastScanTime@CMemoryDiagnosticHandler@@AEAAJXZ; CMemoryDiagnosticHandler::UpdateLastScanTime(void)
0x18001eec0  mov     ebx, eax
0x18001eec2  test    eax, eax
0x18001eec4  jns     short loc_18001EF0F
0x18001eec6  mov     r8, cs:WPP_GLOBAL_Control
0x18001eecd  cmp     r8, r15
0x18001eed0  jz      short loc_18001EEEE
0x18001eed2  test    byte ptr [r8+1Ch], 2
0x18001eed7  jz      short loc_18001EEEE
0x18001eed9  mov     edx, 5Ah ; 'Z'
0x18001eede  mov     rcx, [r8+10h]
0x18001eee2  call    WPP_SF_
0x18001eee7  mov     r8, cs:WPP_GLOBAL_Control
0x18001eeee  cmp     dword ptr [rsi+68h], 1
0x18001eef2  jnz     short loc_18001EF0F
0x18001eef4  cmp     r8, r15
0x18001eef7  jz      loc_18001F005
0x18001eefd  test    byte ptr [r8+1Ch], 1
0x18001ef02  jz      loc_18001F005
0x18001ef08  mov     edx, 5Bh ; '['
0x18001ef0d  jmp     short loc_18001EEAD
0x18001ef0f  lea     r8, [rsi+50h]; unsigned __int64 *
0x18001ef13  lea     rdx, [rsi+58h]; unsigned __int64 **
0x18001ef17  call    ?QueryBadPageList@CMemoryDiagnosticHandler@@AEAAJPEAPEA_KPEA_K@Z; CMemoryDiagnosticHandler::QueryBadPageList(unsigned __int64 * *,unsigned __int64 *)
0x18001ef1c  mov     ebx, eax
0x18001ef1e  test    eax, eax
0x18001ef20  js      loc_18001EFFE
0x18001ef26  mov     rcx, rsi; this
0x18001ef29  call    ?StartMemoryTest@CMemoryDiagnosticHandler@@AEAAJXZ; CMemoryDiagnosticHandler::StartMemoryTest(void)
0x18001ef2e  mov     ebx, eax
0x18001ef30  test    eax, eax
0x18001ef32  js      loc_18001EFFE
0x18001ef38  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef3f  cmp     rcx, r15
0x18001ef42  jz      short loc_18001EF58
0x18001ef44  test    byte ptr [rcx+1Ch], 4
0x18001ef48  jz      short loc_18001EF58
0x18001ef4a  mov     edx, 5Ch ; '\'
0x18001ef4f  mov     rcx, [rcx+10h]
0x18001ef53  call    WPP_SF_
0x18001ef58  mov     rcx, rsi; this
0x18001ef5b  call    ?ProcessMemoryTestResults@CMemoryDiagnosticHandler@@AEAAJXZ; CMemoryDiagnosticHandler::ProcessMemoryTestResults(void)
0x18001ef60  mov     ebx, eax
0x18001ef62  test    eax, eax
0x18001ef64  js      loc_18001EFFE
0x18001ef6a  lea     rdx, [rbp+57h+var_90]; struct _BCD_BADMEM_LIST *
0x18001ef6e  mov     rcx, rsi; this
0x18001ef71  call    ?ReportMemoryTestTelemetry@CMemoryDiagnosticHandler@@AEAAXPEAU_BCD_BADMEM_LIST@@@Z; CMemoryDiagnosticHandler::ReportMemoryTestTelemetry(_BCD_BADMEM_LIST *)
0x18001ef76  jmp     loc_18001EFFE
0x18001ef7b  cmp     r8, r15
0x18001ef7e  jz      short loc_18001EF95
0x18001ef80  test    byte ptr [r8+1Ch], 4
0x18001ef85  jz      short loc_18001EF95
0x18001ef87  mov     edx, 55h ; 'U'
0x18001ef8c  mov     rcx, [r8+10h]
0x18001ef90  call    WPP_SF_
0x18001ef95  lea     rdx, aRunfullmemoryd; "RunFullMemoryDiagnostic"
0x18001ef9c  call    ?ConfigureMemoryDiagnosticTask@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z; CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(ushort const *,int)
0x18001efa1  test    eax, eax
0x18001efa3  jns     short loc_18001EFC8
0x18001efa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efac  cmp     rcx, r15
0x18001efaf  jz      short loc_18001EFC8
0x18001efb1  test    byte ptr [rcx+1Ch], 2
0x18001efb5  jz      short loc_18001EFC8
  ... truncated ...
```
