# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x18000e9d0`
- end: `0x18000ea43`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180011e4c`
- `0x1800120c4`

## callees

- `0x18000adb0`
- `0x18000e778`
- `0x18000e9d0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e9f0`
- `KERNEL32!EnterCriticalSection` at `0x18000e9f0`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea14`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea14`

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
0x18000e9d0  push    rbx
0x18000e9d2  push    rbp
0x18000e9d3  push    rsi
0x18000e9d4  push    rdi
0x18000e9d5  sub     rsp, 28h
0x18000e9d9  mov     rbx, r8
0x18000e9dc  mov     rsi, rdx
0x18000e9df  mov     rbp, rcx
0x18000e9e2  test    rdx, rdx
0x18000e9e5  jz      short loc_18000EA35
0x18000e9e7  test    rbx, rbx
0x18000e9ea  jz      short loc_18000EA35
0x18000e9ec  add     rcx, 20h ; ' '; lpCriticalSection
0x18000e9f0  call    cs:__imp_EnterCriticalSection
0x18000e9f6  mov     [rsp+48h+arg_8], 0
0x18000e9ff  lea     rcx, [rbp+8]; this
0x18000ea03  mov     r8, rbx; unsigned __int16 *
0x18000ea06  mov     rdx, rsi; unsigned __int16 *
0x18000ea09  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000ea0e  mov     ebx, eax
0x18000ea10  lea     rcx, [rbp+20h]; lpCriticalSection
0x18000ea14  call    cs:__imp_LeaveCriticalSection
0x18000ea1a  nop
0x18000ea1b  neg     ebx
0x18000ea1d  sbb     ebx, ebx
0x18000ea1f  not     ebx
0x18000ea21  and     ebx, 8007000Eh
0x18000ea27  lea     rcx, [rsp+48h+arg_8]
0x18000ea2c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000ea31  mov     eax, ebx
0x18000ea33  jmp     short loc_18000EA3A
0x18000ea35  mov     eax, 80070057h
0x18000ea3a  add     rsp, 28h
0x18000ea3e  pop     rdi
0x18000ea3f  pop     rsi
0x18000ea40  pop     rbp
0x18000ea41  pop     rbx
0x18000ea42  retn
```
