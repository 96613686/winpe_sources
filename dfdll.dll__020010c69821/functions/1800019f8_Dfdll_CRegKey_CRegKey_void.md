# Dfdll::CRegKey::~CRegKey(void)

- ea: `0x1800019f8`
- end: `0x180001a64`
- name: `??1CRegKey@Dfdll@@UEAA@XZ`
- size: `108`
- prototype: `void __fastcall(Dfdll::CRegKey *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180001cd0`
- `0x180005400`
- `0x180006180`
- `0x18001f09e`
- `0x18001f152`
- `0x18001f19a`

## callees

- `0x1800019f8`
- `0x180012b30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180001a14`
- `ADVAPI32!RegCloseKey` at `0x180001a14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dfdll::CRegKey::~CRegKey(Dfdll::CRegKey *this, const struct std::nothrow_t *a2)
{
  HKEY v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &Dfdll::CRegKey::`vftable';
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
    RegCloseKey(v3);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 3) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 )
    operator delete(v4, a2);
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 3) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 2) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x1800019f8  push    rbx
0x1800019fa  sub     rsp, 20h
0x1800019fe  mov     rbx, rcx
0x180001a01  lea     rax, ??_7CRegKey@Dfdll@@6B@; const Dfdll::CRegKey::`vftable'
0x180001a08  mov     [rcx], rax
0x180001a0b  mov     rcx, [rcx+8]; hKey
0x180001a0f  test    rcx, rcx
0x180001a12  jz      short loc_180001A1A
0x180001a14  call    cs:__imp_RegCloseKey
0x180001a1a  and     qword ptr [rbx+8], 0
0x180001a1f  lea     rax, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180001a26  mov     [rbx+10h], rax
0x180001a2a  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180001a31  mov     [rbx+18h], rax
0x180001a35  mov     rcx, [rbx+20h]; void *
0x180001a39  test    rcx, rcx
0x180001a3c  jz      short loc_180001A43
0x180001a3e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001a43  and     qword ptr [rbx+20h], 0
0x180001a48  and     dword ptr [rbx+28h], 0
0x180001a4c  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001a53  mov     [rbx+18h], rax
0x180001a57  mov     [rbx+10h], rax
0x180001a5b  mov     [rbx], rax
0x180001a5e  add     rsp, 20h
0x180001a62  pop     rbx
0x180001a63  retn
```
