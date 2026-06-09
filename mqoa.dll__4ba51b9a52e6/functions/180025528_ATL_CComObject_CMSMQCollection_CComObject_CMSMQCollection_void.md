# ATL::CComObject<CMSMQCollection>::CComObject<CMSMQCollection>(void *)

- ea: `0x180025528`
- end: `0x1800255c8`
- name: `??0?$CComObject@VCMSMQCollection@@@ATL@@QEAA@PEAX@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025910`

## callees

- `0x18000a888`
- `0x180026298`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComObject<CMSMQCollection>::CComObject<CMSMQCollection>(__int64 a1)
{
  __int64 v2; // rax

  *(_DWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 24) = 0;
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_BYTE *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  CCriticalSection::CCriticalSection((CCriticalSection *)(a1 + 80));
  v2 = std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Buynode();
  *(_QWORD *)(a1 + 128) = v2;
  *(_BYTE *)(v2 + 57) = 1;
  *(_QWORD *)(*(_QWORD *)(a1 + 128) + 8LL) = *(_QWORD *)(a1 + 128);
  **(_QWORD **)(a1 + 128) = *(_QWORD *)(a1 + 128);
  *(_QWORD *)(*(_QWORD *)(a1 + 128) + 16LL) = *(_QWORD *)(a1 + 128);
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)a1 = &ATL::CComObject<CMSMQCollection>::`vftable'{for `ISupportErrorInfo'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CMSMQCollection>::`vftable'{for `ATL::IDispatchImpl<IMSMQCollection,&_GUID const IID_IMSMQCollection,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
  _InterlockedIncrement(&dword_180038608);
  return a1;
}

```

## disassembly

```asm
0x180025528  mov     [rsp+arg_10], rbx
0x18002552d  mov     [rsp+arg_0], rcx
0x180025532  push    rdi
0x180025533  sub     rsp, 20h
0x180025537  mov     rdi, rcx
0x18002553a  mov     dword ptr [rcx+10h], 0
0x180025541  xorps   xmm0, xmm0
0x180025544  xor     eax, eax
0x180025546  movups  xmmword ptr [rcx+18h], xmm0
0x18002554a  movups  xmmword ptr [rcx+28h], xmm0
0x18002554e  mov     [rcx+38h], rax
0x180025552  mov     [rcx+40h], al
0x180025555  mov     [rcx+48h], rax
0x180025559  add     rcx, 50h ; 'P'; this
0x18002555d  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x180025562  nop
0x180025563  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Buynode(void)
0x180025568  mov     [rdi+80h], rax
0x18002556f  mov     byte ptr [rax+39h], 1
0x180025573  mov     rax, [rdi+80h]
0x18002557a  mov     [rax+8], rax
0x18002557e  mov     rax, [rdi+80h]
0x180025585  mov     [rax], rax
0x180025588  mov     rax, [rdi+80h]
0x18002558f  mov     [rax+10h], rax
0x180025593  mov     qword ptr [rdi+88h], 0
0x18002559e  lea     rax, ??_7?$CComObject@VCMSMQCollection@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQCollection>::`vftable'{for `ISupportErrorInfo'}
0x1800255a5  mov     [rdi], rax
0x1800255a8  lea     rax, ??_7?$CComObject@VCMSMQCollection@@@ATL@@6B?$IDispatchImpl@UIMSMQCollection@@$1?IID_IMSMQCollection@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQCollection>::`vftable'{for `ATL::IDispatchImpl<IMSMQCollection,&_GUID const IID_IMSMQCollection,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x1800255af  mov     [rdi+8], rax
0x1800255b3  lock inc cs:dword_180038608
0x1800255ba  mov     rax, rdi
0x1800255bd  mov     rbx, [rsp+28h+arg_10]
0x1800255c2  add     rsp, 20h
0x1800255c6  pop     rdi
0x1800255c7  retn
```
