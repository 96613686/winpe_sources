# ATL::CRowset<ATL::CDynamicAccessor>::Close(void)

- ea: `0x180008b98`
- end: `0x180008c97`
- name: `?Close@?$CRowset@VCDynamicAccessor@ATL@@@ATL@@QEAAXXZ`
- size: `255`
- prototype: `void __fastcall(struct IUnknown **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180007b0c`
- `0x180008b10`

## callees

- `0x180008b98`
- `0x180008db4`
- `0x18000a330`
- `0x18000c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180008beb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008bf9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008beb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008bf9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008c0a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008c0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bdd`

## pseudocode

```c
void __fastcall ATL::CRowset<ATL::CDynamicAccessor>::Close(struct IUnknown **a1)
{
  ATL::CDynamicAccessor *v2; // rcx
  struct IUnknown *v3; // rdi
  struct IUnknown *v4; // rcx
  struct IUnknown *v5; // rcx

  v2 = (ATL::CDynamicAccessor *)a1[4];
  if ( v2 )
  {
    if ( *a1 )
      ATL::CDynamicAccessor::ReleaseAccessors(v2, *a1);
    v3 = a1[4];
    if ( v3 )
    {
      CoTaskMemFree(v3[5].lpVtbl);
      v3[5].lpVtbl = 0;
      CoTaskMemFree(v3[6].lpVtbl);
      v3[6].lpVtbl = 0;
      operator delete[](v3[2].lpVtbl);
      v3[2].lpVtbl = 0;
      operator delete[](v3[4].lpVtbl);
      v3[4].lpVtbl = 0;
      v3[3].lpVtbl = 0;
      operator delete(v3);
    }
    a1[4] = 0;
  }
  if ( *a1 )
  {
    ATL::CDynamicAccessor::FreeRecordMemory((ATL::CDynamicAccessor *)a1[2], (struct IRowset *)*a1);
    if ( a1[3] )
    {
      ((void (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))(*a1)->lpVtbl[2].QueryInterface)(
        *a1,
        1,
        a1 + 3);
      a1[3] = 0;
    }
    v4 = *a1;
    if ( *a1 )
    {
      *a1 = 0;
      ((void (__fastcall *)(struct IUnknown *))v4->lpVtbl->Release)(v4);
    }
    v5 = a1[1];
    if ( v5 )
    {
      a1[1] = 0;
      ((void (__fastcall *)(struct IUnknown *))v5->lpVtbl->Release)(v5);
    }
  }
}

```

## disassembly

```asm
0x180008b98  mov     [rsp+arg_0], rbx
0x180008b9d  mov     [rsp+arg_8], rsi
0x180008ba2  push    rdi
0x180008ba3  sub     rsp, 40h
0x180008ba7  mov     rbx, rcx
0x180008baa  mov     rcx, [rcx+20h]; this
0x180008bae  xor     esi, esi
0x180008bb0  test    rcx, rcx
0x180008bb3  jz      short loc_180008C14
0x180008bb5  mov     rdx, [rbx]; struct IUnknown *
0x180008bb8  test    rdx, rdx
0x180008bbb  jz      short loc_180008BC2
0x180008bbd  call    ?ReleaseAccessors@CDynamicAccessor@ATL@@QEAAJPEAUIUnknown@@@Z; ATL::CDynamicAccessor::ReleaseAccessors(IUnknown *)
0x180008bc2  mov     rdi, [rbx+20h]
0x180008bc6  test    rdi, rdi
0x180008bc9  jz      short loc_180008C10
0x180008bcb  mov     rcx, [rdi+28h]; pv
0x180008bcf  call    cs:__imp_CoTaskMemFree
0x180008bd5  mov     [rdi+28h], rsi
0x180008bd9  mov     rcx, [rdi+30h]; pv
0x180008bdd  call    cs:__imp_CoTaskMemFree
0x180008be3  mov     [rdi+30h], rsi
0x180008be7  mov     rcx, [rdi+10h]
0x180008beb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008bf1  mov     [rdi+10h], rsi
0x180008bf5  mov     rcx, [rdi+20h]
0x180008bf9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008bff  mov     [rdi+20h], rsi
0x180008c03  mov     [rdi+18h], rsi
0x180008c07  mov     rcx, rdi
0x180008c0a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008c10  mov     [rbx+20h], rsi
0x180008c14  mov     rdx, [rbx]; struct IRowset *
0x180008c17  test    rdx, rdx
0x180008c1a  jz      short loc_180008C87
0x180008c1c  mov     rcx, [rbx+10h]; this
0x180008c20  call    ?FreeRecordMemory@CDynamicAccessor@ATL@@QEAAXPEAUIRowset@@@Z; ATL::CDynamicAccessor::FreeRecordMemory(IRowset *)
0x180008c25  nop
0x180008c26  lea     rdi, [rbx+18h]
0x180008c2a  cmp     [rdi], rsi
0x180008c2d  jz      short loc_180008C55
0x180008c2f  mov     rcx, [rbx]
0x180008c32  mov     rax, [rcx]
0x180008c35  mov     [rsp+48h+var_20], rsi
0x180008c3a  mov     [rsp+48h+var_28], rsi
0x180008c3f  xor     r9d, r9d
0x180008c42  mov     r8, rdi
0x180008c45  lea     edx, [r9+1]
0x180008c49  mov     rax, [rax+30h]
0x180008c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c52  mov     [rdi], rsi
0x180008c55  mov     rcx, [rbx]
0x180008c58  test    rcx, rcx
0x180008c5b  jz      short loc_180008C6D
0x180008c5d  mov     [rbx], rsi
0x180008c60  mov     rax, [rcx]
0x180008c63  mov     rax, [rax+10h]
0x180008c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c6c  nop
0x180008c6d  mov     rcx, [rbx+8]
0x180008c71  test    rcx, rcx
0x180008c74  jz      short loc_180008C87
0x180008c76  mov     [rbx+8], rsi
0x180008c7a  mov     rax, [rcx]
0x180008c7d  mov     rax, [rax+10h]
0x180008c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c86  nop
0x180008c87  mov     rbx, [rsp+48h+arg_0]
0x180008c8c  mov     rsi, [rsp+48h+arg_8]
0x180008c91  add     rsp, 40h
0x180008c95  pop     rdi
0x180008c96  retn
```
