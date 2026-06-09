# CNodeInitObject::UpdateExtensions(void)

- ea: `0x180064f20`
- end: `0x180065021`
- name: `?UpdateExtensions@CNodeInitObject@@MEAAJXZ`
- size: `257`
- prototype: `__int64 __fastcall(CNodeInitObject *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000f738`
- `0x1800304c0`
- `0x180064f20`

## import_xrefs

- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x180064f6c`
- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x180064f6c`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180064f62`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180064f62`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180065002`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180065002`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180064f36`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180064fbd`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180064f36`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180064fbd`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180064ff8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180064ff8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180064f99`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180064f99`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180064f47`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180064fce`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180064f47`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180064fce`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180064fad`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180064fad`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180064fa3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180064fec`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006500e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180064fa3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180064fec`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006500e`

## string_xrefs

- `0x180064f3c`: `IConsoleNameSpace3::UpdateExtensions`
- `0x180064fc3`: `CComponentData::UpdateExtensionSnapIns`

## pseudocode

```c
__int64 __fastcall CNodeInitObject::UpdateExtensions(CNodeInitObject *this)
{
  const unsigned __int16 *v2; // rdx
  struct CSnapIn **v3; // rbx
  __int64 v4; // rax
  unsigned int RequiredExtensions; // ebx
  unsigned int v6; // ebx
  _BYTE v8[24]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v9[24]; // [rsp+38h] [rbp-18h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v8, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v8, L"IConsoleNameSpace3::UpdateExtensions");
  v2 = (const unsigned __int16 *)((char *)this + 184);
  if ( *((_QWORD *)this + 26) >= 8u )
    v2 = *(const unsigned __int16 **)v2;
  mmcerror::SC::SetSnapinName((mmcerror::SC *)v8, v2);
  mmcerror::SC::CheckCallingThreadID((mmcerror::SC *)v8);
  v3 = *(struct CSnapIn ***)(*((_QWORD *)this + 28) + 256LL);
  v4 = ScCheckPointers(v9, v3, 2147549183LL);
  mmcerror::SC::operator=(v8, v4);
  mmcerror::SC::~SC((mmcerror::SC *)v9);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v8) )
  {
    mmcerror::SC::SC((mmcerror::SC *)v9, 0);
    mmcerror::SC::SetFunctionName((mmcerror::SC *)v9, L"CComponentData::UpdateExtensionSnapIns");
    RequiredExtensions = LoadRequiredExtensions(*v3, (const struct SnapinInterfaceWrapper *)(v3 + 1), 0, 1);
    mmcerror::SC::~SC((mmcerror::SC *)v9);
    mmcerror::SC::operator=(v8, RequiredExtensions);
  }
  v6 = mmcerror::SC::ToHr((mmcerror::SC *)v8);
  mmcerror::SC::~SC((mmcerror::SC *)v8);
  return v6;
}

```

## disassembly

```asm
0x180064f20  mov     [rsp-8+arg_0], rbx
0x180064f25  push    rbp
0x180064f26  mov     rbp, rsp
0x180064f29  sub     rsp, 50h
0x180064f2d  mov     rbx, rcx
0x180064f30  xor     edx, edx
0x180064f32  lea     rcx, [rbp+var_30]
0x180064f36  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180064f3c  lea     rdx, aIconsolenamesp_2; "IConsoleNameSpace3::UpdateExtensions"
0x180064f43  lea     rcx, [rbp+var_30]
0x180064f47  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180064f4d  lea     rdx, [rbx+0B8h]
0x180064f54  cmp     qword ptr [rdx+18h], 8
0x180064f59  jb      short loc_180064F5E
0x180064f5b  mov     rdx, [rdx]
0x180064f5e  lea     rcx, [rbp+var_30]
0x180064f62  call    cs:__imp_?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetSnapinName(ushort const *)
0x180064f68  lea     rcx, [rbp+var_30]
0x180064f6c  call    cs:__imp_?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ; mmcerror::SC::CheckCallingThreadID(void)
0x180064f72  mov     rax, [rbx+0E0h]
0x180064f79  lea     rcx, [rbp+var_18]
0x180064f7d  mov     r8d, 8000FFFFh
0x180064f83  mov     rbx, [rax+100h]
0x180064f8a  mov     rdx, rbx
0x180064f8d  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x180064f92  mov     rdx, rax
0x180064f95  lea     rcx, [rbp+var_30]
0x180064f99  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180064f9f  lea     rcx, [rbp+var_18]
0x180064fa3  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180064fa9  lea     rcx, [rbp+var_30]
0x180064fad  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180064fb3  test    al, al
0x180064fb5  jnz     short loc_180064FFE
0x180064fb7  xor     edx, edx
0x180064fb9  lea     rcx, [rbp+var_18]
0x180064fbd  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180064fc3  lea     rdx, aCcomponentdata_0; "CComponentData::UpdateExtensionSnapIns"
0x180064fca  lea     rcx, [rbp+var_18]
0x180064fce  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180064fd4  mov     rcx, [rbx]; this
0x180064fd7  lea     rdx, [rbx+8]
0x180064fdb  mov     r9b, 1
0x180064fde  xor     r8d, r8d
0x180064fe1  call    ?LoadRequiredExtensions@@YAJPEAVCSnapIn@@AEAV?$_snapin_ptr_t@VIComponentDataWrapper@@UIComponentData@@@@PEAVCSnapInsCache@@_N@Z; LoadRequiredExtensions(CSnapIn *,_snapin_ptr_t<IComponentDataWrapper,IComponentData> &,CSnapInsCache *,bool)
0x180064fe6  lea     rcx, [rbp+var_18]
0x180064fea  mov     ebx, eax
0x180064fec  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180064ff2  mov     edx, ebx
0x180064ff4  lea     rcx, [rbp+var_30]
0x180064ff8  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180064ffe  lea     rcx, [rbp+var_30]
0x180065002  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180065008  lea     rcx, [rbp+var_30]
0x18006500c  mov     ebx, eax
0x18006500e  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180065014  mov     eax, ebx
0x180065016  mov     rbx, [rsp+50h+arg_0]
0x18006501b  add     rsp, 50h
0x18006501f  pop     rbp
0x180065020  retn
```
