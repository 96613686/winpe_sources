# MFTEnumCache::~MFTEnumCache(void)

- ea: `0x18004d394`
- end: `0x18004d429`
- name: `??1MFTEnumCache@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(MFTEnumCache *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ced4`

## callees

- `0x180004870`
- `0x18004d394`
- `0x18004d430`
- `0x18004dbac`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d3e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d3e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d3c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d3c6`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18004d407`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18004d407`

## pseudocode

```c
void __fastcall MFTEnumCache::~MFTEnumCache(MFTEnumCache *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  if ( *((_QWORD *)this + 8) )
  {
    CM_Unregister_Notification();
    *((_QWORD *)this + 8) = 0;
  }
  MFTEnumCache::FreeRegListener(this);
  MFTEnumCache::Invalidate(this);
  v2 = (void *)*((_QWORD *)this + 16);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 16) = 0;
  }
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 56LL))(v3, *((_QWORD *)this + 9));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 80);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18004d394  mov     [rsp+arg_0], rbx
0x18004d399  push    rdi
0x18004d39a  sub     rsp, 20h
0x18004d39e  mov     rbx, rcx
0x18004d3a1  mov     rcx, [rcx+40h]
0x18004d3a5  test    rcx, rcx
0x18004d3a8  jnz     short loc_18004D407
0x18004d3aa  mov     rcx, rbx; this
0x18004d3ad  call    ?FreeRegListener@MFTEnumCache@@QEAAXXZ; MFTEnumCache::FreeRegListener(void)
0x18004d3b2  mov     rcx, rbx; this
0x18004d3b5  call    ?Invalidate@MFTEnumCache@@QEAAXXZ; MFTEnumCache::Invalidate(void)
0x18004d3ba  mov     rcx, [rbx+80h]; hObject
0x18004d3c1  test    rcx, rcx
0x18004d3c4  jz      short loc_18004D3D7
0x18004d3c6  call    cs:__imp_CloseHandle
0x18004d3cc  mov     qword ptr [rbx+80h], 0
0x18004d3d7  mov     rcx, [rbx+50h]
0x18004d3db  test    rcx, rcx
0x18004d3de  jnz     short loc_18004D417
0x18004d3e0  lea     rcx, [rbx+58h]; lpCriticalSection
0x18004d3e4  call    cs:__imp_DeleteCriticalSection
0x18004d3ea  lea     rcx, [rbx+50h]
0x18004d3ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d3f3  mov     rcx, rbx
0x18004d3f6  mov     rbx, [rsp+28h+arg_0]
0x18004d3fb  add     rsp, 20h
0x18004d3ff  pop     rdi
0x18004d400  jmp     cs:__imp_DeleteCriticalSection
0x18004d407  call    cs:__imp_CM_Unregister_Notification
0x18004d40d  mov     qword ptr [rbx+40h], 0
0x18004d415  jmp     short loc_18004D3AA
0x18004d417  mov     rax, [rcx]
0x18004d41a  mov     rdx, [rbx+48h]
0x18004d41e  mov     rax, [rax+38h]
0x18004d422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d427  jmp     short loc_18004D3E0
```
