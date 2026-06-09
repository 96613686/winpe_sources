# CSecDesc::AddSid(void *,ulong,ulong)

- ea: `0x18004dfd0`
- end: `0x18004e149`
- name: `?AddSid@CSecDesc@@QEAAHPEAXKK@Z`
- size: `377`
- prototype: `__int64 __fastcall(CSecDesc *this, void *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006ea44`
- `0x180070e90`

## callees

- `0x18000a504`
- `0x18004dfd0`
- `0x180072a08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e0f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e11c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e0f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e11c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004e032`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004e032`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e023`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e023`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e008`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e008`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004e051`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004e051`

## string_xrefs

- `0x18004e0c5`: `AddSid: Not initialised or failure.`
- `0x18004e0ee`: `AddSid: Not a vaild Sid.`
- `0x18004e0fd`: `AddSid: Couldn't allocate memory. Error %d`
- `0x18004e122`: `AddSid: Couldn't copy Sid. Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSecDesc::AddSid(CSecDesc *this, void *a2, int a3, int a4)
{
  SIZE_T LengthSid; // rbp
  HLOCAL v9; // rax
  HLOCAL v10; // rsi
  __int64 result; // rax
  DWORD LastError; // eax
  DWORD v13; // eax
  void *v14; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 4) || *((_DWORD *)this + 5) )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Not initialised or failure.");
    return 0;
  }
  *((_DWORD *)this + 5) = 1;
  if ( !IsValidSid(a2) )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Not a vaild Sid.");
    return 0;
  }
  LengthSid = GetLengthSid(a2);
  v9 = LocalAlloc(0x40u, LengthSid);
  v14 = v9;
  v10 = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Couldn't allocate memory. Error %d", LastError);
    return 0;
  }
  if ( !CopySid(LengthSid, v9, a2) )
  {
    v13 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Couldn't copy Sid. Error %d", v13);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v14);
    return 0;
  }
  *(_QWORD *)(*(_QWORD *)this + 24LL * *((unsigned int *)this + 2)) = v10;
  result = 1;
  *(_DWORD *)(*(_QWORD *)this + 24LL * *((unsigned int *)this + 2) + 8) = a3;
  *(_DWORD *)(*(_QWORD *)this + 24LL * *((unsigned int *)this + 2) + 12) = 1;
  *(_DWORD *)(*(_QWORD *)this + 24LL * (unsigned int)(*((_DWORD *)this + 2))++ + 16) = a4;
  *((_DWORD *)this + 5) = 0;
  return result;
}

```

## disassembly

```asm
0x18004dfd0  mov     [rsp+arg_18], rbx
0x18004dfd5  push    rdi
0x18004dfd6  push    r14
0x18004dfd8  push    r15
0x18004dfda  sub     rsp, 20h
0x18004dfde  cmp     dword ptr [rcx+10h], 0
0x18004dfe2  mov     r14d, r9d
0x18004dfe5  mov     r15d, r8d
0x18004dfe8  mov     rdi, rdx
0x18004dfeb  mov     rbx, rcx
0x18004dfee  jz      loc_18004E0C5
0x18004dff4  cmp     dword ptr [rcx+14h], 0
0x18004dff8  jnz     loc_18004E0C5
0x18004dffe  mov     dword ptr [rcx+14h], 1
0x18004e005  mov     rcx, rdx; pSid
0x18004e008  call    cs:__imp_IsValidSid
0x18004e00e  test    eax, eax
0x18004e010  jz      loc_18004E0EE
0x18004e016  mov     [rsp+38h+arg_8], rbp
0x18004e01b  mov     rcx, rdi; pSid
0x18004e01e  mov     [rsp+38h+arg_10], rsi
0x18004e023  call    cs:__imp_GetLengthSid
0x18004e029  mov     edx, eax; uBytes
0x18004e02b  mov     ecx, 40h ; '@'; uFlags
0x18004e030  mov     ebp, eax
0x18004e032  call    cs:__imp_LocalAlloc
0x18004e038  mov     [rsp+38h+arg_0], rax
0x18004e03d  mov     rsi, rax
0x18004e040  test    rax, rax
0x18004e043  jz      loc_18004E0F7
0x18004e049  mov     r8, rdi; pSourceSid
0x18004e04c  mov     rdx, rax; pDestinationSid
0x18004e04f  mov     ecx, ebp; nDestinationSidLength
0x18004e051  call    cs:__imp_CopySid
0x18004e057  test    eax, eax
0x18004e059  jz      loc_18004E11C
0x18004e05f  mov     eax, [rbx+8]
0x18004e062  lea     rcx, [rax+rax*2]
0x18004e066  mov     rax, [rbx]
0x18004e069  mov     [rax+rcx*8], rsi
0x18004e06d  mov     eax, 1
0x18004e072  mov     ecx, [rbx+8]
0x18004e075  lea     rdx, [rcx+rcx*2]
0x18004e079  mov     rcx, [rbx]
0x18004e07c  mov     [rcx+rdx*8+8], r15d
0x18004e081  mov     ecx, [rbx+8]
0x18004e084  lea     rdx, [rcx+rcx*2]
0x18004e088  mov     rcx, [rbx]
0x18004e08b  mov     dword ptr [rcx+rdx*8+0Ch], 1
0x18004e093  mov     ecx, [rbx+8]
0x18004e096  lea     rdx, [rcx+rcx*2]
0x18004e09a  mov     rcx, [rbx]
0x18004e09d  mov     [rcx+rdx*8+10h], r14d
0x18004e0a2  inc     dword ptr [rbx+8]
0x18004e0a5  mov     dword ptr [rbx+14h], 0
0x18004e0ac  mov     rbp, [rsp+38h+arg_8]
0x18004e0b1  mov     rsi, [rsp+38h+arg_10]
0x18004e0b6  mov     rbx, [rsp+38h+arg_18]
0x18004e0bb  add     rsp, 20h
0x18004e0bf  pop     r15
0x18004e0c1  pop     r14
0x18004e0c3  pop     rdi
0x18004e0c4  retn
0x18004e0c5  lea     r8, aAddsidNotIniti; "AddSid: Not initialised or failure."
0x18004e0cc  mov     edx, 2; unsigned int
0x18004e0d1  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18004e0d8  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18004e0dd  mov     rbx, [rsp+38h+arg_18]
0x18004e0e2  xor     eax, eax
0x18004e0e4  add     rsp, 20h
0x18004e0e8  pop     r15
0x18004e0ea  pop     r14
0x18004e0ec  pop     rdi
0x18004e0ed  retn
0x18004e0ee  lea     r8, aAddsidNotAVail; "AddSid: Not a vaild Sid."
0x18004e0f5  jmp     short loc_18004E0CC
0x18004e0f7  call    cs:__imp_GetLastError
0x18004e0fd  lea     r8, aAddsidCouldnTA; "AddSid: Couldn't allocate memory. Error"...
0x18004e104  mov     edx, 2; unsigned int
0x18004e109  mov     r9d, eax
0x18004e10c  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18004e113  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18004e118  xor     eax, eax
0x18004e11a  jmp     short loc_18004E0AC
0x18004e11c  call    cs:__imp_GetLastError
0x18004e122  lea     r8, aAddsidCouldnTC; "AddSid: Couldn't copy Sid. Error %d"
0x18004e129  mov     edx, 2; unsigned int
0x18004e12e  mov     r9d, eax
0x18004e131  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18004e138  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18004e13d  lea     rcx, [rsp+38h+arg_0]
0x18004e142  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18004e147  jmp     short loc_18004E118
```
