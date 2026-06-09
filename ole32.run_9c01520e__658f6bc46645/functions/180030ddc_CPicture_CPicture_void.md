# CPicture::~CPicture(void)

- ea: `0x180030ddc`
- end: `0x180030f72`
- name: `??1CPicture@@QEAA@XZ`
- size: `406`
- prototype: `void __fastcall(CPicture *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180030d90`

## callees

- `0x180030ddc`
- `0x180030f78`
- `0x180030fe0`
- `0x1800d8010`

## import_xrefs

- `GDI32!DeleteMetaFile` at `0x180030f26`
- `GDI32!DeleteMetaFile` at `0x180030f26`
- `GDI32!DeleteObject` at `0x180030f37`
- `GDI32!DeleteObject` at `0x180030f48`
- `GDI32!DeleteObject` at `0x180030f37`
- `GDI32!DeleteObject` at `0x180030f48`
- `GDI32!DeleteEnhMetaFile` at `0x180030ed8`
- `GDI32!DeleteEnhMetaFile` at `0x180030ed8`
- `USER32!DestroyIcon` at `0x180030f11`
- `USER32!DestroyIcon` at `0x180030f11`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPicture::~CPicture(CPicture *this)
{
  ISimpleBinding *m_qbndData; // rcx
  CGdiCustodian *m_pcstOwn; // rcx
  HBITMAP__ *m_hbmpXor; // rcx
  HBITMAP__ *m_hbmpAnd; // rcx

  this->IPicture::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IPicture'};
  this->IPicture2::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IPicture2'};
  this->IPictureDisp::IDispatch::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IPictureDisp'};
  this->IPersistStream::IPersist::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IPersistStream'};
  this->IConnectionPointContainer::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IConnectionPointContainer'};
  this->IMarshal::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IMarshal'};
  m_qbndData = this->m_qbndData;
  if ( m_qbndData )
  {
    ((void (__fastcall *)(ISimpleBinding *))m_qbndData->lpVtbl[1].QueryInterface)(m_qbndData);
    ((void (__fastcall *)(ISimpleBinding *))this->m_qbndData->lpVtbl->Release)(this->m_qbndData);
  }
  m_pcstOwn = this->m_pcstOwn;
  if ( m_pcstOwn )
    ((void (__fastcall *)(CGdiCustodian *))m_pcstOwn->lpVtbl->Release)(m_pcstOwn);
  if ( (*((_BYTE *)this + 144) & 2) != 0 )
  {
    switch ( this->m_pic.picType )
    {
      case 2u:
        DeleteMetaFile(this->m_pic.wmf.hmeta);
        break;
      case 3u:
        DestroyIcon(this->m_pic.icon.hicon);
        break;
      case 4u:
        DeleteEnhMetaFile(this->m_pic.emf.hemf);
        break;
    }
  }
  m_hbmpXor = this->m_hbmpXor;
  if ( m_hbmpXor )
    DeleteObject(m_hbmpXor);
  m_hbmpAnd = this->m_hbmpAnd;
  if ( m_hbmpAnd )
    DeleteObject(m_hbmpAnd);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&CPicture::s_cPictObjs, 0xFFFFFFFF) == 1 && CPicture::s_ptinfo )
  {
    ((void (__fastcall *)(ITypeInfo *))CPicture::s_ptinfo->lpVtbl->Release)(CPicture::s_ptinfo);
    CPicture::s_ptinfo = 0;
  }
  _InterlockedDecrement((volatile signed __int32 *)&g_cObjs);
  CNotifyCP::~CNotifyCP(&this->m_cpNotify);
  this->m_csmOriginalFormat.lpVtbl = (struct IUnknownVtbl *)CCacheStream::`vftable';
  CCacheStream::Empty(&this->m_csmOriginalFormat);
}

```

## disassembly

