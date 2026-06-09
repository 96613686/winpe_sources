# CIsoBurnUI::~CIsoBurnUI(void)

- ea: `0x14000a694`
- end: `0x14000a703`
- name: `??1CIsoBurnUI@@UEAA@XZ`
- size: `111`
- prototype: `void __fastcall(CIsoBurnUI *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000a710`

## callees

- `0x14000a600`
- `0x14000a694`
- `0x14000f55c`
- `0x140010010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000a6e9`
- `KERNEL32!DeleteCriticalSection` at `0x14000a6e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a6a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a6b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a6a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a6b1`

## pseudocode

```c
void __fastcall CIsoBurnUI::~CIsoBurnUI(CIsoBurnUI *this)
{
  __int64 v2; // rcx
  AtlThunkData_t *v3; // rcx

  CoTaskMemFree(*((LPVOID *)this + 16));
  CoTaskMemFree(*((LPVOID *)this + 18));
  v2 = *((_QWORD *)this + 20);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::~CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>((char *)this + 152);
  if ( *((_BYTE *)this + 120) )
  {
    *((_BYTE *)this + 120) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  }
  v3 = (AtlThunkData_t *)*((_QWORD *)this + 5);
  if ( v3 )
    AtlThunk_FreeData(v3);
}

```

## disassembly

```asm
0x14000a694  push    rbx
0x14000a696  sub     rsp, 20h
0x14000a69a  mov     rbx, rcx
0x14000a69d  mov     rcx, [rcx+80h]; pv
0x14000a6a4  call    cs:__imp_CoTaskMemFree
0x14000a6aa  mov     rcx, [rbx+90h]; pv
0x14000a6b1  call    cs:__imp_CoTaskMemFree
0x14000a6b7  mov     rcx, [rbx+0A0h]
0x14000a6be  test    rcx, rcx
0x14000a6c1  jz      short loc_14000A6CF
0x14000a6c3  mov     rax, [rcx]
0x14000a6c6  mov     rax, [rax+10h]
0x14000a6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6cf  lea     rcx, [rbx+98h]
0x14000a6d6  call    ??1?$CDPA_Base@GVCTContainer_PolicyCoTaskMem@@@@QEAA@XZ; CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>::~CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>(void)
0x14000a6db  lea     rcx, [rbx+50h]; lpCriticalSection
0x14000a6df  cmp     byte ptr [rcx+28h], 0
0x14000a6e3  jz      short loc_14000A6EF
0x14000a6e5  mov     byte ptr [rcx+28h], 0
0x14000a6e9  call    cs:__imp_DeleteCriticalSection
0x14000a6ef  mov     rcx, [rbx+28h]; Thunk
0x14000a6f3  test    rcx, rcx
0x14000a6f6  jz      short loc_14000A6FD
0x14000a6f8  call    AtlThunk_FreeData
0x14000a6fd  add     rsp, 20h
0x14000a701  pop     rbx
0x14000a702  retn
```
