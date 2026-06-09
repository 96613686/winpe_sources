# CSystemWriter::InitializeThreadFunc(void *)

- ea: `0x18001e5e0`
- end: `0x18001e667`
- name: `?InitializeThreadFunc@CSystemWriter@@CAKPEAX@Z`
- size: `135`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006e54`
- `0x18001e494`
- `0x18001e5e0`
- `0x18001ecdc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e659`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e659`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001e5f3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001e5f3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001e61a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001e61a`

## pseudocode

```c
__int64 __fastcall CSystemWriter::InitializeThreadFunc(const unsigned __int16 *Parameter)
{
  HRESULT v1; // eax
  CSystemWriter *v2; // rcx
  char v3; // bl
  void *v4; // rcx

  if ( (unsigned int)CSystemWriter::WaitForServiceRunning(Parameter) )
  {
    v1 = CoInitializeEx(0, 0);
    if ( v1 )
    {
      CSystemWriter::LogSystemErrorEvent(512, L"CoInitializeEx failed.", v1);
    }
    else
    {
      v3 = CSystemWriter::Initialize(v2);
      CoUninitialize();
      if ( v3 )
        goto LABEL_8;
    }
  }
  if ( CSystemWriter::sm_pWriter )
    (**(void (__fastcall ***)(struct CSystemWriter *, __int64))CSystemWriter::sm_pWriter)(CSystemWriter::sm_pWriter, 1);
  CSystemWriter::sm_pWriter = 0;
LABEL_8:
  v4 = (void *)_InterlockedExchange64((volatile __int64 *)&g_hInitializeThread, 0);
  if ( v4 )
    CloseHandle(v4);
  return 0;
}

```

## disassembly

```asm
0x18001e5e0  push    rbx
0x18001e5e2  sub     rsp, 20h
0x18001e5e6  call    ?WaitForServiceRunning@CSystemWriter@@CAHPEBG@Z; CSystemWriter::WaitForServiceRunning(ushort const *)
0x18001e5eb  test    eax, eax
0x18001e5ed  jz      short loc_18001E624
0x18001e5ef  xor     edx, edx; dwCoInit
0x18001e5f1  xor     ecx, ecx; pvReserved
0x18001e5f3  call    cs:__imp_CoInitializeEx
0x18001e5f9  test    eax, eax
0x18001e5fb  jz      short loc_18001E613
0x18001e5fd  mov     r8d, eax; unsigned int
0x18001e600  lea     rdx, aCoinitializeex_1; "CoInitializeEx failed."
0x18001e607  mov     ecx, 200h; unsigned int
0x18001e60c  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001e611  jmp     short loc_18001E624
0x18001e613  call    ?Initialize@CSystemWriter@@AEAA_NXZ; CSystemWriter::Initialize(void)
0x18001e618  mov     bl, al
0x18001e61a  call    cs:__imp_CoUninitialize
0x18001e620  test    bl, bl
0x18001e622  jnz     short loc_18001E64B
0x18001e624  mov     rcx, cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA; CSystemWriter * CSystemWriter::sm_pWriter
0x18001e62b  test    rcx, rcx
0x18001e62e  jz      short loc_18001E640
0x18001e630  mov     rax, [rcx]
0x18001e633  mov     edx, 1
0x18001e638  mov     rax, [rax]
0x18001e63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e640  mov     cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA, 0; CSystemWriter * CSystemWriter::sm_pWriter
0x18001e64b  xor     ecx, ecx
0x18001e64d  xchg    rcx, cs:?g_hInitializeThread@@3PEAXEA; hObject
0x18001e654  test    rcx, rcx
0x18001e657  jz      short loc_18001E65F
0x18001e659  call    cs:__imp_CloseHandle
0x18001e65f  xor     eax, eax
0x18001e661  add     rsp, 20h
0x18001e665  pop     rbx
0x18001e666  retn
```
