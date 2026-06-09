# s_SrvRpcCryptImportKey

- ea: `0x180006bc0`
- end: `0x180006d58`
- name: `s_SrvRpcCryptImportKey`
- size: `408`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180006bc0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180006be4`
- `RPCRT4!RpcImpersonateClient` at `0x180006be4`
- `RPCRT4!RpcRevertToSelf` at `0x180006c9c`
- `RPCRT4!RpcRevertToSelf` at `0x180006c9c`

## string_xrefs

- `0x180006c5b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180006c7a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180006cd4`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180006d36`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptImportKey(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        int a9,
        int a10)
{
  RPC_STATUS v13; // eax
  int v14; // eax
  unsigned int v15; // ebx

  if ( a7 )
  {
    v13 = RpcImpersonateClient(a1);
    if ( !v13 )
    {
      *a7 = -1;
      v14 = off_1800250A0(a2, a3, a4, a5, a6, (__int64)a7, a8, a9, a10);
      v15 = v14;
      if ( v14 < 0 )
        DebugTraceError(
          (unsigned int)v14,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          1269);
      RpcRevertToSelf();
      return v15;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        v13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        224);
    return 2148073504LL;
  }
  else
  {
    v15 = -2146893785;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v15;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
      217);
    return 2148073511LL;
  }
}

```

## disassembly

```asm
0x180006bc0  push    rbx
0x180006bc2  push    rsi
0x180006bc3  push    rdi
0x180006bc4  push    r14
0x180006bc6  sub     rsp, 68h
0x180006bca  mov     rdi, r9
0x180006bcd  mov     rsi, r8
0x180006bd0  mov     r14, rdx
0x180006bd3  mov     rbx, [rsp+88h+arg_30]
0x180006bdb  test    rbx, rbx
0x180006bde  jz      loc_180006CAE
0x180006be4  call    cs:__imp_RpcImpersonateClient
0x180006bea  test    eax, eax
0x180006bec  jnz     loc_180006D04
0x180006bf2  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180006bf9  mov     eax, [rsp+88h+arg_48]
0x180006c00  mov     [rsp+88h+var_48], eax
0x180006c04  mov     eax, [rsp+88h+arg_40]
0x180006c0b  mov     [rsp+88h+var_50], eax
0x180006c0f  mov     rax, [rsp+88h+arg_38]
0x180006c17  mov     [rsp+88h+var_58], rax
0x180006c1c  mov     [rsp+88h+var_60], rbx
0x180006c21  mov     rax, [rsp+88h+arg_28]
0x180006c29  mov     [rsp+88h+var_68], rax
0x180006c2e  mov     r9, [rsp+88h+arg_20]
0x180006c36  mov     r8, rdi
0x180006c39  mov     rdx, rsi
0x180006c3c  mov     rcx, r14
0x180006c3f  mov     rax, cs:off_1800250A0
0x180006c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4b  mov     ebx, eax
0x180006c4d  mov     [rsp+88h+var_38], eax
0x180006c51  test    eax, eax
0x180006c53  jns     short loc_180006C70
0x180006c55  mov     r9d, 4F5h
0x180006c5b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006c62  lea     rdx, aStatus; "Status"
0x180006c69  mov     ecx, eax
0x180006c6b  call    DebugTraceError
0x180006c70  jmp     short loc_180006C9C
0x180006c72  mov     ebx, eax
0x180006c74  mov     r9d, 4FBh
0x180006c7a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006c81  lea     rdx, aNtstatus; "ntStatus"
0x180006c88  mov     ecx, eax
0x180006c8a  call    DebugTraceError
0x180006c8f  mov     ecx, ebx
0x180006c91  call    NormalizeNteStatus
0x180006c96  mov     ebx, eax
0x180006c98  mov     [rsp+88h+var_38], eax
0x180006c9c  call    cs:__imp_RpcRevertToSelf
0x180006ca2  mov     eax, ebx
0x180006ca4  add     rsp, 68h
0x180006ca8  pop     r14
0x180006caa  pop     rdi
0x180006cab  pop     rsi
0x180006cac  pop     rbx
0x180006cad  retn
0x180006cae  mov     ebx, 80090027h
0x180006cb3  lea     rdx, WPP_GLOBAL_Control
0x180006cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cc1  cmp     rcx, rdx
0x180006cc4  jz      short loc_180006CA2
0x180006cc6  test    byte ptr [rcx+1Ch], 1
0x180006cca  jz      short loc_180006CA2
0x180006ccc  mov     dword ptr [rsp+88h+var_58], 4D9h
0x180006cd4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006cdb  mov     [rsp+88h+var_60], r8
0x180006ce0  mov     dword ptr [rsp+88h+var_68], 80090027h
0x180006ce8  lea     r9, aStatus; "Status"
0x180006cef  mov     rcx, [rcx+10h]
0x180006cf3  call    WPP_SF_sDsd
0x180006cf8  mov     eax, ebx
0x180006cfa  add     rsp, 68h
0x180006cfe  pop     r14
0x180006d00  pop     rdi
0x180006d01  pop     rsi
0x180006d02  pop     rbx
0x180006d03  retn
0x180006d04  lea     rdx, WPP_GLOBAL_Control
0x180006d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d12  cmp     rcx, rdx
0x180006d15  jz      short loc_180006D1D
0x180006d17  test    byte ptr [rcx+1Ch], 1
0x180006d1b  jnz     short loc_180006D2E
0x180006d1d  mov     ebx, 80090020h
0x180006d22  mov     eax, ebx
0x180006d24  add     rsp, 68h
0x180006d28  pop     r14
0x180006d2a  pop     rdi
0x180006d2b  pop     rsi
0x180006d2c  pop     rbx
0x180006d2d  retn
0x180006d2e  mov     dword ptr [rsp+88h+var_58], 4E0h
0x180006d36  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006d3d  mov     [rsp+88h+var_60], r8
0x180006d42  mov     dword ptr [rsp+88h+var_68], eax
0x180006d46  lea     r9, aStatus; "Status"
0x180006d4d  mov     rcx, [rcx+10h]
0x180006d51  call    WPP_SF_sDsd
0x180006d56  jmp     short loc_180006D1D
```
