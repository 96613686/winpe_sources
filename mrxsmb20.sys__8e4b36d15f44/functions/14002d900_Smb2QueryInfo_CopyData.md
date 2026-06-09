# Smb2QueryInfo_CopyData

- ea: `0x14002d900`
- end: `0x14002d943`
- name: `Smb2QueryInfo_CopyData`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14002d900`

## import_xrefs

- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002d92f`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002d92f`

## pseudocode

```c
__int64 __fastcall Smb2QueryInfo_CopyData(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int v4; // eax

  v4 = -1073741629;
  if ( a3 >= *(_DWORD *)(a2 + 748) )
    v4 = a4;
  if ( v4 )
    SmbCseUpdateBufferContextStatus(a2, v4);
  return 0;
}

```

## disassembly

```asm
0x14002d900  sub     rsp, 28h
0x14002d904  cmp     r8d, [rdx+2ECh]
0x14002d90b  mov     eax, 0C00000C3h
0x14002d910  mov     r10, rdx
0x14002d913  cmovnb  eax, r9d
0x14002d917  test    eax, eax
0x14002d919  jz      short loc_14002D93B
0x14002d91b  mov     dword ptr [rsp+28h+arg_8], eax
0x14002d91f  mov     rcx, r10
0x14002d922  mov     dword ptr [rsp+28h+arg_8+4], 0
0x14002d92a  mov     rdx, [rsp+28h+arg_8]
0x14002d92f  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14002d936  nop     dword ptr [rax+rax+00h]
0x14002d93b  xor     eax, eax
0x14002d93d  add     rsp, 28h
0x14002d941  retn
```
