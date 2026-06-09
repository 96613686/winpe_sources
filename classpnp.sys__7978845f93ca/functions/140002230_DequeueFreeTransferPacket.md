# DequeueFreeTransferPacket

- ea: `0x140002230`
- end: `0x140002445`
- name: `DequeueFreeTransferPacket`
- size: `533`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140001130`
- `0x140002fb0`
- `0x1400206f8`
- `0x140020ef4`
- `0x140024070`
- `0x140025134`
- `0x140059cb4`
- `0x14005d970`

## callees

- `0x140002230`
- `0x14000eee0`
- `0x14001feac`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000232d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000232d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002353`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002353`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000228f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400022b1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000228f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400022b1`
- `ntoskrnl!ExQueryDepthSList` at `0x140002274`
- `ntoskrnl!ExQueryDepthSList` at `0x140002274`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140002254`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140002254`

## pseudocode

```c
PSLIST_ENTRY __fastcall DequeueFreeTransferPacket(__int64 a1)
{
  unsigned int LockArray_high; // r15d
  _QWORD *v3; // rdi
  unsigned __int64 v4; // rbx
  __int64 CurrentNodeNumber; // rsi
  PSLIST_ENTRY v6; // rax
  int v7; // r14d
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  PSLIST_ENTRY v12; // rbp
  __int64 v13; // rdi
  int v14; // ebx
  __int64 v16; // rax
  KIRQL v17; // al
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // ecx

  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v3 = *(_QWORD **)(*(_QWORD *)(a1 + 64) + 1144LL);
  v4 = (unsigned __int64)LockArray_high << 6;
  CurrentNodeNumber = KeGetCurrentNodeNumber();
  if ( ExQueryDepthSList((PSLIST_HEADER)(v4 + v3[85]))
    && (v6 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v4 + v3[85]))) != 0
    || (v7 = CurrentNodeNumber,
        v8 = CurrentNodeNumber << 6,
        (v6 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v8 + v3[192]))) != 0) )
  {
    v12 = v6 - 1;
    v6->Next = 0;
    if ( LODWORD(v6[23].Next) == -1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v4 + v3[85] + 16));
      LODWORD(v12[24].Next) = LockArray_high;
    }
    goto LABEL_6;
  }
  v16 = NewTransferPacket(a1, v9, v10, v11);
  v12 = (PSLIST_ENTRY)v16;
  if ( !v16 )
  {
    v17 = KeAcquireSpinLockRaiseToDpc(v3 + 195);
    v18 = v3[61];
    if ( v18 )
    {
      v12 = (PSLIST_ENTRY)(v18 - 16);
      v3[61] = 0;
    }
    KeReleaseSpinLock(v3 + 195, v17);
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids);
      }
      return v12;
    }
LABEL_6:
    v13 = *((_QWORD *)&v12[19].Next + 1);
    if ( v13 )
    {
      v14 = *(_DWORD *)(v13 + 32);
      memset(*((void **)&v12[19].Next + 1), 0, (unsigned int)(40 * (v14 + 1)));
      *(_DWORD *)(v13 + 32) = v14;
    }
    return v12;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v8 + v3[192] + 16));
  _InterlockedIncrement((volatile signed __int32 *)(v4 + v3[85] + 16));
  *(_DWORD *)(v16 + 380) = v7;
  *(_DWORD *)(v16 + 384) = LockArray_high;
  v19 = v3[192];
  if ( *(_DWORD *)(v8 + v19 + 20) <= *(_DWORD *)(v8 + v19 + 16) )
    v20 = *(_DWORD *)(v8 + v19 + 16);
  else
    v20 = *(_DWORD *)(v8 + v19 + 20);
  *(_DWORD *)(v8 + v3[192] + 20) = v20;
  return v12;
}

```

## disassembly

