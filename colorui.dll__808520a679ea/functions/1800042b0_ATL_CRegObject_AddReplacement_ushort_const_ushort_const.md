# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x1800042b0`
- end: `0x18000430c`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `92`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003ff0`
- `0x1800042b0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800042d0`
- `KERNEL32!EnterCriticalSection` at `0x1800042d0`
- `KERNEL32!LeaveCriticalSection` at `0x1800042eb`
- `KERNEL32!LeaveCriticalSection` at `0x1800042eb`

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
0x1800042b0  push    rbx
0x1800042b2  push    rbp
0x1800042b3  push    rsi
0x1800042b4  push    rdi
0x1800042b5  sub     rsp, 28h
0x1800042b9  mov     rbx, r8
0x1800042bc  mov     rsi, rdx
0x1800042bf  mov     rbp, rcx
0x1800042c2  test    rdx, rdx
0x1800042c5  jz      short loc_1800042FE
0x1800042c7  test    rbx, rbx
0x1800042ca  jz      short loc_1800042FE
0x1800042cc  add     rcx, 20h ; ' '; lpCriticalSection
0x1800042d0  call    cs:__imp_EnterCriticalSection
0x1800042d6  lea     rcx, [rbp+8]; this
0x1800042da  mov     r8, rbx; unsigned __int16 *
0x1800042dd  mov     rdx, rsi; unsigned __int16 *
0x1800042e0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800042e5  lea     rcx, [rbp+20h]; lpCriticalSection
0x1800042e9  mov     ebx, eax
0x1800042eb  call    cs:__imp_LeaveCriticalSection
0x1800042f1  neg     ebx
0x1800042f3  sbb     eax, eax
0x1800042f5  not     eax
0x1800042f7  and     eax, 8007000Eh
0x1800042fc  jmp     short loc_180004303
0x1800042fe  mov     eax, 80070057h
0x180004303  add     rsp, 28h
0x180004307  pop     rdi
0x180004308  pop     rsi
0x180004309  pop     rbp
0x18000430a  pop     rbx
0x18000430b  retn
```
