# VidSchiPropagatePresentHistoryToken

- ea: `0x14001898c`
- end: `0x140018c18`
- name: `VidSchiPropagatePresentHistoryToken`
- size: `652`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001fa94`
- `0x140024d78`
- `0x140026a78`
- `0x14004eaf0`
- `0x140100a10`

## callees

- `0x14001898c`
- `0x140018c20`
- `0x140018c6c`
- `0x140058760`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018b8c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018b8c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018bb3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018bb3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140018adb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140018adb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140018c00`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140018c00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018aee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018aee`
- `dxgkrnl!DxgCoreInterface` at `0x140018bc4`

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
  const wchar_t *v19; // r9
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
      v19 = *(const wchar_t **)(a10 + 584);
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
    v19 = *(const wchar_t **)(a11 + 24);
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
  ((void (**)(void *, __int64, __int64, const wchar_t *, ...))DxgCoreInterface)[76](v16, v17, v18, v19, v20, v22);
  if ( v22 )
    goto LABEL_7;
  if ( (*(_DWORD *)(a10 + 4) & 0x10) != 0 )
    ExpInterlockedPushEntrySList(a2 + 3, (PSLIST_ENTRY)(&a3[-1].Token.SurfaceComplete + 131));
}

```

## disassembly

```asm
0x14001898c  push    rbx
0x14001898e  push    rbp
0x14001898f  push    rsi
0x140018990  push    rdi
0x140018991  push    r12
0x140018993  push    r13
0x140018995  push    r14
0x140018997  push    r15
0x140018999  sub     rsp, 78h
0x14001899d  mov     rbx, [rsp+0B8h+arg_48]
0x1400189a5  mov     r13b, r9b
0x1400189a8  mov     r14, r8
0x1400189ab  mov     r15, rdx
0x1400189ae  mov     r12, rcx
0x1400189b1  test    rbx, rbx
0x1400189b4  jz      loc_140018AFF
0x1400189ba  mov     rsi, [rbx+230h]
0x1400189c1  test    rsi, rsi
0x1400189c4  jz      loc_140018AFF
0x1400189ca  mov     edi, [rbx+4]
0x1400189cd  mov     edx, [rbx+238h]
0x1400189d3  mov     r8, [rbx+240h]
0x1400189da  mov     r9, [rbx+248h]
0x1400189e1  mov     r10, [rbx+250h]
0x1400189e8  shr     edi, 5
0x1400189eb  and     dil, 1
0x1400189ef  test    r13b, r13b
0x1400189f2  jnz     loc_140018B47
0x1400189f8  test    rsi, rsi
0x1400189fb  jnz     loc_140018BC4
0x140018a01  mov     rdi, [rsp+0B8h+arg_38]
0x140018a09  test    rdi, rdi
0x140018a0c  jnz     loc_140018B5C
0x140018a12  test    rbx, rbx
0x140018a15  jz      loc_140018C11
0x140018a1b  xor     edi, edi
0x140018a1d  cmp     [r12+0A0h], edi
0x140018a25  jbe     short loc_140018A6A
0x140018a27  mov     eax, [rbx+260h]
0x140018a2d  add     eax, 1Ch
0x140018a30  imul    eax, edi
0x140018a33  shl     eax, 3
0x140018a36  mov     ebp, eax
0x140018a38  mov     rcx, [rbx+rax+328h]; P
0x140018a40  test    rcx, rcx
0x140018a43  jz      short loc_140018A5E
0x140018a45  or      eax, 0FFFFFFFFh
0x140018a48  lock xadd [rcx+0Ch], eax
0x140018a4d  cmp     eax, 1
0x140018a50  jz      short loc_140018ACD
0x140018a52  mov     qword ptr [rbx+rbp+328h], 0
0x140018a5e  inc     edi
0x140018a60  cmp     edi, [r12+0A0h]
0x140018a68  jb      short loc_140018A27
0x140018a6a  mov     rcx, [rbx+20h]; Entry
0x140018a6e  test    rcx, rcx
0x140018a71  jz      short loc_140018A80
0x140018a73  call    ?RefCountedBufferRelease@CRefCountedBuffer@@QEAAXXZ; CRefCountedBuffer::RefCountedBufferRelease(void)
0x140018a78  mov     qword ptr [rbx+20h], 0
0x140018a80  mov     eax, [rbx+4]
0x140018a83  and     eax, 1
0x140018a86  mov     r9b, [rsp+0B8h+arg_20]; bool
0x140018a8e  mov     r8b, r13b; bool
0x140018a91  mov     [rsp+0B8h+var_70], rsi; void *
0x140018a96  mov     rdx, r14; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x140018a99  mov     [rsp+0B8h+var_88], al; bool
0x140018a9d  mov     rcx, r15; SpinLock
0x140018aa0  mov     al, [rsp+0B8h+arg_30]
0x140018aa7  mov     [rsp+0B8h+var_90], al; bool
0x140018aab  mov     al, [rsp+0B8h+arg_28]
0x140018ab2  mov     [rsp+0B8h+var_98], al; bool
0x140018ab6  call    ?PropagatePresentHistoryToken@DXGPRESENTHISTORYTOKENQUEUE@@QEAAXPEAU_D3DKMT_PRESENTHISTORYTOKEN@@_N111111PEAX@Z; DXGPRESENTHISTORYTOKENQUEUE::PropagatePresentHistoryToken(_D3DKMT_PRESENTHISTORYTOKEN *,bool,bool,bool,bool,bool,bool,bool,void *)
0x140018abb  add     rsp, 78h
0x140018abf  pop     r15
0x140018ac1  pop     r14
0x140018ac3  pop     r13
0x140018ac5  pop     r12
0x140018ac7  pop     rdi
0x140018ac8  pop     rsi
0x140018ac9  pop     rbp
0x140018aca  pop     rbx
0x140018acb  retn
0x140018acd  mov     rax, [rcx]
0x140018ad0  test    rax, rax
0x140018ad3  jz      short loc_140018AEC
0x140018ad5  mov     rdx, rcx; Entry
0x140018ad8  mov     rcx, rax; Lookaside
0x140018adb  call    cs:__imp_ExFreeToLookasideListEx
0x140018ae2  nop     dword ptr [rax+rax+00h]
0x140018ae7  jmp     loc_140018A52
0x140018aec  xor     edx, edx; Tag
0x140018aee  call    cs:__imp_ExFreePoolWithTag
0x140018af5  nop     dword ptr [rax+rax+00h]
0x140018afa  jmp     loc_140018A52
0x140018aff  mov     rax, [rsp+0B8h+arg_50]
0x140018b07  xor     esi, esi
0x140018b09  xor     edx, edx
0x140018b0b  xor     r8d, r8d
0x140018b0e  xor     r9d, r9d
0x140018b11  xor     r10d, r10d
0x140018b14  xor     dil, dil
0x140018b17  test    rax, rax
0x140018b1a  jz      loc_1400189EF
0x140018b20  mov     rcx, [rax]
0x140018b23  test    rcx, rcx
0x140018b26  jz      loc_1400189EF
0x140018b2c  mov     edx, [rax+8]
0x140018b2f  mov     rsi, rcx
0x140018b32  mov     r8, [rax+10h]
0x140018b36  mov     r9, [rax+18h]
0x140018b3a  mov     r10, [rax+20h]
0x140018b3e  mov     dil, [rax+28h]
0x140018b42  jmp     loc_1400189EB
0x140018b47  cmp     [rsp+0B8h+arg_58], 0
0x140018b4f  jnz     loc_1400189F8
0x140018b55  xor     esi, esi
0x140018b57  jmp     loc_140018A01
0x140018b5c  mov     rax, [rsp+0B8h+arg_40]
0x140018b64  mov     rbp, [rax+0D0h]
0x140018b6b  test    rbp, rbp
0x140018b6e  jz      loc_140018A12
0x140018b74  xorps   xmm0, xmm0
0x140018b77  lea     rcx, [rdi+10h]; SpinLock
0x140018b7b  xor     eax, eax
0x140018b7d  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x140018b82  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x140018b87  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x140018b8c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140018b93  nop     dword ptr [rax+rax+00h]
0x140018b98  lock inc dword ptr [rbp+0Ch]
0x140018b9c  mov     rcx, [rdi+8]; Entry
0x140018ba0  test    rcx, rcx
0x140018ba3  jz      short loc_140018BAA
0x140018ba5  call    ?RefCountedBufferRelease@CRefCountedBuffer@@QEAAXXZ; CRefCountedBuffer::RefCountedBufferRelease(void)
0x140018baa  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x140018baf  mov     [rdi+8], rbp
0x140018bb3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140018bba  nop     dword ptr [rax+rax+00h]
0x140018bbf  jmp     loc_140018A12
0x140018bc4  mov     rax, cs:DxgCoreInterface
0x140018bcb  mov     rcx, rsi
0x140018bce  mov     [rsp+0B8h+var_90], dil
0x140018bd3  mov     qword ptr [rsp+0B8h+var_98], r10
0x140018bd8  mov     rax, [rax+260h]
0x140018bdf  call    _guard_dispatch_icall
0x140018be4  test    dil, dil
0x140018be7  jnz     loc_140018A01
0x140018bed  mov     eax, [rbx+4]
0x140018bf0  test    al, 10h
0x140018bf2  jz      loc_140018ABB
0x140018bf8  lea     rdx, [r14-10h]; ListEntry
0x140018bfc  lea     rcx, [r15+30h]; ListHead
0x140018c00  call    cs:__imp_ExpInterlockedPushEntrySList
0x140018c07  nop     dword ptr [rax+rax+00h]
0x140018c0c  jmp     loc_140018ABB
0x140018c11  xor     eax, eax
0x140018c13  jmp     loc_140018A86
```
