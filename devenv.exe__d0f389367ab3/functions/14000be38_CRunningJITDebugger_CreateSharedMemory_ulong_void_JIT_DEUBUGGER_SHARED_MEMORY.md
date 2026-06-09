# CRunningJITDebugger::CreateSharedMemory(ulong,void * *,JIT_DEUBUGGER_SHARED_MEMORY * *)

- ea: `0x14000be38`
- end: `0x14000bfa8`
- name: `?CreateSharedMemory@CRunningJITDebugger@@CAJKPEAPEAXPEAPEAUJIT_DEUBUGGER_SHARED_MEMORY@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(SIZE_T dwNumberOfBytesToMap, void **, struct JIT_DEUBUGGER_SHARED_MEMORY **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000bb50`

## callees

- `0x140001020`
- `0x14000be38`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x14000bf47`
- `KERNEL32!MapViewOfFile` at `0x14000bf47`
- `KERNEL32!CreateFileMappingW` at `0x14000bef3`
- `KERNEL32!CreateFileMappingW` at `0x14000bef3`
- `KERNEL32!GetCurrentProcessId` at `0x14000beb7`
- `KERNEL32!GetCurrentProcessId` at `0x14000beb7`
- `KERNEL32!CloseHandle` at `0x14000bf73`
- `KERNEL32!CloseHandle` at `0x14000bf73`
- `KERNEL32!GetLastError` at `0x14000bf01`
- `KERNEL32!GetLastError` at `0x14000bf21`
- `KERNEL32!GetLastError` at `0x14000bf52`
- `KERNEL32!GetLastError` at `0x14000bf01`
- `KERNEL32!GetLastError` at `0x14000bf21`
- `KERNEL32!GetLastError` at `0x14000bf52`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x14000bece`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x14000bece`

## pseudocode

```c
__int64 __fastcall CRunningJITDebugger::CreateSharedMemory(
        SIZE_T dwNumberOfBytesToMap,
        void **a2,
        struct JIT_DEUBUGGER_SHARED_MEMORY **a3)
{
  SIZE_T v5; // rbp
  DWORD CurrentProcessId; // eax
  HANDLE FileMappingW; // rdi
  signed int v8; // eax
  signed int v9; // ecx
  __int64 result; // rax
  unsigned int v11; // ebx
  struct JIT_DEUBUGGER_SHARED_MEMORY *v12; // rax
  signed int LastError; // eax
  signed int v14; // ecx
  WCHAR Name[35]; // [rsp+30h] [rbp-88h] BYREF
  __int128 v16; // [rsp+76h] [rbp-42h]

  *a2 = 0;
  *a3 = 0;
  wcscpy(Name, L"Local\\Microsoft_VS80_JIT_Debugger-");
  v16 = 0;
  v5 = (unsigned int)dwNumberOfBytesToMap;
  CurrentProcessId = GetCurrentProcessId();
  _ultow_s(CurrentProcessId, &Name[34], 9u, 16);
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x4000u, Name);
  if ( FileMappingW )
  {
    if ( GetLastError() == 183 )
    {
      v11 = -2147024713;
    }
    else
    {
      v12 = (struct JIT_DEUBUGGER_SHARED_MEMORY *)MapViewOfFile(FileMappingW, 2u, 0, 0, v5);
      if ( v12 )
      {
        *a2 = FileMappingW;
        *a3 = v12;
        return 0;
      }
      LastError = GetLastError();
      v11 = -2147467259;
      v14 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v14 = LastError;
      if ( v14 < 0 )
        v11 = v14;
    }
    CloseHandle(FileMappingW);
    return v11;
  }
  v8 = GetLastError();
  v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v8 <= 0 )
    v9 = v8;
  result = 2147500037LL;
  if ( v9 < 0 )
    return (unsigned int)v9;
  return result;
}

