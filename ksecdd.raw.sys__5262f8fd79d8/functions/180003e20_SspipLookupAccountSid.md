# SspipLookupAccountSid

- ea: `0x180003e20`
- end: `0x18000403e`
- name: `SspipLookupAccountSid`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180003660`

## callees

- `0x180003e20`
- `0x180004050`
- `0x180004074`
- `0x1800108a0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x180003f1b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x180003f1b`
- `ntoskrnl!PsGetCurrentProcess` at `0x180003ef8`
- `ntoskrnl!PsGetCurrentProcess` at `0x180003ef8`
- `ntoskrnl!PsGetProcessId` at `0x180003f07`
- `ntoskrnl!PsGetProcessId` at `0x180003f07`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180004006`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180004023`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180004006`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180004023`
- `msrpc!NdrClientCall3` at `0x180003f79`
- `msrpc!NdrClientCall3` at `0x180003f79`
- `msrpc!I_RpcExceptionFilter` at `0x1800113f7`
- `msrpc!I_RpcExceptionFilter` at `0x1800113f7`

## pseudocode

```c
__int64 __fastcall SspipLookupAccountSid(
        __int64 a1,
        _DWORD *a2,
        UNICODE_STRING *a3,
        _DWORD *a4,
        PUNICODE_STRING DestinationString,
        __int64 a6)
{
  int Pointer; // ebx
  struct _KPROCESS *CurrentProcess; // rax
  CLIENT_CALL_RETURN v13; // rax
  __int64 v14; // [rsp+58h] [rbp-A0h] BYREF
  PVOID v15[2]; // [rsp+60h] [rbp-98h] BYREF
  PVOID DataBuffer[2]; // [rsp+70h] [rbp-88h] BYREF
  CLIENT_CALL_RETURN v17; // [rsp+80h] [rbp-78h]
  _DWORD *v18; // [rsp+88h] [rbp-70h]
  UNICODE_STRING *v19; // [rsp+90h] [rbp-68h]
  _DWORD *v20; // [rsp+98h] [rbp-60h]
  PUNICODE_STRING v21; // [rsp+A0h] [rbp-58h]
  __int128 v22; // [rsp+A8h] [rbp-50h] BYREF

  v18 = a2;
  v19 = a3;
  v20 = a4;
  v21 = DestinationString;
  v14 = 0;
  v22 = 0;
  *(_OWORD *)v15 = 0;
  *(_OWORD *)DataBuffer = 0;
  Pointer = IsOkayToExecRpc(&v14);
  if ( Pointer >= 0 )
  {
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
    *(_QWORD *)&v22 = PsGetProcessId(CurrentProcess);
    *((_QWORD *)&v22 + 1) = PsGetCurrentThreadId();
    v17.Simple = 0;
    v13.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
                    0xEu,
                    0,
                    v14,
                    &v22,
                    a1,
                    v15,
                    DataBuffer,
                    a6).Pointer;
    Pointer = (int)v13.Pointer;
    v17.Pointer = v13.Pointer;
    if ( SLODWORD(v13.Simple) >= 0 )
    {
      if ( a2 )
        *a2 = LOWORD(v15[0]);
      if ( a4 )
        *a4 = LOWORD(DataBuffer[0]);
      if ( !a3
        || LOWORD(v15[0]) > a3->MaximumLength
        || DestinationString && LOWORD(DataBuffer[0]) > DestinationString->MaximumLength )
      {
        Pointer = -1073741789;
      }
      else
      {
        RtlCopyUnicodeString(a3, (PCUNICODE_STRING)v15);
        if ( DestinationString )
          RtlCopyUnicodeString(DestinationString, (PCUNICODE_STRING)DataBuffer);
      }
    }
  }
  if ( v15[1] )
    SspiLocalFree(v15[1]);
  if ( DataBuffer[1] )
    SspiLocalFree(DataBuffer[1]);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180003e20  push    rbx
