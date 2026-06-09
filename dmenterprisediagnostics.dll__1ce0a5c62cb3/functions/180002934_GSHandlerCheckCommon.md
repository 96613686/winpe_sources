# __GSHandlerCheckCommon

- ea: `0x180002934`
- end: `0x180002997`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002910`
- `0x1800242f0`

## callees

- `0x1800017e0`
- `0x180002934`

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
0x180002934  mov     r10, rcx
0x180002937  mov     r11, rdx
0x18000293a  mov     ecx, [r8]
0x18000293d  and     ecx, 0FFFFFFF8h
0x180002940  test    byte ptr [r8], 4
0x180002944  jz      short loc_18000295B
0x180002946  mov     eax, [r8+8]
0x18000294a  movsxd  r9, dword ptr [r8+4]
0x18000294e  neg     eax
0x180002950  movsxd  rdx, eax
0x180002953  add     r9, r10
0x180002956  and     r9, rdx
0x180002959  jmp     short loc_18000295E
0x18000295b  mov     r9, r10
0x18000295e  movsxd  rax, ecx
0x180002961  mov     rdx, [rax+r9]
0x180002965  mov     rax, [r11+10h]
0x180002969  mov     ecx, [rax+8]
0x18000296c  mov     rax, [r11+8]
0x180002970  test    byte ptr [rcx+rax+3], 0Fh
0x180002975  jz      short loc_180002989
0x180002977  movzx   eax, byte ptr [rcx+rax+3]
0x18000297c  mov     ecx, 0FFFFFFF0h
0x180002981  and     rax, rcx
0x180002984  add     rax, r10
0x180002987  jmp     short loc_18000298C
0x180002989  mov     rax, r10
0x18000298c  xor     rdx, rax
0x18000298f  mov     rcx, rdx; StackCookie
0x180002992  jmp     __security_check_cookie
```
