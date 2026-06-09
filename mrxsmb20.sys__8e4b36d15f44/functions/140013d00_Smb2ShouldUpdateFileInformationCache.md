# Smb2ShouldUpdateFileInformationCache

- ea: `0x140013d00`
- end: `0x140013db1`
- name: `Smb2ShouldUpdateFileInformationCache`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x140013210`

## callees

- `0x140013d00`

## import_xrefs

- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140013d2a`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140013d2a`

## pseudocode

```c
bool __fastcall Smb2ShouldUpdateFileInformationCache(_QWORD *a1, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // r10
  __int64 v6; // r8
  char v7; // di
  __int64 InstanceConfigurationBlock; // rax
  char v9; // cl

  v4 = a1[7];
  v5 = *(_QWORD *)(v4 + 120);
  v6 = *(_QWORD *)(v5 + 32);
  if ( (*(_DWORD *)(v6 + 96) & 0x80u) != 0
    || (*(_BYTE *)(*(_QWORD *)(v6 + 32) + 764LL) & 2) == 0
    || (*(_DWORD *)(*(_QWORD *)(v4 + 136) + 8LL) & 1) != 0
    || *(_BYTE *)(v5 + 77)
    || (v7 = 1, (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1[9] + 40LL) + 40LL) + 424LL) + 184LL) & 0x800000) != 0) )
  {
    v7 = 0;
  }
  InstanceConfigurationBlock = MRxSmbGetInstanceConfigurationBlock(a1[10]);
  v9 = 0;
  if ( *(_DWORD *)(InstanceConfigurationBlock + 12) )
    v9 = v7;
  return ((unsigned int)(a2 - 4) <= 1 || (unsigned int)(a2 - 34) <= 1) && v9;
}

```

## disassembly

```asm
0x140013d00  mov     [rsp+arg_0], rbx
0x140013d05  push    rdi
0x140013d06  sub     rsp, 20h
0x140013d0a  mov     r9, rcx
0x140013d0d  mov     ebx, edx
0x140013d0f  mov     rcx, [rcx+38h]
0x140013d13  mov     r10, [rcx+78h]
0x140013d17  mov     r8, [r10+20h]
0x140013d1b  mov     eax, [r8+60h]
0x140013d1f  test    al, al
0x140013d21  jns     short loc_140013D5C
0x140013d23  xor     dil, dil
0x140013d26  mov     rcx, [r9+50h]
0x140013d2a  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x140013d31  nop     dword ptr [rax+rax+00h]
0x140013d36  xor     ecx, ecx
0x140013d38  movzx   edx, dil
0x140013d3c  cmp     [rax+0Ch], ecx
0x140013d3f  lea     eax, [rbx-4]
0x140013d42  cmovnz  ecx, edx
0x140013d45  cmp     eax, 1
0x140013d48  ja      short loc_140013DA3
0x140013d4a  test    cl, cl
0x140013d4c  jnz     short loc_140013DAD
0x140013d4e  xor     al, al
0x140013d50  mov     rbx, [rsp+28h+arg_0]
0x140013d55  add     rsp, 20h
0x140013d59  pop     rdi
0x140013d5a  retn
0x140013d5c  mov     rax, [r8+20h]
0x140013d60  test    byte ptr [rax+2FCh], 2
0x140013d67  jz      short loc_140013D23
0x140013d69  mov     rax, [rcx+88h]
0x140013d70  mov     ecx, [rax+8]
0x140013d73  test    cl, 1
0x140013d76  jnz     short loc_140013D23
0x140013d78  cmp     byte ptr [r10+4Dh], 0
0x140013d7d  jnz     short loc_140013D23
0x140013d7f  mov     rax, [r9+48h]
0x140013d83  mov     dil, 1
0x140013d86  mov     rcx, [rax+28h]
0x140013d8a  mov     rax, [rcx+28h]
0x140013d8e  mov     rcx, [rax+1A8h]
0x140013d95  test    dword ptr [rcx+0B8h], 800000h
0x140013d9f  jnz     short loc_140013D23
0x140013da1  jmp     short loc_140013D26
0x140013da3  lea     eax, [rbx-22h]
0x140013da6  cmp     eax, 1
0x140013da9  ja      short loc_140013D4E
0x140013dab  jmp     short loc_140013D4A
0x140013dad  mov     al, 1
0x140013daf  jmp     short loc_140013D50
```
