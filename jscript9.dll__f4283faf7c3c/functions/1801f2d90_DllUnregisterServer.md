# DllUnregisterServer

- ea: `0x1801f2d90`
- end: `0x1801f2e23`
- name: `DllUnregisterServer`
- size: `147`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1801aacd0`
- `0x1801dd670`
- `0x1801dd77c`
- `0x1801f2d90`
- `0x1801fe340`
- `0x18035e010`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x1801f2e0d`
- `RPCRT4!NdrDllUnregisterProxy` at `0x1801f2e0d`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  unsigned int i; // ebx
  __int64 v1; // rax
  __int64 v2; // rsi
  HRESULT v3; // edi
  const CLSID *v5; // r8

  for ( i = 0; i < 2; ++i )
  {
    v1 = funcs_1801F2D14[i]();
    v2 = v1;
    if ( !v1 )
      return -2147418113;
    v3 = sub_1801DD77C(v1);
    sub_1801DD670(v2);
    if ( v3 < 0 )
      return v3;
  }
  if ( &off_18036C710 )
    v5 = (const CLSID *)&qword_1803B9830;
  else
    v5 = 0;
  return NdrDllUnregisterProxy(hDll, (const ProxyFileInfo **)&pProxyFileList, v5);
}

```

## disassembly

```asm
0x1801f2d90  mov     [rsp+arg_0], rbx
0x1801f2d95  mov     [rsp+arg_8], rsi
0x1801f2d9a  push    rdi
0x1801f2d9b  sub     rsp, 20h
0x1801f2d9f  xor     ebx, ebx
0x1801f2da1  cmp     ebx, 2
0x1801f2da4  jnb     short loc_1801F2DE4
0x1801f2da6  lea     rcx, funcs_1801F2D14
0x1801f2dad  movsxd  rax, ebx
0x1801f2db0  mov     rax, ds:(funcs_1801F2D14 - 1803711B0h)[rcx+rax*8]
0x1801f2db4  call    j_j__guard_dispatch_icall_nop
0x1801f2db9  mov     rsi, rax
0x1801f2dbc  test    rax, rax
0x1801f2dbf  jz      short loc_1801F2DDB
0x1801f2dc1  mov     rcx, rax
0x1801f2dc4  call    sub_1801DD77C
0x1801f2dc9  mov     rcx, rsi
0x1801f2dcc  mov     edi, eax
0x1801f2dce  call    sub_1801DD670
0x1801f2dd3  test    edi, edi
0x1801f2dd5  js      short loc_1801F2DE0
0x1801f2dd7  inc     ebx
0x1801f2dd9  jmp     short loc_1801F2DA1
0x1801f2ddb  mov     edi, 8000FFFFh
0x1801f2de0  mov     eax, edi
0x1801f2de2  jmp     short loc_1801F2E13
0x1801f2de4  mov     rax, cs:pProxyFileList
0x1801f2deb  mov     rcx, [rax+8]
0x1801f2def  mov     rax, [rcx]
0x1801f2df2  test    rax, rax
0x1801f2df5  jz      short loc_1801F2DFC
0x1801f2df7  mov     r8, [rax]
0x1801f2dfa  jmp     short loc_1801F2DFF
0x1801f2dfc  xor     r8d, r8d; pclsid
0x1801f2dff  mov     rcx, cs:hDll; hDll
0x1801f2e06  lea     rdx, pProxyFileList; pProxyFileList
0x1801f2e0d  call    cs:NdrDllUnregisterProxy
0x1801f2e13  mov     rbx, [rsp+28h+arg_0]
0x1801f2e18  mov     rsi, [rsp+28h+arg_8]
0x1801f2e1d  add     rsp, 20h
0x1801f2e21  pop     rdi
0x1801f2e22  retn
```
