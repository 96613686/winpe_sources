# CapabilityUsageHelper::~CapabilityUsageHelper(void)

- ea: `0x100379d7`
- end: `0x10037a1b`
- name: `??1CapabilityUsageHelper@@EAE@XZ`
- size: `68`
- prototype: `void __thiscall(CapabilityUsageHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10019960`

## callees

- `0x10007630`
- `0x100379d7`
- `0x10037ad5`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x100379fe`
- `KERNEL32!CloseHandle` at `0x100379fe`
- `KERNEL32!DeleteCriticalSection` at `0x100379eb`
- `KERNEL32!DeleteCriticalSection` at `0x100379eb`

## pseudocode

```c
void __thiscall CapabilityUsageHelper::~CapabilityUsageHelper(CapabilityUsageHelper *this)
{
  int v2; // eax
  void *v3; // [esp+0h] [ebp-4h]

  *(_DWORD *)this = &CapabilityUsageHelper::`vftable';
  CapabilityUsageHelper::Stop(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 20));
  v2 = *((_DWORD *)this + 4);
  if ( v2 && v2 != -1 )
    CloseHandle(*((HANDLE *)this + 4));
  if ( *((_DWORD *)this + 3) )
    wil::details::CloseHandle(*((HANDLE *)this + 3), v3);
  *((_DWORD *)this + 2) = -1073741823;
}

```

## disassembly

```asm
0x100379d7  mov     edi, edi
0x100379d9  push    esi; void *
0x100379da  mov     esi, ecx
0x100379dc  mov     dword ptr [esi], offset ??_7CapabilityUsageHelper@@6B@; const CapabilityUsageHelper::`vftable'
0x100379e2  call    ?Stop@CapabilityUsageHelper@@QAEJXZ; CapabilityUsageHelper::Stop(void)
0x100379e7  lea     eax, [esi+14h]
0x100379ea  push    eax; lpCriticalSection
0x100379eb  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x100379f1  mov     eax, [esi+10h]
0x100379f4  test    eax, eax
0x100379f6  jz      short loc_10037A04
0x100379f8  cmp     eax, 0FFFFFFFFh
0x100379fb  jz      short loc_10037A04
0x100379fd  push    eax; hObject
0x100379fe  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10037a04  cmp     dword ptr [esi+0Ch], 0
0x10037a08  jz      short loc_10037A12
0x10037a0a  push    dword ptr [esi+0Ch]; hObject
0x10037a0d  call    ?CloseHandle@details@wil@@YGXPAX@Z; wil::details::CloseHandle(void *)
0x10037a12  mov     dword ptr [esi+8], 0C0000001h
0x10037a19  pop     esi
0x10037a1a  retn
```
