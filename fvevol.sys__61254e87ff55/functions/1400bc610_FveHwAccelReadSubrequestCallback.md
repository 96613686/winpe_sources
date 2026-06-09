# FveHwAccelReadSubrequestCallback

- ea: `0x1400bc610`
- end: `0x1400bc8f6`
- name: `FveHwAccelReadSubrequestCallback`
- size: `742`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140006730`
- `0x140006b80`
- `0x1400070ac`
- `0x1400bc610`
- `0x1400d4a70`
- `0x1400d55d0`
- `0x1400d66b0`
- `0x1400d83c0`
- `0x1400d87d0`
- `0x1400d95c0`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x1400bc708`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400bc81d`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400bc708`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400bc81d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc85d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc880`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc85d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc880`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc73c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc73c`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc64e`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc6d8`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc777`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc7ad`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc64e`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc6d8`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc777`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc7ad`
- `ext-ms-win-accel-api-km-l1-1-1!AccelGetStatusFromCompletionRecord` at `0x1400bc673`
- `ext-ms-win-accel-api-km-l1-1-1!AccelGetStatusFromCompletionRecord` at `0x1400bc673`

## pseudocode

```c
__int64 __fastcall FveHwAccelReadSubrequestCallback(__int64 a1, __int64 *a2)
{
  bool v3; // zf
  ULONG_PTR v4; // rbx
  __int64 v5; // rbp
  ULONG_PTR v6; // rdi
  __int64 v7; // r14
  __int64 v8; // rcx
  int v9; // edx
  signed __int32 v10; // eax
  __int64 v11; // rcx
  __int16 v12; // si
  __int64 v13; // rcx
  KIRQL v14; // r14
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  ULONG v17; // esi
  __int64 v18; // rcx
  __int16 v19; // si
  __int64 v20; // rdx
  char v22; // al
  ULONG pulResult; // [rsp+68h] [rbp+10h] BYREF
  ULONGLONG pullResult; // [rsp+70h] [rbp+18h] BYREF

  v3 = *((_DWORD *)a2 + 30) == 3;
  pullResult = 0;
  pulResult = 0;
  if ( !v3 )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  v4 = a2[16];
  v5 = *a2;
  v6 = *(_QWORD *)(v4 + 16);
  v7 = *(_QWORD *)(v4 + 40);
  if ( (a2[14] & 2) == 0 )
    *((_DWORD *)a2 + 29) = AccelGetStatusFromCompletionRecord();
  v8 = *(_QWORD *)(v5 + 8);
  if ( (*(_DWORD *)(v8 + 9928) & 0x2000000) != 0 || (unsigned __int8)FveSimulateResourceStress(v8) )
  {
    *((_DWORD *)a2 + 29) = -1073741823;
    goto LABEL_27;
  }
  if ( v9 < 0 )
  {
LABEL_27:
    v22 = *(_BYTE *)(v4 + 144);
    *(_BYTE *)(v4 + 136) |= 0x40u;
    *(_BYTE *)(v4 + 144) = v22 & 0xF3 | 8;
    FveSetSubrequestState(*(_QWORD *)(v5 + 8), v4, 30);
    return FveCryptoWorkQueue(*(_QWORD *)(v5 + 8), *(_QWORD *)(v4 + 32), v6, 0);
  }
  v10 = _InterlockedDecrement((volatile signed __int32 *)(v4 + 132));
  if ( v10 )
    KeBugCheckEx(0x120u, 0xBu, v4, 0, v10);
  *(_QWORD *)(v4 + 64) = MEMORY[0xFFFFF78000000008];
  v11 = *(_QWORD *)(v7 + 8);
  v12 = *(_WORD *)(v11 + 8);
  if ( (*(_BYTE *)(v11 + 10) & 0x20) != 0 )
    MmUnmapLockedPages(*(PVOID *)(v11 + 24), *(PMDL *)(v7 + 8));
  v13 = *(_QWORD *)(v7 + 8);
  *(_QWORD *)v13 = 0;
  *(_DWORD *)(v13 + 8) = 48;
  *(_QWORD *)(v13 + 32) = 0;
  *(_QWORD *)(v13 + 40) = 0;
  *(_WORD *)(*(_QWORD *)(v7 + 8) + 8LL) = v12;
  v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 104));
  v15 = RtlULongLongSub(*(_QWORD *)v4, *(_QWORD *)(v6 + 64), &pullResult);
  if ( v15 < 0 )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, v15);
  v16 = RtlULongLongToULong(pullResult, &pulResult);
  if ( v16 < 0 )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, v16);
  v17 = pulResult;
  MergeStatusIntoControl(v6, *(unsigned int *)(v4 + 128), pulResult);
  if ( *(int *)(v4 + 128) < 0 && v17 < *(_DWORD *)(v6 + 124) )
    *(_DWORD *)(v6 + 124) = v17;
  if ( *(_DWORD *)(v6 + 120) && *(int *)(v6 + 128) >= 0 && *(_DWORD *)(v6 + 124) == *(_DWORD *)(v6 + 72) )
  {
    v18 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
    v19 = *(_WORD *)(v18 + 8);
    if ( (*(_BYTE *)(v18 + 10) & 0x30) == 0x30 )
      MmUnmapLockedPages(*(PVOID *)(v18 + 24), (PMDL)v18);
    v20 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
    *(_QWORD *)v20 = 0;
    *(_DWORD *)(v20 + 8) = 48;
    *(_QWORD *)(v20 + 32) = 0;
    *(_QWORD *)(v20 + 40) = 0;
    *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL) + 8LL) = v19;
    InitializeNextReadSubrequest(v6, v4);
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 104), v14);
    *(_BYTE *)(v4 + 144) &= 0xFCu;
    return ReadIssue(v4);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 104), v14);
    return FinishPrimaryRequestIfLastSubrequest(v6);
  }
}

