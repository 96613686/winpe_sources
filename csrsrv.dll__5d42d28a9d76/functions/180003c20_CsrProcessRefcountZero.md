# CsrProcessRefcountZero

- ea: `0x180003c20`
- end: `0x180003cb1`
- name: `CsrProcessRefcountZero`
- size: `145`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003670`
- `0x1800036c0`
- `0x180003780`
- `0x180003830`
- `0x180003930`
- `0x180003a20`
- `0x180003bb0`

## callees

- `0x180003c20`
- `0x180003cc0`
- `0x180003de0`

## import_xrefs

- `ntdll!NtClose` at `0x180003c5a`
- `ntdll!NtClose` at `0x180003c88`
- `ntdll!NtClose` at `0x180003c5a`
- `ntdll!NtClose` at `0x180003c88`
- `ntdll!RtlFreeHeap` at `0x180003ca5`
- `ntdll!NtAlpcDeleteSectionView` at `0x180003c78`
- `ntdll!NtAlpcDeleteSectionView` at `0x180003c78`
- `ntdll!NtAlpcDisconnectPort` at `0x180003c4a`
- `ntdll!NtAlpcDisconnectPort` at `0x180003c4a`

## pseudocode

```c
BOOLEAN __fastcall CsrProcessRefcountZero(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // r8

  CsrRemoveProcess();
  v2 = *(_QWORD *)(a1 + 48);
  if ( v2 )
    CsrDereferenceNtSession(v2);
  v3 = *(_QWORD *)(a1 + 56);
  if ( v3 )
  {
    NtAlpcDisconnectPort(v3, 1);
    NtClose(*(HANDLE *)(a1 + 56));
  }
  v4 = *(_QWORD *)(a1 + 64);
  if ( v4 )
    NtAlpcDeleteSectionView(CsrApiPort, 0, v4);
  NtClose(*(HANDLE *)(a1 + 80));
  return RtlFreeHeap(CsrHeap, 0, (PVOID)a1);
}

```

## disassembly

```asm
0x180003c20  push    rbx
0x180003c22  sub     rsp, 20h
0x180003c26  mov     rbx, rcx
0x180003c29  call    CsrRemoveProcess
0x180003c2e  mov     rcx, [rbx+30h]
0x180003c32  test    rcx, rcx
0x180003c35  jz      short loc_180003C3C
0x180003c37  call    CsrDereferenceNtSession
0x180003c3c  mov     rcx, [rbx+38h]
0x180003c40  test    rcx, rcx
0x180003c43  jz      short loc_180003C66
0x180003c45  mov     edx, 1
0x180003c4a  call    cs:__imp_NtAlpcDisconnectPort
0x180003c51  nop     dword ptr [rax+rax+00h]
0x180003c56  mov     rcx, [rbx+38h]; Handle
0x180003c5a  call    cs:__imp_NtClose
0x180003c61  nop     dword ptr [rax+rax+00h]
0x180003c66  mov     r8, [rbx+40h]
0x180003c6a  test    r8, r8
0x180003c6d  jz      short loc_180003C84
0x180003c6f  mov     rcx, cs:CsrApiPort
0x180003c76  xor     edx, edx
0x180003c78  call    cs:__imp_NtAlpcDeleteSectionView
0x180003c7f  nop     dword ptr [rax+rax+00h]
0x180003c84  mov     rcx, [rbx+50h]; Handle
0x180003c88  call    cs:__imp_NtClose
0x180003c8f  nop     dword ptr [rax+rax+00h]
0x180003c94  mov     rcx, cs:CsrHeap
0x180003c9b  mov     r8, rbx
0x180003c9e  xor     edx, edx
0x180003ca0  add     rsp, 20h
0x180003ca4  pop     rbx
0x180003ca5  jmp     cs:__imp_RtlFreeHeap
```
