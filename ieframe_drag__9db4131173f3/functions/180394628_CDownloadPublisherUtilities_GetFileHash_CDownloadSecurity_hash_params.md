# CDownloadPublisherUtilities::_GetFileHash(CDownloadSecurity::_hash_params *)

- ea: `0x180394628`
- end: `0x180394983`
- name: `?_GetFileHash@CDownloadPublisherUtilities@@CAJPEAU_hash_params@CDownloadSecurity@@@Z`
- size: `859`
- prototype: `__int64 __fastcall(struct CDownloadSecurity::_hash_params *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180394350`

## callees

- `0x180394628`
- `0x18039f8f4`
- `0x18054e286`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1803947af`
- `msvcrt!memcpy_s` at `0x1803947af`
- `KERNEL32!CreateFileW` at `0x180394669`
- `KERNEL32!CreateFileW` at `0x180394669`
- `KERNEL32!ReadFile` at `0x180394715`
- `KERNEL32!ReadFile` at `0x180394882`
- `KERNEL32!ReadFile` at `0x180394715`
- `KERNEL32!ReadFile` at `0x180394882`
- `KERNEL32!GetFileSizeEx` at `0x18039468a`
- `KERNEL32!GetFileSizeEx` at `0x18039468a`
- `KERNEL32!SetFilePointer` at `0x180394858`
- `KERNEL32!SetFilePointer` at `0x180394858`
- `KERNEL32!CloseHandle` at `0x180394961`
- `KERNEL32!CloseHandle` at `0x180394961`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18039469d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180394783`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18039469d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180394783`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803947cc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803948a0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803947cc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803948a0`
- `bcrypt!BCryptFinishHash` at `0x180394816`
- `bcrypt!BCryptFinishHash` at `0x180394816`
- `bcrypt!BCryptHashData` at `0x1803947e7`
- `bcrypt!BCryptHashData` at `0x1803947e7`
- `bcrypt!BCryptCreateHash` at `0x1803946d0`
- `bcrypt!BCryptCreateHash` at `0x1803946d0`
- `bcrypt!BCryptDestroyHash` at `0x18039482b`
- `bcrypt!BCryptDestroyHash` at `0x18039482b`

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
0x180394628  push    rbp
0x18039462a  push    rbx
0x18039462b  push    rsi
0x18039462c  push    rdi
0x18039462d  push    r12
0x18039462f  push    r13
0x180394631  push    r14
0x180394633  push    r15
0x180394635  mov     rbp, rsp
0x180394638  sub     rsp, 48h
0x18039463c  xor     esi, esi
0x18039463e  mov     rbx, rcx
0x180394641  mov     rcx, [rcx+40h]; lpFileName
0x180394645  xor     r9d, r9d; lpSecurityAttributes
0x180394648  mov     [rsp+48h+hTemplateFile], rsi; hTemplateFile
0x18039464d  mov     edx, 80000000h; dwDesiredAccess
0x180394652  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18039465a  lea     r15d, [rsi+1]
0x18039465e  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180394666  mov     r8d, r15d; dwShareMode
0x180394669  call    cs:__imp_CreateFileW
0x18039466f  mov     r14, rax
0x180394672  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180394676  jz      loc_180394969
0x18039467c  lea     rdx, [rbp+FileSize]; lpFileSize
0x180394680  mov     qword ptr [rbp+FileSize], rsi
0x180394684  mov     rcx, rax; hFile
0x180394687  mov     r12d, esi
0x18039468a  call    cs:__imp_GetFileSizeEx
0x180394690  test    eax, eax
0x180394692  jz      loc_18039495E
0x180394698  mov     ecx, 10000h; cb
0x18039469d  call    cs:__imp_CoTaskMemAlloc
0x1803946a3  mov     rdi, rax
0x1803946a6  test    rax, rax
0x1803946a9  jz      loc_180394958
0x1803946af  mov     dword ptr [rsp+48h+hTemplateFile], esi; dwFlags
0x1803946b3  lea     rdx, [rbp+phHash]; phHash
0x1803946b7  mov     [rsp+48h+dwFlagsAndAttributes], esi; cbSecret
0x1803946bb  lea     ecx, [rsi+41h]; hAlgorithm
0x1803946be  xor     r9d, r9d; cbHashObject
0x1803946c1  mov     qword ptr [rsp+48h+dwCreationDisposition], rsi; pbSecret
0x1803946c6  xor     r8d, r8d; pbHashObject
0x1803946c9  mov     [rbp+phHash], rsi
0x1803946cd  mov     r13d, esi
0x1803946d0  call    cs:__imp_BCryptCreateHash
0x1803946d6  test    eax, eax
0x1803946d8  jns     short loc_1803946DF
0x1803946da  lea     ecx, [rsi+7]
0x1803946dd  int     29h; Win8: RtlFailFast(ecx)
0x1803946df  cmp     [rbx+49h], sil
0x1803946e3  jz      short loc_1803946F0
0x1803946e5  mov     eax, [rbx+54h]
0x1803946e8  sub     eax, 5
0x1803946eb  cmp     eax, 2
0x1803946ee  jbe     short loc_1803946F3
0x1803946f0  mov     r15b, sil
0x1803946f3  cmp     qword ptr [rbp+FileSize], rsi
0x1803946f7  jle     loc_180394802
0x1803946fd  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180394701  mov     [rbp+NumberOfBytesRead], esi
0x180394704  mov     r8d, 10000h; nNumberOfBytesToRead
0x18039470a  mov     qword ptr [rsp+48h+dwCreationDisposition], rsi; lpOverlapped
0x18039470f  mov     rdx, rdi; lpBuffer
0x180394712  mov     rcx, r14; hFile
0x180394715  call    cs:__imp_ReadFile
0x18039471b  test    eax, eax
0x18039471d  jz      loc_180394802
0x180394723  test    r15b, r15b
0x180394726  jnz     loc_1803947D2
0x18039472c  mov     eax, 1000h
0x180394731  cmp     qword ptr [rbp+FileSize], rax
0x180394735  jge     loc_1803948AB
0x18039473b  sub     eax, [rbp+NumberOfBytesRead]
0x18039473e  xor     edx, edx; Val
0x180394740  mov     ecx, [rbp+NumberOfBytesRead]
0x180394743  mov     r8d, eax; Size
0x180394746  add     rcx, rdi; void *
0x180394749  mov     [rbp+Size], rax
0x18039474d  call    memset_0
0x180394752  mov     r8d, 1000h
0x180394758  mov     rdx, rdi
0x18039475b  or      ecx, 0FFFFFFFFh
0x18039475e  call    MP_INLINE_CRC
0x180394763  mov     r8d, [rbp+NumberOfBytesRead]
0x180394767  mov     rdx, rdi
0x18039476a  or      ecx, 0FFFFFFFFh
0x18039476d  mov     [rbx+34h], eax
0x180394770  call    MP_INLINE_CRC
0x180394775  mov     ecx, 1000h; cb
0x18039477a  mov     [rbx+30h], eax
0x18039477d  mov     [rbx+38h], eax
0x180394780  mov     [rbx+3Ch], esi
0x180394783  call    cs:__imp_CoTaskMemAlloc
0x180394789  mov     rsi, rax
0x18039478c  test    rax, rax
0x18039478f  jz      short loc_1803947D2
0x180394791  mov     r8, [rbp+Size]; Size
0x180394795  xor     edx, edx; Val
0x180394797  mov     rcx, rax; void *
0x18039479a  call    memset_0
0x18039479f  mov     edx, [rbp+NumberOfBytesRead]; DestinationSize
0x1803947a2  mov     r8, rdi; Source
0x1803947a5  mov     rcx, [rbp+Size]
0x1803947a9  mov     r9d, edx; SourceSize
0x1803947ac  add     rcx, rsi; Destination
0x1803947af  call    cs:__imp_memcpy_s
0x1803947b5  mov     r8d, 1000h
0x1803947bb  mov     rdx, rsi
0x1803947be  or      ecx, 0FFFFFFFFh
0x1803947c1  call    MP_INLINE_CRC
0x1803947c6  mov     rcx, rsi; pv
0x1803947c9  mov     [rbx+3Ch], eax
0x1803947cc  call    cs:__imp_CoTaskMemFree
0x1803947d2  mov     esi, [rbp+NumberOfBytesRead]
0x1803947d5  mov     rcx, [rbp+phHash]; hHash
0x1803947d9  xor     r9d, r9d; dwFlags
0x1803947dc  mov     eax, esi
0x1803947de  mov     r8d, esi; cbInput
0x1803947e1  mov     rdx, rdi; pbInput
0x1803947e4  add     r13, rax
0x1803947e7  call    cs:__imp_BCryptHashData
0x1803947ed  xor     esi, esi
0x1803947ef  test    eax, eax
0x1803947f1  jns     short loc_1803947F8
0x1803947f3  lea     ecx, [rsi+7]
0x1803947f6  int     29h; Win8: RtlFailFast(ecx)
0x1803947f8  cmp     r13, qword ptr [rbp+FileSize]
0x1803947fc  jl      loc_1803946FD
0x180394802  lea     rdx, [rbx+10h]; pbOutput
0x180394806  test    rdx, rdx
0x180394809  jz      short loc_180394827
0x18039480b  mov     rcx, [rbp+phHash]; hHash
0x18039480f  xor     r9d, r9d; dwFlags
0x180394812  lea     r8d, [r9+20h]; cbOutput
0x180394816  call    cs:__imp_BCryptFinishHash
0x18039481c  test    eax, eax
0x18039481e  jns     short loc_180394827
0x180394820  mov     ecx, 7
0x180394825  int     29h; Win8: RtlFailFast(ecx)
0x180394827  mov     rcx, [rbp+phHash]; hHash
0x18039482b  call    cs:__imp_BCryptDestroyHash
0x180394831  cmp     qword ptr [rbp+FileSize], 10000h
0x180394839  mov     [rbp+phHash], rsi
0x18039483d  jl      short loc_18039489D
0x18039483f  test    r15b, r15b
0x180394842  jnz     short loc_18039489D
0x180394844  mov     r9d, 2; dwMoveMethod
0x18039484a  mov     [rbx+3Ch], esi
0x18039484d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180394850  mov     edx, 0FFFFF000h; lDistanceToMove
0x180394855  mov     rcx, r14; hFile
0x180394858  call    cs:__imp_SetFilePointer
0x18039485e  or      r15d, 0FFFFFFFFh
0x180394862  cmp     eax, r15d
0x180394865  jz      short loc_18039489D
0x180394867  mov     r13d, 1000h
0x18039486d  mov     [rbp+NumberOfBytesRead], esi
0x180394870  mov     r8d, r13d; nNumberOfBytesToRead
0x180394873  mov     qword ptr [rsp+48h+dwCreationDisposition], rsi; lpOverlapped
0x180394878  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18039487c  mov     rdx, rdi; lpBuffer
0x18039487f  mov     rcx, r14; hFile
0x180394882  call    cs:__imp_ReadFile
0x180394888  test    eax, eax
0x18039488a  jz      short loc_18039489D
0x18039488c  mov     r8d, r13d
0x18039488f  mov     rdx, rdi
0x180394892  mov     ecx, r15d
0x180394895  call    MP_INLINE_CRC
0x18039489a  mov     [rbx+3Ch], eax
0x18039489d  mov     rcx, rdi; pv
0x1803948a0  call    cs:__imp_CoTaskMemFree
0x1803948a6  jmp     loc_18039495E
0x1803948ab  cmp     qword ptr [rbp+FileSize], 10000h
0x1803948b3  mov     rdx, rdi
0x1803948b6  jge     short loc_180394913
0x1803948b8  mov     r8, rax
0x1803948bb  or      ecx, 0FFFFFFFFh
0x1803948be  call    MP_INLINE_CRC
0x1803948c3  mov     esi, [rbp+NumberOfBytesRead]
0x1803948c6  mov     rdx, rdi
0x1803948c9  mov     r8d, esi
0x1803948cc  mov     [rbx+34h], eax
0x1803948cf  or      ecx, 0FFFFFFFFh
0x1803948d2  call    MP_INLINE_CRC
0x1803948d7  mov     ecx, 10000h
0x1803948dc  mov     [rbx+30h], eax
0x1803948df  cmp     esi, ecx
0x1803948e1  jb      short loc_1803948F1
0x1803948e3  mov     r8d, ecx
0x1803948e6  mov     rdx, rdi
0x1803948e9  or      ecx, 0FFFFFFFFh
0x1803948ec  call    MP_INLINE_CRC
0x1803948f1  lea     edx, [rsi-1000h]
0x1803948f7  mov     [rbx+38h], eax
0x1803948fa  add     rdx, rdi
0x1803948fd  mov     r8d, 1000h
0x180394903  or      ecx, 0FFFFFFFFh
0x180394906  call    MP_INLINE_CRC
0x18039490b  mov     [rbx+3Ch], eax
0x18039490e  jmp     loc_1803947D5
0x180394913  test    r13, r13
0x180394916  jnz     short loc_180394953
0x180394918  or      esi, 0FFFFFFFFh
0x18039491b  mov     r8, rax
0x18039491e  mov     ecx, esi
0x180394920  call    MP_INLINE_CRC
0x180394925  mov     r8d, 10000h
0x18039492b  mov     [rbx+34h], eax
0x18039492e  mov     rdx, rdi
0x180394931  mov     ecx, esi
0x180394933  call    MP_INLINE_CRC
0x180394938  mov     [rbx+38h], eax
0x18039493b  mov     rdx, rdi
0x18039493e  or      ecx, esi
0x180394940  mov     esi, [rbp+NumberOfBytesRead]
0x180394943  mov     r8d, esi
0x180394946  call    MP_INLINE_CRC
0x18039494b  mov     [rbx+30h], eax
0x18039494e  jmp     loc_1803947D5
0x180394953  mov     ecx, [rbx+30h]
0x180394956  jmp     short loc_180394940
0x180394958  mov     r12d, 8007000Eh
0x18039495e  mov     rcx, r14; hObject
0x180394961  call    cs:__imp_CloseHandle
0x180394967  jmp     short loc_18039496F
0x180394969  mov     r12d, 80070057h
0x18039496f  mov     eax, r12d
0x180394972  add     rsp, 48h
0x180394976  pop     r15
0x180394978  pop     r14
0x18039497a  pop     r13
0x18039497c  pop     r12
0x18039497e  pop     rdi
0x18039497f  pop     rsi
0x180394980  pop     rbx
0x180394981  pop     rbp
0x180394982  retn
```
