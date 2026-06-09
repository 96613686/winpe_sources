# Smb2IsCollectParsingFailureDiagThrottled

- ea: `0x140036458`
- end: `0x1400364d9`
- name: `Smb2IsCollectParsingFailureDiagThrottled`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140028000`

## callees

- `0x140036410`
- `0x140036458`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14003646d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14003646d`

## pseudocode

```c
bool __fastcall Smb2IsCollectParsingFailureDiagThrottled(__int64 a1, unsigned int a2)
{
  unsigned int v3; // esi
  char v4; // bl
  __int64 v5; // r9
  int v6; // r9d
  __int64 v7; // r8

  v3 = a1;
  v4 = 0;
  if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 451) )
  {
    v6 = *(_DWORD *)Smb2GetParsingFailureThrottlingSlot(v3, a2, MEMORY[0xFFFFF78000000008], v5);
    return (int)(v7 / 10000000) < v6;
  }
  return v4;
}

```

## disassembly

```asm
0x140036458  mov     [rsp+arg_0], rbx
0x14003645d  mov     [rsp+arg_8], rsi
0x140036462  push    rdi
0x140036463  sub     rsp, 20h
0x140036467  mov     edi, edx
0x140036469  mov     esi, ecx
0x14003646b  xor     bl, bl
0x14003646d  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140036474  nop     dword ptr [rax+rax+00h]
0x140036479  cmp     [rax+1C3h], bl
0x14003647f  jz      short loc_1400364C6
0x140036481  mov     r8, 0FFFFF78000000008h
0x14003648b  mov     edx, edi
0x14003648d  mov     ecx, esi
0x14003648f  mov     r8, [r8]
0x140036492  call    Smb2GetParsingFailureThrottlingSlot
0x140036497  movzx   ebx, bl
0x14003649a  mov     r9d, [rax]
0x14003649d  mov     rax, 0D6BF94D5E57A42BDh
0x1400364a7  imul    r8
0x1400364aa  mov     eax, 1
0x1400364af  add     rdx, r8
0x1400364b2  sar     rdx, 17h
0x1400364b6  mov     rcx, rdx
0x1400364b9  shr     rcx, 3Fh
0x1400364bd  add     rdx, rcx
0x1400364c0  cmp     edx, r9d
0x1400364c3  cmovl   ebx, eax
0x1400364c6  mov     rsi, [rsp+28h+arg_8]
0x1400364cb  mov     al, bl
0x1400364cd  mov     rbx, [rsp+28h+arg_0]
0x1400364d2  add     rsp, 20h
0x1400364d6  pop     rdi
0x1400364d7  retn
```
