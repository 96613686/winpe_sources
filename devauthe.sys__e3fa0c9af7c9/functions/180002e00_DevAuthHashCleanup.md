# _DevAuthHashCleanup

- ea: `0x180002e00`
- end: `0x180002e67`
- name: `_DevAuthHashCleanup`
- size: `103`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000258c`
- `0x1800026a0`

## callees

- `0x180002e00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180002e2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002e54`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002e2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002e54`
- `cng!BCryptCloseAlgorithmProvider` at `0x180002e43`
- `cng!BCryptCloseAlgorithmProvider` at `0x180002e43`
- `cng!BCryptDestroyHash` at `0x180002e16`
- `cng!BCryptDestroyHash` at `0x180002e16`

## pseudocode

```c
void __fastcall DevAuthHashCleanup(BCRYPT_ALG_HANDLE *P)
{
  BCRYPT_ALG_HANDLE v2; // rcx
  BCRYPT_ALG_HANDLE v3; // rcx

  if ( P )
  {
    v2 = P[1];
    if ( v2 )
      BCryptDestroyHash(v2);
    v3 = P[2];
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
    if ( *P )
      BCryptCloseAlgorithmProvider(*P, 0);
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x180002e00  test    rcx, rcx
0x180002e03  jz      short locret_180002E65
0x180002e05  push    rbx
0x180002e06  sub     rsp, 20h
0x180002e0a  mov     rbx, rcx
0x180002e0d  mov     rcx, [rcx+8]; hHash
0x180002e11  test    rcx, rcx
0x180002e14  jz      short loc_180002E22
0x180002e16  call    cs:__imp_BCryptDestroyHash
0x180002e1d  nop     dword ptr [rax+rax+00h]
0x180002e22  mov     rcx, [rbx+10h]; P
0x180002e26  test    rcx, rcx
0x180002e29  jz      short loc_180002E39
0x180002e2b  xor     edx, edx; Tag
0x180002e2d  call    cs:__imp_ExFreePoolWithTag
0x180002e34  nop     dword ptr [rax+rax+00h]
0x180002e39  mov     rcx, [rbx]; hAlgorithm
0x180002e3c  test    rcx, rcx
0x180002e3f  jz      short loc_180002E4F
0x180002e41  xor     edx, edx; dwFlags
0x180002e43  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002e4a  nop     dword ptr [rax+rax+00h]
0x180002e4f  xor     edx, edx; Tag
0x180002e51  mov     rcx, rbx; P
0x180002e54  call    cs:__imp_ExFreePoolWithTag
0x180002e5b  nop     dword ptr [rax+rax+00h]
0x180002e60  add     rsp, 20h
0x180002e64  pop     rbx
0x180002e65  retn
```
