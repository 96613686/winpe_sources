# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180008e80`
- end: `0x180008ef3`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bfac`
- `0x18000c224`

## callees

- `0x18000882c`
- `0x180008c2c`
- `0x180008e80`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180008ea0`
- `KERNEL32!EnterCriticalSection` at `0x180008ea0`
- `KERNEL32!LeaveCriticalSection` at `0x180008ec4`
- `KERNEL32!LeaveCriticalSection` at `0x180008ec4`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  _QWORD *v8; // [rsp+58h] [rbp+10h] BYREF

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
0x180008e80  push    rbx
0x180008e82  push    rbp
0x180008e83  push    rsi
0x180008e84  push    rdi
0x180008e85  sub     rsp, 28h
0x180008e89  mov     rbx, r8
0x180008e8c  mov     rsi, rdx
0x180008e8f  mov     rbp, rcx
0x180008e92  test    rdx, rdx
0x180008e95  jz      short loc_180008EE5
0x180008e97  test    rbx, rbx
0x180008e9a  jz      short loc_180008EE5
0x180008e9c  add     rcx, 20h ; ' '; lpCriticalSection
0x180008ea0  call    cs:__imp_EnterCriticalSection
0x180008ea6  mov     [rsp+48h+arg_8], 0
0x180008eaf  lea     rcx, [rbp+8]; this
0x180008eb3  mov     r8, rbx; unsigned __int16 *
0x180008eb6  mov     rdx, rsi; unsigned __int16 *
0x180008eb9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008ebe  mov     ebx, eax
0x180008ec0  lea     rcx, [rbp+20h]; lpCriticalSection
0x180008ec4  call    cs:__imp_LeaveCriticalSection
0x180008eca  nop
0x180008ecb  neg     ebx
0x180008ecd  sbb     ebx, ebx
0x180008ecf  not     ebx
0x180008ed1  and     ebx, 8007000Eh
0x180008ed7  lea     rcx, [rsp+48h+arg_8]
0x180008edc  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008ee1  mov     eax, ebx
0x180008ee3  jmp     short loc_180008EEA
0x180008ee5  mov     eax, 80070057h
0x180008eea  add     rsp, 28h
0x180008eee  pop     rdi
0x180008eef  pop     rsi
0x180008ef0  pop     rbp
0x180008ef1  pop     rbx
0x180008ef2  retn
```
