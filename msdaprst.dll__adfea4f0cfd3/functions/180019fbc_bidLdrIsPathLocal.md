# _bidLdrIsPathLocal

- ea: `0x180019fbc`
- end: `0x18001a0f6`
- name: `_bidLdrIsPathLocal`
- size: `314`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a0fc`

## callees

- `0x180019fbc`
- `0x18002f0e0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18001a09b`
- `msvcrt!wcsncpy_s` at `0x18001a09b`
- `KERNEL32!GetDriveTypeW` at `0x18001a0b2`
- `KERNEL32!GetDriveTypeW` at `0x18001a0b2`
- `KERNEL32!SearchPathW` at `0x18001a06e`
- `KERNEL32!SearchPathW` at `0x18001a06e`
- `KERNEL32!GetFullPathNameW` at `0x18001a03e`
- `KERNEL32!GetFullPathNameW` at `0x18001a03e`

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
0x180019fbc  mov     [rsp+arg_8], rbx
0x180019fc1  mov     [rsp+arg_10], rsi
0x180019fc6  push    rdi
0x180019fc7  sub     rsp, 270h
0x180019fce  mov     rax, cs:__security_cookie
0x180019fd5  xor     rax, rsp
0x180019fd8  mov     [rsp+278h+var_18], rax
0x180019fe0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019fe4  mov     rdi, rcx
0x180019fe7  mov     rax, rbx
0x180019fea  xor     esi, esi
0x180019fec  inc     rax
0x180019fef  cmp     [rcx+rax*2], si
0x180019ff3  jnz     short loc_180019FEC
0x180019ff5  cmp     rax, 3
0x180019ff9  jb      loc_18001A0CE
0x180019fff  cmp     word ptr [rcx], 2Eh ; '.'
0x18001a003  jz      short loc_18001A024
0x18001a005  cmp     word ptr [rcx], 5Ch ; '\'
0x18001a009  jz      loc_18001A0A7
0x18001a00f  cmp     word ptr [rcx], 2Fh ; '/'
0x18001a013  jz      loc_18001A0A7
0x18001a019  cmp     word ptr [rcx+2], 3Ah ; ':'
0x18001a01e  jz      loc_18001A0A7
0x18001a024  cmp     word ptr [rcx], 2Eh ; '.'
0x18001a028  mov     [rsp+278h+FilePart], rsi
0x18001a02d  jnz     short loc_18001A04C
0x18001a02f  lea     r9, [rsp+278h+FilePart]; lpFilePart
0x18001a034  mov     edx, 10Eh; nBufferLength
0x18001a039  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x18001a03e  call    cs:__imp_GetFullPathNameW
0x18001a045  nop     dword ptr [rax+rax+00h]
0x18001a04a  jmp     short loc_18001A07A
0x18001a04c  lea     rax, [rsp+278h+FilePart]
0x18001a051  mov     r9d, 10Eh; nBufferLength
0x18001a057  mov     [rsp+278h+lpFilePart], rax; lpFilePart
0x18001a05c  xor     r8d, r8d; lpExtension
0x18001a05f  lea     rax, [rsp+278h+Buffer]
0x18001a064  mov     rdx, rdi; lpFileName
0x18001a067  xor     ecx, ecx; lpPath
0x18001a069  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001a06e  call    cs:__imp_SearchPathW
0x18001a075  nop     dword ptr [rax+rax+00h]
0x18001a07a  dec     eax
0x18001a07c  cmp     eax, 10Ch
0x18001a081  ja      short loc_18001A0CE
0x18001a083  mov     r9, rbx; MaxCount
0x18001a086  mov     [rsp+278h+var_1E], si
0x18001a08e  lea     r8, [rsp+278h+Buffer]; Source
0x18001a093  mov     edx, 10Eh; SizeInWords
0x18001a098  mov     rcx, rdi; Destination
0x18001a09b  call    cs:__imp_wcsncpy_s
0x18001a0a2  nop     dword ptr [rax+rax+00h]
0x18001a0a7  movzx   ebx, word ptr [rdi+6]
0x18001a0ab  mov     rcx, rdi; lpRootPathName
0x18001a0ae  mov     [rdi+6], si
0x18001a0b2  call    cs:__imp_GetDriveTypeW
0x18001a0b9  nop     dword ptr [rax+rax+00h]
0x18001a0be  mov     ecx, esi
0x18001a0c0  mov     [rdi+6], bx
0x18001a0c4  cmp     eax, 3
0x18001a0c7  setz    cl
0x18001a0ca  mov     eax, ecx
0x18001a0cc  jmp     short loc_18001A0D0
0x18001a0ce  xor     eax, eax
0x18001a0d0  mov     rcx, [rsp+278h+var_18]
0x18001a0d8  xor     rcx, rsp; StackCookie
0x18001a0db  call    __security_check_cookie
0x18001a0e0  lea     r11, [rsp+278h+var_8]
0x18001a0e8  mov     rbx, [r11+18h]
0x18001a0ec  mov     rsi, [r11+20h]
0x18001a0f0  mov     rsp, r11
0x18001a0f3  pop     rdi
0x18001a0f4  retn
```
