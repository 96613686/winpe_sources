# CMemFileReader::Seek(__int64,ulong)

- ea: `0x18012a9e0`
- end: `0x18012ac00`
- name: `?Seek@CMemFileReader@@UEAAJ_JK@Z`
- size: `544`
- prototype: `int(CMemFileReader *__hidden this, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180003d80`
- `0x18012a9e0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012aa94`
- `KERNEL32!GetLastError` at `0x18012ab79`
- `KERNEL32!GetLastError` at `0x18012abc3`
- `KERNEL32!GetLastError` at `0x18012abcd`
- `KERNEL32!GetLastError` at `0x18012aa94`
- `KERNEL32!GetLastError` at `0x18012ab79`
- `KERNEL32!GetLastError` at `0x18012abc3`
- `KERNEL32!GetLastError` at `0x18012abcd`
- `KERNEL32!UnmapViewOfFile` at `0x18012aa77`
- `KERNEL32!UnmapViewOfFile` at `0x18012aa77`
- `KERNEL32!MapViewOfFile` at `0x18012aaf0`
- `KERNEL32!MapViewOfFile` at `0x18012aaf0`
- `KERNEL32!SetFilePointer` at `0x18012ab6a`
- `KERNEL32!SetFilePointer` at `0x18012abb8`
- `KERNEL32!SetFilePointer` at `0x18012ab6a`
- `KERNEL32!SetFilePointer` at `0x18012abb8`

## pseudocode

