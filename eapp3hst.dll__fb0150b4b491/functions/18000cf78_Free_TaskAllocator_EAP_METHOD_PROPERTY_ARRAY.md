# Free<TaskAllocator>(_EAP_METHOD_PROPERTY_ARRAY &)

- ea: `0x18000cf78`
- end: `0x18000cfd7`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z`
- size: `95`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cbc4`
- `0x18000d130`
- `0x18000db80`
- `0x18001f170`
- `0x180030851`

## callees

- `0x18000cf78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Free<TaskAllocator>(__int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rax
  void *v4; // rcx

  if ( *(_DWORD *)a1 && *(_QWORD *)(a1 + 8) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)a1; i = (unsigned int)(i + 1) )
    {
      v3 = *(_QWORD *)(a1 + 8);
      if ( *(_DWORD *)(v3 + 24 * i + 4) == 2 )
      {
        v4 = *(void **)(v3 + 24 * i + 16);
        if ( v4 )
          CoTaskMemFree(v4);
      }
    }
    CoTaskMemFree(*(LPVOID *)(a1 + 8));
    *(_OWORD *)a1 = 0;
  }
}

```

## disassembly

```asm
0x18000cf78  mov     [rsp+arg_0], rbx
0x18000cf7d  push    rdi
0x18000cf7e  sub     rsp, 20h
0x18000cf82  cmp     dword ptr [rcx], 0
0x18000cf85  mov     rbx, rcx
0x18000cf88  jz      short loc_18000CFCC
0x18000cf8a  cmp     qword ptr [rcx+8], 0
0x18000cf8f  jz      short loc_18000CFCC
0x18000cf91  xor     edi, edi
0x18000cf93  cmp     [rcx], edi
0x18000cf95  jbe     short loc_18000CFBC
0x18000cf97  mov     rax, [rbx+8]
0x18000cf9b  lea     rcx, [rdi+rdi*2]
0x18000cf9f  cmp     dword ptr [rax+rcx*8+4], 2
0x18000cfa4  jnz     short loc_18000CFB6
0x18000cfa6  mov     rcx, [rax+rcx*8+10h]; pv
0x18000cfab  test    rcx, rcx
0x18000cfae  jz      short loc_18000CFB6
0x18000cfb0  call    cs:__imp_CoTaskMemFree
0x18000cfb6  inc     edi
0x18000cfb8  cmp     edi, [rbx]
0x18000cfba  jb      short loc_18000CF97
0x18000cfbc  mov     rcx, [rbx+8]; pv
0x18000cfc0  call    cs:__imp_CoTaskMemFree
0x18000cfc6  xorps   xmm0, xmm0
0x18000cfc9  movups  xmmword ptr [rbx], xmm0
0x18000cfcc  mov     rbx, [rsp+28h+arg_0]
0x18000cfd1  add     rsp, 20h
0x18000cfd5  pop     rdi
0x18000cfd6  retn
```