```

## disassembly

```asm
0x1400bc610  mov     rax, rsp
0x1400bc613  mov     [rax+8], rbx
0x1400bc617  mov     [rax+20h], rbp
0x1400bc61b  push    rsi
0x1400bc61c  push    rdi
0x1400bc61d  push    r12
0x1400bc61f  push    r14
0x1400bc621  push    r15
0x1400bc623  sub     rsp, 30h
0x1400bc627  xor     r15d, r15d
0x1400bc62a  mov     rsi, rdx
0x1400bc62d  cmp     dword ptr [rdx+78h], 3
0x1400bc631  mov     [rax+18h], r15
0x1400bc635  mov     [rax+10h], r15d
0x1400bc639  jz      short loc_1400BC65B
0x1400bc63b  xor     r9d, r9d; BugCheckParameter3
0x1400bc63e  mov     [rax-38h], r15
0x1400bc642  xor     r8d, r8d; BugCheckParameter2
0x1400bc645  lea     edx, [r15+0Ch]; BugCheckParameter1
0x1400bc649  mov     ecx, 120h; BugCheckCode
0x1400bc64e  call    cs:__imp_KeBugCheckEx
0x1400bc65b  test    byte ptr [rdx+70h], 2
0x1400bc65f  mov     rbx, [rdx+80h]
0x1400bc666  mov     rbp, [rdx]
0x1400bc669  mov     rdi, [rbx+10h]
0x1400bc66d  mov     r14, [rbx+28h]
0x1400bc671  jnz     short loc_1400BC686
0x1400bc673  call    cs:__imp_AccelGetStatusFromCompletionRecord
0x1400bc67a  nop     dword ptr [rax+rax+00h]
0x1400bc67f  mov     edx, eax
0x1400bc681  mov     [rsi+74h], eax
0x1400bc684  jmp     short loc_1400BC689
0x1400bc686  mov     edx, [rdx+74h]
0x1400bc689  mov     rcx, [rbp+8]
0x1400bc68d  test    dword ptr [rcx+26C8h], 2000000h
0x1400bc697  jnz     loc_1400BC896
0x1400bc69d  call    FveSimulateResourceStress
0x1400bc6a2  test    al, al
0x1400bc6a4  jnz     loc_1400BC896
0x1400bc6aa  test    edx, edx
0x1400bc6ac  js      loc_1400BC89D
0x1400bc6b2  or      eax, 0FFFFFFFFh
0x1400bc6b5  lock xadd [rbx+84h], eax
0x1400bc6bd  sub     eax, 1
0x1400bc6c0  jz      short loc_1400BC6E5
0x1400bc6c2  xor     r9d, r9d; BugCheckParameter3
0x1400bc6c5  cdqe
0x1400bc6c7  mov     r8, rbx; BugCheckParameter2
0x1400bc6ca  mov     [rsp+58h+BugCheckParameter4], rax; BugCheckParameter4
0x1400bc6cf  mov     ecx, 120h; BugCheckCode
0x1400bc6d4  lea     edx, [r9+0Bh]; BugCheckParameter1
0x1400bc6d8  call    cs:__imp_KeBugCheckEx
0x1400bc6e5  mov     rax, ds:0FFFFF78000000008h
0x1400bc6ef  mov     [rbx+40h], rax
0x1400bc6f3  mov     rcx, [r14+8]
0x1400bc6f7  test    byte ptr [rcx+0Ah], 20h
0x1400bc6fb  movzx   esi, word ptr [rcx+8]
0x1400bc6ff  jz      short loc_1400BC714
0x1400bc701  mov     rdx, rcx; MemoryDescriptorList
0x1400bc704  mov     rcx, [rcx+18h]; BaseAddress
0x1400bc708  call    cs:__imp_MmUnmapLockedPages
0x1400bc70f  nop     dword ptr [rax+rax+00h]
0x1400bc714  mov     rcx, [r14+8]
0x1400bc718  lea     rbp, [rdi+68h]
0x1400bc71c  mov     r12d, 30h ; '0'
0x1400bc722  mov     [rcx], r15
0x1400bc725  mov     [rcx+8], r12d
0x1400bc729  mov     [rcx+20h], r15
0x1400bc72d  mov     [rcx+28h], r15
0x1400bc731  mov     rcx, rbp; SpinLock
0x1400bc734  mov     rax, [r14+8]
0x1400bc738  mov     [rax+8], si
0x1400bc73c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400bc743  nop     dword ptr [rax+rax+00h]
0x1400bc748  mov     rdx, [rdi+40h]; ullSubtrahend
0x1400bc74c  lea     r8, [rsp+58h+pullResult]; pullResult
0x1400bc751  mov     rcx, [rbx]; ullMinuend
0x1400bc754  mov     r14b, al
0x1400bc757  call    RtlULongLongSub
0x1400bc75c  test    eax, eax
0x1400bc75e  jns     short loc_1400BC784
0x1400bc760  cdqe
0x1400bc762  lea     edx, [r12-24h]; BugCheckParameter1
0x1400bc767  xor     r9d, r9d; BugCheckParameter3
0x1400bc76a  mov     [rsp+58h+BugCheckParameter4], rax; BugCheckParameter4
0x1400bc76f  xor     r8d, r8d; BugCheckParameter2
0x1400bc772  mov     ecx, 120h; BugCheckCode
0x1400bc777  call    cs:__imp_KeBugCheckEx
0x1400bc784  mov     rcx, [rsp+58h+pullResult]; ullOperand
0x1400bc789  lea     rdx, [rsp+58h+pulResult]; pulResult
0x1400bc78e  call    RtlULongLongToULong
0x1400bc793  test    eax, eax
0x1400bc795  jns     short loc_1400BC7BA
0x1400bc797  xor     r9d, r9d; BugCheckParameter3
0x1400bc79a  cdqe
0x1400bc79c  xor     r8d, r8d; BugCheckParameter2
0x1400bc79f  mov     [rsp+58h+BugCheckParameter4], rax; BugCheckParameter4
0x1400bc7a4  mov     ecx, 120h; BugCheckCode
0x1400bc7a9  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400bc7ad  call    cs:__imp_KeBugCheckEx
0x1400bc7ba  mov     esi, [rsp+58h+pulResult]
0x1400bc7be  mov     rcx, rdi
0x1400bc7c1  mov     edx, [rbx+80h]
0x1400bc7c7  mov     r8d, esi
0x1400bc7ca  call    MergeStatusIntoControl
0x1400bc7cf  cmp     [rbx+80h], r15d
0x1400bc7d6  jge     short loc_1400BC7E0
0x1400bc7d8  cmp     esi, [rdi+7Ch]
0x1400bc7db  jnb     short loc_1400BC7E0
0x1400bc7dd  mov     [rdi+7Ch], esi
0x1400bc7e0  cmp     [rdi+78h], r15d
0x1400bc7e4  jz      loc_1400BC87A
0x1400bc7ea  cmp     [rdi+80h], r15d
0x1400bc7f1  jl      loc_1400BC87A
0x1400bc7f7  mov     eax, [rdi+48h]
0x1400bc7fa  cmp     [rdi+7Ch], eax
0x1400bc7fd  jnz     short loc_1400BC87A
0x1400bc7ff  mov     rax, [rbx+28h]
0x1400bc803  mov     rcx, [rax+8]
0x1400bc807  mov     al, [rcx+0Ah]
0x1400bc80a  movzx   esi, word ptr [rcx+8]
0x1400bc80e  and     al, r12b
0x1400bc811  cmp     al, r12b
0x1400bc814  jnz     short loc_1400BC829
0x1400bc816  mov     rdx, rcx; MemoryDescriptorList
0x1400bc819  mov     rcx, [rcx+18h]; BaseAddress
0x1400bc81d  call    cs:__imp_MmUnmapLockedPages
0x1400bc824  nop     dword ptr [rax+rax+00h]
0x1400bc829  mov     rax, [rbx+28h]
0x1400bc82d  mov     rcx, rdi
0x1400bc830  mov     rdx, [rax+8]
0x1400bc834  mov     [rdx], r15
0x1400bc837  mov     [rdx+8], r12d
0x1400bc83b  mov     [rdx+20h], r15
0x1400bc83f  mov     [rdx+28h], r15
0x1400bc843  mov     rax, [rbx+28h]
0x1400bc847  mov     rdx, [rax+8]
0x1400bc84b  mov     [rdx+8], si
0x1400bc84f  mov     rdx, rbx
0x1400bc852  call    InitializeNextReadSubrequest
0x1400bc857  mov     dl, r14b; NewIrql
0x1400bc85a  mov     rcx, rbp; SpinLock
0x1400bc85d  call    cs:__imp_KeReleaseSpinLock
0x1400bc864  nop     dword ptr [rax+rax+00h]
0x1400bc869  and     byte ptr [rbx+90h], 0FCh
0x1400bc870  mov     rcx, rbx
0x1400bc873  call    ReadIssue
0x1400bc878  jmp     short loc_1400BC8DE
0x1400bc87a  mov     dl, r14b; NewIrql
0x1400bc87d  mov     rcx, rbp; SpinLock
0x1400bc880  call    cs:__imp_KeReleaseSpinLock
0x1400bc887  nop     dword ptr [rax+rax+00h]
0x1400bc88c  mov     rcx, rdi; BugCheckParameter2
0x1400bc88f  call    FinishPrimaryRequestIfLastSubrequest
0x1400bc894  jmp     short loc_1400BC8DE
0x1400bc896  mov     dword ptr [rsi+74h], 0C0000001h
0x1400bc89d  mov     al, [rbx+90h]
0x1400bc8a3  mov     r8d, 1Eh
0x1400bc8a9  or      byte ptr [rbx+88h], 40h
0x1400bc8b0  and     al, 0FBh
0x1400bc8b2  or      al, 8
0x1400bc8b4  mov     byte ptr [rsp+58h+BugCheckParameter4], r15b
0x1400bc8b9  mov     [rbx+90h], al
0x1400bc8bf  mov     rdx, rbx
0x1400bc8c2  mov     rcx, [rbp+8]
0x1400bc8c6  call    FveSetSubrequestState
0x1400bc8cb  mov     rdx, [rbx+20h]
0x1400bc8cf  xor     r9d, r9d
0x1400bc8d2  mov     rcx, [rbp+8]
0x1400bc8d6  mov     r8, rdi
0x1400bc8d9  call    FveCryptoWorkQueue
0x1400bc8de  mov     rbx, [rsp+58h+arg_0]
0x1400bc8e3  mov     rbp, [rsp+58h+arg_18]
0x1400bc8e8  add     rsp, 30h
0x1400bc8ec  pop     r15
0x1400bc8ee  pop     r14
0x1400bc8f0  pop     r12
0x1400bc8f2  pop     rdi
0x1400bc8f3  pop     rsi
0x1400bc8f4  retn
```
