# FwMoneisDiagGetEnterpriseIdAsync

- ea: `0x180029d04`
- end: `0x18002a184`
- name: `FwMoneisDiagGetEnterpriseIdAsync`
- size: `1152`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, RPC_BINDING_HANDLE BindingHandle@<rdx>, LPCWSTR lpUnicodeCharStr@<r8>, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029c60`

## callees

- `0x180007b58`
- `0x180008d60`
- `0x18000a710`
- `0x1800192e0`
- `0x180029d04`
- `0x18002a18c`
- `0x18002ad78`
- `0x18002af34`
- `0x18002dcc0`
- `0x1800729c0`
- `0x180073488`
- `0x1800c0674`
- `0x1800c1888`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180029d6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180029d6f`
- `RPCRT4!RpcAsyncAbortCall` at `0x180029f08`
- `RPCRT4!RpcAsyncAbortCall` at `0x180029f08`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002a10a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002a10a`
- `fwbase!FwHResultToWindowsError` at `0x180029d9a`
- `fwbase!FwHResultToWindowsError` at `0x180029f47`
- `fwbase!FwHResultToWindowsError` at `0x18002a0ab`
- `fwbase!FwHResultToWindowsError` at `0x180029d9a`
- `fwbase!FwHResultToWindowsError` at `0x180029f47`
- `fwbase!FwHResultToWindowsError` at `0x18002a0ab`
- `fwbase!FwStringCopy` at `0x180029f39`
- `fwbase!FwStringCopy` at `0x18002a09d`
- `fwbase!FwStringCopy` at `0x180029f39`
- `fwbase!FwStringCopy` at `0x18002a09d`
- `fwbase!FwAlloc` at `0x180029eb9`
- `fwbase!FwAlloc` at `0x180029eb9`
- `fwbase!FwCriticalSectionLeave` at `0x180029de1`
- `fwbase!FwCriticalSectionLeave` at `0x180029de1`

## pseudocode

```c
__int64 __fastcall FwMoneisDiagGetEnterpriseIdAsync(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        LPCWSTR lpUnicodeCharStr,
        int a4,
        _DWORD *a5,
        const char **a6)
{
  DWORD TickCount; // eax
  DWORD v11; // r13d
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // ebx
  __int64 v15; // rcx
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // r9
  unsigned int v21; // eax
  unsigned int v22; // eax
  _QWORD *v23; // rcx
  unsigned int EnterpriseId; // eax
  __int64 v25; // rdx
  unsigned int v26; // eax
  unsigned int EnterpriseIdFromCaller; // eax
  int v28; // r8d
  unsigned int v29; // edx
  const char *v30; // rax
  int v31; // [rsp+34h] [rbp-1Ch]
  unsigned int ExceptionCode; // [rsp+38h] [rbp-18h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 119, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids);
  ++g_invokedGetEnterpriseId;
  v31 = 0;
  TickCount = GetTickCount();
  *a5 = 0;
  v11 = TickCount;
  *a6 = 0;
  v12 = FwAcquireRPCSharedLock("FwMoneisDiagGetEnterpriseIdAsync");
  v13 = FwHResultToWindowsError(v12);
  ExceptionCode = v13;
  if ( v13 )
  {
    v14 = 0;
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 120, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, v13);
      v15 = WPP_GLOBAL_Control;
    }
    goto LABEL_6;
  }
  v17 = EdpFieldsLock();
  if ( v17 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_31;
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      121,
      WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids,
      (unsigned int)v17);
    goto LABEL_38;
  }
  v31 = 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_S(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      122,
      WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids,
      lpUnicodeCharStr);
  if ( !qword_180132978 || !(unsigned int)FwMoneisDiagIsServerInPolicy(lpUnicodeCharStr) )
  {
    v18 = FwAlloc(128);
    v19 = v18;
    if ( v18 )
    {
      memset_0((void *)(v18 + 8), 0, 0x78u);
      *(_QWORD *)v19 = pAsync;
      v21 = FwStringCopy(lpUnicodeCharStr, v19 + 8);
      v22 = FwHResultToWindowsError(v21);
      ExceptionCode = v22;
      if ( !v22 )
      {
        *(_DWORD *)(v19 + 16) = a4;
        *(_QWORD *)(v19 + 24) = a5;
        *(_QWORD *)(v19 + 32) = a6;
        *(_DWORD *)(v19 + 56) = v11;
        v23 = (_QWORD *)qword_1801328F8;
        if ( *(__int64 **)qword_1801328F8 != &qword_1801328F0 )
          __fastfail(3u);
        *(_QWORD *)(v19 + 40) = &qword_1801328F0;
        *(_QWORD *)(v19 + 48) = v23;
        *v23 = v19 + 40;
        qword_1801328F8 = v19 + 40;
        EnterpriseId = FwMoneisDiagOperationGetEnterpriseId();
        v15 = WPP_GLOBAL_Control;
        v14 = 1;
        ExceptionCode = EnterpriseId;
        if ( EnterpriseId == 997 )
          ExceptionCode = 0;
LABEL_6:
        if ( !ExceptionCode )
          goto LABEL_7;
        goto LABEL_24;
      }
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_31:
        v14 = 1;
        goto LABEL_6;
      }
      v25 = 126;
      v20 = v22;
    }
    else
    {
      v20 = 14;
      ExceptionCode = 14;
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        v14 = 1;
LABEL_24:
        ++g_failedGetEnterpriseId;
        if ( pAsync->Event )
        {
          RpcAsyncAbortCall(pAsync, ExceptionCode);
          v15 = WPP_GLOBAL_Control;
        }
LABEL_7:
        if ( !v31 )
          goto LABEL_9;
        goto LABEL_8;
      }
      v25 = 125;
    }
    goto LABEL_37;
  }
  if ( (a4 & 3) != 0 )
  {
    v26 = FwStringCopy(L"*", a6);
    EnterpriseIdFromCaller = FwHResultToWindowsError(v26);
  }
  else
  {
    EnterpriseIdFromCaller = FwMoneisDiagTryGetEnterpriseIdFromCaller(BindingHandle);
  }
  v29 = EnterpriseIdFromCaller;
  ExceptionCode = EnterpriseIdFromCaller;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v30 = L"<null>";
    if ( *a6 )
      v30 = *a6;
    WPP_SF_SDS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v29, v28, (_DWORD)lpUnicodeCharStr, v29, (__int64)v30);
  }
  RpcAsyncCompleteCall(pAsync, &ExceptionCode);
  ExceptionCode = 0;
  v15 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v25 = 124;
    v20 = 0;
