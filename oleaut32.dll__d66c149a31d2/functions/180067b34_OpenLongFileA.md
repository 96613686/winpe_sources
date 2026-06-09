# OpenLongFileA

- ea: `0x180067b34`
- end: `0x180067d7f`
- name: `OpenLongFileA`
- size: `587`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180048d34`
- `0x18004bcbc`
- `0x18006baa8`

## callees

- `0x180067b34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180067cc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180067cc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067b53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067b83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067d52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067b53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067b83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067d58`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180067ca8`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180067d2f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180067ca8`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180067d2f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180067b73`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180067c65`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180067b73`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180067c65`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180067d04`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180067d04`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180067d49`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180067d49`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180067cd3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180067cd3`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x180067c2d`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x180067c2d`

## pseudocode

```c
__int64 __fastcall OpenLongFileA(LPCSTR lpFileName, __int64 a2, int a3)
{
  DWORD v6; // ecx
  unsigned int v7; // edi
  DWORD v8; // esi
  int v9; // eax
  DWORD v10; // r15d
  DWORD v11; // ecx
  DWORD v12; // ebp
  HANDLE FileA; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // r14d
  int v16; // ecx
  __int64 result; // rax
  int dwCreationDisposition; // [rsp+88h] [rbp+10h]
  WINBOOL Wow64Process; // [rsp+90h] [rbp+18h] BYREF
  PVOID OldValue; // [rsp+98h] [rbp+20h] BYREF

  SetLastError(0);
  if ( (a3 & 0x100) != 0 )
  {
    if ( GetFullPathNameA(lpFileName, 0x103u, (LPSTR)(a2 + 4), 0) <= 0x103 )
    {
      *(_DWORD *)a2 = 0;
      v7 = 0;
      goto LABEL_34;
    }
    goto LABEL_3;
  }
  v7 = 1;
  if ( (a3 & 2) != 0 )
    v8 = -1073741824;
  else
    v8 = (((a3 & 1) == 0) + 1) << 30;
  v9 = a3 & 0x70;
  if ( (a3 & 0x70) != 0 )
  {
    switch ( v9 )
    {
      case 16:
        v10 = 0;
        goto LABEL_17;
      case 32:
        v10 = 5;
        goto LABEL_17;
      case 48:
        v10 = 6;
        goto LABEL_17;
    }
  }
  v10 = 7;
LABEL_17:
  if ( (a3 & 0x1000) != 0 )
    v8 = -1073741824;
  dwCreationDisposition = 3 - ((a3 & 0x1000) != 0);
  if ( (a3 & 0x8000) == 0 )
  {
    v11 = SearchPathA(0, lpFileName, 0, 0x103u, (LPSTR)(a2 + 4), 0);
    if ( v11 > 0x103 )
      goto LABEL_3;
    if ( v11 )
    {
      if ( (a3 & 0x4000) != 0 )
        goto LABEL_34;
    }
    else
    {
      if ( (a3 & 0x4000) != 0 )
      {
        v6 = 2;
        goto LABEL_4;
      }
      if ( GetFullPathNameA(lpFileName, 0x103u, (LPSTR)(a2 + 4), 0) - 1 > 0x102 )
      {
LABEL_3:
        v6 = 13;
LABEL_4:
        SetLastError(v6);
        v7 = -1;
        goto LABEL_34;
      }
    }
  }
  v12 = a3 & 0xFFFF0000;
  FileA = CreateFileA((LPCSTR)(a2 + 4), v8, v10, 0, dwCreationDisposition, v12, 0);
  v7 = (unsigned int)FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    Wow64Process = 0;
    CurrentProcess = GetCurrentProcess();
    if ( IsWow64Process(CurrentProcess, &Wow64Process) )
    {
      LastError = GetLastError();
      if ( LastError == 2 )
      {
        if ( Wow64Process )
        {
          OldValue = 0;
          if ( Wow64DisableWow64FsRedirection(&OldValue) )
          {
            v7 = (unsigned int)CreateFileA((LPCSTR)(a2 + 4), v8, v10, 0, dwCreationDisposition, v12, 0);
            LastError = GetLastError();
            Wow64RevertWow64FsRedirection(OldValue);
          }
          SetLastError(LastError);
        }
      }
    }
  }
LABEL_34:
  v16 = (unsigned __int16)GetLastError();
  result = v7;
  *(_DWORD *)a2 = v16;
  return result;
}

```

