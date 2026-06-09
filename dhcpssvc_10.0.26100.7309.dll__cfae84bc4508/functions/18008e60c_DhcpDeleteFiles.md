# DhcpDeleteFiles

- ea: `0x18008e60c`
- end: `0x18008e877`
- name: `DhcpDeleteFiles`
- size: `619`
- prototype: `__int64 __fastcall(LPCSTR lpPathName, LPCSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000df98`
- `0x18000f4b8`

## callees

- `0x180002854`
- `0x180011724`
- `0x18008e60c`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `KERNEL32!FindFirstFileA` at `0x18008e71c`
- `KERNEL32!FindFirstFileA` at `0x18008e71c`
- `KERNEL32!DeleteFileA` at `0x18008e795`
- `KERNEL32!DeleteFileA` at `0x18008e795`
- `KERNEL32!FindNextFileA` at `0x18008e77c`
- `KERNEL32!FindNextFileA` at `0x18008e77c`
- `KERNEL32!SetCurrentDirectoryA` at `0x18008e6be`
- `KERNEL32!SetCurrentDirectoryA` at `0x18008e80b`
- `KERNEL32!SetCurrentDirectoryA` at `0x18008e6be`
- `KERNEL32!SetCurrentDirectoryA` at `0x18008e80b`
- `KERNEL32!GetCurrentDirectoryA` at `0x18008e664`
- `KERNEL32!GetCurrentDirectoryA` at `0x18008e664`
- `KERNEL32!GetLastError` at `0x18008e676`
- `KERNEL32!GetLastError` at `0x18008e6ce`
- `KERNEL32!GetLastError` at `0x18008e731`
- `KERNEL32!GetLastError` at `0x18008e7a5`
- `KERNEL32!GetLastError` at `0x18008e83d`
- `KERNEL32!GetLastError` at `0x18008e676`
- `KERNEL32!GetLastError` at `0x18008e6ce`
- `KERNEL32!GetLastError` at `0x18008e731`
- `KERNEL32!GetLastError` at `0x18008e7a5`
- `KERNEL32!GetLastError` at `0x18008e83d`
- `KERNEL32!FindClose` at `0x18008e7e9`
- `KERNEL32!FindClose` at `0x18008e7e9`

## pseudocode

```c
__int64 __fastcall DhcpDeleteFiles(LPCSTR lpPathName, LPCSTR lpFileName)
{
  DWORD v4; // edi
  DWORD LastError; // eax
  DWORD v6; // ebx
  DWORD v8; // ebx
  DWORD v9; // esi
  HANDLE FirstFileA; // rbp
  _QWORD *v11; // rax
  __int64 v12; // rdx
  DWORD v13; // ecx
  _WIN32_FIND_DATAA FindFileData; // [rsp+30h] [rbp-278h] BYREF
  CHAR Buffer[272]; // [rsp+170h] [rbp-138h] BYREF

  memset_0(Buffer, 0, 0x104u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = 0;
  if ( !GetCurrentDirectoryA(0x104u, Buffer) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids, LastError);
    return v6;
  }
  if ( SetCurrentDirectoryA(lpPathName) )
  {
    FirstFileA = FindFirstFileA(lpFileName, &FindFileData);
    if ( FirstFileA != (HANDLE)-1LL )
    {
      do
      {
        if ( !DeleteFileA(FindFileData.cFileName) )
        {
          v8 = GetLastError();
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v12 = 18;
LABEL_20:
            WPP_SF_D(v11[2], v12, &WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids, v8);
            goto LABEL_21;
          }
          goto LABEL_21;
        }
      }
      while ( FindNextFileA(FirstFileA, &FindFileData) );
      v8 = GetLastError();
      if ( v8 != 18 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v12 = 19;
          goto LABEL_20;
        }
      }
LABEL_21:
      v9 = v8;
      FindClose(FirstFileA);
      goto LABEL_22;
    }
    v8 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids,
        (_DWORD)lpFileName,
        v8);
  }
  else
  {
    v8 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids, v8);
  }
  v9 = v8;
LABEL_22:
  v13 = 0;
  if ( v8 != 18 )
    v13 = v9;
  if ( v13 != 2 )
    v4 = v13;
  SetCurrentDirectoryA(Buffer);
  return v4;
}

```

