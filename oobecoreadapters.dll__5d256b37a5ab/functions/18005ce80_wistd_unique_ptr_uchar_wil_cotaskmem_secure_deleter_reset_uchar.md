# wistd::unique_ptr<uchar,wil::cotaskmem_secure_deleter>::reset(uchar *)

- ea: `0x18005ce80`
- end: `0x18005cefd`
- name: `?reset@?$unique_ptr@EUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAE@Z`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b870`
- `0x18005b894`
- `0x18005bd1c`

## callees

- `0x18005ce80`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18005cea4`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18005cea4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cef0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cef0`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>::reset(void **a1, void *a2)
{
  _BYTE *v2; // rbx
  __int64 v3; // rax
  _BYTE *i; // rcx
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(LPMALLOC, _BYTE *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v2);
      if ( v3 != -1 )
      {
        for ( i = v2; v3; --v3 )
          *i++ = 0;
      }
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    CoTaskMemFree(v2);
  }
}

```

## disassembly

```asm
0x18005ce80  push    rbx
0x18005ce82  sub     rsp, 20h
0x18005ce86  mov     rbx, [rcx]
0x18005ce89  mov     [rcx], rdx
0x18005ce8c  test    rbx, rbx
0x18005ce8f  jz      short loc_18005CEF7
0x18005ce91  mov     [rsp+28h+ppMalloc], 0
0x18005ce9a  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18005ce9f  mov     ecx, 1; dwMemContext
0x18005cea4  call    cs:__imp_CoGetMalloc
0x18005ceaa  test    eax, eax
0x18005ceac  js      short loc_18005CEED
0x18005ceae  mov     rcx, [rsp+28h+ppMalloc]
0x18005ceb3  mov     rax, [rcx]
0x18005ceb6  mov     rdx, rbx
0x18005ceb9  mov     rax, [rax+30h]
0x18005cebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cec2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005cec6  jz      short loc_18005CEDC
0x18005cec8  mov     rcx, rbx
0x18005cecb  test    rax, rax
0x18005cece  jz      short loc_18005CEDC
0x18005ced0  mov     byte ptr [rcx], 0
0x18005ced3  inc     rcx
0x18005ced6  sub     rax, 1
0x18005ceda  jnz     short loc_18005CED0
0x18005cedc  mov     rcx, [rsp+28h+ppMalloc]
0x18005cee1  mov     rax, [rcx]
0x18005cee4  mov     rax, [rax+10h]
0x18005cee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ceed  mov     rcx, rbx; pv
0x18005cef0  call    cs:__imp_CoTaskMemFree
0x18005cef6  nop
0x18005cef7  add     rsp, 20h
0x18005cefb  pop     rbx
0x18005cefc  retn
```
