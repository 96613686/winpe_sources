# NetTrace::CPersistentTrace::SetSession(NetTrace::ITraceSession *,int)

- ea: `0x180029c2c`
- end: `0x180029deb`
- name: `?SetSession@CPersistentTrace@NetTrace@@QEAAJPEAUITraceSession@2@H@Z`
- size: `447`
- prototype: `__int64 __fastcall(NetTrace::CPersistentTrace *__hidden this, struct NetTrace::ITraceSession *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029ea0`

## callees

- `0x180006f04`
- `0x180028a40`
- `0x180029c2c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029dc7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180029dd5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180029dd5`

## pseudocode

```c
__int64 __fastcall NetTrace::CPersistentTrace::SetSession(
        NetTrace::CPersistentTrace *this,
        struct NetTrace::ITraceSession *a2,
        int a3)
{
  int v3; // r15d
  struct NetTrace::ITraceSession *v4; // r14
  NetTrace::CPersistentTrace *v5; // rsi
  unsigned int v6; // edi
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // r8
  __int64 v10; // rax
  unsigned int i; // r14d
  unsigned int v13; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  ATL::CAtlException *v15; // [rsp+40h] [rbp-38h] BYREF
  ATL::CAtlException *v16; // [rsp+48h] [rbp-30h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = this;
  v6 = -2147024809;
  if ( !a2 )
    goto LABEL_16;
  v6 = *(_DWORD *)this;
  if ( *(_DWORD *)this )
    goto LABEL_16;
  try
  {
    v7 = (*(__int64 (__fastcall **)(struct NetTrace::ITraceSession *))(*(_QWORD *)a2 + 48LL))(a2);
    v8 = -1;
    if ( v7 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v7 + 2 * v9) );
    }
    else
    {
      v9 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v5 + 40, v7, v9);
    v10 = (*(__int64 (__fastcall **)(struct NetTrace::ITraceSession *))(*(_QWORD *)v4 + 56LL))(v4);
    if ( v10 )
    {
      do
        ++v8;
      while ( *(_WORD *)(v10 + 2 * v8) );
    }
    else
    {
      LODWORD(v8) = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v5 + 64, v10, (unsigned int)v8);
    *((_DWORD *)v5 + 18) = (*(__int64 (__fastcall **)(struct NetTrace::ITraceSession *))(*(_QWORD *)v4 + 72LL))(v4);
    *((_DWORD *)v5 + 19) = (*(__int64 (__fastcall **)(struct NetTrace::ITraceSession *))(*(_QWORD *)v4 + 64LL))(v4);
  }
  catch ( ATL::CAtlException *v15 )
  {
    v6 = *(_DWORD *)v15;
    v5 = this;
    v4 = a2;
    if ( *(_DWORD *)v15 )
      goto LABEL_16;
    v3 = a3;
  }
  v6 = (*(__int64 (__fastcall **)(struct NetTrace::ITraceSession *, __int64, __int64, __int64))(*(_QWORD *)v4 + 80LL))(
         v4,
         (__int64)v5 + 80,
         (__int64)v5 + 88,
         (__int64)v5 + 84);
  if ( !v6 )
    *((_DWORD *)v5 + 8) = v3;
LABEL_16:
  pv = 0;
  v13 = 0;
  if ( !v6 )
  {
    v6 = (*(__int64 (__fastcall **)(struct NetTrace::ITraceSession *, LPVOID *, unsigned int *))(*(_QWORD *)v4 + 160LL))(
           v4,
           &pv,
           &v13);
    if ( !v6 )
    {
      for ( i = 0; i < v13 && !v6; ++i )
      {
        try
        {
          ATL::CSimpleArray<NetTrace::TraceProviderInfo,ATL::CSimpleArrayEqualHelper<NetTrace::TraceProviderInfo>>::Add(
            (char *)v5 + 96,
            (char *)pv + 48 * i);
        }
        catch ( ATL::CAtlException *v16 )
        {
          v5 = this;
          v6 = *(_DWORD *)v16;
          continue;
        }
      }
      CoTaskMemFree(pv);
      if ( !v6 )
        return (unsigned int)CoCreateGuid((GUID *)v5 + 3);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180029c2c  mov     [rsp+arg_10], r8d
0x180029c31  mov     [rsp+arg_8], rdx
0x180029c36  mov     [rsp+arg_0], rcx
0x180029c3b  push    rbx
0x180029c3c  push    rsi
0x180029c3d  push    rdi
0x180029c3e  push    r14
0x180029c40  push    r15
0x180029c42  sub     rsp, 50h
0x180029c46  mov     r15d, r8d
0x180029c49  mov     r14, rdx
0x180029c4c  mov     rsi, rcx
0x180029c4f  mov     edi, 80070057h
0x180029c54  xor     ebx, ebx
0x180029c56  test    rdx, rdx
0x180029c59  jz      loc_180029D3F
0x180029c5f  mov     edi, [rcx]
0x180029c61  test    edi, edi
0x180029c63  jnz     loc_180029D3F
0x180029c69  mov     rax, [rdx]
0x180029c6c  mov     rcx, rdx
0x180029c6f  mov     rax, [rax+30h]
0x180029c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c78  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029c7c  test    rax, rax
0x180029c7f  jnz     short loc_180029C86
0x180029c81  mov     r8d, ebx
0x180029c84  jmp     short loc_180029C93
0x180029c86  mov     r8, rdi
0x180029c89  inc     r8
0x180029c8c  cmp     [rax+r8*2], bx
0x180029c91  jnz     short loc_180029C89
0x180029c93  lea     rcx, [rsi+28h]
0x180029c97  mov     rdx, rax
0x180029c9a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180029c9f  mov     rax, [r14]
0x180029ca2  mov     rcx, r14
0x180029ca5  mov     rax, [rax+38h]
0x180029ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cae  test    rax, rax
0x180029cb1  jnz     short loc_180029CB7
0x180029cb3  mov     edi, ebx
0x180029cb5  jmp     short loc_180029CC0
0x180029cb7  inc     rdi
0x180029cba  cmp     [rax+rdi*2], bx
0x180029cbe  jnz     short loc_180029CB7
0x180029cc0  lea     rcx, [rsi+40h]
0x180029cc4  mov     r8d, edi
0x180029cc7  mov     rdx, rax
0x180029cca  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180029ccf  mov     rax, [r14]
0x180029cd2  mov     rcx, r14
0x180029cd5  mov     rax, [rax+48h]
0x180029cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cde  mov     [rsi+48h], eax
0x180029ce1  mov     rax, [r14]
0x180029ce4  mov     rcx, r14
0x180029ce7  mov     rax, [rax+40h]
0x180029ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cf0  mov     [rsi+4Ch], eax
0x180029cf3  jmp     short loc_180029D1A
0x180029cf5  mov     edi, [rsp+78h+arg_18]
0x180029cfc  xor     ebx, ebx
0x180029cfe  mov     rsi, [rsp+78h+arg_0]
0x180029d06  mov     r14, [rsp+78h+arg_8]
0x180029d0e  test    edi, edi
0x180029d10  jnz     short loc_180029D3F
0x180029d12  mov     r15d, [rsp+78h+arg_10]
0x180029d1a  mov     rax, [r14]
0x180029d1d  lea     r9, [rsi+54h]
0x180029d21  lea     r8, [rsi+58h]
0x180029d25  lea     rdx, [rsi+50h]
0x180029d29  mov     rcx, r14
0x180029d2c  mov     rax, [rax+50h]
0x180029d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d35  mov     edi, eax
0x180029d37  test    eax, eax
0x180029d39  jnz     short loc_180029D3F
0x180029d3b  mov     [rsi+20h], r15d
0x180029d3f  mov     [rsp+78h+pv], rbx
0x180029d44  mov     [rsp+78h+var_48], ebx
0x180029d48  test    edi, edi
0x180029d4a  jnz     loc_180029DDD
0x180029d50  mov     rax, [r14]
0x180029d53  lea     r8, [rsp+78h+var_48]
0x180029d58  lea     rdx, [rsp+78h+pv]
0x180029d5d  mov     rcx, r14
0x180029d60  mov     rax, [rax+0A0h]
0x180029d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d6c  mov     edi, eax
0x180029d6e  test    eax, eax
0x180029d70  jnz     short loc_180029DDD
0x180029d72  mov     r14d, ebx
0x180029d75  mov     dword ptr [rsp+78h+arg_8], r14d
0x180029d7d  cmp     r14d, [rsp+78h+var_48]
0x180029d82  jnb     short loc_180029DC2
0x180029d84  test    edi, edi
0x180029d86  jnz     short loc_180029DC2
0x180029d88  mov     eax, r14d
0x180029d8b  lea     rdx, [rax+rax*2]
0x180029d8f  shl     rdx, 4
0x180029d93  add     rdx, [rsp+78h+pv]
0x180029d98  lea     rcx, [rsi+60h]
0x180029d9c  call    ?Add@?$CSimpleArray@UTraceProviderInfo@NetTrace@@V?$CSimpleArrayEqualHelper@UTraceProviderInfo@NetTrace@@@ATL@@@ATL@@QEAAHAEBUTraceProviderInfo@NetTrace@@@Z; ATL::CSimpleArray<NetTrace::TraceProviderInfo,ATL::CSimpleArrayEqualHelper<NetTrace::TraceProviderInfo>>::Add(NetTrace::TraceProviderInfo const &)
0x180029da1  nop
0x180029da2  jmp     short loc_180029DBD
0x180029da4  xor     ebx, ebx
0x180029da6  mov     rsi, [rsp+78h+arg_0]
0x180029dae  mov     edi, [rsp+78h+arg_18]
0x180029db5  mov     r14d, dword ptr [rsp+78h+arg_8]
0x180029dbd  inc     r14d
0x180029dc0  jmp     short loc_180029D75
0x180029dc2  mov     rcx, [rsp+78h+pv]; pv
0x180029dc7  call    cs:__imp_CoTaskMemFree
0x180029dcd  test    edi, edi
0x180029dcf  jnz     short loc_180029DDD
0x180029dd1  lea     rcx, [rsi+30h]; pguid
0x180029dd5  call    cs:__imp_CoCreateGuid
0x180029ddb  mov     edi, eax
0x180029ddd  mov     eax, edi
0x180029ddf  add     rsp, 50h
0x180029de3  pop     r15
0x180029de5  pop     r14
0x180029de7  pop     rdi
0x180029de8  pop     rsi
0x180029de9  pop     rbx
0x180029dea  retn
```
