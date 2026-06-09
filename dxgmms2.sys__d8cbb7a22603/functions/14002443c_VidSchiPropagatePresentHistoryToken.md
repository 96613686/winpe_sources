# VidSchiPropagatePresentHistoryToken

- ea: `0x14002443c`
- end: `0x1400246c8`
- name: `VidSchiPropagatePresentHistoryToken`
- size: `652`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001df34`
- `0x140022304`
- `0x1400250dc`
- `0x14004f200`
- `0x140109b10`

## callees

- `0x14002443c`
- `0x1400246d0`
- `0x14002471c`
- `0x140059030`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002463c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002463c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024663`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024663`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002458b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002458b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400246b0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400246b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002459e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002459e`
- `dxgkrnl!DxgCoreInterface` at `0x140024674`

## pseudocode

```c
void __fastcall VidSchiPropagatePresentHistoryToken(
        __int64 a1,
        union _SLIST_HEADER *a2,
        struct _D3DKMT_PRESENTHISTORYTOKEN *a3,
        bool a4,
        bool a5,
        bool a6,
        bool a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        char a12)
{
  void *v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r10
  int v21; // edi
  char v22; // di
  unsigned int i; // edi
  __int64 v24; // rbp
  __int64 v25; // rcx
  void *v26; // rcx
  BOOL v27; // eax
  __int64 v28; // rbp
  void *v29; // rcx
  bool v30; // [rsp+38h] [rbp-80h]
  bool v31; // [rsp+40h] [rbp-78h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-68h] BYREF

  if ( a10 )
  {
    v16 = *(void **)(a10 + 560);
    if ( v16 )
    {
      v17 = *(unsigned int *)(a10 + 568);
      v18 = *(_QWORD *)(a10 + 576);
      v19 = *(_QWORD *)(a10 + 584);
      v20 = *(_QWORD *)(a10 + 592);
      v21 = *(_DWORD *)(a10 + 4) >> 5;
LABEL_4:
      v22 = v21 & 1;
      goto LABEL_5;
    }
  }
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v22 = 0;
  if ( a11 && *(_QWORD *)a11 )
  {
    v17 = *(unsigned int *)(a11 + 8);
    v16 = *(void **)a11;
    v18 = *(_QWORD *)(a11 + 16);
    v19 = *(_QWORD *)(a11 + 24);
    v20 = *(_QWORD *)(a11 + 32);
    LOBYTE(v21) = *(_BYTE *)(a11 + 40);
    goto LABEL_4;
  }
LABEL_5:
  if ( a4 && !a12 )
  {
    v16 = 0;
LABEL_7:
    if ( a8 )
    {
      v28 = *(_QWORD *)(a9 + 208);
      if ( v28 )
      {
        memset(&LockHandle, 0, sizeof(LockHandle));
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a8 + 16), &LockHandle);
        _InterlockedIncrement((volatile signed __int32 *)(v28 + 12));
        v29 = *(void **)(a8 + 8);
        if ( v29 )
          CRefCountedBuffer::RefCountedBufferRelease(v29);
        *(_QWORD *)(a8 + 8) = v28;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
    }
    if ( a10 )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 160); ++i )
      {
        v24 = 8 * i * (*(_DWORD *)(a10 + 608) + 28);
        v25 = *(_QWORD *)(a10 + v24 + 808);
        if ( v25 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v25 + 12), 0xFFFFFFFF) == 1 )
          {
            if ( *(_QWORD *)v25 )
              ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)v25, (PVOID)v25);
            else
              ExFreePoolWithTag((PVOID)v25, 0);
          }
          *(_QWORD *)(a10 + v24 + 808) = 0;
        }
      }
      v26 = *(void **)(a10 + 32);
      if ( v26 )
      {
        CRefCountedBuffer::RefCountedBufferRelease(v26);
        *(_QWORD *)(a10 + 32) = 0;
      }
      v27 = *(_DWORD *)(a10 + 4) & 1;
    }
    else
    {
      LOBYTE(v27) = 0;
    }
    DXGPRESENTHISTORYTOKENQUEUE::PropagatePresentHistoryToken(&a2->Alignment, a3, a4, a5, a6, a7, v27, v30, v31, v16);
    return;
  }
  if ( !v16 )
    goto LABEL_7;
  ((void (__fastcall *)(void *, __int64, __int64, __int64, __int64, char))DxgCoreInterface[76])(
    v16,
    v17,
    v18,
    v19,
    v20,
    v22);
  if ( v22 )
    goto LABEL_7;
  if ( (*(_DWORD *)(a10 + 4) & 0x10) != 0 )
    ExpInterlockedPushEntrySList(a2 + 3, (PSLIST_ENTRY)(&a3[-1].Token.SurfaceComplete + 131));
}

```

