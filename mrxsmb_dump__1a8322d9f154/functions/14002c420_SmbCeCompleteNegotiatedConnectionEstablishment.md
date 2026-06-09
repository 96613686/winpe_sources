# SmbCeCompleteNegotiatedConnectionEstablishment

- ea: `0x14002c420`
- end: `0x14002c7e2`
- name: `SmbCeCompleteNegotiatedConnectionEstablishment`
- size: `962`
- prototype: `void __fastcall(_DWORD *P)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14002c420`
- `0x1400424ac`
- `0x14004bcc4`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002c4f6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002c511`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002c4f6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002c511`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002c4d9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002c4d9`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002c751`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002c751`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002c459`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002c459`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c46f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c46f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c7c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c7c4`
- `rdbss!RxDiagnosticTrace` at `0x14002c6c6`
- `rdbss!RxDiagnosticTrace` at `0x14002c6c6`

## string_xrefs

- `0x14002c6a3`: `Update:Index %d TargetCount %d CurrentCount %d FailureCount %d`

## pseudocode

```c
void __fastcall SmbCeCompleteNegotiatedConnectionEstablishment(_DWORD *P)
{
  int v2; // r12d
  unsigned __int64 v3; // rax
  __int64 v4; // rbp
  __int64 v5; // rbx
  __int64 v6; // r15
  KIRQL v7; // di
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // r8d
  unsigned int v14; // esi
  __int64 v15; // rdi
  __int16 v16; // dx
  bool v17; // cl
  __int64 v18; // r8
  __int64 v19; // rdx
  unsigned int v20; // ecx
  unsigned int v21; // eax
  int v22; // r8d
  __int64 v23; // rbx
  KIRQL v24; // [rsp+90h] [rbp+8h]

  v2 = P[2];
  v3 = *((_QWORD *)P + 3) & 0xFFFFFFFFFFFFFFFEuLL;
  v4 = *(_QWORD *)(v3 + 432);
  v5 = *(_QWORD *)(v3 + 392);
  v6 = *(_QWORD *)(v4 + 24);
  v7 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920));
  v24 = v7;
  *(_DWORD *)(v6 + 2352) = (unsigned int)PsGetCurrentThreadId();
  if ( v2 >= 0 )
  {
    if ( !v5 || *(_DWORD *)(v5 + 12) )
    {
      v10 = 0x195C000020CLL;
      goto LABEL_46;
    }
    if ( *(_DWORD *)(v5 + 320) == 2 )
    {
      v9 = *(_QWORD *)(v5 + 32);
      if ( *(_DWORD *)(v9 + 56) != 1 || !*(_BYTE *)(v9 + 69) || !(_BYTE)word_14007D202 || *(_DWORD *)(v4 + 784) )
        goto LABEL_11;
      ExAcquirePushLockSharedEx(&MRxSmbRdmaRundownSrwLock, 0, v8);
      if ( MRxSmbRdmaRundownState )
      {
        ExReleasePushLockSharedEx(&MRxSmbRdmaRundownSrwLock, 0);
LABEL_11:
        v10 = 0x19BC000020CLL;
LABEL_46:
        *((_QWORD *)P + 1) = v10;
        goto LABEL_47;
      }
      ExReleasePushLockSharedEx(&MRxSmbRdmaRundownSrwLock, 0);
    }
    v11 = *(_QWORD **)(v4 + 624);
    if ( *v11 != v4 + 616 )
      __fastfail(3u);
    *(_QWORD *)(v5 + 536) = v4 + 616;
    *(_QWORD *)(v5 + 544) = v11;
    *v11 = v5 + 536;
    *(_QWORD *)(v4 + 624) = v5 + 536;
    *(_QWORD *)(v5 + 504) = v4;
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 632));
    v12 = *(_QWORD *)(v4 + 576);
    if ( v12 )
    {
      v13 = *(_DWORD *)(v12 + 8);
      if ( v13 )
      {
        v14 = 0;
        while ( 1 )
        {
          v15 = v12 + 312LL * v14;
          if ( ((*(_BYTE *)(v15 + 36) & 0x10) != 0) == (*(_DWORD *)(v5 + 320) == 2) )
          {
            v16 = *(_WORD *)(v15 + 56);
            if ( v16 == *(_WORD *)(v5 + 400) && *(_WORD *)(v15 + 200) == *(_WORD *)(v5 + 428) )
            {
              v17 = 0;
              if ( v16 == 23 )
              {
                if ( *(_QWORD *)(v15 + 72) == *(_QWORD *)(v5 + 416)
                  && *(_QWORD *)(v15 + 64) == *(_QWORD *)(v5 + 408)
                  && *(_QWORD *)(v15 + 216) == *(_QWORD *)(v5 + 444) )
                {
                  v17 = *(_QWORD *)(v15 + 208) == *(_QWORD *)(v5 + 436);
                }
              }
              else if ( *(_DWORD *)(v15 + 60) == *(_DWORD *)(v5 + 404) )
              {
                v17 = *(_DWORD *)(v15 + 204) == *(_DWORD *)(v5 + 432);
              }
              if ( v17 )
                break;
            }
          }
          if ( ++v14 >= v13 )
            goto LABEL_36;
        }
        ++*(_DWORD *)(v15 + 24);
        v18 = *(unsigned int *)(v15 + 20);
        v19 = *(unsigned int *)(v15 + 24);
        *(_DWORD *)(v15 + 28) = 0;
        *(_DWORD *)(v15 + 32) = 2 * v18;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_dddd(WPP_GLOBAL_Control->AttachedDevice, v19, v18, v14, v18, v19, 0);
        }
        RxDiagnosticTrace(
          *(_QWORD *)(v4 + 16),
          1,
          "Update:Index %d TargetCount %d CurrentCount %d FailureCount %d",
          v14,
          *(_DWORD *)(v15 + 20),
          *(_DWORD *)(v15 + 24),
          *(_DWORD *)(v15 + 28));
LABEL_36:
        v7 = v24;
      }
    }
    if ( (*(_DWORD *)(v4 + 716) & 0x800) != 0 )
    {
      v20 = *(_DWORD *)(v4 + 704);
      if ( v20 <= *(_DWORD *)(v4 + 708) )
        v20 = *(_DWORD *)(v4 + 708);
      v21 = *(_DWORD *)(v4 + 712);
      if ( v20 > v21 )
        v21 = v20;
      if ( *(_DWORD *)(v5 + 320) && v21 > 0x10000 )
      {
        *(_BYTE *)(v5 + 326) = 1;
        *(_DWORD *)(v5 + 328) = v21 + 0x2000;
      }
    }
  }
LABEL_47:
  *(_DWORD *)(v6 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920), v7);
  v23 = *((_QWORD *)P + 2);
  if ( v2
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qZLd(WPP_GLOBAL_Control->AttachedDevice, v4 + 80, v22, v4, v4 + 80, P[2], P[3]);
  }
  if ( v23 )
  {
    *(_QWORD *)(v23 + 8) = *((_QWORD *)P + 1);
    (*(void (__fastcall **)(__int64))v23)(v23);
  }
  ExFreePoolWithTag(P, 0x6D536243u);
}

```

