# VidSchiProcessIsrSuspendContextCompleted

- ea: `0x140055594`
- end: `0x1400556bd`
- name: `VidSchiProcessIsrSuspendContextCompleted`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140027fc0`

## callees

- `0x140004268`
- `0x140055594`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140055623`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140055623`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140055651`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140055651`
- `watchdog!WdLogSingleEntry5` at `0x140055606`
- `watchdog!WdLogSingleEntry5` at `0x140055606`
- `watchdog!WdLogSingleEntry1` at `0x140055668`
- `watchdog!WdLogSingleEntry1` at `0x140055668`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400555d9`

## string_xrefs

- `0x14005567d`: `The list of pending context suspend completed interrupts is full on node %d. There must be severe contention on the scheduler spin lock. This interrupt will be ignored.`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
const signed __int64 *__fastcall VidSchiProcessIsrSuspendContextCompleted(union _SLIST_HEADER *a1, __int64 a2)
{
  struct _SLIST_ENTRY *v4; // rbp
  const signed __int64 *result; // rax
  struct _SLIST_ENTRY *Next; // rbx
  __int64 v7; // rcx
  PSLIST_ENTRY v8; // rax
  int v9; // ecx
  int v10; // r8d

  v4 = *(struct _SLIST_ENTRY **)(*(_QWORD *)(a2 + 8) + 8LL);
  result = (const signed __int64 *)a1[46].Alignment;
  Next = v4[1].Next;
  if ( !_bittest64(result, WORD2(Next->Next)) )
  {
    result = (const signed __int64 *)LODWORD(Next[1].Next);
    if ( (_DWORD)result != 1 )
    {
      if ( LODWORD(Next[1].Next) == 2 )
      {
        v7 = WORD2(Next->Next);
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, 16, a1, v7, 0);
        WdLogGlobalForLineNumber = 926;
      }
      v8 = ExpInterlockedPopEntrySList((PSLIST_HEADER)&Next[833]);
      if ( v8 )
      {
        v8[2].Next = v4;
        *((_QWORD *)&v8[2].Next + 1) = *(_QWORD *)(a2 + 16);
        LODWORD(v8->Next) = 17;
        return (const signed __int64 *)ExpInterlockedPushEntrySList(a1 + 134, v8 + 1);
      }
      else
      {
        WdLogSingleEntry1(1, WORD2(Next->Next));
        WdLogGlobalForLineNumber = 468;
        return (const signed __int64 *)DxgkLogInternalTriageEvent(
                                         v9,
                                         0x40000,
                                         v10,
                                         (unsigned int)L"The list of pending context suspend completed interrupts is full "
                                                        "on node %d. There must be severe contention on the scheduler spi"
                                                        "n lock. This interrupt will be ignored.",
                                         WORD2(Next->Next),
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
0x140055594  push    rbx
0x140055596  push    rbp
0x140055597  push    rsi
0x140055598  push    rdi
0x140055599  sub     rsp, 58h
0x14005559d  mov     rax, [rdx+8]
0x1400555a1  mov     rsi, rdx
0x1400555a4  mov     rdi, rcx
0x1400555a7  mov     rbp, [rax+8]
0x1400555ab  mov     rax, [rcx+2E0h]
0x1400555b2  mov     rbx, [rbp+10h]
0x1400555b6  movzx   r8d, word ptr [rbx+4]
0x1400555bb  bt      [rax], r8
0x1400555bf  jb      loc_1400556B3
0x1400555c5  mov     eax, [rbx+10h]
0x1400555c8  cmp     eax, 1
0x1400555cb  jz      loc_1400556B3
0x1400555d1  mov     eax, [rbx+10h]
0x1400555d4  cmp     eax, 2
0x1400555d7  jnz     short loc_14005561C
0x1400555d9  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400555e0  movzx   ecx, word ptr [rbx+4]
0x1400555e4  mov     dword ptr [rax], 1
0x1400555ea  mov     [rsp+78h+var_50], 0
0x1400555f3  mov     r9, rdi
0x1400555f6  mov     [rsp+78h+var_58], rcx
0x1400555fb  mov     edx, 119h
0x140055600  xor     ecx, ecx
0x140055602  lea     r8d, [rcx+10h]
0x140055606  call    cs:__imp_WdLogSingleEntry5
0x14005560d  nop     dword ptr [rax+rax+00h]
0x140055612  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x14005561c  lea     rcx, [rbx+3410h]; ListHead
0x140055623  call    cs:__imp_ExpInterlockedPopEntrySList
0x14005562a  nop     dword ptr [rax+rax+00h]
0x14005562f  test    rax, rax
0x140055632  jz      short loc_14005565F
0x140055634  mov     [rax+20h], rbp
0x140055638  lea     rdx, [rax+10h]; ListEntry
0x14005563c  mov     rcx, [rsi+10h]
0x140055640  mov     [rax+28h], rcx
0x140055644  lea     rcx, [rdi+860h]; ListHead
0x14005564b  mov     dword ptr [rax], 11h
0x140055651  call    cs:__imp_ExpInterlockedPushEntrySList
0x140055658  nop     dword ptr [rax+rax+00h]
0x14005565d  jmp     short loc_1400556B3
0x14005565f  movzx   edx, word ptr [rbx+4]
0x140055663  mov     ecx, 1
0x140055668  call    cs:__imp_WdLogSingleEntry1
0x14005566f  nop     dword ptr [rax+rax+00h]
0x140055674  mov     [rsp+78h+var_40], 0
0x14005567d  lea     r9, aTheListOfPendi_1; "The list of pending context suspend com"...
0x140055684  mov     cs:WdLogGlobalForLineNumber, 1D4h
0x14005568e  mov     edx, 40000h
0x140055693  movzx   eax, word ptr [rbx+4]
0x140055697  mov     [rsp+78h+var_48], 0
0x1400556a0  mov     [rsp+78h+var_50], 0
0x1400556a9  mov     [rsp+78h+var_58], rax
0x1400556ae  call    DxgkLogInternalTriageEvent
0x1400556b3  add     rsp, 58h
0x1400556b7  pop     rdi
0x1400556b8  pop     rsi
0x1400556b9  pop     rbp
0x1400556ba  pop     rbx
0x1400556bb  retn
```
