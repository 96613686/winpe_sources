# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x1800060e0`
- end: `0x180006153`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c78`

## callees

- `0x180005da0`
- `0x1800060e0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006100`
- `KERNEL32!EnterCriticalSection` at `0x180006100`
- `KERNEL32!LeaveCriticalSection` at `0x18000612a`
- `KERNEL32!LeaveCriticalSection` at `0x18000612a`

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
0x1800060e0  push    rbx
0x1800060e2  push    rbp
0x1800060e3  push    rsi
0x1800060e4  push    rdi
0x1800060e5  sub     rsp, 28h
0x1800060e9  mov     rbx, r8
0x1800060ec  mov     rsi, rdx
0x1800060ef  mov     rbp, rcx
0x1800060f2  test    rdx, rdx
0x1800060f5  jz      short loc_180006144
0x1800060f7  test    rbx, rbx
0x1800060fa  jz      short loc_180006144
0x1800060fc  add     rcx, 20h ; ' '; lpCriticalSection
0x180006100  call    cs:__imp_EnterCriticalSection
0x180006107  nop     dword ptr [rax+rax+00h]
0x18000610c  mov     [rsp+48h+arg_8], 0
0x180006115  lea     rcx, [rbp+8]; this
0x180006119  mov     r8, rbx; unsigned __int16 *
0x18000611c  mov     rdx, rsi; unsigned __int16 *
0x18000611f  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006124  mov     ebx, eax
0x180006126  lea     rcx, [rbp+20h]; lpCriticalSection
0x18000612a  call    cs:__imp_LeaveCriticalSection
0x180006131  nop     dword ptr [rax+rax+00h]
0x180006136  nop
0x180006137  neg     ebx
0x180006139  sbb     eax, eax
0x18000613b  not     eax
0x18000613d  and     eax, 8007000Eh
0x180006142  jmp     short loc_180006149
0x180006144  mov     eax, 80070057h
0x180006149  add     rsp, 28h
0x18000614d  pop     rdi
0x18000614e  pop     rsi
0x18000614f  pop     rbp
0x180006150  pop     rbx
0x180006151  retn
```