0x180003e22  push    rsi
0x180003e23  push    rdi
0x180003e24  push    r12
0x180003e26  push    r13
0x180003e28  push    r14
0x180003e2a  push    r15
0x180003e2c  sub     rsp, 0C0h
0x180003e33  mov     rax, cs:__security_cookie
0x180003e3a  xor     rax, rsp
0x180003e3d  mov     [rsp+0F8h+var_40], rax
0x180003e45  mov     r14, r9
0x180003e48  mov     rsi, r8
0x180003e4b  mov     r15, rdx
0x180003e4e  mov     r12, rcx
0x180003e51  mov     [rsp+0F8h+var_70], rdx
0x180003e59  mov     [rsp+0F8h+var_68], r8
0x180003e61  mov     [rsp+0F8h+var_60], r9
0x180003e69  mov     rdi, [rsp+0F8h+DestinationString]
0x180003e71  mov     [rsp+0F8h+var_58], rdi
0x180003e79  mov     r13, [rsp+0F8h+arg_28]
0x180003e81  mov     [rsp+0F8h+var_A0], 0
0x180003e8a  xorps   xmm0, xmm0
0x180003e8d  movups  [rsp+0F8h+var_50], xmm0
0x180003e95  xorps   xmm1, xmm1
0x180003e98  movups  xmmword ptr [rsp+0F8h+var_98], xmm1
0x180003e9d  movups  xmmword ptr [rsp+0F8h+DataBuffer], xmm0
0x180003ea2  lea     rcx, [rsp+0F8h+var_A0]
0x180003ea7  call    IsOkayToExecRpc
0x180003eac  mov     ebx, eax
0x180003eae  test    eax, eax
0x180003eb0  jns     short loc_180003EF8
0x180003eb2  mov     rcx, [rsp+0F8h+var_98+8]; DataBuffer
0x180003eb7  test    rcx, rcx
0x180003eba  jnz     short loc_180003EF1
0x180003ebc  mov     rcx, [rsp+0F8h+DataBuffer+8]; DataBuffer
0x180003ec1  test    rcx, rcx
0x180003ec4  jz      short loc_180003ECB
0x180003ec6  call    SspiLocalFree
0x180003ecb  mov     eax, ebx
0x180003ecd  mov     rcx, [rsp+0F8h+var_40]
0x180003ed5  xor     rcx, rsp; StackCookie
0x180003ed8  call    __security_check_cookie
0x180003edd  add     rsp, 0C0h
0x180003ee4  pop     r15
0x180003ee6  pop     r14
0x180003ee8  pop     r13
0x180003eea  pop     r12
0x180003eec  pop     rdi
0x180003eed  pop     rsi
0x180003eee  pop     rbx
0x180003eef  retn
0x180003ef1  call    SspiLocalFree
0x180003ef6  jmp     short loc_180003EBC
0x180003ef8  call    cs:__imp_PsGetCurrentProcess
0x180003eff  nop     dword ptr [rax+rax+00h]
0x180003f04  mov     rcx, rax; Process
0x180003f07  call    cs:__imp_PsGetProcessId
0x180003f0e  nop     dword ptr [rax+rax+00h]
0x180003f13  mov     qword ptr [rsp+0F8h+var_50], rax
0x180003f1b  call    cs:__imp_PsGetCurrentThreadId
0x180003f22  nop     dword ptr [rax+rax+00h]
0x180003f27  mov     qword ptr [rsp+0F8h+var_50+8], rax
0x180003f2f  mov     [rsp+0F8h+var_78], 0
0x180003f3b  mov     [rsp+0F8h+var_B8], r13
0x180003f40  lea     rax, [rsp+0F8h+DataBuffer]
0x180003f45  mov     [rsp+0F8h+var_C0], rax
0x180003f4a  lea     rax, [rsp+0F8h+var_98]
0x180003f4f  mov     [rsp+0F8h+var_C8], rax
0x180003f54  mov     [rsp+0F8h+var_D0], r12
0x180003f59  lea     rax, [rsp+0F8h+var_50]
0x180003f61  mov     [rsp+0F8h+var_D8], rax
0x180003f66  mov     r9, [rsp+0F8h+var_A0]
0x180003f6b  xor     r8d, r8d; pReturnValue
0x180003f6e  lea     edx, [r8+0Eh]; nProcNum
0x180003f72  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180003f79  call    cs:__imp_NdrClientCall3
0x180003f80  nop     dword ptr [rax+rax+00h]
0x180003f85  mov     rbx, rax
0x180003f88  mov     [rsp+0F8h+var_78], rax
0x180003f90  mov     [rsp+0F8h+var_A8], eax
0x180003f94  jmp     short loc_180003FBC
0x180003f96  mov     ebx, eax
0x180003f98  mov     [rsp+0F8h+var_A8], eax
0x180003f9c  mov     r15, [rsp+0F8h+var_70]
0x180003fa4  mov     rsi, [rsp+0F8h+var_68]
0x180003fac  mov     r14, [rsp+0F8h+var_60]
0x180003fb4  mov     rdi, [rsp+0F8h+var_58]
0x180003fbc  test    ebx, ebx
0x180003fbe  js      loc_180003EB2
0x180003fc4  test    r15, r15
0x180003fc7  jz      short loc_180003FD1
0x180003fc9  movzx   eax, word ptr [rsp+0F8h+var_98]
0x180003fce  mov     [r15], eax
0x180003fd1  test    r14, r14
0x180003fd4  jz      short loc_180003FDE
0x180003fd6  movzx   eax, word ptr [rsp+0F8h+DataBuffer]
0x180003fdb  mov     [r14], eax
0x180003fde  test    rsi, rsi
0x180003fe1  jz      short loc_180004034
0x180003fe3  movzx   eax, word ptr [rsi+2]
0x180003fe7  cmp     word ptr [rsp+0F8h+var_98], ax
0x180003fec  ja      short loc_180004034
0x180003fee  test    rdi, rdi
0x180003ff1  jz      short loc_180003FFE
0x180003ff3  movzx   eax, word ptr [rdi+2]
0x180003ff7  cmp     word ptr [rsp+0F8h+DataBuffer], ax
0x180003ffc  ja      short loc_180004034
0x180003ffe  lea     rdx, [rsp+0F8h+var_98]; SourceString
0x180004003  mov     rcx, rsi; DestinationString
0x180004006  call    cs:__imp_RtlCopyUnicodeString
0x18000400d  nop     dword ptr [rax+rax+00h]
0x180004012  test    rdi, rdi
0x180004015  jz      loc_180003EB2
0x18000401b  lea     rdx, [rsp+0F8h+DataBuffer]; SourceString
0x180004020  mov     rcx, rdi; DestinationString
0x180004023  call    cs:__imp_RtlCopyUnicodeString
0x18000402a  nop     dword ptr [rax+rax+00h]
0x18000402f  jmp     loc_180003EB2
0x180004034  mov     ebx, 0C0000023h
0x180004039  jmp     loc_180003EB2
0x1800113e9  push    rbp
0x1800113eb  sub     rsp, 50h
0x1800113ef  mov     rbp, rdx
0x1800113f2  mov     rcx, [rcx]
0x1800113f5  mov     ecx, [rcx]; ExceptionCode
0x1800113f7  call    cs:__imp_I_RpcExceptionFilter
0x1800113fe  nop     dword ptr [rax+rax+00h]
0x180011403  nop
0x180011404  add     rsp, 50h
0x180011408  pop     rbp
0x180011409  retn
```
