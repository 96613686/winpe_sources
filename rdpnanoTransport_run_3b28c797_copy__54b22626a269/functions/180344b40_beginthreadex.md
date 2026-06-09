# _beginthreadex

- ea: `0x180344b40`
- end: `0x180344c1e`
- name: `_beginthreadex`
- size: `222`
- prototype: `uintptr_t __cdecl(void *Security, unsigned int StackSize, _beginthreadex_proc_type StartAddress, void *ArgList, unsigned int InitFlag, unsigned int *ThrdAddr)`
- caller_count: `14`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180044310`
- `0x18004b7a0`
- `0x18004f4a4`
- `0x18010db30`
- `0x18011634c`
- `0x180118a9c`
- `0x180126b30`
- `0x180129620`
- `0x180140930`
- `0x180141730`
- `0x180142ce4`
- `0x180143360`
- `0x1801729e0`
- `0x1802fc130`

## callees

- `0x18033f0ac`
- `0x18033f1e8`
- `0x18033f258`
- `0x180344adc`
- `0x180344b40`
- `0x1803566d0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180344bb0`
- `KERNEL32!CreateThread` at `0x180344bb0`
- `KERNEL32!CloseHandle` at `0x180344bd4`
- `KERNEL32!CloseHandle` at `0x180344bd4`
- `KERNEL32!GetLastError` at `0x180344bbe`
- `KERNEL32!GetLastError` at `0x180344bbe`
- `KERNEL32!FreeLibrary` at `0x180344be3`
- `KERNEL32!FreeLibrary` at `0x180344be3`

## pseudocode

```c
uintptr_t __cdecl beginthreadex(
        void *Security,
        unsigned int StackSize,
        _beginthreadex_proc_type StartAddress,
        void *ArgList,
        unsigned int InitFlag,
        unsigned int *ThrdAddr)
{
  uintptr_t v6; // rdi
  SIZE_T v7; // rsi
  _QWORD *thread_parameter; // rbx
  HANDLE v11; // rdx
  DWORD LastError; // eax
  void *v13; // rcx
  HMODULE v14; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  v7 = StackSize;
  if ( StartAddress )
  {
    thread_parameter = (_QWORD *)create_thread_parameter((LPCWSTR)StartAddress);
    if ( thread_parameter )
    {
      ThreadId = 0;
      v11 = CreateThread(
              (LPSECURITY_ATTRIBUTES)Security,
              v7,
              thread_start_unsigned_int____cdecl___void____1_,
              thread_parameter,
              InitFlag,
              &ThreadId);
      if ( v11 )
      {
        if ( ThrdAddr )
          *ThrdAddr = ThreadId;
        return (uintptr_t)v11;
      }
      else
      {
        LastError = GetLastError();
        _acrt_errno_map_os_error(LastError);
        v13 = (void *)thread_parameter[2];
        if ( v13 )
          CloseHandle(v13);
        v14 = (HMODULE)thread_parameter[3];
        if ( v14 )
          FreeLibrary(v14);
        free_base(thread_parameter);
      }
    }
    return v6;
  }
  else
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 0;
  }
}

```

## disassembly

```asm
0x180344b40  mov     [rsp+arg_0], rbx
0x180344b45  mov     [rsp+arg_8], rbp
0x180344b4a  mov     [rsp+arg_18], rsi
0x180344b4f  push    rdi
0x180344b50  sub     rsp, 30h
0x180344b54  xor     edi, edi
0x180344b56  mov     esi, edx
0x180344b58  mov     rbp, rcx
0x180344b5b  test    r8, r8
0x180344b5e  jnz     short loc_180344B77
0x180344b60  call    _errno
0x180344b65  mov     dword ptr [rax], 16h
0x180344b6b  call    _invalid_parameter_noinfo
0x180344b70  xor     eax, eax
0x180344b72  jmp     loc_180344C09
0x180344b77  mov     rdx, r9
0x180344b7a  mov     rcx, r8; lpModuleName
0x180344b7d  call    create_thread_parameter
0x180344b82  mov     rbx, rax
0x180344b85  test    rax, rax
0x180344b88  jz      short loc_180344C06
0x180344b8a  lea     rax, [rsp+38h+ThreadId]
0x180344b8f  mov     [rsp+38h+ThreadId], edi
0x180344b93  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180344b98  lea     r8, thread_start_unsigned_int____cdecl___void____1_; lpStartAddress
0x180344b9f  mov     eax, [rsp+38h+InitFlag]
0x180344ba3  mov     rdx, rsi; dwStackSize
0x180344ba6  mov     r9, rbx; lpParameter
0x180344ba9  mov     [rsp+38h+dwCreationFlags], eax; dwCreationFlags
0x180344bad  mov     rcx, rbp; lpThreadAttributes
0x180344bb0  call    cs:__imp_CreateThread
0x180344bb6  mov     rdx, rax
0x180344bb9  test    rax, rax
0x180344bbc  jnz     short loc_180344BF3
0x180344bbe  call    cs:__imp_GetLastError
0x180344bc4  mov     ecx, eax
0x180344bc6  call    __acrt_errno_map_os_error
0x180344bcb  mov     rcx, [rbx+10h]; hObject
0x180344bcf  test    rcx, rcx
0x180344bd2  jz      short loc_180344BDA
0x180344bd4  call    cs:__imp_CloseHandle
0x180344bda  mov     rcx, [rbx+18h]; hLibModule
0x180344bde  test    rcx, rcx
0x180344be1  jz      short loc_180344BE9
0x180344be3  call    cs:__imp_FreeLibrary
0x180344be9  mov     rcx, rbx; Block
0x180344bec  call    _free_base
0x180344bf1  jmp     short loc_180344C06
0x180344bf3  mov     rcx, [rsp+38h+ThrdAddr]
0x180344bf8  test    rcx, rcx
0x180344bfb  jz      short loc_180344C03
0x180344bfd  mov     eax, [rsp+38h+ThreadId]
0x180344c01  mov     [rcx], eax
0x180344c03  mov     rdi, rdx
0x180344c06  mov     rax, rdi
0x180344c09  mov     rbx, [rsp+38h+arg_0]
0x180344c0e  mov     rbp, [rsp+38h+arg_8]
0x180344c13  mov     rsi, [rsp+38h+arg_18]
0x180344c18  add     rsp, 30h
0x180344c1c  pop     rdi
0x180344c1d  retn
```
