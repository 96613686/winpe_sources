# GpDevice::~GpDevice(void)

- ea: `0x1800072d0`
- end: `0x18000740e`
- name: `??1GpDevice@@UEAA@XZ`
- size: `318`
- prototype: `void __fastcall(GpDevice *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800e2650`
- `0x180113960`

## callees

- `0x1800072d0`
- `0x180007920`
- `0x18001ec80`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800072f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800072f7`
- `GDI32!DeleteDC` at `0x180007332`
- `GDI32!DeleteDC` at `0x180007403`
- `GDI32!DeleteDC` at `0x180007332`
- `GDI32!DeleteDC` at `0x180007403`
- `GDI32!DeleteObject` at `0x180007328`
- `GDI32!DeleteObject` at `0x180007328`

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
0x1800072d0  mov     [rsp+arg_0], rbx
0x1800072d5  push    rdi
0x1800072d6  sub     rsp, 20h
0x1800072da  lea     rax, ??_7GpDevice@@6B@; const GpDevice::`vftable'
0x1800072e1  mov     rbx, rcx
0x1800072e4  lea     rdi, [rcx+630h]
0x1800072eb  mov     [rcx], rax
0x1800072ee  cmp     dword ptr [rdi+28h], 0
0x1800072f2  jz      short loc_180007304
0x1800072f4  mov     rcx, rdi; lpCriticalSection
0x1800072f7  call    cs:__imp_DeleteCriticalSection
0x1800072fd  mov     dword ptr [rdi+28h], 0
0x180007304  mov     rcx, [rbx+610h]
0x18000730b  test    rcx, rcx
0x18000730e  jnz     loc_1800073D1
0x180007314  mov     rcx, [rbx+600h]
0x18000731b  test    rcx, rcx
0x18000731e  jnz     loc_1800073E2
0x180007324  mov     rcx, [rbx+10h]; ho
0x180007328  call    cs:__imp_DeleteObject
0x18000732e  mov     rcx, [rbx+18h]; hdc
0x180007332  call    cs:__imp_DeleteDC
0x180007338  cmp     qword ptr [rbx+5E8h], 0
0x180007340  jnz     loc_1800073F3
0x180007346  mov     rcx, [rbx+28h]
0x18000734a  call    GpFree
0x18000734f  mov     rcx, [rbx+628h]
0x180007356  call    GpFree
0x18000735b  mov     rcx, [rbx+5D8h]
0x180007362  test    rcx, rcx
0x180007365  jz      short loc_180007377
0x180007367  mov     rax, [rcx]
0x18000736a  mov     edx, 1
0x18000736f  mov     rax, [rax]
0x180007372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007377  mov     rcx, [rbx+5D0h]
0x18000737e  test    rcx, rcx
0x180007381  jz      short loc_180007393
0x180007383  mov     rax, [rcx]
0x180007386  mov     edx, 1
0x18000738b  mov     rax, [rax]
0x18000738e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007393  mov     dword ptr [rbx+8], 4C494146h
0x18000739a  lea     rax, ??_7EpScan@@6B@; const EpScan::`vftable'
0x1800073a1  mov     [rbx+58h], rax
0x1800073a5  mov     edi, 2
0x1800073aa  add     rbx, 560h
0x1800073b1  sub     rbx, 278h
0x1800073b8  mov     rcx, rbx; this
0x1800073bb  call    ??1EpBlenderConfig@EpScan@@QEAA@XZ; EpScan::EpBlenderConfig::~EpBlenderConfig(void)
0x1800073c0  sub     rdi, 1
0x1800073c4  jnz     short loc_1800073B1
0x1800073c6  mov     rbx, [rsp+28h+arg_0]
0x1800073cb  add     rsp, 20h
0x1800073cf  pop     rdi
0x1800073d0  retn
0x1800073d1  mov     rax, [rcx]
0x1800073d4  mov     rax, [rax+10h]
0x1800073d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073dd  jmp     loc_180007314
0x1800073e2  mov     rax, [rcx]
0x1800073e5  mov     rax, [rax+10h]
0x1800073e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ee  jmp     loc_180007324
0x1800073f3  mov     rcx, [rbx+5E0h]; hdc
0x1800073fa  test    rcx, rcx
0x1800073fd  jz      loc_180007346
0x180007403  call    cs:__imp_DeleteDC
0x180007409  jmp     loc_180007346
```
