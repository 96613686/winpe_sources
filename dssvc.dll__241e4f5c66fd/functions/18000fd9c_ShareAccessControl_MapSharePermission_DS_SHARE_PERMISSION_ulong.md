# ShareAccessControl::MapSharePermission(_DS_SHARE_PERMISSION,ulong *)

- ea: `0x18000fd9c`
- end: `0x18000fe1a`
- name: `?MapSharePermission@ShareAccessControl@@SAJW4_DS_SHARE_PERMISSION@@PEAK@Z`
- size: `126`
- prototype: `__int64 __fastcall(int, unsigned int *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d3e4`
- `0x1800125c4`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000fd9c`

## string_xrefs

- `0x18000fddd`: `ShareAccessControl::MapSharePermission`

## pseudocode

```c
__int64 __fastcall ShareAccessControl::MapSharePermission(int a1, unsigned int *a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // ecx
  unsigned int v7; // ebx
  DSLogger *v8; // rax

  v6 = 0;
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      v7 = 0x40000000;
    }
    else if ( a1 == 2 )
    {
      v7 = -1073741824;
    }
    else
    {
      v7 = 0;
      v8 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                         0,
                         a2,
                         (unsigned int)(a1 - 1),
                         a4);
      DSLogger::LogError(v8, L"ShareAccessControl::MapSharePermission", 0xF7u, L"Invalid permission %d", a1);
      v6 = -2147024809;
    }
  }
  else
  {
    v7 = 0x80000000;
  }
  *a2 = v7;
  return v6;
}

```

## disassembly

```asm
0x18000fd9c  mov     [rsp+arg_0], rbx
0x18000fda1  mov     [rsp+arg_8], rsi
0x18000fda6  push    rdi
0x18000fda7  sub     rsp, 30h
0x18000fdab  mov     edi, ecx
0x18000fdad  mov     rsi, rdx
0x18000fdb0  xor     ecx, ecx
0x18000fdb2  mov     r8d, edi
0x18000fdb5  test    edi, edi
0x18000fdb7  jz      short loc_18000FE01
0x18000fdb9  sub     r8d, 1
0x18000fdbd  jz      short loc_18000FDFA
0x18000fdbf  cmp     r8d, 1
0x18000fdc3  jz      short loc_18000FDF3
0x18000fdc5  xor     ebx, ebx
0x18000fdc7  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000fdcc  lea     r9, aInvalidPermiss; "Invalid permission %d"
0x18000fdd3  mov     [rsp+38h+var_18], edi
0x18000fdd7  mov     r8d, 0F7h; unsigned int
0x18000fddd  lea     rdx, aShareaccesscon; "ShareAccessControl::MapSharePermission"
0x18000fde4  mov     rcx, rax; this
0x18000fde7  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000fdec  mov     ecx, 80070057h
0x18000fdf1  jmp     short loc_18000FE06
0x18000fdf3  mov     ebx, 0C0000000h
0x18000fdf8  jmp     short loc_18000FE06
0x18000fdfa  mov     ebx, 40000000h
0x18000fdff  jmp     short loc_18000FE06
0x18000fe01  mov     ebx, 80000000h
0x18000fe06  mov     [rsi], ebx
0x18000fe08  mov     eax, ecx
0x18000fe0a  mov     rbx, [rsp+38h+arg_0]
0x18000fe0f  mov     rsi, [rsp+38h+arg_8]
0x18000fe14  add     rsp, 30h
0x18000fe18  pop     rdi
0x18000fe19  retn
```
