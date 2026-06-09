# _NMSG_WRITE

- ea: `0x18003f8e4`
- end: `0x18003faa9`
- name: `_NMSG_WRITE`
- size: `453`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d350`
- `0x18003d7e0`
- `0x18003e790`
- `0x18003f898`

## callees

- `0x18002e600`
- `0x18002f05c`
- `0x180036b64`
- `0x18003f8e4`
- `0x180060c90`
- `0x180060db0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003fa99`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003fa99`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18003f9a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18003f9a5`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18003fa5f`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18003fa5f`

## pseudocode

```c
int __fastcall NMSG_WRITE(int a1)
{
  unsigned int i; // ebx
  char *StdHandle; // rax
  __int64 v4; // r8
  _BYTE *v5; // rdx
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+10h] BYREF

  NumberOfBytesWritten = 0;
  for ( i = 0; i < 0x17; ++i )
  {
    LODWORD(StdHandle) = 2 * i;
    if ( a1 == LODWORD(qword_18007EC30[2 * (int)i]) )
      break;
  }
  if ( i < 0x17 )
  {
    if ( set_error_mode(3) == 1 || (LODWORD(StdHandle) = set_error_mode(3), !(_DWORD)StdHandle) && _app_type == 1 )
    {
      StdHandle = (char *)GetStdHandle(0xFFFFFFF4);
      if ( (unsigned __int64)(StdHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v4 = -1;
        v5 = (_BYTE *)qword_18007EC30[2 * (int)i + 1];
        do
          ++v4;
        while ( v5[v4] );
        LODWORD(StdHandle) = WriteFile(StdHandle, v5, v4, &NumberOfBytesWritten, 0);
      }
    }
    else if ( a1 != 252 )
    {
      if ( strcpy_s(Destination, 0x314u, "Runtime Error!\n\nProgram: ") )
        invoke_watson(0, 0, 0, 0, 0);
      byte_18009F05D = 0;
      if ( !GetModuleFileNameA(0, byte_18009EF59, 0x104u) && strcpy_s(byte_18009EF59, 0x2FBu, "<program name unknown>") )
        invoke_watson(0, 0, 0, 0, 0);
      if ( strcat_s(Destination, 0x314u, "\n\n") )
        invoke_watson(0, 0, 0, 0, 0);
      if ( strcat_s(Destination, 0x314u, (const char *)qword_18007EC30[2 * (int)i + 1]) )
        invoke_watson(0, 0, 0, 0, 0);
      LODWORD(StdHandle) = _crtMessageBoxA(
                             (__int64)Destination,
                             (__int64)"Microsoft Visual C++ Runtime Library",
                             0x12010u);
    }
  }
  return (int)StdHandle;
}

