# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003040`
- end: `0x1800030a6`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002d88`
- `0x180003040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003084`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003084`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003060`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003060`

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
0x180003040  push    rbx
0x180003042  push    rbp
0x180003043  push    rsi
0x180003044  push    rdi
0x180003045  sub     rsp, 28h
0x180003049  mov     rbx, r8
0x18000304c  mov     rsi, rdx
0x18000304f  mov     rbp, rcx
0x180003052  test    rdx, rdx
0x180003055  jz      short loc_180003098
0x180003057  test    rbx, rbx
0x18000305a  jz      short loc_180003098
0x18000305c  add     rcx, 20h ; ' '; lpCriticalSection
0x180003060  call    cs:__imp_EnterCriticalSection
0x180003066  mov     [rsp+48h+arg_8], 0
0x18000306f  lea     rcx, [rbp+8]; this
0x180003073  mov     r8, rbx; unsigned __int16 *
0x180003076  mov     rdx, rsi; unsigned __int16 *
0x180003079  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000307e  mov     ebx, eax
0x180003080  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003084  call    cs:__imp_LeaveCriticalSection
0x18000308a  nop
0x18000308b  neg     ebx
0x18000308d  sbb     eax, eax
0x18000308f  not     eax
0x180003091  and     eax, 8007000Eh
0x180003096  jmp     short loc_18000309D
0x180003098  mov     eax, 80070057h
0x18000309d  add     rsp, 28h
0x1800030a1  pop     rdi
0x1800030a2  pop     rsi
0x1800030a3  pop     rbp
0x1800030a4  pop     rbx
0x1800030a5  retn
```
