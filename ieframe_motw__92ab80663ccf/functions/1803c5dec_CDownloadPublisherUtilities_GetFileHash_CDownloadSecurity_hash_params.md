# CDownloadPublisherUtilities::_GetFileHash(CDownloadSecurity::_hash_params *)

- ea: `0x1803c5dec`
- end: `0x1803c61a2`
- name: `?_GetFileHash@CDownloadPublisherUtilities@@CAJPEAU_hash_params@CDownloadSecurity@@@Z`
- size: `950`
- prototype: `__int64 __fastcall(struct CDownloadSecurity::_hash_params *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1803c5ae0`

## callees

- `0x1803c5dec`
- `0x1803d1740`
- `0x180591ef6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1803c5f97`
- `msvcrt!memcpy_s` at `0x1803c5f97`
- `KERNEL32!CreateFileW` at `0x1803c5e2d`
- `KERNEL32!CreateFileW` at `0x1803c5e2d`
- `KERNEL32!ReadFile` at `0x1803c5ef1`
- `KERNEL32!ReadFile` at `0x1803c608e`
- `KERNEL32!ReadFile` at `0x1803c5ef1`
- `KERNEL32!ReadFile` at `0x1803c608e`
- `KERNEL32!GetFileSizeEx` at `0x1803c5e54`
- `KERNEL32!GetFileSizeEx` at `0x1803c5e54`
- `KERNEL32!SetFilePointer` at `0x1803c605e`
- `KERNEL32!SetFilePointer` at `0x1803c605e`
- `KERNEL32!CloseHandle` at `0x1803c6179`
- `KERNEL32!CloseHandle` at `0x1803c6179`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1803c5e6d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1803c5f65`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1803c5e6d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1803c5f65`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803c5fba`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803c60b2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803c5fba`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803c60b2`
- `bcrypt!BCryptFinishHash` at `0x1803c6010`
- `bcrypt!BCryptFinishHash` at `0x1803c6010`
- `bcrypt!BCryptHashData` at `0x1803c5fdb`
- `bcrypt!BCryptHashData` at `0x1803c5fdb`
- `bcrypt!BCryptCreateHash` at `0x1803c5ea6`
- `bcrypt!BCryptCreateHash` at `0x1803c5ea6`
- `bcrypt!BCryptDestroyHash` at `0x1803c602b`
- `bcrypt!BCryptDestroyHash` at `0x1803c602b`

## pseudocode

```c
__int64 __fastcall CDownloadPublisherUtilities::_GetFileHash(struct CDownloadSecurity::_hash_params *a1)
{
  char v2; // r15
  HANDLE FileW; // rax
  void *v4; // r14
  unsigned int v5; // r12d
  char *v6; // rdi
  union _LARGE_INTEGER v7; // r13
  int v8; // eax
  __int64 v9; // r8
  int v10; // eax
  char *v11; // rax
  char *v12; // rsi
  ULONG v13; // esi
  char *v14; // rdx
  int v15; // eax
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rcx
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+48h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+50h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+A0h] [rbp+58h] BYREF
  size_t Size; // [rsp+A8h] [rbp+60h]

  v2 = 1;
  FileW = CreateFileW(*((LPCWSTR *)a1 + 8), 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    FileSize.QuadPart = 0;
    v5 = 0;
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      v6 = (char *)CoTaskMemAlloc(0x10000u);
      if ( v6 )
      {
        phHash = 0;
        v7.QuadPart = 0;
        if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0) < 0 )
          __fastfail(7u);
        if ( !*((_BYTE *)a1 + 73) || (unsigned int)(*((_DWORD *)a1 + 21) - 5) > 2 )
          v2 = 0;
        if ( FileSize.QuadPart > 0 )
        {
          do
          {
            NumberOfBytesRead = 0;
            if ( !ReadFile(v4, v6, 0x10000u, &NumberOfBytesRead, 0) )
              break;
            if ( !v2 )
            {
              if ( FileSize.QuadPart >= 4096 )
              {
                v14 = v6;
                if ( FileSize.QuadPart >= 0x10000 )
                {
                  if ( v7.QuadPart )
                  {
                    v18 = *((unsigned int *)a1 + 12);
                  }
                  else
                  {
                    *((_DWORD *)a1 + 13) = MP_INLINE_CRC(0xFFFFFFFFLL, v6, 4096);
                    *((_DWORD *)a1 + 14) = MP_INLINE_CRC(0xFFFFFFFFLL, v6, 0x10000);
                    v14 = v6;
                    v18 = 0xFFFFFFFFLL;
                  }
                  v13 = NumberOfBytesRead;
                  *((_DWORD *)a1 + 12) = MP_INLINE_CRC(v18, v14, NumberOfBytesRead);
                }
                else
                {
                  v15 = MP_INLINE_CRC(0xFFFFFFFFLL, v6, 4096);
                  v13 = NumberOfBytesRead;
                  v16 = NumberOfBytesRead;
                  *((_DWORD *)a1 + 13) = v15;
                  v17 = MP_INLINE_CRC(0xFFFFFFFFLL, v6, v16);
                  *((_DWORD *)a1 + 12) = v17;
                  if ( v13 >= 0x10000 )
                    v17 = MP_INLINE_CRC(0xFFFFFFFFLL, v6, 0x10000);
                  *((_DWORD *)a1 + 14) = v17;
                  *((_DWORD *)a1 + 15) = MP_INLINE_CRC(0xFFFFFFFFLL, &v6[v13 - 4096], 4096);
                }
                goto LABEL_16;
              }
              Size = 4096 - NumberOfBytesRead;
              memset_0(&v6[NumberOfBytesRead], 0, Size);
              v8 = MP_INLINE_CRC(0xFFFFFFFFLL, v6, 4096);
              v9 = NumberOfBytesRead;
              *((_DWORD *)a1 + 13) = v8;
              v10 = MP_INLINE_CRC(0xFFFFFFFFLL, v6, v9);
              *((_DWORD *)a1 + 12) = v10;
              *((_DWORD *)a1 + 14) = v10;
              *((_DWORD *)a1 + 15) = 0;
              v11 = (char *)CoTaskMemAlloc(0x1000u);
              v12 = v11;
              if ( v11 )
              {
                memset_0(v11, 0, Size);
                memcpy_s(&v12[Size], NumberOfBytesRead, v6, NumberOfBytesRead);
                *((_DWORD *)a1 + 15) = MP_INLINE_CRC(0xFFFFFFFFLL, v12, 4096);
                CoTaskMemFree(v12);
              }
            }
            v13 = NumberOfBytesRead;
LABEL_16:
            v7.QuadPart += v13;
            if ( BCryptHashData(phHash, (PUCHAR)v6, v13, 0) < 0 )
              __fastfail(7u);
          }
          while ( v7.QuadPart < FileSize.QuadPart );
        }
        if ( a1 != (struct CDownloadSecurity::_hash_params *)-16LL
          && BCryptFinishHash(phHash, (PUCHAR)a1 + 16, 0x20u, 0) < 0 )
        {
          __fastfail(7u);
        }
        BCryptDestroyHash(phHash);
        phHash = 0;
        if ( FileSize.QuadPart >= 0x10000 && !v2 )
        {
          *((_DWORD *)a1 + 15) = 0;
          if ( SetFilePointer(v4, -4096, 0, 2u) != -1 )
          {
            NumberOfBytesRead = 0;
            if ( ReadFile(v4, v6, 0x1000u, &NumberOfBytesRead, 0) )
              *((_DWORD *)a1 + 15) = MP_INLINE_CRC(0xFFFFFFFFLL, v6, 4096);
          }
        }
        CoTaskMemFree(v6);
      }
      else
      {
        v5 = -2147024882;
      }
    }
    CloseHandle(v4);
  }
  return v5;
}

