# CImpersonate::ImpersonateUser(IUserName *)

- ea: `0x180018288`
- end: `0x180018324`
- name: `?ImpersonateUser@CImpersonate@@QEAAJPEAUIUserName@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this, struct IUserName *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180016ee4`
- `0x180017a50`

## callees

- `0x1800074c0`
- `0x180018288`
- `0x180018700`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800182ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800182ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001830c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001830c`

## string_xrefs

- `0x1800182ee`: `CImpersonate::ImpersonateUser`
- `0x1800182e7`: `ImpersonateUser failed: 0x%x in %s`
- `0x1800182cb`: `pUserName->DuplicateTokenInPid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CImpersonate::ImpersonateUser(CImpersonate *this, struct IUserName *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v5)(struct IUserName *, _QWORD, HANDLE *); // rbx
  DWORD CurrentProcessId; // eax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(_QWORD *)a2;
  hObject = 0;
  v5 = *(__int64 (__fastcall **)(struct IUserName *, _QWORD, HANDLE *))(v2 + 80);
  CurrentProcessId = GetCurrentProcessId();
  v7 = v5(a2, CurrentProcessId, &hObject);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = CImpersonate::ImpersonateUser(this, hObject);
    v8 = v9;
    if ( v9 < 0 )
      _DbgPrintMessage(8, "ImpersonateUser failed: 0x%x in %s", (unsigned int)v9, "CImpersonate::ImpersonateUser");
  }
  else
  {
    _DbgPrintMessage(
      8,
      "pUserName->DuplicateTokenInPid failed: 0x%x in %s",
      (unsigned int)v7,
      "CImpersonate::ImpersonateUser");
  }
  if ( hObject )
    CloseHandle(hObject);
  return v8;
}

```

## disassembly

```asm
0x180018288  mov     [rsp+arg_0], rbx
0x18001828d  mov     [rsp+arg_10], rsi
0x180018292  push    rdi
0x180018293  sub     rsp, 20h
0x180018297  mov     rax, [rdx]
0x18001829a  mov     rdi, rdx
0x18001829d  mov     rsi, rcx
0x1800182a0  mov     [rsp+28h+hObject], 0
0x1800182a9  mov     rbx, [rax+50h]
0x1800182ad  call    cs:__imp_GetCurrentProcessId
0x1800182b3  lea     r8, [rsp+28h+hObject]
0x1800182b8  mov     rcx, rdi
0x1800182bb  mov     edx, eax
0x1800182bd  mov     rax, rbx
0x1800182c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182c5  mov     ebx, eax
0x1800182c7  test    eax, eax
0x1800182c9  jns     short loc_1800182D4
0x1800182cb  lea     rdx, aPusernameDupli; "pUserName->DuplicateTokenInPid failed: "...
0x1800182d2  jmp     short loc_1800182EE
0x1800182d4  mov     rdx, [rsp+28h+hObject]; void *
0x1800182d9  mov     rcx, rsi; this
0x1800182dc  call    ?ImpersonateUser@CImpersonate@@QEAAJPEAX@Z; CImpersonate::ImpersonateUser(void *)
0x1800182e1  mov     ebx, eax
0x1800182e3  test    eax, eax
0x1800182e5  jns     short loc_180018302
0x1800182e7  lea     rdx, aImpersonateuse; "ImpersonateUser failed: 0x%x in %s"
0x1800182ee  lea     r9, aCimpersonateIm; "CImpersonate::ImpersonateUser"
0x1800182f5  mov     r8d, eax
0x1800182f8  mov     ecx, 8; int
0x1800182fd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018302  mov     rcx, [rsp+28h+hObject]; hObject
0x180018307  test    rcx, rcx
0x18001830a  jz      short loc_180018312
0x18001830c  call    cs:__imp_CloseHandle
0x180018312  mov     rsi, [rsp+28h+arg_10]
0x180018317  mov     eax, ebx
0x180018319  mov     rbx, [rsp+28h+arg_0]
0x18001831e  add     rsp, 20h
0x180018322  pop     rdi
0x180018323  retn
```
