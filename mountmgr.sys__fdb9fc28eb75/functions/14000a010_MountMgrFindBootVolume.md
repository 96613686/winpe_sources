# MountMgrFindBootVolume

- ea: `0x14000a010`
- end: `0x14000a043`
- name: `MountMgrFindBootVolume`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a190`

## callees

- `0x14000a010`

## pseudocode

```c
__int64 __fastcall MountMgrFindBootVolume(__int64 a1, __int64 **a2)
{
  __int64 *v2; // r8

  v2 = *(__int64 **)(a1 + 16);
  *a2 = 0;
  if ( v2 == (__int64 *)(a1 + 16) )
    return 3221226021LL;
  while ( (v2[15] & 0x100) == 0 )
  {
    v2 = (__int64 *)*v2;
    if ( v2 == (__int64 *)(a1 + 16) )
      return 3221226021LL;
  }
  *a2 = v2;
  return 0;
}

```

## disassembly

```asm
0x14000a010  mov     r8, [rcx+10h]
0x14000a014  lea     rax, [rcx+10h]
0x14000a018  mov     qword ptr [rdx], 0
0x14000a01f  cmp     r8, rax
0x14000a022  jz      short loc_14000A036
0x14000a024  test    dword ptr [r8+78h], 100h
0x14000a02c  jnz     short loc_14000A03D
0x14000a02e  mov     r8, [r8]
0x14000a031  cmp     r8, rax
0x14000a034  jnz     short loc_14000A024
0x14000a036  mov     eax, 0C0000225h
0x14000a03b  retn
0x14000a03d  mov     [rdx], r8
0x14000a040  xor     eax, eax
0x14000a042  retn
```
