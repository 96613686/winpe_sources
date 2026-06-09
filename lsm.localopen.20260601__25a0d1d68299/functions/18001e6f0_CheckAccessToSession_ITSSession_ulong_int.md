# CheckAccessToSession(ITSSession *,ulong,int)

- ea: `0x18001e6f0`
- end: `0x18001e7df`
- name: `?CheckAccessToSession@@YAJPEAUITSSession@@KH@Z`
- size: `239`
- prototype: `__int64 __fastcall(struct ITSSession *, unsigned int, int)`
- caller_count: `13`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000cfb0`
- `0x180020b00`
- `0x1800327e0`
- `0x18005f690`
- `0x180060190`
- `0x180061450`
- `0x180061650`
- `0x180061860`
- `0x1800619a0`
- `0x180061af0`
- `0x180062120`
- `0x1800625d0`
- `0x180062a60`

## callees

- `0x1800077a0`
- `0x18001e6f0`
- `0x18009c010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001e70e`
- `RPCRT4!RpcImpersonateClient` at `0x18001e70e`
- `RPCRT4!RpcRevertToSelf` at `0x18001e742`
- `RPCRT4!RpcRevertToSelf` at `0x18001e742`

## string_xrefs

- `0x18001e768`: `AccessCheckEx failed: 0x%X`
- `0x18001e780`: `CheckAccessToSession`
- `0x18001e7a9`: `Cannot impersonate client: %d`

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
0x18001e6f0  mov     [rsp+arg_0], rbx
0x18001e6f5  mov     [rsp+arg_8], rsi
0x18001e6fa  push    rdi
0x18001e6fb  sub     rsp, 30h
0x18001e6ff  mov     edi, r8d
0x18001e702  mov     esi, edx
0x18001e704  mov     rbx, rcx
0x18001e707  test    rcx, rcx
0x18001e70a  jz      short loc_18001E780
0x18001e70c  xor     ecx, ecx; BindingHandle
0x18001e70e  call    cs:__imp_RpcImpersonateClient
0x18001e715  nop     dword ptr [rax+rax+00h]
0x18001e71a  test    eax, eax
0x18001e71c  jnz     loc_18001E7A6
0x18001e722  mov     rax, [rbx]
0x18001e725  mov     r9d, edi
0x18001e728  xor     r8d, r8d
0x18001e72b  mov     edx, esi
0x18001e72d  mov     rcx, rbx
0x18001e730  mov     rax, [rax+90h]
0x18001e737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e73c  mov     ebx, eax
0x18001e73e  test    eax, eax
0x18001e740  js      short loc_18001E765
0x18001e742  call    cs:__imp_RpcRevertToSelf
0x18001e749  nop     dword ptr [rax+rax+00h]
0x18001e74e  test    eax, eax
0x18001e750  jnz     short loc_18001E7C1
0x18001e752  mov     eax, ebx
0x18001e754  mov     rbx, [rsp+38h+arg_0]
0x18001e759  mov     rsi, [rsp+38h+arg_8]
0x18001e75e  add     rsp, 30h
0x18001e762  pop     rdi
0x18001e763  retn
0x18001e765  mov     r8d, eax
0x18001e768  lea     rdx, aAccesscheckexF; "AccessCheckEx failed: 0x%X"
0x18001e76f  mov     ecx, 8; int
0x18001e774  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001e779  mov     ebx, 80070005h
0x18001e77e  jmp     short loc_18001E742
0x18001e780  lea     r9, aCheckaccesstos_3; "CheckAccessToSession"
0x18001e787  mov     ecx, 8; int
0x18001e78c  lea     r8, aPsession; "pSession"
0x18001e793  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18001e79a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001e79f  mov     eax, 80070057h
0x18001e7a4  jmp     short loc_18001E754
0x18001e7a6  mov     r8d, eax
0x18001e7a9  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x18001e7b0  mov     ecx, 8; int
0x18001e7b5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001e7ba  mov     eax, 80070005h
0x18001e7bf  jmp     short loc_18001E754
0x18001e7c1  mov     r8d, eax
0x18001e7c4  lea     rdx, aRpcreverttosel_0; "RpcRevertToSelf failed: %d"
0x18001e7cb  mov     ecx, 8; int
0x18001e7d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001e7d5  mov     eax, 80070005h
0x18001e7da  jmp     loc_18001E754
```
