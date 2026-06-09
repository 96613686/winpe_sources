# NfsUpCallpPasswdGroupLoadPasswdGroupFile

- ea: `0x140010da4`
- end: `0x1400110f6`
- name: `NfsUpCallpPasswdGroupLoadPasswdGroupFile`
- size: `850`
- prototype: `__int64 __fastcall(_QWORD *, __int64, const WCHAR *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1400114ac`
- `0x140011800`

## callees

- `0x140010da4`
- `0x1400110fc`
- `0x140011244`

## import_xrefs

- `KERNEL32!ReadFile` at `0x140010eb5`
- `KERNEL32!ReadFile` at `0x140010eb5`
- `KERNEL32!GetFileSizeEx` at `0x140010e26`
- `KERNEL32!GetFileSizeEx` at `0x140010e26`
- `KERNEL32!MultiByteToWideChar` at `0x140010ef3`
- `KERNEL32!MultiByteToWideChar` at `0x140010f2d`
- `KERNEL32!MultiByteToWideChar` at `0x140010ef3`
- `KERNEL32!MultiByteToWideChar` at `0x140010f2d`
- `KERNEL32!GetLastError` at `0x140010e02`
- `KERNEL32!GetLastError` at `0x140010e30`
- `KERNEL32!GetLastError` at `0x140010ebf`
- `KERNEL32!GetLastError` at `0x140010f04`
- `KERNEL32!GetLastError` at `0x140010f37`
- `KERNEL32!GetLastError` at `0x140010e02`
- `KERNEL32!GetLastError` at `0x140010e30`
- `KERNEL32!GetLastError` at `0x140010ebf`
- `KERNEL32!GetLastError` at `0x140010f04`
- `KERNEL32!GetLastError` at `0x140010f37`
- `KERNEL32!CloseHandle` at `0x140010ed0`
- `KERNEL32!CloseHandle` at `0x140010ed0`
- `KERNEL32!CreateFileW` at `0x140010df3`
- `KERNEL32!CreateFileW` at `0x140010df3`
- `ntdll!RtlAllocateHeap` at `0x140010e80`
- `ntdll!RtlAllocateHeap` at `0x140010ffd`
- `ntdll!RtlAllocateHeap` at `0x14001102d`
- `ntdll!RtlAllocateHeap` at `0x140010e80`
- `ntdll!RtlAllocateHeap` at `0x140010ffd`
- `ntdll!RtlAllocateHeap` at `0x14001102d`
- `ntdll!RtlFreeHeap` at `0x140010f56`
- `ntdll!RtlFreeHeap` at `0x1400110af`
- `ntdll!RtlFreeHeap` at `0x1400110d6`
- `ntdll!RtlFreeHeap` at `0x140010f56`
- `ntdll!RtlFreeHeap` at `0x1400110af`
- `ntdll!RtlFreeHeap` at `0x1400110d6`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupLoadPasswdGroupFile(_QWORD *a1, __int64 a2, const WCHAR *a3, char a4)
{
  unsigned int cchWideChar; // r15d
  DWORD LastError; // ebx
  HANDLE FileW; // rbp
  void *v9; // rdi
  WCHAR *v10; // r14
  CHAR *v11; // rsi
  CHAR *Heap; // rax
  unsigned int v13; // eax
  unsigned int v14; // r11d
  __int64 v15; // rbp
  unsigned int v16; // r10d
  WCHAR *v17; // rdx
  unsigned __int64 v18; // r9
  WCHAR *i; // r8
  char *v20; // rcx
  unsigned __int16 v21; // cx
  __int64 v22; // rbx
  char *v23; // rax
  int v24; // ecx
  int v25; // r9d
  union _LARGE_INTEGER FileSize; // [rsp+80h] [rbp+8h] BYREF
  __int64 NumberOfBytesRead; // [rsp+88h] [rbp+10h] BYREF
  char v29; // [rsp+98h] [rbp+20h]

  v29 = a4;
  NumberOfBytesRead = a2;
  cchWideChar = 0;
  *a1 = 0;
  FileSize.QuadPart = 0;
  LastError = 0;
  FileW = CreateFileW(a3, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError )
      return LastError;
  }
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( GetFileSizeEx(FileW, &FileSize) || (LastError = GetLastError()) == 0 )
  {
    if ( FileSize.QuadPart )
    {
      if ( FileSize.QuadPart <= 0x10000000 )
      {
        Heap = (CHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, FileSize.QuadPart);
        v11 = Heap;
        if ( Heap )
        {
          LODWORD(NumberOfBytesRead) = 0;
          if ( !ReadFile(FileW, Heap, FileSize.LowPart, (LPDWORD)&NumberOfBytesRead, 0) )
            LastError = GetLastError();
        }
        else
        {
          LastError = 8;
        }
      }
      else
      {
        LastError = 223;
      }
    }
    else
    {
      LastError = 232;
    }
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( !LastError )
  {
    v13 = MultiByteToWideChar(1u, 0, v11, FileSize.LowPart, 0, 0);
    cchWideChar = v13;
    if ( v13 )
    {
      v10 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v13);
      if ( v10 )
      {
LABEL_18:
        if ( !MultiByteToWideChar(1u, 0, v11, FileSize.LowPart, v10, cchWideChar) )
          LastError = GetLastError();
        goto LABEL_20;
      }
      LastError = 8;
    }
    else
    {
      cchWideChar = 0;
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_18;
    }
  }
