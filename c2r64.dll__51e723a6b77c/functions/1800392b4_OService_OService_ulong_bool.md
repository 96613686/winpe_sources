# OService::OService(ulong,bool)

- ea: `0x1800392b4`
- end: `0x18003936f`
- name: `??0OService@@QEAA@K_N@Z`
- size: `187`
- prototype: `OService *__fastcall(OService *__hidden this, unsigned int, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180018870`

## callees

- `0x1800392b4`
- `0x18003e690`
- `0x1800409e0`
- `0x180133538`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003931f`
- `KERNEL32!GetLastError` at `0x18003931f`
- `ADVAPI32!OpenSCManagerW` at `0x180039311`
- `ADVAPI32!OpenSCManagerW` at `0x180039311`

## string_xrefs

- `0x180039328`: `failed to open SCM database`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
OService *__fastcall OService::OService(OService *this)
{
  SC_HANDLE v2; // rax
  DWORD LastError; // eax
  _BYTE pExceptionObject[912]; // [rsp+30h] [rbp-3A8h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_BYTE *)this + 40) = 0;
  *((_DWORD *)this + 11) = 143;
  v2 = OpenSCManagerW(0, 0, 4u);
  *(_QWORD *)this = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    OException::OException(pExceptionObject, 15, LastError, L"failed to open SCM database", this);
    throw (OException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x1800392b4  push    rbx
0x1800392b6  sub     rsp, 3D0h
0x1800392bd  mov     rax, cs:__security_cookie
0x1800392c4  xor     rax, rsp
0x1800392c7  mov     [rsp+3D8h+var_18], rax
0x1800392cf  mov     rbx, rcx
0x1800392d2  mov     [rsp+3D8h+var_3B8], rcx
0x1800392d7  mov     qword ptr [rcx], 0
0x1800392de  mov     qword ptr [rcx+8], 0
0x1800392e6  mov     qword ptr [rcx+10h], 0
0x1800392ee  mov     qword ptr [rcx+18h], 0
0x1800392f6  mov     qword ptr [rcx+20h], 0
0x1800392fe  mov     byte ptr [rcx+28h], 0
0x180039302  mov     dword ptr [rcx+2Ch], 8Fh
0x180039309  xor     edx, edx; lpDatabaseName
0x18003930b  xor     ecx, ecx; lpMachineName
0x18003930d  lea     r8d, [rdx+4]; dwDesiredAccess
0x180039311  call    cs:__imp_OpenSCManagerW
0x180039317  mov     [rbx], rax
0x18003931a  test    rax, rax
0x18003931d  jnz     short loc_180039353
0x18003931f  call    cs:__imp_GetLastError
0x180039325  mov     r8d, eax
0x180039328  lea     r9, aFailedToOpenSc; "failed to open SCM database"
0x18003932f  mov     edx, 0Fh
0x180039334  lea     rcx, [rsp+3D8h+pExceptionObject]
0x180039339  call    ??$?0$0BM@@OException@@QEAA@W4exceptionType@et@@IAEAY0BM@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[28])
0x18003933e  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180039345  lea     rcx, [rsp+3D8h+pExceptionObject]; pExceptionObject
0x18003934a  call    _CxxThrowException
0x180039350  jmp     short $+2
0x180039352  nop
0x180039353  mov     rax, rbx
0x180039356  mov     rcx, [rsp+3D8h+var_18]
0x18003935e  xor     rcx, rsp; StackCookie
0x180039361  call    __security_check_cookie
0x180039366  add     rsp, 3D0h
0x18003936d  pop     rbx
0x18003936e  retn
```
