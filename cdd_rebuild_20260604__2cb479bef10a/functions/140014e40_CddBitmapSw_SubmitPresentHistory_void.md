# CddBitmapSw::SubmitPresentHistory(void)

- ea: `0x140014e40`
- end: `0x140015125`
- name: `?SubmitPresentHistory@CddBitmapSw@@UEAAJXZ`
- size: `741`
- prototype: `__int64 __fastcall(CddBitmapSw *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140014e40`
- `0x140015440`
- `0x140031084`
- `0x1400372d0`
- `0x140037340`
- `0x140037640`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140014f75`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400150e8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140014f75`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400150e8`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001509f`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001510b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001509f`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001510b`
- `ntoskrnl!DbgPrint` at `0x140014edd`
- `ntoskrnl!DbgPrint` at `0x140014fa9`
- `ntoskrnl!DbgPrint` at `0x140014edd`
- `ntoskrnl!DbgPrint` at `0x140014fa9`
- `ntoskrnl!KdDebuggerEnabled` at `0x140014eca`
- `ntoskrnl!KdDebuggerEnabled` at `0x140014f96`
- `watchdog!WdLogNewEntry5_WdError` at `0x140014f03`
- `watchdog!WdLogNewEntry5_WdError` at `0x140014fd1`
- `watchdog!WdLogNewEntry5_WdError` at `0x140014f03`
- `watchdog!WdLogNewEntry5_WdError` at `0x140014fd1`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140014e7a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001501f`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140014e7a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001501f`
- `watchdog!WdLogSingleEntry0` at `0x140014e63`
- `watchdog!WdLogSingleEntry0` at `0x140014eec`
- `watchdog!WdLogSingleEntry0` at `0x140014fba`
- `watchdog!WdLogSingleEntry0` at `0x140015008`
- `watchdog!WdLogSingleEntry0` at `0x140014e63`
- `watchdog!WdLogSingleEntry0` at `0x140014eec`
- `watchdog!WdLogSingleEntry0` at `0x140014fba`
- `watchdog!WdLogSingleEntry0` at `0x140015008`

## string_xrefs

- `0x140014ed6`: `CDD worker thread expected`

## pseudocode

