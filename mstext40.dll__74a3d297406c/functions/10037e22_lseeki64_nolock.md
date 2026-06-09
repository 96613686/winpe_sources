# __lseeki64_nolock

- ea: `0x10037e22`
- end: `0x10037e95`
- name: `__lseeki64_nolock`
- size: `115`
- prototype: `int __cdecl(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100374c1`
- `0x10037d26`
- `0x1003c3cb`

## callees

- `0x1002d6bb`
- `0x1002d6dc`
- `0x10037e22`
- `0x1003bcf2`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10037e63`
- `KERNEL32!GetLastError` at `0x10037e63`
- `KERNEL32!SetFilePointerEx` at `0x10037e59`
- `KERNEL32!SetFilePointerEx` at `0x10037e59`

## pseudocode

```c
LARGE_INTEGER __cdecl _lseeki64_nolock(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)
{
  void *osfhandle; // eax
  DWORD LastError; // eax
  LARGE_INTEGER NewFilePointer; // [esp+8h] [ebp-8h] BYREF

  osfhandle = (void *)_get_osfhandle(FileHandle);
  if ( osfhandle == (void *)-1 )
  {
    *_errno() = 9;
    return (LARGE_INTEGER)-1LL;
  }
  if ( !SetFilePointerEx(osfhandle, liDistanceToMove, &NewFilePointer, dwMoveMethod) )
  {
    LastError = GetLastError();
    _dosmaperr(LastError);
    return (LARGE_INTEGER)-1LL;
  }
  *(_BYTE *)(__pioinfo[FileHandle >> 5] + ((FileHandle & 0x1F) << 6) + 4) &= ~2u;
  return NewFilePointer;
}

```

## disassembly

```asm
0x10037e22  push    ebp
0x10037e23  mov     ebp, esp
0x10037e25  push    ecx
0x10037e26  push    ecx
0x10037e27  push    esi
0x10037e28  mov     esi, [ebp+FileHandle]
0x10037e2b  push    edi
0x10037e2c  push    esi; FileHandle
0x10037e2d  call    __get_osfhandle
0x10037e32  or      edi, 0FFFFFFFFh
0x10037e35  pop     ecx
0x10037e36  cmp     eax, edi
0x10037e38  jnz     short loc_10037E4B
0x10037e3a  call    __errno
0x10037e3f  mov     dword ptr [eax], 9
0x10037e45  mov     eax, edi
0x10037e47  mov     edx, edi
0x10037e49  jmp     short loc_10037E8F
0x10037e4b  push    [ebp+dwMoveMethod]; dwMoveMethod
0x10037e4e  lea     ecx, [ebp+NewFilePointer]
0x10037e51  push    ecx; lpNewFilePointer
0x10037e52  push    dword ptr [ebp+liDistanceToMove+4]
0x10037e55  push    dword ptr [ebp+liDistanceToMove]; liDistanceToMove
0x10037e58  push    eax; hFile
0x10037e59  call    ds:__imp__SetFilePointerEx@20
0x10037e5f  test    eax, eax
0x10037e61  jnz     short loc_10037E72
0x10037e63  call    ds:__imp__GetLastError@0
0x10037e69  push    eax
0x10037e6a  call    __dosmaperr
0x10037e6f  pop     ecx
0x10037e70  jmp     short loc_10037E45
0x10037e72  mov     eax, esi
0x10037e74  and     esi, 1Fh
0x10037e77  sar     eax, 5
0x10037e7a  shl     esi, 6
0x10037e7d  mov     eax, ___pioinfo[eax*4]
0x10037e84  and     byte ptr [eax+esi+4], 0FDh
0x10037e89  mov     eax, dword ptr [ebp+NewFilePointer]
0x10037e8c  mov     edx, dword ptr [ebp+NewFilePointer+4]
0x10037e8f  pop     edi
0x10037e90  pop     esi
0x10037e91  mov     esp, ebp
0x10037e93  pop     ebp
0x10037e94  retn
```
