# RasAuthAttributeCreate

- ea: `0x18000ab30`
- end: `0x18000abab`
- name: `RasAuthAttributeCreate`
- size: `123`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180007370`
- `0x18000a4c0`
- `0x18000a900`
- `0x180011414`
- `0x180014bd8`
- `0x180018c8c`
- `0x180019034`
- `0x1800192e0`
- `0x180019c3c`

## callees

- `0x18000ab30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ab54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ab54`

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
0x18000ab30  push    rbx
0x18000ab32  sub     rsp, 20h
0x18000ab36  mov     ebx, ecx
0x18000ab38  lea     eax, [rbx+1]
0x18000ab3b  cmp     eax, ecx
0x18000ab3d  jb      short loc_18000ABA3
0x18000ab3f  shl     rax, 4
0x18000ab43  mov     ecx, 0FFFFFFFFh
0x18000ab48  cmp     rax, rcx
0x18000ab4b  ja      short loc_18000ABA3
0x18000ab4d  mov     edx, eax; uBytes
0x18000ab4f  mov     ecx, 40h ; '@'; uFlags
0x18000ab54  call    cs:__imp_LocalAlloc
0x18000ab5a  xor     r9d, r9d
0x18000ab5d  mov     rcx, rax
0x18000ab60  test    rax, rax
0x18000ab63  jz      short loc_18000ABA3
0x18000ab65  mov     edx, r9d
0x18000ab68  test    ebx, ebx
0x18000ab6a  jz      short loc_18000AB8F
0x18000ab6c  mov     r8d, r9d
0x18000ab6f  mov     rax, r8
0x18000ab72  inc     edx
0x18000ab74  add     rax, rax
0x18000ab77  inc     r8
0x18000ab7a  mov     dword ptr [rcx+rax*8], 0FFFFFFFFh
0x18000ab81  mov     [rcx+rax*8+4], r9d
0x18000ab86  mov     [rcx+rax*8+8], r9
0x18000ab8b  cmp     edx, ebx
0x18000ab8d  jb      short loc_18000AB6F
0x18000ab8f  mov     rax, rbx
0x18000ab92  add     rax, rax
0x18000ab95  mov     [rcx+rax*8], r9
0x18000ab99  mov     [rcx+rax*8+8], r9
0x18000ab9e  mov     rax, rcx
0x18000aba1  jmp     short loc_18000ABA5
0x18000aba3  xor     eax, eax
0x18000aba5  add     rsp, 20h
0x18000aba9  pop     rbx
0x18000abaa  retn
```
