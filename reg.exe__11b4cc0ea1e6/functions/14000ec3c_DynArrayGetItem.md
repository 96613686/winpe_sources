# __DynArrayGetItem

- ea: `0x14000ec3c`
- end: `0x14000ec73`
- name: `__DynArrayGetItem`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x1400053e0`
- `0x140007170`
- `0x140007834`
- `0x140007be0`
- `0x140008320`
- `0x14000caa8`
- `0x14000cd48`
- `0x14000d8b4`
- `0x14000e838`
- `0x14000e87c`
- `0x14000e8c8`
- `0x14000e928`
- `0x14000e994`
- `0x14000eb48`

## callees

- `0x14000ec3c`

## pseudocode

```c
__int64 __fastcall _DynArrayGetItem(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 result; // rax
  __int64 v4; // r9
  unsigned int i; // ecx

  if ( !a1 || *(_DWORD *)a1 != 9 || *(_DWORD *)(a1 + 4) <= a2 )
    return 0;
  result = *(_QWORD *)(a1 + 8);
  v4 = 0;
  for ( i = 1; i <= a2; result = *(_QWORD *)(result + 24) )
  {
    ++i;
    v4 = result;
  }
  if ( a3 )
    *a3 = v4;
  return result;
}

```

## disassembly

```asm
0x14000ec3c  test    rcx, rcx
0x14000ec3f  jz      short loc_14000EC70
0x14000ec41  cmp     dword ptr [rcx], 9
0x14000ec44  jnz     short loc_14000EC70
0x14000ec46  cmp     [rcx+4], edx
0x14000ec49  jbe     short loc_14000EC70
0x14000ec4b  mov     rax, [rcx+8]
0x14000ec4f  xor     r9d, r9d
0x14000ec52  lea     ecx, [r9+1]
0x14000ec56  cmp     edx, ecx
0x14000ec58  jb      short loc_14000EC67
0x14000ec5a  inc     ecx
0x14000ec5c  mov     r9, rax
0x14000ec5f  mov     rax, [rax+18h]
0x14000ec63  cmp     ecx, edx
0x14000ec65  jbe     short loc_14000EC5A
0x14000ec67  test    r8, r8
0x14000ec6a  jz      short locret_14000EC72
0x14000ec6c  mov     [r8], r9
0x14000ec6f  retn
0x14000ec70  xor     eax, eax
0x14000ec72  retn
```
