# FwUpcallInitialize

- ea: `0x18007ccd8`
- end: `0x18007cebc`
- name: `FwUpcallInitialize`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800af160`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x18007ccd8`
- `0x18007cec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007ce1d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007ce1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cdce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cdce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce35`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007cdb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007cdb6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007cd4d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007cd4d`

## pseudocode

```c
__int64 FwUpcallInitialize()
{
  unsigned int v0; // ebx
  __int64 v1; // rcx
  DWORD v2; // eax
  signed int v3; // eax
  __int64 v4; // rdx
  signed int LastError; // eax

  v0 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_0ca9e11aaf2f3bbba2aed40f63d91021_Traceguids);
  qword_1801340B0 = (__int64)CDfwEngWriter::NotifyCallback;
  hFile = CreateFileW(L"\\\\.\\MpsDevice", 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
  if ( hFile != (HANDLE)-1LL )
  {
    qword_180134098 = CreateEventW(0, 0, 0, 0);
    if ( qword_180134098 )
    {
      qword_1801340A8 = CreateThread(0, 0, FwUpcallThread, 0, 0, 0);
      if ( qword_1801340A8 )
        goto LABEL_23;
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      v1 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_21;
      v4 = 20;
    }
    else
    {
      v3 = GetLastError();
      v0 = v3;
      if ( v3 > 0 )
        v0 = (unsigned __int16)v3 | 0x80070000;
      v1 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_21:
        if ( (v0 & 0x80000000) != 0 )
        {
          FwUpcallShutdown();
          goto LABEL_23;
        }
        goto LABEL_24;
      }
      v4 = 19;
    }
    WPP_SF_d(*(_QWORD *)(v1 + 16), v4, WPP_0ca9e11aaf2f3bbba2aed40f63d91021_Traceguids, v0);
    v1 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  v1 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v0;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v2 = GetLastError();
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_0ca9e11aaf2f3bbba2aed40f63d91021_Traceguids, v2);
LABEL_23:
    v1 = WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( (_UNKNOWN *)v1 != &WPP_GLOBAL_Control && (*(_BYTE *)(v1 + 28) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(v1 + 16), 21, WPP_0ca9e11aaf2f3bbba2aed40f63d91021_Traceguids);
  return v0;
}

