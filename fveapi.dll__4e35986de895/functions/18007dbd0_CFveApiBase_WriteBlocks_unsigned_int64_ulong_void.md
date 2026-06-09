# CFveApiBase::WriteBlocks(unsigned __int64,ulong,void *)

- ea: `0x18007dbd0`
- end: `0x18007dce4`
- name: `?WriteBlocks@CFveApiBase@@MEAAJ_KKPEAX@Z`
- size: `276`
- prototype: `int(CFveApiBase *__hidden this, unsigned __int64, unsigned int, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180005410`
- `0x18007dbd0`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007dc90`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007dc90`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007dc67`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007dc67`

## pseudocode

```c
__int64 __fastcall CFveApiBase::WriteBlocks(CFveApiBase *this, union _LARGE_INTEGER a2, DWORD a3, void *a4)
{
  int LastHresultError; // ebx
  HANDLE hFile; // [rsp+40h] [rbp-48h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-40h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+50h] [rbp-38h] BYREF

  NewFilePointer.QuadPart = 0;
  NumberOfBytesWritten = 0;
  hFile = (HANDLE)-1LL;
  if ( (*(unsigned __int8 (__fastcall **)(CFveApiBase *))(*(_QWORD *)this + 104LL))(this) )
  {
    LastHresultError = (*(__int64 (__fastcall **)(CFveApiBase *, HANDLE *))(*(_QWORD *)this + 216LL))(this, &hFile);
    if ( LastHresultError >= 0 )
    {
      NewFilePointer = a2;
      if ( !SetFilePointerEx(hFile, a2, &NewFilePointer, 0) || !WriteFile(hFile, a4, a3, &NumberOfBytesWritten, 0) )
        LastHresultError = GetLastHresultError();
    }
  }
  else
  {
    LastHresultError = -2147024890;
  }
  if ( hFile != (HANDLE)-1LL )
    (*(void (__fastcall **)(CFveApiBase *))(*(_QWORD *)this + 232LL))(this);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x18007dbd0  push    rbx
0x18007dbd2  push    rsi
0x18007dbd3  push    rdi
0x18007dbd4  push    r14
0x18007dbd6  push    r15
0x18007dbd8  sub     rsp, 60h
0x18007dbdc  mov     rax, cs:__security_cookie
0x18007dbe3  xor     rax, rsp
0x18007dbe6  mov     [rsp+88h+var_30], rax
0x18007dbeb  mov     r15, r9
0x18007dbee  mov     r14d, r8d
0x18007dbf1  mov     rsi, rdx
0x18007dbf4  mov     rdi, rcx
0x18007dbf7  mov     [rsp+88h+var_50], rcx
0x18007dbfc  mov     qword ptr [rsp+88h+NewFilePointer], 0
0x18007dc05  mov     [rsp+88h+NumberOfBytesWritten], 0
0x18007dc0d  mov     [rsp+88h+hFile], 0FFFFFFFFFFFFFFFFh
0x18007dc16  mov     rax, [rcx]
0x18007dc19  mov     rax, [rax+68h]
0x18007dc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc22  test    al, al
0x18007dc24  jnz     short loc_18007DC31
0x18007dc26  mov     ebx, 80070006h
0x18007dc2b  mov     [rsp+88h+var_58], ebx
0x18007dc2f  jmp     short loc_18007DCAB
0x18007dc31  mov     rax, [rdi]
0x18007dc34  lea     rdx, [rsp+88h+hFile]
0x18007dc39  mov     rcx, rdi
0x18007dc3c  mov     rax, [rax+0D8h]
0x18007dc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc48  mov     ebx, eax
0x18007dc4a  mov     [rsp+88h+var_58], eax
0x18007dc4e  test    eax, eax
0x18007dc50  js      short loc_18007DCAB
0x18007dc52  mov     qword ptr [rsp+88h+NewFilePointer], rsi
0x18007dc57  xor     r9d, r9d; dwMoveMethod
0x18007dc5a  lea     r8, [rsp+88h+NewFilePointer]; lpNewFilePointer
0x18007dc5f  mov     rdx, rsi; liDistanceToMove
0x18007dc62  mov     rcx, [rsp+88h+hFile]; hFile
0x18007dc67  call    cs:__imp_SetFilePointerEx
0x18007dc6e  nop     dword ptr [rax+rax+00h]
0x18007dc73  test    eax, eax
0x18007dc75  jz      short loc_18007DCA0
0x18007dc77  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x18007dc80  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007dc85  mov     r8d, r14d; nNumberOfBytesToWrite
0x18007dc88  mov     rdx, r15; lpBuffer
0x18007dc8b  mov     rcx, [rsp+88h+hFile]; hFile
0x18007dc90  call    cs:__imp_WriteFile
0x18007dc97  nop     dword ptr [rax+rax+00h]
0x18007dc9c  test    eax, eax
0x18007dc9e  jnz     short loc_18007DCAB
0x18007dca0  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18007dca5  mov     [rsp+88h+var_58], eax
0x18007dca9  mov     ebx, eax
0x18007dcab  mov     rdx, [rsp+88h+hFile]
0x18007dcb0  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18007dcb4  jz      short loc_18007DCC8
0x18007dcb6  mov     rax, [rdi]
0x18007dcb9  mov     rcx, rdi
0x18007dcbc  mov     rax, [rax+0E8h]
0x18007dcc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dcc8  mov     eax, ebx
0x18007dcca  mov     rcx, [rsp+88h+var_30]
0x18007dccf  xor     rcx, rsp; StackCookie
0x18007dcd2  call    __security_check_cookie
0x18007dcd7  add     rsp, 60h
0x18007dcdb  pop     r15
0x18007dcdd  pop     r14
0x18007dcdf  pop     rdi
0x18007dce0  pop     rsi
0x18007dce1  pop     rbx
0x18007dce2  retn
0x180123d37  push    rbp
0x180123d39  sub     rsp, 30h
0x180123d3d  mov     rbp, rdx
0x180123d40  mov     rdx, [rbp+40h]
0x180123d44  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180123d48  jz      short loc_180123D5E
0x180123d4a  mov     rcx, [rbp+38h]
0x180123d4e  mov     rax, [rcx]
0x180123d51  mov     rax, [rax+0E8h]
0x180123d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123d5d  nop
0x180123d5e  add     rsp, 30h
0x180123d62  pop     rbp
0x180123d63  retn
```
