# NsiSetObjectSecurity

- ea: `0x180002b90`
- end: `0x180002bc6`
- name: `NsiSetObjectSecurity`
- size: `54`
- prototype: `__int64 __fastcall(LPVOID lpOutBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800013b0`

## pseudocode

```c
DWORD __fastcall NsiSetObjectSecurity(LPVOID lpOutBuffer)
{
  DWORD v2; // [rsp+48h] [rbp+10h] BYREF

  v2 = 48;
  return NsiIoctl(0x12003Bu, lpOutBuffer, 0x30u, lpOutBuffer, &v2, 0);
}

```

## disassembly

```asm
0x180002b90  mov     r11, rsp
0x180002b93  sub     rsp, 38h
0x180002b97  mov     r8d, 30h ; '0'; nInBufferSize
0x180002b9d  mov     qword ptr [r11-10h], 0
0x180002ba5  lea     rax, [r11+10h]
0x180002ba9  mov     [r11+10h], r8d
0x180002bad  mov     r9, rcx; lpOutBuffer
0x180002bb0  mov     [r11-18h], rax
0x180002bb4  mov     rdx, rcx; lpInBuffer
0x180002bb7  mov     ecx, 12003Bh; dwIoControlCode
0x180002bbc  call    NsiIoctl
0x180002bc1  add     rsp, 38h
0x180002bc5  retn
```
