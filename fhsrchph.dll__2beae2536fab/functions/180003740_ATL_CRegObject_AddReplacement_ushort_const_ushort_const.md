# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003740`
- end: `0x1800037a6`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003414`
- `0x180003740`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003760`
- `KERNEL32!EnterCriticalSection` at `0x180003760`
- `KERNEL32!LeaveCriticalSection` at `0x180003784`
- `KERNEL32!LeaveCriticalSection` at `0x180003784`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx

  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v6 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180003740  push    rbx
0x180003742  push    rbp
0x180003743  push    rsi
0x180003744  push    rdi
0x180003745  sub     rsp, 28h
0x180003749  mov     rbx, r8
0x18000374c  mov     rsi, rdx
0x18000374f  mov     rbp, rcx
0x180003752  test    rdx, rdx
0x180003755  jz      short loc_180003798
0x180003757  test    rbx, rbx
0x18000375a  jz      short loc_180003798
0x18000375c  add     rcx, 20h ; ' '; lpCriticalSection
0x180003760  call    cs:__imp_EnterCriticalSection
0x180003766  mov     [rsp+48h+arg_8], 0
0x18000376f  lea     rcx, [rbp+8]; this
0x180003773  mov     r8, rbx; unsigned __int16 *
0x180003776  mov     rdx, rsi; unsigned __int16 *
0x180003779  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000377e  mov     ebx, eax
0x180003780  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003784  call    cs:__imp_LeaveCriticalSection
0x18000378a  nop
0x18000378b  neg     ebx
0x18000378d  sbb     eax, eax
0x18000378f  not     eax
0x180003791  and     eax, 8007000Eh
0x180003796  jmp     short loc_18000379D
0x180003798  mov     eax, 80070057h
0x18000379d  add     rsp, 28h
0x1800037a1  pop     rdi
0x1800037a2  pop     rsi
0x1800037a3  pop     rbp
0x1800037a4  pop     rbx
0x1800037a5  retn
```
