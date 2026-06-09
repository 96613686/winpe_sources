# MRxDAVOuterStart

- ea: `0x14000fde4`
- end: `0x140010162`
- name: `MRxDAVOuterStart`
- size: `894`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000f120`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400016d4`
- `0x1400017e4`
- `0x14000fde4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fe17`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fe53`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fe91`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000feff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000ff6e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010040`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400100ae`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400100da`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001012b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fe17`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fe53`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fe91`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000feff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000ff6e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010040`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400100ae`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400100da`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001012b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000fed1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000fed1`
- `ntoskrnl!PsCreateSystemThread` at `0x14001007f`
- `ntoskrnl!PsCreateSystemThread` at `0x14001007f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140010109`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140028e32`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140010109`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140028e32`
- `rdbss!RxStartMinirdr` at `0x14000ff37`
- `rdbss!RxStartMinirdr` at `0x14000ff37`

## pseudocode

```c
__int64 __fastcall MRxDAVOuterStart(PRX_CONTEXT RxContext)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  PNON_PAGED_FCB NonPagedFcb; // rbx
  int *v9; // r12
  __int64 v10; // rbx
  HANDLE v11; // rax
  unsigned int started; // edi
  __int64 v13; // rbx
  HANDLE v14; // rax
  __int64 v15; // r8
  wchar_t *v16; // r9
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rbx
  HANDLE v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rbx
  HANDLE v28; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v2, 25, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, CurrentThreadId);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v5 = PsGetCurrentThreadId();
    WPP_SF_qq(v4, 26, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v5, RxContext);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v7 = PsGetCurrentThreadId();
    WPP_SF_q(v6, 27, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v7);
  }
  NonPagedFcb = RxContext->NonPagedFcb;
  v9 = (int *)*((_QWORD *)&RxContext->9 + 19);
  NonPagedFcb[3].PagingIoResource.CreatorBackTraceIndex = (ULONG_PTR)RxContext->pFcb;
  ExAcquireFastMutexUnsafe(&MRxDAVSerializationMutex);
  if ( LOBYTE(NonPagedFcb[3].PagingIoResource.Reserved2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_q(v10, 28, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v11);
    }
    started = -1073741572;
    goto LABEL_37;
  }
  started = RxStartMinirdr(RxContext, (PBOOLEAN)&RxContext->RealDevice + 3);
  if ( started )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
      goto LABEL_37;
    v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v25 = PsGetCurrentThreadId();
    v26 = 32;
LABEL_36:
    WPP_SF_qD(v24, v26, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v25, started);
    goto LABEL_37;
  }
  LOBYTE(NonPagedFcb[3].PagingIoResource.Reserved2) = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v14 = PsGetCurrentThreadId();
    WPP_SF_q(v13, 29, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v14);
  }
  v15 = 2147483646;
  v16 = (wchar_t *)(v9 + 1);
  v17 = 260;
  v18 = &DavWinInetCachePath;
  v19 = 0;
  while ( v17 )
  {
    if ( !v15 || !*v16 )
      goto LABEL_26;
    *v18++ = *v16++;
    --v17;
    --v15;
    ++v19;
  }
  --v18;
LABEL_26:
  *v18 = 0;
  DavSvcHostProcessId = *v9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = PsGetCurrentThreadId();
    WPP_SF_qSD(v20, v22, v23, v21);
  }
  started = PsCreateSystemThread(&TimerThreadHandle, 0x1FFFFFu, 0, 0, 0, MRxDAVContextTimerThread, 0);
  if ( started
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v25 = PsGetCurrentThreadId();
    v26 = 31;
    goto LABEL_36;
  }
LABEL_37:
  ExReleaseFastMutexUnsafe(&MRxDAVSerializationMutex);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v28 = PsGetCurrentThreadId();
    WPP_SF_qD(v27, 33, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v28, started);
  }
  return started;
}

