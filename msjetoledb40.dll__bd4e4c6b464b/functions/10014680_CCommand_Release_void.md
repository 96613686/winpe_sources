# CCommand::Release(void)

- ea: `0x10014680`
- end: `0x100146d9`
- name: `?Release@CCommand@@UAGKXZ`
- size: `89`
- prototype: `unsigned int __stdcall(CCommand *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x10014680`
- `0x1001c6d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100146a4`
- `KERNEL32!LeaveCriticalSection` at `0x100146cb`
- `KERNEL32!LeaveCriticalSection` at `0x100146a4`
- `KERNEL32!LeaveCriticalSection` at `0x100146cb`
- `KERNEL32!EnterCriticalSection` at `0x10014691`
- `KERNEL32!EnterCriticalSection` at `0x10014691`

## pseudocode

```c
int __stdcall CCommand::Release(CCommand *this)
{
  int v2; // edi
  struct _RTL_CRITICAL_SECTION *v3; // [esp-4h] [ebp-Ch]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 248);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 1, 0xFFFFFFFF) )
  {
    v2 = *((_DWORD *)this + 1);
    LeaveCriticalSection(v3);
    return v2;
  }
  else
  {
    LeaveCriticalSection(v3);
    if ( this )
      (*(void (__thiscall **)(CCommand *, int))(*(_DWORD *)this + 12))(this, 1);
    return 0;
  }
}

```

## disassembly

```asm
0x10014680  mov     edi, edi
0x10014682  push    ebp
0x10014683  mov     ebp, esp
0x10014685  push    esi
0x10014686  push    edi
0x10014687  mov     edi, [ebp+this]
0x1001468a  lea     esi, [edi+0F8h]
0x10014690  push    esi; lpCriticalSection
0x10014691  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10014697  lea     ecx, [edi+4]
0x1001469a  or      eax, 0FFFFFFFFh
0x1001469d  lock xadd [ecx], eax
0x100146a1  push    esi; lpCriticalSection
0x100146a2  jnz     short loc_100146C9
0x100146a4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100146aa  test    edi, edi
0x100146ac  jz      short loc_100146C1
0x100146ae  mov     eax, [edi]
0x100146b0  push    1
0x100146b2  mov     esi, [eax+0Ch]
0x100146b5  mov     ecx, esi
0x100146b7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100146bd  mov     ecx, edi
0x100146bf  call    esi
0x100146c1  pop     edi
0x100146c2  xor     eax, eax
0x100146c4  pop     esi
0x100146c5  pop     ebp
0x100146c6  retn    4
0x100146c9  mov     edi, [ecx]
0x100146cb  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100146d1  mov     eax, edi
0x100146d3  pop     edi
0x100146d4  pop     esi
0x100146d5  pop     ebp
0x100146d6  retn    4
```
