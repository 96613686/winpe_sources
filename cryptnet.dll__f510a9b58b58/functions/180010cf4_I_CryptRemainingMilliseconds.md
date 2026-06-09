# I_CryptRemainingMilliseconds

- ea: `0x180010cf4`
- end: `0x180010d48`
- name: `I_CryptRemainingMilliseconds`
- size: `84`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime1)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008f80`
- `0x18000fb70`

## callees

- `0x180010cf4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010d0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010d0b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010d19`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010d19`

## pseudocode

```c
__int64 __fastcall I_CryptRemainingMilliseconds(FILETIME *lpFileTime1)
{
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+10h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( CompareFileTime(lpFileTime1, &SystemTimeAsFileTime) <= 0 )
    return 0;
  else
    return (unsigned int)((*(_QWORD *)lpFileTime1 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
}

```

## disassembly

```asm
0x180010cf4  push    rbx
0x180010cf6  sub     rsp, 20h
0x180010cfa  mov     rbx, rcx
0x180010cfd  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180010d06  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010d0b  call    cs:__imp_GetSystemTimeAsFileTime
0x180010d11  lea     rdx, [rsp+28h+SystemTimeAsFileTime]; lpFileTime2
0x180010d16  mov     rcx, rbx; lpFileTime1
0x180010d19  call    cs:__imp_CompareFileTime
0x180010d1f  test    eax, eax
0x180010d21  jle     short loc_180010D44
0x180010d23  mov     rcx, [rbx]
0x180010d26  mov     rax, 346DC5D63886594Bh
0x180010d30  sub     rcx, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180010d35  mul     rcx
0x180010d38  shr     rdx, 0Bh
0x180010d3c  mov     eax, edx
0x180010d3e  add     rsp, 20h
0x180010d42  pop     rbx
0x180010d43  retn
0x180010d44  xor     eax, eax
0x180010d46  jmp     short loc_180010D3E
```
