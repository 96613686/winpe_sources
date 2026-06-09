# MRxDAVTimeOutTheContexts

- ea: `0x140005554`
- end: `0x1400059dc`
- name: `MRxDAVTimeOutTheContexts`
- size: `1160`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140004950`
- `0x140010168`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140004350`
- `0x140005554`
- `0x140027658`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000560e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005728`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400057e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005885`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400058d8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000560e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005728`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400057e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005885`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400058d8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000558d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005910`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000558d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005910`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000585d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005965`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000585d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005965`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140005787`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140005787`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400059a9`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400059a9`

## pseudocode

```c
void __fastcall MRxDAVTimeOutTheContexts(int a1)
{
  unsigned int v1; // esi
  int v2; // r13d
  int i; // ebx
  __int64 *v4; // r15
  DWORD LowPart; // ecx
  __int64 v6; // rbp
  int v7; // eax
  __int64 *v8; // r14
  int v9; // ebx
  __int64 v10; // rdi
  HANDLE v11; // rax
  int v12; // edi
  __int64 v13; // rbx
  HANDLE v14; // rax
  signed __int64 v15; // r14
  __int64 v16; // rax
  signed __int64 v17; // rbx
  __int64 v18; // rdi
  HANDLE v19; // rax
  __int64 v20; // rbx
  HANDLE CurrentThreadId; // rax
  int v22; // edi
  __int64 v23; // rbx
  HANDLE v24; // rax
  unsigned int v25; // ebx
  union _LARGE_INTEGER Interval; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v28; // [rsp+90h] [rbp+18h]
  __int64 v29; // [rsp+98h] [rbp+20h] BYREF

  v1 = 0;
  v2 = 0;
  v28 = 0;
  for ( i = a1; ; i = a1 )
  {
    ExAcquireResourceExclusiveLite(&UMRxAsyncEngineContextListLock, 1u);
    v4 = (__int64 *)UMRxAsyncEngineContextList;
    LowPart = 0;
    Interval.LowPart = 0;
    if ( (__int64 *)UMRxAsyncEngineContextList != &UMRxAsyncEngineContextList )
    {
      while ( 1 )
      {
        v6 = (__int64)(v4 - 4);
        v7 = *((_DWORD *)v4 + 8);
        v8 = v4;
        v4 = (__int64 *)*v4;
        v29 = v6;
        if ( !v7 )
        {
          Interval.LowPart = LowPart + 1;
          goto LABEL_62;
        }
        if ( !i )
          break;
        if ( (unsigned int)(*(_DWORD *)(v6 + 48) - 2) > 1 )
          goto LABEL_55;
LABEL_54:
        if ( v2 )
        {
LABEL_55:
          _InterlockedIncrement((volatile signed __int32 *)(v6 + 4));
          *(_DWORD *)(v6 + 48) = 3;
          ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            CurrentThreadId = PsGetCurrentThreadId();
            WPP_SF_q(v20, 17, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId);
          }
          v22 = MRxDAVCancelTheContext(v6, 0, 1);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v24 = PsGetCurrentThreadId();
            WPP_SF_qD(v23, 18, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v24, v22);
          }
          v2 = 0;
          ExAcquireResourceExclusiveLite(&UMRxAsyncEngineContextListLock, 1u);
          UMRxFinalizeAsyncEngineContext(&v29);
          v4 = (__int64 *)UMRxAsyncEngineContextList;
        }
LABEL_62:
        LowPart = Interval.LowPart;
        i = a1;
        if ( v4 == &UMRxAsyncEngineContextList )
          goto LABEL_63;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v9 = *((_DWORD *)v8 + 178);
        v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v11 = PsGetCurrentThreadId();
        WPP_SF_qD(v10, 14, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v11, v9);
      }
      v12 = *((_DWORD *)v8 + 178);
      if ( v12 > 8 )
      {
        switch ( v12 )
        {
          case 11:
            v1 = QueryDirectoryRequestTimeoutValueInSec;
            goto LABEL_45;
          case 12:
            v1 = SetFileInfoRequestTimeoutValueInSec;
            goto LABEL_45;
          case 13:
            v1 = QueryFileInfoRequestTimeoutValueInSec;
            goto LABEL_45;
          case 14:
            v1 = QueryVolumeInfoRequestTimeoutValueInSec;
            goto LABEL_45;
          case 15:
            v1 = LockRefreshRequestTimeoutValueInSec;
            goto LABEL_45;
          case 16:
            v1 = FsCtlRequestTimeoutValueInSec;
            goto LABEL_45;
          case 17:
            v1 = DevFsCtlRequestTimeoutValueInSec;
            goto LABEL_45;
        }
      }
      else
      {
        switch ( v12 )
        {
          case 8:
            v1 = ReNameRequestTimeoutValueInSec;
            goto LABEL_45;
          case 0:
            v1 = CreateRequestTimeoutValueInSec;
            goto LABEL_45;
          case 1:
            v1 = FinalizeFobxRequestTimeoutValueInSec;
            goto LABEL_45;
          case 2:
            v1 = FinalizeFcbRequestTimeoutValueInSec;
            goto LABEL_45;
          case 3:
            v1 = CreateSrvCallRequestTimeoutValueInSec;
            goto LABEL_45;
          case 4:
            v1 = CreateVNetRootRequestTimeoutValueInSec;
            goto LABEL_45;
          case 5:
            v1 = FinalizeSrvCallRequestTimeoutValueInSec;
            goto LABEL_45;
          case 6:
            v1 = FinalizeVNetRootRequestTimeoutValueInSec;
            goto LABEL_45;
          case 7:
            v1 = CloseRequestTimeoutValueInSec;
LABEL_45:
            v15 = v1 * (unsigned __int64)(0x989680 / KeQueryTimeIncrement());
            v16 = *(_QWORD *)(v6 + 72);
            if ( v16 == 0xFFFFFFFFLL )
            {
              v17 = 0;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
              {
                v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                v19 = PsGetCurrentThreadId();
                WPP_SF_q(v18, 16, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v19);
              }
            }
            else
            {
              v17 = MEMORY[0xFFFFF78000000320] - v16;
            }
            if ( v17 > v15 && (unsigned int)(*(_DWORD *)(v6 + 48) - 2) > 1 )
            {
              *(_QWORD *)(v6 + 72) = 0xFFFFFFFFLL;
              v2 = 1;
            }
            goto LABEL_54;
        }
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v14 = PsGetCurrentThreadId();
        WPP_SF_qD(v13, 15, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v14, v12);
      }
      goto LABEL_45;
    }
LABEL_63:
    ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
    if ( !Interval.LowPart )
      break;
    if ( !a1 )
      break;
    v25 = v28;
    if ( v28 >= 0xA )
      break;
    Interval.QuadPart = -500000;
    KeDelayExecutionThread(0, 0, &Interval);
    v28 = v25 + 1;
  }
}

```

