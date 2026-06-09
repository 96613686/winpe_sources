# Dfdll::CCriticialSection::~CCriticialSection(void)

- ea: `0x180008b8c`
- end: `0x180008bf1`
- name: `??1CCriticialSection@Dfdll@@UEAA@XZ`
- size: `101`
- prototype: `void __fastcall(Dfdll::CCriticialSection *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800091d0`
- `0x18001f8e0`

## callees

- `0x180008b8c`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008ba3`
- `KERNEL32!DeleteCriticalSection` at `0x180008ba3`

## pseudocode

```c
void __fastcall Dfdll::CCriticialSection::~CCriticialSection(Dfdll::CCriticialSection *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &Dfdll::CCriticialSection::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *(_QWORD *)this = &Dfdll::CSynchronizationObject::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CPointerHolder<Dfdll::CString>::`vftable';
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v2 )
    (**v2)(v2, 1);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x180008b8c  push    rbx
0x180008b8e  sub     rsp, 20h
0x180008b92  mov     rbx, rcx
0x180008b95  lea     rax, ??_7CCriticialSection@Dfdll@@6B@; const Dfdll::CCriticialSection::`vftable'
0x180008b9c  mov     [rcx], rax
0x180008b9f  add     rcx, 18h; lpCriticalSection
0x180008ba3  call    cs:__imp_DeleteCriticalSection
0x180008ba9  lea     rax, ??_7CSynchronizationObject@Dfdll@@6B@; const Dfdll::CSynchronizationObject::`vftable'
0x180008bb0  mov     [rbx], rax
0x180008bb3  lea     rax, ??_7?$CPointerHolder@VCString@Dfdll@@@Dfdll@@6B@; const Dfdll::CPointerHolder<Dfdll::CString>::`vftable'
0x180008bba  mov     [rbx+8], rax
0x180008bbe  mov     rcx, [rbx+10h]
0x180008bc2  test    rcx, rcx
0x180008bc5  jz      short loc_180008BD8
0x180008bc7  mov     rax, [rcx]
0x180008bca  mov     edx, 1
0x180008bcf  mov     rax, [rax]
0x180008bd2  call    cs:__guard_dispatch_icall_fptr
0x180008bd8  and     qword ptr [rbx+10h], 0
0x180008bdd  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180008be4  mov     [rbx+8], rax
0x180008be8  mov     [rbx], rax
0x180008beb  add     rsp, 20h
0x180008bef  pop     rbx
0x180008bf0  retn
```
