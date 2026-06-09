# DfsRootFolder::CreateRenameName(_UNICODE_STRING *)

- ea: `0x1400298e0`
- end: `0x14002997d`
- name: `?CreateRenameName@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@@Z`
- size: `157`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002ec0c`

## callees

- `0x1400298e0`
- `0x140058b04`
- `0x14005ce70`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x140029956`
- `RPCRT4!RpcStringFreeW` at `0x140029956`
- `RPCRT4!UuidToStringW` at `0x14002992b`
- `RPCRT4!UuidToStringW` at `0x14002992b`
- `RPCRT4!UuidCreate` at `0x14002990f`
- `RPCRT4!UuidCreate` at `0x14002990f`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::CreateRenameName(DfsRootFolder *this, struct _UNICODE_STRING *a2)
{
  unsigned int UnicodePathString; // ebx
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-20h] BYREF

  StringUuid = 0;
  Uuid = 0;
  UnicodePathString = UuidCreate(&Uuid);
  if ( !UnicodePathString )
  {
    UnicodePathString = UuidToStringW(&Uuid, &StringUuid);
    if ( !UnicodePathString )
    {
      UnicodePathString = DfsCreateUnicodePathString(a2, 0, 0, StringUuid);
      RpcStringFreeW(&StringUuid);
    }
  }
  return UnicodePathString;
}

```

## disassembly

```asm
0x1400298e0  mov     [rsp+arg_0], rbx
0x1400298e5  push    rdi
0x1400298e6  sub     rsp, 40h
0x1400298ea  mov     rax, cs:__security_cookie
0x1400298f1  xor     rax, rsp
0x1400298f4  mov     [rsp+48h+var_10], rax
0x1400298f9  and     [rsp+48h+StringUuid], 0
0x1400298ff  lea     rcx, [rsp+48h+Uuid]; Uuid
0x140029904  xorps   xmm0, xmm0
0x140029907  mov     rdi, rdx
0x14002990a  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x14002990f  call    cs:__imp_UuidCreate
0x140029916  nop     dword ptr [rax+rax+00h]
0x14002991b  mov     ebx, eax
0x14002991d  test    eax, eax
0x14002991f  jnz     short loc_140029962
0x140029921  lea     rdx, [rsp+48h+StringUuid]; StringUuid
0x140029926  lea     rcx, [rsp+48h+Uuid]; Uuid
0x14002992b  call    cs:__imp_UuidToStringW
0x140029932  nop     dword ptr [rax+rax+00h]
0x140029937  mov     ebx, eax
0x140029939  test    eax, eax
0x14002993b  jnz     short loc_140029962
0x14002993d  mov     r9, [rsp+48h+StringUuid]
0x140029942  xor     r8d, r8d
0x140029945  xor     edx, edx
0x140029947  mov     rcx, rdi
0x14002994a  call    DfsCreateUnicodePathString
0x14002994f  lea     rcx, [rsp+48h+StringUuid]; String
0x140029954  mov     ebx, eax
0x140029956  call    cs:__imp_RpcStringFreeW
0x14002995d  nop     dword ptr [rax+rax+00h]
0x140029962  mov     eax, ebx
0x140029964  mov     rcx, [rsp+48h+var_10]
0x140029969  xor     rcx, rsp; StackCookie
0x14002996c  call    __security_check_cookie
0x140029971  mov     rbx, [rsp+48h+arg_0]
0x140029976  add     rsp, 40h
0x14002997a  pop     rdi
0x14002997b  retn
```
