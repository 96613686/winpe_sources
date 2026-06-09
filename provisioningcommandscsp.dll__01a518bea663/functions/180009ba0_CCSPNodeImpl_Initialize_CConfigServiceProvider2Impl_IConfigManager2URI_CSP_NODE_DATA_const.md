# CCSPNodeImpl::Initialize(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *)

- ea: `0x180009ba0`
- end: `0x180009c14`
- name: `?Initialize@CCSPNodeImpl@@UEAAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(CCSPNodeImpl *this, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009ba0`
- `0x18000e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009bf5`
- `msvcrt!memcpy_s` at `0x180009bf5`

## pseudocode

```c
__int64 __fastcall CCSPNodeImpl::Initialize(
        CCSPNodeImpl *this,
        struct CConfigServiceProvider2Impl *a2,
        struct IConfigManager2URI *a3,
        const struct CSP_NODE_DATA *a4)
{
  unsigned int v6; // edi

  if ( *((_OWORD *)this + 1) == 0 )
  {
    v6 = 0;
    *((_QWORD *)this + 2) = a2;
    if ( a3 )
    {
      *((_QWORD *)this + 3) = a3;
      (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)a3 + 8LL))(a3);
    }
    if ( a4 )
      memcpy_s((char *)this + 32, 0x20u, a4, 0x20u);
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v6;
}

```

## disassembly

```asm
0x180009ba0  mov     [rsp+arg_0], rbx
0x180009ba5  mov     [rsp+arg_8], rsi
0x180009baa  push    rdi
0x180009bab  sub     rsp, 20h
0x180009baf  cmp     qword ptr [rcx+10h], 0
0x180009bb4  mov     rsi, r9
0x180009bb7  mov     rbx, rcx
0x180009bba  jnz     short loc_180009BFD
0x180009bbc  cmp     qword ptr [rcx+18h], 0
0x180009bc1  jnz     short loc_180009BFD
0x180009bc3  xor     edi, edi
0x180009bc5  mov     [rcx+10h], rdx
0x180009bc9  test    r8, r8
0x180009bcc  jz      short loc_180009BE1
0x180009bce  mov     [rcx+18h], r8
0x180009bd2  mov     rcx, r8
0x180009bd5  mov     rax, [r8]
0x180009bd8  mov     rax, [rax+8]
0x180009bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009be1  test    rsi, rsi
0x180009be4  jz      short loc_180009C02
0x180009be6  mov     edx, 20h ; ' '; DestinationSize
0x180009beb  lea     rcx, [rbx+20h]; Destination
0x180009bef  mov     r9d, edx; SourceSize
0x180009bf2  mov     r8, rsi; Source
0x180009bf5  call    cs:__imp_memcpy_s
0x180009bfb  jmp     short loc_180009C02
0x180009bfd  mov     edi, 8000FFFFh
0x180009c02  mov     rbx, [rsp+28h+arg_0]
0x180009c07  mov     eax, edi
0x180009c09  mov     rsi, [rsp+28h+arg_8]
0x180009c0e  add     rsp, 20h
0x180009c12  pop     rdi
0x180009c13  retn
```
