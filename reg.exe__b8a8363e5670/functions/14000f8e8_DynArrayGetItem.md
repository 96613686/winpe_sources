# __DynArrayGetItem

- ea: `0x14000f8e8`
- end: `0x14000f920`
- name: `__DynArrayGetItem`
- size: `56`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x1400056ec`
- `0x1400075ac`
- `0x140007cbc`
- `0x1400080a4`
- `0x140008838`
- `0x14000d3e8`
- `0x14000d694`
- `0x14000e3bc`
- `0x14000f4d8`
- `0x14000f51c`
- `0x14000f568`
- `0x14000f5c8`
- `0x14000f638`
- `0x14000f7f4`

## callees

- `0x14000f8e8`

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
0x14000f8e8  test    rcx, rcx
0x14000f8eb  jz      short loc_14000F91D
0x14000f8ed  cmp     dword ptr [rcx], 9
0x14000f8f0  jnz     short loc_14000F91D
0x14000f8f2  cmp     [rcx+4], edx
0x14000f8f5  jbe     short loc_14000F91D
0x14000f8f7  mov     rax, [rcx+8]
0x14000f8fb  xor     r9d, r9d
0x14000f8fe  lea     ecx, [r9+1]
0x14000f902  cmp     edx, ecx
0x14000f904  jb      short loc_14000F913
0x14000f906  inc     ecx
0x14000f908  mov     r9, rax
0x14000f90b  mov     rax, [rax+18h]
0x14000f90f  cmp     ecx, edx
0x14000f911  jbe     short loc_14000F906
0x14000f913  test    r8, r8
0x14000f916  jz      short locret_14000F91F
0x14000f918  mov     [r8], r9
0x14000f91b  retn
0x14000f91d  xor     eax, eax
0x14000f91f  retn
```
