# _commit

- ea: `0x18001ff10`
- end: `0x18001ffee`
- name: `_commit`
- size: `222`
- prototype: `int __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001ed48`

## callees

- `0x18000e448`
- `0x18000e4c4`
- `0x180010a08`
- `0x18001ea08`
- `0x18001eb58`
- `0x18001ebf8`
- `0x18001ff10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ff8e`
- `KERNEL32!GetLastError` at `0x18001ff8e`
- `KERNEL32!FlushFileBuffers` at `0x18001ff84`
- `KERNEL32!FlushFileBuffers` at `0x18001ff84`

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
0x18001ff10  mov     [rsp+arg_0], ecx
0x18001ff14  push    rbx
0x18001ff15  push    rsi
0x18001ff16  push    rdi
0x18001ff17  push    r14
0x18001ff19  sub     rsp, 38h
0x18001ff1d  movsxd  rdi, ecx
0x18001ff20  cmp     edi, 0FFFFFFFEh
0x18001ff23  jnz     short loc_18001FF35
0x18001ff25  call    _errno
0x18001ff2a  mov     dword ptr [rax], 9
0x18001ff30  jmp     loc_18001FFE1
0x18001ff35  test    ecx, ecx
0x18001ff37  js      loc_18001FFBE
0x18001ff3d  cmp     edi, cs:_nhandle
0x18001ff43  jnb     short loc_18001FFBE
0x18001ff45  mov     rbx, rdi
0x18001ff48  shr     rbx, 5
0x18001ff4c  lea     r14, __pioinfo
0x18001ff53  mov     eax, edi
0x18001ff55  and     eax, 1Fh
0x18001ff58  imul    rsi, rax, 38h ; '8'
0x18001ff5c  mov     rax, [r14+rbx*8]
0x18001ff60  test    byte ptr [rax+rsi+8], 1
0x18001ff65  jz      short loc_18001FFBE
0x18001ff67  mov     ecx, edi
0x18001ff69  call    __lock_fhandle
0x18001ff6e  nop
0x18001ff6f  mov     rax, [r14+rbx*8]
0x18001ff73  test    byte ptr [rax+rsi+8], 1
0x18001ff78  jz      short loc_18001FFA5
0x18001ff7a  mov     ecx, edi; FileHandle
0x18001ff7c  call    _get_osfhandle
0x18001ff81  mov     rcx, rax; hFile
0x18001ff84  call    cs:__imp_FlushFileBuffers
0x18001ff8a  test    eax, eax
0x18001ff8c  jnz     short loc_18001FF98
0x18001ff8e  call    cs:__imp_GetLastError
0x18001ff94  mov     ebx, eax
0x18001ff96  jmp     short loc_18001FF9A
0x18001ff98  xor     ebx, ebx
0x18001ff9a  test    ebx, ebx
0x18001ff9c  jz      short loc_18001FFB3
0x18001ff9e  call    __doserrno
0x18001ffa3  mov     [rax], ebx
0x18001ffa5  call    _errno
0x18001ffaa  mov     dword ptr [rax], 9
0x18001ffb0  or      ebx, 0FFFFFFFFh
0x18001ffb3  mov     ecx, edi
0x18001ffb5  call    _unlock_fhandle
0x18001ffba  mov     eax, ebx
0x18001ffbc  jmp     short loc_18001FFE4
0x18001ffbe  call    _errno
0x18001ffc3  mov     [rsp+58h+Reserved], 0; Reserved
0x18001ffcc  mov     dword ptr [rax], 9
0x18001ffd2  xor     r9d, r9d; LineNo
0x18001ffd5  xor     r8d, r8d; FileName
0x18001ffd8  xor     edx, edx; FunctionName
0x18001ffda  xor     ecx, ecx; Expression
0x18001ffdc  call    _invalid_parameter
0x18001ffe1  or      eax, 0FFFFFFFFh
0x18001ffe4  add     rsp, 38h
0x18001ffe8  pop     r14
0x18001ffea  pop     rdi
0x18001ffeb  pop     rsi
0x18001ffec  pop     rbx
0x18001ffed  retn
0x18004380b  push    rbp
0x18004380d  sub     rsp, 30h
0x180043811  mov     rbp, rdx
0x180043814  mov     ecx, [rbp+60h]
0x180043817  add     rsp, 30h
0x18004381b  pop     rbp
0x18004381c  jmp     _unlock_fhandle
```
