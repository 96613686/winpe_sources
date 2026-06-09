# EtwLogNCryptCreateKeyFailed

- ea: `0x18001b728`
- end: `0x18001b77c`
- name: `EtwLogNCryptCreateKeyFailed`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800175f0`

## callees

- `0x18000f098`
- `0x180016c78`
- `0x18001b728`

## pseudocode

```c
ULONG __fastcall EtwLogNCryptCreateKeyFailed(const wchar_t *a1, const wchar_t *a2, const wchar_t *a3, char a4, char a5)
{
  const wchar_t *ProcessName; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx

  if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 1) == 0 )
    return 0;
  ProcessName = (const wchar_t *)I_GetProcessName();
  return McTemplateU0zzzddz_EventWriteTransfer(v11, v10, a1, a2, a3, a4, a5, ProcessName);
}

```

## disassembly

```asm
0x18001b728  push    rbx
0x18001b72a  push    rbp
0x18001b72b  push    rsi
0x18001b72c  push    rdi
0x18001b72d  sub     rsp, 48h
0x18001b731  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 1
0x18001b738  mov     ebx, r9d
0x18001b73b  mov     rdi, r8
0x18001b73e  mov     rsi, rdx
0x18001b741  mov     rbp, rcx
0x18001b744  jz      short loc_18001B771
0x18001b746  call    I_GetProcessName
0x18001b74b  mov     [rsp+68h+var_30], rax
0x18001b750  mov     r9, rsi
0x18001b753  mov     eax, [rsp+68h+arg_20]
0x18001b75a  mov     r8, rbp
0x18001b75d  mov     [rsp+68h+var_38], eax
0x18001b761  mov     [rsp+68h+var_40], ebx
0x18001b765  mov     [rsp+68h+var_48], rdi
0x18001b76a  call    McTemplateU0zzzddz_EventWriteTransfer
0x18001b76f  jmp     short loc_18001B773
0x18001b771  xor     eax, eax
0x18001b773  add     rsp, 48h
0x18001b777  pop     rdi
0x18001b778  pop     rsi
0x18001b779  pop     rbp
0x18001b77a  pop     rbx
0x18001b77b  retn
```
