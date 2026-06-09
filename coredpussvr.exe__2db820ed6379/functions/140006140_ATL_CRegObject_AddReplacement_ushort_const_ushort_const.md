# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x140006140`
- end: `0x1400061b3`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008460`
- `0x14000878c`

## callees

- `0x140005e4c`
- `0x140006140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006160`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006160`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000618a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000618a`

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
0x140006140  push    rbx
0x140006142  push    rbp
0x140006143  push    rsi
0x140006144  push    rdi
0x140006145  sub     rsp, 28h
0x140006149  mov     rbx, r8
0x14000614c  mov     rsi, rdx
0x14000614f  mov     rbp, rcx
0x140006152  test    rdx, rdx
0x140006155  jz      short loc_1400061A4
0x140006157  test    rbx, rbx
0x14000615a  jz      short loc_1400061A4
0x14000615c  add     rcx, 20h ; ' '; lpCriticalSection
0x140006160  call    cs:__imp_EnterCriticalSection
0x140006167  nop     dword ptr [rax+rax+00h]
0x14000616c  mov     [rsp+48h+arg_8], 0
0x140006175  lea     rcx, [rbp+8]; this
0x140006179  mov     r8, rbx; unsigned __int16 *
0x14000617c  mov     rdx, rsi; unsigned __int16 *
0x14000617f  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140006184  mov     ebx, eax
0x140006186  lea     rcx, [rbp+20h]; lpCriticalSection
0x14000618a  call    cs:__imp_LeaveCriticalSection
0x140006191  nop     dword ptr [rax+rax+00h]
0x140006196  nop
0x140006197  neg     ebx
0x140006199  sbb     eax, eax
0x14000619b  not     eax
0x14000619d  and     eax, 8007000Eh
0x1400061a2  jmp     short loc_1400061A9
0x1400061a4  mov     eax, 80070057h
0x1400061a9  add     rsp, 28h
0x1400061ad  pop     rdi
0x1400061ae  pop     rsi
0x1400061af  pop     rbp
0x1400061b0  pop     rbx
0x1400061b1  retn
```
