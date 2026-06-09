# Smb2Write_RdmaDirectWriteComplete

- ea: `0x140031180`
- end: `0x140031243`
- name: `Smb2Write_RdmaDirectWriteComplete`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14001e470`
- `0x140031180`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14003119e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14003119e`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140031221`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140031221`
- `mrxsmb!SmbCseRdmaDirectWriteComplete` at `0x140031230`
- `mrxsmb!SmbCseRdmaDirectWriteComplete` at `0x140031230`

## pseudocode

```c
__int64 __fastcall Smb2Write_RdmaDirectWriteComplete(__int64 a1, __int64 a2)
{
  int v3; // eax
  __int64 v4; // r8

  if ( (int)a1 < 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)(a2 + 56) + 68LL), 0x2000u);
    *(_DWORD *)(a2 + 748) = 0;
    SmbCseUpdateBufferContextStatus(a2, 3221225996LL);
  }
  else
  {
    v3 = *(_DWORD *)(a2 + 1396);
    *(_DWORD *)(a2 + 4) |= 0x400u;
    *(_DWORD *)(a2 + 748) = v3;
    if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 64) & 1) != 0 && *(_QWORD *)(a2 + 848) )
    {
      v4 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 56) + 88LL) + 424LL);
      Smb2Write_UpdatePerfCounters(
        *(_QWORD *)(v4 + 1480) + 192LL * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v4 + 1488)),
        a2);
    }
  }
  return SmbCseRdmaDirectWriteComplete(a2);
}

```

## disassembly

```asm
0x140031180  push    rbx
0x140031182  sub     rsp, 20h
0x140031186  mov     rbx, rdx
0x140031189  test    ecx, ecx
0x14003118b  js      short loc_1400311F3
0x14003118d  mov     eax, [rdx+574h]
0x140031193  bts     dword ptr [rdx+4], 0Ah
0x140031198  mov     [rdx+2ECh], eax
0x14003119e  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400311a5  nop     dword ptr [rax+rax+00h]
0x1400311aa  test    byte ptr [rax+40h], 1
0x1400311ae  jz      short loc_14003122D
0x1400311b0  cmp     qword ptr [rbx+350h], 0
0x1400311b8  jz      short loc_14003122D
0x1400311ba  mov     rax, [rbx+38h]
0x1400311be  xor     edx, edx
0x1400311c0  mov     rcx, [rax+58h]
0x1400311c4  mov     eax, gs:1A4h
0x1400311cc  mov     r8, [rcx+1A8h]
0x1400311d3  div     dword ptr [r8+5D0h]
0x1400311da  lea     rcx, [rdx+rdx*2]
0x1400311de  mov     rdx, rbx
0x1400311e1  shl     rcx, 6
0x1400311e5  add     rcx, [r8+5C8h]
0x1400311ec  call    Smb2Write_UpdatePerfCounters
0x1400311f1  jmp     short loc_14003122D
0x1400311f3  mov     rax, [rdx+38h]
0x1400311f7  lock or dword ptr [rax+44h], 2000h
0x1400311ff  mov     dword ptr [rdx+2ECh], 0
0x140031209  mov     rcx, rbx
0x14003120c  mov     dword ptr [rsp+28h+arg_8], 0C000020Ch
0x140031214  mov     dword ptr [rsp+28h+arg_8+4], 0
0x14003121c  mov     rdx, [rsp+28h+arg_8]
0x140031221  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x140031228  nop     dword ptr [rax+rax+00h]
0x14003122d  mov     rcx, rbx
0x140031230  call    cs:__imp_SmbCseRdmaDirectWriteComplete
0x140031237  nop     dword ptr [rax+rax+00h]
0x14003123c  add     rsp, 20h
0x140031240  pop     rbx
0x140031241  retn
```
