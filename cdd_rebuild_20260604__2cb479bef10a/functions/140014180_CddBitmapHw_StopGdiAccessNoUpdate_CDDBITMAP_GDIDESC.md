# CddBitmapHw::StopGdiAccessNoUpdate(CDDBITMAP_GDIDESC *)

- ea: `0x140014180`
- end: `0x1400142fd`
- name: `?StopGdiAccessNoUpdate@CddBitmapHw@@UEAAXPEAUCDDBITMAP_GDIDESC@@@Z`
- size: `381`
- prototype: `void __fastcall(CddBitmapHw *__hidden this, struct CDDBITMAP_GDIDESC *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140014180`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14001421b`
- `ntoskrnl!KeReleaseSemaphore` at `0x140014243`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001421b`
- `ntoskrnl!KeReleaseSemaphore` at `0x140014243`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400141b8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400141b8`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140014252`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140014252`
- `ntoskrnl!DbgPrint` at `0x14001429d`
- `ntoskrnl!DbgPrint` at `0x14001429d`
- `ntoskrnl!KdDebuggerEnabled` at `0x140014286`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400142c4`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400142c4`
- `watchdog!WdLogSingleEntry0` at `0x1400142ae`
- `watchdog!WdLogSingleEntry0` at `0x1400142ae`

## string_xrefs

- `0x140014296`: `Error in CddBitmapStagingApertureMem::DecrementGdiAccessCount`

## pseudocode

```c
void __fastcall CddBitmapHw::StopGdiAccessNoUpdate(CddBitmapHw *this, struct CDDBITMAP_GDIDESC *a2)
{
  __int64 v2; // rdi
  __int64 v4; // r14
  _QWORD *v5; // rsi
  __int64 v6; // rbp
  _QWORD *v7; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rax

  v2 = *((_QWORD *)a2 + 7);
  if ( v2 )
  {
    v4 = *(_QWORD *)(*(_QWORD *)v2 + 2904LL);
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v4);
    v5 = (_QWORD *)*((_QWORD *)a2 + 1);
    v6 = v5[4];
    if ( !*(_DWORD *)(v6 + 144) && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error in CddBitmapStagingApertureMem::DecrementGdiAccessCount");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 41;
      v9 = (_QWORD *)WdLogNewEntry5_WdError();
      v9[3] = gCddImageInfo;
      v9[4] = (unsigned int)dword_14003E570;
      v9[5] = 215857758;
      WdLogGlobalForLineNumber = 41;
      __debugbreak();
    }
    --*(_DWORD *)(v6 + 144);
    v7 = (_QWORD *)(v2 + 792);
    v8 = *(_QWORD *)(v2 + 792);
    if ( *(_QWORD *)(v8 + 8) != v2 + 792 )
      __fastfail(3u);
    *v5 = v8;
    v5[1] = v7;
    *(_QWORD *)(v8 + 8) = v5;
    *v7 = v5;
    KeReleaseSemaphore(*(PRKSEMAPHORE *)(v2 + 808), 0, 1, 0);
    if ( !*(_DWORD *)(v5[4] + 144LL) )
      KeReleaseSemaphore(*(PRKSEMAPHORE *)(v2 + 56), 0, 1, 0);
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v4);
    *((_QWORD *)a2 + 7) = 0;
  }
  *(_QWORD *)a2 = 0;
  *((_DWORD *)a2 + 4) = 0;
  *((_QWORD *)a2 + 3) = 0;
  *((_DWORD *)a2 + 8) = 0;
}

