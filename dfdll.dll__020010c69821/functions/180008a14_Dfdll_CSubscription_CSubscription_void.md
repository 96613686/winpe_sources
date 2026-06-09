# Dfdll::CSubscription::CSubscription(void)

- ea: `0x180008a14`
- end: `0x180008b00`
- name: `??0CSubscription@Dfdll@@QEAA@XZ`
- size: `236`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x18000444c`
- `0x180004580`
- `0x180004bcc`
- `0x180006180`
- `0x180006e60`
- `0x180007040`
- `0x180007130`

## pseudocode

```c
Dfdll::CSubscription *__fastcall Dfdll::CSubscription::CSubscription(Dfdll::CSubscription *this)
{
  Dfdll::CSubscription *result; // rax

  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CBuffer<unsigned short>::`vftable';
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 5) = &Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable';
  *((_QWORD *)this + 7) = &Dfdll::CIUnknownBasedPointer<IDefinitionAppId>::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = &Dfdll::CIUnknownBasedPointer<IDefinitionAppId>::`vftable';
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = &Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable';
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 13) = &Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable';
  *((_QWORD *)this + 15) = &Dfdll::CIUnknownBasedPointer<IStore>::`vftable';
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = &Dfdll::CIUnknownBasedPointer<IIdentityAuthority>::`vftable';
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = &Dfdll::CIUnknownBasedPointer<IAppIdAuthority>::`vftable';
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = &Dfdll::CIUnknownBasedPointer<ICMS>::`vftable';
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = &Dfdll::CIUnknownBasedPointer<ICMS>::`vftable';
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 40;
  *((_OWORD *)this + 13) = SXS_INSTALL_REFERENCE_SCHEME_OPAQUESTRING;
  *((_QWORD *)this + 28) = Dfdll::Constants::Strings::InstallReferenceIdentifier;
  result = this;
  *((_QWORD *)this + 29) = 0;
  return result;
}

```

## disassembly

```asm
0x180008a14  xor     r8d, r8d
0x180008a17  lea     rdx, ??_7?$CIUnknownBasedPointer@UIDefinitionIdentity@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable'
0x180008a1e  mov     [rcx+10h], r8
0x180008a22  lea     rax, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180008a29  mov     [rcx], rax
0x180008a2c  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180008a33  mov     [rcx+8], rax
0x180008a37  lea     rax, ??_7?$CIUnknownBasedPointer@UIDefinitionAppId@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IDefinitionAppId>::`vftable'
0x180008a3e  mov     [rcx+18h], r8d
0x180008a42  mov     [rcx+20h], r8d
0x180008a46  mov     [rcx+30h], r8
0x180008a4a  mov     [rcx+28h], rdx
0x180008a4e  mov     [rcx+38h], rax
0x180008a52  mov     [rcx+40h], r8
0x180008a56  mov     [rcx+48h], rax
0x180008a5a  lea     rax, ??_7?$CIUnknownBasedPointer@UIStore@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IStore>::`vftable'
0x180008a61  mov     [rcx+50h], r8
0x180008a65  mov     [rcx+60h], r8
0x180008a69  mov     [rcx+58h], rdx
0x180008a6d  mov     [rcx+70h], r8
0x180008a71  mov     [rcx+68h], rdx
0x180008a75  mov     [rcx+78h], rax
0x180008a79  lea     rax, ??_7?$CIUnknownBasedPointer@UIIdentityAuthority@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IIdentityAuthority>::`vftable'
0x180008a80  mov     [rcx+80h], r8
0x180008a87  mov     [rcx+88h], rax
0x180008a8e  lea     rax, ??_7?$CIUnknownBasedPointer@UIAppIdAuthority@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IAppIdAuthority>::`vftable'
0x180008a95  mov     [rcx+90h], r8
0x180008a9c  mov     [rcx+98h], rax
0x180008aa3  lea     rax, ??_7?$CIUnknownBasedPointer@UICMS@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<ICMS>::`vftable'
0x180008aaa  mov     [rcx+0A0h], r8
0x180008ab1  mov     [rcx+0A8h], rax
0x180008ab8  mov     [rcx+0B0h], r8
0x180008abf  mov     [rcx+0B8h], rax
0x180008ac6  mov     [rcx+0C0h], r8
0x180008acd  mov     qword ptr [rcx+0C8h], 28h ; '('
0x180008ad8  movups  xmm0, cs:SXS_INSTALL_REFERENCE_SCHEME_OPAQUESTRING
0x180008adf  movdqu  xmmword ptr [rcx+0D0h], xmm0
0x180008ae7  mov     rax, cs:?InstallReferenceIdentifier@Strings@Constants@Dfdll@@3QEAGEA; ushort * Dfdll::Constants::Strings::InstallReferenceIdentifier
0x180008aee  mov     [rcx+0E0h], rax
0x180008af5  mov     rax, rcx
0x180008af8  mov     [rcx+0E8h], r8
0x180008aff  retn
```
