# CIDiagnosisParameterEnum::~CIDiagnosisParameterEnum(void)

- ea: `0x18001105c`
- end: `0x1800110cc`
- name: `??1CIDiagnosisParameterEnum@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(CIDiagnosisParameterEnum *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011390`

## callees

- `0x18001105c`
- `0x180015b60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800110a5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800110a5`
- `KERNEL32!DeleteCriticalSection` at `0x1800110ba`
- `KERNEL32!DeleteCriticalSection` at `0x1800110ba`

## pseudocode

```c
void __fastcall CIDiagnosisParameterEnum::~CIDiagnosisParameterEnum(CIDiagnosisParameterEnum *this)
{
  void **v2; // rbx

  *(_QWORD *)this = &CIDiagnosisParameterEnum::`vftable';
  v2 = (void **)((char *)this + 64);
  std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Erase(
    (char *)this + 64,
    *(_QWORD *)(*((_QWORD *)this + 8) + 8LL));
  *((_QWORD *)*v2 + 1) = *v2;
  *(_QWORD *)*v2 = *v2;
  *((_QWORD *)*v2 + 2) = *v2;
  v2[1] = 0;
  operator delete(*v2);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18001105c  mov     [rsp+arg_0], rbx
0x180011061  push    rdi
0x180011062  sub     rsp, 20h
0x180011066  mov     rdi, rcx
0x180011069  lea     rax, ??_7CIDiagnosisParameterEnum@@6B@; const CIDiagnosisParameterEnum::`vftable'
0x180011070  mov     [rcx], rax
0x180011073  lea     rbx, [rcx+40h]
0x180011077  mov     rdx, [rbx]
0x18001107a  mov     rdx, [rdx+8]
0x18001107e  mov     rcx, rbx
0x180011081  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::_Erase(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x180011086  mov     rax, [rbx]
0x180011089  mov     [rax+8], rax
0x18001108d  mov     rax, [rbx]
0x180011090  mov     [rax], rax
0x180011093  mov     rax, [rbx]
0x180011096  mov     [rax+10h], rax
0x18001109a  mov     qword ptr [rbx+8], 0
0x1800110a2  mov     rcx, [rbx]
0x1800110a5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800110ab  nop
0x1800110ac  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800110b0  cmp     byte ptr [rcx+28h], 0
0x1800110b4  jz      short loc_1800110C1
0x1800110b6  mov     byte ptr [rcx+28h], 0
0x1800110ba  call    cs:__imp_DeleteCriticalSection
0x1800110c0  nop
0x1800110c1  mov     rbx, [rsp+28h+arg_0]
0x1800110c6  add     rsp, 20h
0x1800110ca  pop     rdi
0x1800110cb  retn
```
