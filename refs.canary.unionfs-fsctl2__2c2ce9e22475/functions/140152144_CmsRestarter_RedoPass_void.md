# CmsRestarter::RedoPass(void)

- ea: `0x140152144`
- end: `0x140152544`
- name: `?RedoPass@CmsRestarter@@AEAAJXZ`
- size: `1024`
- prototype: `__int64 __fastcall(CmsRestarter *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140153df8`

## callees

- `0x1400710d0`
- `0x14009c9d0`
- `0x1400b4264`
- `0x1400c831c`
- `0x1400f3a34`
- `0x14014d128`
- `0x140152144`
- `0x140155654`
- `0x140172e80`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14015217b`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401524fd`
- `ntoskrnl!IoGetActivityIdThread` at `0x14015217b`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401524fd`
- `ntoskrnl!KeSetEvent` at `0x1401522cb`
- `ntoskrnl!KeSetEvent` at `0x14015235f`
- `ntoskrnl!KeSetEvent` at `0x1401522cb`
- `ntoskrnl!KeSetEvent` at `0x14015235f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401523e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401523e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401523fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401523fa`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401522a1`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401522a1`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1401521c4`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1401521c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401523d8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401523d8`
- `ntoskrnl!KeInitializeEvent` at `0x1401522b6`
- `ntoskrnl!KeInitializeEvent` at `0x1401522e5`
- `ntoskrnl!KeInitializeEvent` at `0x1401522b6`
- `ntoskrnl!KeInitializeEvent` at `0x1401522e5`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015239d`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015239d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140152385`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140152385`

## pseudocode

