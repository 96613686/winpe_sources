# CSimpStreamOpen::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x18004f6a0`
- end: `0x18004f7c9`
- name: `?Seek@CSimpStreamOpen@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `297`
- prototype: `int(CSimpStreamOpen *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180031b68`
- `0x18004f6a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f703`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f797`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f703`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f797`

## pseudocode

```c
__int64 __fastcall CSimpStreamOpen::Seek(
        CSimpStreamOpen *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        union _ULARGE_INTEGER *a4)
{
  __int64 result; // rax
  int v7; // r10d
  unsigned int v8; // ebp
  signed int LowPart; // ebx
  int v10; // edx
  LONG v11; // edx
  DWORD v12; // eax
  int v13; // r10d
  DWORD v14; // eax
  LONG v15; // r8d

  result = CExpParameterValidate::Seek((union _LARGE_INTEGER)this, a3, a4);
  v8 = result;
  if ( (int)result < 0 )
    return result;
  if ( !v7 )
  {
    LowPart = a2.LowPart;
    if ( a2.HighPart )
      LowPart = -1;
    if ( LowPart >= 0 && (unsigned int)LowPart <= *(_DWORD *)(*((_QWORD *)this + 6) + 72LL) )
    {
      v10 = *((_DWORD *)this + 5);
LABEL_8:
      v11 = LowPart + v10;
      goto LABEL_9;
    }
    return 2147680257LL;
  }
  v11 = 0;
  if ( a2.HighPart <= 0 && ((LowPart = a2.LowPart, a2.HighPart) || a2.LowPart < 0x80000000) )
  {
    if ( a2.QuadPart <= (__int64)0xFFFFFFFF7FFFFFFFuLL )
      LowPart = 0x80000000;
  }
  else
  {
    LowPart = 0x7FFFFFFF;
  }
  v13 = v7 - 1;
  if ( v13 )
  {
    if ( v13 != 1 )
      goto LABEL_9;
    if ( LowPart <= 0 && (LowPart >= 0 || (unsigned int)-LowPart <= *(_DWORD *)(*((_QWORD *)this + 6) + 72LL)) )
    {
      v10 = *((_DWORD *)this + 5) + *(_DWORD *)(*((_QWORD *)this + 6) + 72LL);
      goto LABEL_8;
    }
    return 2147680257LL;
  }
  v14 = SetFilePointer(*((HANDLE *)this + 5), 0, 0, 1u);
  v15 = *((_DWORD *)this + 5);
  v11 = v14 + LowPart;
  if ( v14 + LowPart > v15 + *(_DWORD *)(*((_QWORD *)this + 6) + 72LL) || v11 < v15 )
    return 2147680257LL;
LABEL_9:
  v12 = SetFilePointer(*((HANDLE *)this + 5), v11, 0, 0);
  if ( a4 )
  {
    a4->HighPart = 0;
    a4->LowPart = v12 - *((_DWORD *)this + 5);
  }
  *((_DWORD *)this + 6) = v12;
  return v8;
}

```

## disassembly

```asm
0x18004f6a0  mov     [rsp+arg_8], rdx
0x18004f6a5  push    rbx
0x18004f6a6  push    rbp
0x18004f6a7  push    rsi
0x18004f6a8  push    rdi
0x18004f6a9  sub     rsp, 28h
0x18004f6ad  mov     r10d, r8d
0x18004f6b0  mov     rsi, r9
0x18004f6b3  mov     edx, r10d; unsigned int
0x18004f6b6  mov     r8, r9; union _ULARGE_INTEGER *
0x18004f6b9  mov     rdi, rcx
0x18004f6bc  call    ?Seek@CExpParameterValidate@@SAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CExpParameterValidate::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x18004f6c1  mov     ebp, eax
0x18004f6c3  test    eax, eax
0x18004f6c5  js      loc_18004F7C0
0x18004f6cb  test    r10d, r10d
0x18004f6ce  jnz     short loc_18004F726
0x18004f6d0  mov     ebx, dword ptr [rsp+48h+arg_8]
0x18004f6d4  or      eax, 0FFFFFFFFh
0x18004f6d7  cmp     dword ptr [rsp+48h+arg_8+4], r10d
0x18004f6dc  cmovnz  ebx, eax
0x18004f6df  test    ebx, ebx
0x18004f6e1  js      loc_18004F7BB
0x18004f6e7  mov     rax, [rdi+30h]
0x18004f6eb  cmp     ebx, [rax+48h]
0x18004f6ee  ja      loc_18004F7BB
0x18004f6f4  mov     edx, [rdi+14h]
0x18004f6f7  add     edx, ebx; lDistanceToMove
0x18004f6f9  mov     rcx, [rdi+28h]; hFile
0x18004f6fd  xor     r9d, r9d; dwMoveMethod
0x18004f700  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004f703  call    cs:__imp_SetFilePointer
0x18004f709  test    rsi, rsi
0x18004f70c  jz      short loc_18004F71C
0x18004f70e  mov     ecx, eax
0x18004f710  mov     dword ptr [rsi+4], 0
0x18004f717  sub     ecx, [rdi+14h]
0x18004f71a  mov     [rsi], ecx
0x18004f71c  mov     [rdi+18h], eax
0x18004f71f  mov     eax, ebp
0x18004f721  jmp     loc_18004F7C0
0x18004f726  mov     eax, dword ptr [rsp+48h+arg_8+4]
0x18004f72a  xor     edx, edx; lDistanceToMove
0x18004f72c  test    eax, eax
0x18004f72e  jg      short loc_18004F752
0x18004f730  mov     ebx, dword ptr [rsp+48h+arg_8]
0x18004f734  mov     ecx, 80000000h
0x18004f739  jnz     short loc_18004F73F
0x18004f73b  cmp     ebx, ecx
0x18004f73d  jnb     short loc_18004F752
0x18004f73f  cmp     eax, 0FFFFFFFFh
0x18004f742  jl      short loc_18004F74E
0x18004f744  jnz     short loc_18004F757
0x18004f746  cmp     ebx, 7FFFFFFFh
0x18004f74c  ja      short loc_18004F757
0x18004f74e  mov     ebx, ecx
0x18004f750  jmp     short loc_18004F757
0x18004f752  mov     ebx, 7FFFFFFFh
0x18004f757  test    r10d, r10d
0x18004f75a  jz      short loc_18004F6DF
0x18004f75c  sub     r10d, 1
0x18004f760  jz      short loc_18004F78A
0x18004f762  cmp     r10d, 1
0x18004f766  jnz     short loc_18004F6F9
0x18004f768  test    ebx, ebx
0x18004f76a  jg      short loc_18004F7BB
0x18004f76c  jns     short loc_18004F77B
0x18004f76e  mov     rcx, [rdi+30h]
0x18004f772  mov     eax, ebx
0x18004f774  neg     eax
0x18004f776  cmp     eax, [rcx+48h]
0x18004f779  ja      short loc_18004F7BB
0x18004f77b  mov     rax, [rdi+30h]
0x18004f77f  mov     edx, [rax+48h]
0x18004f782  add     edx, [rdi+14h]
0x18004f785  jmp     loc_18004F6F7
0x18004f78a  mov     rcx, [rdi+28h]; hFile
0x18004f78e  mov     r9d, 1; dwMoveMethod
0x18004f794  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004f797  call    cs:__imp_SetFilePointer
0x18004f79d  mov     r8d, [rdi+14h]
0x18004f7a1  lea     edx, [rax+rbx]
0x18004f7a4  mov     rax, [rdi+30h]
0x18004f7a8  mov     eax, [rax+48h]
0x18004f7ab  add     eax, r8d
0x18004f7ae  cmp     edx, eax
0x18004f7b0  ja      short loc_18004F7BB
0x18004f7b2  cmp     edx, r8d
0x18004f7b5  jge     loc_18004F6F9
0x18004f7bb  mov     eax, 80030001h
0x18004f7c0  add     rsp, 28h
0x18004f7c4  pop     rdi
0x18004f7c5  pop     rsi
0x18004f7c6  pop     rbp
0x18004f7c7  pop     rbx
0x18004f7c8  retn
```
