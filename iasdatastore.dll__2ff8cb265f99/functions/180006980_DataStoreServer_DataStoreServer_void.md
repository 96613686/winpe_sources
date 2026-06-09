# DataStoreServer::~DataStoreServer(void)

- ea: `0x180006980`
- end: `0x180006aeb`
- name: `??1DataStoreServer@@QEAA@XZ`
- size: `363`
- prototype: `void __fastcall(DataStoreServer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800068dc`

## callees

- `0x180006980`
- `0x180010010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180006a9f`
- `KERNEL32!Sleep` at `0x180006a9f`
- `KERNEL32!DeleteCriticalSection` at `0x180006ae4`
- `ole32!CoTaskMemFree` at `0x18000699f`
- `ole32!CoTaskMemFree` at `0x1800069bc`
- `ole32!CoTaskMemFree` at `0x1800069d9`
- `ole32!CoTaskMemFree` at `0x18000699f`
- `ole32!CoTaskMemFree` at `0x1800069bc`
- `ole32!CoTaskMemFree` at `0x1800069d9`
- `rtutils!TraceDeregisterW` at `0x180006ac3`
- `rtutils!TraceDeregisterW` at `0x180006ac3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DataStoreServer::~DataStoreServer(DataStoreServer *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  *(_QWORD *)this = &DataStoreServer::`vftable';
  v2 = (void *)*((_QWORD *)this + 274);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 274) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 275);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 275) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 276);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 276) = 0;
  }
  *((_QWORD *)this + 268) = 0;
  *((_QWORD *)this + 269) = 0;
  *((_QWORD *)this + 270) = 0;
  *((_QWORD *)this + 271) = 0;
  v5 = *((_QWORD *)this + 272);
  if ( v5 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 32LL))(v5, 1);
  v6 = *((_QWORD *)this + 271);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 270);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 269);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *((_QWORD *)this + 268);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  while ( _InterlockedExchange(&lLocked, 1) )
    Sleep(5u);
  if ( !--lRefCount )
  {
    TraceDeregisterW(dwTraceID);
    dwTraceID = -1;
  }
  _InterlockedExchange(&lLocked, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180006980  push    rbx
0x180006982  sub     rsp, 20h
0x180006986  mov     rbx, rcx
0x180006989  lea     rax, ??_7DataStoreServer@@6B@; const DataStoreServer::`vftable'
0x180006990  mov     [rcx], rax
0x180006993  mov     rcx, [rcx+890h]; pv
0x18000699a  test    rcx, rcx
0x18000699d  jz      short loc_1800069B0
0x18000699f  call    cs:__imp_CoTaskMemFree
0x1800069a5  mov     qword ptr [rbx+890h], 0
0x1800069b0  mov     rcx, [rbx+898h]; pv
0x1800069b7  test    rcx, rcx
0x1800069ba  jz      short loc_1800069CD
0x1800069bc  call    cs:__imp_CoTaskMemFree
0x1800069c2  mov     qword ptr [rbx+898h], 0
0x1800069cd  mov     rcx, [rbx+8A0h]; pv
0x1800069d4  test    rcx, rcx
0x1800069d7  jz      short loc_1800069EA
0x1800069d9  call    cs:__imp_CoTaskMemFree
0x1800069df  mov     qword ptr [rbx+8A0h], 0
0x1800069ea  mov     qword ptr [rbx+860h], 0
0x1800069f5  mov     qword ptr [rbx+868h], 0
0x180006a00  mov     qword ptr [rbx+870h], 0
0x180006a0b  mov     qword ptr [rbx+878h], 0
0x180006a16  mov     rcx, [rbx+880h]
0x180006a1d  test    rcx, rcx
0x180006a20  jz      short loc_180006A34
0x180006a22  mov     rax, [rcx]
0x180006a25  mov     edx, 1
0x180006a2a  mov     rax, [rax+20h]
0x180006a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a33  nop
0x180006a34  mov     rcx, [rbx+878h]
0x180006a3b  test    rcx, rcx
0x180006a3e  jz      short loc_180006A4D
0x180006a40  mov     rax, [rcx]
0x180006a43  mov     rax, [rax+10h]
0x180006a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a4c  nop
0x180006a4d  mov     rcx, [rbx+870h]
0x180006a54  test    rcx, rcx
0x180006a57  jz      short loc_180006A66
0x180006a59  mov     rax, [rcx]
0x180006a5c  mov     rax, [rax+10h]
0x180006a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a65  nop
0x180006a66  mov     rcx, [rbx+868h]
0x180006a6d  test    rcx, rcx
0x180006a70  jz      short loc_180006A7F
0x180006a72  mov     rax, [rcx]
0x180006a75  mov     rax, [rax+10h]
0x180006a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a7e  nop
0x180006a7f  mov     rcx, [rbx+860h]
0x180006a86  test    rcx, rcx
0x180006a89  jz      short loc_180006A98
0x180006a8b  mov     rax, [rcx]
0x180006a8e  mov     rax, [rax+10h]
0x180006a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a97  nop
0x180006a98  jmp     short loc_180006AA5
0x180006a9a  mov     ecx, 5; dwMilliseconds
0x180006a9f  call    cs:__imp_Sleep
0x180006aa5  mov     eax, 1
0x180006aaa  xchg    eax, cs:lLocked
0x180006ab0  test    eax, eax
0x180006ab2  jnz     short loc_180006A9A
0x180006ab4  sub     cs:lRefCount, 1
0x180006abb  jnz     short loc_180006AD3
0x180006abd  mov     ecx, cs:dwTraceID; dwTraceID
0x180006ac3  call    cs:__imp_TraceDeregisterW
0x180006ac9  mov     cs:dwTraceID, 0FFFFFFFFh
0x180006ad3  xor     eax, eax
0x180006ad5  xchg    eax, cs:lLocked
0x180006adb  lea     rcx, [rbx+8]
0x180006adf  add     rsp, 20h
0x180006ae3  pop     rbx
0x180006ae4  jmp     cs:__imp_DeleteCriticalSection
```
