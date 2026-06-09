# CheckAccessToSession(ITSSession *,ulong,int)

- ea: `0x18001d320`
- end: `0x18001d3fe`
- name: `?CheckAccessToSession@@YAJPEAUITSSession@@KH@Z`
- size: `222`
- prototype: `__int64 __fastcall(struct ITSSession *, unsigned int, int)`
- caller_count: `13`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000e690`
- `0x180016960`
- `0x180030790`
- `0x18005bc50`
- `0x18005c770`
- `0x18005d9c0`
- `0x18005dbb0`
- `0x18005ddc0`
- `0x18005df00`
- `0x18005e050`
- `0x18005e640`
- `0x18005eae0`
- `0x18005ef70`

## callees

- `0x1800074c0`
- `0x18001d320`
- `0x180097010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001d33e`
- `RPCRT4!RpcImpersonateClient` at `0x18001d33e`
- `RPCRT4!RpcRevertToSelf` at `0x18001d368`
- `RPCRT4!RpcRevertToSelf` at `0x18001d368`

## string_xrefs

- `0x18001d387`: `AccessCheckEx failed: 0x%X`
- `0x18001d3c8`: `Cannot impersonate client: %d`
- `0x18001d39f`: `CheckAccessToSession`

## pseudocode

```c
__int64 __fastcall CheckAccessToSession(struct ITSSession *a1, unsigned int a2, unsigned int a3)
{
  RPC_STATUS v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  RPC_STATUS v9; // eax

  if ( a1 )
  {
    v6 = RpcImpersonateClient(0);
    if ( v6 )
    {
      _DbgPrintMessage(8, "Cannot impersonate client: %d", v6);
      return 2147942405LL;
    }
    else
    {
      v7 = (*(__int64 (__fastcall **)(struct ITSSession *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 144LL))(
             a1,
             a2,
             0,
             a3);
      v8 = v7;
      if ( v7 < 0 )
      {
        _DbgPrintMessage(8, "AccessCheckEx failed: 0x%X", v7);
        v8 = -2147024891;
      }
      v9 = RpcRevertToSelf();
      if ( v9 )
      {
        _DbgPrintMessage(8, "RpcRevertToSelf failed: %d", v9);
        return 2147942405LL;
      }
      else
      {
        return v8;
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pSession", "CheckAccessToSession");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001d320  mov     [rsp+arg_0], rbx
0x18001d325  mov     [rsp+arg_8], rsi
0x18001d32a  push    rdi
0x18001d32b  sub     rsp, 30h
0x18001d32f  mov     edi, r8d
0x18001d332  mov     esi, edx
0x18001d334  mov     rbx, rcx
0x18001d337  test    rcx, rcx
0x18001d33a  jz      short loc_18001D39F
0x18001d33c  xor     ecx, ecx; BindingHandle
0x18001d33e  call    cs:__imp_RpcImpersonateClient
0x18001d344  test    eax, eax
0x18001d346  jnz     short loc_18001D3C5
0x18001d348  mov     rax, [rbx]
0x18001d34b  mov     r9d, edi
0x18001d34e  xor     r8d, r8d
0x18001d351  mov     edx, esi
0x18001d353  mov     rcx, rbx
0x18001d356  mov     rax, [rax+90h]
0x18001d35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d362  mov     ebx, eax
0x18001d364  test    eax, eax
0x18001d366  js      short loc_18001D384
0x18001d368  call    cs:__imp_RpcRevertToSelf
0x18001d36e  test    eax, eax
0x18001d370  jnz     short loc_18001D3E0
0x18001d372  mov     eax, ebx
0x18001d374  mov     rbx, [rsp+38h+arg_0]
0x18001d379  mov     rsi, [rsp+38h+arg_8]
0x18001d37e  add     rsp, 30h
0x18001d382  pop     rdi
0x18001d383  retn
0x18001d384  mov     r8d, eax
0x18001d387  lea     rdx, aAccesscheckexF; "AccessCheckEx failed: 0x%X"
0x18001d38e  mov     ecx, 8; int
0x18001d393  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001d398  mov     ebx, 80070005h
0x18001d39d  jmp     short loc_18001D368
0x18001d39f  lea     r9, aCheckaccesstos_3; "CheckAccessToSession"
0x18001d3a6  mov     ecx, 8; int
0x18001d3ab  lea     r8, aPsession; "pSession"
0x18001d3b2  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18001d3b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001d3be  mov     eax, 80070057h
0x18001d3c3  jmp     short loc_18001D374
0x18001d3c5  mov     r8d, eax
0x18001d3c8  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x18001d3cf  mov     ecx, 8; int
0x18001d3d4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001d3d9  mov     eax, 80070005h
0x18001d3de  jmp     short loc_18001D374
0x18001d3e0  mov     r8d, eax
0x18001d3e3  lea     rdx, aRpcreverttosel_0; "RpcRevertToSelf failed: %d"
0x18001d3ea  mov     ecx, 8; int
0x18001d3ef  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001d3f4  mov     eax, 80070005h
0x18001d3f9  jmp     loc_18001D374
```