```

## disassembly

```asm
0x18003f8e4  push    rbx
0x18003f8e6  push    rbp
0x18003f8e7  push    rdi
0x18003f8e8  push    r14
0x18003f8ea  sub     rsp, 38h
0x18003f8ee  mov     edi, ecx
0x18003f8f0  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18003f8f8  xor     ebx, ebx
0x18003f8fa  lea     r14, qword_18007EC30
0x18003f901  movsxd  rax, ebx
0x18003f904  add     rax, rax
0x18003f907  cmp     edi, [r14+rax*8]
0x18003f90b  jz      short loc_18003F914
0x18003f90d  inc     ebx
0x18003f90f  cmp     ebx, 17h
0x18003f912  jb      short loc_18003F901
0x18003f914  cmp     ebx, 17h
0x18003f917  jnb     loc_18003FA9F
0x18003f91d  mov     ebp, 3
0x18003f922  mov     ecx, ebp; Mode
0x18003f924  call    _set_error_mode
0x18003f929  cmp     eax, 1
0x18003f92c  jz      loc_18003FA5A
0x18003f932  mov     ecx, ebp; Mode
0x18003f934  call    _set_error_mode
0x18003f939  test    eax, eax
0x18003f93b  jnz     short loc_18003F94A
0x18003f93d  cmp     cs:__app_type, 1
0x18003f944  jz      loc_18003FA5A
0x18003f94a  cmp     edi, 0FCh
0x18003f950  jz      loc_18003FA9F
0x18003f956  mov     ebp, 314h
0x18003f95b  lea     rdi, Destination
0x18003f962  mov     edx, ebp; SizeInBytes
0x18003f964  lea     r8, aRuntimeErrorPr; "Runtime Error!\n\nProgram: "
0x18003f96b  mov     rcx, rdi; Destination
0x18003f96e  call    strcpy_s
0x18003f973  test    eax, eax
0x18003f975  jz      short loc_18003F98F
0x18003f977  xor     r9d, r9d; LineNo
0x18003f97a  mov     [rsp+58h+Reserved], 0; Reserved
0x18003f983  xor     r8d, r8d; FileName
0x18003f986  xor     edx, edx; FunctionName
0x18003f988  xor     ecx, ecx; Expression
0x18003f98a  call    _invoke_watson
0x18003f98f  mov     r8d, 104h; nSize
0x18003f995  mov     cs:byte_18009F05D, 0
0x18003f99c  lea     rdx, byte_18009EF59; lpFilename
0x18003f9a3  xor     ecx, ecx; hModule
0x18003f9a5  call    cs:__imp_GetModuleFileNameA
0x18003f9ab  test    eax, eax
0x18003f9ad  jnz     short loc_18003F9E3
0x18003f9af  lea     r8, aProgramNameUnk; "<program name unknown>"
0x18003f9b6  mov     edx, 2FBh; SizeInBytes
0x18003f9bb  lea     rcx, byte_18009EF59; Destination
0x18003f9c2  call    strcpy_s
0x18003f9c7  test    eax, eax
0x18003f9c9  jz      short loc_18003F9E3
0x18003f9cb  xor     r9d, r9d; LineNo
0x18003f9ce  mov     [rsp+58h+Reserved], 0; Reserved
0x18003f9d7  xor     r8d, r8d; FileName
0x18003f9da  xor     edx, edx; FunctionName
0x18003f9dc  xor     ecx, ecx; Expression
0x18003f9de  call    _invoke_watson
0x18003f9e3  lea     r8, asc_18008368C; "\n\n"
0x18003f9ea  mov     rdx, rbp; SizeInBytes
0x18003f9ed  mov     rcx, rdi; Destination
0x18003f9f0  call    strcat_s
0x18003f9f5  test    eax, eax
0x18003f9f7  jz      short loc_18003FA11
0x18003f9f9  xor     r9d, r9d; LineNo
0x18003f9fc  mov     [rsp+58h+Reserved], 0; Reserved
0x18003fa05  xor     r8d, r8d; FileName
0x18003fa08  xor     edx, edx; FunctionName
0x18003fa0a  xor     ecx, ecx; Expression
0x18003fa0c  call    _invoke_watson
0x18003fa11  movsxd  r8, ebx
0x18003fa14  mov     rdx, rbp; SizeInBytes
0x18003fa17  add     r8, r8
0x18003fa1a  mov     rcx, rdi; Destination
0x18003fa1d  mov     r8, [r14+r8*8+8]; Source
0x18003fa22  call    strcat_s
0x18003fa27  test    eax, eax
0x18003fa29  jz      short loc_18003FA43
0x18003fa2b  xor     r9d, r9d; LineNo
0x18003fa2e  mov     [rsp+58h+Reserved], 0; Reserved
0x18003fa37  xor     r8d, r8d; FileName
0x18003fa3a  xor     edx, edx; FunctionName
0x18003fa3c  xor     ecx, ecx; Expression
0x18003fa3e  call    _invoke_watson
0x18003fa43  mov     r8d, 12010h
0x18003fa49  lea     rdx, aMicrosoftVisua; "Microsoft Visual C++ Runtime Library"
0x18003fa50  mov     rcx, rdi
0x18003fa53  call    __crtMessageBoxA
0x18003fa58  jmp     short loc_18003FA9F
0x18003fa5a  mov     ecx, 0FFFFFFF4h; nStdHandle
0x18003fa5f  call    cs:__imp_GetStdHandle
0x18003fa65  lea     rcx, [rax-1]
0x18003fa69  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003fa6d  ja      short loc_18003FA9F
0x18003fa6f  movsxd  rcx, ebx
0x18003fa72  add     rcx, rcx
0x18003fa75  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003fa79  mov     rdx, [r14+rcx*8+8]; lpBuffer
0x18003fa7e  inc     r8; nNumberOfBytesToWrite
0x18003fa81  cmp     byte ptr [rdx+r8], 0
0x18003fa86  jnz     short loc_18003FA7E
0x18003fa88  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003fa8d  mov     [rsp+58h+Reserved], 0; lpOverlapped
0x18003fa96  mov     rcx, rax; hFile
0x18003fa99  call    cs:__imp_WriteFile
0x18003fa9f  add     rsp, 38h
0x18003faa3  pop     r14
0x18003faa5  pop     rdi
0x18003faa6  pop     rbp
0x18003faa7  pop     rbx
0x18003faa8  retn
```
