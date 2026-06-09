# FileReadRoutine

- ea: `0x180147fc0`
- end: `0x18014804f`
- name: `FileReadRoutine`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180147fc0`
- `0x18015c080`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180147ff5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180147ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148005`

## pseudocode

```c
__int64 __fastcall FileReadRoutine(void *a1, DWORD a2, void *a3)
{
  signed int LastError; // eax
  unsigned int v5; // r10d
  unsigned int v6; // r10d
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v5 = -2147024809;
LABEL_9:
    LogErrorFxn(a1, v5);
    return v6;
  }
  if ( !ReadFile(a1, a3, a2, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_9;
  }
  return NumberOfBytesRead != a2 ? 0x8007001E : 0;
}

```

## disassembly

```asm
0x180147fc0  push    rbx
0x180147fc2  sub     rsp, 30h
0x180147fc6  mov     [rsp+38h+NumberOfBytesRead], 0
0x180147fce  mov     rax, r8
0x180147fd1  mov     ebx, edx
0x180147fd3  test    rcx, rcx
0x180147fd6  jz      short loc_180148037
0x180147fd8  test    edx, edx
0x180147fda  jz      short loc_180148037
0x180147fdc  test    rax, rax
0x180147fdf  jz      short loc_180148037
0x180147fe1  mov     r8d, edx; nNumberOfBytesToRead
0x180147fe4  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180147fed  mov     rdx, rax; lpBuffer
0x180147ff0  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180147ff5  call    cs:__imp_ReadFile
0x180147ffc  nop     dword ptr [rax+rax+00h]
0x180148001  test    eax, eax
0x180148003  jnz     short loc_180148025
0x180148005  call    cs:__imp_GetLastError
0x18014800c  nop     dword ptr [rax+rax+00h]
0x180148011  mov     r10d, eax
0x180148014  test    eax, eax
0x180148016  jle     short loc_18014803D
0x180148018  movzx   r10d, ax
0x18014801c  or      r10d, 80070000h
0x180148023  jmp     short loc_18014803D
0x180148025  sub     ebx, [rsp+38h+NumberOfBytesRead]
0x180148029  neg     ebx
0x18014802b  sbb     r10d, r10d
0x18014802e  and     r10d, 8007001Eh
0x180148035  jmp     short loc_180148045
0x180148037  mov     r10d, 80070057h
0x18014803d  mov     edx, r10d
0x180148040  call    LogErrorFxn
0x180148045  mov     eax, r10d
0x180148048  add     rsp, 30h
0x18014804c  pop     rbx
0x18014804d  retn
```
