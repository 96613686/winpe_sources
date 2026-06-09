# NsiCancelChangeNotification

- ea: `0x1800010a0`
- end: `0x1800010db`
- name: `NsiCancelChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800013b0`

## pseudocode

```c
DWORD __fastcall NsiCancelChangeNotification(__int64 a1)
{
  __int64 InBuffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp+10h] BYREF

  InBuffer = a1;
  BytesReturned = 0;
  return NsiIoctl(0x120040u, &InBuffer, 8u, 0, &BytesReturned, 0);
}

```

## disassembly

```asm
0x1800010a0  mov     [rsp+InBuffer], rcx
0x1800010a5  sub     rsp, 38h
0x1800010a9  xor     eax, eax
0x1800010ab  lea     rdx, [rsp+38h+InBuffer]; lpInBuffer
0x1800010b0  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x1800010b5  xor     r9d, r9d; lpOutBuffer
0x1800010b8  mov     [rsp+38h+BytesReturned], eax
0x1800010bc  mov     r8d, 8; nInBufferSize
0x1800010c2  lea     rax, [rsp+38h+BytesReturned]
0x1800010c7  mov     ecx, 120040h; dwIoControlCode
0x1800010cc  mov     [rsp+38h+lpBytesReturned], rax; lpBytesReturned
0x1800010d1  call    NsiIoctl
0x1800010d6  add     rsp, 38h
0x1800010da  retn
```
