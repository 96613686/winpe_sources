# DhcpDeleteFiles

- ea: `0x18008e74c`
- end: `0x18008e9c3`
- name: `DhcpDeleteFiles`
- size: `631`
- prototype: `__int64 __fastcall(LPCSTR lpPathName, LPCSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000d644`
- `0x18000eb90`

## callees

- `0x18000282c`
- `0x180010e3c`
- `0x18008e74c`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `KERNEL32!FindNextFileA` at `0x18008e8ca`
- `KERNEL32!FindNextFileA` at `0x18008e8ca`
- `KERNEL32!DeleteFileA` at `0x18008e8e3`
- `KERNEL32!DeleteFileA` at `0x18008e8e3`
- `KERNEL32!FindFirstFileA` at `0x18008e862`
- `KERNEL32!FindFirstFileA` at `0x18008e862`
- `KERNEL32!SetCurrentDirectoryA` at `0x18008e7fe`
- `KERNEL32!SetCurrentDirectoryA` at `0x18008e957`
- `KERNEL32!SetCurrentDirectoryA` at `0x18008e7fe`
- `KERNEL32!SetCurrentDirectoryA` at `0x18008e957`
- `KERNEL32!GetCurrentDirectoryA` at `0x18008e7a4`
- `KERNEL32!GetCurrentDirectoryA` at `0x18008e7a4`
- `KERNEL32!GetLastError` at `0x18008e7b6`
- `KERNEL32!GetLastError` at `0x18008e80e`
- `KERNEL32!GetLastError` at `0x18008e877`
- `KERNEL32!GetLastError` at `0x18008e8f3`
- `KERNEL32!GetLastError` at `0x18008e989`
- `KERNEL32!GetLastError` at `0x18008e7b6`
- `KERNEL32!GetLastError` at `0x18008e80e`
- `KERNEL32!GetLastError` at `0x18008e877`
- `KERNEL32!GetLastError` at `0x18008e8f3`
- `KERNEL32!GetLastError` at `0x18008e989`
- `KERNEL32!FindClose` at `0x18008e935`
- `KERNEL32!FindClose` at `0x18008e935`

## pseudocode

```c
__int64 __fastcall DhcpDeleteFiles(LPCSTR lpPathName, LPCSTR lpFileName)
{
  DWORD v4; // edi
  DWORD v5; // eax
  DWORD v6; // ebx
  DWORD LastError; // ebx
  HANDLE FirstFileA; // rsi
  _QWORD *v10; // rax
  __int64 v11; // rdx
  DWORD v12; // ecx
  _WIN32_FIND_DATAA FindFileData; // [rsp+30h] [rbp-278h] BYREF
  CHAR Buffer[272]; // [rsp+170h] [rbp-138h] BYREF

  memset_0(Buffer, 0, 0x104u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = 0;
  if ( GetCurrentDirectoryA(0x104u, Buffer) )
  {
    if ( SetCurrentDirectoryA(lpPathName) )
    {
      FirstFileA = FindFirstFileA(lpFileName, &FindFileData);
      if ( FirstFileA == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            (unsigned int)&WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids,
            (_DWORD)lpFileName,
            LastError);
      }
      else
      {
        do
        {
          if ( !DeleteFileA(FindFileData.cFileName) )
          {
            LastError = GetLastError();
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v11 = 18;
LABEL_19:
              WPP_SF_D(v10[2], v11, &WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids, LastError);
              goto LABEL_20;
            }
            goto LABEL_20;
          }
        }
        while ( FindNextFileA(FirstFileA, &FindFileData) );
        LastError = GetLastError();
        if ( LastError != 18 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v11 = 19;
            goto LABEL_19;
          }
        }
LABEL_20:
        FindClose(FirstFileA);
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids, LastError);
    }
    v12 = 0;
    if ( LastError != 18 )
      v12 = LastError;
    if ( v12 != 2 )
      v4 = v12;
    SetCurrentDirectoryA(Buffer);
    return v4;
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids, v5);
    return v6;
  }
}

```

## disassembly

