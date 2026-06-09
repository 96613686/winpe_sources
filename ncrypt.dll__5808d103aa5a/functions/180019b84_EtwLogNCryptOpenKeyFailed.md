# EtwLogNCryptOpenKeyFailed

- ea: `0x180019b84`
- end: `0x180019bd2`
- name: `EtwLogNCryptOpenKeyFailed`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f290`

## callees

- `0x18000f098`
- `0x18000f7b0`
- `0x180019b84`

## pseudocode

```c
ULONG __fastcall EtwLogNCryptOpenKeyFailed(const wchar_t *a1, const wchar_t *a2, char a3)
{
  const wchar_t *ProcessName; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx

  if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 1) == 0 )
    return 0;
  ProcessName = (const wchar_t *)I_GetProcessName();
  return McTemplateU0zzdz_EventWriteTransfer(v8, v7, a1, a2, a3, ProcessName);
}

```

## disassembly

```asm
0x180019b84  mov     [rsp+arg_0], rbx
0x180019b89  mov     [rsp+arg_8], rsi
0x180019b8e  push    rdi
0x180019b8f  sub     rsp, 30h
0x180019b93  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 1
0x180019b9a  mov     ebx, r8d
0x180019b9d  mov     rdi, rdx
0x180019ba0  mov     rsi, rcx
0x180019ba3  jz      short loc_180019BC0
0x180019ba5  call    I_GetProcessName
0x180019baa  mov     [rsp+38h+var_10], rax
0x180019baf  mov     r9, rdi
0x180019bb2  mov     r8, rsi
0x180019bb5  mov     [rsp+38h+var_18], ebx
0x180019bb9  call    McTemplateU0zzdz_EventWriteTransfer
0x180019bbe  jmp     short loc_180019BC2
0x180019bc0  xor     eax, eax
0x180019bc2  mov     rbx, [rsp+38h+arg_0]
0x180019bc7  mov     rsi, [rsp+38h+arg_8]
0x180019bcc  add     rsp, 30h
0x180019bd0  pop     rdi
0x180019bd1  retn
```
