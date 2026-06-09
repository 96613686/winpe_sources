# __GSHandlerCheckCommon

- ea: `0x18000355c`
- end: `0x1800035bf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003538`

## callees

- `0x18000355c`
- `0x1800035f0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x18000355c  mov     r10, rcx
0x18000355f  mov     r11, rdx
0x180003562  mov     ecx, [r8]
0x180003565  and     ecx, 0FFFFFFF8h
0x180003568  test    byte ptr [r8], 4
0x18000356c  jz      short loc_180003583
0x18000356e  mov     eax, [r8+8]
0x180003572  movsxd  r9, dword ptr [r8+4]
0x180003576  neg     eax
0x180003578  movsxd  rdx, eax
0x18000357b  add     r9, r10
0x18000357e  and     r9, rdx
0x180003581  jmp     short loc_180003586
0x180003583  mov     r9, r10
0x180003586  movsxd  rax, ecx
0x180003589  mov     rdx, [rax+r9]
0x18000358d  mov     rax, [r11+10h]
0x180003591  mov     ecx, [rax+8]
0x180003594  mov     rax, [r11+8]
0x180003598  test    byte ptr [rcx+rax+3], 0Fh
0x18000359d  jz      short loc_1800035B1
0x18000359f  movzx   eax, byte ptr [rcx+rax+3]
0x1800035a4  mov     ecx, 0FFFFFFF0h
0x1800035a9  and     rax, rcx
0x1800035ac  add     rax, r10
0x1800035af  jmp     short loc_1800035B4
0x1800035b1  mov     rax, r10
0x1800035b4  xor     rdx, rax
0x1800035b7  mov     rcx, rdx; StackCookie
0x1800035ba  jmp     __security_check_cookie
```
