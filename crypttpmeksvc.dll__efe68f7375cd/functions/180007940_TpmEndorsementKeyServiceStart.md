# TpmEndorsementKeyServiceStart

- ea: `0x180007940`
- end: `0x180007a59`
- name: `TpmEndorsementKeyServiceStart`
- size: `281`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004e80`

## callees

- `0x180007940`
- `0x18000a800`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800079da`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800079da`
- `RPCRT4!RpcServerRegisterIf3` at `0x180007a23`
- `RPCRT4!RpcServerRegisterIf3` at `0x180007a23`

## pseudocode

```c
__int64 TpmEndorsementKeyServiceStart()
{
  DWORD LastError; // eax
  DWORD v1; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-59h] BYREF
  WCHAR StringSecurityDescriptor[72]; // [rsp+50h] [rbp-49h] BYREF

  wcscpy(StringSecurityDescriptor, L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;R;;;AC)");
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    LastError = RpcServerRegisterIf3(qword_18000C000, 0, 0, 33, 10, 0, CryptSvcSecurityCallback, SecurityDescriptor);
  else
    LastError = GetLastError();
  v1 = LastError;
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v1;
}

```

## disassembly

```asm
0x180007940  mov     [rsp-8+arg_0], rbx
0x180007945  push    rbp
0x180007946  lea     rbp, [rsp-57h]
0x18000794b  sub     rsp, 0F0h
0x180007952  mov     rax, cs:__security_cookie
0x180007959  xor     rax, rsp
0x18000795c  mov     [rbp+57h+var_10], rax
0x180007960  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x180007967  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000796b  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+10h; "GWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)("...
0x180007972  lea     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180007976  movups  xmmword ptr [rbp+57h+StringSecurityDescriptor], xmm0
0x18000797a  xor     r9d, r9d; SecurityDescriptorSize
0x18000797d  mov     [rbp+57h+SecurityDescriptor], 0
0x180007985  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+20h; "D)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;"...
0x18000798c  movups  [rbp+57h+var_80], xmm0
0x180007990  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+40h; "C)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)"
0x180007997  lea     edx, [r9+1]; StringSDRevision
0x18000799b  movups  [rbp+57h+var_90], xmm1
0x18000799f  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+30h; "GWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;G"...
0x1800079a6  movups  [rbp+57h+var_60], xmm0
0x1800079aa  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+60h; ";;GA;;;OW)(A;;GR;;;AC)"
0x1800079b1  movups  [rbp+57h+var_70], xmm1
0x1800079b5  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+50h; ";;;BA)(A;;GA;;;OW)(A;;GR;;;AC)"
0x1800079bc  movups  [rbp+57h+var_40], xmm0
0x1800079c0  movups  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+7Eh; "R;;;AC)"
0x1800079c7  movups  [rbp+57h+var_50], xmm1
0x1800079cb  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+70h; "W)(A;;GR;;;AC)"
0x1800079d2  movups  [rbp+57h+var_30], xmm1
0x1800079d6  movups  [rbp+57h+var_30+0Eh], xmm0
0x1800079da  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800079e0  test    eax, eax
0x1800079e2  jnz     short loc_1800079EC
0x1800079e4  call    cs:__imp_GetLastError
0x1800079ea  jmp     short loc_180007A29
0x1800079ec  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800079f0  lea     rcx, qword_18000C000
0x1800079f7  mov     [rsp+0F0h+var_B8], rax
0x1800079fc  mov     r9d, 21h ; '!'
0x180007a02  lea     rax, CryptSvcSecurityCallback
0x180007a09  xor     r8d, r8d
0x180007a0c  mov     [rsp+0F0h+var_C0], rax
0x180007a11  xor     edx, edx
0x180007a13  mov     [rsp+0F0h+var_C8], 0
0x180007a1b  mov     [rsp+0F0h+var_D0], 0Ah
0x180007a23  call    cs:__imp_RpcServerRegisterIf3
0x180007a29  mov     ebx, eax
0x180007a2b  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180007a2f  test    rcx, rcx
0x180007a32  jz      short loc_180007A3A
0x180007a34  call    cs:__imp_LocalFree
0x180007a3a  mov     eax, ebx
0x180007a3c  mov     rcx, [rbp+57h+var_10]
0x180007a40  xor     rcx, rsp; StackCookie
0x180007a43  call    __security_check_cookie
0x180007a48  mov     rbx, [rsp+0F0h+arg_0]
0x180007a50  add     rsp, 0F0h
0x180007a57  pop     rbp
0x180007a58  retn
```