## disassembly

```asm
0x18008e60c  mov     [rsp+arg_10], rbx
0x18008e611  push    rbp
0x18008e612  push    rsi
0x18008e613  push    rdi
0x18008e614  sub     rsp, 290h
0x18008e61b  mov     rax, cs:__security_cookie
0x18008e622  xor     rax, rsp
0x18008e625  mov     [rsp+2A8h+var_28], rax
0x18008e62d  mov     rsi, rdx
0x18008e630  mov     rbx, rcx
0x18008e633  mov     edi, 104h
0x18008e638  lea     rcx, [rsp+2A8h+Buffer]; void *
0x18008e640  mov     r8d, edi; Size
0x18008e643  xor     edx, edx; Val
0x18008e645  call    memset_0
0x18008e64a  xor     edx, edx; Val
0x18008e64c  lea     r8d, [rdi+3Ch]; Size
0x18008e650  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x18008e655  call    memset_0
0x18008e65a  lea     rdx, [rsp+2A8h+Buffer]; lpBuffer
0x18008e662  mov     ecx, edi; nBufferLength
0x18008e664  call    cs:__imp_GetCurrentDirectoryA
0x18008e66b  nop     dword ptr [rax+rax+00h]
0x18008e670  xor     edi, edi
0x18008e672  test    eax, eax
0x18008e674  jnz     short loc_18008E6BB
0x18008e676  call    cs:__imp_GetLastError
0x18008e67d  nop     dword ptr [rax+rax+00h]
0x18008e682  mov     ebx, eax
0x18008e684  mov     r10, cs:WPP_GLOBAL_Control
0x18008e68b  lea     rcx, WPP_GLOBAL_Control
0x18008e692  cmp     r10, rcx
0x18008e695  jz      short loc_18008E6B4
0x18008e697  test    byte ptr [r10+1Ch], 10h
0x18008e69c  jz      short loc_18008E6B4
0x18008e69e  mov     rcx, [r10+10h]
0x18008e6a2  lea     edx, [rdi+0Fh]
0x18008e6a5  mov     r9d, eax
0x18008e6a8  lea     r8, WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids
0x18008e6af  call    WPP_SF_D
0x18008e6b4  mov     eax, ebx
0x18008e6b6  jmp     loc_18008E819
0x18008e6bb  mov     rcx, rbx; lpPathName
0x18008e6be  call    cs:__imp_SetCurrentDirectoryA
0x18008e6c5  nop     dword ptr [rax+rax+00h]
0x18008e6ca  test    eax, eax
0x18008e6cc  jnz     short loc_18008E714
0x18008e6ce  call    cs:__imp_GetLastError
0x18008e6d5  nop     dword ptr [rax+rax+00h]
0x18008e6da  mov     ebx, eax
0x18008e6dc  mov     rax, cs:WPP_GLOBAL_Control
0x18008e6e3  lea     rcx, WPP_GLOBAL_Control
0x18008e6ea  cmp     rax, rcx
0x18008e6ed  jz      short loc_18008E70D
0x18008e6ef  test    byte ptr [rax+1Ch], 10h
0x18008e6f3  jz      short loc_18008E70D
0x18008e6f5  mov     rcx, [rax+10h]
0x18008e6f9  lea     r8, WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids
0x18008e700  mov     edx, 10h
0x18008e705  mov     r9d, ebx
0x18008e708  call    WPP_SF_D
0x18008e70d  mov     esi, ebx
0x18008e70f  jmp     loc_18008E7F5
0x18008e714  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18008e719  mov     rcx, rsi; lpFileName
0x18008e71c  call    cs:__imp_FindFirstFileA
0x18008e723  nop     dword ptr [rax+rax+00h]
0x18008e728  mov     rbp, rax
0x18008e72b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008e72f  jnz     short loc_18008E790
0x18008e731  call    cs:__imp_GetLastError
0x18008e738  nop     dword ptr [rax+rax+00h]
0x18008e73d  mov     ebx, eax
0x18008e73f  mov     rax, cs:WPP_GLOBAL_Control
0x18008e746  lea     rcx, WPP_GLOBAL_Control
0x18008e74d  cmp     rax, rcx
0x18008e750  jz      short loc_18008E70D
0x18008e752  test    byte ptr [rax+1Ch], 10h
0x18008e756  jz      short loc_18008E70D
0x18008e758  mov     rcx, [rax+10h]
0x18008e75c  lea     edx, [rbp+12h]
0x18008e75f  mov     r9, rsi
0x18008e762  mov     [rsp+2A8h+var_288], ebx
0x18008e766  lea     r8, WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids
0x18008e76d  call    WPP_SF_sd
0x18008e772  jmp     short loc_18008E70D
0x18008e774  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18008e779  mov     rcx, rbp; hFindFile
0x18008e77c  call    cs:__imp_FindNextFileA
0x18008e783  nop     dword ptr [rax+rax+00h]
0x18008e788  test    eax, eax
0x18008e78a  jz      loc_18008E83D
0x18008e790  lea     rcx, [rsp+2A8h+FindFileData.cFileName]; lpFileName
0x18008e795  call    cs:__imp_DeleteFileA
0x18008e79c  nop     dword ptr [rax+rax+00h]
0x18008e7a1  test    eax, eax
0x18008e7a3  jnz     short loc_18008E774
0x18008e7a5  call    cs:__imp_GetLastError
0x18008e7ac  nop     dword ptr [rax+rax+00h]
0x18008e7b1  mov     ebx, eax
0x18008e7b3  mov     rax, cs:WPP_GLOBAL_Control
0x18008e7ba  lea     rcx, WPP_GLOBAL_Control
0x18008e7c1  cmp     rax, rcx
0x18008e7c4  jz      short loc_18008E7E4
0x18008e7c6  test    byte ptr [rax+1Ch], 10h
0x18008e7ca  jz      short loc_18008E7E4
0x18008e7cc  mov     edx, 12h
0x18008e7d1  mov     rcx, [rax+10h]
0x18008e7d5  lea     r8, WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids
0x18008e7dc  mov     r9d, ebx
0x18008e7df  call    WPP_SF_D
0x18008e7e4  mov     rcx, rbp; hFindFile
0x18008e7e7  mov     esi, ebx
0x18008e7e9  call    cs:__imp_FindClose
0x18008e7f0  nop     dword ptr [rax+rax+00h]
0x18008e7f5  cmp     ebx, 12h
0x18008e7f8  mov     ecx, edi
0x18008e7fa  cmovnz  ecx, esi
0x18008e7fd  cmp     ecx, 2
0x18008e800  cmovnz  edi, ecx
0x18008e803  lea     rcx, [rsp+2A8h+Buffer]; lpPathName
0x18008e80b  call    cs:__imp_SetCurrentDirectoryA
0x18008e812  nop     dword ptr [rax+rax+00h]
0x18008e817  mov     eax, edi
0x18008e819  mov     rcx, [rsp+2A8h+var_28]
0x18008e821  xor     rcx, rsp; StackCookie
0x18008e824  call    __security_check_cookie
0x18008e829  mov     rbx, [rsp+2A8h+arg_10]
0x18008e831  add     rsp, 290h
0x18008e838  pop     rdi
0x18008e839  pop     rsi
0x18008e83a  pop     rbp
0x18008e83b  retn
0x18008e83d  call    cs:__imp_GetLastError
0x18008e844  nop     dword ptr [rax+rax+00h]
0x18008e849  mov     ebx, eax
0x18008e84b  cmp     eax, 12h
0x18008e84e  jz      short loc_18008E7E4
0x18008e850  mov     rax, cs:WPP_GLOBAL_Control
0x18008e857  lea     rcx, WPP_GLOBAL_Control
0x18008e85e  cmp     rax, rcx
0x18008e861  jz      short loc_18008E7E4
0x18008e863  test    byte ptr [rax+1Ch], 10h
0x18008e867  jz      loc_18008E7E4
0x18008e86d  mov     edx, 13h
0x18008e872  jmp     loc_18008E7D1
```
