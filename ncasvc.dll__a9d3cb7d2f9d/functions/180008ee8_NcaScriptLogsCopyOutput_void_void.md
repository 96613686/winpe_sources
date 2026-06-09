# NcaScriptLogsCopyOutput(void *,void *)

- ea: `0x180008ee8`
- end: `0x180009151`
- name: `?NcaScriptLogsCopyOutput@@YAKPEAX0@Z`
- size: `617`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800092f0`

## callees

- `0x180004f34`
- `0x180008ee8`
- `0x18001cc3e`
- `0x18001cc70`
- `0x18001cd00`

## import_xrefs

- `msvcrt!strchr` at `0x180008f92`
- `msvcrt!strchr` at `0x180008f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090e2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008f6a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008f6a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180009029`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180009029`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180008fc7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180008fc7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009001`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009001`

## pseudocode

```c
__int64 __fastcall NcaScriptLogsCopyOutput(void *a1, void *a2)
{
  DWORD v4; // ebx
  int v5; // esi
  char *v6; // rax
  int v7; // edi
  int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  DWORD LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-CCh] BYREF
  char Buffer[4112]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR WideCharStr[4096]; // [rsp+1050h] [rbp+F50h] BYREF

  v4 = 0;
  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  memset_0(Buffer, 0, 0x1001u);
  memset_0(WideCharStr, 0, sizeof(WideCharStr));
  v5 = 0;
  while ( 1 )
  {
    if ( !ReadFile(a2, Buffer, 0x1000u, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      v11 = 38;
      v4 = LastError;
      if ( LastError != 38 )
        return v4;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v10 = 54;
LABEL_26:
      WPP_SF_d(v9[2], v10, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, v11);
      return v4;
    }
    if ( !NumberOfBytesRead )
      return v4;
    v6 = strchr(Buffer, 30);
    if ( v6 )
    {
      v7 = (_DWORD)v6 - (unsigned int)Buffer;
      if ( !SetFilePointer(a2, v7 - NumberOfBytesRead + 1, 0, 1u) )
      {
        v4 = GetLastError();
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v4;
        v10 = 56;
        goto LABEL_15;
      }
      v5 = 1;
    }
    else
    {
      v7 = NumberOfBytesRead;
    }
    v8 = MultiByteToWideChar(1u, 0, Buffer, v7, WideCharStr, 4096);
    if ( !v8 )
    {
      v4 = GetLastError();
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v10 = 57;
LABEL_15:
      v11 = v4;
      goto LABEL_26;
    }
    if ( !WriteFile(a1, WideCharStr, 2 * v8, &NumberOfBytesWritten, 0) )
      break;
    if ( v5 )
      return v4;
  }
  v4 = GetLastError();
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 58;
    goto LABEL_15;
  }
  return v4;
}

```

## disassembly

