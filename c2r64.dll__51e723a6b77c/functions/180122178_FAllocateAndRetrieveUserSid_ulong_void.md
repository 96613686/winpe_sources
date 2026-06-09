# FAllocateAndRetrieveUserSid(ulong,void * *)

- ea: `0x180122178`
- end: `0x1801223bd`
- name: `?FAllocateAndRetrieveUserSid@@YAHKPEAPEAX@Z`
- size: `581`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004198`
- `0x1801229d0`
- `0x180122f4c`

## callees

- `0x1800264b4`
- `0x18003e690`
- `0x180122178`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18012222b`
- `KERNEL32!GetCurrentProcess` at `0x18012222b`
- `KERNEL32!GetLastError` at `0x180122211`
- `KERNEL32!GetLastError` at `0x180122266`
- `KERNEL32!GetLastError` at `0x1801222de`
- `KERNEL32!GetLastError` at `0x180122330`
- `KERNEL32!GetLastError` at `0x180122353`
- `KERNEL32!GetLastError` at `0x180122211`
- `KERNEL32!GetLastError` at `0x180122266`
- `KERNEL32!GetLastError` at `0x1801222de`
- `KERNEL32!GetLastError` at `0x180122330`
- `KERNEL32!GetLastError` at `0x180122353`
- `KERNEL32!CloseHandle` at `0x18012238b`
- `KERNEL32!CloseHandle` at `0x18012238b`
- `KERNEL32!GlobalFree` at `0x18012236d`
- `KERNEL32!GlobalFree` at `0x18012236d`
- `KERNEL32!GlobalAlloc` at `0x18012228f`
- `KERNEL32!GlobalAlloc` at `0x180122305`
- `KERNEL32!GlobalAlloc` at `0x18012228f`
- `KERNEL32!GlobalAlloc` at `0x180122305`
- `KERNEL32!GetCurrentThread` at `0x1801221f1`
- `KERNEL32!GetCurrentThread` at `0x1801221f1`
- `ADVAPI32!OpenProcessToken` at `0x18012223e`
- `ADVAPI32!OpenProcessToken` at `0x18012223e`
- `ADVAPI32!GetTokenInformation` at `0x180122260`
- `ADVAPI32!GetTokenInformation` at `0x1801222ce`
- `ADVAPI32!GetTokenInformation` at `0x180122260`
- `ADVAPI32!GetTokenInformation` at `0x1801222ce`
- `ADVAPI32!IsValidSid` at `0x180122349`
- `ADVAPI32!IsValidSid` at `0x180122349`
- `ADVAPI32!OpenThreadToken` at `0x180122207`
- `ADVAPI32!OpenThreadToken` at `0x180122207`
- `ADVAPI32!GetLengthSid` at `0x1801222f7`
- `ADVAPI32!GetLengthSid` at `0x1801222f7`
- `ADVAPI32!CopySid` at `0x180122326`
- `ADVAPI32!CopySid` at `0x180122326`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall FAllocateAndRetrieveUserSid(int a1, void **a2)
{
  PSID *v4; // rdi
  char v5; // si
  signed int v6; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD v9; // r9d
  PSID *p_TokenInformation; // rsi
  signed int LastError; // eax
  HGLOBAL v12; // rax
  signed int v13; // eax
  signed int v14; // eax
  BOOL v15; // ebx
  HANDLE v16; // rcx
  DWORD TokenInformationLength[2]; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C8h] BYREF
  char TokenInformation; // [rsp+48h] [rbp-C0h] BYREF

  if ( !a2 )
    return 0;
  TokenHandle = 0;
  TokenInformationLength[0] = 0;
  v4 = 0;
  v5 = 0;
  *a2 = 0;
  if ( a1 == 1 )
    goto LABEL_11;
  if ( a1 != 2 )
  {
    MsoShipAssertTagProc(1339788);
    goto LABEL_6;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      goto LABEL_6;
    v5 = 1;
  }
  if ( v5 )
  {
LABEL_11:
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_6;
  }
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, TokenInformationLength);
  if ( GetLastError() == 122 )
  {
    v9 = TokenInformationLength[0];
    if ( TokenInformationLength[0] >= 0x100 )
    {
      v4 = (PSID *)GlobalAlloc(0, TokenInformationLength[0]);
      p_TokenInformation = v4;
      MsoShipAssertTagProc(1339792);
      if ( !v4 )
      {
        v6 = -2147024882;
        goto LABEL_33;
      }
      v9 = TokenInformationLength[0];
    }
    else
    {
      p_TokenInformation = (PSID *)&TokenInformation;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, p_TokenInformation, v9, TokenInformationLength) )
      goto LABEL_22;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( !v6 )
    {
LABEL_22:
      TokenInformationLength[0] = GetLengthSid(*p_TokenInformation);
      v12 = GlobalAlloc(0, TokenInformationLength[0]);
      *a2 = v12;
      if ( v12 )
      {
        v6 = 0;
        if ( CopySid(TokenInformationLength[0], v12, *p_TokenInformation) )
          goto LABEL_38;
        v13 = GetLastError();
        v6 = v13;
        if ( v13 > 0 )
          v6 = (unsigned __int16)v13 | 0x80070000;
        if ( !v6 )
        {
LABEL_38:
          if ( !IsValidSid(*a2) )
          {
            v14 = GetLastError();
            v6 = v14;
            if ( v14 > 0 )
              v6 = (unsigned __int16)v14 | 0x80070000;
          }
        }
      }
      else
      {
        v6 = -2147024882;
      }
    }
    if ( v4 )
      GlobalFree(v4);
    goto LABEL_33;
  }
