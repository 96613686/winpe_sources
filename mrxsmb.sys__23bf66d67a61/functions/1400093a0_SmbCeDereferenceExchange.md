# SmbCeDereferenceExchange

- ea: `0x1400093a0`
- end: `0x1400097cd`
- name: `SmbCeDereferenceExchange`
- size: `1069`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `30`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002270`
- `0x140004b90`
- `0x1400050b0`
- `0x140005740`
- `0x140006150`
- `0x140006ec0`
- `0x140009000`
- `0x140009070`
- `0x140009360`
- `0x1400099d0`
- `0x14000a100`
- `0x14000a260`
- `0x14000c270`
- `0x14000c720`
- `0x14000c880`
- `0x14000d080`
- `0x14000d3e0`
- `0x14000dd90`
- `0x14000e020`
- `0x14000ea90`
- `0x140012190`
- `0x140013cb0`
- `0x140016e60`
- `0x14001a760`
- `0x14001b7d0`
- `0x14002b410`
- `0x14002dab0`
- `0x14002fbb0`
- `0x14003d0f0`
- `0x140045c60`

## callees

- `0x140004360`
- `0x1400093a0`
- `0x1400097e0`
- `0x1400099d0`
- `0x140009fc0`
- `0x14000a000`
- `0x140014370`
- `0x140014400`
- `0x140021130`
- `0x140028230`
- `0x140028960`
- `0x140037eb0`
- `0x140037fa4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140009544`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140009544`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400095de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400095de`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x14000949a`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x14000949a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000940e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000940e`
- `ntoskrnl!KeBugCheckEx` at `0x140009480`
- `ntoskrnl!KeBugCheckEx` at `0x140009480`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000955d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000955d`
- `rdbss!RxPostToWorkerThread` at `0x1400095af`
- `rdbss!RxPostToWorkerThread` at `0x1400095af`

## pseudocode

