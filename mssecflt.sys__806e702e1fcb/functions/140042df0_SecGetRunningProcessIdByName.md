# SecGetRunningProcessIdByName

- ea: `0x140042df0`
- end: `0x140042e86`
- name: `SecGetRunningProcessIdByName`
- size: `150`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002dc0c`

## callees

- `0x140009b80`
- `0x140042d34`
- `0x140042df0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140042e35`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140042e35`

## pseudocode

```c
__int64 __fastcall SecGetRunningProcessIdByName(PCUNICODE_STRING String1, _QWORD *a2)
{
  unsigned int v4; // esi
  unsigned int *AllRunningProcesses; // rdi
  unsigned int *v6; // rbx
  __int64 v8; // rax

  v4 = -1073741275;
  AllRunningProcesses = (unsigned int *)SecGetAllRunningProcesses();
  v6 = AllRunningProcesses;
  if ( !AllRunningProcesses )
    return 3221225626LL;
  while ( RtlCompareUnicodeString(String1, (PCUNICODE_STRING)(v6 + 14), 1u) )
  {
    v8 = *v6;
    if ( (_DWORD)v8 )
    {
      v6 = (unsigned int *)((char *)v6 + v8);
      if ( v6 )
        continue;
    }
    goto LABEL_8;
  }
  v4 = 0;
  *a2 = *((_QWORD *)v6 + 10);
LABEL_8:
  SecFreePool(AllRunningProcesses, 0x42747053u);
  return v4;
}

```

## disassembly

```asm
0x140042df0  mov     rax, rsp
0x140042df3  mov     [rax+8], rbx
0x140042df7  mov     [rax+10h], rbp
0x140042dfb  mov     [rax+18h], rsi
0x140042dff  mov     [rax+20h], rdi
0x140042e03  push    r14
0x140042e05  sub     rsp, 20h
0x140042e09  mov     r14, rdx
0x140042e0c  mov     rbp, rcx
0x140042e0f  mov     esi, 0C0000225h
0x140042e14  call    SecGetAllRunningProcesses
0x140042e19  mov     rdi, rax
0x140042e1c  mov     rbx, rax
0x140042e1f  test    rax, rax
0x140042e22  jnz     short loc_140042E2B
0x140042e24  mov     eax, 0C000009Ah
0x140042e29  jmp     short loc_140042E6A
0x140042e2b  lea     rdx, [rbx+38h]; String2
0x140042e2f  mov     r8b, 1; CaseInSensitive
0x140042e32  mov     rcx, rbp; String1
0x140042e35  call    cs:__imp_RtlCompareUnicodeString
0x140042e3c  nop     dword ptr [rax+rax+00h]
0x140042e41  test    eax, eax
0x140042e43  jz      short loc_140042E52
0x140042e45  mov     eax, [rbx]
0x140042e47  test    eax, eax
0x140042e49  jz      short loc_140042E5B
0x140042e4b  add     rbx, rax
0x140042e4e  jnz     short loc_140042E2B
0x140042e50  jmp     short loc_140042E5B
0x140042e52  mov     rax, [rbx+50h]
0x140042e56  xor     esi, esi
0x140042e58  mov     [r14], rax
0x140042e5b  mov     edx, 42747053h; Tag
0x140042e60  mov     rcx, rdi; P
0x140042e63  call    SecFreePool
0x140042e68  mov     eax, esi
0x140042e6a  mov     rbx, [rsp+28h+arg_0]
0x140042e6f  mov     rbp, [rsp+28h+arg_8]
0x140042e74  mov     rsi, [rsp+28h+arg_10]
0x140042e79  mov     rdi, [rsp+28h+arg_18]
0x140042e7e  add     rsp, 20h
0x140042e82  pop     r14
0x140042e84  retn
```