LABEL_20:
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  if ( !LastError )
  {
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v17 = v10;
    v18 = (unsigned __int64)&v10[cchWideChar];
    if ( (unsigned __int64)v10 >= v18 )
    {
LABEL_34:
      v22 = 16LL * (unsigned int)v15;
      v23 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v22 + v14 + 32LL);
      v9 = v23;
      if ( v23 )
      {
        LOBYTE(v25) = v29;
        *((_DWORD *)v23 + 6) = v15;
        *(_QWORD *)v23 = v23 + 32;
        *((_QWORD *)v23 + 1) = &v23[8 * v15 + 32];
        *((_QWORD *)v23 + 2) = &v23[v22 + 32];
        LastError = NfsUpCallpPasswdGroupPopulatePasswdGroupData(
                      v24,
                      (_DWORD)v23,
                      (_DWORD)a3,
                      v25,
                      (__int64)v10,
                      cchWideChar);
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      while ( 1 )
      {
        ++v16;
        for ( i = v17; (unsigned __int64)i < v18; ++i )
        {
          if ( *i == 10 )
            break;
        }
        v20 = (char *)v17;
        if ( v17 < i )
        {
          do
          {
            if ( *(_WORD *)v20 == 58 )
              break;
            v20 += 2;
          }
          while ( v20 < (char *)i );
        }
        if ( v20 - (char *)v17 > 0xFFFF )
          break;
        v21 = (_WORD)v20 - (_WORD)v17;
        if ( v21 )
        {
          v15 = (unsigned int)(v15 + 1);
          v14 += (v21 + 31) & 0xFFFFFFF8;
        }
        v17 = i + 1;
        if ( (unsigned __int64)(i + 1) >= v18 )
          goto LABEL_34;
      }
      NfsUpCallpPasswdGroupLogPasswdGroupBadSyntax(v20, a3, v16);
      LastError = 13;
    }
  }
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( LastError )
  {
    if ( v9 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  }
  else
  {
    *a1 = v9;
  }
  return LastError;
}

