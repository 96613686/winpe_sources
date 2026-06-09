# FDIReadCFFILEEntry

- ea: `0x180004b84`
- end: `0x180004be2`
- name: `FDIReadCFFILEEntry`
- size: `94`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000254c`
- `0x1800048d0`

## callees

- `0x180004b84`
- `0x180004be8`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall FDIReadCFFILEEntry(__int64 *a1)
{
  __int64 v2; // rdx
  __int64 v4; // rax

  if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64))a1[4])(a1[27], (__int64)a1 + 188, 16) == 16
    && (unsigned int)FDIReadPSZ((char *)a1 + 268, v2, a1) )
  {
    return 1;
  }
  v4 = *a1;
  *(_QWORD *)v4 = 4;
  *(_DWORD *)(v4 + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x180004b84  push    rbx
0x180004b86  sub     rsp, 20h
0x180004b8a  mov     rbx, rcx
0x180004b8d  lea     rdx, [rcx+0BCh]
0x180004b94  mov     rcx, [rcx+0D8h]
0x180004b9b  mov     r8d, 10h
0x180004ba1  mov     rax, [rbx+20h]
0x180004ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004baa  cmp     eax, 10h
0x180004bad  jnz     short loc_180004BCD
0x180004baf  lea     rcx, [rbx+10Ch]
0x180004bb6  mov     r8, rbx
0x180004bb9  call    FDIReadPSZ
0x180004bbe  test    eax, eax
0x180004bc0  jz      short loc_180004BCD
0x180004bc2  mov     eax, 1
0x180004bc7  add     rsp, 20h
0x180004bcb  pop     rbx
0x180004bcc  retn
0x180004bcd  mov     rax, [rbx]
0x180004bd0  mov     qword ptr [rax], 4
0x180004bd7  mov     dword ptr [rax+8], 1
0x180004bde  xor     eax, eax
0x180004be0  jmp     short loc_180004BC7
```
