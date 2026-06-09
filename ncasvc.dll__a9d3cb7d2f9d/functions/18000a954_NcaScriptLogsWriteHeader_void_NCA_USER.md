# NcaScriptLogsWriteHeader(void *,NCA_USER_ *)

- ea: `0x18000a954`
- end: `0x18000ad11`
- name: `?NcaScriptLogsWriteHeader@@YAKPEAXPEAUNCA_USER_@@@Z`
- size: `957`
- prototype: `__int64 __fastcall(void *, struct NCA_USER_ *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000ae34`

## callees

- `0x180004f34`
- `0x180009714`
- `0x180009998`
- `0x18000a954`
- `0x18000ad68`
- `0x18001cc3e`
- `0x18001cc70`
- `0x18001cd00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aca9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a9cb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000aa3b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000aae1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ab8c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ac39`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ac99`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a9cb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000aa3b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000aae1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ab8c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ac39`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ac99`

## pseudocode

```c
__int64 __fastcall NcaScriptLogsWriteHeader(void *a1, struct NCA_USER_ *a2)
{
  DWORD UserStatus; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // r8
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // ecx
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-CCh] BYREF
  __int16 Buffer; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v16[4096]; // [rsp+40h] [rbp-C0h] BYREF

  v13 = 0;
  NumberOfBytesWritten = 0;
  memset_0(v16, 0, sizeof(v16));
  Buffer = -257;
  if ( WriteFile(a1, &Buffer, 2u, &NumberOfBytesWritten, 0) )
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)wszNcaScriptLogHtmlHeader + v8) );
    if ( WriteFile(a1, wszNcaScriptLogHtmlHeader, 2 * v8, &NumberOfBytesWritten, 0) )
    {
      UserStatus = NcaScriptLogsGetUserStatus(a2, v9, v16, &v13);
      if ( UserStatus )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 29;
          goto LABEL_41;
        }
      }
      else if ( WriteFile(a1, v16, 2 * v13, &NumberOfBytesWritten, 0) )
      {
        v13 = 0;
        UserStatus = NcaScriptsLogsGetProbesStatus(a2, v10, v16, &v13);
        if ( UserStatus )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 31;
            goto LABEL_41;
          }
        }
        else if ( WriteFile(a1, v16, 2 * v13, &NumberOfBytesWritten, 0) )
        {
          v13 = 0;
          UserStatus = NcaScriptLogsGetMultisiteStatus(v11, v16, &v13);
          if ( UserStatus )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 33;
              goto LABEL_41;
            }
          }
          else if ( !v13 || WriteFile(a1, v16, 2 * v13, &NumberOfBytesWritten, 0) )
          {
            do
              ++v7;
            while ( *((_WORD *)qword_180029618 + v7) );
            if ( !WriteFile(a1, qword_180029618, 2 * v7, &NumberOfBytesWritten, 0) )
            {
              UserStatus = GetLastError();
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v6 = 35;
                goto LABEL_41;
              }
            }
          }
          else
          {
            UserStatus = GetLastError();
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 34;
              goto LABEL_41;
            }
          }
        }
        else
        {
          UserStatus = GetLastError();
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 32;
            goto LABEL_41;
          }
        }
      }
      else
      {
        UserStatus = GetLastError();
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 30;
          goto LABEL_41;
        }
      }
    }
    else
    {
      UserStatus = GetLastError();
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 28;
        goto LABEL_41;
      }
    }
  }
  else
  {
    UserStatus = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 27;
LABEL_41:
      WPP_SF_d(v5[2], v6, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, UserStatus);
    }
  }
  return UserStatus;
}

