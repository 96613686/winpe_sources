# _bidLdrIsPathLocal

- ea: `0x18003b418`
- end: `0x18003b52d`
- name: `_bidLdrIsPathLocal`
- size: `277`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800197e4`

## callees

- `0x18003b418`
- `0x18007e700`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18003b4df`
- `msvcrt!wcsncpy_s` at `0x18003b4df`
- `KERNEL32!GetDriveTypeW` at `0x18003b4f0`
- `KERNEL32!GetDriveTypeW` at `0x18003b4f0`
- `KERNEL32!SearchPathW` at `0x18003b4b8`
- `KERNEL32!SearchPathW` at `0x18003b4b8`
- `KERNEL32!GetFullPathNameW` at `0x18003b48e`
- `KERNEL32!GetFullPathNameW` at `0x18003b48e`

## pseudocode

```c
_BOOL8 __fastcall bidLdrIsPathLocal(WCHAR *lpRootPathName)
{
  unsigned __int64 v2; // rax
  bool v3; // zf
  DWORD FullPathNameW; // eax
  WCHAR v5; // bx
  UINT DriveTypeW; // eax
  LPWSTR FilePart[2]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Buffer[272]; // [rsp+40h] [rbp-238h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( lpRootPathName[v2] );
  if ( v2 >= 3 )
  {
    if ( *lpRootPathName != 46 && (*lpRootPathName == 92 || *lpRootPathName == 47 || lpRootPathName[1] == 58) )
      goto LABEL_13;
    v3 = *lpRootPathName == 46;
    FilePart[0] = 0;
    if ( v3 )
      FullPathNameW = GetFullPathNameW(lpRootPathName, 0x10Eu, Buffer, FilePart);
    else
      FullPathNameW = SearchPathW(0, lpRootPathName, 0, 0x10Eu, Buffer, FilePart);
    if ( FullPathNameW - 1 <= 0x10C )
    {
      Buffer[269] = 0;
      wcsncpy_s(lpRootPathName, 0x10Eu, Buffer, 0xFFFFFFFFFFFFFFFFuLL);
LABEL_13:
      v5 = lpRootPathName[3];
      lpRootPathName[3] = 0;
      DriveTypeW = GetDriveTypeW(lpRootPathName);
      lpRootPathName[3] = v5;
      return DriveTypeW == 3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003b418  mov     [rsp+arg_8], rbx
0x18003b41d  mov     [rsp+arg_10], rsi
0x18003b422  push    rdi
0x18003b423  sub     rsp, 270h
0x18003b42a  mov     rax, cs:__security_cookie
0x18003b431  xor     rax, rsp
0x18003b434  mov     [rsp+278h+var_18], rax
0x18003b43c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003b440  mov     rdi, rcx
0x18003b443  mov     rax, rbx
0x18003b446  xor     esi, esi
0x18003b448  inc     rax
0x18003b44b  cmp     [rcx+rax*2], si
0x18003b44f  jnz     short loc_18003B448
0x18003b451  cmp     rax, 3
0x18003b455  jb      loc_18003B506
0x18003b45b  cmp     word ptr [rcx], 2Eh ; '.'
0x18003b45f  jz      short loc_18003B474
0x18003b461  cmp     word ptr [rcx], 5Ch ; '\'
0x18003b465  jz      short loc_18003B4E5
0x18003b467  cmp     word ptr [rcx], 2Fh ; '/'
0x18003b46b  jz      short loc_18003B4E5
0x18003b46d  cmp     word ptr [rcx+2], 3Ah ; ':'
0x18003b472  jz      short loc_18003B4E5
0x18003b474  cmp     word ptr [rcx], 2Eh ; '.'
0x18003b478  mov     [rsp+278h+FilePart], rsi
0x18003b47d  jnz     short loc_18003B496
0x18003b47f  lea     r9, [rsp+278h+FilePart]; lpFilePart
0x18003b484  mov     edx, 10Eh; nBufferLength
0x18003b489  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x18003b48e  call    cs:__imp_GetFullPathNameW
0x18003b494  jmp     short loc_18003B4BE
0x18003b496  lea     rax, [rsp+278h+FilePart]
0x18003b49b  mov     r9d, 10Eh; nBufferLength
0x18003b4a1  mov     [rsp+278h+lpFilePart], rax; lpFilePart
0x18003b4a6  xor     r8d, r8d; lpExtension
0x18003b4a9  lea     rax, [rsp+278h+Buffer]
0x18003b4ae  mov     rdx, rdi; lpFileName
0x18003b4b1  xor     ecx, ecx; lpPath
0x18003b4b3  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003b4b8  call    cs:__imp_SearchPathW
0x18003b4be  dec     eax
0x18003b4c0  cmp     eax, 10Ch
0x18003b4c5  ja      short loc_18003B506
0x18003b4c7  mov     r9, rbx; MaxCount
0x18003b4ca  mov     [rsp+278h+var_1E], si
0x18003b4d2  lea     r8, [rsp+278h+Buffer]; Source
0x18003b4d7  mov     edx, 10Eh; SizeInWords
0x18003b4dc  mov     rcx, rdi; Destination
0x18003b4df  call    cs:__imp_wcsncpy_s
0x18003b4e5  movzx   ebx, word ptr [rdi+6]
0x18003b4e9  mov     rcx, rdi; lpRootPathName
0x18003b4ec  mov     [rdi+6], si
0x18003b4f0  call    cs:__imp_GetDriveTypeW
0x18003b4f6  mov     ecx, esi
0x18003b4f8  mov     [rdi+6], bx
0x18003b4fc  cmp     eax, 3
0x18003b4ff  setz    cl
0x18003b502  mov     eax, ecx
0x18003b504  jmp     short loc_18003B508
0x18003b506  xor     eax, eax
0x18003b508  mov     rcx, [rsp+278h+var_18]
0x18003b510  xor     rcx, rsp; StackCookie
0x18003b513  call    __security_check_cookie
0x18003b518  lea     r11, [rsp+278h+var_8]
0x18003b520  mov     rbx, [r11+18h]
0x18003b524  mov     rsi, [r11+20h]
0x18003b528  mov     rsp, r11
0x18003b52b  pop     rdi
0x18003b52c  retn
```
