# wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>::~unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>(void)

- ea: `0x18001afc8`
- end: `0x18001b049`
- name: `??1?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@QEAA@XZ`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020040`
- `0x180020a54`
- `0x18002f619`
- `0x18002f661`

## callees

- `0x18001afc8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001aff0`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001aff0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b03c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b03c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>::~unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>(
        void **a1)
{
  _BYTE *v1; // rbx
  __int64 v2; // rax
  _BYTE *i; // rcx
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  *a1 = 0;
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

```

## disassembly

```asm
0x18001afc8  push    rbx
0x18001afca  sub     rsp, 20h
0x18001afce  mov     rbx, [rcx]
0x18001afd1  mov     qword ptr [rcx], 0
0x18001afd8  test    rbx, rbx
0x18001afdb  jz      short loc_18001B043
0x18001afdd  mov     [rsp+28h+ppMalloc], 0
0x18001afe6  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18001afeb  mov     ecx, 1; dwMemContext
0x18001aff0  call    cs:__imp_CoGetMalloc
0x18001aff6  test    eax, eax
0x18001aff8  js      short loc_18001B039
0x18001affa  mov     rcx, [rsp+28h+ppMalloc]
0x18001afff  mov     rax, [rcx]
0x18001b002  mov     rdx, rbx
0x18001b005  mov     rax, [rax+30h]
0x18001b009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b00e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b012  jz      short loc_18001B028
0x18001b014  mov     rcx, rbx
0x18001b017  test    rax, rax
0x18001b01a  jz      short loc_18001B028
0x18001b01c  mov     byte ptr [rcx], 0
0x18001b01f  inc     rcx
0x18001b022  sub     rax, 1
0x18001b026  jnz     short loc_18001B01C
0x18001b028  mov     rcx, [rsp+28h+ppMalloc]
0x18001b02d  mov     rax, [rcx]
0x18001b030  mov     rax, [rax+10h]
0x18001b034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b039  mov     rcx, rbx; pv
0x18001b03c  call    cs:__imp_CoTaskMemFree
0x18001b042  nop
0x18001b043  add     rsp, 20h
0x18001b047  pop     rbx
0x18001b048  retn
```
