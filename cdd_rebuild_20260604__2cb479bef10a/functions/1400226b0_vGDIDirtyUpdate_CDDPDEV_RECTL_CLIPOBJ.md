# vGDIDirtyUpdate(CDDPDEV *,_RECTL *,_CLIPOBJ *)

- ea: `0x1400226b0`
- end: `0x140022925`
- name: `?vGDIDirtyUpdate@@YAXPEAUCDDPDEV@@PEAU_RECTL@@PEAU_CLIPOBJ@@@Z`
- size: `629`
- prototype: `void __fastcall(struct CDDPDEV *, struct _RECTL *, struct _CLIPOBJ *)`
- caller_count: `12`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000919c`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`

## callees

- `0x140002470`
- `0x14000fbb4`
- `0x140010670`
- `0x1400226b0`
- `0x14002292c`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140022767`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140022767`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002274b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140022840`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002274b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140022840`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022885`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022885`
- `ntoskrnl!KeSetEvent` at `0x1400228f4`
- `ntoskrnl!KeSetEvent` at `0x1400228f4`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400228b1`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400228b1`
- `watchdog!WdLogSingleEntry0` at `0x14002289a`
- `watchdog!WdLogSingleEntry0` at `0x14002289a`
- `WIN32K!CddEngEqualRgn` at `0x1400227f6`
- `WIN32K!CddEngEqualRgn` at `0x1400227f6`
- `WIN32K!CddEngCombineRgn` at `0x140022791`
- `WIN32K!CddEngCombineRgn` at `0x1400227d5`
- `WIN32K!CddEngCombineRgn` at `0x140022791`
- `WIN32K!CddEngCombineRgn` at `0x1400227d5`
- `WIN32K!EngReleaseSemaphore` at `0x14002290d`
- `WIN32K!EngReleaseSemaphore` at `0x14002290d`
- `WIN32K!EngAcquireSemaphore` at `0x1400226d6`
- `WIN32K!EngAcquireSemaphore` at `0x1400226d6`

## pseudocode

```c
void __fastcall vGDIDirtyUpdate(struct CDDPDEV *a1, struct tagRECT *a2, struct _CLIPOBJ *a3)
{
  HSEMAPHORE v3; // rsi
  int v4; // r14d
  unsigned int v8; // ebp
  __int64 v9; // rbx
  int v10; // r8d
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // ebp
  __int64 v15; // rcx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // [rsp+20h] [rbp-38h] BYREF
  int v19; // [rsp+28h] [rbp-30h]

  v3 = (HSEMAPHORE)*((_QWORD *)a1 + 365);
  v4 = 0;
  if ( v3 )
  {
    EngAcquireSemaphore(*((HSEMAPHORE *)a1 + 365));
    v4 = 1;
  }
  v8 = ClipRect(a1, a2, a3);
  if ( (*((unsigned int (**)(void))a1 + 63))() != 4 )
  {
    v9 = *((_QWORD *)a1 + 684);
    if ( v9 != (*((__int64 (**)(void))a1 + 34))() )
    {
      CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v18, *((struct CDDMUTEX **)a1 + 686), v10);
      CddIssueCommand(a1, 21);
      if ( v19 )
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v18);
    }
  }
  if ( v8 > 1 )
  {
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)a1 + 360));
    v11 = (_QWORD *)((char *)a1 + 2816);
    if ( (unsigned int)CddEngCombineRgn((char *)a1 + 2816, *((_QWORD *)a1 + 358), *((_QWORD *)a1 + 353), 2) )
    {
      v12 = *((_QWORD *)a1 + 358);
      *((_QWORD *)a1 + 358) = *v11;
      *v11 = v12;
    }
    if ( *((_BYTE *)a1 + 2713) )
    {
      v13 = CddEngCombineRgn((char *)a1 + 2816, *((_QWORD *)a1 + 359), *((_QWORD *)a1 + 353), 4);
      v14 = v13;
      if ( v13 )
      {
        if ( v13 == 1 || !(unsigned int)CddEngEqualRgn(*v11, *((_QWORD *)a1 + 359)) )
        {
          v15 = *((_QWORD *)a1 + 359);
          *((_QWORD *)a1 + 359) = *v11;
          *v11 = v15;
          if ( v14 == 1 )
            *((_BYTE *)a1 + 2713) = 0;
          (*((void (**)(void))a1 + 74))();
        }
      }
    }
    v16 = *((_QWORD *)a1 + 360);
    *((_BYTE *)a1 + 2712) = 1;
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v16);
    if ( ((*((_DWORD *)a1 + 686) & 4) != 0 || *((_BYTE *)a1 + 2752)) && *((_BYTE *)a1 + 2716) && !*((_BYTE *)a1 + 2715) )
    {
      *((_BYTE *)a1 + 2752) = 0;
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 772;
        v17 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v17[3] = gCddImageInfo;
        v17[4] = (unsigned int)dword_14003E570;
        v17[5] = 215857758;
        WdLogGlobalForLineNumber = 772;
      }
      GetConnectedStandbyProcessName(a1);
      KeSetEvent(*((PRKEVENT *)a1 + 328), 0, 0);
    }
  }
  if ( v3 )
  {
    if ( v4 )
      EngReleaseSemaphore(v3);
  }
}

```

