# UlpSetRequestQueueState

- ea: `0x1400d003c`
- end: `0x1400d01c1`
- name: `UlpSetRequestQueueState`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400cd5e0`

## callees

- `0x140041778`
- `0x1400a0968`
- `0x1400a1808`
- `0x1400a21ec`
- `0x1400d003c`
- `0x1401c3f58`
- `0x1401c57e4`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d00f3`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d0179`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d00f3`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d0179`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d00c0`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d013c`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d00c0`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d013c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d00ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d0185`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d00ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d0185`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d00ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d0129`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d00ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d0129`

## pseudocode

```c
void __fastcall UlpSetRequestQueueState(__int64 a1, unsigned int a2, int a3)
{
  int v5; // esi
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  _QWORD *v8; // rbx
  int v9; // [rsp+28h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF
  __int64 *v11; // [rsp+38h] [rbp-10h]

  v10 = (__int64)&v10;
  v11 = &v10;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 139, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, a2);
  if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
  {
    v9 = a2;
    WPP_SF_qZL(a1, 140, a3, a1, a1 + 160, v9, v10, v11);
  }
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  v5 = *(_DWORD *)(a1 + 248);
  *(_DWORD *)(a1 + 248) = a2;
  if ( a2 )
    UlpFlushPendingRequests(a1, &v10, 0);
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  KeLeaveCriticalRegion();
  if ( a2 )
  {
    v6 = UlpRequestQueueStateToErrorCode(a2);
    UlpRejectFlushedRequests(a1, &v10, v6, 0);
  }
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  if ( a2 != v5 )
  {
    v7 = *(_QWORD **)(a1 + 216);
    if ( v7 != (_QWORD *)(a1 + 216) )
    {
      do
      {
        v8 = (_QWORD *)*v7;
        UlFlushCacheByRequestQueue(v7[11], a1);
        v7 = v8;
      }
      while ( v8 != (_QWORD *)(a1 + 216) );
    }
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  KeLeaveCriticalRegion();
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 141, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
}

```

## disassembly

```asm
0x1400d003c  mov     r11, rsp
0x1400d003f  mov     [r11+8], rbx
0x1400d0043  mov     [r11+10h], rsi
0x1400d0047  push    rdi
0x1400d0048  sub     rsp, 40h
0x1400d004c  lea     rax, [r11-18h]
0x1400d0050  mov     ebx, edx
0x1400d0052  mov     [r11-18h], rax
0x1400d0056  mov     rdi, rcx
0x1400d0059  lea     rax, [r11-18h]
0x1400d005d  mov     [r11-10h], rax
0x1400d0061  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400d0068  jz      short loc_1400D0087
0x1400d006a  mov     edx, 8Bh
0x1400d006f  mov     dword ptr [rsp+48h+var_28], ebx
0x1400d0073  mov     ecx, 408h
0x1400d0078  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400d007f  mov     r9, rdi
0x1400d0082  call    WPP_SF_qD
0x1400d0087  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x1400d008e  jz      short loc_1400D00AD
0x1400d0090  lea     rax, [rdi+0A0h]
0x1400d0097  mov     [rsp+48h+var_20], ebx
0x1400d009b  mov     edx, 8Ch
0x1400d00a0  mov     [rsp+48h+var_28], rax
0x1400d00a5  mov     r9, rdi
0x1400d00a8  call    WPP_SF_qZL
0x1400d00ad  call    cs:__imp_KeEnterCriticalRegion
0x1400d00b4  nop     dword ptr [rax+rax+00h]
0x1400d00b9  mov     rcx, [rdi+118h]
0x1400d00c0  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d00c7  nop     dword ptr [rax+rax+00h]
0x1400d00cc  mov     esi, [rdi+0F8h]
0x1400d00d2  mov     [rdi+0F8h], ebx
0x1400d00d8  test    ebx, ebx
0x1400d00da  jz      short loc_1400D00EC
0x1400d00dc  xor     r8d, r8d
0x1400d00df  lea     rdx, [rsp+48h+var_18]
0x1400d00e4  mov     rcx, rdi
0x1400d00e7  call    UlpFlushPendingRequests
0x1400d00ec  mov     rcx, [rdi+118h]
0x1400d00f3  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400d00fa  nop     dword ptr [rax+rax+00h]
0x1400d00ff  call    cs:__imp_KeLeaveCriticalRegion
0x1400d0106  nop     dword ptr [rax+rax+00h]
0x1400d010b  test    ebx, ebx
0x1400d010d  jz      short loc_1400D0129
0x1400d010f  mov     ecx, ebx
0x1400d0111  call    UlpRequestQueueStateToErrorCode
0x1400d0116  xor     r9d, r9d
0x1400d0119  lea     rdx, [rsp+48h+var_18]
0x1400d011e  mov     r8d, eax
0x1400d0121  mov     rcx, rdi
0x1400d0124  call    UlpRejectFlushedRequests
0x1400d0129  call    cs:__imp_KeEnterCriticalRegion
0x1400d0130  nop     dword ptr [rax+rax+00h]
0x1400d0135  mov     rcx, [rdi+118h]
0x1400d013c  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d0143  nop     dword ptr [rax+rax+00h]
0x1400d0148  cmp     ebx, esi
0x1400d014a  jz      short loc_1400D0172
0x1400d014c  lea     rsi, [rdi+0D8h]
0x1400d0153  mov     rcx, [rsi]
0x1400d0156  cmp     rcx, rsi
0x1400d0159  jz      short loc_1400D0172
0x1400d015b  mov     rbx, [rcx]
0x1400d015e  mov     rdx, rdi
0x1400d0161  mov     rcx, [rcx+58h]
0x1400d0165  call    UlFlushCacheByRequestQueue
0x1400d016a  mov     rcx, rbx
0x1400d016d  cmp     rbx, rsi
0x1400d0170  jnz     short loc_1400D015B
0x1400d0172  mov     rcx, [rdi+118h]
0x1400d0179  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400d0180  nop     dword ptr [rax+rax+00h]
0x1400d0185  call    cs:__imp_KeLeaveCriticalRegion
0x1400d018c  nop     dword ptr [rax+rax+00h]
0x1400d0191  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400d0198  jz      short loc_1400D01B0
0x1400d019a  mov     edx, 8Dh
0x1400d019f  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400d01a6  mov     ecx, 408h
0x1400d01ab  call    WPP_SF_
0x1400d01b0  mov     rbx, [rsp+48h+arg_0]
0x1400d01b5  mov     rsi, [rsp+48h+arg_8]
0x1400d01ba  add     rsp, 40h
0x1400d01be  pop     rdi
0x1400d01bf  retn
```
