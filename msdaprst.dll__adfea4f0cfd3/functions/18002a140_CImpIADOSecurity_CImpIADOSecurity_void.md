# CImpIADOSecurity::~CImpIADOSecurity(void)

- ea: `0x18002a140`
- end: `0x18002a199`
- name: `??1CImpIADOSecurity@@QEAA@XZ`
- size: `89`
- prototype: `void __fastcall(CImpIADOSecurity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013f2c`
- `0x18002fc53`

## callees

- `0x18002a830`
- `0x18002a8a0`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002a18d`

## pseudocode

```c
void __fastcall CImpIADOSecurity::~CImpIADOSecurity(CImpIADOSecurity *this)
{
  *(_QWORD *)this = &CImpIADOSecurity::`vftable'{for `IADOSecurity'};
  *((_QWORD *)this + 1) = &CImpIADOSecurity::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 2) = &CImpIADOSecurity::`vftable'{for `IObjectSafety'};
  CImpIADOSecurity::SetURL(this, 0);
  CImpIADOSecurity::SetSite((CImpIADOSecurity *)((char *)this + 8), 0);
  MPDeleteCriticalSection((char *)this + 48);
}

```

## disassembly

```asm
0x18002a140  mov     [rsp+arg_0], rbx
0x18002a145  push    rdi
0x18002a146  sub     rsp, 20h
0x18002a14a  lea     rax, ??_7CImpIADOSecurity@@6BIADOSecurity@@@; const CImpIADOSecurity::`vftable'{for `IADOSecurity'}
0x18002a151  xor     edx, edx; unsigned __int16 *
0x18002a153  mov     [rcx], rax
0x18002a156  mov     rdi, rcx
0x18002a159  lea     rax, ??_7CImpIADOSecurity@@6BIObjectWithSite@@@; const CImpIADOSecurity::`vftable'{for `IObjectWithSite'}
0x18002a160  mov     [rcx+8], rax
0x18002a164  lea     rax, ??_7CImpIADOSecurity@@6BIObjectSafety@@@; const CImpIADOSecurity::`vftable'{for `IObjectSafety'}
0x18002a16b  mov     [rcx+10h], rax
0x18002a16f  call    ?SetURL@CImpIADOSecurity@@UEAAJPEAG@Z; CImpIADOSecurity::SetURL(ushort *)
0x18002a174  xor     edx, edx; struct IUnknown *
0x18002a176  lea     rcx, [rdi+8]; this
0x18002a17a  call    ?SetSite@CImpIADOSecurity@@UEAAJPEAUIUnknown@@@Z; CImpIADOSecurity::SetSite(IUnknown *)
0x18002a17f  lea     rcx, [rdi+30h]
0x18002a183  mov     rbx, [rsp+28h+arg_0]
0x18002a188  add     rsp, 20h
0x18002a18c  pop     rdi
0x18002a18d  jmp     cs:__imp_MPDeleteCriticalSection
```
