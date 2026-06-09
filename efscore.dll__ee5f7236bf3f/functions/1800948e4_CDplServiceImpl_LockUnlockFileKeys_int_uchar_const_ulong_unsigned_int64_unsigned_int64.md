# CDplServiceImpl::LockUnlockFileKeys(int,uchar const *,ulong,unsigned __int64,unsigned __int64)

- ea: `0x1800948e4`
- end: `0x180094ba9`
- name: `?LockUnlockFileKeys@CDplServiceImpl@@AEAAXHPEBEK_K1@Z`
- size: `709`
- prototype: `void(CDplServiceImpl *__hidden this, int, const unsigned __int8 *, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18008f69c`
- `0x18009002c`
- `0x180093920`

## callees

- `0x180004f86`
- `0x180005045`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800948e4`
- `0x180099734`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094a9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094a9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094b15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094b53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094b53`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180094a8e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180094a8e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180094b0b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180094b0b`

## pseudocode

```c
void __fastcall CDplServiceImpl::LockUnlockFileKeys(
        CDplServiceImpl *this,
        int a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  size_t v7; // rdi
  int v10; // ecx
  unsigned int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdi
  HANDLE FileW; // rax
  signed int LastError; // eax
  signed int v16; // eax
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-89h] BYREF
  int InBuffer; // [rsp+50h] [rbp-79h] BYREF
  int v19; // [rsp+54h] [rbp-75h]
  unsigned __int16 v20; // [rsp+58h] [rbp-71h]
  unsigned __int16 v21; // [rsp+5Ah] [rbp-6Fh] BYREF
  BOOL v22; // [rsp+5Ch] [rbp-6Dh]
  unsigned __int64 v23; // [rsp+60h] [rbp-69h]
  unsigned __int64 v24; // [rsp+68h] [rbp-61h]

  v7 = a4;
  memset_0(&InBuffer, 0, 0x80u);
  BytesReturned[0] = 0;
  fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 46);
  if ( (unsigned int)v7 > 0x40 )
  {
    v11 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 37, 50);
    goto LABEL_21;
  }
  v11 = 0;
  memset_0(&InBuffer, 0, 0x80u);
  InBuffer = 32;
  v19 = 32;
  v22 = a2 != 0;
  v23 = a5;
  v24 = a6;
  if ( a3 && (_DWORD)v7 )
  {
    v20 = 64;
    fnEfsLogTrace1Strings(v12, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 81);
    v11 = ULongToUShort(v7, &v21);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v11,
                37,
                81) < 0 )
      goto LABEL_21;
    memcpy_0((char *)&InBuffer + v20, a3, v7);
    v19 = v20 + v21;
  }
  v13 = -1;
  if ( *((_QWORD *)this + 36) == -1 )
  {
    FileW = CreateFileW(L"\\\\.\\Ntfs", 0, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v13 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 37, 109);
      goto LABEL_21;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 36, (signed __int64)FileW, -1) == -1 )
      v13 = -1;
  }
  if ( !DeviceIoControl(*((HANDLE *)this + 36), 0x90404u, &InBuffer, 0x80u, 0, 0, BytesReturned, 0) )
  {
    v16 = GetLastError();
    v11 = v16;
    if ( v16 > 0 )
      v11 = (unsigned __int16)v16 | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 37, 128);
  }
  if ( v13 != -1 )
    CloseHandle((HANDLE)v13);
LABEL_21:
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v11,
    37,
    135);
}

