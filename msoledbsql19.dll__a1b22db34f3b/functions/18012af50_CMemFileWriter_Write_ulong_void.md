# CMemFileWriter::Write(ulong,void *)

- ea: `0x18012af50`
- end: `0x18012b287`
- name: `?Write@CMemFileWriter@@UEAAJKPEAX@Z`
- size: `823`
- prototype: `int(CMemFileWriter *__hidden this, unsigned int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180003d80`
- `0x180129c80`
- `0x18012af50`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012b098`
- `KERNEL32!GetLastError` at `0x18012b0cd`
- `KERNEL32!GetLastError` at `0x18012b17a`
- `KERNEL32!GetLastError` at `0x18012b24f`
- `KERNEL32!GetLastError` at `0x18012b098`
- `KERNEL32!GetLastError` at `0x18012b0cd`
- `KERNEL32!GetLastError` at `0x18012b17a`
- `KERNEL32!GetLastError` at `0x18012b24f`
- `KERNEL32!UnmapViewOfFile` at `0x18012b0b9`
- `KERNEL32!UnmapViewOfFile` at `0x18012b0b9`
- `KERNEL32!FlushViewOfFile` at `0x18012b07b`
- `KERNEL32!FlushViewOfFile` at `0x18012b07b`
- `KERNEL32!MapViewOfFile` at `0x18012b1bb`
- `KERNEL32!MapViewOfFile` at `0x18012b1bb`
- `KERNEL32!CreateFileMappingW` at `0x18012b158`
- `KERNEL32!CreateFileMappingW` at `0x18012b158`
- `KERNEL32!WriteFile` at `0x18012b245`
- `KERNEL32!WriteFile` at `0x18012b245`
- `KERNEL32!CloseHandle` at `0x18012b126`
- `KERNEL32!CloseHandle` at `0x18012b126`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012afbc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012aff0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012b003`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012b04b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012afbc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012aff0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012b003`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012b04b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012b00f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012b057`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012b00f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012b057`

## pseudocode

```c
__int64 __fastcall CMemFileWriter::Write(CMemFileWriter *this, DWORD a2, char *a3)
{
  char *v3; // r15
  DWORD v4; // r12d
  unsigned int v6; // edi
  unsigned int i; // esi
  void *v8; // rcx
  signed int LastError; // eax
  signed int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // edx
  HANDLE FileMappingW; // rax
  signed int v15; // eax
  unsigned int v16; // eax
  LPVOID v17; // rax
  void *v18; // rcx
  signed int v19; // eax
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-40h] BYREF

  v3 = a3;
  v4 = a2;
  *(_QWORD *)NumberOfBytesWritten = this;
  v6 = 0;
  if ( *((_DWORD *)this + 8) )
  {
    if ( !a3 )
      return (unsigned int)-2147024809;
    for ( i = *((_DWORD *)this + 19) - *((_DWORD *)this + 18); ; i = *((_DWORD *)this + 19) )
    {
      v8 = (void *)(*((_QWORD *)this + 6) + *((unsigned int *)this + 18));
      if ( i >= v4 )
      {
        if ( v4 )
        {
          if ( !v8 )
            goto LABEL_8;
          if ( !v3 || i < (unsigned __int64)v4 )
          {
            memset_0(v8, 0, i);
            if ( v3 )
            {
              if ( i >= (unsigned __int64)v4 )
                goto LABEL_16;
              *_errno() = 34;
            }
            else
            {
LABEL_8:
              *_errno() = 22;
            }
            _invalid_parameter_noinfo();
            goto LABEL_16;
          }
          memcpy_0(v8, v3, v4);
        }
LABEL_16:
        *((_QWORD *)this + 7) += v4;
        *((_DWORD *)this + 18) += v4;
        return v6;
      }
      if ( i )
      {
        if ( v8 )
        {
          if ( v3 )
          {
            memcpy_0(v8, v3, i);
            goto LABEL_23;
          }
          memset_0(v8, 0, i);
        }
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
LABEL_23:
      v4 -= i;
      *((_QWORD *)this + 7) += i;
      *((_DWORD *)this + 18) += i;
      v3 += i;
      if ( !FlushViewOfFile(*((LPCVOID *)this + 6), *((unsigned int *)this + 19)) )
      {
        (*(void (__fastcall **)(CMemFileWriter *))(*(_QWORD *)this + 48LL))(this);
        *((_DWORD *)this + 6) = 0;
        LastError = GetLastError();
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return (unsigned int)LastError;
      }
      if ( !UnmapViewOfFile(*((LPCVOID *)this + 6)) )
      {
        CMemFileWriter::HandleMappingFailure(this, 0);
        v10 = GetLastError();
        if ( v10 > 0 )
          return (unsigned __int16)v10 | 0x80070000;
        return (unsigned int)v10;
      }
      v11 = *((_QWORD *)this + 8) + *((unsigned int *)this + 19);
      *((_QWORD *)this + 8) = v11;
      v12 = *((_QWORD *)this + 2);
      if ( v12 - v11 < 0x100000 )
        v13 = v12 - v11;
      else
        v13 = 0x100000;
      *((_DWORD *)this + 19) = v13;
      *((_DWORD *)this + 18) = 0;
      if ( v13 < 0x100000 )
      {
        CloseHandle(*((HANDLE *)this + 5));
        *((_QWORD *)this + 2) += (unsigned int)(0x100000 - *((_DWORD *)this + 19));
        FileMappingW = CreateFileMappingW(
                         *((HANDLE *)this + 1),
                         0,
                         4u,
                         HIDWORD(*((_QWORD *)this + 2)),
                         *((_QWORD *)this + 2),
                         0);
        *((_QWORD *)this + 5) = FileMappingW;
        if ( !FileMappingW )
        {
          (*(void (__fastcall **)(CMemFileWriter *))(*(_QWORD *)this + 48LL))(this);
          *((_DWORD *)this + 6) = 0;
          v15 = GetLastError();
          if ( v15 > 0 )
            return (unsigned __int16)v15 | 0x80070000;
          return (unsigned int)v15;
        }
        LODWORD(v11) = *((_DWORD *)this + 16);
        v16 = *((_DWORD *)this + 4) - v11;
        *((_DWORD *)this + 19) = v16;
        v13 = v16;
      }
      v17 = MapViewOfFile(*((HANDLE *)this + 5), 2u, *((_DWORD *)this + 17), v11, v13);
      *((_QWORD *)this + 6) = v17;
      if ( !v17 )
      {
        (*(void (__fastcall **)(CMemFileWriter *))(*(_QWORD *)this + 48LL))(this);
        *((_DWORD *)this + 6) = 0;
        return (unsigned int)-2147221298;
      }
    }
  }
  NumberOfBytesWritten[0] = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  v18 = (void *)*((_QWORD *)this + 1);
  if ( v18 == (void *)-1LL )
  {
    return (unsigned int)-2147221301;
  }
  else if ( !WriteFile(v18, a3, a2, NumberOfBytesWritten, 0) )
  {
    v19 = GetLastError();
    if ( v19 > 0 )
      return (unsigned __int16)v19 | 0x80070000;
    return (unsigned int)v19;
  }
  return v6;
}

