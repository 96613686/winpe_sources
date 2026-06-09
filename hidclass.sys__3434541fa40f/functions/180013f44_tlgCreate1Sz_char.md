# _tlgCreate1Sz_char

- ea: `0x180013f44`
- end: `0x180013f75`
- name: `_tlgCreate1Sz_char`
- size: `49`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180008650`
- `0x180009664`
- `0x18000c948`
- `0x18001acb8`
- `0x18001ec30`
- `0x18001ed14`
- `0x18001fabc`
- `0x180021d38`
- `0x180021e1c`
- `0x18002204c`
- `0x180023fe0`
- `0x1800268d8`

## callees

- `0x180013f44`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_char(__int64 a1, const CHAR *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( a2[v2] );
    result = (unsigned int)(v2 + 1);
  }
  else
  {
    a2 = File;
    result = 1;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x180013f44  test    rdx, rdx
0x180013f47  jz      short loc_180013F67
0x180013f49  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013f4d  inc     rax
0x180013f50  cmp     byte ptr [rdx+rax], 0
0x180013f54  jnz     short loc_180013F4D
0x180013f56  inc     eax
0x180013f58  mov     [rcx], rdx
0x180013f5b  mov     [rcx+8], eax
0x180013f5e  mov     dword ptr [rcx+0Ch], 0
0x180013f65  retn
0x180013f67  lea     rdx, File
0x180013f6e  mov     eax, 1
0x180013f73  jmp     short loc_180013F58
```
