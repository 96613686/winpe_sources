# CreateUuidString(ushort * *)

- ea: `0x140009738`
- end: `0x140009801`
- name: `?CreateUuidString@@YAJPEAPEAG@Z`
- size: `201`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004aa0`
- `0x14000a6b8`

## callees

- `0x140009738`
- `0x1400109c0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400097a6`
- `OLEAUT32!__imp_SysAllocString` at `0x1400097a6`
- `RPCRT4!RpcStringFreeW` at `0x1400097c6`
- `RPCRT4!RpcStringFreeW` at `0x1400097c6`
- `RPCRT4!UuidCreate` at `0x14000976a`
- `RPCRT4!UuidCreate` at `0x14000976a`
- `RPCRT4!UuidToStringW` at `0x14000978f`
- `RPCRT4!UuidToStringW` at `0x14000978f`

## pseudocode

```c
__int64 __fastcall CreateUuidString(unsigned __int16 **a1)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  unsigned __int16 *v5; // rax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-20h] BYREF

  if ( a1 )
  {
    Uuid = 0;
    v2 = UuidCreate(&Uuid);
    v3 = v2;
    v4 = v2 <= 0;
    if ( v2 || (StringUuid = 0, v2 = UuidToStringW(&Uuid, &StringUuid), v3 = v2, v4 = v2 <= 0, v2) )
    {
      if ( !v4 )
        return (unsigned __int16)v2 | 0x80070000;
    }
    else
    {
      v5 = SysAllocString(StringUuid);
      if ( v5 )
        *a1 = v5;
      else
        v3 = -2147024882;
      RpcStringFreeW(&StringUuid);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x140009738  mov     [rsp+arg_8], rbx
0x14000973d  push    rdi
0x14000973e  sub     rsp, 40h
0x140009742  mov     rax, cs:__security_cookie
0x140009749  xor     rax, rsp
0x14000974c  mov     [rsp+48h+var_10], rax
0x140009751  mov     rdi, rcx
0x140009754  test    rcx, rcx
0x140009757  jz      loc_1400097E1
0x14000975d  xorps   xmm0, xmm0
0x140009760  lea     rcx, [rsp+48h+Uuid]; Uuid
0x140009765  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x14000976a  call    cs:__imp_UuidCreate
0x140009771  nop     dword ptr [rax+rax+00h]
0x140009776  mov     ebx, eax
0x140009778  test    eax, eax
0x14000977a  jnz     short loc_1400097D4
0x14000977c  lea     rdx, [rsp+48h+StringUuid]; StringUuid
0x140009781  mov     [rsp+48h+StringUuid], 0
0x14000978a  lea     rcx, [rsp+48h+Uuid]; Uuid
0x14000978f  call    cs:__imp_UuidToStringW
0x140009796  nop     dword ptr [rax+rax+00h]
0x14000979b  mov     ebx, eax
0x14000979d  test    eax, eax
0x14000979f  jnz     short loc_1400097D4
0x1400097a1  mov     rcx, [rsp+48h+StringUuid]; psz
0x1400097a6  call    cs:__imp_SysAllocString
0x1400097ad  nop     dword ptr [rax+rax+00h]
0x1400097b2  test    rax, rax
0x1400097b5  jz      short loc_1400097BC
0x1400097b7  mov     [rdi], rax
0x1400097ba  jmp     short loc_1400097C1
0x1400097bc  mov     ebx, 8007000Eh
0x1400097c1  lea     rcx, [rsp+48h+StringUuid]; String
0x1400097c6  call    cs:__imp_RpcStringFreeW
0x1400097cd  nop     dword ptr [rax+rax+00h]
0x1400097d2  jmp     short loc_1400097E6
0x1400097d4  jle     short loc_1400097E6
0x1400097d6  movzx   ebx, ax
0x1400097d9  or      ebx, 80070000h
0x1400097df  jmp     short loc_1400097E6
0x1400097e1  mov     ebx, 80070057h
0x1400097e6  mov     eax, ebx
0x1400097e8  mov     rcx, [rsp+48h+var_10]
0x1400097ed  xor     rcx, rsp; StackCookie
0x1400097f0  call    __security_check_cookie
0x1400097f5  mov     rbx, [rsp+48h+arg_8]
0x1400097fa  add     rsp, 40h
0x1400097fe  pop     rdi
0x1400097ff  retn
```