```asm
0x18008e74c  mov     [rsp+arg_10], rbx
0x18008e751  push    rbp
0x18008e752  push    rsi
0x18008e753  push    rdi
0x18008e754  sub     rsp, 290h
0x18008e75b  mov     rax, cs:__security_cookie
0x18008e762  xor     rax, rsp
0x18008e765  mov     [rsp+2A8h+var_28], rax
0x18008e76d  mov     rbp, rdx
0x18008e770  mov     rbx, rcx
0x18008e773  mov     edi, 104h
0x18008e778  lea     rcx, [rsp+2A8h+Buffer]; void *
0x18008e780  mov     r8d, edi; Size
0x18008e783  xor     edx, edx; Val
0x18008e785  call    memset_0
0x18008e78a  xor     edx, edx; Val
0x18008e78c  lea     r8d, [rdi+3Ch]; Size
0x18008e790  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x18008e795  call    memset_0
0x18008e79a  lea     rdx, [rsp+2A8h+Buffer]; lpBuffer
0x18008e7a2  mov     ecx, edi; nBufferLength
0x18008e7a4  call    cs:__imp_GetCurrentDirectoryA
0x18008e7ab  nop     dword ptr [rax+rax+00h]
0x18008e7b0  xor     edi, edi
0x18008e7b2  test    eax, eax
0x18008e7b4  jnz     short loc_18008E7FB
0x18008e7b6  call    cs:__imp_GetLastError
0x18008e7bd  nop     dword ptr [rax+rax+00h]
0x18008e7c2  mov     ebx, eax
0x18008e7c4  mov     r10, cs:WPP_GLOBAL_Control
0x18008e7cb  lea     rcx, WPP_GLOBAL_Control
0x18008e7d2  cmp     r10, rcx
0x18008e7d5  jz      short loc_18008E7F4
0x18008e7d7  test    byte ptr [r10+1Ch], 10h
0x18008e7dc  jz      short loc_18008E7F4
0x18008e7de  mov     rcx, [r10+10h]
0x18008e7e2  lea     edx, [rdi+0Fh]
0x18008e7e5  mov     r9d, eax
0x18008e7e8  lea     r8, WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids
0x18008e7ef  call    WPP_SF_D
0x18008e7f4  mov     eax, ebx
0x18008e7f6  jmp     loc_18008E965
0x18008e7fb  mov     rcx, rbx; lpPathName
0x18008e7fe  call    cs:__imp_SetCurrentDirectoryA
0x18008e805  nop     dword ptr [rax+rax+00h]
0x18008e80a  test    eax, eax
0x18008e80c  jnz     short loc_18008E85A
0x18008e80e  call    cs:__imp_GetLastError
0x18008e815  nop     dword ptr [rax+rax+00h]
0x18008e81a  mov     ebx, eax
0x18008e81c  mov     rax, cs:WPP_GLOBAL_Control
0x18008e823  lea     rcx, WPP_GLOBAL_Control
0x18008e82a  cmp     rax, rcx
0x18008e82d  jz      loc_18008E941
0x18008e833  test    byte ptr [rax+1Ch], 10h
0x18008e837  jz      loc_18008E941
0x18008e83d  mov     rcx, [rax+10h]
0x18008e841  lea     r8, WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids
0x18008e848  mov     edx, 10h
0x18008e84d  mov     r9d, ebx
0x18008e850  call    WPP_SF_D
0x18008e855  jmp     loc_18008E941
0x18008e85a  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18008e85f  mov     rcx, rbp; lpFileName
0x18008e862  call    cs:__imp_FindFirstFileA
0x18008e869  nop     dword ptr [rax+rax+00h]
0x18008e86e  mov     rsi, rax
0x18008e871  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008e875  jnz     short loc_18008E8DE
0x18008e877  call    cs:__imp_GetLastError
0x18008e87e  nop     dword ptr [rax+rax+00h]
0x18008e883  mov     ebx, eax
0x18008e885  mov     rax, cs:WPP_GLOBAL_Control
0x18008e88c  lea     rcx, WPP_GLOBAL_Control
0x18008e893  cmp     rax, rcx
0x18008e896  jz      loc_18008E941
0x18008e89c  test    byte ptr [rax+1Ch], 10h
0x18008e8a0  jz      loc_18008E941
0x18008e8a6  mov     rcx, [rax+10h]
0x18008e8aa  lea     edx, [rsi+12h]
0x18008e8ad  mov     r9, rbp
0x18008e8b0  mov     [rsp+2A8h+var_288], ebx
0x18008e8b4  lea     r8, WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids
0x18008e8bb  call    WPP_SF_sd
0x18008e8c0  jmp     short loc_18008E941
0x18008e8c2  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18008e8c7  mov     rcx, rsi; hFindFile
0x18008e8ca  call    cs:__imp_FindNextFileA
0x18008e8d1  nop     dword ptr [rax+rax+00h]
0x18008e8d6  test    eax, eax
0x18008e8d8  jz      loc_18008E989
0x18008e8de  lea     rcx, [rsp+2A8h+FindFileData.cFileName]; lpFileName
0x18008e8e3  call    cs:__imp_DeleteFileA
0x18008e8ea  nop     dword ptr [rax+rax+00h]
0x18008e8ef  test    eax, eax
0x18008e8f1  jnz     short loc_18008E8C2
0x18008e8f3  call    cs:__imp_GetLastError
0x18008e8fa  nop     dword ptr [rax+rax+00h]
0x18008e8ff  mov     ebx, eax
0x18008e901  mov     rax, cs:WPP_GLOBAL_Control
0x18008e908  lea     rcx, WPP_GLOBAL_Control
0x18008e90f  cmp     rax, rcx
0x18008e912  jz      short loc_18008E932
0x18008e914  test    byte ptr [rax+1Ch], 10h
0x18008e918  jz      short loc_18008E932
0x18008e91a  mov     edx, 12h
0x18008e91f  mov     rcx, [rax+10h]
0x18008e923  lea     r8, WPP_364920719fff3c9afc48baa9c9bb6408_Traceguids
0x18008e92a  mov     r9d, ebx
0x18008e92d  call    WPP_SF_D
0x18008e932  mov     rcx, rsi; hFindFile
0x18008e935  call    cs:__imp_FindClose
0x18008e93c  nop     dword ptr [rax+rax+00h]
0x18008e941  cmp     ebx, 12h
0x18008e944  mov     ecx, edi
0x18008e946  cmovnz  ecx, ebx
0x18008e949  cmp     ecx, 2
0x18008e94c  cmovnz  edi, ecx
0x18008e94f  lea     rcx, [rsp+2A8h+Buffer]; lpPathName
0x18008e957  call    cs:__imp_SetCurrentDirectoryA
0x18008e95e  nop     dword ptr [rax+rax+00h]
0x18008e963  mov     eax, edi
0x18008e965  mov     rcx, [rsp+2A8h+var_28]
0x18008e96d  xor     rcx, rsp; StackCookie
0x18008e970  call    __security_check_cookie
0x18008e975  mov     rbx, [rsp+2A8h+arg_10]
0x18008e97d  add     rsp, 290h
0x18008e984  pop     rdi
0x18008e985  pop     rsi
0x18008e986  pop     rbp
0x18008e987  retn
0x18008e989  call    cs:__imp_GetLastError
0x18008e990  nop     dword ptr [rax+rax+00h]
0x18008e995  mov     ebx, eax
0x18008e997  cmp     eax, 12h
0x18008e99a  jz      short loc_18008E932
0x18008e99c  mov     rax, cs:WPP_GLOBAL_Control
0x18008e9a3  lea     rcx, WPP_GLOBAL_Control
0x18008e9aa  cmp     rax, rcx
0x18008e9ad  jz      short loc_18008E932
0x18008e9af  test    byte ptr [rax+1Ch], 10h
0x18008e9b3  jz      loc_18008E932
0x18008e9b9  mov     edx, 13h
0x18008e9be  jmp     loc_18008E91F
```
