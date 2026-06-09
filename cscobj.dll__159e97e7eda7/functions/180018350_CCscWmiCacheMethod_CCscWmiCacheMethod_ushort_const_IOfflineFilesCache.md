# CCscWmiCacheMethod::CCscWmiCacheMethod(ushort const *,IOfflineFilesCache *)

- ea: `0x180018350`
- end: `0x1800183a7`
- name: `??0CCscWmiCacheMethod@@QEAA@PEBGPEAUIOfflineFilesCache@@@Z`
- size: `87`
- prototype: `CCscWmiCacheMethod *__fastcall(CCscWmiCacheMethod *__hidden this, const unsigned __int16 *, struct IOfflineFilesCache *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018480`
- `0x180018b68`

## callees

- `0x180016738`

## string_xrefs

- `0x18001836a`: `Win32_OfflineFilesCache`

## pseudocode

```c
CCscWmiCacheMethod *__fastcall CCscWmiCacheMethod::CCscWmiCacheMethod(
        CCscWmiCacheMethod *this,
        const unsigned __int16 *a2,
        IUnknown *a3)
{
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CCscWmiMethod::`vftable';
  *((_QWORD *)this + 3) = a2;
  *((_QWORD *)this + 2) = L"Win32_OfflineFilesCache";
  *((_QWORD *)this + 4) = 0;
  _InterlockedIncrement(&g_cRefDll);
  *(_QWORD *)this = &CCscWmiCacheMethod::`vftable';
  CInterThreadIFacePtr<IOfflineFilesCache>::CInterThreadIFacePtr<IOfflineFilesCache>((__int64)this + 40, a3);
  return this;
}

```

## disassembly

```asm
0x180018350  push    rbx
0x180018352  sub     rsp, 20h
0x180018356  lea     rax, ??_7CCscWmiMethod@@6B@; const CCscWmiMethod::`vftable'
0x18001835d  mov     dword ptr [rcx+8], 1
0x180018364  mov     [rcx], rax
0x180018367  mov     rbx, rcx
0x18001836a  lea     rax, CSCWMI_STR_OFFLINEFILESCACHE; "Win32_OfflineFilesCache"
0x180018371  mov     [rcx+18h], rdx
0x180018375  mov     [rcx+10h], rax
0x180018379  mov     qword ptr [rcx+20h], 0
0x180018381  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x180018388  lea     rax, ??_7CCscWmiCacheMethod@@6B@; const CCscWmiCacheMethod::`vftable'
0x18001838f  mov     rdx, r8
0x180018392  mov     [rcx], rax
0x180018395  add     rcx, 28h ; '('
0x180018399  call    ??0?$CInterThreadIFacePtr@UIOfflineFilesCache@@@@QEAA@PEAUIOfflineFilesCache@@@Z; CInterThreadIFacePtr<IOfflineFilesCache>::CInterThreadIFacePtr<IOfflineFilesCache>(IOfflineFilesCache *)
0x18001839e  mov     rax, rbx
0x1800183a1  add     rsp, 20h
0x1800183a5  pop     rbx
0x1800183a6  retn
```
