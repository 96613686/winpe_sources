# CStagingPool::ReleaseGdiSurface(CDDBITMAP_GDIDESC *)

- ea: `0x14000be40`
- end: `0x14000bf7e`
- name: `?ReleaseGdiSurface@CStagingPool@@QEAAXPEAUCDDBITMAP_GDIDESC@@@Z`
- size: `318`
- prototype: `void __fastcall(CStagingPool *__hidden this, struct CDDBITMAP_GDIDESC *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140002504`
- `0x140004904`
- `0x14000a254`
- `0x14000ca00`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x1400200e8`
- `0x140033548`

## callees

- `0x14000be40`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14000beba`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000bee2`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000beba`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000bee2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000be5c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000be5c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000bef1`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000bef1`
- `ntoskrnl!DbgPrint` at `0x14000bf1e`
- `ntoskrnl!DbgPrint` at `0x14000bf1e`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000bf07`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000bf45`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000bf45`
- `watchdog!WdLogSingleEntry0` at `0x14000bf2f`
- `watchdog!WdLogSingleEntry0` at `0x14000bf2f`

## string_xrefs

- `0x14000bf17`: `Error in CddBitmapStagingApertureMem::DecrementGdiAccessCount`

## pseudocode

```c
void __fastcall CStagingPool::ReleaseGdiSurface(CStagingPool *this, struct CDDBITMAP_GDIDESC *a2)
{
  __int64 v4; // rbp
  _QWORD *v5; // rbx
  __int64 v6; // rsi
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax

  v4 = *(_QWORD *)(*(_QWORD *)this + 2904LL);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v4);
  v5 = (_QWORD *)*((_QWORD *)a2 + 1);
  v6 = v5[4];
  if ( !*(_DWORD *)(v6 + 144) && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("Error in CddBitmapStagingApertureMem::DecrementGdiAccessCount");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 41;
    v11 = (_QWORD *)WdLogNewEntry5_WdError(v10, v9);
    v11[3] = gCddImageInfo;
    v11[4] = (unsigned int)dword_14003E570;
    v11[5] = 215857758;
    WdLogGlobalForLineNumber = 41;
    __debugbreak();
  }
  --*(_DWORD *)(v6 + 144);
  v7 = (_QWORD *)((char *)this + 792);
  v8 = *((_QWORD *)this + 99);
  if ( *(CStagingPool **)(v8 + 8) != (CStagingPool *)((char *)this + 792) )
    __fastfail(3u);
  *v5 = v8;
  v5[1] = v7;
  *(_QWORD *)(v8 + 8) = v5;
  *v7 = v5;
  KeReleaseSemaphore(*((PRKSEMAPHORE *)this + 101), 0, 1, 0);
  if ( !*(_DWORD *)(v5[4] + 144LL) )
    KeReleaseSemaphore(*((PRKSEMAPHORE *)this + 7), 0, 1, 0);
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v4);
}

```

## disassembly

```asm
0x14000be40  push    rbx
0x14000be42  push    rbp
0x14000be43  push    rsi
0x14000be44  push    rdi
0x14000be45  sub     rsp, 28h
0x14000be49  mov     rax, [rcx]
0x14000be4c  mov     rdi, rcx
0x14000be4f  mov     rbx, rdx
0x14000be52  mov     rbp, [rax+0B58h]
0x14000be59  mov     rcx, rbp
0x14000be5c  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000be63  nop     dword ptr [rax+rax+00h]
0x14000be68  mov     rbx, [rbx+8]
0x14000be6c  mov     rsi, [rbx+20h]
0x14000be70  cmp     dword ptr [rsi+90h], 0
0x14000be77  jbe     loc_14000BF07
0x14000be7d  dec     dword ptr [rsi+90h]
0x14000be83  lea     rax, [rdi+318h]
0x14000be8a  mov     rcx, [rax]
0x14000be8d  cmp     [rcx+8], rax
0x14000be91  jz      short loc_14000BE9A
0x14000be93  mov     ecx, 3
0x14000be98  int     29h; Win8: RtlFailFast(ecx)
0x14000be9a  mov     [rbx], rcx
0x14000be9d  xor     r9d, r9d; Wait
0x14000bea0  mov     [rbx+8], rax
0x14000bea4  xor     edx, edx; Increment
0x14000bea6  mov     [rcx+8], rbx
0x14000beaa  mov     r8d, 1; Adjustment
0x14000beb0  mov     [rax], rbx
0x14000beb3  mov     rcx, [rdi+328h]; Semaphore
0x14000beba  call    cs:__imp_KeReleaseSemaphore
0x14000bec1  nop     dword ptr [rax+rax+00h]
0x14000bec6  mov     rax, [rbx+20h]
0x14000beca  cmp     dword ptr [rax+90h], 0
0x14000bed1  jnz     short loc_14000BEEE
0x14000bed3  mov     rcx, [rdi+38h]; Semaphore
0x14000bed7  xor     r9d, r9d; Wait
0x14000beda  xor     edx, edx; Increment
0x14000bedc  mov     r8d, 1; Adjustment
0x14000bee2  call    cs:__imp_KeReleaseSemaphore
0x14000bee9  nop     dword ptr [rax+rax+00h]
0x14000beee  mov     rcx, rbp
0x14000bef1  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000bef8  nop     dword ptr [rax+rax+00h]
0x14000befd  add     rsp, 28h
0x14000bf01  pop     rdi
0x14000bf02  pop     rsi
0x14000bf03  pop     rbp
0x14000bf04  pop     rbx
0x14000bf05  retn
0x14000bf07  mov     rax, cs:KdDebuggerEnabled
0x14000bf0e  cmp     byte ptr [rax], 0
0x14000bf11  jz      loc_14000BE7D
0x14000bf17  lea     rcx, aErrorInCddbitm; "Error in CddBitmapStagingApertureMem::D"...
0x14000bf1e  call    cs:__imp_DbgPrint
0x14000bf25  nop     dword ptr [rax+rax+00h]
0x14000bf2a  mov     ecx, 2
0x14000bf2f  call    cs:__imp_WdLogSingleEntry0
0x14000bf36  nop     dword ptr [rax+rax+00h]
0x14000bf3b  mov     cs:WdLogGlobalForLineNumber, 29h ; ')'
0x14000bf45  call    cs:__imp_WdLogNewEntry5_WdError
0x14000bf4c  nop     dword ptr [rax+rax+00h]
0x14000bf51  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000bf58  mov     [rax+18h], rcx
0x14000bf5c  mov     ecx, cs:dword_14003E570
0x14000bf62  mov     [rax+20h], rcx
0x14000bf66  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000bf6e  mov     cs:WdLogGlobalForLineNumber, 29h ; ')'
0x14000bf78  int     3; Trap to Debugger
0x14000bf79  jmp     loc_14000BE7D
```
