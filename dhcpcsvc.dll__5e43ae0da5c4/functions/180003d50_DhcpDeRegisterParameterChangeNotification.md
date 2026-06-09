# DhcpDeRegisterParameterChangeNotification

- ea: `0x180003d50`
- end: `0x180003e66`
- name: `DhcpDeRegisterParameterChangeNotification`
- size: `278`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800031c0`
- `0x1800062b0`

## callees

- `0x180003d50`
- `0x18000f4ec`
- `0x180011f08`
- `0x1800127f0`
- `0x180012a40`
- `0x180012df0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180003dcd`
- `RPCRT4!NdrClientCall3` at `0x180003dcd`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180003d89`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180003de9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180003e07`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180003d89`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180003de9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180003e07`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentProcessId` at `0x180003d78`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentProcessId` at `0x180003d78`
- `api-ms-win-downlevel-kernel32-l1-1-0!CloseHandle` at `0x180003e32`
- `api-ms-win-downlevel-kernel32-l1-1-0!CloseHandle` at `0x180003e32`

## pseudocode

```c
__int64 __fastcall DhcpDeRegisterParameterChangeNotification(HANDLE hObject, __int64 a2, __int64 a3)
{
  DWORD CurrentProcessId; // ebx
  LPWSTR CommandLineW; // rax
  CLIENT_CALL_RETURN v6; // rcx
  unsigned int Pointer; // ebx
  LPWSTR v8; // rax
  CLIENT_CALL_RETURN v10; // [rsp+20h] [rbp-28h]

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_q(hObject, 87, a3, hObject);
  CurrentProcessId = GetCurrentProcessId();
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 88, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xFu, 0, 0, CurrentProcessId, hObject).Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v8 = GetCommandLineW();
    WPP_SF_DS(1028, 89, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v8);
  }
  if ( !Pointer )
    CloseHandle(hObject);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    LODWORD(v10.Pointer) = Pointer;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qD)(
      (CLIENT_CALL_RETURN)v6.Simple,
      90,
      WPP_e15037783097355a5233924022d92169_Traceguids,
      hObject,
      (CLIENT_CALL_RETURN)v10.Simple);
  }
  return Pointer;
}

```

## disassembly

```asm
0x180003d50  mov     [rsp+arg_10], rbx
0x180003d55  mov     [rsp+arg_0], rcx
0x180003d5a  push    rdi
0x180003d5b  sub     rsp, 40h
0x180003d5f  mov     rdi, rcx
0x180003d62  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180003d69  jz      short loc_180003D78
0x180003d6b  mov     edx, 57h ; 'W'
0x180003d70  mov     r9, rcx
0x180003d73  call    WPP_SF_q
0x180003d78  call    cs:__imp_GetCurrentProcessId
0x180003d7e  mov     ebx, eax
0x180003d80  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180003d87  jz      short loc_180003DA9
0x180003d89  call    cs:__imp_GetCommandLineW
0x180003d8f  mov     r9, rax
0x180003d92  mov     edx, 58h ; 'X'
0x180003d97  mov     ecx, 404h
0x180003d9c  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180003da3  call    WPP_SF_S
0x180003da8  nop
0x180003da9  mov     [rsp+48h+arg_8], 0
0x180003db2  mov     [rsp+48h+var_20], rdi
0x180003db7  mov     dword ptr [rsp+48h+var_28], ebx
0x180003dbb  xor     r9d, r9d
0x180003dbe  xor     r8d, r8d; pReturnValue
0x180003dc1  mov     edx, 0Fh; nProcNum
0x180003dc6  lea     rcx, pProxyInfo; pProxyInfo
0x180003dcd  call    cs:__imp_NdrClientCall3
0x180003dd3  mov     rbx, rax
0x180003dd6  mov     [rsp+48h+arg_8], rax
0x180003ddb  mov     [rsp+48h+var_18], eax
0x180003ddf  jmp     short loc_180003DFE
0x180003de1  mov     edi, eax
0x180003de3  mov     ebx, eax
0x180003de5  mov     [rsp+48h+var_18], eax
0x180003de9  call    cs:__imp_GetCommandLineW
0x180003def  mov     rdx, rax
0x180003df2  mov     ecx, ebx
0x180003df4  call    TraceRpcException
0x180003df9  mov     rdi, [rsp+48h+arg_0]
0x180003dfe  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180003e05  jz      short loc_180003E2B
0x180003e07  call    cs:__imp_GetCommandLineW
0x180003e0d  mov     edx, 59h ; 'Y'
0x180003e12  mov     ecx, 404h
0x180003e17  mov     [rsp+48h+var_28], rax
0x180003e1c  mov     r9d, ebx
0x180003e1f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180003e26  call    WPP_SF_DS
0x180003e2b  test    ebx, ebx
0x180003e2d  jnz     short loc_180003E38
0x180003e2f  mov     rcx, rdi; hObject
0x180003e32  call    cs:__imp_CloseHandle
0x180003e38  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180003e3f  jz      short loc_180003E59
0x180003e41  mov     edx, 5Ah ; 'Z'
0x180003e46  mov     dword ptr [rsp+48h+var_28], ebx
0x180003e4a  mov     r9, rdi
0x180003e4d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180003e54  call    WPP_SF_qD
0x180003e59  mov     eax, ebx
0x180003e5b  mov     rbx, [rsp+48h+arg_10]
0x180003e60  add     rsp, 40h
0x180003e64  pop     rdi
0x180003e65  retn
0x180010c20  push    rbp
0x180010c22  sub     rsp, 30h
0x180010c26  mov     rbp, rdx
0x180010c29  mov     rcx, [rcx]
0x180010c2c  mov     ecx, [rcx]; ExceptionCode
0x180010c2e  call    cs:__imp_I_RpcExceptionFilter
0x180010c34  nop
0x180010c35  add     rsp, 30h
0x180010c39  pop     rbp
0x180010c3a  retn
```
