# CreateGuid

- ea: `0x18003d890`
- end: `0x18003d92a`
- name: `CreateGuid`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003e520`

## callees

- `0x180006fa4`
- `0x18003d890`
- `0x180044880`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18003d8d9`
- `RPCRT4!UuidToStringW` at `0x18003d8d9`
- `RPCRT4!RpcStringFreeW` at `0x18003d8fb`
- `RPCRT4!RpcStringFreeW` at `0x18003d8fb`
- `RPCRT4!UuidCreate` at `0x18003d8c5`
- `RPCRT4!UuidCreate` at `0x18003d8c5`

## pseudocode

```c
__int64 __fastcall CreateGuid(__int64 a1, unsigned __int64 a2)
{
  unsigned __int64 v4; // rbx
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-20h] BYREF

  StringUuid = 0;
  Uuid = 0;
  if ( UuidCreate(&Uuid) || UuidToStringW(&Uuid, &StringUuid) )
    return 1;
  v4 = Wcslcpy(a1, StringUuid, a2);
  RpcStringFreeW(&StringUuid);
  return v4 >= a2 ? 4 : 0;
}

```

## disassembly

```asm
0x18003d890  mov     [rsp+arg_10], rbx
0x18003d895  push    rdi
0x18003d896  sub     rsp, 40h
0x18003d89a  mov     rax, cs:__security_cookie
0x18003d8a1  xor     rax, rsp
0x18003d8a4  mov     [rsp+48h+var_10], rax
0x18003d8a9  mov     rbx, rcx
0x18003d8ac  mov     [rsp+48h+StringUuid], 0
0x18003d8b5  xorps   xmm0, xmm0
0x18003d8b8  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18003d8bd  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18003d8c2  mov     rdi, rdx
0x18003d8c5  call    cs:__imp_UuidCreate
0x18003d8cb  test    eax, eax
0x18003d8cd  jnz     short loc_18003D90D
0x18003d8cf  lea     rdx, [rsp+48h+StringUuid]; StringUuid
0x18003d8d4  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18003d8d9  call    cs:__imp_UuidToStringW
0x18003d8df  test    eax, eax
0x18003d8e1  jnz     short loc_18003D90D
0x18003d8e3  mov     rdx, [rsp+48h+StringUuid]
0x18003d8e8  mov     r8, rdi
0x18003d8eb  mov     rcx, rbx
0x18003d8ee  call    Wcslcpy
0x18003d8f3  lea     rcx, [rsp+48h+StringUuid]; String
0x18003d8f8  mov     rbx, rax
0x18003d8fb  call    cs:__imp_RpcStringFreeW
0x18003d901  cmp     rbx, rdi
0x18003d904  sbb     eax, eax
0x18003d906  not     eax
0x18003d908  and     eax, 4
0x18003d90b  jmp     short loc_18003D912
0x18003d90d  mov     eax, 1
0x18003d912  mov     rcx, [rsp+48h+var_10]
0x18003d917  xor     rcx, rsp; StackCookie
0x18003d91a  call    __security_check_cookie
0x18003d91f  mov     rbx, [rsp+48h+arg_10]
0x18003d924  add     rsp, 40h
0x18003d928  pop     rdi
0x18003d929  retn
```
