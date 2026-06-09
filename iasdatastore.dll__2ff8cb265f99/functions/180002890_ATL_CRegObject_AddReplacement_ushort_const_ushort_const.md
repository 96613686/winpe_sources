# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180002890`
- end: `0x1800028f6`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000252c`
- `0x180002890`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800028b0`
- `KERNEL32!EnterCriticalSection` at `0x1800028b0`
- `KERNEL32!LeaveCriticalSection` at `0x1800028d4`
- `KERNEL32!LeaveCriticalSection` at `0x1800028d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180002890  push    rbx
0x180002892  push    rbp
0x180002893  push    rsi
0x180002894  push    rdi
0x180002895  sub     rsp, 28h
0x180002899  mov     rbx, r8
0x18000289c  mov     rsi, rdx
0x18000289f  mov     rbp, rcx
0x1800028a2  test    rdx, rdx
0x1800028a5  jz      short loc_1800028E8
0x1800028a7  test    rbx, rbx
0x1800028aa  jz      short loc_1800028E8
0x1800028ac  add     rcx, 20h ; ' '; lpCriticalSection
0x1800028b0  call    cs:__imp_EnterCriticalSection
0x1800028b6  mov     [rsp+48h+arg_8], 0
0x1800028bf  lea     rcx, [rbp+8]; this
0x1800028c3  mov     r8, rbx; unsigned __int16 *
0x1800028c6  mov     rdx, rsi; unsigned __int16 *
0x1800028c9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800028ce  mov     ebx, eax
0x1800028d0  lea     rcx, [rbp+20h]; lpCriticalSection
0x1800028d4  call    cs:__imp_LeaveCriticalSection
0x1800028da  nop
0x1800028db  neg     ebx
0x1800028dd  sbb     eax, eax
0x1800028df  not     eax
0x1800028e1  and     eax, 8007000Eh
0x1800028e6  jmp     short loc_1800028ED
0x1800028e8  mov     eax, 80070057h
0x1800028ed  add     rsp, 28h
0x1800028f1  pop     rdi
0x1800028f2  pop     rsi
0x1800028f3  pop     rbp
0x1800028f4  pop     rbx
0x1800028f5  retn
```
