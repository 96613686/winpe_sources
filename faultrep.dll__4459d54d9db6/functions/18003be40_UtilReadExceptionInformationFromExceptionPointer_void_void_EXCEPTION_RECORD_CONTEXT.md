# UtilReadExceptionInformationFromExceptionPointer(void *,void *,_EXCEPTION_RECORD *,_CONTEXT *)

- ea: `0x18003be40`
- end: `0x18003bf31`
- name: `?UtilReadExceptionInformationFromExceptionPointer@@YAJPEAX0PEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@@Z`
- size: `241`
- prototype: `signed int __fastcall(HANDLE hProcess, void *, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800124b8`

## callees

- `0x18003be40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be85`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003be7b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003bec3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003befa`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003be7b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003bec3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003befa`

## pseudocode

```c
signed int __fastcall UtilReadExceptionInformationFromExceptionPointer(
        HANDLE hProcess,
        void *a2,
        struct _EXCEPTION_RECORD *a3,
        struct _CONTEXT *a4)
{
  signed int result; // eax
  SIZE_T NumberOfBytesRead; // [rsp+30h] [rbp-28h] BYREF
  LPCVOID lpBaseAddress[4]; // [rsp+38h] [rbp-20h] BYREF

  NumberOfBytesRead = 0;
  *(_OWORD *)lpBaseAddress = 0;
  if ( !ReadProcessMemory(hProcess, a2, lpBaseAddress, 0x10u, &NumberOfBytesRead) )
    goto LABEL_2;
  if ( NumberOfBytesRead != 16 )
    return -2147024597;
  if ( ReadProcessMemory(hProcess, lpBaseAddress[0], a3, 0x98u, &NumberOfBytesRead) )
  {
    if ( NumberOfBytesRead == 152 )
    {
      if ( !a4 )
        return 0;
      if ( ReadProcessMemory(hProcess, lpBaseAddress[1], a4, 0x4D0u, &NumberOfBytesRead) )
        return NumberOfBytesRead != 1232 ? 0x8007012B : 0;
      goto LABEL_2;
    }
    return -2147024597;
  }
LABEL_2:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003be40  mov     r11, rsp
0x18003be43  mov     [r11+8], rbx
0x18003be47  mov     [r11+10h], rsi
0x18003be4b  push    rdi
0x18003be4c  sub     rsp, 50h
0x18003be50  mov     rbx, r9
0x18003be53  mov     qword ptr [r11-28h], 0
0x18003be5b  mov     rsi, r8
0x18003be5e  lea     rax, [r11-28h]
0x18003be62  xorps   xmm0, xmm0
0x18003be65  mov     [r11-38h], rax
0x18003be69  mov     r9d, 10h; nSize
0x18003be6f  lea     r8, [r11-20h]; lpBuffer
0x18003be73  movups  xmmword ptr [rsp+58h+lpBaseAddress], xmm0
0x18003be78  mov     rdi, rcx
0x18003be7b  call    cs:__imp_ReadProcessMemory
0x18003be81  test    eax, eax
0x18003be83  jnz     short loc_18003BEA0
0x18003be85  call    cs:__imp_GetLastError
0x18003be8b  test    eax, eax
0x18003be8d  jle     loc_18003BF21
0x18003be93  movzx   eax, ax
0x18003be96  or      eax, 80070000h
0x18003be9b  jmp     loc_18003BF21
0x18003bea0  cmp     [rsp+58h+NumberOfBytesRead], 10h
0x18003bea6  jnz     short loc_18003BF1C
0x18003bea8  mov     rdx, [rsp+58h+lpBaseAddress]; lpBaseAddress
0x18003bead  lea     rax, [rsp+58h+NumberOfBytesRead]
0x18003beb2  mov     r9d, 98h; nSize
0x18003beb8  mov     [rsp+58h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18003bebd  mov     r8, rsi; lpBuffer
0x18003bec0  mov     rcx, rdi; hProcess
0x18003bec3  call    cs:__imp_ReadProcessMemory
0x18003bec9  test    eax, eax
0x18003becb  jz      short loc_18003BE85
0x18003becd  cmp     [rsp+58h+NumberOfBytesRead], 98h
0x18003bed6  jnz     short loc_18003BF1C
0x18003bed8  test    rbx, rbx
0x18003bedb  jz      short loc_18003BF18
0x18003bedd  mov     rdx, [rsp+58h+lpBaseAddress+8]; lpBaseAddress
0x18003bee2  lea     rax, [rsp+58h+NumberOfBytesRead]
0x18003bee7  mov     esi, 4D0h
0x18003beec  mov     [rsp+58h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18003bef1  mov     r9d, esi; nSize
0x18003bef4  mov     r8, rbx; lpBuffer
0x18003bef7  mov     rcx, rdi; hProcess
0x18003befa  call    cs:__imp_ReadProcessMemory
0x18003bf00  test    eax, eax
0x18003bf02  jz      short loc_18003BE85
0x18003bf04  mov     rax, [rsp+58h+NumberOfBytesRead]
0x18003bf09  sub     rax, rsi
0x18003bf0c  neg     rax
0x18003bf0f  sbb     eax, eax
0x18003bf11  and     eax, 8007012Bh
0x18003bf16  jmp     short loc_18003BF21
0x18003bf18  xor     eax, eax
0x18003bf1a  jmp     short loc_18003BF21
0x18003bf1c  mov     eax, 8007012Bh
0x18003bf21  mov     rbx, [rsp+58h+arg_0]
0x18003bf26  mov     rsi, [rsp+58h+arg_8]
0x18003bf2b  add     rsp, 50h
0x18003bf2f  pop     rdi
0x18003bf30  retn
```
