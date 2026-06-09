# FwUpcallInitialize

- ea: `0x1800790e0`
- end: `0x18007929b`
- name: `FwUpcallInitialize`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800a9490`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x1800790e0`
- `0x1800792a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180079209`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180079209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800791c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007921b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800791c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007921b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800791b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800791b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180079155`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180079155`

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
  qword_18012DEE0 = (__int64)CDfwEngWriter::NotifyCallback;
  hFile = CreateFileW(L"\\\\.\\MpsDevice", 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
  if ( hFile != (HANDLE)-1LL )
  {
    qword_18012DEC8 = CreateEventW(0, 0, 0, 0);
    if ( qword_18012DEC8 )
    {
      qword_18012DED8 = CreateThread(0, 0, FwUpcallThread, 0, 0, 0);
      if ( qword_18012DED8 )
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
0x1800790e0  mov     [rsp+arg_0], rbx
0x1800790e5  mov     [rsp+arg_8], rbp
0x1800790ea  push    rsi
0x1800790eb  sub     rsp, 40h
0x1800790ef  xor     ebx, ebx
0x1800790f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800790f8  lea     rsi, WPP_GLOBAL_Control
0x1800790ff  lea     rbp, WPP_0ca9e11aaf2f3bbba2aed40f63d91021_Traceguids
0x180079106  cmp     rcx, rsi
0x180079109  jz      short loc_180079120
0x18007910b  test    byte ptr [rcx+1Ch], 8
0x18007910f  jz      short loc_180079120
0x180079111  mov     rcx, [rcx+10h]
0x180079115  lea     edx, [rbx+11h]
0x180079118  mov     r8, rbp
0x18007911b  call    WPP_SF_
0x180079120  lea     rax, ?NotifyCallback@CDfwEngWriter@@SAJPEAU_MPS_NOTIFY_USER_REQUEST@@@Z; CDfwEngWriter::NotifyCallback(_MPS_NOTIFY_USER_REQUEST *)
0x180079127  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18007912c  mov     [rsp+48h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180079134  lea     rcx, FileName; "\\\\.\\MpsDevice"
0x18007913b  xor     r9d, r9d; lpSecurityAttributes
0x18007913e  mov     cs:qword_18012DEE0, rax
0x180079145  xor     r8d, r8d; dwShareMode
0x180079148  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180079150  mov     edx, 0C0000000h; dwDesiredAccess
0x180079155  call    cs:__imp_CreateFileW
0x18007915b  mov     cs:hFile, rax
0x180079162  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180079166  jnz     short loc_1800791A8
0x180079168  mov     rcx, cs:WPP_GLOBAL_Control
0x18007916f  cmp     rcx, rsi
0x180079172  jz      loc_180079289
0x180079178  test    byte ptr [rcx+1Ch], 4
0x18007917c  jz      loc_18007926D
0x180079182  call    cs:__imp_GetLastError
0x180079188  mov     rcx, cs:WPP_GLOBAL_Control
0x18007918f  mov     edx, 12h
0x180079194  mov     r9d, eax
0x180079197  mov     r8, rbp
0x18007919a  mov     rcx, [rcx+10h]
0x18007919e  call    WPP_SF_d
0x1800791a3  jmp     loc_180079266
0x1800791a8  xor     r9d, r9d; lpName
0x1800791ab  xor     r8d, r8d; bInitialState
0x1800791ae  xor     edx, edx; bManualReset
0x1800791b0  xor     ecx, ecx; lpEventAttributes
0x1800791b2  call    cs:__imp_CreateEventW
0x1800791b8  mov     cs:qword_18012DEC8, rax
0x1800791bf  test    rax, rax
0x1800791c2  jnz     short loc_1800791F2
0x1800791c4  call    cs:__imp_GetLastError
0x1800791ca  mov     ebx, eax
0x1800791cc  test    eax, eax
0x1800791ce  jle     short loc_1800791D9
0x1800791d0  movzx   ebx, ax
0x1800791d3  or      ebx, 80070000h
0x1800791d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800791e0  cmp     rcx, rsi
0x1800791e3  jz      short loc_18007925D
0x1800791e5  test    byte ptr [rcx+1Ch], 1
0x1800791e9  jz      short loc_18007925D
0x1800791eb  mov     edx, 13h
0x1800791f0  jmp     short loc_180079247
0x1800791f2  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], rbx; lpThreadId
0x1800791f7  lea     r8, FwUpcallThread; lpStartAddress
0x1800791fe  xor     r9d, r9d; lpParameter
0x180079201  mov     [rsp+48h+dwCreationDisposition], ebx; dwCreationFlags
0x180079205  xor     edx, edx; dwStackSize
0x180079207  xor     ecx, ecx; lpThreadAttributes
0x180079209  call    cs:__imp_CreateThread
0x18007920f  mov     cs:qword_18012DED8, rax
0x180079216  test    rax, rax
0x180079219  jnz     short loc_180079266
0x18007921b  call    cs:__imp_GetLastError
0x180079221  mov     ebx, eax
0x180079223  test    eax, eax
0x180079225  jle     short loc_180079230
0x180079227  movzx   ebx, ax
0x18007922a  or      ebx, 80070000h
0x180079230  mov     rcx, cs:WPP_GLOBAL_Control
0x180079237  cmp     rcx, rsi
0x18007923a  jz      short loc_18007925D
0x18007923c  test    byte ptr [rcx+1Ch], 1
0x180079240  jz      short loc_18007925D
0x180079242  mov     edx, 14h
0x180079247  mov     rcx, [rcx+10h]
0x18007924b  mov     r9d, ebx
0x18007924e  mov     r8, rbp
0x180079251  call    WPP_SF_d
0x180079256  mov     rcx, cs:WPP_GLOBAL_Control
0x18007925d  test    ebx, ebx
0x18007925f  jns     short loc_18007926D
0x180079261  call    FwUpcallShutdown
0x180079266  mov     rcx, cs:WPP_GLOBAL_Control
0x18007926d  cmp     rcx, rsi
0x180079270  jz      short loc_180079289
0x180079272  test    byte ptr [rcx+1Ch], 8
0x180079276  jz      short loc_180079289
0x180079278  mov     rcx, [rcx+10h]
0x18007927c  mov     edx, 15h
0x180079281  mov     r8, rbp
0x180079284  call    WPP_SF_
0x180079289  mov     rbp, [rsp+48h+arg_8]
0x18007928e  mov     eax, ebx
0x180079290  mov     rbx, [rsp+48h+arg_0]
0x180079295  add     rsp, 40h
0x180079299  pop     rsi
0x18007929a  retn
```