```c
__int64 __fastcall SmbCeDereferenceExchange(unsigned __int64 pContext)
{
  unsigned __int32 v2; // ebx
  ULONG_PTR v4; // r12
  ULONG_PTR v5; // r14
  ULONG_PTR v6; // r15
  __int64 v7; // r13
  __int64 v8; // rbp
  int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  struct _LOOKASIDE_LIST_EX *v14; // rdi
  struct _RDBSS_DEVICE_OBJECT *v15; // rdi
  KIRQL v16; // al
  unsigned int v17; // r8d
  __int64 i; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rdx
  char v22; // [rsp+70h] [rbp+8h]
  ULONG_PTR BugCheckParameter2; // [rsp+78h] [rbp+10h]

  v2 = _InterlockedDecrement((volatile signed __int32 *)(pContext + 4));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
      pContext,
      v2 + 1,
      v2);
  }
  if ( !v2 )
  {
    if ( KeGetCurrentIrql() < 2u || (*(_DWORD *)(pContext + 68) & 0x40000) != 0 )
    {
      v4 = *(_QWORD *)(pContext + 72);
      v5 = *(_QWORD *)(pContext + 88);
      v6 = *(_QWORD *)(pContext + 96);
      v7 = *(_QWORD *)(v4 + 24);
      v8 = *(_QWORD *)(pContext + 56);
      BugCheckParameter2 = *(_QWORD *)(pContext + 80);
      if ( v8 )
      {
        v22 = 0;
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 4));
        v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 8));
        v17 = *(_DWORD *)(v8 + 20);
        *(_BYTE *)(v8 + 16) = v16;
        if ( v17 <= 1 || v17 - 2 <= 1 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qqD(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_2ecbbf7dc68f37694aaad8a30b991413_Traceguids,
              pContext,
              v8,
              v17);
          }
          for ( i = 0; (unsigned int)i < *(_DWORD *)(v8 + 168); i = (unsigned int)(i + 1) )
          {
            if ( *(_QWORD *)(8 * i + v8 + 176) == pContext )
            {
              *(_QWORD *)(8 * i + v8 + 176) = 0;
              *(_QWORD *)(pContext + 56) = 0;
              v19 = (unsigned int)--*(_DWORD *)(v8 + 168);
              v22 = 1;
              if ( (unsigned int)i < (unsigned int)v19 )
              {
                do
                {
                  v21 = (unsigned int)(i + 1);
                  *(_QWORD *)(v8 + 8 * i + 176) = *(_QWORD *)(v8 + 8 * v21 + 176);
                  v19 = *(unsigned int *)(v8 + 168);
                  i = v21;
                }
                while ( (unsigned int)v21 < (unsigned int)v19 );
              }
              *(_QWORD *)(v8 + 8 * v19 + 176) = 0;
              v20 = *(_DWORD *)(v8 + 168);
              if ( v20 && *(_DWORD *)(v8 + 172) == v20 && (*(_DWORD *)(v8 + 68) & 8) != 0 )
              {
                SmbCepResumeCompoundingKeyExchangesAndReleaseLock(v8);
                goto LABEL_37;
              }
              break;
            }
          }
        }
        SmbCeReleaseCompoundingKeyLock(v8);
        if ( v22 )
LABEL_37:
          SmbCseDereferenceCompoundingKey(v8);
      }
      v9 = _InterlockedDecrement((volatile signed __int32 *)(v7 + 2600));
      if ( v9 < 0 )
        KeBugCheckEx(0x27u, 0xA0001u, v7 + 2600, v9, 0);
      if ( !v9 )
        ExUnblockOnAddressPushLockEx(v7 + 2608, 0);
      if ( v5 )
      {
        SmbCeDereferenceVNetRootContext(v5);
      }
      else if ( BugCheckParameter2 )
      {
        SmbCeDereferenceSessionEntryEx(BugCheckParameter2);
      }
      else
      {
        SmbCeDereferenceServerEntryEx(v4);
      }
      if ( v6 )
        SmbCeDereferenceBindingObject(v6);
      v10 = *(_QWORD *)(pContext + 472);
      if ( v10 )
        SmbMmFreeSmbBuffer(v10, 1834181464);
      v11 = *(_QWORD *)(pContext + 480);
      if ( v11 )
        SmbMmFreeSmbBuffer(v11, 1834181464);
      v12 = *(_QWORD *)(pContext + 488);
      if ( v12 )
        SmbMmFreeSmbBuffer(v12, 1834181464);
      v13 = *(_QWORD *)(pContext + 496);
      if ( v13 )
        SmbMmFreeSmbBuffer(v13, 1834181464);
      if ( (*(_DWORD *)(pContext + 68) & 2) == 0 )
      {
        if ( (*(_DWORD *)(pContext + 68) & 4) != 0 )
        {
          v14 = (struct _LOOKASIDE_LIST_EX *)((char *)SmbMmExchangeLookasideList
                                            + 128 * (unsigned __int64)*(unsigned __int16 *)(pContext + 34));
          if ( !LOBYTE(v14[3].L.Depth) )
            PplpLazyInitializeLookasideList(SmbMmExchangeLookasideList, &v14[2]);
          ExFreeToLookasideListEx(v14 + 2, (PVOID)(pContext & 0xFFFFFFFFFFFFF000uLL));
        }
        else
        {
          ExFreePoolWithTag((PVOID)pContext, 0x6D536358u);
        }
      }
    }
    else
    {
      v15 = *(struct _RDBSS_DEVICE_OBJECT **)(*(_QWORD *)(pContext + 72) + 24LL);
      SmbCeIncrementTeardownOpCounter(v15, pContext, 7);
      RxPostToWorkerThread(
        v15,
        NormalWorkQueue,
        (PRX_WORK_QUEUE_ITEM)(pContext + 240),
        SmbCepDiscardExchangeWorker,
        (PVOID)pContext);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400093a0  push    rbx
0x1400093a2  push    rsi
0x1400093a3  push    rdi
0x1400093a4  sub     rsp, 50h
0x1400093a8  mov     edi, 0FFFFFFFFh
0x1400093ad  mov     rsi, rcx
0x1400093b0  mov     ebx, edi
0x1400093b2  lock xadd [rcx+4], ebx
0x1400093b7  dec     ebx
0x1400093b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400093c0  lea     rax, WPP_GLOBAL_Control
0x1400093c7  cmp     rcx, rax
0x1400093ca  jz      short loc_1400093D7
0x1400093cc  mov     eax, [rcx+2Ch]
0x1400093cf  test    al, 10h
0x1400093d1  jnz     loc_140009715
0x1400093d7  mov     [rsp+68h+var_20], r12
0x1400093dc  mov     [rsp+68h+var_28], r13
0x1400093e1  mov     [rsp+68h+var_30], r14
0x1400093e6  mov     [rsp+68h+var_38], r15
0x1400093eb  test    ebx, ebx
0x1400093ed  jz      short loc_14000940E
0x1400093ef  mov     r15, [rsp+68h+var_38]
0x1400093f4  mov     eax, ebx
0x1400093f6  mov     r14, [rsp+68h+var_30]
0x1400093fb  mov     r13, [rsp+68h+var_28]
0x140009400  mov     r12, [rsp+68h+var_20]
0x140009405  add     rsp, 50h
0x140009409  pop     rdi
0x14000940a  pop     rsi
0x14000940b  pop     rbx
0x14000940c  retn
0x14000940e  call    cs:__imp_KeGetCurrentIrql
0x140009415  nop     dword ptr [rax+rax+00h]
0x14000941a  cmp     al, 2
0x14000941c  jnb     loc_14000956E
0x140009422  mov     r12, [rsi+48h]
0x140009426  mov     rax, [rsi+50h]
0x14000942a  mov     r14, [rsi+58h]
0x14000942e  mov     r15, [rsi+60h]
0x140009432  mov     r13, [r12+18h]
0x140009437  mov     [rsp+68h+arg_10], rbp
0x14000943f  mov     rbp, [rsi+38h]
0x140009443  mov     [rsp+68h+BugCheckParameter2], rax
0x140009448  test    rbp, rbp
0x14000944b  jnz     loc_1400095D1
0x140009451  lea     r8, [r13+0A28h]; BugCheckParameter2
0x140009458  lock xadd [r8], edi
0x14000945d  sub     edi, 1
0x140009460  mov     rbp, [rsp+68h+arg_10]
0x140009468  jns     short loc_14000948D
0x14000946a  movsxd  r9, edi; BugCheckParameter3
0x14000946d  mov     edx, 0A0001h; BugCheckParameter1
0x140009472  mov     ecx, 27h ; '''; BugCheckCode
0x140009477  mov     [rsp+68h+BugCheckParameter4], 0; BugCheckParameter4
0x140009480  call    cs:__imp_KeBugCheckEx
0x14000948d  test    edi, edi
0x14000948f  jnz     short loc_1400094A6
0x140009491  lea     rcx, [r13+0A30h]
0x140009498  xor     edx, edx
0x14000949a  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x1400094a1  nop     dword ptr [rax+rax+00h]
0x1400094a6  test    r14, r14
0x1400094a9  jz      loc_14000976A
0x1400094af  mov     rcx, r14; BugCheckParameter2
0x1400094b2  call    SmbCeDereferenceVNetRootContext
0x1400094b7  test    r15, r15
0x1400094ba  jnz     loc_140009784
0x1400094c0  mov     rcx, [rsi+1D8h]
0x1400094c7  test    rcx, rcx
0x1400094ca  jnz     loc_140009791
0x1400094d0  mov     rcx, [rsi+1E0h]
0x1400094d7  test    rcx, rcx
0x1400094da  jnz     loc_1400097A0
0x1400094e0  mov     rcx, [rsi+1E8h]
0x1400094e7  test    rcx, rcx
0x1400094ea  jnz     loc_1400097AF
0x1400094f0  mov     rcx, [rsi+1F0h]
0x1400094f7  test    rcx, rcx
0x1400094fa  jnz     loc_1400097BE
0x140009500  mov     eax, [rsi+44h]
0x140009503  test    al, 2
0x140009505  jnz     loc_1400093EF
0x14000950b  mov     eax, [rsi+44h]
0x14000950e  test    al, 4
0x140009510  jz      short loc_140009555
0x140009512  movzx   edi, word ptr [rsi+22h]
0x140009516  mov     rcx, cs:SmbMmExchangeLookasideList
0x14000951d  shl     rdi, 7
0x140009521  add     rdi, rcx
0x140009524  movzx   eax, byte ptr [rdi+130h]
0x14000952b  test    al, al
0x14000952d  jz      loc_1400095C0
0x140009533  and     rsi, 0FFFFFFFFFFFFF000h
0x14000953a  lea     rcx, [rdi+0C0h]; Lookaside
0x140009541  mov     rdx, rsi; Entry
0x140009544  call    cs:__imp_ExFreeToLookasideListEx
0x14000954b  nop     dword ptr [rax+rax+00h]
0x140009550  jmp     loc_1400093EF
0x140009555  mov     edx, 6D536358h; Tag
0x14000955a  mov     rcx, rsi; P
0x14000955d  call    cs:__imp_ExFreePoolWithTag
0x140009564  nop     dword ptr [rax+rax+00h]
0x140009569  jmp     loc_1400093EF
0x14000956e  mov     eax, [rsi+44h]
0x140009571  bt      eax, 12h
0x140009575  jb      loc_140009422
0x14000957b  mov     rax, [rsi+48h]
0x14000957f  mov     r8d, 7
0x140009585  mov     rdx, rsi
0x140009588  mov     rdi, [rax+18h]
0x14000958c  mov     rcx, rdi
0x14000958f  call    SmbCeIncrementTeardownOpCounter
0x140009594  lea     r8, [rsi+0F0h]; pWorkQueueItem
0x14000959b  mov     [rsp+68h+BugCheckParameter4], rsi; pContext
0x1400095a0  lea     r9, SmbCepDiscardExchangeWorker; Routine
0x1400095a7  mov     edx, 3; WorkQueueType
0x1400095ac  mov     rcx, rdi; pMRxDeviceObject
0x1400095af  call    cs:__imp_RxPostToWorkerThread
0x1400095b6  nop     dword ptr [rax+rax+00h]
0x1400095bb  jmp     loc_1400093EF
0x1400095c0  lea     rdx, [rdi+0C0h]
0x1400095c7  call    PplpLazyInitializeLookasideList
0x1400095cc  jmp     loc_140009533
0x1400095d1  mov     [rsp+68h+arg_0], 0
0x1400095d6  lock inc dword ptr [rbp+4]
0x1400095da  lea     rcx, [rbp+8]; SpinLock
0x1400095de  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400095e5  nop     dword ptr [rax+rax+00h]
0x1400095ea  mov     r8d, [rbp+14h]
0x1400095ee  mov     [rbp+10h], al
0x1400095f1  cmp     r8d, 1
0x1400095f5  jnz     loc_140009747
0x1400095fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140009602  lea     rax, WPP_GLOBAL_Control
0x140009609  cmp     rcx, rax
0x14000960c  jz      short loc_140009619
0x14000960e  mov     eax, [rcx+2Ch]
0x140009611  test    al, 20h
0x140009613  jnz     loc_1400096B8
0x140009619  mov     r8d, [rbp+0A8h]
0x140009620  xor     ecx, ecx
0x140009622  cmp     ecx, r8d
0x140009625  jb      short loc_140009647
0x140009627  mov     rcx, rbp
0x14000962a  call    SmbCeReleaseCompoundingKeyLock
0x14000962f  cmp     [rsp+68h+arg_0], 0
0x140009634  jz      loc_140009451
0x14000963a  mov     rcx, rbp
0x14000963d  call    SmbCseDereferenceCompoundingKey
0x140009642  jmp     loc_140009451
0x140009647  lea     rdx, ds:0[rcx*8]
0x14000964f  cmp     [rdx+rbp+0B0h], rsi
0x140009657  jnz     short loc_1400096B1
0x140009659  mov     qword ptr [rdx+rbp+0B0h], 0
0x140009665  mov     qword ptr [rsi+38h], 0
0x14000966d  dec     dword ptr [rbp+0A8h]
0x140009673  mov     eax, [rbp+0A8h]
0x140009679  mov     [rsp+68h+arg_0], 1
0x14000967e  cmp     ecx, eax
0x140009680  jb      short loc_1400096F0
0x140009682  mov     qword ptr [rbp+rax*8+0B0h], 0
0x14000968e  mov     eax, [rbp+0A8h]
0x140009694  test    eax, eax
0x140009696  jz      short loc_140009627
0x140009698  cmp     [rbp+0ACh], eax
0x14000969e  jnz     short loc_140009627
0x1400096a0  mov     eax, [rbp+44h]
0x1400096a3  test    al, 8
0x1400096a5  jz      short loc_140009627
0x1400096a7  mov     rcx, rbp
0x1400096aa  call    SmbCepResumeCompoundingKeyExchangesAndReleaseLock
0x1400096af  jmp     short loc_14000963A
0x1400096b1  inc     ecx
0x1400096b3  jmp     loc_140009622
0x1400096b8  cmp     byte ptr [rcx+29h], 4
0x1400096bc  jb      loc_140009619
0x1400096c2  mov     rcx, [rcx+18h]
0x1400096c6  mov     edx, 14h
0x1400096cb  mov     [rsp+68h+var_40], r8d
0x1400096d0  mov     r9, rsi
0x1400096d3  lea     r8, WPP_2ecbbf7dc68f37694aaad8a30b991413_Traceguids
0x1400096da  mov     [rsp+68h+BugCheckParameter4], rbp
0x1400096df  call    WPP_SF_qqD
0x1400096e4  jmp     loc_140009619
0x1400096f0  lea     edx, [rcx+1]
0x1400096f3  mov     rax, [rbp+rdx*8+0B0h]
0x1400096fb  mov     [rbp+rcx*8+0B0h], rax
0x140009703  mov     eax, [rbp+0A8h]
0x140009709  mov     ecx, edx
0x14000970b  cmp     edx, eax
0x14000970d  jnb     loc_140009682
0x140009713  jmp     short loc_1400096F0
0x140009715  cmp     byte ptr [rcx+29h], 4
0x140009719  jb      loc_1400093D7
0x14000971f  mov     rcx, [rcx+18h]
0x140009723  lea     eax, [rbx+1]
0x140009726  mov     edx, 22h ; '"'
0x14000972b  mov     [rsp+68h+var_40], ebx
0x14000972f  mov     r9, rsi
0x140009732  mov     dword ptr [rsp+68h+BugCheckParameter4], eax
0x140009736  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x14000973d  call    WPP_SF_qDD
0x140009742  jmp     loc_1400093D7
0x140009747  mov     ecx, r8d
0x14000974a  test    r8d, r8d
0x14000974d  jz      loc_1400095FB
0x140009753  sub     ecx, 2
0x140009756  jz      loc_1400095FB
0x14000975c  cmp     ecx, 1
0x14000975f  jnz     loc_140009627
0x140009765  jmp     loc_1400095FB
0x14000976a  mov     rcx, [rsp+68h+BugCheckParameter2]; BugCheckParameter2
0x14000976f  xor     edx, edx
0x140009771  test    rcx, rcx
0x140009774  jz      loc_14005C5D4
0x14000977a  call    SmbCeDereferenceSessionEntryEx
0x14000977f  jmp     loc_1400094B7
0x140009784  mov     rcx, r15; BugCheckParameter2
0x140009787  call    SmbCeDereferenceBindingObject
0x14000978c  jmp     loc_1400094C0
0x140009791  mov     edx, 6D536358h
0x140009796  call    SmbMmFreeSmbBuffer
0x14000979b  jmp     loc_1400094D0
0x1400097a0  mov     edx, 6D536358h
0x1400097a5  call    SmbMmFreeSmbBuffer
0x1400097aa  jmp     loc_1400094E0
0x1400097af  mov     edx, 6D536358h
0x1400097b4  call    SmbMmFreeSmbBuffer
0x1400097b9  jmp     loc_1400094F0
0x1400097be  mov     edx, 6D536358h
0x1400097c3  call    SmbMmFreeSmbBuffer
0x1400097c8  jmp     loc_140009500
0x14005c5d4  mov     rcx, r12; BugCheckParameter2
0x14005c5d7  call    SmbCeDereferenceServerEntryEx
0x14005c5dc  nop
0x14005c5dd  jmp     loc_1400094B7
```
