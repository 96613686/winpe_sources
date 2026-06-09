# VidSchiProcessIsrHwQueuePageFaulted

- ea: `0x140055224`
- end: `0x1400553cd`
- name: `VidSchiProcessIsrHwQueuePageFaulted`
- size: `425`
- prototype: `const signed __int64 *__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140027fc0`

## callees

- `0x140004268`
- `0x140055224`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140055314`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140055314`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005535a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005535a`
- `watchdog!WdLogSingleEntry5` at `0x14005528f`
- `watchdog!WdLogSingleEntry5` at `0x1400552f7`
- `watchdog!WdLogSingleEntry5` at `0x14005528f`
- `watchdog!WdLogSingleEntry5` at `0x1400552f7`
- `watchdog!WdLogSingleEntry1` at `0x140055371`
- `watchdog!WdLogSingleEntry1` at `0x140055371`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14005526a`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400552ca`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
const signed __int64 *__fastcall VidSchiProcessIsrHwQueuePageFaulted(__int64 a1, __int64 a2)
{
  __int64 *v2; // rbx
  __int64 v4; // rdx
  __int64 v6; // r9
  __int64 v7; // r8
  unsigned __int64 v8; // rcx
  __int64 v9; // rbx
  const signed __int64 *result; // rax
  __int64 v11; // rcx
  PSLIST_ENTRY v12; // rax
  struct _SLIST_ENTRY v13; // xmm1
  int v14; // ecx
  int v15; // r8d

  v2 = *(__int64 **)(a1 + 776);
  v4 = *(unsigned int *)(a2 + 44);
  v6 = *(unsigned int *)(a2 + 40);
  v7 = (unsigned int)v6 + *(unsigned __int8 *)(v4 + a1 + 96);
  v8 = (unsigned int)v7;
  if ( (unsigned int)v7 < *(_DWORD *)(a1 + 848) )
    v2 += v7;
  v9 = *v2;
  if ( (*(_DWORD *)(v9 + 12) & 2) == 0 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 281, 13, 0, v6, v4);
    WdLogGlobalForLineNumber = 926;
  }
  result = *(const signed __int64 **)(a1 + 736);
  if ( !_bittest64(result, v8) )
  {
    result = (const signed __int64 *)*(unsigned int *)(v9 + 16);
    if ( (_DWORD)result != 1 )
    {
      if ( *(_DWORD *)(v9 + 16) == 2 )
      {
        v11 = *(unsigned __int16 *)(v9 + 4);
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, 16, a1, v11, 0);
        WdLogGlobalForLineNumber = 926;
      }
      v12 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v9 + 11520));
      if ( v12 )
      {
        v12[2].Next = (struct _SLIST_ENTRY *)v9;
        *(PSLIST_ENTRY)((char *)v12 + 40) = *(PSLIST_ENTRY)(a2 + 8);
        *(PSLIST_ENTRY)((char *)v12 + 56) = *(PSLIST_ENTRY)(a2 + 24);
        *(PSLIST_ENTRY)((char *)v12 + 72) = *(PSLIST_ENTRY)(a2 + 40);
        v13 = *(struct _SLIST_ENTRY *)(a2 + 56);
        LODWORD(v12->Next) = 12;
        *(PSLIST_ENTRY)((char *)v12 + 88) = v13;
        return (const signed __int64 *)ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 2144), v12 + 1);
      }
      else
      {
        WdLogSingleEntry1(1, *(unsigned __int16 *)(v9 + 4));
        WdLogGlobalForLineNumber = 533;
        return (const signed __int64 *)DxgkLogInternalTriageEvent(
                                         v14,
                                         0x40000,
                                         v15,
                                         (unsigned int)L"The list of pending HW queue page faulted interrupts is full on n"
                                                        "ode %d. There must be severe contention on the scheduler spin lo"
                                                        "ck. This interrupt will be ignored.",
                                         *(unsigned __int16 *)(v9 + 4),
                                         0,
                                         0,
                                         0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140055224  mov     [rsp+arg_0], rbx
0x140055229  mov     [rsp+arg_8], rsi
0x14005522e  push    rdi
0x14005522f  sub     rsp, 50h
0x140055233  mov     rbx, [rcx+308h]
0x14005523a  mov     rsi, rdx
0x14005523d  mov     edx, [rdx+2Ch]
0x140055240  mov     rdi, rcx
0x140055243  mov     r9d, [rsi+28h]
0x140055247  movzx   r8d, byte ptr [rdx+rcx+60h]
0x14005524d  add     r8d, r9d
0x140055250  mov     ecx, r8d
0x140055253  cmp     r8d, [rdi+350h]
0x14005525a  jnb     short loc_140055260
0x14005525c  lea     rbx, [rbx+r8*8]
0x140055260  mov     rbx, [rbx]
0x140055263  mov     eax, [rbx+0Ch]
0x140055266  test    al, 2
0x140055268  jnz     short loc_1400552A5
0x14005526a  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140055271  mov     dword ptr [rax], 1
0x140055277  mov     [rsp+58h+var_30], rdx
0x14005527c  xor     ecx, ecx
0x14005527e  mov     [rsp+58h+var_38], r9
0x140055283  mov     edx, 119h
0x140055288  xor     r9d, r9d
0x14005528b  lea     r8d, [r9+0Dh]
0x14005528f  call    cs:__imp_WdLogSingleEntry5
0x140055296  nop     dword ptr [rax+rax+00h]
0x14005529b  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x1400552a5  mov     rax, [rdi+2E0h]
0x1400552ac  bt      [rax], rcx
0x1400552b0  jb      loc_1400553BC
0x1400552b6  mov     eax, [rbx+10h]
0x1400552b9  cmp     eax, 1
0x1400552bc  jz      loc_1400553BC
0x1400552c2  mov     eax, [rbx+10h]
0x1400552c5  cmp     eax, 2
0x1400552c8  jnz     short loc_14005530D
0x1400552ca  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400552d1  movzx   ecx, word ptr [rbx+4]
0x1400552d5  mov     dword ptr [rax], 1
0x1400552db  mov     [rsp+58h+var_30], 0
0x1400552e4  mov     r9, rdi
0x1400552e7  mov     [rsp+58h+var_38], rcx
0x1400552ec  mov     edx, 119h
0x1400552f1  xor     ecx, ecx
0x1400552f3  lea     r8d, [rcx+10h]
0x1400552f7  call    cs:__imp_WdLogSingleEntry5
0x1400552fe  nop     dword ptr [rax+rax+00h]
0x140055303  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x14005530d  lea     rcx, [rbx+2D00h]; ListHead
0x140055314  call    cs:__imp_ExpInterlockedPopEntrySList
0x14005531b  nop     dword ptr [rax+rax+00h]
0x140055320  test    rax, rax
0x140055323  jz      short loc_140055368
0x140055325  mov     [rax+20h], rbx
0x140055329  lea     rdx, [rax+10h]; ListEntry
0x14005532d  movups  xmm0, xmmword ptr [rsi+8]
0x140055331  lea     rcx, [rdi+860h]; ListHead
0x140055338  movups  xmmword ptr [rax+28h], xmm0
0x14005533c  movups  xmm1, xmmword ptr [rsi+18h]
0x140055340  movups  xmmword ptr [rax+38h], xmm1
0x140055344  movups  xmm0, xmmword ptr [rsi+28h]
0x140055348  movups  xmmword ptr [rax+48h], xmm0
0x14005534c  movups  xmm1, xmmword ptr [rsi+38h]
0x140055350  mov     dword ptr [rax], 0Ch
0x140055356  movups  xmmword ptr [rax+58h], xmm1
0x14005535a  call    cs:__imp_ExpInterlockedPushEntrySList
0x140055361  nop     dword ptr [rax+rax+00h]
0x140055366  jmp     short loc_1400553BC
0x140055368  movzx   edx, word ptr [rbx+4]
0x14005536c  mov     ecx, 1
0x140055371  call    cs:__imp_WdLogSingleEntry1
0x140055378  nop     dword ptr [rax+rax+00h]
0x14005537d  mov     [rsp+58h+var_20], 0
0x140055386  lea     r9, aTheListOfPendi_2; "The list of pending HW queue page fault"...
0x14005538d  mov     cs:WdLogGlobalForLineNumber, 215h
0x140055397  mov     edx, 40000h
0x14005539c  movzx   eax, word ptr [rbx+4]
0x1400553a0  mov     [rsp+58h+var_28], 0
0x1400553a9  mov     [rsp+58h+var_30], 0
0x1400553b2  mov     [rsp+58h+var_38], rax
0x1400553b7  call    DxgkLogInternalTriageEvent
0x1400553bc  mov     rbx, [rsp+58h+arg_0]
0x1400553c1  mov     rsi, [rsp+58h+arg_8]
0x1400553c6  add     rsp, 50h
0x1400553ca  pop     rdi
0x1400553cb  retn
```
