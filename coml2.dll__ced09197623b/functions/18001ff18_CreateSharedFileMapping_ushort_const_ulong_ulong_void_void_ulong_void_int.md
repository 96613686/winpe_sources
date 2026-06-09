# CreateSharedFileMapping(ushort const *,ulong,ulong,void *,void *,ulong,void * *,int *)

- ea: `0x18001ff18`
- end: `0x18002003b`
- name: `?CreateSharedFileMapping@@YAPEAXPEBGKKPEAX1KPEAPEAXPEAH@Z`
- size: `291`
- prototype: `void *(const unsigned __int16 *, unsigned int, unsigned int, void *, void *, unsigned int, void **, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001fd94`

## callees

- `0x18001ff18`
- `0x18003e5a8`
- `0x18004a0e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffa9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ffe4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ffe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ffdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ffdc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001ff5c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001ff5c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18001ff9b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18001ff9b`

## string_xrefs

- `0x18001ffc0`: `onecore\internal\com\inc\combase\smcreate.hxx`
- `0x18001fffc`: `onecore\internal\com\inc\combase\smcreate.hxx`

## pseudocode

```c
HANDLE __fastcall CreateSharedFileMapping(
        const unsigned __int16 *a1,
        DWORD dwMaximumSizeLow,
        __int64 a3,
        void *a4,
        void *a5,
        unsigned int a6,
        void **a7,
        int *a8)
{
  HANDLE v8; // rdi
  BOOL v9; // ebp
  void *v10; // rsi
  const char *LastError; // rbx
  struct _SECURITY_ATTRIBUTES v13; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)&v13.nLength = 24;
  *(_QWORD *)&v13.bInheritHandle = 0;
  v13.lpSecurityDescriptor = a5;
  v8 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &v13, 0x4000004u, 0, dwMaximumSizeLow, 0);
  if ( v8 )
  {
    v9 = GetLastError() == 0;
    v10 = MapViewOfFileEx(v8, 2u, 0, 0, 0, 0);
    if ( !v10 )
    {
      LastError = (const char *)GetLastError();
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\internal\\com\\inc\\combase\\smcreate.hxx",
        LastError,
        (unsigned int)"Name:%ws",
        0);
      CloseHandle(v8);
      SetLastError((DWORD)LastError);
      v8 = 0;
    }
  }
  else
  {
    v10 = 0;
    v9 = 1;
    wil::details::in1diag3::Log_GetLastErrorMsg(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\internal\\com\\inc\\combase\\smcreate.hxx",
      "Name:%ws",
      0);
  }
  if ( a8 )
    *a8 = v9;
  *a7 = v10;
  return v8;
}

```

## disassembly

```asm
0x18001ff18  mov     r11, rsp
0x18001ff1b  push    rbx
0x18001ff1c  push    rbp
0x18001ff1d  push    rsi
0x18001ff1e  push    rdi
0x18001ff1f  sub     rsp, 58h
0x18001ff23  mov     rax, [rsp+78h+arg_20]
0x18001ff2b  xor     r9d, r9d; dwMaximumSizeHigh
0x18001ff2e  mov     qword ptr [r11-50h], 0
0x18001ff36  mov     r8d, 4000004h; flProtect
0x18001ff3c  mov     [rsp+78h+dwMaximumSizeLow], edx; dwMaximumSizeLow
0x18001ff40  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001ff44  lea     rdx, [r11-48h]; lpFileMappingAttributes
0x18001ff48  mov     qword ptr [r11-48h], 18h
0x18001ff50  mov     qword ptr [r11-38h], 0
0x18001ff58  mov     [r11-40h], rax
0x18001ff5c  call    cs:__imp_CreateFileMappingW
0x18001ff62  mov     rdi, rax
0x18001ff65  test    rax, rax
0x18001ff68  jz      loc_18001FFEE
0x18001ff6e  call    cs:__imp_GetLastError
0x18001ff74  xor     ebp, ebp
0x18001ff76  mov     [rsp+78h+lpBaseAddress], 0; lpBaseAddress
0x18001ff7f  test    eax, eax
0x18001ff81  mov     qword ptr [rsp+78h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18001ff8a  mov     rcx, rdi; hFileMappingObject
0x18001ff8d  setz    bpl
0x18001ff91  xor     r9d, r9d; dwFileOffsetLow
0x18001ff94  xor     r8d, r8d; dwFileOffsetHigh
0x18001ff97  lea     edx, [r9+2]; dwDesiredAccess
0x18001ff9b  call    cs:__imp_MapViewOfFileEx
0x18001ffa1  mov     rsi, rax
0x18001ffa4  test    rax, rax
0x18001ffa7  jnz     short loc_180020015
0x18001ffa9  call    cs:__imp_GetLastError
0x18001ffaf  mov     rcx, [rsp+78h]; this
0x18001ffb4  lea     r9, aNameWs; "Name:%ws"
0x18001ffbb  mov     [rsp+78h+lpBaseAddress], rsi; char *
0x18001ffc0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\combase\\s"...
0x18001ffc7  mov     qword ptr [rsp+78h+dwMaximumSizeLow], r9; unsigned int
0x18001ffcc  lea     edx, [rsi+32h]; void *
0x18001ffcf  mov     r9d, eax; char *
0x18001ffd2  mov     ebx, eax
0x18001ffd4  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001ffd9  mov     rcx, rdi; hObject
0x18001ffdc  call    cs:__imp_CloseHandle
0x18001ffe2  mov     ecx, ebx; dwErrCode
0x18001ffe4  call    cs:__imp_SetLastError
0x18001ffea  xor     edi, edi
0x18001ffec  jmp     short loc_180020015
0x18001ffee  mov     rcx, [rsp+78h]; this
0x18001fff3  lea     r9, aNameWs; "Name:%ws"
0x18001fffa  xor     esi, esi
0x18001fffc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\combase\\s"...
0x180020003  mov     ebp, 1
0x180020008  mov     qword ptr [rsp+78h+dwMaximumSizeLow], rsi; char *
0x18002000d  lea     edx, [rbp+39h]; void *
0x180020010  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180020015  mov     rax, [rsp+78h+arg_38]
0x18002001d  test    rax, rax
0x180020020  jz      short loc_180020024
0x180020022  mov     [rax], ebp
0x180020024  mov     rax, [rsp+78h+arg_30]
0x18002002c  mov     [rax], rsi
0x18002002f  mov     rax, rdi
0x180020032  add     rsp, 58h
0x180020036  pop     rdi
0x180020037  pop     rsi
0x180020038  pop     rbp
0x180020039  pop     rbx
0x18002003a  retn
```
