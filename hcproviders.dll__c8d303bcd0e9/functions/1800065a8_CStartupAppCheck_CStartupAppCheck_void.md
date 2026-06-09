# CStartupAppCheck::~CStartupAppCheck(void)

- ea: `0x1800065a8`
- end: `0x180006628`
- name: `??1CStartupAppCheck@@MEAA@XZ`
- size: `128`
- prototype: `void __fastcall(CStartupAppCheck *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006680`

## callees

- `0x1800039f0`
- `0x1800065a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000660f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000660f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800065cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800065cc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800065df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800065df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065f7`

## pseudocode

```c
void __fastcall CStartupAppCheck::~CStartupAppCheck(CStartupAppCheck *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rcx
  HKEY v4; // rcx

  *(_QWORD *)this = &CStartupAppCheck::`vftable';
  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 30);
  if ( v2 )
  {
    SetThreadpoolWait(v2, 0, 0);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 30));
  }
  v3 = (void *)*((_QWORD *)this + 29);
  if ( v3 )
    CloseHandle(v3);
  v4 = (HKEY)*((_QWORD *)this + 28);
  if ( v4 )
    RegCloseKey(v4);
  CCheckBase::~CCheckBase(this);
}

```

## disassembly

```asm
0x1800065a8  push    rbx
0x1800065aa  sub     rsp, 20h
0x1800065ae  lea     rax, ??_7CStartupAppCheck@@6B@; const CStartupAppCheck::`vftable'
0x1800065b5  mov     rbx, rcx
0x1800065b8  mov     [rcx], rax
0x1800065bb  mov     rcx, [rcx+0F0h]; pwa
0x1800065c2  test    rcx, rcx
0x1800065c5  jz      short loc_1800065EB
0x1800065c7  xor     r8d, r8d; pftTimeout
0x1800065ca  xor     edx, edx; h
0x1800065cc  call    cs:__imp_SetThreadpoolWait
0x1800065d3  nop     dword ptr [rax+rax+00h]
0x1800065d8  mov     rcx, [rbx+0F0h]; pwa
0x1800065df  call    cs:__imp_CloseThreadpoolWait
0x1800065e6  nop     dword ptr [rax+rax+00h]
0x1800065eb  mov     rcx, [rbx+0E8h]; hObject
0x1800065f2  test    rcx, rcx
0x1800065f5  jz      short loc_180006603
0x1800065f7  call    cs:__imp_CloseHandle
0x1800065fe  nop     dword ptr [rax+rax+00h]
0x180006603  mov     rcx, [rbx+0E0h]; hKey
0x18000660a  test    rcx, rcx
0x18000660d  jz      short loc_18000661B
0x18000660f  call    cs:__imp_RegCloseKey
0x180006616  nop     dword ptr [rax+rax+00h]
0x18000661b  mov     rcx, rbx; this
0x18000661e  add     rsp, 20h
0x180006622  pop     rbx
0x180006623  jmp     ??1CCheckBase@@MEAA@XZ; CCheckBase::~CCheckBase(void)
```
