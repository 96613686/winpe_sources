# FwpmTransactionCommit0

- ea: `0x18000adf0`
- end: `0x18000aed6`
- name: `FwpmTransactionCommit0`
- size: `230`
- prototype: `DWORD __stdcall(HANDLE engineHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800034e0`
- `0x18000adf0`
- `0x18004b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ae21`
- `RPCRT4!NdrClientCall3` at `0x18000ae21`

## string_xrefs

- `0x18000ae91`: `FwpmTransactionCommit0`
- `0x18000ae9a`: `FwppProxyTransactionCommit`
- `0x18000ae4f`: `BfeRpcTransactionCommit`

## pseudocode

```c
DWORD __stdcall FwpmTransactionCommit0(HANDLE engineHandle)
{
  unsigned int Pointer; // eax
  const char *v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rax
  DWORD v6; // edx

  if ( engineHandle )
  {
    if ( *((_QWORD *)engineHandle + 14) )
    {
      Pointer = (*(__int64 (__fastcall **)(_QWORD))(g_pBfeDirectDispatchTable + 88))(0);
      if ( !Pointer )
        return 0;
      v3 = "BfeRpcTransactionCommit";
    }
    else
    {
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0xDu,
                                0,
                                *(_QWORD *)engineHandle,
                                *((_QWORD *)engineHandle + 1)).Pointer;
      if ( !Pointer )
        return 0;
      v3 = "FwppProxyTransactionCommit";
    }
    v4 = Pointer;
  }
  else
  {
    v4 = 2150760476LL;
    v3 = "FwpmTransactionCommit0";
  }
  v5 = WfpReportSysErrorAsWinError(engineHandle, v3, v4);
  if ( !v5 )
    return 0;
  v6 = (unsigned __int16)v5;
  if ( (v5 & 0x1FFF0000) != 0x70000 )
    v6 = v5;
  switch ( v6 )
  {
    case 0x6BFu:
    case 6u:
      return -2144206832;
    case 0x6C5u:
      return -2144206819;
    case 0x6EFu:
    case 0x6F4u:
      return -2144206820;
  }
  return v6;
}

```

## disassembly

```asm
0x18000adf0  sub     rsp, 38h
0x18000adf4  test    rcx, rcx
0x18000adf7  jz      loc_18000AE8B
0x18000adfd  mov     rdx, [rcx+70h]
0x18000ae01  test    rdx, rdx
0x18000ae04  jnz     short loc_18000AE39
0x18000ae06  mov     rax, [rcx+8]
0x18000ae0a  xor     r8d, r8d; pReturnValue
0x18000ae0d  mov     r9, [rcx]
0x18000ae10  mov     edx, 0Dh; nProcNum
0x18000ae15  lea     rcx, pProxyInfo; pProxyInfo
0x18000ae1c  mov     [rsp+38h+var_18], rax
0x18000ae21  call    cs:__imp_NdrClientCall3
0x18000ae28  nop     dword ptr [rax+rax+00h]
0x18000ae2d  test    eax, eax
0x18000ae2f  jnz     short loc_18000AE9A
0x18000ae31  xor     eax, eax
0x18000ae33  add     rsp, 38h
0x18000ae37  retn
0x18000ae39  mov     rax, cs:g_pBfeDirectDispatchTable
0x18000ae40  xor     ecx, ecx
0x18000ae42  mov     rax, [rax+58h]
0x18000ae46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae4b  test    eax, eax
0x18000ae4d  jz      short loc_18000AE31
0x18000ae4f  lea     rdx, aBferpctransact; "BfeRpcTransactionCommit"
0x18000ae56  mov     r8d, eax
0x18000ae59  call    WfpReportSysErrorAsWinError
0x18000ae5e  mov     rcx, rax
0x18000ae61  test    rax, rax
0x18000ae64  jz      short loc_18000AE31
0x18000ae66  mov     eax, ecx
0x18000ae68  movzx   edx, cx
0x18000ae6b  and     eax, 1FFF0000h
0x18000ae70  cmp     eax, 70000h
0x18000ae75  cmovnz  edx, ecx
0x18000ae78  cmp     edx, 6BFh
0x18000ae7e  jnz     short loc_18000AEA3
0x18000ae80  mov     eax, 80320010h
0x18000ae85  add     rsp, 38h
0x18000ae89  retn
0x18000ae8b  mov     r8d, 8032001Ch
0x18000ae91  lea     rdx, aFwpmtransactio_4; "FwpmTransactionCommit0"
0x18000ae98  jmp     short loc_18000AE59
0x18000ae9a  lea     rdx, aFwppproxytrans; "FwppProxyTransactionCommit"
0x18000aea1  jmp     short loc_18000AE56
0x18000aea3  mov     eax, edx
0x18000aea5  sub     eax, 6
0x18000aea8  jz      short loc_18000AE80
0x18000aeaa  sub     eax, 6BFh
0x18000aeaf  jz      short loc_18000AECC
0x18000aeb1  sub     eax, 2Ah ; '*'
0x18000aeb4  jz      short loc_18000AEC2
0x18000aeb6  cmp     eax, 5
0x18000aeb9  jz      short loc_18000AEC2
0x18000aebb  mov     eax, edx
0x18000aebd  jmp     loc_18000AE33
0x18000aec2  mov     eax, 8032001Ch
0x18000aec7  jmp     loc_18000AE33
0x18000aecc  mov     eax, 8032001Dh
0x18000aed1  jmp     loc_18000AE33
```
