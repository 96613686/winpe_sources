# _NMSG_WRITE

- ea: `0x18001880c`
- end: `0x1800189d1`
- name: `_NMSG_WRITE`
- size: `453`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f1a8`
- `0x18000fb64`
- `0x1800187c0`
- `0x180018ab8`

## callees

- `0x18000e318`
- `0x180010a14`
- `0x18001880c`
- `0x18001a970`
- `0x18001d184`
- `0x18001d1e4`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1800189c1`
- `KERNEL32!WriteFile` at `0x1800189c1`
- `KERNEL32!GetStdHandle` at `0x180018987`
- `KERNEL32!GetStdHandle` at `0x180018987`
- `KERNEL32!GetModuleFileNameA` at `0x1800188cd`
- `KERNEL32!GetModuleFileNameA` at `0x1800188cd`

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
    if ( a1 == *((_DWORD *)&unk_1800461B0 + 4 * (int)i) )
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
        v5 = (_BYTE *)*((_QWORD *)&unk_1800461B0 + 2 * (int)i + 1);
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
      byte_18006084D = 0;
      if ( !GetModuleFileNameA(0, byte_180060749, 0x104u) && strcpy_s(byte_180060749, 0x2FBu, "<program name unknown>") )
        invoke_watson(0, 0, 0, 0, 0);
      if ( strcat_s(Destination, 0x314u, "\n\n") )
        invoke_watson(0, 0, 0, 0, 0);
      if ( strcat_s(Destination, 0x314u, *((const char **)&unk_1800461B0 + 2 * (int)i + 1)) )
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
0x18001880c  push    rbx
0x18001880e  push    rbp
0x18001880f  push    rdi
0x180018810  push    r14
0x180018812  sub     rsp, 38h
0x180018816  mov     edi, ecx
0x180018818  mov     [rsp+58h+NumberOfBytesWritten], 0
0x180018820  xor     ebx, ebx
0x180018822  lea     r14, unk_1800461B0
0x180018829  movsxd  rax, ebx
0x18001882c  add     rax, rax
0x18001882f  cmp     edi, [r14+rax*8]
0x180018833  jz      short loc_18001883C
0x180018835  inc     ebx
0x180018837  cmp     ebx, 17h
0x18001883a  jb      short loc_180018829
0x18001883c  cmp     ebx, 17h
0x18001883f  jnb     loc_1800189C7
0x180018845  mov     ebp, 3
0x18001884a  mov     ecx, ebp; Mode
0x18001884c  call    _set_error_mode
0x180018851  cmp     eax, 1
0x180018854  jz      loc_180018982
0x18001885a  mov     ecx, ebp; Mode
0x18001885c  call    _set_error_mode
0x180018861  test    eax, eax
0x180018863  jnz     short loc_180018872
0x180018865  cmp     cs:__app_type, 1
0x18001886c  jz      loc_180018982
0x180018872  cmp     edi, 0FCh
0x180018878  jz      loc_1800189C7
0x18001887e  mov     ebp, 314h
0x180018883  lea     rdi, Destination
0x18001888a  mov     edx, ebp; SizeInBytes
0x18001888c  lea     r8, aRuntimeErrorPr; "Runtime Error!\n\nProgram: "
0x180018893  mov     rcx, rdi; Destination
0x180018896  call    strcpy_s
0x18001889b  test    eax, eax
0x18001889d  jz      short loc_1800188B7
0x18001889f  xor     r9d, r9d; LineNo
0x1800188a2  mov     [rsp+58h+Reserved], 0; Reserved
0x1800188ab  xor     r8d, r8d; FileName
0x1800188ae  xor     edx, edx; FunctionName
0x1800188b0  xor     ecx, ecx; Expression
0x1800188b2  call    _invoke_watson
0x1800188b7  mov     r8d, 104h; nSize
0x1800188bd  mov     cs:byte_18006084D, 0
0x1800188c4  lea     rdx, byte_180060749; lpFilename
0x1800188cb  xor     ecx, ecx; hModule
0x1800188cd  call    cs:__imp_GetModuleFileNameA
0x1800188d3  test    eax, eax
0x1800188d5  jnz     short loc_18001890B
0x1800188d7  lea     r8, aProgramNameUnk; "<program name unknown>"
0x1800188de  mov     edx, 2FBh; SizeInBytes
0x1800188e3  lea     rcx, byte_180060749; Destination
0x1800188ea  call    strcpy_s
0x1800188ef  test    eax, eax
0x1800188f1  jz      short loc_18001890B
0x1800188f3  xor     r9d, r9d; LineNo
0x1800188f6  mov     [rsp+58h+Reserved], 0; Reserved
0x1800188ff  xor     r8d, r8d; FileName
0x180018902  xor     edx, edx; FunctionName
0x180018904  xor     ecx, ecx; Expression
0x180018906  call    _invoke_watson
0x18001890b  lea     r8, asc_18004D890; "\n\n"
0x180018912  mov     rdx, rbp; SizeInBytes
0x180018915  mov     rcx, rdi; Destination
0x180018918  call    strcat_s
0x18001891d  test    eax, eax
0x18001891f  jz      short loc_180018939
0x180018921  xor     r9d, r9d; LineNo
0x180018924  mov     [rsp+58h+Reserved], 0; Reserved
0x18001892d  xor     r8d, r8d; FileName
0x180018930  xor     edx, edx; FunctionName
0x180018932  xor     ecx, ecx; Expression
0x180018934  call    _invoke_watson
0x180018939  movsxd  r8, ebx
0x18001893c  mov     rdx, rbp; SizeInBytes
0x18001893f  add     r8, r8
0x180018942  mov     rcx, rdi; Destination
0x180018945  mov     r8, [r14+r8*8+8]; Source
0x18001894a  call    strcat_s
0x18001894f  test    eax, eax
0x180018951  jz      short loc_18001896B
0x180018953  xor     r9d, r9d; LineNo
0x180018956  mov     [rsp+58h+Reserved], 0; Reserved
0x18001895f  xor     r8d, r8d; FileName
0x180018962  xor     edx, edx; FunctionName
0x180018964  xor     ecx, ecx; Expression
0x180018966  call    _invoke_watson
0x18001896b  mov     r8d, 12010h
0x180018971  lea     rdx, aMicrosoftVisua; "Microsoft Visual C++ Runtime Library"
0x180018978  mov     rcx, rdi
0x18001897b  call    __crtMessageBoxA
0x180018980  jmp     short loc_1800189C7
0x180018982  mov     ecx, 0FFFFFFF4h; nStdHandle
0x180018987  call    cs:__imp_GetStdHandle
0x18001898d  lea     rcx, [rax-1]
0x180018991  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180018995  ja      short loc_1800189C7
0x180018997  movsxd  rcx, ebx
0x18001899a  add     rcx, rcx
0x18001899d  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800189a1  mov     rdx, [r14+rcx*8+8]; lpBuffer
0x1800189a6  inc     r8; nNumberOfBytesToWrite
0x1800189a9  cmp     byte ptr [rdx+r8], 0
0x1800189ae  jnz     short loc_1800189A6
0x1800189b0  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800189b5  mov     [rsp+58h+Reserved], 0; lpOverlapped
0x1800189be  mov     rcx, rax; hFile
0x1800189c1  call    cs:__imp_WriteFile
0x1800189c7  add     rsp, 38h
0x1800189cb  pop     r14
0x1800189cd  pop     rdi
0x1800189ce  pop     rbp
0x1800189cf  pop     rbx
0x1800189d0  retn
```
