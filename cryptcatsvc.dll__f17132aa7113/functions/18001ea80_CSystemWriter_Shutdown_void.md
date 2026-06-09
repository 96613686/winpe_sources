# CSystemWriter::Shutdown(void)

- ea: `0x18001ea80`
- end: `0x18001eb21`
- name: `?Shutdown@CSystemWriter@@SAXXZ`
- size: `161`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ad54`

## callees

- `0x180006e54`
- `0x18001ea80`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ea9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ea9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eaa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eaa3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001eab9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001eab9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001eaee`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001eaee`

## pseudocode

```c
void CSystemWriter::Shutdown(void)
{
  void *v0; // rbx
  struct CSystemWriter *v1; // rbx
  HRESULT v2; // eax
  __int64 v3; // rcx

  v0 = (void *)_InterlockedExchange64((volatile __int64 *)&g_hInitializeThread, 0);
  if ( v0 )
  {
    WaitForSingleObject(v0, 0xFFFFFFFF);
    CloseHandle(v0);
  }
  v1 = CSystemWriter::sm_pWriter;
  if ( CSystemWriter::sm_pWriter )
  {
    v2 = CoInitializeEx(0, 0);
    if ( v2 )
    {
      CSystemWriter::LogSystemErrorEvent(512, L"CoInitializeEx failed in Unitialize.", v2);
    }
    else
    {
      v3 = *((_QWORD *)v1 + 1);
      if ( v3 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
      CoUninitialize();
    }
    if ( CSystemWriter::sm_pWriter )
      (**(void (__fastcall ***)(struct CSystemWriter *, __int64))CSystemWriter::sm_pWriter)(
        CSystemWriter::sm_pWriter,
        1);
    CSystemWriter::sm_pWriter = 0;
  }
}

```

## disassembly

```asm
0x18001ea80  push    rbx
0x18001ea82  sub     rsp, 20h
0x18001ea86  xor     ebx, ebx
0x18001ea88  xchg    rbx, cs:?g_hInitializeThread@@3PEAXEA; void * g_hInitializeThread
0x18001ea8f  test    rbx, rbx
0x18001ea92  jz      short loc_18001EAA9
0x18001ea94  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001ea97  mov     rcx, rbx; hHandle
0x18001ea9a  call    cs:__imp_WaitForSingleObject
0x18001eaa0  mov     rcx, rbx; hObject
0x18001eaa3  call    cs:__imp_CloseHandle
0x18001eaa9  mov     rbx, cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA; CSystemWriter * CSystemWriter::sm_pWriter
0x18001eab0  test    rbx, rbx
0x18001eab3  jz      short loc_18001EB1B
0x18001eab5  xor     edx, edx; dwCoInit
0x18001eab7  xor     ecx, ecx; pvReserved
0x18001eab9  call    cs:__imp_CoInitializeEx
0x18001eabf  test    eax, eax
0x18001eac1  jz      short loc_18001EAD9
0x18001eac3  mov     r8d, eax; unsigned int
0x18001eac6  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed in Unitialize."
0x18001eacd  mov     ecx, 200h; unsigned int
0x18001ead2  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001ead7  jmp     short loc_18001EAF4
0x18001ead9  mov     rcx, [rbx+8]
0x18001eadd  test    rcx, rcx
0x18001eae0  jz      short loc_18001EAEE
0x18001eae2  mov     rax, [rcx]
0x18001eae5  mov     rax, [rax+28h]
0x18001eae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaee  call    cs:__imp_CoUninitialize
0x18001eaf4  mov     rcx, cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA; CSystemWriter * CSystemWriter::sm_pWriter
0x18001eafb  test    rcx, rcx
0x18001eafe  jz      short loc_18001EB10
0x18001eb00  mov     rax, [rcx]
0x18001eb03  mov     edx, 1
0x18001eb08  mov     rax, [rax]
0x18001eb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb10  mov     cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA, 0; CSystemWriter * CSystemWriter::sm_pWriter
0x18001eb1b  add     rsp, 20h
0x18001eb1f  pop     rbx
0x18001eb20  retn
```
