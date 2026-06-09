# DataStoreComServer::get_ProductLimits(tagIAS_PRODUCT_LIMITS *)

- ea: `0x180007120`
- end: `0x180007149`
- name: `?get_ProductLimits@DataStoreComServer@@UEAAJPEAUtagIAS_PRODUCT_LIMITS@@@Z`
- size: `41`
- prototype: `__int64 __fastcall(DataStoreComServer *__hidden this, struct tagIAS_PRODUCT_LIMITS *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007120`

## import_xrefs

- `iassvcs!IASGetProductLimits` at `0x180007132`
- `iassvcs!IASGetProductLimits` at `0x180007132`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::get_ProductLimits(DataStoreComServer *this, struct tagIAS_PRODUCT_LIMITS *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = IASGetProductLimits(0);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007120  sub     rsp, 28h
0x180007124  test    rdx, rdx
0x180007127  jnz     short loc_180007130
0x180007129  mov     eax, 80004003h
0x18000712e  jmp     short loc_180007144
0x180007130  xor     ecx, ecx
0x180007132  call    cs:__imp_IASGetProductLimits
0x180007138  test    eax, eax
0x18000713a  jle     short loc_180007144
0x18000713c  movzx   eax, ax
0x18000713f  or      eax, 80070000h
0x180007144  add     rsp, 28h
0x180007148  retn
```
