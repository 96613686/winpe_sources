# ShouldLazilyWriteBoundSet(SmsBindable *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uchar,long &)

- ea: `0x1400944f0`
- end: `0x1400947e4`
- name: `?ShouldLazilyWriteBoundSet@@YAEPEAUSmsBindable@@_K111EAEAJ@Z`
- size: `756`
- prototype: `unsigned __int8 __fastcall(struct SmsBindable *, unsigned __int64, unsigned __int64, unsigned __int64, ULONG Seed, char, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400be0f0`

## callees

- `0x140060a4c`
- `0x140082ee0`
- `0x1400944f0`
- `0x1400a1d00`
- `0x1400a76ac`
- `0x140117cb0`
- `0x140117cd8`
- `0x1401185f0`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14009477d`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f9911`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f9988`
- `ntoskrnl!IoGetActivityIdThread` at `0x14009477d`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f9911`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f9988`
- `ntoskrnl!DbgPrintEx` at `0x1401f9a09`
- `ntoskrnl!DbgPrintEx` at `0x1401f9a09`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14009467b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14009467b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400946c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140094710`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400946c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140094710`
- `ntoskrnl!RtlRandomEx` at `0x1400945a9`
- `ntoskrnl!RtlRandomEx` at `0x1400945a9`

## pseudocode

```c
__int64 __fastcall ShouldLazilyWriteBoundSet(
        CmsBPlusTable **a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        CmsBPlusTable *Seed,
        char a6,
        int *a7)
{
  unsigned __int64 v7; // rbp
  unsigned __int8 v11; // r14
  __int64 v13; // rcx
  __int64 v14; // rbp
  KIRQL v15; // al
  CmsBPlusTable *v16; // rdx
  int v17; // eax
  unsigned __int64 v18; // rdi
  char v19; // di
  CmsBPlusTable *v20; // rdx
  int v21; // ebx
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  __int64 Length; // rax
  __int64 v26; // r9
  char v27; // di
  CmsBPlusTable *v28; // rdx
  int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // rcx
  int ActivityIdThread; // eax
  char v33; // di
  CmsBPlusTable *v34; // rdx
  int v35; // ebx
  __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // eax
  unsigned int PercentageLogFreedIfAdvanced; // edi
  int LogFullPercentage; // ebx
  unsigned int RecordReferenceLogPercentage; // eax

  v7 = a4 - (_QWORD)Seed;
  if ( (unsigned __int64)Seed >= a4 )
    v7 = 0;
  if ( !*(_BYTE *)(*(_QWORD *)(*((_QWORD *)*a1 + 3) + 72LL) + 3458LL) || *((_QWORD *)*a1 + 21) != *((_QWORD *)*a1 + 20) )
    return 0;
  if ( !a6 )
  {
    _InterlockedIncrement(&dword_140261F54);
LABEL_36:
    v11 = 1;
    if ( dword_1402403A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
    {
      v27 = CmsBPlusTable::EtwTableIdLow(*a1);
      v29 = CmsBPlusTable::EtwTableIdHigh(v28);
      ActivityIdThread = IoGetActivityIdThread(v31, v30);
      McTemplateK0iiq_EtwWriteTransfer(
        (unsigned int)MinstoreEventProvider_Context,
        (unsigned int)LazyWriterQueueEntry,
        ActivityIdThread,
        v29,
        v27,
        0);
    }
    return v11;
  }
  if ( *a7 > 0 )
  {
    --*a7;
    _InterlockedIncrement(&dword_140261F58);
    goto LABEL_36;
  }
  v11 = 0;
  if ( (unsigned __int64)(a2 - (_QWORD)a1[79]) >= 0x11E1A300 )
  {
    v11 = 1;
    _InterlockedIncrement(&dword_140261F64);
    if ( dword_1402403A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
    {
      v33 = CmsBPlusTable::EtwTableIdLow(*a1);
      v35 = CmsBPlusTable::EtwTableIdHigh(v34);
      v38 = IoGetActivityIdThread(v37, v36);
      McTemplateK0iiq_EtwWriteTransfer(
        (unsigned int)MinstoreEventProvider_Context,
        (unsigned int)LazyWriterQueueEntry,
        v38,
        v35,
        v33,
        3);
    }
  }
  if ( *((_DWORD *)a1 + 162) )
  {
    if ( (unsigned __int64)(a2 - (_QWORD)a1[80]) > 0x55D4A80 )
    {
      _InterlockedIncrement(&dword_140261F6C);
    }
    else if ( v7 )
    {
      _InterlockedIncrement(&dword_140261F70);
    }
    else
    {
      v13 = *((_QWORD *)*a1 + 3);
      v14 = *(_QWORD *)(v13 + 72) + 2880LL;
      if ( a1[58] )
      {
        v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(v13 + 72) + 2936LL));
        *(_BYTE *)(v14 + 64) = v15;
        v16 = a1[58];
        if ( v16 )
        {
          v17 = *(_DWORD *)(v14 + 296);
          Seed = a1[58];
          if ( (v17 & 4) != 0 )
          {
            if ( (unsigned __int64)v16 < *(_QWORD *)(v14 + 128) )
            {
              Length = MlLogGetLength(*(_QWORD *)(v14 + 72), &Seed, v14 + 128, *(_QWORD *)(v14 + 80));
              v18 = 100
                  * ((unsigned __int64)*(unsigned int *)(v14 + 288) + Length)
                  / (*(_QWORD *)(v26 + 3216) << *(_DWORD *)(v26 + 64));
            }
            else
            {
              LODWORD(v18) = 0;
            }
          }
          else
          {
            LODWORD(v18) = 0;
          }
          KeReleaseSpinLock((PKSPIN_LOCK)(v14 + 56), *(_BYTE *)(v14 + 64));
        }
        else
        {
          KeReleaseSpinLock((PKSPIN_LOCK)(v14 + 56), v15);
          LODWORD(v18) = 0;
        }
      }
      else
      {
        LODWORD(v18) = 0;
      }
      if ( (unsigned int)v18 >= (unsigned __int8)byte_14026207B )
      {
        if ( dword_140262084 )
        {
          PercentageLogFreedIfAdvanced = CmsDurableLog::GetPercentageLogFreedIfAdvanced((CmsDurableLog *)v14);
          LogFullPercentage = CmsDurableLog::GetLogFullPercentage((CmsDurableLog *)v14);
          RecordReferenceLogPercentage = CmsDurableLog::GetRecordReferenceLogPercentage(
                                           (CmsDurableLog *)v14,
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
        _InterlockedIncrement(&dword_140261F74);
      }
      else
      {
        if ( !dword_1402620A8 || *((_DWORD *)a1 + 167) < dword_1402620A8 )
          return v11;
        _InterlockedIncrement(&dword_140261F78);
      }
    }
    return 1;
  }
  LODWORD(Seed) = 43962;
  if ( a2 - a3 > 10000 * ((unsigned __int64)(RtlRandomEx((PULONG)&Seed) % 0x7FFFFFFE % 0x1388) + 5000) )
  {
    v11 = 1;
    _InterlockedIncrement(&dword_140261F68);
    if ( dword_1402403A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
    {
      v19 = CmsBPlusTable::EtwTableIdLow(*a1);
      v21 = CmsBPlusTable::EtwTableIdHigh(v20);
      v24 = IoGetActivityIdThread(v23, v22);
      McTemplateK0iiq_EtwWriteTransfer(
        (unsigned int)MinstoreEventProvider_Context,
        (unsigned int)LazyWriterQueueEntry,
        v24,
        v21,
        v19,
        2);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1400944f0  mov     [rsp+arg_10], rbp
0x1400944f5  mov     [rsp+arg_18], rsi
0x1400944fa  push    r12
0x1400944fc  push    r14
0x1400944fe  push    r15
0x140094500  sub     rsp, 30h
0x140094504  xor     eax, eax
0x140094506  mov     rbp, r9
0x140094509  sub     rbp, [rsp+48h+Seed]
0x14009450e  mov     r15, rdx
0x140094511  cmp     [rsp+48h+Seed], r9
0x140094516  mov     rsi, rcx
0x140094519  mov     r12, r8
0x14009451c  cmovnb  rbp, rax
0x140094520  mov     rax, [rcx]
0x140094523  mov     rdx, [rax+18h]
0x140094527  mov     rcx, [rdx+48h]
0x14009452b  cmp     byte ptr [rcx+0D82h], 0
0x140094532  jz      loc_140094731
0x140094538  mov     rdx, [rax+0A8h]
0x14009453f  mov     rcx, [rax+0A0h]
0x140094546  cmp     rdx, rcx
0x140094549  jnz     loc_140094731
0x14009454f  cmp     [rsp+48h+arg_28], 0
0x140094554  mov     [rsp+48h+arg_0], rbx
0x140094559  mov     [rsp+48h+arg_8], rdi
0x14009455e  jz      loc_140094739
0x140094564  mov     rcx, [rsp+48h+arg_30]
0x14009456c  mov     eax, [rcx]
0x14009456e  test    eax, eax
0x140094570  jg      loc_140094746
0x140094576  mov     rax, r15
0x140094579  xor     r14b, r14b
0x14009457c  sub     rax, [rsi+278h]
0x140094583  cmp     rax, 11E1A300h
0x140094589  jnb     loc_1401F9949
0x14009458f  cmp     dword ptr [rsi+288h], 0
0x140094596  jnz     loc_14009463E
0x14009459c  lea     rcx, [rsp+48h+Seed]; Seed
0x1400945a1  mov     dword ptr [rsp+48h+Seed], 0ABBAh
0x1400945a9  call    cs:__imp_RtlRandomEx
0x1400945b0  nop     dword ptr [rax+rax+00h]
0x1400945b5  mov     r8d, eax
0x1400945b8  sub     r15, r12
0x1400945bb  mov     ecx, r8d
0x1400945be  mov     eax, 5
0x1400945c3  mul     r8d
0x1400945c6  sub     ecx, edx
0x1400945c8  shr     ecx, 1
0x1400945ca  add     ecx, edx
0x1400945cc  shr     ecx, 1Eh
0x1400945cf  imul    eax, ecx, 7FFFFFFEh
0x1400945d5  sub     r8d, eax
0x1400945d8  mov     eax, 0D1B71759h
0x1400945dd  mul     r8d
0x1400945e0  shr     edx, 0Ch
0x1400945e3  imul    eax, edx, 1388h
0x1400945e9  sub     r8d, eax
0x1400945ec  mov     eax, r8d
0x1400945ef  add     rax, 1388h
0x1400945f5  imul    rcx, rax, 2710h
0x1400945fc  cmp     r15, rcx
0x1400945ff  jbe     short loc_14009461A
0x140094601  mov     r14b, 1
0x140094604  nop
0x140094605  lock inc cs:dword_140261F68
0x14009460c  nop
0x14009460d  cmp     cs:dword_1402403A4, 1
0x140094614  jz      loc_140094757
0x14009461a  mov     rbx, [rsp+48h+arg_0]
0x14009461f  mov     rdi, [rsp+48h+arg_8]
0x140094624  mov     rbp, [rsp+48h+arg_10]
0x140094629  movzx   eax, r14b
0x14009462d  mov     rsi, [rsp+48h+arg_18]
0x140094632  add     rsp, 30h
0x140094636  pop     r15
0x140094638  pop     r14
0x14009463a  pop     r12
0x14009463c  retn
0x14009463e  sub     r15, [rsi+280h]
0x140094645  cmp     r15, 55D4A80h
0x14009464c  ja      loc_140094720
0x140094652  test    rbp, rbp
0x140094655  jnz     loc_140094796
0x14009465b  mov     rax, [rsi]
0x14009465e  mov     rcx, [rax+18h]
0x140094662  mov     rbp, [rcx+48h]
0x140094666  add     rbp, 0B40h
0x14009466d  cmp     qword ptr [rsi+1D0h], 0
0x140094675  jz      short loc_1400946D4
0x140094677  lea     rcx, [rbp+38h]; SpinLock
0x14009467b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140094682  nop     dword ptr [rax+rax+00h]
0x140094687  mov     [rbp+40h], al
0x14009468a  mov     rdx, [rsi+1D0h]
0x140094691  test    rdx, rdx
0x140094694  jz      short loc_140094709
0x140094696  mov     eax, [rbp+128h]
0x14009469c  mov     [rsp+48h+Seed], rdx
0x1400946a1  test    al, 4
0x1400946a3  jz      loc_1400947A0
0x1400946a9  lea     r8, [rbp+80h]
0x1400946b0  mov     rax, [r8]
0x1400946b3  cmp     rdx, rax
0x1400946b6  jb      loc_1400947A7
0x1400946bc  xor     edi, edi
0x1400946be  movzx   edx, byte ptr [rbp+40h]; NewIrql
0x1400946c2  lea     rcx, [rbp+38h]; SpinLock
0x1400946c6  call    cs:__imp_KeReleaseSpinLock
0x1400946cd  nop     dword ptr [rax+rax+00h]
0x1400946d2  jmp     short loc_1400946D6
0x1400946d4  xor     edi, edi
0x1400946d6  movzx   eax, cs:byte_14026207B
0x1400946dd  cmp     edi, eax
0x1400946df  jnb     loc_1401F99C0
0x1400946e5  mov     eax, cs:dword_1402620A8
0x1400946eb  test    eax, eax
0x1400946ed  jz      loc_14009461A
0x1400946f3  cmp     [rsi+29Ch], eax
0x1400946f9  jl      loc_14009461A
0x1400946ff  nop
0x140094700  lock inc cs:dword_140261F78
0x140094707  jmp     short loc_140094728
0x140094709  movzx   edx, al; NewIrql
0x14009470c  lea     rcx, [rbp+38h]; SpinLock
0x140094710  call    cs:__imp_KeReleaseSpinLock
0x140094717  nop     dword ptr [rax+rax+00h]
0x14009471c  xor     edi, edi
0x14009471e  jmp     short loc_1400946D6
0x140094720  nop
0x140094721  lock inc cs:dword_140261F6C
0x140094728  nop
0x140094729  mov     r14b, 1
0x14009472c  jmp     loc_14009461A
0x140094731  xor     r14b, r14b
0x140094734  jmp     loc_140094624
0x140094739  nop
0x14009473a  lock inc cs:dword_140261F54
0x140094741  jmp     loc_1401F98DA
0x140094746  dec     eax
0x140094748  mov     [rcx], eax
0x14009474a  nop
0x14009474b  lock inc cs:dword_140261F58
0x140094752  jmp     loc_1401F98DA
0x140094757  test    cs:Microsoft_Windows_MinstoreEnableBits, r14b
0x14009475e  jz      loc_14009461A
0x140094764  mov     rdx, [rsi]
0x140094767  mov     rcx, rdx; this
0x14009476a  call    ?EtwTableIdLow@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdLow(void)
0x14009476f  mov     rcx, rdx; this
0x140094772  mov     rdi, rax
0x140094775  call    ?EtwTableIdHigh@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdHigh(void)
0x14009477a  mov     rbx, rax
0x14009477d  call    cs:__imp_IoGetActivityIdThread
0x140094784  nop     dword ptr [rax+rax+00h]
0x140094789  mov     [rsp+48h+var_20], 2
0x140094791  jmp     loc_1401F9925
0x140094796  nop
0x140094797  lock inc cs:dword_140261F70
0x14009479e  jmp     short loc_140094728
0x1400947a0  xor     edi, edi
0x1400947a2  jmp     loc_1400946BE
0x1400947a7  mov     rcx, [rbp+48h]
0x1400947ab  lea     rdx, [rsp+48h+Seed]
0x1400947b0  mov     r9, [rbp+50h]
0x1400947b4  call    MlLogGetLength
0x1400947b9  mov     ecx, [r9+40h]
0x1400947bd  mov     r8, rax
0x1400947c0  mov     eax, [rbp+120h]
0x1400947c6  xor     edx, edx
0x1400947c8  add     r8, rax
0x1400947cb  imul    rax, r8, 64h ; 'd'
0x1400947cf  mov     r8, [r9+0C90h]
0x1400947d6  shl     r8, cl
0x1400947d9  div     r8
0x1400947dc  mov     rdi, rax
0x1400947df  jmp     loc_1400946BE
0x1401f98da  nop
0x1401f98db  mov     r14b, 1
0x1401f98de  cmp     cs:dword_1402403A4, 1
0x1401f98e5  jnz     loc_14009461A
0x1401f98eb  test    cs:Microsoft_Windows_MinstoreEnableBits, r14b
0x1401f98f2  jz      loc_14009461A
0x1401f98f8  mov     rdx, [rsi]
0x1401f98fb  mov     rcx, rdx; this
0x1401f98fe  call    ?EtwTableIdLow@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdLow(void)
0x1401f9903  mov     rcx, rdx; this
0x1401f9906  mov     rdi, rax
0x1401f9909  call    ?EtwTableIdHigh@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdHigh(void)
0x1401f990e  mov     rbx, rax
0x1401f9911  call    cs:__imp_IoGetActivityIdThread
0x1401f9918  nop     dword ptr [rax+rax+00h]
0x1401f991d  mov     [rsp+48h+var_20], 0
0x1401f9925  mov     r9, rbx
0x1401f9928  mov     [rsp+48h+var_28], rdi
0x1401f992d  mov     r8, rax
0x1401f9930  lea     rdx, LazyWriterQueueEntry
0x1401f9937  lea     rcx, MinstoreEventProvider_Context
0x1401f993e  call    McTemplateK0iiq_EtwWriteTransfer
0x1401f9943  nop
0x1401f9944  jmp     loc_14009461A
0x1401f9949  mov     r14b, 1
0x1401f994c  nop
0x1401f994d  lock inc cs:dword_140261F64
0x1401f9954  nop
0x1401f9955  cmp     cs:dword_1402403A4, 1
0x1401f995c  jnz     loc_14009458F
0x1401f9962  test    cs:Microsoft_Windows_MinstoreEnableBits, r14b
0x1401f9969  jz      loc_14009458F
0x1401f996f  mov     rdx, [rsi]
0x1401f9972  mov     rcx, rdx; this
0x1401f9975  call    ?EtwTableIdLow@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdLow(void)
0x1401f997a  mov     rcx, rdx; this
0x1401f997d  mov     rdi, rax
0x1401f9980  call    ?EtwTableIdHigh@CmsBPlusTable@@QEAA_KXZ; CmsBPlusTable::EtwTableIdHigh(void)
0x1401f9985  mov     rbx, rax
0x1401f9988  call    cs:__imp_IoGetActivityIdThread
0x1401f998f  nop     dword ptr [rax+rax+00h]
0x1401f9994  mov     [rsp+48h+var_20], 3
0x1401f999c  lea     rdx, LazyWriterQueueEntry
0x1401f99a3  mov     r8, rax
0x1401f99a6  mov     [rsp+48h+var_28], rdi
0x1401f99ab  mov     r9, rbx
0x1401f99ae  lea     rcx, MinstoreEventProvider_Context
0x1401f99b5  call    McTemplateK0iiq_EtwWriteTransfer
0x1401f99ba  nop
0x1401f99bb  jmp     loc_14009458F
0x1401f99c0  cmp     cs:dword_140262084, 0
0x1401f99c7  jz      short loc_1401F9A15
0x1401f99c9  mov     rcx, rbp; this
0x1401f99cc  call    ?GetPercentageLogFreedIfAdvanced@CmsDurableLog@@QEAAKXZ; CmsDurableLog::GetPercentageLogFreedIfAdvanced(void)
0x1401f99d1  mov     rcx, rbp; this
0x1401f99d4  mov     edi, eax
0x1401f99d6  call    ?GetLogFullPercentage@CmsDurableLog@@QEAAEXZ; CmsDurableLog::GetLogFullPercentage(void)
0x1401f99db  xor     r8d, r8d; unsigned __int64 *
0x1401f99de  movzx   ebx, al
0x1401f99e1  lea     rdx, [rsi+1B0h]; struct CmsMemLog *
0x1401f99e8  mov     rcx, rbp; this
0x1401f99eb  call    ?GetRecordReferenceLogPercentage@CmsDurableLog@@QEAAKPEAVCmsMemLog@@PEA_K@Z; CmsDurableLog::GetRecordReferenceLogPercentage(CmsMemLog *,unsigned __int64 *)
0x1401f99f0  mov     r9d, eax
0x1401f99f3  mov     [rsp+48h+var_20], edi
0x1401f99f7  lea     r8, aLwSchedulingBe; "LW scheduling because of log (case 2) %"...
0x1401f99fe  mov     dword ptr [rsp+48h+var_28], ebx
0x1401f9a02  xor     edx, edx; Level
0x1401f9a04  mov     ecx, 65h ; 'e'; ComponentId
0x1401f9a09  call    cs:__imp_DbgPrintEx
0x1401f9a10  nop     dword ptr [rax+rax+00h]
0x1401f9a15  nop
0x1401f9a16  lock inc cs:dword_140261F74
0x1401f9a1d  jmp     loc_140094728
```
