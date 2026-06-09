# DllRegisterServer

- ea: `0x1801f2cf0`
- end: `0x1801f2d85`
- name: `DllRegisterServer`
- size: `149`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1801aacd0`
- `0x1801dd16c`
- `0x1801dd670`
- `0x1801f2cf0`
- `0x1801fe340`
- `0x18035e010`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x1801f2d6f`
- `RPCRT4!NdrDllRegisterProxy` at `0x1801f2d6f`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
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
    v3 = sub_1801DD16C(v1);
    sub_1801DD670(v2);
    if ( v3 < 0 )
      return v3;
  }
  if ( &off_18036C710 )
    v5 = (const CLSID *)&qword_1803B9830;
  else
    v5 = 0;
  return NdrDllRegisterProxy(hDll, (const ProxyFileInfo **)&pProxyFileList, v5);
}

```

## disassembly

```asm
0x1801f2cf0  mov     [rsp+arg_0], rbx
0x1801f2cf5  mov     [rsp+arg_8], rsi
0x1801f2cfa  push    rdi
0x1801f2cfb  sub     rsp, 20h
0x1801f2cff  xor     ebx, ebx
0x1801f2d01  cmp     ebx, 2
0x1801f2d04  jnb     short loc_1801F2D46
0x1801f2d06  lea     rcx, funcs_1801F2D14
0x1801f2d0d  movsxd  rax, ebx
0x1801f2d10  mov     rax, ds:(funcs_1801F2D14 - 1803711B0h)[rcx+rax*8]
0x1801f2d14  call    j_j__guard_dispatch_icall_nop
0x1801f2d19  mov     rsi, rax
0x1801f2d1c  test    rax, rax
0x1801f2d1f  jz      short loc_1801F2D3F
0x1801f2d21  mov     rcx, rax
0x1801f2d24  call    sub_1801DD16C
0x1801f2d29  mov     rcx, rsi
0x1801f2d2c  mov     edi, eax
0x1801f2d2e  call    sub_1801DD670
0x1801f2d33  test    edi, edi
0x1801f2d35  js      short loc_1801F2D3B
0x1801f2d37  inc     ebx
0x1801f2d39  jmp     short loc_1801F2D01
0x1801f2d3b  mov     eax, edi
0x1801f2d3d  jmp     short loc_1801F2D75
0x1801f2d3f  mov     eax, 8000FFFFh
0x1801f2d44  jmp     short loc_1801F2D75
0x1801f2d46  mov     rax, cs:pProxyFileList
0x1801f2d4d  mov     rcx, [rax+8]
0x1801f2d51  mov     rax, [rcx]
0x1801f2d54  test    rax, rax
0x1801f2d57  jz      short loc_1801F2D5E
0x1801f2d59  mov     r8, [rax]
0x1801f2d5c  jmp     short loc_1801F2D61
0x1801f2d5e  xor     r8d, r8d; pclsid
0x1801f2d61  mov     rcx, cs:hDll; hDll
0x1801f2d68  lea     rdx, pProxyFileList; pProxyFileList
0x1801f2d6f  call    cs:NdrDllRegisterProxy
0x1801f2d75  mov     rbx, [rsp+28h+arg_0]
0x1801f2d7a  mov     rsi, [rsp+28h+arg_8]
0x1801f2d7f  add     rsp, 20h
0x1801f2d83  pop     rdi
0x1801f2d84  retn
```
