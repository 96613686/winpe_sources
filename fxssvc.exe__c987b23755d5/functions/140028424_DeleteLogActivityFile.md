# DeleteLogActivityFile

- ea: `0x140028424`
- end: `0x140028626`
- name: `DeleteLogActivityFile`
- size: `514`
- prototype: `__int64 __fastcall(LPCWSTR pszLogFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002b3d0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14002793c`
- `0x140027f80`
- `0x140028424`
- `0x14002bf54`
- `0x140065dbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400284ed`
- `KERNEL32!GetLastError` at `0x140028546`
- `KERNEL32!GetLastError` at `0x1400284ed`
- `KERNEL32!GetLastError` at `0x140028546`
- `KERNEL32!CloseHandle` at `0x1400284e3`
- `KERNEL32!CloseHandle` at `0x1400284e3`
- `KERNEL32!DeleteFileW` at `0x14002853c`
- `KERNEL32!DeleteFileW` at `0x14002853c`

## pseudocode

```c
__int64 __fastcall DeleteLogActivityFile(LPCWSTR pszLogFileName)
{
  unsigned int v1; // ebx
  const wchar_t *v2; // rdx
  WCHAR *v3; // rsi
  unsigned int v4; // ebx
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  HANDLE v7; // rcx
  HANDLE *v8; // rdi
  DWORD LastError; // eax
  CMapDeviceId *v10; // rcx
  __int64 v11; // rdx
  struct _SECURITY_ATTRIBUTES *v12; // r9
  DWORD v13; // eax
  ULONG v15; // [rsp+20h] [rbp-28h]
  ULONG v16; // [rsp+28h] [rbp-20h]

  v1 = (unsigned int)pszLogFileName;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  v2 = L"InboxLOG.txt";
  if ( v1 )
    v2 = L"OutboxLOG.txt";
  v3 = (WCHAR *)BuildFullFileName(*(_QWORD *)&fDesiredAccess, v2);
  if ( !v3 )
  {
    v4 = 8;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 100;
LABEL_41:
      WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  v7 = g_hOutboxActivityLogFile;
  v8 = &g_hInboxActivityLogFile;
  if ( v1 )
    v8 = &g_hOutboxActivityLogFile;
  else
    v7 = g_hInboxActivityLogFile;
  if ( !CloseHandle(v7) )
  {
    LastError = GetLastError();
    v4 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_42;
    }
    v11 = 101;
    goto LABEL_20;
  }
  *v8 = (HANDLE)-1LL;
  if ( !DeleteFileW(v3) )
  {
    v13 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v13);
    }
  }
  LastError = (unsigned int)CreateLogFile((LPCWSTR)v1, fDesiredAccess, (DWORD)v8, v12, v15, v16);
  v4 = LastError;
  if ( LastError )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_42;
    }
    v11 = 103;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
    goto LABEL_42;
  }
  if ( !(unsigned int)SetFileToCurrentTime(*v8) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
      goto LABEL_42;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_37;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, 0);
  }
  v5 = WPP_GLOBAL_Control;
LABEL_37:
  if ( v5 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 && *((_BYTE *)v5 + 25) >= 5u )
  {
    v6 = 105;
    goto LABEL_41;
  }
LABEL_42:
  pMemFree(v3);
  return v4;
}

```

## disassembly

