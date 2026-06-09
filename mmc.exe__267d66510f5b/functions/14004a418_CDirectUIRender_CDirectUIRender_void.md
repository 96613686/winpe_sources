# CDirectUIRender::~CDirectUIRender(void)

- ea: `0x14004a418`
- end: `0x14004a544`
- name: `??1CDirectUIRender@@UEAA@XZ`
- size: `300`
- prototype: `void __fastcall(CDirectUIRender *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14004a3e0`

## callees

- `0x14004a418`
- `0x14006623c`
- `0x1400e9000`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14004a529`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14004a529`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14004a436`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14004a436`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14004a448`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14004a448`
- `KERNEL32!DeleteAtom` at `0x14004a497`
- `KERNEL32!DeleteAtom` at `0x14004a4a6`
- `KERNEL32!DeleteAtom` at `0x14004a4b5`
- `KERNEL32!DeleteAtom` at `0x14004a4c4`
- `KERNEL32!DeleteAtom` at `0x14004a4d3`
- `KERNEL32!DeleteAtom` at `0x14004a4e2`
- `KERNEL32!DeleteAtom` at `0x14004a4f1`
- `KERNEL32!DeleteAtom` at `0x14004a500`
- `KERNEL32!DeleteAtom` at `0x14004a497`
- `KERNEL32!DeleteAtom` at `0x14004a4a6`
- `KERNEL32!DeleteAtom` at `0x14004a4b5`
- `KERNEL32!DeleteAtom` at `0x14004a4c4`
- `KERNEL32!DeleteAtom` at `0x14004a4d3`
- `KERNEL32!DeleteAtom` at `0x14004a4e2`
- `KERNEL32!DeleteAtom` at `0x14004a4f1`
- `KERNEL32!DeleteAtom` at `0x14004a500`
- `DUI70!?Destroy@NativeHWNDHost@DirectUI@@QEAAXXZ` at `0x14004a50f`
- `DUI70!?Destroy@NativeHWNDHost@DirectUI@@QEAAXXZ` at `0x14004a50f`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x14004a51e`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x14004a51e`

## pseudocode

```c
void __fastcall CDirectUIRender::~CDirectUIRender(CDirectUIRender *this)
{
  ATOM v2; // cx
  ATOM v3; // cx
  ATOM v4; // cx
  ATOM v5; // cx
  ATOM v6; // cx
  ATOM v7; // cx
  ATOM v8; // cx
  ATOM v9; // cx
  DirectUI::NativeHWNDHost *v10; // rcx
  DirectUI::DUIXmlParser *v11; // rcx
  _BYTE v12[40]; // [rsp+20h] [rbp-28h] BYREF

  *(_QWORD *)this = &CDirectUIRender::`vftable';
  mmcerror::SC::SC((mmcerror::SC *)v12, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v12, L"CDirectUIRender::~CDirectUIRender");
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_af702272411f32d5bae2e4aec0f6e859_Traceguids);
  if ( *((_BYTE *)this + 8) )
    CDirectUIRender::FreezeLayout(this, 0);
  v2 = *((_WORD *)this + 40);
  if ( v2 )
    DeleteAtom(v2);
  v3 = *((_WORD *)this + 41);
  if ( v3 )
    DeleteAtom(v3);
  v4 = *((_WORD *)this + 42);
  if ( v4 )
    DeleteAtom(v4);
  v5 = *((_WORD *)this + 43);
  if ( v5 )
    DeleteAtom(v5);
  v6 = *((_WORD *)this + 44);
  if ( v6 )
    DeleteAtom(v6);
  v7 = *((_WORD *)this + 45);
  if ( v7 )
    DeleteAtom(v7);
  v8 = *((_WORD *)this + 46);
  if ( v8 )
    DeleteAtom(v8);
  v9 = *((_WORD *)this + 47);
  if ( v9 )
    DeleteAtom(v9);
  v10 = (DirectUI::NativeHWNDHost *)*((_QWORD *)this + 6);
  if ( v10 )
    DirectUI::NativeHWNDHost::Destroy(v10);
  v11 = (DirectUI::DUIXmlParser *)*((_QWORD *)this + 5);
  if ( v11 )
    DirectUI::DUIXmlParser::Destroy(v11);
  mmcerror::SC::~SC((mmcerror::SC *)v12);
  *(_QWORD *)this = &CObject::`vftable';
}

```

## disassembly