LABEL_6:
  v6 = -2147467259;
LABEL_33:
  v15 = v6 >= 0;
  v16 = TokenHandle;
  if ( TokenHandle )
  {
    TokenHandle = 0;
    CloseHandle(v16);
  }
  return v15;
}

```

## disassembly

```asm
0x180122178  mov     rax, rsp
0x18012217b  mov     [rax+8], rbx
0x18012217f  mov     [rax+18h], rsi
0x180122183  mov     [rax+20h], rdi
0x180122187  push    rbp
0x180122188  push    r12
0x18012218a  push    r14
0x18012218c  lea     rbp, [rax-68h]
0x180122190  sub     rsp, 150h
0x180122197  mov     rax, cs:__security_cookie
0x18012219e  xor     rax, rsp
0x1801221a1  mov     [rbp+60h+var_20], rax
0x1801221a5  mov     r14, rdx
0x1801221a8  mov     ebx, ecx
0x1801221aa  test    rdx, rdx
0x1801221ad  jnz     short loc_1801221B6
0x1801221af  xor     eax, eax
0x1801221b1  jmp     loc_180122394
0x1801221b6  mov     [rsp+160h+TokenHandle], 0
0x1801221bf  mov     [rsp+160h+TokenInformationLength], 0
0x1801221c7  xor     edi, edi
0x1801221c9  xor     sil, sil
0x1801221cc  mov     [rdx], rdi
0x1801221cf  lea     r12d, [rdi+1]
0x1801221d3  cmp     ebx, r12d
0x1801221d6  jz      short loc_18012222B
0x1801221d8  cmp     ebx, 2
0x1801221db  jz      short loc_1801221F1
0x1801221dd  mov     ecx, 14718Ch
0x1801221e2  call    MsoShipAssertTagProc
0x1801221e7  mov     ebx, 80004005h
0x1801221ec  jmp     loc_180122373
0x1801221f1  call    cs:__imp_GetCurrentThread
0x1801221f7  lea     r9, [rsp+160h+TokenHandle]; TokenHandle
0x1801221fc  mov     r8d, r12d; OpenAsSelf
0x1801221ff  mov     edx, 8; DesiredAccess
0x180122204  mov     rcx, rax; ThreadHandle
0x180122207  call    cs:__imp_OpenThreadToken
0x18012220d  test    eax, eax
0x18012220f  jnz     short loc_180122221
0x180122211  call    cs:__imp_GetLastError
0x180122217  cmp     eax, 3F0h
0x18012221c  jnz     short loc_1801221E7
0x18012221e  mov     sil, r12b
0x180122221  cmp     ebx, r12d
0x180122224  jz      short loc_18012222B
0x180122226  test    sil, sil
0x180122229  jz      short loc_180122248
0x18012222b  call    cs:__imp_GetCurrentProcess
0x180122231  lea     r8, [rsp+160h+TokenHandle]; TokenHandle
0x180122236  mov     edx, 8; DesiredAccess
0x18012223b  mov     rcx, rax; ProcessHandle
0x18012223e  call    cs:__imp_OpenProcessToken
0x180122244  test    eax, eax
0x180122246  jz      short loc_1801221E7
0x180122248  lea     rax, [rsp+160h+TokenInformationLength]
0x18012224d  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180122252  xor     r9d, r9d; TokenInformationLength
0x180122255  xor     r8d, r8d; TokenInformation
0x180122258  mov     edx, r12d; TokenInformationClass
0x18012225b  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x180122260  call    cs:__imp_GetTokenInformation
0x180122266  call    cs:__imp_GetLastError
0x18012226c  cmp     eax, 7Ah ; 'z'
0x18012226f  jnz     loc_1801221E7
0x180122275  mov     r9d, [rsp+160h+TokenInformationLength]
0x18012227a  cmp     r9d, 100h
0x180122281  jnb     short loc_18012228A
0x180122283  lea     rsi, [rsp+160h+TokenInformation]
0x180122288  jmp     short loc_1801222B9
0x18012228a  mov     rdx, r9; dwBytes
0x18012228d  xor     ecx, ecx; uFlags
0x18012228f  call    cs:__imp_GlobalAlloc
0x180122295  mov     rdi, rax
0x180122298  mov     rsi, rax
0x18012229b  mov     ecx, 147190h
0x1801222a0  call    MsoShipAssertTagProc
0x1801222a5  test    rsi, rsi
0x1801222a8  jnz     short loc_1801222B4
0x1801222aa  mov     ebx, 8007000Eh
0x1801222af  jmp     loc_180122373
0x1801222b4  mov     r9d, [rsp+160h+TokenInformationLength]; TokenInformationLength
0x1801222b9  lea     rax, [rsp+160h+TokenInformationLength]
0x1801222be  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x1801222c3  mov     r8, rsi; TokenInformation
0x1801222c6  mov     edx, r12d; TokenInformationClass
0x1801222c9  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x1801222ce  call    cs:__imp_GetTokenInformation
0x1801222d4  mov     r12d, 80070000h
0x1801222da  test    eax, eax
0x1801222dc  jnz     short loc_1801222F4
0x1801222de  call    cs:__imp_GetLastError
0x1801222e4  mov     ebx, eax
0x1801222e6  test    eax, eax
0x1801222e8  jle     short loc_1801222F0
0x1801222ea  movzx   ebx, ax
0x1801222ed  or      ebx, r12d
0x1801222f0  test    ebx, ebx
0x1801222f2  jnz     short loc_180122365
0x1801222f4  mov     rcx, [rsi]; pSid
0x1801222f7  call    cs:__imp_GetLengthSid
0x1801222fd  mov     edx, eax; dwBytes
0x1801222ff  mov     [rsp+160h+TokenInformationLength], edx
0x180122303  xor     ecx, ecx; uFlags
0x180122305  call    cs:__imp_GlobalAlloc
0x18012230b  mov     [r14], rax
0x18012230e  test    rax, rax
0x180122311  jnz     short loc_18012231A
0x180122313  mov     ebx, 8007000Eh
0x180122318  jmp     short loc_180122365
0x18012231a  xor     ebx, ebx
0x18012231c  mov     r8, [rsi]; pSourceSid
0x18012231f  mov     rdx, rax; pDestinationSid
0x180122322  mov     ecx, [rsp+160h+TokenInformationLength]; nDestinationSidLength
0x180122326  call    cs:__imp_CopySid
0x18012232c  test    eax, eax
0x18012232e  jnz     short loc_180122346
0x180122330  call    cs:__imp_GetLastError
0x180122336  mov     ebx, eax
0x180122338  test    eax, eax
0x18012233a  jle     short loc_180122342
0x18012233c  movzx   ebx, ax
0x18012233f  or      ebx, r12d
0x180122342  test    ebx, ebx
0x180122344  jnz     short loc_180122365
0x180122346  mov     rcx, [r14]; pSid
0x180122349  call    cs:__imp_IsValidSid
0x18012234f  test    eax, eax
0x180122351  jnz     short loc_180122365
0x180122353  call    cs:__imp_GetLastError
0x180122359  mov     ebx, eax
0x18012235b  test    eax, eax
0x18012235d  jle     short loc_180122365
0x18012235f  movzx   ebx, ax
0x180122362  or      ebx, r12d
0x180122365  test    rdi, rdi
0x180122368  jz      short loc_180122373
0x18012236a  mov     rcx, rdi; hMem
0x18012236d  call    cs:__imp_GlobalFree
0x180122373  not     ebx
0x180122375  shr     ebx, 1Fh
0x180122378  mov     rcx, [rsp+160h+TokenHandle]; hObject
0x18012237d  test    rcx, rcx
0x180122380  jz      short loc_180122392
0x180122382  mov     [rsp+160h+TokenHandle], 0
0x18012238b  call    cs:__imp_CloseHandle
0x180122391  nop
0x180122392  mov     eax, ebx
0x180122394  mov     rcx, [rbp+60h+var_20]
0x180122398  xor     rcx, rsp; StackCookie
0x18012239b  call    __security_check_cookie
0x1801223a0  lea     r11, [rsp+160h+var_10]
0x1801223a8  mov     rbx, [r11+20h]
0x1801223ac  mov     rsi, [r11+30h]
0x1801223b0  mov     rdi, [r11+38h]
0x1801223b4  mov     rsp, r11
0x1801223b7  pop     r14
0x1801223b9  pop     r12
0x1801223bb  pop     rbp
0x1801223bc  retn
```
