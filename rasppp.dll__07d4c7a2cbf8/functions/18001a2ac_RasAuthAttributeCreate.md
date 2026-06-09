# RasAuthAttributeCreate

- ea: `0x18001a2ac`
- end: `0x18001a327`
- name: `RasAuthAttributeCreate`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001016c`
- `0x1800111d8`
- `0x18001a170`
- `0x18001a200`
- `0x180027340`
- `0x180027964`
- `0x180029d0c`

## callees

- `0x18001a2ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a2d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a2d0`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeCreate(unsigned int a1)
{
  __int64 v1; // rbx
  __int64 v2; // rax
  unsigned __int64 v3; // rax
  _DWORD *v4; // rcx
  unsigned int v5; // edx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rax

  v1 = a1;
  v2 = a1 + 1;
  if ( (unsigned int)v2 < a1 )
    return 0;
  v3 = 16 * v2;
  if ( v3 > 0xFFFFFFFF )
    return 0;
  v4 = LocalAlloc(0x40u, (unsigned int)v3);
  if ( !v4 )
    return 0;
  v5 = 0;
  if ( (_DWORD)v1 )
  {
    v6 = 0;
    do
    {
      ++v5;
      v7 = 2 * v6++;
      v4[2 * v7] = -1;
      v4[2 * v7 + 1] = 0;
      *(_QWORD *)&v4[2 * v7 + 2] = 0;
    }
    while ( v5 < (unsigned int)v1 );
  }
  v8 = 2 * v1;
  *(_QWORD *)&v4[2 * v8] = 0;
  *(_QWORD *)&v4[2 * v8 + 2] = 0;
  return v4;
}

```

## disassembly

```asm
0x18001a2ac  push    rbx
0x18001a2ae  sub     rsp, 20h
0x18001a2b2  mov     ebx, ecx
0x18001a2b4  lea     eax, [rbx+1]
0x18001a2b7  cmp     eax, ecx
0x18001a2b9  jb      short loc_18001A31F
0x18001a2bb  shl     rax, 4
0x18001a2bf  mov     ecx, 0FFFFFFFFh
0x18001a2c4  cmp     rax, rcx
0x18001a2c7  ja      short loc_18001A31F
0x18001a2c9  mov     edx, eax; uBytes
0x18001a2cb  mov     ecx, 40h ; '@'; uFlags
0x18001a2d0  call    cs:__imp_LocalAlloc
0x18001a2d6  xor     r9d, r9d
0x18001a2d9  mov     rcx, rax
0x18001a2dc  test    rax, rax
0x18001a2df  jz      short loc_18001A31F
0x18001a2e1  mov     edx, r9d
0x18001a2e4  test    ebx, ebx
0x18001a2e6  jz      short loc_18001A30B
0x18001a2e8  mov     r8d, r9d
0x18001a2eb  mov     rax, r8
0x18001a2ee  inc     edx
0x18001a2f0  add     rax, rax
0x18001a2f3  inc     r8
0x18001a2f6  mov     dword ptr [rcx+rax*8], 0FFFFFFFFh
0x18001a2fd  mov     [rcx+rax*8+4], r9d
0x18001a302  mov     [rcx+rax*8+8], r9
0x18001a307  cmp     edx, ebx
0x18001a309  jb      short loc_18001A2EB
0x18001a30b  mov     rax, rbx
0x18001a30e  add     rax, rax
0x18001a311  mov     [rcx+rax*8], r9
0x18001a315  mov     [rcx+rax*8+8], r9
0x18001a31a  mov     rax, rcx
0x18001a31d  jmp     short loc_18001A321
0x18001a31f  xor     eax, eax
0x18001a321  add     rsp, 20h
0x18001a325  pop     rbx
0x18001a326  retn
```
