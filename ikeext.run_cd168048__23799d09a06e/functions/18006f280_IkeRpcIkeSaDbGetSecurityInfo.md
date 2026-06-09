# IkeRpcIkeSaDbGetSecurityInfo

- ea: `0x18006f280`
- end: `0x18006f335`
- name: `IkeRpcIkeSaDbGetSecurityInfo`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004aa3c`
- `0x18006e82c`
- `0x18006f280`
- `0x1800ec308`
- `0x1800ec660`
- `0x1800ecb7c`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18006f308`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006f308`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006f2f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006f2f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006f2ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006f2ce`

## string_xrefs

- `0x18006f29c`: `IkeRpcIkeSaDbGetSecurityInfo`
- `0x18006f31e`: `IkeRpcIkeSaDbGetSecurityInfo`

## pseudocode

```c
__int64 __fastcall IkeRpcIkeSaDbGetSecurityInfo(__int64 a1, SECURITY_INFORMATION a2, __int64 a3)
{
  __int64 SecurityInfo; // rdi
  __int64 v7; // rax
  PSECURITY_DESCRIPTOR v8; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp+20h] BYREF

  SecurityDescriptor = 0;
  TraceLogHelper("IkeRpcIkeSaDbGetSecurityInfo", 1);
  SecurityInfo = IkeCanAcceptRpcCall();
  if ( !SecurityInfo )
  {
    v7 = IkeSecurityInformationValidate(a2);
    LODWORD(SecurityInfo) = v7;
    if ( !v7 )
    {
      AcquireSRWLockShared(&gIkeRpcIkeSecurityDescLock);
      SecurityInfo = IkeSaDbGetSecurityInfo(*(&gIkeRpcIntfc + 1), a1, a2, &SecurityDescriptor);
      ReleaseSRWLockShared(&gIkeRpcIkeSecurityDescLock);
      if ( !SecurityInfo )
      {
        v8 = SecurityDescriptor;
        *(_DWORD *)a3 = RtlLengthSecurityDescriptor(SecurityDescriptor);
        *(_QWORD *)(a3 + 8) = v8;
      }
    }
  }
  IkeRpcRaiseExceptionIfError(SecurityInfo);
  TraceLogHelper("IkeRpcIkeSaDbGetSecurityInfo", 0);
  return 0;
}

```

## disassembly

```asm
0x18006f280  push    rbx
0x18006f282  push    rbp
0x18006f283  push    rsi
0x18006f284  push    rdi
0x18006f285  sub     rsp, 28h
0x18006f289  mov     ebx, edx
0x18006f28b  mov     [rsp+48h+SecurityDescriptor], 0
0x18006f294  mov     rbp, rcx
0x18006f297  mov     edx, 1
0x18006f29c  lea     rcx, aIkerpcikesadbg; "IkeRpcIkeSaDbGetSecurityInfo"
0x18006f2a3  mov     rsi, r8
0x18006f2a6  call    TraceLogHelper
0x18006f2ab  call    IkeCanAcceptRpcCall
0x18006f2b0  mov     rdi, rax
0x18006f2b3  test    rax, rax
0x18006f2b6  jnz     short loc_18006F314
0x18006f2b8  mov     ecx, ebx
0x18006f2ba  call    IkeSecurityInformationValidate
0x18006f2bf  mov     rdi, rax
0x18006f2c2  test    rax, rax
0x18006f2c5  jnz     short loc_18006F314
0x18006f2c7  lea     rcx, gIkeRpcIkeSecurityDescLock; SRWLock
0x18006f2ce  call    cs:__imp_AcquireSRWLockShared
0x18006f2d4  mov     rcx, qword ptr cs:gIkeRpcIntfc+8; pSecurityDescriptor
0x18006f2db  lea     r9, [rsp+48h+SecurityDescriptor]
0x18006f2e0  mov     r8d, ebx
0x18006f2e3  mov     rdx, rbp
0x18006f2e6  call    IkeSaDbGetSecurityInfo
0x18006f2eb  lea     rcx, gIkeRpcIkeSecurityDescLock; SRWLock
0x18006f2f2  mov     rdi, rax
0x18006f2f5  call    cs:__imp_ReleaseSRWLockShared
0x18006f2fb  test    rdi, rdi
0x18006f2fe  jnz     short loc_18006F314
0x18006f300  mov     rbx, [rsp+48h+SecurityDescriptor]
0x18006f305  mov     rcx, rbx; SecurityDescriptor
0x18006f308  call    cs:__imp_RtlLengthSecurityDescriptor
0x18006f30e  mov     [rsi], eax
0x18006f310  mov     [rsi+8], rbx
0x18006f314  mov     rcx, rdi; exception
0x18006f317  call    IkeRpcRaiseExceptionIfError
0x18006f31c  xor     edx, edx
0x18006f31e  lea     rcx, aIkerpcikesadbg; "IkeRpcIkeSaDbGetSecurityInfo"
0x18006f325  call    TraceLogHelper
0x18006f32a  xor     eax, eax
0x18006f32c  add     rsp, 28h
0x18006f330  pop     rdi
0x18006f331  pop     rsi
0x18006f332  pop     rbp
0x18006f333  pop     rbx
0x18006f334  retn
```
