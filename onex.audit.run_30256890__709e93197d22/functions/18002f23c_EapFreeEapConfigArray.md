# EapFreeEapConfigArray

- ea: `0x18002f23c`
- end: `0x18002f2fa`
- name: `EapFreeEapConfigArray`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002ef1c`
- `0x18002f300`

## callees

- `0x18002f23c`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x18002f284`
- `MobileNetworking!FreeMemory` at `0x18002f2b4`
- `MobileNetworking!FreeMemory` at `0x18002f2dd`
- `MobileNetworking!FreeMemory` at `0x18002f284`
- `MobileNetworking!FreeMemory` at `0x18002f2b4`
- `MobileNetworking!FreeMemory` at `0x18002f2dd`

## string_xrefs

- `0x18002f27d`: `EapFreeEapConfigArray`
- `0x18002f2ad`: `EapFreeEapConfigArray`
- `0x18002f2d3`: `EapFreeEapConfigArray`

## pseudocode

```c
__int64 __fastcall EapFreeEapConfigArray(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 v3; // rsi
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  __int64 result; // rax

  v1 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 8) && *(_DWORD *)(a1 + 4) )
  {
    v3 = 0;
    do
    {
      v4 = (_QWORD *)(*v1 + 16LL + 40 * v3);
      if ( *v4 )
      {
        FreeMemory(v4, "EapFreeEapConfigArray", 62);
        *(_QWORD *)(*v1 + 40 * v3 + 16) = 0;
      }
      v5 = (_QWORD *)(*v1 + 24LL + 40 * v3);
      if ( *v5 )
      {
        FreeMemory(v5, "EapFreeEapConfigArray", 67);
        *(_QWORD *)(*v1 + 40 * v3 + 16) = 0;
      }
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < *(_DWORD *)(a1 + 4) );
    result = FreeMemory(v1, "EapFreeEapConfigArray", 71);
    *v1 = 0;
    *(_DWORD *)(a1 + 4) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002f23c  push    rbx
0x18002f23e  push    rbp
0x18002f23f  push    rsi
0x18002f240  push    rdi
0x18002f241  sub     rsp, 28h
0x18002f245  lea     rbx, [rcx+8]
0x18002f249  mov     rdi, rcx
0x18002f24c  cmp     qword ptr [rbx], 0
0x18002f250  jz      loc_18002F2F1
0x18002f256  cmp     dword ptr [rcx+4], 0
0x18002f25a  jbe     loc_18002F2F1
0x18002f260  xor     esi, esi
0x18002f262  mov     rcx, [rbx]
0x18002f265  lea     rbp, [rsi+rsi*4]
0x18002f269  add     rcx, 10h
0x18002f26d  lea     rcx, [rcx+rbp*8]
0x18002f271  cmp     qword ptr [rcx], 0
0x18002f275  jz      short loc_18002F296
0x18002f277  mov     r8d, 3Eh ; '>'
0x18002f27d  lea     rdx, aEapfreeeapconf; "EapFreeEapConfigArray"
0x18002f284  call    cs:__imp_FreeMemory
0x18002f28a  mov     rax, [rbx]
0x18002f28d  mov     qword ptr [rax+rbp*8+10h], 0
0x18002f296  mov     rcx, [rbx]
0x18002f299  add     rcx, 18h
0x18002f29d  lea     rcx, [rcx+rbp*8]
0x18002f2a1  cmp     qword ptr [rcx], 0
0x18002f2a5  jz      short loc_18002F2C6
0x18002f2a7  mov     r8d, 43h ; 'C'
0x18002f2ad  lea     rdx, aEapfreeeapconf; "EapFreeEapConfigArray"
0x18002f2b4  call    cs:__imp_FreeMemory
0x18002f2ba  mov     rax, [rbx]
0x18002f2bd  mov     qword ptr [rax+rbp*8+10h], 0
0x18002f2c6  inc     esi
0x18002f2c8  cmp     esi, [rdi+4]
0x18002f2cb  jb      short loc_18002F262
0x18002f2cd  mov     r8d, 47h ; 'G'
0x18002f2d3  lea     rdx, aEapfreeeapconf; "EapFreeEapConfigArray"
0x18002f2da  mov     rcx, rbx
0x18002f2dd  call    cs:__imp_FreeMemory
0x18002f2e3  mov     qword ptr [rbx], 0
0x18002f2ea  mov     dword ptr [rdi+4], 0
0x18002f2f1  add     rsp, 28h
0x18002f2f5  pop     rdi
0x18002f2f6  pop     rsi
0x18002f2f7  pop     rbp
0x18002f2f8  pop     rbx
0x18002f2f9  retn
```
