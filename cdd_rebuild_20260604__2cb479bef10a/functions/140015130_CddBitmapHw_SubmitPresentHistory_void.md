# CddBitmapHw::SubmitPresentHistory(void)

- ea: `0x140015130`
- end: `0x14001542d`
- name: `?SubmitPresentHistory@CddBitmapHw@@UEAAJXZ`
- size: `765`
- prototype: `__int64 __fastcall(CddBitmapHw *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400133d0`
- `0x140015130`
- `0x140015440`
- `0x1400372d0`
- `0x140037340`
- `0x140037640`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400151d0`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400153f6`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400151d0`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400153f6`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140015264`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001541c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140015264`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001541c`
- `ntoskrnl!DbgPrint` at `0x1400152c6`
- `ntoskrnl!DbgPrint` at `0x140015336`
- `ntoskrnl!DbgPrint` at `0x1400152c6`
- `ntoskrnl!DbgPrint` at `0x140015336`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400152af`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001531f`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400152eb`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001535b`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400152eb`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001535b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400153ab`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400153ab`
- `watchdog!WdLogSingleEntry0` at `0x1400152d4`
- `watchdog!WdLogSingleEntry0` at `0x140015344`
- `watchdog!WdLogSingleEntry0` at `0x140015394`
- `watchdog!WdLogSingleEntry0` at `0x1400152d4`
- `watchdog!WdLogSingleEntry0` at `0x140015344`
- `watchdog!WdLogSingleEntry0` at `0x140015394`

## string_xrefs

- `0x1400152bf`: `CDD worker thread expected`

## pseudocode

