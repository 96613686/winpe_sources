# OutputDebugStringDBWIN(ushort const *,...)

- ea: `0x180002994`
- end: `0x180002b3d`
- name: `?OutputDebugStringDBWIN@@YAXPEBGZZ`
- size: `425`
- prototype: `void(wchar_t *Format, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800026d0`

## callees

- `0x180002994`
- `0x180012b02`
- `0x180012b40`

## import_xrefs

- `msvcrt!_vsnwprintf_s` at `0x1800029f0`
- `msvcrt!_vsnwprintf_s` at `0x1800029f0`
- `msvcrt!wcstombs` at `0x180002acb`
- `msvcrt!wcstombs` at `0x180002acb`
- `msvcrt!sprintf_s` at `0x180002ae6`
- `msvcrt!sprintf_s` at `0x180002ae6`
- `KERNEL32!MapViewOfFile` at `0x180002a89`
- `KERNEL32!MapViewOfFile` at `0x180002a89`
- `KERNEL32!CreateFileMappingW` at `0x180002a61`
- `KERNEL32!CreateFileMappingW` at `0x180002a61`
- `KERNEL32!GetCurrentProcessId` at `0x180002aa3`
- `KERNEL32!GetCurrentProcessId` at `0x180002aa3`
- `KERNEL32!CloseHandle` at `0x180002af8`
- `KERNEL32!CloseHandle` at `0x180002b01`
- `KERNEL32!CloseHandle` at `0x180002b0f`
- `KERNEL32!CloseHandle` at `0x180002b18`
- `KERNEL32!CloseHandle` at `0x180002af8`
- `KERNEL32!CloseHandle` at `0x180002b01`
- `KERNEL32!CloseHandle` at `0x180002b0f`
- `KERNEL32!CloseHandle` at `0x180002b18`
- `KERNEL32!SetEvent` at `0x180002aef`
- `KERNEL32!SetEvent` at `0x180002aef`
- `KERNEL32!OpenEventW` at `0x180002a0c`
- `KERNEL32!OpenEventW` at `0x180002a2a`
- `KERNEL32!OpenEventW` at `0x180002a0c`
- `KERNEL32!OpenEventW` at `0x180002a2a`
- `KERNEL32!WaitForSingleObject` at `0x180002a9d`
- `KERNEL32!WaitForSingleObject` at `0x180002a9d`

## string_xrefs

- `0x1800029f8`: `DBWIN_BUFFER_READY`
- `0x180002a20`: `DBWIN_DATA_READY`

## pseudocode

```c
void OutputDebugStringDBWIN(wchar_t *Format, ...)
{
  HANDLE v1; // rbx
  HANDLE v2; // rdi
  void *v3; // rcx
  HANDLE FileMappingW; // rax
  void *v5; // rsi
  char *v6; // r14
  char Dest[512]; // [rsp+40h] [rbp-628h] BYREF
  wchar_t Source[504]; // [rsp+240h] [rbp-428h] BYREF
  va_list va; // [rsp+678h] [rbp+10h] BYREF

  va_start(va, Format);
  _vsnwprintf_s(Source, 0x1F4u, 0x1F3u, Format, va);
  Source[499] = 0;
  v1 = OpenEventW(2u, 0, L"DBWIN_BUFFER_READY");
  if ( v1 )
  {
    v2 = OpenEventW(2u, 0, L"DBWIN_DATA_READY");
    if ( v2 )
    {
      FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x1000u, L"DBWIN_BUFFER");
      v5 = FileMappingW;
      if ( !FileMappingW || (v6 = (char *)MapViewOfFile(FileMappingW, 2u, 0, 0, 0x200u)) == 0 )
      {
        CloseHandle(v1);
        v3 = v2;
        goto LABEL_8;
      }
      WaitForSingleObject(v1, 0xFFFFFFFF);
      *(_DWORD *)v6 = GetCurrentProcessId();
      memset_0(Dest, 0, 0x1F4u);
      wcstombs(Dest, Source, 0x1F4u);
      sprintf_s(v6 + 4, 0x1FCu, "%s", Dest);
      SetEvent(v2);
      CloseHandle(v5);
      CloseHandle(v2);
    }
    v3 = v1;
LABEL_8:
    CloseHandle(v3);
  }
}

```

## disassembly

