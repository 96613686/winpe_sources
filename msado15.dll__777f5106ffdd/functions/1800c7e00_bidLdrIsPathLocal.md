# _bidLdrIsPathLocal

- ea: `0x1800c7e00`
- end: `0x1800c7f3a`
- name: `_bidLdrIsPathLocal`
- size: `314`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800c7f40`

## callees

- `0x1800c7e00`
- `0x1800cdb20`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800c7edf`
- `msvcrt!wcsncpy_s` at `0x1800c7edf`
- `KERNEL32!GetDriveTypeW` at `0x1800c7ef6`
- `KERNEL32!GetDriveTypeW` at `0x1800c7ef6`
- `KERNEL32!SearchPathW` at `0x1800c7eb2`
- `KERNEL32!SearchPathW` at `0x1800c7eb2`
- `KERNEL32!GetFullPathNameW` at `0x1800c7e82`
- `KERNEL32!GetFullPathNameW` at `0x1800c7e82`

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
0x1800c7e00  mov     [rsp+arg_8], rbx
0x1800c7e05  mov     [rsp+arg_10], rsi
0x1800c7e0a  push    rdi
0x1800c7e0b  sub     rsp, 270h
0x1800c7e12  mov     rax, cs:__security_cookie
0x1800c7e19  xor     rax, rsp
0x1800c7e1c  mov     [rsp+278h+var_18], rax
0x1800c7e24  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800c7e28  mov     rdi, rcx
0x1800c7e2b  mov     rax, rbx
0x1800c7e2e  xor     esi, esi
0x1800c7e30  inc     rax
0x1800c7e33  cmp     [rcx+rax*2], si
0x1800c7e37  jnz     short loc_1800C7E30
0x1800c7e39  cmp     rax, 3
0x1800c7e3d  jb      loc_1800C7F12
0x1800c7e43  cmp     word ptr [rcx], 2Eh ; '.'
0x1800c7e47  jz      short loc_1800C7E68
0x1800c7e49  cmp     word ptr [rcx], 5Ch ; '\'
0x1800c7e4d  jz      loc_1800C7EEB
0x1800c7e53  cmp     word ptr [rcx], 2Fh ; '/'
0x1800c7e57  jz      loc_1800C7EEB
0x1800c7e5d  cmp     word ptr [rcx+2], 3Ah ; ':'
0x1800c7e62  jz      loc_1800C7EEB
0x1800c7e68  cmp     word ptr [rcx], 2Eh ; '.'
0x1800c7e6c  mov     [rsp+278h+FilePart], rsi
0x1800c7e71  jnz     short loc_1800C7E90
0x1800c7e73  lea     r9, [rsp+278h+FilePart]; lpFilePart
0x1800c7e78  mov     edx, 10Eh; nBufferLength
0x1800c7e7d  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x1800c7e82  call    cs:__imp_GetFullPathNameW
0x1800c7e89  nop     dword ptr [rax+rax+00h]
0x1800c7e8e  jmp     short loc_1800C7EBE
0x1800c7e90  lea     rax, [rsp+278h+FilePart]
0x1800c7e95  mov     r9d, 10Eh; nBufferLength
0x1800c7e9b  mov     [rsp+278h+lpFilePart], rax; lpFilePart
0x1800c7ea0  xor     r8d, r8d; lpExtension
0x1800c7ea3  lea     rax, [rsp+278h+Buffer]
0x1800c7ea8  mov     rdx, rdi; lpFileName
0x1800c7eab  xor     ecx, ecx; lpPath
0x1800c7ead  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800c7eb2  call    cs:__imp_SearchPathW
0x1800c7eb9  nop     dword ptr [rax+rax+00h]
0x1800c7ebe  dec     eax
0x1800c7ec0  cmp     eax, 10Ch
0x1800c7ec5  ja      short loc_1800C7F12
0x1800c7ec7  mov     r9, rbx; MaxCount
0x1800c7eca  mov     [rsp+278h+var_1E], si
0x1800c7ed2  lea     r8, [rsp+278h+Buffer]; Source
0x1800c7ed7  mov     edx, 10Eh; SizeInWords
0x1800c7edc  mov     rcx, rdi; Destination
0x1800c7edf  call    cs:__imp_wcsncpy_s
0x1800c7ee6  nop     dword ptr [rax+rax+00h]
0x1800c7eeb  movzx   ebx, word ptr [rdi+6]
0x1800c7eef  mov     rcx, rdi; lpRootPathName
0x1800c7ef2  mov     [rdi+6], si
0x1800c7ef6  call    cs:__imp_GetDriveTypeW
0x1800c7efd  nop     dword ptr [rax+rax+00h]
0x1800c7f02  mov     ecx, esi
0x1800c7f04  mov     [rdi+6], bx
0x1800c7f08  cmp     eax, 3
0x1800c7f0b  setz    cl
0x1800c7f0e  mov     eax, ecx
0x1800c7f10  jmp     short loc_1800C7F14
0x1800c7f12  xor     eax, eax
0x1800c7f14  mov     rcx, [rsp+278h+var_18]
0x1800c7f1c  xor     rcx, rsp; StackCookie
0x1800c7f1f  call    __security_check_cookie
0x1800c7f24  lea     r11, [rsp+278h+var_8]
0x1800c7f2c  mov     rbx, [r11+18h]
0x1800c7f30  mov     rsi, [r11+20h]
0x1800c7f34  mov     rsp, r11
0x1800c7f37  pop     rdi
0x1800c7f38  retn
```