```

## disassembly

```asm
0x18000a954  mov     [rsp-8+arg_10], rbx
0x18000a959  push    rbp
0x18000a95a  push    rsi
0x18000a95b  push    rdi
0x18000a95c  push    r14
0x18000a95e  push    r15
0x18000a960  lea     rbp, [rsp-1F50h]
0x18000a968  mov     eax, 2050h
0x18000a96d  call    _alloca_probe
0x18000a972  sub     rsp, rax
0x18000a975  mov     rax, cs:__security_cookie
0x18000a97c  xor     rax, rsp
0x18000a97f  mov     [rbp+1F70h+var_30], rax
0x18000a986  mov     r14, rdx
0x18000a989  mov     rsi, rcx
0x18000a98c  xor     r15d, r15d
0x18000a98f  lea     rcx, [rsp+2070h+var_2030]; void *
0x18000a994  xor     edx, edx; Val
0x18000a996  mov     [rsp+2070h+var_2040], r15d
0x18000a99b  mov     r8d, 2000h; Size
0x18000a9a1  mov     [rsp+2070h+NumberOfBytesWritten], r15d
0x18000a9a6  call    memset_0
0x18000a9ab  mov     eax, 0FEFFh
0x18000a9b0  mov     [rsp+2070h+lpOverlapped], r15; lpOverlapped
0x18000a9b5  lea     r9, [rsp+2070h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000a9ba  mov     [rsp+2070h+Buffer], ax
0x18000a9bf  lea     r8d, [r15+2]; nNumberOfBytesToWrite
0x18000a9c3  mov     rcx, rsi; hFile
0x18000a9c6  lea     rdx, [rsp+2070h+Buffer]; lpBuffer
0x18000a9cb  call    cs:__imp_WriteFile
0x18000a9d2  nop     dword ptr [rax+rax+00h]
0x18000a9d7  test    eax, eax
0x18000a9d9  jnz     short loc_18000AA13
0x18000a9db  call    cs:__imp_GetLastError
0x18000a9e2  nop     dword ptr [rax+rax+00h]
0x18000a9e7  mov     ebx, eax
0x18000a9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9f0  lea     rax, WPP_GLOBAL_Control
0x18000a9f7  cmp     rcx, rax
0x18000a9fa  jz      loc_18000ACE8
0x18000aa00  test    byte ptr [rcx+1Ch], 1
0x18000aa04  jz      loc_18000ACE8
0x18000aa0a  lea     edx, [r15+1Bh]
0x18000aa0e  jmp     loc_18000ACD5
0x18000aa13  mov     rdx, cs:?wszNcaScriptLogHtmlHeader@@3PAPEAGA; lpBuffer
0x18000aa1a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000aa1e  mov     r8, rdi
0x18000aa21  inc     r8
0x18000aa24  cmp     [rdx+r8*2], r15w
0x18000aa29  jnz     short loc_18000AA21
0x18000aa2b  add     r8d, r8d; nNumberOfBytesToWrite
0x18000aa2e  mov     [rsp+2070h+lpOverlapped], r15; lpOverlapped
0x18000aa33  lea     r9, [rsp+2070h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000aa38  mov     rcx, rsi; hFile
0x18000aa3b  call    cs:__imp_WriteFile
0x18000aa42  nop     dword ptr [rax+rax+00h]
0x18000aa47  test    eax, eax
0x18000aa49  jnz     short loc_18000AA84
0x18000aa4b  call    cs:__imp_GetLastError
0x18000aa52  nop     dword ptr [rax+rax+00h]
0x18000aa57  mov     ebx, eax
0x18000aa59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa60  lea     rax, WPP_GLOBAL_Control
0x18000aa67  cmp     rcx, rax
0x18000aa6a  jz      loc_18000ACE8
0x18000aa70  test    byte ptr [rcx+1Ch], 1
0x18000aa74  jz      loc_18000ACE8
0x18000aa7a  mov     edx, 1Ch
0x18000aa7f  jmp     loc_18000ACD5
0x18000aa84  lea     r9, [rsp+2070h+var_2040]; unsigned int *
0x18000aa89  mov     rcx, r14; struct NCA_USER_ *
0x18000aa8c  lea     r8, [rsp+2070h+var_2030]; unsigned __int16 *
0x18000aa91  call    ?NcaScriptLogsGetUserStatus@@YAKPEAUNCA_USER_@@KPEAGPEAK@Z; NcaScriptLogsGetUserStatus(NCA_USER_ *,ulong,ushort *,ulong *)
0x18000aa96  mov     ebx, eax
0x18000aa98  test    eax, eax
0x18000aa9a  jz      short loc_18000AAC7
0x18000aa9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaa3  lea     rax, WPP_GLOBAL_Control
0x18000aaaa  cmp     rcx, rax
0x18000aaad  jz      loc_18000ACE8
0x18000aab3  test    byte ptr [rcx+1Ch], 1
0x18000aab7  jz      loc_18000ACE8
0x18000aabd  mov     edx, 1Dh
0x18000aac2  jmp     loc_18000ACD5
0x18000aac7  mov     r8d, [rsp+2070h+var_2040]
0x18000aacc  lea     r9, [rsp+2070h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000aad1  add     r8d, r8d; nNumberOfBytesToWrite
0x18000aad4  mov     [rsp+2070h+lpOverlapped], r15; lpOverlapped
0x18000aad9  lea     rdx, [rsp+2070h+var_2030]; lpBuffer
0x18000aade  mov     rcx, rsi; hFile
0x18000aae1  call    cs:__imp_WriteFile
0x18000aae8  nop     dword ptr [rax+rax+00h]
0x18000aaed  test    eax, eax
0x18000aaef  jnz     short loc_18000AB2A
0x18000aaf1  call    cs:__imp_GetLastError
0x18000aaf8  nop     dword ptr [rax+rax+00h]
0x18000aafd  mov     ebx, eax
0x18000aaff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab06  lea     rax, WPP_GLOBAL_Control
0x18000ab0d  cmp     rcx, rax
0x18000ab10  jz      loc_18000ACE8
0x18000ab16  test    byte ptr [rcx+1Ch], 1
0x18000ab1a  jz      loc_18000ACE8
0x18000ab20  mov     edx, 1Eh
0x18000ab25  jmp     loc_18000ACD5
0x18000ab2a  lea     r9, [rsp+2070h+var_2040]; unsigned int *
0x18000ab2f  mov     [rsp+2070h+var_2040], r15d
0x18000ab34  lea     r8, [rsp+2070h+var_2030]; unsigned __int16 *
0x18000ab39  mov     rcx, r14; struct NCA_USER_ *
0x18000ab3c  call    ?NcaScriptsLogsGetProbesStatus@@YAKPEAUNCA_USER_@@KPEAGPEAK@Z; NcaScriptsLogsGetProbesStatus(NCA_USER_ *,ulong,ushort *,ulong *)
0x18000ab41  mov     ebx, eax
0x18000ab43  test    eax, eax
0x18000ab45  jz      short loc_18000AB72
0x18000ab47  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab4e  lea     rax, WPP_GLOBAL_Control
0x18000ab55  cmp     rcx, rax
0x18000ab58  jz      loc_18000ACE8
0x18000ab5e  test    byte ptr [rcx+1Ch], 1
0x18000ab62  jz      loc_18000ACE8
0x18000ab68  mov     edx, 1Fh
0x18000ab6d  jmp     loc_18000ACD5
0x18000ab72  mov     r8d, [rsp+2070h+var_2040]
0x18000ab77  lea     r9, [rsp+2070h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000ab7c  add     r8d, r8d; nNumberOfBytesToWrite
0x18000ab7f  mov     [rsp+2070h+lpOverlapped], r15; lpOverlapped
0x18000ab84  lea     rdx, [rsp+2070h+var_2030]; lpBuffer
0x18000ab89  mov     rcx, rsi; hFile
0x18000ab8c  call    cs:__imp_WriteFile
0x18000ab93  nop     dword ptr [rax+rax+00h]
0x18000ab98  test    eax, eax
0x18000ab9a  jnz     short loc_18000ABD5
0x18000ab9c  call    cs:__imp_GetLastError
0x18000aba3  nop     dword ptr [rax+rax+00h]
0x18000aba8  mov     ebx, eax
0x18000abaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abb1  lea     rax, WPP_GLOBAL_Control
0x18000abb8  cmp     rcx, rax
0x18000abbb  jz      loc_18000ACE8
0x18000abc1  test    byte ptr [rcx+1Ch], 1
0x18000abc5  jz      loc_18000ACE8
0x18000abcb  mov     edx, 20h ; ' '
0x18000abd0  jmp     loc_18000ACD5
0x18000abd5  lea     r8, [rsp+2070h+var_2040]; unsigned int *
0x18000abda  mov     [rsp+2070h+var_2040], r15d
0x18000abdf  lea     rdx, [rsp+2070h+var_2030]; unsigned __int16 *
0x18000abe4  call    ?NcaScriptLogsGetMultisiteStatus@@YAKKPEAGPEAK@Z; NcaScriptLogsGetMultisiteStatus(ulong,ushort *,ulong *)
0x18000abe9  mov     ebx, eax
0x18000abeb  test    eax, eax
0x18000abed  jz      short loc_18000AC1A
0x18000abef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abf6  lea     rax, WPP_GLOBAL_Control
0x18000abfd  cmp     rcx, rax
0x18000ac00  jz      loc_18000ACE8
0x18000ac06  test    byte ptr [rcx+1Ch], 1
0x18000ac0a  jz      loc_18000ACE8
0x18000ac10  mov     edx, 21h ; '!'
0x18000ac15  jmp     loc_18000ACD5
0x18000ac1a  mov     r8d, [rsp+2070h+var_2040]
0x18000ac1f  test    r8d, r8d
0x18000ac22  jz      short loc_18000AC77
0x18000ac24  add     r8d, r8d; nNumberOfBytesToWrite
0x18000ac27  mov     [rsp+2070h+lpOverlapped], r15; lpOverlapped
0x18000ac2c  lea     r9, [rsp+2070h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000ac31  mov     rcx, rsi; hFile
0x18000ac34  lea     rdx, [rsp+2070h+var_2030]; lpBuffer
0x18000ac39  call    cs:__imp_WriteFile
0x18000ac40  nop     dword ptr [rax+rax+00h]
0x18000ac45  test    eax, eax
0x18000ac47  jnz     short loc_18000AC77
0x18000ac49  call    cs:__imp_GetLastError
0x18000ac50  nop     dword ptr [rax+rax+00h]
0x18000ac55  mov     ebx, eax
0x18000ac57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac5e  lea     rax, WPP_GLOBAL_Control
0x18000ac65  cmp     rcx, rax
0x18000ac68  jz      short loc_18000ACE8
0x18000ac6a  test    byte ptr [rcx+1Ch], 1
0x18000ac6e  jz      short loc_18000ACE8
0x18000ac70  mov     edx, 22h ; '"'
0x18000ac75  jmp     short loc_18000ACD5
0x18000ac77  mov     rdx, cs:qword_180029618; lpBuffer
0x18000ac7e  inc     rdi
0x18000ac81  cmp     [rdx+rdi*2], r15w
0x18000ac86  jnz     short loc_18000AC7E
0x18000ac88  lea     r8d, [rdi+rdi]; nNumberOfBytesToWrite
0x18000ac8c  mov     [rsp+2070h+lpOverlapped], r15; lpOverlapped
0x18000ac91  lea     r9, [rsp+2070h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000ac96  mov     rcx, rsi; hFile
0x18000ac99  call    cs:__imp_WriteFile
0x18000aca0  nop     dword ptr [rax+rax+00h]
0x18000aca5  test    eax, eax
0x18000aca7  jnz     short loc_18000ACE8
0x18000aca9  call    cs:__imp_GetLastError
0x18000acb0  nop     dword ptr [rax+rax+00h]
0x18000acb5  mov     ebx, eax
0x18000acb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acbe  lea     rax, WPP_GLOBAL_Control
0x18000acc5  cmp     rcx, rax
0x18000acc8  jz      short loc_18000ACE8
0x18000acca  test    byte ptr [rcx+1Ch], 1
0x18000acce  jz      short loc_18000ACE8
0x18000acd0  mov     edx, 23h ; '#'
0x18000acd5  mov     rcx, [rcx+10h]
0x18000acd9  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000ace0  mov     r9d, ebx
0x18000ace3  call    WPP_SF_d
0x18000ace8  mov     eax, ebx
0x18000acea  mov     rcx, [rbp+1F70h+var_30]
0x18000acf1  xor     rcx, rsp; StackCookie
0x18000acf4  call    __security_check_cookie
0x18000acf9  mov     rbx, [rsp+2070h+arg_10]
0x18000ad01  add     rsp, 2050h
0x18000ad08  pop     r15
0x18000ad0a  pop     r14
0x18000ad0c  pop     rdi
0x18000ad0d  pop     rsi
0x18000ad0e  pop     rbp
0x18000ad0f  retn
```
