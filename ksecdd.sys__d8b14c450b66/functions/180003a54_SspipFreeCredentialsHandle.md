# SspipFreeCredentialsHandle

- ea: `0x180003a54`
- end: `0x180003c2f`
- name: `SspipFreeCredentialsHandle`
- size: `475`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800279c0`

## callees

- `0x180003a54`
- `0x180004050`
- `0x180004074`
- `0x180007594`
- `0x180010840`
- `0x180010920`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x180003af5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x180003af5`
- `ntoskrnl!PsGetCurrentProcess` at `0x180003ad2`
- `ntoskrnl!PsGetCurrentProcess` at `0x180003ad2`
- `ntoskrnl!PsGetProcessId` at `0x180003ae1`
- `ntoskrnl!PsGetProcessId` at `0x180003ae1`
- `msrpc!NdrClientCall3` at `0x180003b59`
- `msrpc!NdrClientCall3` at `0x180003b59`
- `msrpc!I_RpcExceptionFilter` at `0x180011327`
- `msrpc!I_RpcExceptionFilter` at `0x180011327`

## pseudocode

```c
__int64 __fastcall SspipFreeCredentialsHandle(_QWORD *a1)
{
  __int64 result; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  struct _KPROCESS *CurrentProcess; // rax
  CLIENT_CALL_RETURN v8; // rbx
  _BYTE *v9; // rcx
  __int64 v10; // rcx
  __int128 *v11; // rax
  __int64 v12; // rax
  __int64 v13; // [rsp+48h] [rbp-70h] BYREF
  CLIENT_CALL_RETURN v14; // [rsp+50h] [rbp-68h]
  __int128 v15; // [rsp+58h] [rbp-60h] BYREF
  __int128 v16; // [rsp+68h] [rbp-50h]
  PVOID DataBuffer[2]; // [rsp+78h] [rbp-40h]
  __int128 v18; // [rsp+88h] [rbp-30h] BYREF
  __int128 v19; // [rsp+98h] [rbp-20h] BYREF

  v13 = 0;
  v19 = 0;
  v18 = 0;
  v15 = 0;
  v16 = 0;
  *(_OWORD *)DataBuffer = 0;
  if ( !*a1 && !a1[1] )
    return 0;
  result = IsOkayToExecRpc(&v13);
  if ( (int)result >= 0 )
  {
    v18 = *(_OWORD *)a1;
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v4, v3, v5, v6);
    *(_QWORD *)&v19 = PsGetProcessId(CurrentProcess);
    *((_QWORD *)&v19 + 1) = PsGetCurrentThreadId();
    if ( *(_QWORD *)&WPP_MAIN_CB.DeviceType )
    {
      LODWORD(v8.Pointer) = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int128 *, _QWORD))(*(_QWORD *)&WPP_MAIN_CB.DeviceType
                                                                                              + 16LL))(
                              0,
                              &v19,
                              &v18,
                              0);
    }
    else
    {
      do
      {
        v14.Simple = 0;
        v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo, 5u, 0, v13, &v19, &v18, &v15).Pointer;
        v14.Pointer = v8.Pointer;
      }
      while ( (LODWORD(v8.Pointer) == -1073741801 || LODWORD(v8.Pointer) == -1073741670) && SspipSleep() >= 0 );
    }
    v9 = DataBuffer[0];
    if ( DataBuffer[0] )
    {
      v12 = DWORD2(v16);
      if ( DWORD2(v16) )
      {
        do
        {
          *v9++ = 0;
          --v12;
        }
        while ( v12 );
        v9 = DataBuffer[0];
      }
      SspiLocalFree(v9);
    }
    v10 = 48;
    v11 = &v15;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (__int128 *)((char *)v11 + 1);
      --v10;
    }
    while ( v10 );
    return LODWORD(v8.Pointer);
  }
  return result;
}

```

## disassembly

