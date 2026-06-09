# CheckHeader(void *,CFHEADER *,CFRESERVE *)

- ea: `0x18000d81c`
- end: `0x18000d95f`
- name: `?CheckHeader@@YAHPEAXPEAUCFHEADER@@PEAUCFRESERVE@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(HANDLE hFile, struct CFHEADER *lpBuffer, struct CFRESERVE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f5cc`

## callees

- `0x180002620`
- `0x18000d81c`
- `0x18000f4b4`
- `0x18000f500`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000d8a9`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000d8a9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d87e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d8e6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d87e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d8e6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000d855`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000d855`

## pseudocode

```c
__int64 __fastcall CheckHeader(HANDLE hFile, struct CFHEADER *lpBuffer, struct CFRESERVE *a3)
{
  __int64 result; // rax
  unsigned __int64 i; // rsi
  unsigned __int64 v8; // rbx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+38h] [rbp-30h] BYREF

  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  if ( SetFilePointer(hFile, 0, 0, 0) == -1
    || !ReadFile(hFile, lpBuffer, 0x24u, &NumberOfBytesRead, 0)
    || NumberOfBytesRead != 36
    || *((int *)lpBuffer + 2) < 0
    || !GetFileSizeEx(hFile, &FileSize)
    || *((int *)lpBuffer + 2) > FileSize.QuadPart
    || (*((_BYTE *)lpBuffer + 30) & 4) != 0
    && (!ReadFile(hFile, a3, 4u, &NumberOfBytesRead, 0)
     || NumberOfBytesRead != 4
     || !(unsigned int)SetFilePointerRelative(hFile, *(unsigned __int16 *)a3)) )
  {
    return 0;
  }
  result = 1;
  if ( (*((_BYTE *)lpBuffer + 30) & 1) != 0 )
  {
    for ( i = 0; i < 2; ++i )
    {
      result = SkipStringInFile(hFile);
      if ( !(_DWORD)result )
        return result;
    }
  }
  if ( (*((_BYTE *)lpBuffer + 30) & 2) != 0 )
  {
    v8 = 0;
    do
    {
      if ( v8 >= 2 )
        break;
      result = SkipStringInFile(hFile);
      ++v8;
    }
    while ( (_DWORD)result );
  }
  return result;
}

```

## disassembly

```asm
0x18000d81c  push    rbx
0x18000d81e  push    rsi
0x18000d81f  push    rdi
0x18000d820  sub     rsp, 50h
0x18000d824  mov     rax, cs:__security_cookie
0x18000d82b  xor     rax, rsp
0x18000d82e  mov     [rsp+68h+var_28], rax
0x18000d833  mov     rsi, r8
0x18000d836  mov     [rsp+68h+NumberOfBytesRead], 0
0x18000d83e  mov     rbx, rdx
0x18000d841  mov     qword ptr [rsp+68h+FileSize], 0
0x18000d84a  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000d84d  xor     edx, edx; lDistanceToMove
0x18000d84f  xor     r9d, r9d; dwMoveMethod
0x18000d852  mov     rdi, rcx
0x18000d855  call    cs:__imp_SetFilePointer
0x18000d85b  cmp     eax, 0FFFFFFFFh
0x18000d85e  jz      loc_18000D948
0x18000d864  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000d869  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18000d872  mov     r8d, 24h ; '$'; nNumberOfBytesToRead
0x18000d878  mov     rdx, rbx; lpBuffer
0x18000d87b  mov     rcx, rdi; hFile
0x18000d87e  call    cs:__imp_ReadFile
0x18000d884  test    eax, eax
0x18000d886  jz      loc_18000D948
0x18000d88c  cmp     [rsp+68h+NumberOfBytesRead], 24h ; '$'
0x18000d891  jnz     loc_18000D948
0x18000d897  cmp     dword ptr [rbx+8], 0
0x18000d89b  jl      loc_18000D948
0x18000d8a1  lea     rdx, [rsp+68h+FileSize]; lpFileSize
0x18000d8a6  mov     rcx, rdi; hFile
0x18000d8a9  call    cs:__imp_GetFileSizeEx
0x18000d8af  test    eax, eax
0x18000d8b1  jz      loc_18000D948
0x18000d8b7  movsxd  rax, dword ptr [rbx+8]
0x18000d8bb  cmp     rax, qword ptr [rsp+68h+FileSize]
0x18000d8c0  jg      loc_18000D948
0x18000d8c6  test    byte ptr [rbx+1Eh], 4
0x18000d8ca  jz      short loc_18000D906
0x18000d8cc  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000d8d1  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18000d8da  mov     r8d, 4; nNumberOfBytesToRead
0x18000d8e0  mov     rdx, rsi; lpBuffer
0x18000d8e3  mov     rcx, rdi; hFile
0x18000d8e6  call    cs:__imp_ReadFile
0x18000d8ec  test    eax, eax
0x18000d8ee  jz      short loc_18000D948
0x18000d8f0  cmp     [rsp+68h+NumberOfBytesRead], 4
0x18000d8f5  jnz     short loc_18000D948
0x18000d8f7  movzx   edx, word ptr [rsi]; int
0x18000d8fa  mov     rcx, rdi; void *
0x18000d8fd  call    ?SetFilePointerRelative@@YAHPEAXJ@Z; SetFilePointerRelative(void *,long)
0x18000d902  test    eax, eax
0x18000d904  jz      short loc_18000D948
0x18000d906  mov     eax, 1
0x18000d90b  test    [rbx+1Eh], al
0x18000d90e  jz      short loc_18000D929
0x18000d910  xor     esi, esi
0x18000d912  cmp     rsi, 2
0x18000d916  jnb     short loc_18000D929
0x18000d918  mov     rcx, rdi; hFile
0x18000d91b  call    ?SkipStringInFile@@YAHPEAX@Z; SkipStringInFile(void *)
0x18000d920  inc     rsi
0x18000d923  test    eax, eax
0x18000d925  jnz     short loc_18000D912
0x18000d927  jmp     short loc_18000D94A
0x18000d929  test    byte ptr [rbx+1Eh], 2
0x18000d92d  jz      short loc_18000D94A
0x18000d92f  xor     ebx, ebx
0x18000d931  cmp     rbx, 2
0x18000d935  jnb     short loc_18000D94A
0x18000d937  mov     rcx, rdi; hFile
0x18000d93a  call    ?SkipStringInFile@@YAHPEAX@Z; SkipStringInFile(void *)
0x18000d93f  inc     rbx
0x18000d942  test    eax, eax
0x18000d944  jnz     short loc_18000D931
0x18000d946  jmp     short loc_18000D94A
0x18000d948  xor     eax, eax
0x18000d94a  mov     rcx, [rsp+68h+var_28]
0x18000d94f  xor     rcx, rsp; StackCookie
0x18000d952  call    __security_check_cookie
0x18000d957  add     rsp, 50h
0x18000d95b  pop     rdi
0x18000d95c  pop     rsi
0x18000d95d  pop     rbx
0x18000d95e  retn
```