```

## disassembly

```asm
0x18007ccd8  mov     [rsp+arg_0], rbx
0x18007ccdd  mov     [rsp+arg_8], rbp
0x18007cce2  push    rsi
0x18007cce3  sub     rsp, 40h
0x18007cce7  xor     ebx, ebx
0x18007cce9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ccf0  lea     rsi, WPP_GLOBAL_Control
0x18007ccf7  lea     rbp, WPP_0ca9e11aaf2f3bbba2aed40f63d91021_Traceguids
0x18007ccfe  cmp     rcx, rsi
0x18007cd01  jz      short loc_18007CD18
0x18007cd03  test    byte ptr [rcx+1Ch], 8
0x18007cd07  jz      short loc_18007CD18
0x18007cd09  mov     rcx, [rcx+10h]
0x18007cd0d  lea     edx, [rbx+11h]
0x18007cd10  mov     r8, rbp
0x18007cd13  call    WPP_SF_
0x18007cd18  lea     rax, ?NotifyCallback@CDfwEngWriter@@SAJPEAU_MPS_NOTIFY_USER_REQUEST@@@Z; CDfwEngWriter::NotifyCallback(_MPS_NOTIFY_USER_REQUEST *)
0x18007cd1f  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18007cd24  mov     [rsp+48h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18007cd2c  lea     rcx, FileName; "\\\\.\\MpsDevice"
0x18007cd33  xor     r9d, r9d; lpSecurityAttributes
0x18007cd36  mov     cs:qword_1801340B0, rax
0x18007cd3d  xor     r8d, r8d; dwShareMode
0x18007cd40  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18007cd48  mov     edx, 0C0000000h; dwDesiredAccess
0x18007cd4d  call    cs:__imp_CreateFileW
0x18007cd54  nop     dword ptr [rax+rax+00h]
0x18007cd59  mov     cs:hFile, rax
0x18007cd60  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007cd64  jnz     short loc_18007CDAC
0x18007cd66  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cd6d  cmp     rcx, rsi
0x18007cd70  jz      loc_18007CEA9
0x18007cd76  test    byte ptr [rcx+1Ch], 4
0x18007cd7a  jz      loc_18007CE8D
0x18007cd80  call    cs:__imp_GetLastError
0x18007cd87  nop     dword ptr [rax+rax+00h]
0x18007cd8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cd93  mov     edx, 12h
0x18007cd98  mov     r9d, eax
0x18007cd9b  mov     r8, rbp
0x18007cd9e  mov     rcx, [rcx+10h]
0x18007cda2  call    WPP_SF_d
0x18007cda7  jmp     loc_18007CE86
0x18007cdac  xor     r9d, r9d; lpName
0x18007cdaf  xor     r8d, r8d; bInitialState
0x18007cdb2  xor     edx, edx; bManualReset
0x18007cdb4  xor     ecx, ecx; lpEventAttributes
0x18007cdb6  call    cs:__imp_CreateEventW
0x18007cdbd  nop     dword ptr [rax+rax+00h]
0x18007cdc2  mov     cs:qword_180134098, rax
0x18007cdc9  test    rax, rax
0x18007cdcc  jnz     short loc_18007CE06
0x18007cdce  call    cs:__imp_GetLastError
0x18007cdd5  nop     dword ptr [rax+rax+00h]
0x18007cdda  mov     ebx, eax
0x18007cddc  test    eax, eax
0x18007cdde  jle     short loc_18007CDE9
0x18007cde0  movzx   ebx, ax
0x18007cde3  or      ebx, 80070000h
0x18007cde9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cdf0  cmp     rcx, rsi
0x18007cdf3  jz      loc_18007CE7D
0x18007cdf9  test    byte ptr [rcx+1Ch], 1
0x18007cdfd  jz      short loc_18007CE7D
0x18007cdff  mov     edx, 13h
0x18007ce04  jmp     short loc_18007CE67
0x18007ce06  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], rbx; lpThreadId
0x18007ce0b  lea     r8, FwUpcallThread; lpStartAddress
0x18007ce12  xor     r9d, r9d; lpParameter
0x18007ce15  mov     [rsp+48h+dwCreationDisposition], ebx; dwCreationFlags
0x18007ce19  xor     edx, edx; dwStackSize
0x18007ce1b  xor     ecx, ecx; lpThreadAttributes
0x18007ce1d  call    cs:__imp_CreateThread
0x18007ce24  nop     dword ptr [rax+rax+00h]
0x18007ce29  mov     cs:qword_1801340A8, rax
0x18007ce30  test    rax, rax
0x18007ce33  jnz     short loc_18007CE86
0x18007ce35  call    cs:__imp_GetLastError
0x18007ce3c  nop     dword ptr [rax+rax+00h]
0x18007ce41  mov     ebx, eax
0x18007ce43  test    eax, eax
0x18007ce45  jle     short loc_18007CE50
0x18007ce47  movzx   ebx, ax
0x18007ce4a  or      ebx, 80070000h
0x18007ce50  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce57  cmp     rcx, rsi
0x18007ce5a  jz      short loc_18007CE7D
0x18007ce5c  test    byte ptr [rcx+1Ch], 1
0x18007ce60  jz      short loc_18007CE7D
0x18007ce62  mov     edx, 14h
0x18007ce67  mov     rcx, [rcx+10h]
0x18007ce6b  mov     r9d, ebx
0x18007ce6e  mov     r8, rbp
0x18007ce71  call    WPP_SF_d
0x18007ce76  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce7d  test    ebx, ebx
0x18007ce7f  jns     short loc_18007CE8D
0x18007ce81  call    FwUpcallShutdown
0x18007ce86  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce8d  cmp     rcx, rsi
0x18007ce90  jz      short loc_18007CEA9
0x18007ce92  test    byte ptr [rcx+1Ch], 8
0x18007ce96  jz      short loc_18007CEA9
0x18007ce98  mov     rcx, [rcx+10h]
0x18007ce9c  mov     edx, 15h
0x18007cea1  mov     r8, rbp
0x18007cea4  call    WPP_SF_
0x18007cea9  mov     rbp, [rsp+48h+arg_8]
0x18007ceae  mov     eax, ebx
0x18007ceb0  mov     rbx, [rsp+48h+arg_0]
0x18007ceb5  add     rsp, 40h
0x18007ceb9  pop     rsi
0x18007ceba  retn
```