```

## disassembly

```asm
0x1800948e4  push    rbp
0x1800948e6  push    rbx
0x1800948e7  push    rsi
0x1800948e8  push    rdi
0x1800948e9  push    r13
0x1800948eb  push    r14
0x1800948ed  push    r15
0x1800948ef  lea     rbp, [rsp-17h]
0x1800948f4  sub     rsp, 0E0h
0x1800948fb  mov     rax, cs:__security_cookie
0x180094902  xor     rax, rsp
0x180094905  mov     [rbp+47h+var_40], rax
0x180094909  mov     r14, r8
0x18009490c  mov     edi, r9d
0x18009490f  mov     r15d, edx
0x180094912  mov     rsi, rcx
0x180094915  xor     edx, edx; Val
0x180094917  lea     rcx, [rbp+47h+InBuffer]; void *
0x18009491b  mov     r8d, 80h; Size
0x180094921  call    memset_0
0x180094926  mov     r13d, 25h ; '%'
0x18009492c  mov     [rsp+110h+BytesReturned], 0
0x180094934  mov     r9d, r13d
0x180094937  mov     [rsp+110h+dwCreationDisposition], 212Eh
0x18009493f  lea     r8, sourceString
0x180094946  lea     rdx, EFS_TRACE_ENTER_EVENT
0x18009494d  call    fnEfsLogTrace1Strings
0x180094952  cmp     edi, 40h ; '@'
0x180094955  jbe     short loc_180094985
0x180094957  mov     ebx, 80070057h
0x18009495c  mov     [rsp+110h+dwCreationDisposition], 2132h
0x180094964  mov     r8d, 80070057h
0x18009496a  mov     rcx, cs:g_hPublisher
0x180094971  lea     rdx, EFS_TRACE_ERROR
0x180094978  mov     r9d, r13d
0x18009497b  call    fnEfsLogTrace1
0x180094980  jmp     loc_180094B59
0x180094985  xor     edx, edx; Val
0x180094987  lea     rcx, [rbp+47h+InBuffer]; void *
0x18009498b  mov     r8d, 80h; Size
0x180094991  xor     ebx, ebx
0x180094993  call    memset_0
0x180094998  lea     eax, [rbx+20h]
0x18009499b  mov     [rbp+47h+InBuffer], eax
0x18009499e  mov     [rbp+47h+var_BC], eax
0x1800949a1  xor     eax, eax
0x1800949a3  test    r15d, r15d
0x1800949a6  setnz   al
0x1800949a9  mov     [rbp+47h+var_B4], eax
0x1800949ac  mov     rax, [rbp+47h+arg_20]
0x1800949b0  mov     [rbp+47h+var_B0], rax
0x1800949b4  mov     rax, [rbp+47h+arg_28]
0x1800949b8  mov     [rbp+47h+var_A8], rax
0x1800949bc  test    r14, r14
0x1800949bf  jz      loc_180094A5C
0x1800949c5  test    edi, edi
0x1800949c7  jz      loc_180094A5C
0x1800949cd  lea     eax, [rbx+40h]
0x1800949d0  mov     r15d, 2151h
0x1800949d6  mov     r9d, r13d
0x1800949d9  mov     [rbp+47h+var_B8], ax
0x1800949dd  lea     r8, sourceString
0x1800949e4  mov     [rsp+110h+dwCreationDisposition], r15d
0x1800949e9  lea     rdx, EFS_TRACE_START_EVENT
0x1800949f0  call    fnEfsLogTrace1Strings
0x1800949f5  lea     rdx, [rbp+47h+var_B6]; unsigned __int16 *
0x1800949f9  mov     ecx, edi; unsigned int
0x1800949fb  call    ?ULongToUShort@@YAJKPEAG@Z; ULongToUShort(ulong,ushort *)
0x180094a00  mov     rcx, cs:g_hPublisher
0x180094a07  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180094a0e  mov     dword ptr [rsp+110h+hTemplateFile], r15d
0x180094a13  lea     r9, sourceString
0x180094a1a  mov     [rsp+110h+dwFlagsAndAttributes], r13d
0x180094a1f  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180094a26  mov     [rsp+110h+dwCreationDisposition], eax
0x180094a2a  mov     ebx, eax
0x180094a2c  call    fnEfsLogTrace1String1Dword
0x180094a31  test    eax, eax
0x180094a33  js      loc_180094B59
0x180094a39  movzx   eax, [rbp+47h+var_B8]
0x180094a3d  lea     rcx, [rbp+47h+InBuffer]
0x180094a41  add     rcx, rax; void *
0x180094a44  mov     r8, rdi; Size
0x180094a47  mov     rdx, r14; Src
0x180094a4a  call    memcpy_0
0x180094a4f  movzx   ecx, [rbp+47h+var_B6]
0x180094a53  movzx   eax, [rbp+47h+var_B8]
0x180094a57  add     ecx, eax
0x180094a59  mov     [rbp+47h+var_BC], ecx
0x180094a5c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180094a60  mov     rdi, r14
0x180094a63  cmp     [rsi+120h], r14
0x180094a6a  jnz     short loc_180094AD1
0x180094a6c  mov     [rsp+110h+hTemplateFile], r14; hTemplateFile
0x180094a71  lea     r8d, [r14+4]; dwShareMode
0x180094a75  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180094a7d  lea     rcx, FileName; "\\\\.\\Ntfs"
0x180094a84  xor     r9d, r9d; lpSecurityAttributes
0x180094a87  mov     [rsp+110h+dwCreationDisposition], r8d; dwCreationDisposition
0x180094a8c  xor     edx, edx; dwDesiredAccess
0x180094a8e  call    cs:__imp_CreateFileW
0x180094a94  mov     rdi, rax
0x180094a97  cmp     rax, r14
0x180094a9a  jnz     short loc_180094AC1
0x180094a9c  call    cs:__imp_GetLastError
0x180094aa2  mov     ebx, eax
0x180094aa4  test    eax, eax
0x180094aa6  jle     short loc_180094AB1
0x180094aa8  movzx   ebx, ax
0x180094aab  or      ebx, 80070000h
0x180094ab1  mov     [rsp+110h+dwCreationDisposition], 216Dh
0x180094ab9  mov     r8d, ebx
0x180094abc  jmp     loc_18009496A
0x180094ac1  mov     rax, r14
0x180094ac4  lock cmpxchg [rsi+120h], rdi
0x180094acd  cmovz   rdi, r14
0x180094ad1  mov     rcx, [rsi+120h]; hDevice
0x180094ad8  lea     rax, [rsp+110h+BytesReturned]
0x180094add  mov     [rsp+110h+lpOverlapped], 0; lpOverlapped
0x180094ae6  lea     r8, [rbp+47h+InBuffer]; lpInBuffer
0x180094aea  mov     [rsp+110h+hTemplateFile], rax; lpBytesReturned
0x180094aef  mov     r9d, 80h; nInBufferSize
0x180094af5  mov     [rsp+110h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180094afd  mov     edx, 90404h; dwIoControlCode
0x180094b02  mov     qword ptr [rsp+110h+dwCreationDisposition], 0; lpOutBuffer
0x180094b0b  call    cs:__imp_DeviceIoControl
0x180094b11  test    eax, eax
0x180094b13  jnz     short loc_180094B4B
0x180094b15  call    cs:__imp_GetLastError
0x180094b1b  mov     ebx, eax
0x180094b1d  test    eax, eax
0x180094b1f  jle     short loc_180094B2A
0x180094b21  movzx   ebx, ax
0x180094b24  or      ebx, 80070000h
0x180094b2a  mov     rcx, cs:g_hPublisher
0x180094b31  lea     rdx, EFS_TRACE_ERROR
0x180094b38  mov     r9d, r13d
0x180094b3b  mov     [rsp+110h+dwCreationDisposition], 2180h
0x180094b43  mov     r8d, ebx
0x180094b46  call    fnEfsLogTrace1
0x180094b4b  cmp     rdi, r14
0x180094b4e  jz      short loc_180094B59
0x180094b50  mov     rcx, rdi; hObject
0x180094b53  call    cs:__imp_CloseHandle
0x180094b59  mov     rcx, cs:g_hPublisher
0x180094b60  lea     r9, sourceString
0x180094b67  mov     dword ptr [rsp+110h+hTemplateFile], 2187h
0x180094b6f  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x180094b76  mov     [rsp+110h+dwFlagsAndAttributes], r13d
0x180094b7b  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x180094b82  mov     [rsp+110h+dwCreationDisposition], ebx
0x180094b86  call    fnEfsLogTrace1String1Dword
0x180094b8b  mov     rcx, [rbp+47h+var_40]
0x180094b8f  xor     rcx, rsp; StackCookie
0x180094b92  call    __security_check_cookie
0x180094b97  add     rsp, 0E0h
0x180094b9e  pop     r15
0x180094ba0  pop     r14
0x180094ba2  pop     r13
0x180094ba4  pop     rdi
0x180094ba5  pop     rsi
0x180094ba6  pop     rbx
0x180094ba7  pop     rbp
0x180094ba8  retn
```
