# EdpCleanupLocalOnlyRpcCall

- ea: `0x180003a24`
- end: `0x180003a59`
- name: `EdpCleanupLocalOnlyRpcCall`
- size: `53`
- prototype: ``
- caller_count: `22`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180003dd0`
- `0x180003e90`
- `0x180003fe0`
- `0x1800040c0`
- `0x1800041a0`
- `0x180004290`
- `0x180004380`
- `0x180004470`
- `0x180004540`
- `0x180004630`
- `0x1800047c0`
- `0x180004900`
- `0x180004ad0`
- `0x180004b90`
- `0x180004d30`
- `0x180004e00`
- `0x1800052b0`
- `0x1800053b0`
- `0x180005480`
- `0x180005640`
- `0x1800077c0`
- `0x1800084f0`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180003a4d`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180003a2d`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180003a2d`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180003a3c`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180003a3c`

## pseudocode

```c
RPC_STATUS __fastcall EdpCleanupLocalOnlyRpcCall(__int64 a1)
{
  EfsDllUnloadUserProfile(a1);
  EfsDllFreeUserInfo(a1);
  return RpcRevertToSelf();
}

```

## disassembly

```asm
0x180003a24  push    rbx
0x180003a26  sub     rsp, 20h
0x180003a2a  mov     rbx, rcx
0x180003a2d  call    cs:__imp_EfsDllUnloadUserProfile
0x180003a34  nop     dword ptr [rax+rax+00h]
0x180003a39  mov     rcx, rbx
0x180003a3c  call    cs:__imp_EfsDllFreeUserInfo
0x180003a43  nop     dword ptr [rax+rax+00h]
0x180003a48  add     rsp, 20h
0x180003a4c  pop     rbx
0x180003a4d  jmp     cs:__imp_RpcRevertToSelf
```
