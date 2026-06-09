# MRxSmb2Flush

- ea: `0x1400228e0`
- end: `0x1400229a3`
- name: `MRxSmb2Flush`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400228e0`

## import_xrefs

- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002297c`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002298a`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002297c`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002298a`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002295a`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002295a`
- `mrxsmb!SmbCeInitializeExchange` at `0x140022936`
- `mrxsmb!SmbCeInitializeExchange` at `0x140022936`

## pseudocode

```c
__int64 __fastcall MRxSmb2Flush(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // rax
  __int64 result; // rax
  unsigned int v5; // ebx
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 72);
  v2 = *(_QWORD *)(*(_QWORD *)(v1 + 40) + 40LL);
  v3 = *(_QWORD *)(v1 + 48);
  v6 = 0;
  if ( (*(_DWORD *)(v3 + 8) & 0x20) != 0 )
    return 0;
  result = SmbCeInitializeExchange(&v6, a1, 0, 0, 0, v2, 2528, &FlushDispatch);
  if ( !(_DWORD)result )
  {
    _InterlockedOr((volatile signed __int32 *)(v6 + 68), 1u);
    v5 = SmbCeInitiateExchange(v6);
    if ( v5 == 259 )
    {
      return SmbCeWaitForCompletionAndFinalizeExchangeEx(v6, 0, 0, 0);
    }
    else
    {
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v6, 0, 0, 0);
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400228e0  sub     rsp, 48h
0x1400228e4  mov     rdx, [rcx+48h]
0x1400228e8  mov     rax, [rdx+28h]
0x1400228ec  mov     r8, [rax+28h]
0x1400228f0  mov     rax, [rdx+30h]
0x1400228f4  xor     edx, edx
0x1400228f6  mov     [rsp+48h+arg_0], rdx
0x1400228fb  mov     eax, [rax+8]
0x1400228fe  test    al, 20h
0x140022900  jz      short loc_14002290A
0x140022902  mov     eax, edx
0x140022904  add     rsp, 48h
0x140022908  retn
0x14002290a  lea     rax, FlushDispatch
0x140022911  xor     r9d, r9d
0x140022914  mov     [rsp+48h+var_10], rax
0x140022919  mov     [rsp+48h+var_18], 9E0h
0x140022921  mov     [rsp+48h+var_20], r8
0x140022926  xor     r8d, r8d
0x140022929  mov     [rsp+48h+var_28], rdx
0x14002292e  mov     rdx, rcx
0x140022931  lea     rcx, [rsp+48h+arg_0]
0x140022936  call    cs:__imp_SmbCeInitializeExchange
0x14002293d  nop     dword ptr [rax+rax+00h]
0x140022942  test    eax, eax
0x140022944  jnz     short loc_14002299D
0x140022946  mov     rax, [rsp+48h+arg_0]
0x14002294b  mov     [rsp+48h+var_8], rbx
0x140022950  lock or dword ptr [rax+44h], 1
0x140022955  mov     rcx, [rsp+48h+arg_0]
0x14002295a  call    cs:__imp_SmbCeInitiateExchange
0x140022961  nop     dword ptr [rax+rax+00h]
0x140022966  mov     rcx, [rsp+48h+arg_0]
0x14002296b  xor     r9d, r9d
0x14002296e  xor     r8d, r8d
0x140022971  xor     edx, edx
0x140022973  mov     ebx, eax
0x140022975  cmp     eax, 103h
0x14002297a  jnz     short loc_14002298A
0x14002297c  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140022983  nop     dword ptr [rax+rax+00h]
0x140022988  jmp     short loc_140022998
0x14002298a  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140022991  nop     dword ptr [rax+rax+00h]
0x140022996  mov     eax, ebx
0x140022998  mov     rbx, [rsp+48h+var_8]
0x14002299d  add     rsp, 48h
0x1400229a1  retn
```
