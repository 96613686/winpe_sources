# STRING_HANDLE_unbind

- ea: `0x180043d00`
- end: `0x180043d52`
- name: `STRING_HANDLE_unbind`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180043a84`

## callees

- `0x180007c90`
- `0x1800364ec`
- `0x180043d00`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180043d1d`
- `RPCRT4!RpcBindingFree` at `0x180043d1d`

## string_xrefs

- `0x180043d2c`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`

## pseudocode

```c
void __fastcall STRING_HANDLE_unbind(__int64 a1, void *a2)
{
  unsigned int v2; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Binding = a2;
  v2 = RpcBindingFree(&Binding);
  if ( v2 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
      (const char *)v2,
      (unsigned int)Binding);
}

```

## disassembly

```asm
0x180043d00  sub     rsp, 38h
0x180043d04  mov     rax, cs:__security_cookie
0x180043d0b  xor     rax, rsp
0x180043d0e  mov     [rsp+38h+var_10], rax
0x180043d13  lea     rcx, [rsp+38h+Binding]; Binding
0x180043d18  mov     [rsp+38h+Binding], rdx; unsigned int
0x180043d1d  call    cs:__imp_RpcBindingFree
0x180043d23  test    eax, eax
0x180043d25  jz      short loc_180043D40
0x180043d27  mov     rcx, [rsp+38h]; this
0x180043d2c  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x180043d33  mov     r9d, eax; char *
0x180043d36  mov     edx, 3Ch ; '<'; void *
0x180043d3b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180043d40  mov     rcx, [rsp+38h+var_10]
0x180043d45  xor     rcx, rsp; StackCookie
0x180043d48  call    __security_check_cookie
0x180043d4d  add     rsp, 38h
0x180043d51  retn
```
