# GetServerVariableCacheUrl(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x180016c20`
- end: `0x180016dcf`
- name: `?GetServerVariableCacheUrl@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `431`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180016c20`
- `0x18002dfa0`
- `0x180038010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x180016ce7`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180016ce7`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180016d21`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180016d21`

## pseudocode

```c
__int64 __fastcall GetServerVariableCacheUrl(struct W3_CONTEXT *a1, const unsigned __int16 **a2, unsigned int *a3)
{
  __int64 v6; // r9
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v11; // rbx
  ULONG v12; // edx
  __int64 v13; // rax
  WCHAR *v14; // rax
  unsigned int v15; // r12d
  unsigned __int16 *v16; // rax
  const unsigned __int16 *v17; // rbx
  ULONG AddressStringLength; // [rsp+80h] [rbp+8h] BYREF
  __int64 v19; // [rsp+98h] [rbp+20h]

  v6 = *(_QWORD *)(*((_QWORD *)a1 + 49) + 48LL);
  v7 = *(_QWORD *)(v6 + 40);
  v8 = *(unsigned int *)(v6 + 240);
  if ( (*(_BYTE *)v7 & 2) == 0 )
  {
    *a2 = *(const unsigned __int16 **)(v6 + 224);
    LODWORD(v9) = v8;
LABEL_3:
    *a3 = v9;
    return 0;
  }
  v11 = *(_QWORD *)(v7 + 112);
  if ( *(_WORD *)v11 == 2 )
  {
    v12 = 16;
  }
  else
  {
    if ( *(_WORD *)v11 != 23 )
      return 2147942413LL;
    v12 = 60;
  }
  v19 = *(_QWORD *)(v6 + 232);
  v13 = *(_QWORD *)a1;
  AddressStringLength = v12;
  v14 = (WCHAR *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *, _QWORD))(v13 + 144))(a1, 2 * v12);
  if ( !v14 )
    return 2147942408LL;
  if ( *(_WORD *)v11 == 2 )
    RtlIpv4AddressToStringExW((const struct in_addr *)(v11 + 4), 0, v14, &AddressStringLength);
  else
    RtlIpv6AddressToStringExW((const struct in6_addr *)(v11 + 8), *(_DWORD *)(v11 + 24), 0, v14, &AddressStringLength);
  if ( v8 + (unsigned __int64)(AddressStringLength - 1) + 2 <= 0xFFFFFFFF )
  {
    v15 = v8 + AddressStringLength - 1 + 2;
    v16 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *, _QWORD))(*(_QWORD *)a1 + 144LL))(
                                a1,
                                2 * v15);
    v17 = v16;
    if ( v16 )
    {
      StringCchPrintfW(v16, v15, L"%.*s:%s%.*s");
      v9 = -1;
      *a2 = v17;
      do
        ++v9;
      while ( v17[v9] );
      goto LABEL_3;
    }
    return 2147942408LL;
  }
  return 2147942934LL;
}

