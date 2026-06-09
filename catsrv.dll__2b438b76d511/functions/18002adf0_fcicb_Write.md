# fcicb_Write

- ea: `0x18002adf0`
- end: `0x18002b100`
- name: `fcicb_Write`
- size: `784`
- prototype: `UINT __cdecl(INT_PTR hf, void *memory, UINT cb, int *err, void *pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002b1c0`

## callees

- `0x18000a01c`
- `0x18002adf0`
- `0x180055502`
- `0x18005550e`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002afb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002afb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aedf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aedf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0ce`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002ae9e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002ae9e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002b07e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002b07e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002aed5`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002aed5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002af5b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002b0c3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002af5b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002b0c3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002af7e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002af7e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002af15`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002af15`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002af37`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002af37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b03d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b03d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b04d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b04d`

## pseudocode

```c
__int64 __fastcall fcicb_Write(int *hf, void *memory, int cb, DWORD *err)
{
  int v8; // eax
  LONG *v9; // r14
  int v10; // ecx
  int *v11; // r12
  HANDLE FileW; // rax
  LONG v13; // ebx
  unsigned int v14; // ecx
  LPVOID v15; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR TempFileName[264]; // [rsp+260h] [rbp+160h] BYREF

  NumberOfBytesWritten = 0;
  memset_0(Buffer, 0, 0x20Au);
  memset_0(TempFileName, 0, 0x20Au);
  v8 = *hf;
  v9 = hf + 4;
  if ( (*hf & 1) != 0 )
  {
    v10 = *v9 + cb;
    if ( v10 < (unsigned int)cb )
    {
LABEL_3:
      *err = 111;
      return 0;
    }
    v11 = hf + 6;
    if ( v10 > hf[6] )
    {
      if ( (v8 & 2) != 0 )
      {
        if ( !GetTempPathW(0x105u, Buffer) && (int)StringCchCopyW(Buffer, 0x105u, L".") < 0 )
          goto LABEL_3;
        if ( !GetTempFileNameW(Buffer, L"SD_", 0, TempFileName) )
        {
          *err = GetLastError();
          return 0;
        }
        FileW = CreateFileW(TempFileName, 0xC0000000, 0, 0, 2u, 0x4000100u, 0);
        *((_QWORD *)hf + 4) = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          cb = 0;
          *err = GetLastError();
          DeleteFileW(TempFileName);
          return (unsigned int)cb;
        }
        if ( !WriteFile(FileW, *((LPCVOID *)hf + 1), hf[5], &NumberOfBytesWritten, 0)
          || NumberOfBytesWritten != hf[5]
          || (v13 = *v9, SetFilePointer(*((HANDLE *)hf + 4), *v9, 0, 0) != v13) )
        {
          *err = GetLastError();
          cb = 0;
          CloseHandle(*((HANDLE *)hf + 4));
          return (unsigned int)cb;
        }
        CoTaskMemFree(*((LPVOID *)hf + 1));
        *hf &= ~1u;
        v8 = *hf;
        *((_QWORD *)hf + 1) = 0;
      }
      else
      {
        cb = *v11 - *v9;
      }
    }
  }
  else
  {
    v11 = hf + 6;
  }
  if ( (v8 & 1) != 0 )
  {
    memcpy_0((void *)(*((_QWORD *)hf + 1) + *v9), memory, (unsigned int)cb);
    v14 = cb + *v9;
    if ( v14 < cb )
      goto LABEL_3;
    if ( v14 > 0x7FFFFFFF )
    {
      *v9 = -1;
      goto LABEL_3;
    }
    *v9 = v14;
    if ( hf[5] < (int)v14 )
      hf[5] = v14;
  }
  else if ( (v8 & 4) != 0 )
  {
    if ( hf[10] && cb )
    {
      if ( *v11 < cb )
      {
        if ( *v11 )
          CoTaskMemFree(*((LPVOID *)hf + 1));
        *v11 = 0;
        v15 = CoTaskMemAlloc((unsigned int)cb);
        *((_QWORD *)hf + 1) = v15;
        if ( v15 )
          hf[6] = cb;
      }
      if ( !hf[6]
        || !ReadFile(*((HANDLE *)hf + 4), *((LPVOID *)hf + 1), cb, &NumberOfBytesWritten, 0)
        || NumberOfBytesWritten != cb
        || memcmp_0(*((const void **)hf + 1), memory, (unsigned int)cb) )
      {
        hf[10] = 0;
      }
    }
  }
  else
  {
    if ( !WriteFile(*((HANDLE *)hf + 4), memory, cb, &NumberOfBytesWritten, 0) )
      *err = GetLastError();
    return NumberOfBytesWritten;
  }
  return (unsigned int)cb;
}

```

