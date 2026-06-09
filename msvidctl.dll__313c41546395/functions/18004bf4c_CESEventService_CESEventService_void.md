# CESEventService::~CESEventService(void)

- ea: `0x18004bf4c`
- end: `0x18004bfc5`
- name: `??1CESEventService@@QEAA@XZ`
- size: `121`
- prototype: `void __fastcall(CESEventService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004be94`

## callees

- `0x180006b38`
- `0x18004bf4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bf80`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bf97`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bf80`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bf97`
- `KERNEL32!DeleteCriticalSection` at `0x18004bf71`
- `KERNEL32!DeleteCriticalSection` at `0x18004bf71`
- `KERNEL32!DeleteCriticalSection` at `0x18004bfbe`

## pseudocode

```c
void __fastcall CESEventService::~CESEventService(CESEventService *this)
{
  void *v2; // rcx
  void *v3; // rcx

  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>((char *)this + 168);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>((char *)this + 152);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    free(v2);
    *((_QWORD *)this + 11) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 12);
  if ( v3 )
  {
    free(v3);
    *((_QWORD *)this + 12) = 0;
  }
  *((_DWORD *)this + 26) = 0;
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>((char *)this + 8);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x18004bf4c  push    rbx
0x18004bf4e  sub     rsp, 20h
0x18004bf52  mov     rbx, rcx
0x18004bf55  add     rcx, 0A8h
0x18004bf5c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18004bf61  lea     rcx, [rbx+98h]
0x18004bf68  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18004bf6d  lea     rcx, [rbx+70h]; lpCriticalSection
0x18004bf71  call    cs:__imp_DeleteCriticalSection
0x18004bf77  mov     rcx, [rbx+58h]; Block
0x18004bf7b  test    rcx, rcx
0x18004bf7e  jz      short loc_18004BF8E
0x18004bf80  call    cs:__imp_free
0x18004bf86  mov     qword ptr [rbx+58h], 0
0x18004bf8e  mov     rcx, [rbx+60h]; Block
0x18004bf92  test    rcx, rcx
0x18004bf95  jz      short loc_18004BFA5
0x18004bf97  call    cs:__imp_free
0x18004bf9d  mov     qword ptr [rbx+60h], 0
0x18004bfa5  lea     rcx, [rbx+8]
0x18004bfa9  mov     dword ptr [rbx+68h], 0
0x18004bfb0  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18004bfb5  lea     rcx, [rbx+30h]
0x18004bfb9  add     rsp, 20h
0x18004bfbd  pop     rbx
0x18004bfbe  jmp     cs:__imp_DeleteCriticalSection
```
