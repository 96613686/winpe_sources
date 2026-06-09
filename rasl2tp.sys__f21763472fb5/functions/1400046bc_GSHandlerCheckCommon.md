# __GSHandlerCheckCommon

- ea: `0x1400046bc`
- end: `0x14000472c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004698`

## callees

- `0x1400046bc`
- `0x1400047f0`

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
0x1400046bc  sub     rsp, 28h
0x1400046c0  mov     eax, [r8]
0x1400046c3  mov     r10, rcx
0x1400046c6  mov     ecx, eax
0x1400046c8  mov     r11, rdx
0x1400046cb  and     ecx, 0FFFFFFF8h
0x1400046ce  test    al, 4
0x1400046d0  jz      short loc_1400046E7
0x1400046d2  mov     eax, [r8+8]
0x1400046d6  movsxd  r9, dword ptr [r8+4]
0x1400046da  neg     eax
0x1400046dc  movsxd  rdx, eax
0x1400046df  add     r9, r10
0x1400046e2  and     r9, rdx
0x1400046e5  jmp     short loc_1400046EA
0x1400046e7  mov     r9, r10
0x1400046ea  movsxd  rax, ecx
0x1400046ed  mov     rdx, [rax+r9]
0x1400046f1  mov     rax, [r11+10h]
0x1400046f5  mov     ecx, [rax+8]
0x1400046f8  mov     rax, [r11+8]
0x1400046fc  movzx   r8d, byte ptr [rcx+rax+3]
0x140004702  test    r8b, 0Fh
0x140004706  jz      short loc_140004718
0x140004708  mov     eax, r8d
0x14000470b  mov     ecx, 0FFFFFFF0h
0x140004710  and     rax, rcx
0x140004713  add     rax, r10
0x140004716  jmp     short loc_14000471B
0x140004718  mov     rax, r10
0x14000471b  xor     rdx, rax
0x14000471e  mov     rcx, rdx; StackCookie
0x140004721  call    __security_check_cookie
0x140004726  add     rsp, 28h
0x14000472a  retn
```
