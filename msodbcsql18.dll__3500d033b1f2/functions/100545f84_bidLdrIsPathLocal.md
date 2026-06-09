# _bidLdrIsPathLocal

- ea: `0x100545f84`
- end: `0x100546093`
- name: `_bidLdrIsPathLocal`
- size: `271`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10054609c`

## callees

- `0x100545f84`
- `0x100548210`

## import_xrefs

- `KERNEL32!SearchPathW` at `0x100545ffd`
- `KERNEL32!SearchPathW` at `0x100545ffd`
- `KERNEL32!GetDriveTypeW` at `0x100546057`
- `KERNEL32!GetDriveTypeW` at `0x100546057`
- `KERNEL32!GetFullPathNameW` at `0x10054601a`
- `KERNEL32!GetFullPathNameW` at `0x10054601a`
- `KERNEL32!lstrlenW` at `0x100545fae`
- `KERNEL32!lstrlenW` at `0x100545fae`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x100546043`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x100546043`

## pseudocode

```c
__int64 __fastcall bidLdrIsPathLocal(WCHAR *lpRootPathName, int a2)
{
  rsize_t v2; // rbx
  unsigned int v4; // esi
  DWORD FullPathNameW; // eax
  WCHAR v6; // bx
  UINT DriveTypeW; // eax
  LPWSTR FilePart[2]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Buffer[272]; // [rsp+40h] [rbp-238h] BYREF

  v2 = a2;
  if ( lstrlenW(lpRootPathName) >= 3 )
  {
    v4 = 0;
    if ( *lpRootPathName == 46 )
    {
      _mm_lfence();
      FullPathNameW = GetFullPathNameW(lpRootPathName, 0x10Eu, Buffer, FilePart);
    }
    else
    {
      if ( *lpRootPathName == 92 || *lpRootPathName == 47 || lpRootPathName[1] == 58 )
        goto LABEL_10;
      _mm_lfence();
      FullPathNameW = SearchPathW(0, lpRootPathName, 0, 0x10Eu, Buffer, FilePart);
    }
    if ( FullPathNameW - 1 <= 0x10C )
    {
      _mm_lfence();
      Buffer[269] = 0;
      wcsncpy_s(lpRootPathName, v2, Buffer, 0xFFFFFFFFFFFFFFFFuLL);
LABEL_10:
      _mm_lfence();
      v6 = lpRootPathName[3];
      lpRootPathName[3] = 0;
      DriveTypeW = GetDriveTypeW(lpRootPathName);
      lpRootPathName[3] = v6;
      LOBYTE(v4) = DriveTypeW == 3;
      return v4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x100545f84  mov     [rsp+arg_10], rbx
0x100545f89  mov     [rsp+arg_18], rsi
0x100545f8e  push    rdi
0x100545f8f  sub     rsp, 270h
0x100545f96  mov     rax, cs:__security_cookie
0x100545f9d  xor     rax, rsp
0x100545fa0  mov     [rsp+278h+var_18], rax
0x100545fa8  movsxd  rbx, edx
0x100545fab  mov     rdi, rcx
0x100545fae  call    cs:__imp_lstrlenW
0x100545fb4  cmp     eax, 3
0x100545fb7  jl      loc_10054606C
0x100545fbd  xor     esi, esi
0x100545fbf  cmp     word ptr [rdi], 2Eh ; '.'
0x100545fc3  jz      short loc_100546005
0x100545fc5  cmp     word ptr [rdi], 5Ch ; '\'
0x100545fc9  jz      short loc_100546049
0x100545fcb  cmp     word ptr [rdi], 2Fh ; '/'
0x100545fcf  jz      short loc_100546049
0x100545fd1  cmp     word ptr [rdi+2], 3Ah ; ':'
0x100545fd6  jz      short loc_100546049
0x100545fd8  lfence
0x100545fdb  lea     rax, [rsp+278h+FilePart]
0x100545fe0  mov     r9d, 10Eh; nBufferLength
0x100545fe6  mov     [rsp+278h+lpFilePart], rax; lpFilePart
0x100545feb  xor     r8d, r8d; lpExtension
0x100545fee  lea     rax, [rsp+278h+Buffer]
0x100545ff3  mov     rdx, rdi; lpFileName
0x100545ff6  xor     ecx, ecx; lpPath
0x100545ff8  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x100545ffd  call    cs:__imp_SearchPathW
0x100546003  jmp     short loc_100546020
0x100546005  lfence
0x100546008  lea     r9, [rsp+278h+FilePart]; lpFilePart
0x10054600d  mov     edx, 10Eh; nBufferLength
0x100546012  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x100546017  mov     rcx, rdi; lpFileName
0x10054601a  call    cs:__imp_GetFullPathNameW
0x100546020  dec     eax
0x100546022  cmp     eax, 10Ch
0x100546027  ja      short loc_10054606C
0x100546029  lfence
0x10054602c  mov     rdx, rbx; SizeInWords
0x10054602f  mov     [rsp+278h+var_1E], si
0x100546037  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x10054603b  lea     r8, [rsp+278h+Buffer]; Source
0x100546040  mov     rcx, rdi; Destination
0x100546043  call    cs:__imp_wcsncpy_s
0x100546049  lfence
0x10054604c  movzx   ebx, word ptr [rdi+6]
0x100546050  mov     rcx, rdi; lpRootPathName
0x100546053  mov     [rdi+6], si
0x100546057  call    cs:__imp_GetDriveTypeW
0x10054605d  cmp     eax, 3
0x100546060  mov     [rdi+6], bx
0x100546064  setz    sil
0x100546068  mov     eax, esi
0x10054606a  jmp     short loc_10054606E
0x10054606c  xor     eax, eax
0x10054606e  mov     rcx, [rsp+278h+var_18]
0x100546076  xor     rcx, rsp; StackCookie
0x100546079  call    __security_check_cookie
0x10054607e  lea     r11, [rsp+278h+var_8]
0x100546086  mov     rbx, [r11+20h]
0x10054608a  mov     rsi, [r11+28h]
0x10054608e  mov     rsp, r11
0x100546091  pop     rdi
0x100546092  retn
```