## disassembly

```asm
0x140005554  mov     [rsp+arg_0], ecx
0x140005558  push    rbx
0x140005559  push    rbp
0x14000555a  push    rsi
0x14000555b  push    rdi
0x14000555c  push    r12
0x14000555e  push    r13
0x140005560  push    r14
0x140005562  push    r15
0x140005564  sub     rsp, 38h
0x140005568  xor     esi, esi
0x14000556a  lea     rbp, UMRxAsyncEngineContextList
0x140005571  xor     r13d, r13d
0x140005574  mov     [rsp+78h+arg_10], esi
0x14000557b  mov     ebx, ecx
0x14000557d  lea     rdi, WPP_GLOBAL_Control
0x140005584  mov     dl, 1; Wait
0x140005586  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x14000558d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140005594  nop     dword ptr [rax+rax+00h]
0x140005599  mov     r15, cs:UMRxAsyncEngineContextList
0x1400055a0  xor     ecx, ecx
0x1400055a2  mov     dword ptr [rsp+78h+Interval], ecx
0x1400055a9  mov     r12d, 1
0x1400055af  cmp     r15, rbp
0x1400055b2  jz      loc_14000595E
0x1400055b8  lea     rbp, [r15-20h]
0x1400055bc  mov     eax, [rbp+40h]
0x1400055bf  lea     r14, [r15]
0x1400055c2  mov     r15, [r15]
0x1400055c5  mov     [rsp+78h+arg_18], rbp
0x1400055cd  test    eax, eax
0x1400055cf  jnz     short loc_1400055DF
0x1400055d1  inc     ecx
0x1400055d3  mov     dword ptr [rsp+78h+Interval], ecx
0x1400055da  jmp     loc_140005934
0x1400055df  test    ebx, ebx
0x1400055e1  jnz     loc_140005832
0x1400055e7  mov     rdi, cs:WPP_GLOBAL_Control
0x1400055ee  lea     rdx, WPP_GLOBAL_Control
0x1400055f5  cmp     rdi, rdx
0x1400055f8  jz      short loc_14000563C
0x1400055fa  test    dword ptr [rdi+2Ch], 2000h
0x140005601  jz      short loc_14000563C
0x140005603  mov     ebx, [r14+2C8h]
0x14000560a  mov     rdi, [rdi+18h]
0x14000560e  call    cs:__imp_PsGetCurrentThreadId
0x140005615  nop     dword ptr [rax+rax+00h]
0x14000561a  mov     edx, 0Eh
0x14000561f  mov     [rsp+78h+var_58], ebx
0x140005623  mov     r9, rax
0x140005626  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x14000562d  mov     rcx, rdi
0x140005630  call    WPP_SF_qD
0x140005635  lea     rdx, WPP_GLOBAL_Control
0x14000563c  mov     edi, [r14+2C8h]
0x140005643  cmp     edi, 8
0x140005646  jg      loc_1400056E2
0x14000564c  jz      loc_1400056D7
0x140005652  mov     ecx, edi
0x140005654  test    edi, edi
0x140005656  jz      short loc_1400056CC
0x140005658  sub     ecx, 1
0x14000565b  jz      short loc_1400056C1
0x14000565d  sub     ecx, 1
0x140005660  jz      short loc_1400056B6
0x140005662  sub     ecx, 1
0x140005665  jz      short loc_1400056AB
0x140005667  sub     ecx, 1
0x14000566a  jz      short loc_1400056A0
0x14000566c  sub     ecx, 1
0x14000566f  jz      short loc_140005695
0x140005671  sub     ecx, 1
0x140005674  jz      short loc_14000568A
0x140005676  cmp     ecx, 1
0x140005679  jnz     loc_14000570F
0x14000567f  mov     esi, cs:CloseRequestTimeoutValueInSec
0x140005685  jmp     loc_140005787
0x14000568a  mov     esi, cs:FinalizeVNetRootRequestTimeoutValueInSec
0x140005690  jmp     loc_140005787
0x140005695  mov     esi, cs:FinalizeSrvCallRequestTimeoutValueInSec
0x14000569b  jmp     loc_140005787
0x1400056a0  mov     esi, cs:CreateVNetRootRequestTimeoutValueInSec
0x1400056a6  jmp     loc_140005787
0x1400056ab  mov     esi, cs:CreateSrvCallRequestTimeoutValueInSec
0x1400056b1  jmp     loc_140005787
0x1400056b6  mov     esi, cs:FinalizeFcbRequestTimeoutValueInSec
0x1400056bc  jmp     loc_140005787
0x1400056c1  mov     esi, cs:FinalizeFobxRequestTimeoutValueInSec
0x1400056c7  jmp     loc_140005787
0x1400056cc  mov     esi, cs:CreateRequestTimeoutValueInSec
0x1400056d2  jmp     loc_140005787
0x1400056d7  mov     esi, cs:ReNameRequestTimeoutValueInSec
0x1400056dd  jmp     loc_140005787
0x1400056e2  mov     ecx, edi
0x1400056e4  sub     ecx, 0Bh
0x1400056e7  jz      loc_140005781
0x1400056ed  sub     ecx, 1
0x1400056f0  jz      loc_140005779
0x1400056f6  sub     ecx, 1
0x1400056f9  jz      short loc_140005771
0x1400056fb  sub     ecx, 1
0x1400056fe  jz      short loc_140005769
0x140005700  sub     ecx, 1
0x140005703  jz      short loc_140005761
0x140005705  sub     ecx, 1
0x140005708  jz      short loc_140005759
0x14000570a  cmp     ecx, 1
0x14000570d  jz      short loc_140005751
0x14000570f  mov     rbx, cs:WPP_GLOBAL_Control
0x140005716  cmp     rbx, rdx
0x140005719  jz      short loc_140005787
0x14000571b  test    dword ptr [rbx+2Ch], 2000h
0x140005722  jz      short loc_140005787
0x140005724  mov     rbx, [rbx+18h]
0x140005728  call    cs:__imp_PsGetCurrentThreadId
0x14000572f  nop     dword ptr [rax+rax+00h]
0x140005734  mov     edx, 0Fh
0x140005739  mov     [rsp+78h+var_58], edi
0x14000573d  mov     r9, rax
0x140005740  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x140005747  mov     rcx, rbx
0x14000574a  call    WPP_SF_qD
0x14000574f  jmp     short loc_140005787
0x140005751  mov     esi, cs:DevFsCtlRequestTimeoutValueInSec
0x140005757  jmp     short loc_140005787
0x140005759  mov     esi, cs:FsCtlRequestTimeoutValueInSec
0x14000575f  jmp     short loc_140005787
0x140005761  mov     esi, cs:LockRefreshRequestTimeoutValueInSec
0x140005767  jmp     short loc_140005787
0x140005769  mov     esi, cs:QueryVolumeInfoRequestTimeoutValueInSec
0x14000576f  jmp     short loc_140005787
0x140005771  mov     esi, cs:QueryFileInfoRequestTimeoutValueInSec
0x140005777  jmp     short loc_140005787
0x140005779  mov     esi, cs:SetFileInfoRequestTimeoutValueInSec
0x14000577f  jmp     short loc_140005787
0x140005781  mov     esi, cs:QueryDirectoryRequestTimeoutValueInSec
0x140005787  call    cs:__imp_KeQueryTimeIncrement
0x14000578e  nop     dword ptr [rax+rax+00h]
0x140005793  xor     edx, edx
0x140005795  mov     rbx, 0FFFFF78000000320h
0x14000579f  mov     ecx, eax
0x1400057a1  mov     eax, 989680h
0x1400057a6  div     ecx
0x1400057a8  mov     rbx, [rbx]
0x1400057ab  mov     ecx, 0FFFFFFFFh
0x1400057b0  mov     r14d, eax
0x1400057b3  mov     eax, esi
0x1400057b5  imul    r14, rax
0x1400057b9  mov     rax, [rbp+48h]
0x1400057bd  cmp     rax, rcx
0x1400057c0  jz      short loc_1400057C7
0x1400057c2  sub     rbx, rax
0x1400057c5  jmp     short loc_14000580F
0x1400057c7  xor     ebx, ebx
0x1400057c9  mov     rdi, cs:WPP_GLOBAL_Control
0x1400057d0  lea     rax, WPP_GLOBAL_Control
0x1400057d7  cmp     rdi, rax
0x1400057da  jz      short loc_14000580F
0x1400057dc  test    dword ptr [rdi+2Ch], 2000h
0x1400057e3  jz      short loc_14000580F
0x1400057e5  mov     rdi, [rdi+18h]
0x1400057e9  call    cs:__imp_PsGetCurrentThreadId
0x1400057f0  nop     dword ptr [rax+rax+00h]
0x1400057f5  lea     edx, [rbx+10h]
0x1400057f8  mov     rcx, rdi
0x1400057fb  mov     r9, rax
0x1400057fe  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x140005805  call    WPP_SF_q
0x14000580a  mov     ecx, 0FFFFFFFFh
0x14000580f  lea     rdi, WPP_GLOBAL_Control
0x140005816  cmp     rbx, r14
0x140005819  jle     short loc_14000583D
0x14000581b  mov     eax, [rbp+30h]
0x14000581e  sub     eax, 2
0x140005821  cmp     eax, 1
0x140005824  jbe     short loc_14000583D
0x140005826  mov     [rbp+48h], rcx
0x14000582a  mov     r13d, 1
0x140005830  jmp     short loc_14000583D
0x140005832  mov     eax, [rbp+30h]
0x140005835  sub     eax, 2
0x140005838  cmp     eax, 1
0x14000583b  ja      short loc_140005846
0x14000583d  test    r13d, r13d
0x140005840  jz      loc_140005934
0x140005846  lock inc dword ptr [rbp+4]
0x14000584a  mov     dword ptr [rbp+30h], 3
0x140005851  test    r12d, r12d
0x140005854  jz      short loc_14000586C
0x140005856  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x14000585d  call    cs:__imp_ExReleaseResourceLite
0x140005864  nop     dword ptr [rax+rax+00h]
0x140005869  xor     r12d, r12d
0x14000586c  mov     rbx, cs:WPP_GLOBAL_Control
0x140005873  cmp     rbx, rdi
0x140005876  jz      short loc_1400058A8
0x140005878  test    dword ptr [rbx+2Ch], 2000h
0x14000587f  jz      short loc_1400058A8
0x140005881  mov     rbx, [rbx+18h]
0x140005885  call    cs:__imp_PsGetCurrentThreadId
0x14000588c  nop     dword ptr [rax+rax+00h]
0x140005891  mov     edx, 11h
0x140005896  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x14000589d  mov     r9, rax
0x1400058a0  mov     rcx, rbx
0x1400058a3  call    WPP_SF_q
0x1400058a8  xor     edx, edx
0x1400058aa  mov     rcx, rbp
0x1400058ad  lea     r8d, [rdx+1]
0x1400058b1  call    MRxDAVCancelTheContext
0x1400058b6  mov     edi, eax
0x1400058b8  mov     rbx, cs:WPP_GLOBAL_Control
0x1400058bf  lea     rax, WPP_GLOBAL_Control
0x1400058c6  cmp     rbx, rax
0x1400058c9  jz      short loc_1400058FF
0x1400058cb  test    dword ptr [rbx+2Ch], 2000h
0x1400058d2  jz      short loc_1400058FF
0x1400058d4  mov     rbx, [rbx+18h]
0x1400058d8  call    cs:__imp_PsGetCurrentThreadId
0x1400058df  nop     dword ptr [rax+rax+00h]
0x1400058e4  mov     edx, 12h
0x1400058e9  mov     [rsp+78h+var_58], edi
0x1400058ed  mov     r9, rax
0x1400058f0  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x1400058f7  mov     rcx, rbx
0x1400058fa  call    WPP_SF_qD
0x1400058ff  xor     r13d, r13d
0x140005902  test    r12d, r12d
0x140005905  jnz     short loc_140005920
0x140005907  mov     dl, 1; Wait
0x140005909  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x140005910  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140005917  nop     dword ptr [rax+rax+00h]
0x14000591c  lea     r12d, [r13+1]
0x140005920  lea     rcx, [rsp+78h+arg_18]
0x140005928  call    UMRxFinalizeAsyncEngineContext
0x14000592d  mov     r15, cs:UMRxAsyncEngineContextList
0x140005934  mov     ecx, dword ptr [rsp+78h+Interval]
0x14000593b  lea     rbp, UMRxAsyncEngineContextList
0x140005942  mov     ebx, [rsp+78h+arg_0]
0x140005949  lea     rdi, WPP_GLOBAL_Control
0x140005950  cmp     r15, rbp
0x140005953  jnz     loc_1400055B8
0x140005959  test    r12d, r12d
0x14000595c  jz      short loc_140005971
0x14000595e  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x140005965  call    cs:__imp_ExReleaseResourceLite
0x14000596c  nop     dword ptr [rax+rax+00h]
0x140005971  cmp     dword ptr [rsp+78h+Interval], 0
0x140005979  jbe     short loc_1400059CA
0x14000597b  cmp     [rsp+78h+arg_0], 0
0x140005983  jz      short loc_1400059CA
0x140005985  mov     ebx, [rsp+78h+arg_10]
0x14000598c  cmp     ebx, 0Ah
0x14000598f  jnb     short loc_1400059CA
0x140005991  lea     r8, [rsp+78h+Interval]; Interval
0x140005999  mov     qword ptr [rsp+78h+Interval], 0FFFFFFFFFFF85EE0h
0x1400059a5  xor     edx, edx; Alertable
0x1400059a7  xor     ecx, ecx; WaitMode
0x1400059a9  call    cs:__imp_KeDelayExecutionThread
0x1400059b0  nop     dword ptr [rax+rax+00h]
0x1400059b5  inc     ebx
0x1400059b7  mov     [rsp+78h+arg_10], ebx
0x1400059be  mov     ebx, [rsp+78h+arg_0]
0x1400059c5  jmp     loc_14000557D
0x1400059ca  add     rsp, 38h
0x1400059ce  pop     r15
0x1400059d0  pop     r14
0x1400059d2  pop     r13
0x1400059d4  pop     r12
0x1400059d6  pop     rdi
0x1400059d7  pop     rsi
0x1400059d8  pop     rbp
0x1400059d9  pop     rbx
0x1400059da  retn
```
