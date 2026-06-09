# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180002900`
- end: `0x180002966`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800025d8`
- `0x180002900`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002920`
- `KERNEL32!EnterCriticalSection` at `0x180002920`
- `KERNEL32!LeaveCriticalSection` at `0x180002944`
- `KERNEL32!LeaveCriticalSection` at `0x180002944`

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
0x180002900  push    rbx
0x180002902  push    rbp
0x180002903  push    rsi
0x180002904  push    rdi
0x180002905  sub     rsp, 28h
0x180002909  mov     rbx, r8
0x18000290c  mov     rsi, rdx
0x18000290f  mov     rbp, rcx
0x180002912  test    rdx, rdx
0x180002915  jz      short loc_180002958
0x180002917  test    rbx, rbx
0x18000291a  jz      short loc_180002958
0x18000291c  add     rcx, 20h ; ' '; lpCriticalSection
0x180002920  call    cs:__imp_EnterCriticalSection
0x180002926  mov     [rsp+48h+arg_8], 0
0x18000292f  lea     rcx, [rbp+8]; this
0x180002933  mov     r8, rbx; unsigned __int16 *
0x180002936  mov     rdx, rsi; unsigned __int16 *
0x180002939  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000293e  mov     ebx, eax
0x180002940  lea     rcx, [rbp+20h]; lpCriticalSection
0x180002944  call    cs:__imp_LeaveCriticalSection
0x18000294a  nop
0x18000294b  neg     ebx
0x18000294d  sbb     eax, eax
0x18000294f  not     eax
0x180002951  and     eax, 8007000Eh
0x180002956  jmp     short loc_18000295D
0x180002958  mov     eax, 80070057h
0x18000295d  add     rsp, 28h
0x180002961  pop     rdi
0x180002962  pop     rsi
0x180002963  pop     rbp
0x180002964  pop     rbx
0x180002965  retn
```
