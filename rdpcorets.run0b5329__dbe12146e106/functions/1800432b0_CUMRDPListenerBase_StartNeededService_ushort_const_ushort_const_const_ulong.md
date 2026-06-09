# CUMRDPListenerBase::StartNeededService(ushort const *,ushort const * * const,ulong)

- ea: `0x1800432b0`
- end: `0x180043379`
- name: `?StartNeededService@CUMRDPListenerBase@@MEAAJPEBGQEAPEBGK@Z`
- size: `201`
- prototype: `int(CUMRDPListenerBase *__hidden this, const unsigned __int16 *, const unsigned __int16 **const, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800432b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004330c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004330c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043357`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800432e8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800432e8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800432ce`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800432ce`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800432fe`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800432fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004332f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004334f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004332f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004334f`

## pseudocode

```c
__int64 __fastcall CUMRDPListenerBase::StartNeededService(
        CUMRDPListenerBase *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **const a3,
        DWORD a4)
{
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rsi
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rdi
  unsigned int v11; // ebx
  signed int LastError; // eax
  signed int v13; // eax
  signed int v14; // eax

  v7 = OpenSCManagerW(0, 0, 0x80000000);
  v8 = v7;
  if ( v7 )
  {
    v9 = OpenServiceW(v7, a2, 0x10u);
    v10 = v9;
    if ( v9 )
    {
      if ( StartServiceW(v9, a4, a3) )
      {
        v11 = 0;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( v11 == -2147023840 )
          v11 = 0;
      }
      CloseServiceHandle(v10);
    }
    else
    {
      v13 = GetLastError();
      v11 = v13;
      if ( v13 > 0 )
        v11 = (unsigned __int16)v13 | 0x80070000;
    }
    CloseServiceHandle(v8);
  }
  else
  {
    v14 = GetLastError();
    v11 = v14;
    if ( v14 > 0 )
      return (unsigned __int16)v14 | 0x80070000;
  }
  return v11;
}

```

## disassembly

```asm
0x1800432b0  push    rbx
0x1800432b2  push    rbp
0x1800432b3  push    rsi
0x1800432b4  push    rdi
0x1800432b5  push    r14
0x1800432b7  sub     rsp, 20h
0x1800432bb  mov     r14, r8
0x1800432be  mov     rbx, rdx
0x1800432c1  xor     edx, edx; lpDatabaseName
0x1800432c3  mov     r8d, 80000000h; dwDesiredAccess
0x1800432c9  xor     ecx, ecx; lpMachineName
0x1800432cb  mov     ebp, r9d
0x1800432ce  call    cs:__imp_OpenSCManagerW
0x1800432d4  mov     rsi, rax
0x1800432d7  test    rax, rax
0x1800432da  jz      short loc_180043357
0x1800432dc  mov     r8d, 10h; dwDesiredAccess
0x1800432e2  mov     rdx, rbx; lpServiceName
0x1800432e5  mov     rcx, rax; hSCManager
0x1800432e8  call    cs:__imp_OpenServiceW
0x1800432ee  mov     rdi, rax
0x1800432f1  test    rax, rax
0x1800432f4  jz      short loc_180043337
0x1800432f6  mov     r8, r14; lpServiceArgVectors
0x1800432f9  mov     edx, ebp; dwNumServiceArgs
0x1800432fb  mov     rcx, rax; hService
0x1800432fe  call    cs:__imp_StartServiceW
0x180043304  test    eax, eax
0x180043306  jz      short loc_18004330C
0x180043308  xor     ebx, ebx
0x18004330a  jmp     short loc_18004332C
0x18004330c  call    cs:__imp_GetLastError
0x180043312  mov     ebx, eax
0x180043314  test    eax, eax
0x180043316  jle     short loc_180043321
0x180043318  movzx   ebx, ax
0x18004331b  or      ebx, 80070000h
0x180043321  xor     eax, eax
0x180043323  cmp     ebx, 80070420h
0x180043329  cmovz   ebx, eax
0x18004332c  mov     rcx, rdi; hSCObject
0x18004332f  call    cs:__imp_CloseServiceHandle
0x180043335  jmp     short loc_18004334C
0x180043337  call    cs:__imp_GetLastError
0x18004333d  mov     ebx, eax
0x18004333f  test    eax, eax
0x180043341  jle     short loc_18004334C
0x180043343  movzx   ebx, ax
0x180043346  or      ebx, 80070000h
0x18004334c  mov     rcx, rsi; hSCObject
0x18004334f  call    cs:__imp_CloseServiceHandle
0x180043355  jmp     short loc_18004336C
0x180043357  call    cs:__imp_GetLastError
0x18004335d  mov     ebx, eax
0x18004335f  test    eax, eax
0x180043361  jle     short loc_18004336C
0x180043363  movzx   ebx, ax
0x180043366  or      ebx, 80070000h
0x18004336c  mov     eax, ebx
0x18004336e  add     rsp, 20h
0x180043372  pop     r14
0x180043374  pop     rdi
0x180043375  pop     rsi
0x180043376  pop     rbp
0x180043377  pop     rbx
0x180043378  retn
```
