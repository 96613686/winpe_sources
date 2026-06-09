# DimSecObjAccessCheck(ulong,ulong *)

- ea: `0x180019950`
- end: `0x180019a1c`
- name: `?DimSecObjAccessCheck@@YAKKPEAK@Z`
- size: `204`
- prototype: `RPC_STATUS __fastcall(DWORD DesiredAccess, LPBOOL AccessStatus)`
- caller_count: `49`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800057f0`
- `0x1800086e0`
- `0x18000cc50`
- `0x18000cd40`
- `0x18000cdd0`
- `0x18000ce40`
- `0x18000d020`
- `0x18000d0c0`
- `0x18000d370`
- `0x18000d560`
- `0x18000d600`
- `0x18000d750`
- `0x18000d7d0`
- `0x18000db8c`
- `0x18000dbf4`
- `0x18000e4c0`
- `0x18000e540`
- `0x18000e770`
- `0x18000e7f0`
- `0x18000e8a0`
- `0x18000f4a0`
- `0x18000f6c0`
- `0x18000f7a0`
- `0x18000f800`
- `0x18000f890`
- `0x18000f910`
- `0x18000f990`
- `0x18000fa10`
- `0x18000ff00`
- `0x18000ff70`
- `0x18000ffe0`
- `0x1800101b0`
- `0x180010250`
- `0x180010370`
- `0x180010420`
- `0x180010560`
- `0x1800106d0`
- `0x1800107f0`
- `0x180010860`
- `0x180010cd0`
- `0x180012c40`
- `0x180012d30`
- `0x180012e20`
- `0x180012f40`
- `0x180013060`
- `0x180013180`
- `0x180013270`
- `0x180013390`
- `0x180019a24`

## callees

- `0x180019950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x1800199d9`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x1800199d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199e3`
- `RPCRT4!RpcRevertToSelf` at `0x1800199eb`
- `RPCRT4!RpcRevertToSelf` at `0x1800199f5`
- `RPCRT4!RpcRevertToSelf` at `0x1800199eb`
- `RPCRT4!RpcRevertToSelf` at `0x1800199f5`
- `RPCRT4!RpcImpersonateClient` at `0x180019971`
- `RPCRT4!RpcImpersonateClient` at `0x180019971`

## string_xrefs

- `0x180019995`: `RemoteAccess`

## pseudocode

```c
RPC_STATUS __fastcall DimSecObjAccessCheck(DWORD DesiredAccess, LPBOOL AccessStatus)
{
  RPC_STATUS result; // eax
  DWORD LastError; // ebx
  DWORD GrantedAccess; // [rsp+80h] [rbp+18h] BYREF
  WINBOOL pfGenerateOnClose; // [rsp+88h] [rbp+20h] BYREF

  GrantedAccess = 0;
  pfGenerateOnClose = 0;
  result = RpcImpersonateClient(0);
  if ( !result )
  {
    if ( AccessCheckAndAuditAlarmW(
           L"RemoteAccess",
           0,
           ObjectTypeName,
           ObjectName,
           NewDescriptor,
           DesiredAccess,
           &GenericMapping,
           0,
           &GrantedAccess,
           AccessStatus,
           &pfGenerateOnClose) )
    {
      result = RpcRevertToSelf();
      if ( !result )
      {
        *AccessStatus = GrantedAccess != DesiredAccess ? 5 : 0;
        return 0;
      }
    }
    else
    {
      LastError = GetLastError();
      RpcRevertToSelf();
      return LastError;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019950  mov     rax, rsp
0x180019953  mov     [rax+8], rbx
0x180019957  push    rdi
0x180019958  sub     rsp, 60h
0x18001995c  mov     ebx, ecx
0x18001995e  mov     dword ptr [rax+18h], 0
0x180019965  xor     ecx, ecx; BindingHandle
0x180019967  mov     dword ptr [rax+20h], 0
0x18001996e  mov     rdi, rdx
0x180019971  call    cs:__imp_RpcImpersonateClient
0x180019977  test    eax, eax
0x180019979  jnz     loc_180019A11
0x18001997f  mov     r9, cs:ObjectName; ObjectName
0x180019986  lea     rax, [rsp+68h+arg_18]
0x18001998e  mov     r8, cs:ObjectTypeName; ObjectTypeName
0x180019995  lea     rcx, SubsystemName; "RemoteAccess"
0x18001999c  mov     [rsp+68h+pfGenerateOnClose], rax; pfGenerateOnClose
0x1800199a1  xor     edx, edx; HandleId
0x1800199a3  mov     [rsp+68h+AccessStatus], rdi; AccessStatus
0x1800199a8  lea     rax, [rsp+68h+arg_10]
0x1800199b0  mov     [rsp+68h+GrantedAccess], rax; GrantedAccess
0x1800199b5  lea     rax, GenericMapping
0x1800199bc  mov     [rsp+68h+ObjectCreation], 0; ObjectCreation
0x1800199c4  mov     [rsp+68h+GenericMapping], rax; GenericMapping
0x1800199c9  mov     rax, cs:NewDescriptor
0x1800199d0  mov     [rsp+68h+DesiredAccess], ebx; DesiredAccess
0x1800199d4  mov     [rsp+68h+SecurityDescriptor], rax; SecurityDescriptor
0x1800199d9  call    cs:__imp_AccessCheckAndAuditAlarmW
0x1800199df  test    eax, eax
0x1800199e1  jnz     short loc_1800199F5
0x1800199e3  call    cs:__imp_GetLastError
0x1800199e9  mov     ebx, eax
0x1800199eb  call    cs:__imp_RpcRevertToSelf
0x1800199f1  mov     eax, ebx
0x1800199f3  jmp     short loc_180019A11
0x1800199f5  call    cs:__imp_RpcRevertToSelf
0x1800199fb  test    eax, eax
0x1800199fd  jnz     short loc_180019A11
0x1800199ff  sub     ebx, [rsp+68h+arg_10]
0x180019a06  neg     ebx
0x180019a08  sbb     eax, eax
0x180019a0a  and     eax, 5
0x180019a0d  mov     [rdi], eax
0x180019a0f  xor     eax, eax
0x180019a11  mov     rbx, [rsp+68h+arg_0]
0x180019a16  add     rsp, 60h
0x180019a1a  pop     rdi
0x180019a1b  retn
```
