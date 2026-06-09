# CSimpStream::Write(void const *,ulong,ulong *)

- ea: `0x1800396a0`
- end: `0x180039737`
- name: `?Write@CSimpStream@@UEAAJPEBXKPEAK@Z`
- size: `151`
- prototype: `int(CSimpStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18004f9e0`

## callees

- `0x180026bc4`
- `0x1800396a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003970f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003970f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800396fe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800396fe`

## pseudocode

```c
__int64 __fastcall CSimpStream::Write(CSimpStream *this, const void *a2, DWORD a3, unsigned int *a4)
{
  DWORD *v6; // rdi
  unsigned int v7; // ebx
  BOOL v8; // eax
  DWORD LastError; // eax
  int v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    return 2147680265LL;
  v6 = (DWORD *)&v10;
  if ( a4 )
    v6 = a4;
  if ( *((_DWORD *)this + 6) >= 0x7FFFFF00u || a3 >= 2147483392 - *((_DWORD *)this + 6) )
    return 2147680529LL;
  v7 = 0;
  v8 = WriteFile(*((HANDLE *)this + 5), a2, a3, v6, 0);
  *((_DWORD *)this + 6) += *v6;
  if ( !v8 )
  {
    LastError = GetLastError();
    return (unsigned int)Win32ErrorToScode(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x1800396a0  mov     [rsp+arg_0], rbx
0x1800396a5  mov     [rsp+arg_8], rsi
0x1800396aa  push    rdi
0x1800396ab  sub     rsp, 30h
0x1800396af  mov     [rsp+38h+arg_18], 0
0x1800396b7  mov     rsi, rcx
0x1800396ba  test    r9, r9
0x1800396bd  jz      short loc_1800396C6
0x1800396bf  mov     dword ptr [r9], 0
0x1800396c6  test    rdx, rdx
0x1800396c9  jnz     short loc_1800396D2
0x1800396cb  mov     eax, 80030009h
0x1800396d0  jmp     short loc_180039727
0x1800396d2  test    r9, r9
0x1800396d5  lea     rdi, [rsp+38h+arg_18]
0x1800396da  mov     eax, 7FFFFF00h
0x1800396df  cmovnz  rdi, r9
0x1800396e3  cmp     [rcx+18h], eax
0x1800396e6  jnb     short loc_180039722
0x1800396e8  sub     eax, [rcx+18h]
0x1800396eb  cmp     r8d, eax
0x1800396ee  jnb     short loc_180039722
0x1800396f0  mov     rcx, [rcx+28h]; hFile
0x1800396f4  xor     ebx, ebx
0x1800396f6  mov     r9, rdi; lpNumberOfBytesWritten
0x1800396f9  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x1800396fe  call    cs:__imp_WriteFile
0x180039704  mov     ecx, eax
0x180039706  mov     eax, [rdi]
0x180039708  add     [rsi+18h], eax
0x18003970b  test    ecx, ecx
0x18003970d  jnz     short loc_18003971E
0x18003970f  call    cs:__imp_GetLastError
0x180039715  mov     ecx, eax; unsigned int
0x180039717  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18003971c  mov     ebx, eax
0x18003971e  mov     eax, ebx
0x180039720  jmp     short loc_180039727
0x180039722  mov     eax, 80030111h
0x180039727  mov     rbx, [rsp+38h+arg_0]
0x18003972c  mov     rsi, [rsp+38h+arg_8]
0x180039731  add     rsp, 30h
0x180039735  pop     rdi
0x180039736  retn
```
