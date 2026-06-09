# CMemoryDiagnosticHandler::Worker(void)

- ea: `0x18001d7a0`
- end: `0x18001ddaa`
- name: `?Worker@CMemoryDiagnosticHandler@@EEAAJXZ`
- size: `1546`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001940`
- `0x180001a7c`
- `0x180002e50`
- `0x180003294`
- `0x1800032cc`
- `0x18001a5a0`
- `0x18001aa94`
- `0x18001bcd0`
- `0x18001be90`
- `0x18001c310`
- `0x18001cae4`
- `0x18001cd88`
- `0x18001d094`
- `0x18001d378`
- `0x18001d7a0`
- `0x18001e21c`
- `0x18001e24c`
- `0x18001e290`
- `0x18001e37c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001d9a7`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001d9a7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001d7ed`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001dd3a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001d7ed`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001dd3a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d81e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001dd7a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d81e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001dd7a`
- `ADVAPI32!EventUnregister` at `0x18001dd6d`
- `ADVAPI32!EventUnregister` at `0x18001dd6d`
- `bcd!BcdCloseObject` at `0x18001da53`
- `bcd!BcdCloseObject` at `0x18001da53`
- `bcd!BcdOpenSystemStore` at `0x18001d843`
- `bcd!BcdOpenSystemStore` at `0x18001d843`
- `bcd!BcdCloseStore` at `0x18001da6c`
- `bcd!BcdCloseStore` at `0x18001da6c`
- `bcd!BcdGetElementData` at `0x18001d8ca`
- `bcd!BcdGetElementData` at `0x18001d916`
- `bcd!BcdGetElementData` at `0x18001d8ca`
- `bcd!BcdGetElementData` at `0x18001d916`
- `bcd!BcdOpenObject` at `0x18001d888`
- `bcd!BcdOpenObject` at `0x18001d888`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::Worker(CMemoryDiagnosticHandler *this)
{
  unsigned __int64 v2; // r12
  int v3; // eax
  __int64 *v4; // r15
  int ElementData; // eax
  __int64 v6; // r8
  int v7; // edi
  CMemoryDiagnosticHandler *v8; // rcx
  __int64 v9; // rdx
  int TriggerType; // ebx
  void *v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned __int64 i; // rcx
  unsigned __int64 v15; // r14
  __int64 v16; // rdx
  __int64 v17; // r9
  CMemoryDiagnosticHandler *v18; // rcx
  CMemoryDiagnosticHandler *v19; // rcx
  __int64 v20; // rdx
  int v21; // eax
  CMemoryDiagnosticHandler *v22; // rcx
  __int64 v23; // r8
  int v24; // eax
  REGHANDLE v25; // rcx
  __int64 v27; // [rsp+30h] [rbp-59h] BYREF
  __int64 v28; // [rsp+38h] [rbp-51h] BYREF
  __int64 v29; // [rsp+40h] [rbp-49h] BYREF
  char v30; // [rsp+49h] [rbp-40h]
  void *Block[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v32; // [rsp+60h] [rbp-29h]
  _BYTE v33[32]; // [rsp+70h] [rbp-19h] BYREF
  __int64 *v34; // [rsp+90h] [rbp+7h]
  __int64 v35; // [rsp+98h] [rbp+Fh]
  __int64 *v36; // [rsp+A0h] [rbp+17h]
  __int64 v37; // [rsp+A8h] [rbp+1Fh]

  v2 = 0;
  *(_OWORD *)Block = 0;
  v32 = 0;
  LODWORD(v27) = 0;
  CMemoryDiagnosticHandler::InitializeSettings(this);
  AcquireSRWLockExclusive(&stru_18002F938);
  v3 = dword_18002F91C;
  if ( !dword_18002F91C )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18002F050);
    v3 = dword_18002F91C;
  }
  dword_18002F91C = v3 + 1;
  ReleaseSRWLockExclusive(&stru_18002F938);
  v30 = 1;
  v28 = 0;
  v29 = 0;
  v4 = 0;
  HIDWORD(v27) = 0;
  ElementData = BcdOpenSystemStore(&v28);
  v7 = ElementData;
  if ( ElementData < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v9 = 62;
    goto LABEL_20;
  }
  ElementData = BcdOpenObject(v28, &GUID_BAD_MEMORY_GROUP, &v29);
  v7 = ElementData;
  if ( ElementData < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v9 = 63;
    goto LABEL_20;
  }
  TriggerType = 0;
  ElementData = BcdGetElementData(v29, 385875978, 0, (char *)&v27 + 4);
  v7 = ElementData;
  if ( ElementData == -1073741275 )
  {
LABEL_24:
    v11 = Block[1];
    v8 = WPP_GLOBAL_Control;
    goto LABEL_38;
  }
  if ( ElementData != -1073741789 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v9 = 64;
    goto LABEL_20;
  }
  v4 = (__int64 *)operator new[](HIDWORD(v27));
  ElementData = BcdGetElementData(v29, 385875978, v4, (char *)&v27 + 4);
  v7 = ElementData;
  if ( ElementData >= 0 )
  {
    Block[0] = v4;
    v11 = (void *)((unsigned __int64)HIDWORD(v27) >> 3);
    Block[1] = v11;
    v2 = 1;
    v32 = 1;
    qsort(v4, (size_t)v11, 8u, CMemoryDiagnosticHandler::static_PageNumberCompare);
    v13 = *v4;
    for ( i = 1; i < (unsigned __int64)v11; ++i )
    {
      if ( v4[i] > (unsigned __int64)(v13 + 1) )
        v32 = ++v2;
      v13 = v4[i];
    }
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
      {
        WPP_SF_PP(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v6, v11, v2);
        v8 = WPP_GLOBAL_Control;
      }
      v15 = 0;
      if ( v11 )
      {
        do
        {
          if ( v8 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
          {
            WPP_SF_P(*((_QWORD *)v8 + 2), 68, v6, v4[v15]);
            v8 = WPP_GLOBAL_Control;
          }
          ++v15;
        }
        while ( v15 < (unsigned __int64)v11 );
      }
    }
    goto LABEL_38;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 66;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, v6, (unsigned int)ElementData);
    v8 = WPP_GLOBAL_Control;
  }
