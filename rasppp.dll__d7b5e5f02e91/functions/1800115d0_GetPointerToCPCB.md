# GetPointerToCPCB

- ea: `0x1800115d0`
- end: `0x180011652`
- name: `GetPointerToCPCB`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `31`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000423c`
- `0x1800043a8`
- `0x18000442c`
- `0x180009920`
- `0x180009aac`
- `0x18000b2e8`
- `0x18000be68`
- `0x18000c050`
- `0x18000c234`
- `0x18000c3e8`
- `0x18000c8d4`
- `0x18000cc7c`
- `0x18000cdc8`
- `0x18000cf3c`
- `0x18000d450`
- `0x18000d6b4`
- `0x18000d8b4`
- `0x18000e358`
- `0x18000e540`
- `0x18000e7a4`
- `0x18000eb90`
- `0x18000ecac`
- `0x180010f00`
- `0x180012104`
- `0x180013cf4`
- `0x1800140a4`
- `0x180014808`
- `0x180015660`
- `0x180015730`
- `0x180015d28`
- `0x1800181b0`

## callees

- `0x1800115d0`

## pseudocode

```c
unsigned __int64 __fastcall GetPointerToCPCB(__int64 a1, unsigned int a2)
{
  unsigned __int64 result; // rax
  int v3; // edx

  if ( a2 == -1 )
    return 0;
  if ( !a2 )
    return a1 + 1456;
  if ( a2 < (unsigned int)PppConfigInfo )
    return ((unsigned __int64)(a2 - 1) << 6) + *(_QWORD *)(a1 + 8) + 4112LL;
  v3 = *((_DWORD *)CpTable + 44 * a2);
  if ( v3 == 49193 )
    return a1 + 1264;
  if ( v3 == *(_DWORD *)(a1 + 1332) )
    return a1 + 1328;
  result = 0;
  if ( v3 == *(_DWORD *)(a1 + 1396) )
    return a1 + 1392;
  return result;
}

```

## disassembly

```asm
0x1800115d0  mov     r8, rcx
0x1800115d3  cmp     edx, 0FFFFFFFFh
0x1800115d6  jnz     short loc_1800115DC
0x1800115d8  xor     eax, eax
0x1800115da  retn
0x1800115dc  test    edx, edx
0x1800115de  jnz     short loc_1800115E9
0x1800115e0  lea     rax, [rcx+5B0h]
0x1800115e7  retn
0x1800115e9  cmp     edx, dword ptr cs:PppConfigInfo
0x1800115ef  jb      short loc_18001163D
0x1800115f1  mov     eax, edx
0x1800115f3  imul    rcx, rax, 0B0h
0x1800115fa  mov     rax, cs:CpTable
0x180011601  mov     edx, [rcx+rax]
0x180011604  cmp     edx, 0C029h
0x18001160a  jnz     short loc_180011615
0x18001160c  lea     rax, [r8+4F0h]
0x180011613  retn
0x180011615  cmp     edx, [r8+534h]
0x18001161c  jnz     short loc_180011627
0x18001161e  lea     rax, [r8+530h]
0x180011625  retn
0x180011627  xor     eax, eax
0x180011629  lea     rcx, [r8+570h]
0x180011630  cmp     edx, [r8+574h]
0x180011637  cmovz   rax, rcx
0x18001163b  retn
0x18001163d  mov     rax, [r8+8]
0x180011641  lea     ecx, [rdx-1]
0x180011644  shl     rcx, 6
0x180011648  add     rax, 1010h
0x18001164e  add     rax, rcx
0x180011651  retn
```
