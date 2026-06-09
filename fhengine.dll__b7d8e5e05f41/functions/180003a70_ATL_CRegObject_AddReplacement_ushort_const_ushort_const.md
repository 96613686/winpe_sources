# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003a70`
- end: `0x180003ae3`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006664`

## callees

- `0x180002f64`
- `0x1800037fc`
- `0x180003a70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003a90`
- `KERNEL32!EnterCriticalSection` at `0x180003a90`
- `KERNEL32!LeaveCriticalSection` at `0x180003ab4`
- `KERNEL32!LeaveCriticalSection` at `0x180003ab4`

## pseudocode

```c
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
0x180003a70  push    rbx
0x180003a72  push    rbp
0x180003a73  push    rsi
0x180003a74  push    rdi
0x180003a75  sub     rsp, 28h
0x180003a79  mov     rbx, r8
0x180003a7c  mov     rsi, rdx
0x180003a7f  mov     rbp, rcx
0x180003a82  test    rdx, rdx
0x180003a85  jz      short loc_180003AD5
0x180003a87  test    rbx, rbx
0x180003a8a  jz      short loc_180003AD5
0x180003a8c  add     rcx, 20h ; ' '; lpCriticalSection
0x180003a90  call    cs:__imp_EnterCriticalSection
0x180003a96  mov     [rsp+48h+arg_8], 0
0x180003a9f  lea     rcx, [rbp+8]; this
0x180003aa3  mov     r8, rbx; unsigned __int16 *
0x180003aa6  mov     rdx, rsi; unsigned __int16 *
0x180003aa9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180003aae  mov     ebx, eax
0x180003ab0  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003ab4  call    cs:__imp_LeaveCriticalSection
0x180003aba  nop
0x180003abb  neg     ebx
0x180003abd  sbb     ebx, ebx
0x180003abf  not     ebx
0x180003ac1  and     ebx, 8007000Eh
0x180003ac7  lea     rcx, [rsp+48h+arg_8]
0x180003acc  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003ad1  mov     eax, ebx
0x180003ad3  jmp     short loc_180003ADA
0x180003ad5  mov     eax, 80070057h
0x180003ada  add     rsp, 28h
0x180003ade  pop     rdi
0x180003adf  pop     rsi
0x180003ae0  pop     rbp
0x180003ae1  pop     rbx
0x180003ae2  retn
```