```

## disassembly

```asm
0x14000fde4  push    rbx
0x14000fde6  push    rdi
0x14000fde7  push    r12
0x14000fde9  push    r13
0x14000fdeb  push    r14
0x14000fded  sub     rsp, 70h
0x14000fdf1  mov     rdi, rcx
0x14000fdf4  lea     r13, WPP_GLOBAL_Control
0x14000fdfb  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fe02  mov     r14d, 4000h
0x14000fe08  cmp     rbx, r13
0x14000fe0b  jz      short loc_14000FE3A
0x14000fe0d  test    [rbx+2Ch], r14d
0x14000fe11  jz      short loc_14000FE3A
0x14000fe13  mov     rbx, [rbx+18h]
0x14000fe17  call    cs:__imp_PsGetCurrentThreadId
0x14000fe1e  nop     dword ptr [rax+rax+00h]
0x14000fe23  mov     r9, rax
0x14000fe26  mov     edx, 19h
0x14000fe2b  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000fe32  mov     rcx, rbx
0x14000fe35  call    WPP_SF_q
0x14000fe3a  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fe41  cmp     rbx, r13
0x14000fe44  jz      short loc_14000FE7B
0x14000fe46  test    dword ptr [rbx+2Ch], 2000h
0x14000fe4d  jz      short loc_14000FE7B
0x14000fe4f  mov     rbx, [rbx+18h]
0x14000fe53  call    cs:__imp_PsGetCurrentThreadId
0x14000fe5a  nop     dword ptr [rax+rax+00h]
0x14000fe5f  mov     r9, rax
0x14000fe62  mov     edx, 1Ah
0x14000fe67  mov     [rsp+98h+ClientId], rdi
0x14000fe6c  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000fe73  mov     rcx, rbx
0x14000fe76  call    WPP_SF_qq
0x14000fe7b  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fe82  cmp     rbx, r13
0x14000fe85  jz      short loc_14000FEB4
0x14000fe87  test    [rbx+2Ch], r14d
0x14000fe8b  jz      short loc_14000FEB4
0x14000fe8d  mov     rbx, [rbx+18h]
0x14000fe91  call    cs:__imp_PsGetCurrentThreadId
0x14000fe98  nop     dword ptr [rax+rax+00h]
0x14000fe9d  mov     r9, rax
0x14000fea0  mov     edx, 1Bh
0x14000fea5  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000feac  mov     rcx, rbx
0x14000feaf  call    WPP_SF_q
0x14000feb4  mov     rbx, [rdi+50h]
0x14000feb8  mov     r12, [rdi+228h]
0x14000febf  mov     rax, [rdi+38h]
0x14000fec3  mov     [rbx+668h], rax
0x14000feca  lea     rcx, MRxDAVSerializationMutex; FastMutex
0x14000fed1  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000fed8  nop     dword ptr [rax+rax+00h]
0x14000fedd  nop
0x14000fede  cmp     byte ptr [rbx+660h], 0
0x14000fee5  jz      short loc_14000FF30
0x14000fee7  mov     rbx, cs:WPP_GLOBAL_Control
0x14000feee  cmp     rbx, r13
0x14000fef1  jz      short loc_14000FF22
0x14000fef3  mov     eax, [rbx+2Ch]
0x14000fef6  test    r14d, eax
0x14000fef9  jz      short loc_14000FF22
0x14000fefb  mov     rbx, [rbx+18h]
0x14000feff  call    cs:__imp_PsGetCurrentThreadId
0x14000ff06  nop     dword ptr [rax+rax+00h]
0x14000ff0b  mov     r9, rax
0x14000ff0e  mov     edx, 1Ch
0x14000ff13  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000ff1a  mov     rcx, rbx
0x14000ff1d  call    WPP_SF_q
0x14000ff22  mov     edi, 0C00000FCh
0x14000ff27  mov     [rsp+98h+var_58], edi
0x14000ff2b  jmp     loc_140010102
0x14000ff30  lea     rdx, [rdi+23h]; PostToFsp
0x14000ff34  mov     rcx, rdi; RxContext
0x14000ff37  call    cs:__imp_RxStartMinirdr
0x14000ff3e  nop     dword ptr [rax+rax+00h]
0x14000ff43  mov     edi, eax
0x14000ff45  mov     [rsp+98h+var_58], eax
0x14000ff49  test    eax, eax
0x14000ff4b  jnz     loc_1400100C1
0x14000ff51  mov     byte ptr [rbx+660h], 1
0x14000ff58  mov     rbx, cs:WPP_GLOBAL_Control
0x14000ff5f  cmp     rbx, r13
0x14000ff62  jz      short loc_14000FF8F
0x14000ff64  test    [rbx+2Ch], r14d
0x14000ff68  jz      short loc_14000FF8F
0x14000ff6a  mov     rbx, [rbx+18h]
0x14000ff6e  call    cs:__imp_PsGetCurrentThreadId
0x14000ff75  nop     dword ptr [rax+rax+00h]
0x14000ff7a  mov     r9, rax
0x14000ff7d  lea     edx, [rdi+1Dh]
0x14000ff80  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000ff87  mov     rcx, rbx
0x14000ff8a  call    WPP_SF_q
0x14000ff8f  mov     r8d, 7FFFFFFEh
0x14000ff95  mov     [rsp+98h+var_30], r8
0x14000ff9a  lea     r9, [r12+4]
0x14000ff9f  mov     [rsp+98h+var_40], r9
0x14000ffa4  mov     edx, 104h
0x14000ffa9  mov     [rsp+98h+var_38], rdx
0x14000ffae  lea     rcx, DavWinInetCachePath
0x14000ffb5  mov     [rsp+98h+var_50], rcx
0x14000ffba  xor     edi, edi
0x14000ffbc  mov     eax, edi
0x14000ffbe  mov     [rsp+98h+var_48], rax
0x14000ffc3  test    rdx, rdx
0x14000ffc6  jz      short loc_14001000C
0x14000ffc8  test    r8, r8
0x14000ffcb  jz      short loc_140010007
0x14000ffcd  movzx   r10d, word ptr [r9]
0x14000ffd1  test    r10w, r10w
0x14000ffd5  jz      short loc_140010007
0x14000ffd7  mov     [rcx], r10w
0x14000ffdb  add     rcx, 2
0x14000ffdf  mov     [rsp+98h+var_50], rcx
0x14000ffe4  add     r9, 2
0x14000ffe8  mov     [rsp+98h+var_40], r9
0x14000ffed  dec     rdx
0x14000fff0  mov     [rsp+98h+var_38], rdx
0x14000fff5  dec     r8
0x14000fff8  mov     [rsp+98h+var_30], r8
0x14000fffd  inc     rax
0x140010000  mov     [rsp+98h+var_48], rax
0x140010005  jmp     short loc_14000FFC3
0x140010007  test    rdx, rdx
0x14001000a  jnz     short loc_14001001D
0x14001000c  sub     rcx, 2
0x140010010  mov     [rsp+98h+var_50], rcx
0x140010015  dec     rax
0x140010018  mov     [rsp+98h+var_48], rax
0x14001001d  mov     [rcx], di
0x140010020  mov     eax, [r12]
0x140010024  mov     cs:DavSvcHostProcessId, eax
0x14001002a  mov     rbx, cs:WPP_GLOBAL_Control
0x140010031  cmp     rbx, r13
0x140010034  jz      short loc_140010057
0x140010036  test    [rbx+2Ch], r14d
0x14001003a  jz      short loc_140010057
0x14001003c  mov     rbx, [rbx+18h]
0x140010040  call    cs:__imp_PsGetCurrentThreadId
0x140010047  nop     dword ptr [rax+rax+00h]
0x14001004c  mov     r9, rax
0x14001004f  mov     rcx, rbx
0x140010052  call    WPP_SF_qSD
0x140010057  mov     [rsp+98h+StartContext], rdi; StartContext
0x14001005c  lea     rax, MRxDAVContextTimerThread
0x140010063  mov     [rsp+98h+StartRoutine], rax; StartRoutine
0x140010068  mov     [rsp+98h+ClientId], rdi; ClientId
0x14001006d  xor     r9d, r9d; ProcessHandle
0x140010070  xor     r8d, r8d; ObjectAttributes
0x140010073  mov     edx, 1FFFFFh; DesiredAccess
0x140010078  lea     rcx, TimerThreadHandle; ThreadHandle
0x14001007f  call    cs:__imp_PsCreateSystemThread
0x140010086  nop     dword ptr [rax+rax+00h]
0x14001008b  mov     edi, eax
0x14001008d  mov     [rsp+98h+var_58], eax
0x140010091  test    eax, eax
0x140010093  jz      short loc_140010102
0x140010095  mov     rbx, cs:WPP_GLOBAL_Control
0x14001009c  cmp     rbx, r13
0x14001009f  jz      short loc_140010102
0x1400100a1  mov     eax, [rbx+2Ch]
0x1400100a4  bt      eax, 0Dh
0x1400100a8  jnb     short loc_140010102
0x1400100aa  mov     rbx, [rbx+18h]
0x1400100ae  call    cs:__imp_PsGetCurrentThreadId
0x1400100b5  nop     dword ptr [rax+rax+00h]
0x1400100ba  mov     edx, 1Fh
0x1400100bf  jmp     short loc_1400100EB
0x1400100c1  mov     rbx, cs:WPP_GLOBAL_Control
0x1400100c8  cmp     rbx, r13
0x1400100cb  jz      short loc_140010102
0x1400100cd  mov     eax, [rbx+2Ch]
0x1400100d0  bt      eax, 0Dh
0x1400100d4  jnb     short loc_140010102
0x1400100d6  mov     rbx, [rbx+18h]
0x1400100da  call    cs:__imp_PsGetCurrentThreadId
0x1400100e1  nop     dword ptr [rax+rax+00h]
0x1400100e6  mov     edx, 20h ; ' '
0x1400100eb  mov     dword ptr [rsp+98h+ClientId], edi
0x1400100ef  mov     r9, rax
0x1400100f2  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x1400100f9  mov     rcx, rbx
0x1400100fc  call    WPP_SF_qD
0x140010101  nop
0x140010102  lea     rcx, MRxDAVSerializationMutex; FastMutex
0x140010109  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140010110  nop     dword ptr [rax+rax+00h]
0x140010115  mov     rbx, cs:WPP_GLOBAL_Control
0x14001011c  cmp     rbx, r13
0x14001011f  jz      short loc_140010152
0x140010121  test    [rbx+2Ch], r14d
0x140010125  jz      short loc_140010152
0x140010127  mov     rbx, [rbx+18h]
0x14001012b  call    cs:__imp_PsGetCurrentThreadId
0x140010132  nop     dword ptr [rax+rax+00h]
0x140010137  mov     r9, rax
0x14001013a  mov     edx, 21h ; '!'
0x14001013f  mov     dword ptr [rsp+98h+ClientId], edi
0x140010143  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14001014a  mov     rcx, rbx
0x14001014d  call    WPP_SF_qD
0x140010152  mov     eax, edi
0x140010154  add     rsp, 70h
0x140010158  pop     r14
0x14001015a  pop     r13
0x14001015c  pop     r12
0x14001015e  pop     rdi
0x14001015f  pop     rbx
0x140010160  retn
0x140028e22  push    rbp
0x140028e24  sub     rsp, 40h
0x140028e28  mov     rbp, rdx
0x140028e2b  lea     rcx, MRxDAVSerializationMutex; FastMutex
0x140028e32  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140028e39  nop     dword ptr [rax+rax+00h]
0x140028e3e  nop
0x140028e3f  add     rsp, 40h
0x140028e43  pop     rbp
0x140028e44  retn
```
