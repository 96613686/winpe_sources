# AcknowledgeBreak

- ea: `0x14002ce1c`
- end: `0x14002ceee`
- name: `AcknowledgeBreak`
- size: `210`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013fa0`

## callees

- `0x14002ce1c`

## import_xrefs

- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002cec4`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002ced4`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002cec4`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002ced4`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002cea2`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002cea2`
- `mrxsmb!SmbCeInitializeExchange` at `0x14002ce75`
- `mrxsmb!SmbCeInitializeExchange` at `0x14002ce75`

## pseudocode

```c
__int64 __fastcall AcknowledgeBreak(__int64 a1, char a2)
{
  __int64 v2; // rdi
  __int64 v3; // r8
  __int64 (__fastcall **v4)(); // rax
  int v5; // ebx
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 72);
  v3 = *(_QWORD *)(*(_QWORD *)(v2 + 40) + 40LL);
  v4 = &LeaseDispatch;
  if ( !a2 )
    v4 = &OplockDispatch;
  v7 = 0;
  v5 = SmbCeInitializeExchange(&v7, a1, 0, 0, 0, v3, 2552, v4);
  if ( v5 >= 0 )
  {
    *(_QWORD *)(v7 + 2408) = v2;
    _InterlockedOr((volatile signed __int32 *)(v7 + 68), 1u);
    v5 = SmbCeInitiateExchange(v7);
    if ( v5 == 259 )
      return (unsigned int)SmbCeWaitForCompletionAndFinalizeExchangeEx(v7, 0, 0, 0);
    else
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v7, 0, 0, 0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002ce1c  mov     r11, rsp
0x14002ce1f  mov     [r11+10h], rbx
0x14002ce23  push    rdi
0x14002ce24  sub     rsp, 40h
0x14002ce28  mov     rdi, [rcx+48h]
0x14002ce2c  lea     r9, OplockDispatch
0x14002ce33  test    dl, dl
0x14002ce35  mov     rdx, rcx
0x14002ce38  lea     rcx, [r11+8]
0x14002ce3c  mov     rax, [rdi+28h]
0x14002ce40  mov     r8, [rax+28h]
0x14002ce44  lea     rax, LeaseDispatch
0x14002ce4b  cmovz   rax, r9
0x14002ce4f  mov     qword ptr [r11+8], 0
0x14002ce57  mov     [r11-10h], rax
0x14002ce5b  xor     r9d, r9d
0x14002ce5e  mov     [rsp+48h+var_18], 9F8h
0x14002ce66  mov     [r11-20h], r8
0x14002ce6a  xor     r8d, r8d
0x14002ce6d  mov     qword ptr [r11-28h], 0
0x14002ce75  call    cs:__imp_SmbCeInitializeExchange
0x14002ce7c  nop     dword ptr [rax+rax+00h]
0x14002ce81  mov     ebx, eax
0x14002ce83  test    eax, eax
0x14002ce85  js      short loc_14002CEE0
0x14002ce87  mov     rax, [rsp+48h+arg_0]
0x14002ce8c  mov     [rax+968h], rdi
0x14002ce93  mov     rax, [rsp+48h+arg_0]
0x14002ce98  lock or dword ptr [rax+44h], 1
0x14002ce9d  mov     rcx, [rsp+48h+arg_0]
0x14002cea2  call    cs:__imp_SmbCeInitiateExchange
0x14002cea9  nop     dword ptr [rax+rax+00h]
0x14002ceae  mov     rcx, [rsp+48h+arg_0]
0x14002ceb3  xor     r9d, r9d
0x14002ceb6  xor     r8d, r8d
0x14002ceb9  xor     edx, edx
0x14002cebb  mov     ebx, eax
0x14002cebd  cmp     eax, 103h
0x14002cec2  jnz     short loc_14002CED4
0x14002cec4  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14002cecb  nop     dword ptr [rax+rax+00h]
0x14002ced0  mov     ebx, eax
0x14002ced2  jmp     short loc_14002CEE0
0x14002ced4  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14002cedb  nop     dword ptr [rax+rax+00h]
0x14002cee0  mov     eax, ebx
0x14002cee2  mov     rbx, [rsp+48h+arg_8]
0x14002cee7  add     rsp, 40h
0x14002ceeb  pop     rdi
0x14002ceec  retn
```
