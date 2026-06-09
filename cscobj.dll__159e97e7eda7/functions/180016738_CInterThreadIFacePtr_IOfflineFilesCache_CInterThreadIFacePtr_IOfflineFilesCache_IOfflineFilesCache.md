# CInterThreadIFacePtr<IOfflineFilesCache>::CInterThreadIFacePtr<IOfflineFilesCache>(IOfflineFilesCache *)

- ea: `0x180016738`
- end: `0x180016774`
- name: `??0?$CInterThreadIFacePtr@UIOfflineFilesCache@@@@QEAA@PEAUIOfflineFilesCache@@@Z`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800176e0`
- `0x180018350`

## callees

- `0x180016738`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180016762`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180016762`

## pseudocode

```c
__int64 __fastcall CInterThreadIFacePtr<IOfflineFilesCache>::CInterThreadIFacePtr<IOfflineFilesCache>(
        __int64 a1,
        IUnknown *a2)
{
  *(_DWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = a2;
  if ( a2 )
    *(_DWORD *)(a1 + 16) = CoMarshalInterThreadInterfaceInStream(
                             &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5,
                             a2,
                             (LPSTREAM *)(a1 + 8));
  return a1;
}

```

## disassembly

```asm
0x180016738  push    rbx
0x18001673a  sub     rsp, 20h
0x18001673e  mov     dword ptr [rcx+10h], 0
0x180016745  lea     r8, [rcx+8]; ppStm
0x180016749  mov     qword ptr [r8], 0
0x180016750  mov     rbx, rcx
0x180016753  mov     [rcx], rdx
0x180016756  test    rdx, rdx
0x180016759  jz      short loc_18001676B
0x18001675b  lea     rcx, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180016762  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180016768  mov     [rbx+10h], eax
0x18001676b  mov     rax, rbx
0x18001676e  add     rsp, 20h
0x180016772  pop     rbx
0x180016773  retn
```
