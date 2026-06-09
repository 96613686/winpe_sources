# MkvMfSourceLib::MkvTimedText::~MkvTimedText(void)

- ea: `0x18003ca28`
- end: `0x18003cb10`
- name: `??1MkvTimedText@MkvMfSourceLib@@UEAA@XZ`
- size: `232`
- prototype: `void __fastcall(MkvMfSourceLib::MkvTimedText *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003ccc0`

## callees

- `0x180005c68`
- `0x180008344`
- `0x18003c110`
- `0x18003c8d8`
- `0x18003c908`
- `0x18003ca28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003caef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003caef`
- `MFPlat!MFUnlockWorkQueue` at `0x18003ca4d`
- `MFPlat!MFUnlockWorkQueue` at `0x18003ca4d`

## pseudocode

```c
void __fastcall MkvMfSourceLib::MkvTimedText::~MkvTimedText(MkvMfSourceLib::MkvTimedText *this)
{
  DWORD v2; // ecx
  __int64 v3; // rcx

  *(_QWORD *)this = &MkvMfSourceLib::MkvTimedText::`vftable'{for `IMFTimedTextDataSource'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFTimedTextDataSource,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = *((_DWORD *)this + 31);
  if ( v2 )
    MFUnlockWorkQueue(v2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 192);
  std::_Tree<std::_Tmap_traits<unsigned long,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>((char *)this + 176);
  v3 = *((_QWORD *)this + 19);
  if ( v3 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>>>(
      v3,
      *((_QWORD *)this + 20));
    std::_Deallocate<16>(
      *((_QWORD *)this + 19),
      (*((_QWORD *)this + 21) - *((_QWORD *)this + 19)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
    *((_QWORD *)this + 21) = 0;
  }
  std::_Tree<std::_Tmap_traits<unsigned long,MkvMfSourceLib::MkvTimedText::TrackData,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,MkvMfSourceLib::MkvTimedText::TrackData>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,MkvMfSourceLib::MkvTimedText::TrackData,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,MkvMfSourceLib::MkvTimedText::TrackData>>,0>>((char *)this + 136);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 112);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 104);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x18003ca28  push    rbx
0x18003ca2a  sub     rsp, 20h
0x18003ca2e  lea     rax, ??_7MkvTimedText@MkvMfSourceLib@@6BIMFTimedTextDataSource@@@; const MkvMfSourceLib::MkvTimedText::`vftable'{for `IMFTimedTextDataSource'}
0x18003ca35  mov     rbx, rcx
0x18003ca38  mov     [rcx], rax
0x18003ca3b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMFTimedTextDataSource@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFTimedTextDataSource,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003ca42  mov     [rcx+8], rax
0x18003ca46  mov     ecx, [rcx+7Ch]; dwWorkQueue
0x18003ca49  test    ecx, ecx
0x18003ca4b  jz      short loc_18003CA59
0x18003ca4d  call    cs:__imp_MFUnlockWorkQueue
0x18003ca54  nop     dword ptr [rax+rax+00h]
0x18003ca59  lea     rcx, [rbx+0C0h]
0x18003ca60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ca65  lea     rcx, [rbx+0B0h]
0x18003ca6c  call    ??1?$_Tree@V?$_Tmap_traits@KVChapterTrackData@MkvTimedText@MkvMfSourceLib@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>::~_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>(void)
0x18003ca71  mov     rcx, [rbx+98h]
0x18003ca78  test    rcx, rcx
0x18003ca7b  jz      short loc_18003CAC4
0x18003ca7d  mov     rdx, [rbx+0A0h]
0x18003ca84  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>>>(Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle> *,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle> * const,std::allocator<Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>> &)
0x18003ca89  mov     rcx, [rbx+98h]
0x18003ca90  mov     rdx, [rbx+0A8h]
0x18003ca97  sub     rdx, rcx
0x18003ca9a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18003ca9e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003caa3  mov     qword ptr [rbx+98h], 0
0x18003caae  mov     qword ptr [rbx+0A0h], 0
0x18003cab9  mov     qword ptr [rbx+0A8h], 0
0x18003cac4  lea     rcx, [rbx+88h]
0x18003cacb  call    ??1?$_Tree@V?$_Tmap_traits@KVTrackData@MkvTimedText@MkvMfSourceLib@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::TrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>>,0>>::~_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::TrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>>,0>>(void)
0x18003cad0  lea     rcx, [rbx+70h]
0x18003cad4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003cad9  lea     rcx, [rbx+68h]
0x18003cadd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003cae2  lea     rcx, [rbx+60h]
0x18003cae6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003caeb  lea     rcx, [rbx+30h]; lpCriticalSection
0x18003caef  call    cs:__imp_DeleteCriticalSection
0x18003caf6  nop     dword ptr [rax+rax+00h]
0x18003cafb  lea     rcx, [rbx+20h]
0x18003caff  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18003cb06  add     rsp, 20h
0x18003cb0a  pop     rbx
0x18003cb0b  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
