# LogInboundActivity(_JOB_QUEUE *,_FSPI_JOB_STATUS const *)

- ea: `0x14002b684`
- end: `0x14002b8b9`
- name: `?LogInboundActivity@@YAHPEAU_JOB_QUEUE@@PEBU_FSPI_JOB_STATUS@@@Z`
- size: `565`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, const struct _FSPI_JOB_STATUS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14003ed20`

## callees

- `0x140001b8c`
- `0x140004b30`
- `0x140004b58`
- `0x140028b6c`
- `0x14002b3d0`
- `0x14002b4a8`
- `0x14002b684`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002b822`
- `KERNEL32!GetLastError` at `0x14002b822`
- `KERNEL32!SetLastError` at `0x14002b87f`
- `KERNEL32!SetLastError` at `0x14002b87f`
- `KERNEL32!WriteFile` at `0x14002b818`
- `KERNEL32!WriteFile` at `0x14002b818`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LogInboundActivity(struct _JOB_QUEUE *a1, const struct _FSPI_JOB_STATUS *a2)
{
  DWORD v4; // ebx
  int InboundCommandText; // eax
  DWORD v7; // eax
  HANDLE v8; // rcx
  LPCVOID *v9; // rdx
  DWORD LastError; // eax
  __int64 v11; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-58h] BYREF
  int v13; // [rsp+34h] [rbp-54h]
  exception *v14; // [rsp+38h] [rbp-50h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v16; // [rsp+50h] [rbp-38h]
  unsigned __int64 v17; // [rsp+58h] [rbp-30h]

  v4 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  v17 = 7;
  v16 = 0;
  LOWORD(lpBuffer[0]) = 0;
  NumberOfBytesWritten = 0;
  if ( !*(&g_ActivityLoggingConfig + 1) )
    return 1;
  try
  {
    InboundCommandText = GetInboundCommandText(a1, a2, lpBuffer);
  }
  catch ( exception *v14 )
  {
    v13 = 14;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = (*(__int64 (__fastcall **)(exception *))(*(_QWORD *)v14 + 8LL))(v14);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v11);
    }
    v4 = v13;
    goto LABEL_37;
  }
  if ( InboundCommandText )
  {
    if ( !(unsigned int)LogFileLimitReached(0) )
      goto LABEL_26;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
    }
    v7 = LogFileLimitReachAction(0);
    v4 = v7;
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v7);
      }
      if ( !*(&g_ActivityLoggingConfig + 1) )
        goto LABEL_37;
      v8 = g_hInboxActivityLogFile;
      if ( g_hInboxActivityLogFile == (HANDLE)-1LL )
        goto LABEL_37;
      v4 = 0;
    }
    else
    {
LABEL_26:
      v8 = g_hInboxActivityLogFile;
    }
    v9 = lpBuffer;
    if ( v17 >= 8 )
      v9 = (LPCVOID *)lpBuffer[0];
    if ( !WriteFile(v8, v9, 2 * v16, &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
      }
    }
    if ( !v4 )
    {
      if ( v17 >= 8 )
        operator delete((void *)lpBuffer[0]);
      return 1;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
    }
    v4 = 14;
  }
LABEL_37:
  SetLastError(v4);
  if ( v17 >= 8 )
    operator delete((void *)lpBuffer[0]);
  return 0;
}