LABEL_21:
  TriggerType = v7 | 0x10000000;
  if ( v7 < 0 && v4 )
  {
    operator delete(v4);
    goto LABEL_24;
  }
  v11 = Block[1];
LABEL_38:
  if ( v29 )
  {
    BcdCloseObject(v29);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v28 )
  {
    BcdCloseStore(v28);
    v8 = WPP_GLOBAL_Control;
  }
  if ( TriggerType >= 0 )
  {
    if ( (unsigned __int64)v11 < *((unsigned int *)this + 15) && v2 < 0x80 )
    {
      TriggerType = CMemoryDiagnosticHandler::GetTriggerType(this);
      if ( TriggerType < 0 )
        goto LABEL_86;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, v6, *((unsigned int *)this + 26));
      }
      if ( *((_DWORD *)this + 26) != 1
        || (TriggerType = CMemoryDiagnosticHandler::EventScanCriteriaMet(this, (int *)&v27), (_DWORD)v27) )
      {
        TriggerType = CMemoryDiagnosticHandler::UpdateLastScanTime(v18);
        if ( TriggerType >= 0 )
          goto LABEL_67;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90);
          v19 = WPP_GLOBAL_Control;
        }
        if ( *((_DWORD *)this + 26) != 1 )
        {
LABEL_67:
          TriggerType = CMemoryDiagnosticHandler::QueryBadPageList(
                          v19,
                          (unsigned __int64 **)this + 11,
                          (unsigned __int64 *)this + 10);
          if ( TriggerType >= 0 )
          {
            TriggerType = CMemoryDiagnosticHandler::StartMemoryTest(this);
            if ( TriggerType >= 0 )
            {
              if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92);
              }
              TriggerType = CMemoryDiagnosticHandler::ProcessMemoryTestResults(this);
              if ( TriggerType >= 0 )
                CMemoryDiagnosticHandler::ReportMemoryTestTelemetry(this, (struct _BCD_BADMEM_LIST *)Block);
            }
          }
          goto LABEL_86;
        }
        if ( v19 == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control || (*((_BYTE *)v19 + 28) & 1) == 0 )
          goto LABEL_86;
        v20 = 91;
      }
      else
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_86;
        }
        v20 = 89;
      }
      WPP_SF_(*((_QWORD *)v19 + 2), v20);
      goto LABEL_86;
    }
    if ( v8 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v8 + 2), 85);
    v21 = CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(v8, L"RunFullMemoryDiagnostic", v6);
    if ( v21 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, v23, (unsigned int)v21);
      }
    }
    v24 = CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(v22, L"ProcessMemoryDiagnosticEvents", v23);
    TriggerType = v24;
    if ( v24 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v16 = 87;
        v17 = (unsigned int)v24;
        goto LABEL_85;
      }
    }
  }
  else if ( v8 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
  {
    v16 = 10;
    v17 = (unsigned int)TriggerType;
LABEL_85:
    WPP_SF_d(*((_QWORD *)v8 + 2), v16, v6, v17);
  }
LABEL_86:
  if ( Block[0] )
    operator delete(Block[0]);
  if ( TriggerType < 0 )
  {
    if ( (unsigned int)dword_18002F050 > 5
      && (qword_18002F060 & 0x400000000000LL) != 0
      && (qword_18002F068 & 0x400000000000LL) == qword_18002F068 )
    {
      LODWORD(v27) = TriggerType;
      v36 = &v27;
      v37 = 4;
      v34 = &v28;
      v35 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_18002F050, word_18002A61A, 0, 0, 4, v33, v27, 0x1000000);
    }
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v6, (unsigned int)TriggerType);
    }
  }
  AcquireSRWLockExclusive(&stru_18002F938);
  if ( !--dword_18002F91C )
  {
    v25 = RegHandle;
    dword_18002F050 = 0;
    RegHandle = 0;
    EventUnregister(v25);
  }
  ReleaseSRWLockExclusive(&stru_18002F938);
  return (unsigned int)TriggerType;
}

