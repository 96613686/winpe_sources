# sub_1801B5CDC

- ea: `0x1801b5cdc`
- end: `0x1801b5dba`
- name: `sub_1801B5CDC`
- size: `222`
- prototype: `__int64 __usercall@<rax>(LPSECURITY_ATTRIBUTES lpThreadAttributes@<rcx>, SIZE_T dwStackSize@<rdx>, LPCWSTR lpModuleName@<r8>, DWORD, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c150`
- `0x180256910`

## callees

- `0x1801b4110`
- `0x1801b5c74`
- `0x1801b5cdc`
- `0x1801be864`
- `0x1801be8f0`
- `0x1801cba40`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1801b5d4c`
- `KERNEL32!CreateThread` at `0x1801b5d4c`
- `KERNEL32!GetLastError` at `0x1801b5d5a`
- `KERNEL32!GetLastError` at `0x1801b5d5a`
- `KERNEL32!CloseHandle` at `0x1801b5d70`
- `KERNEL32!CloseHandle` at `0x1801b5d70`
- `KERNEL32!FreeLibrary` at `0x1801b5d7f`
- `KERNEL32!FreeLibrary` at `0x1801b5d7f`

## pseudocode

```c
HANDLE __fastcall sub_1801B5CDC(
        LPSECURITY_ATTRIBUTES lpThreadAttributes,
        SIZE_T dwStackSize,
        LPCWSTR lpModuleName,
        __int64 a4,
        DWORD dwCreationFlags,
        DWORD *a6)
{
  __int64 v6; // rdi
  SIZE_T v7; // rsi
  _QWORD *v10; // rbx
  HANDLE v11; // rdx
  DWORD LastError; // eax
  void *v13; // rcx
  HMODULE v14; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  v7 = (unsigned int)dwStackSize;
  if ( lpModuleName )
  {
    v10 = (_QWORD *)sub_1801B5C74(lpModuleName);
    if ( v10 )
    {
      ThreadId = 0;
      v11 = CreateThread(lpThreadAttributes, v7, StartAddress, v10, dwCreationFlags, &ThreadId);
      if ( v11 )
      {
        if ( a6 )
          *a6 = ThreadId;
        return v11;
      }
      else
      {
        LastError = GetLastError();
        sub_1801BE864(LastError);
        v13 = (void *)v10[2];
        if ( v13 )
          CloseHandle(v13);
        v14 = (HMODULE)v10[3];
        if ( v14 )
          FreeLibrary(v14);
        sub_1801CBA40(v10);
      }
    }
    return (HANDLE)v6;
  }
  else
  {
    *(_DWORD *)sub_1801BE8F0() = 22;
    invalid_parameter_noinfo();
    return 0;
  }
}

```

## disassembly

```asm
0x1801b5cdc  mov     [rsp+arg_0], rbx
0x1801b5ce1  mov     [rsp+arg_8], rbp
0x1801b5ce6  mov     [rsp+arg_18], rsi
0x1801b5ceb  push    rdi
0x1801b5cec  sub     rsp, 30h
0x1801b5cf0  xor     edi, edi
0x1801b5cf2  mov     esi, edx
0x1801b5cf4  mov     rbp, rcx
0x1801b5cf7  test    r8, r8
0x1801b5cfa  jnz     short loc_1801B5D13
0x1801b5cfc  call    sub_1801BE8F0
0x1801b5d01  mov     dword ptr [rax], 16h
0x1801b5d07  call    _invalid_parameter_noinfo
0x1801b5d0c  xor     eax, eax
0x1801b5d0e  jmp     loc_1801B5DA5
0x1801b5d13  mov     rdx, r9
0x1801b5d16  mov     rcx, r8; lpModuleName
0x1801b5d19  call    sub_1801B5C74
0x1801b5d1e  mov     rbx, rax
0x1801b5d21  test    rax, rax
0x1801b5d24  jz      short loc_1801B5DA2
0x1801b5d26  lea     rax, [rsp+38h+ThreadId]
0x1801b5d2b  mov     [rsp+38h+ThreadId], edi
0x1801b5d2f  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1801b5d34  lea     r8, StartAddress; lpStartAddress
0x1801b5d3b  mov     eax, [rsp+38h+arg_20]
0x1801b5d3f  mov     rdx, rsi; dwStackSize
0x1801b5d42  mov     r9, rbx; lpParameter
0x1801b5d45  mov     [rsp+38h+dwCreationFlags], eax; dwCreationFlags
0x1801b5d49  mov     rcx, rbp; lpThreadAttributes
0x1801b5d4c  call    cs:CreateThread
0x1801b5d52  mov     rdx, rax
0x1801b5d55  test    rax, rax
0x1801b5d58  jnz     short loc_1801B5D8F
0x1801b5d5a  call    cs:__imp_GetLastError
0x1801b5d60  mov     ecx, eax
0x1801b5d62  call    sub_1801BE864
0x1801b5d67  mov     rcx, [rbx+10h]; hObject
0x1801b5d6b  test    rcx, rcx
0x1801b5d6e  jz      short loc_1801B5D76
0x1801b5d70  call    cs:__imp_CloseHandle
0x1801b5d76  mov     rcx, [rbx+18h]; hLibModule
0x1801b5d7a  test    rcx, rcx
0x1801b5d7d  jz      short loc_1801B5D85
0x1801b5d7f  call    cs:__imp_FreeLibrary
0x1801b5d85  mov     rcx, rbx; lpMem
0x1801b5d88  call    sub_1801CBA40
0x1801b5d8d  jmp     short loc_1801B5DA2
0x1801b5d8f  mov     rcx, [rsp+38h+arg_28]
0x1801b5d94  test    rcx, rcx
0x1801b5d97  jz      short loc_1801B5D9F
0x1801b5d99  mov     eax, [rsp+38h+ThreadId]
0x1801b5d9d  mov     [rcx], eax
0x1801b5d9f  mov     rdi, rdx
0x1801b5da2  mov     rax, rdi
0x1801b5da5  mov     rbx, [rsp+38h+arg_0]
0x1801b5daa  mov     rbp, [rsp+38h+arg_8]
0x1801b5daf  mov     rsi, [rsp+38h+arg_18]
0x1801b5db4  add     rsp, 30h
0x1801b5db8  pop     rdi
0x1801b5db9  retn
```
