# Smb2IsKnownVmbusPassthroughEcp

- ea: `0x1400178d0`
- end: `0x140017928`
- name: `Smb2IsKnownVmbusPassthroughEcp`
- size: `88`
- prototype: `bool __fastcall(__int64, const void *, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007470`

## callees

- `0x1400178d0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400178fd`
- `ntoskrnl!RtlCompareMemory` at `0x140017913`
- `ntoskrnl!RtlCompareMemory` at `0x1400178fd`
- `ntoskrnl!RtlCompareMemory` at `0x140017913`

## pseudocode

```c
bool __fastcall Smb2IsKnownVmbusPassthroughEcp(__int64 a1, const void *a2, char a3)
{
  if ( (*(_BYTE *)(a1 + 1314) & 4) == 0 )
    return 0;
  if ( !a3 )
    return RtlCompareMemory(a2, &GUID_ECP_CLOUDFILES_ATTRIBUTION, 0x10u) == 16;
  return RtlCompareMemory(a2, &GUID_ECP_CLOUDFILES_ATTRIBUTION, 0x10u) == 16;
}

```

## disassembly

```asm
0x1400178d0  sub     rsp, 28h
0x1400178d4  test    byte ptr [rcx+522h], 4
0x1400178db  mov     r9, rdx
0x1400178de  jnz     short loc_1400178E8
0x1400178e0  xor     al, al
0x1400178e2  add     rsp, 28h
0x1400178e6  retn
0x1400178e8  test    r8b, r8b
0x1400178eb  lea     rdx, GUID_ECP_CLOUDFILES_ATTRIBUTION; Source2
0x1400178f2  mov     r8d, 10h; Length
0x1400178f8  mov     rcx, r9; Source1
0x1400178fb  jz      short loc_140017913
0x1400178fd  call    cs:__imp_RtlCompareMemory
0x140017904  nop     dword ptr [rax+rax+00h]
0x140017909  cmp     rax, 10h
0x14001790d  jnz     short loc_1400178E0
0x14001790f  mov     al, 1
0x140017911  jmp     short loc_1400178E2
0x140017913  call    cs:__imp_RtlCompareMemory
0x14001791a  nop     dword ptr [rax+rax+00h]
0x14001791f  cmp     rax, 10h
0x140017923  setz    al
0x140017926  jmp     short loc_1400178E2
```
