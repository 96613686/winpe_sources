# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x18000e050`
- end: `0x18000e0b6`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dc5c`
- `0x18000e050`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e070`
- `KERNEL32!EnterCriticalSection` at `0x18000e070`
- `KERNEL32!LeaveCriticalSection` at `0x18000e094`
- `KERNEL32!LeaveCriticalSection` at `0x18000e094`

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
0x18000e050  push    rbx
0x18000e052  push    rbp
0x18000e053  push    rsi
0x18000e054  push    rdi
0x18000e055  sub     rsp, 28h
0x18000e059  mov     rbx, r8
0x18000e05c  mov     rsi, rdx
0x18000e05f  mov     rbp, rcx
0x18000e062  test    rdx, rdx
0x18000e065  jz      short loc_18000E0A8
0x18000e067  test    rbx, rbx
0x18000e06a  jz      short loc_18000E0A8
0x18000e06c  add     rcx, 20h ; ' '; lpCriticalSection
0x18000e070  call    cs:__imp_EnterCriticalSection
0x18000e076  mov     [rsp+48h+arg_8], 0
0x18000e07f  lea     rcx, [rbp+8]; this
0x18000e083  mov     r8, rbx; unsigned __int16 *
0x18000e086  mov     rdx, rsi; unsigned __int16 *
0x18000e089  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000e08e  mov     ebx, eax
0x18000e090  lea     rcx, [rbp+20h]; lpCriticalSection
0x18000e094  call    cs:__imp_LeaveCriticalSection
0x18000e09a  nop
0x18000e09b  neg     ebx
0x18000e09d  sbb     eax, eax
0x18000e09f  not     eax
0x18000e0a1  and     eax, 8007000Eh
0x18000e0a6  jmp     short loc_18000E0AD
0x18000e0a8  mov     eax, 80070057h
0x18000e0ad  add     rsp, 28h
0x18000e0b1  pop     rdi
0x18000e0b2  pop     rsi
0x18000e0b3  pop     rbp
0x18000e0b4  pop     rbx
0x18000e0b5  retn
```
