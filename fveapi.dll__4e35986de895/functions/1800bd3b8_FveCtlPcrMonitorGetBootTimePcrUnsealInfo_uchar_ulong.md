# FveCtlPcrMonitorGetBootTimePcrUnsealInfo(uchar *,ulong *)

- ea: `0x1800bd3b8`
- end: `0x1800bd5b6`
- name: `?FveCtlPcrMonitorGetBootTimePcrUnsealInfo@@YAJPEAEPEAK@Z`
- size: `510`
- prototype: `__int64 __fastcall(unsigned __int8 *lpOutBuffer, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800bd044`

## callees

- `0x180005410`
- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x1800bd3b8`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd55a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180126d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd55a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180126d43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bd452`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bd452`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800bd4ab`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800bd535`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800bd4ab`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800bd535`

## pseudocode

```c
__int64 __fastcall FveCtlPcrMonitorGetBootTimePcrUnsealInfo(unsigned __int8 *lpOutBuffer, unsigned int *a2)
{
  HANDLE FileW; // rdi
  unsigned int v5; // eax
  unsigned int LastHresultError; // ebx
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD BytesReturned; // [rsp+48h] [rbp-30h] BYREF
  __int64 OutBuffer; // [rsp+50h] [rbp-28h] BYREF

  BytesReturned = 0;
  OutBuffer = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 391, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
  FileW = CreateFileW(L"\\\\.\\BitLocker", 0x80u, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_5;
  if ( !DeviceIoControl(FileW, 0x4C4210D8u, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
  {
    LastHresultError = GetLastHresultError();
    if ( LastHresultError != -2147024662 )
      goto LABEL_20;
    if ( BytesReturned < 8 )
    {
      v5 = FromNtStatus(-1073741823);
      goto LABEL_6;
    }
  }
  v7 = *a2;
  if ( lpOutBuffer )
  {
    if ( v7 < (unsigned __int16)OutBuffer )
    {
      *a2 = (unsigned __int16)OutBuffer;
      LastHresultError = -2147024662;
      goto LABEL_20;
    }
    if ( !DeviceIoControl(FileW, 0x4C4210D8u, 0, 0, lpOutBuffer, v7, &BytesReturned, 0) )
    {
LABEL_5:
      v5 = GetLastHresultError();
LABEL_6:
      LastHresultError = v5;
      goto LABEL_20;
    }
    v8 = BytesReturned;
  }
  else
  {
    if ( v7 )
    {
      LastHresultError = -2147467261;
      goto LABEL_20;
    }
    v8 = (unsigned __int16)OutBuffer;
  }
  LastHresultError = 0;
  *a2 = v8;
LABEL_20:
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      392,
      &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
      LastHresultError);
  return LastHresultError;
}

```

## disassembly

```asm
0x1800bd3b8  mov     r11, rsp
0x1800bd3bb  mov     [r11+18h], rbx
0x1800bd3bf  mov     [r11+20h], rsi
0x1800bd3c3  push    rdi
0x1800bd3c4  push    r12
0x1800bd3c6  push    r14
0x1800bd3c8  sub     rsp, 60h
0x1800bd3cc  mov     rax, cs:__security_cookie
0x1800bd3d3  xor     rax, rsp
0x1800bd3d6  mov     [rsp+78h+var_20], rax
0x1800bd3db  mov     rsi, rdx
0x1800bd3de  mov     r14, rcx
0x1800bd3e1  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFFh
0x1800bd3e9  mov     [rsp+78h+BytesReturned], 0
0x1800bd3f1  mov     qword ptr [r11-28h], 0
0x1800bd3f9  lea     r12, WPP_GLOBAL_Control
0x1800bd400  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd407  cmp     rcx, r12
0x1800bd40a  jz      short loc_1800BD428
0x1800bd40c  test    byte ptr [rcx+1Ch], 20h
0x1800bd410  jz      short loc_1800BD428
0x1800bd412  mov     edx, 187h
0x1800bd417  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800bd41e  mov     rcx, [rcx+10h]
0x1800bd422  call    WPP_SF_
0x1800bd427  nop
0x1800bd428  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800bd431  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800bd439  mov     r8d, 3; dwShareMode
0x1800bd43f  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800bd444  xor     r9d, r9d; lpSecurityAttributes
0x1800bd447  lea     edx, [r8+7Dh]; dwDesiredAccess
0x1800bd44b  lea     rcx, FileName; "\\\\.\\BitLocker"
0x1800bd452  call    cs:__imp_CreateFileW
0x1800bd459  nop     dword ptr [rax+rax+00h]
0x1800bd45e  mov     rdi, rax
0x1800bd461  mov     [rsp+78h+var_38], rax
0x1800bd466  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bd46a  jnz     short loc_1800BD478
0x1800bd46c  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x1800bd471  mov     ebx, eax
0x1800bd473  jmp     loc_1800BD551
0x1800bd478  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800bd481  lea     rax, [rsp+78h+BytesReturned]
0x1800bd486  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x1800bd48b  mov     [rsp+78h+dwFlagsAndAttributes], 8; nOutBufferSize
0x1800bd493  lea     rax, [rsp+78h+OutBuffer]
0x1800bd498  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpOutBuffer
0x1800bd49d  xor     r9d, r9d; nInBufferSize
0x1800bd4a0  xor     r8d, r8d; lpInBuffer
0x1800bd4a3  mov     edx, 4C4210D8h; dwIoControlCode
0x1800bd4a8  mov     rcx, rdi; hDevice
0x1800bd4ab  call    cs:__imp_DeviceIoControl
0x1800bd4b2  nop     dword ptr [rax+rax+00h]
0x1800bd4b7  test    eax, eax
0x1800bd4b9  jnz     short loc_1800BD4E0
0x1800bd4bb  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x1800bd4c0  mov     ebx, eax
0x1800bd4c2  cmp     eax, 800700EAh
0x1800bd4c7  jnz     loc_1800BD551
0x1800bd4cd  cmp     [rsp+78h+BytesReturned], 8
0x1800bd4d2  jnb     short loc_1800BD4E0
0x1800bd4d4  mov     ecx, 0C0000001h; int
0x1800bd4d9  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bd4de  jmp     short loc_1800BD471
0x1800bd4e0  mov     eax, [rsi]
0x1800bd4e2  test    r14, r14
0x1800bd4e5  jnz     short loc_1800BD4F9
0x1800bd4e7  test    eax, eax
0x1800bd4e9  jnz     short loc_1800BD4F2
0x1800bd4eb  movzx   eax, word ptr [rsp+78h+OutBuffer]
0x1800bd4f0  jmp     short loc_1800BD54D
0x1800bd4f2  mov     ebx, 80004003h
0x1800bd4f7  jmp     short loc_1800BD551
0x1800bd4f9  movzx   ecx, word ptr [rsp+78h+OutBuffer]
0x1800bd4fe  cmp     eax, ecx
0x1800bd500  jnb     short loc_1800BD50B
0x1800bd502  mov     [rsi], ecx
0x1800bd504  mov     ebx, 800700EAh
0x1800bd509  jmp     short loc_1800BD551
0x1800bd50b  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800bd514  lea     rcx, [rsp+78h+BytesReturned]
0x1800bd519  mov     [rsp+78h+hTemplateFile], rcx; lpBytesReturned
0x1800bd51e  mov     [rsp+78h+dwFlagsAndAttributes], eax; nOutBufferSize
0x1800bd522  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOutBuffer
0x1800bd527  xor     r9d, r9d; nInBufferSize
0x1800bd52a  xor     r8d, r8d; lpInBuffer
0x1800bd52d  mov     edx, 4C4210D8h; dwIoControlCode
0x1800bd532  mov     rcx, rdi; hDevice
0x1800bd535  call    cs:__imp_DeviceIoControl
0x1800bd53c  nop     dword ptr [rax+rax+00h]
0x1800bd541  test    eax, eax
0x1800bd543  jz      loc_1800BD46C
0x1800bd549  mov     eax, [rsp+78h+BytesReturned]
0x1800bd54d  xor     ebx, ebx
0x1800bd54f  mov     [rsi], eax
0x1800bd551  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800bd555  jz      short loc_1800BD566
0x1800bd557  mov     rcx, rdi; hObject
0x1800bd55a  call    cs:__imp_CloseHandle
0x1800bd561  nop     dword ptr [rax+rax+00h]
0x1800bd566  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd56d  cmp     rcx, r12
0x1800bd570  jz      short loc_1800BD590
0x1800bd572  test    byte ptr [rcx+1Ch], 20h
0x1800bd576  jz      short loc_1800BD590
0x1800bd578  mov     edx, 188h
0x1800bd57d  mov     r9d, ebx
0x1800bd580  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800bd587  mov     rcx, [rcx+10h]
0x1800bd58b  call    WPP_SF_d
0x1800bd590  mov     eax, ebx
0x1800bd592  mov     rcx, [rsp+78h+var_20]
0x1800bd597  xor     rcx, rsp; StackCookie
0x1800bd59a  call    __security_check_cookie
0x1800bd59f  lea     r11, [rsp+78h+var_18]
0x1800bd5a4  mov     rbx, [r11+30h]
0x1800bd5a8  mov     rsi, [r11+38h]
0x1800bd5ac  mov     rsp, r11
0x1800bd5af  pop     r14
0x1800bd5b1  pop     r12
0x1800bd5b3  pop     rdi
0x1800bd5b4  retn
0x180126d30  push    rbp
0x180126d32  sub     rsp, 40h
0x180126d36  mov     rbp, rdx
0x180126d39  mov     rcx, [rbp+40h]; hObject
0x180126d3d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180126d41  jz      short loc_180126D57
0x180126d43  call    cs:__imp_CloseHandle
0x180126d4a  nop     dword ptr [rax+rax+00h]
0x180126d4f  mov     qword ptr [rbp+40h], 0FFFFFFFFFFFFFFFFh
0x180126d57  add     rsp, 40h
0x180126d5b  pop     rbp
0x180126d5c  retn
```