```

## disassembly

```asm
0x1803c5dec  push    rbp
0x1803c5dee  push    rbx
0x1803c5def  push    rsi
0x1803c5df0  push    rdi
0x1803c5df1  push    r12
0x1803c5df3  push    r13
0x1803c5df5  push    r14
0x1803c5df7  push    r15
0x1803c5df9  mov     rbp, rsp
0x1803c5dfc  sub     rsp, 48h
0x1803c5e00  xor     esi, esi
0x1803c5e02  mov     rbx, rcx
0x1803c5e05  mov     rcx, [rcx+40h]; lpFileName
0x1803c5e09  xor     r9d, r9d; lpSecurityAttributes
0x1803c5e0c  mov     [rsp+48h+hTemplateFile], rsi; hTemplateFile
0x1803c5e11  mov     edx, 80000000h; dwDesiredAccess
0x1803c5e16  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1803c5e1e  lea     r15d, [rsi+1]
0x1803c5e22  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1803c5e2a  mov     r8d, r15d; dwShareMode
0x1803c5e2d  call    cs:__imp_CreateFileW
0x1803c5e34  nop     dword ptr [rax+rax+00h]
0x1803c5e39  mov     r14, rax
0x1803c5e3c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1803c5e40  jz      loc_1803C6187
0x1803c5e46  lea     rdx, [rbp+FileSize]; lpFileSize
0x1803c5e4a  mov     qword ptr [rbp+FileSize], rsi
0x1803c5e4e  mov     rcx, rax; hFile
0x1803c5e51  mov     r12d, esi
0x1803c5e54  call    cs:__imp_GetFileSizeEx
0x1803c5e5b  nop     dword ptr [rax+rax+00h]
0x1803c5e60  test    eax, eax
0x1803c5e62  jz      loc_1803C6176
0x1803c5e68  mov     ecx, 10000h; cb
0x1803c5e6d  call    cs:__imp_CoTaskMemAlloc
0x1803c5e74  nop     dword ptr [rax+rax+00h]
0x1803c5e79  mov     rdi, rax
0x1803c5e7c  test    rax, rax
0x1803c5e7f  jz      loc_1803C6170
0x1803c5e85  mov     dword ptr [rsp+48h+hTemplateFile], esi; dwFlags
0x1803c5e89  lea     rdx, [rbp+phHash]; phHash
0x1803c5e8d  mov     [rsp+48h+dwFlagsAndAttributes], esi; cbSecret
0x1803c5e91  lea     ecx, [rsi+41h]; hAlgorithm
0x1803c5e94  xor     r9d, r9d; cbHashObject
0x1803c5e97  mov     qword ptr [rsp+48h+dwCreationDisposition], rsi; pbSecret
0x1803c5e9c  xor     r8d, r8d; pbHashObject
0x1803c5e9f  mov     [rbp+phHash], rsi
0x1803c5ea3  mov     r13d, esi
0x1803c5ea6  call    cs:__imp_BCryptCreateHash
0x1803c5ead  nop     dword ptr [rax+rax+00h]
0x1803c5eb2  test    eax, eax
0x1803c5eb4  jns     short loc_1803C5EBB
0x1803c5eb6  lea     ecx, [rsi+7]
0x1803c5eb9  int     29h; Win8: RtlFailFast(ecx)
0x1803c5ebb  cmp     [rbx+49h], sil
0x1803c5ebf  jz      short loc_1803C5ECC
0x1803c5ec1  mov     eax, [rbx+54h]
0x1803c5ec4  sub     eax, 5
0x1803c5ec7  cmp     eax, 2
0x1803c5eca  jbe     short loc_1803C5ECF
0x1803c5ecc  mov     r15b, sil
0x1803c5ecf  cmp     qword ptr [rbp+FileSize], rsi
0x1803c5ed3  jle     loc_1803C5FFC
0x1803c5ed9  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1803c5edd  mov     [rbp+NumberOfBytesRead], esi
0x1803c5ee0  mov     r8d, 10000h; nNumberOfBytesToRead
0x1803c5ee6  mov     qword ptr [rsp+48h+dwCreationDisposition], rsi; lpOverlapped
0x1803c5eeb  mov     rdx, rdi; lpBuffer
0x1803c5eee  mov     rcx, r14; hFile
0x1803c5ef1  call    cs:__imp_ReadFile
0x1803c5ef8  nop     dword ptr [rax+rax+00h]
0x1803c5efd  test    eax, eax
0x1803c5eff  jz      loc_1803C5FFC
0x1803c5f05  test    r15b, r15b
0x1803c5f08  jnz     loc_1803C5FC6
0x1803c5f0e  mov     eax, 1000h
0x1803c5f13  cmp     qword ptr [rbp+FileSize], rax
0x1803c5f17  jge     loc_1803C60C3
0x1803c5f1d  sub     eax, [rbp+NumberOfBytesRead]
0x1803c5f20  xor     edx, edx; Val
0x1803c5f22  mov     ecx, [rbp+NumberOfBytesRead]
0x1803c5f25  mov     r8d, eax; Size
0x1803c5f28  add     rcx, rdi; void *
0x1803c5f2b  mov     [rbp+Size], rax
0x1803c5f2f  call    memset_0
0x1803c5f34  mov     r8d, 1000h
0x1803c5f3a  mov     rdx, rdi
0x1803c5f3d  or      ecx, 0FFFFFFFFh
0x1803c5f40  call    MP_INLINE_CRC
0x1803c5f45  mov     r8d, [rbp+NumberOfBytesRead]
0x1803c5f49  mov     rdx, rdi
0x1803c5f4c  or      ecx, 0FFFFFFFFh
0x1803c5f4f  mov     [rbx+34h], eax
0x1803c5f52  call    MP_INLINE_CRC
0x1803c5f57  mov     ecx, 1000h; cb
0x1803c5f5c  mov     [rbx+30h], eax
0x1803c5f5f  mov     [rbx+38h], eax
0x1803c5f62  mov     [rbx+3Ch], esi
0x1803c5f65  call    cs:__imp_CoTaskMemAlloc
0x1803c5f6c  nop     dword ptr [rax+rax+00h]
0x1803c5f71  mov     rsi, rax
0x1803c5f74  test    rax, rax
0x1803c5f77  jz      short loc_1803C5FC6
0x1803c5f79  mov     r8, [rbp+Size]; Size
0x1803c5f7d  xor     edx, edx; Val
0x1803c5f7f  mov     rcx, rax; void *
0x1803c5f82  call    memset_0
0x1803c5f87  mov     edx, [rbp+NumberOfBytesRead]; DestinationSize
0x1803c5f8a  mov     r8, rdi; Source
0x1803c5f8d  mov     rcx, [rbp+Size]
0x1803c5f91  mov     r9d, edx; SourceSize
0x1803c5f94  add     rcx, rsi; Destination
0x1803c5f97  call    cs:__imp_memcpy_s
0x1803c5f9e  nop     dword ptr [rax+rax+00h]
0x1803c5fa3  mov     r8d, 1000h
0x1803c5fa9  mov     rdx, rsi
0x1803c5fac  or      ecx, 0FFFFFFFFh
0x1803c5faf  call    MP_INLINE_CRC
0x1803c5fb4  mov     rcx, rsi; pv
0x1803c5fb7  mov     [rbx+3Ch], eax
0x1803c5fba  call    cs:__imp_CoTaskMemFree
0x1803c5fc1  nop     dword ptr [rax+rax+00h]
0x1803c5fc6  mov     esi, [rbp+NumberOfBytesRead]
0x1803c5fc9  mov     rcx, [rbp+phHash]; hHash
0x1803c5fcd  xor     r9d, r9d; dwFlags
0x1803c5fd0  mov     eax, esi
0x1803c5fd2  mov     r8d, esi; cbInput
0x1803c5fd5  mov     rdx, rdi; pbInput
0x1803c5fd8  add     r13, rax
0x1803c5fdb  call    cs:__imp_BCryptHashData
0x1803c5fe2  nop     dword ptr [rax+rax+00h]
0x1803c5fe7  xor     esi, esi
0x1803c5fe9  test    eax, eax
0x1803c5feb  jns     short loc_1803C5FF2
0x1803c5fed  lea     ecx, [rsi+7]
0x1803c5ff0  int     29h; Win8: RtlFailFast(ecx)
0x1803c5ff2  cmp     r13, qword ptr [rbp+FileSize]
0x1803c5ff6  jl      loc_1803C5ED9
0x1803c5ffc  lea     rdx, [rbx+10h]; pbOutput
0x1803c6000  test    rdx, rdx
0x1803c6003  jz      short loc_1803C6027
0x1803c6005  mov     rcx, [rbp+phHash]; hHash
0x1803c6009  xor     r9d, r9d; dwFlags
0x1803c600c  lea     r8d, [r9+20h]; cbOutput
0x1803c6010  call    cs:__imp_BCryptFinishHash
0x1803c6017  nop     dword ptr [rax+rax+00h]
0x1803c601c  test    eax, eax
0x1803c601e  jns     short loc_1803C6027
0x1803c6020  mov     ecx, 7
0x1803c6025  int     29h; Win8: RtlFailFast(ecx)
0x1803c6027  mov     rcx, [rbp+phHash]; hHash
0x1803c602b  call    cs:__imp_BCryptDestroyHash
0x1803c6032  nop     dword ptr [rax+rax+00h]
0x1803c6037  cmp     qword ptr [rbp+FileSize], 10000h
0x1803c603f  mov     [rbp+phHash], rsi
0x1803c6043  jl      short loc_1803C60AF
0x1803c6045  test    r15b, r15b
0x1803c6048  jnz     short loc_1803C60AF
0x1803c604a  mov     r9d, 2; dwMoveMethod
0x1803c6050  mov     [rbx+3Ch], esi
0x1803c6053  xor     r8d, r8d; lpDistanceToMoveHigh
0x1803c6056  mov     edx, 0FFFFF000h; lDistanceToMove
0x1803c605b  mov     rcx, r14; hFile
0x1803c605e  call    cs:__imp_SetFilePointer
0x1803c6065  nop     dword ptr [rax+rax+00h]
0x1803c606a  or      r15d, 0FFFFFFFFh
0x1803c606e  cmp     eax, r15d
0x1803c6071  jz      short loc_1803C60AF
0x1803c6073  mov     r13d, 1000h
0x1803c6079  mov     [rbp+NumberOfBytesRead], esi
0x1803c607c  mov     r8d, r13d; nNumberOfBytesToRead
0x1803c607f  mov     qword ptr [rsp+48h+dwCreationDisposition], rsi; lpOverlapped
0x1803c6084  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1803c6088  mov     rdx, rdi; lpBuffer
0x1803c608b  mov     rcx, r14; hFile
0x1803c608e  call    cs:__imp_ReadFile
0x1803c6095  nop     dword ptr [rax+rax+00h]
0x1803c609a  test    eax, eax
0x1803c609c  jz      short loc_1803C60AF
0x1803c609e  mov     r8d, r13d
0x1803c60a1  mov     rdx, rdi
0x1803c60a4  mov     ecx, r15d
0x1803c60a7  call    MP_INLINE_CRC
0x1803c60ac  mov     [rbx+3Ch], eax
0x1803c60af  mov     rcx, rdi; pv
0x1803c60b2  call    cs:__imp_CoTaskMemFree
0x1803c60b9  nop     dword ptr [rax+rax+00h]
0x1803c60be  jmp     loc_1803C6176
0x1803c60c3  cmp     qword ptr [rbp+FileSize], 10000h
0x1803c60cb  mov     rdx, rdi
0x1803c60ce  jge     short loc_1803C612B
0x1803c60d0  mov     r8, rax
0x1803c60d3  or      ecx, 0FFFFFFFFh
0x1803c60d6  call    MP_INLINE_CRC
0x1803c60db  mov     esi, [rbp+NumberOfBytesRead]
0x1803c60de  mov     rdx, rdi
0x1803c60e1  mov     r8d, esi
0x1803c60e4  mov     [rbx+34h], eax
0x1803c60e7  or      ecx, 0FFFFFFFFh
0x1803c60ea  call    MP_INLINE_CRC
0x1803c60ef  mov     ecx, 10000h
0x1803c60f4  mov     [rbx+30h], eax
0x1803c60f7  cmp     esi, ecx
0x1803c60f9  jb      short loc_1803C6109
0x1803c60fb  mov     r8d, ecx
0x1803c60fe  mov     rdx, rdi
0x1803c6101  or      ecx, 0FFFFFFFFh
0x1803c6104  call    MP_INLINE_CRC
0x1803c6109  lea     edx, [rsi-1000h]
0x1803c610f  mov     [rbx+38h], eax
0x1803c6112  add     rdx, rdi
0x1803c6115  mov     r8d, 1000h
0x1803c611b  or      ecx, 0FFFFFFFFh
0x1803c611e  call    MP_INLINE_CRC
0x1803c6123  mov     [rbx+3Ch], eax
0x1803c6126  jmp     loc_1803C5FC9
0x1803c612b  test    r13, r13
0x1803c612e  jnz     short loc_1803C616B
0x1803c6130  or      esi, 0FFFFFFFFh
0x1803c6133  mov     r8, rax
0x1803c6136  mov     ecx, esi
0x1803c6138  call    MP_INLINE_CRC
0x1803c613d  mov     r8d, 10000h
0x1803c6143  mov     [rbx+34h], eax
0x1803c6146  mov     rdx, rdi
0x1803c6149  mov     ecx, esi
0x1803c614b  call    MP_INLINE_CRC
0x1803c6150  mov     [rbx+38h], eax
0x1803c6153  mov     rdx, rdi
0x1803c6156  or      ecx, esi
0x1803c6158  mov     esi, [rbp+NumberOfBytesRead]
0x1803c615b  mov     r8d, esi
0x1803c615e  call    MP_INLINE_CRC
0x1803c6163  mov     [rbx+30h], eax
0x1803c6166  jmp     loc_1803C5FC9
0x1803c616b  mov     ecx, [rbx+30h]
0x1803c616e  jmp     short loc_1803C6158
0x1803c6170  mov     r12d, 8007000Eh
0x1803c6176  mov     rcx, r14; hObject
0x1803c6179  call    cs:__imp_CloseHandle
0x1803c6180  nop     dword ptr [rax+rax+00h]
0x1803c6185  jmp     short loc_1803C618D
0x1803c6187  mov     r12d, 80070057h
0x1803c618d  mov     eax, r12d
0x1803c6190  add     rsp, 48h
0x1803c6194  pop     r15
0x1803c6196  pop     r14
0x1803c6198  pop     r13
0x1803c619a  pop     r12
0x1803c619c  pop     rdi
0x1803c619d  pop     rsi
0x1803c619e  pop     rbx
0x1803c619f  pop     rbp
0x1803c61a0  retn
```