```

## disassembly

```asm
0x14000be38  mov     [rsp+arg_18], rbx
0x14000be3d  push    rbp
0x14000be3e  push    rsi
0x14000be3f  push    rdi
0x14000be40  sub     rsp, 0A0h
0x14000be47  mov     rax, cs:__security_cookie
0x14000be4e  xor     rax, rsp
0x14000be51  mov     [rsp+0B8h+var_28], rax
0x14000be59  and     qword ptr [rdx], 0
0x14000be5d  mov     rsi, r8
0x14000be60  and     qword ptr [r8], 0
0x14000be64  mov     rbx, rdx
0x14000be67  movaps  xmm0, xmmword ptr cs:aLocalMicrosoft; "Local\\Microsoft_VS80_JIT_Debugger-"
0x14000be6e  movaps  xmm1, xmmword ptr cs:aLocalMicrosoft+10h; "crosoft_VS80_JIT_Debugger-"
0x14000be75  mov     eax, dword ptr cs:aLocalMicrosoft+40h; "r-"
0x14000be7b  movaps  xmmword ptr [rsp+0B8h+Name], xmm0
0x14000be80  movaps  xmm0, xmmword ptr cs:aLocalMicrosoft+20h; "VS80_JIT_Debugger-"
0x14000be87  movaps  [rsp+0B8h+var_68], xmm0
0x14000be8c  xorps   xmm0, xmm0
0x14000be8f  movaps  [rsp+0B8h+var_78], xmm1
0x14000be94  movaps  xmm1, xmmword ptr cs:aLocalMicrosoft+30h; "_Debugger-"
0x14000be9b  mov     [rsp+0B8h+var_48], eax
0x14000be9f  movzx   eax, word ptr cs:aLocalMicrosoft+44h; ""
0x14000bea6  movups  [rsp+0B8h+var_42], xmm0
0x14000beab  mov     ebp, ecx
0x14000bead  movaps  [rsp+0B8h+var_58], xmm1
0x14000beb2  mov     [rsp+0B8h+Buffer], ax
0x14000beb7  call    cs:__imp_GetCurrentProcessId
0x14000bebd  mov     r9d, 10h; Radix
0x14000bec3  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x14000bec8  mov     ecx, eax; Value
0x14000beca  lea     r8d, [r9-7]; BufferCount
0x14000bece  call    cs:__imp__ultow_s
0x14000bed4  xor     r9d, r9d; dwMaximumSizeHigh
0x14000bed7  lea     rax, [rsp+0B8h+Name]
0x14000bedc  mov     [rsp+0B8h+lpName], rax; lpName
0x14000bee1  xor     edx, edx; lpFileMappingAttributes
0x14000bee3  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x14000bee7  mov     [rsp+0B8h+dwMaximumSizeLow], 4000h; dwMaximumSizeLow
0x14000beef  lea     r8d, [r9+4]; flProtect
0x14000bef3  call    cs:__imp_CreateFileMappingW
0x14000bef9  mov     rdi, rax
0x14000befc  test    rax, rax
0x14000beff  jnz     short loc_14000BF21
0x14000bf01  call    cs:__imp_GetLastError
0x14000bf07  movzx   ecx, ax
0x14000bf0a  or      ecx, 80070000h
0x14000bf10  test    eax, eax
0x14000bf12  cmovle  ecx, eax
0x14000bf15  mov     eax, 80004005h
0x14000bf1a  test    ecx, ecx
0x14000bf1c  cmovs   eax, ecx
0x14000bf1f  jmp     short loc_14000BF85
0x14000bf21  call    cs:__imp_GetLastError
0x14000bf27  cmp     eax, 0B7h
0x14000bf2c  jnz     short loc_14000BF35
0x14000bf2e  mov     ebx, 800700B7h
0x14000bf33  jmp     short loc_14000BF70
0x14000bf35  xor     r9d, r9d; dwFileOffsetLow
0x14000bf38  mov     qword ptr [rsp+0B8h+dwMaximumSizeLow], rbp; dwNumberOfBytesToMap
0x14000bf3d  xor     r8d, r8d; dwFileOffsetHigh
0x14000bf40  mov     rcx, rdi; hFileMappingObject
0x14000bf43  lea     edx, [r9+2]; dwDesiredAccess
0x14000bf47  call    cs:__imp_MapViewOfFile
0x14000bf4d  test    rax, rax
0x14000bf50  jnz     short loc_14000BF7D
0x14000bf52  call    cs:__imp_GetLastError
0x14000bf58  movzx   ecx, ax
0x14000bf5b  mov     ebx, 80004005h
0x14000bf60  or      ecx, 80070000h
0x14000bf66  test    eax, eax
0x14000bf68  cmovle  ecx, eax
0x14000bf6b  test    ecx, ecx
0x14000bf6d  cmovs   ebx, ecx
0x14000bf70  mov     rcx, rdi; hObject
0x14000bf73  call    cs:__imp_CloseHandle
0x14000bf79  mov     eax, ebx
0x14000bf7b  jmp     short loc_14000BF85
0x14000bf7d  mov     [rbx], rdi
0x14000bf80  mov     [rsi], rax
0x14000bf83  xor     eax, eax
0x14000bf85  mov     rcx, [rsp+0B8h+var_28]
0x14000bf8d  xor     rcx, rsp; StackCookie
0x14000bf90  call    __security_check_cookie
0x14000bf95  mov     rbx, [rsp+0B8h+arg_18]
0x14000bf9d  add     rsp, 0A0h
0x14000bfa4  pop     rdi
0x14000bfa5  pop     rsi
0x14000bfa6  pop     rbp
0x14000bfa7  retn
```
