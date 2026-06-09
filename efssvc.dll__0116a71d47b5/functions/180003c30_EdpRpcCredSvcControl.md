# EdpRpcCredSvcControl

- ea: `0x180003c30`
- end: `0x180003d65`
- name: `EdpRpcCredSvcControl`
- size: `309`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, unsigned int, __int64, __int64, __int64, int, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180003c30`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d38`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180003c6e`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180003c6e`
- `EFSCORE!EdpDllCredSvcControl` at `0x180003d05`
- `EFSCORE!EdpDllCredSvcControl` at `0x180003d05`

## pseudocode

```c
__int64 __fastcall EdpRpcCredSvcControl(
        RPC_BINDING_HANDLE Binding,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        __int64 a10)
{
  int v14; // edi
  RPC_STATUS v15; // eax
  int v16; // ecx
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  int v21; // ecx
  void *ClientProcess; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v24[152]; // [rsp+70h] [rbp-98h] BYREF

  memset_0(v24, 0, 0x70u);
  v14 = 0;
  ClientProcess = 0;
  v15 = I_RpcOpenClientProcess(Binding, 0x1000u, &ClientProcess);
  if ( v15 )
  {
    v17 = 0;
    fnEfsLogTrace1(v16, (unsigned int)EFS_API_ERROR, v15, 6, 108);
  }
  else
  {
    v18 = EdpBeginLocalOnlyRpcCall((__int64)v24);
    v17 = v18;
    if ( v18 >= 0 )
    {
      v14 = 1;
      v20 = EdpDllCredSvcControl(v24, ClientProcess, a2, a3, a4, a5, a6, a7, a8, a9, a10);
      v17 = v20;
      if ( v20 < 0 )
        fnEfsLogTrace1(v21, (unsigned int)EFS_API_ERROR, v20, 6, 133);
    }
    else
    {
      fnEfsLogTrace1(v19, (unsigned int)EFS_API_ERROR, v18, 6, 115);
    }
  }
  if ( ClientProcess )
  {
    CloseHandle(ClientProcess);
    ClientProcess = 0;
  }
  if ( v14 )
    EdpCleanupLocalOnlyRpcCall((__int64)v24);
  return v17;
}

```

## disassembly

```asm
0x180003c30  push    rbx
0x180003c32  push    rbp
0x180003c33  push    rsi
0x180003c34  push    rdi
0x180003c35  push    r14
0x180003c37  sub     rsp, 0E0h
0x180003c3e  mov     r14d, edx
0x180003c41  mov     rbp, r8
0x180003c44  xor     edx, edx; Val
0x180003c46  mov     rbx, rcx
0x180003c49  lea     rcx, [rsp+108h+var_98]; void *
0x180003c4e  mov     rsi, r9
0x180003c51  lea     r8d, [rdx+70h]; Size
0x180003c55  call    memset_0
0x180003c5a  xor     edi, edi
0x180003c5c  lea     r8, [rsp+108h+ClientProcess]; ClientProcess
0x180003c61  mov     edx, 1000h; DesiredAccess
0x180003c66  mov     [rsp+108h+ClientProcess], rdi
0x180003c6b  mov     rcx, rbx; Binding
0x180003c6e  call    cs:__imp_I_RpcOpenClientProcess
0x180003c74  test    eax, eax
0x180003c76  jz      short loc_180003C87
0x180003c78  xor     ebx, ebx
0x180003c7a  mov     dword ptr [rsp+108h+var_E8], 0F6Ch
0x180003c82  jmp     loc_180003D19
0x180003c87  lea     rcx, [rsp+108h+var_98]
0x180003c8c  call    EdpBeginLocalOnlyRpcCall
0x180003c91  mov     ebx, eax
0x180003c93  test    eax, eax
0x180003c95  jns     short loc_180003CA1
0x180003c97  mov     dword ptr [rsp+108h+var_E8], 0F73h
0x180003c9f  jmp     short loc_180003D19
0x180003ca1  mov     rax, [rsp+108h+arg_48]
0x180003ca9  lea     rcx, [rsp+108h+var_98]
0x180003cae  mov     rdx, [rsp+108h+ClientProcess]
0x180003cb3  mov     r9, rbp
0x180003cb6  mov     [rsp+108h+var_B8], rax
0x180003cbb  mov     r8d, r14d
0x180003cbe  mov     rax, [rsp+108h+arg_40]
0x180003cc6  mov     edi, 1
0x180003ccb  mov     [rsp+108h+var_C0], rax
0x180003cd0  mov     eax, [rsp+108h+arg_38]
0x180003cd7  mov     [rsp+108h+var_C8], eax
0x180003cdb  mov     rax, [rsp+108h+arg_30]
0x180003ce3  mov     [rsp+108h+var_D0], rax
0x180003ce8  mov     eax, [rsp+108h+arg_28]
0x180003cef  mov     [rsp+108h+var_D8], eax
0x180003cf3  mov     rax, [rsp+108h+arg_20]
0x180003cfb  mov     [rsp+108h+var_E0], rax
0x180003d00  mov     [rsp+108h+var_E8], rsi
0x180003d05  call    cs:__imp_EdpDllCredSvcControl
0x180003d0b  mov     ebx, eax
0x180003d0d  test    eax, eax
0x180003d0f  jns     short loc_180003D2E
0x180003d11  mov     dword ptr [rsp+108h+var_E8], 0F85h
0x180003d19  mov     r9d, 6
0x180003d1f  lea     rdx, EFS_API_ERROR
0x180003d26  mov     r8d, eax
0x180003d29  call    fnEfsLogTrace1
0x180003d2e  mov     rcx, [rsp+108h+ClientProcess]; hObject
0x180003d33  test    rcx, rcx
0x180003d36  jz      short loc_180003D47
0x180003d38  call    cs:__imp_CloseHandle
0x180003d3e  mov     [rsp+108h+ClientProcess], 0
0x180003d47  test    edi, edi
0x180003d49  jz      short loc_180003D55
0x180003d4b  lea     rcx, [rsp+108h+var_98]
0x180003d50  call    EdpCleanupLocalOnlyRpcCall
0x180003d55  mov     eax, ebx
0x180003d57  add     rsp, 0E0h
0x180003d5e  pop     r14
0x180003d60  pop     rdi
0x180003d61  pop     rsi
0x180003d62  pop     rbp
0x180003d63  pop     rbx
0x180003d64  retn
```
