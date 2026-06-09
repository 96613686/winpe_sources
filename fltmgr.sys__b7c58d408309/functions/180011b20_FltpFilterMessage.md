# FltpFilterMessage

- ea: `0x180011b20`
- end: `0x180011d04`
- name: `FltpFilterMessage`
- size: `484`
- prototype: `__int64 __fastcall(__int64, volatile void *, unsigned int, volatile void *, unsigned int Length, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180060110`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x180011b20`
- `0x180024880`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x180011c7d`
- `ntoskrnl!ProbeForRead` at `0x180011c7d`
- `ntoskrnl!ProbeForWrite` at `0x180011c9d`
- `ntoskrnl!ProbeForWrite` at `0x180011c9d`
- `ntoskrnl!ExAcquireRundownProtection` at `0x180011bb5`
- `ntoskrnl!ExAcquireRundownProtection` at `0x180011bb5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x180011c3a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x180011c3a`

## pseudocode

```c
__int64 __fastcall FltpFilterMessage(
        __int64 a1,
        volatile void *a2,
        unsigned int a3,
        volatile void *a4,
        unsigned int Length,
        __int64 a6,
        char a7)
{
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(_QWORD, volatile void *, _QWORD, volatile void *, _QWORD, __int64); // rsi
  unsigned int v11; // r12d
  NTSTATUS v12; // eax
  unsigned int v13; // r14d
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 (__fastcall *v17)(_QWORD, volatile void *, _QWORD, volatile void *, _QWORD, __int64, bool); // [rsp+70h] [rbp+8h]

  v8 = *(_QWORD *)(a1 + 32);
  v9 = *(_QWORD *)(*(_QWORD *)(v8 + 8) + 16LL);
  v10 = *(__int64 (__fastcall **)(_QWORD, volatile void *, _QWORD, volatile void *, _QWORD, __int64))(v9 + 32);
  v17 = *(__int64 (__fastcall **)(_QWORD, volatile void *, _QWORD, volatile void *, _QWORD, __int64, bool))(v9 + 40);
  if ( !v10 && !*(_QWORD *)(v9 + 40) )
    return 3221225488LL;
  if ( a7 || !v10 )
  {
    v11 = Length;
  }
  else
  {
    ProbeForRead(a2, a3, 1u);
    v11 = Length;
    ProbeForWrite(a4, Length, 1u);
  }
  v12 = FltObjectReference(*(PVOID *)(v9 + 48));
  if ( (int)FltpDbgStatus(v12) < 0 )
  {
    return (unsigned int)-1073741769;
  }
  else
  {
    v13 = 0;
    if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(v8 + 8) + 32LL)) )
      v13 = -1073741769;
    if ( (int)FltpDbgStatus(v13) >= 0 )
    {
      v14 = *(_QWORD *)(v8 + 8);
      if ( v10 )
        v15 = v10(*(_QWORD *)(v14 + 24), a2, a3, a4, v11, a6);
      else
        v15 = v17(*(_QWORD *)(v14 + 24), a2, a3, a4, v11, a6, a7 == 0);
      v13 = v15;
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(v8 + 8) + 32LL));
    }
    FltObjectDereference(*(PVOID *)(v9 + 48));
  }
  return v13;
}

```

## disassembly