```

## disassembly

```asm
0x140014180  mov     [rsp+arg_8], rbx
0x140014185  mov     [rsp+arg_10], rsi
0x14001418a  push    rdi
0x14001418b  push    r14
0x14001418d  push    r15
0x14001418f  sub     rsp, 20h
0x140014193  mov     rdi, [rdx+38h]
0x140014197  xor     r15d, r15d
0x14001419a  mov     rbx, rdx
0x14001419d  test    rdi, rdi
0x1400141a0  jz      loc_140014262
0x1400141a6  mov     rax, [rdi]
0x1400141a9  mov     [rsp+38h+arg_0], rbp
0x1400141ae  mov     r14, [rax+0B58h]
0x1400141b5  mov     rcx, r14
0x1400141b8  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x1400141bf  nop     dword ptr [rax+rax+00h]
0x1400141c4  mov     rsi, [rbx+8]
0x1400141c8  mov     rbp, [rsi+20h]
0x1400141cc  cmp     [rbp+90h], r15d
0x1400141d3  jbe     loc_140014286
0x1400141d9  dec     dword ptr [rbp+90h]
0x1400141df  lea     rax, [rdi+318h]
0x1400141e6  mov     rcx, [rax]
0x1400141e9  mov     rbp, [rsp+38h+arg_0]
0x1400141ee  cmp     [rcx+8], rax
0x1400141f2  jz      short loc_1400141FB
0x1400141f4  mov     ecx, 3
0x1400141f9  int     29h; Win8: RtlFailFast(ecx)
0x1400141fb  mov     [rsi], rcx
0x1400141fe  xor     r9d, r9d; Wait
0x140014201  mov     [rsi+8], rax
0x140014205  xor     edx, edx; Increment
0x140014207  mov     [rcx+8], rsi
0x14001420b  mov     r8d, 1; Adjustment
0x140014211  mov     [rax], rsi
0x140014214  mov     rcx, [rdi+328h]; Semaphore
0x14001421b  call    cs:__imp_KeReleaseSemaphore
0x140014222  nop     dword ptr [rax+rax+00h]
0x140014227  mov     rax, [rsi+20h]
0x14001422b  cmp     [rax+90h], r15d
0x140014232  jnz     short loc_14001424F
0x140014234  mov     rcx, [rdi+38h]; Semaphore
0x140014238  xor     r9d, r9d; Wait
0x14001423b  xor     edx, edx; Increment
0x14001423d  mov     r8d, 1; Adjustment
0x140014243  call    cs:__imp_KeReleaseSemaphore
0x14001424a  nop     dword ptr [rax+rax+00h]
0x14001424f  mov     rcx, r14
0x140014252  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140014259  nop     dword ptr [rax+rax+00h]
0x14001425e  mov     [rbx+38h], r15
0x140014262  mov     rsi, [rsp+38h+arg_10]
0x140014267  mov     [rbx], r15
0x14001426a  mov     [rbx+10h], r15d
0x14001426e  mov     [rbx+18h], r15
0x140014272  mov     [rbx+20h], r15d
0x140014276  mov     rbx, [rsp+38h+arg_8]
0x14001427b  add     rsp, 20h
0x14001427f  pop     r15
0x140014281  pop     r14
0x140014283  pop     rdi
0x140014284  retn
0x140014286  mov     rax, cs:KdDebuggerEnabled
0x14001428d  cmp     [rax], r15b
0x140014290  jz      loc_1400141D9
0x140014296  lea     rcx, aErrorInCddbitm; "Error in CddBitmapStagingApertureMem::D"...
0x14001429d  call    cs:__imp_DbgPrint
0x1400142a4  nop     dword ptr [rax+rax+00h]
0x1400142a9  mov     ecx, 2
0x1400142ae  call    cs:__imp_WdLogSingleEntry0
0x1400142b5  nop     dword ptr [rax+rax+00h]
0x1400142ba  mov     cs:WdLogGlobalForLineNumber, 29h ; ')'
0x1400142c4  call    cs:__imp_WdLogNewEntry5_WdError
0x1400142cb  nop     dword ptr [rax+rax+00h]
0x1400142d0  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400142d7  mov     [rax+18h], rcx
0x1400142db  mov     ecx, cs:dword_14003E570
0x1400142e1  mov     [rax+20h], rcx
0x1400142e5  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400142ed  mov     cs:WdLogGlobalForLineNumber, 29h ; ')'
0x1400142f7  int     3; Trap to Debugger
0x1400142f8  jmp     loc_1400141D9
```
