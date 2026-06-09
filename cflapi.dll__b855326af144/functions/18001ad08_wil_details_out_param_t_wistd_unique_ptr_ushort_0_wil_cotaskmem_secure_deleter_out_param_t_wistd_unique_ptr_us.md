# wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>>(void)

- ea: `0x18001ad08`
- end: `0x18001ad92`
- name: `??1?$out_param_t@V?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020a54`
- `0x18002f673`

## callees

- `0x18001ad08`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001ad39`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001ad39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>(
        __int64 a1)
{
  _BYTE *v1; // rbx
  __int64 v2; // rax
  _BYTE *i; // rcx
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(_BYTE ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
    {
      ppMalloc = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v2 = ((__int64 (__fastcall *)(LPMALLOC, _BYTE *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v1);
        if ( v2 != -1 )
        {
          for ( i = v1; v2; --v2 )
            *i++ = 0;
        }
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      CoTaskMemFree(v1);
    }
  }
}

```

## disassembly

```asm
0x18001ad08  push    rbx
0x18001ad0a  sub     rsp, 20h
0x18001ad0e  cmp     byte ptr [rcx+10h], 0
0x18001ad12  jz      short loc_18001AD8C
0x18001ad14  mov     rdx, [rcx+8]
0x18001ad18  mov     rax, [rcx]
0x18001ad1b  mov     rbx, [rax]
0x18001ad1e  mov     [rax], rdx
0x18001ad21  test    rbx, rbx
0x18001ad24  jz      short loc_18001AD8C
0x18001ad26  mov     [rsp+28h+ppMalloc], 0
0x18001ad2f  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18001ad34  mov     ecx, 1; dwMemContext
0x18001ad39  call    cs:__imp_CoGetMalloc
0x18001ad3f  test    eax, eax
0x18001ad41  js      short loc_18001AD82
0x18001ad43  mov     rcx, [rsp+28h+ppMalloc]
0x18001ad48  mov     rax, [rcx]
0x18001ad4b  mov     rdx, rbx
0x18001ad4e  mov     rax, [rax+30h]
0x18001ad52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad57  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ad5b  jz      short loc_18001AD71
0x18001ad5d  mov     rcx, rbx
0x18001ad60  test    rax, rax
0x18001ad63  jz      short loc_18001AD71
0x18001ad65  mov     byte ptr [rcx], 0
0x18001ad68  inc     rcx
0x18001ad6b  sub     rax, 1
0x18001ad6f  jnz     short loc_18001AD65
0x18001ad71  mov     rcx, [rsp+28h+ppMalloc]
0x18001ad76  mov     rax, [rcx]
0x18001ad79  mov     rax, [rax+10h]
0x18001ad7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad82  mov     rcx, rbx; pv
0x18001ad85  call    cs:__imp_CoTaskMemFree
0x18001ad8b  nop
0x18001ad8c  add     rsp, 20h
0x18001ad90  pop     rbx
0x18001ad91  retn
```
