# MdaGetRemoteProtocolInformation

- ea: `0x14001a688`
- end: `0x14001a701`
- name: `MdaGetRemoteProtocolInformation`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001100`

## callees

- `0x14001a688`
- `0x14003b0c0`

## pseudocode

```c
__int64 __fastcall MdaGetRemoteProtocolInformation(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  __int16 v6; // bp
  unsigned int v7; // edi

  v6 = 3 - (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 120) + 32LL) + 32LL) + 88LL) != 3);
  if ( *a5 >= 0x74u )
  {
    v7 = 0;
    memset((void *)(a4 + 14), 0, 0x66u);
    *(_DWORD *)a4 = 7602177;
    *(_DWORD *)(a4 + 10) = 0;
    *(_DWORD *)(a4 + 4) = 4325376;
    *(_WORD *)(a4 + 8) = v6;
    *a5 -= 116;
  }
  else
  {
    return (unsigned int)-1073741789;
  }
  return v7;
}

```

## disassembly

```asm
0x14001a688  push    rbx
0x14001a68a  push    rbp
0x14001a68b  push    rsi
0x14001a68c  push    rdi
0x14001a68d  push    r14
0x14001a68f  sub     rsp, 20h
0x14001a693  mov     rax, [rdx+78h]
0x14001a697  mov     rbx, r9
0x14001a69a  mov     rsi, [rsp+48h+arg_20]
0x14001a69f  mov     rcx, [rax+20h]
0x14001a6a3  mov     rax, [rcx+20h]
0x14001a6a7  mov     ecx, [rax+58h]
0x14001a6aa  mov     eax, 3
0x14001a6af  sub     ecx, eax
0x14001a6b1  neg     ecx
0x14001a6b3  sbb     bp, bp
0x14001a6b6  lea     r14d, [rax+71h]
0x14001a6ba  add     bp, ax
0x14001a6bd  cmp     [rsi], r14d
0x14001a6c0  jnb     short loc_14001A6C9
0x14001a6c2  mov     edi, 0C0000023h
0x14001a6c7  jmp     short loc_14001A6F3
0x14001a6c9  xor     edi, edi
0x14001a6cb  lea     rcx, [r9+0Eh]; void *
0x14001a6cf  xor     edx, edx; Val
0x14001a6d1  lea     r8d, [rdi+66h]; Size
0x14001a6d5  call    memset
0x14001a6da  xor     ecx, ecx
0x14001a6dc  mov     dword ptr [rbx], 740001h
0x14001a6e2  mov     [rbx+0Ah], ecx
0x14001a6e5  mov     dword ptr [rbx+4], 420000h
0x14001a6ec  mov     [rbx+8], bp
0x14001a6f0  add     dword ptr [rsi], 0FFFFFF8Ch
0x14001a6f3  mov     eax, edi
0x14001a6f5  add     rsp, 20h
0x14001a6f9  pop     r14
0x14001a6fb  pop     rdi
0x14001a6fc  pop     rsi
0x14001a6fd  pop     rbp
0x14001a6fe  pop     rbx
0x14001a6ff  retn
```
