# __RTCastToVoid

- ea: `0x18000e020`
- end: `0x18000e087`
- name: `__RTCastToVoid`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000abd0`
- `0x18000b680`
- `0x18000e020`

## string_xrefs

- `0x18000e064`: `Access violation - no RTTI data!`

## pseudocode

```c
char *__fastcall _RTCastToVoid(_QWORD *a1)
{
  __int64 v3; // rcx
  char *v4; // rdx

  if ( !a1 )
    return 0;
  v3 = *(_QWORD *)(*a1 - 8LL);
  v4 = (char *)a1 - *(unsigned int *)(v3 + 4);
  if ( *(_DWORD *)(v3 + 8) )
    v4 -= *(int *)((char *)a1 - *(unsigned int *)(v3 + 8));
  return v4;
}

```

## disassembly

```asm
0x18000e020  sub     rsp, 48h
0x18000e024  mov     r8, rcx
0x18000e027  test    rcx, rcx
0x18000e02a  jnz     short loc_18000E033
0x18000e02c  xor     eax, eax
0x18000e02e  add     rsp, 48h
0x18000e032  retn
0x18000e033  mov     rax, [rcx]
0x18000e036  mov     rcx, [rax-8]
0x18000e03a  mov     eax, [rcx+4]
0x18000e03d  mov     rdx, r8
0x18000e040  sub     rdx, rax
0x18000e043  mov     [rsp+48h+var_28], rdx
0x18000e048  cmp     dword ptr [rcx+8], 0
0x18000e04c  jz      short loc_18000E05F
0x18000e04e  mov     ecx, [rcx+8]
0x18000e051  sub     r8, rcx
0x18000e054  movsxd  rcx, dword ptr [r8]
0x18000e057  sub     rdx, rcx
0x18000e05a  mov     [rsp+48h+var_28], rdx
0x18000e05f  mov     rax, rdx
0x18000e062  jmp     short loc_18000E02E
0x18000e064  lea     rdx, aAccessViolatio; "Access violation - no RTTI data!"
0x18000e06b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000e070  call    ??0__non_rtti_object@@QEAA@PEBD@Z; __non_rtti_object::__non_rtti_object(char const *)
0x18000e075  lea     rdx, _TI3?AV__non_rtti_object@@; pThrowInfo
0x18000e07c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e081  call    _CxxThrowException
0x18007b3e8  push    rbp
0x18007b3ea  sub     rsp, 20h
0x18007b3ee  mov     rbp, rdx
0x18007b3f1  mov     rax, [rcx]
0x18007b3f4  xor     ecx, ecx
0x18007b3f6  cmp     dword ptr [rax], 0C0000005h
0x18007b3fc  setz    cl
0x18007b3ff  mov     eax, ecx
0x18007b401  add     rsp, 20h
0x18007b405  pop     rbp
0x18007b406  retn
```
