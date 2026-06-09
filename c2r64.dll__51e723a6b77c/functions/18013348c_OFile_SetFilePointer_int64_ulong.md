# OFile::SetFilePointer(__int64,ulong)

- ea: `0x18013348c`
- end: `0x180133536`
- name: `?SetFilePointer@OFile@@QEAA_J_JK@Z`
- size: `170`
- prototype: `__int64(OFile *__hidden this, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001bee0`

## callees

- `0x18003e690`
- `0x1800409e0`
- `0x180043d40`
- `0x1801329b8`
- `0x18013348c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801334ed`
- `KERNEL32!GetLastError` at `0x1801334ed`
- `KERNEL32!SetFilePointerEx` at `0x1801334e3`
- `KERNEL32!SetFilePointerEx` at `0x1801334e3`

## string_xrefs

- `0x1801334af`: `can't set the pointer of a file that's not open.`

## pseudocode

```c
LARGE_INTEGER __fastcall OFile::SetFilePointer(OFile *this, LARGE_INTEGER a2, DWORD a3)
{
  void *v3; // rcx
  DWORD LastError; // eax
  __int64 v5; // rdx
  LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-3B8h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+30h] [rbp-3A8h] BYREF

  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 == (void *)-1LL )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))OException::OException)(
      pExceptionObject,
      (LARGE_INTEGER)a2.QuadPart,
      L"can't set the pointer of a file that's not open.");
    throw (OException *)pExceptionObject;
  }
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(v3, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    OException::OException(pExceptionObject, v5, LastError, L"Failed to set the file pointer");
    throw (OException *)pExceptionObject;
  }
  return NewFilePointer;
}

```

## disassembly

```asm
0x18013348c  sub     rsp, 3D8h
0x180133493  mov     rax, cs:__security_cookie
0x18013349a  xor     rax, rsp
0x18013349d  mov     [rsp+3D8h+var_18], rax
0x1801334a5  mov     rcx, [rcx+30h]; hFile
0x1801334a9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801334ad  jnz     short loc_1801334D2
0x1801334af  lea     r8, aCanTSetThePoin; "can't set the pointer of a file that's "...
0x1801334b6  lea     rcx, [rsp+3D8h+pExceptionObject]
0x1801334bb  call    ??$?0$0DB@@OException@@QEAA@W4exceptionType@et@@AEAY0DB@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[49])
0x1801334c0  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1801334c7  lea     rcx, [rsp+3D8h+pExceptionObject]; pExceptionObject
0x1801334cc  call    _CxxThrowException
0x1801334d2  mov     r9d, r8d; dwMoveMethod
0x1801334d5  mov     qword ptr [rsp+3D8h+NewFilePointer], 0
0x1801334de  lea     r8, [rsp+3D8h+NewFilePointer]; lpNewFilePointer
0x1801334e3  call    cs:__imp_SetFilePointerEx
0x1801334e9  test    eax, eax
0x1801334eb  jnz     short loc_180133519
0x1801334ed  call    cs:__imp_GetLastError
0x1801334f3  mov     r8d, eax
0x1801334f6  lea     r9, aFailedToSetThe_0; "Failed to set the file pointer"
0x1801334fd  lea     rcx, [rsp+3D8h+pExceptionObject]
0x180133502  call    ??$?0$0BP@@OException@@QEAA@W4exceptionType@et@@IAEAY0BP@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[31])
0x180133507  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18013350e  lea     rcx, [rsp+3D8h+pExceptionObject]; pExceptionObject
0x180133513  call    _CxxThrowException
0x180133519  mov     rax, qword ptr [rsp+3D8h+NewFilePointer]
0x18013351e  mov     rcx, [rsp+3D8h+var_18]
0x180133526  xor     rcx, rsp; StackCookie
0x180133529  call    __security_check_cookie
0x18013352e  add     rsp, 3D8h
0x180133535  retn
```
