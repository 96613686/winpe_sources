# CAAccessCheckpEx(void *,void *,ulong,int)

- ea: `0x180029ddc`
- end: `0x18002a046`
- name: `?CAAccessCheckpEx@@YAJPEAX0KH@Z`
- size: `618`
- prototype: `__int64 __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext, PSECURITY_DESCRIPTOR pSecurityDescriptor, unsigned int, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000af94`
- `0x18002cfd0`
- `0x18002d010`
- `0x18002fa3c`

## callees

- `0x180008400`
- `0x180008610`
- `0x180010600`
- `0x180012450`
- `0x180029ddc`

## import_xrefs

- `AUTHZ!AuthzAccessCheck` at `0x180029ee2`
- `AUTHZ!AuthzAccessCheck` at `0x180029f58`
- `AUTHZ!AuthzAccessCheck` at `0x180029fd2`
- `AUTHZ!AuthzAccessCheck` at `0x180029ee2`
- `AUTHZ!AuthzAccessCheck` at `0x180029f58`
- `AUTHZ!AuthzAccessCheck` at `0x180029fd2`

## pseudocode

```c
__int64 __fastcall CAAccessCheckpEx(
        AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        unsigned int a3,
        int a4)
{
  unsigned int v7; // edi
  int TemplateAccessRights; // eax
  unsigned int v9; // ebx
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  int v14; // [rsp+50h] [rbp-9h] BYREF
  int v15; // [rsp+54h] [rbp-5h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+58h] [rbp-1h] BYREF
  unsigned int v17; // [rsp+D8h] [rbp+7Fh] BYREF

  v17 = 0;
  v7 = 0;
  if ( a4 )
  {
    v17 = 0;
    pReply.GrantedAccessMask = &v17;
    pReply.Error = (PDWORD)&v14;
    pReply.SaclEvaluationResults = (PDWORD)&v15;
    v14 = 0;
    v15 = 0;
    *(_QWORD *)&pReply.ResultListLength = 1;
    if ( pSecurityDescriptor && hAuthzClientContext )
    {
      if ( (a3 & 0xFFFFFFF8) != 0 )
      {
        v9 = -2147024809;
        CSPrintErrorLineFile(0x39E0194u, -2147024809);
        goto LABEL_32;
      }
      if ( (a3 & 4) != 0 )
      {
        if ( !AuthzAccessCheck(0, hAuthzClientContext, &g_AuthzRequestRead, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
        {
          v9 = myHLastError();
          v12 = 62194068;
          goto LABEL_31;
        }
        if ( *pReply.Error || (v17 & 0x10) == 0 )
          goto LABEL_6;
        v7 = 4;
      }
      if ( (a3 & 1) != 0 )
      {
        v17 = 0;
        v14 = 0;
        v15 = 0;
        if ( !AuthzAccessCheck(0, hAuthzClientContext, &g_AuthzRequestEnroll, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
        {
          v9 = myHLastError();
          v12 = 64356756;
          goto LABEL_31;
        }
        if ( *pReply.Error || (v17 & 0x100) == 0 )
          goto LABEL_6;
        v7 |= 1u;
      }
      if ( (a3 & 2) == 0 )
        goto LABEL_6;
      v17 = 0;
      v14 = 0;
      v15 = 0;
      if ( AuthzAccessCheck(0, hAuthzClientContext, &g_AuthzRequestAutoEnroll, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
      {
        if ( !*pReply.Error && (v17 & 0x100) != 0 )
          v7 |= 2u;
        goto LABEL_6;
      }
      v9 = myHLastError();
      v12 = 66453908;
    }
    else
    {
      v9 = -2147467261;
      v12 = 60031380;
    }
LABEL_31:
    CSPrintErrorLineFile(v12, v9);
    if ( !v9 )
      goto LABEL_6;
LABEL_32:
    v10 = v9;
    v11 = 78054182;
    goto LABEL_4;
  }
  TemplateAccessRights = myGetTemplateAccessRights(hAuthzClientContext, pSecurityDescriptor, a3, &v17);
  v9 = TemplateAccessRights;
  if ( TemplateAccessRights )
  {
    v10 = TemplateAccessRights;
    v11 = 77464358;
LABEL_4:
    CSPrintErrorLineFile(v11, v10);
    return v9;
  }
  v7 = v17;
LABEL_6:
  if ( (a3 & 0xFFFEFFFF) == v7 )
  {
    return 0;
  }
  else
  {
    v9 = -2147024891;
    CSPrintErrorLineFileData2(0, 0x4B00326u, -2147024891, -2147024891);
  }
  return v9;
}

```

