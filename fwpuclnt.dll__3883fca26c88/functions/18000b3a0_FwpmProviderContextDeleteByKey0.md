# FwpmProviderContextDeleteByKey0

- ea: `0x18000b3a0`
- end: `0x18000b493`
- name: `FwpmProviderContextDeleteByKey0`
- size: `243`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const GUID *key)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800034e0`
- `0x18000b3a0`
- `0x18004b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b438`
- `RPCRT4!NdrClientCall3` at `0x18000b438`

## string_xrefs

- `0x18000b40f`: `FwpmProviderContextDeleteByKey0`
- `0x18000b448`: `FwppProxyProviderContextDeleteByKey`
- `0x18000b451`: `BfeRpcProviderContextDeleteByKey`

## pseudocode

```c
DWORD __stdcall FwpmProviderContextDeleteByKey0(HANDLE engineHandle, const GUID *key)
{
  __int64 v3; // rdx
  unsigned int Pointer; // eax
  __int64 v6; // rax
  DWORD v7; // edx
  __int64 v8; // r8
  const char *v9; // rdx

  if ( engineHandle )
  {
    v3 = *((_QWORD *)engineHandle + 14);
    if ( v3 )
    {
      Pointer = (*(__int64 (__fastcall **)(_QWORD, __int64, const GUID *))(g_pBfeDirectDispatchTable + 48))(0, v3, key);
      if ( !Pointer )
        return 0;
      v9 = "BfeRpcProviderContextDeleteByKey";
    }
    else
    {
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x1Cu,
                                0,
                                *(_QWORD *)engineHandle,
                                *((_QWORD *)engineHandle + 1),
                                key).Pointer;
      if ( !Pointer )
        return 0;
      v9 = "FwppProxyProviderContextDeleteByKey";
    }
    v8 = Pointer;
  }
  else
  {
    v8 = 2150760476LL;
    v9 = "FwpmProviderContextDeleteByKey0";
  }
  v6 = WfpReportSysErrorAsWinError(engineHandle, v9, v8);
  if ( !v6 )
    return 0;
  v7 = (unsigned __int16)v6;
  if ( (v6 & 0x1FFF0000) != 0x70000 )
    v7 = v6;
  switch ( v7 )
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
  return v7;
}

```

## disassembly

```asm
0x18000b3a0  sub     rsp, 38h
0x18000b3a4  mov     r8, rdx
0x18000b3a7  test    rcx, rcx
0x18000b3aa  jz      short loc_18000B409
0x18000b3ac  mov     rdx, [rcx+70h]
0x18000b3b0  test    rdx, rdx
0x18000b3b3  jz      short loc_18000B418
0x18000b3b5  mov     rax, cs:g_pBfeDirectDispatchTable
0x18000b3bc  xor     ecx, ecx
0x18000b3be  mov     rax, [rax+30h]
0x18000b3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3c7  test    eax, eax
0x18000b3c9  jnz     loc_18000B451
0x18000b3cf  xor     eax, eax
0x18000b3d1  add     rsp, 38h
0x18000b3d5  retn
0x18000b3d7  call    WfpReportSysErrorAsWinError
0x18000b3dc  mov     rcx, rax
0x18000b3df  test    rax, rax
0x18000b3e2  jz      short loc_18000B3CF
0x18000b3e4  mov     eax, ecx
0x18000b3e6  movzx   edx, cx
0x18000b3e9  and     eax, 1FFF0000h
0x18000b3ee  cmp     eax, 70000h
0x18000b3f3  cmovnz  edx, ecx
0x18000b3f6  cmp     edx, 6BFh
0x18000b3fc  jnz     short loc_18000B460
0x18000b3fe  mov     eax, 80320010h
0x18000b403  add     rsp, 38h
0x18000b407  retn
0x18000b409  mov     r8d, 8032001Ch
0x18000b40f  lea     rdx, aFwpmproviderco_27; "FwpmProviderContextDeleteByKey0"
0x18000b416  jmp     short loc_18000B3D7
0x18000b418  mov     rax, [rcx+8]
0x18000b41c  mov     edx, 1Ch; nProcNum
0x18000b421  mov     r9, [rcx]
0x18000b424  lea     rcx, pProxyInfo; pProxyInfo
0x18000b42b  mov     [rsp+38h+var_10], r8
0x18000b430  xor     r8d, r8d; pReturnValue
0x18000b433  mov     [rsp+38h+var_18], rax
0x18000b438  call    cs:__imp_NdrClientCall3
0x18000b43f  nop     dword ptr [rax+rax+00h]
0x18000b444  test    eax, eax
0x18000b446  jz      short loc_18000B3CF
0x18000b448  lea     rdx, aFwppproxyprovi_12; "FwppProxyProviderContextDeleteByKey"
0x18000b44f  jmp     short loc_18000B458
0x18000b451  lea     rdx, aBferpcprovider_0; "BfeRpcProviderContextDeleteByKey"
0x18000b458  mov     r8d, eax
0x18000b45b  jmp     loc_18000B3D7
0x18000b460  mov     eax, edx
0x18000b462  sub     eax, 6
0x18000b465  jz      short loc_18000B3FE
0x18000b467  sub     eax, 6BFh
0x18000b46c  jz      short loc_18000B489
0x18000b46e  sub     eax, 2Ah ; '*'
0x18000b471  jz      short loc_18000B47F
0x18000b473  cmp     eax, 5
0x18000b476  jz      short loc_18000B47F
0x18000b478  mov     eax, edx
0x18000b47a  jmp     loc_18000B3D1
0x18000b47f  mov     eax, 8032001Ch
0x18000b484  jmp     loc_18000B3D1
0x18000b489  mov     eax, 8032001Dh
0x18000b48e  jmp     loc_18000B3D1
```
