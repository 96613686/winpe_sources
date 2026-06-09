# BackupCallback(void *,void *)

- ea: `0x18002f940`
- end: `0x18002faaf`
- name: `?BackupCallback@@YAJPEAX0@Z`
- size: `367`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007f10`
- `0x18002f940`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x18002f9ba`
- `RPCRT4!RpcStringBindingParseW` at `0x18002f9ba`
- `RPCRT4!RpcStringFreeW` at `0x18002fa79`
- `RPCRT4!RpcStringFreeW` at `0x18002fa90`
- `RPCRT4!RpcStringFreeW` at `0x18002fa79`
- `RPCRT4!RpcStringFreeW` at `0x18002fa90`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002f969`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002f969`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f9f4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fa22`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fa49`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f9f4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fa22`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fa49`

## string_xrefs

- `0x18002f98a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BackupCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rcx
  RPC_WSTR Protseq; // [rsp+50h] [rbp+20h] BYREF
  RPC_WSTR StringBinding; // [rsp+58h] [rbp+28h] BYREF

  StringBinding = 0;
  Protseq = 0;
  v2 = RpcBindingToStringBindingW(Context, &StringBinding);
  v3 = v2;
  if ( v2 )
  {
    v4 = 1894;
LABEL_3:
    v5 = v2;
LABEL_4:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v4);
    goto LABEL_12;
  }
  v2 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
  v3 = v2;
  if ( v2 )
  {
    v4 = 1906;
    goto LABEL_3;
  }
  if ( CompareStringW(0x7Fu, 1u, Protseq, -1, L"ncalrpc", -1) != 2
    && CompareStringW(0x7Fu, 1u, Protseq, -1, L"ncacn_np", -1) != 2
    && CompareStringW(0x7Fu, 1u, Protseq, -1, L"ncacn_np", -1) != 2 )
  {
    v3 = 5;
    v4 = 1931;
    v5 = 5;
    goto LABEL_4;
  }
  v3 = 0;
LABEL_12:
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v3;
}

```

## disassembly

```asm
0x18002f940  mov     [rsp-8+arg_0], rbx
0x18002f945  mov     [rsp-8+arg_8], r15
0x18002f94a  push    rbp
0x18002f94b  mov     rbp, rsp
0x18002f94e  sub     rsp, 30h
0x18002f952  mov     rcx, rdx; Binding
0x18002f955  mov     [rbp+StringBinding], 0
0x18002f95d  lea     rdx, [rbp+StringBinding]; StringBinding
0x18002f961  mov     [rbp+Protseq], 0
0x18002f969  call    cs:__imp_RpcBindingToStringBindingW
0x18002f970  nop     dword ptr [rax+rax+00h]
0x18002f975  mov     ebx, eax
0x18002f977  test    eax, eax
0x18002f979  jz      short loc_18002F99B
0x18002f97b  mov     r9d, 766h
0x18002f981  mov     ecx, eax
0x18002f983  lea     rdx, aStatus; "Status"
0x18002f98a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002f991  call    DebugTraceError
0x18002f996  jmp     loc_18002FA6E
0x18002f99b  mov     rcx, [rbp+StringBinding]; StringBinding
0x18002f99f  lea     r8, [rbp+Protseq]; Protseq
0x18002f9a3  mov     [rsp+30h+NetworkOptions], 0; NetworkOptions
0x18002f9ac  xor     r9d, r9d; NetworkAddr
0x18002f9af  xor     edx, edx; ObjUuid
0x18002f9b1  mov     [rsp+30h+Endpoint], 0; Endpoint
0x18002f9ba  call    cs:__imp_RpcStringBindingParseW
0x18002f9c1  nop     dword ptr [rax+rax+00h]
0x18002f9c6  mov     ebx, eax
0x18002f9c8  test    eax, eax
0x18002f9ca  jz      short loc_18002F9D4
0x18002f9cc  mov     r9d, 772h
0x18002f9d2  jmp     short loc_18002F981
0x18002f9d4  mov     r8, [rbp+Protseq]; lpString1
0x18002f9d8  lea     rax, Protseq; "ncalrpc"
0x18002f9df  or      ebx, 0FFFFFFFFh
0x18002f9e2  mov     dword ptr [rsp+30h+NetworkOptions], ebx; cchCount2
0x18002f9e6  mov     r9d, ebx; cchCount1
0x18002f9e9  mov     [rsp+30h+Endpoint], rax; lpString2
0x18002f9ee  lea     edx, [rbx+2]; dwCmpFlags
0x18002f9f1  lea     ecx, [rdx+7Eh]; Locale
0x18002f9f4  call    cs:__imp_CompareStringW
0x18002f9fb  nop     dword ptr [rax+rax+00h]
0x18002fa00  cmp     eax, 2
0x18002fa03  jz      short loc_18002FA6C
0x18002fa05  mov     r8, [rbp+Protseq]; lpString1
0x18002fa09  lea     edx, [rbx+2]; dwCmpFlags
0x18002fa0c  lea     r15, aNcacnNp; "ncacn_np"
0x18002fa13  mov     dword ptr [rsp+30h+NetworkOptions], ebx; cchCount2
0x18002fa17  lea     ecx, [rdx+7Eh]; Locale
0x18002fa1a  mov     [rsp+30h+Endpoint], r15; lpString2
0x18002fa1f  mov     r9d, ebx; cchCount1
0x18002fa22  call    cs:__imp_CompareStringW
0x18002fa29  nop     dword ptr [rax+rax+00h]
0x18002fa2e  cmp     eax, 2
0x18002fa31  jz      short loc_18002FA6C
0x18002fa33  mov     r8, [rbp+Protseq]; lpString1
0x18002fa37  lea     edx, [rbx+2]; dwCmpFlags
0x18002fa3a  lea     ecx, [rdx+7Eh]; Locale
0x18002fa3d  mov     dword ptr [rsp+30h+NetworkOptions], ebx; cchCount2
0x18002fa41  mov     r9d, ebx; cchCount1
0x18002fa44  mov     [rsp+30h+Endpoint], r15; lpString2
0x18002fa49  call    cs:__imp_CompareStringW
0x18002fa50  nop     dword ptr [rax+rax+00h]
0x18002fa55  cmp     eax, 2
0x18002fa58  jz      short loc_18002FA6C
0x18002fa5a  mov     ebx, 5
0x18002fa5f  mov     r9d, 78Bh
0x18002fa65  mov     ecx, ebx
0x18002fa67  jmp     loc_18002F983
0x18002fa6c  xor     ebx, ebx
0x18002fa6e  cmp     [rbp+Protseq], 0
0x18002fa73  jz      short loc_18002FA85
0x18002fa75  lea     rcx, [rbp+Protseq]; String
0x18002fa79  call    cs:__imp_RpcStringFreeW
0x18002fa80  nop     dword ptr [rax+rax+00h]
0x18002fa85  cmp     [rbp+StringBinding], 0
0x18002fa8a  jz      short loc_18002FA9C
0x18002fa8c  lea     rcx, [rbp+StringBinding]; String
0x18002fa90  call    cs:__imp_RpcStringFreeW
0x18002fa97  nop     dword ptr [rax+rax+00h]
0x18002fa9c  mov     r15, [rsp+30h+arg_8]
0x18002faa1  mov     eax, ebx
0x18002faa3  mov     rbx, [rsp+30h+arg_0]
0x18002faa8  add     rsp, 30h
0x18002faac  pop     rbp
0x18002faad  retn
```