## disassembly

```asm
0x180067b34  mov     [rsp+arg_0], rbx
0x180067b39  push    rbp
0x180067b3a  push    rsi
0x180067b3b  push    rdi
0x180067b3c  push    r12
0x180067b3e  push    r13
0x180067b40  push    r14
0x180067b42  push    r15
0x180067b44  sub     rsp, 40h
0x180067b48  mov     r13, rcx
0x180067b4b  mov     ebp, r8d
0x180067b4e  xor     ecx, ecx; dwErrCode
0x180067b50  mov     r12, rdx
0x180067b53  call    cs:__imp_SetLastError
0x180067b59  bt      ebp, 8
0x180067b5d  jnb     short loc_180067B9F
0x180067b5f  mov     r14d, 103h
0x180067b65  lea     r8, [r12+4]; lpBuffer
0x180067b6a  mov     edx, r14d; nBufferLength
0x180067b6d  xor     r9d, r9d; lpFilePart
0x180067b70  mov     rcx, r13; lpFileName
0x180067b73  call    cs:__imp_GetFullPathNameA
0x180067b79  cmp     eax, r14d
0x180067b7c  jbe     short loc_180067B92
0x180067b7e  mov     ecx, 0Dh; dwErrCode
0x180067b83  call    cs:__imp_SetLastError
0x180067b89  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180067b8d  jmp     loc_180067D58
0x180067b92  xor     ebx, ebx
0x180067b94  mov     [r12], ebx
0x180067b98  mov     edi, ebx
0x180067b9a  jmp     loc_180067D58
0x180067b9f  mov     edi, 1
0x180067ba4  mov     ecx, 0C0000000h
0x180067ba9  test    bpl, 2
0x180067bad  jz      short loc_180067BB3
0x180067baf  mov     esi, ecx
0x180067bb1  jmp     short loc_180067BBE
0x180067bb3  mov     esi, ebp
0x180067bb5  not     esi
0x180067bb7  and     esi, edi
0x180067bb9  add     esi, edi
0x180067bbb  shl     esi, 1Eh
0x180067bbe  mov     eax, ebp
0x180067bc0  xor     ebx, ebx
0x180067bc2  and     eax, 70h
0x180067bc5  jz      short loc_180067BE9
0x180067bc7  cmp     eax, 10h
0x180067bca  jz      short loc_180067BE4
0x180067bcc  cmp     eax, 20h ; ' '
0x180067bcf  jz      short loc_180067BDC
0x180067bd1  cmp     eax, 30h ; '0'
0x180067bd4  jnz     short loc_180067BE9
0x180067bd6  lea     r15d, [rbx+6]
0x180067bda  jmp     short loc_180067BEF
0x180067bdc  mov     r15d, 5
0x180067be2  jmp     short loc_180067BEF
0x180067be4  mov     r15d, ebx
0x180067be7  jmp     short loc_180067BEF
0x180067be9  mov     r15d, 7
0x180067bef  mov     eax, ebp
0x180067bf1  and     eax, 1000h
0x180067bf6  cmovnz  esi, ecx
0x180067bf9  neg     eax
0x180067bfb  sbb     edx, edx
0x180067bfd  add     edx, 3
0x180067c00  mov     [rsp+78h+dwCreationDisposition], edx
0x180067c07  lea     rdx, [r12+4]
0x180067c0c  bt      ebp, 0Fh
0x180067c10  jb      short loc_180067C81
0x180067c12  mov     [rsp+78h+lpFilePart], rbx; lpFilePart
0x180067c17  mov     r14d, 103h
0x180067c1d  mov     [rsp+78h+lpBuffer], rdx; lpBuffer
0x180067c22  mov     r9d, r14d; nBufferLength
0x180067c25  mov     rdx, r13; lpFileName
0x180067c28  xor     r8d, r8d; lpExtension
0x180067c2b  xor     ecx, ecx; lpPath
0x180067c2d  call    cs:__imp_SearchPathA
0x180067c33  mov     ecx, eax
0x180067c35  cmp     eax, r14d
0x180067c38  ja      loc_180067B7E
0x180067c3e  mov     eax, ebp
0x180067c40  and     eax, 4000h
0x180067c45  test    ecx, ecx
0x180067c47  jnz     short loc_180067C79
0x180067c49  test    eax, eax
0x180067c4b  jz      short loc_180067C57
0x180067c4d  mov     ecx, 2
0x180067c52  jmp     loc_180067B83
0x180067c57  xor     r9d, r9d; lpFilePart
0x180067c5a  lea     r8, [r12+4]; lpBuffer
0x180067c5f  mov     edx, r14d; nBufferLength
0x180067c62  mov     rcx, r13; lpFileName
0x180067c65  call    cs:__imp_GetFullPathNameA
0x180067c6b  dec     eax
0x180067c6d  cmp     eax, 102h
0x180067c72  jbe     short loc_180067C81
0x180067c74  jmp     loc_180067B7E
0x180067c79  test    eax, eax
0x180067c7b  jnz     loc_180067D58
0x180067c81  mov     eax, [rsp+78h+dwCreationDisposition]
0x180067c88  lea     rcx, [r12+4]; lpFileName
0x180067c8d  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x180067c92  and     ebp, 0FFFF0000h
0x180067c98  mov     dword ptr [rsp+78h+lpFilePart], ebp; dwFlagsAndAttributes
0x180067c9c  xor     r9d, r9d; lpSecurityAttributes
0x180067c9f  mov     r8d, r15d; dwShareMode
0x180067ca2  mov     dword ptr [rsp+78h+lpBuffer], eax; dwCreationDisposition
0x180067ca6  mov     edx, esi; dwDesiredAccess
0x180067ca8  call    cs:__imp_CreateFileA
0x180067cae  mov     rdi, rax
0x180067cb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180067cb5  jnz     loc_180067D58
0x180067cbb  mov     [rsp+78h+Wow64Process], ebx
0x180067cc2  call    cs:__imp_GetCurrentProcess
0x180067cc8  mov     rcx, rax; hProcess
0x180067ccb  lea     rdx, [rsp+78h+Wow64Process]; Wow64Process
0x180067cd3  call    cs:__imp_IsWow64Process
0x180067cd9  test    eax, eax
0x180067cdb  jz      short loc_180067D58
0x180067cdd  call    cs:__imp_GetLastError
0x180067ce3  mov     r14d, eax
0x180067ce6  cmp     eax, 2
0x180067ce9  jnz     short loc_180067D58
0x180067ceb  cmp     [rsp+78h+Wow64Process], ebx
0x180067cf2  jz      short loc_180067D58
0x180067cf4  lea     rcx, [rsp+78h+OldValue]; OldValue
0x180067cfc  mov     [rsp+78h+OldValue], rbx
0x180067d04  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180067d0a  test    eax, eax
0x180067d0c  jz      short loc_180067D4F
0x180067d0e  mov     eax, [rsp+78h+dwCreationDisposition]
0x180067d15  lea     rcx, [r12+4]; lpFileName
0x180067d1a  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x180067d1f  xor     r9d, r9d; lpSecurityAttributes
0x180067d22  mov     dword ptr [rsp+78h+lpFilePart], ebp; dwFlagsAndAttributes
0x180067d26  mov     r8d, r15d; dwShareMode
0x180067d29  mov     edx, esi; dwDesiredAccess
0x180067d2b  mov     dword ptr [rsp+78h+lpBuffer], eax; dwCreationDisposition
0x180067d2f  call    cs:__imp_CreateFileA
0x180067d35  mov     rdi, rax
0x180067d38  call    cs:__imp_GetLastError
0x180067d3e  mov     rcx, [rsp+78h+OldValue]; OlValue
0x180067d46  mov     r14d, eax
0x180067d49  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180067d4f  mov     ecx, r14d; dwErrCode
0x180067d52  call    cs:__imp_SetLastError
0x180067d58  call    cs:__imp_GetLastError
0x180067d5e  mov     rbx, [rsp+78h+arg_0]
0x180067d66  movzx   ecx, ax
0x180067d69  mov     eax, edi
0x180067d6b  mov     [r12], ecx
0x180067d6f  add     rsp, 40h
0x180067d73  pop     r15
0x180067d75  pop     r14
0x180067d77  pop     r13
0x180067d79  pop     r12
0x180067d7b  pop     rdi
0x180067d7c  pop     rsi
0x180067d7d  pop     rbp
0x180067d7e  retn
```
