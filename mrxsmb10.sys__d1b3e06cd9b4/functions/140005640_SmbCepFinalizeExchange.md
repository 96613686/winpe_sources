# SmbCepFinalizeExchange

- ea: `0x140005640`
- end: `0x140005a9e`
- name: `SmbCepFinalizeExchange`
- size: `1118`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400054b0`
- `0x140012d48`

## callees

- `0x140005640`
- `0x140005aa4`
- `0x140005c60`
- `0x140016640`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400057aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400057d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400058a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000594b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400057aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400057d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400058a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000594b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005694`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000586d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005694`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000586d`
- `ntoskrnl!IoFreeMdl` at `0x140005a6a`
- `ntoskrnl!IoFreeMdl` at `0x140005a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a86`
- `rdbss!RxPostToWorkerThread` at `0x14000584d`
- `rdbss!RxPostToWorkerThread` at `0x1400058d4`
- `rdbss!RxPostToWorkerThread` at `0x14000584d`
- `rdbss!RxPostToWorkerThread` at `0x1400058d4`
- `mrxsmb!MRxSmbDeviceObject` at `0x14000582b`
- `mrxsmb!MRxSmbDeviceObject` at `0x1400058b2`

## pseudocode

```c
NTSTATUS __fastcall SmbCepFinalizeExchange(char *pContext)
{
  int v1; // eax
  __int64 v3; // rsi
  _QWORD *v4; // rdi
  KIRQL v5; // al
  int v6; // ecx
  _QWORD *v7; // rdx
  __int64 v8; // r9
  unsigned __int16 v9; // cx
  __int16 v10; // r8
  unsigned __int64 v11; // r10
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int16 v15; // r11
  __int16 v16; // r11
  NTSTATUS result; // eax
  __int64 v18; // rdi
  KIRQL v19; // al
  int v20; // ecx
  unsigned __int64 v21; // r11
  __int64 v22; // rcx
  __int64 *v23; // r11
  int v24; // eax
  __int64 v25; // rcx
  _QWORD *v26; // r8
  __int64 v27; // rax
  _QWORD *v28; // rcx
  __int64 *v29; // rdx
  __int64 *v30; // r8
  bool i; // zf
  unsigned __int64 *v32; // rax
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rcx
  unsigned __int64 *v35; // rax
  unsigned __int64 v36; // rcx
  void *v37; // rcx
  char v38; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_DWORD *)pContext + 18);
  if ( v1 >= 0 )
  {
    v38 = 0;
    *((_QWORD *)pContext + 18) = 0;
    if ( (v1 & 2) != 0 )
    {
LABEL_19:
      if ( *((_QWORD *)pContext + 40) )
      {
        IoFreeMdl(*((PMDL *)pContext + 41));
        v37 = (void *)*((_QWORD *)pContext + 40);
        *((_QWORD *)pContext + 41) = 0;
        ExFreePoolWithTag(v37, 0);
        *((_QWORD *)pContext + 40) = 0;
      }
      result = (*(__int64 (__fastcall **)(char *, char *))(*((_QWORD *)pContext + 19) + 32LL))(pContext, &v38);
      if ( !result )
      {
        if ( v38 )
          return RxPostToWorkerThread(
                   MRxSmbDeviceObject,
                   NormalWorkQueue,
                   (PRX_WORK_QUEUE_ITEM)(pContext + 176),
                   SmbCeFinalizeExchangeWorkerThreadRoutine,
                   pContext);
      }
      return result;
    }
    if ( *((_WORD *)pContext + 32) == 0xFFFF )
    {
LABEL_18:
      *((_DWORD *)pContext + 18) &= ~1u;
      goto LABEL_19;
    }
    v3 = *((_QWORD *)pContext + 10);
    v4 = 0;
    v5 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
    v6 = *((_DWORD *)pContext + 18);
    s_SmbCeDbSpinLockSavedIrql = v5;
    if ( (v6 & 1) != 0 )
    {
      v7 = *(_QWORD **)(v3 + 352);
      if ( v7 != (_QWORD *)(v3 + 352) )
      {
        v4 = v7 - 4;
        if ( v7 != (_QWORD *)32 )
        {
          v25 = *v7;
          if ( *(_QWORD **)(*v7 + 8LL) != v7 )
            goto LABEL_35;
          v26 = (_QWORD *)v7[1];
          if ( (_QWORD *)*v26 != v7 )
            goto LABEL_35;
          *v26 = v25;
          *(_QWORD *)(v25 + 8) = v26;
        }
      }
      v8 = *(_QWORD *)(v3 + 384);
      if ( v8 )
      {
        v9 = *(_WORD *)(v8 + 8);
        if ( v9 >= 0x10u )
          v10 = *((_WORD *)pContext + 32);
        else
          v10 = *((_WORD *)pContext + 32) & ((1 << v9) - 1);
        v11 = *(_QWORD *)(v8 + 48);
        if ( v4 )
        {
          while ( 1 )
          {
            v12 = v11 + 8 * ((unsigned __int64)(unsigned __int16)(v10 & *(_WORD *)(v11 + 22)) >> *(_BYTE *)(v11 + 24));
            v13 = *(_QWORD *)(v12 + 40) & 3LL;
            if ( (_DWORD)v13 == 2 )
              break;
            if ( (_DWORD)v13 == 1 )
              goto LABEL_13;
            v33 = *(_QWORD *)(v12 + 40) & 0xFFFFFFFFFFFFFFFCuLL;
            if ( (_DWORD)v13 != 3 )
              v33 = v11;
            v11 = v33;
          }
          *(_QWORD *)(v12 + 40) = v4[7] | 2LL;
LABEL_13:
          *(_DWORD *)(v4[7] + 72LL) |= 1u;
          if ( *(_WORD *)(*(_QWORD *)(v3 + 384) + 8LL) >= 0x10u )
          {
            v16 = v10;
          }
          else
          {
            v14 = v4[7];
            v15 = (unsigned __int16)_InterlockedIncrement((volatile signed __int32 *)(v3 + 492)) << *(_BYTE *)(*(_QWORD *)(v3 + 384) + 8LL);
            *(_WORD *)(v14 + 62) = v15;
            v16 = v10 | v15;
          }
          *(_WORD *)(v4[7] + 64LL) = v16;
          *(_DWORD *)(v4[8] + 4LL) = 0;
          KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
LABEL_16:
          SmbCeResume(v4[8]);
          SmbMmFreeObjectPool(v4);
          goto LABEL_18;
        }
        while ( 1 )
        {
          v21 = ((unsigned __int64)(unsigned __int16)(v10 & *(_WORD *)(v11 + 22)) >> *(_BYTE *)(v11 + 24)) + 5;
          v22 = *(_QWORD *)(v11 + 8 * v21);
          v23 = (__int64 *)(v11 + 8 * v21);
          v24 = v22 & 3;
          if ( v24 == 2 )
            break;
          if ( v24 == 1 )
            goto LABEL_31;
          v34 = v22 & 0xFFFFFFFFFFFFFFFCuLL;
          if ( v24 != 3 )
            v34 = v11;
          v11 = v34;
        }
        --*(_WORD *)(v11 + 18);
        if ( *(_QWORD *)(v11 + 32) )
        {
LABEL_30:
          *v23 = *(_QWORD *)(v11 + 32) | 1LL;
          *(_QWORD *)(v11 + 32) = v23;
LABEL_31:
          --*(_WORD *)(v8 + 4);
          KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
          goto LABEL_18;
        }
        v27 = *(_QWORD *)v11;
        if ( *(_QWORD *)(*(_QWORD *)v11 + 8LL) == v11 )
        {
          v28 = *(_QWORD **)(v11 + 8);
          if ( *v28 == v11 )
          {
            *v28 = v27;
            v29 = (__int64 *)(v8 + 16);
            *(_QWORD *)(v27 + 8) = v28;
            *(_QWORD *)(v11 + 8) = v11;
            *(_QWORD *)v11 = v11;
            v30 = *(__int64 **)(v8 + 16);
            for ( i = v30 == (__int64 *)(v8 + 16); ; i = v30 == v29 )
            {
              if ( i )
                v30 = 0;
              if ( !v30 )
                goto LABEL_46;
              if ( *((_BYTE *)v30 + 27) >= *(_BYTE *)(v11 + 27) )
                break;
              v30 = (__int64 *)*v30;
            }
            v35 = (unsigned __int64 *)v30[1];
            if ( v35 )
            {
              v36 = *v35;
              if ( *(unsigned __int64 **)(*v35 + 8) == v35 )
              {
                *(_QWORD *)v11 = v36;
                *(_QWORD *)(v11 + 8) = v35;
                *(_QWORD *)(v36 + 8) = v11;
                *v35 = v11;
                goto LABEL_30;
              }
            }
            else
            {
LABEL_46:
              v32 = *(unsigned __int64 **)(v8 + 24);
              if ( (__int64 *)*v32 == v29 )
              {
                *(_QWORD *)v11 = v29;
                *(_QWORD *)(v11 + 8) = v32;
                *v32 = v11;
                *(_QWORD *)(v8 + 24) = v11;
                goto LABEL_30;
              }
            }
          }
        }
LABEL_35:
        __fastfail(3u);
      }
    }
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, v5);
    if ( !v4 )
      goto LABEL_18;
    goto LABEL_16;
  }
  v18 = *((_QWORD *)pContext + 20);
  v19 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v20 = *(_DWORD *)(v18 + 72);
  s_SmbCeDbSpinLockSavedIrql = v19;
  if ( (v20 & 8) == 0 )
    ++*(_DWORD *)(v18 + 116);
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, v19);
  return RxPostToWorkerThread(
           MRxSmbDeviceObject,
           NormalWorkQueue,
           (PRX_WORK_QUEUE_ITEM)(pContext + 176),
           SmbCepFinalizeAssociatedExchange,
           pContext);
}

```

