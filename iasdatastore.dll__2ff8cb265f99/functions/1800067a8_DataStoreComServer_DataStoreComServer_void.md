# DataStoreComServer::DataStoreComServer(void)

- ea: `0x1800067a8`
- end: `0x18000689b`
- name: `??0DataStoreComServer@@QEAA@XZ`
- size: `243`
- prototype: `DataStoreComServer *__fastcall(DataStoreComServer *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003be4`
- `0x180003d18`
- `0x180003f78`

## callees

- `0x180002310`
- `0x1800067a8`
- `0x180008d7c`
- `0x18000cbb0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006802`
- `KERNEL32!InitializeCriticalSection` at `0x180006802`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
DataStoreComServer *__fastcall DataStoreComServer::DataStoreComServer(DataStoreComServer *this)
{
  char *v2; // rax
  char *v3; // rbx

  *((_DWORD *)this + 2) = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_BYTE *)this + 56) = 0;
  IASTraceInitializeEx(0);
  *(_QWORD *)this = &DataStoreComServer::`vftable';
  v2 = (char *)operator new(0x8B8u);
  v3 = v2;
  if ( v2 )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
    IASTraceInitializeEx(0);
    *(_QWORD *)v3 = &DataStoreServer::`vftable';
    v3[48] = 0;
    *((_QWORD *)v3 + 268) = 0;
    *((_QWORD *)v3 + 269) = 0;
    *((_QWORD *)v3 + 270) = 0;
    *((_QWORD *)v3 + 271) = 0;
    *((_QWORD *)v3 + 272) = 0;
    *((_QWORD *)v3 + 274) = 0;
    *((_QWORD *)v3 + 275) = 0;
    *((_QWORD *)v3 + 276) = 0;
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)this + 9) = v3;
  if ( v3 )
    DataStoreServer::Initialize((DataStoreServer *)v3);
  return this;
}

```

## disassembly

```asm
0x1800067a8  mov     [rsp+arg_10], rbx
0x1800067ad  mov     [rsp+arg_0], rcx
0x1800067b2  push    rdi
0x1800067b3  sub     rsp, 20h
0x1800067b7  mov     rdi, rcx
0x1800067ba  mov     dword ptr [rcx+8], 0
0x1800067c1  xorps   xmm0, xmm0
0x1800067c4  xor     eax, eax
0x1800067c6  movups  xmmword ptr [rcx+10h], xmm0
0x1800067ca  movups  xmmword ptr [rcx+20h], xmm0
0x1800067ce  mov     [rcx+30h], rax
0x1800067d2  mov     [rcx+38h], al
0x1800067d5  xor     ecx, ecx; Source
0x1800067d7  call    IASTraceInitializeEx
0x1800067dc  nop
0x1800067dd  lea     rax, ??_7DataStoreComServer@@6B@; const DataStoreComServer::`vftable'
0x1800067e4  mov     [rdi], rax
0x1800067e7  mov     ecx, 8B8h; Size
0x1800067ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800067f1  mov     rbx, rax
0x1800067f4  mov     [rsp+28h+arg_8], rax
0x1800067f9  test    rax, rax
0x1800067fc  jz      short loc_180006879
0x1800067fe  lea     rcx, [rax+8]; lpCriticalSection
0x180006802  call    cs:__imp_InitializeCriticalSection
0x180006808  nop
0x180006809  xor     ecx, ecx; Source
0x18000680b  call    IASTraceInitializeEx
0x180006810  nop
0x180006811  lea     rax, ??_7DataStoreServer@@6B@; const DataStoreServer::`vftable'
0x180006818  mov     [rbx], rax
0x18000681b  mov     byte ptr [rbx+30h], 0
0x18000681f  mov     qword ptr [rbx+860h], 0
0x18000682a  mov     qword ptr [rbx+868h], 0
0x180006835  mov     qword ptr [rbx+870h], 0
0x180006840  mov     qword ptr [rbx+878h], 0
0x18000684b  mov     qword ptr [rbx+880h], 0
0x180006856  mov     qword ptr [rbx+890h], 0
0x180006861  mov     qword ptr [rbx+898h], 0
0x18000686c  mov     qword ptr [rbx+8A0h], 0
0x180006877  jmp     short loc_18000687B
0x180006879  xor     ebx, ebx
0x18000687b  mov     [rdi+48h], rbx
0x18000687f  test    rbx, rbx
0x180006882  jz      short loc_18000688D
0x180006884  mov     rcx, rbx; this
0x180006887  call    ?Initialize@DataStoreServer@@QEAAJXZ; DataStoreServer::Initialize(void)
0x18000688c  nop
0x18000688d  mov     rax, rdi
0x180006890  mov     rbx, [rsp+28h+arg_10]
0x180006895  add     rsp, 20h
0x180006899  pop     rdi
0x18000689a  retn
```
