# _commit

- ea: `0x18001e3d0`
- end: `0x18001e4ae`
- name: `_commit`
- size: `222`
- prototype: `int __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004a974`

## callees

- `0x180007e80`
- `0x180007f00`
- `0x18001e3d0`
- `0x18001fc98`
- `0x18001ffd0`
- `0x18002026c`
- `0x18002f050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e44e`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001e444`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001e444`

## pseudocode

```c
int __cdecl commit(int FileHandle)
{
  unsigned __int64 v2; // rbx
  __int64 v3; // rsi
  void *osfhandle; // rax
  DWORD LastError; // ebx

  if ( FileHandle == -2 )
  {
    *errno() = 9;
    return -1;
  }
  if ( FileHandle < 0
    || FileHandle >= (unsigned int)nhandle
    || (v2 = (unsigned __int64)FileHandle >> 5,
        v3 = 56LL * (FileHandle & 0x1F),
        (*(_BYTE *)(_pioinfo[v2] + v3 + 8) & 1) == 0) )
  {
    *errno() = 9;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  _lock_fhandle((unsigned int)FileHandle);
  if ( (*(_BYTE *)(_pioinfo[v2] + v3 + 8) & 1) != 0 )
  {
    osfhandle = (void *)get_osfhandle(FileHandle);
    if ( FlushFileBuffers(osfhandle) )
      LastError = 0;
    else
      LastError = GetLastError();
    if ( !LastError )
      goto LABEL_13;
    *_doserrno() = LastError;
  }
  *errno() = 9;
  LastError = -1;
LABEL_13:
  unlock_fhandle((unsigned int)FileHandle);
  return LastError;
}

```

## disassembly

```asm
0x18001e3d0  mov     [rsp+arg_0], ecx
0x18001e3d4  push    rbx
0x18001e3d5  push    rsi
0x18001e3d6  push    rdi
0x18001e3d7  push    r14
0x18001e3d9  sub     rsp, 38h
0x18001e3dd  movsxd  rdi, ecx
0x18001e3e0  cmp     edi, 0FFFFFFFEh
0x18001e3e3  jnz     short loc_18001E3F5
0x18001e3e5  call    _errno
0x18001e3ea  mov     dword ptr [rax], 9
0x18001e3f0  jmp     loc_18001E4A1
0x18001e3f5  test    ecx, ecx
0x18001e3f7  js      loc_18001E47E
0x18001e3fd  cmp     edi, cs:_nhandle
0x18001e403  jnb     short loc_18001E47E
0x18001e405  mov     rbx, rdi
0x18001e408  shr     rbx, 5
0x18001e40c  lea     r14, __pioinfo
0x18001e413  mov     eax, edi
0x18001e415  and     eax, 1Fh
0x18001e418  imul    rsi, rax, 38h ; '8'
0x18001e41c  mov     rax, [r14+rbx*8]
0x18001e420  test    byte ptr [rax+rsi+8], 1
0x18001e425  jz      short loc_18001E47E
0x18001e427  mov     ecx, edi
0x18001e429  call    __lock_fhandle
0x18001e42e  nop
0x18001e42f  mov     rax, [r14+rbx*8]
0x18001e433  test    byte ptr [rax+rsi+8], 1
0x18001e438  jz      short loc_18001E465
0x18001e43a  mov     ecx, edi; FileHandle
0x18001e43c  call    _get_osfhandle
0x18001e441  mov     rcx, rax; hFile
0x18001e444  call    cs:__imp_FlushFileBuffers
0x18001e44a  test    eax, eax
0x18001e44c  jnz     short loc_18001E458
0x18001e44e  call    cs:__imp_GetLastError
0x18001e454  mov     ebx, eax
0x18001e456  jmp     short loc_18001E45A
0x18001e458  xor     ebx, ebx
0x18001e45a  test    ebx, ebx
0x18001e45c  jz      short loc_18001E473
0x18001e45e  call    __doserrno
0x18001e463  mov     [rax], ebx
0x18001e465  call    _errno
0x18001e46a  mov     dword ptr [rax], 9
0x18001e470  or      ebx, 0FFFFFFFFh
0x18001e473  mov     ecx, edi
0x18001e475  call    _unlock_fhandle
0x18001e47a  mov     eax, ebx
0x18001e47c  jmp     short loc_18001E4A4
0x18001e47e  call    _errno
0x18001e483  mov     [rsp+58h+Reserved], 0; Reserved
0x18001e48c  mov     dword ptr [rax], 9
0x18001e492  xor     r9d, r9d; LineNo
0x18001e495  xor     r8d, r8d; FileName
0x18001e498  xor     edx, edx; FunctionName
0x18001e49a  xor     ecx, ecx; Expression
0x18001e49c  call    _invalid_parameter
0x18001e4a1  or      eax, 0FFFFFFFFh
0x18001e4a4  add     rsp, 38h
0x18001e4a8  pop     r14
0x18001e4aa  pop     rdi
0x18001e4ab  pop     rsi
0x18001e4ac  pop     rbx
0x18001e4ad  retn
0x18007b869  push    rbp
0x18007b86b  sub     rsp, 30h
0x18007b86f  mov     rbp, rdx
0x18007b872  mov     ecx, [rbp+60h]
0x18007b875  add     rsp, 30h
0x18007b879  pop     rbp
0x18007b87a  jmp     _unlock_fhandle
```
