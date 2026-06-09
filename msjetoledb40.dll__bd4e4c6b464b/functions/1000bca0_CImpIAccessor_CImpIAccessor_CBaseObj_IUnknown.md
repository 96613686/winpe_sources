# CImpIAccessor::CImpIAccessor(CBaseObj *,IUnknown *)

- ea: `0x1000bca0`
- end: `0x1000bce7`
- name: `??0CImpIAccessor@@QAE@PAVCBaseObj@@PAUIUnknown@@@Z`
- size: `71`
- prototype: `CImpIAccessor *__thiscall(CImpIAccessor *__hidden this, struct CBaseObj *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10028340`

## callees

- `0x1000bca0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1000bccd`
- `KERNEL32!InitializeCriticalSection` at `0x1000bccd`

## pseudocode

```c
CImpIAccessor *__thiscall CImpIAccessor::CImpIAccessor(CImpIAccessor *this, struct CBaseObj *a2, struct IUnknown *a3)
{
  struct IUnknown *v4; // eax

  *((_DWORD *)this + 2) = a2;
  *(_DWORD *)this = &CImpIAccessor::`vftable';
  *((_DWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 5) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 1);
  v4 = a3;
  if ( !a3 )
    v4 = (struct IUnknown *)*((_DWORD *)this + 2);
  *((_DWORD *)this + 3) = v4;
  return this;
}

```

## disassembly

```asm
0x1000bca0  mov     edi, edi
0x1000bca2  push    ebp
0x1000bca3  mov     ebp, esp
0x1000bca5  mov     eax, [ebp+arg_0]
0x1000bca8  push    esi
0x1000bca9  mov     esi, ecx
0x1000bcab  mov     [esi+8], eax
0x1000bcae  lea     eax, [esi+18h]
0x1000bcb1  push    eax; lpCriticalSection
0x1000bcb2  mov     dword ptr [esi], offset ??_7CImpIAccessor@@6B@; const CImpIAccessor::`vftable'
0x1000bcb8  mov     dword ptr [esi+4], 0
0x1000bcbf  mov     dword ptr [esi+10h], 0
0x1000bcc6  mov     dword ptr [esi+14h], 0
0x1000bccd  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1000bcd3  mov     eax, [ebp+arg_4]
0x1000bcd6  test    eax, eax
0x1000bcd8  jnz     short loc_1000BCDD
0x1000bcda  mov     eax, [esi+8]
0x1000bcdd  mov     [esi+0Ch], eax
0x1000bce0  mov     eax, esi
0x1000bce2  pop     esi
0x1000bce3  pop     ebp
0x1000bce4  retn    8
```
