# CRpcUtils::DuplicateClientToken(void *,void * *)

- ea: `0x180028750`
- end: `0x180028883`
- name: `?DuplicateClientToken@CRpcUtils@@SAJPEAXPEAPEAX@Z`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE SourceHandle, PHANDLE TargetHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002f3c0`
- `0x180031680`
- `0x180058770`

## callees

- `0x1800077a0`
- `0x180028750`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x1800287d2`
- `ntdll!NtDuplicateObject` at `0x1800287d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028819`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002876e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002876e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180028795`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180028795`

## string_xrefs

- `0x180028803`: `CRpcUtils::DuplicateClientToken`
- `0x180028863`: `CRpcUtils::DuplicateClientToken`
- `0x18002883d`: `OpenProcess failed: 0x%x in %s`

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
0x180028750  mov     rax, rsp
0x180028753  push    rbx
0x180028754  push    rbp
0x180028755  push    rsi
0x180028756  push    rdi
0x180028757  sub     rsp, 48h
0x18002875b  mov     rsi, rdx
0x18002875e  mov     dword ptr [rax+18h], 0
0x180028765  mov     rbp, rcx
0x180028768  lea     rdx, [rax+18h]; Pid
0x18002876c  xor     ecx, ecx; Binding
0x18002876e  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180028775  nop     dword ptr [rax+rax+00h]
0x18002877a  mov     ebx, eax
0x18002877c  test    eax, eax
0x18002877e  jg      loc_180028827
0x180028784  test    ebx, ebx
0x180028786  js      short loc_1800287F9
0x180028788  mov     r8d, [rsp+68h+dwProcessId]; dwProcessId
0x180028790  xor     edx, edx; bInheritHandle
0x180028792  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180028795  call    cs:__imp_OpenProcess
0x18002879c  nop     dword ptr [rax+rax+00h]
0x1800287a1  mov     rdi, rax
0x1800287a4  test    rax, rax
0x1800287a7  jz      loc_180028846
0x1800287ad  mov     [rsp+68h+Options], 6; Options
0x1800287b5  mov     r9, rsi; TargetHandle
0x1800287b8  mov     [rsp+68h+HandleAttributes], 0; HandleAttributes
0x1800287c0  or      r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1800287c4  mov     rdx, rbp; SourceHandle
0x1800287c7  mov     [rsp+68h+DesiredAccess], 0; DesiredAccess
0x1800287cf  mov     rcx, rdi; SourceProcessHandle
0x1800287d2  call    cs:__imp_NtDuplicateObject
0x1800287d9  nop     dword ptr [rax+rax+00h]
0x1800287de  mov     ebx, eax
0x1800287e0  or      ebx, 10000000h
0x1800287e6  jl      short loc_180028863
0x1800287e8  test    rdi, rdi
0x1800287eb  jnz     short loc_180028816
0x1800287ed  mov     eax, ebx
0x1800287ef  add     rsp, 48h
0x1800287f3  pop     rdi
0x1800287f4  pop     rsi
0x1800287f5  pop     rbp
0x1800287f6  pop     rbx
0x1800287f7  retn
0x1800287f9  lea     rdx, aIRpcbindinginq_1; "I_RpcBindingInqLocalClientPID failed: 0"...
0x180028800  mov     r8d, ebx
0x180028803  lea     r9, aCrpcutilsDupli_0; "CRpcUtils::DuplicateClientToken"
0x18002880a  mov     ecx, 8; int
0x18002880f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028814  jmp     short loc_1800287ED
0x180028816  mov     rcx, rdi; hObject
0x180028819  call    cs:__imp_CloseHandle
0x180028820  nop     dword ptr [rax+rax+00h]
0x180028825  jmp     short loc_1800287ED
0x180028827  movzx   ebx, ax
0x18002882a  or      ebx, 80070000h
0x180028830  jmp     loc_180028784
0x180028835  test    ebx, ebx
0x180028837  jns     loc_1800287AD
0x18002883d  lea     rdx, aOpenprocessFai; "OpenProcess failed: 0x%x in %s"
0x180028844  jmp     short loc_180028800
0x180028846  call    cs:__imp_GetLastError
0x18002884d  nop     dword ptr [rax+rax+00h]
0x180028852  mov     ebx, eax
0x180028854  test    eax, eax
0x180028856  jle     short loc_180028835
0x180028858  movzx   ebx, ax
0x18002885b  or      ebx, 80070000h
0x180028861  jmp     short loc_180028835
0x180028863  lea     r9, aCrpcutilsDupli_0; "CRpcUtils::DuplicateClientToken"
0x18002886a  mov     r8d, ebx
0x18002886d  lea     rdx, aNtduplicateobj; "NtDuplicateObject failed: 0x%x in %s"
0x180028874  mov     ecx, 8; int
0x180028879  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002887e  jmp     loc_1800287E8
```
