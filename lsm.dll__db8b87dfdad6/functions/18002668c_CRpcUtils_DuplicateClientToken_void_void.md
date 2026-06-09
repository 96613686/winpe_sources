# CRpcUtils::DuplicateClientToken(void *,void * *)

- ea: `0x18002668c`
- end: `0x18002679c`
- name: `?DuplicateClientToken@CRpcUtils@@SAJPEAXPEAPEAX@Z`
- size: `272`
- prototype: `__int64 __fastcall(HANDLE SourceHandle, PHANDLE TargetHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002d3b4`
- `0x18002f650`
- `0x180054fd0`

## callees

- `0x1800074c0`
- `0x18002668c`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x180026702`
- `ntdll!NtDuplicateObject` at `0x180026702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026742`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026742`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800266aa`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800266aa`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800266cb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800266cb`

## string_xrefs

- `0x18002672c`: `CRpcUtils::DuplicateClientToken`
- `0x18002677c`: `CRpcUtils::DuplicateClientToken`
- `0x18002675c`: `OpenProcess failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CRpcUtils::DuplicateClientToken(HANDLE SourceHandle, PHANDLE TargetHandle)
{
  RPC_STATUS v4; // eax
  int v5; // ebx
  HANDLE v6; // rdi
  NTSTATUS v7; // eax
  signed int LastError; // eax
  DWORD dwProcessId; // [rsp+80h] [rbp+18h] BYREF

  dwProcessId = 0;
  v4 = I_RpcBindingInqLocalClientPID(0, &dwProcessId);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    _DbgPrintMessage(
      8,
      "I_RpcBindingInqLocalClientPID failed: 0x%x in %s",
      (unsigned int)v5,
      "CRpcUtils::DuplicateClientToken");
  }
  else
  {
    v6 = OpenProcess(0x40u, 0, dwProcessId);
    if ( v6 )
      goto LABEL_5;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
    {
LABEL_5:
      v7 = NtDuplicateObject(v6, SourceHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL, TargetHandle, 0, 0, 6u);
      v5 = v7 | 0x10000000;
      if ( v7 < 0 )
        _DbgPrintMessage(8, "NtDuplicateObject failed: 0x%x in %s", v5, "CRpcUtils::DuplicateClientToken");
      if ( v6 )
        CloseHandle(v6);
    }
    else
    {
      _DbgPrintMessage(8, "OpenProcess failed: 0x%x in %s", (unsigned int)v5, "CRpcUtils::DuplicateClientToken");
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002668c  mov     rax, rsp
0x18002668f  push    rbx
0x180026690  push    rbp
0x180026691  push    rsi
0x180026692  push    rdi
0x180026693  sub     rsp, 48h
0x180026697  mov     rsi, rdx
0x18002669a  mov     dword ptr [rax+18h], 0
0x1800266a1  mov     rbp, rcx
0x1800266a4  lea     rdx, [rax+18h]; Pid
0x1800266a8  xor     ecx, ecx; Binding
0x1800266aa  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800266b0  mov     ebx, eax
0x1800266b2  test    eax, eax
0x1800266b4  jg      loc_18002674A
0x1800266ba  test    ebx, ebx
0x1800266bc  js      short loc_180026722
0x1800266be  mov     r8d, [rsp+68h+dwProcessId]; dwProcessId
0x1800266c6  xor     edx, edx; bInheritHandle
0x1800266c8  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800266cb  call    cs:__imp_OpenProcess
0x1800266d1  mov     rdi, rax
0x1800266d4  test    rax, rax
0x1800266d7  jz      loc_180026765
0x1800266dd  mov     [rsp+68h+Options], 6; Options
0x1800266e5  mov     r9, rsi; TargetHandle
0x1800266e8  mov     [rsp+68h+HandleAttributes], 0; HandleAttributes
0x1800266f0  or      r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1800266f4  mov     rdx, rbp; SourceHandle
0x1800266f7  mov     [rsp+68h+DesiredAccess], 0; DesiredAccess
0x1800266ff  mov     rcx, rdi; SourceProcessHandle
0x180026702  call    cs:__imp_NtDuplicateObject
0x180026708  mov     ebx, eax
0x18002670a  or      ebx, 10000000h
0x180026710  jl      short loc_18002677C
0x180026712  test    rdi, rdi
0x180026715  jnz     short loc_18002673F
0x180026717  mov     eax, ebx
0x180026719  add     rsp, 48h
0x18002671d  pop     rdi
0x18002671e  pop     rsi
0x18002671f  pop     rbp
0x180026720  pop     rbx
0x180026721  retn
0x180026722  lea     rdx, aIRpcbindinginq_1; "I_RpcBindingInqLocalClientPID failed: 0"...
0x180026729  mov     r8d, ebx
0x18002672c  lea     r9, aCrpcutilsDupli_0; "CRpcUtils::DuplicateClientToken"
0x180026733  mov     ecx, 8; int
0x180026738  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002673d  jmp     short loc_180026717
0x18002673f  mov     rcx, rdi; hObject
0x180026742  call    cs:__imp_CloseHandle
0x180026748  jmp     short loc_180026717
0x18002674a  movzx   ebx, ax
0x18002674d  or      ebx, 80070000h
0x180026753  jmp     loc_1800266BA
0x180026758  test    ebx, ebx
0x18002675a  jns     short loc_1800266DD
0x18002675c  lea     rdx, aOpenprocessFai; "OpenProcess failed: 0x%x in %s"
0x180026763  jmp     short loc_180026729
0x180026765  call    cs:__imp_GetLastError
0x18002676b  mov     ebx, eax
0x18002676d  test    eax, eax
0x18002676f  jle     short loc_180026758
0x180026771  movzx   ebx, ax
0x180026774  or      ebx, 80070000h
0x18002677a  jmp     short loc_180026758
0x18002677c  lea     r9, aCrpcutilsDupli_0; "CRpcUtils::DuplicateClientToken"
0x180026783  mov     r8d, ebx
0x180026786  lea     rdx, aNtduplicateobj; "NtDuplicateObject failed: 0x%x in %s"
0x18002678d  mov     ecx, 8; int
0x180026792  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180026797  jmp     loc_180026712
```