## disassembly

```asm
0x14002443c  push    rbx
0x14002443e  push    rbp
0x14002443f  push    rsi
0x140024440  push    rdi
0x140024441  push    r12
0x140024443  push    r13
0x140024445  push    r14
0x140024447  push    r15
0x140024449  sub     rsp, 78h
0x14002444d  mov     rbx, [rsp+0B8h+arg_48]
0x140024455  mov     r13b, r9b
0x140024458  mov     r14, r8
0x14002445b  mov     r15, rdx
0x14002445e  mov     r12, rcx
0x140024461  test    rbx, rbx
0x140024464  jz      loc_1400245AF
0x14002446a  mov     rsi, [rbx+230h]
0x140024471  test    rsi, rsi
0x140024474  jz      loc_1400245AF
0x14002447a  mov     edi, [rbx+4]
0x14002447d  mov     edx, [rbx+238h]
0x140024483  mov     r8, [rbx+240h]
0x14002448a  mov     r9, [rbx+248h]
0x140024491  mov     r10, [rbx+250h]
0x140024498  shr     edi, 5
0x14002449b  and     dil, 1
0x14002449f  test    r13b, r13b
0x1400244a2  jnz     loc_1400245F7
0x1400244a8  test    rsi, rsi
0x1400244ab  jnz     loc_140024674
0x1400244b1  mov     rdi, [rsp+0B8h+arg_38]
0x1400244b9  test    rdi, rdi
0x1400244bc  jnz     loc_14002460C
0x1400244c2  test    rbx, rbx
0x1400244c5  jz      loc_1400246C1
0x1400244cb  xor     edi, edi
0x1400244cd  cmp     [r12+0A0h], edi
0x1400244d5  jbe     short loc_14002451A
0x1400244d7  mov     eax, [rbx+260h]
0x1400244dd  add     eax, 1Ch
0x1400244e0  imul    eax, edi
0x1400244e3  shl     eax, 3
0x1400244e6  mov     ebp, eax
0x1400244e8  mov     rcx, [rbx+rax+328h]; P
0x1400244f0  test    rcx, rcx
0x1400244f3  jz      short loc_14002450E
0x1400244f5  or      eax, 0FFFFFFFFh
0x1400244f8  lock xadd [rcx+0Ch], eax
0x1400244fd  cmp     eax, 1
0x140024500  jz      short loc_14002457D
0x140024502  mov     qword ptr [rbx+rbp+328h], 0
0x14002450e  inc     edi
0x140024510  cmp     edi, [r12+0A0h]
0x140024518  jb      short loc_1400244D7
0x14002451a  mov     rcx, [rbx+20h]; Entry
0x14002451e  test    rcx, rcx
0x140024521  jz      short loc_140024530
0x140024523  call    ?RefCountedBufferRelease@CRefCountedBuffer@@QEAAXXZ; CRefCountedBuffer::RefCountedBufferRelease(void)
0x140024528  mov     qword ptr [rbx+20h], 0
0x140024530  mov     eax, [rbx+4]
0x140024533  and     eax, 1
0x140024536  mov     r9b, [rsp+0B8h+arg_20]; bool
0x14002453e  mov     r8b, r13b; bool
0x140024541  mov     [rsp+0B8h+var_70], rsi; void *
0x140024546  mov     rdx, r14; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x140024549  mov     [rsp+0B8h+var_88], al; bool
0x14002454d  mov     rcx, r15; SpinLock
0x140024550  mov     al, [rsp+0B8h+arg_30]
0x140024557  mov     [rsp+0B8h+var_90], al; bool
0x14002455b  mov     al, [rsp+0B8h+arg_28]
0x140024562  mov     [rsp+0B8h+var_98], al; bool
0x140024566  call    ?PropagatePresentHistoryToken@DXGPRESENTHISTORYTOKENQUEUE@@QEAAXPEAU_D3DKMT_PRESENTHISTORYTOKEN@@_N111111PEAX@Z; DXGPRESENTHISTORYTOKENQUEUE::PropagatePresentHistoryToken(_D3DKMT_PRESENTHISTORYTOKEN *,bool,bool,bool,bool,bool,bool,bool,void *)
0x14002456b  add     rsp, 78h
0x14002456f  pop     r15
0x140024571  pop     r14
0x140024573  pop     r13
0x140024575  pop     r12
0x140024577  pop     rdi
0x140024578  pop     rsi
0x140024579  pop     rbp
0x14002457a  pop     rbx
0x14002457b  retn
0x14002457d  mov     rax, [rcx]
0x140024580  test    rax, rax
0x140024583  jz      short loc_14002459C
0x140024585  mov     rdx, rcx; Entry
0x140024588  mov     rcx, rax; Lookaside
0x14002458b  call    cs:__imp_ExFreeToLookasideListEx
0x140024592  nop     dword ptr [rax+rax+00h]
0x140024597  jmp     loc_140024502
0x14002459c  xor     edx, edx; Tag
0x14002459e  call    cs:__imp_ExFreePoolWithTag
0x1400245a5  nop     dword ptr [rax+rax+00h]
0x1400245aa  jmp     loc_140024502
0x1400245af  mov     rax, [rsp+0B8h+arg_50]
0x1400245b7  xor     esi, esi
0x1400245b9  xor     edx, edx
0x1400245bb  xor     r8d, r8d
0x1400245be  xor     r9d, r9d
0x1400245c1  xor     r10d, r10d
0x1400245c4  xor     dil, dil
0x1400245c7  test    rax, rax
0x1400245ca  jz      loc_14002449F
0x1400245d0  mov     rcx, [rax]
0x1400245d3  test    rcx, rcx
0x1400245d6  jz      loc_14002449F
0x1400245dc  mov     edx, [rax+8]
0x1400245df  mov     rsi, rcx
0x1400245e2  mov     r8, [rax+10h]
0x1400245e6  mov     r9, [rax+18h]
0x1400245ea  mov     r10, [rax+20h]
0x1400245ee  mov     dil, [rax+28h]
0x1400245f2  jmp     loc_14002449B
0x1400245f7  cmp     [rsp+0B8h+arg_58], 0
0x1400245ff  jnz     loc_1400244A8
0x140024605  xor     esi, esi
0x140024607  jmp     loc_1400244B1
0x14002460c  mov     rax, [rsp+0B8h+arg_40]
0x140024614  mov     rbp, [rax+0D0h]
0x14002461b  test    rbp, rbp
0x14002461e  jz      loc_1400244C2
0x140024624  xorps   xmm0, xmm0
0x140024627  lea     rcx, [rdi+10h]; SpinLock
0x14002462b  xor     eax, eax
0x14002462d  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x140024632  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x140024637  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x14002463c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140024643  nop     dword ptr [rax+rax+00h]
0x140024648  lock inc dword ptr [rbp+0Ch]
0x14002464c  mov     rcx, [rdi+8]; Entry
0x140024650  test    rcx, rcx
0x140024653  jz      short loc_14002465A
0x140024655  call    ?RefCountedBufferRelease@CRefCountedBuffer@@QEAAXXZ; CRefCountedBuffer::RefCountedBufferRelease(void)
0x14002465a  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14002465f  mov     [rdi+8], rbp
0x140024663  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002466a  nop     dword ptr [rax+rax+00h]
0x14002466f  jmp     loc_1400244C2
0x140024674  mov     rax, cs:DxgCoreInterface
0x14002467b  mov     rcx, rsi
0x14002467e  mov     [rsp+0B8h+var_90], dil
0x140024683  mov     qword ptr [rsp+0B8h+var_98], r10
0x140024688  mov     rax, [rax+260h]
0x14002468f  call    _guard_dispatch_icall
0x140024694  test    dil, dil
0x140024697  jnz     loc_1400244B1
0x14002469d  mov     eax, [rbx+4]
0x1400246a0  test    al, 10h
0x1400246a2  jz      loc_14002456B
0x1400246a8  lea     rdx, [r14-10h]; ListEntry
0x1400246ac  lea     rcx, [r15+30h]; ListHead
0x1400246b0  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400246b7  nop     dword ptr [rax+rax+00h]
0x1400246bc  jmp     loc_14002456B
0x1400246c1  xor     eax, eax
0x1400246c3  jmp     loc_140024536
```