## disassembly

```asm
0x18002adf0  push    rbp
0x18002adf2  push    rbx
0x18002adf3  push    rsi
0x18002adf4  push    rdi
0x18002adf5  push    r12
0x18002adf7  push    r13
0x18002adf9  push    r14
0x18002adfb  push    r15
0x18002adfd  lea     rbp, [rsp-388h]
0x18002ae05  sub     rsp, 488h
0x18002ae0c  mov     rax, cs:__security_cookie
0x18002ae13  xor     rax, rsp
0x18002ae16  mov     [rbp+3C0h+var_50], rax
0x18002ae1d  mov     edi, r8d
0x18002ae20  mov     [rsp+4C0h+NumberOfBytesWritten], 0
0x18002ae28  mov     r13, rdx
0x18002ae2b  mov     rsi, rcx
0x18002ae2e  mov     ebx, 20Ah
0x18002ae33  lea     rcx, [rsp+4C0h+Buffer]; void *
0x18002ae38  mov     r8d, ebx; Size
0x18002ae3b  xor     edx, edx; Val
0x18002ae3d  mov     r15, r9
0x18002ae40  call    memset_0
0x18002ae45  mov     r8d, ebx; Size
0x18002ae48  lea     rcx, [rbp+3C0h+TempFileName]; void *
0x18002ae4f  xor     edx, edx; Val
0x18002ae51  call    memset_0
0x18002ae56  mov     eax, [rsi]
0x18002ae58  lea     r14, [rsi+10h]
0x18002ae5c  test    al, 1
0x18002ae5e  jz      loc_18002AFC3
0x18002ae64  mov     edx, [r14]
0x18002ae67  lea     ecx, [rdx+rdi]
0x18002ae6a  cmp     ecx, edi
0x18002ae6c  jnb     short loc_18002AE7C
0x18002ae6e  mov     dword ptr [r15], 6Fh ; 'o'
0x18002ae75  xor     edi, edi
0x18002ae77  jmp     loc_18002B0DB
0x18002ae7c  lea     r12, [rsi+18h]
0x18002ae80  cmp     ecx, [r12]
0x18002ae84  jle     loc_18002AFC7
0x18002ae8a  test    al, 2
0x18002ae8c  jz      loc_18002AFBB
0x18002ae92  mov     ebx, 105h
0x18002ae97  lea     rdx, [rsp+4C0h+Buffer]; lpBuffer
0x18002ae9c  mov     ecx, ebx; nBufferLength
0x18002ae9e  call    cs:__imp_GetTempPathW
0x18002aea4  test    eax, eax
0x18002aea6  jnz     short loc_18002AEBF
0x18002aea8  lea     r8, asc_18005EA94; "."
0x18002aeaf  mov     edx, ebx; unsigned __int64
0x18002aeb1  lea     rcx, [rsp+4C0h+Buffer]; unsigned __int16 *
0x18002aeb6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002aebb  test    eax, eax
0x18002aebd  js      short loc_18002AE6E
0x18002aebf  lea     r9, [rbp+3C0h+TempFileName]; lpTempFileName
0x18002aec6  xor     r8d, r8d; uUnique
0x18002aec9  lea     rdx, PrefixString; "SD_"
0x18002aed0  lea     rcx, [rsp+4C0h+Buffer]; lpPathName
0x18002aed5  call    cs:__imp_GetTempFileNameW
0x18002aedb  test    eax, eax
0x18002aedd  jnz     short loc_18002AEEA
0x18002aedf  call    cs:__imp_GetLastError
0x18002aee5  mov     [r15], eax
0x18002aee8  jmp     short loc_18002AE75
0x18002aeea  mov     [rsp+4C0h+hTemplateFile], 0; hTemplateFile
0x18002aef3  lea     rcx, [rbp+3C0h+TempFileName]; lpFileName
0x18002aefa  mov     [rsp+4C0h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x18002af02  xor     r9d, r9d; lpSecurityAttributes
0x18002af05  xor     r8d, r8d; dwShareMode
0x18002af08  mov     [rsp+4C0h+dwCreationDisposition], 2; dwCreationDisposition
0x18002af10  mov     edx, 0C0000000h; dwDesiredAccess
0x18002af15  call    cs:__imp_CreateFileW
0x18002af1b  mov     [rsi+20h], rax
0x18002af1f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002af23  jnz     short loc_18002AF42
0x18002af25  call    cs:__imp_GetLastError
0x18002af2b  lea     rcx, [rbp+3C0h+TempFileName]; lpFileName
0x18002af32  xor     edi, edi
0x18002af34  mov     [r15], eax
0x18002af37  call    cs:__imp_DeleteFileW
0x18002af3d  jmp     loc_18002B0DB
0x18002af42  mov     r8d, [rsi+14h]; nNumberOfBytesToWrite
0x18002af46  lea     r9, [rsp+4C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002af4b  mov     rdx, [rsi+8]; lpBuffer
0x18002af4f  mov     rcx, rax; hFile
0x18002af52  mov     qword ptr [rsp+4C0h+dwCreationDisposition], 0; lpOverlapped
0x18002af5b  call    cs:__imp_WriteFile
0x18002af61  cmp     eax, 1
0x18002af64  jnz     short loc_18002AFA1
0x18002af66  mov     eax, [rsi+14h]
0x18002af69  cmp     [rsp+4C0h+NumberOfBytesWritten], eax
0x18002af6d  jnz     short loc_18002AFA1
0x18002af6f  mov     ebx, [r14]
0x18002af72  xor     r9d, r9d; dwMoveMethod
0x18002af75  mov     rcx, [rsi+20h]; hFile
0x18002af79  mov     edx, ebx; lDistanceToMove
0x18002af7b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002af7e  call    cs:__imp_SetFilePointer
0x18002af84  cmp     eax, ebx
0x18002af86  jnz     short loc_18002AFA1
0x18002af88  mov     rcx, [rsi+8]; pv
0x18002af8c  call    cs:__imp_CoTaskMemFree
0x18002af92  and     dword ptr [rsi], 0FFFFFFFEh
0x18002af95  mov     eax, [rsi]
0x18002af97  mov     qword ptr [rsi+8], 0
0x18002af9f  jmp     short loc_18002AFC7
0x18002afa1  call    cs:__imp_GetLastError
0x18002afa7  mov     [r15], eax
0x18002afaa  xor     edi, edi
0x18002afac  mov     rcx, [rsi+20h]; hObject
0x18002afb0  call    cs:__imp_CloseHandle
0x18002afb6  jmp     loc_18002B0DB
0x18002afbb  mov     edi, [r12]
0x18002afbf  sub     edi, edx
0x18002afc1  jmp     short loc_18002AFC7
0x18002afc3  lea     r12, [rsi+18h]
0x18002afc7  test    al, 1
0x18002afc9  jz      short loc_18002B012
0x18002afcb  movsxd  rcx, dword ptr [r14]
0x18002afce  mov     rdx, r13; Src
0x18002afd1  add     rcx, [rsi+8]; void *
0x18002afd5  mov     r8d, edi; Size
0x18002afd8  call    memcpy_0
0x18002afdd  mov     ecx, [r14]
0x18002afe0  add     ecx, edi
0x18002afe2  cmp     ecx, edi
0x18002afe4  jb      loc_18002AE6E
0x18002afea  cmp     ecx, 7FFFFFFFh
0x18002aff0  ja      short loc_18002B006
0x18002aff2  mov     [r14], ecx
0x18002aff5  cmp     [rsi+14h], ecx
0x18002aff8  jge     loc_18002B0DB
0x18002affe  mov     [rsi+14h], ecx
0x18002b001  jmp     loc_18002B0DB
0x18002b006  mov     dword ptr [r14], 0FFFFFFFFh
0x18002b00d  jmp     loc_18002AE6E
0x18002b012  test    al, 4
0x18002b014  jz      loc_18002B0AB
0x18002b01a  cmp     dword ptr [rsi+28h], 0
0x18002b01e  jz      loc_18002B0DB
0x18002b024  test    edi, edi
0x18002b026  jz      loc_18002B0DB
0x18002b02c  cmp     [r12], edi
0x18002b030  jge     short loc_18002B05F
0x18002b032  cmp     dword ptr [r12], 0
0x18002b037  jz      short loc_18002B043
0x18002b039  mov     rcx, [rsi+8]; pv
0x18002b03d  call    cs:__imp_CoTaskMemFree
0x18002b043  mov     ecx, edi; cb
0x18002b045  mov     dword ptr [r12], 0
0x18002b04d  call    cs:__imp_CoTaskMemAlloc
0x18002b053  mov     [rsi+8], rax
0x18002b057  test    rax, rax
0x18002b05a  jz      short loc_18002B05F
0x18002b05c  mov     [rsi+18h], edi
0x18002b05f  cmp     dword ptr [rsi+18h], 0
0x18002b063  jz      short loc_18002B0A2
0x18002b065  mov     rdx, [rsi+8]; lpBuffer
0x18002b069  lea     r9, [rsp+4C0h+NumberOfBytesWritten]; lpNumberOfBytesRead
0x18002b06e  mov     rcx, [rsi+20h]; hFile
0x18002b072  mov     r8d, edi; nNumberOfBytesToRead
0x18002b075  mov     qword ptr [rsp+4C0h+dwCreationDisposition], 0; lpOverlapped
0x18002b07e  call    cs:__imp_ReadFile
0x18002b084  cmp     eax, 1
0x18002b087  jnz     short loc_18002B0A2
0x18002b089  cmp     [rsp+4C0h+NumberOfBytesWritten], edi
0x18002b08d  jnz     short loc_18002B0A2
0x18002b08f  mov     rcx, [rsi+8]; Buf1
0x18002b093  mov     rdx, r13; Buf2
0x18002b096  mov     r8d, edi; Size
0x18002b099  call    memcmp_0
0x18002b09e  test    eax, eax
0x18002b0a0  jz      short loc_18002B0DB
0x18002b0a2  mov     dword ptr [rsi+28h], 0
0x18002b0a9  jmp     short loc_18002B0DB
0x18002b0ab  mov     rcx, [rsi+20h]; hFile
0x18002b0af  lea     r9, [rsp+4C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002b0b4  mov     r8d, edi; nNumberOfBytesToWrite
0x18002b0b7  mov     qword ptr [rsp+4C0h+dwCreationDisposition], 0; lpOverlapped
0x18002b0c0  mov     rdx, r13; lpBuffer
0x18002b0c3  call    cs:__imp_WriteFile
0x18002b0c9  cmp     eax, 1
0x18002b0cc  jz      short loc_18002B0D7
0x18002b0ce  call    cs:__imp_GetLastError
0x18002b0d4  mov     [r15], eax
0x18002b0d7  mov     edi, [rsp+4C0h+NumberOfBytesWritten]
0x18002b0db  mov     eax, edi
0x18002b0dd  mov     rcx, [rbp+3C0h+var_50]
0x18002b0e4  xor     rcx, rsp; StackCookie
0x18002b0e7  call    __security_check_cookie
0x18002b0ec  add     rsp, 488h
0x18002b0f3  pop     r15
0x18002b0f5  pop     r14
0x18002b0f7  pop     r13
0x18002b0f9  pop     r12
0x18002b0fb  pop     rdi
0x18002b0fc  pop     rsi
0x18002b0fd  pop     rbx
0x18002b0fe  pop     rbp
0x18002b0ff  retn
```