```asm
0x180030ddc  push    rbx
0x180030dde  sub     rsp, 20h
0x180030de2  mov     rbx, this
0x180030de5  lea     rax, ??_7CPicture@@6BIPicture@@@; const CPicture::`vftable'{for `IPicture'}
0x180030dec  mov     [this], rax
0x180030def  lea     rax, ??_7CPicture@@6BIPicture2@@@; const CPicture::`vftable'{for `IPicture2'}
0x180030df6  mov     [this+8], rax
0x180030dfa  lea     rax, ??_7CPicture@@6BIPictureDisp@@@; const CPicture::`vftable'{for `IPictureDisp'}
0x180030e01  mov     [this+10h], rax
0x180030e05  lea     rax, ??_7CPicture@@6BIPersistStream@@@; const CPicture::`vftable'{for `IPersistStream'}
0x180030e0c  mov     [this+18h], rax
0x180030e10  lea     rax, ??_7CPicture@@6BIConnectionPointContainer@@@; const CPicture::`vftable'{for `IConnectionPointContainer'}
0x180030e17  mov     [this+20h], rax
0x180030e1b  lea     rax, ??_7CPicture@@6BIMarshal@@@; const CPicture::`vftable'{for `IMarshal'}
0x180030e22  mov     [this+28h], rax
0x180030e26  mov     this, [this+98h]
0x180030e2d  test    this, this
0x180030e30  jnz     loc_180030EE9
0x180030e36  mov     this, [rbx+88h]
0x180030e3d  test    this, this
0x180030e40  jz      short loc_180030E4E
0x180030e42  mov     rax, [this]
0x180030e45  mov     rax, [rax+10h]
0x180030e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e4e  test    byte ptr [rbx+90h], 2
0x180030e55  jnz     short loc_180030EC2
0x180030e57  mov     this, [rbx+70h]; ho
0x180030e5b  test    this, this
0x180030e5e  jnz     loc_180030F37
0x180030e64  mov     this, [rbx+68h]; ho
0x180030e68  test    this, this
0x180030e6b  jnz     loc_180030F48
0x180030e71  or      eax, 0FFFFFFFFh
0x180030e74  lock xadd cs:?s_cPictObjs@CPicture@@0IA, eax; uint CPicture::s_cPictObjs
0x180030e7c  cmp     eax, 1
0x180030e7f  jnz     short loc_180030E91
0x180030e81  mov     this, cs:?s_ptinfo@CPicture@@0PEAUITypeInfo@@EA; ITypeInfo * CPicture::s_ptinfo
0x180030e88  test    this, this
0x180030e8b  jnz     loc_180030F59
0x180030e91  lock dec cs:?g_cObjs@@3IA; uint g_cObjs
0x180030e98  lea     this, [rbx+0B8h]; this
0x180030e9f  call    ??1CNotifyCP@@QEAA@XZ; CNotifyCP::~CNotifyCP(void)
0x180030ea4  lea     this, [rbx+0A0h]; this
0x180030eab  lea     rax, ??_7CCacheStream@@6B@; const CCacheStream::`vftable'
0x180030eb2  mov     [this], rax
0x180030eb5  call    ?Empty@CCacheStream@@UEAAJXZ; CCacheStream::Empty(void)
0x180030eba  nop
0x180030ebb  add     rsp, 20h
0x180030ebf  pop     rbx
0x180030ec0  retn
0x180030ec2  mov     ecx, [rbx+3Ch]
0x180030ec5  sub     ecx, 2
0x180030ec8  jz      short loc_180030F22
0x180030eca  sub     ecx, 1
0x180030ecd  jz      short loc_180030F0D
0x180030ecf  cmp     ecx, 1
0x180030ed2  jnz     short loc_180030E57
0x180030ed4  mov     this, [rbx+40h]; hmf
0x180030ed8  call    cs:__imp_DeleteEnhMetaFile
0x180030edf  nop     dword ptr [rax+rax+00h]
0x180030ee4  jmp     loc_180030E57
0x180030ee9  mov     rax, [this]
0x180030eec  mov     rax, [rax+18h]
0x180030ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ef5  mov     this, [rbx+98h]
0x180030efc  mov     rax, [this]
0x180030eff  mov     rax, [rax+10h]
0x180030f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f08  jmp     loc_180030E36
0x180030f0d  mov     this, [rbx+40h]; hIcon
0x180030f11  call    cs:__imp_DestroyIcon
0x180030f18  nop     dword ptr [rax+rax+00h]
0x180030f1d  jmp     loc_180030E57
0x180030f22  mov     this, [rbx+40h]; hmf
0x180030f26  call    cs:__imp_DeleteMetaFile
0x180030f2d  nop     dword ptr [rax+rax+00h]
0x180030f32  jmp     loc_180030E57
0x180030f37  call    cs:__imp_DeleteObject
0x180030f3e  nop     dword ptr [rax+rax+00h]
0x180030f43  jmp     loc_180030E64
0x180030f48  call    cs:__imp_DeleteObject
0x180030f4f  nop     dword ptr [rax+rax+00h]
0x180030f54  jmp     loc_180030E71
0x180030f59  mov     rax, [this]
0x180030f5c  mov     rax, [rax+10h]
0x180030f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f65  and     cs:?s_ptinfo@CPicture@@0PEAUITypeInfo@@EA, 0; ITypeInfo * CPicture::s_ptinfo
0x180030f6d  jmp     loc_180030E91
```
