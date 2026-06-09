# UMRxEnqueueUserModeCallUp

- ea: `0x1400273f0`
- end: `0x140027650`
- name: `UMRxEnqueueUserModeCallUp`
- size: `608`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400287f4`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x1400273f0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140027432`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002746a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400274ac`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027503`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027587`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002761d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027432`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002746a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400274ac`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027503`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027587`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002761d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400274d7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002755e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400274d7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002755e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002752d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140027546`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400275b1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400275ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002752d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140027546`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400275b1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400275ce`
- `ntoskrnl!KeInsertQueue` at `0x1400275f3`
- `ntoskrnl!KeInsertQueue` at `0x1400275f3`

## pseudocode

```c
__int64 __fastcall UMRxEnqueueUserModeCallUp(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v5; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v7; // rbx
  HANDLE v8; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 v14; // rbx
  HANDLE v15; // rax
  __int64 v16; // rbx
  HANDLE v17; // rax

  v2 = *(_QWORD *)(a2 + 80);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v5, 75, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
      {
        v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v8 = PsGetCurrentThreadId();
        WPP_SF_qqq(v7, 76, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v8, a1, a2);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
      {
        v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v10 = PsGetCurrentThreadId();
        WPP_SF_q(v9, 77, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v10);
      }
    }
  }
  ExAcquireResourceExclusiveLite((PERESOURCE)(v2 + 1456), 1u);
  if ( *(_BYTE *)(v2 + 1616) )
  {
    ExReleaseResourceLite((PERESOURCE)(v2 + 1456));
    ExAcquireResourceExclusiveLite(&UMRxAsyncEngineContextListLock, 1u);
    if ( *(_DWORD *)(a1 + 48) == 3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
      {
        v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v15 = PsGetCurrentThreadId();
        WPP_SF_qD(v14, 79, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v15, -1073741536);
      }
      ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
      return 3221225760LL;
    }
    else
    {
      *(_DWORD *)(a1 + 48) = 1;
      ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
      _InterlockedIncrement((volatile signed __int32 *)(v2 + 1612));
      KeInsertQueue((PRKQUEUE)(v2 + 1392), (PLIST_ENTRY)(a1 + 360));
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
      {
        v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v17 = PsGetCurrentThreadId();
        WPP_SF_qD(v16, 80, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v17, 259);
      }
      return 259;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_qD(v11, 78, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v12, -1073741573);
    }
    ExReleaseResourceLite((PERESOURCE)(v2 + 1456));
    return 3221225723LL;
  }
}

```

## disassembly

