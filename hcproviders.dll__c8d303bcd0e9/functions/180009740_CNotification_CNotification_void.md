# CNotification::~CNotification(void)

- ea: `0x180009740`
- end: `0x180009802`
- name: `??1CNotification@@AEAA@XZ`
- size: `194`
- prototype: `void __fastcall(CNotification *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800099d0`

## callees

- `0x180009740`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097e8`

## pseudocode

```c
void __fastcall CNotification::~CNotification(CNotification *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &CNotification::`vftable';
  v2 = *((_QWORD *)this + 18);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 22);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 23);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v4 + 32) + 16LL))(v4 + 32);
  v5 = *((_QWORD *)this + 24);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v5 + 32) + 16LL))(v5 + 32);
  CoTaskMemFree(*((LPVOID *)this + 19));
  CoTaskMemFree(*((LPVOID *)this + 20));
  CoTaskMemFree(*((LPVOID *)this + 21));
  _InterlockedDecrement(&g_cLocks);
}

```

## disassembly

```asm
0x180009740  push    rbx
0x180009742  sub     rsp, 20h
0x180009746  lea     rax, ??_7CNotification@@6B@; const CNotification::`vftable'
0x18000974d  mov     rbx, rcx
0x180009750  mov     [rcx], rax
0x180009753  mov     rcx, [rcx+90h]
0x18000975a  test    rcx, rcx
0x18000975d  jz      short loc_18000976B
0x18000975f  mov     rax, [rcx]
0x180009762  mov     rax, [rax+10h]
0x180009766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000976b  mov     rcx, [rbx+0B0h]
0x180009772  test    rcx, rcx
0x180009775  jz      short loc_180009783
0x180009777  mov     rax, [rcx]
0x18000977a  mov     rax, [rax+10h]
0x18000977e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009783  mov     rcx, [rbx+0B8h]
0x18000978a  test    rcx, rcx
0x18000978d  jz      short loc_18000979F
0x18000978f  add     rcx, 20h ; ' '
0x180009793  mov     rax, [rcx]
0x180009796  mov     rax, [rax+10h]
0x18000979a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000979f  mov     rcx, [rbx+0C0h]
0x1800097a6  test    rcx, rcx
0x1800097a9  jz      short loc_1800097BB
0x1800097ab  add     rcx, 20h ; ' '
0x1800097af  mov     rax, [rcx]
0x1800097b2  mov     rax, [rax+10h]
0x1800097b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097bb  mov     rcx, [rbx+98h]; pv
0x1800097c2  call    cs:__imp_CoTaskMemFree
0x1800097c9  nop     dword ptr [rax+rax+00h]
0x1800097ce  mov     rcx, [rbx+0A0h]; pv
0x1800097d5  call    cs:__imp_CoTaskMemFree
0x1800097dc  nop     dword ptr [rax+rax+00h]
0x1800097e1  mov     rcx, [rbx+0A8h]; pv
0x1800097e8  call    cs:__imp_CoTaskMemFree
0x1800097ef  nop     dword ptr [rax+rax+00h]
0x1800097f4  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x1800097fb  add     rsp, 20h
0x1800097ff  pop     rbx
0x180009800  retn
```
