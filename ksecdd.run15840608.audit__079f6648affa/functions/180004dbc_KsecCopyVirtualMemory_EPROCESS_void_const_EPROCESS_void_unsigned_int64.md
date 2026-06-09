# KsecCopyVirtualMemory(_EPROCESS *,void const *,_EPROCESS *,void *,unsigned __int64)

- ea: `0x180004dbc`
- end: `0x180004e74`
- name: `?KsecCopyVirtualMemory@@YAJPEAU_EPROCESS@@PEBX0PEAX_K@Z`
- size: `184`
- prototype: `int(struct _EPROCESS *, const void *, struct _EPROCESS *, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e7c`

## callees

- `0x180004dbc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x180004e01`
- `ntoskrnl!ProbeForRead` at `0x180004e17`
- `ntoskrnl!ProbeForRead` at `0x180004e01`
- `ntoskrnl!ProbeForRead` at `0x180004e17`
- `ntoskrnl!MmCopyVirtualMemory` at `0x180004e48`
- `ntoskrnl!MmCopyVirtualMemory` at `0x180004e48`

## pseudocode

```c
__int64 __fastcall KsecCopyVirtualMemory(
        struct _EPROCESS *a1,
        volatile void *a2,
        struct _EPROCESS *a3,
        void *a4,
        SIZE_T a5)
{
  unsigned int v9; // edi
  SIZE_T v10; // rbx
  char v12; // [rsp+28h] [rbp-60h]
  _QWORD v13[8]; // [rsp+48h] [rbp-40h] BYREF

  v13[0] = 0;
  v9 = 0;
  v10 = a5;
  if ( a5 <= 1 )
    v10 = 1;
  ProbeForRead(a4, v10, 1u);
  ProbeForRead(a2, v10, 1u);
  if ( a5 )
  {
    v12 = 1;
    return (unsigned int)MmCopyVirtualMemory(a1, a2, a3, a4, a5, v12, v13);
  }
  return v9;
}

```

## disassembly

```asm
0x180004dbc  push    rbx
0x180004dbe  push    rsi
0x180004dbf  push    rdi
0x180004dc0  push    r12
0x180004dc2  push    r13
0x180004dc4  push    r14
0x180004dc6  push    r15
0x180004dc8  sub     rsp, 50h
0x180004dcc  mov     r14, r9
0x180004dcf  mov     r12, r8
0x180004dd2  mov     r15, rdx
0x180004dd5  mov     r13, rcx
0x180004dd8  mov     [rsp+88h+var_40], 0
0x180004de1  xor     edi, edi
0x180004de3  mov     rsi, [rsp+88h+arg_20]
0x180004deb  mov     rbx, rsi
0x180004dee  lea     eax, [rdi+1]
0x180004df1  cmp     rsi, rax
0x180004df4  cmovbe  rbx, rax
0x180004df8  mov     r8d, eax; Alignment
0x180004dfb  mov     rdx, rbx; Length
0x180004dfe  mov     rcx, r9; Address
0x180004e01  call    cs:__imp_ProbeForRead
0x180004e08  nop     dword ptr [rax+rax+00h]
0x180004e0d  lea     r8d, [rdi+1]; Alignment
0x180004e11  mov     rdx, rbx; Length
0x180004e14  mov     rcx, r15; Address
0x180004e17  call    cs:__imp_ProbeForRead
0x180004e1e  nop     dword ptr [rax+rax+00h]
0x180004e23  test    rsi, rsi
0x180004e26  jz      short loc_180004E5A
0x180004e28  lea     rax, [rsp+88h+var_40]
0x180004e2d  mov     [rsp+88h+var_58], rax
0x180004e32  mov     [rsp+88h+var_60], 1
0x180004e37  mov     [rsp+88h+var_68], rsi
0x180004e3c  mov     r9, r14
0x180004e3f  mov     r8, r12
0x180004e42  mov     rdx, r15
0x180004e45  mov     rcx, r13
0x180004e48  call    cs:__imp_MmCopyVirtualMemory
0x180004e4f  nop     dword ptr [rax+rax+00h]
0x180004e54  mov     edi, eax
0x180004e56  mov     [rsp+88h+var_48], eax
0x180004e5a  mov     eax, edi
0x180004e5c  jmp     short loc_180004E63
0x180004e5e  mov     eax, 0C0000005h
0x180004e63  add     rsp, 50h
0x180004e67  pop     r15
0x180004e69  pop     r14
0x180004e6b  pop     r13
0x180004e6d  pop     r12
0x180004e6f  pop     rdi
0x180004e70  pop     rsi
0x180004e71  pop     rbx
0x180004e72  retn
```
