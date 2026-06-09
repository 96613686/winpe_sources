# Smb2Read_CopyData

- ea: `0x14001b010`
- end: `0x14001b0b0`
- name: `Smb2Read_CopyData`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14001b010`

## import_xrefs

- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001b06c`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001b06c`

## pseudocode

```c
__int64 __fastcall Smb2Read_CopyData(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  if ( a4 < 0 )
  {
    SmbCseUpdateBufferContextStatus(a2, (unsigned int)a4);
    return 0;
  }
  else
  {
    if ( *(_DWORD *)(a1 + 1044) == 1
      && *(_BYTE *)(a1 + 1052)
      && (*(_DWORD *)(a1 + 68) & 0x1000800) == 0
      && (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 632LL) <= 1u || *(_QWORD *)(a1 + 200) % 0x23C34600uLL >= 0x4C4B40) )
    {
      _InterlockedOr((volatile signed __int32 *)(a1 + 68), 0x100000u);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14001b010  sub     rsp, 38h
0x14001b014  mov     rax, rdx
0x14001b017  test    r9d, r9d
0x14001b01a  js      short loc_14001B057
0x14001b01c  cmp     dword ptr [rcx+414h], 1
0x14001b023  jz      short loc_14001B02D
0x14001b025  xor     eax, eax
0x14001b027  add     rsp, 38h
0x14001b02b  retn
0x14001b02d  cmp     byte ptr [rcx+41Ch], 0
0x14001b034  jz      short loc_14001B025
0x14001b036  mov     eax, [rcx+44h]
0x14001b039  test    eax, 1000800h
0x14001b03e  jnz     short loc_14001B025
0x14001b040  mov     rax, [rcx+48h]
0x14001b044  cmp     dword ptr [rax+278h], 1
0x14001b04b  ja      short loc_14001B080
0x14001b04d  lock or dword ptr [rcx+44h], 100000h
0x14001b055  jmp     short loc_14001B025
0x14001b057  mov     dword ptr [rsp+38h+var_18], r9d
0x14001b05c  mov     rcx, rax
0x14001b05f  mov     dword ptr [rsp+38h+var_18+4], 0
0x14001b067  mov     rdx, [rsp+38h+var_18]
0x14001b06c  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14001b073  nop     dword ptr [rax+rax+00h]
0x14001b078  xor     eax, eax
0x14001b07a  add     rsp, 38h
0x14001b07e  retn
0x14001b080  mov     r8, [rcx+0C8h]
0x14001b087  mov     rax, 0E5109EC205D7BEA7h
0x14001b091  mul     r8
0x14001b094  shr     rdx, 1Dh
0x14001b098  imul    rax, rdx, 23C34600h
0x14001b09f  sub     r8, rax
0x14001b0a2  cmp     r8, 4C4B40h
0x14001b0a9  jnb     short loc_14001B04D
0x14001b0ab  jmp     loc_14001B025
```
