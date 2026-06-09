# GenerateNameWithGUID(ushort const *,STRU *)

- ea: `0x180024650`
- end: `0x180024737`
- name: `?GenerateNameWithGUID@@YAKPEBGPEAVSTRU@@@Z`
- size: `231`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct STRU *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800026d0`
- `0x18000f600`
- `0x180024650`
- `0x18002e560`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180024710`
- `RPCRT4!RpcStringFreeW` at `0x180024710`
- `RPCRT4!UuidToStringW` at `0x1800246b3`
- `RPCRT4!UuidToStringW` at `0x1800246b3`
- `RPCRT4!UuidCreate` at `0x180024692`
- `RPCRT4!UuidCreate` at `0x180024692`

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
0x180024650  mov     [rsp+arg_10], rbx
0x180024655  push    rdi
0x180024656  sub     rsp, 40h
0x18002465a  mov     rax, cs:__security_cookie
0x180024661  xor     rax, rsp
0x180024664  mov     [rsp+48h+var_10], rax
0x180024669  mov     [rsp+48h+StringUuid], 0
0x180024672  xorps   xmm0, xmm0
0x180024675  mov     rdi, rdx
0x180024678  mov     rbx, rcx
0x18002467b  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180024680  test    rdx, rdx
0x180024683  jnz     short loc_18002468D
0x180024685  lea     eax, [rdx+57h]
0x180024688  jmp     loc_18002471E
0x18002468d  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180024692  call    cs:__imp_UuidCreate
0x180024699  nop     dword ptr [rax+rax+00h]
0x18002469e  test    eax, eax
0x1800246a0  jz      short loc_1800246A9
0x1800246a2  mov     edi, 3EBh
0x1800246a7  jmp     short loc_180024703
0x1800246a9  lea     rdx, [rsp+48h+StringUuid]; StringUuid
0x1800246ae  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800246b3  call    cs:__imp_UuidToStringW
0x1800246ba  nop     dword ptr [rax+rax+00h]
0x1800246bf  test    eax, eax
0x1800246c1  jnz     short loc_1800246A2
0x1800246c3  test    rbx, rbx
0x1800246c6  jz      short loc_1800246DE
0x1800246c8  mov     rdx, rbx; unsigned __int16 *
0x1800246cb  mov     rcx, rdi; this
0x1800246ce  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800246d3  test    eax, eax
0x1800246d5  jns     short loc_1800246EA
0x1800246d7  mov     edi, 0Eh
0x1800246dc  jmp     short loc_180024703
0x1800246de  mov     rdx, [rdi+20h]
0x1800246e2  xor     eax, eax
0x1800246e4  mov     [rdx], ax
0x1800246e7  mov     [rdi+30h], eax
0x1800246ea  mov     rdx, [rsp+48h+StringUuid]; unsigned __int16 *
0x1800246ef  mov     rcx, rdi; this
0x1800246f2  xor     ebx, ebx
0x1800246f4  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800246f9  lea     edi, [rbx+0Eh]
0x1800246fc  test    eax, eax
0x1800246fe  cmovs   ebx, edi
0x180024701  mov     edi, ebx
0x180024703  cmp     [rsp+48h+StringUuid], 0
0x180024709  jz      short loc_18002471C
0x18002470b  lea     rcx, [rsp+48h+StringUuid]; String
0x180024710  call    cs:__imp_RpcStringFreeW
0x180024717  nop     dword ptr [rax+rax+00h]
0x18002471c  mov     eax, edi
0x18002471e  mov     rcx, [rsp+48h+var_10]
0x180024723  xor     rcx, rsp; StackCookie
0x180024726  call    __security_check_cookie
0x18002472b  mov     rbx, [rsp+48h+arg_10]
0x180024730  add     rsp, 40h
0x180024734  pop     rdi
0x180024735  retn
```