```asm
0x1400273f0  push    rbx
0x1400273f2  push    rbp
0x1400273f3  push    rsi
0x1400273f4  push    rdi
0x1400273f5  push    r14
0x1400273f7  push    r15
0x1400273f9  sub     rsp, 38h
0x1400273fd  mov     rsi, [rdx+50h]
0x140027401  mov     rdi, rdx
0x140027404  mov     rbp, rcx
0x140027407  mov     rbx, cs:WPP_GLOBAL_Control
0x14002740e  lea     r14, WPP_GLOBAL_Control
0x140027415  lea     r15, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x14002741c  cmp     rbx, r14
0x14002741f  jz      loc_1400274CB
0x140027425  test    dword ptr [rbx+2Ch], 800h
0x14002742c  jz      short loc_140027451
0x14002742e  mov     rbx, [rbx+18h]
0x140027432  call    cs:__imp_PsGetCurrentThreadId
0x140027439  nop     dword ptr [rax+rax+00h]
0x14002743e  mov     edx, 4Bh ; 'K'
0x140027443  mov     r8, r15
0x140027446  mov     r9, rax
0x140027449  mov     rcx, rbx
0x14002744c  call    WPP_SF_q
0x140027451  mov     rbx, cs:WPP_GLOBAL_Control
0x140027458  cmp     rbx, r14
0x14002745b  jz      short loc_1400274CB
0x14002745d  test    dword ptr [rbx+2Ch], 200h
0x140027464  jz      short loc_140027493
0x140027466  mov     rbx, [rbx+18h]
0x14002746a  call    cs:__imp_PsGetCurrentThreadId
0x140027471  nop     dword ptr [rax+rax+00h]
0x140027476  mov     edx, 4Ch ; 'L'
0x14002747b  mov     [rsp+68h+var_40], rdi
0x140027480  mov     r9, rax
0x140027483  mov     [rsp+68h+var_48], rbp
0x140027488  mov     r8, r15
0x14002748b  mov     rcx, rbx
0x14002748e  call    WPP_SF_qqq
0x140027493  mov     rbx, cs:WPP_GLOBAL_Control
0x14002749a  cmp     rbx, r14
0x14002749d  jz      short loc_1400274CB
0x14002749f  test    dword ptr [rbx+2Ch], 400h
0x1400274a6  jz      short loc_1400274CB
0x1400274a8  mov     rbx, [rbx+18h]
0x1400274ac  call    cs:__imp_PsGetCurrentThreadId
0x1400274b3  nop     dword ptr [rax+rax+00h]
0x1400274b8  mov     edx, 4Dh ; 'M'
0x1400274bd  mov     r8, r15
0x1400274c0  mov     r9, rax
0x1400274c3  mov     rcx, rbx
0x1400274c6  call    WPP_SF_q
0x1400274cb  lea     rdi, [rsi+5B0h]
0x1400274d2  mov     dl, 1; Wait
0x1400274d4  mov     rcx, rdi; Resource
0x1400274d7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400274de  nop     dword ptr [rax+rax+00h]
0x1400274e3  cmp     byte ptr [rsi+650h], 0
0x1400274ea  jnz     short loc_140027543
0x1400274ec  mov     rbx, cs:WPP_GLOBAL_Control
0x1400274f3  cmp     rbx, r14
0x1400274f6  jz      short loc_14002752A
0x1400274f8  mov     eax, [rbx+2Ch]
0x1400274fb  test    al, al
0x1400274fd  jns     short loc_14002752A
0x1400274ff  mov     rbx, [rbx+18h]
0x140027503  call    cs:__imp_PsGetCurrentThreadId
0x14002750a  nop     dword ptr [rax+rax+00h]
0x14002750f  mov     edx, 4Eh ; 'N'
0x140027514  mov     dword ptr [rsp+68h+var_48], 0C00000FBh
0x14002751c  mov     r9, rax
0x14002751f  mov     r8, r15
0x140027522  mov     rcx, rbx
0x140027525  call    WPP_SF_qD
0x14002752a  mov     rcx, rdi; Resource
0x14002752d  call    cs:__imp_ExReleaseResourceLite
0x140027534  nop     dword ptr [rax+rax+00h]
0x140027539  mov     eax, 0C00000FBh
0x14002753e  jmp     loc_140027642
0x140027543  mov     rcx, rdi; Resource
0x140027546  call    cs:__imp_ExReleaseResourceLite
0x14002754d  nop     dword ptr [rax+rax+00h]
0x140027552  lea     rdi, UMRxAsyncEngineContextListLock
0x140027559  mov     dl, 1; Wait
0x14002755b  mov     rcx, rdi; Resource
0x14002755e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140027565  nop     dword ptr [rax+rax+00h]
0x14002756a  cmp     dword ptr [rbp+30h], 3
0x14002756e  jnz     short loc_1400275C4
0x140027570  mov     rbx, cs:WPP_GLOBAL_Control
0x140027577  cmp     rbx, r14
0x14002757a  jz      short loc_1400275AE
0x14002757c  mov     eax, [rbx+2Ch]
0x14002757f  test    al, al
0x140027581  jns     short loc_1400275AE
0x140027583  mov     rbx, [rbx+18h]
0x140027587  call    cs:__imp_PsGetCurrentThreadId
0x14002758e  nop     dword ptr [rax+rax+00h]
0x140027593  mov     edx, 4Fh ; 'O'
0x140027598  mov     dword ptr [rsp+68h+var_48], 0C0000120h
0x1400275a0  mov     r9, rax
0x1400275a3  mov     r8, r15
0x1400275a6  mov     rcx, rbx
0x1400275a9  call    WPP_SF_qD
0x1400275ae  mov     rcx, rdi; Resource
0x1400275b1  call    cs:__imp_ExReleaseResourceLite
0x1400275b8  nop     dword ptr [rax+rax+00h]
0x1400275bd  mov     eax, 0C0000120h
0x1400275c2  jmp     short loc_140027642
0x1400275c4  mov     rcx, rdi; Resource
0x1400275c7  mov     dword ptr [rbp+30h], 1
0x1400275ce  call    cs:__imp_ExReleaseResourceLite
0x1400275d5  nop     dword ptr [rax+rax+00h]
0x1400275da  lock inc dword ptr [rbp+4]
0x1400275de  lock inc dword ptr [rsi+64Ch]
0x1400275e5  lea     rdx, [rbp+168h]; Entry
0x1400275ec  lea     rcx, [rsi+570h]; Queue
0x1400275f3  call    cs:__imp_KeInsertQueue
0x1400275fa  nop     dword ptr [rax+rax+00h]
0x1400275ff  mov     rbx, cs:WPP_GLOBAL_Control
0x140027606  mov     edi, 103h
0x14002760b  cmp     rbx, r14
0x14002760e  jz      short loc_140027640
0x140027610  test    dword ptr [rbx+2Ch], 800h
0x140027617  jz      short loc_140027640
0x140027619  mov     rbx, [rbx+18h]
0x14002761d  call    cs:__imp_PsGetCurrentThreadId
0x140027624  nop     dword ptr [rax+rax+00h]
0x140027629  mov     edx, 50h ; 'P'
0x14002762e  mov     dword ptr [rsp+68h+var_48], edi
0x140027632  mov     r9, rax
0x140027635  mov     r8, r15
0x140027638  mov     rcx, rbx
0x14002763b  call    WPP_SF_qD
0x140027640  mov     eax, edi
0x140027642  add     rsp, 38h
0x140027646  pop     r15
0x140027648  pop     r14
0x14002764a  pop     rdi
0x14002764b  pop     rsi
0x14002764c  pop     rbp
0x14002764d  pop     rbx
0x14002764e  retn
```
