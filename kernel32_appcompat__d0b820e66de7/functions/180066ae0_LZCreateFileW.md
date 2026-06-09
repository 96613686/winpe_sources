# LZCreateFileW

- ea: `0x180066ae0`
- end: `0x180066c0f`
- name: `LZCreateFileW`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001cb8c`
- `0x180066998`
- `0x180066ae0`
- `0x180066c20`
- `0x18007625c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066bac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066bca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066bac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066bca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180066b31`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180066b7c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180066b31`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180066b7c`

## pseudocode

```c
__int64 __fastcall LZCreateFileW(__int64 a1, DWORD a2, DWORD a3, DWORD a4, __int64 a5)
{
  HANDLE FileW; // rbx
  INT v10; // edi

  if ( (int)RtlStringCchCopyW(&Destination, 262, a1) < 0 )
    return 4294967289LL;
  FileW = CreateFileW(&Destination, a2, a3, 0, a4, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( NtCurrentTeb()->LastErrorValue != 2 )
      return 0xFFFFFFFFLL;
    MakeCompressedNameW();
    FileW = CreateFileW(&Destination, a2, a3, 0, a4, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
      return 0xFFFFFFFFLL;
  }
  if ( a4 == 3 )
  {
    v10 = LZInit((INT)FileW);
    if ( v10 < 0 )
      CloseHandle(FileW);
    if ( a5 && (int)RtlStringCchCopyW(a5, 260, &Destination) < 0 )
      return (unsigned int)-7;
  }
  else
  {
    v10 = ConvertWin32FHToDos((unsigned int)FileW);
    if ( v10 == -5 )
      CloseHandle(FileW);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180066ae0  push    rbx
0x180066ae2  push    rbp
0x180066ae3  push    rsi
0x180066ae4  push    rdi
0x180066ae5  sub     rsp, 48h
0x180066ae9  mov     esi, r8d
0x180066aec  mov     ebp, edx
0x180066aee  mov     r8, rcx
0x180066af1  mov     edx, 106h
0x180066af6  lea     rcx, Destination
0x180066afd  mov     edi, r9d
0x180066b00  call    RtlStringCchCopyW
0x180066b05  test    eax, eax
0x180066b07  js      loc_180066C00
0x180066b0d  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180066b16  lea     rcx, Destination; lpFileName
0x180066b1d  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180066b25  xor     r9d, r9d; lpSecurityAttributes
0x180066b28  mov     r8d, esi; dwShareMode
0x180066b2b  mov     [rsp+68h+dwCreationDisposition], edi; dwCreationDisposition
0x180066b2f  mov     edx, ebp; dwDesiredAccess
0x180066b31  call    cs:__imp_CreateFileW
0x180066b38  nop     dword ptr [rax+rax+00h]
0x180066b3d  mov     rbx, rax
0x180066b40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180066b44  jnz     short loc_180066B96
0x180066b46  mov     eax, gs:68h
0x180066b4e  cmp     eax, 2
0x180066b51  jnz     short loc_180066B91
0x180066b53  call    MakeCompressedNameW
0x180066b58  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180066b61  lea     rcx, Destination; lpFileName
0x180066b68  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180066b70  xor     r9d, r9d; lpSecurityAttributes
0x180066b73  mov     r8d, esi; dwShareMode
0x180066b76  mov     [rsp+68h+dwCreationDisposition], edi; dwCreationDisposition
0x180066b7a  mov     edx, ebp; dwDesiredAccess
0x180066b7c  call    cs:__imp_CreateFileW
0x180066b83  nop     dword ptr [rax+rax+00h]
0x180066b88  mov     rbx, rax
0x180066b8b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180066b8f  jnz     short loc_180066B96
0x180066b91  or      eax, 0FFFFFFFFh
0x180066b94  jmp     short loc_180066C05
0x180066b96  mov     ecx, ebx; hfSource
0x180066b98  cmp     edi, 3
0x180066b9b  jz      short loc_180066BBC
0x180066b9d  call    ConvertWin32FHToDos
0x180066ba2  mov     edi, eax
0x180066ba4  cmp     eax, 0FFFFFFFBh
0x180066ba7  jnz     short loc_180066BB8
0x180066ba9  mov     rcx, rbx; hObject
0x180066bac  call    cs:__imp_CloseHandle
0x180066bb3  nop     dword ptr [rax+rax+00h]
0x180066bb8  mov     eax, edi
0x180066bba  jmp     short loc_180066C05
0x180066bbc  call    LZInit
0x180066bc1  mov     edi, eax
0x180066bc3  test    eax, eax
0x180066bc5  jns     short loc_180066BD6
0x180066bc7  mov     rcx, rbx; hObject
0x180066bca  call    cs:__imp_CloseHandle
0x180066bd1  nop     dword ptr [rax+rax+00h]
0x180066bd6  mov     rcx, [rsp+68h+arg_20]
0x180066bde  test    rcx, rcx
0x180066be1  jz      short loc_180066BB8
0x180066be3  lea     r8, Destination
0x180066bea  mov     edx, 104h
0x180066bef  call    RtlStringCchCopyW
0x180066bf4  test    eax, eax
0x180066bf6  mov     ecx, 0FFFFFFF9h
0x180066bfb  cmovs   edi, ecx
0x180066bfe  jmp     short loc_180066BB8
0x180066c00  mov     eax, 0FFFFFFF9h
0x180066c05  add     rsp, 48h
0x180066c09  pop     rdi
0x180066c0a  pop     rsi
0x180066c0b  pop     rbp
0x180066c0c  pop     rbx
0x180066c0d  retn
```