LABEL_37:
    WPP_SF_d(*(_QWORD *)(v15 + 16), v25, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, v20);
LABEL_38:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v14 = 1;
LABEL_8:
  FwCriticalSectionLeave(qword_180132910);
  v15 = WPP_GLOBAL_Control;
LABEL_9:
  if ( v14 )
  {
    FwReleaseRPCSharedLock("FwMoneisDiagGetEnterpriseIdAsync");
    v15 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v15 != &WPP_GLOBAL_Control && (*(_BYTE *)(v15 + 28) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(v15 + 16), 127, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, ExceptionCode);
  return ExceptionCode;
}

```

## disassembly

```asm
0x180029d04  mov     [rsp-38h+arg_18], rbx
0x180029d09  push    rbp
0x180029d0a  push    rsi
0x180029d0b  push    rdi
0x180029d0c  push    r12
0x180029d0e  push    r13
0x180029d10  push    r14
0x180029d12  push    r15
0x180029d14  mov     rbp, rsp
0x180029d17  sub     rsp, 50h
0x180029d1b  mov     rax, cs:__security_cookie
0x180029d22  xor     rax, rsp
0x180029d25  mov     [rbp+var_10], rax
0x180029d29  mov     r15, [rbp+arg_20]
0x180029d2d  mov     esi, r9d
0x180029d30  mov     rdi, [rbp+arg_28]
0x180029d34  mov     r14, r8
0x180029d37  mov     rbx, rdx
0x180029d3a  mov     r12, rcx
0x180029d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d44  lea     rax, WPP_GLOBAL_Control
0x180029d4b  cmp     rcx, rax
0x180029d4e  jz      short loc_180029D5A
0x180029d50  test    byte ptr [rcx+1Ch], 8
0x180029d54  jnz     loc_180029FE4
0x180029d5a  inc     cs:g_invokedGetEnterpriseId
0x180029d61  mov     [rbp+ExceptionCode], 0
0x180029d68  mov     [rbp+var_1C], 0
0x180029d6f  call    cs:__imp_GetTickCount
0x180029d76  nop     dword ptr [rax+rax+00h]
0x180029d7b  mov     dword ptr [r15], 0
0x180029d82  lea     rcx, aFwmoneisdiagge_1; "FwMoneisDiagGetEnterpriseIdAsync"
0x180029d89  mov     r13d, eax
0x180029d8c  mov     qword ptr [rdi], 0
0x180029d93  call    FwAcquireRPCSharedLock
0x180029d98  mov     ecx, eax
0x180029d9a  call    cs:__imp_FwHResultToWindowsError
0x180029da1  nop     dword ptr [rax+rax+00h]
0x180029da6  mov     [rbp+ExceptionCode], eax
0x180029da9  test    eax, eax
0x180029dab  jz      loc_180029E59
0x180029db1  xor     ebx, ebx
0x180029db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180029dba  lea     rsi, WPP_GLOBAL_Control
0x180029dc1  cmp     rcx, rsi
0x180029dc4  jnz     loc_180029FFE
0x180029dca  cmp     [rbp+ExceptionCode], 0
0x180029dce  jnz     loc_180029EEF
0x180029dd4  cmp     [rbp+var_1C], 0
0x180029dd8  jz      short loc_180029DF4
0x180029dda  lea     rcx, qword_180132910
0x180029de1  call    cs:__imp_FwCriticalSectionLeave
0x180029de8  nop     dword ptr [rax+rax+00h]
0x180029ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180029df4  test    ebx, ebx
0x180029df6  jz      short loc_180029E0B
0x180029df8  lea     rcx, aFwmoneisdiagge_1; "FwMoneisDiagGetEnterpriseIdAsync"
0x180029dff  call    FwReleaseRPCSharedLock
0x180029e04  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e0b  cmp     rcx, rsi
0x180029e0e  jnz     short loc_180029E38
0x180029e10  mov     eax, [rbp+ExceptionCode]
0x180029e13  mov     rcx, [rbp+var_10]
0x180029e17  xor     rcx, rsp; StackCookie
0x180029e1a  call    __security_check_cookie
0x180029e1f  mov     rbx, [rsp+50h+arg_18]
0x180029e27  add     rsp, 50h
0x180029e2b  pop     r15
0x180029e2d  pop     r14
0x180029e2f  pop     r13
0x180029e31  pop     r12
0x180029e33  pop     rdi
0x180029e34  pop     rsi
0x180029e35  pop     rbp
0x180029e36  retn
0x180029e38  test    byte ptr [rcx+1Ch], 8
0x180029e3c  jz      short loc_180029E10
0x180029e3e  mov     r9d, [rbp+ExceptionCode]
0x180029e42  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x180029e49  mov     rcx, [rcx+10h]
0x180029e4d  mov     edx, 7Fh
0x180029e52  call    WPP_SF_d
0x180029e57  jmp     short loc_180029E10
0x180029e59  mov     [rbp+var_20], 1
0x180029e60  call    EdpFieldsLock
0x180029e65  test    eax, eax
0x180029e67  js      loc_180029FC9
0x180029e6d  mov     [rbp+var_1C], 1
0x180029e74  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e7b  lea     rax, WPP_GLOBAL_Control
0x180029e82  cmp     rcx, rax
0x180029e85  jz      short loc_180029E91
0x180029e87  test    byte ptr [rcx+1Ch], 4
0x180029e8b  jnz     loc_18002A070
0x180029e91  cmp     cs:qword_180132978, 0
0x180029e99  jz      short loc_180029EB4
0x180029e9b  lea     r8, dword_180132980
0x180029ea2  mov     edx, esi
0x180029ea4  mov     rcx, r14; lpUnicodeCharStr
0x180029ea7  call    FwMoneisDiagIsServerInPolicy
0x180029eac  test    eax, eax
0x180029eae  jnz     loc_18002A08D
0x180029eb4  mov     ecx, 80h
0x180029eb9  call    cs:__imp_FwAlloc
0x180029ec0  nop     dword ptr [rax+rax+00h]
0x180029ec5  mov     rbx, rax
0x180029ec8  test    rax, rax
0x180029ecb  jnz     short loc_180029F20
0x180029ecd  lea     r9d, [rax+0Eh]
0x180029ed1  mov     [rbp+ExceptionCode], r9d
0x180029ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x180029edc  lea     rsi, WPP_GLOBAL_Control
0x180029ee3  cmp     rcx, rsi
0x180029ee6  jnz     loc_18002A13B
0x180029eec  mov     ebx, [rbp+var_20]
0x180029eef  inc     cs:g_failedGetEnterpriseId
0x180029ef6  cmp     dword ptr [r12+28h], 0
0x180029efc  jz      loc_180029DD4
0x180029f02  mov     edx, [rbp+ExceptionCode]; ExceptionCode
0x180029f05  mov     rcx, r12; pAsync
0x180029f08  call    cs:__imp_RpcAsyncAbortCall
0x180029f0f  nop     dword ptr [rax+rax+00h]
0x180029f14  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f1b  jmp     loc_180029DD4
0x180029f20  xor     edx, edx; Val
0x180029f22  lea     rcx, [rax+8]; void *
0x180029f26  lea     r8d, [rdx+78h]; Size
0x180029f2a  call    memset_0
0x180029f2f  lea     rdx, [rbx+8]
0x180029f33  mov     [rbx], r12
0x180029f36  mov     rcx, r14
0x180029f39  call    cs:__imp_FwStringCopy
0x180029f40  nop     dword ptr [rax+rax+00h]
0x180029f45  mov     ecx, eax
0x180029f47  call    cs:__imp_FwHResultToWindowsError
0x180029f4e  nop     dword ptr [rax+rax+00h]
0x180029f53  mov     [rbp+ExceptionCode], eax
0x180029f56  test    eax, eax
0x180029f58  jnz     loc_18002A14F
0x180029f5e  mov     [rbx+10h], esi
0x180029f61  lea     rdx, qword_1801328F0
0x180029f68  mov     [rbx+18h], r15
0x180029f6c  mov     [rbx+20h], rdi
0x180029f70  mov     [rbx+38h], r13d
0x180029f74  mov     rcx, cs:qword_1801328F8
0x180029f7b  cmp     [rcx], rdx
0x180029f7e  jnz     loc_18002A17D
0x180029f84  lea     rax, [rbx+28h]
0x180029f88  mov     [rax], rdx
0x180029f8b  mov     [rax+8], rcx
0x180029f8f  mov     [rcx], rax
0x180029f92  mov     cs:qword_1801328F8, rax
0x180029f99  call    FwMoneisDiagOperationGetEnterpriseId
0x180029f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fa5  lea     rsi, WPP_GLOBAL_Control
0x180029fac  mov     ebx, [rbp+var_20]
0x180029faf  mov     [rbp+ExceptionCode], eax
0x180029fb2  cmp     eax, 3E5h
0x180029fb7  jnz     loc_180029DCA
0x180029fbd  mov     [rbp+ExceptionCode], 0
0x180029fc4  jmp     loc_180029DCA
0x180029fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fd0  lea     rsi, WPP_GLOBAL_Control
0x180029fd7  cmp     rcx, rsi
0x180029fda  jnz     short loc_18002A02C
0x180029fdc  mov     ebx, [rbp+var_20]
0x180029fdf  jmp     loc_180029DCA
0x180029fe4  mov     rcx, [rcx+10h]
0x180029fe8  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x180029fef  mov     edx, 77h ; 'w'
0x180029ff4  call    WPP_SF_
0x180029ff9  jmp     loc_180029D5A
0x180029ffe  test    byte ptr [rcx+1Ch], 1
0x18002a002  jz      loc_180029DCA
0x18002a008  mov     rcx, [rcx+10h]
0x18002a00c  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x18002a013  mov     edx, 78h ; 'x'
0x18002a018  mov     r9d, eax
0x18002a01b  call    WPP_SF_d
0x18002a020  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a027  jmp     loc_180029DCA
0x18002a02c  test    byte ptr [rcx+1Ch], 1
0x18002a030  jz      short loc_180029FDC
0x18002a032  mov     rcx, [rcx+10h]
0x18002a036  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x18002a03d  mov     edx, 79h ; 'y'
0x18002a042  mov     r9d, eax
0x18002a045  call    WPP_SF_d
0x18002a04a  jmp     short loc_18002A064
0x18002a04c  mov     edx, 7Ch ; '|'
0x18002a051  xor     r9d, r9d
0x18002a054  mov     rcx, [rcx+10h]
0x18002a058  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x18002a05f  call    WPP_SF_d
0x18002a064  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a06b  jmp     loc_180029FDC
0x18002a070  mov     rcx, [rcx+10h]
0x18002a074  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x18002a07b  mov     edx, 7Ah ; 'z'
0x18002a080  mov     r9, r14
0x18002a083  call    WPP_SF_S
0x18002a088  jmp     loc_180029E91
0x18002a08d  mov     rdx, rdi
0x18002a090  test    sil, 3
0x18002a094  jz      short loc_18002A0B9
0x18002a096  lea     rcx, String1; "*"
0x18002a09d  call    cs:__imp_FwStringCopy
0x18002a0a4  nop     dword ptr [rax+rax+00h]
0x18002a0a9  mov     ecx, eax
0x18002a0ab  call    cs:__imp_FwHResultToWindowsError
0x18002a0b2  nop     dword ptr [rax+rax+00h]
0x18002a0b7  jmp     short loc_18002A0C1
0x18002a0b9  mov     rcx, rbx; BindingHandle
0x18002a0bc  call    FwMoneisDiagTryGetEnterpriseIdFromCaller
0x18002a0c1  mov     edx, eax
0x18002a0c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0ca  lea     rsi, WPP_GLOBAL_Control
0x18002a0d1  mov     [rbp+ExceptionCode], eax
0x18002a0d4  cmp     rcx, rsi
0x18002a0d7  jz      short loc_18002A103
0x18002a0d9  test    byte ptr [rcx+1Ch], 4
0x18002a0dd  jz      short loc_18002A103
0x18002a0df  cmp     qword ptr [rdi], 0
0x18002a0e3  lea     rax, aNull; "<null>"
0x18002a0ea  mov     rcx, [rcx+10h]
0x18002a0ee  mov     r9, r14
0x18002a0f1  cmovnz  rax, [rdi]
0x18002a0f5  mov     [rsp+50h+var_28], rax
0x18002a0fa  mov     [rsp+50h+var_30], edx
0x18002a0fe  call    WPP_SF_SDS
0x18002a103  lea     rdx, [rbp+ExceptionCode]; Reply
0x18002a107  mov     rcx, r12; pAsync
0x18002a10a  call    cs:__imp_RpcAsyncCompleteCall
0x18002a111  nop     dword ptr [rax+rax+00h]
0x18002a116  mov     [rbp+ExceptionCode], 0
0x18002a11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a124  cmp     rcx, rsi
0x18002a127  jz      short loc_18002A133
0x18002a129  test    byte ptr [rcx+1Ch], 1
0x18002a12d  jnz     loc_18002A04C
0x18002a133  mov     ebx, [rbp+var_20]
0x18002a136  jmp     loc_180029DDA
0x18002a13b  test    byte ptr [rcx+1Ch], 1
0x18002a13f  jz      loc_180029EEC
0x18002a145  mov     edx, 7Dh ; '}'
0x18002a14a  jmp     loc_18002A054
0x18002a14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a156  lea     rsi, WPP_GLOBAL_Control
0x18002a15d  cmp     rcx, rsi
0x18002a160  jz      loc_180029FDC
0x18002a166  test    byte ptr [rcx+1Ch], 1
0x18002a16a  jz      loc_180029FDC
0x18002a170  mov     edx, 7Eh ; '~'
0x18002a175  mov     r9d, eax
0x18002a178  jmp     loc_18002A054
0x18002a17d  mov     ecx, 3
0x18002a182  int     29h; Win8: RtlFailFast(ecx)
```
