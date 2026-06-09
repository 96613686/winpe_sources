# PCChainManager::~PCChainManager(void)

- ea: `0x1801087c0`
- end: `0x180108809`
- name: `??1PCChainManager@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(PCChainManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18010878c`

## callees

- `0x1800379e0`
- `0x1801087c0`
- `0x180109534`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801087db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801087db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180108801`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180108801`

## pseudocode

```c
void __fastcall PCChainManager::~PCChainManager(PCChainManager *this)
{
  struct _TP_WORK *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rdx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 9);
  if ( v2 )
    CloseThreadpoolWork(v2);
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 8) = 0;
  }
  CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>::~CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>((char *)this + 24);
  LOBYTE(v4) = 1;
  CArray<win_scope::unique_object<IPCChainWork *>,CDefaultTraits<win_scope::unique_object<IPCChainWork *>>,CDefaultAllocator>::RemoveAll(
    this,
    v4);
}

```

## disassembly

```asm
0x1801087c0  push    rbx
0x1801087c2  sub     rsp, 20h
0x1801087c6  mov     rbx, rcx
0x1801087c9  mov     rcx, [rcx+48h]; pwk
0x1801087cd  test    rcx, rcx
0x1801087d0  jnz     short loc_180108801
0x1801087d2  mov     rcx, [rbx+40h]; hObject
0x1801087d6  test    rcx, rcx
0x1801087d9  jz      short loc_1801087E9
0x1801087db  call    cs:__imp_CloseHandle
0x1801087e1  mov     qword ptr [rbx+40h], 0
0x1801087e9  lea     rcx, [rbx+18h]; void *
0x1801087ed  call    ??1?$CArray@UD2D1_INPUT_DESCRIPTION@@VCInputDescriptionTraits@?$CDIHeapRenderInfoRenderDataCommon@VCDIPSRenderData@@@@VCDefaultAllocator@@@@QEAA@XZ; CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>::~CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>(void)
0x1801087f2  mov     dl, 1
0x1801087f4  mov     rcx, rbx
0x1801087f7  add     rsp, 20h
0x1801087fb  pop     rbx
0x1801087fc  jmp     ?RemoveAll@?$CArray@V?$unique_object@PEAUIPCChainWork@@@win_scope@@V?$CDefaultTraits@V?$unique_object@PEAUIPCChainWork@@@win_scope@@@@VCDefaultAllocator@@@@QEAAX_N@Z; CArray<win_scope::unique_object<IPCChainWork *>,CDefaultTraits<win_scope::unique_object<IPCChainWork *>>,CDefaultAllocator>::RemoveAll(bool)
0x180108801  call    cs:__imp_CloseThreadpoolWork
0x180108807  jmp     short loc_1801087D2
```
