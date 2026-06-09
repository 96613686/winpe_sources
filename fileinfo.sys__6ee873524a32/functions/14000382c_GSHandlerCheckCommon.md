# __GSHandlerCheckCommon

- ea: `0x14000382c`
- end: `0x14000389c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003808`
- `0x1400038a4`

## callees

- `0x14000382c`
- `0x140003920`

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
0x14000382c  sub     rsp, 28h
0x140003830  mov     eax, [r8]
0x140003833  mov     r10, rcx
0x140003836  mov     ecx, eax
0x140003838  mov     r11, rdx
0x14000383b  and     ecx, 0FFFFFFF8h
0x14000383e  test    al, 4
0x140003840  jz      short loc_140003857
0x140003842  mov     eax, [r8+8]
0x140003846  movsxd  r9, dword ptr [r8+4]
0x14000384a  neg     eax
0x14000384c  movsxd  rdx, eax
0x14000384f  add     r9, r10
0x140003852  and     r9, rdx
0x140003855  jmp     short loc_14000385A
0x140003857  mov     r9, r10
0x14000385a  movsxd  rax, ecx
0x14000385d  mov     rdx, [rax+r9]
0x140003861  mov     rax, [r11+10h]
0x140003865  mov     ecx, [rax+8]
0x140003868  mov     rax, [r11+8]
0x14000386c  movzx   r8d, byte ptr [rcx+rax+3]
0x140003872  test    r8b, 0Fh
0x140003876  jz      short loc_140003888
0x140003878  mov     eax, r8d
0x14000387b  mov     ecx, 0FFFFFFF0h
0x140003880  and     rax, rcx
0x140003883  add     rax, r10
0x140003886  jmp     short loc_14000388B
0x140003888  mov     rax, r10
0x14000388b  xor     rdx, rax
0x14000388e  mov     rcx, rdx; StackCookie
0x140003891  call    __security_check_cookie
0x140003896  add     rsp, 28h
0x14000389a  retn
```
