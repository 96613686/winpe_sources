# LipsStringCopyWtoAAlloc

- ea: `0x18004ce40`
- end: `0x18004cfaa`
- name: `LipsStringCopyWtoAAlloc`
- size: `362`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, int cchWideChar, CHAR **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004cd7c`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000c4d0`
- `0x18000e510`
- `0x18004ce40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cf3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cf3a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004ce77`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004cf2e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004ce77`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004cf2e`

## string_xrefs

- `0x18004cf89`: `LipsStringCopyWtoAAlloc`

## pseudocode

```c
__int64 __fastcall LipsStringCopyWtoAAlloc(LPCWCH lpWideCharStr, int cchWideChar, CHAR **a3, int *a4)
{
  unsigned int v4; // ebx
  unsigned int v9; // eax
  SIZE_T cbMultiByte; // rsi
  DWORD LastError; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  CHAR *lpMultiByteStr; // rax
  CHAR *v16; // rdi
  int v17; // esi
  DWORD v18; // eax

  v4 = 0;
  v9 = WideCharToMultiByte(0, 0, lpWideCharStr, cchWideChar, 0, 0, 0, 0);
  cbMultiByte = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return (unsigned int)LipsReportError(v4, (int)"LipsStringCopyWtoAAlloc");
      v13 = 23;
      v14 = LastError;
      goto LABEL_10;
    }
  }
  lpMultiByteStr = (CHAR *)IpsecAllocMem(cbMultiByte);
  v16 = lpMultiByteStr;
  if ( !lpMultiByteStr )
  {
    v4 = 8;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return (unsigned int)LipsReportError(v4, (int)"LipsStringCopyWtoAAlloc");
    v13 = 24;
    v14 = 8;
LABEL_10:
    WPP_SF_d(v12[2], v13, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids, v14);
    return (unsigned int)LipsReportError(v4, (int)"LipsStringCopyWtoAAlloc");
  }
  v17 = WideCharToMultiByte(0, 0, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( !v17 )
  {
    v18 = GetLastError();
    v4 = v18;
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids, v18);
      goto LABEL_17;
    }
  }
  *a3 = v16;
  *a4 = v17;
  if ( v4 )
  {
LABEL_17:
    IpsecFreeMem(v16);
    return (unsigned int)LipsReportError(v4, (int)"LipsStringCopyWtoAAlloc");
  }
  return v4;
}

```

## disassembly

```asm
0x18004ce40  mov     rax, rsp
0x18004ce43  push    rbx
0x18004ce44  push    rbp
0x18004ce45  push    rsi
0x18004ce46  push    rdi
0x18004ce47  push    r12
0x18004ce49  push    r14
0x18004ce4b  push    r15
0x18004ce4d  sub     rsp, 40h
0x18004ce51  xor     ebx, ebx
0x18004ce53  mov     r14, r9
0x18004ce56  mov     [rax-40h], rbx
0x18004ce5a  mov     r15, r8
0x18004ce5d  mov     [rax-48h], rbx
0x18004ce61  mov     ebp, edx
0x18004ce63  mov     r12, rcx
0x18004ce66  mov     [rax-50h], ebx
0x18004ce69  mov     r9d, edx; cchWideChar
0x18004ce6c  mov     [rax-58h], rbx
0x18004ce70  mov     r8, rcx; lpWideCharStr
0x18004ce73  xor     edx, edx; dwFlags
0x18004ce75  xor     ecx, ecx; CodePage
0x18004ce77  call    cs:__imp_WideCharToMultiByte
0x18004ce7d  mov     esi, eax
0x18004ce7f  test    eax, eax
0x18004ce81  jnz     short loc_18004CEBA
0x18004ce83  call    cs:__imp_GetLastError
0x18004ce89  mov     ebx, eax
0x18004ce8b  test    eax, eax
0x18004ce8d  jz      short loc_18004CEBA
0x18004ce8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ce96  lea     rdx, WPP_GLOBAL_Control
0x18004ce9d  cmp     rcx, rdx
0x18004cea0  jz      loc_18004CF89
0x18004cea6  test    byte ptr [rcx+1Ch], 10h
0x18004ceaa  jz      loc_18004CF89
0x18004ceb0  mov     edx, 17h
0x18004ceb5  mov     r9d, eax
0x18004ceb8  jmp     short loc_18004CEF4
0x18004ceba  mov     rcx, rsi
0x18004cebd  call    IpsecAllocMem
0x18004cec2  mov     rdi, rax
0x18004cec5  test    rax, rax
0x18004cec8  jnz     short loc_18004CF09
0x18004ceca  lea     ebx, [rax+8]
0x18004cecd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ced4  lea     rdx, WPP_GLOBAL_Control
0x18004cedb  cmp     rcx, rdx
0x18004cede  jz      loc_18004CF89
0x18004cee4  test    byte ptr [rcx+1Ch], 10h
0x18004cee8  jz      loc_18004CF89
0x18004ceee  lea     edx, [rax+18h]
0x18004cef1  mov     r9d, ebx
0x18004cef4  mov     rcx, [rcx+10h]
0x18004cef8  lea     r8, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids
0x18004ceff  call    WPP_SF_d
0x18004cf04  jmp     loc_18004CF89
0x18004cf09  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18004cf12  mov     r9d, ebp; cchWideChar
0x18004cf15  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18004cf1e  mov     r8, r12; lpWideCharStr
0x18004cf21  mov     [rsp+78h+cbMultiByte], esi; cbMultiByte
0x18004cf25  xor     edx, edx; dwFlags
0x18004cf27  xor     ecx, ecx; CodePage
0x18004cf29  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x18004cf2e  call    cs:__imp_WideCharToMultiByte
0x18004cf34  mov     esi, eax
0x18004cf36  test    eax, eax
0x18004cf38  jnz     short loc_18004CF77
0x18004cf3a  call    cs:__imp_GetLastError
0x18004cf40  mov     ebx, eax
0x18004cf42  test    eax, eax
0x18004cf44  jz      short loc_18004CF77
0x18004cf46  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cf4d  lea     rdx, WPP_GLOBAL_Control
0x18004cf54  cmp     rcx, rdx
0x18004cf57  jz      short loc_18004CF81
0x18004cf59  test    byte ptr [rcx+1Ch], 10h
0x18004cf5d  jz      short loc_18004CF81
0x18004cf5f  mov     rcx, [rcx+10h]
0x18004cf63  lea     edx, [rsi+19h]
0x18004cf66  mov     r9d, eax
0x18004cf69  lea     r8, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids
0x18004cf70  call    WPP_SF_d
0x18004cf75  jmp     short loc_18004CF81
0x18004cf77  mov     [r15], rdi
0x18004cf7a  mov     [r14], esi
0x18004cf7d  test    ebx, ebx
0x18004cf7f  jz      short loc_18004CF99
0x18004cf81  mov     rcx, rdi; lpMem
0x18004cf84  call    IpsecFreeMem
0x18004cf89  lea     rdx, aLipsstringcopy; "LipsStringCopyWtoAAlloc"
0x18004cf90  mov     ecx, ebx
0x18004cf92  call    LipsReportError
0x18004cf97  mov     ebx, eax
0x18004cf99  mov     eax, ebx
0x18004cf9b  add     rsp, 40h
0x18004cf9f  pop     r15
0x18004cfa1  pop     r14
0x18004cfa3  pop     r12
0x18004cfa5  pop     rdi
0x18004cfa6  pop     rsi
0x18004cfa7  pop     rbp
0x18004cfa8  pop     rbx
0x18004cfa9  retn
```
