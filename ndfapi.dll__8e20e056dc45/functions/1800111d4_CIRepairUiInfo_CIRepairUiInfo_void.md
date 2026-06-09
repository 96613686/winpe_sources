# CIRepairUiInfo::~CIRepairUiInfo(void)

- ea: `0x1800111d4`
- end: `0x180011218`
- name: `??1CIRepairUiInfo@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CIRepairUiInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180011550`

## callees

- `0x1800111d4`
- `0x180021010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001120b`
- `KERNEL32!DeleteCriticalSection` at `0x18001120b`

## pseudocode

```c
void __fastcall CIRepairUiInfo::~CIRepairUiInfo(CIRepairUiInfo *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CIRepairUiInfo::`vftable';
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x1800111d4  push    rbx
0x1800111d6  sub     rsp, 20h
0x1800111da  mov     rbx, rcx
0x1800111dd  lea     rax, ??_7CIRepairUiInfo@@6B@; const CIRepairUiInfo::`vftable'
0x1800111e4  mov     [rcx], rax
0x1800111e7  mov     rcx, [rcx+40h]
0x1800111eb  test    rcx, rcx
0x1800111ee  jz      short loc_1800111FD
0x1800111f0  mov     rax, [rcx]
0x1800111f3  mov     rax, [rax+10h]
0x1800111f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111fc  nop
0x1800111fd  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011201  cmp     byte ptr [rcx+28h], 0
0x180011205  jz      short loc_180011212
0x180011207  mov     byte ptr [rcx+28h], 0
0x18001120b  call    cs:__imp_DeleteCriticalSection
0x180011211  nop
0x180011212  add     rsp, 20h
0x180011216  pop     rbx
0x180011217  retn
```
