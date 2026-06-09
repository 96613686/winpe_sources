# ATL::CDacl::~CDacl(void)

- ea: `0x180008e6c`
- end: `0x180008ea7`
- name: `??1CDacl@ATL@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(ATL::CDacl *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180009460`
- `0x18000c478`
- `0x18002d1b6`

## callees

- `0x180008bf8`
- `0x18000dfd0`

## import_xrefs

- `msvcrt!free` at `0x180008ea0`

## pseudocode

```c
void __fastcall ATL::CDacl::~CDacl(ATL::CDacl *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &ATL::CDacl::`vftable';
  ATL::CDacl::RemoveAllAces(this);
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>((__int64)this + 24);
  v2 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)this = &ATL::CAcl::`vftable';
  free(v2);
}

```

## disassembly

```asm
0x180008e6c  push    rbx
0x180008e6e  sub     rsp, 20h
0x180008e72  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180008e79  mov     rbx, rcx
0x180008e7c  mov     [rcx], rax
0x180008e7f  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180008e84  lea     rcx, [rbx+18h]
0x180008e88  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x180008e8d  mov     rcx, [rbx+8]
0x180008e91  lea     rax, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x180008e98  mov     [rbx], rax
0x180008e9b  add     rsp, 20h
0x180008e9f  pop     rbx
0x180008ea0  jmp     cs:__imp_free
```
