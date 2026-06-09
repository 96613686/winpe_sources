# NsiDeregisterChangeNotificationEx

- ea: `0x180001370`
- end: `0x1800013aa`
- name: `NsiDeregisterChangeNotificationEx`
- size: `58`
- prototype: `__int64 __fastcall(LPVOID lpOutBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800013b0`

## pseudocode

```c
DWORD __fastcall NsiDeregisterChangeNotificationEx(LPVOID lpOutBuffer)
{
  DWORD BytesReturned; // [rsp+48h] [rbp+10h] BYREF

  BytesReturned = 40;
  return NsiIoctl(0x120023u, lpOutBuffer, 0x28u, lpOutBuffer, &BytesReturned, 0);
}

```

## disassembly

```asm
0x180001370  sub     rsp, 38h
0x180001374  lea     rax, [rsp+38h+BytesReturned]
0x180001379  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180001382  mov     r9, rcx; lpOutBuffer
0x180001385  mov     [rsp+38h+lpBytesReturned], rax; lpBytesReturned
0x18000138a  mov     rdx, rcx; lpInBuffer
0x18000138d  mov     [rsp+38h+BytesReturned], 28h ; '('
0x180001395  mov     ecx, 120023h; dwIoControlCode
0x18000139a  mov     r8d, 28h ; '('; nInBufferSize
0x1800013a0  call    NsiIoctl
0x1800013a5  add     rsp, 38h
0x1800013a9  retn
```
