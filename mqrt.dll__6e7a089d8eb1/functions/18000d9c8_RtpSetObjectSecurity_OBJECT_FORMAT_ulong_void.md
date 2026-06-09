# RtpSetObjectSecurity(OBJECT_FORMAT *,ulong,void *)

- ea: `0x18000d9c8`
- end: `0x18000da5b`
- name: `?RtpSetObjectSecurity@@YAJPEAUOBJECT_FORMAT@@KPEAX@Z`
- size: `147`
- prototype: `__int64 __fastcall(struct OBJECT_FORMAT *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800106c0`

## callees

- `0x18000d7c0`
- `0x18000d9c8`
- `0x180013c74`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000da28`
- `RPCRT4!NdrClientCall3` at `0x18000da28`
- `KERNEL32!TlsGetValue` at `0x18000d9f9`
- `KERNEL32!TlsGetValue` at `0x18000d9f9`

## pseudocode

```c
__int64 __fastcall RtpSetObjectSecurity(struct OBJECT_FORMAT *a1, int a2, void *a3)
{
  LPVOID Value; // rax
  int Pointer; // eax
  unsigned int v8; // ebx
  int v10; // [rsp+28h] [rbp-20h]
  DWORD v11; // [rsp+30h] [rbp-18h]
  DWORD v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  GetSecurityDescriptorSize(a3, &v12);
  Value = TlsGetValue(g_hBindIndex);
  v11 = v12;
  v10 = a2;
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 7u, 0, Value, a1, v10, v11, a3).Pointer;
  v8 = Pointer;
  if ( Pointer < 0 )
    LogMsgHR(Pointer, (wchar_t *)L"rt/qmrt", 0x1Eu);
  return v8;
}

```

## disassembly

```asm
0x18000d9c8  mov     rax, rsp
0x18000d9cb  mov     [rax+8], rbx
0x18000d9cf  mov     [rax+10h], rsi
0x18000d9d3  push    rdi
0x18000d9d4  sub     rsp, 40h
0x18000d9d8  mov     edi, edx
0x18000d9da  mov     dword ptr [rax+20h], 0
0x18000d9e1  mov     rsi, rcx
0x18000d9e4  lea     rdx, [rax+20h]
0x18000d9e8  mov     rcx, r8
0x18000d9eb  mov     rbx, r8
0x18000d9ee  call    GetSecurityDescriptorSize
0x18000d9f3  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x18000d9f9  call    cs:__imp_TlsGetValue
0x18000d9ff  mov     r8d, [rsp+48h+arg_18]
0x18000da04  lea     rcx, pProxyInfo; pProxyInfo
0x18000da0b  mov     [rsp+48h+var_10], rbx
0x18000da10  mov     r9, rax
0x18000da13  mov     [rsp+48h+var_18], r8d
0x18000da18  xor     r8d, r8d; pReturnValue
0x18000da1b  mov     [rsp+48h+var_20], edi
0x18000da1f  mov     [rsp+48h+var_28], rsi
0x18000da24  lea     edx, [r8+7]; nProcNum
0x18000da28  call    cs:__imp_NdrClientCall3
0x18000da2e  mov     rbx, rax
0x18000da31  test    eax, eax
0x18000da33  jns     short loc_18000DA49
0x18000da35  mov     r8d, 1Eh; unsigned __int16
0x18000da3b  lea     rdx, aRtQmrt; "rt/qmrt"
0x18000da42  mov     ecx, ebx; int
0x18000da44  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000da49  mov     rsi, [rsp+48h+arg_8]
0x18000da4e  mov     eax, ebx
0x18000da50  mov     rbx, [rsp+48h+arg_0]
0x18000da55  add     rsp, 40h
0x18000da59  pop     rdi
0x18000da5a  retn
```