## disassembly

```asm
0x1400226b0  push    rbx
0x1400226b2  push    rbp
0x1400226b3  push    rsi
0x1400226b4  push    rdi
0x1400226b5  push    r14
0x1400226b7  sub     rsp, 30h
0x1400226bb  mov     rsi, [rcx+0B68h]
0x1400226c2  xor     r14d, r14d
0x1400226c5  mov     rbx, r8
0x1400226c8  mov     rbp, rdx
0x1400226cb  mov     rdi, rcx
0x1400226ce  test    rsi, rsi
0x1400226d1  jz      short loc_1400226E8
0x1400226d3  mov     rcx, rsi; hsem
0x1400226d6  call    cs:__imp_EngAcquireSemaphore
0x1400226dd  nop     dword ptr [rax+rax+00h]
0x1400226e2  mov     r14d, 1
0x1400226e8  mov     r8, rbx; struct _CLIPOBJ *
0x1400226eb  mov     rdx, rbp; struct tagRECT *
0x1400226ee  mov     rcx, rdi; struct CDDPDEV *
0x1400226f1  call    ?ClipRect@@YAHPEAUCDDPDEV@@PEAUtagRECT@@PEAU_CLIPOBJ@@@Z; ClipRect(CDDPDEV *,tagRECT *,_CLIPOBJ *)
0x1400226f6  mov     ebp, eax
0x1400226f8  mov     rax, [rdi+1F8h]
0x1400226ff  call    _guard_dispatch_icall
0x140022704  cmp     eax, 4
0x140022707  jz      short loc_140022757
0x140022709  mov     rax, [rdi+110h]
0x140022710  mov     rbx, [rdi+1560h]
0x140022717  call    _guard_dispatch_icall
0x14002271c  cmp     rbx, rax
0x14002271f  jz      short loc_140022757
0x140022721  mov     rdx, [rdi+1570h]; struct CDDMUTEX *
0x140022728  lea     rcx, [rsp+58h+var_38]; this
0x14002272d  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x140022732  mov     edx, 15h
0x140022737  mov     rcx, rdi
0x14002273a  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x14002273f  cmp     [rsp+58h+var_30], 0
0x140022744  jz      short loc_140022757
0x140022746  mov     rcx, [rsp+58h+var_38]
0x14002274b  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140022752  nop     dword ptr [rax+rax+00h]
0x140022757  cmp     ebp, 1
0x14002275a  jbe     loc_140022900
0x140022760  mov     rcx, [rdi+0B40h]
0x140022767  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14002276e  nop     dword ptr [rax+rax+00h]
0x140022773  mov     r8, [rdi+0B08h]
0x14002277a  lea     rbx, [rdi+0B00h]
0x140022781  mov     rdx, [rdi+0B30h]
0x140022788  mov     rcx, rbx
0x14002278b  mov     r9d, 2
0x140022791  call    cs:__imp_CddEngCombineRgn
0x140022798  nop     dword ptr [rax+rax+00h]
0x14002279d  test    eax, eax
0x14002279f  jz      short loc_1400227B5
0x1400227a1  mov     rcx, [rdi+0B30h]
0x1400227a8  mov     rax, [rbx]
0x1400227ab  mov     [rdi+0B30h], rax
0x1400227b2  mov     [rbx], rcx
0x1400227b5  cmp     byte ptr [rdi+0A99h], 0
0x1400227bc  jz      short loc_140022832
0x1400227be  mov     r8, [rdi+0B08h]
0x1400227c5  mov     r9d, 4
0x1400227cb  mov     rdx, [rdi+0B38h]
0x1400227d2  mov     rcx, rbx
0x1400227d5  call    cs:__imp_CddEngCombineRgn
0x1400227dc  nop     dword ptr [rax+rax+00h]
0x1400227e1  mov     ebp, eax
0x1400227e3  test    eax, eax
0x1400227e5  jz      short loc_140022832
0x1400227e7  cmp     eax, 1
0x1400227ea  jz      short loc_140022806
0x1400227ec  mov     rdx, [rdi+0B38h]
0x1400227f3  mov     rcx, [rbx]
0x1400227f6  call    cs:__imp_CddEngEqualRgn
0x1400227fd  nop     dword ptr [rax+rax+00h]
0x140022802  test    eax, eax
0x140022804  jnz     short loc_140022832
0x140022806  mov     rcx, [rdi+0B38h]
0x14002280d  mov     rax, [rbx]
0x140022810  mov     [rdi+0B38h], rax
0x140022817  mov     [rbx], rcx
0x14002281a  cmp     ebp, 1
0x14002281d  jnz     short loc_140022826
0x14002281f  mov     byte ptr [rdi+0A99h], 0
0x140022826  mov     rax, [rdi+250h]
0x14002282d  call    _guard_dispatch_icall
0x140022832  mov     rcx, [rdi+0B40h]
0x140022839  mov     byte ptr [rdi+0A98h], 1
0x140022840  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140022847  nop     dword ptr [rax+rax+00h]
0x14002284c  mov     eax, [rdi+0AB8h]
0x140022852  test    al, 4
0x140022854  jnz     short loc_140022864
0x140022856  mov     al, [rdi+0AC0h]
0x14002285c  test    al, al
0x14002285e  jz      loc_140022900
0x140022864  cmp     byte ptr [rdi+0A9Ch], 0
0x14002286b  jz      loc_140022900
0x140022871  cmp     byte ptr [rdi+0A9Bh], 0
0x140022878  jnz     loc_140022900
0x14002287e  mov     byte ptr [rdi+0AC0h], 0
0x140022885  call    cs:__imp_KeGetCurrentIrql
0x14002288c  nop     dword ptr [rax+rax+00h]
0x140022891  test    al, al
0x140022893  jz      short loc_1400228E0
0x140022895  mov     ecx, 1
0x14002289a  call    cs:__imp_WdLogSingleEntry0
0x1400228a1  nop     dword ptr [rax+rax+00h]
0x1400228a6  mov     ebx, 304h
0x1400228ab  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400228b1  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400228b8  nop     dword ptr [rax+rax+00h]
0x1400228bd  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400228c4  mov     [rax+18h], rcx
0x1400228c8  mov     ecx, cs:dword_14003E570
0x1400228ce  mov     [rax+20h], rcx
0x1400228d2  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400228da  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400228e0  mov     rcx, rdi; struct CDDPDEV *
0x1400228e3  call    ?GetConnectedStandbyProcessName@@YAXPEAUCDDPDEV@@@Z; GetConnectedStandbyProcessName(CDDPDEV *)
0x1400228e8  mov     rcx, [rdi+0A40h]; Event
0x1400228ef  xor     r8d, r8d; Wait
0x1400228f2  xor     edx, edx; Increment
0x1400228f4  call    cs:__imp_KeSetEvent
0x1400228fb  nop     dword ptr [rax+rax+00h]
0x140022900  test    rsi, rsi
0x140022903  jz      short loc_140022919
0x140022905  test    r14d, r14d
0x140022908  jz      short loc_140022919
0x14002290a  mov     rcx, rsi; hsem
0x14002290d  call    cs:__imp_EngReleaseSemaphore
0x140022914  nop     dword ptr [rax+rax+00h]
0x140022919  add     rsp, 30h
0x14002291d  pop     r14
0x14002291f  pop     rdi
0x140022920  pop     rsi
0x140022921  pop     rbp
0x140022922  pop     rbx
0x140022923  retn
```
