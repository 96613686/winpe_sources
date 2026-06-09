# GetServerVariableCacheUrl(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x180015a20`
- end: `0x180015bbe`
- name: `?GetServerVariableCacheUrl@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180015a20`
- `0x18002b8b0`
- `0x180035010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x180015ae6`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180015ae6`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180015b1a`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180015b1a`

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
0x180015a20  mov     [rsp+arg_8], rbx
0x180015a25  push    rbp
0x180015a26  push    rsi
0x180015a27  push    rdi
0x180015a28  push    r12
0x180015a2a  push    r13
0x180015a2c  push    r14
0x180015a2e  push    r15
0x180015a30  sub     rsp, 40h
0x180015a34  mov     rax, [rcx+188h]
0x180015a3b  mov     r13, r8
0x180015a3e  mov     r15, rdx
0x180015a41  mov     rsi, rcx
0x180015a44  mov     r9, [rax+30h]
0x180015a48  mov     rbx, [r9+28h]
0x180015a4c  mov     r14, [r9+0E0h]
0x180015a53  mov     edi, [r9+0F0h]
0x180015a5a  test    byte ptr [rbx], 2
0x180015a5d  jnz     short loc_180015A82
0x180015a5f  mov     [rdx], r14
0x180015a62  mov     eax, edi
0x180015a64  mov     [r13+0], eax
0x180015a68  xor     eax, eax
0x180015a6a  mov     rbx, [rsp+78h+arg_8]
0x180015a72  add     rsp, 40h
0x180015a76  pop     r15
0x180015a78  pop     r14
0x180015a7a  pop     r13
0x180015a7c  pop     r12
0x180015a7e  pop     rdi
0x180015a7f  pop     rsi
0x180015a80  pop     rbp
0x180015a81  retn
0x180015a82  mov     rbx, [rbx+70h]
0x180015a86  cmp     word ptr [rbx], 2
0x180015a8a  jz      short loc_180015AEE
0x180015a8c  cmp     word ptr [rbx], 17h
0x180015a90  jnz     short loc_180015AFF
0x180015a92  mov     edx, 3Ch ; '<'
0x180015a97  mov     rax, [r9+0E8h]
0x180015a9e  mov     [rsp+78h+arg_18], rax
0x180015aa6  mov     rax, [rcx]
0x180015aa9  mov     [rsp+78h+arg_0], edx
0x180015ab0  add     edx, edx
0x180015ab2  mov     rax, [rax+90h]
0x180015ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015abe  mov     rbp, rax
0x180015ac1  test    rax, rax
0x180015ac4  jz      short loc_180015AF5
0x180015ac6  cmp     word ptr [rbx], 2
0x180015aca  jz      short loc_180015B09
0x180015acc  mov     edx, [rbx+18h]; ScopeId
0x180015acf  lea     rax, [rsp+78h+arg_0]
0x180015ad7  xor     r8d, r8d; Port
0x180015ada  mov     [rsp+78h+AddressStringLength], rax; AddressStringLength
0x180015adf  lea     rcx, [rbx+8]; Address
0x180015ae3  mov     r9, rbp; AddressString
0x180015ae6  call    cs:__imp_RtlIpv6AddressToStringExW
0x180015aec  jmp     short loc_180015B20
0x180015aee  mov     edx, 10h
0x180015af3  jmp     short loc_180015A97
0x180015af5  mov     eax, 80070008h
0x180015afa  jmp     loc_180015A6A
0x180015aff  mov     eax, 8007000Dh
0x180015b04  jmp     loc_180015A6A
0x180015b09  xor     edx, edx; Port
0x180015b0b  lea     rcx, [rbx+4]; Address
0x180015b0f  lea     r9, [rsp+78h+arg_0]; AddressStringLength
0x180015b17  mov     r8, rbp; AddressString
0x180015b1a  call    cs:__imp_RtlIpv4AddressToStringExW
0x180015b20  mov     r8d, [rsp+78h+arg_0]
0x180015b28  mov     eax, 0FFFFFFFFh
0x180015b2d  dec     r8d
0x180015b30  mov     edx, r8d
0x180015b33  add     rdx, 2
0x180015b37  add     rdx, rdi
0x180015b3a  cmp     rdx, rax
0x180015b3d  jbe     short loc_180015B49
0x180015b3f  mov     eax, 80070216h
0x180015b44  jmp     loc_180015A6A
0x180015b49  mov     rax, [rsi]
0x180015b4c  lea     r12d, [r8+2]
0x180015b50  add     r12d, edi
0x180015b53  mov     rcx, rsi
0x180015b56  mov     rax, [rax+90h]
0x180015b5d  lea     edx, [r12+r12]
0x180015b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b66  xor     esi, esi
0x180015b68  mov     rbx, rax
0x180015b6b  test    rax, rax
0x180015b6e  jz      short loc_180015AF5
0x180015b70  mov     rax, [rsp+78h+arg_18]
0x180015b78  lea     r8, aSSS; "%.*s:%s%.*s"
0x180015b7f  mov     [rsp+78h+var_40], rax
0x180015b84  mov     r9, rax
0x180015b87  sub     r9, r14
0x180015b8a  mov     edx, r12d; unsigned __int64
0x180015b8d  sar     r9, 1
0x180015b90  mov     rcx, rbx; unsigned __int16 *
0x180015b93  sub     edi, r9d
0x180015b96  mov     [rsp+78h+var_48], edi
0x180015b9a  mov     [rsp+78h+var_50], rbp
0x180015b9f  mov     [rsp+78h+AddressStringLength], r14
0x180015ba4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015ba9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015bad  mov     [r15], rbx
0x180015bb0  inc     rax
0x180015bb3  cmp     [rbx+rax*2], si
0x180015bb7  jnz     short loc_180015BB0
0x180015bb9  jmp     loc_180015A64
```
