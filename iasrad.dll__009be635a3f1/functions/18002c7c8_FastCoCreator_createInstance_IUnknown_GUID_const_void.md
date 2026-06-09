# FastCoCreator::createInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18002c7c8`
- end: `0x18002c88e`
- name: `?createInstance@FastCoCreator@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `198`
- prototype: `__int64 __fastcall(FastCoCreator *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002c7a8`

## callees

- `0x18002c7c8`
- `0x180030010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002c7de`
- `KERNEL32!EnterCriticalSection` at `0x18002c7de`
- `KERNEL32!LeaveCriticalSection` at `0x18002c87b`
- `KERNEL32!LeaveCriticalSection` at `0x18002c87b`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18002c813`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18002c813`

## pseudocode

```c
__int64 __fastcall FastCoCreator::createInstance(
        FastCoCreator *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  LPVOID v5; // rcx
  HRESULT ClassObject; // ebx

  EnterCriticalSection(&CriticalSection);
  v5 = ppv;
  if ( ppv
    || (ClassObject = CoGetClassObject(
                        RegularExpression::theCreator,
                        dwClsContext,
                        0,
                        &GUID_00000001_0000_0000_c000_000000000046,
                        &ppv),
        (v5 = ppv) != 0) )
  {
    ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)v5 + 24LL))(
                    v5,
                    0,
                    &GUID_3f4dacb0_160d_11d2_a8e9_00104b365c9f,
                    a4);
    if ( ClassObject < 0 )
    {
      if ( !dword_180041328 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
    }
    else
    {
      ++dword_180041328;
    }
  }
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x18002c7c8  mov     [rsp+arg_0], rbx
0x18002c7cd  push    rdi
0x18002c7ce  sub     rsp, 30h
0x18002c7d2  mov     rdi, r9
0x18002c7d5  xor     ebx, ebx
0x18002c7d7  lea     rcx, CriticalSection; lpCriticalSection
0x18002c7de  call    cs:__imp_EnterCriticalSection
0x18002c7e4  mov     rcx, cs:ppv
0x18002c7eb  test    rcx, rcx
0x18002c7ee  jnz     short loc_18002C827
0x18002c7f0  lea     rax, ppv
0x18002c7f7  mov     [rsp+38h+ppv], rax; ppv
0x18002c7fc  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18002c803  xor     r8d, r8d; pvReserved
0x18002c806  mov     edx, cs:dwClsContext; dwClsContext
0x18002c80c  mov     rcx, cs:?theCreator@RegularExpression@@0VFastCoCreator@@A; rclsid
0x18002c813  call    cs:__imp_CoGetClassObject
0x18002c819  mov     ebx, eax
0x18002c81b  mov     rcx, cs:ppv
0x18002c822  test    rcx, rcx
0x18002c825  jz      short loc_18002C874
0x18002c827  mov     rax, [rcx]
0x18002c82a  mov     r9, rdi
0x18002c82d  lea     r8, _GUID_3f4dacb0_160d_11d2_a8e9_00104b365c9f
0x18002c834  xor     edx, edx
0x18002c836  mov     rax, [rax+18h]
0x18002c83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c83f  mov     ebx, eax
0x18002c841  test    eax, eax
0x18002c843  js      short loc_18002C84D
0x18002c845  inc     cs:dword_180041328
0x18002c84b  jmp     short loc_18002C874
0x18002c84d  cmp     cs:dword_180041328, 0
0x18002c854  jnz     short loc_18002C874
0x18002c856  mov     rcx, cs:ppv
0x18002c85d  mov     rax, [rcx]
0x18002c860  mov     rax, [rax+10h]
0x18002c864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c869  mov     cs:ppv, 0
0x18002c874  lea     rcx, CriticalSection; lpCriticalSection
0x18002c87b  call    cs:__imp_LeaveCriticalSection
0x18002c881  mov     eax, ebx
0x18002c883  mov     rbx, [rsp+38h+arg_0]
0x18002c888  add     rsp, 30h
0x18002c88c  pop     rdi
0x18002c88d  retn
```
