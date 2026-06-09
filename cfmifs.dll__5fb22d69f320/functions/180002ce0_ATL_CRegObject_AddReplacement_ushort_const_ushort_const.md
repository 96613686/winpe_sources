# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180002ce0`
- end: `0x180002d3c`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `92`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800029fc`
- `0x180002ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d00`

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
0x180002ce0  push    rbx
0x180002ce2  push    rbp
0x180002ce3  push    rsi
0x180002ce4  push    rdi
0x180002ce5  sub     rsp, 28h
0x180002ce9  mov     rbx, r8
0x180002cec  mov     rsi, rdx
0x180002cef  mov     rbp, rcx
0x180002cf2  test    rdx, rdx
0x180002cf5  jz      short loc_180002D2E
0x180002cf7  test    rbx, rbx
0x180002cfa  jz      short loc_180002D2E
0x180002cfc  add     rcx, 20h ; ' '; lpCriticalSection
0x180002d00  call    cs:__imp_EnterCriticalSection
0x180002d06  lea     rcx, [rbp+8]; this
0x180002d0a  mov     r8, rbx; unsigned __int16 *
0x180002d0d  mov     rdx, rsi; unsigned __int16 *
0x180002d10  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180002d15  lea     rcx, [rbp+20h]; lpCriticalSection
0x180002d19  mov     ebx, eax
0x180002d1b  call    cs:__imp_LeaveCriticalSection
0x180002d21  neg     ebx
0x180002d23  sbb     eax, eax
0x180002d25  not     eax
0x180002d27  and     eax, 8007000Eh
0x180002d2c  jmp     short loc_180002D33
0x180002d2e  mov     eax, 80070057h
0x180002d33  add     rsp, 28h
0x180002d37  pop     rdi
0x180002d38  pop     rsi
0x180002d39  pop     rbp
0x180002d3a  pop     rbx
0x180002d3b  retn
```