```c
__int64 __fastcall CmsRestarter::RedoPass(CmsRestarter *this, const struct std::nothrow_t *a2)
{
  int v2; // ebp
  CmsRestarter *v3; // r14
  int v4; // ebx
  __int64 v5; // rdi
  int ActivityIdThread; // eax
  ULONG ActiveProcessorCount; // eax
  unsigned __int64 v8; // rbp
  unsigned __int128 v9; // rax
  __int64 v10; // rbx
  bool v11; // cf
  unsigned __int64 v12; // rbx
  unsigned __int64 *v13; // rax
  unsigned __int64 *v14; // rdi
  _QWORD *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // r15d
  __int64 v19; // rbx
  __int64 v20; // rdi
  void *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rdi
  KIRQL v24; // al
  unsigned int *v25; // rax
  int v26; // eax
  bool v27; // zf
  __int64 v28; // rbx
  __int64 v29; // rdi
  int v30; // eax
  __int64 v32; // [rsp+60h] [rbp+8h] BYREF
  __int64 v33; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  v32 = 0;
  v3 = this;
  if ( dword_1402403A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    v4 = *((_DWORD *)this + 8);
    v5 = *((_QWORD *)this + 5);
    ActivityIdThread = IoGetActivityIdThread(this, a2);
    McTemplateK0iix_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)RedoPassStart,
      ActivityIdThread,
      v5,
      0,
      v4);
  }
  if ( *((_DWORD *)v3 + 50) )
  {
    *((_DWORD *)v3 + 4) = 4;
    ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
    v8 = 2 * ActiveProcessorCount;
    v9 = 2 * ActiveProcessorCount * (unsigned __int128)0x160uLL;
    v10 = v9;
    if ( !is_mul_ok(v8, 0x160u) )
      v10 = -1;
    v11 = __CFADD__(v10, 8);
    v12 = v10 + 8;
    if ( v11 )
      v12 = -1;
    v13 = (unsigned __int64 *)operator new(v12, *((const struct std::nothrow_t **)&v9 + 1));
    v14 = v13;
    if ( v13 )
    {
      memset(v13, 0, v12);
      v15 = v14 + 1;
      *v14 = v8;
      `vector constructor iterator'(
        v14 + 1,
        0x160u,
        (unsigned int)v8,
        (void *(*)(void *))CmsLogRedoQueue::CmsLogRedoQueue);
    }
    else
    {
      v15 = 0;
    }
    v16 = *((_QWORD *)v3 + 32);
    v33 = 0;
    *((_QWORD *)v3 + 32) = v15;
    if ( v16 )
      utl::default_delete<CmsLogRedoQueue [0]>::operator()<CmsLogRedoQueue,0>();
    utl::unique_ptr<CmsLogRedoQueue [0],utl::default_delete<CmsLogRedoQueue [0]>>::~unique_ptr<CmsLogRedoQueue [0],utl::default_delete<CmsLogRedoQueue [0]>>(&v33);
    v17 = *((_QWORD *)v3 + 32);
    if ( !v17 )
      goto LABEL_38;
    *((_QWORD *)v3 + 29) = v17;
    v18 = 0;
    *((_QWORD *)v3 + 30) = v8;
    v19 = *((_QWORD *)v3 + 29);
    v20 = v19 + 352 * v8;
    while ( v19 != v20 )
    {
      *(_DWORD *)(v19 + 344) = v18++;
      KeInitializeSpinLock((PKSPIN_LOCK)(v19 + 32));
      KeInitializeEvent((PRKEVENT)(v19 + 40), NotificationEvent, 0);
      KeSetEvent((PRKEVENT)(v19 + 40), 0, 0);
      KeInitializeEvent((PRKEVENT)(v19 + 136), SynchronizationEvent, 0);
      *(_QWORD *)(v19 + 336) = v3;
      v19 += 352;
    }
    v21 = operator new(v8, a2);
    *((_QWORD *)v3 + 43) = v21;
    if ( v21 )
    {
      memset(v21, 0, v8);
      v2 = MlLogScanLog(
             *(_QWORD *)(*(_QWORD *)v3 + 72LL),
             *((_QWORD *)v3 + 1),
             *((_QWORD *)v3 + 5),
             (unsigned int)&CmsRestarter::RedoOneMergedRecordBlock,
             (__int64)v3,
             (__int64)&v32);
      KeSetEvent((PRKEVENT)((char *)v3 + 296), 0, 0);
      if ( v2 < 0 && *((int *)v3 + 56) >= 0 )
      {
        ExAcquirePushLockExclusiveEx((char *)v3 + 248, 0);
        *((_DWORD *)v3 + 56) = v2;
        ExReleasePushLockEx((char *)v3 + 248, 0);
      }
      v22 = *((_QWORD *)v3 + 29);
      v23 = v22 + 352LL * *((_QWORD *)v3 + 30);
      while ( v22 != v23 )
      {
        KeWaitForSingleObject((PVOID)(v22 + 40), Executive, 0, 0, 0);
        v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v22 + 32));
        KeReleaseSpinLock((PKSPIN_LOCK)(v22 + 32), v24);
        v22 += 352;
      }
      if ( v2 >= 0 )
      {
        v2 = *((_DWORD *)v3 + 56);
        *((_QWORD *)v3 + 13) = v32;
        if ( v2 >= 0 )
        {
          v25 = (unsigned int *)*((_QWORD *)v3 + 29);
          this = (CmsRestarter *)&v25[88 * *((_QWORD *)v3 + 30)];
          while ( v25 != (unsigned int *)this )
          {
            a2 = (const struct std::nothrow_t *)v25[2];
            *((_DWORD *)v3 + 50) -= (_DWORD)a2;
            v25 += 88;
          }
          v26 = *((_DWORD *)v3 + 51);
          v27 = *((_DWORD *)v3 + 50) == v26;
          *((_DWORD *)v3 + 50) -= v26;
          if ( v27 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_38fa40eb983e345104985e233278c3ef_Traceguids,
                *((_QWORD *)v3 + 26));
            }
            v2 = CmsObjectTable::SetMinimumNewObjectId(
                   *(CmsObjectTable **)(*((_QWORD *)v3 + 1) + 3408LL),
                   (CmsRestarter *)((char *)v3 + 208));
            if ( v2 == -1073741811 )
              v2 = 0;
          }
          else
          {
            v2 = -1073741774;
          }
        }
      }
    }
    else
    {
LABEL_38:
      v2 = -1073741670;
    }
  }
  if ( dword_1402403A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    v28 = *((_QWORD *)v3 + 12);
    v29 = *((_QWORD *)v3 + 5);
    v30 = IoGetActivityIdThread(this, a2);
    McTemplateK0iix_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)RedoPassEnd,
      v30,
      v29,
      v28,
      0);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140152144  mov     [rsp+arg_10], rbx
