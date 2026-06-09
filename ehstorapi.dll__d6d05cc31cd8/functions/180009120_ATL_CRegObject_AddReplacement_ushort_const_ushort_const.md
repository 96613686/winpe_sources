# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180009120`
- end: `0x180009193`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b7bc`
- `0x18000ba34`

## callees

- `0x180008bf4`
- `0x180008efc`
- `0x180009120`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180009140`
- `KERNEL32!EnterCriticalSection` at `0x180009140`
- `KERNEL32!LeaveCriticalSection` at `0x180009164`
- `KERNEL32!LeaveCriticalSection` at `0x180009164`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v8 = 0;
  v6 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v8);
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180009120  push    rbx
0x180009122  push    rbp
0x180009123  push    rsi
0x180009124  push    rdi
0x180009125  sub     rsp, 28h
0x180009129  mov     rbx, r8
0x18000912c  mov     rsi, rdx
0x18000912f  mov     rbp, rcx
0x180009132  test    rdx, rdx
0x180009135  jz      short loc_180009185
0x180009137  test    rbx, rbx
0x18000913a  jz      short loc_180009185
0x18000913c  add     rcx, 20h ; ' '; lpCriticalSection
0x180009140  call    cs:__imp_EnterCriticalSection
0x180009146  mov     [rsp+48h+arg_8], 0
0x18000914f  lea     rcx, [rbp+8]; this
0x180009153  mov     r8, rbx; unsigned __int16 *
0x180009156  mov     rdx, rsi; unsigned __int16 *
0x180009159  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000915e  mov     ebx, eax
0x180009160  lea     rcx, [rbp+20h]; lpCriticalSection
0x180009164  call    cs:__imp_LeaveCriticalSection
0x18000916a  nop
0x18000916b  neg     ebx
0x18000916d  sbb     ebx, ebx
0x18000916f  not     ebx
0x180009171  and     ebx, 8007000Eh
0x180009177  lea     rcx, [rsp+48h+arg_8]
0x18000917c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009181  mov     eax, ebx
0x180009183  jmp     short loc_18000918A
0x180009185  mov     eax, 80070057h
0x18000918a  add     rsp, 28h
0x18000918e  pop     rdi
0x18000918f  pop     rsi
0x180009190  pop     rbp
0x180009191  pop     rbx
0x180009192  retn
```
