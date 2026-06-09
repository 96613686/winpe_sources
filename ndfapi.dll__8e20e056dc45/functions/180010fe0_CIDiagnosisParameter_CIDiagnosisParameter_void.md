# CIDiagnosisParameter::~CIDiagnosisParameter(void)

- ea: `0x180010fe0`
- end: `0x180011055`
- name: `??1CIDiagnosisParameter@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(CIDiagnosisParameter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011330`

## callees

- `0x180010fe0`
- `0x180021010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011049`
- `KERNEL32!DeleteCriticalSection` at `0x180011049`

## pseudocode

```c
void __fastcall CIDiagnosisParameter::~CIDiagnosisParameter(CIDiagnosisParameter *this)
{
  volatile signed __int32 *v1; // rdx
  volatile signed __int32 *v3; // rdx

  v1 = (volatile signed __int32 *)(*((_QWORD *)this + 9) - 24LL);
  *(_QWORD *)this = &CIDiagnosisParameter::`vftable';
  if ( _InterlockedExchangeAdd(v1 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v1 + 8LL))(*(_QWORD *)v1);
  v3 = (volatile signed __int32 *)(*((_QWORD *)this + 8) - 24LL);
  if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180010fe0  push    rbx
0x180010fe2  sub     rsp, 20h
0x180010fe6  mov     rdx, [rcx+48h]
0x180010fea  lea     rax, ??_7CIDiagnosisParameter@@6B@; const CIDiagnosisParameter::`vftable'
0x180010ff1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180010ff5  mov     [rcx], rax
0x180010ff8  or      eax, 0FFFFFFFFh
0x180010ffb  mov     rbx, rcx
0x180010ffe  lock xadd [rdx+10h], eax
0x180011003  sub     eax, 1
0x180011006  jg      short loc_180011017
0x180011008  mov     rcx, [rdx]
0x18001100b  mov     rax, [rcx]
0x18001100e  mov     rax, [rax+8]
0x180011012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011017  mov     rdx, [rbx+40h]
0x18001101b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001101f  or      eax, 0FFFFFFFFh
0x180011022  lock xadd [rdx+10h], eax
0x180011027  sub     eax, 1
0x18001102a  jg      short loc_18001103B
0x18001102c  mov     rcx, [rdx]
0x18001102f  mov     rax, [rcx]
0x180011032  mov     rax, [rax+8]
0x180011036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001103b  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001103f  cmp     byte ptr [rcx+28h], 0
0x180011043  jz      short loc_18001104F
0x180011045  mov     byte ptr [rcx+28h], 0
0x180011049  call    cs:__imp_DeleteCriticalSection
0x18001104f  add     rsp, 20h
0x180011053  pop     rbx
0x180011054  retn
```
