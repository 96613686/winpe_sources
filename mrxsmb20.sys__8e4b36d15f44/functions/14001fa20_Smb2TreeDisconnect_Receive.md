# Smb2TreeDisconnect_Receive

- ea: `0x14001fa20`
- end: `0x14001fa79`
- name: `Smb2TreeDisconnect_Receive`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14001fa20`

## import_xrefs

- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001fa65`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001fa65`

## pseudocode

```c
__int64 __fastcall Smb2TreeDisconnect_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _DWORD *a6,
        __int64 a7)
{
  unsigned int v7; // eax

  v7 = *(_DWORD *)(a3 + 16);
  if ( !v7 && (a4 < 0x44 || *(_WORD *)(a7 + 64) != 4) )
    v7 = -1073741629;
  *a6 = a5;
  SmbCseUpdateBufferContextStatus(a2, v7);
  return 0;
}

```

## disassembly

```asm
0x14001fa20  sub     rsp, 28h
0x14001fa24  mov     eax, [r8+10h]
0x14001fa28  mov     r10, rdx
0x14001fa2b  test    eax, eax
0x14001fa2d  jnz     short loc_14001FA46
0x14001fa2f  cmp     r9d, 44h ; 'D'
0x14001fa33  jb      short loc_14001FA41
0x14001fa35  mov     rcx, [rsp+28h+arg_30]
0x14001fa3a  cmp     word ptr [rcx+40h], 4
0x14001fa3f  jz      short loc_14001FA46
0x14001fa41  mov     eax, 0C00000C3h
0x14001fa46  mov     rdx, [rsp+28h+arg_28]
0x14001fa4b  mov     ecx, [rsp+28h+arg_20]
0x14001fa4f  mov     dword ptr [rsp+28h+arg_28], eax
0x14001fa53  mov     dword ptr [rsp+28h+arg_28+4], 0
0x14001fa5b  mov     [rdx], ecx
0x14001fa5d  mov     rcx, r10
0x14001fa60  mov     rdx, [rsp+28h+arg_28]
0x14001fa65  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14001fa6c  nop     dword ptr [rax+rax+00h]
0x14001fa71  xor     eax, eax
0x14001fa73  add     rsp, 28h
0x14001fa77  retn
```
