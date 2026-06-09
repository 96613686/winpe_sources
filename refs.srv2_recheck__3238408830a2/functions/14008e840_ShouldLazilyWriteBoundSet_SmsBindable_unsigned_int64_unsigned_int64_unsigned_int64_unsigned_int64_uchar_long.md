# ShouldLazilyWriteBoundSet(SmsBindable *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uchar,long &)

- ea: `0x14008e840`
- end: `0x14008eb27`
- name: `?ShouldLazilyWriteBoundSet@@YAEPEAUSmsBindable@@_K111EAEAJ@Z`
- size: `743`
- prototype: `unsigned __int8 __fastcall(struct SmsBindable *, unsigned __int64, unsigned __int64, unsigned __int64, ULONG Seed, char, _SmsPerfStats *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400be6d0`

## callees

- `0x140008c40`
- `0x140022ba8`
- `0x14008e840`
- `0x14009cab0`
- `0x1400a252c`
- `0x14011c2ac`
- `0x14011d2f0`
- `0x14011d318`
- `0x14011dc44`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14008eac3`
- `ntoskrnl!IoGetActivityIdThread` at `0x14020161b`
- `ntoskrnl!IoGetActivityIdThread` at `0x140201693`
- `ntoskrnl!IoGetActivityIdThread` at `0x14008eac3`
- `ntoskrnl!IoGetActivityIdThread` at `0x14020161b`
- `ntoskrnl!IoGetActivityIdThread` at `0x140201693`
- `ntoskrnl!DbgPrintEx` at `0x140201714`
- `ntoskrnl!DbgPrintEx` at `0x140201714`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008e9cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008e9cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008ea17`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008ea5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008ea17`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008ea5e`
- `ntoskrnl!RtlRandomEx` at `0x14008e8f9`
- `ntoskrnl!RtlRandomEx` at `0x14008e8f9`

## pseudocode

