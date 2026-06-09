# PsCreateHash(SIP_SUBJECTINFO_ const *,ulong *,SIP_INDIRECT_DATA_ *)

- ea: `0x1800049c0`
- end: `0x180004a36`
- name: `?PsCreateHash@@YAHPEBUSIP_SUBJECTINFO_@@PEAKPEAUSIP_INDIRECT_DATA_@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(const struct SIP_SUBJECTINFO_ *, unsigned int *, struct SIP_INDIRECT_DATA_ *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001014`
- `0x1800037bc`
- `0x1800049c0`
- `0x180006010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180004a1e`
- `KERNEL32!SetLastError` at `0x180004a1e`

## pseudocode

```c
_BOOL8 __fastcall PsCreateHash(const struct SIP_SUBJECTINFO_ *a1, unsigned int *a2, struct SIP_INDIRECT_DATA_ *a3)
{
  DWORD Hash; // ebx
  SipProvider *v7; // rdi

  Hash = 8;
  v7 = (SipProvider *)operator new(8u);
  if ( !v7
    || (*(_QWORD *)v7 = &PsSipProvider::`vftable',
        Hash = SipProvider::CreateHash(v7, a1, a2, a3),
        (**(void (__fastcall ***)(SipProvider *, __int64))v7)(v7, 1),
        Hash) )
  {
    SetLastError(Hash);
  }
  return Hash == 0;
}

```

## disassembly

```asm
0x1800049c0  push    rbx
0x1800049c2  push    rbp
0x1800049c3  push    rsi
0x1800049c4  push    rdi
0x1800049c5  push    r14
0x1800049c7  sub     rsp, 20h
0x1800049cb  mov     r14, rcx
0x1800049ce  mov     ebx, 8
0x1800049d3  mov     ecx, ebx; Size
0x1800049d5  mov     rsi, r8
0x1800049d8  mov     rbp, rdx
0x1800049db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800049e0  mov     rdi, rax
0x1800049e3  test    rax, rax
0x1800049e6  jz      short loc_180004A1C
0x1800049e8  lea     rax, ??_7PsSipProvider@@6B@; const PsSipProvider::`vftable'
0x1800049ef  mov     r9, rsi; struct SIP_INDIRECT_DATA_ *
0x1800049f2  mov     r8, rbp; unsigned int *
0x1800049f5  mov     [rdi], rax
0x1800049f8  mov     rdx, r14; struct SIP_SUBJECTINFO_ *
0x1800049fb  mov     rcx, rdi; this
0x1800049fe  call    ?CreateHash@SipProvider@@QEAAKPEBUSIP_SUBJECTINFO_@@PEAKPEAUSIP_INDIRECT_DATA_@@@Z; SipProvider::CreateHash(SIP_SUBJECTINFO_ const *,ulong *,SIP_INDIRECT_DATA_ *)
0x180004a03  mov     ebx, eax
0x180004a05  mov     rcx, [rdi]
0x180004a08  mov     edx, 1
0x180004a0d  mov     rax, [rcx]
0x180004a10  mov     rcx, rdi
0x180004a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a18  test    ebx, ebx
0x180004a1a  jz      short loc_180004A24
0x180004a1c  mov     ecx, ebx; dwErrCode
0x180004a1e  call    cs:__imp_SetLastError
0x180004a24  xor     eax, eax
0x180004a26  test    ebx, ebx
0x180004a28  setz    al
0x180004a2b  add     rsp, 20h
0x180004a2f  pop     r14
0x180004a31  pop     rdi
0x180004a32  pop     rsi
0x180004a33  pop     rbp
0x180004a34  pop     rbx
0x180004a35  retn
```
