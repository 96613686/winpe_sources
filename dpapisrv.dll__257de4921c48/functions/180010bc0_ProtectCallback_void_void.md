# ProtectCallback(void *,void *)

- ea: `0x180010bc0`
- end: `0x180010d0b`
- name: `?ProtectCallback@@YAJPEAX0@Z`
- size: `331`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007f10`
- `0x180010bc0`
- `0x18001eb8c`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x180010c17`
- `RPCRT4!RpcStringBindingParseW` at `0x180010c17`
- `RPCRT4!RpcStringFreeW` at `0x180010c70`
- `RPCRT4!RpcStringFreeW` at `0x180010c89`
- `RPCRT4!RpcStringFreeW` at `0x180010c70`
- `RPCRT4!RpcStringFreeW` at `0x180010c89`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180010be0`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180010be0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180010c4d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180010c4d`

## string_xrefs

- `0x180010cbb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\dpapi.cpp`
- `0x180010cf1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\dpapi.cpp`

## pseudocode

```c
__int64 __fastcall ProtectCallback(void *a1, void *a2)
{
  int v2; // edx
  unsigned int v3; // ebx
  unsigned int v4; // eax
  RPC_WSTR Protseq; // [rsp+60h] [rbp+18h] BYREF
  RPC_WSTR StringBinding; // [rsp+68h] [rbp+20h] BYREF

  StringBinding = 0;
  Protseq = 0;
  v3 = RpcBindingToStringBindingW(a2, &StringBinding);
  if ( v3 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v2,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"Status",
        v3,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\dpapi.cpp",
        56);
  }
  else
  {
    v4 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    v3 = v4;
    if ( v4 )
      DebugTraceError(v4, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\dpapi.cpp", 68);
    else
      v3 = CompareStringW(0x7Fu, 1u, Protseq, -1, L"ncalrpc", -1) != 2 ? 5 : 0;
  }
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v3;
}

```

## disassembly

```asm
0x180010bc0  push    rbx
0x180010bc2  sub     rsp, 40h
0x180010bc6  mov     rcx, rdx; Binding
0x180010bc9  mov     [rsp+48h+StringBinding], 0
0x180010bd2  lea     rdx, [rsp+48h+StringBinding]; StringBinding
0x180010bd7  mov     [rsp+48h+Protseq], 0
0x180010be0  call    cs:__imp_RpcBindingToStringBindingW
0x180010be7  nop     dword ptr [rax+rax+00h]
0x180010bec  mov     ebx, eax
0x180010bee  test    eax, eax
0x180010bf0  jnz     loc_180010C9E
0x180010bf6  mov     rcx, [rsp+48h+StringBinding]; StringBinding
0x180010bfb  lea     r8, [rsp+48h+Protseq]; Protseq
0x180010c00  mov     [rsp+48h+NetworkOptions], 0; NetworkOptions
0x180010c09  xor     r9d, r9d; NetworkAddr
0x180010c0c  xor     edx, edx; ObjUuid
0x180010c0e  mov     [rsp+48h+Endpoint], 0; Endpoint
0x180010c17  call    cs:__imp_RpcStringBindingParseW
0x180010c1e  nop     dword ptr [rax+rax+00h]
0x180010c23  mov     ebx, eax
0x180010c25  test    eax, eax
0x180010c27  jnz     loc_180010CEB
0x180010c2d  mov     r8, [rsp+48h+Protseq]; lpString1
0x180010c32  lea     rax, Protseq; "ncalrpc"
0x180010c39  or      r9d, 0FFFFFFFFh; cchCount1
0x180010c3d  lea     edx, [rbx+1]; dwCmpFlags
0x180010c40  mov     dword ptr [rsp+48h+NetworkOptions], r9d; cchCount2
0x180010c45  lea     ecx, [rbx+7Fh]; Locale
0x180010c48  mov     [rsp+48h+Endpoint], rax; lpString2
0x180010c4d  call    cs:__imp_CompareStringW
0x180010c54  nop     dword ptr [rax+rax+00h]
0x180010c59  sub     eax, 2
0x180010c5c  neg     eax
0x180010c5e  sbb     ebx, ebx
0x180010c60  and     ebx, 5
0x180010c63  cmp     [rsp+48h+Protseq], 0
0x180010c69  jz      short loc_180010C7C
0x180010c6b  lea     rcx, [rsp+48h+Protseq]; String
0x180010c70  call    cs:__imp_RpcStringFreeW
0x180010c77  nop     dword ptr [rax+rax+00h]
0x180010c7c  cmp     [rsp+48h+StringBinding], 0
0x180010c82  jz      short loc_180010C95
0x180010c84  lea     rcx, [rsp+48h+StringBinding]; String
0x180010c89  call    cs:__imp_RpcStringFreeW
0x180010c90  nop     dword ptr [rax+rax+00h]
0x180010c95  mov     eax, ebx
0x180010c97  add     rsp, 40h
0x180010c9b  pop     rbx
0x180010c9c  retn
0x180010c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ca5  lea     rax, WPP_GLOBAL_Control
0x180010cac  cmp     rcx, rax
0x180010caf  jz      short loc_180010C63
0x180010cb1  test    byte ptr [rcx+1Ch], 1
0x180010cb5  jz      short loc_180010C63
0x180010cb7  mov     rcx, [rcx+10h]
0x180010cbb  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180010cc2  mov     [rsp+48h+var_18], 38h ; '8'
0x180010cca  lea     r9, aStatus; "Status"
0x180010cd1  mov     [rsp+48h+NetworkOptions], r8
0x180010cd6  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180010cdd  mov     dword ptr [rsp+48h+Endpoint], ebx
0x180010ce1  call    WPP_SF_sDsd
0x180010ce6  jmp     loc_180010C63
0x180010ceb  mov     r9d, 44h ; 'D'
0x180010cf1  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180010cf8  lea     rdx, aStatus; "Status"
0x180010cff  mov     ecx, eax
0x180010d01  call    DebugTraceError
0x180010d06  jmp     loc_180010C63
```
