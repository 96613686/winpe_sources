# PrnExcept::PropertyElement::PropertyElement(wchar_t const *,tagVARIANT const *)

- ea: `0x1400169a4`
- end: `0x140016a48`
- name: `??0PropertyElement@PrnExcept@@QEAA@PEB_WPEBUtagVARIANT@@@Z`
- size: `164`
- prototype: `PrnExcept::PropertyElement *__fastcall(PrnExcept::PropertyElement *this, const wchar_t *, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140016f70`

## callees

- `0x14001500c`
- `0x1400169a4`
- `0x14004650c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1400169fd`
- `OLEAUT32!__imp_VariantInit` at `0x1400169fd`
- `OLEAUT32!__imp_VariantCopy` at `0x140016a13`
- `OLEAUT32!__imp_VariantCopy` at `0x140016a13`

## pseudocode

```c
PrnExcept::PropertyElement *__fastcall PrnExcept::PropertyElement::PropertyElement(
        PrnExcept::PropertyElement *this,
        const wchar_t *a2,
        const struct tagVARIANT *a3)
{
  NCoreLibrary::TString *v5; // rcx
  int v6; // eax
  int v7; // edx
  const char *v8; // r8
  unsigned int v9; // r9d
  HRESULT v10; // eax
  int v11; // edx
  const char *v12; // r8
  unsigned int v13; // r9d

  *((_DWORD *)this + 2) = 1802398836;
  *((_QWORD *)this + 2) = this;
  *((_QWORD *)this + 3) = this;
  *(_QWORD *)this = &PrnExcept::PropertyElement::`vftable';
  v5 = (PrnExcept::PropertyElement *)((char *)this + 32);
  *(_QWORD *)v5 = &NCoreLibrary::TString::gszNullState;
  v6 = NCoreLibrary::TString::Update(v5, a2);
  if ( v6 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v6, v7, v8, v9);
  VariantInit((VARIANTARG *)((char *)this + 40));
  if ( a3->vt == 0x4000 )
  {
    *(_OWORD *)((char *)this + 40) = *(_OWORD *)&a3->vt;
    *((_QWORD *)this + 7) = a3->pRecInfo;
  }
  else
  {
    v10 = VariantCopy((VARIANTARG *)((char *)this + 40), a3);
    if ( v10 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v10, v11, v12, v13);
  }
  return this;
}

```

## disassembly

```asm
0x1400169a4  mov     [rsp+arg_8], rbx
0x1400169a9  mov     [rsp+arg_10], rsi
0x1400169ae  mov     [rsp+arg_0], rcx
0x1400169b3  push    rdi
0x1400169b4  sub     rsp, 20h
0x1400169b8  mov     rsi, r8
0x1400169bb  mov     rbx, rcx
0x1400169be  mov     dword ptr [rcx+8], 6B6E6C74h
0x1400169c5  mov     [rcx+10h], rcx
0x1400169c9  mov     [rcx+18h], rcx
0x1400169cd  lea     rax, ??_7PropertyElement@PrnExcept@@6B@; const PrnExcept::PropertyElement::`vftable'
0x1400169d4  mov     [rcx], rax
0x1400169d7  add     rcx, 20h ; ' '; this
0x1400169db  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PA_WA; wchar_t near * NCoreLibrary::TString::gszNullState
0x1400169e2  mov     [rcx], rax
0x1400169e5  call    ?Update@TString@NCoreLibrary@@QEAAJPEB_W@Z; NCoreLibrary::TString::Update(wchar_t const *)
0x1400169ea  test    eax, eax
0x1400169ec  jns     short loc_1400169F6
0x1400169ee  mov     ecx, eax; this
0x1400169f0  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400169f6  lea     rdi, [rbx+28h]
0x1400169fa  mov     rcx, rdi; pvarg
0x1400169fd  call    cs:__imp_VariantInit
0x140016a03  mov     eax, 4000h
0x140016a08  cmp     [rsi], ax
0x140016a0b  jz      short loc_140016A25
0x140016a0d  mov     rdx, rsi; pvargSrc
0x140016a10  mov     rcx, rdi; pvargDest
0x140016a13  call    cs:__imp_VariantCopy
0x140016a19  test    eax, eax
0x140016a1b  jns     short loc_140016A35
0x140016a1d  mov     ecx, eax; this
0x140016a1f  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140016a25  movups  xmm0, xmmword ptr [rsi]
0x140016a28  movups  xmmword ptr [rdi], xmm0
0x140016a2b  movsd   xmm1, qword ptr [rsi+10h]
0x140016a30  movsd   qword ptr [rdi+10h], xmm1
0x140016a35  mov     rax, rbx
0x140016a38  mov     rbx, [rsp+28h+arg_8]
0x140016a3d  mov     rsi, [rsp+28h+arg_10]
0x140016a42  add     rsp, 20h
0x140016a46  pop     rdi
0x140016a47  retn
```
