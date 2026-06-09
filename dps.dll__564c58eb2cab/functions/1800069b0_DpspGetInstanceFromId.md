# DpspGetInstanceFromId

- ea: `0x1800069b0`
- end: `0x180006a34`
- name: `DpspGetInstanceFromId`
- size: `132`
- prototype: `__int64 __fastcall(_QWORD *, int *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002510`
- `0x180002a08`
- `0x1800054f0`
- `0x18000bd28`
- `0x18000bf58`
- `0x18000c21c`
- `0x1800104f4`
- `0x1800146b0`
- `0x1800149dc`
- `0x180014df0`
- `0x180015918`
- `0x180015b84`

## callees

- `0x1800069b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006a16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006a16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006a20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006a20`

## pseudocode

```c
__int64 __fastcall DpspGetInstanceFromId(_QWORD *a1, int *a2)
{
  __int64 v2; // rbx

  v2 = g_pInstanceHead;
  if ( !g_pInstanceHead )
  {
LABEL_5:
    if ( a2 )
      *a2 = 1;
    return v2;
  }
  while ( *(_QWORD *)(v2 + 24) != *a1 || *(_QWORD *)(v2 + 32) != a1[1] )
  {
    v2 = *(_QWORD *)(v2 + 1232);
    if ( !v2 )
      goto LABEL_5;
  }
  if ( a2 )
    *a2 = ((unsigned __int8)*(_DWORD *)(v2 + 104) >> 5) & 2;
  if ( !v2 )
    return v2;
  AcquireSRWLockExclusive((PSRWLOCK)(v2 + 16));
  ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
  return v2;
}

```

## disassembly

```asm
0x1800069b0  push    rbx
0x1800069b2  sub     rsp, 20h
0x1800069b6  mov     rbx, cs:g_pInstanceHead
0x1800069bd  test    rbx, rbx
0x1800069c0  jz      short loc_1800069E1
0x1800069c2  mov     rax, [rbx+18h]
0x1800069c6  cmp     rax, [rcx]
0x1800069c9  jnz     short loc_1800069D5
0x1800069cb  mov     rax, [rbx+20h]
0x1800069cf  cmp     rax, [rcx+8]
0x1800069d3  jz      short loc_1800069F5
0x1800069d5  mov     rbx, [rbx+4D0h]
0x1800069dc  test    rbx, rbx
0x1800069df  jnz     short loc_1800069C2
0x1800069e1  test    rdx, rdx
0x1800069e4  jz      short loc_1800069EC
0x1800069e6  mov     dword ptr [rdx], 1
0x1800069ec  mov     rax, rbx
0x1800069ef  add     rsp, 20h
0x1800069f3  pop     rbx
0x1800069f4  retn
0x1800069f5  test    rdx, rdx
0x1800069f8  jz      short loc_180006A08
0x1800069fa  mov     eax, [rbx+68h]
0x1800069fd  movzx   ecx, al
0x180006a00  shr     ecx, 5
0x180006a03  and     ecx, 2
0x180006a06  mov     [rdx], ecx
0x180006a08  test    rbx, rbx
0x180006a0b  jz      short loc_1800069EC
0x180006a0d  lea     rcx, [rbx+10h]; SRWLock
0x180006a11  mov     [rsp+28h+arg_0], rdi
0x180006a16  call    cs:__imp_AcquireSRWLockExclusive
0x180006a1c  lea     rcx, [rbx+10h]; SRWLock
0x180006a20  call    cs:__imp_ReleaseSRWLockExclusive
0x180006a26  mov     rdi, [rsp+28h+arg_0]
0x180006a2b  mov     rax, rbx
0x180006a2e  add     rsp, 20h
0x180006a32  pop     rbx
0x180006a33  retn
```
