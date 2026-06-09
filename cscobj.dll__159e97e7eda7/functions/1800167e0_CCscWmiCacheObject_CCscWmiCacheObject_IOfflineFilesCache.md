# CCscWmiCacheObject::CCscWmiCacheObject(IOfflineFilesCache *)

- ea: `0x1800167e0`
- end: `0x180016838`
- name: `??0CCscWmiCacheObject@@QEAA@PEAUIOfflineFilesCache@@@Z`
- size: `88`
- prototype: `CCscWmiCacheObject *__fastcall(CCscWmiCacheObject *__hidden this, struct IOfflineFilesCache *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800181d0`
- `0x18002273c`

## callees

- `0x1800167e0`
- `0x18002c010`

## string_xrefs

- `0x1800167f3`: `Win32_OfflineFilesCache`

## pseudocode

```c
CCscWmiCacheObject *__fastcall CCscWmiCacheObject::CCscWmiCacheObject(
        CCscWmiCacheObject *this,
        struct IOfflineFilesCache *a2)
{
  *(_QWORD *)this = &CCscWmiObject::`vftable';
  *((_QWORD *)this + 1) = L"Win32_OfflineFilesCache";
  _InterlockedIncrement(&g_cRefDll);
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &CCscWmiCacheObject::`vftable';
  if ( a2 )
  {
    *((_QWORD *)this + 2) = a2;
    ((void (__fastcall *)(struct IOfflineFilesCache *))a2->lpVtbl->AddRef)(a2);
  }
  return this;
}

```

## disassembly

```asm
0x1800167e0  push    rbx
0x1800167e2  sub     rsp, 20h
0x1800167e6  lea     rax, ??_7CCscWmiObject@@6B@; const CCscWmiObject::`vftable'
0x1800167ed  mov     rbx, rcx
0x1800167f0  mov     [rcx], rax
0x1800167f3  lea     rax, CSCWMI_STR_OFFLINEFILESCACHE; "Win32_OfflineFilesCache"
0x1800167fa  mov     [rcx+8], rax
0x1800167fe  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x180016805  mov     qword ptr [rcx+10h], 0
0x18001680d  lea     rax, ??_7CCscWmiCacheObject@@6B@; const CCscWmiCacheObject::`vftable'
0x180016814  mov     [rcx], rax
0x180016817  test    rdx, rdx
0x18001681a  jz      short loc_18001682F
0x18001681c  mov     [rcx+10h], rdx
0x180016820  mov     rcx, rdx
0x180016823  mov     rax, [rdx]
0x180016826  mov     rax, [rax+8]
0x18001682a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001682f  mov     rax, rbx
0x180016832  add     rsp, 20h
0x180016836  pop     rbx
0x180016837  retn
```
