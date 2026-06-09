# CmsRestarter::RedoPass(void)

- ea: `0x14015b624`
- end: `0x14015ba24`
- name: `?RedoPass@CmsRestarter@@AEAAJXZ`
- size: `1024`
- prototype: `__int64 __fastcall(CmsRestarter *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14015d68c`

## callees

- `0x140088930`
- `0x140097ba0`
- `0x1400b07a4`
- `0x1400ced2c`
- `0x1400f8c78`
- `0x140156138`
- `0x14015b624`
- `0x14015f214`
- `0x14017d14c`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14015b65b`
- `ntoskrnl!IoGetActivityIdThread` at `0x14015b9dd`
- `ntoskrnl!IoGetActivityIdThread` at `0x14015b65b`
- `ntoskrnl!IoGetActivityIdThread` at `0x14015b9dd`
- `ntoskrnl!KeSetEvent` at `0x14015b7ab`
- `ntoskrnl!KeSetEvent` at `0x14015b83f`
- `ntoskrnl!KeSetEvent` at `0x14015b7ab`
- `ntoskrnl!KeSetEvent` at `0x14015b83f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14015b8c8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14015b8c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14015b8da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14015b8da`
- `ntoskrnl!KeInitializeSpinLock` at `0x14015b781`
- `ntoskrnl!KeInitializeSpinLock` at `0x14015b781`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14015b6a4`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14015b6a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015b8b8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015b8b8`
- `ntoskrnl!KeInitializeEvent` at `0x14015b796`
- `ntoskrnl!KeInitializeEvent` at `0x14015b7c5`
- `ntoskrnl!KeInitializeEvent` at `0x14015b796`
- `ntoskrnl!KeInitializeEvent` at `0x14015b7c5`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015b87d`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015b87d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015b865`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015b865`

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
  if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
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
              WPP_SF_ii(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_d6f1a70892843b576046f9b8179af02d_Traceguids,
                *((_QWORD *)v3 + 26));
            }
            v2 = CmsObjectTable::SetMinimumNewObjectId(
                   *(CmsObjectTable **)(*((_QWORD *)v3 + 1) + 3344LL),
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
  if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
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
0x14015b624  mov     [rsp+arg_10], rbx
0x14015b629  push    rbp
0x14015b62a  push    rsi
0x14015b62b  push    rdi
0x14015b62c  push    r14
0x14015b62e  push    r15
0x14015b630  sub     rsp, 30h
0x14015b634  xor     ebp, ebp
0x14015b636  mov     [rsp+58h+arg_0], 0
0x14015b63f  cmp     cs:dword_1402473A4, 1
0x14015b646  mov     r14, rcx
0x14015b649  jnz     short loc_14015B68A
0x14015b64b  test    cs:Microsoft_Windows_MinstoreEnableBits, 1
0x14015b652  jz      short loc_14015B68A
0x14015b654  mov     ebx, [rcx+20h]
0x14015b657  mov     rdi, [rcx+28h]
0x14015b65b  call    cs:__imp_IoGetActivityIdThread
0x14015b662  nop     dword ptr [rax+rax+00h]
0x14015b667  mov     [rsp+58h+var_30], rbx
0x14015b66c  lea     rdx, RedoPassStart
0x14015b673  mov     r8, rax
0x14015b676  mov     [rsp+58h+Timeout], rbp
0x14015b67b  mov     r9, rdi
0x14015b67e  lea     rcx, MinstoreEventProvider_Context
0x14015b685  call    McTemplateK0iix_EtwWriteTransfer
0x14015b68a  cmp     [r14+0C8h], ebp
0x14015b691  jz      loc_14015B9C3
0x14015b697  mov     ecx, 0FFFFh; GroupNumber
0x14015b69c  mov     dword ptr [r14+10h], 4
0x14015b6a4  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14015b6ab  nop     dword ptr [rax+rax+00h]
0x14015b6b0  mov     esi, 160h
0x14015b6b5  lea     ebp, [rax+rax]
0x14015b6b8  mov     eax, esi
0x14015b6ba  mul     rbp
0x14015b6bd  mov     rbx, rax
0x14015b6c0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14015b6c7  cmovb   rbx, rax
0x14015b6cb  add     rbx, 8
0x14015b6cf  cmovb   rbx, rax
0x14015b6d3  mov     rcx, rbx; unsigned __int64
0x14015b6d6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14015b6db  mov     rdi, rax
0x14015b6de  test    rax, rax
0x14015b6e1  jz      short loc_14015B70D
0x14015b6e3  mov     r8, rbx; Size
0x14015b6e6  xor     edx, edx; Val
0x14015b6e8  mov     rcx, rax; void *
0x14015b6eb  call    memset
0x14015b6f0  lea     rbx, [rdi+8]
0x14015b6f4  mov     [rdi], rbp
0x14015b6f7  mov     rcx, rbx; void *
0x14015b6fa  lea     r9, ??0CmsLogRedoQueue@@QEAA@XZ; void *(*)(void *)
0x14015b701  mov     r8d, ebp; unsigned __int64
0x14015b704  mov     edx, esi; unsigned __int64
0x14015b706  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14015b70b  jmp     short loc_14015B70F
0x14015b70d  xor     ebx, ebx
0x14015b70f  mov     rdx, [r14+100h]
0x14015b716  mov     [rsp+58h+arg_8], 0
0x14015b71f  mov     [r14+100h], rbx
0x14015b726  test    rdx, rdx
0x14015b729  jz      short loc_14015B730
0x14015b72b  call    ??$?RVCmsLogRedoQueue@@$0A@@?$default_delete@$$BY0A@VCmsLogRedoQueue@@@utl@@QEBAXPEAVCmsLogRedoQueue@@@Z; utl::default_delete<CmsLogRedoQueue [0]>::operator()<CmsLogRedoQueue,0>(CmsLogRedoQueue *)
0x14015b730  lea     rcx, [rsp+58h+arg_8]
0x14015b735  call    ??1?$unique_ptr@$$BY0A@VCmsLogRedoQueue@@U?$default_delete@$$BY0A@VCmsLogRedoQueue@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CmsLogRedoQueue [0],utl::default_delete<CmsLogRedoQueue [0]>>::~unique_ptr<CmsLogRedoQueue [0],utl::default_delete<CmsLogRedoQueue [0]>>(void)
0x14015b73a  mov     rax, [r14+100h]
0x14015b741  test    rax, rax
0x14015b744  jz      loc_14015B9BE
0x14015b74a  mov     [r14+0E8h], rax
0x14015b751  xor     r15d, r15d
0x14015b754  imul    rdi, rbp, 160h
0x14015b75b  mov     [r14+0F0h], rbp
0x14015b762  mov     rbx, [r14+0E8h]
0x14015b769  add     rdi, rbx
0x14015b76c  cmp     rbx, rdi
0x14015b76f  jz      short loc_14015B7E2
0x14015b771  mov     eax, r15d
0x14015b774  lea     rcx, [rbx+20h]; SpinLock
0x14015b778  mov     [rbx+158h], eax
0x14015b77e  inc     r15d
0x14015b781  call    cs:__imp_KeInitializeSpinLock
0x14015b788  nop     dword ptr [rax+rax+00h]
0x14015b78d  xor     r8d, r8d; State
0x14015b790  lea     rcx, [rbx+28h]; Event
0x14015b794  xor     edx, edx; Type
0x14015b796  call    cs:__imp_KeInitializeEvent
0x14015b79d  nop     dword ptr [rax+rax+00h]
0x14015b7a2  xor     r8d, r8d; Wait
0x14015b7a5  lea     rcx, [rbx+28h]; Event
0x14015b7a9  xor     edx, edx; Increment
0x14015b7ab  call    cs:__imp_KeSetEvent
0x14015b7b2  nop     dword ptr [rax+rax+00h]
0x14015b7b7  xor     r8d, r8d; State
0x14015b7ba  lea     rcx, [rbx+88h]; Event
0x14015b7c1  lea     edx, [r8+1]; Type
0x14015b7c5  call    cs:__imp_KeInitializeEvent
0x14015b7cc  nop     dword ptr [rax+rax+00h]
0x14015b7d1  mov     esi, 160h
0x14015b7d6  mov     [rbx+150h], r14
0x14015b7dd  add     rbx, rsi
0x14015b7e0  jmp     short loc_14015B76C
0x14015b7e2  mov     rcx, rbp; unsigned __int64
0x14015b7e5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14015b7ea  mov     [r14+158h], rax
0x14015b7f1  test    rax, rax
0x14015b7f4  jz      loc_14015B9BE
0x14015b7fa  mov     r8, rbp; Size
0x14015b7fd  xor     edx, edx; Val
0x14015b7ff  mov     rcx, rax; void *
0x14015b802  call    memset
0x14015b807  mov     rcx, [r14]
0x14015b80a  lea     rax, [rsp+58h+arg_0]
0x14015b80f  mov     r8, [r14+28h]
0x14015b813  lea     r9, ?RedoOneMergedRecordBlock@CmsRestarter@@CAJT_ML_LSN@@PEAXK1@Z; CmsRestarter::RedoOneMergedRecordBlock(_ML_LSN,void *,ulong,void *)
0x14015b81a  mov     rdx, [r14+8]
0x14015b81e  mov     [rsp+58h+var_30], rax
0x14015b823  mov     rcx, [rcx+48h]
0x14015b827  mov     [rsp+58h+Timeout], r14
0x14015b82c  call    MlLogScanLog
0x14015b831  lea     rcx, [r14+128h]; Event
0x14015b838  xor     r8d, r8d; Wait
0x14015b83b  xor     edx, edx; Increment
0x14015b83d  mov     ebp, eax
0x14015b83f  call    cs:__imp_KeSetEvent
0x14015b846  nop     dword ptr [rax+rax+00h]
0x14015b84b  test    ebp, ebp
0x14015b84d  jns     short loc_14015B889
0x14015b84f  cmp     dword ptr [r14+0E0h], 0
0x14015b857  jl      short loc_14015B889
0x14015b859  lea     rbx, [r14+0F8h]
0x14015b860  xor     edx, edx
0x14015b862  mov     rcx, rbx
0x14015b865  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14015b86c  nop     dword ptr [rax+rax+00h]
0x14015b871  xor     edx, edx
0x14015b873  mov     [r14+0E0h], ebp
0x14015b87a  mov     rcx, rbx
0x14015b87d  call    cs:__imp_ExReleasePushLockEx
0x14015b884  nop     dword ptr [rax+rax+00h]
0x14015b889  imul    rdi, [r14+0F0h], 160h
0x14015b894  mov     rbx, [r14+0E8h]
0x14015b89b  add     rdi, rbx
0x14015b89e  cmp     rbx, rdi
0x14015b8a1  jz      short loc_14015B8F0
0x14015b8a3  lea     rcx, [rbx+28h]; Object
0x14015b8a7  mov     [rsp+58h+Timeout], 0; Timeout
0x14015b8b0  xor     r9d, r9d; Alertable
0x14015b8b3  xor     r8d, r8d; WaitMode
0x14015b8b6  xor     edx, edx; WaitReason
0x14015b8b8  call    cs:__imp_KeWaitForSingleObject
0x14015b8bf  nop     dword ptr [rax+rax+00h]
0x14015b8c4  lea     rcx, [rbx+20h]; SpinLock
0x14015b8c8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14015b8cf  nop     dword ptr [rax+rax+00h]
0x14015b8d4  mov     dl, al; NewIrql
0x14015b8d6  lea     rcx, [rbx+20h]; SpinLock
0x14015b8da  call    cs:__imp_KeReleaseSpinLock
0x14015b8e1  nop     dword ptr [rax+rax+00h]
0x14015b8e6  mov     esi, 160h
0x14015b8eb  add     rbx, rsi
0x14015b8ee  jmp     short loc_14015B89E
0x14015b8f0  test    ebp, ebp
0x14015b8f2  js      loc_14015B9C3
0x14015b8f8  mov     rax, [rsp+58h+arg_0]
0x14015b8fd  mov     ebp, [r14+0E0h]
0x14015b904  mov     [r14+68h], rax
0x14015b908  test    ebp, ebp
0x14015b90a  js      loc_14015B9C3
0x14015b910  imul    rcx, [r14+0F0h], 160h
0x14015b91b  mov     rax, [r14+0E8h]
0x14015b922  add     rcx, rax
0x14015b925  cmp     rax, rcx
0x14015b928  jz      short loc_14015B939
0x14015b92a  mov     edx, [rax+8]
0x14015b92d  sub     [r14+0C8h], edx
0x14015b934  add     rax, rsi
0x14015b937  jmp     short loc_14015B925
0x14015b939  mov     eax, [r14+0CCh]
0x14015b940  sub     [r14+0C8h], eax
0x14015b947  jz      short loc_14015B950
0x14015b949  mov     ebp, 0C0000032h
0x14015b94e  jmp     short loc_14015B9C3
0x14015b950  mov     rcx, cs:WPP_GLOBAL_Control
0x14015b957  lea     rax, WPP_GLOBAL_Control
0x14015b95e  cmp     rcx, rax
0x14015b961  jz      short loc_14015B99A
0x14015b963  test    dword ptr [rcx+2Ch], 1000h
0x14015b96a  jz      short loc_14015B99A
0x14015b96c  cmp     byte ptr [rcx+29h], 2
0x14015b970  jb      short loc_14015B99A
0x14015b972  mov     rax, [r14+0D8h]
0x14015b979  lea     r8, WPP_d6f1a70892843b576046f9b8179af02d_Traceguids
0x14015b980  mov     r9, [r14+0D0h]
0x14015b987  mov     edx, 14h
0x14015b98c  mov     rcx, [rcx+18h]
0x14015b990  mov     [rsp+58h+Timeout], rax
0x14015b995  call    WPP_SF_ii
0x14015b99a  mov     rcx, [r14+8]
0x14015b99e  lea     rdx, [r14+0D0h]; union SmsBigIdentifier *
0x14015b9a5  mov     rcx, [rcx+0D10h]; this
0x14015b9ac  call    ?SetMinimumNewObjectId@CmsObjectTable@@QEAAJPEATSmsBigIdentifier@@@Z; CmsObjectTable::SetMinimumNewObjectId(SmsBigIdentifier *)
0x14015b9b1  mov     ebp, eax
0x14015b9b3  cmp     eax, 0C000000Dh
0x14015b9b8  jnz     short loc_14015B9C3
0x14015b9ba  xor     ebp, ebp
0x14015b9bc  jmp     short loc_14015B9C3
0x14015b9be  mov     ebp, 0C000009Ah
0x14015b9c3  cmp     cs:dword_1402473A4, 1
0x14015b9ca  jnz     short loc_14015BA10
0x14015b9cc  test    cs:Microsoft_Windows_MinstoreEnableBits, 1
0x14015b9d3  jz      short loc_14015BA10
0x14015b9d5  mov     rbx, [r14+60h]
0x14015b9d9  mov     rdi, [r14+28h]
0x14015b9dd  call    cs:__imp_IoGetActivityIdThread
0x14015b9e4  nop     dword ptr [rax+rax+00h]
0x14015b9e9  mov     [rsp+58h+var_30], 0
0x14015b9f2  lea     rdx, RedoPassEnd
0x14015b9f9  mov     r8, rax
0x14015b9fc  mov     [rsp+58h+Timeout], rbx
0x14015ba01  mov     r9, rdi
0x14015ba04  lea     rcx, MinstoreEventProvider_Context
0x14015ba0b  call    McTemplateK0iix_EtwWriteTransfer
0x14015ba10  mov     rbx, [rsp+58h+arg_10]
0x14015ba15  mov     eax, ebp
0x14015ba17  add     rsp, 30h
0x14015ba1b  pop     r15
0x14015ba1d  pop     r14
0x14015ba1f  pop     rdi
0x14015ba20  pop     rsi
0x14015ba21  pop     rbp
0x14015ba22  retn
```
