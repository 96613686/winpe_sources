# NsiSetParameterEx

- ea: `0x180001330`
- end: `0x180001361`
- name: `NsiSetParameterEx`
- size: `49`
- prototype: `__int64 __fastcall(LPVOID lpOutBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800013b0`

## pseudocode

```c
DWORD __fastcall NsiSetParameterEx(DWORD *lpOutBuffer)
{
  return NsiIoctl(0x12000Bu, lpOutBuffer, 0x50u, lpOutBuffer, lpOutBuffer + 18, 0);
}

```

## disassembly

```asm
0x180001330  sub     rsp, 38h
0x180001334  lea     rax, [rcx+48h]
0x180001338  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180001341  mov     r9, rcx; lpOutBuffer
0x180001344  mov     [rsp+38h+lpBytesReturned], rax; lpBytesReturned
0x180001349  mov     rdx, rcx; lpInBuffer
0x18000134c  mov     r8d, 50h ; 'P'; nInBufferSize
0x180001352  mov     ecx, 12000Bh; dwIoControlCode
0x180001357  call    NsiIoctl
0x18000135c  add     rsp, 38h
0x180001360  retn
```
