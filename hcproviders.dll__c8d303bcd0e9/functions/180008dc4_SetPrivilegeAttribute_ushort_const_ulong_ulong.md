# SetPrivilegeAttribute(ushort const *,ulong,ulong *)

- ea: `0x180008dc4`
- end: `0x180008ecf`
- name: `?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z`
- size: `267`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008a60`

## callees

- `0x180008d00`
- `0x180008dc4`
- `0x180009e40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ea0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e92`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180008e66`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180008e66`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180008dfe`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180008dfe`

## string_xrefs

- `0x180008df5`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall SetPrivilegeAttribute(const unsigned __int16 *a1, DWORD a2, unsigned int *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  DWORD LastError; // ebx
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-18h] BYREF

  Luid = 0;
  if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &Luid)
    && (TokenHandle = 0, (int)SHOpenEffectiveToken(v6, v5, &TokenHandle) >= 0) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a2;
    PreviousState = 0;
    ReturnLength = 16;
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) && a3 )
      *a3 = PreviousState.Privileges[0].Attributes;
    LastError = GetLastError();
    CloseHandle(TokenHandle);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180008dc4  mov     [rsp-8+arg_0], rbx
0x180008dc9  mov     [rsp-8+arg_8], rdi
0x180008dce  push    rbp
0x180008dcf  mov     rbp, rsp
0x180008dd2  sub     rsp, 70h
0x180008dd6  mov     rax, cs:__security_cookie
0x180008ddd  xor     rax, rsp
0x180008de0  mov     [rbp+var_8], rax
0x180008de4  mov     rbx, r8
0x180008de7  mov     qword ptr [rbp+Luid.LowPart], 0
0x180008def  mov     edi, edx
0x180008df1  lea     r8, [rbp+Luid]; lpLuid
0x180008df5  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x180008dfc  xor     ecx, ecx; lpSystemName
0x180008dfe  call    cs:__imp_LookupPrivilegeValueW
0x180008e05  nop     dword ptr [rax+rax+00h]
0x180008e0a  test    eax, eax
0x180008e0c  jz      loc_180008EA0
0x180008e12  lea     r8, [rbp+TokenHandle]; void **
0x180008e16  mov     [rbp+TokenHandle], 0
0x180008e1e  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x180008e23  test    eax, eax
0x180008e25  js      short loc_180008EA0
0x180008e27  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180008e2b  lea     r8, [rbp+NewState]; NewState
0x180008e2f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180008e33  xorps   xmm0, xmm0
0x180008e36  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x180008e3a  mov     r9d, 10h; BufferLength
0x180008e40  lea     rax, [rbp+var_40]
0x180008e44  mov     [rbp+NewState.PrivilegeCount], 1
0x180008e4b  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180008e50  xor     edx, edx; DisableAllPrivileges
0x180008e52  lea     rax, [rbp+var_18]
0x180008e56  mov     [rbp+NewState.Privileges.Attributes], edi
0x180008e59  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180008e5e  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm0
0x180008e62  mov     [rbp+var_40], r9d
0x180008e66  call    cs:__imp_AdjustTokenPrivileges
0x180008e6d  nop     dword ptr [rax+rax+00h]
0x180008e72  test    eax, eax
0x180008e74  jz      short loc_180008E80
0x180008e76  test    rbx, rbx
0x180008e79  jz      short loc_180008E80
0x180008e7b  mov     eax, [rbp+var_18.Privileges.Attributes]
0x180008e7e  mov     [rbx], eax
0x180008e80  call    cs:__imp_GetLastError
0x180008e87  nop     dword ptr [rax+rax+00h]
0x180008e8c  mov     rcx, [rbp+TokenHandle]; hObject
0x180008e90  mov     ebx, eax
0x180008e92  call    cs:__imp_CloseHandle
0x180008e99  nop     dword ptr [rax+rax+00h]
0x180008e9e  jmp     short loc_180008EAE
0x180008ea0  call    cs:__imp_GetLastError
0x180008ea7  nop     dword ptr [rax+rax+00h]
0x180008eac  mov     ebx, eax
0x180008eae  mov     eax, ebx
0x180008eb0  mov     rcx, [rbp+var_8]
0x180008eb4  xor     rcx, rsp; StackCookie
0x180008eb7  call    __security_check_cookie
0x180008ebc  lea     r11, [rsp+70h+var_s0]
0x180008ec1  mov     rbx, [r11+10h]
0x180008ec5  mov     rdi, [r11+18h]
0x180008ec9  mov     rsp, r11
0x180008ecc  pop     rbp
0x180008ecd  retn
```