```

## disassembly

```asm
0x18012af50  mov     [rsp+arg_18], rbx
0x18012af55  push    rsi
0x18012af56  push    rdi
0x18012af57  push    r12
0x18012af59  push    r14
0x18012af5b  push    r15
0x18012af5d  sub     rsp, 60h
0x18012af61  mov     rax, cs:__security_cookie
0x18012af68  xor     rax, rsp
0x18012af6b  mov     [rsp+88h+var_38], rax
0x18012af70  mov     r15, r8
0x18012af73  mov     r12d, edx
0x18012af76  mov     rbx, rcx
0x18012af79  mov     qword ptr [rsp+88h+NumberOfBytesWritten], rcx
0x18012af7e  xor     edi, edi
0x18012af80  cmp     [rcx+20h], edi
0x18012af83  jz      loc_18012B217
0x18012af89  test    r8, r8
0x18012af8c  jnz     short loc_18012AF98
0x18012af8e  mov     edi, 80070057h
0x18012af93  jmp     loc_18012B263
0x18012af98  mov     esi, [rcx+4Ch]
0x18012af9b  sub     esi, [rcx+48h]
0x18012af9e  xchg    ax, ax
0x18012afa0  mov     r14d, esi
0x18012afa3  mov     ecx, [rbx+48h]
0x18012afa6  add     rcx, [rbx+30h]; void *
0x18012afaa  cmp     esi, r12d
0x18012afad  jb      short loc_18012B029
0x18012afaf  mov     esi, r12d
0x18012afb2  test    r12d, r12d
0x18012afb5  jz      short loc_18012B015
0x18012afb7  test    rcx, rcx
0x18012afba  jnz     short loc_18012AFCA
0x18012afbc  call    cs:__imp__errno
0x18012afc2  mov     dword ptr [rax], 16h
0x18012afc8  jmp     short loc_18012B00F
0x18012afca  test    r15, r15
0x18012afcd  jz      short loc_18012AFE1
0x18012afcf  cmp     r14, rsi
0x18012afd2  jb      short loc_18012AFE1
0x18012afd4  mov     r8, rsi; Size
0x18012afd7  mov     rdx, r15; Src
0x18012afda  call    memcpy_0
0x18012afdf  jmp     short loc_18012B015
0x18012afe1  mov     r8, r14; Size
0x18012afe4  xor     edx, edx; Val
0x18012afe6  call    memset_0
0x18012afeb  test    r15, r15
0x18012afee  jnz     short loc_18012AFFE
0x18012aff0  call    cs:__imp__errno
0x18012aff6  mov     dword ptr [rax], 16h
0x18012affc  jmp     short loc_18012B00F
0x18012affe  cmp     r14, rsi
0x18012b001  jnb     short loc_18012B015
0x18012b003  call    cs:__imp__errno
0x18012b009  mov     dword ptr [rax], 22h ; '"'
0x18012b00f  call    cs:__imp__invalid_parameter_noinfo
0x18012b015  mov     rcx, [rbx+38h]
0x18012b019  add     rcx, rsi
0x18012b01c  mov     [rbx+38h], rcx
0x18012b020  add     [rbx+48h], r12d
0x18012b024  jmp     loc_18012B263
0x18012b029  test    esi, esi
0x18012b02b  jz      short loc_18012B05D
0x18012b02d  test    rcx, rcx
0x18012b030  jz      short loc_18012B04B
0x18012b032  mov     r8, r14; Size
0x18012b035  test    r15, r15
0x18012b038  jz      short loc_18012B044
0x18012b03a  mov     rdx, r15; Src
0x18012b03d  call    memcpy_0
0x18012b042  jmp     short loc_18012B05D
0x18012b044  xor     edx, edx; Val
0x18012b046  call    memset_0
0x18012b04b  call    cs:__imp__errno
0x18012b051  mov     dword ptr [rax], 16h
0x18012b057  call    cs:__imp__invalid_parameter_noinfo
0x18012b05d  sub     r12d, esi
0x18012b060  mov     [rsp+88h+var_50], r12d
0x18012b065  add     [rbx+38h], r14
0x18012b069  add     [rbx+48h], esi
0x18012b06c  add     r15, r14
0x18012b06f  mov     [rsp+88h+var_48], r15
0x18012b074  mov     edx, [rbx+4Ch]; dwNumberOfBytesToFlush
0x18012b077  mov     rcx, [rbx+30h]; lpBaseAddress
0x18012b07b  call    cs:__imp_FlushViewOfFile
0x18012b081  test    eax, eax
0x18012b083  jnz     short loc_18012B0B5
0x18012b085  mov     rax, [rbx]
0x18012b088  mov     rcx, rbx
0x18012b08b  mov     rax, [rax+30h]
0x18012b08f  call    cs:__guard_dispatch_icall_fptr
0x18012b095  mov     [rbx+18h], edi
0x18012b098  call    cs:__imp_GetLastError
0x18012b09e  test    eax, eax
0x18012b0a0  jle     short loc_18012B0AA
0x18012b0a2  movzx   eax, ax
0x18012b0a5  or      eax, 80070000h
0x18012b0aa  mov     edi, eax
0x18012b0ac  mov     [rsp+88h+var_58], eax
0x18012b0b0  jmp     loc_18012B263
0x18012b0b5  mov     rcx, [rbx+30h]; lpBaseAddress
0x18012b0b9  call    cs:__imp_UnmapViewOfFile
0x18012b0bf  test    eax, eax
0x18012b0c1  jnz     short loc_18012B0EA
0x18012b0c3  xor     edx, edx
0x18012b0c5  mov     rcx, rbx
0x18012b0c8  call    ?HandleMappingFailure@CMemFileWriter@@AEAAXW4EMappingFailureWrite@@@Z; CMemFileWriter::HandleMappingFailure(EMappingFailureWrite)
0x18012b0cd  call    cs:__imp_GetLastError
0x18012b0d3  test    eax, eax
0x18012b0d5  jle     short loc_18012B0DF
0x18012b0d7  movzx   eax, ax
0x18012b0da  or      eax, 80070000h
0x18012b0df  mov     edi, eax
0x18012b0e1  mov     [rsp+88h+var_58], eax
0x18012b0e5  jmp     loc_18012B263
0x18012b0ea  mov     ecx, [rbx+4Ch]
0x18012b0ed  add     rcx, [rbx+40h]
0x18012b0f1  mov     [rbx+40h], rcx
0x18012b0f5  mov     rdx, [rbx+10h]
0x18012b0f9  mov     rax, rdx
0x18012b0fc  sub     rax, rcx
0x18012b0ff  cmp     rax, 100000h
0x18012b105  jl      short loc_18012B10E
0x18012b107  mov     edx, 100000h
0x18012b10c  jmp     short loc_18012B110
0x18012b10e  sub     edx, ecx
0x18012b110  mov     [rbx+4Ch], edx
0x18012b113  mov     [rbx+48h], edi
0x18012b116  cmp     edx, 100000h
0x18012b11c  jnb     loc_18012B1A4
0x18012b122  mov     rcx, [rbx+28h]; hObject
0x18012b126  call    cs:__imp_CloseHandle
0x18012b12c  mov     eax, 100000h
0x18012b131  sub     eax, [rbx+4Ch]
0x18012b134  add     [rbx+10h], rax
0x18012b138  mov     rax, [rbx+10h]
0x18012b13c  mov     r9, rax
0x18012b13f  shr     r9, 20h; dwMaximumSizeHigh
0x18012b143  mov     [rsp+88h+lpName], rdi; lpName
0x18012b148  mov     [rsp+88h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18012b14c  xor     edx, edx; lpFileMappingAttributes
0x18012b14e  mov     r8d, 4; flProtect
0x18012b154  mov     rcx, [rbx+8]; hFile
0x18012b158  call    cs:__imp_CreateFileMappingW
0x18012b15e  mov     [rbx+28h], rax
0x18012b162  test    rax, rax
0x18012b165  jnz     short loc_18012B197
0x18012b167  mov     rax, [rbx]
0x18012b16a  mov     rcx, rbx
0x18012b16d  mov     rax, [rax+30h]
0x18012b171  call    cs:__guard_dispatch_icall_fptr
0x18012b177  mov     [rbx+18h], edi
0x18012b17a  call    cs:__imp_GetLastError
0x18012b180  test    eax, eax
0x18012b182  jle     short loc_18012B18C
0x18012b184  movzx   eax, ax
0x18012b187  or      eax, 80070000h
0x18012b18c  mov     edi, eax
0x18012b18e  mov     [rsp+88h+var_58], eax
0x18012b192  jmp     loc_18012B263
0x18012b197  mov     ecx, [rbx+40h]
0x18012b19a  mov     eax, [rbx+10h]
0x18012b19d  sub     eax, ecx
0x18012b19f  mov     [rbx+4Ch], eax
0x18012b1a2  mov     edx, eax
0x18012b1a4  mov     eax, edx
0x18012b1a6  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x18012b1ab  mov     r9d, ecx; dwFileOffsetLow
0x18012b1ae  mov     r8d, [rbx+44h]; dwFileOffsetHigh
0x18012b1b2  mov     edx, 2; dwDesiredAccess
0x18012b1b7  mov     rcx, [rbx+28h]; hFileMappingObject
0x18012b1bb  call    cs:__imp_MapViewOfFile
0x18012b1c1  mov     [rbx+30h], rax
0x18012b1c5  test    rax, rax
0x18012b1c8  jnz     short loc_18012B1E8
0x18012b1ca  mov     rax, [rbx]
0x18012b1cd  mov     rcx, rbx
0x18012b1d0  mov     rax, [rax+30h]
0x18012b1d4  call    cs:__guard_dispatch_icall_fptr
0x18012b1da  mov     [rbx+18h], edi
0x18012b1dd  mov     edi, 800400CEh
0x18012b1e2  mov     [rsp+88h+var_58], edi
0x18012b1e6  jmp     short loc_18012B263
0x18012b1e8  mov     esi, [rbx+4Ch]
0x18012b1eb  jmp     loc_18012AFA0
0x18012b1f0  mov     rbx, qword ptr [rsp+88h+NumberOfBytesWritten]
0x18012b1f5  mov     rax, [rbx]
0x18012b1f8  mov     rcx, rbx
0x18012b1fb  mov     rax, [rax+30h]
0x18012b1ff  call    cs:__guard_dispatch_icall_fptr
0x18012b205  mov     dword ptr [rbx+18h], 0
0x18012b20c  mov     edi, 800400CEh
0x18012b211  mov     [rsp+88h+var_58], edi
0x18012b215  jmp     short loc_18012B263
0x18012b217  mov     [rsp+88h+NumberOfBytesWritten], edi
0x18012b21b  test    r15, r15
0x18012b21e  jz      loc_18012AF8E
0x18012b224  mov     rcx, [rcx+8]; hFile
0x18012b228  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012b22c  jnz     short loc_18012B235
0x18012b22e  mov     edi, 800400CBh
0x18012b233  jmp     short loc_18012B263
0x18012b235  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rdi; lpOverlapped
0x18012b23a  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18012b23f  mov     r8d, edx; nNumberOfBytesToWrite
0x18012b242  mov     rdx, r15; lpBuffer
0x18012b245  call    cs:__imp_WriteFile
0x18012b24b  test    eax, eax
0x18012b24d  jnz     short loc_18012B263
0x18012b24f  call    cs:__imp_GetLastError
0x18012b255  test    eax, eax
0x18012b257  jle     short loc_18012B261
0x18012b259  movzx   eax, ax
0x18012b25c  or      eax, 80070000h
0x18012b261  mov     edi, eax
0x18012b263  mov     eax, edi
0x18012b265  mov     rcx, [rsp+88h+var_38]
0x18012b26a  xor     rcx, rsp; StackCookie
0x18012b26d  call    __security_check_cookie
0x18012b272  mov     rbx, [rsp+88h+arg_18]
0x18012b27a  add     rsp, 60h
0x18012b27e  pop     r15
0x18012b280  pop     r14
0x18012b282  pop     r12
0x18012b284  pop     rdi
0x18012b285  pop     rsi
0x18012b286  retn
```
