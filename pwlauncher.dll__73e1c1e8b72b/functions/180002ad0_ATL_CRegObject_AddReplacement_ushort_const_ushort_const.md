# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180002ad0`
- end: `0x180002b36`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002818`
- `0x180002ad0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002af0`
- `KERNEL32!EnterCriticalSection` at `0x180002af0`
- `KERNEL32!LeaveCriticalSection` at `0x180002b14`
- `KERNEL32!LeaveCriticalSection` at `0x180002b14`

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
0x180002ad0  push    rbx
0x180002ad2  push    rbp
0x180002ad3  push    rsi
0x180002ad4  push    rdi
0x180002ad5  sub     rsp, 28h
0x180002ad9  mov     rbx, r8
0x180002adc  mov     rsi, rdx
0x180002adf  mov     rbp, rcx
0x180002ae2  test    rdx, rdx
0x180002ae5  jz      short loc_180002B28
0x180002ae7  test    rbx, rbx
0x180002aea  jz      short loc_180002B28
0x180002aec  add     rcx, 20h ; ' '; lpCriticalSection
0x180002af0  call    cs:__imp_EnterCriticalSection
0x180002af6  mov     [rsp+48h+arg_8], 0
0x180002aff  lea     rcx, [rbp+8]; this
0x180002b03  mov     r8, rbx; unsigned __int16 *
0x180002b06  mov     rdx, rsi; unsigned __int16 *
0x180002b09  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180002b0e  mov     ebx, eax
0x180002b10  lea     rcx, [rbp+20h]; lpCriticalSection
0x180002b14  call    cs:__imp_LeaveCriticalSection
0x180002b1a  nop
0x180002b1b  neg     ebx
0x180002b1d  sbb     eax, eax
0x180002b1f  not     eax
0x180002b21  and     eax, 8007000Eh
0x180002b26  jmp     short loc_180002B2D
0x180002b28  mov     eax, 80070057h
0x180002b2d  add     rsp, 28h
0x180002b31  pop     rdi
0x180002b32  pop     rsi
0x180002b33  pop     rbp
0x180002b34  pop     rbx
0x180002b35  retn
```