```

## disassembly

```asm
0x18001d7a0  mov     [rsp-8+arg_8], rbx
0x18001d7a5  mov     [rsp-8+arg_10], rsi
0x18001d7aa  push    rbp
0x18001d7ab  push    rdi
0x18001d7ac  push    r12
0x18001d7ae  push    r14
0x18001d7b0  push    r15
0x18001d7b2  lea     rbp, [rsp-37h]
0x18001d7b7  sub     rsp, 0C0h
0x18001d7be  mov     rax, cs:__security_cookie
0x18001d7c5  xor     rax, rsp
0x18001d7c8  mov     [rbp+57h+var_30], rax
0x18001d7cc  mov     rsi, rcx
0x18001d7cf  xorps   xmm0, xmm0
0x18001d7d2  xor     r12d, r12d
0x18001d7d5  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18001d7d9  mov     [rbp+57h+var_80], r12
0x18001d7dd  mov     [rbp+57h+var_B0], r12d
0x18001d7e1  call    ?InitializeSettings@CMemoryDiagnosticHandler@@AEAAXXZ; CMemoryDiagnosticHandler::InitializeSettings(void)
0x18001d7e6  lea     rcx, stru_18002F938; SRWLock
0x18001d7ed  call    cs:__imp_AcquireSRWLockExclusive
0x18001d7f3  mov     eax, cs:dword_18002F91C
0x18001d7f9  test    eax, eax
0x18001d7fb  jnz     short loc_18001D80F
0x18001d7fd  lea     rcx, dword_18002F050; CallbackContext
0x18001d804  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001d809  mov     eax, cs:dword_18002F91C
0x18001d80f  inc     eax
0x18001d811  mov     cs:dword_18002F91C, eax
0x18001d817  lea     rcx, stru_18002F938; SRWLock
0x18001d81e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d824  mov     [rbp+57h+var_97], 1
0x18001d828  mov     qword ptr [rbp+57h+var_AC+4], 0
0x18001d830  mov     [rbp+57h+var_A0], 0
0x18001d838  xor     r15d, r15d
0x18001d83b  mov     dword ptr [rbp+57h+var_AC], r15d
0x18001d83f  lea     rcx, [rbp+57h+var_AC+4]
0x18001d843  call    cs:__imp_BcdOpenSystemStore
0x18001d849  mov     edi, eax
0x18001d84b  lea     r14, WPP_GLOBAL_Control
0x18001d852  test    eax, eax
0x18001d854  jns     short loc_18001D879
0x18001d856  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d85d  cmp     rcx, r14
0x18001d860  jz      loc_18001D94C
0x18001d866  test    byte ptr [rcx+1Ch], 1
0x18001d86a  jz      loc_18001D94C
0x18001d870  lea     edx, [r15+3Eh]
0x18001d874  jmp     loc_18001D939
0x18001d879  lea     r8, [rbp+57h+var_A0]
0x18001d87d  lea     rdx, GUID_BAD_MEMORY_GROUP
0x18001d884  mov     rcx, qword ptr [rbp+57h+var_AC+4]
0x18001d888  call    cs:__imp_BcdOpenObject
0x18001d88e  mov     edi, eax
0x18001d890  test    eax, eax
0x18001d892  jns     short loc_18001D8B8
0x18001d894  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d89b  cmp     rcx, r14
0x18001d89e  jz      loc_18001D94C
0x18001d8a4  test    byte ptr [rcx+1Ch], 1
0x18001d8a8  jz      loc_18001D94C
0x18001d8ae  mov     edx, 3Fh ; '?'
0x18001d8b3  jmp     loc_18001D939
0x18001d8b8  xor     ebx, ebx
0x18001d8ba  lea     r9, [rbp+57h+var_AC]
0x18001d8be  xor     r8d, r8d
0x18001d8c1  mov     edx, 1700000Ah
0x18001d8c6  mov     rcx, [rbp+57h+var_A0]
0x18001d8ca  call    cs:__imp_BcdGetElementData
0x18001d8d0  mov     edi, eax
0x18001d8d2  cmp     eax, 0C0000225h
0x18001d8d7  jz      loc_18001D963
0x18001d8dd  cmp     eax, 0C0000023h
0x18001d8e2  jz      short loc_18001D8FB
0x18001d8e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8eb  cmp     rcx, r14
0x18001d8ee  jz      short loc_18001D94C
0x18001d8f0  test    byte ptr [rcx+1Ch], 1
0x18001d8f4  jz      short loc_18001D94C
0x18001d8f6  lea     edx, [rbx+40h]
0x18001d8f9  jmp     short loc_18001D939
0x18001d8fb  mov     ecx, dword ptr [rbp+57h+var_AC]; unsigned __int64
0x18001d8fe  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d903  mov     r15, rax
0x18001d906  lea     r9, [rbp+57h+var_AC]
0x18001d90a  mov     r8, rax
0x18001d90d  mov     edx, 1700000Ah
0x18001d912  mov     rcx, [rbp+57h+var_A0]
0x18001d916  call    cs:__imp_BcdGetElementData
0x18001d91c  mov     edi, eax
0x18001d91e  test    eax, eax
0x18001d920  jns     short loc_18001D97C
0x18001d922  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d929  cmp     rcx, r14
0x18001d92c  jz      short loc_18001D94C
0x18001d92e  test    byte ptr [rcx+1Ch], 1
0x18001d932  jz      short loc_18001D94C
0x18001d934  mov     edx, 42h ; 'B'
0x18001d939  mov     r9d, eax
0x18001d93c  mov     rcx, [rcx+10h]
0x18001d940  call    WPP_SF_d
0x18001d945  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d94c  mov     ebx, edi
0x18001d94e  or      ebx, 10000000h
0x18001d954  jge     short loc_18001D973
0x18001d956  test    r15, r15
0x18001d959  jz      short loc_18001D973
0x18001d95b  mov     rcx, r15; Block
0x18001d95e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d963  mov     rdi, [rbp+57h+Block+8]
0x18001d967  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d96e  jmp     loc_18001DA47
0x18001d973  mov     rdi, [rbp+57h+Block+8]
0x18001d977  jmp     loc_18001DA47
0x18001d97c  mov     [rbp+57h+Block], r15
0x18001d980  mov     edi, dword ptr [rbp+57h+var_AC]
0x18001d983  shr     rdi, 3
0x18001d987  mov     [rbp+57h+Block+8], rdi
0x18001d98b  mov     r12d, 1
0x18001d991  mov     [rbp+57h+var_80], r12
0x18001d995  lea     r9, ?static_PageNumberCompare@CMemoryDiagnosticHandler@@CAHPEBX0@Z; CompareFunction
0x18001d99c  lea     r8d, [r12+7]; SizeOfElements
0x18001d9a1  mov     rdx, rdi; NumOfElements
0x18001d9a4  mov     rcx, r15; Base
0x18001d9a7  call    cs:__imp_qsort
0x18001d9ad  mov     rax, [r15]
0x18001d9b0  mov     ecx, r12d
0x18001d9b3  cmp     rdi, r12
0x18001d9b6  jbe     short loc_18001D9D4
0x18001d9b8  inc     rax
0x18001d9bb  cmp     [r15+rcx*8], rax
0x18001d9bf  jbe     short loc_18001D9C8
0x18001d9c1  inc     r12
0x18001d9c4  mov     [rbp+57h+var_80], r12
0x18001d9c8  mov     rax, [r15+rcx*8]
0x18001d9cc  inc     rcx
0x18001d9cf  cmp     rcx, rdi
0x18001d9d2  jb      short loc_18001D9B8
0x18001d9d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9db  test    byte ptr [rcx+1Ch], 4
0x18001d9df  jz      short loc_18001DA47
0x18001d9e1  cmp     rcx, r14
0x18001d9e4  jz      short loc_18001D9FE
0x18001d9e6  mov     [rsp+0E0h+var_C0], r12
0x18001d9eb  mov     r9, rdi
0x18001d9ee  mov     rcx, [rcx+10h]
0x18001d9f2  call    WPP_SF_PP
0x18001d9f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9fe  xor     r14d, r14d
0x18001da01  test    rdi, rdi
0x18001da04  jz      short loc_18001DA40
0x18001da06  lea     rax, WPP_GLOBAL_Control
0x18001da0d  cmp     rcx, rax
0x18001da10  jz      short loc_18001DA38
0x18001da12  test    byte ptr [rcx+1Ch], 4
0x18001da16  jz      short loc_18001DA38
0x18001da18  mov     edx, 44h ; 'D'
0x18001da1d  mov     r9, [r15+r14*8]
0x18001da21  mov     rcx, [rcx+10h]
0x18001da25  call    WPP_SF_P
0x18001da2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da31  lea     rax, WPP_GLOBAL_Control
0x18001da38  inc     r14
0x18001da3b  cmp     r14, rdi
0x18001da3e  jb      short loc_18001DA0D
0x18001da40  lea     r14, WPP_GLOBAL_Control
0x18001da47  mov     rax, [rbp+57h+var_A0]
0x18001da4b  test    rax, rax
0x18001da4e  jz      short loc_18001DA60
0x18001da50  mov     rcx, rax
0x18001da53  call    cs:__imp_BcdCloseObject
0x18001da59  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da60  mov     rax, qword ptr [rbp+57h+var_AC+4]
0x18001da64  test    rax, rax
0x18001da67  jz      short loc_18001DA79
0x18001da69  mov     rcx, rax
0x18001da6c  call    cs:__imp_BcdCloseStore
0x18001da72  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da79  mov     r15d, 0Ah
0x18001da7f  test    ebx, ebx
0x18001da81  jns     short loc_18001DAA1
0x18001da83  cmp     rcx, r14
0x18001da86  jz      short loc_18001DA99
0x18001da88  test    byte ptr [rcx+1Ch], 1
0x18001da8c  jz      short loc_18001DA99
0x18001da8e  mov     edx, r15d
0x18001da91  mov     r9d, ebx
0x18001da94  jmp     loc_18001DC6D
0x18001da99  test    ebx, ebx
0x18001da9b  js      loc_18001DC76
0x18001daa1  mov     eax, [rsi+3Ch]
0x18001daa4  cmp     rdi, rax
0x18001daa7  jnb     loc_18001DBF5
0x18001daad  cmp     r12, 80h
0x18001dab4  jnb     loc_18001DBF5
0x18001daba  mov     rcx, rsi; this
0x18001dabd  call    ?GetTriggerType@CMemoryDiagnosticHandler@@AEAAJXZ; CMemoryDiagnosticHandler::GetTriggerType(void)
0x18001dac2  mov     ebx, eax
0x18001dac4  test    eax, eax
0x18001dac6  js      loc_18001DC76
0x18001dacc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dad3  cmp     rcx, r14
0x18001dad6  jz      short loc_18001DAF0
0x18001dad8  test    byte ptr [rcx+1Ch], 4
0x18001dadc  jz      short loc_18001DAF0
0x18001dade  mov     edx, 58h ; 'X'
0x18001dae3  mov     r9d, [rsi+68h]
0x18001dae7  mov     rcx, [rcx+10h]
0x18001daeb  call    WPP_SF_d
0x18001daf0  cmp     dword ptr [rsi+68h], 1
0x18001daf4  jnz     short loc_18001DB37
0x18001daf6  lea     rdx, [rbp+57h+var_B0]; int *
0x18001dafa  mov     rcx, rsi; this
0x18001dafd  call    ?EventScanCriteriaMet@CMemoryDiagnosticHandler@@AEAAJPEAH@Z; CMemoryDiagnosticHandler::EventScanCriteriaMet(int *)
0x18001db02  mov     ebx, eax
0x18001db04  cmp     [rbp+57h+var_B0], 0
0x18001db08  jnz     short loc_18001DB37
0x18001db0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db11  cmp     rcx, r14
0x18001db14  jz      loc_18001DC76
0x18001db1a  test    byte ptr [rcx+1Ch], 4
0x18001db1e  jz      loc_18001DC76
0x18001db24  mov     edx, 59h ; 'Y'
0x18001db29  mov     rcx, [rcx+10h]
0x18001db2d  call    WPP_SF_
0x18001db32  jmp     loc_18001DC76
0x18001db37  call    ?UpdateLastScanTime@CMemoryDiagnosticHandler@@AEAAJXZ; CMemoryDiagnosticHandler::UpdateLastScanTime(void)
0x18001db3c  mov     ebx, eax
0x18001db3e  test    eax, eax
0x18001db40  jns     short loc_18001DB89
0x18001db42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db49  cmp     rcx, r14
0x18001db4c  jz      short loc_18001DB69
0x18001db4e  test    byte ptr [rcx+1Ch], 2
0x18001db52  jz      short loc_18001DB69
0x18001db54  mov     edx, 5Ah ; 'Z'
0x18001db59  mov     rcx, [rcx+10h]
0x18001db5d  call    WPP_SF_
0x18001db62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db69  cmp     dword ptr [rsi+68h], 1
0x18001db6d  jnz     short loc_18001DB89
0x18001db6f  cmp     rcx, r14
0x18001db72  jz      loc_18001DC76
0x18001db78  test    byte ptr [rcx+1Ch], 1
0x18001db7c  jz      loc_18001DC76
0x18001db82  mov     edx, 5Bh ; '['
0x18001db87  jmp     short loc_18001DB29
0x18001db89  lea     r8, [rsi+50h]; unsigned __int64 *
0x18001db8d  lea     rdx, [rsi+58h]; unsigned __int64 **
0x18001db91  call    ?QueryBadPageList@CMemoryDiagnosticHandler@@AEAAJPEAPEA_KPEA_K@Z; CMemoryDiagnosticHandler::QueryBadPageList(unsigned __int64 * *,unsigned __int64 *)
0x18001db96  mov     ebx, eax
0x18001db98  test    eax, eax
0x18001db9a  js      loc_18001DC76
0x18001dba0  mov     rcx, rsi; this
0x18001dba3  call    ?StartMemoryTest@CMemoryDiagnosticHandler@@AEAAJXZ; CMemoryDiagnosticHandler::StartMemoryTest(void)
0x18001dba8  mov     ebx, eax
0x18001dbaa  test    eax, eax
0x18001dbac  js      loc_18001DC76
0x18001dbb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbb9  cmp     rcx, r14
0x18001dbbc  jz      short loc_18001DBD2
0x18001dbbe  test    byte ptr [rcx+1Ch], 4
0x18001dbc2  jz      short loc_18001DBD2
0x18001dbc4  mov     edx, 5Ch ; '\'
0x18001dbc9  mov     rcx, [rcx+10h]
0x18001dbcd  call    WPP_SF_
0x18001dbd2  mov     rcx, rsi; this
0x18001dbd5  call    ?ProcessMemoryTestResults@CMemoryDiagnosticHandler@@AEAAJXZ; CMemoryDiagnosticHandler::ProcessMemoryTestResults(void)
0x18001dbda  mov     ebx, eax
0x18001dbdc  test    eax, eax
0x18001dbde  js      loc_18001DC76
0x18001dbe4  lea     rdx, [rbp+57h+Block]; struct _BCD_BADMEM_LIST *
0x18001dbe8  mov     rcx, rsi; this
0x18001dbeb  call    ?ReportMemoryTestTelemetry@CMemoryDiagnosticHandler@@AEAAXPEAU_BCD_BADMEM_LIST@@@Z; CMemoryDiagnosticHandler::ReportMemoryTestTelemetry(_BCD_BADMEM_LIST *)
0x18001dbf0  jmp     loc_18001DC76
0x18001dbf5  cmp     rcx, r14
0x18001dbf8  jz      short loc_18001DC0E
0x18001dbfa  test    byte ptr [rcx+1Ch], 4
0x18001dbfe  jz      short loc_18001DC0E
0x18001dc00  mov     edx, 55h ; 'U'
0x18001dc05  mov     rcx, [rcx+10h]
0x18001dc09  call    WPP_SF_
0x18001dc0e  lea     rdx, aRunfullmemoryd; "RunFullMemoryDiagnostic"
0x18001dc15  call    ?ConfigureMemoryDiagnosticTask@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z; CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(ushort const *,int)
0x18001dc1a  test    eax, eax
0x18001dc1c  jns     short loc_18001DC41
0x18001dc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc25  cmp     rcx, r14
0x18001dc28  jz      short loc_18001DC41
0x18001dc2a  test    byte ptr [rcx+1Ch], 2
0x18001dc2e  jz      short loc_18001DC41
0x18001dc30  mov     edx, 56h ; 'V'
0x18001dc35  mov     r9d, eax
0x18001dc38  mov     rcx, [rcx+10h]
0x18001dc3c  call    WPP_SF_d
0x18001dc41  lea     rdx, aProcessmemoryd; "ProcessMemoryDiagnosticEvents"
0x18001dc48  call    ?ConfigureMemoryDiagnosticTask@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z; CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(ushort const *,int)
0x18001dc4d  mov     ebx, eax
0x18001dc4f  test    eax, eax
0x18001dc51  jns     short loc_18001DC76
  ... truncated ...
```
