# s_SrvRpcCryptSignHash

- ea: `0x1800079a0`
- end: `0x180007ac5`
- name: `s_SrvRpcCryptSignHash`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x1800079a0`
- `0x180007ad0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800079c4`
- `RPCRT4!RpcImpersonateClient` at `0x1800079c4`
- `RPCRT4!RpcRevertToSelf` at `0x180007a8a`
- `RPCRT4!RpcRevertToSelf` at `0x180007a8a`

## string_xrefs

- `0x180007a49`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007a68`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007aa9`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptSignHash(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9,
        _DWORD *a10,
        int a11)
{
  unsigned int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  unsigned int v17; // ebx

  if ( a10 )
  {
    v14 = RpcImpersonateClient(a1);
    if ( v14 )
    {
      DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1376);
      return (unsigned int)-2146893792;
    }
    else
    {
      *a10 = 0;
      v15 = UnpackPaddingInfoPtr(a5);
      v16 = off_1800250B0(a2, a3, a4, v15, a6, a7, a8, a9, (__int64)a10, a11);
      v17 = v16;
      if ( v16 < 0 )
        DebugTraceError(
          (unsigned int)v16,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          1398);
      RpcRevertToSelf();
    }
  }
  else
  {
    return (unsigned int)-2146893785;
  }
  return v17;
}

```

## disassembly

```asm
0x1800079a0  push    rbx
0x1800079a2  push    rsi
0x1800079a3  push    rdi
0x1800079a4  push    r14
0x1800079a6  sub     rsp, 78h
0x1800079aa  mov     rdi, r9
0x1800079ad  mov     rsi, r8
0x1800079b0  mov     r14, rdx
0x1800079b3  mov     rbx, [rsp+98h+arg_48]
0x1800079bb  test    rbx, rbx
0x1800079be  jz      loc_180007A9C
0x1800079c4  call    cs:__imp_RpcImpersonateClient
0x1800079ca  test    eax, eax
0x1800079cc  jnz     loc_180007AA3
0x1800079d2  mov     [rbx], eax
0x1800079d4  mov     rcx, [rsp+98h+arg_20]
0x1800079dc  call    _UnpackPaddingInfoPtr
0x1800079e1  mov     r9, rax
0x1800079e4  mov     eax, [rsp+98h+arg_50]
0x1800079eb  mov     [rsp+98h+var_50], eax
0x1800079ef  mov     [rsp+98h+var_58], rbx
0x1800079f4  mov     eax, [rsp+98h+arg_40]
0x1800079fb  mov     [rsp+98h+var_60], eax
0x1800079ff  mov     rax, [rsp+98h+arg_38]
0x180007a07  mov     [rsp+98h+var_68], rax
0x180007a0c  mov     eax, [rsp+98h+arg_30]
0x180007a13  mov     [rsp+98h+var_70], eax
0x180007a17  mov     rax, [rsp+98h+arg_28]
0x180007a1f  mov     [rsp+98h+var_78], rax
0x180007a24  mov     r8, rdi
0x180007a27  mov     rdx, rsi
0x180007a2a  mov     rcx, r14
0x180007a2d  mov     rax, cs:off_1800250B0
0x180007a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a39  mov     ebx, eax
0x180007a3b  mov     [rsp+98h+var_38], eax
0x180007a3f  test    eax, eax
0x180007a41  jns     short loc_180007A5E
0x180007a43  mov     r9d, 576h
0x180007a49  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007a50  lea     rdx, aStatus; "Status"
0x180007a57  mov     ecx, eax
0x180007a59  call    DebugTraceError
0x180007a5e  jmp     short loc_180007A8A
0x180007a60  mov     ebx, eax
0x180007a62  mov     r9d, 57Ch
0x180007a68  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007a6f  lea     rdx, aNtstatus; "ntStatus"
0x180007a76  mov     ecx, eax
0x180007a78  call    DebugTraceError
0x180007a7d  mov     ecx, ebx
0x180007a7f  call    NormalizeNteStatus
0x180007a84  mov     ebx, eax
0x180007a86  mov     [rsp+98h+var_38], eax
0x180007a8a  call    cs:__imp_RpcRevertToSelf
0x180007a90  mov     eax, ebx
0x180007a92  add     rsp, 78h
0x180007a96  pop     r14
0x180007a98  pop     rdi
0x180007a99  pop     rsi
0x180007a9a  pop     rbx
0x180007a9b  retn
0x180007a9c  mov     ebx, 80090027h
0x180007aa1  jmp     short loc_180007A90
0x180007aa3  mov     r9d, 560h
0x180007aa9  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007ab0  lea     rdx, aStatus; "Status"
0x180007ab7  mov     ecx, eax
0x180007ab9  call    DebugTraceError
0x180007abe  mov     ebx, 80090020h
0x180007ac3  jmp     short loc_180007A90
```