```asm
0x140002230  push    rbx
0x140002232  push    rbp
0x140002233  push    rsi
0x140002234  push    rdi
0x140002235  push    r14
0x140002237  push    r15
0x140002239  sub     rsp, 28h
0x14000223d  mov     rax, [rcx+40h]
0x140002241  mov     rbp, rcx
0x140002244  mov     r15d, gs:1A4h
0x14000224d  mov     rdi, [rax+478h]
0x140002254  call    cs:__imp_KeGetCurrentNodeNumber
0x14000225b  nop     dword ptr [rax+rax+00h]
0x140002260  mov     rcx, [rdi+2A8h]
0x140002267  mov     ebx, r15d
0x14000226a  shl     rbx, 6
0x14000226e  add     rcx, rbx; SListHead
0x140002271  movzx   esi, ax
0x140002274  call    cs:__imp_ExQueryDepthSList
0x14000227b  nop     dword ptr [rax+rax+00h]
0x140002280  test    ax, ax
0x140002283  jz      short loc_1400022A0
0x140002285  mov     rcx, [rdi+2A8h]
0x14000228c  add     rcx, rbx; ListHead
0x14000228f  call    cs:__imp_ExpInterlockedPopEntrySList
0x140002296  nop     dword ptr [rax+rax+00h]
0x14000229b  test    rax, rax
0x14000229e  jnz     short loc_1400022C2
0x1400022a0  mov     rcx, [rdi+600h]
0x1400022a7  mov     r14, rsi
0x1400022aa  shl     rsi, 6
0x1400022ae  add     rcx, rsi; ListHead
0x1400022b1  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400022b8  nop     dword ptr [rax+rax+00h]
0x1400022bd  test    rax, rax
0x1400022c0  jz      short loc_140002312
0x1400022c2  lea     rbp, [rax-10h]
0x1400022c6  mov     qword ptr [rax], 0
0x1400022cd  cmp     dword ptr [rbp+180h], 0FFFFFFFFh
0x1400022d4  jz      loc_1400023AA
0x1400022da  mov     rdi, [rbp+138h]
0x1400022e1  test    rdi, rdi
0x1400022e4  jz      short loc_140002301
0x1400022e6  mov     ebx, [rdi+20h]
0x1400022e9  xor     edx, edx; Val
0x1400022eb  mov     rcx, rdi; void *
0x1400022ee  lea     eax, [rbx+1]
0x1400022f1  lea     r8d, [rax+rax*4]
0x1400022f5  shl     r8d, 3; Size
0x1400022f9  call    memset
0x1400022fe  mov     [rdi+20h], ebx
0x140002301  mov     rax, rbp
0x140002304  add     rsp, 28h
0x140002308  pop     r15
0x14000230a  pop     r14
0x14000230c  pop     rdi
0x14000230d  pop     rsi
0x14000230e  pop     rbp
0x14000230f  pop     rbx
0x140002310  retn
0x140002312  mov     rcx, rbp
0x140002315  call    NewTransferPacket
0x14000231a  mov     rbp, rax
0x14000231d  test    rax, rax
0x140002320  jnz     loc_1400023C2
0x140002326  lea     rcx, [rdi+618h]; SpinLock
0x14000232d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002334  nop     dword ptr [rax+rax+00h]
0x140002339  mov     rcx, [rdi+1E8h]
0x140002340  test    rcx, rcx
0x140002343  jnz     loc_140002431
0x140002349  movzx   edx, al; NewIrql
0x14000234c  lea     rcx, [rdi+618h]; SpinLock
0x140002353  call    cs:__imp_KeReleaseSpinLock
0x14000235a  nop     dword ptr [rax+rax+00h]
0x14000235f  test    rbp, rbp
0x140002362  jnz     loc_1400022DA
0x140002368  mov     rcx, cs:WPP_GLOBAL_Control
0x14000236f  lea     rax, WPP_GLOBAL_Control
0x140002376  cmp     rcx, rax
0x140002379  jz      short loc_140002301
0x14000237b  mov     eax, [rcx+2Ch]
0x14000237e  test    al, 8
0x140002380  jz      loc_140002301
0x140002386  cmp     byte ptr [rcx+29h], 3
0x14000238a  jb      loc_140002301
0x140002390  mov     rcx, [rcx+18h]
0x140002394  lea     r8, WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids
0x14000239b  mov     edx, 10h
0x1400023a0  call    WPP_SF_
0x1400023a5  jmp     loc_140002301
0x1400023aa  mov     rax, [rdi+2A8h]
0x1400023b1  lock inc dword ptr [rbx+rax+10h]
0x1400023b6  mov     [rbp+180h], r15d
0x1400023bd  jmp     loc_1400022DA
0x1400023c2  mov     rcx, [rdi+600h]
0x1400023c9  lock inc dword ptr [rsi+rcx+10h]
0x1400023ce  mov     rcx, [rdi+2A8h]
0x1400023d5  lock inc dword ptr [rbx+rcx+10h]
0x1400023da  mov     [rax+17Ch], r14d
0x1400023e1  mov     [rax+180h], r15d
0x1400023e8  mov     rcx, [rdi+600h]
0x1400023ef  mov     r8d, [rsi+rcx+14h]
0x1400023f4  mov     rcx, [rdi+600h]
0x1400023fb  mov     edx, [rsi+rcx+10h]
0x1400023ff  mov     rax, [rdi+600h]
0x140002406  cmp     r8d, edx
0x140002409  jbe     short loc_14000242B
0x14000240b  mov     ecx, [rsi+rax+14h]
0x14000240f  mov     rax, [rdi+600h]
0x140002416  mov     [rsi+rax+14h], ecx
0x14000241a  mov     rax, rbp
0x14000241d  add     rsp, 28h
0x140002421  pop     r15
0x140002423  pop     r14
0x140002425  pop     rdi
0x140002426  pop     rsi
0x140002427  pop     rbp
0x140002428  pop     rbx
0x140002429  retn
0x14000242b  mov     ecx, [rsi+rax+10h]
0x14000242f  jmp     short loc_14000240F
0x140002431  lea     rbp, [rcx-10h]
0x140002435  mov     qword ptr [rdi+1E8h], 0
0x140002440  jmp     loc_140002349
```