```

## disassembly

```asm
0x14002b684  mov     [rsp+arg_10], rbx
0x14002b689  push    rsi
0x14002b68a  push    r12
0x14002b68c  push    r14
0x14002b68e  sub     rsp, 70h
0x14002b692  mov     rax, cs:__security_cookie
0x14002b699  xor     rax, rsp
0x14002b69c  mov     [rsp+88h+var_28], rax
0x14002b6a1  mov     r14, rdx
0x14002b6a4  mov     rsi, rcx
0x14002b6a7  xor     ebx, ebx
0x14002b6a9  lea     r12, WPP_GLOBAL_Control
0x14002b6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b6b7  cmp     rcx, r12
0x14002b6ba  jz      short loc_14002B6DB
0x14002b6bc  test    byte ptr [rcx+1Ch], 4
0x14002b6c0  jz      short loc_14002B6DB
0x14002b6c2  cmp     byte ptr [rcx+19h], 5
0x14002b6c6  jb      short loc_14002B6DB
0x14002b6c8  lea     edx, [rbx+0Ah]
0x14002b6cb  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002b6d2  mov     rcx, [rcx+10h]
0x14002b6d6  call    WPP_SF_
0x14002b6db  mov     [rsp+88h+var_30], 7
0x14002b6e4  mov     [rsp+88h+var_38], rbx
0x14002b6e9  xor     eax, eax
0x14002b6eb  mov     word ptr [rsp+88h+lpBuffer], ax
0x14002b6f0  mov     [rsp+88h+NumberOfBytesWritten], eax
0x14002b6f4  cmp     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+4, eax; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x14002b6fa  jnz     short loc_14002B706
0x14002b6fc  mov     eax, 1
0x14002b701  jmp     loc_14002B89A
0x14002b706  lea     r8, [rsp+88h+lpBuffer]
0x14002b70b  mov     rdx, r14
0x14002b70e  mov     rcx, rsi
0x14002b711  call    GetInboundCommandText
0x14002b716  test    eax, eax
0x14002b718  jnz     short loc_14002B74F
0x14002b71a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b721  cmp     rcx, r12
0x14002b724  jz      short loc_14002B745
0x14002b726  test    byte ptr [rcx+1Ch], 4
0x14002b72a  jz      short loc_14002B745
0x14002b72c  cmp     byte ptr [rcx+19h], 2
0x14002b730  jb      short loc_14002B745
0x14002b732  lea     edx, [rax+0Bh]
0x14002b735  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002b73c  mov     rcx, [rcx+10h]
0x14002b740  call    WPP_SF_
0x14002b745  mov     ebx, 0Eh
0x14002b74a  jmp     loc_14002B87D
0x14002b74f  xor     ecx, ecx
0x14002b751  call    LogFileLimitReached
0x14002b756  test    eax, eax
0x14002b758  jz      loc_14002B7EA
0x14002b75e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b765  cmp     rcx, r12
0x14002b768  jz      short loc_14002B78B
0x14002b76a  test    byte ptr [rcx+1Ch], 4
0x14002b76e  jz      short loc_14002B78B
0x14002b770  cmp     byte ptr [rcx+19h], 5
0x14002b774  jb      short loc_14002B78B
0x14002b776  mov     edx, 0Dh
0x14002b77b  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002b782  mov     rcx, [rcx+10h]
0x14002b786  call    WPP_SF_
0x14002b78b  xor     ecx, ecx; pszLogFileName
0x14002b78d  call    LogFileLimitReachAction
0x14002b792  mov     ebx, eax
0x14002b794  test    eax, eax
0x14002b796  jz      short loc_14002B7EA
0x14002b798  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b79f  cmp     rcx, r12
0x14002b7a2  jz      short loc_14002B7C8
0x14002b7a4  test    byte ptr [rcx+1Ch], 4
0x14002b7a8  jz      short loc_14002B7C8
0x14002b7aa  cmp     byte ptr [rcx+19h], 2
0x14002b7ae  jb      short loc_14002B7C8
0x14002b7b0  mov     edx, 0Eh
0x14002b7b5  mov     r9d, eax
0x14002b7b8  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002b7bf  mov     rcx, [rcx+10h]
0x14002b7c3  call    WPP_SF_d
0x14002b7c8  cmp     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+4, 0; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x14002b7cf  jz      loc_14002B87D
0x14002b7d5  mov     rcx, cs:?g_hInboxActivityLogFile@@3PEAXEA; void * g_hInboxActivityLogFile
0x14002b7dc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002b7e0  jz      loc_14002B87D
0x14002b7e6  xor     ebx, ebx
0x14002b7e8  jmp     short loc_14002B7F1
0x14002b7ea  mov     rcx, cs:?g_hInboxActivityLogFile@@3PEAXEA; hFile
0x14002b7f1  mov     r8d, dword ptr [rsp+88h+var_38]
0x14002b7f6  lea     rdx, [rsp+88h+lpBuffer]
0x14002b7fb  cmp     [rsp+88h+var_30], 8
0x14002b801  cmovnb  rdx, [rsp+88h+lpBuffer]; lpBuffer
0x14002b807  add     r8d, r8d; nNumberOfBytesToWrite
0x14002b80a  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x14002b813  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002b818  call    cs:__imp_WriteFile
0x14002b81e  test    eax, eax
0x14002b820  jnz     short loc_14002B85A
0x14002b822  call    cs:__imp_GetLastError
0x14002b828  mov     ebx, eax
0x14002b82a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b831  cmp     rcx, r12
0x14002b834  jz      short loc_14002B85A
0x14002b836  test    byte ptr [rcx+1Ch], 4
0x14002b83a  jz      short loc_14002B85A
0x14002b83c  cmp     byte ptr [rcx+19h], 2
0x14002b840  jb      short loc_14002B85A
0x14002b842  mov     edx, 0Fh
0x14002b847  mov     r9d, eax
0x14002b84a  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002b851  mov     rcx, [rcx+10h]
0x14002b855  call    WPP_SF_d
0x14002b85a  test    ebx, ebx
0x14002b85c  jnz     short loc_14002B87D
0x14002b85e  cmp     [rsp+88h+var_30], 8
0x14002b864  jb      loc_14002B6FC
0x14002b86a  mov     rcx, [rsp+88h+lpBuffer]; Block
0x14002b86f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002b874  jmp     loc_14002B6FC
0x14002b879  mov     ebx, [rsp+88h+var_54]
0x14002b87d  mov     ecx, ebx; dwErrCode
0x14002b87f  call    cs:__imp_SetLastError
0x14002b885  nop
0x14002b886  cmp     [rsp+88h+var_30], 8
0x14002b88c  jb      short loc_14002B898
0x14002b88e  mov     rcx, [rsp+88h+lpBuffer]; Block
0x14002b893  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002b898  xor     eax, eax
0x14002b89a  mov     rcx, [rsp+88h+var_28]
0x14002b89f  xor     rcx, rsp; StackCookie
0x14002b8a2  call    __security_check_cookie
0x14002b8a7  mov     rbx, [rsp+88h+arg_10]
0x14002b8af  add     rsp, 70h
0x14002b8b3  pop     r14
0x14002b8b5  pop     r12
0x14002b8b7  pop     rsi
0x14002b8b8  retn
```
