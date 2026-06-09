# VidSchiProcessIsrHwQueuePageFaulted

- ea: `0x14005494c`
- end: `0x140054af5`
- name: `VidSchiProcessIsrHwQueuePageFaulted`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002a680`

## callees

- `0x1400045ec`
- `0x14005494c`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140054a3c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140054a3c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140054a82`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140054a82`
- `watchdog!WdLogSingleEntry5` at `0x1400549b7`
- `watchdog!WdLogSingleEntry5` at `0x140054a1f`
- `watchdog!WdLogSingleEntry5` at `0x1400549b7`
- `watchdog!WdLogSingleEntry5` at `0x140054a1f`
- `watchdog!WdLogSingleEntry1` at `0x140054a99`
- `watchdog!WdLogSingleEntry1` at `0x140054a99`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140054992`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400549f2`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
const signed __int64 *__fastcall VidSchiProcessIsrHwQueuePageFaulted(__int64 a1, __int64 a2)
{
  __int64 *v2; // rbx
  __int64 v5; // r8
  unsigned __int64 v6; // rcx
  __int64 v7; // rbx
  const signed __int64 *result; // rax
  PSLIST_ENTRY v9; // rax
  struct _SLIST_ENTRY v10; // xmm1
  int v11; // ecx
  int v12; // r8d

  v2 = *(__int64 **)(a1 + 776);
  v5 = *(_DWORD *)(a2 + 40) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 44) + a1 + 96);
  v6 = (unsigned int)v5;
  if ( (unsigned int)v5 < *(_DWORD *)(a1 + 848) )
    v2 += v5;
  v7 = *v2;
  if ( (*(_DWORD *)(v7 + 12) & 2) == 0 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 281, 13);
    WdLogGlobalForLineNumber = 921;
  }
  result = *(const signed __int64 **)(a1 + 736);
  if ( !_bittest64(result, v6) )
  {
    result = (const signed __int64 *)*(unsigned int *)(v7 + 16);
    if ( (_DWORD)result != 1 )
    {
      if ( *(_DWORD *)(v7 + 16) == 2 )
      {
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, 16);
        WdLogGlobalForLineNumber = 921;
      }
      v9 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v7 + 11520));
      if ( v9 )
      {
        v9[2].Next = (struct _SLIST_ENTRY *)v7;
        *(PSLIST_ENTRY)((char *)v9 + 40) = *(PSLIST_ENTRY)(a2 + 8);
        *(PSLIST_ENTRY)((char *)v9 + 56) = *(PSLIST_ENTRY)(a2 + 24);
        *(PSLIST_ENTRY)((char *)v9 + 72) = *(PSLIST_ENTRY)(a2 + 40);
        v10 = *(struct _SLIST_ENTRY *)(a2 + 56);
        LODWORD(v9->Next) = 12;
        *(PSLIST_ENTRY)((char *)v9 + 88) = v10;
        return (const signed __int64 *)ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 2144), v9 + 1);
      }
      else
      {
        WdLogSingleEntry1(1, *(unsigned __int16 *)(v7 + 4));
        WdLogGlobalForLineNumber = 533;
        return (const signed __int64 *)DxgkLogInternalTriageEvent(
                                         v11,
                                         0x40000,
                                         v12,
                                         (unsigned int)L"The list of pending HW queue page faulted interrupts is full on n"
                                                        "ode %d. There must be severe contention on the scheduler spin lo"
                                                        "ck. This interrupt will be ignored.",
                                         *(unsigned __int16 *)(v7 + 4),
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
0x14005494c  mov     [rsp+arg_0], rbx
0x140054951  mov     [rsp+arg_8], rsi
0x140054956  push    rdi
0x140054957  sub     rsp, 50h
0x14005495b  mov     rbx, [rcx+308h]
0x140054962  mov     rsi, rdx
0x140054965  mov     edx, [rdx+2Ch]
0x140054968  mov     rdi, rcx
0x14005496b  mov     r9d, [rsi+28h]
0x14005496f  movzx   r8d, byte ptr [rdx+rcx+60h]
0x140054975  add     r8d, r9d
0x140054978  mov     ecx, r8d
0x14005497b  cmp     r8d, [rdi+350h]
0x140054982  jnb     short loc_140054988
0x140054984  lea     rbx, [rbx+r8*8]
0x140054988  mov     rbx, [rbx]
0x14005498b  mov     eax, [rbx+0Ch]
0x14005498e  test    al, 2
0x140054990  jnz     short loc_1400549CD
0x140054992  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140054999  mov     dword ptr [rax], 1
0x14005499f  mov     [rsp+58h+var_30], rdx
0x1400549a4  xor     ecx, ecx
0x1400549a6  mov     [rsp+58h+var_38], r9
0x1400549ab  mov     edx, 119h
0x1400549b0  xor     r9d, r9d
0x1400549b3  lea     r8d, [r9+0Dh]
0x1400549b7  call    cs:__imp_WdLogSingleEntry5
0x1400549be  nop     dword ptr [rax+rax+00h]
0x1400549c3  mov     cs:WdLogGlobalForLineNumber, 399h
0x1400549cd  mov     rax, [rdi+2E0h]
0x1400549d4  bt      [rax], rcx
0x1400549d8  jb      loc_140054AE4
0x1400549de  mov     eax, [rbx+10h]
0x1400549e1  cmp     eax, 1
0x1400549e4  jz      loc_140054AE4
0x1400549ea  mov     eax, [rbx+10h]
0x1400549ed  cmp     eax, 2
0x1400549f0  jnz     short loc_140054A35
0x1400549f2  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400549f9  movzx   ecx, word ptr [rbx+4]
0x1400549fd  mov     dword ptr [rax], 1
0x140054a03  mov     [rsp+58h+var_30], 0
0x140054a0c  mov     r9, rdi
0x140054a0f  mov     [rsp+58h+var_38], rcx
0x140054a14  mov     edx, 119h
0x140054a19  xor     ecx, ecx
0x140054a1b  lea     r8d, [rcx+10h]
0x140054a1f  call    cs:__imp_WdLogSingleEntry5
0x140054a26  nop     dword ptr [rax+rax+00h]
0x140054a2b  mov     cs:WdLogGlobalForLineNumber, 399h
0x140054a35  lea     rcx, [rbx+2D00h]; ListHead
0x140054a3c  call    cs:__imp_ExpInterlockedPopEntrySList
0x140054a43  nop     dword ptr [rax+rax+00h]
0x140054a48  test    rax, rax
0x140054a4b  jz      short loc_140054A90
0x140054a4d  mov     [rax+20h], rbx
0x140054a51  lea     rdx, [rax+10h]; ListEntry
0x140054a55  movups  xmm0, xmmword ptr [rsi+8]
0x140054a59  lea     rcx, [rdi+860h]; ListHead
0x140054a60  movups  xmmword ptr [rax+28h], xmm0
0x140054a64  movups  xmm1, xmmword ptr [rsi+18h]
0x140054a68  movups  xmmword ptr [rax+38h], xmm1
0x140054a6c  movups  xmm0, xmmword ptr [rsi+28h]
0x140054a70  movups  xmmword ptr [rax+48h], xmm0
0x140054a74  movups  xmm1, xmmword ptr [rsi+38h]
0x140054a78  mov     dword ptr [rax], 0Ch
0x140054a7e  movups  xmmword ptr [rax+58h], xmm1
0x140054a82  call    cs:__imp_ExpInterlockedPushEntrySList
0x140054a89  nop     dword ptr [rax+rax+00h]
0x140054a8e  jmp     short loc_140054AE4
0x140054a90  movzx   edx, word ptr [rbx+4]
0x140054a94  mov     ecx, 1
0x140054a99  call    cs:__imp_WdLogSingleEntry1
0x140054aa0  nop     dword ptr [rax+rax+00h]
0x140054aa5  mov     [rsp+58h+var_20], 0
0x140054aae  lea     r9, aTheListOfPendi_2; "The list of pending HW queue page fault"...
0x140054ab5  mov     cs:WdLogGlobalForLineNumber, 215h
0x140054abf  mov     edx, 40000h
0x140054ac4  movzx   eax, word ptr [rbx+4]
0x140054ac8  mov     [rsp+58h+var_28], 0
0x140054ad1  mov     [rsp+58h+var_30], 0
0x140054ada  mov     [rsp+58h+var_38], rax
0x140054adf  call    DxgkLogInternalTriageEvent
0x140054ae4  mov     rbx, [rsp+58h+arg_0]
0x140054ae9  mov     rsi, [rsp+58h+arg_8]
0x140054aee  add     rsp, 50h
0x140054af2  pop     rdi
0x140054af3  retn
```