```asm
0x180002994  mov     r11, rsp
0x180002997  mov     [r11+8], rcx
0x18000299b  mov     [r11+10h], rdx
0x18000299f  mov     [r11+18h], r8
0x1800029a3  mov     [r11+20h], r9
0x1800029a7  push    rbx
0x1800029a8  push    rsi
0x1800029a9  push    rdi
0x1800029aa  push    r14
0x1800029ac  push    r15
0x1800029ae  sub     rsp, 640h
0x1800029b5  mov     rax, cs:__security_cookie
0x1800029bc  xor     rax, rsp
0x1800029bf  mov     [rsp+668h+var_38], rax
0x1800029c7  mov     r8d, 1F3h; MaxCount
0x1800029cd  mov     [rsp+668h+var_638], 0
0x1800029d6  lea     rax, [r11+10h]
0x1800029da  mov     r9, rcx; Format
0x1800029dd  lea     rcx, [r11-428h]; Buffer
0x1800029e4  mov     [rsp+668h+ArgList], rax; ArgList
0x1800029e9  lea     r15d, [r8+1]
0x1800029ed  mov     edx, r15d; BufferCount
0x1800029f0  call    cs:__imp__vsnwprintf_s
0x1800029f6  xor     eax, eax
0x1800029f8  lea     r8, Name; "DBWIN_BUFFER_READY"
0x1800029ff  xor     edx, edx; bInheritHandle
0x180002a01  mov     [rsp+668h+var_42], ax
0x180002a09  lea     ecx, [rax+2]; dwDesiredAccess
0x180002a0c  call    cs:__imp_OpenEventW
0x180002a12  mov     rbx, rax
0x180002a15  test    rax, rax
0x180002a18  jz      loc_180002B1E
0x180002a1e  xor     edx, edx; bInheritHandle
0x180002a20  lea     r8, aDbwinDataReady; "DBWIN_DATA_READY"
0x180002a27  lea     ecx, [rdx+2]; dwDesiredAccess
0x180002a2a  call    cs:__imp_OpenEventW
0x180002a30  mov     rdi, rax
0x180002a33  test    rax, rax
0x180002a36  jnz     short loc_180002A40
0x180002a38  mov     rcx, rbx
0x180002a3b  jmp     loc_180002B18
0x180002a40  xor     r9d, r9d; dwMaximumSizeHigh
0x180002a43  lea     rax, aDbwinBuffer; "DBWIN_BUFFER"
0x180002a4a  mov     [rsp+668h+lpName], rax; lpName
0x180002a4f  xor     edx, edx; lpFileMappingAttributes
0x180002a51  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180002a55  mov     dword ptr [rsp+668h+ArgList], 1000h; dwMaximumSizeLow
0x180002a5d  lea     r8d, [r9+4]; flProtect
0x180002a61  call    cs:__imp_CreateFileMappingW
0x180002a67  mov     rsi, rax
0x180002a6a  test    rax, rax
0x180002a6d  jz      loc_180002B0C
0x180002a73  xor     r9d, r9d; dwFileOffsetLow
0x180002a76  mov     [rsp+668h+ArgList], 200h; dwNumberOfBytesToMap
0x180002a7f  xor     r8d, r8d; dwFileOffsetHigh
0x180002a82  mov     rcx, rax; hFileMappingObject
0x180002a85  lea     edx, [r9+2]; dwDesiredAccess
0x180002a89  call    cs:__imp_MapViewOfFile
0x180002a8f  mov     r14, rax
0x180002a92  test    rax, rax
0x180002a95  jz      short loc_180002B0C
0x180002a97  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002a9a  mov     rcx, rbx; hHandle
0x180002a9d  call    cs:__imp_WaitForSingleObject
0x180002aa3  call    cs:__imp_GetCurrentProcessId
0x180002aa9  mov     r8, r15; Size
0x180002aac  lea     rcx, [rsp+668h+Dest]; void *
0x180002ab1  xor     edx, edx; Val
0x180002ab3  mov     [r14], eax
0x180002ab6  call    memset_0
0x180002abb  mov     r8, r15; MaxCount
0x180002abe  lea     rdx, [rsp+668h+Source]; Source
0x180002ac6  lea     rcx, [rsp+668h+Dest]; Dest
0x180002acb  call    cs:__imp_wcstombs
0x180002ad1  lea     rcx, [r14+4]; Buffer
0x180002ad5  mov     edx, 1FCh; BufferCount
0x180002ada  lea     r9, [rsp+668h+Dest]
0x180002adf  lea     r8, Format; "%s"
0x180002ae6  call    cs:__imp_sprintf_s
0x180002aec  mov     rcx, rdi; hEvent
0x180002aef  call    cs:__imp_SetEvent
0x180002af5  mov     rcx, rsi; hObject
0x180002af8  call    cs:__imp_CloseHandle
0x180002afe  mov     rcx, rdi; hObject
0x180002b01  call    cs:__imp_CloseHandle
0x180002b07  jmp     loc_180002A38
0x180002b0c  mov     rcx, rbx; hObject
0x180002b0f  call    cs:__imp_CloseHandle
0x180002b15  mov     rcx, rdi; hObject
0x180002b18  call    cs:__imp_CloseHandle
0x180002b1e  mov     rcx, [rsp+668h+var_38]
0x180002b26  xor     rcx, rsp; StackCookie
0x180002b29  call    __security_check_cookie
0x180002b2e  add     rsp, 640h
0x180002b35  pop     r15
0x180002b37  pop     r14
0x180002b39  pop     rdi
0x180002b3a  pop     rsi
0x180002b3b  pop     rbx
0x180002b3c  retn
```