0x140152149  push    rbp
0x14015214a  push    rsi
0x14015214b  push    rdi
0x14015214c  push    r14
0x14015214e  push    r15
0x140152150  sub     rsp, 30h
0x140152154  xor     ebp, ebp
0x140152156  mov     [rsp+58h+arg_0], 0
0x14015215f  cmp     cs:dword_1402403A4, 1
0x140152166  mov     r14, rcx
0x140152169  jnz     short loc_1401521AA
0x14015216b  test    cs:Microsoft_Windows_MinstoreEnableBits, 1
0x140152172  jz      short loc_1401521AA
0x140152174  mov     ebx, [rcx+20h]
0x140152177  mov     rdi, [rcx+28h]
0x14015217b  call    cs:__imp_IoGetActivityIdThread
0x140152182  nop     dword ptr [rax+rax+00h]
0x140152187  mov     [rsp+58h+var_30], rbx
0x14015218c  lea     rdx, RedoPassStart
0x140152193  mov     r8, rax
0x140152196  mov     [rsp+58h+Timeout], rbp
0x14015219b  mov     r9, rdi
0x14015219e  lea     rcx, MinstoreEventProvider_Context
0x1401521a5  call    McTemplateK0iix_EtwWriteTransfer
0x1401521aa  cmp     [r14+0C8h], ebp
0x1401521b1  jz      loc_1401524E3
0x1401521b7  mov     ecx, 0FFFFh; GroupNumber
0x1401521bc  mov     dword ptr [r14+10h], 4
0x1401521c4  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1401521cb  nop     dword ptr [rax+rax+00h]
0x1401521d0  mov     esi, 160h
0x1401521d5  lea     ebp, [rax+rax]
0x1401521d8  mov     eax, esi
0x1401521da  mul     rbp
0x1401521dd  mov     rbx, rax
0x1401521e0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1401521e7  cmovb   rbx, rax
0x1401521eb  add     rbx, 8
0x1401521ef  cmovb   rbx, rax
0x1401521f3  mov     rcx, rbx; unsigned __int64
0x1401521f6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1401521fb  mov     rdi, rax
0x1401521fe  test    rax, rax
0x140152201  jz      short loc_14015222D
0x140152203  mov     r8, rbx; Size
0x140152206  xor     edx, edx; Val
0x140152208  mov     rcx, rax; void *
0x14015220b  call    memset
0x140152210  lea     rbx, [rdi+8]
0x140152214  mov     [rdi], rbp
0x140152217  mov     rcx, rbx; void *
0x14015221a  lea     r9, ??0CmsLogRedoQueue@@QEAA@XZ; void *(*)(void *)
0x140152221  mov     r8d, ebp; unsigned __int64
0x140152224  mov     edx, esi; unsigned __int64
0x140152226  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14015222b  jmp     short loc_14015222F
0x14015222d  xor     ebx, ebx
0x14015222f  mov     rdx, [r14+100h]
0x140152236  mov     [rsp+58h+arg_8], 0
0x14015223f  mov     [r14+100h], rbx
0x140152246  test    rdx, rdx
0x140152249  jz      short loc_140152250
0x14015224b  call    ??$?RVCmsLogRedoQueue@@$0A@@?$default_delete@$$BY0A@VCmsLogRedoQueue@@@utl@@QEBAXPEAVCmsLogRedoQueue@@@Z; utl::default_delete<CmsLogRedoQueue [0]>::operator()<CmsLogRedoQueue,0>(CmsLogRedoQueue *)
0x140152250  lea     rcx, [rsp+58h+arg_8]
0x140152255  call    ??1?$unique_ptr@$$BY0A@VCmsLogRedoQueue@@U?$default_delete@$$BY0A@VCmsLogRedoQueue@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CmsLogRedoQueue [0],utl::default_delete<CmsLogRedoQueue [0]>>::~unique_ptr<CmsLogRedoQueue [0],utl::default_delete<CmsLogRedoQueue [0]>>(void)
0x14015225a  mov     rax, [r14+100h]
0x140152261  test    rax, rax
0x140152264  jz      loc_1401524DE
0x14015226a  mov     [r14+0E8h], rax
0x140152271  xor     r15d, r15d
0x140152274  imul    rdi, rbp, 160h
0x14015227b  mov     [r14+0F0h], rbp
0x140152282  mov     rbx, [r14+0E8h]
0x140152289  add     rdi, rbx
0x14015228c  cmp     rbx, rdi
0x14015228f  jz      short loc_140152302
0x140152291  mov     eax, r15d
0x140152294  lea     rcx, [rbx+20h]; SpinLock
0x140152298  mov     [rbx+158h], eax
0x14015229e  inc     r15d
0x1401522a1  call    cs:__imp_KeInitializeSpinLock
0x1401522a8  nop     dword ptr [rax+rax+00h]
0x1401522ad  xor     r8d, r8d; State
0x1401522b0  lea     rcx, [rbx+28h]; Event
0x1401522b4  xor     edx, edx; Type
0x1401522b6  call    cs:__imp_KeInitializeEvent
0x1401522bd  nop     dword ptr [rax+rax+00h]
0x1401522c2  xor     r8d, r8d; Wait
0x1401522c5  lea     rcx, [rbx+28h]; Event
0x1401522c9  xor     edx, edx; Increment
0x1401522cb  call    cs:__imp_KeSetEvent
0x1401522d2  nop     dword ptr [rax+rax+00h]
0x1401522d7  xor     r8d, r8d; State
0x1401522da  lea     rcx, [rbx+88h]; Event
0x1401522e1  lea     edx, [r8+1]; Type
0x1401522e5  call    cs:__imp_KeInitializeEvent
0x1401522ec  nop     dword ptr [rax+rax+00h]
0x1401522f1  mov     esi, 160h
0x1401522f6  mov     [rbx+150h], r14
0x1401522fd  add     rbx, rsi
0x140152300  jmp     short loc_14015228C
0x140152302  mov     rcx, rbp; unsigned __int64
0x140152305  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14015230a  mov     [r14+158h], rax
0x140152311  test    rax, rax
0x140152314  jz      loc_1401524DE
0x14015231a  mov     r8, rbp; Size
0x14015231d  xor     edx, edx; Val
0x14015231f  mov     rcx, rax; void *
0x140152322  call    memset
0x140152327  mov     rcx, [r14]
0x14015232a  lea     rax, [rsp+58h+arg_0]
0x14015232f  mov     r8, [r14+28h]
0x140152333  lea     r9, ?RedoOneMergedRecordBlock@CmsRestarter@@CAJT_ML_LSN@@PEAXK1@Z; CmsRestarter::RedoOneMergedRecordBlock(_ML_LSN,void *,ulong,void *)
0x14015233a  mov     rdx, [r14+8]
0x14015233e  mov     [rsp+58h+var_30], rax
0x140152343  mov     rcx, [rcx+48h]
0x140152347  mov     [rsp+58h+Timeout], r14
0x14015234c  call    MlLogScanLog
0x140152351  lea     rcx, [r14+128h]; Event
0x140152358  xor     r8d, r8d; Wait
0x14015235b  xor     edx, edx; Increment
0x14015235d  mov     ebp, eax
0x14015235f  call    cs:__imp_KeSetEvent
0x140152366  nop     dword ptr [rax+rax+00h]
0x14015236b  test    ebp, ebp
0x14015236d  jns     short loc_1401523A9
0x14015236f  cmp     dword ptr [r14+0E0h], 0
0x140152377  jl      short loc_1401523A9
0x140152379  lea     rbx, [r14+0F8h]
0x140152380  xor     edx, edx
0x140152382  mov     rcx, rbx
0x140152385  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14015238c  nop     dword ptr [rax+rax+00h]
0x140152391  xor     edx, edx
0x140152393  mov     [r14+0E0h], ebp
0x14015239a  mov     rcx, rbx
0x14015239d  call    cs:__imp_ExReleasePushLockEx
0x1401523a4  nop     dword ptr [rax+rax+00h]
0x1401523a9  imul    rdi, [r14+0F0h], 160h
0x1401523b4  mov     rbx, [r14+0E8h]
0x1401523bb  add     rdi, rbx
0x1401523be  cmp     rbx, rdi
0x1401523c1  jz      short loc_140152410
0x1401523c3  lea     rcx, [rbx+28h]; Object
0x1401523c7  mov     [rsp+58h+Timeout], 0; Timeout
0x1401523d0  xor     r9d, r9d; Alertable
0x1401523d3  xor     r8d, r8d; WaitMode
0x1401523d6  xor     edx, edx; WaitReason
0x1401523d8  call    cs:__imp_KeWaitForSingleObject
0x1401523df  nop     dword ptr [rax+rax+00h]
0x1401523e4  lea     rcx, [rbx+20h]; SpinLock
0x1401523e8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1401523ef  nop     dword ptr [rax+rax+00h]
0x1401523f4  mov     dl, al; NewIrql
0x1401523f6  lea     rcx, [rbx+20h]; SpinLock
0x1401523fa  call    cs:__imp_KeReleaseSpinLock
0x140152401  nop     dword ptr [rax+rax+00h]
0x140152406  mov     esi, 160h
0x14015240b  add     rbx, rsi
0x14015240e  jmp     short loc_1401523BE
0x140152410  test    ebp, ebp
0x140152412  js      loc_1401524E3
0x140152418  mov     rax, [rsp+58h+arg_0]
0x14015241d  mov     ebp, [r14+0E0h]
0x140152424  mov     [r14+68h], rax
0x140152428  test    ebp, ebp
0x14015242a  js      loc_1401524E3
0x140152430  imul    rcx, [r14+0F0h], 160h
0x14015243b  mov     rax, [r14+0E8h]
0x140152442  add     rcx, rax
0x140152445  cmp     rax, rcx
0x140152448  jz      short loc_140152459
0x14015244a  mov     edx, [rax+8]
0x14015244d  sub     [r14+0C8h], edx
0x140152454  add     rax, rsi
0x140152457  jmp     short loc_140152445
0x140152459  mov     eax, [r14+0CCh]
0x140152460  sub     [r14+0C8h], eax
0x140152467  jz      short loc_140152470
0x140152469  mov     ebp, 0C0000032h
0x14015246e  jmp     short loc_1401524E3
0x140152470  mov     rcx, cs:WPP_GLOBAL_Control
0x140152477  lea     rax, WPP_GLOBAL_Control
0x14015247e  cmp     rcx, rax
0x140152481  jz      short loc_1401524BA
0x140152483  test    dword ptr [rcx+2Ch], 1000h
0x14015248a  jz      short loc_1401524BA
0x14015248c  cmp     byte ptr [rcx+29h], 2
0x140152490  jb      short loc_1401524BA
0x140152492  mov     rax, [r14+0D8h]
0x140152499  lea     r8, WPP_38fa40eb983e345104985e233278c3ef_Traceguids
0x1401524a0  mov     r9, [r14+0D0h]
0x1401524a7  mov     edx, 14h
0x1401524ac  mov     rcx, [rcx+18h]
0x1401524b0  mov     [rsp+58h+Timeout], rax
0x1401524b5  call    WPP_SF_qq
0x1401524ba  mov     rcx, [r14+8]
0x1401524be  lea     rdx, [r14+0D0h]; union SmsBigIdentifier *
0x1401524c5  mov     rcx, [rcx+0D50h]; this
0x1401524cc  call    ?SetMinimumNewObjectId@CmsObjectTable@@QEAAJPEATSmsBigIdentifier@@@Z; CmsObjectTable::SetMinimumNewObjectId(SmsBigIdentifier *)
0x1401524d1  mov     ebp, eax
0x1401524d3  cmp     eax, 0C000000Dh
0x1401524d8  jnz     short loc_1401524E3
0x1401524da  xor     ebp, ebp
0x1401524dc  jmp     short loc_1401524E3
0x1401524de  mov     ebp, 0C000009Ah
0x1401524e3  cmp     cs:dword_1402403A4, 1
0x1401524ea  jnz     short loc_140152530
0x1401524ec  test    cs:Microsoft_Windows_MinstoreEnableBits, 1
0x1401524f3  jz      short loc_140152530
0x1401524f5  mov     rbx, [r14+60h]
0x1401524f9  mov     rdi, [r14+28h]
0x1401524fd  call    cs:__imp_IoGetActivityIdThread
0x140152504  nop     dword ptr [rax+rax+00h]
0x140152509  mov     [rsp+58h+var_30], 0
0x140152512  lea     rdx, RedoPassEnd
0x140152519  mov     r8, rax
0x14015251c  mov     [rsp+58h+Timeout], rbx
0x140152521  mov     r9, rdi
0x140152524  lea     rcx, MinstoreEventProvider_Context
0x14015252b  call    McTemplateK0iix_EtwWriteTransfer
0x140152530  mov     rbx, [rsp+58h+arg_10]
0x140152535  mov     eax, ebp
0x140152537  add     rsp, 30h
0x14015253b  pop     r15
0x14015253d  pop     r14
0x14015253f  pop     rdi
0x140152540  pop     rsi
0x140152541  pop     rbp
0x140152542  retn
```
