# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x18000c050`
- end: `0x18000c0c2`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `114`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dfcc`
- `0x18000e224`

## callees

- `0x18000bc94`
- `0x18000bedc`
- `0x18000c050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c094`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c094`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c070`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c070`

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
0x18000c050  push    rbx
0x18000c052  push    rbp
0x18000c053  push    rsi
0x18000c054  push    rdi
0x18000c055  sub     rsp, 28h
0x18000c059  mov     rbx, r8
0x18000c05c  mov     rsi, rdx
0x18000c05f  mov     rbp, rcx
0x18000c062  test    rdx, rdx
0x18000c065  jz      short loc_18000C0B4
0x18000c067  test    rbx, rbx
0x18000c06a  jz      short loc_18000C0B4
0x18000c06c  add     rcx, 20h ; ' '; lpCriticalSection
0x18000c070  call    cs:__imp_EnterCriticalSection
0x18000c076  lea     rcx, [rbp+8]; this
0x18000c07a  mov     [rsp+48h+arg_8], 0
0x18000c083  mov     r8, rbx; unsigned __int16 *
0x18000c086  mov     rdx, rsi; unsigned __int16 *
0x18000c089  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000c08e  lea     rcx, [rbp+20h]; lpCriticalSection
0x18000c092  mov     ebx, eax
0x18000c094  call    cs:__imp_LeaveCriticalSection
0x18000c09a  neg     ebx
0x18000c09c  lea     rcx, [rsp+48h+arg_8]
0x18000c0a1  sbb     ebx, ebx
0x18000c0a3  not     ebx
0x18000c0a5  and     ebx, 8007000Eh
0x18000c0ab  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c0b0  mov     eax, ebx
0x18000c0b2  jmp     short loc_18000C0B9
0x18000c0b4  mov     eax, 80070057h
0x18000c0b9  add     rsp, 28h
0x18000c0bd  pop     rdi
0x18000c0be  pop     rsi
0x18000c0bf  pop     rbp
0x18000c0c0  pop     rbx
0x18000c0c1  retn
```