```c
__int64 __fastcall CddBitmapHw::SubmitPresentHistory(CddBitmapHw *this)
{
  unsigned int v2; // esi
  __int64 v3; // rcx
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rsi
  unsigned int v7; // eax
  char *v8; // rbp
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rax

  if ( (*((_DWORD *)this + 32) & 4) != 0 )
    return 0;
  v2 = 0;
  if ( *((_QWORD *)this + 68) )
  {
    v3 = *((_QWORD *)this + 1);
    v4 = *(unsigned int *)(*(_QWORD *)(v3 + 12704) + 8LL);
    if ( KeGetCurrentThread() != *(struct _KTHREAD **)(v3 + 2568) && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("CDD worker thread expected");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 339;
      v12 = (_QWORD *)WdLogNewEntry5_WdError(v11, v10);
      v12[3] = gCddImageInfo;
      v12[4] = (unsigned int)dword_14003E570;
      v12[5] = 215857758;
      WdLogGlobalForLineNumber = 339;
      __debugbreak();
    }
    memset((void *)(*((_QWORD *)this + 1) + 7312LL), 0, 0x438u);
    v5 = *((_QWORD *)this + 1) + 7312LL;
    *(_DWORD *)v5 = 1;
    *(_QWORD *)(v5 + 16) = *((_QWORD *)this + 70);
    *(_QWORD *)(v5 + 24) = *((_QWORD *)this + 68);
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)this + 147));
    v6 = 288 * v4;
    v7 = *(_DWORD *)((char *)this + v6 + 856);
    *(_DWORD *)(v5 + 56) = v7;
    if ( v7 > 0x10 && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Invalid number of sdirty rects");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 352;
      v15 = (_QWORD *)WdLogNewEntry5_WdError(v14, v13);
      v15[3] = gCddImageInfo;
      v15[4] = (unsigned int)dword_14003E570;
      v15[5] = 215857758;
      WdLogGlobalForLineNumber = 352;
      __debugbreak();
    }
    if ( *(_DWORD *)(v5 + 56) > 0x10u )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 353;
      v18 = (_QWORD *)WdLogNewEntry5_WdAssertion(v17, v16);
      v18[3] = gCddImageInfo;
      v18[4] = (unsigned int)dword_14003E570;
      v18[5] = 215857758;
      WdLogGlobalForLineNumber = 353;
    }
    v8 = (char *)this + v6 + 600;
    memmove((void *)(v5 + 60), v8, 16LL * *(unsigned int *)(v5 + 56));
    CDirtyRegion::GetScrollData((CDirtyRegion *)v8, (struct tagRECT *)(v5 + 32), (struct tagPOINT *)(v5 + 48));
    *(_QWORD *)((char *)this + v6 + 856) = 0;
    *(_QWORD *)((char *)this + v6 + 868) = 0;
    *(_DWORD *)((char *)this + v6 + 864) = 0;
    *(_DWORD *)((char *)this + v6 + 884) = 1;
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)this + 147));
    v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*((_QWORD *)this + 1) + 288LL))(
           *(unsigned int *)(*((_QWORD *)this + 1) + 2524LL),
           v5,
           *(_QWORD *)(*((_QWORD *)this + 1) + 3616LL));
    if ( v2 == 258 && (*((_DWORD *)this + 32) & 4) == 0 )
    {
      ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)this + 147));
      CDirtyRegion::AddRects((CDirtyRegion *)v8, (const struct tagRECT *)(v5 + 60), *(_DWORD *)(v5 + 56), 0);
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)this + 147));
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140015130  push    rbx
0x140015132  push    rbp
0x140015133  push    rsi
0x140015134  push    rdi
0x140015135  push    r14
0x140015137  sub     rsp, 20h
0x14001513b  mov     eax, [rcx+80h]
0x140015141  mov     rbx, rcx
0x140015144  test    al, 4
0x140015146  jnz     loc_1400152AB
0x14001514c  xor     esi, esi
0x14001514e  cmp     [rcx+220h], rsi
0x140015155  jz      loc_14001529D
0x14001515b  mov     rcx, [rcx+8]
0x14001515f  mov     ebp, 2
0x140015164  mov     r14d, 0CDDBA5Eh
0x14001516a  mov     rax, [rcx+31A0h]
0x140015171  mov     esi, [rax+8]
0x140015174  mov     rax, gs:188h
0x14001517d  cmp     rax, [rcx+0A08h]
0x140015184  jnz     loc_1400152AF
0x14001518a  mov     rcx, [rbx+8]
0x14001518e  xor     edx, edx; Val
0x140015190  add     rcx, 1C90h; void *
0x140015197  mov     r8d, 438h; Size
0x14001519d  call    memset
0x1400151a2  mov     rdi, [rbx+8]
0x1400151a6  add     rdi, 1C90h
0x1400151ad  mov     dword ptr [rdi], 1
0x1400151b3  mov     rax, [rbx+230h]
0x1400151ba  mov     [rdi+10h], rax
0x1400151be  mov     rax, [rbx+220h]
0x1400151c5  mov     [rdi+18h], rax
0x1400151c9  mov     rcx, [rbx+498h]
0x1400151d0  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x1400151d7  nop     dword ptr [rax+rax+00h]
0x1400151dc  lea     rsi, [rsi+rsi*8]
0x1400151e0  shl     rsi, 5
0x1400151e4  mov     eax, [rsi+rbx+358h]
0x1400151eb  mov     [rdi+38h], eax
0x1400151ee  cmp     eax, 10h
0x1400151f1  ja      loc_14001531F
0x1400151f7  cmp     dword ptr [rdi+38h], 10h
0x1400151fb  ja      loc_14001538F
0x140015201  mov     r8d, [rdi+38h]
0x140015205  lea     rbp, [rbx+258h]
0x14001520c  add     rbp, rsi
0x14001520f  shl     r8, 4; Size
0x140015213  mov     rdx, rbp; Src
0x140015216  lea     rcx, [rdi+3Ch]; void *
0x14001521a  call    memmove
0x14001521f  lea     r8, [rdi+30h]; struct tagPOINT *
0x140015223  mov     rcx, rbp; this
0x140015226  lea     rdx, [rdi+20h]; struct tagRECT *
0x14001522a  call    ?GetScrollData@CDirtyRegion@@QEAAXPEAUtagRECT@@PEAUtagPOINT@@@Z; CDirtyRegion::GetScrollData(tagRECT *,tagPOINT *)
0x14001522f  mov     qword ptr [rsi+rbx+358h], 0
0x14001523b  mov     qword ptr [rsi+rbx+364h], 0
0x140015247  mov     dword ptr [rsi+rbx+360h], 0
0x140015252  mov     dword ptr [rsi+rbx+374h], 1
0x14001525d  mov     rcx, [rbx+498h]
0x140015264  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14001526b  nop     dword ptr [rax+rax+00h]
0x140015270  mov     rcx, [rbx+8]
0x140015274  mov     rdx, rdi
0x140015277  mov     rax, [rcx+120h]
0x14001527e  mov     r8, [rcx+0E20h]
0x140015285  mov     ecx, [rcx+9DCh]
0x14001528b  call    _guard_dispatch_icall
0x140015290  mov     esi, eax
0x140015292  cmp     eax, 102h
0x140015297  jz      loc_1400153DE
0x14001529d  mov     eax, esi
0x14001529f  add     rsp, 20h
0x1400152a3  pop     r14
0x1400152a5  pop     rdi
0x1400152a6  pop     rsi
0x1400152a7  pop     rbp
0x1400152a8  pop     rbx
0x1400152a9  retn
0x1400152ab  xor     eax, eax
0x1400152ad  jmp     short loc_14001529F
0x1400152af  mov     rax, cs:KdDebuggerEnabled
0x1400152b6  cmp     byte ptr [rax], 0
0x1400152b9  jz      loc_14001518A
0x1400152bf  lea     rcx, aCddWorkerThrea; "CDD worker thread expected"
0x1400152c6  call    cs:__imp_DbgPrint
0x1400152cd  nop     dword ptr [rax+rax+00h]
0x1400152d2  mov     ecx, ebp
0x1400152d4  call    cs:__imp_WdLogSingleEntry0
0x1400152db  nop     dword ptr [rax+rax+00h]
0x1400152e0  mov     edi, 153h
0x1400152e5  mov     cs:WdLogGlobalForLineNumber, edi
0x1400152eb  call    cs:__imp_WdLogNewEntry5_WdError
0x1400152f2  nop     dword ptr [rax+rax+00h]
0x1400152f7  mov     rcx, rax
0x1400152fa  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140015301  mov     [rcx+18h], rax
0x140015305  mov     eax, cs:dword_14003E570
0x14001530b  mov     [rcx+20h], rax
0x14001530f  mov     [rcx+28h], r14
0x140015313  mov     cs:WdLogGlobalForLineNumber, edi
0x140015319  int     3; Trap to Debugger
0x14001531a  jmp     loc_14001518A
0x14001531f  mov     rax, cs:KdDebuggerEnabled
0x140015326  cmp     byte ptr [rax], 0
0x140015329  jz      loc_1400151F7
0x14001532f  lea     rcx, aInvalidNumberO_0; "Invalid number of sdirty rects"
0x140015336  call    cs:__imp_DbgPrint
0x14001533d  nop     dword ptr [rax+rax+00h]
0x140015342  mov     ecx, ebp
0x140015344  call    cs:__imp_WdLogSingleEntry0
0x14001534b  nop     dword ptr [rax+rax+00h]
0x140015350  mov     ebp, 160h
0x140015355  mov     cs:WdLogGlobalForLineNumber, ebp
0x14001535b  call    cs:__imp_WdLogNewEntry5_WdError
0x140015362  nop     dword ptr [rax+rax+00h]
0x140015367  mov     rcx, rax
0x14001536a  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140015371  mov     [rcx+18h], rax
0x140015375  mov     eax, cs:dword_14003E570
0x14001537b  mov     [rcx+20h], rax
0x14001537f  mov     [rcx+28h], r14
0x140015383  mov     cs:WdLogGlobalForLineNumber, ebp
0x140015389  int     3; Trap to Debugger
0x14001538a  jmp     loc_1400151F7
0x14001538f  mov     ecx, 1
0x140015394  call    cs:__imp_WdLogSingleEntry0
0x14001539b  nop     dword ptr [rax+rax+00h]
0x1400153a0  mov     ebp, 161h
0x1400153a5  mov     cs:WdLogGlobalForLineNumber, ebp
0x1400153ab  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400153b2  nop     dword ptr [rax+rax+00h]
0x1400153b7  mov     rcx, rax
0x1400153ba  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400153c1  mov     [rcx+18h], rax
0x1400153c5  mov     eax, cs:dword_14003E570
0x1400153cb  mov     [rcx+20h], rax
0x1400153cf  mov     [rcx+28h], r14
0x1400153d3  mov     cs:WdLogGlobalForLineNumber, ebp
0x1400153d9  jmp     loc_140015201
0x1400153de  mov     r8d, [rbx+80h]
0x1400153e5  test    r8b, 4
0x1400153e9  jnz     loc_14001529D
0x1400153ef  mov     rcx, [rbx+498h]
0x1400153f6  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x1400153fd  nop     dword ptr [rax+rax+00h]
0x140015402  mov     r8d, [rdi+38h]; unsigned int
0x140015406  lea     rdx, [rdi+3Ch]; struct tagRECT *
0x14001540a  xor     r9d, r9d; struct tagPOINT *
0x14001540d  mov     rcx, rbp; this
0x140015410  call    ?AddRects@CDirtyRegion@@QEAAXPEBUtagRECT@@IPEBUtagPOINT@@@Z; CDirtyRegion::AddRects(tagRECT const *,uint,tagPOINT const *)
0x140015415  mov     rcx, [rbx+498h]
0x14001541c  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140015423  nop     dword ptr [rax+rax+00h]
0x140015428  jmp     loc_14001529D
```
