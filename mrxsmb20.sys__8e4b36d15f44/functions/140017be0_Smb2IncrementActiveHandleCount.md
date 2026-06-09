# Smb2IncrementActiveHandleCount

- ea: `0x140017be0`
- end: `0x140017c5d`
- name: `Smb2IncrementActiveHandleCount`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400087c0`

## callees

- `0x140017be0`

## import_xrefs

- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140017c21`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140017c4a`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140017c21`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140017c4a`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140017c0a`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140017c0a`

## pseudocode

```c
__int64 __fastcall Smb2IncrementActiveHandleCount(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v3; // rdx
  unsigned int v5; // eax
  __int64 v6; // rdx

  v1 = *(_QWORD *)(a1 + 384);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 432));
  if ( *(_DWORD *)(a1 + 704) )
  {
    v5 = *(_DWORD *)(v1 + 772);
    v6 = 10;
    if ( v5 )
      v6 = v5;
    return SmbCeSetConnectionKeepalive(a1, v6, 2);
  }
  else
  {
    v3 = *(unsigned int *)(v1 + 776);
    if ( !(_DWORD)v3 )
      v3 = *(_DWORD *)(MRxSmbGetConfigurationBlock(a1) + 12) >> 1;
    return SmbCeSetConnectionKeepalive(a1, v3, 0);
  }
}

```

## disassembly

```asm
0x140017be0  push    rbx
0x140017be2  sub     rsp, 20h
0x140017be6  mov     rdx, [rcx+180h]
0x140017bed  mov     rbx, rcx
0x140017bf0  lock inc dword ptr [rcx+1B0h]
0x140017bf7  cmp     dword ptr [rcx+2C0h], 0
0x140017bfe  jnz     short loc_140017C34
0x140017c00  mov     edx, [rdx+308h]
0x140017c06  test    edx, edx
0x140017c08  jnz     short loc_140017C1B
0x140017c0a  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140017c11  nop     dword ptr [rax+rax+00h]
0x140017c16  mov     edx, [rax+0Ch]
0x140017c19  shr     edx, 1
0x140017c1b  xor     r8d, r8d
0x140017c1e  mov     rcx, rbx
0x140017c21  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140017c28  nop     dword ptr [rax+rax+00h]
0x140017c2d  add     rsp, 20h
0x140017c31  pop     rbx
0x140017c32  retn
0x140017c34  mov     eax, [rdx+304h]
0x140017c3a  mov     r8d, 2
0x140017c40  test    eax, eax
0x140017c42  mov     edx, 0Ah
0x140017c47  cmovnz  edx, eax
0x140017c4a  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140017c51  nop     dword ptr [rax+rax+00h]
0x140017c56  add     rsp, 20h
0x140017c5a  pop     rbx
0x140017c5b  retn
```
