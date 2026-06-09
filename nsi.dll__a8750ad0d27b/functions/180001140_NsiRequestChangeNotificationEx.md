# NsiRequestChangeNotificationEx

- ea: `0x180001140`
- end: `0x18000119a`
- name: `NsiRequestChangeNotificationEx`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD *lpInBuffer)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010f0`

## callees

- `0x180001140`
- `0x1800013b0`

## pseudocode

```c
__int64 __fastcall NsiRequestChangeNotificationEx(_QWORD *lpInBuffer)
{
  __int64 result; // rax
  _QWORD *v3; // rdx
  struct _OVERLAPPED *lpOverlapped; // [rsp+28h] [rbp-10h]
  DWORD BytesReturned; // [rsp+40h] [rbp+8h] BYREF

  lpOverlapped = (struct _OVERLAPPED *)lpInBuffer[3];
  BytesReturned = 40;
  result = NsiIoctl(0x12003Fu, lpInBuffer, 0x28u, 0, &BytesReturned, lpOverlapped);
  v3 = (_QWORD *)lpInBuffer[4];
  if ( v3 )
  {
    if ( lpInBuffer[3] )
      *v3 = g_NsiAsyncDeviceHandle;
  }
  return result;
}

```

## disassembly

```asm
0x180001140  push    rbx
0x180001142  sub     rsp, 30h
0x180001146  mov     rax, [rcx+18h]
0x18000114a  mov     rbx, rcx
0x18000114d  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x180001152  mov     rdx, rcx; lpInBuffer
0x180001155  lea     rax, [rsp+38h+BytesReturned]
0x18000115a  mov     [rsp+38h+BytesReturned], 28h ; '('
0x180001162  xor     r9d, r9d; lpOutBuffer
0x180001165  mov     [rsp+38h+lpBytesReturned], rax; lpBytesReturned
0x18000116a  mov     r8d, 28h ; '('; nInBufferSize
0x180001170  mov     ecx, 12003Fh; dwIoControlCode
0x180001175  call    NsiIoctl
0x18000117a  mov     rdx, [rbx+20h]
0x18000117e  test    rdx, rdx
0x180001181  jz      short loc_180001194
0x180001183  cmp     qword ptr [rbx+18h], 0
0x180001188  jz      short loc_180001194
0x18000118a  mov     rcx, cs:g_NsiAsyncDeviceHandle
0x180001191  mov     [rdx], rcx
0x180001194  add     rsp, 30h
0x180001198  pop     rbx
0x180001199  retn
```
