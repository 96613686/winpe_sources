# CCSPNodeImpl::Initialize(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *)

- ea: `0x18000a040`
- end: `0x18000a0bb`
- name: `?Initialize@CCSPNodeImpl@@UEAAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@@Z`
- size: `123`
- prototype: `int(CCSPNodeImpl *__hidden this, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a040`
- `0x18000e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a095`
- `msvcrt!memcpy_s` at `0x18000a095`

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
0x18000a040  mov     [rsp+arg_0], rbx
0x18000a045  mov     [rsp+arg_8], rsi
0x18000a04a  push    rdi
0x18000a04b  sub     rsp, 20h
0x18000a04f  cmp     qword ptr [rcx+10h], 0
0x18000a054  mov     rsi, r9
0x18000a057  mov     rbx, rcx
0x18000a05a  jnz     short loc_18000A0A3
0x18000a05c  cmp     qword ptr [rcx+18h], 0
0x18000a061  jnz     short loc_18000A0A3
0x18000a063  xor     edi, edi
0x18000a065  mov     [rcx+10h], rdx
0x18000a069  test    r8, r8
0x18000a06c  jz      short loc_18000A081
0x18000a06e  mov     [rcx+18h], r8
0x18000a072  mov     rcx, r8
0x18000a075  mov     rax, [r8]
0x18000a078  mov     rax, [rax+8]
0x18000a07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a081  test    rsi, rsi
0x18000a084  jz      short loc_18000A0A8
0x18000a086  mov     edx, 20h ; ' '; DestinationSize
0x18000a08b  lea     rcx, [rbx+20h]; Destination
0x18000a08f  mov     r9d, edx; SourceSize
0x18000a092  mov     r8, rsi; Source
0x18000a095  call    cs:__imp_memcpy_s
0x18000a09c  nop     dword ptr [rax+rax+00h]
0x18000a0a1  jmp     short loc_18000A0A8
0x18000a0a3  mov     edi, 8000FFFFh
0x18000a0a8  mov     rbx, [rsp+28h+arg_0]
0x18000a0ad  mov     eax, edi
0x18000a0af  mov     rsi, [rsp+28h+arg_8]
0x18000a0b4  add     rsp, 20h
0x18000a0b8  pop     rdi
0x18000a0b9  retn
```
