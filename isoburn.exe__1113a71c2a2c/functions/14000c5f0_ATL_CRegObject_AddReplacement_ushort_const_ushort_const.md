# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x14000c5f0`
- end: `0x14000c64c`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `92`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000c44c`
- `0x14000c5f0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000c610`
- `KERNEL32!EnterCriticalSection` at `0x14000c610`
- `KERNEL32!LeaveCriticalSection` at `0x14000c62b`
- `KERNEL32!LeaveCriticalSection` at `0x14000c62b`

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
0x14000c5f0  push    rbx
0x14000c5f2  push    rbp
0x14000c5f3  push    rsi
0x14000c5f4  push    rdi
0x14000c5f5  sub     rsp, 28h
0x14000c5f9  mov     rbx, r8
0x14000c5fc  mov     rsi, rdx
0x14000c5ff  mov     rbp, rcx
0x14000c602  test    rdx, rdx
0x14000c605  jz      short loc_14000C63E
0x14000c607  test    rbx, rbx
0x14000c60a  jz      short loc_14000C63E
0x14000c60c  add     rcx, 20h ; ' '; lpCriticalSection
0x14000c610  call    cs:__imp_EnterCriticalSection
0x14000c616  lea     rcx, [rbp+8]; this
0x14000c61a  mov     r8, rbx; unsigned __int16 *
0x14000c61d  mov     rdx, rsi; unsigned __int16 *
0x14000c620  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000c625  lea     rcx, [rbp+20h]; lpCriticalSection
0x14000c629  mov     ebx, eax
0x14000c62b  call    cs:__imp_LeaveCriticalSection
0x14000c631  neg     ebx
0x14000c633  sbb     eax, eax
0x14000c635  not     eax
0x14000c637  and     eax, 8007000Eh
0x14000c63c  jmp     short loc_14000C643
0x14000c63e  mov     eax, 80070057h
0x14000c643  add     rsp, 28h
0x14000c647  pop     rdi
0x14000c648  pop     rsi
0x14000c649  pop     rbp
0x14000c64a  pop     rbx
0x14000c64b  retn
```
