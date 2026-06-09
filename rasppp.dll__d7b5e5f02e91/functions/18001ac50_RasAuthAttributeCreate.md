# RasAuthAttributeCreate

- ea: `0x18001ac50`
- end: `0x18001acd2`
- name: `RasAuthAttributeCreate`
- size: `130`
- prototype: `_DWORD *__fastcall(unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001063c`
- `0x180011778`
- `0x18001ab0c`
- `0x18001aba0`
- `0x1800281ac`
- `0x18002881c`
- `0x18002aca4`

## callees

- `0x18001ac50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ac74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ac74`

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
0x18001ac50  push    rbx
0x18001ac52  sub     rsp, 20h
0x18001ac56  mov     ebx, ecx
0x18001ac58  lea     eax, [rbx+1]
0x18001ac5b  cmp     eax, ecx
0x18001ac5d  jb      short loc_18001ACC9
0x18001ac5f  shl     rax, 4
0x18001ac63  mov     ecx, 0FFFFFFFFh
0x18001ac68  cmp     rax, rcx
0x18001ac6b  ja      short loc_18001ACC9
0x18001ac6d  mov     edx, eax; uBytes
0x18001ac6f  mov     ecx, 40h ; '@'; uFlags
0x18001ac74  call    cs:__imp_LocalAlloc
0x18001ac7b  nop     dword ptr [rax+rax+00h]
0x18001ac80  xor     r9d, r9d
0x18001ac83  mov     rcx, rax
0x18001ac86  test    rax, rax
0x18001ac89  jz      short loc_18001ACC9
0x18001ac8b  mov     edx, r9d
0x18001ac8e  test    ebx, ebx
0x18001ac90  jz      short loc_18001ACB5
0x18001ac92  mov     r8d, r9d
0x18001ac95  mov     rax, r8
0x18001ac98  inc     edx
0x18001ac9a  add     rax, rax
0x18001ac9d  inc     r8
0x18001aca0  mov     dword ptr [rcx+rax*8], 0FFFFFFFFh
0x18001aca7  mov     [rcx+rax*8+4], r9d
0x18001acac  mov     [rcx+rax*8+8], r9
0x18001acb1  cmp     edx, ebx
0x18001acb3  jb      short loc_18001AC95
0x18001acb5  mov     rax, rbx
0x18001acb8  add     rax, rax
0x18001acbb  mov     [rcx+rax*8], r9
0x18001acbf  mov     [rcx+rax*8+8], r9
0x18001acc4  mov     rax, rcx
0x18001acc7  jmp     short loc_18001ACCB
0x18001acc9  xor     eax, eax
0x18001accb  add     rsp, 20h
0x18001accf  pop     rbx
0x18001acd0  retn
```