```

## disassembly

```asm
0x180016c20  mov     [rsp+arg_8], rbx
0x180016c25  push    rbp
0x180016c26  push    rsi
0x180016c27  push    rdi
0x180016c28  push    r12
0x180016c2a  push    r13
0x180016c2c  push    r14
0x180016c2e  push    r15
0x180016c30  sub     rsp, 40h
0x180016c34  mov     rax, [rcx+188h]
0x180016c3b  mov     r13, r8
0x180016c3e  mov     r15, rdx
0x180016c41  mov     rsi, rcx
0x180016c44  mov     r9, [rax+30h]
0x180016c48  mov     rbx, [r9+28h]
0x180016c4c  mov     r14, [r9+0E0h]
0x180016c53  mov     edi, [r9+0F0h]
0x180016c5a  test    byte ptr [rbx], 2
0x180016c5d  jnz     short loc_180016C83
0x180016c5f  mov     [rdx], r14
0x180016c62  mov     eax, edi
0x180016c64  mov     [r13+0], eax
0x180016c68  xor     eax, eax
0x180016c6a  mov     rbx, [rsp+78h+arg_8]
0x180016c72  add     rsp, 40h
0x180016c76  pop     r15
0x180016c78  pop     r14
0x180016c7a  pop     r13
0x180016c7c  pop     r12
0x180016c7e  pop     rdi
0x180016c7f  pop     rsi
0x180016c80  pop     rbp
0x180016c81  retn
0x180016c83  mov     rbx, [rbx+70h]
0x180016c87  cmp     word ptr [rbx], 2
0x180016c8b  jz      short loc_180016CF5
0x180016c8d  cmp     word ptr [rbx], 17h
0x180016c91  jnz     short loc_180016D06
0x180016c93  mov     edx, 3Ch ; '<'
0x180016c98  mov     rax, [r9+0E8h]
0x180016c9f  mov     [rsp+78h+arg_18], rax
0x180016ca7  mov     rax, [rcx]
0x180016caa  mov     [rsp+78h+arg_0], edx
0x180016cb1  add     edx, edx
0x180016cb3  mov     rax, [rax+90h]
0x180016cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cbf  mov     rbp, rax
0x180016cc2  test    rax, rax
0x180016cc5  jz      short loc_180016CFC
0x180016cc7  cmp     word ptr [rbx], 2
0x180016ccb  jz      short loc_180016D10
0x180016ccd  mov     edx, [rbx+18h]; ScopeId
0x180016cd0  lea     rax, [rsp+78h+arg_0]
0x180016cd8  xor     r8d, r8d; Port
0x180016cdb  mov     [rsp+78h+AddressStringLength], rax; AddressStringLength
0x180016ce0  lea     rcx, [rbx+8]; Address
0x180016ce4  mov     r9, rbp; AddressString
0x180016ce7  call    cs:__imp_RtlIpv6AddressToStringExW
0x180016cee  nop     dword ptr [rax+rax+00h]
0x180016cf3  jmp     short loc_180016D2D
0x180016cf5  mov     edx, 10h
0x180016cfa  jmp     short loc_180016C98
0x180016cfc  mov     eax, 80070008h
0x180016d01  jmp     loc_180016C6A
0x180016d06  mov     eax, 8007000Dh
0x180016d0b  jmp     loc_180016C6A
0x180016d10  xor     edx, edx; Port
0x180016d12  lea     rcx, [rbx+4]; Address
0x180016d16  lea     r9, [rsp+78h+arg_0]; AddressStringLength
0x180016d1e  mov     r8, rbp; AddressString
0x180016d21  call    cs:__imp_RtlIpv4AddressToStringExW
0x180016d28  nop     dword ptr [rax+rax+00h]
0x180016d2d  mov     r8d, [rsp+78h+arg_0]
0x180016d35  mov     eax, 0FFFFFFFFh
0x180016d3a  dec     r8d
0x180016d3d  mov     edx, r8d
0x180016d40  add     rdx, 2
0x180016d44  add     rdx, rdi
0x180016d47  cmp     rdx, rax
0x180016d4a  jbe     short loc_180016D56
0x180016d4c  mov     eax, 80070216h
0x180016d51  jmp     loc_180016C6A
0x180016d56  mov     rax, [rsi]
0x180016d59  lea     r12d, [r8+2]
0x180016d5d  add     r12d, edi
0x180016d60  mov     rcx, rsi
0x180016d63  mov     rax, [rax+90h]
0x180016d6a  lea     edx, [r12+r12]
0x180016d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d73  xor     esi, esi
0x180016d75  mov     rbx, rax
0x180016d78  test    rax, rax
0x180016d7b  jz      loc_180016CFC
0x180016d81  mov     rax, [rsp+78h+arg_18]
0x180016d89  lea     r8, aSSS; "%.*s:%s%.*s"
0x180016d90  mov     [rsp+78h+var_40], rax
0x180016d95  mov     r9, rax
0x180016d98  sub     r9, r14
0x180016d9b  mov     edx, r12d; unsigned __int64
0x180016d9e  sar     r9, 1
0x180016da1  mov     rcx, rbx; unsigned __int16 *
0x180016da4  sub     edi, r9d
0x180016da7  mov     [rsp+78h+var_48], edi
0x180016dab  mov     [rsp+78h+var_50], rbp
0x180016db0  mov     [rsp+78h+AddressStringLength], r14
0x180016db5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016dba  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016dbe  mov     [r15], rbx
0x180016dc1  inc     rax
0x180016dc4  cmp     [rbx+rax*2], si
0x180016dc8  jnz     short loc_180016DC1
0x180016dca  jmp     loc_180016C64
```
