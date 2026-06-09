# CAutoImpersonate::Impersonate(void)

- ea: `0x180030a50`
- end: `0x180030aac`
- name: `?Impersonate@CAutoImpersonate@@QEAAJXZ`
- size: `92`
- prototype: `HRESULT __fastcall(CAutoImpersonate *this)`
- caller_count: `13`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b8c0`
- `0x18001bb00`
- `0x180021990`
- `0x18002b060`
- `0x18002b1b0`
- `0x18002b2d0`
- `0x18002d0c0`
- `0x18002d69c`
- `0x18002dcb4`
- `0x180031674`
- `0x1800316e8`
- `0x1800317f4`
- `0x1800328a0`

## callees

- `0x180030a50`
- `0x180030ab4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180030a81`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180030a81`

## pseudocode

```c
HRESULT __fastcall CAutoImpersonate::Impersonate(CAutoImpersonate *this)
{
  HRESULT result; // eax
  int v3; // edx
  int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  result = CAutoImpersonate::IsImpersonating(this, &v4);
  if ( result >= 0 )
  {
    v3 = v4;
    *((_DWORD *)this + 2) = v4;
    *((_DWORD *)this + 3) = 1;
    if ( v3 )
      return 1;
    result = CoImpersonateClient();
    if ( result >= 0 )
    {
      *(_DWORD *)this = 1;
      return result;
    }
    if ( result == -2147417833 || result == -2147467262 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180030a50  push    rbx
0x180030a52  sub     rsp, 20h
0x180030a56  lea     rdx, [rsp+28h+arg_8]; int *
0x180030a5b  mov     [rsp+28h+arg_8], 0
0x180030a63  mov     rbx, rcx
0x180030a66  call    ?IsImpersonating@CAutoImpersonate@@QEAAJPEAH@Z; CAutoImpersonate::IsImpersonating(int *)
0x180030a6b  test    eax, eax
0x180030a6d  js      short loc_180030AA6
0x180030a6f  mov     edx, [rsp+28h+arg_8]
0x180030a73  mov     [rbx+8], edx
0x180030a76  mov     dword ptr [rbx+0Ch], 1
0x180030a7d  test    edx, edx
0x180030a7f  jnz     short loc_180030AA1
0x180030a81  call    cs:__imp_CoImpersonateClient
0x180030a87  test    eax, eax
0x180030a89  js      short loc_180030A93
0x180030a8b  mov     dword ptr [rbx], 1
0x180030a91  jmp     short loc_180030AA6
0x180030a93  cmp     eax, 80010117h
0x180030a98  jz      short loc_180030AA1
0x180030a9a  cmp     eax, 80004002h
0x180030a9f  jnz     short loc_180030AA6
0x180030aa1  mov     eax, 1
0x180030aa6  add     rsp, 20h
0x180030aaa  pop     rbx
0x180030aab  retn
```
