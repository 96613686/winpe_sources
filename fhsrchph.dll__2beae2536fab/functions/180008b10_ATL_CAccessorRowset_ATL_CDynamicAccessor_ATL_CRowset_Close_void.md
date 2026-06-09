# ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::Close(void)

- ea: `0x180008b10`
- end: `0x180008b8f`
- name: `?Close@?$CAccessorRowset@VCDynamicAccessor@ATL@@VCRowset@2@@ATL@@QEAAXXZ`
- size: `127`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180007b0c`
- `0x1800099e4`

## callees

- `0x180008b10`
- `0x180008b98`
- `0x18000a330`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180008b53`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008b65`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008b53`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008b65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b41`

## pseudocode

```c
__int64 __fastcall ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::Close(__int64 a1)
{
  struct IUnknown *v1; // rdx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 result; // rax

  v1 = *(struct IUnknown **)(a1 + 72);
  if ( v1 )
  {
    ATL::CDynamicAccessor::ReleaseAccessors((ATL::CDynamicAccessor *)a1, v1);
    CoTaskMemFree(*(LPVOID *)(a1 + 40));
    v3 = *(void **)(a1 + 48);
    *(_QWORD *)(a1 + 40) = 0;
    CoTaskMemFree(v3);
    v4 = *(void **)(a1 + 16);
    *(_QWORD *)(a1 + 48) = 0;
    operator delete[](v4);
    v5 = *(void **)(a1 + 32);
    *(_QWORD *)(a1 + 16) = 0;
    operator delete[](v5);
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    return ATL::CRowset<ATL::CDynamicAccessor>::Close(a1 + 72);
  }
  return result;
}

```

## disassembly

```asm
0x180008b10  mov     [rsp+arg_0], rbx
0x180008b15  push    rdi
0x180008b16  sub     rsp, 20h
0x180008b1a  mov     rdx, [rcx+48h]; struct IUnknown *
0x180008b1e  mov     rbx, rcx
0x180008b21  test    rdx, rdx
0x180008b24  jz      short loc_180008B84
0x180008b26  call    ?ReleaseAccessors@CDynamicAccessor@ATL@@QEAAJPEAUIUnknown@@@Z; ATL::CDynamicAccessor::ReleaseAccessors(IUnknown *)
0x180008b2b  mov     rcx, [rbx+28h]; pv
0x180008b2f  call    cs:__imp_CoTaskMemFree
0x180008b35  mov     rcx, [rbx+30h]; pv
0x180008b39  mov     qword ptr [rbx+28h], 0
0x180008b41  call    cs:__imp_CoTaskMemFree
0x180008b47  mov     rcx, [rbx+10h]
0x180008b4b  mov     qword ptr [rbx+30h], 0
0x180008b53  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008b59  mov     rcx, [rbx+20h]
0x180008b5d  mov     qword ptr [rbx+10h], 0
0x180008b65  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008b6b  lea     rcx, [rbx+48h]
0x180008b6f  mov     qword ptr [rbx+20h], 0
0x180008b77  mov     qword ptr [rbx+18h], 0
0x180008b7f  call    ?Close@?$CRowset@VCDynamicAccessor@ATL@@@ATL@@QEAAXXZ; ATL::CRowset<ATL::CDynamicAccessor>::Close(void)
0x180008b84  mov     rbx, [rsp+28h+arg_0]
0x180008b89  add     rsp, 20h
0x180008b8d  pop     rdi
0x180008b8e  retn
```
