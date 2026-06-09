# OnDllProcessAttach(bool,void *)

- ea: `0x1800de51c`
- end: `0x1800de623`
- name: `?OnDllProcessAttach@@YAH_NPEAX@Z`
- size: `263`
- prototype: `int(bool, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180121ed0`

## callees

- `0x180057560`
- `0x1800de51c`
- `0x180106eb8`
- `0x18010ac60`
- `0x18010de84`
- `0x1801401f4`
- `0x1801f7a58`
- `0x1801f7e48`
- `0x1801f808c`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800de5c2`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800de5c2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800de59a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800de5b3`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800de59a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800de5b3`

## pseudocode

```c
__int64 __fastcall OnDllProcessAttach(__int64 a1, HMODULE a2)
{
  RTL_SRWLOCK *Lock; // rax
  RTL_SRWLOCK *v5; // rax

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRicheditCore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRicheditCore>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRicheditCore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRicheditCore>::GetImpl'::`2'::impl) )
    {
      RichEdit::RichEditCoreAPIs::RichEditCoreMethods::Initialize(&qword_1802E4830);
      if ( !byte_1802E4838 )
        goto LABEL_8;
      RichEdit::RichEditCoreAPIs::RegisterProviders();
    }
    if ( byte_1802E4838 )
    {
      if ( qword_1802E4900 )
        return (unsigned __int8)qword_1802E4900();
      return 0;
    }
  }
LABEL_8:
  CLockSharedData::LockOwner = 0;
  Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
  InitializeSRWLock(Lock);
  v5 = (RTL_SRWLOCK *)CLockSharedOS::GetLock(1);
  InitializeSRWLock(v5);
  DisableThreadLibraryCalls(a2);
  hinstRE = a2;
  if ( IClipboard::Create() )
  {
    wcscpy(&ClassName, L"RICHEDIT50W");
    if ( !(unsigned __int8)IsRegisterClassWPresent() || (unsigned int)RichFRegisterClass() )
    {
      McGenEventRegister_EventRegister();
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800de51c  push    rbx
0x1800de51e  sub     rsp, 20h
0x1800de522  mov     rbx, rdx
0x1800de525  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRicheditCore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRicheditCore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRicheditCore> `wil::Feature<__WilFeatureTraits_Feature_EnableRicheditCore>::GetImpl(void)'::`2'::impl
0x1800de52c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRicheditCore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRicheditCore>::__private_IsEnabled(void)
0x1800de531  test    al, al
0x1800de533  jz      short loc_1800DE585
0x1800de535  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRicheditCore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRicheditCore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRicheditCore> `wil::Feature<__WilFeatureTraits_Feature_EnableRicheditCore>::GetImpl(void)'::`2'::impl
0x1800de53c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRicheditCore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRicheditCore>::__private_IsEnabled(void)
0x1800de541  test    al, al
0x1800de543  jz      short loc_1800DE55F
0x1800de545  lea     rcx, qword_1802E4830; this
0x1800de54c  call    ?Initialize@RichEditCoreMethods@RichEditCoreAPIs@RichEdit@@QEAAXXZ; RichEdit::RichEditCoreAPIs::RichEditCoreMethods::Initialize(void)
0x1800de551  cmp     cs:byte_1802E4838, 0
0x1800de558  jz      short loc_1800DE585
0x1800de55a  call    RichEdit__RichEditCoreAPIs__RegisterProviders
0x1800de55f  cmp     cs:byte_1802E4838, 0
0x1800de566  jz      short loc_1800DE585
0x1800de568  mov     rax, cs:qword_1802E4900
0x1800de56f  test    rax, rax
0x1800de572  jz      loc_1800DE61A
0x1800de578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de57d  movzx   eax, al
0x1800de580  jmp     loc_1800DE61C
0x1800de585  xor     ecx, ecx
0x1800de587  mov     cs:?LockOwner@CLockSharedData@@2PAIA, 0; uint near * CLockSharedData::LockOwner
0x1800de592  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800de597  mov     rcx, rax; SRWLock
0x1800de59a  call    cs:__imp_InitializeSRWLock
0x1800de5a1  nop     dword ptr [rax+rax+00h]
0x1800de5a6  mov     ecx, 1
0x1800de5ab  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800de5b0  mov     rcx, rax; SRWLock
0x1800de5b3  call    cs:__imp_InitializeSRWLock
0x1800de5ba  nop     dword ptr [rax+rax+00h]
0x1800de5bf  mov     rcx, rbx; hLibModule
0x1800de5c2  call    cs:__imp_DisableThreadLibraryCalls
0x1800de5c9  nop     dword ptr [rax+rax+00h]
0x1800de5ce  mov     cs:?hinstRE@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * hinstRE
0x1800de5d5  call    ?Create@IClipboard@@SA_NXZ; IClipboard::Create(void)
0x1800de5da  test    al, al
0x1800de5dc  jz      short loc_1800DE61A
0x1800de5de  movups  xmm0, xmmword ptr cs:aRichedit50w; "RICHEDIT50W"
0x1800de5e5  movsd   xmm1, qword ptr cs:aRichedit50w+10h; "50W"
0x1800de5ed  movups  cs:ClassName, xmm0
0x1800de5f4  movsd   cs:qword_1802E4180, xmm1
0x1800de5fc  call    IsRegisterClassWPresent
0x1800de601  test    al, al
0x1800de603  jz      short loc_1800DE60E
0x1800de605  call    RichFRegisterClass
0x1800de60a  test    eax, eax
0x1800de60c  jz      short loc_1800DE61A
0x1800de60e  call    McGenEventRegister_EventRegister
0x1800de613  mov     eax, 1
0x1800de618  jmp     short loc_1800DE61C
0x1800de61a  xor     eax, eax
0x1800de61c  add     rsp, 20h
0x1800de620  pop     rbx
0x1800de621  retn
```
