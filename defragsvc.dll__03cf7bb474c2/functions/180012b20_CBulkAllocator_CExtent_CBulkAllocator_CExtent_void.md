# CBulkAllocator<_CExtent>::~CBulkAllocator<_CExtent>(void)

- ea: `0x180012b20`
- end: `0x180012bd5`
- name: `??1?$CBulkAllocator@U_CExtent@@@@AEAA@XZ`
- size: `181`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800125a0`

## callees

- `0x180012b20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012bbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012bbe`

## pseudocode

```c
void __fastcall CBulkAllocator<_CExtent>::~CBulkAllocator<_CExtent>(__int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rcx

  if ( *(_QWORD *)(a1 + 8) )
  {
    v2 = 0;
    v3 = 0;
    do
    {
      v4 = *(_QWORD *)(v3 + *(_QWORD *)(a1 + 8));
      if ( v4 )
      {
        CoTaskMemFree(*(LPVOID *)(v4 + 8));
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + v3) + 8LL) = 0;
        CoTaskMemFree(**(LPVOID **)(v3 + *(_QWORD *)(a1 + 8)));
        **(_QWORD **)(v3 + *(_QWORD *)(a1 + 8)) = 0;
        CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(a1 + 8) + v3));
        *(_QWORD *)(v3 + *(_QWORD *)(a1 + 8)) = 0;
      }
      ++v2;
      v3 += 8;
    }
    while ( v2 != 0x10000 );
    CoTaskMemFree(*(LPVOID *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180012b20  mov     [rsp+arg_0], rbx
0x180012b25  mov     [rsp+arg_8], rsi
0x180012b2a  push    rdi
0x180012b2b  sub     rsp, 20h
0x180012b2f  cmp     qword ptr [rcx+8], 0
0x180012b34  mov     rbx, rcx
0x180012b37  jz      short loc_180012B6C
0x180012b39  xor     esi, esi
0x180012b3b  xor     edi, edi
0x180012b3d  mov     rax, [rbx+8]
0x180012b41  mov     rcx, [rdi+rax]
0x180012b45  test    rcx, rcx
0x180012b48  jnz     short loc_180012B7C
0x180012b4a  inc     rsi
0x180012b4d  add     rdi, 8
0x180012b51  cmp     rsi, 10000h
0x180012b58  jnz     short loc_180012B3D
0x180012b5a  mov     rcx, [rbx+8]; pv
0x180012b5e  call    cs:__imp_CoTaskMemFree
0x180012b64  mov     qword ptr [rbx+8], 0
0x180012b6c  mov     rbx, [rsp+28h+arg_0]
0x180012b71  mov     rsi, [rsp+28h+arg_8]
0x180012b76  add     rsp, 20h
0x180012b7a  pop     rdi
0x180012b7b  retn
0x180012b7c  mov     rcx, [rcx+8]; pv
0x180012b80  call    cs:__imp_CoTaskMemFree
0x180012b86  mov     rax, [rbx+8]
0x180012b8a  mov     rcx, [rax+rdi]
0x180012b8e  mov     qword ptr [rcx+8], 0
0x180012b96  mov     rax, [rbx+8]
0x180012b9a  mov     rcx, [rdi+rax]
0x180012b9e  mov     rcx, [rcx]; pv
0x180012ba1  call    cs:__imp_CoTaskMemFree
0x180012ba7  mov     rax, [rbx+8]
0x180012bab  mov     rcx, [rdi+rax]
0x180012baf  mov     qword ptr [rcx], 0
0x180012bb6  mov     rcx, [rbx+8]
0x180012bba  mov     rcx, [rcx+rdi]; pv
0x180012bbe  call    cs:__imp_CoTaskMemFree
0x180012bc4  mov     rax, [rbx+8]
0x180012bc8  mov     qword ptr [rdi+rax], 0
0x180012bd0  jmp     loc_180012B4A
```
