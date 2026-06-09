# NsiSetAllParametersEx

- ea: `0x1800011a0`
- end: `0x1800011da`
- name: `NsiSetAllParametersEx`
- size: `58`
- prototype: `__int64 __fastcall(LPVOID lpOutBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800013b0`

## pseudocode

```c
DWORD __fastcall NsiSetAllParametersEx(LPVOID lpOutBuffer)
{
  DWORD BytesReturned; // [rsp+48h] [rbp+10h] BYREF

  BytesReturned = 72;
  return NsiIoctl(0x120013u, lpOutBuffer, 0x48u, lpOutBuffer, &BytesReturned, 0);
}

```

## disassembly

```asm
0x1800011a0  sub     rsp, 38h
0x1800011a4  lea     rax, [rsp+38h+BytesReturned]
0x1800011a9  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800011b2  mov     r9, rcx; lpOutBuffer
0x1800011b5  mov     [rsp+38h+lpBytesReturned], rax; lpBytesReturned
0x1800011ba  mov     rdx, rcx; lpInBuffer
0x1800011bd  mov     [rsp+38h+BytesReturned], 48h ; 'H'
0x1800011c5  mov     ecx, 120013h; dwIoControlCode
0x1800011ca  mov     r8d, 48h ; 'H'; nInBufferSize
0x1800011d0  call    NsiIoctl
0x1800011d5  add     rsp, 38h
0x1800011d9  retn
```
