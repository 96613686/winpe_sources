# UMRxCreateAsyncEngineContext

- ea: `0x140027210`
- end: `0x1400273e7`
- name: `UMRxCreateAsyncEngineContext`
- size: `471`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400269d8`

## callees

- `0x14000163c`
- `0x1400017e4`
- `0x140006c00`
- `0x140027210`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002723d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027279`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400272dc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002723d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027279`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400272dc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002737d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002737d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400273bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400273bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400272b1`
- `ntoskrnl!ExAllocatePool2` at `0x1400272b1`
- `ntoskrnl!KeInitializeEvent` at `0x14002735d`
- `ntoskrnl!KeInitializeEvent` at `0x14002735d`

## pseudocode

```c
__int64 __fastcall UMRxCreateAsyncEngineContext(__int64 a1)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  __int64 Pool2; // rax
  __int64 v7; // rbx
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 v11; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v2, 30, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v5 = PsGetCurrentThreadId();
      WPP_SF_qq(v4, 31, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v5, a1);
    }
  }
  Pool2 = ExAllocatePool2(66, 768, 1146504056);
  v7 = Pool2;
  if ( Pool2 )
  {
    memset((void *)(Pool2 + 4), 0, 0x2FCu);
    *(_DWORD *)v7 = 50392528;
    _InterlockedAdd((volatile signed __int32 *)(v7 + 4), 1u);
    _InterlockedAdd((volatile signed __int32 *)(a1 + 4), 1u);
    *(_QWORD *)(v7 + 80) = a1;
    *(_DWORD *)(v7 + 224) = 0;
    *(_DWORD *)(v7 + 64) = 0;
    *(_QWORD *)(v7 + 88) = *(_QWORD *)(a1 + 208);
    *(_QWORD *)(a1 + 208) = v7;
    KeInitializeEvent((PRKEVENT)(v7 + 448), SynchronizationEvent, 0);
    if ( (unsigned __int8)(*(_BYTE *)(a1 + 32) - 3) > 1u )
    {
      ExAcquireResourceExclusiveLite(&UMRxAsyncEngineContextListLock, 1u);
      v11 = UMRxAsyncEngineContextList;
      if ( *(__int64 **)(UMRxAsyncEngineContextList + 8) != &UMRxAsyncEngineContextList )
        __fastfail(3u);
      *(_QWORD *)(v7 + 32) = UMRxAsyncEngineContextList;
      *(_QWORD *)(v7 + 40) = &UMRxAsyncEngineContextList;
      *(_QWORD *)(v11 + 8) = v7 + 32;
      UMRxAsyncEngineContextList = v7 + 32;
      ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
      *(_QWORD *)(v7 + 72) = MEMORY[0xFFFFF78000000320];
    }
    return v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      WPP_SF_q(v8, 32, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v9);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140027210  push    rbx
0x140027212  push    rsi
0x140027213  push    rdi
0x140027214  push    r14
0x140027216  sub     rsp, 38h
0x14002721a  mov     rdi, rcx
0x14002721d  mov     rbx, cs:WPP_GLOBAL_Control
0x140027224  lea     rsi, WPP_GLOBAL_Control
0x14002722b  cmp     rbx, rsi
0x14002722e  jz      short loc_1400272A1
0x140027230  test    dword ptr [rbx+2Ch], 800h
0x140027237  jz      short loc_140027260
0x140027239  mov     rbx, [rbx+18h]
0x14002723d  call    cs:__imp_PsGetCurrentThreadId
0x140027244  nop     dword ptr [rax+rax+00h]
0x140027249  mov     edx, 1Eh
0x14002724e  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027255  mov     r9, rax
0x140027258  mov     rcx, rbx
0x14002725b  call    WPP_SF_q
0x140027260  mov     rbx, cs:WPP_GLOBAL_Control
0x140027267  cmp     rbx, rsi
0x14002726a  jz      short loc_1400272A1
0x14002726c  test    dword ptr [rbx+2Ch], 200h
0x140027273  jz      short loc_1400272A1
0x140027275  mov     rbx, [rbx+18h]
0x140027279  call    cs:__imp_PsGetCurrentThreadId
0x140027280  nop     dword ptr [rax+rax+00h]
0x140027285  mov     edx, 1Fh
0x14002728a  mov     [rsp+58h+var_38], rdi
0x14002728f  mov     r9, rax
0x140027292  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027299  mov     rcx, rbx
0x14002729c  call    WPP_SF_qq
0x1400272a1  mov     edx, 300h
0x1400272a6  mov     ecx, 42h ; 'B'
0x1400272ab  mov     r8d, 44564378h
0x1400272b1  call    cs:__imp_ExAllocatePool2
0x1400272b8  nop     dword ptr [rax+rax+00h]
0x1400272bd  mov     rbx, rax
0x1400272c0  test    rax, rax
0x1400272c3  jnz     short loc_140027306
0x1400272c5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400272cc  cmp     rbx, rsi
0x1400272cf  jz      short loc_1400272FF
0x1400272d1  mov     eax, [rbx+2Ch]
0x1400272d4  test    al, al
0x1400272d6  jns     short loc_1400272FF
0x1400272d8  mov     rbx, [rbx+18h]
0x1400272dc  call    cs:__imp_PsGetCurrentThreadId
0x1400272e3  nop     dword ptr [rax+rax+00h]
0x1400272e8  mov     edx, 20h ; ' '
0x1400272ed  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400272f4  mov     r9, rax
0x1400272f7  mov     rcx, rbx
0x1400272fa  call    WPP_SF_q
0x1400272ff  xor     eax, eax
0x140027301  jmp     loc_1400273DC
0x140027306  lea     rcx, [rax+4]; void *
0x14002730a  xor     edx, edx; Val
0x14002730c  mov     r8d, 2FCh; Size
0x140027312  call    memset
0x140027317  mov     dword ptr [rbx], 300EDD0h
0x14002731d  mov     esi, 1
0x140027322  lock add [rbx+4], esi
0x140027326  lock add [rdi+4], esi
0x14002732a  mov     [rbx+50h], rdi
0x14002732e  lea     rcx, [rbx+1C0h]; Event
0x140027335  mov     dword ptr [rbx+0E0h], 0
0x14002733f  xor     r8d, r8d; State
0x140027342  mov     dword ptr [rbx+40h], 0
0x140027349  mov     edx, esi; Type
0x14002734b  mov     rax, [rdi+0D0h]
0x140027352  mov     [rbx+58h], rax
0x140027356  mov     [rdi+0D0h], rbx
0x14002735d  call    cs:__imp_KeInitializeEvent
0x140027364  nop     dword ptr [rax+rax+00h]
0x140027369  mov     al, [rdi+20h]
0x14002736c  sub     al, 3
0x14002736e  cmp     al, sil
0x140027371  jbe     short loc_1400273D9
0x140027373  mov     dl, sil; Wait
0x140027376  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x14002737d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140027384  nop     dword ptr [rax+rax+00h]
0x140027389  mov     rdx, cs:UMRxAsyncEngineContextList
0x140027390  lea     r8, UMRxAsyncEngineContextList
0x140027397  cmp     [rdx+8], r8
0x14002739b  jz      short loc_1400273A2
0x14002739d  lea     ecx, [rsi+2]
0x1400273a0  int     29h; Win8: RtlFailFast(ecx)
0x1400273a2  lea     rax, [rbx+20h]
0x1400273a6  mov     [rax], rdx
0x1400273a9  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x1400273b0  mov     [rax+8], r8
0x1400273b4  mov     [rdx+8], rax
0x1400273b8  mov     cs:UMRxAsyncEngineContextList, rax
0x1400273bf  call    cs:__imp_ExReleaseResourceLite
0x1400273c6  nop     dword ptr [rax+rax+00h]
0x1400273cb  mov     rax, ds:0FFFFF78000000320h
0x1400273d5  mov     [rbx+48h], rax
0x1400273d9  mov     rax, rbx
0x1400273dc  add     rsp, 38h
0x1400273e0  pop     r14
0x1400273e2  pop     rdi
0x1400273e3  pop     rsi
0x1400273e4  pop     rbx
0x1400273e5  retn
```
