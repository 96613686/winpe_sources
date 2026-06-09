# EtwLogNCryptOperationFailed

- ea: `0x180010684`
- end: `0x1800106dd`
- name: `EtwLogNCryptOperationFailed`
- size: `89`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008820`
- `0x18000a3d0`
- `0x18000ba30`
- `0x18000c5b0`
- `0x18000d100`
- `0x180010a90`
- `0x180010c90`
- `0x180011f00`
- `0x180012e00`
- `0x1800140b0`
- `0x1800147a0`
- `0x180016620`
- `0x180017990`
- `0x18001bed0`
- `0x18001c0b0`
- `0x18001c3a0`

## callees

- `0x18000f098`
- `0x18000f148`
- `0x180010684`

## pseudocode

```c
ULONG __fastcall EtwLogNCryptOperationFailed(int a1, const wchar_t *a2, const wchar_t *a3, __int64 a4, char a5)
{
  const wchar_t *ProcessName; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v12; // [rsp+28h] [rbp-30h]
  int v13; // [rsp+30h] [rbp-28h]

  if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 1) == 0 )
    return 0;
  ProcessName = (const wchar_t *)I_GetProcessName();
  return McTemplateU0qzzzzdz_EventWriteTransfer(v10, v9, a1, a2, a3, v12, v13, a5, ProcessName);
}

```

## disassembly

```asm
0x180010684  mov     [rsp+arg_0], rbx
0x180010689  mov     [rsp+arg_8], rsi
0x18001068e  push    rdi
0x18001068f  sub     rsp, 50h
0x180010693  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 1
0x18001069a  mov     rbx, r8
0x18001069d  mov     rdi, rdx
0x1800106a0  mov     esi, ecx
0x1800106a2  jz      short loc_1800106D9
0x1800106a4  call    I_GetProcessName
0x1800106a9  mov     [rsp+58h+var_18], rax
0x1800106ae  mov     r9, rdi
0x1800106b1  mov     eax, [rsp+58h+arg_20]
0x1800106b8  mov     r8d, esi
0x1800106bb  mov     [rsp+58h+var_20], eax
0x1800106bf  mov     [rsp+58h+var_38], rbx
0x1800106c4  call    McTemplateU0qzzzzdz_EventWriteTransfer
0x1800106c9  mov     rbx, [rsp+58h+arg_0]
0x1800106ce  mov     rsi, [rsp+58h+arg_8]
0x1800106d3  add     rsp, 50h
0x1800106d7  pop     rdi
0x1800106d8  retn
0x1800106d9  xor     eax, eax
0x1800106db  jmp     short loc_1800106C9
```
