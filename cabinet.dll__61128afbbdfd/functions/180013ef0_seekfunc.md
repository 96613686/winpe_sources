# seekfunc

- ea: `0x180013ef0`
- end: `0x180013f2b`
- name: `seekfunc`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180013ef0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180013f17`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180013f17`

## pseudocode

```c
DWORD __fastcall seekfunc(void *a1, LONG a2, int a3)
{
  DWORD v3; // r9d
  int v4; // r8d
  DWORD result; // eax

  v3 = 0;
  if ( a3 )
  {
    v4 = a3 - 1;
    if ( v4 )
    {
      if ( v4 == 1 )
        v3 = 2;
    }
    else
    {
      v3 = 1;
    }
  }
  result = SetFilePointer(a1, a2, 0, v3);
  if ( result == -1 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180013ef0  sub     rsp, 28h
0x180013ef4  xor     r9d, r9d
0x180013ef7  test    r8d, r8d
0x180013efa  jz      short loc_180013F14
0x180013efc  sub     r8d, 1
0x180013f00  jz      short loc_180013F0E
0x180013f02  cmp     r8d, 1
0x180013f06  jnz     short loc_180013F14
0x180013f08  lea     r9d, [r8+1]
0x180013f0c  jmp     short loc_180013F14
0x180013f0e  mov     r9d, 1; dwMoveMethod
0x180013f14  xor     r8d, r8d; lpDistanceToMoveHigh
0x180013f17  call    cs:__imp_SetFilePointer
0x180013f1d  or      ecx, 0FFFFFFFFh
0x180013f20  cmp     eax, 0FFFFFFFFh
0x180013f23  cmovz   eax, ecx
0x180013f26  add     rsp, 28h
0x180013f2a  retn
```
