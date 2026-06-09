# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003070`
- end: `0x1800030e3`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000596c`

## callees

- `0x180002d90`
- `0x180003070`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800030ba`
- `KERNEL32!LeaveCriticalSection` at `0x1800030ba`
- `KERNEL32!EnterCriticalSection` at `0x180003090`
- `KERNEL32!EnterCriticalSection` at `0x180003090`

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
0x180003070  push    rbx
0x180003072  push    rbp
0x180003073  push    rsi
0x180003074  push    rdi
0x180003075  sub     rsp, 28h
0x180003079  mov     rbx, r8
0x18000307c  mov     rsi, rdx
0x18000307f  mov     rbp, rcx
0x180003082  test    rdx, rdx
0x180003085  jz      short loc_1800030D4
0x180003087  test    rbx, rbx
0x18000308a  jz      short loc_1800030D4
0x18000308c  add     rcx, 20h ; ' '; lpCriticalSection
0x180003090  call    cs:__imp_EnterCriticalSection
0x180003097  nop     dword ptr [rax+rax+00h]
0x18000309c  mov     [rsp+48h+arg_8], 0
0x1800030a5  lea     rcx, [rbp+8]; this
0x1800030a9  mov     r8, rbx; unsigned __int16 *
0x1800030ac  mov     rdx, rsi; unsigned __int16 *
0x1800030af  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800030b4  mov     ebx, eax
0x1800030b6  lea     rcx, [rbp+20h]; lpCriticalSection
0x1800030ba  call    cs:__imp_LeaveCriticalSection
0x1800030c1  nop     dword ptr [rax+rax+00h]
0x1800030c6  nop
0x1800030c7  neg     ebx
0x1800030c9  sbb     eax, eax
0x1800030cb  not     eax
0x1800030cd  and     eax, 8007000Eh
0x1800030d2  jmp     short loc_1800030D9
0x1800030d4  mov     eax, 80070057h
0x1800030d9  add     rsp, 28h
0x1800030dd  pop     rdi
0x1800030de  pop     rsi
0x1800030df  pop     rbp
0x1800030e0  pop     rbx
0x1800030e1  retn
```
