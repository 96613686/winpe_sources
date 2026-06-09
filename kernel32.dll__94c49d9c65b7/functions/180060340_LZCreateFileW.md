# LZCreateFileW

- ea: `0x180060340`
- end: `0x180060456`
- name: `LZCreateFileW`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001ece0`
- `0x180060224`
- `0x180060340`
- `0x180060460`
- `0x18006e8b8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060418`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060391`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800603d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060391`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800603d6`

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
0x180060340  push    rbx
0x180060342  push    rbp
0x180060343  push    rsi
0x180060344  push    rdi
0x180060345  sub     rsp, 48h
0x180060349  mov     esi, r8d
0x18006034c  mov     ebp, edx
0x18006034e  mov     r8, rcx
0x180060351  mov     edx, 106h
0x180060356  lea     rcx, Destination
0x18006035d  mov     edi, r9d
0x180060360  call    RtlStringCchCopyW
0x180060365  test    eax, eax
0x180060367  js      loc_180060448
0x18006036d  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180060376  lea     rcx, Destination; lpFileName
0x18006037d  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180060385  xor     r9d, r9d; lpSecurityAttributes
0x180060388  mov     r8d, esi; dwShareMode
0x18006038b  mov     [rsp+68h+dwCreationDisposition], edi; dwCreationDisposition
0x18006038f  mov     edx, ebp; dwDesiredAccess
0x180060391  call    cs:__imp_CreateFileW
0x180060397  mov     rbx, rax
0x18006039a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006039e  jnz     short loc_1800603EA
0x1800603a0  mov     eax, gs:68h
0x1800603a8  cmp     eax, 2
0x1800603ab  jnz     short loc_1800603E5
0x1800603ad  call    MakeCompressedNameW
0x1800603b2  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800603bb  lea     rcx, Destination; lpFileName
0x1800603c2  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800603ca  xor     r9d, r9d; lpSecurityAttributes
0x1800603cd  mov     r8d, esi; dwShareMode
0x1800603d0  mov     [rsp+68h+dwCreationDisposition], edi; dwCreationDisposition
0x1800603d4  mov     edx, ebp; dwDesiredAccess
0x1800603d6  call    cs:__imp_CreateFileW
0x1800603dc  mov     rbx, rax
0x1800603df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800603e3  jnz     short loc_1800603EA
0x1800603e5  or      eax, 0FFFFFFFFh
0x1800603e8  jmp     short loc_18006044D
0x1800603ea  mov     ecx, ebx; hfSource
0x1800603ec  cmp     edi, 3
0x1800603ef  jz      short loc_18006040A
0x1800603f1  call    ConvertWin32FHToDos
0x1800603f6  mov     edi, eax
0x1800603f8  cmp     eax, 0FFFFFFFBh
0x1800603fb  jnz     short loc_180060406
0x1800603fd  mov     rcx, rbx; hObject
0x180060400  call    cs:__imp_CloseHandle
0x180060406  mov     eax, edi
0x180060408  jmp     short loc_18006044D
0x18006040a  call    LZInit
0x18006040f  mov     edi, eax
0x180060411  test    eax, eax
0x180060413  jns     short loc_18006041E
0x180060415  mov     rcx, rbx; hObject
0x180060418  call    cs:__imp_CloseHandle
0x18006041e  mov     rcx, [rsp+68h+arg_20]
0x180060426  test    rcx, rcx
0x180060429  jz      short loc_180060406
0x18006042b  lea     r8, Destination
0x180060432  mov     edx, 104h
0x180060437  call    RtlStringCchCopyW
0x18006043c  test    eax, eax
0x18006043e  mov     ecx, 0FFFFFFF9h
0x180060443  cmovs   edi, ecx
0x180060446  jmp     short loc_180060406
0x180060448  mov     eax, 0FFFFFFF9h
0x18006044d  add     rsp, 48h
0x180060451  pop     rdi
0x180060452  pop     rsi
0x180060453  pop     rbp
0x180060454  pop     rbx
0x180060455  retn
```