```

## disassembly

```asm
0x140010da4  mov     rax, rsp
0x140010da7  mov     [rax+18h], rbx
0x140010dab  mov     [rax+20h], r9b
0x140010daf  mov     [rax+10h], rdx
0x140010db3  push    rbp
0x140010db4  push    rsi
0x140010db5  push    rdi
0x140010db6  push    r12
0x140010db8  push    r13
0x140010dba  push    r14
0x140010dbc  push    r15
0x140010dbe  sub     rsp, 40h
0x140010dc2  xor     r15d, r15d
0x140010dc5  mov     r12, r8
0x140010dc8  mov     [rax-48h], r15
0x140010dcc  mov     r13, rcx
0x140010dcf  mov     [rcx], r15
0x140010dd2  xor     r9d, r9d; lpSecurityAttributes
0x140010dd5  mov     [rax-50h], r15d
0x140010dd9  mov     edx, 80000000h; dwDesiredAccess
0x140010dde  lea     r8d, [r15+1]; dwShareMode
0x140010de2  mov     [rax+8], r15
0x140010de6  mov     rcx, r12; lpFileName
0x140010de9  mov     dword ptr [rax-58h], 3
0x140010df0  mov     ebx, r15d
0x140010df3  call    cs:__imp_CreateFileW
0x140010df9  mov     rbp, rax
0x140010dfc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010e00  jnz     short loc_140010E12
0x140010e02  call    cs:__imp_GetLastError
0x140010e08  mov     ebx, eax
0x140010e0a  test    eax, eax
0x140010e0c  jnz     loc_1400110DC
0x140010e12  lea     rdx, [rsp+78h+FileSize]; lpFileSize
0x140010e1a  mov     rcx, rbp; hFile
0x140010e1d  mov     rdi, r15
0x140010e20  mov     r14, r15
0x140010e23  mov     rsi, r15
0x140010e26  call    cs:__imp_GetFileSizeEx
0x140010e2c  test    eax, eax
0x140010e2e  jnz     short loc_140010E40
0x140010e30  call    cs:__imp_GetLastError
0x140010e36  mov     ebx, eax
0x140010e38  test    eax, eax
0x140010e3a  jnz     loc_140010EC7
0x140010e40  cmp     qword ptr [rsp+78h+FileSize], rsi
0x140010e48  jnz     short loc_140010E51
0x140010e4a  mov     ebx, 0E8h
0x140010e4f  jmp     short loc_140010EC7
0x140010e51  cmp     qword ptr [rsp+78h+FileSize], 10000000h
0x140010e5d  jle     short loc_140010E66
0x140010e5f  mov     ebx, 0DFh
0x140010e64  jmp     short loc_140010EC7
0x140010e66  mov     rcx, gs:60h
0x140010e6f  mov     edx, 8; Flags
0x140010e74  mov     r8, qword ptr [rsp+78h+FileSize]; Size
0x140010e7c  mov     rcx, [rcx+30h]; HeapHandle
0x140010e80  call    cs:__imp_RtlAllocateHeap
0x140010e86  mov     rsi, rax
0x140010e89  test    rax, rax
0x140010e8c  jnz     short loc_140010E93
0x140010e8e  lea     ebx, [rax+8]
0x140010e91  jmp     short loc_140010EC7
0x140010e93  mov     r8d, dword ptr [rsp+78h+FileSize]; nNumberOfBytesToRead
0x140010e9b  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140010ea3  mov     rdx, rax; lpBuffer
0x140010ea6  mov     dword ptr [rsp+78h+NumberOfBytesRead], edi
0x140010ead  mov     rcx, rbp; hFile
0x140010eb0  mov     [rsp+78h+lpOverlapped], rdi; lpOverlapped
0x140010eb5  call    cs:__imp_ReadFile
0x140010ebb  test    eax, eax
0x140010ebd  jnz     short loc_140010EC7
0x140010ebf  call    cs:__imp_GetLastError
0x140010ec5  mov     ebx, eax
0x140010ec7  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x140010ecb  jz      short loc_140010ED6
0x140010ecd  mov     rcx, rbp; hObject
0x140010ed0  call    cs:__imp_CloseHandle
0x140010ed6  test    ebx, ebx
0x140010ed8  jnz     short loc_140010F3F
0x140010eda  mov     r9d, dword ptr [rsp+78h+FileSize]; cbMultiByte
0x140010ee2  lea     ecx, [rbx+1]; CodePage
0x140010ee5  mov     [rsp+78h+cchWideChar], edi; cchWideChar
0x140010ee9  mov     r8, rsi; lpMultiByteStr
0x140010eec  xor     edx, edx; dwFlags
0x140010eee  mov     [rsp+78h+lpOverlapped], rdi; lpWideCharStr
0x140010ef3  call    cs:__imp_MultiByteToWideChar
0x140010ef9  mov     r15d, eax
0x140010efc  test    eax, eax
0x140010efe  jnz     loc_140011013
0x140010f04  call    cs:__imp_GetLastError
0x140010f0a  xor     r15d, r15d
0x140010f0d  mov     ebx, eax
0x140010f0f  test    eax, eax
0x140010f11  jnz     short loc_140010F3F
0x140010f13  mov     r9d, dword ptr [rsp+78h+FileSize]; cbMultiByte
0x140010f1b  xor     edx, edx; dwFlags
0x140010f1d  mov     [rsp+78h+cchWideChar], r15d; cchWideChar
0x140010f22  mov     r8, rsi; lpMultiByteStr
0x140010f25  mov     [rsp+78h+lpOverlapped], r14; lpWideCharStr
0x140010f2a  lea     ecx, [rdx+1]; CodePage
0x140010f2d  call    cs:__imp_MultiByteToWideChar
0x140010f33  test    eax, eax
0x140010f35  jnz     short loc_140010F3F
0x140010f37  call    cs:__imp_GetLastError
0x140010f3d  mov     ebx, eax
0x140010f3f  test    rsi, rsi
0x140010f42  jz      short loc_140010F5C
0x140010f44  mov     rcx, gs:60h
0x140010f4d  mov     r8, rsi; P
0x140010f50  xor     edx, edx; Flags
0x140010f52  mov     rcx, [rcx+30h]; HeapHandle
0x140010f56  call    cs:__imp_RtlFreeHeap
0x140010f5c  test    ebx, ebx
0x140010f5e  jnz     loc_140011098
0x140010f64  mov     eax, r15d
0x140010f67  xor     r11d, r11d
0x140010f6a  xor     ebp, ebp
0x140010f6c  xor     r10d, r10d
0x140010f6f  mov     rdx, r14
0x140010f72  lea     r9, [r14+rax*2]
0x140010f76  cmp     r14, r9
0x140010f79  jnb     short loc_140010FDB
0x140010f7b  inc     r10d
0x140010f7e  mov     r8, rdx
0x140010f81  cmp     rdx, r9
0x140010f84  jnb     short loc_140010F96
0x140010f86  cmp     word ptr [r8], 0Ah
0x140010f8b  jz      short loc_140010F96
0x140010f8d  add     r8, 2
0x140010f91  cmp     r8, r9
0x140010f94  jb      short loc_140010F86
0x140010f96  mov     rcx, rdx
0x140010f99  cmp     rdx, r8
0x140010f9c  jnb     short loc_140010FAD
0x140010f9e  cmp     word ptr [rcx], 3Ah ; ':'
0x140010fa2  jz      short loc_140010FAD
0x140010fa4  add     rcx, 2
0x140010fa8  cmp     rcx, r8
0x140010fab  jb      short loc_140010F9E
0x140010fad  mov     rax, rcx
0x140010fb0  sub     rax, rdx
0x140010fb3  cmp     rax, 0FFFFh
0x140010fb9  jg      loc_140011046
0x140010fbf  sub     cx, dx
0x140010fc2  jz      short loc_140010FD2
0x140010fc4  movzx   eax, cx
0x140010fc7  inc     ebp
0x140010fc9  add     eax, 1Fh
0x140010fcc  and     eax, 0FFFFFFF8h
0x140010fcf  add     r11d, eax
0x140010fd2  lea     rdx, [r8+2]
0x140010fd6  cmp     rdx, r9
0x140010fd9  jb      short loc_140010F7B
0x140010fdb  mov     rcx, gs:60h
0x140010fe4  mov     edx, 8; Flags
0x140010fe9  mov     r8d, r11d
0x140010fec  add     r8, 20h ; ' '
0x140010ff0  mov     ebx, ebp
0x140010ff2  shl     rbx, 4
0x140010ff6  mov     rcx, [rcx+30h]; HeapHandle
0x140010ffa  add     r8, rbx; Size
0x140010ffd  call    cs:__imp_RtlAllocateHeap
0x140011003  mov     rdi, rax
0x140011006  test    rax, rax
0x140011009  jnz     short loc_140011058
0x14001100b  lea     ebx, [rax+8]
0x14001100e  jmp     loc_140011098
0x140011013  mov     rcx, gs:60h
0x14001101c  mov     r8, r15
0x14001101f  mov     ebp, 8
0x140011024  add     r8, r8; Size
0x140011027  mov     edx, ebp; Flags
0x140011029  mov     rcx, [rcx+30h]; HeapHandle
0x14001102d  call    cs:__imp_RtlAllocateHeap
0x140011033  mov     r14, rax
0x140011036  test    rax, rax
0x140011039  jnz     loc_140010F13
0x14001103f  mov     ebx, ebp
0x140011041  jmp     loc_140010F3F
0x140011046  mov     r8d, r10d
0x140011049  mov     rdx, r12
0x14001104c  call    NfsUpCallpPasswdGroupLogPasswdGroupBadSyntax
0x140011051  mov     ebx, 0Dh
0x140011056  jmp     short loc_140011098
0x140011058  mov     r9b, [rsp+78h+arg_18]
0x140011060  mov     r8, r12
0x140011063  mov     [rax+18h], ebp
0x140011066  mov     rdx, rdi
0x140011069  add     rax, 20h ; ' '
0x14001106d  mov     [rsp+78h+cchWideChar], r15d
0x140011072  mov     [rdi], rax
0x140011075  lea     rax, [rbp+4]
0x140011079  lea     rax, [rdi+rax*8]
0x14001107d  mov     [rsp+78h+lpOverlapped], r14
0x140011082  mov     [rdi+8], rax
0x140011086  lea     rax, [rdi+20h]
0x14001108a  add     rax, rbx
0x14001108d  mov     [rdi+10h], rax
0x140011091  call    NfsUpCallpPasswdGroupPopulatePasswdGroupData
0x140011096  mov     ebx, eax
0x140011098  test    r14, r14
0x14001109b  jz      short loc_1400110B5
0x14001109d  mov     rcx, gs:60h
0x1400110a6  mov     r8, r14; P
0x1400110a9  xor     edx, edx; Flags
0x1400110ab  mov     rcx, [rcx+30h]; HeapHandle
0x1400110af  call    cs:__imp_RtlFreeHeap
0x1400110b5  test    ebx, ebx
0x1400110b7  jnz     short loc_1400110BF
0x1400110b9  mov     [r13+0], rdi
0x1400110bd  jmp     short loc_1400110DC
0x1400110bf  test    rdi, rdi
0x1400110c2  jz      short loc_1400110DC
0x1400110c4  mov     rcx, gs:60h
0x1400110cd  mov     r8, rdi; P
0x1400110d0  xor     edx, edx; Flags
0x1400110d2  mov     rcx, [rcx+30h]; HeapHandle
0x1400110d6  call    cs:__imp_RtlFreeHeap
0x1400110dc  mov     eax, ebx
0x1400110de  mov     rbx, [rsp+78h+arg_10]
0x1400110e6  add     rsp, 40h
0x1400110ea  pop     r15
0x1400110ec  pop     r14
0x1400110ee  pop     r13
0x1400110f0  pop     r12
0x1400110f2  pop     rdi
0x1400110f3  pop     rsi
0x1400110f4  pop     rbp
0x1400110f5  retn
```
