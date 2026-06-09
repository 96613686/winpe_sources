# LRPC_FAST_BINDING_HANDLE::NegotiateTransferSyntax(_RPC_MESSAGE *)

- ea: `0x18005e0e0`
- end: `0x18005e3f7`
- name: `?NegotiateTransferSyntax@LRPC_FAST_BINDING_HANDLE@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `791`
- prototype: `__int64 __fastcall(LRPC_FAST_BINDING_HANDLE *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001b00c`
- `0x180021e18`
- `0x180025c00`
- `0x180029cc4`
- `0x18005e0e0`
- `0x18005e400`
- `0x18005e4a8`
- `0x1800ca140`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18005e3c1`
- `ntdll!EtwEventActivityIdControl` at `0x18005e3c1`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18005e395`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18005e395`

## pseudocode

```c
__int64 __fastcall LRPC_FAST_BINDING_HANDLE::NegotiateTransferSyntax(
        LRPC_CASSOCIATION **this,
        struct _RPC_MESSAGE *a2,
        __int64 a3)
{
  unsigned int i; // ecx
  LRPC_CASSOCIATION *v6; // rax
  __int64 v7; // rax
  struct LRPC_FAST_CAUSAL_FLOW *v8; // r12
  unsigned int v9; // esi
  unsigned __int64 v10; // r14
  struct LRPC_FAST_CCALL *v11; // rbx
  signed __int32 v12; // edx
  LRPC_CASSOCIATION *v13; // rax
  LRPC_CASSOCIATION *v15; // rax
  union _SLIST_HEADER *v16; // rcx
  PSLIST_ENTRY v17; // rax
  char v18; // [rsp+30h] [rbp-79h] BYREF
  char v19; // [rsp+38h] [rbp-71h] BYREF
  struct LRPC_FAST_CCALL *v20; // [rsp+40h] [rbp-69h] BYREF
  __int64 v21; // [rsp+48h] [rbp-61h] BYREF
  __int64 v22; // [rsp+50h] [rbp-59h] BYREF
  char v23[16]; // [rsp+60h] [rbp-49h] BYREF
  char *v24; // [rsp+70h] [rbp-39h]
  __int64 v25; // [rsp+78h] [rbp-31h]
  char *v26; // [rsp+80h] [rbp-29h]
  __int64 v27; // [rsp+88h] [rbp-21h]
  struct LRPC_FAST_CCALL **v28; // [rsp+90h] [rbp-19h]
  __int64 v29; // [rsp+98h] [rbp-11h]
  __int64 *v30; // [rsp+A0h] [rbp-9h]
  __int64 v31; // [rsp+A8h] [rbp-1h]
  __int64 *v32; // [rsp+B0h] [rbp+7h]
  __int64 v33; // [rsp+B8h] [rbp+Fh]

  if ( dword_1800F9624 )
  {
    for ( i = 0; i < 4; ++i )
    {
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 104 )
        goto LABEL_8;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      v29 = 8;
      v24 = &v18;
      v31 = 8;
      v26 = &v19;
      v33 = 8;
      v28 = &v20;
      v21 = 0;
      v30 = &v22;
      v32 = &v21;
      v22 = 0;
      v20 = (struct LRPC_FAST_CCALL *)this;
      v19 = 112;
      v18 = 104;
      v25 = 1;
      v27 = 1;
      McGenEventWrite_EtwEventWriteTransfer(&RpcEtwGuid_Context, (__int64)RPCLogEvent, a3, 6, (__int64)v23);
    }
  }
LABEL_8:
  v6 = this[8];
  if ( v6 )
    v7 = *((_QWORD *)v6 + 12);
  else
    v7 = 0;
  if ( *((int *)this + 99) < 11 )
  {
    RpcpReportFatalError(7, this);
    __debugbreak();
  }
  v8 = 0;
  v9 = 0;
  if ( (a2->RpcFlags & 0x8000) == 0 )
  {
    if ( v7 )
      v10 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
    else
      LODWORD(v10) = 0;
    v11 = this[66];
    if ( v11
      && v11 == (struct LRPC_FAST_CCALL *)_InterlockedCompareExchange64(
                                            (volatile signed __int64 *)this + 66,
                                            0,
                                            (signed __int64)v11) )
    {
      goto LABEL_16;
    }
    v16 = (union _SLIST_HEADER *)(this + 68);
LABEL_36:
    v17 = InterlockedPopEntrySList(v16);
    v11 = (struct LRPC_FAST_CCALL *)&v17[-37];
    if ( !v17 )
      v11 = 0;
    goto LABEL_16;
  }
  if ( ((_DWORD)this[62] & 1) == 0 )
  {
    if ( !LrpcAsyncInitialized )
    {
      v9 = InitializeAsyncLrpc();
      if ( v9 )
        return v9;
    }
    v9 = LRPC_BASE_BINDING_HANDLE::EnableAsyncIfNecessary((LRPC_BASE_BINDING_HANDLE *)this);
    if ( v9 )
      return v9;
  }
  if ( (a2->RpcFlags & 0x2000) == 0 )
  {
    v15 = this[8];
    v9 = 0;
    if ( !v15 || !*((_QWORD *)v15 + 9) )
      v8 = this[76];
  }
  v11 = this[70];
  LODWORD(v10) = 0;
  if ( !v11
    || v11 != (struct LRPC_FAST_CCALL *)_InterlockedCompareExchange64(
                                          (volatile signed __int64 *)this + 70,
                                          0,
                                          (signed __int64)v11) )
  {
    v16 = (union _SLIST_HEADER *)(this + 72);
    goto LABEL_36;
  }
LABEL_16:
  v20 = v11;
  if ( v11 )
  {
    v12 = _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v11 + 35) + 188LL));
    *((_QWORD *)v11 + 74) = 0;
    *((_DWORD *)v11 + 73) = v12;
    *((_DWORD *)v11 + 75) = 0;
    REFERENCED_OBJECT::SingleThreadedAddReference(v11);
  }
  else
  {
    v9 = LRPC_CASSOCIATION::AllocateCall(this[61], a2, v10, (struct LRPC_FAST_BINDING_HANDLE *)this, v8, &v20);
    if ( v9 )
      return v9;
    v11 = v20;
  }
  *((_DWORD *)v11 + 67) = 1;
  if ( dword_1800F9624 )
    EtwEventActivityIdControl(1, (char *)v11 + 208);
  else
    *((GUID *)v11 + 13) = g_NullActivityId;
  v13 = this[74];
  a2->Handle = v11;
  a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)((char *)v13 + 24);
  return v9;
}

```

## disassembly

```asm
0x18005e0e0  mov     [rsp-8+arg_10], rbx
0x18005e0e5  push    rbp
0x18005e0e6  push    rsi
0x18005e0e7  push    rdi
0x18005e0e8  push    r12
0x18005e0ea  push    r13
0x18005e0ec  push    r14
0x18005e0ee  push    r15
0x18005e0f0  lea     rbp, [rsp-27h]
0x18005e0f5  sub     rsp, 0D0h
0x18005e0fc  mov     rax, cs:__security_cookie
0x18005e103  xor     rax, rsp
0x18005e106  mov     [rbp+57h+var_40], rax
0x18005e10a  xor     r13d, r13d
0x18005e10d  mov     r15, rdx
0x18005e110  cmp     cs:dword_1800F9624, r13d
0x18005e117  mov     rdi, rcx
0x18005e11a  jz      short loc_18005E149
0x18005e11c  mov     ecx, r13d
0x18005e11f  cmp     ecx, 4
0x18005e122  jnb     short loc_18005E138
0x18005e124  movsxd  rax, ecx
0x18005e127  lea     rdx, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18005e12e  cmp     byte ptr [rax+rdx], 68h ; 'h'
0x18005e132  jz      short loc_18005E149
0x18005e134  inc     ecx
0x18005e136  jmp     short loc_18005E11F
0x18005e138  mov     ecx, 8
0x18005e13d  test    cs:Microsoft_Windows_RPCEnableBits, cl
0x18005e143  jnz     loc_18005E251
0x18005e149  mov     rax, [rdi+40h]
0x18005e14d  test    rax, rax
0x18005e150  jz      loc_18005E3B3
0x18005e156  mov     rax, [rax+60h]
0x18005e15a  cmp     dword ptr [rdi+18Ch], 0Bh
0x18005e161  jl      loc_18005E3CC
0x18005e167  test    dword ptr [r15+48h], 8000h
0x18005e16f  mov     r12, r13
0x18005e172  mov     esi, r13d
0x18005e175  jnz     loc_18005E30A
0x18005e17b  test    rax, rax
0x18005e17e  jnz     loc_18005E3DA
0x18005e184  mov     r14d, r13d
0x18005e187  mov     rbx, [rdi+210h]
0x18005e18e  test    rbx, rbx
0x18005e191  jz      loc_18005E38E
0x18005e197  mov     rcx, r13
0x18005e19a  mov     rax, rbx
0x18005e19d  lock cmpxchg [rdi+210h], rcx
0x18005e1a6  jnz     loc_18005E38E
0x18005e1ac  mov     [rbp+57h+var_C0], rbx
0x18005e1b0  test    rbx, rbx
0x18005e1b3  jz      loc_18005E2D0
0x18005e1b9  mov     rax, [rbx+118h]
0x18005e1c0  mov     r14d, 1
0x18005e1c6  mov     edx, r14d
0x18005e1c9  lock xadd [rax+0BCh], edx
0x18005e1d1  add     edx, r14d
0x18005e1d4  mov     [rbx+250h], r13
0x18005e1db  mov     rcx, rbx; this
0x18005e1de  mov     [rbx+124h], edx
0x18005e1e4  mov     [rbx+12Ch], r13d
0x18005e1eb  call    ?SingleThreadedAddReference@REFERENCED_OBJECT@@QEAAXXZ; REFERENCED_OBJECT::SingleThreadedAddReference(void)
0x18005e1f0  mov     [rbx+10Ch], r14d
0x18005e1f7  lea     rax, [rbx+0D0h]
0x18005e1fe  cmp     cs:dword_1800F9624, r13d
0x18005e205  jnz     loc_18005E3BB
0x18005e20b  movups  xmm0, xmmword ptr cs:?g_NullActivityId@@3U_GUID@@B.Data1; _GUID const g_NullActivityId ...
0x18005e212  movdqu  xmmword ptr [rax], xmm0
0x18005e216  mov     rax, [rdi+250h]
0x18005e21d  add     rax, 18h
0x18005e221  mov     [r15], rbx
0x18005e224  mov     [r15+20h], rax
0x18005e228  mov     eax, esi
0x18005e22a  mov     rcx, [rbp+57h+var_40]
0x18005e22e  xor     rcx, rsp; StackCookie
0x18005e231  call    __security_check_cookie
0x18005e236  mov     rbx, [rsp+100h+arg_10]
0x18005e23e  add     rsp, 0D0h
0x18005e245  pop     r15
0x18005e247  pop     r14
0x18005e249  pop     r13
0x18005e24b  pop     r12
0x18005e24d  pop     rdi
0x18005e24e  pop     rsi
0x18005e24f  pop     rbp
0x18005e250  retn
0x18005e251  lea     rax, [rbp+57h+var_D0]
0x18005e255  mov     [rbp+57h+var_68], rcx
0x18005e259  mov     [rbp+57h+var_90], rax
0x18005e25d  lea     rdx, RPCLogEvent
0x18005e264  lea     rax, [rbp+57h+var_C8]
0x18005e268  mov     [rbp+57h+var_58], rcx
0x18005e26c  mov     [rbp+57h+var_80], rax
0x18005e270  mov     r9d, 6
0x18005e276  lea     rax, [rbp+57h+var_C0]
0x18005e27a  mov     [rbp+57h+var_48], rcx
0x18005e27e  mov     [rbp+57h+var_70], rax
0x18005e282  lea     rcx, RpcEtwGuid_Context
0x18005e289  lea     rax, [rbp+57h+var_B0]
0x18005e28d  mov     [rbp+57h+var_B8], r13
0x18005e291  mov     [rbp+57h+var_60], rax
0x18005e295  lea     rax, [rbp+57h+var_B8]
0x18005e299  mov     [rbp+57h+var_50], rax
0x18005e29d  lea     rax, [rbp+57h+var_A0]
0x18005e2a1  mov     [rsp+100h+var_E0], rax
0x18005e2a6  mov     [rbp+57h+var_B0], r13
0x18005e2aa  mov     [rbp+57h+var_C0], rdi
0x18005e2ae  mov     [rbp+57h+var_C8], 70h ; 'p'
0x18005e2b2  mov     [rbp+57h+var_D0], 68h ; 'h'
0x18005e2b6  mov     [rbp+57h+var_88], 1
0x18005e2be  mov     [rbp+57h+var_78], 1
0x18005e2c6  call    McGenEventWrite_EtwEventWriteTransfer
0x18005e2cb  jmp     loc_18005E149
0x18005e2d0  mov     rcx, [rdi+1E8h]; this
0x18005e2d7  lea     rax, [rbp+57h+var_C0]
0x18005e2db  mov     [rsp+100h+var_D8], rax; struct LRPC_FAST_CCALL **
0x18005e2e0  mov     r9, rdi; struct LRPC_FAST_BINDING_HANDLE *
0x18005e2e3  mov     r8d, r14d; unsigned int
0x18005e2e6  mov     [rsp+100h+var_E0], r12; struct LRPC_FAST_CAUSAL_FLOW *
0x18005e2eb  mov     rdx, r15; struct _RPC_MESSAGE *
0x18005e2ee  call    ?AllocateCall@LRPC_CASSOCIATION@@QEAAJPEAU_RPC_MESSAGE@@KPEAVLRPC_FAST_BINDING_HANDLE@@PEAVLRPC_FAST_CAUSAL_FLOW@@PEAPEAVLRPC_FAST_CCALL@@@Z; LRPC_CASSOCIATION::AllocateCall(_RPC_MESSAGE *,ulong,LRPC_FAST_BINDING_HANDLE *,LRPC_FAST_CAUSAL_FLOW *,LRPC_FAST_CCALL * *)
0x18005e2f3  mov     esi, eax
0x18005e2f5  test    eax, eax
0x18005e2f7  jnz     loc_18005E228
0x18005e2fd  mov     rbx, [rbp+57h+var_C0]
0x18005e301  lea     r14d, [rax+1]
0x18005e305  jmp     loc_18005E1F0
0x18005e30a  mov     eax, [rdi+1F0h]
0x18005e310  test    al, 1
0x18005e312  jnz     short loc_18005E33E
0x18005e314  cmp     cs:?LrpcAsyncInitialized@@3HA, r13d; int LrpcAsyncInitialized
0x18005e31b  jnz     short loc_18005E32C
0x18005e31d  call    ?InitializeAsyncLrpc@@YAJXZ; InitializeAsyncLrpc(void)
0x18005e322  mov     esi, eax
0x18005e324  test    eax, eax
0x18005e326  jnz     loc_18005E228
0x18005e32c  mov     rcx, rdi; this
0x18005e32f  call    ?EnableAsyncIfNecessary@LRPC_BASE_BINDING_HANDLE@@QEAAJXZ; LRPC_BASE_BINDING_HANDLE::EnableAsyncIfNecessary(void)
0x18005e334  mov     esi, eax
0x18005e336  test    eax, eax
0x18005e338  jnz     loc_18005E228
0x18005e33e  test    dword ptr [r15+48h], 2000h
0x18005e346  jnz     short loc_18005E361
0x18005e348  mov     rax, [rdi+40h]
0x18005e34c  mov     esi, r13d
0x18005e34f  test    rax, rax
0x18005e352  jz      short loc_18005E35A
0x18005e354  cmp     [rax+48h], r13
0x18005e358  jnz     short loc_18005E361
0x18005e35a  mov     r12, [rdi+260h]
0x18005e361  mov     rbx, [rdi+230h]
0x18005e368  mov     r14d, r13d
0x18005e36b  test    rbx, rbx
0x18005e36e  jz      short loc_18005E385
0x18005e370  mov     rcx, r13
0x18005e373  mov     rax, rbx
0x18005e376  lock cmpxchg [rdi+230h], rcx
0x18005e37f  jz      loc_18005E1AC
0x18005e385  lea     rcx, [rdi+240h]
0x18005e38c  jmp     short loc_18005E395
0x18005e38e  lea     rcx, [rdi+220h]; ListHead
0x18005e395  call    cs:__imp_InterlockedPopEntrySList
0x18005e39b  lea     rbx, [rax-250h]
0x18005e3a2  test    rax, rax
0x18005e3a5  jnz     loc_18005E1AC
0x18005e3ab  mov     rbx, r13
0x18005e3ae  jmp     loc_18005E1AC
0x18005e3b3  mov     rax, r13
0x18005e3b6  jmp     loc_18005E15A
0x18005e3bb  mov     rdx, rax
0x18005e3be  mov     ecx, r14d
0x18005e3c1  call    cs:__imp_EtwEventActivityIdControl
0x18005e3c7  jmp     loc_18005E216
0x18005e3cc  mov     rdx, rdi
0x18005e3cf  mov     ecx, 7
0x18005e3d4  call    RpcpReportFatalError
0x18005e3d9  int     3; Trap to Debugger
0x18005e3da  mov     eax, 7FFE0320h
0x18005e3df  mov     rax, [rax]
0x18005e3e2  mov     r14d, ds:7FFE0004h
0x18005e3ea  imul    r14, rax
0x18005e3ee  shr     r14, 18h
0x18005e3f2  jmp     loc_18005E187
```
