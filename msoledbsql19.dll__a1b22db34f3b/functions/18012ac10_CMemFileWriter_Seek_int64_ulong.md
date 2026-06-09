# CMemFileWriter::Seek(__int64,ulong)

- ea: `0x18012ac10`
- end: `0x18012ae97`
- name: `?Seek@CMemFileWriter@@UEAAJ_JK@Z`
- size: `647`
- prototype: `int(CMemFileWriter *__hidden this, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x180003d80`
- `0x18012ac10`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012acab`
- `KERNEL32!GetLastError` at `0x18012adcd`
- `KERNEL32!GetLastError` at `0x18012ae10`
- `KERNEL32!GetLastError` at `0x18012ae5a`
- `KERNEL32!GetLastError` at `0x18012ae64`
- `KERNEL32!GetLastError` at `0x18012acab`
- `KERNEL32!GetLastError` at `0x18012adcd`
- `KERNEL32!GetLastError` at `0x18012ae10`
- `KERNEL32!GetLastError` at `0x18012ae5a`
- `KERNEL32!GetLastError` at `0x18012ae64`
- `KERNEL32!UnmapViewOfFile` at `0x18012ac8e`
- `KERNEL32!UnmapViewOfFile` at `0x18012ac8e`
- `KERNEL32!MapViewOfFile` at `0x18012ad63`
- `KERNEL32!MapViewOfFile` at `0x18012ad63`
- `KERNEL32!CreateFileMappingW` at `0x18012ad2c`
- `KERNEL32!CreateFileMappingW` at `0x18012ad2c`
- `KERNEL32!SetFilePointer` at `0x18012ae01`
- `KERNEL32!SetFilePointer` at `0x18012ae4f`
- `KERNEL32!SetFilePointer` at `0x18012ae01`
- `KERNEL32!SetFilePointer` at `0x18012ae4f`
- `KERNEL32!GetFileSize` at `0x18012adbf`
- `KERNEL32!GetFileSize` at `0x18012adbf`
- `KERNEL32!CloseHandle` at `0x18012acfd`
- `KERNEL32!CloseHandle` at `0x18012acfd`

## pseudocode

```c
int __fastcall CMemFileWriter::Seek(CMemFileWriter *this, __int64 a2, DWORD a3)
{
  int v3; // edi
  __int64 v5; // rsi
  int result; // eax
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  unsigned int v11; // edx
  void *v12; // rcx
  __int64 dwMaximumSizeLow; // r9
  HANDLE FileMappingW; // rax
  unsigned int v15; // eax
  LPVOID v16; // rax
  void *v17; // rcx
  DWORD FileSize; // eax
  void *v19; // rcx
  signed int LastError; // eax
  LONG DistanceToMoveHigh[2]; // [rsp+30h] [rbp-38h] BYREF
  LONG v22[2]; // [rsp+38h] [rbp-30h] BYREF

  v3 = 0;
  v5 = a2;
  if ( !*((_DWORD *)this + 8) )
  {
    v17 = (void *)*((_QWORD *)this + 1);
    *(_QWORD *)v22 = 0;
    DistanceToMoveHigh[1] = 0;
    if ( v17 == (void *)-1LL )
      return -2147221301;
    FileSize = GetFileSize(v17, (LPDWORD)this + 5);
    *((_DWORD *)this + 4) = FileSize;
    if ( FileSize != -1 || !GetLastError() )
    {
      if ( !a3 )
      {
        if ( v5 > *((_QWORD *)this + 2) )
          return -2147221297;
LABEL_35:
        v19 = (void *)*((_QWORD *)this + 1);
        *(_QWORD *)v22 = v5;
        if ( SetFilePointer(v19, v5, &v22[1], a3) != -1 || !GetLastError() )
          return v3;
        goto LABEL_37;
      }
      if ( a3 != 1 )
        return -2147024809;
      DistanceToMoveHigh[0] = SetFilePointer(*((HANDLE *)this + 1), 0, &DistanceToMoveHigh[1], 1u);
      if ( DistanceToMoveHigh[0] != -1 || !GetLastError() )
      {
        if ( v5 + *(_QWORD *)DistanceToMoveHigh > *((_QWORD *)this + 2) )
          return -2147221297;
        goto LABEL_35;
      }
    }
LABEL_37:
    LastError = GetLastError();
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
  if ( a3 )
  {
    if ( a3 != 1 )
      return -2147221297;
    v5 = *((_QWORD *)this + 7) + a2;
    if ( v5 > *((_QWORD *)this + 2) || v5 < 0 )
      return -2147221297;
  }
  else if ( a2 > *((_QWORD *)this + 2) || a2 < 0 )
  {
    return -2147221297;
  }
  *((_QWORD *)this + 7) = v5;
  v8 = *((_QWORD *)this + 8);
  if ( v5 >= v8 && v5 < v8 + *((unsigned int *)this + 19) )
  {
LABEL_21:
    *((_DWORD *)this + 18) = *((_DWORD *)this + 14) - *((_DWORD *)this + 16);
    return v3;
  }
  if ( !UnmapViewOfFile(*((LPCVOID *)this + 6)) )
    goto LABEL_12;
  v9 = *((_QWORD *)this + 2);
  v10 = *((_QWORD *)this + 7) & 0xFFFFFFFFFFF00000uLL;
  *((_QWORD *)this + 8) = v10;
  if ( (__int64)(v9 - v10) > 0x100000 )
  {
    *((_DWORD *)this + 19) = 0x100000;
    v11 = 0x100000;
    goto LABEL_19;
  }
  v11 = v9 - v10;
  *((_DWORD *)this + 19) = v11;
  if ( v11 >= 0x100000 )
  {
LABEL_19:
    v16 = MapViewOfFile(*((HANDLE *)this + 5), 2u, *((_DWORD *)this + 17), v10, v11);
    *((_QWORD *)this + 6) = v16;
    if ( !v16 )
    {
      (*(void (__fastcall **)(CMemFileWriter *))(*(_QWORD *)this + 48LL))(this);
      result = -2147221298;
      *((_DWORD *)this + 6) = 0;
      return result;
    }
    goto LABEL_21;
  }
  CloseHandle(*((HANDLE *)this + 5));
  v12 = (void *)*((_QWORD *)this + 1);
  dwMaximumSizeLow = *((_QWORD *)this + 2) + (unsigned int)(0x100000 - *((_DWORD *)this + 19));
  *((_QWORD *)this + 2) = dwMaximumSizeLow;
  FileMappingW = CreateFileMappingW(v12, 0, 4u, HIDWORD(dwMaximumSizeLow), dwMaximumSizeLow, 0);
  *((_QWORD *)this + 5) = FileMappingW;
  if ( FileMappingW )
  {
    LODWORD(v10) = *((_DWORD *)this + 16);
    v15 = *((_DWORD *)this + 4) - v10;
    *((_DWORD *)this + 19) = v15;
    v11 = v15;
    goto LABEL_19;
  }
LABEL_12:
  (*(void (__fastcall **)(CMemFileWriter *))(*(_QWORD *)this + 48LL))(this);
  *((_DWORD *)this + 6) = 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18012ac10  mov     [rsp+arg_18], rbx
0x18012ac15  push    rbp
0x18012ac16  push    rsi
0x18012ac17  push    rdi
0x18012ac18  sub     rsp, 50h
0x18012ac1c  mov     rax, cs:__security_cookie
0x18012ac23  xor     rax, rsp
0x18012ac26  mov     [rsp+68h+var_28], rax
0x18012ac2b  xor     edi, edi
0x18012ac2d  mov     ebp, r8d
0x18012ac30  mov     rsi, rdx
0x18012ac33  mov     rbx, rcx
0x18012ac36  cmp     [rcx+20h], edi
0x18012ac39  jz      loc_18012AD9D
0x18012ac3f  test    r8d, r8d
0x18012ac42  jz      short loc_18012AC63
0x18012ac44  cmp     r8d, 1
0x18012ac48  jnz     short loc_18012AC59
0x18012ac4a  add     rsi, [rcx+38h]
0x18012ac4e  cmp     rsi, [rcx+10h]
0x18012ac52  jg      short loc_18012AC59
0x18012ac54  test    rsi, rsi
0x18012ac57  jns     short loc_18012AC6E
0x18012ac59  mov     eax, 800400CFh
0x18012ac5e  jmp     loc_18012AE7A
0x18012ac63  cmp     rsi, [rcx+10h]
0x18012ac67  jg      short loc_18012AC59
0x18012ac69  test    rsi, rsi
0x18012ac6c  js      short loc_18012AC59
0x18012ac6e  mov     [rcx+38h], rsi
0x18012ac72  mov     rcx, [rcx+40h]
0x18012ac76  cmp     rsi, rcx
0x18012ac79  jl      short loc_18012AC8A
0x18012ac7b  mov     eax, [rbx+4Ch]
0x18012ac7e  add     rax, rcx
0x18012ac81  cmp     rsi, rax
0x18012ac84  jl      loc_18012AD8F
0x18012ac8a  mov     rcx, [rbx+30h]; lpBaseAddress
0x18012ac8e  call    cs:__imp_UnmapViewOfFile
0x18012ac94  test    eax, eax
0x18012ac96  jnz     short loc_18012ACC6
0x18012ac98  mov     rax, [rbx]
0x18012ac9b  mov     rcx, rbx
0x18012ac9e  mov     rax, [rax+30h]
0x18012aca2  call    cs:__guard_dispatch_icall_fptr
0x18012aca8  mov     [rbx+18h], edi
0x18012acab  call    cs:__imp_GetLastError
0x18012acb1  test    eax, eax
0x18012acb3  jle     loc_18012AE7A
0x18012acb9  movzx   eax, ax
0x18012acbc  or      eax, 80070000h
0x18012acc1  jmp     loc_18012AE7A
0x18012acc6  mov     rcx, [rbx+38h]
0x18012acca  mov     esi, 100000h
0x18012accf  mov     rdx, [rbx+10h]
0x18012acd3  and     rcx, 0FFFFFFFFFFF00000h
0x18012acda  mov     rax, rdx
0x18012acdd  mov     [rbx+40h], rcx
0x18012ace1  sub     rax, rcx
0x18012ace4  cmp     rax, rsi
0x18012ace7  jle     short loc_18012ACF0
0x18012ace9  mov     [rbx+4Ch], esi
0x18012acec  mov     edx, esi
0x18012acee  jmp     short loc_18012AD4C
0x18012acf0  sub     edx, ecx
0x18012acf2  mov     [rbx+4Ch], edx
0x18012acf5  cmp     edx, esi
0x18012acf7  jnb     short loc_18012AD4C
0x18012acf9  mov     rcx, [rbx+28h]; hObject
0x18012acfd  call    cs:__imp_CloseHandle
0x18012ad03  sub     esi, [rbx+4Ch]
0x18012ad06  mov     r8d, 4; flProtect
0x18012ad0c  mov     rcx, [rbx+8]; hFile
0x18012ad10  mov     edx, esi
0x18012ad12  add     rdx, [rbx+10h]
0x18012ad16  mov     r9, rdx
0x18012ad19  mov     [rbx+10h], rdx
0x18012ad1d  mov     [rsp+68h+lpName], rdi; lpName
0x18012ad22  mov     [rsp+68h+dwMaximumSizeLow], edx; dwMaximumSizeLow
0x18012ad26  xor     edx, edx; lpFileMappingAttributes
0x18012ad28  shr     r9, 20h; dwMaximumSizeHigh
0x18012ad2c  call    cs:__imp_CreateFileMappingW
0x18012ad32  mov     [rbx+28h], rax
0x18012ad36  test    rax, rax
0x18012ad39  jz      loc_18012AC98
0x18012ad3f  mov     eax, [rbx+10h]
0x18012ad42  mov     ecx, [rbx+40h]
0x18012ad45  sub     eax, ecx
0x18012ad47  mov     [rbx+4Ch], eax
0x18012ad4a  mov     edx, eax
0x18012ad4c  mov     r8d, [rbx+44h]; dwFileOffsetHigh
0x18012ad50  mov     r9d, ecx; dwFileOffsetLow
0x18012ad53  mov     rcx, [rbx+28h]; hFileMappingObject
0x18012ad57  mov     eax, edx
0x18012ad59  mov     edx, 2; dwDesiredAccess
0x18012ad5e  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x18012ad63  call    cs:__imp_MapViewOfFile
0x18012ad69  mov     [rbx+30h], rax
0x18012ad6d  test    rax, rax
0x18012ad70  jnz     short loc_18012AD8F
0x18012ad72  mov     rax, [rbx]
0x18012ad75  mov     rcx, rbx
0x18012ad78  mov     rax, [rax+30h]
0x18012ad7c  call    cs:__guard_dispatch_icall_fptr
0x18012ad82  mov     eax, 800400CEh
0x18012ad87  mov     [rbx+18h], edi
0x18012ad8a  jmp     loc_18012AE7A
0x18012ad8f  mov     ecx, [rbx+38h]
0x18012ad92  sub     ecx, [rbx+40h]
0x18012ad95  mov     [rbx+48h], ecx
0x18012ad98  jmp     loc_18012AE78
0x18012ad9d  mov     rcx, [rcx+8]; hFile
0x18012ada1  mov     qword ptr [rsp+68h+var_30], rdi
0x18012ada6  mov     qword ptr [rsp+68h+DistanceToMoveHigh], rdi
0x18012adab  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012adaf  jnz     short loc_18012ADBB
0x18012adb1  mov     edi, 800400CBh
0x18012adb6  jmp     loc_18012AE78
0x18012adbb  lea     rdx, [rbx+14h]; lpFileSizeHigh
0x18012adbf  call    cs:__imp_GetFileSize
0x18012adc5  mov     [rbx+10h], eax
0x18012adc8  cmp     eax, 0FFFFFFFFh
0x18012adcb  jnz     short loc_18012ADDB
0x18012adcd  call    cs:__imp_GetLastError
0x18012add3  test    eax, eax
0x18012add5  jnz     loc_18012AE64
0x18012addb  mov     eax, ebp
0x18012addd  test    ebp, ebp
0x18012addf  jz      short loc_18012AE2F
0x18012ade1  cmp     eax, 1
0x18012ade4  jz      short loc_18012ADF0
0x18012ade6  mov     edi, 80070057h
0x18012adeb  jmp     loc_18012AE78
0x18012adf0  mov     rcx, [rbx+8]; hFile
0x18012adf4  lea     r8, [rsp+68h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18012adf9  mov     r9d, 1; dwMoveMethod
0x18012adff  xor     edx, edx; lDistanceToMove
0x18012ae01  call    cs:__imp_SetFilePointer
0x18012ae07  mov     [rsp+68h+DistanceToMoveHigh], eax
0x18012ae0b  cmp     eax, 0FFFFFFFFh
0x18012ae0e  jnz     short loc_18012AE1A
0x18012ae10  call    cs:__imp_GetLastError
0x18012ae16  test    eax, eax
0x18012ae18  jnz     short loc_18012AE64
0x18012ae1a  mov     rcx, qword ptr [rsp+68h+DistanceToMoveHigh]
0x18012ae1f  add     rcx, rsi
0x18012ae22  cmp     rcx, [rbx+10h]
0x18012ae26  jle     short loc_18012AE3C
0x18012ae28  mov     edi, 800400CFh
0x18012ae2d  jmp     short loc_18012AE78
0x18012ae2f  cmp     rsi, [rbx+10h]
0x18012ae33  jle     short loc_18012AE3C
0x18012ae35  mov     edi, 800400CFh
0x18012ae3a  jmp     short loc_18012AE78
0x18012ae3c  mov     rcx, [rbx+8]; hFile
0x18012ae40  lea     r8, [rsp+68h+var_30+4]; lpDistanceToMoveHigh
0x18012ae45  mov     r9d, ebp; dwMoveMethod
0x18012ae48  mov     qword ptr [rsp+68h+var_30], rsi
0x18012ae4d  mov     edx, esi; lDistanceToMove
0x18012ae4f  call    cs:__imp_SetFilePointer
0x18012ae55  cmp     eax, 0FFFFFFFFh
0x18012ae58  jnz     short loc_18012AE78
0x18012ae5a  call    cs:__imp_GetLastError
0x18012ae60  test    eax, eax
0x18012ae62  jz      short loc_18012AE78
0x18012ae64  call    cs:__imp_GetLastError
0x18012ae6a  test    eax, eax
0x18012ae6c  jle     short loc_18012AE76
0x18012ae6e  movzx   eax, ax
0x18012ae71  or      eax, 80070000h
0x18012ae76  mov     edi, eax
0x18012ae78  mov     eax, edi
0x18012ae7a  mov     rcx, [rsp+68h+var_28]
0x18012ae7f  xor     rcx, rsp; StackCookie
0x18012ae82  call    __security_check_cookie
0x18012ae87  mov     rbx, [rsp+68h+arg_18]
0x18012ae8f  add     rsp, 50h
0x18012ae93  pop     rdi
0x18012ae94  pop     rsi
0x18012ae95  pop     rbp
0x18012ae96  retn
```
