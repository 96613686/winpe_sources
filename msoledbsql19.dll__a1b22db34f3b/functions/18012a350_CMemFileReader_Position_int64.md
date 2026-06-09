# CMemFileReader::Position(__int64 *)

- ea: `0x18012a350`
- end: `0x18012a408`
- name: `?Position@CMemFileReader@@UEAAJPEA_J@Z`
- size: `184`
- prototype: `__int64 __fastcall(CMemFileReader *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180003d80`
- `0x18012a350`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012a3c6`
- `KERNEL32!GetLastError` at `0x18012a3d0`
- `KERNEL32!GetLastError` at `0x18012a3c6`
- `KERNEL32!GetLastError` at `0x18012a3d0`
- `KERNEL32!SetFilePointer` at `0x18012a3b7`
- `KERNEL32!SetFilePointer` at `0x18012a3b7`

## pseudocode

```c
__int64 __fastcall CMemFileReader::Position(CMemFileReader *this, __int64 *a2)
{
  unsigned int v2; // ebx
  void *v5; // rcx
  signed int LastError; // eax
  LONG DistanceToMoveHigh[2]; // [rsp+20h] [rbp-18h] BYREF

  v2 = 0;
  if ( *((_DWORD *)this + 8) )
  {
    if ( !a2 )
      return 2147942487LL;
    *a2 = *((_QWORD *)this + 7);
  }
  else
  {
    DistanceToMoveHigh[1] = 0;
    if ( a2 )
    {
      v5 = (void *)*((_QWORD *)this + 1);
      if ( v5 == (void *)-1LL )
      {
        return (unsigned int)-2147221301;
      }
      else
      {
        DistanceToMoveHigh[0] = SetFilePointer(v5, 0, &DistanceToMoveHigh[1], 1u);
        if ( DistanceToMoveHigh[0] == -1 && GetLastError() )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
          return (unsigned int)LastError;
        }
        else
        {
          *a2 = *(_QWORD *)DistanceToMoveHigh;
        }
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18012a350  mov     [rsp+arg_10], rbx
0x18012a355  push    rdi
0x18012a356  sub     rsp, 30h
0x18012a35a  mov     rax, cs:__security_cookie
0x18012a361  xor     rax, rsp
0x18012a364  mov     [rsp+38h+var_10], rax
0x18012a369  xor     ebx, ebx
0x18012a36b  mov     rdi, rdx
0x18012a36e  cmp     [rcx+20h], ebx
0x18012a371  jz      short loc_18012A388
0x18012a373  test    rdx, rdx
0x18012a376  jnz     short loc_18012A37F
0x18012a378  mov     eax, 80070057h
0x18012a37d  jmp     short loc_18012A3F0
0x18012a37f  mov     rcx, [rcx+38h]
0x18012a383  mov     [rdx], rcx
0x18012a386  jmp     short loc_18012A3EE
0x18012a388  mov     qword ptr [rsp+38h+DistanceToMoveHigh], rbx
0x18012a38d  test    rdi, rdi
0x18012a390  jnz     short loc_18012A399
0x18012a392  mov     ebx, 80070057h
0x18012a397  jmp     short loc_18012A3EE
0x18012a399  mov     rcx, [rcx+8]; hFile
0x18012a39d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012a3a1  jnz     short loc_18012A3AA
0x18012a3a3  mov     ebx, 800400CBh
0x18012a3a8  jmp     short loc_18012A3EE
0x18012a3aa  mov     r9d, 1; dwMoveMethod
0x18012a3b0  lea     r8, [rsp+38h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18012a3b5  xor     edx, edx; lDistanceToMove
0x18012a3b7  call    cs:__imp_SetFilePointer
0x18012a3bd  mov     [rsp+38h+DistanceToMoveHigh], eax
0x18012a3c1  cmp     eax, 0FFFFFFFFh
0x18012a3c4  jnz     short loc_18012A3E6
0x18012a3c6  call    cs:__imp_GetLastError
0x18012a3cc  test    eax, eax
0x18012a3ce  jz      short loc_18012A3E6
0x18012a3d0  call    cs:__imp_GetLastError
0x18012a3d6  test    eax, eax
0x18012a3d8  jle     short loc_18012A3E2
0x18012a3da  movzx   eax, ax
0x18012a3dd  or      eax, 80070000h
0x18012a3e2  mov     ebx, eax
0x18012a3e4  jmp     short loc_18012A3EE
0x18012a3e6  mov     rax, qword ptr [rsp+38h+DistanceToMoveHigh]
0x18012a3eb  mov     [rdi], rax
0x18012a3ee  mov     eax, ebx
0x18012a3f0  mov     rcx, [rsp+38h+var_10]
0x18012a3f5  xor     rcx, rsp; StackCookie
0x18012a3f8  call    __security_check_cookie
0x18012a3fd  mov     rbx, [rsp+38h+arg_10]
0x18012a402  add     rsp, 30h
0x18012a406  pop     rdi
0x18012a407  retn
```
