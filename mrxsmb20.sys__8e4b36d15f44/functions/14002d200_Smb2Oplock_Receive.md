# Smb2Oplock_Receive

- ea: `0x14002d200`
- end: `0x14002d286`
- name: `Smb2Oplock_Receive`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x14002d200`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002d23b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002d23b`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002d224`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002d224`

## pseudocode

```c
__int64 __fastcall Smb2Oplock_Receive(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, _DWORD *a6)
{
  __int64 v7; // rcx

  SmbCseUpdateBufferContextStatus(a2, *(unsigned int *)(a3 + 16));
  *a6 = a5;
  if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v7) + 64) & 1) != 0 )
    _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                    * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                   % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL)
                                                                               + 1488LL))
                                                    + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                    + 84));
  return 0;
}

```

## disassembly

```asm
0x14002d200  push    rbx
0x14002d202  sub     rsp, 20h
0x14002d206  mov     eax, [r8+10h]
0x14002d20a  mov     r9, rdx
0x14002d20d  mov     dword ptr [rsp+28h+arg_10], eax
0x14002d211  mov     rbx, rcx
0x14002d214  mov     dword ptr [rsp+28h+arg_10+4], 0
0x14002d21c  mov     rcx, r9
0x14002d21f  mov     rdx, [rsp+28h+arg_10]
0x14002d224  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14002d22b  nop     dword ptr [rax+rax+00h]
0x14002d230  mov     rdx, [rsp+28h+arg_28]
0x14002d235  mov     eax, [rsp+28h+arg_20]
0x14002d239  mov     [rdx], eax
0x14002d23b  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14002d242  nop     dword ptr [rax+rax+00h]
0x14002d247  test    byte ptr [rax+40h], 1
0x14002d24b  jz      short loc_14002D27D
0x14002d24d  mov     rax, [rbx+58h]
0x14002d251  xor     edx, edx
0x14002d253  mov     r8, [rax+1A8h]
0x14002d25a  mov     eax, gs:1A4h
0x14002d262  div     dword ptr [r8+5D0h]
0x14002d269  mov     rax, [r8+5C8h]
0x14002d270  lea     rdx, [rdx+rdx*2]
0x14002d274  shl     rdx, 6
0x14002d278  lock inc dword ptr [rdx+rax+54h]
0x14002d27d  xor     eax, eax
0x14002d27f  add     rsp, 20h
0x14002d283  pop     rbx
0x14002d284  retn
```
