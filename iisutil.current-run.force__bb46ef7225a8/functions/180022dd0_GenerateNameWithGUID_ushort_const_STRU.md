# GenerateNameWithGUID(ushort const *,STRU *)

- ea: `0x180022dd0`
- end: `0x180022ea1`
- name: `?GenerateNameWithGUID@@YAKPEBGPEAVSTRU@@@Z`
- size: `209`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct STRU *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001b60`
- `0x18000e3d0`
- `0x180022dd0`
- `0x18002c4c0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180022e81`
- `RPCRT4!RpcStringFreeW` at `0x180022e81`
- `RPCRT4!UuidToStringW` at `0x180022e2a`
- `RPCRT4!UuidToStringW` at `0x180022e2a`
- `RPCRT4!UuidCreate` at `0x180022e0f`
- `RPCRT4!UuidCreate` at `0x180022e0f`

## pseudocode

```c
__int64 __fastcall GenerateNameWithGUID(const unsigned __int16 *a1, struct STRU *this)
{
  unsigned int v5; // edi
  int v6; // ebx
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-20h] BYREF

  StringUuid = 0;
  Uuid = 0;
  if ( !this )
    return 87;
  if ( !UuidCreate(&Uuid) && !UuidToStringW(&Uuid, &StringUuid) )
  {
    if ( a1 )
    {
      if ( STRU::Copy(this, a1) < 0 )
      {
        v5 = 14;
        goto LABEL_13;
      }
    }
    else
    {
      **((_WORD **)this + 4) = 0;
      *((_DWORD *)this + 12) = 0;
    }
    v6 = 0;
    if ( STRU::Append(this, StringUuid) < 0 )
      v6 = 14;
    v5 = v6;
    goto LABEL_13;
  }
  v5 = 1003;
LABEL_13:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return v5;
}

```

## disassembly

```asm
0x180022dd0  mov     [rsp+arg_10], rbx
0x180022dd5  push    rdi
0x180022dd6  sub     rsp, 40h
0x180022dda  mov     rax, cs:__security_cookie
0x180022de1  xor     rax, rsp
0x180022de4  mov     [rsp+48h+var_10], rax
0x180022de9  mov     [rsp+48h+StringUuid], 0
0x180022df2  xorps   xmm0, xmm0
0x180022df5  mov     rdi, rdx
0x180022df8  mov     rbx, rcx
0x180022dfb  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180022e00  test    rdx, rdx
0x180022e03  jnz     short loc_180022E0A
0x180022e05  lea     eax, [rdx+57h]
0x180022e08  jmp     short loc_180022E89
0x180022e0a  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180022e0f  call    cs:__imp_UuidCreate
0x180022e15  test    eax, eax
0x180022e17  jz      short loc_180022E20
0x180022e19  mov     edi, 3EBh
0x180022e1e  jmp     short loc_180022E74
0x180022e20  lea     rdx, [rsp+48h+StringUuid]; StringUuid
0x180022e25  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180022e2a  call    cs:__imp_UuidToStringW
0x180022e30  test    eax, eax
0x180022e32  jnz     short loc_180022E19
0x180022e34  test    rbx, rbx
0x180022e37  jz      short loc_180022E4F
0x180022e39  mov     rdx, rbx; unsigned __int16 *
0x180022e3c  mov     rcx, rdi; this
0x180022e3f  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180022e44  test    eax, eax
0x180022e46  jns     short loc_180022E5B
0x180022e48  mov     edi, 0Eh
0x180022e4d  jmp     short loc_180022E74
0x180022e4f  mov     rdx, [rdi+20h]
0x180022e53  xor     eax, eax
0x180022e55  mov     [rdx], ax
0x180022e58  mov     [rdi+30h], eax
0x180022e5b  mov     rdx, [rsp+48h+StringUuid]; unsigned __int16 *
0x180022e60  mov     rcx, rdi; this
0x180022e63  xor     ebx, ebx
0x180022e65  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180022e6a  lea     edi, [rbx+0Eh]
0x180022e6d  test    eax, eax
0x180022e6f  cmovs   ebx, edi
0x180022e72  mov     edi, ebx
0x180022e74  cmp     [rsp+48h+StringUuid], 0
0x180022e7a  jz      short loc_180022E87
0x180022e7c  lea     rcx, [rsp+48h+StringUuid]; String
0x180022e81  call    cs:__imp_RpcStringFreeW
0x180022e87  mov     eax, edi
0x180022e89  mov     rcx, [rsp+48h+var_10]
0x180022e8e  xor     rcx, rsp; StackCookie
0x180022e91  call    __security_check_cookie
0x180022e96  mov     rbx, [rsp+48h+arg_10]
0x180022e9b  add     rsp, 40h
0x180022e9f  pop     rdi
0x180022ea0  retn
```