```c
int __fastcall CMemFileReader::Seek(CMemFileReader *this, __int64 a2, DWORD a3)
{
  int v3; // edi
  __int64 v5; // rsi
  int result; // eax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // r9
  unsigned int v12; // ecx
  LPVOID v13; // rax
  void *v14; // rcx
  void *v15; // rcx
  signed int LastError; // eax
  LONG DistanceToMoveHigh[2]; // [rsp+30h] [rbp-38h] BYREF
  LONG v18[2]; // [rsp+38h] [rbp-30h] BYREF

  v3 = 0;
  v5 = a2;
  if ( !*((_DWORD *)this + 8) )
  {
    v14 = (void *)*((_QWORD *)this + 1);
    *(_QWORD *)v18 = 0;
    DistanceToMoveHigh[1] = 0;
    if ( v14 == (void *)-1LL )
      return -2147221301;
    if ( a3 )
    {
      if ( a3 != 1 )
        return -2147024809;
      DistanceToMoveHigh[0] = SetFilePointer(v14, 0, &DistanceToMoveHigh[1], 1u);
      if ( DistanceToMoveHigh[0] == -1 && GetLastError() )
      {
LABEL_34:
        LastError = GetLastError();
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return LastError;
      }
      if ( v5 + *(_QWORD *)DistanceToMoveHigh > *((_QWORD *)this + 2) )
        return -2147221300;
    }
    else if ( a2 > *((_QWORD *)this + 2) )
    {
      return -2147221300;
    }
    v15 = (void *)*((_QWORD *)this + 1);
    *(_QWORD *)v18 = v5;
    if ( SetFilePointer(v15, v5, &v18[1], a3) != -1 || !GetLastError() )
      return v3;
    goto LABEL_34;
  }
  if ( a3 )
  {
    if ( a3 != 1 )
      return -2147221297;
    v5 = *((_QWORD *)this + 7) + a2;
    v8 = *((_QWORD *)this + 2);
    if ( v5 > v8 || v5 < 0 )
      return -2147221300;
  }
  else
  {
    v8 = *((_QWORD *)this + 2);
    if ( a2 > v8 || a2 < 0 )
      return -2147221300;
  }
  *((_QWORD *)this + 7) = v5;
  v9 = *((_QWORD *)this + 8);
  if ( v5 >= v9 && v5 < v9 + *((unsigned int *)this + 19) || v5 == v8 )
  {
LABEL_20:
    *((_DWORD *)this + 18) = *((_DWORD *)this + 14) - *((_DWORD *)this + 16);
    return v3;
  }
  if ( UnmapViewOfFile(*((LPCVOID *)this + 6)) )
  {
    v10 = *((_QWORD *)this + 2);
    v11 = *((_QWORD *)this + 7) & 0xFFFFFFFFFFF00000uLL;
    v12 = v10 - v11;
    *((_QWORD *)this + 8) = v11;
    if ( (__int64)(v10 - v11) > 0x100000 )
      v12 = 0x100000;
    *((_DWORD *)this + 19) = v12;
    v13 = MapViewOfFile(*((HANDLE *)this + 5), 4u, HIDWORD(v11), v11, v12);
    *((_QWORD *)this + 6) = v13;
    if ( !v13 )
    {
      (*(void (__fastcall **)(CMemFileReader *))(*(_QWORD *)this + 56LL))(this);
      result = -2147221299;
      *((_DWORD *)this + 6) = 0;
      return result;
    }
    goto LABEL_20;
  }
  (*(void (__fastcall **)(CMemFileReader *))(*(_QWORD *)this + 56LL))(this);
  *((_DWORD *)this + 6) = 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18012a9e0  mov     [rsp+arg_18], rbx
0x18012a9e5  push    rbp
0x18012a9e6  push    rsi
0x18012a9e7  push    rdi
0x18012a9e8  sub     rsp, 50h
0x18012a9ec  mov     rax, cs:__security_cookie
0x18012a9f3  xor     rax, rsp
0x18012a9f6  mov     [rsp+68h+var_28], rax
0x18012a9fb  xor     edi, edi
0x18012a9fd  mov     ebp, r8d
0x18012aa00  mov     rsi, rdx
0x18012aa03  mov     rbx, rcx
0x18012aa06  cmp     [rcx+20h], edi
0x18012aa09  jz      loc_18012AB2A
0x18012aa0f  test    r8d, r8d
0x18012aa12  jz      short loc_18012AA40
0x18012aa14  cmp     r8d, 1
0x18012aa18  jz      short loc_18012AA24
0x18012aa1a  mov     eax, 800400CFh
0x18012aa1f  jmp     loc_18012ABE3
0x18012aa24  add     rsi, [rcx+38h]
0x18012aa28  mov     rcx, [rcx+10h]
0x18012aa2c  cmp     rsi, rcx
0x18012aa2f  jg      short loc_18012AA36
0x18012aa31  test    rsi, rsi
0x18012aa34  jns     short loc_18012AA4E
0x18012aa36  mov     eax, 800400CCh
0x18012aa3b  jmp     loc_18012ABE3
0x18012aa40  mov     rcx, [rcx+10h]
0x18012aa44  cmp     rsi, rcx
0x18012aa47  jg      short loc_18012AA36
0x18012aa49  test    rsi, rsi
0x18012aa4c  js      short loc_18012AA36
0x18012aa4e  mov     [rbx+38h], rsi
0x18012aa52  mov     rdx, [rbx+40h]
0x18012aa56  cmp     rsi, rdx
0x18012aa59  jl      short loc_18012AA6A
0x18012aa5b  mov     eax, [rbx+4Ch]
0x18012aa5e  add     rax, rdx
0x18012aa61  cmp     rsi, rax
0x18012aa64  jl      loc_18012AB1C
0x18012aa6a  cmp     rsi, rcx
0x18012aa6d  jz      loc_18012AB1C
0x18012aa73  mov     rcx, [rbx+30h]; lpBaseAddress
0x18012aa77  call    cs:__imp_UnmapViewOfFile
0x18012aa7d  test    eax, eax
0x18012aa7f  jnz     short loc_18012AAAF
0x18012aa81  mov     rax, [rbx]
0x18012aa84  mov     rcx, rbx
0x18012aa87  mov     rax, [rax+38h]
0x18012aa8b  call    cs:__guard_dispatch_icall_fptr
0x18012aa91  mov     [rbx+18h], edi
0x18012aa94  call    cs:__imp_GetLastError
0x18012aa9a  test    eax, eax
0x18012aa9c  jle     loc_18012ABE3
0x18012aaa2  movzx   eax, ax
0x18012aaa5  or      eax, 80070000h
0x18012aaaa  jmp     loc_18012ABE3
0x18012aaaf  mov     rcx, [rbx+10h]
0x18012aab3  mov     edx, 100000h
0x18012aab8  mov     r9, [rbx+38h]
0x18012aabc  mov     rax, rcx
0x18012aabf  and     r9, 0FFFFFFFFFFF00000h; dwFileOffsetLow
0x18012aac6  sub     ecx, r9d
0x18012aac9  mov     [rbx+40h], r9
0x18012aacd  sub     rax, r9
0x18012aad0  mov     r8, r9
0x18012aad3  shr     r8, 20h; dwFileOffsetHigh
0x18012aad7  cmp     rax, rdx
0x18012aada  cmovg   ecx, edx
0x18012aadd  mov     edx, 4; dwDesiredAccess
0x18012aae2  mov     eax, ecx
0x18012aae4  mov     [rbx+4Ch], ecx
0x18012aae7  mov     rcx, [rbx+28h]; hFileMappingObject
0x18012aaeb  mov     [rsp+68h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x18012aaf0  call    cs:__imp_MapViewOfFile
0x18012aaf6  mov     [rbx+30h], rax
0x18012aafa  test    rax, rax
0x18012aafd  jnz     short loc_18012AB1C
0x18012aaff  mov     rax, [rbx]
0x18012ab02  mov     rcx, rbx
0x18012ab05  mov     rax, [rax+38h]
0x18012ab09  call    cs:__guard_dispatch_icall_fptr
0x18012ab0f  mov     eax, 800400CDh
0x18012ab14  mov     [rbx+18h], edi
0x18012ab17  jmp     loc_18012ABE3
0x18012ab1c  mov     ecx, [rbx+38h]
0x18012ab1f  sub     ecx, [rbx+40h]
0x18012ab22  mov     [rbx+48h], ecx
0x18012ab25  jmp     loc_18012ABE1
0x18012ab2a  mov     rcx, [rcx+8]; hFile
0x18012ab2e  mov     qword ptr [rsp+68h+var_30], rdi
0x18012ab33  mov     qword ptr [rsp+68h+DistanceToMoveHigh], rdi
0x18012ab38  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012ab3c  jnz     short loc_18012AB48
0x18012ab3e  mov     edi, 800400CBh
0x18012ab43  jmp     loc_18012ABE1
0x18012ab48  mov     eax, ebp
0x18012ab4a  test    ebp, ebp
0x18012ab4c  jz      short loc_18012AB98
0x18012ab4e  cmp     eax, 1
0x18012ab51  jz      short loc_18012AB5D
0x18012ab53  mov     edi, 80070057h
0x18012ab58  jmp     loc_18012ABE1
0x18012ab5d  mov     r9d, 1; dwMoveMethod
0x18012ab63  lea     r8, [rsp+68h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18012ab68  xor     edx, edx; lDistanceToMove
0x18012ab6a  call    cs:__imp_SetFilePointer
0x18012ab70  mov     [rsp+68h+DistanceToMoveHigh], eax
0x18012ab74  cmp     eax, 0FFFFFFFFh
0x18012ab77  jnz     short loc_18012AB83
0x18012ab79  call    cs:__imp_GetLastError
0x18012ab7f  test    eax, eax
0x18012ab81  jnz     short loc_18012ABCD
0x18012ab83  mov     rcx, qword ptr [rsp+68h+DistanceToMoveHigh]
0x18012ab88  add     rcx, rsi
0x18012ab8b  cmp     rcx, [rbx+10h]
0x18012ab8f  jle     short loc_18012ABA5
0x18012ab91  mov     edi, 800400CCh
0x18012ab96  jmp     short loc_18012ABE1
0x18012ab98  cmp     rsi, [rbx+10h]
0x18012ab9c  jle     short loc_18012ABA5
0x18012ab9e  mov     edi, 800400CCh
0x18012aba3  jmp     short loc_18012ABE1
0x18012aba5  mov     rcx, [rbx+8]; hFile
0x18012aba9  lea     r8, [rsp+68h+var_30+4]; lpDistanceToMoveHigh
0x18012abae  mov     r9d, ebp; dwMoveMethod
0x18012abb1  mov     qword ptr [rsp+68h+var_30], rsi
0x18012abb6  mov     edx, esi; lDistanceToMove
0x18012abb8  call    cs:__imp_SetFilePointer
0x18012abbe  cmp     eax, 0FFFFFFFFh
0x18012abc1  jnz     short loc_18012ABE1
0x18012abc3  call    cs:__imp_GetLastError
0x18012abc9  test    eax, eax
0x18012abcb  jz      short loc_18012ABE1
0x18012abcd  call    cs:__imp_GetLastError
0x18012abd3  test    eax, eax
0x18012abd5  jle     short loc_18012ABDF
0x18012abd7  movzx   eax, ax
0x18012abda  or      eax, 80070000h
0x18012abdf  mov     edi, eax
0x18012abe1  mov     eax, edi
0x18012abe3  mov     rcx, [rsp+68h+var_28]
0x18012abe8  xor     rcx, rsp; StackCookie
0x18012abeb  call    __security_check_cookie
0x18012abf0  mov     rbx, [rsp+68h+arg_18]
0x18012abf8  add     rsp, 50h
0x18012abfc  pop     rdi
0x18012abfd  pop     rsi
0x18012abfe  pop     rbp
0x18012abff  retn
```
