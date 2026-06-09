# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x1800023f0`
- end: `0x18000244c`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `92`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002178`
- `0x1800023f0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000242b`
- `KERNEL32!LeaveCriticalSection` at `0x18000242b`
- `KERNEL32!EnterCriticalSection` at `0x180002410`
- `KERNEL32!EnterCriticalSection` at `0x180002410`

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
0x1800023f0  push    rbx
0x1800023f2  push    rbp
0x1800023f3  push    rsi
0x1800023f4  push    rdi
0x1800023f5  sub     rsp, 28h
0x1800023f9  mov     rbx, r8
0x1800023fc  mov     rsi, rdx
0x1800023ff  mov     rbp, rcx
0x180002402  test    rdx, rdx
0x180002405  jz      short loc_18000243E
0x180002407  test    rbx, rbx
0x18000240a  jz      short loc_18000243E
0x18000240c  add     rcx, 20h ; ' '; lpCriticalSection
0x180002410  call    cs:__imp_EnterCriticalSection
0x180002416  lea     rcx, [rbp+8]; this
0x18000241a  mov     r8, rbx; unsigned __int16 *
0x18000241d  mov     rdx, rsi; unsigned __int16 *
0x180002420  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180002425  lea     rcx, [rbp+20h]; lpCriticalSection
0x180002429  mov     ebx, eax
0x18000242b  call    cs:__imp_LeaveCriticalSection
0x180002431  neg     ebx
0x180002433  sbb     eax, eax
0x180002435  not     eax
0x180002437  and     eax, 8007000Eh
0x18000243c  jmp     short loc_180002443
0x18000243e  mov     eax, 80070057h
0x180002443  add     rsp, 28h
0x180002447  pop     rdi
0x180002448  pop     rsi
0x180002449  pop     rbp
0x18000244a  pop     rbx
0x18000244b  retn
```