## disassembly

```asm
0x140005640  push    rbx
0x140005642  push    rsi
0x140005643  push    rdi
0x140005644  sub     rsp, 30h
0x140005648  mov     eax, [rcx+48h]
0x14000564b  mov     rbx, rcx
0x14000564e  test    eax, eax
0x140005650  js      loc_14000585B
0x140005656  mov     [rsp+48h+arg_8], rbp
0x14000565b  xor     ebp, ebp
0x14000565d  mov     [rsp+48h+arg_10], r14
0x140005662  mov     [rsp+48h+arg_0], 0
0x140005667  mov     [rcx+90h], rbp
0x14000566e  test    al, 2
0x140005670  jnz     loc_1400057E8
0x140005676  mov     r14d, 0FFFFh
0x14000567c  cmp     [rcx+40h], r14w
0x140005681  jz      loc_1400057E4
0x140005687  mov     rsi, [rcx+50h]
0x14000568b  mov     edi, ebp
0x14000568d  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140005694  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000569b  nop     dword ptr [rax+rax+00h]
0x1400056a0  mov     ecx, [rbx+48h]
0x1400056a3  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x1400056a9  test    cl, 1
0x1400056ac  jz      loc_1400057C9
0x1400056b2  lea     rcx, [rsi+160h]
0x1400056b9  mov     rdx, [rcx]
0x1400056bc  cmp     rdx, rcx
0x1400056bf  jz      short loc_1400056CE
0x1400056c1  lea     rdi, [rdx-20h]
0x1400056c5  test    rdi, rdi
0x1400056c8  jnz     loc_14000596E
0x1400056ce  mov     r9, [rsi+180h]
0x1400056d5  test    r9, r9
0x1400056d8  jz      loc_1400057C9
0x1400056de  movzx   ecx, word ptr [r9+8]
0x1400056e3  mov     r11d, 1
0x1400056e9  movzx   eax, word ptr [rbx+40h]
0x1400056ed  cmp     cx, 10h
0x1400056f1  jnb     loc_14000595C
0x1400056f7  mov     r8d, r11d
0x1400056fa  shl     r8w, cl
0x1400056fe  dec     r8w
0x140005702  and     r8w, ax
0x140005706  mov     r10, [r9+30h]
0x14000570a  test    rdi, rdi
0x14000570d  jz      loc_1400058F0
0x140005713  movzx   ecx, byte ptr [r10+18h]
0x140005718  movzx   edx, word ptr [r10+16h]
0x14000571d  movzx   eax, r8w
0x140005721  and     rdx, rax
0x140005724  shr     rdx, cl
0x140005727  lea     rcx, [r10+rdx*8]
0x14000572b  mov     rdx, [r10+rdx*8+28h]
0x140005730  mov     eax, edx
0x140005732  and     eax, 3
0x140005735  cmp     eax, 2
0x140005738  jnz     loc_140005A02
0x14000573e  mov     rax, [rdi+38h]
0x140005742  or      rax, 2
0x140005746  mov     [rcx+28h], rax
0x14000574a  mov     rax, [rdi+38h]
0x14000574e  or      [rax+48h], r11d
0x140005752  mov     rax, [rsi+180h]
0x140005759  cmp     word ptr [rax+8], 10h
0x14000575e  jnb     loc_140005965
0x140005764  mov     rax, [rdi+38h]
0x140005768  lock xadd [rsi+1ECh], r11d
0x140005771  mov     rcx, [rsi+180h]
0x140005778  inc     r11d
0x14000577b  movzx   ecx, byte ptr [rcx+8]
0x14000577f  shl     r11w, cl
0x140005783  mov     [rax+3Eh], r11w
0x140005788  or      r11w, r8w
0x14000578c  mov     rax, [rdi+38h]
0x140005790  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140005797  mov     [rax+40h], r11w
0x14000579c  mov     rax, [rdi+40h]
0x1400057a0  mov     [rax+4], ebp
0x1400057a3  movzx   edx, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x1400057aa  call    cs:__imp_KeReleaseSpinLock
0x1400057b1  nop     dword ptr [rax+rax+00h]
0x1400057b6  mov     rcx, [rdi+40h]
0x1400057ba  call    SmbCeResume
0x1400057bf  mov     rcx, rdi
0x1400057c2  call    SmbMmFreeObjectPool
0x1400057c7  jmp     short loc_1400057E4
0x1400057c9  movzx   edx, al; NewIrql
0x1400057cc  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400057d3  call    cs:__imp_KeReleaseSpinLock
0x1400057da  nop     dword ptr [rax+rax+00h]
0x1400057df  test    rdi, rdi
0x1400057e2  jnz     short loc_1400057B6
0x1400057e4  and     dword ptr [rbx+48h], 0FFFFFFFEh
0x1400057e8  cmp     [rbx+140h], rbp
0x1400057ef  jnz     loc_140005A63
0x1400057f5  mov     rax, [rbx+98h]
0x1400057fc  lea     rdx, [rsp+48h+arg_0]
0x140005801  mov     rcx, rbx
0x140005804  mov     rax, [rax+20h]
0x140005808  call    _guard_dispatch_icall
0x14000580d  test    eax, eax
0x14000580f  jz      short loc_140005824
0x140005811  mov     rbp, [rsp+48h+arg_8]
0x140005816  mov     r14, [rsp+48h+arg_10]
0x14000581b  add     rsp, 30h
0x14000581f  pop     rdi
0x140005820  pop     rsi
0x140005821  pop     rbx
0x140005822  retn
0x140005824  cmp     [rsp+48h+arg_0], bpl
0x140005829  jz      short loc_140005811
0x14000582b  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140005832  lea     r8, [rbx+0B0h]; pWorkQueueItem
0x140005839  lea     r9, SmbCeFinalizeExchangeWorkerThreadRoutine; Routine
0x140005840  mov     [rsp+48h+pContext], rbx; pContext
0x140005845  mov     edx, 3; WorkQueueType
0x14000584a  mov     rcx, [rcx]; pMRxDeviceObject
0x14000584d  call    cs:__imp_RxPostToWorkerThread
0x140005854  nop     dword ptr [rax+rax+00h]
0x140005859  jmp     short loc_140005811
0x14000585b  mov     rdi, [rcx+0A0h]
0x140005862  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140005869  mov     rsi, [rdi+50h]
0x14000586d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005874  nop     dword ptr [rax+rax+00h]
0x140005879  mov     ecx, [rdi+48h]
0x14000587c  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140005882  test    cl, 8
0x140005885  jnz     short loc_14000589C
0x140005887  test    rsi, rsi
0x14000588a  jz      short loc_140005899
0x14000588c  cmp     dword ptr [rsi+148h], 0
0x140005893  jnz     loc_1400059F8
0x140005899  inc     dword ptr [rdi+74h]
0x14000589c  movzx   edx, al; NewIrql
0x14000589f  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400058a6  call    cs:__imp_KeReleaseSpinLock
0x1400058ad  nop     dword ptr [rax+rax+00h]
0x1400058b2  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x1400058b9  lea     r8, [rbx+0B0h]; pWorkQueueItem
0x1400058c0  lea     r9, SmbCepFinalizeAssociatedExchange; Routine
0x1400058c7  mov     [rsp+48h+pContext], rbx; pContext
0x1400058cc  mov     edx, 3; WorkQueueType
0x1400058d1  mov     rcx, [rcx]; pMRxDeviceObject
0x1400058d4  call    cs:__imp_RxPostToWorkerThread
0x1400058db  nop     dword ptr [rax+rax+00h]
0x1400058e0  add     rsp, 30h
0x1400058e4  pop     rdi
0x1400058e5  pop     rsi
0x1400058e6  pop     rbx
0x1400058e7  retn
0x1400058f0  movzx   ecx, byte ptr [r10+18h]
0x1400058f5  movzx   r11d, word ptr [r10+16h]
0x1400058fa  movzx   eax, r8w
0x1400058fe  and     r11, rax
0x140005901  shr     r11, cl
0x140005904  add     r11, 5
0x140005908  mov     rcx, [r10+r11*8]
0x14000590c  lea     r11, [r10+r11*8]
0x140005910  mov     eax, ecx
0x140005912  and     eax, 3
0x140005915  cmp     eax, 2
0x140005918  jnz     loc_140005A1E
0x14000591e  add     [r10+12h], r14w
0x140005923  cmp     [r10+20h], rbp
0x140005927  jz      short loc_140005993
0x140005929  mov     rax, [r10+20h]
0x14000592d  or      rax, 1
0x140005931  mov     [r11], rax
0x140005934  mov     [r10+20h], r11
0x140005938  add     [r9+4], r14w
0x14000593d  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140005944  movzx   edx, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000594b  call    cs:__imp_KeReleaseSpinLock
0x140005952  nop     dword ptr [rax+rax+00h]
0x140005957  jmp     loc_1400057E4
0x14000595c  movzx   r8d, ax
0x140005960  jmp     loc_140005706
0x140005965  movzx   r11d, r8w
0x140005969  jmp     loc_14000578C
0x14000596e  mov     rcx, [rdx]
0x140005971  cmp     [rcx+8], rdx
0x140005975  jz      short loc_14000597E
0x140005977  mov     ecx, 3
0x14000597c  int     29h; Win8: RtlFailFast(ecx)
0x14000597e  mov     r8, [rdx+8]
0x140005982  cmp     [r8], rdx
0x140005985  jnz     short loc_140005977
0x140005987  mov     [r8], rcx
0x14000598a  mov     [rcx+8], r8
0x14000598e  jmp     loc_1400056CE
0x140005993  mov     rax, [r10]
0x140005996  cmp     [rax+8], r10
0x14000599a  jnz     short loc_140005977
0x14000599c  mov     rcx, [r10+8]
0x1400059a0  cmp     [rcx], r10
0x1400059a3  jnz     short loc_140005977
0x1400059a5  mov     [rcx], rax
0x1400059a8  lea     rdx, [r9+10h]
0x1400059ac  mov     [rax+8], rcx
0x1400059b0  mov     [r10+8], r10
0x1400059b4  mov     [r10], r10
0x1400059b7  mov     r8, [rdx]
0x1400059ba  cmp     r8, rdx
0x1400059bd  cmovz   r8, rbp
0x1400059c1  test    r8, r8
0x1400059c4  jz      short loc_1400059DC
0x1400059c6  movzx   eax, byte ptr [r10+1Bh]
0x1400059cb  cmp     [r8+1Bh], al
0x1400059cf  jnb     short loc_140005A3A
0x1400059d1  mov     rcx, [r8]
0x1400059d4  mov     r8, rcx
0x1400059d7  cmp     rcx, rdx
0x1400059da  jmp     short loc_1400059BD
0x1400059dc  mov     rax, [rdx+8]
0x1400059e0  cmp     [rax], rdx
0x1400059e3  jnz     short loc_140005977
0x1400059e5  mov     [r10], rdx
0x1400059e8  mov     [r10+8], rax
0x1400059ec  mov     [rax], r10
0x1400059ef  mov     [rdx+8], r10
0x1400059f3  jmp     loc_140005929
0x1400059f8  mov     ecx, 0ED04h
0x1400059fd  jmp     loc_140005899
0x140005a02  cmp     eax, r11d
0x140005a05  jz      loc_14000574A
0x140005a0b  and     rdx, 0FFFFFFFFFFFFFFFCh
0x140005a0f  cmp     eax, 3
0x140005a12  cmovnz  rdx, r10
0x140005a16  mov     r10, rdx
0x140005a19  jmp     loc_140005713
0x140005a1e  cmp     eax, 1
0x140005a21  jz      loc_140005938
0x140005a27  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140005a2b  cmp     eax, 3
0x140005a2e  cmovnz  rcx, r10
0x140005a32  mov     r10, rcx
0x140005a35  jmp     loc_1400058F0
0x140005a3a  mov     rax, [r8+8]
0x140005a3e  test    rax, rax
0x140005a41  jz      short loc_1400059DC
0x140005a43  mov     rcx, [rax]
0x140005a46  cmp     [rcx+8], rax
0x140005a4a  jnz     loc_140005977
0x140005a50  mov     [r10], rcx
0x140005a53  mov     [r10+8], rax
0x140005a57  mov     [rcx+8], r10
0x140005a5b  mov     [rax], r10
0x140005a5e  jmp     loc_140005929
0x140005a63  mov     rcx, [rbx+148h]; Mdl
0x140005a6a  call    cs:__imp_IoFreeMdl
0x140005a71  nop     dword ptr [rax+rax+00h]
0x140005a76  mov     rcx, [rbx+140h]; P
0x140005a7d  xor     edx, edx; Tag
0x140005a7f  mov     [rbx+148h], rbp
0x140005a86  call    cs:__imp_ExFreePoolWithTag
0x140005a8d  nop     dword ptr [rax+rax+00h]
0x140005a92  mov     [rbx+140h], rbp
0x140005a99  jmp     loc_1400057F5
```
