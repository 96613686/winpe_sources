# PinReadData(void *,KSSTREAM_HEADER *,_OVERLAPPED *)

- ea: `0x1800211cc`
- end: `0x18002124c`
- name: `?PinReadData@@YAJPEAXPEAUKSSTREAM_HEADER@@PEAU_OVERLAPPED@@@Z`
- size: `128`
- prototype: `__int64 __fastcall(void *, struct KSSTREAM_HEADER *, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001daa8`

## callees

- `0x180007684`
- `0x1800211cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021207`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800211fd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800211fd`

## pseudocode

```c
__int64 __fastcall PinReadData(void *a1, struct KSSTREAM_HEADER *a2, struct _OVERLAPPED *a3)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-28h]
  ULONG nOutBufferSize; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v9; // [rsp+58h] [rbp+10h] BYREF

  nOutBufferSize = a2->Size;
  v9 = 0;
  if ( DeviceIoControl(a1, 0x2F4017u, 0, 0, a2, nOutBufferSize, &v9, a3) )
    return 0;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError == 997 )
    return 0;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x277,
      (unsigned int)"avcore\\audiocore\\lib\\kslib\\kslib.cpp",
      (const char *)v4,
      v6);
  return v4;
}

```

## disassembly

```asm
0x1800211cc  mov     r11, rsp
0x1800211cf  push    rbx
0x1800211d0  sub     rsp, 40h
0x1800211d4  mov     [r11-10h], r8
0x1800211d8  lea     rax, [r11+10h]
0x1800211dc  mov     [r11-18h], rax
0x1800211e0  xor     r9d, r9d; nInBufferSize
0x1800211e3  mov     eax, [rdx]
0x1800211e5  xor     r8d, r8d; lpInBuffer
0x1800211e8  mov     [rsp+48h+nOutBufferSize], eax; nOutBufferSize
0x1800211ec  mov     [r11-28h], rdx
0x1800211f0  mov     edx, 2F4017h; dwIoControlCode
0x1800211f5  mov     [rsp+48h+arg_8], 0
0x1800211fd  call    cs:__imp_DeviceIoControl
0x180021203  test    eax, eax
0x180021205  jnz     short loc_180021244
0x180021207  call    cs:__imp_GetLastError
0x18002120d  mov     ebx, eax
0x18002120f  cmp     eax, 3E5h
0x180021214  jz      short loc_180021244
0x180021216  test    eax, eax
0x180021218  jle     short loc_180021223
0x18002121a  movzx   ebx, ax
0x18002121d  or      ebx, 80070000h
0x180021223  test    ebx, ebx
0x180021225  jns     short loc_180021240
0x180021227  mov     rcx, [rsp+48h]; this
0x18002122c  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\lib\\kslib\\kslib.cp"...
0x180021233  mov     r9d, ebx; char *
0x180021236  mov     edx, 277h; void *
0x18002123b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021240  mov     eax, ebx
0x180021242  jmp     short loc_180021246
0x180021244  xor     eax, eax
0x180021246  add     rsp, 40h
0x18002124a  pop     rbx
0x18002124b  retn
```
