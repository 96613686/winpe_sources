# SspipDeleteSecurityContext

- ea: `0x180003c38`
- end: `0x180003e17`
- name: `SspipDeleteSecurityContext`
- size: `479`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025db0`

## callees

- `0x180003c38`
- `0x180004050`
- `0x180004074`
- `0x180007594`
- `0x180010840`
- `0x180010920`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x180003cd9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x180003cd9`
- `ntoskrnl!PsGetCurrentProcess` at `0x180003cb6`
- `ntoskrnl!PsGetCurrentProcess` at `0x180003cb6`
- `ntoskrnl!PsGetProcessId` at `0x180003cc5`
- `ntoskrnl!PsGetProcessId` at `0x180003cc5`
- `msrpc!NdrClientCall3` at `0x180003d3d`
- `msrpc!NdrClientCall3` at `0x180003d3d`
- `msrpc!I_RpcExceptionFilter` at `0x18001134f`
- `msrpc!I_RpcExceptionFilter` at `0x18001134f`

## pseudocode

```c
__int64 __fastcall SspipDeleteSecurityContext(_QWORD *a1)
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
                                                                                              + 32LL))(
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
        v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo, 7u, 0, v13, &v19, &v18, &v15).Pointer;
        v14.Pointer = v8.Pointer;
      }
      while ( (LODWORD(v8.Pointer) == -1073741670 || LODWORD(v8.Pointer) == -1073741801) && SspipSleep() >= 0 );
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
0x180003c38  mov     r11, rsp
0x180003c3b  mov     [r11+10h], rbx
0x180003c3f  push    rsi
0x180003c40  sub     rsp, 0B0h
0x180003c47  mov     rax, cs:__security_cookie
0x180003c4e  xor     rax, rsp
0x180003c51  mov     [rsp+0B8h+var_10], rax
0x180003c59  mov     rsi, rcx
0x180003c5c  mov     qword ptr [r11-70h], 0
0x180003c64  xorps   xmm0, xmm0
0x180003c67  movups  xmmword ptr [r11-20h], xmm0
0x180003c6c  xorps   xmm1, xmm1
0x180003c6f  movups  xmmword ptr [r11-30h], xmm1
0x180003c74  movups  [rsp+0B8h+var_60], xmm0
0x180003c79  movups  [rsp+0B8h+var_50], xmm0
0x180003c7e  movups  xmmword ptr [rsp+0B8h+DataBuffer], xmm0
0x180003c83  cmp     qword ptr [rcx], 0
0x180003c87  jz      loc_180003DD0
0x180003c8d  lea     rcx, [rsp+0B8h+var_70]
0x180003c92  call    IsOkayToExecRpc
0x180003c97  test    eax, eax
0x180003c99  js      loc_180003D8F
0x180003c9f  mov     rax, [rsi]
0x180003ca2  mov     [rsp+0B8h+var_30], rax
0x180003caa  mov     rax, [rsi+8]
0x180003cae  mov     [rsp+0B8h+var_28], rax
0x180003cb6  call    cs:__imp_PsGetCurrentProcess
0x180003cbd  nop     dword ptr [rax+rax+00h]
0x180003cc2  mov     rcx, rax; Process
0x180003cc5  call    cs:__imp_PsGetProcessId
0x180003ccc  nop     dword ptr [rax+rax+00h]
0x180003cd1  mov     [rsp+0B8h+var_20], rax
0x180003cd9  call    cs:__imp_PsGetCurrentThreadId
0x180003ce0  nop     dword ptr [rax+rax+00h]
0x180003ce5  mov     [rsp+0B8h+var_18], rax
0x180003ced  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceType
0x180003cf4  test    rax, rax
0x180003cf7  jnz     loc_180003DDF
0x180003cfd  mov     [rsp+0B8h+var_68], 0
0x180003d06  lea     rax, [rsp+0B8h+var_60]
0x180003d0b  mov     [rsp+0B8h+var_88], rax
0x180003d10  lea     rax, [rsp+0B8h+var_30]
0x180003d18  mov     [rsp+0B8h+var_90], rax
0x180003d1d  lea     rax, [rsp+0B8h+var_20]
0x180003d25  mov     [rsp+0B8h+var_98], rax
0x180003d2a  mov     r9, [rsp+0B8h+var_70]
0x180003d2f  xor     r8d, r8d; pReturnValue
0x180003d32  lea     edx, [r8+7]; nProcNum
0x180003d36  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180003d3d  call    cs:__imp_NdrClientCall3
0x180003d44  nop     dword ptr [rax+rax+00h]
0x180003d49  mov     rbx, rax
0x180003d4c  mov     [rsp+0B8h+var_68], rax
0x180003d51  mov     [rsp+0B8h+var_78], eax
0x180003d55  jmp     short loc_180003D5D
0x180003d57  mov     ebx, eax
0x180003d59  mov     [rsp+0B8h+var_78], eax
0x180003d5d  cmp     ebx, 0C000009Ah
0x180003d63  jz      short loc_180003DB1
0x180003d65  cmp     ebx, 0C0000017h
0x180003d6b  jz      short loc_180003DB1
0x180003d6d  mov     rcx, [rsp+0B8h+DataBuffer]; DataBuffer
0x180003d72  test    rcx, rcx
0x180003d75  jnz     short loc_180003DC0
0x180003d77  mov     ecx, 30h ; '0'
0x180003d7c  lea     rax, [rsp+0B8h+var_60]
0x180003d81  mov     byte ptr [rax], 0
0x180003d84  inc     rax
0x180003d87  sub     rcx, 1
0x180003d8b  jnz     short loc_180003D81
0x180003d8d  mov     eax, ebx
0x180003d8f  mov     rcx, [rsp+0B8h+var_10]
0x180003d97  xor     rcx, rsp; StackCookie
0x180003d9a  call    __security_check_cookie
0x180003d9f  mov     rbx, [rsp+0B8h+arg_8]
0x180003da7  add     rsp, 0B0h
0x180003dae  pop     rsi
0x180003daf  retn
0x180003db1  call    ?SspipSleep@@YAJK@Z; SspipSleep(ulong)
0x180003db6  test    eax, eax
0x180003db8  jns     loc_180003CFD
0x180003dbe  jmp     short loc_180003D6D
0x180003dc0  mov     eax, dword ptr [rsp+0B8h+var_50+8]
0x180003dc4  test    rax, rax
0x180003dc7  jnz     short loc_180003E04
0x180003dc9  call    SspiLocalFree
0x180003dce  jmp     short loc_180003D77
0x180003dd0  cmp     qword ptr [rcx+8], 0
0x180003dd5  jnz     loc_180003C8D
0x180003ddb  xor     eax, eax
0x180003ddd  jmp     short loc_180003D8F
0x180003ddf  mov     rax, [rax+20h]
0x180003de3  xor     r9d, r9d
0x180003de6  lea     r8, [rsp+0B8h+var_30]
0x180003dee  lea     rdx, [rsp+0B8h+var_20]
0x180003df6  xor     ecx, ecx
0x180003df8  call    _guard_dispatch_icall
0x180003dfd  mov     ebx, eax
0x180003dff  jmp     loc_180003D6D
0x180003e04  mov     byte ptr [rcx], 0
0x180003e07  inc     rcx
0x180003e0a  sub     rax, 1
0x180003e0e  jnz     short loc_180003E04
0x180003e10  mov     rcx, [rsp+0B8h+DataBuffer]
0x180003e15  jmp     short loc_180003DC9
0x180011341  push    rbp
0x180011343  sub     rsp, 40h
0x180011347  mov     rbp, rdx
0x18001134a  mov     rcx, [rcx]
0x18001134d  mov     ecx, [rcx]; ExceptionCode
0x18001134f  call    cs:__imp_I_RpcExceptionFilter
0x180011356  nop     dword ptr [rax+rax+00h]
0x18001135b  nop
0x18001135c  add     rsp, 40h
0x180011360  pop     rbp
0x180011361  retn
```
