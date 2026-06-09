# GpDevice::~GpDevice(void)

- ea: `0x1800c72bc`
- end: `0x1800c7410`
- name: `??1GpDevice@@UEAA@XZ`
- size: `340`
- prototype: `void __fastcall(GpDevice *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800c7280`
- `0x180101ccc`

## callees

- `0x18001f950`
- `0x180020410`
- `0x1800c72bc`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c72e3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c72e3`
- `GDI32!DeleteDC` at `0x1800c7327`
- `GDI32!DeleteDC` at `0x1800c73ff`
- `GDI32!DeleteDC` at `0x1800c7327`
- `GDI32!DeleteDC` at `0x1800c73ff`
- `GDI32!DeleteObject` at `0x1800c7317`
- `GDI32!DeleteObject` at `0x1800c7317`

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
0x1800c72bc  mov     [rsp+arg_0], rbx
0x1800c72c1  push    rdi
0x1800c72c2  sub     rsp, 20h
0x1800c72c6  lea     rax, ??_7GpDevice@@6B@; const GpDevice::`vftable'
0x1800c72cd  mov     rbx, rcx
0x1800c72d0  lea     rdi, [rcx+630h]
0x1800c72d7  mov     [rcx], rax
0x1800c72da  cmp     dword ptr [rdi+28h], 0
0x1800c72de  jz      short loc_1800C72F3
0x1800c72e0  mov     rcx, rdi; lpCriticalSection
0x1800c72e3  call    cs:__imp_DeleteCriticalSection
0x1800c72ea  nop     dword ptr [rax+rax+00h]
0x1800c72ef  and     dword ptr [rdi+28h], 0
0x1800c72f3  mov     rcx, [rbx+610h]
0x1800c72fa  test    rcx, rcx
0x1800c72fd  jnz     loc_1800C73CD
0x1800c7303  mov     rcx, [rbx+600h]
0x1800c730a  test    rcx, rcx
0x1800c730d  jnz     loc_1800C73DE
0x1800c7313  mov     rcx, [rbx+10h]; ho
0x1800c7317  call    cs:__imp_DeleteObject
0x1800c731e  nop     dword ptr [rax+rax+00h]
0x1800c7323  mov     rcx, [rbx+18h]; hdc
0x1800c7327  call    cs:__imp_DeleteDC
0x1800c732e  nop     dword ptr [rax+rax+00h]
0x1800c7333  cmp     qword ptr [rbx+5E8h], 0
0x1800c733b  jnz     loc_1800C73EF
0x1800c7341  mov     rcx, [rbx+28h]
0x1800c7345  call    GpFree
0x1800c734a  mov     rcx, [rbx+628h]
0x1800c7351  call    GpFree
0x1800c7356  mov     rcx, [rbx+5D8h]
0x1800c735d  test    rcx, rcx
0x1800c7360  jz      short loc_1800C7372
0x1800c7362  mov     rax, [rcx]
0x1800c7365  mov     edx, 1
0x1800c736a  mov     rax, [rax]
0x1800c736d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7372  mov     rcx, [rbx+5D0h]
0x1800c7379  test    rcx, rcx
0x1800c737c  jz      short loc_1800C738E
0x1800c737e  mov     rax, [rcx]
0x1800c7381  mov     edx, 1
0x1800c7386  mov     rax, [rax]
0x1800c7389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c738e  mov     dword ptr [rbx+8], 4C494146h
0x1800c7395  lea     rax, ??_7EpScan@@6B@; const EpScan::`vftable'
0x1800c739c  mov     [rbx+58h], rax
0x1800c73a0  mov     edi, 2
0x1800c73a5  add     rbx, 560h
0x1800c73ac  sub     rbx, 278h
0x1800c73b3  mov     rcx, rbx; this
0x1800c73b6  call    ??1EpBlenderConfig@EpScan@@QEAA@XZ; EpScan::EpBlenderConfig::~EpBlenderConfig(void)
0x1800c73bb  sub     rdi, 1
0x1800c73bf  jnz     short loc_1800C73AC
0x1800c73c1  mov     rbx, [rsp+28h+arg_0]
0x1800c73c6  add     rsp, 20h
0x1800c73ca  pop     rdi
0x1800c73cb  retn
0x1800c73cd  mov     rax, [rcx]
0x1800c73d0  mov     rax, [rax+10h]
0x1800c73d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c73d9  jmp     loc_1800C7303
0x1800c73de  mov     rax, [rcx]
0x1800c73e1  mov     rax, [rax+10h]
0x1800c73e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c73ea  jmp     loc_1800C7313
0x1800c73ef  mov     rcx, [rbx+5E0h]; hdc
0x1800c73f6  test    rcx, rcx
0x1800c73f9  jz      loc_1800C7341
0x1800c73ff  call    cs:__imp_DeleteDC
0x1800c7406  nop     dword ptr [rax+rax+00h]
0x1800c740b  jmp     loc_1800C7341
```
