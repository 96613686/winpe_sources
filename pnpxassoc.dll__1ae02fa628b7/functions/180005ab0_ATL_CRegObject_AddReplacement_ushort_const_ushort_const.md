# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180005ab0`
- end: `0x180005b0c`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `92`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800056c8`
- `0x180005ab0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180005aeb`
- `KERNEL32!LeaveCriticalSection` at `0x180005aeb`
- `KERNEL32!EnterCriticalSection` at `0x180005ad0`
- `KERNEL32!EnterCriticalSection` at `0x180005ad0`

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
0x180005ab0  push    rbx
0x180005ab2  push    rbp
0x180005ab3  push    rsi
0x180005ab4  push    rdi
0x180005ab5  sub     rsp, 28h
0x180005ab9  mov     rbx, r8
0x180005abc  mov     rsi, rdx
0x180005abf  mov     rbp, rcx
0x180005ac2  test    rdx, rdx
0x180005ac5  jz      short loc_180005AFE
0x180005ac7  test    rbx, rbx
0x180005aca  jz      short loc_180005AFE
0x180005acc  add     rcx, 20h ; ' '; lpCriticalSection
0x180005ad0  call    cs:__imp_EnterCriticalSection
0x180005ad6  lea     rcx, [rbp+8]; this
0x180005ada  mov     r8, rbx; unsigned __int16 *
0x180005add  mov     rdx, rsi; unsigned __int16 *
0x180005ae0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005ae5  lea     rcx, [rbp+20h]; lpCriticalSection
0x180005ae9  mov     ebx, eax
0x180005aeb  call    cs:__imp_LeaveCriticalSection
0x180005af1  neg     ebx
0x180005af3  sbb     eax, eax
0x180005af5  not     eax
0x180005af7  and     eax, 8007000Eh
0x180005afc  jmp     short loc_180005B03
0x180005afe  mov     eax, 80070057h
0x180005b03  add     rsp, 28h
0x180005b07  pop     rdi
0x180005b08  pop     rsi
0x180005b09  pop     rbp
0x180005b0a  pop     rbx
0x180005b0b  retn
```