## disassembly

```asm
0x180029ddc  push    rbp
0x180029dde  push    rbx
0x180029ddf  push    rsi
0x180029de0  push    rdi
0x180029de1  push    r14
0x180029de3  push    r15
0x180029de5  lea     rbp, [rsp-2Fh]
0x180029dea  sub     rsp, 88h
0x180029df1  xor     r15d, r15d
0x180029df4  mov     esi, r8d
0x180029df7  mov     [rbp+57h+arg_18], r15d
0x180029dfb  mov     r14, rdx
0x180029dfe  mov     rbx, rcx
0x180029e01  mov     edi, r15d
0x180029e04  test    r9d, r9d
0x180029e07  jnz     short loc_180029E54
0x180029e09  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x180029e0d  call    ?myGetTemplateAccessRights@@YAJPEAX0KPEAK@Z; myGetTemplateAccessRights(void *,void *,ulong,ulong *)
0x180029e12  mov     ebx, eax
0x180029e14  test    eax, eax
0x180029e16  jz      short loc_180029E29
0x180029e18  mov     edx, eax; int
0x180029e1a  mov     ecx, 49E0326h; unsigned int
0x180029e1f  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180029e24  jmp     loc_18002A034
0x180029e29  mov     edi, [rbp+57h+arg_18]
0x180029e2c  btr     esi, 10h
0x180029e30  cmp     esi, edi
0x180029e32  jz      loc_18002A031
0x180029e38  mov     ebx, 80070005h
0x180029e3d  mov     edx, 4B00326h; unsigned int
0x180029e42  mov     r9d, ebx; int
0x180029e45  mov     r8d, ebx; int
0x180029e48  xor     ecx, ecx; unsigned __int16 *
0x180029e4a  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180029e4f  jmp     loc_18002A034
0x180029e54  mov     [rbp+57h+arg_18], r15d
0x180029e58  lea     rax, [rbp+57h+arg_18]
0x180029e5c  mov     [rbp+57h+var_58.GrantedAccessMask], rax
0x180029e60  lea     rax, [rbp+57h+var_60]
0x180029e64  mov     [rbp+57h+var_58.Error], rax
0x180029e68  lea     rax, [rbp+57h+var_5C]
0x180029e6c  mov     [rbp+57h+var_58.SaclEvaluationResults], rax
0x180029e70  mov     [rbp+57h+var_60], r15d
0x180029e74  mov     [rbp+57h+var_5C], r15d
0x180029e78  mov     qword ptr [rbp+57h+var_58.ResultListLength], 1
0x180029e80  test    r14, r14
0x180029e83  jz      loc_18002A00C
0x180029e89  test    rbx, rbx
0x180029e8c  jz      loc_18002A00C
0x180029e92  test    esi, 0FFFFFFF8h
0x180029e98  jz      short loc_180029EB0
0x180029e9a  mov     ebx, 80070057h
0x180029e9f  mov     ecx, 39E0194h; unsigned int
0x180029ea4  mov     edx, ebx; int
0x180029ea6  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180029eab  jmp     loc_18002A025
0x180029eb0  test    sil, 4
0x180029eb4  jz      short loc_180029F1A
0x180029eb6  mov     [rsp+0B0h+phAccessCheckResults], r15; phAccessCheckResults
0x180029ebb  lea     rax, [rbp+57h+var_58]
0x180029ebf  mov     [rsp+0B0h+pReply], rax; pReply
0x180029ec4  lea     r8, ?g_AuthzRequestRead@@3U_AUTHZ_ACCESS_REQUEST@@A; pRequest
0x180029ecb  mov     [rsp+0B0h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x180029ed0  xor     r9d, r9d; hAuditEvent
0x180029ed3  mov     [rsp+0B0h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x180029ed8  mov     rdx, rbx; hAuthzClientContext
0x180029edb  xor     ecx, ecx; Flags
0x180029edd  mov     [rsp+0B0h+pSecurityDescriptor], r14; pSecurityDescriptor
0x180029ee2  call    cs:__imp_AuthzAccessCheck
0x180029ee8  test    eax, eax
0x180029eea  jnz     short loc_180029EFD
0x180029eec  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180029ef1  mov     ebx, eax
0x180029ef3  mov     ecx, 3B50194h
0x180029ef8  jmp     loc_18002A016
0x180029efd  mov     rax, [rbp+57h+var_58.Error]
0x180029f01  cmp     [rax], r15d
0x180029f04  jnz     loc_180029E2C
0x180029f0a  mov     eax, [rbp+57h+arg_18]
0x180029f0d  test    al, 10h
0x180029f0f  jz      loc_180029E2C
0x180029f15  mov     edi, 4
0x180029f1a  test    sil, 1
0x180029f1e  jz      short loc_180029F90
0x180029f20  mov     [rsp+0B0h+phAccessCheckResults], r15; phAccessCheckResults
0x180029f25  lea     rax, [rbp+57h+var_58]
0x180029f29  mov     [rsp+0B0h+pReply], rax; pReply
0x180029f2e  lea     r8, ?g_AuthzRequestEnroll@@3U_AUTHZ_ACCESS_REQUEST@@A; pRequest
0x180029f35  mov     [rsp+0B0h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x180029f3a  xor     r9d, r9d; hAuditEvent
0x180029f3d  mov     [rsp+0B0h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x180029f42  mov     rdx, rbx; hAuthzClientContext
0x180029f45  xor     ecx, ecx; Flags
0x180029f47  mov     [rsp+0B0h+pSecurityDescriptor], r14; pSecurityDescriptor
0x180029f4c  mov     [rbp+57h+arg_18], r15d
0x180029f50  mov     [rbp+57h+var_60], r15d
0x180029f54  mov     [rbp+57h+var_5C], r15d
0x180029f58  call    cs:__imp_AuthzAccessCheck
0x180029f5e  test    eax, eax
0x180029f60  jnz     short loc_180029F73
0x180029f62  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180029f67  mov     ebx, eax
0x180029f69  mov     ecx, 3D60194h
0x180029f6e  jmp     loc_18002A016
0x180029f73  mov     rax, [rbp+57h+var_58.Error]
0x180029f77  cmp     [rax], r15d
0x180029f7a  jnz     loc_180029E2C
0x180029f80  test    [rbp+57h+arg_18], 100h
0x180029f87  jz      loc_180029E2C
0x180029f8d  or      edi, 1
0x180029f90  test    sil, 2
0x180029f94  jz      loc_180029E2C
0x180029f9a  mov     [rsp+0B0h+phAccessCheckResults], r15; phAccessCheckResults
0x180029f9f  lea     rax, [rbp+57h+var_58]
0x180029fa3  mov     [rsp+0B0h+pReply], rax; pReply
0x180029fa8  lea     r8, ?g_AuthzRequestAutoEnroll@@3U_AUTHZ_ACCESS_REQUEST@@A; pRequest
0x180029faf  mov     [rsp+0B0h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x180029fb4  xor     r9d, r9d; hAuditEvent
0x180029fb7  mov     [rsp+0B0h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x180029fbc  mov     rdx, rbx; hAuthzClientContext
0x180029fbf  xor     ecx, ecx; Flags
0x180029fc1  mov     [rsp+0B0h+pSecurityDescriptor], r14; pSecurityDescriptor
0x180029fc6  mov     [rbp+57h+arg_18], r15d
0x180029fca  mov     [rbp+57h+var_60], r15d
0x180029fce  mov     [rbp+57h+var_5C], r15d
0x180029fd2  call    cs:__imp_AuthzAccessCheck
0x180029fd8  test    eax, eax
0x180029fda  jnz     short loc_180029FEA
0x180029fdc  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180029fe1  mov     ebx, eax
0x180029fe3  mov     ecx, 3F60194h
0x180029fe8  jmp     short loc_18002A016
0x180029fea  mov     rax, [rbp+57h+var_58.Error]
0x180029fee  cmp     [rax], r15d
0x180029ff1  jnz     loc_180029E2C
0x180029ff7  test    [rbp+57h+arg_18], 100h
0x180029ffe  jz      loc_180029E2C
0x18002a004  or      edi, 2
0x18002a007  jmp     loc_180029E2C
0x18002a00c  mov     ebx, 80004003h
0x18002a011  mov     ecx, 3940194h; unsigned int
0x18002a016  mov     edx, ebx; int
0x18002a018  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002a01d  test    ebx, ebx
0x18002a01f  jz      loc_180029E2C
0x18002a025  mov     edx, ebx
0x18002a027  mov     ecx, 4A70326h
0x18002a02c  jmp     loc_180029E1F
0x18002a031  mov     ebx, r15d
0x18002a034  mov     eax, ebx
0x18002a036  add     rsp, 88h
0x18002a03d  pop     r15
0x18002a03f  pop     r14
0x18002a041  pop     rdi
0x18002a042  pop     rsi
0x18002a043  pop     rbx
0x18002a044  pop     rbp
0x18002a045  retn
```