```asm
0x180003a54  mov     r11, rsp
0x180003a57  mov     [r11+10h], rbx
0x180003a5b  push    rsi
0x180003a5c  sub     rsp, 0B0h
0x180003a63  mov     rax, cs:__security_cookie
0x180003a6a  xor     rax, rsp
0x180003a6d  mov     [rsp+0B8h+var_10], rax
0x180003a75  mov     rsi, rcx
0x180003a78  mov     qword ptr [r11-70h], 0
0x180003a80  xorps   xmm0, xmm0
0x180003a83  movups  xmmword ptr [r11-20h], xmm0
0x180003a88  xorps   xmm1, xmm1
0x180003a8b  movups  xmmword ptr [r11-30h], xmm1
0x180003a90  movups  [rsp+0B8h+var_60], xmm0
0x180003a95  movups  [rsp+0B8h+var_50], xmm0
0x180003a9a  movups  xmmword ptr [rsp+0B8h+DataBuffer], xmm0
0x180003a9f  cmp     qword ptr [rcx], 0
0x180003aa3  jz      loc_180003BE8
0x180003aa9  lea     rcx, [rsp+0B8h+var_70]
0x180003aae  call    IsOkayToExecRpc
0x180003ab3  test    eax, eax
0x180003ab5  js      loc_180003BAC
0x180003abb  mov     rax, [rsi]
0x180003abe  mov     [rsp+0B8h+var_30], rax
0x180003ac6  mov     rax, [rsi+8]
0x180003aca  mov     [rsp+0B8h+var_28], rax
0x180003ad2  call    cs:__imp_PsGetCurrentProcess
0x180003ad9  nop     dword ptr [rax+rax+00h]
0x180003ade  mov     rcx, rax; Process
0x180003ae1  call    cs:__imp_PsGetProcessId
0x180003ae8  nop     dword ptr [rax+rax+00h]
0x180003aed  mov     [rsp+0B8h+var_20], rax
0x180003af5  call    cs:__imp_PsGetCurrentThreadId
0x180003afc  nop     dword ptr [rax+rax+00h]
0x180003b01  mov     [rsp+0B8h+var_18], rax
0x180003b09  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceType
0x180003b10  test    rax, rax
0x180003b13  jnz     loc_180003BF7
0x180003b19  mov     [rsp+0B8h+var_68], 0
0x180003b22  lea     rax, [rsp+0B8h+var_60]
0x180003b27  mov     [rsp+0B8h+var_88], rax
0x180003b2c  lea     rax, [rsp+0B8h+var_30]
0x180003b34  mov     [rsp+0B8h+var_90], rax
0x180003b39  lea     rax, [rsp+0B8h+var_20]
0x180003b41  mov     [rsp+0B8h+var_98], rax
0x180003b46  mov     r9, [rsp+0B8h+var_70]
0x180003b4b  xor     r8d, r8d; pReturnValue
0x180003b4e  lea     edx, [r8+5]; nProcNum
0x180003b52  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180003b59  call    cs:__imp_NdrClientCall3
0x180003b60  nop     dword ptr [rax+rax+00h]
0x180003b65  mov     rbx, rax
0x180003b68  mov     [rsp+0B8h+var_68], rax
0x180003b6d  mov     [rsp+0B8h+var_78], eax
0x180003b71  jmp     short loc_180003B79
0x180003b73  mov     ebx, eax
0x180003b75  mov     [rsp+0B8h+var_78], eax
0x180003b79  cmp     ebx, 0C0000017h
0x180003b7f  jnz     short loc_180003BCE
0x180003b81  call    ?SspipSleep@@YAJK@Z; SspipSleep(ulong)
0x180003b86  test    eax, eax
0x180003b88  jns     short loc_180003B19
0x180003b8a  mov     rcx, [rsp+0B8h+DataBuffer]; DataBuffer
0x180003b8f  test    rcx, rcx
0x180003b92  jnz     short loc_180003BD8
0x180003b94  mov     ecx, 30h ; '0'
0x180003b99  lea     rax, [rsp+0B8h+var_60]
0x180003b9e  mov     byte ptr [rax], 0
0x180003ba1  inc     rax
0x180003ba4  sub     rcx, 1
0x180003ba8  jnz     short loc_180003B9E
0x180003baa  mov     eax, ebx
0x180003bac  mov     rcx, [rsp+0B8h+var_10]
0x180003bb4  xor     rcx, rsp; StackCookie
0x180003bb7  call    __security_check_cookie
0x180003bbc  mov     rbx, [rsp+0B8h+arg_8]
0x180003bc4  add     rsp, 0B0h
0x180003bcb  pop     rsi
0x180003bcc  retn
0x180003bce  cmp     ebx, 0C000009Ah
0x180003bd4  jnz     short loc_180003B8A
0x180003bd6  jmp     short loc_180003B81
0x180003bd8  mov     eax, dword ptr [rsp+0B8h+var_50+8]
0x180003bdc  test    rax, rax
0x180003bdf  jnz     short loc_180003C1C
0x180003be1  call    SspiLocalFree
0x180003be6  jmp     short loc_180003B94
0x180003be8  cmp     qword ptr [rcx+8], 0
0x180003bed  jnz     loc_180003AA9
0x180003bf3  xor     eax, eax
0x180003bf5  jmp     short loc_180003BAC
0x180003bf7  mov     rax, [rax+10h]
0x180003bfb  xor     r9d, r9d
0x180003bfe  lea     r8, [rsp+0B8h+var_30]
0x180003c06  lea     rdx, [rsp+0B8h+var_20]
0x180003c0e  xor     ecx, ecx
0x180003c10  call    _guard_dispatch_icall
0x180003c15  mov     ebx, eax
0x180003c17  jmp     loc_180003B8A
0x180003c1c  mov     byte ptr [rcx], 0
0x180003c1f  inc     rcx
0x180003c22  sub     rax, 1
0x180003c26  jnz     short loc_180003C1C
0x180003c28  mov     rcx, [rsp+0B8h+DataBuffer]
0x180003c2d  jmp     short loc_180003BE1
0x180011319  push    rbp
0x18001131b  sub     rsp, 40h
0x18001131f  mov     rbp, rdx
0x180011322  mov     rcx, [rcx]
0x180011325  mov     ecx, [rcx]; ExceptionCode
0x180011327  call    cs:__imp_I_RpcExceptionFilter
0x18001132e  nop     dword ptr [rax+rax+00h]
0x180011333  nop
0x180011334  add     rsp, 40h
0x180011338  pop     rbp
0x180011339  retn
```