```c
__int64 __fastcall ShouldLazilyWriteBoundSet(
        CmsBPlusTable **a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        CmsBPlusTable *Seed,
        char a6,
        _SmsPerfStats *a7)
{
  unsigned __int64 v7; // rbp
  CmsBPlusTable *v11; // rax
  _SmsPerfStats *v12; // rcx
  unsigned __int8 v13; // r14
  unsigned __int64 v14; // rcx
  __int64 v16; // rbp
  KIRQL v17; // al
  CmsBPlusTable *v18; // rdx
  int v19; // eax
  unsigned __int64 v20; // rdi
  int v21; // edx
  int v22; // edx
  char v23; // di
  CmsBPlusTable *v24; // rdx
  int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  __int64 Length; // rax
  __int64 v30; // r9
  char v31; // di
  CmsBPlusTable *v32; // rdx
  int v33; // ebx
  __int64 v34; // rdx
  __int64 v35; // rcx
  int ActivityIdThread; // eax
  char v37; // di
  CmsBPlusTable *v38; // rdx
  int v39; // ebx
  __int64 v40; // rdx
  __int64 v41; // rcx
  int v42; // eax
  unsigned int PercentageLogFreedIfAdvanced; // edi
  int LogFullPercentage; // ebx
  unsigned int RecordReferenceLogPercentage; // eax

  v7 = a4 - (_QWORD)Seed;
  if ( (unsigned __int64)Seed >= a4 )
    v7 = 0;
  v11 = *a1;
  if ( !*(_BYTE *)(*(_QWORD *)(*((_QWORD *)*a1 + 3) + 72LL) + 3394LL) )
    return 0;
  v12 = (_SmsPerfStats *)*((_QWORD *)v11 + 20);
  if ( *((_SmsPerfStats **)v11 + 21) != v12 )
    return 0;
  if ( !a6 )
  {
    v22 = 0;
LABEL_36:
    v13 = 1;
    _SmsPerfStats::IncrementLazyWriterWriteBoundSetReasonCount(v12, v22);
    if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
    {
      v31 = CmsBPlusTable::EtwTableIdLow(*a1);
      v33 = CmsBPlusTable::EtwTableIdHigh(v32);
      ActivityIdThread = IoGetActivityIdThread(v35, v34);
      McTemplateK0iiq_EtwWriteTransfer(
        (unsigned int)MinstoreEventProvider_Context,
        (unsigned int)LazyWriterQueueEntry,
        ActivityIdThread,
        v33,
        v31,
        0);
    }
    return v13;
  }
  v12 = a7;
  if ( *(int *)a7 > 0 )
  {
    v22 = 1;
    --*(_DWORD *)a7;
    goto LABEL_36;
  }
  v13 = 0;
  if ( (unsigned __int64)(a2 - (_QWORD)a1[79]) >= 0x11E1A300 )
  {
    v13 = 1;
    _SmsPerfStats::IncrementLazyWriterWriteBoundSetReasonCount(a7, 4);
    if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
    {
      v37 = CmsBPlusTable::EtwTableIdLow(*a1);
      v39 = CmsBPlusTable::EtwTableIdHigh(v38);
      v42 = IoGetActivityIdThread(v41, v40);
      McTemplateK0iiq_EtwWriteTransfer(
        (unsigned int)MinstoreEventProvider_Context,
        (unsigned int)LazyWriterQueueEntry,
        v42,
        v39,
        v37,
        3);
    }
  }
  if ( *((_DWORD *)a1 + 162) )
  {
    if ( (unsigned __int64)(a2 - (_QWORD)a1[80]) > 0x55D4A80 )
    {
      v21 = 6;
    }
    else if ( v7 )
    {
      v21 = 7;
    }
    else
    {
      v12 = (_SmsPerfStats *)*((_QWORD *)*a1 + 3);
      v16 = *((_QWORD *)v12 + 9) + 2816LL;
      if ( a1[58] )
      {
        v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*((_QWORD *)v12 + 9) + 2872LL));
        *(_BYTE *)(v16 + 64) = v17;
        v18 = a1[58];
        if ( v18 )
        {
          v19 = *(_DWORD *)(v16 + 296);
          Seed = a1[58];
          if ( (v19 & 4) != 0 )
          {
            if ( (unsigned __int64)v18 < *(_QWORD *)(v16 + 128) )
            {
              Length = MlLogGetLength(*(_QWORD *)(v16 + 72), &Seed, v16 + 128, *(_QWORD *)(v16 + 80));
              v20 = 100
                  * ((unsigned __int64)*(unsigned int *)(v16 + 288) + Length)
                  / (*(_QWORD *)(v30 + 3152) << *(_DWORD *)(v30 + 64));
            }
            else
            {
              LODWORD(v20) = 0;
            }
          }
          else
          {
            LODWORD(v20) = 0;
          }
          KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 56), *(_BYTE *)(v16 + 64));
        }
        else
        {
          KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 56), v17);
          LODWORD(v20) = 0;
        }
      }
      else
      {
        LODWORD(v20) = 0;
      }
      if ( (unsigned int)v20 >= (unsigned __int8)byte_14026907B )
      {
        if ( dword_140269084 )
        {
          PercentageLogFreedIfAdvanced = CmsDurableLog::GetPercentageLogFreedIfAdvanced((CmsDurableLog *)v16);
          LogFullPercentage = CmsDurableLog::GetLogFullPercentage((CmsDurableLog *)v16);
          RecordReferenceLogPercentage = CmsDurableLog::GetRecordReferenceLogPercentage(
                                           (CmsDurableLog *)v16,
                                           (struct CmsMemLog *)(a1 + 54),
                                           0);
          DbgPrintEx(
            0x65u,
            0,
            "LW scheduling because of log (case 2) %d pct (%d full, %d reclaimable) [opt0]\n",
            RecordReferenceLogPercentage,
            LogFullPercentage,
            PercentageLogFreedIfAdvanced);
        }
        v21 = 8;
      }
      else
      {
        if ( !dword_1402690A8 || *((_DWORD *)a1 + 167) < dword_1402690A8 )
          return v13;
        v21 = 9;
      }
    }
    v13 = 1;
    _SmsPerfStats::IncrementLazyWriterWriteBoundSetReasonCount(v12, v21);
    return v13;
  }
  LODWORD(Seed) = 43962;
  v14 = 10000 * (RtlRandomEx((PULONG)&Seed) % 0x7FFFFFFE % 0x1388 + 5000LL);
  if ( a2 - a3 > v14 )
  {
    v13 = 1;
    _SmsPerfStats::IncrementLazyWriterWriteBoundSetReasonCount((_SmsPerfStats *)v14, 5);
    if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
    {
      v23 = CmsBPlusTable::EtwTableIdLow(*a1);
      v25 = CmsBPlusTable::EtwTableIdHigh(v24);
      v28 = IoGetActivityIdThread(v27, v26);
      McTemplateK0iiq_EtwWriteTransfer(
        (unsigned int)MinstoreEventProvider_Context,
        (unsigned int)LazyWriterQueueEntry,
        v28,
        v25,
        v23,
        2);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x14008e840  mov     [rsp+arg_10], rbp
0x14008e845  mov     [rsp+arg_18], rsi
0x14008e84a  push    r12
0x14008e84c  push    r14
0x14008e84e  push    r15
0x14008e850  sub     rsp, 30h
0x14008e854  xor     eax, eax
0x14008e856  mov     rbp, r9
0x14008e859  sub     rbp, [rsp+48h+Seed]
0x14008e85e  mov     r15, rdx
0x14008e861  cmp     [rsp+48h+Seed], r9
0x14008e866  mov     rsi, rcx
0x14008e869  mov     r12, r8
0x14008e86c  cmovnb  rbp, rax
0x14008e870  mov     rax, [rcx]
0x14008e873  mov     rdx, [rax+18h]
0x14008e877  mov     rcx, [rdx+48h]
0x14008e87b  cmp     byte ptr [rcx+0D42h], 0
0x14008e882  jz      loc_14008EA80
0x14008e888  mov     rdx, [rax+0A8h]
0x14008e88f  mov     rcx, [rax+0A0h]; this
0x14008e896  cmp     rdx, rcx
0x14008e899  jnz     loc_14008EA80
0x14008e89f  cmp     [rsp+48h+arg_28], 0
0x14008e8a4  mov     [rsp+48h+arg_0], rbx
0x14008e8a9  mov     [rsp+48h+arg_8], rdi
0x14008e8ae  jz      loc_14008EA88
0x14008e8b4  mov     rcx, [rsp+48h+arg_30]; this
0x14008e8bc  mov     eax, [rcx]
0x14008e8be  test    eax, eax
0x14008e8c0  jg      loc_14008EA8F
0x14008e8c6  mov     rax, r15
0x14008e8c9  xor     r14b, r14b
0x14008e8cc  sub     rax, [rsi+278h]
0x14008e8d3  cmp     rax, 11E1A300h
0x14008e8d9  jnb     loc_140201653
0x14008e8df  cmp     dword ptr [rsi+288h], 0
0x14008e8e6  jnz     loc_14008E98F
0x14008e8ec  lea     rcx, [rsp+48h+Seed]; Seed
0x14008e8f1  mov     dword ptr [rsp+48h+Seed], 0ABBAh
0x14008e8f9  call    cs:__imp_RtlRandomEx
0x14008e900  nop     dword ptr [rax+rax+00h]
0x14008e905  mov     r8d, eax
0x14008e908  sub     r15, r12
0x14008e90b  mov     ecx, r8d
0x14008e90e  mov     eax, 5
0x14008e913  mul     r8d
0x14008e916  sub     ecx, edx
0x14008e918  shr     ecx, 1
0x14008e91a  add     ecx, edx
0x14008e91c  shr     ecx, 1Eh
0x14008e91f  imul    eax, ecx, 7FFFFFFEh
0x14008e925  sub     r8d, eax
0x14008e928  mov     eax, 0D1B71759h
0x14008e92d  mul     r8d
0x14008e930  shr     edx, 0Ch
0x14008e933  imul    eax, edx, 1388h
0x14008e939  sub     r8d, eax
0x14008e93c  mov     eax, r8d
0x14008e93f  add     rax, 1388h
0x14008e945  imul    rcx, rax, 2710h; this
0x14008e94c  cmp     r15, rcx
0x14008e94f  jbe     short loc_14008E96B
0x14008e951  mov     edx, 5; int
0x14008e956  mov     r14b, 1
0x14008e959  call    ?IncrementLazyWriterWriteBoundSetReasonCount@_SmsPerfStats@@QEAAXH@Z; _SmsPerfStats::IncrementLazyWriterWriteBoundSetReasonCount(int)
0x14008e95e  cmp     cs:dword_1402473A4, 1
0x14008e965  jz      loc_14008EA9D
0x14008e96b  mov     rbx, [rsp+48h+arg_0]
0x14008e970  mov     rdi, [rsp+48h+arg_8]
0x14008e975  mov     rbp, [rsp+48h+arg_10]
0x14008e97a  movzx   eax, r14b
0x14008e97e  mov     rsi, [rsp+48h+arg_18]
0x14008e983  add     rsp, 30h
0x14008e987  pop     r15
0x14008e989  pop     r14
0x14008e98b  pop     r12
0x14008e98d  retn
0x14008e98f  sub     r15, [rsi+280h]
0x14008e996  cmp     r15, 55D4A80h
0x14008e99d  ja      loc_14008EA6E
0x14008e9a3  test    rbp, rbp
0x14008e9a6  jnz     loc_14008EADC
0x14008e9ac  mov     rax, [rsi]
0x14008e9af  mov     rcx, [rax+18h]
0x14008e9b3  mov     rbp, [rcx+48h]
0x14008e9b7  add     rbp, 0B00h
0x14008e9be  cmp     qword ptr [rsi+1D0h], 0
0x14008e9c6  jz      short loc_14008EA25
0x14008e9c8  lea     rcx, [rbp+38h]; SpinLock
0x14008e9cc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008e9d3  nop     dword ptr [rax+rax+00h]
0x14008e9d8  mov     [rbp+40h], al
0x14008e9db  mov     rdx, [rsi+1D0h]
0x14008e9e2  test    rdx, rdx
0x14008e9e5  jz      short loc_14008EA57
0x14008e9e7  mov     eax, [rbp+128h]
0x14008e9ed  mov     [rsp+48h+Seed], rdx
0x14008e9f2  test    al, 4
0x14008e9f4  jz      loc_14008EAE3
0x14008e9fa  lea     r8, [rbp+80h]
0x14008ea01  mov     rax, [r8]
0x14008ea04  cmp     rdx, rax
0x14008ea07  jb      loc_14008EAEA
0x14008ea0d  xor     edi, edi
0x14008ea0f  movzx   edx, byte ptr [rbp+40h]; NewIrql
0x14008ea13  lea     rcx, [rbp+38h]; SpinLock
0x14008ea17  call    cs:__imp_KeReleaseSpinLock
0x14008ea1e  nop     dword ptr [rax+rax+00h]
0x14008ea23  jmp     short loc_14008EA27
0x14008ea25  xor     edi, edi
0x14008ea27  movzx   eax, cs:byte_14026907B
0x14008ea2e  cmp     edi, eax
0x14008ea30  jnb     loc_1402016CB
0x14008ea36  mov     eax, cs:dword_1402690A8
0x14008ea3c  test    eax, eax
0x14008ea3e  jz      loc_14008E96B
0x14008ea44  cmp     [rsi+29Ch], eax
0x14008ea4a  jl      loc_14008E96B
0x14008ea50  mov     edx, 9
0x14008ea55  jmp     short loc_14008EA73
0x14008ea57  movzx   edx, al; NewIrql
0x14008ea5a  lea     rcx, [rbp+38h]; SpinLock
0x14008ea5e  call    cs:__imp_KeReleaseSpinLock
0x14008ea65  nop     dword ptr [rax+rax+00h]
0x14008ea6a  xor     edi, edi
0x14008ea6c  jmp     short loc_14008EA27
0x14008ea6e  mov     edx, 6; int
0x14008ea73  mov     r14b, 1
0x14008ea76  call    ?IncrementLazyWriterWriteBoundSetReasonCount@_SmsPerfStats@@QEAAXH@Z; _SmsPerfStats::IncrementLazyWriterWriteBoundSetReasonCount(int)
0x14008ea7b  jmp     loc_14008E96B
0x14008ea80  xor     r14b, r14b
0x14008ea83  jmp     loc_14008E975
0x14008ea88  xor     edx, edx; int
0x14008ea8a  jmp     loc_1402015E0
0x14008ea8f  dec     eax
0x14008ea91  mov     edx, 1
0x14008ea96  mov     [rcx], eax
0x14008ea98  jmp     loc_1402015E0
0x14008ea9d  test    cs:Microsoft_Windows_MinstoreEnableBits, r14b
0x14008eaa4  jz      loc_14008E96B
0x14008eaaa  mov     rdx, [rsi]
0x14008eaad  mov     rcx, rdx; this
0x14008eab0  call    ?EtwTableIdLow@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdLow(void)
0x14008eab5  mov     rcx, rdx; this
0x14008eab8  mov     rdi, rax
0x14008eabb  call    ?EtwTableIdHigh@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdHigh(void)
0x14008eac0  mov     rbx, rax
0x14008eac3  call    cs:__imp_IoGetActivityIdThread
0x14008eaca  nop     dword ptr [rax+rax+00h]
0x14008eacf  mov     [rsp+48h+var_20], 2
0x14008ead7  jmp     loc_14020162F
0x14008eadc  mov     edx, 7
0x14008eae1  jmp     short loc_14008EA73
0x14008eae3  xor     edi, edi
0x14008eae5  jmp     loc_14008EA0F
0x14008eaea  mov     rcx, [rbp+48h]
0x14008eaee  lea     rdx, [rsp+48h+Seed]
0x14008eaf3  mov     r9, [rbp+50h]
0x14008eaf7  call    MlLogGetLength
0x14008eafc  mov     ecx, [r9+40h]
0x14008eb00  mov     r8, rax
0x14008eb03  mov     eax, [rbp+120h]
0x14008eb09  xor     edx, edx
0x14008eb0b  add     r8, rax
0x14008eb0e  imul    rax, r8, 64h ; 'd'
0x14008eb12  mov     r8, [r9+0C50h]
0x14008eb19  shl     r8, cl
0x14008eb1c  div     r8
0x14008eb1f  mov     rdi, rax
0x14008eb22  jmp     loc_14008EA0F
0x1402015e0  mov     r14b, 1
0x1402015e3  call    ?IncrementLazyWriterWriteBoundSetReasonCount@_SmsPerfStats@@QEAAXH@Z; _SmsPerfStats::IncrementLazyWriterWriteBoundSetReasonCount(int)
0x1402015e8  cmp     cs:dword_1402473A4, 1
0x1402015ef  jnz     loc_14008E96B
0x1402015f5  test    cs:Microsoft_Windows_MinstoreEnableBits, r14b
0x1402015fc  jz      loc_14008E96B
0x140201602  mov     rdx, [rsi]
0x140201605  mov     rcx, rdx; this
0x140201608  call    ?EtwTableIdLow@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdLow(void)
0x14020160d  mov     rcx, rdx; this
0x140201610  mov     rdi, rax
0x140201613  call    ?EtwTableIdHigh@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdHigh(void)
0x140201618  mov     rbx, rax
0x14020161b  call    cs:__imp_IoGetActivityIdThread
0x140201622  nop     dword ptr [rax+rax+00h]
0x140201627  mov     [rsp+48h+var_20], 0
0x14020162f  mov     r9, rbx
0x140201632  mov     [rsp+48h+var_28], rdi
0x140201637  mov     r8, rax
0x14020163a  lea     rdx, LazyWriterQueueEntry
0x140201641  lea     rcx, MinstoreEventProvider_Context
0x140201648  call    McTemplateK0iiq_EtwWriteTransfer
0x14020164d  nop
0x14020164e  jmp     loc_14008E96B
0x140201653  mov     edx, 4; int
0x140201658  mov     r14b, 1
0x14020165b  call    ?IncrementLazyWriterWriteBoundSetReasonCount@_SmsPerfStats@@QEAAXH@Z; _SmsPerfStats::IncrementLazyWriterWriteBoundSetReasonCount(int)
0x140201660  cmp     cs:dword_1402473A4, 1
0x140201667  jnz     loc_14008E8DF
0x14020166d  test    cs:Microsoft_Windows_MinstoreEnableBits, r14b
0x140201674  jz      loc_14008E8DF
0x14020167a  mov     rdx, [rsi]
0x14020167d  mov     rcx, rdx; this
0x140201680  call    ?EtwTableIdLow@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdLow(void)
0x140201685  mov     rcx, rdx; this
0x140201688  mov     rdi, rax
0x14020168b  call    ?EtwTableIdHigh@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdHigh(void)
0x140201690  mov     rbx, rax
0x140201693  call    cs:__imp_IoGetActivityIdThread
0x14020169a  nop     dword ptr [rax+rax+00h]
0x14020169f  mov     [rsp+48h+var_20], 3
0x1402016a7  lea     rdx, LazyWriterQueueEntry
0x1402016ae  mov     r8, rax
0x1402016b1  mov     [rsp+48h+var_28], rdi
0x1402016b6  mov     r9, rbx
0x1402016b9  lea     rcx, MinstoreEventProvider_Context
0x1402016c0  call    McTemplateK0iiq_EtwWriteTransfer
0x1402016c5  nop
0x1402016c6  jmp     loc_14008E8DF
0x1402016cb  cmp     cs:dword_140269084, 0
0x1402016d2  jz      short loc_140201720
0x1402016d4  mov     rcx, rbp; this
0x1402016d7  call    ?GetPercentageLogFreedIfAdvanced@CmsDurableLog@@QEAAKXZ; CmsDurableLog::GetPercentageLogFreedIfAdvanced(void)
0x1402016dc  mov     rcx, rbp; this
0x1402016df  mov     edi, eax
0x1402016e1  call    ?GetLogFullPercentage@CmsDurableLog@@QEAAEXZ; CmsDurableLog::GetLogFullPercentage(void)
0x1402016e6  xor     r8d, r8d; unsigned __int64 *
0x1402016e9  movzx   ebx, al
0x1402016ec  lea     rdx, [rsi+1B0h]; struct CmsMemLog *
0x1402016f3  mov     rcx, rbp; this
0x1402016f6  call    ?GetRecordReferenceLogPercentage@CmsDurableLog@@QEAAKPEAVCmsMemLog@@PEA_K@Z; CmsDurableLog::GetRecordReferenceLogPercentage(CmsMemLog *,unsigned __int64 *)
0x1402016fb  mov     r9d, eax
0x1402016fe  mov     [rsp+48h+var_20], edi
0x140201702  lea     r8, aLwSchedulingBe; "LW scheduling because of log (case 2) %"...
0x140201709  mov     dword ptr [rsp+48h+var_28], ebx
0x14020170d  xor     edx, edx; Level
0x14020170f  mov     ecx, 65h ; 'e'; ComponentId
0x140201714  call    cs:__imp_DbgPrintEx
0x14020171b  nop     dword ptr [rax+rax+00h]
0x140201720  mov     edx, 8
0x140201725  jmp     loc_14008EA73
```
