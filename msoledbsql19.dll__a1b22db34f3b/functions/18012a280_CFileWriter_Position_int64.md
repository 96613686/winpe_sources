# CFileWriter::Position(__int64 *)

- ea: `0x18012a280`
- end: `0x18012a348`
- name: `?Position@CFileWriter@@UEAAJPEA_J@Z`
- size: `200`
- prototype: `__int64 __fastcall(CFileWriter *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180003d80`
- `0x18012a280`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012a2fc`
- `KERNEL32!GetLastError` at `0x18012a306`
- `KERNEL32!GetLastError` at `0x18012a2fc`
- `KERNEL32!GetLastError` at `0x18012a306`
- `KERNEL32!SetFilePointer` at `0x18012a2ed`
- `KERNEL32!SetFilePointer` at `0x18012a2ed`

## pseudocode

```c
signed int __fastcall CFileWriter::Position(CFileWriter *this, __int64 *a2)
{
  signed int result; // eax
  void *v4; // rcx
  LONG DistanceToMoveHigh[2]; // [rsp+20h] [rbp-18h] BYREF

  DistanceToMoveHigh[1] = 0;
  if ( !a2 )
    return -2147024809;
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 == (void *)-1LL )
    return -2147221301;
  DistanceToMoveHigh[0] = SetFilePointer(v4, 0, &DistanceToMoveHigh[1], 1u);
  if ( DistanceToMoveHigh[0] == -1 && GetLastError() )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    result = 0;
    *a2 = *(_QWORD *)DistanceToMoveHigh;
  }
  return result;
}

```

## disassembly

```asm
0x18012a280  push    rbx
0x18012a282  sub     rsp, 30h
0x18012a286  mov     rax, cs:__security_cookie
0x18012a28d  xor     rax, rsp
0x18012a290  mov     [rsp+38h+var_10], rax
0x18012a295  mov     qword ptr [rsp+38h+DistanceToMoveHigh], 0
0x18012a29e  mov     rbx, rdx
0x18012a2a1  test    rdx, rdx
0x18012a2a4  jnz     short loc_18012A2BE
0x18012a2a6  mov     eax, 80070057h
0x18012a2ab  mov     rcx, [rsp+38h+var_10]
0x18012a2b0  xor     rcx, rsp; StackCookie
0x18012a2b3  call    __security_check_cookie
0x18012a2b8  add     rsp, 30h
0x18012a2bc  pop     rbx
0x18012a2bd  retn
0x18012a2be  mov     rcx, [rcx+8]; hFile
0x18012a2c2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012a2c6  jnz     short loc_18012A2E0
0x18012a2c8  mov     eax, 800400CBh
0x18012a2cd  mov     rcx, [rsp+38h+var_10]
0x18012a2d2  xor     rcx, rsp; StackCookie
0x18012a2d5  call    __security_check_cookie
0x18012a2da  add     rsp, 30h
0x18012a2de  pop     rbx
0x18012a2df  retn
0x18012a2e0  mov     r9d, 1; dwMoveMethod
0x18012a2e6  lea     r8, [rsp+38h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18012a2eb  xor     edx, edx; lDistanceToMove
0x18012a2ed  call    cs:__imp_SetFilePointer
0x18012a2f3  mov     [rsp+38h+DistanceToMoveHigh], eax
0x18012a2f7  cmp     eax, 0FFFFFFFFh
0x18012a2fa  jnz     short loc_18012A32B
0x18012a2fc  call    cs:__imp_GetLastError
0x18012a302  test    eax, eax
0x18012a304  jz      short loc_18012A32B
0x18012a306  call    cs:__imp_GetLastError
0x18012a30c  test    eax, eax
0x18012a30e  jle     short loc_18012A335
0x18012a310  movzx   eax, ax
0x18012a313  or      eax, 80070000h
0x18012a318  mov     rcx, [rsp+38h+var_10]
0x18012a31d  xor     rcx, rsp; StackCookie
0x18012a320  call    __security_check_cookie
0x18012a325  add     rsp, 30h
0x18012a329  pop     rbx
0x18012a32a  retn
0x18012a32b  mov     rcx, qword ptr [rsp+38h+DistanceToMoveHigh]
0x18012a330  xor     eax, eax
0x18012a332  mov     [rbx], rcx
0x18012a335  mov     rcx, [rsp+38h+var_10]
0x18012a33a  xor     rcx, rsp; StackCookie
0x18012a33d  call    __security_check_cookie
0x18012a342  add     rsp, 30h
0x18012a346  pop     rbx
0x18012a347  retn
```