```asm
0x180008ee8  mov     [rsp-8+arg_10], rbx
0x180008eed  push    rbp
0x180008eee  push    rsi
0x180008eef  push    rdi
0x180008ef0  push    r14
0x180008ef2  push    r15
0x180008ef4  lea     rbp, [rsp-2F60h]
0x180008efc  mov     eax, 3060h
0x180008f01  call    _alloca_probe
0x180008f06  sub     rsp, rax
0x180008f09  mov     rax, cs:__security_cookie
0x180008f10  xor     rax, rsp
0x180008f13  mov     [rbp+2F80h+var_30], rax
0x180008f1a  mov     r14, rdx
0x180008f1d  mov     r15, rcx
0x180008f20  xor     ebx, ebx
0x180008f22  lea     rcx, [rsp+3080h+Buffer]; void *
0x180008f27  xor     edx, edx; Val
0x180008f29  mov     [rsp+3080h+NumberOfBytesRead], ebx
0x180008f2d  mov     r8d, 1001h; Size
0x180008f33  mov     [rsp+3080h+NumberOfBytesWritten], ebx
0x180008f37  call    memset_0
0x180008f3c  xor     edx, edx; Val
0x180008f3e  lea     rcx, [rbp+2F80h+WideCharStr]; void *
0x180008f45  mov     r8d, 2000h; Size
0x180008f4b  call    memset_0
0x180008f50  xor     esi, esi
0x180008f52  lea     r9, [rsp+3080h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180008f57  mov     [rsp+3080h+lpOverlapped], rbx; lpOverlapped
0x180008f5c  mov     r8d, 1000h; nNumberOfBytesToRead
0x180008f62  lea     rdx, [rsp+3080h+Buffer]; lpBuffer
0x180008f67  mov     rcx, r14; hFile
0x180008f6a  call    cs:__imp_ReadFile
0x180008f71  nop     dword ptr [rax+rax+00h]
0x180008f76  test    eax, eax
0x180008f78  jz      loc_1800090E2
0x180008f7e  cmp     [rsp+3080h+NumberOfBytesRead], ebx
0x180008f82  jz      loc_180009128
0x180008f88  mov     edx, 1Eh; Val
0x180008f8d  lea     rcx, [rsp+3080h+Buffer]; Str
0x180008f92  call    cs:__imp_strchr
0x180008f99  nop     dword ptr [rax+rax+00h]
0x180008f9e  mov     rdi, rax
0x180008fa1  test    rax, rax
0x180008fa4  jnz     short loc_180008FAC
0x180008fa6  mov     edi, [rsp+3080h+NumberOfBytesRead]
0x180008faa  jmp     short loc_180008FE0
0x180008fac  lea     rax, [rsp+3080h+Buffer]
0x180008fb1  mov     r9d, 1; dwMoveMethod
0x180008fb7  sub     edi, eax
0x180008fb9  xor     r8d, r8d; lpDistanceToMoveHigh
0x180008fbc  mov     edx, edi
0x180008fbe  mov     rcx, r14; hFile
0x180008fc1  sub     edx, [rsp+3080h+NumberOfBytesRead]
0x180008fc5  inc     edx; lDistanceToMove
0x180008fc7  call    cs:__imp_SetFilePointer
0x180008fce  nop     dword ptr [rax+rax+00h]
0x180008fd3  test    eax, eax
0x180008fd5  jz      loc_1800090B4
0x180008fdb  mov     esi, 1
0x180008fe0  xor     edx, edx; dwFlags
0x180008fe2  mov     [rsp+3080h+cchWideChar], 1000h; cchWideChar
0x180008fea  lea     rax, [rbp+2F80h+WideCharStr]
0x180008ff1  mov     r9d, edi; cbMultiByte
0x180008ff4  lea     r8, [rsp+3080h+Buffer]; lpMultiByteStr
0x180008ff9  mov     [rsp+3080h+lpOverlapped], rax; lpWideCharStr
0x180008ffe  lea     ecx, [rdx+1]; CodePage
0x180009001  call    cs:__imp_MultiByteToWideChar
0x180009008  nop     dword ptr [rax+rax+00h]
0x18000900d  test    eax, eax
0x18000900f  jz      short loc_180009082
0x180009011  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x180009015  mov     [rsp+3080h+lpOverlapped], rbx; lpOverlapped
0x18000901a  lea     r9, [rsp+3080h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000901f  mov     rcx, r15; hFile
0x180009022  lea     rdx, [rbp+2F80h+WideCharStr]; lpBuffer
0x180009029  call    cs:__imp_WriteFile
0x180009030  nop     dword ptr [rax+rax+00h]
0x180009035  test    eax, eax
0x180009037  jz      short loc_180009046
0x180009039  test    esi, esi
0x18000903b  jz      loc_180008F52
0x180009041  jmp     loc_180009128
0x180009046  call    cs:__imp_GetLastError
0x18000904d  nop     dword ptr [rax+rax+00h]
0x180009052  mov     ebx, eax
0x180009054  mov     rcx, cs:WPP_GLOBAL_Control
0x18000905b  lea     rax, WPP_GLOBAL_Control
0x180009062  cmp     rcx, rax
0x180009065  jz      loc_180009128
0x18000906b  test    byte ptr [rcx+1Ch], 1
0x18000906f  jz      loc_180009128
0x180009075  mov     edx, 3Ah ; ':'
0x18000907a  mov     r9d, ebx
0x18000907d  jmp     loc_180009118
0x180009082  call    cs:__imp_GetLastError
0x180009089  nop     dword ptr [rax+rax+00h]
0x18000908e  mov     ebx, eax
0x180009090  mov     rcx, cs:WPP_GLOBAL_Control
0x180009097  lea     rax, WPP_GLOBAL_Control
0x18000909e  cmp     rcx, rax
0x1800090a1  jz      loc_180009128
0x1800090a7  test    byte ptr [rcx+1Ch], 1
0x1800090ab  jz      short loc_180009128
0x1800090ad  mov     edx, 39h ; '9'
0x1800090b2  jmp     short loc_18000907A
0x1800090b4  call    cs:__imp_GetLastError
0x1800090bb  nop     dword ptr [rax+rax+00h]
0x1800090c0  mov     ebx, eax
0x1800090c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090c9  lea     rax, WPP_GLOBAL_Control
0x1800090d0  cmp     rcx, rax
0x1800090d3  jz      short loc_180009128
0x1800090d5  test    byte ptr [rcx+1Ch], 1
0x1800090d9  jz      short loc_180009128
0x1800090db  mov     edx, 38h ; '8'
0x1800090e0  jmp     short loc_18000907A
0x1800090e2  call    cs:__imp_GetLastError
0x1800090e9  nop     dword ptr [rax+rax+00h]
0x1800090ee  mov     r9d, 26h ; '&'
0x1800090f4  mov     ebx, eax
0x1800090f6  cmp     eax, r9d
0x1800090f9  jnz     short loc_180009128
0x1800090fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009102  lea     rax, WPP_GLOBAL_Control
0x180009109  cmp     rcx, rax
0x18000910c  jz      short loc_180009128
0x18000910e  test    byte ptr [rcx+1Ch], 1
0x180009112  jz      short loc_180009128
0x180009114  lea     edx, [r9+10h]
0x180009118  mov     rcx, [rcx+10h]
0x18000911c  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x180009123  call    WPP_SF_d
0x180009128  mov     eax, ebx
0x18000912a  mov     rcx, [rbp+2F80h+var_30]
0x180009131  xor     rcx, rsp; StackCookie
0x180009134  call    __security_check_cookie
0x180009139  mov     rbx, [rsp+3080h+arg_10]
0x180009141  add     rsp, 3060h
0x180009148  pop     r15
0x18000914a  pop     r14
0x18000914c  pop     rdi
0x18000914d  pop     rsi
0x18000914e  pop     rbp
0x18000914f  retn
```
