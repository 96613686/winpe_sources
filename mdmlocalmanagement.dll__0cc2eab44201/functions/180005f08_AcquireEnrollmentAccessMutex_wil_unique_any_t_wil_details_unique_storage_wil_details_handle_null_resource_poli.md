# AcquireEnrollmentAccessMutex(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x180005f08`
- end: `0x180005ff8`
- name: `?AcquireEnrollmentAccessMutex@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000632c`

## callees

- `0x180005f08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180005f22`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180005f22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005fbd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005fbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f85`

## pseudocode

```c
__int64 __fastcall AcquireEnrollmentAccessMutex(char *a1)
{
  char *MutexW; // rsi
  HANDLE v3; // rbp
  DWORD LastError; // ebx
  signed int v5; // eax
  unsigned int v6; // ebx
  DWORD v7; // eax
  char v9; // [rsp+20h] [rbp-38h] BYREF

  MutexW = (char *)CreateMutexW(0, 1, L"__MDM_LOCAL_MANAGEMENT_NAMED_MUTEX__");
  if ( a1 == &v9 )
  {
    if ( (unsigned __int64)(MutexW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(MutexW);
  }
  else
  {
    v3 = *(HANDLE *)a1;
    if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v3);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = MutexW;
  }
  if ( *(_QWORD *)a1 )
  {
    v6 = 0;
    v7 = WaitForSingleObject(*(HANDLE *)a1, 0x7530u);
    switch ( v7 )
    {
      case 0u:
        return v6;
      case 0x80u:
        return (unsigned int)-2147418113;
      case 0x102u:
        return (unsigned int)-2147023436;
    }
    if ( v7 != -1 )
      return (unsigned int)-2147418113;
  }
  v5 = GetLastError();
  v6 = v5;
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x180005f08  push    rbx
0x180005f0a  push    rbp
0x180005f0b  push    rsi
0x180005f0c  push    rdi
0x180005f0d  sub     rsp, 38h
0x180005f11  mov     rdi, rcx
0x180005f14  lea     r8, Name; "__MDM_LOCAL_MANAGEMENT_NAMED_MUTEX__"
0x180005f1b  xor     ecx, ecx; lpMutexAttributes
0x180005f1d  mov     edx, 1; bInitialOwner
0x180005f22  call    cs:__imp_CreateMutexW
0x180005f29  nop     dword ptr [rax+rax+00h]
0x180005f2e  mov     rsi, rax
0x180005f31  lea     rax, [rsp+58h+var_38]
0x180005f36  cmp     rdi, rax
0x180005f39  jz      short loc_180005F78
0x180005f3b  mov     rbp, [rdi]
0x180005f3e  lea     rdx, [rbp-1]
0x180005f42  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180005f46  ja      short loc_180005F73
0x180005f48  call    cs:__imp_GetLastError
0x180005f4f  nop     dword ptr [rax+rax+00h]
0x180005f54  mov     rcx, rbp; hObject
0x180005f57  mov     ebx, eax
0x180005f59  call    cs:__imp_CloseHandle
0x180005f60  nop     dword ptr [rax+rax+00h]
0x180005f65  mov     ecx, ebx; dwErrCode
0x180005f67  call    cs:__imp_SetLastError
0x180005f6e  nop     dword ptr [rax+rax+00h]
0x180005f73  mov     [rdi], rsi
0x180005f76  jmp     short loc_180005F91
0x180005f78  lea     rax, [rsi-1]
0x180005f7c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005f80  ja      short loc_180005F91
0x180005f82  mov     rcx, rsi; hObject
0x180005f85  call    cs:__imp_CloseHandle
0x180005f8c  nop     dword ptr [rax+rax+00h]
0x180005f91  mov     rcx, [rdi]; hHandle
0x180005f94  test    rcx, rcx
0x180005f97  jnz     short loc_180005FB6
0x180005f99  call    cs:__imp_GetLastError
0x180005fa0  nop     dword ptr [rax+rax+00h]
0x180005fa5  mov     ebx, eax
0x180005fa7  test    eax, eax
0x180005fa9  jle     short loc_180005FE5
0x180005fab  movzx   ebx, ax
0x180005fae  or      ebx, 80070000h
0x180005fb4  jmp     short loc_180005FE5
0x180005fb6  mov     edx, 7530h; dwMilliseconds
0x180005fbb  xor     ebx, ebx
0x180005fbd  call    cs:__imp_WaitForSingleObject
0x180005fc4  nop     dword ptr [rax+rax+00h]
0x180005fc9  test    eax, eax
0x180005fcb  jz      short loc_180005FE5
0x180005fcd  cmp     eax, 80h
0x180005fd2  jz      short loc_180005FE0
0x180005fd4  cmp     eax, 102h
0x180005fd9  jz      short loc_180005FF1
0x180005fdb  cmp     eax, 0FFFFFFFFh
0x180005fde  jz      short loc_180005F99
0x180005fe0  mov     ebx, 8000FFFFh
0x180005fe5  mov     eax, ebx
0x180005fe7  add     rsp, 38h
0x180005feb  pop     rdi
0x180005fec  pop     rsi
0x180005fed  pop     rbp
0x180005fee  pop     rbx
0x180005fef  retn
0x180005ff1  mov     ebx, 800705B4h
0x180005ff6  jmp     short loc_180005FE5
```
