# ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::~CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>(void)

- ea: `0x180007b0c`
- end: `0x180007baf`
- name: `??1?$CAccessorRowset@VCDynamicAccessor@ATL@@VCRowset@2@@ATL@@QEAA@XZ`
- size: `163`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180007bb8`
- `0x1800099e4`

## callees

- `0x180007b0c`
- `0x180008b10`
- `0x180008b98`
- `0x18000c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180007b7c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007b8e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007b7c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007b8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b6a`

## pseudocode

```c
void __fastcall ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::~CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::Close(a1);
  ATL::CRowset<ATL::CDynamicAccessor>::Close(a1 + 72);
  v2 = *(_QWORD *)(a1 + 80);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *(_QWORD *)(a1 + 72);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  CoTaskMemFree(*(LPVOID *)(a1 + 40));
  *(_QWORD *)(a1 + 40) = 0;
  CoTaskMemFree(*(LPVOID *)(a1 + 48));
  *(_QWORD *)(a1 + 48) = 0;
  operator delete[](*(void **)(a1 + 16));
  *(_QWORD *)(a1 + 16) = 0;
  operator delete[](*(void **)(a1 + 32));
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x180007b0c  mov     [rsp+arg_0], rbx
0x180007b11  push    rdi
0x180007b12  sub     rsp, 20h
0x180007b16  mov     rbx, rcx
0x180007b19  call    ?Close@?$CAccessorRowset@VCDynamicAccessor@ATL@@VCRowset@2@@ATL@@QEAAXXZ; ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::Close(void)
0x180007b1e  lea     rcx, [rbx+48h]
0x180007b22  call    ?Close@?$CRowset@VCDynamicAccessor@ATL@@@ATL@@QEAAXXZ; ATL::CRowset<ATL::CDynamicAccessor>::Close(void)
0x180007b27  nop
0x180007b28  mov     rcx, [rbx+50h]
0x180007b2c  test    rcx, rcx
0x180007b2f  jz      short loc_180007B3E
0x180007b31  mov     rax, [rcx]
0x180007b34  mov     rax, [rax+10h]
0x180007b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b3d  nop
0x180007b3e  mov     rcx, [rbx+48h]
0x180007b42  test    rcx, rcx
0x180007b45  jz      short loc_180007B54
0x180007b47  mov     rax, [rcx]
0x180007b4a  mov     rax, [rax+10h]
0x180007b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b53  nop
0x180007b54  mov     rcx, [rbx+28h]; pv
0x180007b58  call    cs:__imp_CoTaskMemFree
0x180007b5e  mov     qword ptr [rbx+28h], 0
0x180007b66  mov     rcx, [rbx+30h]; pv
0x180007b6a  call    cs:__imp_CoTaskMemFree
0x180007b70  mov     qword ptr [rbx+30h], 0
0x180007b78  mov     rcx, [rbx+10h]
0x180007b7c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007b82  mov     qword ptr [rbx+10h], 0
0x180007b8a  mov     rcx, [rbx+20h]
0x180007b8e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007b94  mov     qword ptr [rbx+20h], 0
0x180007b9c  mov     qword ptr [rbx+18h], 0
0x180007ba4  mov     rbx, [rsp+28h+arg_0]
0x180007ba9  add     rsp, 20h
0x180007bad  pop     rdi
0x180007bae  retn
```
