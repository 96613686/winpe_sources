# HvServiceUtil::Ioctl(ulong,void const *,ulong,void *,ulong)

- ea: `0x180007594`
- end: `0x1800075e3`
- name: `?Ioctl@HvServiceUtil@@AEBAXKPEBXKPEAXK@Z`
- size: `79`
- prototype: `void __fastcall(HANDLE *this, DWORD, void *, DWORD, void *lpOutBuffer, DWORD nOutBufferSize)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001a80`
- `0x1800077e0`
- `0x180007af8`
- `0x180008700`

## callees

- `0x180007594`
- `0x180007f3c`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800075bf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800075bf`

## string_xrefs

- `0x1800075ce`: `onecore\hv\common\inc\HvServiceUtil.h`

## pseudocode

```c
void __fastcall HvServiceUtil::Ioctl(
        HANDLE *this,
        DWORD a2,
        void *a3,
        DWORD a4,
        void *lpOutBuffer,
        DWORD nOutBufferSize)
{
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !DeviceIoControl(*this, a2, a3, a4, lpOutBuffer, nOutBufferSize, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\hv\\common\\inc\\HvServiceUtil.h",
      v6);
}

```

## disassembly

```asm
0x180007594  sub     rsp, 48h
0x180007598  mov     eax, [rsp+48h+arg_28]
0x18000759c  mov     rcx, [rcx]; hDevice
0x18000759f  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800075a8  mov     [rsp+48h+lpBytesReturned], 0; lpBytesReturned
0x1800075b1  mov     [rsp+48h+nOutBufferSize], eax; nOutBufferSize
0x1800075b5  mov     rax, [rsp+48h+arg_20]
0x1800075ba  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x1800075bf  call    cs:__imp_DeviceIoControl
0x1800075c5  test    eax, eax
0x1800075c7  jnz     short loc_1800075DE
0x1800075c9  mov     rcx, [rsp+48h]; this
0x1800075ce  lea     r8, aOnecoreHvCommo; "onecore\\hv\\common\\inc\\HvServiceUtil"...
0x1800075d5  lea     edx, [rax+28h]; void *
0x1800075d8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800075de  add     rsp, 48h
0x1800075e2  retn
```
