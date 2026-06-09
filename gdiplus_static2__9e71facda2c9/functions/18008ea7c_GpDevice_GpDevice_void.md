# GpDevice::~GpDevice(void)

- ea: `0x18008ea7c`
- end: `0x18008ebd3`
- name: `??1GpDevice@@UEAA@XZ`
- size: `343`
- prototype: `void __fastcall(GpDevice *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18008e910`
- `0x18011b6a4`

## callees

- `0x180010bd0`
- `0x18008ea7c`
- `0x18008f0f0`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008eaa3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008eaa3`
- `GDI32!DeleteDC` at `0x18008eaea`
- `GDI32!DeleteDC` at `0x18008ebc2`
- `GDI32!DeleteDC` at `0x18008eaea`
- `GDI32!DeleteDC` at `0x18008ebc2`
- `GDI32!DeleteObject` at `0x18008eada`
- `GDI32!DeleteObject` at `0x18008eada`

## pseudocode

```c
void __fastcall GpDevice::~GpDevice(GpDevice *this)
{
  char *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  __int64 v7; // rdi
  EpScan::EpBlenderConfig *v8; // rbx
  HDC v9; // rcx

  v2 = (char *)this + 1584;
  *(_QWORD *)this = &GpDevice::`vftable';
  if ( *((_DWORD *)this + 406) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
    *((_DWORD *)v2 + 10) = 0;
  }
  v3 = *((_QWORD *)this + 194);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 192);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  DeleteObject(*((HGDIOBJ *)this + 2));
  DeleteDC(*((HDC *)this + 3));
  if ( *((_QWORD *)this + 189) )
  {
    v9 = (HDC)*((_QWORD *)this + 188);
    if ( v9 )
      DeleteDC(v9);
  }
  GpFree(*((_QWORD *)this + 5));
  GpFree(*((_QWORD *)this + 197));
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 187);
  if ( v5 )
    (**v5)(v5, 1);
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 186);
  if ( v6 )
    (**v6)(v6, 1);
  *((_DWORD *)this + 2) = 1279869254;
  *((_QWORD *)this + 11) = &EpScan::`vftable';
  v7 = 2;
  v8 = (GpDevice *)((char *)this + 1376);
  do
  {
    v8 = (EpScan::EpBlenderConfig *)((char *)v8 - 632);
    EpScan::EpBlenderConfig::~EpBlenderConfig(v8);
    --v7;
  }
  while ( v7 );
}

```

## disassembly

```asm
0x18008ea7c  mov     [rsp+arg_0], rbx
0x18008ea81  push    rdi
0x18008ea82  sub     rsp, 20h
0x18008ea86  lea     rax, ??_7GpDevice@@6B@; const GpDevice::`vftable'
0x18008ea8d  mov     rbx, rcx
0x18008ea90  lea     rdi, [rcx+630h]
0x18008ea97  mov     [rcx], rax
0x18008ea9a  cmp     dword ptr [rdi+28h], 0
0x18008ea9e  jz      short loc_18008EAB6
0x18008eaa0  mov     rcx, rdi; lpCriticalSection
0x18008eaa3  call    cs:__imp_DeleteCriticalSection
0x18008eaaa  nop     dword ptr [rax+rax+00h]
0x18008eaaf  mov     dword ptr [rdi+28h], 0
0x18008eab6  mov     rcx, [rbx+610h]
0x18008eabd  test    rcx, rcx
0x18008eac0  jnz     loc_18008EB90
0x18008eac6  mov     rcx, [rbx+600h]
0x18008eacd  test    rcx, rcx
0x18008ead0  jnz     loc_18008EBA1
0x18008ead6  mov     rcx, [rbx+10h]; ho
0x18008eada  call    cs:__imp_DeleteObject
0x18008eae1  nop     dword ptr [rax+rax+00h]
0x18008eae6  mov     rcx, [rbx+18h]; hdc
0x18008eaea  call    cs:__imp_DeleteDC
0x18008eaf1  nop     dword ptr [rax+rax+00h]
0x18008eaf6  cmp     qword ptr [rbx+5E8h], 0
0x18008eafe  jnz     loc_18008EBB2
0x18008eb04  mov     rcx, [rbx+28h]
0x18008eb08  call    GpFree
0x18008eb0d  mov     rcx, [rbx+628h]
0x18008eb14  call    GpFree
0x18008eb19  mov     rcx, [rbx+5D8h]
0x18008eb20  test    rcx, rcx
0x18008eb23  jz      short loc_18008EB35
0x18008eb25  mov     rax, [rcx]
0x18008eb28  mov     edx, 1
0x18008eb2d  mov     rax, [rax]
0x18008eb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb35  mov     rcx, [rbx+5D0h]
0x18008eb3c  test    rcx, rcx
0x18008eb3f  jz      short loc_18008EB51
0x18008eb41  mov     rax, [rcx]
0x18008eb44  mov     edx, 1
0x18008eb49  mov     rax, [rax]
0x18008eb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb51  mov     dword ptr [rbx+8], 4C494146h
0x18008eb58  lea     rax, ??_7EpScan@@6B@; const EpScan::`vftable'
0x18008eb5f  mov     [rbx+58h], rax
0x18008eb63  mov     edi, 2
0x18008eb68  add     rbx, 560h
0x18008eb6f  sub     rbx, 278h
0x18008eb76  mov     rcx, rbx; this
0x18008eb79  call    ??1EpBlenderConfig@EpScan@@QEAA@XZ; EpScan::EpBlenderConfig::~EpBlenderConfig(void)
0x18008eb7e  sub     rdi, 1
0x18008eb82  jnz     short loc_18008EB6F
0x18008eb84  mov     rbx, [rsp+28h+arg_0]
0x18008eb89  add     rsp, 20h
0x18008eb8d  pop     rdi
0x18008eb8e  retn
0x18008eb90  mov     rax, [rcx]
0x18008eb93  mov     rax, [rax+10h]
0x18008eb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb9c  jmp     loc_18008EAC6
0x18008eba1  mov     rax, [rcx]
0x18008eba4  mov     rax, [rax+10h]
0x18008eba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ebad  jmp     loc_18008EAD6
0x18008ebb2  mov     rcx, [rbx+5E0h]; hdc
0x18008ebb9  test    rcx, rcx
0x18008ebbc  jz      loc_18008EB04
0x18008ebc2  call    cs:__imp_DeleteDC
0x18008ebc9  nop     dword ptr [rax+rax+00h]
0x18008ebce  jmp     loc_18008EB04
```
