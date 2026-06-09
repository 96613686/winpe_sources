# ServiceHandle::ServiceHandle(SC_HANDLE__ *,wchar_t const *,ulong)

- ea: `0x18020bfec`
- end: `0x18020c084`
- name: `??0ServiceHandle@@QEAA@PEAUSC_HANDLE__@@PEB_WK@Z`
- size: `152`
- prototype: `ServiceHandle *(ServiceHandle *__hidden this, struct SC_HANDLE__ *, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1801ebf2c`

## callees

- `0x180154068`
- `0x1801f2fe4`
- `0x18020bfec`

## import_xrefs

- `kernel32!GetLastError` at `0x18020c021`
- `kernel32!GetLastError` at `0x18020c021`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18020c013`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18020c013`

## string_xrefs

- `0x18020c003`: `FontCache`

## pseudocode

```c
ServiceHandle *__fastcall ServiceHandle::ServiceHandle(ServiceHandle *this, SC_HANDLE a2, const wchar_t *a3, int a4)
{
  SC_HANDLE v5; // rax
  signed int LastError; // eax
  unsigned int v7; // edx
  int v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = a4;
  *((_DWORD *)this + 2) = 0;
  v5 = OpenServiceW(a2, L"FontCache", 0x14u);
  *(_QWORD *)this = v5;
  if ( v5 )
    return this;
  LastError = GetLastError();
  if ( !LastError )
  {
    v7 = -2147467259;
    *((_DWORD *)this + 2) = -2147467259;
    goto LABEL_10;
  }
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  else
    v7 = LastError;
  *((_DWORD *)this + 2) = v7;
  if ( LastError != 1060 && LastError != 5 )
  {
LABEL_10:
    Exception::Exception((Exception *)&v9, v7, LastError);
    LogAndThrow<OSException>(&v9, 0x6C646E685F73LL, 42);
  }
  return this;
}

```

## disassembly

```asm
0x18020bfec  mov     [rsp+arg_18], r9d
0x18020bff1  push    rbx
0x18020bff2  sub     rsp, 20h
0x18020bff6  mov     rax, rdx
0x18020bff9  mov     dword ptr [rcx+8], 0
0x18020c000  mov     rbx, rcx
0x18020c003  lea     rdx, ?FontCacheServiceName@@3QB_WB; "FontCache"
0x18020c00a  mov     rcx, rax; hSCManager
0x18020c00d  mov     r8d, 14h; dwDesiredAccess
0x18020c013  call    cs:__imp_OpenServiceW
0x18020c019  mov     [rbx], rax
0x18020c01c  test    rax, rax
0x18020c01f  jnz     short loc_18020C049
0x18020c021  call    cs:__imp_GetLastError
0x18020c027  test    eax, eax
0x18020c029  jz      short loc_18020C052
0x18020c02b  jg      short loc_18020C031
0x18020c02d  mov     edx, eax
0x18020c02f  jmp     short loc_18020C03A
0x18020c031  movzx   edx, ax
0x18020c034  or      edx, 80070000h
0x18020c03a  mov     [rbx+8], edx
0x18020c03d  cmp     eax, 424h
0x18020c042  jz      short loc_18020C049
0x18020c044  cmp     eax, 5
0x18020c047  jnz     short loc_18020C05C
0x18020c049  mov     rax, rbx
0x18020c04c  add     rsp, 20h
0x18020c050  pop     rbx
0x18020c051  retn
0x18020c052  mov     ecx, 80004005h
0x18020c057  mov     edx, ecx; int
0x18020c059  mov     [rbx+8], ecx
0x18020c05c  mov     r8d, eax; unsigned int
0x18020c05f  lea     rcx, [rsp+28h+arg_18]; this
0x18020c064  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18020c069  mov     rdx, 6C646E685F73h
0x18020c073  lea     rcx, [rsp+28h+arg_18]
0x18020c078  mov     r8d, 2Ah ; '*'
0x18020c07e  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
```
