# CError::Release(void)

- ea: `0x1000ec00`
- end: `0x1000ecae`
- name: `?Release@CError@@UAGKXZ`
- size: `174`
- prototype: `unsigned int __stdcall(CError *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1000ec00`
- `0x1004cea1`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1000ec4f`
- `KERNEL32!DeleteCriticalSection` at `0x1000ec4f`
- `KERNEL32!LeaveCriticalSection` at `0x1000ec25`
- `KERNEL32!LeaveCriticalSection` at `0x1000ec75`
- `KERNEL32!LeaveCriticalSection` at `0x1000ec84`
- `KERNEL32!LeaveCriticalSection` at `0x1000eca1`
- `KERNEL32!LeaveCriticalSection` at `0x1000ec25`
- `KERNEL32!LeaveCriticalSection` at `0x1000ec75`
- `KERNEL32!LeaveCriticalSection` at `0x1000ec84`
- `KERNEL32!LeaveCriticalSection` at `0x1000eca1`
- `KERNEL32!EnterCriticalSection` at `0x1000ec0b`
- `KERNEL32!EnterCriticalSection` at `0x1000ec63`
- `KERNEL32!EnterCriticalSection` at `0x1000ec8f`
- `KERNEL32!EnterCriticalSection` at `0x1000ec0b`
- `KERNEL32!EnterCriticalSection` at `0x1000ec63`
- `KERNEL32!EnterCriticalSection` at `0x1000ec8f`

## pseudocode

```c
int __stdcall CError::Release(CError *this)
{
  _DWORD *v1; // eax
  int v3; // esi

  EnterCriticalSection(&g_CriticalSection);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 1, 0xFFFFFFFF) )
  {
    v3 = *((_DWORD *)this + 1);
    LeaveCriticalSection(&g_CriticalSection);
    EnterCriticalSection(&g_CriticalSection);
    _InterlockedDecrement(&g_cObj);
    LeaveCriticalSection(&g_CriticalSection);
    return v3;
  }
  else
  {
    LeaveCriticalSection(&g_CriticalSection);
    if ( this )
    {
      v1 = (_DWORD *)*((_DWORD *)this + 3);
      *(_DWORD *)this = &CError::`vftable';
      if ( v1 )
      {
        *v1 = &CImpIErrorLookup::`vftable';
        operator delete(v1);
      }
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      operator delete(this);
    }
    EnterCriticalSection(&g_CriticalSection);
    _InterlockedDecrement(&g_cObj);
    LeaveCriticalSection(&g_CriticalSection);
    return 0;
  }
}

```

## disassembly

```asm
0x1000ec00  mov     edi, edi
0x1000ec02  push    ebp
0x1000ec03  mov     ebp, esp
0x1000ec05  push    esi
0x1000ec06  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000ec0b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000ec11  mov     esi, [ebp+Block]
0x1000ec14  or      eax, 0FFFFFFFFh
0x1000ec17  lea     ecx, [esi+4]
0x1000ec1a  lock xadd [ecx], eax
0x1000ec1e  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000ec23  jnz     short loc_1000EC82
0x1000ec25  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000ec2b  test    esi, esi
0x1000ec2d  jz      short loc_1000EC5E
0x1000ec2f  mov     eax, [esi+0Ch]
0x1000ec32  mov     dword ptr [esi], offset ??_7CError@@6B@; const CError::`vftable'
0x1000ec38  test    eax, eax
0x1000ec3a  jz      short loc_1000EC4B
0x1000ec3c  push    eax; Block
0x1000ec3d  mov     dword ptr [eax], offset ??_7CImpIErrorLookup@@6B@; const CImpIErrorLookup::`vftable'
0x1000ec43  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000ec48  add     esp, 4
0x1000ec4b  lea     eax, [esi+10h]
0x1000ec4e  push    eax; lpCriticalSection
0x1000ec4f  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1000ec55  push    esi; Block
0x1000ec56  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000ec5b  add     esp, 4
0x1000ec5e  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000ec63  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000ec69  lock dec ?g_cObj@@3JA; long g_cObj
0x1000ec70  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000ec75  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000ec7b  xor     eax, eax
0x1000ec7d  pop     esi
0x1000ec7e  pop     ebp
0x1000ec7f  retn    4
0x1000ec82  mov     esi, [ecx]
0x1000ec84  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000ec8a  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000ec8f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000ec95  lock dec ?g_cObj@@3JA; long g_cObj
0x1000ec9c  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000eca1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000eca7  mov     eax, esi
0x1000eca9  pop     esi
0x1000ecaa  pop     ebp
0x1000ecab  retn    4
```
