# UlpSetRequestQueueState

- ea: `0x1400d011c`
- end: `0x1400d02a1`
- name: `UlpSetRequestQueueState`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400cd6c0`

## callees

- `0x140041798`
- `0x1400a0988`
- `0x1400a1828`
- `0x1400a220c`
- `0x1400d011c`
- `0x1401c3f58`
- `0x1401c57e4`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d01d3`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d0259`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d01d3`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d0259`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d01a0`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d021c`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d01a0`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d021c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d01df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d0265`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d01df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d0265`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d018d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d0209`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d018d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d0209`

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
0x1400d011c  mov     r11, rsp
0x1400d011f  mov     [r11+8], rbx
0x1400d0123  mov     [r11+10h], rsi
0x1400d0127  push    rdi
0x1400d0128  sub     rsp, 40h
0x1400d012c  lea     rax, [r11-18h]
0x1400d0130  mov     ebx, edx
0x1400d0132  mov     [r11-18h], rax
0x1400d0136  mov     rdi, rcx
0x1400d0139  lea     rax, [r11-18h]
0x1400d013d  mov     [r11-10h], rax
0x1400d0141  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400d0148  jz      short loc_1400D0167
0x1400d014a  mov     edx, 8Bh
0x1400d014f  mov     dword ptr [rsp+48h+var_28], ebx
0x1400d0153  mov     ecx, 408h
0x1400d0158  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400d015f  mov     r9, rdi
0x1400d0162  call    WPP_SF_qD
0x1400d0167  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x1400d016e  jz      short loc_1400D018D
0x1400d0170  lea     rax, [rdi+0A0h]
0x1400d0177  mov     [rsp+48h+var_20], ebx
0x1400d017b  mov     edx, 8Ch
0x1400d0180  mov     [rsp+48h+var_28], rax
0x1400d0185  mov     r9, rdi
0x1400d0188  call    WPP_SF_qZL
0x1400d018d  call    cs:__imp_KeEnterCriticalRegion
0x1400d0194  nop     dword ptr [rax+rax+00h]
0x1400d0199  mov     rcx, [rdi+118h]
0x1400d01a0  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d01a7  nop     dword ptr [rax+rax+00h]
0x1400d01ac  mov     esi, [rdi+0F8h]
0x1400d01b2  mov     [rdi+0F8h], ebx
0x1400d01b8  test    ebx, ebx
0x1400d01ba  jz      short loc_1400D01CC
0x1400d01bc  xor     r8d, r8d
0x1400d01bf  lea     rdx, [rsp+48h+var_18]
0x1400d01c4  mov     rcx, rdi
0x1400d01c7  call    UlpFlushPendingRequests
0x1400d01cc  mov     rcx, [rdi+118h]
0x1400d01d3  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400d01da  nop     dword ptr [rax+rax+00h]
0x1400d01df  call    cs:__imp_KeLeaveCriticalRegion
0x1400d01e6  nop     dword ptr [rax+rax+00h]
0x1400d01eb  test    ebx, ebx
0x1400d01ed  jz      short loc_1400D0209
0x1400d01ef  mov     ecx, ebx
0x1400d01f1  call    UlpRequestQueueStateToErrorCode
0x1400d01f6  xor     r9d, r9d
0x1400d01f9  lea     rdx, [rsp+48h+var_18]
0x1400d01fe  mov     r8d, eax
0x1400d0201  mov     rcx, rdi
0x1400d0204  call    UlpRejectFlushedRequests
0x1400d0209  call    cs:__imp_KeEnterCriticalRegion
0x1400d0210  nop     dword ptr [rax+rax+00h]
0x1400d0215  mov     rcx, [rdi+118h]
0x1400d021c  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d0223  nop     dword ptr [rax+rax+00h]
0x1400d0228  cmp     ebx, esi
0x1400d022a  jz      short loc_1400D0252
0x1400d022c  lea     rsi, [rdi+0D8h]
0x1400d0233  mov     rcx, [rsi]
0x1400d0236  cmp     rcx, rsi
0x1400d0239  jz      short loc_1400D0252
0x1400d023b  mov     rbx, [rcx]
0x1400d023e  mov     rdx, rdi
0x1400d0241  mov     rcx, [rcx+58h]
0x1400d0245  call    UlFlushCacheByRequestQueue
0x1400d024a  mov     rcx, rbx
0x1400d024d  cmp     rbx, rsi
0x1400d0250  jnz     short loc_1400D023B
0x1400d0252  mov     rcx, [rdi+118h]
0x1400d0259  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400d0260  nop     dword ptr [rax+rax+00h]
0x1400d0265  call    cs:__imp_KeLeaveCriticalRegion
0x1400d026c  nop     dword ptr [rax+rax+00h]
0x1400d0271  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400d0278  jz      short loc_1400D0290
0x1400d027a  mov     edx, 8Dh
0x1400d027f  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400d0286  mov     ecx, 408h
0x1400d028b  call    WPP_SF_
0x1400d0290  mov     rbx, [rsp+48h+arg_0]
0x1400d0295  mov     rsi, [rsp+48h+arg_8]
0x1400d029a  add     rsp, 40h
0x1400d029e  pop     rdi
0x1400d029f  retn
```
