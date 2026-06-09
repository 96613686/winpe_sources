# VidSchiProcessIsrSuspendContextCompleted

- ea: `0x140054cbc`
- end: `0x140054de5`
- name: `VidSchiProcessIsrSuspendContextCompleted`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002a680`

## callees

- `0x1400045ec`
- `0x140054cbc`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140054d4b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140054d4b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140054d79`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140054d79`
- `watchdog!WdLogSingleEntry5` at `0x140054d2e`
- `watchdog!WdLogSingleEntry5` at `0x140054d2e`
- `watchdog!WdLogSingleEntry1` at `0x140054d90`
- `watchdog!WdLogSingleEntry1` at `0x140054d90`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140054d01`

## string_xrefs

- `0x140054da5`: `The list of pending context suspend completed interrupts is full on node %d. There must be severe contention on the scheduler spin lock. This interrupt will be ignored.`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
const signed __int64 *__fastcall VidSchiProcessIsrSuspendContextCompleted(union _SLIST_HEADER *a1, __int64 a2)
{
  struct _SLIST_ENTRY *v4; // rbp
  const signed __int64 *result; // rax
  struct _SLIST_ENTRY *Next; // rbx
  PSLIST_ENTRY v7; // rax
  int v8; // ecx
  int v9; // r8d

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
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, 16);
        WdLogGlobalForLineNumber = 921;
      }
      v7 = ExpInterlockedPopEntrySList((PSLIST_HEADER)&Next[833]);
      if ( v7 )
      {
        v7[2].Next = v4;
        *((_QWORD *)&v7[2].Next + 1) = *(_QWORD *)(a2 + 16);
        LODWORD(v7->Next) = 17;
        return (const signed __int64 *)ExpInterlockedPushEntrySList(a1 + 134, v7 + 1);
      }
      else
      {
        WdLogSingleEntry1(1, WORD2(Next->Next));
        WdLogGlobalForLineNumber = 468;
        return (const signed __int64 *)DxgkLogInternalTriageEvent(
                                         v8,
                                         0x40000,
                                         v9,
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
0x140054cbc  push    rbx
0x140054cbe  push    rbp
0x140054cbf  push    rsi
0x140054cc0  push    rdi
0x140054cc1  sub     rsp, 58h
0x140054cc5  mov     rax, [rdx+8]
0x140054cc9  mov     rsi, rdx
0x140054ccc  mov     rdi, rcx
0x140054ccf  mov     rbp, [rax+8]
0x140054cd3  mov     rax, [rcx+2E0h]
0x140054cda  mov     rbx, [rbp+10h]
0x140054cde  movzx   r8d, word ptr [rbx+4]
0x140054ce3  bt      [rax], r8
0x140054ce7  jb      loc_140054DDB
0x140054ced  mov     eax, [rbx+10h]
0x140054cf0  cmp     eax, 1
0x140054cf3  jz      loc_140054DDB
0x140054cf9  mov     eax, [rbx+10h]
0x140054cfc  cmp     eax, 2
0x140054cff  jnz     short loc_140054D44
0x140054d01  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140054d08  movzx   ecx, word ptr [rbx+4]
0x140054d0c  mov     dword ptr [rax], 1
0x140054d12  mov     [rsp+78h+var_50], 0
0x140054d1b  mov     r9, rdi
0x140054d1e  mov     [rsp+78h+var_58], rcx
0x140054d23  mov     edx, 119h
0x140054d28  xor     ecx, ecx
0x140054d2a  lea     r8d, [rcx+10h]
0x140054d2e  call    cs:__imp_WdLogSingleEntry5
0x140054d35  nop     dword ptr [rax+rax+00h]
0x140054d3a  mov     cs:WdLogGlobalForLineNumber, 399h
0x140054d44  lea     rcx, [rbx+3410h]; ListHead
0x140054d4b  call    cs:__imp_ExpInterlockedPopEntrySList
0x140054d52  nop     dword ptr [rax+rax+00h]
0x140054d57  test    rax, rax
0x140054d5a  jz      short loc_140054D87
0x140054d5c  mov     [rax+20h], rbp
0x140054d60  lea     rdx, [rax+10h]; ListEntry
0x140054d64  mov     rcx, [rsi+10h]
0x140054d68  mov     [rax+28h], rcx
0x140054d6c  lea     rcx, [rdi+860h]; ListHead
0x140054d73  mov     dword ptr [rax], 11h
0x140054d79  call    cs:__imp_ExpInterlockedPushEntrySList
0x140054d80  nop     dword ptr [rax+rax+00h]
0x140054d85  jmp     short loc_140054DDB
0x140054d87  movzx   edx, word ptr [rbx+4]
0x140054d8b  mov     ecx, 1
0x140054d90  call    cs:__imp_WdLogSingleEntry1
0x140054d97  nop     dword ptr [rax+rax+00h]
0x140054d9c  mov     [rsp+78h+var_40], 0
0x140054da5  lea     r9, aTheListOfPendi_1; "The list of pending context suspend com"...
0x140054dac  mov     cs:WdLogGlobalForLineNumber, 1D4h
0x140054db6  mov     edx, 40000h
0x140054dbb  movzx   eax, word ptr [rbx+4]
0x140054dbf  mov     [rsp+78h+var_48], 0
0x140054dc8  mov     [rsp+78h+var_50], 0
0x140054dd1  mov     [rsp+78h+var_58], rax
0x140054dd6  call    DxgkLogInternalTriageEvent
0x140054ddb  add     rsp, 58h
0x140054ddf  pop     rdi
0x140054de0  pop     rsi
0x140054de1  pop     rbp
0x140054de2  pop     rbx
0x140054de3  retn
```
