# List_Allocate

- ea: `0x18000128c`
- end: `0x1800012f3`
- name: `List_Allocate`
- size: `103`
- prototype: `_QWORD *__fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002eac`
- `0x180003a34`
- `0x180003bb8`
- `0x1800042b0`

## callees

- `0x18000128c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalLock` at `0x1800012c5`
- `api-ms-win-core-heap-l2-1-0!LocalLock` at `0x1800012c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800012e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800012e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800012b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800012b4`

## pseudocode

```c
_QWORD *__fastcall List_Allocate(unsigned int a1)
{
  unsigned int v1; // eax
  HLOCAL v2; // rax
  HLOCAL v3; // rbx
  _QWORD *v4; // rax

  v1 = *((_DWORD *)&arrayOfLists + 4 * a1);
  if ( v1 + 19 >= v1 )
  {
    v2 = LocalAlloc(0x40u, (int)(v1 + 19) & 0xFFFFFFFFFFFFFFFCuLL);
    v3 = v2;
    if ( v2 )
    {
      v4 = LocalLock(v2);
      if ( v4 )
      {
        v4[1] = v3;
        *v4 = 0;
        return v4 + 2;
      }
      LocalFree(MEMORY[8]);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000128c  push    rbx
0x18000128e  sub     rsp, 20h
0x180001292  mov     eax, ecx
0x180001294  lea     rcx, arrayOfLists
0x18000129b  add     rax, rax
0x18000129e  mov     eax, [rcx+rax*8]
0x1800012a1  lea     ecx, [rax+13h]
0x1800012a4  cmp     ecx, eax
0x1800012a6  jb      short loc_1800012EB
0x1800012a8  movsxd  rdx, ecx
0x1800012ab  mov     ecx, 40h ; '@'; uFlags
0x1800012b0  and     rdx, 0FFFFFFFFFFFFFFFCh; uBytes
0x1800012b4  call    cs:__imp_LocalAlloc
0x1800012ba  mov     rbx, rax
0x1800012bd  test    rax, rax
0x1800012c0  jz      short loc_1800012EB
0x1800012c2  mov     rcx, rax; hMem
0x1800012c5  call    cs:__imp_LocalLock
0x1800012cb  test    rax, rax
0x1800012ce  jz      short loc_1800012E1
0x1800012d0  mov     [rax+8], rbx
0x1800012d4  mov     qword ptr [rax], 0
0x1800012db  add     rax, 10h
0x1800012df  jmp     short loc_1800012ED
0x1800012e1  mov     rcx, [rax+8]; hMem
0x1800012e5  call    cs:__imp_LocalFree
0x1800012eb  xor     eax, eax
0x1800012ed  add     rsp, 20h
0x1800012f1  pop     rbx
0x1800012f2  retn
```
