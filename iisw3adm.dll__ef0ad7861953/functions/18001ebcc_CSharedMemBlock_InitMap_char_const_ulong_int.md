# CSharedMemBlock::InitMap(char const *,ulong,int)

- ea: `0x18001ebcc`
- end: `0x18001ecc9`
- name: `?InitMap@CSharedMemBlock@@QEAAJPEBDKH@Z`
- size: `253`
- prototype: `int(CSharedMemBlock *__hidden this, const char *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001e7b0`

## callees

- `0x18001ebcc`
- `0x18001ecd0`
- `0x18006101a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec99`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ec82`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ec82`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18001ec0b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18001ec0b`
- `api-ms-win-core-kernel32-legacy-l1-1-2!OpenFileMappingA` at `0x18001ec5d`
- `api-ms-win-core-kernel32-legacy-l1-1-2!OpenFileMappingA` at `0x18001ec5d`

## pseudocode

```c
int __fastcall CSharedMemBlock::InitMap(CSharedMemBlock *this, const char *a2, unsigned int a3, int a4)
{
  size_t dwMaximumSizeLow; // rsi
  int result; // eax
  HANDLE FileMappingA; // rax
  HANDLE v10; // rax
  void *v11; // rax

  dwMaximumSizeLow = a3;
  if ( a4 )
  {
    result = CSharedMemBlock::InitSD(this);
    if ( result < 0 )
      return result;
    FileMappingA = CreateFileMappingA(
                     (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                     (LPSECURITY_ATTRIBUTES)((char *)this + 16),
                     4u,
                     0,
                     dwMaximumSizeLow,
                     a2);
    *(_QWORD *)this = FileMappingA;
    if ( !FileMappingA )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( GetLastError() == 183 )
    {
      CloseHandle(*(HANDLE *)this);
      result = -2147024713;
      *(_QWORD *)this = 0;
      return result;
    }
  }
  else
  {
    v10 = OpenFileMappingA(6u, 0, a2);
    *(_QWORD *)this = v10;
    if ( !v10 )
      return -2147467259;
  }
  v11 = MapViewOfFile(*(HANDLE *)this, 0xF001Fu, 0, 0, 0);
  *((_QWORD *)this + 1) = v11;
  if ( !v11 )
  {
    if ( *(_QWORD *)this )
    {
      CloseHandle(*(HANDLE *)this);
      *(_QWORD *)this = 0;
    }
    return -2147467259;
  }
  if ( a4 )
    memset_0(v11, 0, dwMaximumSizeLow);
  return 0;
}

```

## disassembly

```asm
0x18001ebcc  push    rbx
0x18001ebce  push    rbp
0x18001ebcf  push    rsi
0x18001ebd0  push    rdi
0x18001ebd1  sub     rsp, 38h
0x18001ebd5  mov     esi, r8d
0x18001ebd8  mov     edi, r9d
0x18001ebdb  mov     rbp, rdx
0x18001ebde  mov     rbx, rcx
0x18001ebe1  test    r9d, r9d
0x18001ebe4  jz      short loc_18001EC55
0x18001ebe6  call    ?InitSD@CSharedMemBlock@@QEAAJXZ; CSharedMemBlock::InitSD(void)
0x18001ebeb  test    eax, eax
0x18001ebed  js      loc_18001ECAB
0x18001ebf3  xor     r9d, r9d; dwMaximumSizeHigh
0x18001ebf6  mov     [rsp+58h+lpName], rbp; lpName
0x18001ebfb  lea     rdx, [rbx+10h]; lpFileMappingAttributes
0x18001ebff  mov     [rsp+58h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x18001ec03  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001ec07  lea     r8d, [r9+4]; flProtect
0x18001ec0b  call    cs:__imp_CreateFileMappingA
0x18001ec11  mov     [rbx], rax
0x18001ec14  test    rax, rax
0x18001ec17  jnz     short loc_18001EC31
0x18001ec19  call    cs:__imp_GetLastError
0x18001ec1f  test    eax, eax
0x18001ec21  jle     loc_18001ECAB
0x18001ec27  movzx   eax, ax
0x18001ec2a  or      eax, 80070000h
0x18001ec2f  jmp     short loc_18001ECAB
0x18001ec31  call    cs:__imp_GetLastError
0x18001ec37  cmp     eax, 0B7h
0x18001ec3c  jnz     short loc_18001EC6B
0x18001ec3e  mov     rcx, [rbx]; hObject
0x18001ec41  call    cs:__imp_CloseHandle
0x18001ec47  mov     eax, 800700B7h
0x18001ec4c  mov     qword ptr [rbx], 0
0x18001ec53  jmp     short loc_18001ECAB
0x18001ec55  xor     edx, edx; bInheritHandle
0x18001ec57  mov     r8, rbp; lpName
0x18001ec5a  lea     ecx, [rdx+6]; dwDesiredAccess
0x18001ec5d  call    cs:__imp_OpenFileMappingA
0x18001ec63  mov     [rbx], rax
0x18001ec66  test    rax, rax
0x18001ec69  jz      short loc_18001ECA6
0x18001ec6b  mov     rcx, [rbx]; hFileMappingObject
0x18001ec6e  xor     r9d, r9d; dwFileOffsetLow
0x18001ec71  xor     r8d, r8d; dwFileOffsetHigh
0x18001ec74  mov     qword ptr [rsp+58h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18001ec7d  mov     edx, 0F001Fh; dwDesiredAccess
0x18001ec82  call    cs:__imp_MapViewOfFile
0x18001ec88  mov     [rbx+8], rax
0x18001ec8c  test    rax, rax
0x18001ec8f  jnz     short loc_18001ECB4
0x18001ec91  mov     rcx, [rbx]; hObject
0x18001ec94  test    rcx, rcx
0x18001ec97  jz      short loc_18001ECA6
0x18001ec99  call    cs:__imp_CloseHandle
0x18001ec9f  mov     qword ptr [rbx], 0
0x18001eca6  mov     eax, 80004005h
0x18001ecab  add     rsp, 38h
0x18001ecaf  pop     rdi
0x18001ecb0  pop     rsi
0x18001ecb1  pop     rbp
0x18001ecb2  pop     rbx
0x18001ecb3  retn
0x18001ecb4  test    edi, edi
0x18001ecb6  jz      short loc_18001ECC5
0x18001ecb8  mov     r8, rsi; Size
0x18001ecbb  xor     edx, edx; Val
0x18001ecbd  mov     rcx, rax; void *
0x18001ecc0  call    memset_0
0x18001ecc5  xor     eax, eax
0x18001ecc7  jmp     short loc_18001ECAB
```
