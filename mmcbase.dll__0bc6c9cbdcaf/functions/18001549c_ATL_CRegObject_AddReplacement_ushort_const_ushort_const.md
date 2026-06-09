# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x18001549c`
- end: `0x1800154dd`
- name: `?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z`
- size: `65`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015ca0`

## callees

- `0x1800152a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800154b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800154b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800154cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800154cc`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  LODWORD(a3) = ATL::CExpansionVector::Add(this, a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x18001549c  push    rbx
0x18001549e  push    rbp
0x18001549f  push    rsi
0x1800154a0  push    rdi
0x1800154a1  sub     rsp, 28h
0x1800154a5  mov     rsi, rcx
0x1800154a8  mov     rbx, r8
0x1800154ab  add     rcx, 10h; lpCriticalSection
0x1800154af  mov     rdi, rdx
0x1800154b2  call    cs:__imp_EnterCriticalSection
0x1800154b8  mov     r8, rbx; unsigned __int16 *
0x1800154bb  mov     rdx, rdi; unsigned __int16 *
0x1800154be  mov     rcx, rsi; this
0x1800154c1  call    ?Add@CExpansionVector@ATL@@QEAAJPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800154c6  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800154ca  mov     ebx, eax
0x1800154cc  call    cs:__imp_LeaveCriticalSection
0x1800154d2  mov     eax, ebx
0x1800154d4  add     rsp, 28h
0x1800154d8  pop     rdi
0x1800154d9  pop     rsi
0x1800154da  pop     rbp
0x1800154db  pop     rbx
0x1800154dc  retn
```
