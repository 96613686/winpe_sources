# NsiGetObjectSecurity

- ea: `0x180002b50`
- end: `0x180002b86`
- name: `NsiGetObjectSecurity`
- size: `54`
- prototype: `__int64 __fastcall(LPVOID lpOutBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800013b0`

## pseudocode

```c
DWORD __fastcall NsiGetObjectSecurity(LPVOID lpOutBuffer)
{
  DWORD v2; // [rsp+48h] [rbp+10h] BYREF

  v2 = 48;
  return NsiIoctl(0x120037u, lpOutBuffer, 0x30u, lpOutBuffer, &v2, 0);
}

```

## disassembly

```asm
0x180002b50  mov     r11, rsp
0x180002b53  sub     rsp, 38h
0x180002b57  mov     r8d, 30h ; '0'; nInBufferSize
0x180002b5d  mov     qword ptr [r11-10h], 0
0x180002b65  lea     rax, [r11+10h]
0x180002b69  mov     [r11+10h], r8d
0x180002b6d  mov     r9, rcx; lpOutBuffer
0x180002b70  mov     [r11-18h], rax
0x180002b74  mov     rdx, rcx; lpInBuffer
0x180002b77  mov     ecx, 120037h; dwIoControlCode
0x180002b7c  call    NsiIoctl
0x180002b81  add     rsp, 38h
0x180002b85  retn
```
