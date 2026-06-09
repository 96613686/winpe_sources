# CFileStream::SeekTo(unsigned __int64)

- ea: `0x180025a10`
- end: `0x180025a83`
- name: `?SeekTo@CFileStream@@AEAA_K_K@Z`
- size: `115`
- prototype: `unsigned __int64 __fastcall(CFileStream *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180025010`
- `0x180025154`
- `0x180025460`
- `0x1800256b0`
- `0x18004c1b0`

## callees

- `0x180025a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a56`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180025a47`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180025a47`

## pseudocode

```c
unsigned __int64 __fastcall CFileStream::SeekTo(CFileStream *this, __int64 a2)
{
  __int64 v2; // rax
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 DistanceToMoveHigh; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 6);
  HIDWORD(DistanceToMoveHigh) = 0;
  if ( v2 && a2 == *(_QWORD *)(v2 + 48) )
    return a2;
  v5 = (void *)*((_QWORD *)this + 8);
  HIDWORD(DistanceToMoveHigh) = HIDWORD(a2);
  LODWORD(DistanceToMoveHigh) = SetFilePointer(v5, a2, (PLONG)&DistanceToMoveHigh + 1, 0);
  if ( (_DWORD)DistanceToMoveHigh == -1 && GetLastError() )
    return -1;
  v6 = *((_QWORD *)this + 6);
  if ( v6 )
    *(_QWORD *)(v6 + 48) = DistanceToMoveHigh;
  return DistanceToMoveHigh;
}

```

## disassembly

```asm
0x180025a10  push    rbx
0x180025a12  sub     rsp, 20h
0x180025a16  mov     rax, [rcx+30h]
0x180025a1a  mov     rbx, rcx
0x180025a1d  mov     [rsp+28h+DistanceToMoveHigh], 0
0x180025a26  test    rax, rax
0x180025a29  jz      short loc_180025A36
0x180025a2b  cmp     rdx, [rax+30h]
0x180025a2f  jnz     short loc_180025A36
0x180025a31  mov     rax, rdx
0x180025a34  jmp     short loc_180025A7D
0x180025a36  mov     rcx, [rcx+40h]; hFile
0x180025a3a  lea     r8, [rsp+28h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x180025a3f  xor     r9d, r9d; dwMoveMethod
0x180025a42  mov     [rsp+28h+DistanceToMoveHigh], rdx
0x180025a47  call    cs:__imp_SetFilePointer
0x180025a4d  mov     dword ptr [rsp+28h+DistanceToMoveHigh], eax
0x180025a51  cmp     eax, 0FFFFFFFFh
0x180025a54  jnz     short loc_180025A66
0x180025a56  call    cs:__imp_GetLastError
0x180025a5c  test    eax, eax
0x180025a5e  jz      short loc_180025A66
0x180025a60  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025a64  jmp     short loc_180025A7D
0x180025a66  mov     rcx, [rbx+30h]
0x180025a6a  test    rcx, rcx
0x180025a6d  jz      short loc_180025A78
0x180025a6f  mov     rax, [rsp+28h+DistanceToMoveHigh]
0x180025a74  mov     [rcx+30h], rax
0x180025a78  mov     rax, [rsp+28h+DistanceToMoveHigh]
0x180025a7d  add     rsp, 20h
0x180025a81  pop     rbx
0x180025a82  retn
```