```asm
0x14004a418  mov     [rsp+arg_0], rbx
0x14004a41d  push    rdi
0x14004a41e  sub     rsp, 40h
0x14004a422  mov     rbx, rcx
0x14004a425  lea     rax, ??_7CDirectUIRender@@6B@; const CDirectUIRender::`vftable'
0x14004a42c  mov     [rcx], rax
0x14004a42f  xor     edx, edx
0x14004a431  lea     rcx, [rsp+48h+var_28]
0x14004a436  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14004a43c  lea     rdx, aCdirectuirende; "CDirectUIRender::~CDirectUIRender"
0x14004a443  lea     rcx, [rsp+48h+var_28]
0x14004a448  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14004a44e  lea     rax, WPP_GLOBAL_Control
0x14004a455  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a45c  cmp     rcx, rax
0x14004a45f  jz      short loc_14004A47C
0x14004a461  cmp     byte ptr [rcx+19h], 4
0x14004a465  jb      short loc_14004A47C
0x14004a467  mov     edx, 0Ah
0x14004a46c  lea     r8, WPP_af702272411f32d5bae2e4aec0f6e859_Traceguids
0x14004a473  mov     rcx, [rcx+10h]
0x14004a477  call    WPP_SF_
0x14004a47c  xor     edi, edi
0x14004a47e  cmp     [rbx+8], dil
0x14004a482  jz      short loc_14004A48E
0x14004a484  xor     edx, edx; bool
0x14004a486  mov     rcx, rbx; this
0x14004a489  call    ?FreezeLayout@CDirectUIRender@@QEAAX_N@Z; CDirectUIRender::FreezeLayout(bool)
0x14004a48e  movzx   ecx, word ptr [rbx+50h]; nAtom
0x14004a492  test    cx, cx
0x14004a495  jz      short loc_14004A49D
0x14004a497  call    cs:__imp_DeleteAtom
0x14004a49d  movzx   ecx, word ptr [rbx+52h]; nAtom
0x14004a4a1  test    cx, cx
0x14004a4a4  jz      short loc_14004A4AC
0x14004a4a6  call    cs:__imp_DeleteAtom
0x14004a4ac  movzx   ecx, word ptr [rbx+54h]; nAtom
0x14004a4b0  test    cx, cx
0x14004a4b3  jz      short loc_14004A4BB
0x14004a4b5  call    cs:__imp_DeleteAtom
0x14004a4bb  movzx   ecx, word ptr [rbx+56h]; nAtom
0x14004a4bf  test    cx, cx
0x14004a4c2  jz      short loc_14004A4CA
0x14004a4c4  call    cs:__imp_DeleteAtom
0x14004a4ca  movzx   ecx, word ptr [rbx+58h]; nAtom
0x14004a4ce  test    cx, cx
0x14004a4d1  jz      short loc_14004A4D9
0x14004a4d3  call    cs:__imp_DeleteAtom
0x14004a4d9  movzx   ecx, word ptr [rbx+5Ah]; nAtom
0x14004a4dd  test    cx, cx
0x14004a4e0  jz      short loc_14004A4E8
0x14004a4e2  call    cs:__imp_DeleteAtom
0x14004a4e8  movzx   ecx, word ptr [rbx+5Ch]; nAtom
0x14004a4ec  test    cx, cx
0x14004a4ef  jz      short loc_14004A4F7
0x14004a4f1  call    cs:__imp_DeleteAtom
0x14004a4f7  movzx   ecx, word ptr [rbx+5Eh]; nAtom
0x14004a4fb  test    cx, cx
0x14004a4fe  jz      short loc_14004A506
0x14004a500  call    cs:__imp_DeleteAtom
0x14004a506  mov     rcx, [rbx+30h]
0x14004a50a  test    rcx, rcx
0x14004a50d  jz      short loc_14004A515
0x14004a50f  call    cs:__imp_?Destroy@NativeHWNDHost@DirectUI@@QEAAXXZ; DirectUI::NativeHWNDHost::Destroy(void)
0x14004a515  mov     rcx, [rbx+28h]
0x14004a519  test    rcx, rcx
0x14004a51c  jz      short loc_14004A524
0x14004a51e  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x14004a524  lea     rcx, [rsp+48h+var_28]
0x14004a529  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14004a52f  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x14004a536  mov     [rbx], rax
0x14004a539  mov     rbx, [rsp+48h+arg_0]
0x14004a53e  add     rsp, 40h
0x14004a542  pop     rdi
0x14004a543  retn
```
