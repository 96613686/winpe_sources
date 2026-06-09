# EdpRpcCredSvcControl

- ea: `0x180003e90`
- end: `0x180003fd8`
- name: `EdpRpcCredSvcControl`
- size: `328`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, unsigned int, __int64, __int64, __int64, int, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180003e90`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fa4`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180003ece`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180003ece`
- `EFSCORE!EdpDllCredSvcControl` at `0x180003f6b`
- `EFSCORE!EdpDllCredSvcControl` at `0x180003f6b`

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
  __int64 v16; // rcx
  unsigned int v17; // ebx
  signed int v18; // eax
  __int64 v19; // rcx
  signed int v20; // eax
  __int64 v21; // rcx
  void *ClientProcess; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v24[152]; // [rsp+70h] [rbp-98h] BYREF

  memset_0(v24, 0, 0x70u);
  v14 = 0;
  ClientProcess = 0;
  v15 = I_RpcOpenClientProcess(Binding, 0x1000u, &ClientProcess);
  if ( v15 )
  {
    v17 = 0;
    fnEfsLogTrace1(v16, (__int64)EFS_API_ERROR, v15, 6, 108);
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
        fnEfsLogTrace1(v21, (__int64)EFS_API_ERROR, v20, 6, 133);
    }
    else
    {
      fnEfsLogTrace1(v19, (__int64)EFS_API_ERROR, v18, 6, 115);
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
0x180003e90  push    rbx
0x180003e92  push    rbp
0x180003e93  push    rsi
0x180003e94  push    rdi
0x180003e95  push    r14
0x180003e97  sub     rsp, 0E0h
0x180003e9e  mov     r14d, edx
0x180003ea1  mov     rbp, r8
0x180003ea4  xor     edx, edx; Val
0x180003ea6  mov     rbx, rcx
0x180003ea9  lea     rcx, [rsp+108h+var_98]; void *
0x180003eae  mov     rsi, r9
0x180003eb1  lea     r8d, [rdx+70h]; Size
0x180003eb5  call    memset_0
0x180003eba  xor     edi, edi
0x180003ebc  lea     r8, [rsp+108h+ClientProcess]; ClientProcess
0x180003ec1  mov     edx, 1000h; DesiredAccess
0x180003ec6  mov     [rsp+108h+ClientProcess], rdi
0x180003ecb  mov     rcx, rbx; Binding
0x180003ece  call    cs:__imp_I_RpcOpenClientProcess
0x180003ed5  nop     dword ptr [rax+rax+00h]
0x180003eda  test    eax, eax
0x180003edc  jz      short loc_180003EED
0x180003ede  xor     ebx, ebx
0x180003ee0  mov     dword ptr [rsp+108h+var_E8], 0F6Ch
0x180003ee8  jmp     loc_180003F85
0x180003eed  lea     rcx, [rsp+108h+var_98]
0x180003ef2  call    EdpBeginLocalOnlyRpcCall
0x180003ef7  mov     ebx, eax
0x180003ef9  test    eax, eax
0x180003efb  jns     short loc_180003F07
0x180003efd  mov     dword ptr [rsp+108h+var_E8], 0F73h
0x180003f05  jmp     short loc_180003F85
0x180003f07  mov     rax, [rsp+108h+arg_48]
0x180003f0f  lea     rcx, [rsp+108h+var_98]
0x180003f14  mov     rdx, [rsp+108h+ClientProcess]
0x180003f19  mov     r9, rbp
0x180003f1c  mov     [rsp+108h+var_B8], rax
0x180003f21  mov     r8d, r14d
0x180003f24  mov     rax, [rsp+108h+arg_40]
0x180003f2c  mov     edi, 1
0x180003f31  mov     [rsp+108h+var_C0], rax
0x180003f36  mov     eax, [rsp+108h+arg_38]
0x180003f3d  mov     [rsp+108h+var_C8], eax
0x180003f41  mov     rax, [rsp+108h+arg_30]
0x180003f49  mov     [rsp+108h+var_D0], rax
0x180003f4e  mov     eax, [rsp+108h+arg_28]
0x180003f55  mov     [rsp+108h+var_D8], eax
0x180003f59  mov     rax, [rsp+108h+arg_20]
0x180003f61  mov     [rsp+108h+var_E0], rax
0x180003f66  mov     [rsp+108h+var_E8], rsi
0x180003f6b  call    cs:__imp_EdpDllCredSvcControl
0x180003f72  nop     dword ptr [rax+rax+00h]
0x180003f77  mov     ebx, eax
0x180003f79  test    eax, eax
0x180003f7b  jns     short loc_180003F9A
0x180003f7d  mov     dword ptr [rsp+108h+var_E8], 0F85h
0x180003f85  mov     r9d, 6
0x180003f8b  lea     rdx, EFS_API_ERROR
0x180003f92  mov     r8d, eax
0x180003f95  call    fnEfsLogTrace1
0x180003f9a  mov     rcx, [rsp+108h+ClientProcess]; hObject
0x180003f9f  test    rcx, rcx
0x180003fa2  jz      short loc_180003FB9
0x180003fa4  call    cs:__imp_CloseHandle
0x180003fab  nop     dword ptr [rax+rax+00h]
0x180003fb0  mov     [rsp+108h+ClientProcess], 0
0x180003fb9  test    edi, edi
0x180003fbb  jz      short loc_180003FC7
0x180003fbd  lea     rcx, [rsp+108h+var_98]
0x180003fc2  call    EdpCleanupLocalOnlyRpcCall
0x180003fc7  mov     eax, ebx
0x180003fc9  add     rsp, 0E0h
0x180003fd0  pop     r14
0x180003fd2  pop     rdi
0x180003fd3  pop     rsi
0x180003fd4  pop     rbp
0x180003fd5  pop     rbx
0x180003fd6  retn
```