## disassembly

```asm
0x14002c420  push    rbx
0x14002c422  push    rbp
0x14002c423  push    rsi
0x14002c424  push    rdi
0x14002c425  push    r12
0x14002c427  push    r13
0x14002c429  push    r14
0x14002c42b  push    r15
0x14002c42d  sub     rsp, 48h
0x14002c431  mov     rax, [rcx+18h]
0x14002c435  mov     r14, rcx
0x14002c438  mov     r12d, [rcx+8]
0x14002c43c  and     rax, 0FFFFFFFFFFFFFFFEh
0x14002c440  mov     rbp, [rax+1B0h]
0x14002c447  mov     rbx, [rax+188h]
0x14002c44e  mov     r15, [rbp+18h]
0x14002c452  lea     rcx, [r15+780h]; SpinLock
0x14002c459  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002c460  nop     dword ptr [rax+rax+00h]
0x14002c465  movzx   edi, al
0x14002c468  mov     [rsp+88h+arg_0], al
0x14002c46f  call    cs:__imp_PsGetCurrentThreadId
0x14002c476  nop     dword ptr [rax+rax+00h]
0x14002c47b  mov     [r15+930h], eax
0x14002c482  lea     rsi, WPP_GLOBAL_Control
0x14002c489  test    r12d, r12d
0x14002c48c  js      loc_14002C73B
0x14002c492  test    rbx, rbx
0x14002c495  jz      loc_14002C72D
0x14002c49b  cmp     dword ptr [rbx+0Ch], 0
0x14002c49f  jnz     loc_14002C72D
0x14002c4a5  cmp     dword ptr [rbx+140h], 2
0x14002c4ac  jnz     short loc_14002C51D
0x14002c4ae  mov     rax, [rbx+20h]
0x14002c4b2  cmp     dword ptr [rax+38h], 1
0x14002c4b6  jnz     short loc_14002C502
0x14002c4b8  cmp     byte ptr [rax+45h], 0
0x14002c4bc  jz      short loc_14002C502
0x14002c4be  cmp     byte ptr cs:word_14007D202, 0
0x14002c4c5  jz      short loc_14002C502
0x14002c4c7  cmp     dword ptr [rbp+310h], 0
0x14002c4ce  jnz     short loc_14002C502
0x14002c4d0  xor     edx, edx
0x14002c4d2  lea     rcx, MRxSmbRdmaRundownSrwLock
0x14002c4d9  call    cs:__imp_ExAcquirePushLockSharedEx
0x14002c4e0  nop     dword ptr [rax+rax+00h]
0x14002c4e5  xor     edx, edx
0x14002c4e7  lea     rcx, MRxSmbRdmaRundownSrwLock
0x14002c4ee  cmp     cs:MRxSmbRdmaRundownState, edx
0x14002c4f4  jz      short loc_14002C511
0x14002c4f6  call    cs:__imp_ExReleasePushLockSharedEx
0x14002c4fd  nop     dword ptr [rax+rax+00h]
0x14002c502  mov     rax, 19BC000020Ch
0x14002c50c  jmp     loc_14002C737
0x14002c511  call    cs:__imp_ExReleasePushLockSharedEx
0x14002c518  nop     dword ptr [rax+rax+00h]
0x14002c51d  lea     rcx, [rbp+268h]
0x14002c524  mov     rdx, [rcx+8]
0x14002c528  cmp     [rdx], rcx
0x14002c52b  jz      short loc_14002C534
0x14002c52d  mov     ecx, 3
0x14002c532  int     29h; Win8: RtlFailFast(ecx)
0x14002c534  lea     rax, [rbx+218h]
0x14002c53b  mov     [rax], rcx
0x14002c53e  mov     [rax+8], rdx
0x14002c542  mov     [rdx], rax
0x14002c545  mov     [rcx+8], rax
0x14002c549  mov     [rbx+1F8h], rbp
0x14002c550  lock inc dword ptr [rbp+278h]
0x14002c557  mov     r9, [rbp+240h]
0x14002c55e  test    r9, r9
0x14002c561  jz      loc_14002C6E1
0x14002c567  mov     r8d, [r9+8]
0x14002c56b  test    r8d, r8d
0x14002c56e  jz      loc_14002C6E1
0x14002c574  xor     esi, esi
0x14002c576  mov     r11d, 1
0x14002c57c  cmp     dword ptr [rbx+140h], 2
0x14002c583  setz    r10b
0x14002c587  nop     word ptr [rax+rax+00000000h]
0x14002c590  mov     eax, esi
0x14002c592  imul    rdi, rax, 138h
0x14002c599  add     rdi, r9
0x14002c59c  movzx   eax, byte ptr [rdi+24h]
0x14002c5a0  shr     al, 4
0x14002c5a3  and     al, r11b
0x14002c5a6  cmp     al, r10b
0x14002c5a9  jnz     loc_14002C636
0x14002c5af  movzx   edx, word ptr [rdi+38h]
0x14002c5b3  cmp     dx, [rbx+190h]
0x14002c5ba  jnz     short loc_14002C636
0x14002c5bc  movzx   eax, word ptr [rbx+1ACh]
0x14002c5c3  cmp     [rdi+0C8h], ax
0x14002c5ca  jnz     short loc_14002C636
0x14002c5cc  xor     cl, cl
0x14002c5ce  cmp     dx, 17h
0x14002c5d2  jnz     short loc_14002C614
0x14002c5d4  mov     rax, [rbx+1A0h]
0x14002c5db  cmp     [rdi+48h], rax
0x14002c5df  jnz     short loc_14002C632
0x14002c5e1  mov     rax, [rbx+198h]
0x14002c5e8  cmp     [rdi+40h], rax
0x14002c5ec  jnz     short loc_14002C632
0x14002c5ee  mov     rax, [rbx+1BCh]
0x14002c5f5  cmp     [rdi+0D8h], rax
0x14002c5fc  jnz     short loc_14002C632
0x14002c5fe  mov     rax, [rbx+1B4h]
0x14002c605  cmp     [rdi+0D0h], rax
0x14002c60c  jnz     short loc_14002C632
0x14002c60e  movzx   ecx, r11b
0x14002c612  jmp     short loc_14002C632
0x14002c614  mov     eax, [rbx+194h]
0x14002c61a  cmp     [rdi+3Ch], eax
0x14002c61d  jnz     short loc_14002C632
0x14002c61f  mov     eax, [rbx+1B0h]
0x14002c625  cmp     [rdi+0CCh], eax
0x14002c62b  movzx   ecx, cl
0x14002c62e  cmovz   ecx, r11d
0x14002c632  test    cl, cl
0x14002c634  jnz     short loc_14002C646
0x14002c636  inc     esi
0x14002c638  cmp     esi, r8d
0x14002c63b  jb      loc_14002C590
0x14002c641  jmp     loc_14002C6D2
0x14002c646  inc     dword ptr [rdi+18h]
0x14002c649  mov     r8d, [rdi+14h]
0x14002c64d  xor     r9d, r9d
0x14002c650  mov     edx, [rdi+18h]
0x14002c653  mov     [rdi+1Ch], r9d
0x14002c657  lea     eax, [r8+r8]
0x14002c65b  mov     [rdi+20h], eax
0x14002c65e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c665  lea     rax, WPP_GLOBAL_Control
0x14002c66c  cmp     rcx, rax
0x14002c66f  jz      short loc_14002C6A0
0x14002c671  test    dword ptr [rcx+2Ch], 100h
0x14002c678  jz      short loc_14002C6A0
0x14002c67a  cmp     byte ptr [rcx+29h], 2
0x14002c67e  jb      short loc_14002C6A0
0x14002c680  mov     rcx, [rcx+18h]
0x14002c684  mov     [rsp+88h+var_58], r9d
0x14002c689  mov     r9d, esi
0x14002c68c  mov     [rsp+88h+var_60], edx
0x14002c690  mov     dword ptr [rsp+88h+var_68], r8d
0x14002c695  call    WPP_SF_dddd
0x14002c69a  mov     r11d, 1
0x14002c6a0  mov     eax, [rdi+1Ch]
0x14002c6a3  lea     r8, aUpdateIndexDTa; "Update:Index %d TargetCount %d CurrentC"...
0x14002c6aa  mov     rcx, [rbp+10h]
0x14002c6ae  mov     r9d, esi
0x14002c6b1  mov     [rsp+88h+var_58], eax
0x14002c6b5  mov     edx, r11d
0x14002c6b8  mov     eax, [rdi+18h]
0x14002c6bb  mov     [rsp+88h+var_60], eax
0x14002c6bf  mov     eax, [rdi+14h]
0x14002c6c2  mov     dword ptr [rsp+88h+var_68], eax
0x14002c6c6  call    cs:__imp_RxDiagnosticTrace
0x14002c6cd  nop     dword ptr [rax+rax+00h]
0x14002c6d2  movzx   edi, [rsp+88h+arg_0]
0x14002c6da  lea     rsi, WPP_GLOBAL_Control
0x14002c6e1  test    dword ptr [rbp+2CCh], 800h
0x14002c6eb  jz      short loc_14002C73B
0x14002c6ed  mov     eax, [rbp+2C4h]
0x14002c6f3  mov     ecx, [rbp+2C0h]
0x14002c6f9  cmp     ecx, eax
0x14002c6fb  cmovbe  ecx, eax
0x14002c6fe  mov     eax, [rbp+2C8h]
0x14002c704  cmp     ecx, eax
0x14002c706  cmova   eax, ecx
0x14002c709  cmp     dword ptr [rbx+140h], 0
0x14002c710  jz      short loc_14002C73B
0x14002c712  cmp     eax, 10000h
0x14002c717  jbe     short loc_14002C73B
0x14002c719  add     eax, 2000h
0x14002c71e  mov     byte ptr [rbx+146h], 1
0x14002c725  mov     [rbx+148h], eax
0x14002c72b  jmp     short loc_14002C73B
0x14002c72d  mov     rax, 195C000020Ch
0x14002c737  mov     [r14+8], rax
0x14002c73b  movzx   edx, dil; OldIrql
0x14002c73f  mov     dword ptr [r15+930h], 0FFFFFFFFh
0x14002c74a  lea     rcx, [r15+780h]; SpinLock
0x14002c751  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002c758  nop     dword ptr [rax+rax+00h]
0x14002c75d  mov     rbx, [r14+10h]
0x14002c761  test    r12d, r12d
0x14002c764  jz      short loc_14002C7A4
0x14002c766  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c76d  cmp     rcx, rsi
0x14002c770  jz      short loc_14002C7A4
0x14002c772  mov     eax, [rcx+2Ch]
0x14002c775  test    al, 1
0x14002c777  jz      short loc_14002C7A4
0x14002c779  cmp     byte ptr [rcx+29h], 1
0x14002c77d  jb      short loc_14002C7A4
0x14002c77f  mov     eax, [r14+0Ch]
0x14002c783  lea     rdx, [rbp+50h]
0x14002c787  mov     rcx, [rcx+18h]
0x14002c78b  mov     r9, rbp
0x14002c78e  mov     [rsp+88h+var_58], eax
0x14002c792  mov     eax, [r14+8]
0x14002c796  mov     [rsp+88h+var_60], eax
0x14002c79a  mov     [rsp+88h+var_68], rdx
0x14002c79f  call    WPP_SF_qZLd
0x14002c7a4  test    rbx, rbx
0x14002c7a7  jz      short loc_14002C7BC
0x14002c7a9  mov     rax, [r14+8]
0x14002c7ad  mov     rcx, rbx
0x14002c7b0  mov     [rbx+8], rax
0x14002c7b4  mov     rax, [rbx]
0x14002c7b7  call    _guard_dispatch_icall
0x14002c7bc  mov     edx, 6D536243h; Tag
0x14002c7c1  mov     rcx, r14; P
0x14002c7c4  call    cs:__imp_ExFreePoolWithTag
0x14002c7cb  nop     dword ptr [rax+rax+00h]
0x14002c7d0  add     rsp, 48h
0x14002c7d4  pop     r15
0x14002c7d6  pop     r14
0x14002c7d8  pop     r13
0x14002c7da  pop     r12
0x14002c7dc  pop     rdi
0x14002c7dd  pop     rsi
0x14002c7de  pop     rbp
0x14002c7df  pop     rbx
0x14002c7e0  retn
```