```asm
0x180011b20  mov     [rsp+arg_18], rbx
0x180011b25  mov     [rsp+arg_10], r8d
0x180011b2a  mov     [rsp+arg_8], rdx
0x180011b2f  push    rsi
0x180011b30  push    rdi
0x180011b31  push    r12
0x180011b33  push    r13
0x180011b35  push    r14
0x180011b37  sub     rsp, 40h
0x180011b3b  mov     r13, r9
0x180011b3e  mov     r9, rdx
0x180011b41  mov     rbx, [rcx+20h]
0x180011b45  mov     rax, [rbx+8]
0x180011b49  mov     rdi, [rax+10h]
0x180011b4d  mov     rsi, [rdi+20h]
0x180011b51  mov     rax, [rdi+28h]
0x180011b55  mov     [rsp+68h+arg_0], rax
0x180011b5a  test    rsi, rsi
0x180011b5d  jz      loc_180011CB0
0x180011b63  cmp     [rsp+68h+arg_30], 0
0x180011b6b  jz      loc_180011C68
0x180011b71  mov     r12d, dword ptr [rsp+68h+Length]
0x180011b79  mov     rcx, [rdi+30h]; FltObject
0x180011b7d  call    FltObjectReference
0x180011b82  mov     r8d, 0AD6h
0x180011b88  mov     [rsp+68h+var_48], 0
0x180011b91  mov     r9d, 0C01C000Bh
0x180011b97  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x180011b9e  mov     ecx, eax
0x180011ba0  call    FltpDbgStatus
0x180011ba5  test    eax, eax
0x180011ba7  js      loc_180011CF9
0x180011bad  mov     rcx, [rbx+8]
0x180011bb1  add     rcx, 20h ; ' '; RunRef
0x180011bb5  call    cs:__imp_ExAcquireRundownProtection
0x180011bbc  nop     dword ptr [rax+rax+00h]
0x180011bc1  xor     r14d, r14d
0x180011bc4  mov     ecx, 0C0000037h
0x180011bc9  test    al, al
0x180011bcb  cmovz   r14d, ecx
0x180011bcf  mov     r8d, 0ADFh
0x180011bd5  mov     [rsp+68h+var_48], 0
0x180011bde  mov     r9d, ecx
0x180011be1  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x180011be8  mov     ecx, r14d
0x180011beb  call    FltpDbgStatus
0x180011bf0  test    eax, eax
0x180011bf2  js      short loc_180011C46
0x180011bf4  mov     rax, [rbx+8]
0x180011bf8  mov     r9, r13
0x180011bfb  mov     r8d, [rsp+68h+arg_10]
0x180011c03  test    rsi, rsi
0x180011c06  jz      loc_180011CC0
0x180011c0c  mov     rdx, [rsp+68h+arg_28]
0x180011c14  mov     [rsp+68h+var_40], rdx
0x180011c19  mov     dword ptr [rsp+68h+var_48], r12d
0x180011c1e  mov     rdx, [rsp+68h+arg_8]
0x180011c23  mov     rcx, [rax+18h]
0x180011c27  mov     rax, rsi
0x180011c2a  call    _guard_dispatch_icall
0x180011c2f  mov     r14d, eax
0x180011c32  mov     rcx, [rbx+8]
0x180011c36  add     rcx, 20h ; ' '; RunRef
0x180011c3a  call    cs:__imp_ExReleaseRundownProtection
0x180011c41  nop     dword ptr [rax+rax+00h]
0x180011c46  mov     rcx, [rdi+30h]; FltObject
0x180011c4a  call    FltObjectDereference
0x180011c4f  mov     eax, r14d
0x180011c52  mov     rbx, [rsp+68h+arg_18]
0x180011c5a  add     rsp, 40h
0x180011c5e  pop     r14
0x180011c60  pop     r13
0x180011c62  pop     r12
0x180011c64  pop     rdi
0x180011c65  pop     rsi
0x180011c66  retn
0x180011c68  test    rsi, rsi
0x180011c6b  jz      loc_180011B71
0x180011c71  mov     edx, r8d; Length
0x180011c74  mov     r8d, 1; Alignment
0x180011c7a  mov     rcx, r9; Address
0x180011c7d  call    cs:__imp_ProbeForRead
0x180011c84  nop     dword ptr [rax+rax+00h]
0x180011c89  mov     r12d, dword ptr [rsp+68h+Length]
0x180011c91  mov     edx, r12d; Length
0x180011c94  mov     r8d, 1; Alignment
0x180011c9a  mov     rcx, r13; Address
0x180011c9d  call    cs:__imp_ProbeForWrite
0x180011ca4  nop     dword ptr [rax+rax+00h]
0x180011ca9  jmp     loc_180011B79
0x180011cae  jmp     short loc_180011C52
0x180011cb0  test    rax, rax
0x180011cb3  jnz     loc_180011B63
0x180011cb9  mov     eax, 0C0000010h
0x180011cbe  jmp     short loc_180011C52
0x180011cc0  cmp     [rsp+68h+arg_30], 0
0x180011cc8  setz    cl
0x180011ccb  mov     [rsp+68h+var_38], cl
0x180011ccf  mov     rcx, [rsp+68h+arg_28]
0x180011cd7  mov     [rsp+68h+var_40], rcx
0x180011cdc  mov     dword ptr [rsp+68h+var_48], r12d
0x180011ce1  mov     rdx, [rsp+68h+arg_8]
0x180011ce6  mov     rcx, [rax+18h]
0x180011cea  mov     rax, [rsp+68h+arg_0]
0x180011cef  call    _guard_dispatch_icall
0x180011cf4  jmp     loc_180011C2F
0x180011cf9  mov     r14d, 0C0000037h
0x180011cff  jmp     loc_180011C4F
```
