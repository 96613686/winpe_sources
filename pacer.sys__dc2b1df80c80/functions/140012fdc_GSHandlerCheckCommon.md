# __GSHandlerCheckCommon

- ea: `0x140012fdc`
- end: `0x14001304c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012fb8`

## callees

- `0x140012fdc`
- `0x140013110`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x140012fdc  sub     rsp, 28h
0x140012fe0  mov     eax, [r8]
0x140012fe3  mov     r10, rcx
0x140012fe6  mov     ecx, eax
0x140012fe8  mov     r11, rdx
0x140012feb  and     ecx, 0FFFFFFF8h
0x140012fee  test    al, 4
0x140012ff0  jz      short loc_140013007
0x140012ff2  mov     eax, [r8+8]
0x140012ff6  movsxd  r9, dword ptr [r8+4]
0x140012ffa  neg     eax
0x140012ffc  movsxd  rdx, eax
0x140012fff  add     r9, r10
0x140013002  and     r9, rdx
0x140013005  jmp     short loc_14001300A
0x140013007  mov     r9, r10
0x14001300a  movsxd  rax, ecx
0x14001300d  mov     rdx, [rax+r9]
0x140013011  mov     rax, [r11+10h]
0x140013015  mov     ecx, [rax+8]
0x140013018  mov     rax, [r11+8]
0x14001301c  movzx   r8d, byte ptr [rcx+rax+3]
0x140013022  test    r8b, 0Fh
0x140013026  jz      short loc_140013038
0x140013028  mov     eax, r8d
0x14001302b  mov     ecx, 0FFFFFFF0h
0x140013030  and     rax, rcx
0x140013033  add     rax, r10
0x140013036  jmp     short loc_14001303B
0x140013038  mov     rax, r10
0x14001303b  xor     rdx, rax
0x14001303e  mov     rcx, rdx; StackCookie
0x140013041  call    __security_check_cookie
0x140013046  add     rsp, 28h
0x14001304a  retn
```
