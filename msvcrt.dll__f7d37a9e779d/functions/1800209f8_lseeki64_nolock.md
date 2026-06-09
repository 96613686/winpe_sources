# _lseeki64_nolock

- ea: `0x1800209f8`
- end: `0x180020a8c`
- name: `_lseeki64_nolock`
- size: `148`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001df6c`
- `0x18001ecd0`
- `0x18001ef40`
- `0x1800208f0`
- `0x180020ee8`
- `0x180021c08`
- `0x1800227c0`
- `0x180023314`

## callees

- `0x180007ea8`
- `0x180007f00`
- `0x18001ffd0`
- `0x1800209f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a49`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180020a3a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180020a3a`

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
0x1800209f8  mov     [rsp+arg_0], rbx
0x1800209fd  push    rdi
0x1800209fe  sub     rsp, 20h
0x180020a02  movsxd  rbx, ecx
0x180020a05  mov     edi, r8d
0x180020a08  mov     ecx, ebx; FileHandle
0x180020a0a  mov     [rsp+28h+DistanceToMoveHigh], rdx
0x180020a0f  call    _get_osfhandle
0x180020a14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020a18  jnz     short loc_180020A2B
0x180020a1a  call    _errno
0x180020a1f  mov     dword ptr [rax], 9
0x180020a25  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020a29  jmp     short loc_180020A81
0x180020a2b  mov     edx, dword ptr [rsp+28h+DistanceToMoveHigh]; lDistanceToMove
0x180020a2f  lea     r8, [rsp+28h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x180020a34  mov     r9d, edi; dwMoveMethod
0x180020a37  mov     rcx, rax; hFile
0x180020a3a  call    cs:__imp_SetFilePointer
0x180020a40  mov     dword ptr [rsp+28h+DistanceToMoveHigh], eax
0x180020a44  cmp     eax, 0FFFFFFFFh
0x180020a47  jnz     short loc_180020A5C
0x180020a49  call    cs:__imp_GetLastError
0x180020a4f  test    eax, eax
0x180020a51  jz      short loc_180020A5C
0x180020a53  mov     ecx, eax
0x180020a55  call    _dosmaperr
0x180020a5a  jmp     short loc_180020A25
0x180020a5c  mov     eax, ebx
0x180020a5e  lea     r8, __pioinfo
0x180020a65  and     eax, 1Fh
0x180020a68  mov     rdx, rbx
0x180020a6b  imul    rcx, rax, 38h ; '8'
0x180020a6f  sar     rdx, 5
0x180020a73  mov     rax, [r8+rdx*8]
0x180020a77  and     byte ptr [rax+rcx+8], 0FDh
0x180020a7c  mov     rax, [rsp+28h+DistanceToMoveHigh]
0x180020a81  mov     rbx, [rsp+28h+arg_0]
0x180020a86  add     rsp, 20h
0x180020a8a  pop     rdi
0x180020a8b  retn
```
