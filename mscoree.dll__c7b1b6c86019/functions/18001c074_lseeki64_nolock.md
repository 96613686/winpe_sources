# _lseeki64_nolock

- ea: `0x18001c074`
- end: `0x18001c108`
- name: `_lseeki64_nolock`
- size: `148`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001b808`
- `0x18001bf6c`
- `0x18001f024`

## callees

- `0x18000e470`
- `0x18000e4c4`
- `0x18001c074`
- `0x18001eb58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c0c5`
- `KERNEL32!GetLastError` at `0x18001c0c5`
- `KERNEL32!SetFilePointer` at `0x18001c0b6`
- `KERNEL32!SetFilePointer` at `0x18001c0b6`

## pseudocode

```c
__int64 __fastcall lseeki64_nolock(int a1, __int64 a2, DWORD a3)
{
  __int64 v3; // rbx
  void *osfhandle; // rax
  DWORD LastError; // eax
  __int64 DistanceToMoveHigh; // [rsp+38h] [rbp+10h] BYREF

  v3 = a1;
  DistanceToMoveHigh = a2;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *errno() = 9;
    return -1;
  }
  LODWORD(DistanceToMoveHigh) = SetFilePointer(osfhandle, DistanceToMoveHigh, (PLONG)&DistanceToMoveHigh + 1, a3);
  if ( (_DWORD)DistanceToMoveHigh == -1 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      dosmaperr(LastError);
      return -1;
    }
  }
  *(_BYTE *)(_pioinfo[v3 >> 5] + 56 * (v3 & 0x1F) + 8) &= ~2u;
  return DistanceToMoveHigh;
}

```

## disassembly

```asm
0x18001c074  mov     [rsp+arg_0], rbx
0x18001c079  push    rdi
0x18001c07a  sub     rsp, 20h
0x18001c07e  movsxd  rbx, ecx
0x18001c081  mov     edi, r8d
0x18001c084  mov     ecx, ebx; FileHandle
0x18001c086  mov     [rsp+28h+DistanceToMoveHigh], rdx
0x18001c08b  call    _get_osfhandle
0x18001c090  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c094  jnz     short loc_18001C0A7
0x18001c096  call    _errno
0x18001c09b  mov     dword ptr [rax], 9
0x18001c0a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c0a5  jmp     short loc_18001C0FD
0x18001c0a7  mov     edx, dword ptr [rsp+28h+DistanceToMoveHigh]; lDistanceToMove
0x18001c0ab  lea     r8, [rsp+28h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18001c0b0  mov     r9d, edi; dwMoveMethod
0x18001c0b3  mov     rcx, rax; hFile
0x18001c0b6  call    cs:__imp_SetFilePointer
0x18001c0bc  mov     dword ptr [rsp+28h+DistanceToMoveHigh], eax
0x18001c0c0  cmp     eax, 0FFFFFFFFh
0x18001c0c3  jnz     short loc_18001C0D8
0x18001c0c5  call    cs:__imp_GetLastError
0x18001c0cb  test    eax, eax
0x18001c0cd  jz      short loc_18001C0D8
0x18001c0cf  mov     ecx, eax
0x18001c0d1  call    _dosmaperr
0x18001c0d6  jmp     short loc_18001C0A1
0x18001c0d8  mov     eax, ebx
0x18001c0da  lea     r8, __pioinfo
0x18001c0e1  and     eax, 1Fh
0x18001c0e4  mov     rdx, rbx
0x18001c0e7  imul    rcx, rax, 38h ; '8'
0x18001c0eb  sar     rdx, 5
0x18001c0ef  mov     rax, [r8+rdx*8]
0x18001c0f3  and     byte ptr [rax+rcx+8], 0FDh
0x18001c0f8  mov     rax, [rsp+28h+DistanceToMoveHigh]
0x18001c0fd  mov     rbx, [rsp+28h+arg_0]
0x18001c102  add     rsp, 20h
0x18001c106  pop     rdi
0x18001c107  retn
```
