# Smb2UpdateIncomingSignature

- ea: `0x1400336ac`
- end: `0x1400336ff`
- name: `Smb2UpdateIncomingSignature`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d140`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x1400336c3`
- `ksecdd!BCryptHashData` at `0x1400336c3`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x1400336e5`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x1400336e5`

## pseudocode

```c
__int64 __fastcall Smb2UpdateIncomingSignature(__int64 a1, UCHAR *a2, ULONG a3)
{
  unsigned int v4; // ebx

  v4 = BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a1 + 792), a2, a3, 0);
  SmbCseUpdateBufferContextStatus(a1, v4);
  return v4;
}

```

## disassembly

```asm
0x1400336ac  mov     [rsp+arg_8], rbx
0x1400336b1  push    rdi
0x1400336b2  sub     rsp, 20h
0x1400336b6  mov     rdi, rcx
0x1400336b9  xor     r9d, r9d; dwFlags
0x1400336bc  mov     rcx, [rcx+318h]; hHash
0x1400336c3  call    cs:__imp_BCryptHashData
0x1400336ca  nop     dword ptr [rax+rax+00h]
0x1400336cf  mov     dword ptr [rsp+28h+arg_0+4], 0
0x1400336d7  mov     rcx, rdi
0x1400336da  mov     dword ptr [rsp+28h+arg_0], eax
0x1400336de  mov     ebx, eax
0x1400336e0  mov     rdx, [rsp+28h+arg_0]
0x1400336e5  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x1400336ec  nop     dword ptr [rax+rax+00h]
0x1400336f1  mov     eax, ebx
0x1400336f3  mov     rbx, [rsp+28h+arg_8]
0x1400336f8  add     rsp, 20h
0x1400336fc  pop     rdi
0x1400336fd  retn
```
