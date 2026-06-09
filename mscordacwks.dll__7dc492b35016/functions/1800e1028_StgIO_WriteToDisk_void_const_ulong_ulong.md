# StgIO::WriteToDisk(void const *,ulong,ulong *)

- ea: `0x1800e1028`
- end: `0x1800e10bd`
- name: `?WriteToDisk@StgIO@@AEAAJPEBXKPEAK@Z`
- size: `149`
- prototype: `int(StgIO *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800de7cc`
- `0x1800e0808`
- `0x1800e1c40`

## callees

- `0x1800e1028`
- `0x1800f0490`
- `0x180106100`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e107d`
- `KERNEL32!GetLastError` at `0x1800e107d`
- `KERNEL32!WriteFile` at `0x1800e1073`
- `KERNEL32!WriteFile` at `0x1800e1073`

## pseudocode

```c
__int64 __fastcall StgIO::WriteToDisk(StgIO *this, const void *a2, __int64 a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  DWORD *v5; // r10
  signed int LastError; // eax
  __int64 v7; // rcx
  char v10; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  v5 = (DWORD *)&v10;
  if ( a4 )
    v5 = a4;
  switch ( *((_DWORD *)this + 34) )
  {
    case 1:
      goto LABEL_19;
    case 2:
      return (unsigned int)-2147418113;
    case 3:
      return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, const void *, __int64, DWORD *))(**((_QWORD **)this + 10)
                                                                                             + 32LL))(
                             *((_QWORD *)this + 10),
                             a2,
                             a3,
                             v5);
    case 4:
    case 5:
      return (unsigned int)-2147418113;
    case 6:
LABEL_19:
      if ( !WriteFile(*((HANDLE *)this + 11), a2, a3, v5, 0) )
      {
        LastError = GetLastError();
        v7 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v7 = (unsigned int)LastError;
        return (unsigned int)PostError(v7);
      }
      break;
  }
  return v4;
}

```

## disassembly

```asm
0x1800e1028  push    rbx
0x1800e102a  sub     rsp, 30h
0x1800e102e  xor     ebx, ebx
0x1800e1030  lea     r10, [rsp+38h+arg_0]
0x1800e1035  test    r9, r9
0x1800e1038  cmovnz  r10, r9
0x1800e103c  mov     r9d, [rcx+88h]
0x1800e1043  sub     r9d, 1
0x1800e1047  jz      short loc_1800E1067
0x1800e1049  sub     r9d, 1
0x1800e104d  jz      short loc_1800E10B6
0x1800e104f  sub     r9d, 1
0x1800e1053  jz      short loc_1800E10A0
0x1800e1055  sub     r9d, 1
0x1800e1059  jz      short loc_1800E10B6
0x1800e105b  sub     r9d, 1
0x1800e105f  jz      short loc_1800E10B6
0x1800e1061  cmp     r9d, 1
0x1800e1065  jnz     short loc_1800E1098
0x1800e1067  mov     rcx, [rcx+58h]; hFile
0x1800e106b  mov     r9, r10; lpNumberOfBytesWritten
0x1800e106e  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x1800e1073  call    cs:__imp_WriteFile
0x1800e1079  test    eax, eax
0x1800e107b  jnz     short loc_1800E1098
0x1800e107d  call    cs:__imp_GetLastError
0x1800e1083  movzx   ecx, ax
0x1800e1086  or      ecx, 80070000h
0x1800e108c  test    eax, eax
0x1800e108e  cmovle  ecx, eax
0x1800e1091  call    PostError
0x1800e1096  mov     ebx, eax
0x1800e1098  mov     eax, ebx
0x1800e109a  add     rsp, 30h
0x1800e109e  pop     rbx
0x1800e109f  retn
0x1800e10a0  mov     rcx, [rcx+50h]
0x1800e10a4  mov     r9, r10
0x1800e10a7  mov     rax, [rcx]
0x1800e10aa  mov     rax, [rax+20h]
0x1800e10ae  call    cs:__guard_dispatch_icall_fptr
0x1800e10b4  jmp     short loc_1800E1096
0x1800e10b6  mov     ebx, 8000FFFFh
0x1800e10bb  jmp     short loc_1800E1098
```
