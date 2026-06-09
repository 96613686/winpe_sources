# CImportExportCallback::~CImportExportCallback(void)

- ea: `0x1400185d8`
- end: `0x14001862e`
- name: `??1CImportExportCallback@@IEAA@XZ`
- size: `86`
- prototype: `void __fastcall(CImportExportCallback *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140018ac0`

## callees

- `0x140009090`
- `0x1400185d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140018605`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140018605`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018614`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018614`

## pseudocode

```c
void __fastcall CImportExportCallback::~CImportExportCallback(CImportExportCallback *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CImportExportCallback::`vftable'{for `IAepImportExportCallback'};
  *((_QWORD *)this + 1) = &CImportExportCallback::`vftable'{for `IDafPrivImpersonationToken'};
  *((_QWORD *)this + 2) = &CImportExportCallback::`vftable'{for `IServiceProvider'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
    MIDL_user_free(v3);
}

```

## disassembly

```asm
0x1400185d8  push    rbx
0x1400185da  sub     rsp, 20h
0x1400185de  lea     rax, ??_7CImportExportCallback@@6BIAepImportExportCallback@@@; const CImportExportCallback::`vftable'{for `IAepImportExportCallback'}
0x1400185e5  mov     rbx, rcx
0x1400185e8  mov     [rcx], rax
0x1400185eb  lea     rax, ??_7CImportExportCallback@@6BIDafPrivImpersonationToken@@@; const CImportExportCallback::`vftable'{for `IDafPrivImpersonationToken'}
0x1400185f2  mov     [rcx+8], rax
0x1400185f6  lea     rax, ??_7CImportExportCallback@@6BIServiceProvider@@@; const CImportExportCallback::`vftable'{for `IServiceProvider'}
0x1400185fd  mov     [rcx+10h], rax
0x140018601  add     rcx, 30h ; '0'; lpCriticalSection
0x140018605  call    cs:__imp_DeleteCriticalSection
0x14001860b  mov     rcx, [rbx+60h]; hObject
0x14001860f  test    rcx, rcx
0x140018612  jz      short loc_14001861A
0x140018614  call    cs:__imp_CloseHandle
0x14001861a  mov     rcx, [rbx+20h]; void *
0x14001861e  test    rcx, rcx
0x140018621  jz      short loc_140018628
0x140018623  call    MIDL_user_free
0x140018628  add     rsp, 20h
0x14001862c  pop     rbx
0x14001862d  retn
```