```c
__int64 __fastcall CddBitmapSw::SubmitPresentHistory(CddBitmapSw *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  _QWORD *v4; // rax
  unsigned int v5; // esi
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rdi
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  const struct tagRECT *v17; // r9
  const struct tagPOINT *v19; // [rsp+20h] [rbp-38h]

  if ( (*((_DWORD *)this + 32) & 2) == 0 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 251;
    v4 = (_QWORD *)WdLogNewEntry5_WdAssertion(v3, v2);
    v4[3] = gCddImageInfo;
    v4[4] = (unsigned int)dword_14003E570;
    v4[5] = 215857758;
    WdLogGlobalForLineNumber = 251;
  }
  v5 = 0;
  if ( *((_QWORD *)this + 68) )
  {
    if ( KeGetCurrentThread() != *(struct _KTHREAD **)(*((_QWORD *)this + 1) + 2568LL) && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("CDD worker thread expected");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 263;
      v8 = (_QWORD *)WdLogNewEntry5_WdError(v7, v6);
      v8[3] = gCddImageInfo;
      v8[4] = (unsigned int)dword_14003E570;
      v8[5] = 215857758;
      WdLogGlobalForLineNumber = 263;
      __debugbreak();
    }
    memset((void *)(*((_QWORD *)this + 1) + 7312LL), 0, 0x438u);
    v9 = *((_QWORD *)this + 1) + 7312LL;
    *(_DWORD *)v9 = 1;
    *(_QWORD *)(v9 + 16) = *((_QWORD *)this + 69);
    *(_QWORD *)(v9 + 24) = *((_QWORD *)this + 68);
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)this + 108));
    v10 = *((_DWORD *)this + 207);
    *(_DWORD *)(v9 + 56) = v10;
    if ( v10 > 0x10 && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Invalid number of dirty rects");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 276;
      v13 = (_QWORD *)WdLogNewEntry5_WdError(v12, v11);
      v13[3] = gCddImageInfo;
      v13[4] = (unsigned int)dword_14003E570;
      v13[5] = 215857758;
      WdLogGlobalForLineNumber = 276;
      __debugbreak();
    }
    if ( *(_DWORD *)(v9 + 56) > 0x10u )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 277;
      v16 = (_QWORD *)WdLogNewEntry5_WdAssertion(v15, v14);
      v16[3] = gCddImageInfo;
      v16[4] = (unsigned int)dword_14003E570;
      v16[5] = 215857758;
      WdLogGlobalForLineNumber = 277;
    }
    memmove((void *)(v9 + 60), (char *)this + 572, 16LL * *(unsigned int *)(v9 + 56));
    CDirtyRegion::GetScrollData(
      (CddBitmapSw *)((char *)this + 572),
      (struct tagRECT *)(v9 + 32),
      (struct tagPOINT *)(v9 + 48));
    *(_QWORD *)((char *)this + 828) = 0;
    *((_QWORD *)this + 105) = 0;
    *((_DWORD *)this + 209) = 0;
    *((_DWORD *)this + 214) = 1;
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)this + 108));
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*((_QWORD *)this + 1) + 288LL))(
           *(unsigned int *)(*((_QWORD *)this + 1) + 2524LL),
           v9,
           *(_QWORD *)(*((_QWORD *)this + 1) + 3616LL));
    if ( v5 == 258 && (*((_DWORD *)this + 32) & 4) == 0 )
    {
      ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)this + 108));
      CDirtyRegion::RestoreDirtyRegion(
        (CddBitmapSw *)((char *)this + 572),
        (const struct tagRECT *)(v9 + 60),
        *(_DWORD *)(v9 + 56),
        v17,
        v19);
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)this + 108));
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140014e40  push    rbx
0x140014e42  push    rbp
0x140014e43  push    rsi
0x140014e44  push    rdi
0x140014e45  push    r14
0x140014e47  sub     rsp, 30h
0x140014e4b  mov     eax, [rcx+80h]
0x140014e51  mov     rbx, rcx
0x140014e54  mov     r14d, 0CDDBA5Eh
0x140014e5a  test    al, 2
0x140014e5c  jnz     short loc_140014EA5
0x140014e5e  mov     ecx, 1
0x140014e63  call    cs:__imp_WdLogSingleEntry0
0x140014e6a  nop     dword ptr [rax+rax+00h]
0x140014e6f  mov     edi, 0FBh
0x140014e74  mov     cs:WdLogGlobalForLineNumber, edi
0x140014e7a  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140014e81  nop     dword ptr [rax+rax+00h]
0x140014e86  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140014e8d  mov     [rax+18h], rcx
0x140014e91  mov     ecx, cs:dword_14003E570
0x140014e97  mov     [rax+20h], rcx
0x140014e9b  mov     [rax+28h], r14
0x140014e9f  mov     cs:WdLogGlobalForLineNumber, edi
0x140014ea5  xor     esi, esi
0x140014ea7  cmp     [rbx+220h], rsi
0x140014eae  jz      loc_140015117
0x140014eb4  mov     rcx, gs:188h
0x140014ebd  mov     rax, [rbx+8]
0x140014ec1  cmp     rcx, [rax+0A08h]
0x140014ec8  jz      short loc_140014F2F
0x140014eca  mov     rax, cs:KdDebuggerEnabled
0x140014ed1  cmp     [rax], sil
0x140014ed4  jz      short loc_140014F2F
0x140014ed6  lea     rcx, aCddWorkerThrea; "CDD worker thread expected"
0x140014edd  call    cs:__imp_DbgPrint
0x140014ee4  nop     dword ptr [rax+rax+00h]
0x140014ee9  lea     ecx, [rsi+2]
0x140014eec  call    cs:__imp_WdLogSingleEntry0
0x140014ef3  nop     dword ptr [rax+rax+00h]
0x140014ef8  mov     edi, 107h
0x140014efd  mov     cs:WdLogGlobalForLineNumber, edi
0x140014f03  call    cs:__imp_WdLogNewEntry5_WdError
0x140014f0a  nop     dword ptr [rax+rax+00h]
0x140014f0f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140014f16  mov     [rax+18h], rcx
0x140014f1a  mov     ecx, cs:dword_14003E570
0x140014f20  mov     [rax+20h], rcx
0x140014f24  mov     [rax+28h], r14
0x140014f28  mov     cs:WdLogGlobalForLineNumber, edi
0x140014f2e  int     3; Trap to Debugger
0x140014f2f  mov     rcx, [rbx+8]
0x140014f33  xor     edx, edx; Val
0x140014f35  add     rcx, 1C90h; void *
0x140014f3c  mov     r8d, 438h; Size
0x140014f42  call    memset
0x140014f47  mov     rdi, [rbx+8]
0x140014f4b  add     rdi, 1C90h
0x140014f52  mov     dword ptr [rdi], 1
0x140014f58  mov     rax, [rbx+228h]
0x140014f5f  mov     [rdi+10h], rax
0x140014f63  mov     rax, [rbx+220h]
0x140014f6a  mov     [rdi+18h], rax
0x140014f6e  mov     rcx, [rbx+360h]
0x140014f75  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140014f7c  nop     dword ptr [rax+rax+00h]
0x140014f81  lea     rbp, [rbx+23Ch]
0x140014f88  mov     eax, [rbp+100h]
0x140014f8e  mov     [rdi+38h], eax
0x140014f91  cmp     eax, 10h
0x140014f94  jbe     short loc_140014FFD
0x140014f96  mov     rax, cs:KdDebuggerEnabled
0x140014f9d  cmp     [rax], sil
0x140014fa0  jz      short loc_140014FFD
0x140014fa2  lea     rcx, aInvalidNumberO; "Invalid number of dirty rects"
0x140014fa9  call    cs:__imp_DbgPrint
0x140014fb0  nop     dword ptr [rax+rax+00h]
0x140014fb5  mov     ecx, 2
0x140014fba  call    cs:__imp_WdLogSingleEntry0
0x140014fc1  nop     dword ptr [rax+rax+00h]
0x140014fc6  mov     esi, 114h
0x140014fcb  mov     cs:WdLogGlobalForLineNumber, esi
0x140014fd1  call    cs:__imp_WdLogNewEntry5_WdError
0x140014fd8  nop     dword ptr [rax+rax+00h]
0x140014fdd  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140014fe4  mov     [rax+18h], rcx
0x140014fe8  mov     ecx, cs:dword_14003E570
0x140014fee  mov     [rax+20h], rcx
0x140014ff2  mov     [rax+28h], r14
0x140014ff6  mov     cs:WdLogGlobalForLineNumber, esi
0x140014ffc  int     3; Trap to Debugger
0x140014ffd  cmp     dword ptr [rdi+38h], 10h
0x140015001  jbe     short loc_14001504A
0x140015003  mov     ecx, 1
0x140015008  call    cs:__imp_WdLogSingleEntry0
0x14001500f  nop     dword ptr [rax+rax+00h]
0x140015014  mov     esi, 115h
0x140015019  mov     cs:WdLogGlobalForLineNumber, esi
0x14001501f  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140015026  nop     dword ptr [rax+rax+00h]
0x14001502b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140015032  mov     [rax+18h], rcx
0x140015036  mov     ecx, cs:dword_14003E570
0x14001503c  mov     [rax+20h], rcx
0x140015040  mov     [rax+28h], r14
0x140015044  mov     cs:WdLogGlobalForLineNumber, esi
0x14001504a  mov     r8d, [rdi+38h]
0x14001504e  lea     rcx, [rdi+3Ch]; void *
0x140015052  shl     r8, 4; Size
0x140015056  mov     rdx, rbp; Src
0x140015059  call    memmove
0x14001505e  lea     r8, [rdi+30h]; struct tagPOINT *
0x140015062  mov     rcx, rbp; this
0x140015065  lea     rdx, [rdi+20h]; struct tagRECT *
0x140015069  call    ?GetScrollData@CDirtyRegion@@QEAAXPEAUtagRECT@@PEAUtagPOINT@@@Z; CDirtyRegion::GetScrollData(tagRECT *,tagPOINT *)
0x14001506e  mov     qword ptr [rbx+33Ch], 0
0x140015079  mov     qword ptr [rbx+348h], 0
0x140015084  mov     dword ptr [rbx+344h], 0
0x14001508e  mov     dword ptr [rbx+358h], 1
0x140015098  mov     rcx, [rbx+360h]
0x14001509f  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1400150a6  nop     dword ptr [rax+rax+00h]
0x1400150ab  mov     rcx, [rbx+8]
0x1400150af  mov     rdx, rdi
0x1400150b2  mov     rax, [rcx+120h]
0x1400150b9  mov     r8, [rcx+0E20h]
0x1400150c0  mov     ecx, [rcx+9DCh]
0x1400150c6  call    _guard_dispatch_icall
0x1400150cb  mov     esi, eax
0x1400150cd  cmp     eax, 102h
0x1400150d2  jnz     short loc_140015117
0x1400150d4  mov     r8d, [rbx+80h]
0x1400150db  test    r8b, 4
0x1400150df  jnz     short loc_140015117
0x1400150e1  mov     rcx, [rbx+360h]
0x1400150e8  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x1400150ef  nop     dword ptr [rax+rax+00h]
0x1400150f4  mov     r8d, [rdi+38h]; unsigned int
0x1400150f8  lea     rdx, [rdi+3Ch]; struct tagRECT *
0x1400150fc  mov     rcx, rbp; this
0x1400150ff  call    ?RestoreDirtyRegion@CDirtyRegion@@QEAAXPEBUtagRECT@@I0PEBUtagPOINT@@@Z; CDirtyRegion::RestoreDirtyRegion(tagRECT const *,uint,tagRECT const *,tagPOINT const *)
0x140015104  mov     rcx, [rbx+360h]
0x14001510b  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140015112  nop     dword ptr [rax+rax+00h]
0x140015117  mov     eax, esi
0x140015119  add     rsp, 30h
0x14001511d  pop     r14
0x14001511f  pop     rdi
0x140015120  pop     rsi
0x140015121  pop     rbp
0x140015122  pop     rbx
0x140015123  retn
```
