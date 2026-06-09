# CImpersonate::ImpersonateUser(IUserName *)

- ea: `0x18000c208`
- end: `0x18000c2b1`
- name: `?ImpersonateUser@CImpersonate@@QEAAJPEAUIUserName@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this, struct IUserName *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000b978`
- `0x18000cb34`

## callees

- `0x1800077a0`
- `0x18000c208`
- `0x18000c720`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c22d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c22d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c292`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c292`

## string_xrefs

- `0x18000c251`: `pUserName->DuplicateTokenInPid failed: 0x%x in %s`
- `0x18000c274`: `CImpersonate::ImpersonateUser`
- `0x18000c26d`: `ImpersonateUser failed: 0x%x in %s`

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
0x18000c208  mov     [rsp+arg_0], rbx
0x18000c20d  mov     [rsp+arg_10], rsi
0x18000c212  push    rdi
0x18000c213  sub     rsp, 20h
0x18000c217  mov     rax, [rdx]
0x18000c21a  mov     rdi, rdx
0x18000c21d  mov     rsi, rcx
0x18000c220  mov     [rsp+28h+hObject], 0
0x18000c229  mov     rbx, [rax+50h]
0x18000c22d  call    cs:__imp_GetCurrentProcessId
0x18000c234  nop     dword ptr [rax+rax+00h]
0x18000c239  lea     r8, [rsp+28h+hObject]
0x18000c23e  mov     rcx, rdi
0x18000c241  mov     edx, eax
0x18000c243  mov     rax, rbx
0x18000c246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c24b  mov     ebx, eax
0x18000c24d  test    eax, eax
0x18000c24f  jns     short loc_18000C25A
0x18000c251  lea     rdx, aPusernameDupli; "pUserName->DuplicateTokenInPid failed: "...
0x18000c258  jmp     short loc_18000C274
0x18000c25a  mov     rdx, [rsp+28h+hObject]; void *
0x18000c25f  mov     rcx, rsi; this
0x18000c262  call    ?ImpersonateUser@CImpersonate@@QEAAJPEAX@Z; CImpersonate::ImpersonateUser(void *)
0x18000c267  mov     ebx, eax
0x18000c269  test    eax, eax
0x18000c26b  jns     short loc_18000C288
0x18000c26d  lea     rdx, aImpersonateuse; "ImpersonateUser failed: 0x%x in %s"
0x18000c274  lea     r9, aCimpersonateIm; "CImpersonate::ImpersonateUser"
0x18000c27b  mov     r8d, eax
0x18000c27e  mov     ecx, 8; int
0x18000c283  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c288  mov     rcx, [rsp+28h+hObject]; hObject
0x18000c28d  test    rcx, rcx
0x18000c290  jz      short loc_18000C29E
0x18000c292  call    cs:__imp_CloseHandle
0x18000c299  nop     dword ptr [rax+rax+00h]
0x18000c29e  mov     rsi, [rsp+28h+arg_10]
0x18000c2a3  mov     eax, ebx
0x18000c2a5  mov     rbx, [rsp+28h+arg_0]
0x18000c2aa  add     rsp, 20h
0x18000c2ae  pop     rdi
0x18000c2af  retn
```