```asm
0x140028424  push    rbx
0x140028426  push    rsi
0x140028427  push    rdi
0x140028428  push    r14; fFlagsAndAttributes
0x14002842a  push    r15; fCreateDisposition
0x14002842c  sub     rsp, 20h
0x140028430  mov     ebx, ecx
0x140028432  mov     rcx, cs:WPP_GLOBAL_Control
0x140028439  lea     r14, WPP_GLOBAL_Control
0x140028440  lea     r15, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028447  cmp     rcx, r14
0x14002844a  jz      short loc_140028469
0x14002844c  test    byte ptr [rcx+1Ch], 4
0x140028450  jz      short loc_140028469
0x140028452  cmp     byte ptr [rcx+19h], 5
0x140028456  jb      short loc_140028469
0x140028458  mov     rcx, [rcx+10h]
0x14002845c  mov     edx, 63h ; 'c'
0x140028461  mov     r8, r15
0x140028464  call    WPP_SF_
0x140028469  mov     rcx, qword ptr cs:fDesiredAccess
0x140028470  lea     rax, aOutboxlogTxt; "OutboxLOG.txt"
0x140028477  test    ebx, ebx
0x140028479  lea     rdx, aInboxlogTxt; "InboxLOG.txt"
0x140028480  cmovnz  rdx, rax
0x140028484  call    BuildFullFileName
0x140028489  mov     rsi, rax
0x14002848c  test    rax, rax
0x14002848f  jnz     short loc_1400284C0
0x140028491  lea     ebx, [rax+8]
0x140028494  mov     rcx, cs:WPP_GLOBAL_Control
0x14002849b  cmp     rcx, r14
0x14002849e  jz      loc_140028610
0x1400284a4  test    byte ptr [rcx+1Ch], 4
0x1400284a8  jz      loc_140028610
0x1400284ae  cmp     byte ptr [rcx+19h], 2
0x1400284b2  jb      loc_140028610
0x1400284b8  lea     edx, [rax+64h]
0x1400284bb  jmp     loc_140028604
0x1400284c0  mov     rcx, cs:?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x1400284c7  lea     rax, ?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x1400284ce  test    ebx, ebx
0x1400284d0  lea     rdi, ?g_hInboxActivityLogFile@@3PEAXEA; void * g_hInboxActivityLogFile
0x1400284d7  cmovz   rcx, cs:?g_hInboxActivityLogFile@@3PEAXEA; hObject
0x1400284df  cmovnz  rdi, rax
0x1400284e3  call    cs:__imp_CloseHandle
0x1400284e9  test    eax, eax
0x1400284eb  jnz     short loc_140028532
0x1400284ed  call    cs:__imp_GetLastError
0x1400284f3  mov     ebx, eax
0x1400284f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400284fc  cmp     rcx, r14
0x1400284ff  jz      loc_140028610
0x140028505  test    byte ptr [rcx+1Ch], 4
0x140028509  jz      loc_140028610
0x14002850f  cmp     byte ptr [rcx+19h], 2
0x140028513  jb      loc_140028610
0x140028519  mov     edx, 65h ; 'e'
0x14002851e  mov     rcx, [rcx+10h]
0x140028522  mov     r9d, eax
0x140028525  mov     r8, r15
0x140028528  call    WPP_SF_d
0x14002852d  jmp     loc_140028610
0x140028532  mov     rcx, rsi; lpFileName
0x140028535  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14002853c  call    cs:__imp_DeleteFileW
0x140028542  test    eax, eax
0x140028544  jnz     short loc_140028578
0x140028546  call    cs:__imp_GetLastError
0x14002854c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028553  cmp     rcx, r14
0x140028556  jz      short loc_140028578
0x140028558  test    byte ptr [rcx+1Ch], 4
0x14002855c  jz      short loc_140028578
0x14002855e  cmp     byte ptr [rcx+19h], 2
0x140028562  jb      short loc_140028578
0x140028564  mov     rcx, [rcx+10h]
0x140028568  mov     edx, 66h ; 'f'
0x14002856d  mov     r9d, eax
0x140028570  mov     r8, r15
0x140028573  call    WPP_SF_d
0x140028578  mov     rdx, qword ptr cs:fDesiredAccess; fDesiredAccess
0x14002857f  mov     r8, rdi; dwShareMode
0x140028582  mov     ecx, ebx; pszLogFileName
0x140028584  call    CreateLogFile
0x140028589  mov     ebx, eax
0x14002858b  test    eax, eax
0x14002858d  jz      short loc_1400285B1
0x14002858f  mov     rcx, cs:WPP_GLOBAL_Control
0x140028596  cmp     rcx, r14
0x140028599  jz      short loc_140028610
0x14002859b  test    byte ptr [rcx+1Ch], 4
0x14002859f  jz      short loc_140028610
0x1400285a1  cmp     byte ptr [rcx+19h], 2
0x1400285a5  jb      short loc_140028610
0x1400285a7  mov     edx, 67h ; 'g'
0x1400285ac  jmp     loc_14002851E
0x1400285b1  mov     rcx, [rdi]; hFile
0x1400285b4  call    SetFileToCurrentTime
0x1400285b9  test    eax, eax
0x1400285bb  jnz     short loc_1400285E7
0x1400285bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400285c4  cmp     rcx, r14
0x1400285c7  jz      short loc_140028610
0x1400285c9  test    byte ptr [rcx+1Ch], 4
0x1400285cd  jz      short loc_1400285EE
0x1400285cf  cmp     byte ptr [rcx+19h], 2
0x1400285d3  jb      short loc_1400285EE
0x1400285d5  mov     rcx, [rcx+10h]
0x1400285d9  lea     edx, [rax+68h]
0x1400285dc  xor     r9d, r9d
0x1400285df  mov     r8, r15
0x1400285e2  call    WPP_SF_d
0x1400285e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400285ee  cmp     rcx, r14
0x1400285f1  jz      short loc_140028610
0x1400285f3  test    byte ptr [rcx+1Ch], 4
0x1400285f7  jz      short loc_140028610
0x1400285f9  cmp     byte ptr [rcx+19h], 5
0x1400285fd  jb      short loc_140028610
0x1400285ff  mov     edx, 69h ; 'i'
0x140028604  mov     rcx, [rcx+10h]
0x140028608  mov     r8, r15
0x14002860b  call    WPP_SF_
0x140028610  mov     rcx, rsi; lpMem
0x140028613  call    pMemFree
0x140028618  mov     eax, ebx
0x14002861a  add     rsp, 20h
0x14002861e  pop     r15
0x140028620  pop     r14
0x140028622  pop     rdi
0x140028623  pop     rsi
0x140028624  pop     rbx
0x140028625  retn
```
