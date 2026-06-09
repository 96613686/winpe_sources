# DRR_DeleteAnyGrowableArray

- ea: `0x18000cfe8`
- end: `0x18000d04d`
- name: `DRR_DeleteAnyGrowableArray`
- size: `101`
- prototype: `HLOCAL __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fb4`
- `0x180004110`
- `0x180004e90`

## callees

- `0x18000cfe8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d033`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d033`

## pseudocode

```c
HLOCAL __fastcall DRR_DeleteAnyGrowableArray(__int64 a1, unsigned int a2)
{
  unsigned int i; // r9d
  __int64 v4; // rcx
  HLOCAL result; // rax

  for ( i = a2; i < *(_DWORD *)(a1 + 8) - 1; *(_QWORD *)(*(_QWORD *)a1 + 8 * v4) = *(_QWORD *)(*(_QWORD *)a1 + 8LL * i) )
    v4 = i++;
  result = *(HLOCAL *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL * i) = 0;
  if ( (*(_DWORD *)(a1 + 8))-- == 1 )
  {
    result = LocalFree(*(HLOCAL *)a1);
    *(_QWORD *)a1 = 0;
    *(_DWORD *)(a1 + 12) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000cfe8  push    rbx
0x18000cfea  sub     rsp, 20h
0x18000cfee  mov     eax, [rcx+8]
0x18000cff1  mov     r9d, edx
0x18000cff4  dec     eax
0x18000cff6  mov     rbx, rcx
0x18000cff9  cmp     edx, eax
0x18000cffb  jnb     short loc_18000D01C
0x18000cffd  mov     rdx, [rbx]
0x18000d000  lea     r8d, [r9+1]
0x18000d004  mov     ecx, r9d
0x18000d007  mov     r9d, r8d
0x18000d00a  mov     rax, [rdx+r8*8]
0x18000d00e  mov     [rdx+rcx*8], rax
0x18000d012  mov     eax, [rbx+8]
0x18000d015  dec     eax
0x18000d017  cmp     r8d, eax
0x18000d01a  jb      short loc_18000CFFD
0x18000d01c  mov     rax, [rbx]
0x18000d01f  mov     ecx, r9d
0x18000d022  mov     qword ptr [rax+rcx*8], 0
0x18000d02a  add     dword ptr [rbx+8], 0FFFFFFFFh
0x18000d02e  jnz     short loc_18000D047
0x18000d030  mov     rcx, [rbx]; hMem
0x18000d033  call    cs:__imp_LocalFree
0x18000d039  mov     qword ptr [rbx], 0
0x18000d040  mov     dword ptr [rbx+0Ch], 0
0x18000d047  add     rsp, 20h
0x18000d04b  pop     rbx
0x18000d04c  retn
```
