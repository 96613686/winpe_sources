# ScenarioInstanceData::ScenarioInstanceData(void)

- ea: `0x1800378f0`
- end: `0x180037cd7`
- name: `??0ScenarioInstanceData@@QEAA@XZ`
- size: `999`
- prototype: `ScenarioInstanceData *__fastcall(ScenarioInstanceData *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018674`

## callees

- `0x180008da0`
- `0x180032830`
- `0x1800378f0`
- `0x18003dfdc`
- `0x180041b70`
- `0x180044654`
- `0x18004551c`
- `0x18004cf68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180037b63`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180037b63`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ScenarioInstanceData *__fastcall ScenarioInstanceData::ScenarioInstanceData(ScenarioInstanceData *this)
{
  SIZE_T size_of; // rax
  _QWORD *v3; // rax
  _QWORD *v4; // rax

  *(GUID *)this = GUID_NULL;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 83) = 0;
  *((_DWORD *)this + 20) &= 0xFF000000;
  *((_BYTE *)this + 87) = 0;
  *((_DWORD *)this + 21) &= 0xFF000000;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_BYTE *)this + 108) = 0;
  *((_WORD *)this + 60) = 0;
  *((_BYTE *)this + 122) = 0;
  *((_DWORD *)this + 31) = 0;
  *((_WORD *)this + 64) = 0;
  *(_QWORD *)((char *)this + 132) = 0;
  *((_DWORD *)this + 35) = 0;
  *((_BYTE *)this + 144) = 0;
  *((_BYTE *)this + 156) = -2;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_BYTE *)this + 176) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_WORD *)this + 114) = 0;
  *((_DWORD *)this + 58) = 2;
  *((_BYTE *)this + 236) = 0;
  *((_DWORD *)this + 60) = 0;
  *((_WORD *)this + 122) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_BYTE *)this + 272) = 0;
  *((_DWORD *)this + 69) = 0;
  *((_DWORD *)this + 70) = 3;
  *((_DWORD *)this + 71) = 3;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  `eh vector constructor iterator'(
    (char *)this + 432,
    0x18u,
    2u,
    (void (*)(void *))std::vector<ServicePowerRequest>::vector<ServicePowerRequest>,
    std::vector<unsigned __int64>::~vector<unsigned __int64>);
  `eh vector constructor iterator'(
    (char *)this + 480,
    0x10u,
    2u,
    (void (*)(void *))std::map<_GUID,std::wstring,GuidCompare,std::allocator<std::pair<_GUID const,std::wstring>>>::map<_GUID,std::wstring,GuidCompare,std::allocator<std::pair<_GUID const,std::wstring>>>,
    std::map<_GUID,std::wstring,GuidCompare,std::allocator<std::pair<_GUID const,std::wstring>>>::~map<_GUID,std::wstring,GuidCompare,std::allocator<std::pair<_GUID const,std::wstring>>>);
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  BlockerData::BlockerData((char *)this + 632);
  *((_QWORD *)this + 79) = &ProcessorData::`vftable';
  CoCreateGuid((GUID *)((char *)this + 1208));
  std::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>((_QWORD *)this + 153);
  std::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>((_QWORD *)this + 155);
  *((_DWORD *)this + 314) = 0;
  std::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>((_QWORD *)this + 158);
  std::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>((_QWORD *)this + 160);
  *((_QWORD *)this + 165) = 0;
  *((_QWORD *)this + 166) = 0;
  *((_QWORD *)this + 167) = 0;
  *((_QWORD *)this + 168) = 0;
  *((_QWORD *)this + 169) = 0;
  *((_QWORD *)this + 170) = 0;
  size_of = std::_Get_size_of_n<72>(1);
  v3 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *((_QWORD *)this + 169) = v3;
  *((_QWORD *)this + 171) = 0;
  *((_QWORD *)this + 172) = 0;
  *((_DWORD *)this + 346) = 0;
  *((_BYTE *)this + 1388) = 0;
  *((_QWORD *)this + 174) = 0;
  *((_QWORD *)this + 176) = 0;
  *((_QWORD *)this + 177) = 0;
  *((_QWORD *)this + 178) = 0;
  *((_QWORD *)this + 179) = 0;
  *((_DWORD *)this + 360) = 0;
  SegmentDataEx::SegmentDataEx((char *)this + 1448, 0);
  SegmentDataEx::SegmentDataEx((char *)this + 1576, 1);
  *((_BYTE *)this + 1704) = 0;
  *((_DWORD *)this + 427) = 0;
  *((_DWORD *)this + 22) = 17;
  v4 = operator new(0x58u);
  if ( v4 )
  {
    *v4 = 0;
    v4[1] = 0;
    v4[2] = 0;
    v4[3] = 0;
    v4[4] = 0;
    v4[5] = 0;
    *((_DWORD *)v4 + 12) = 0;
    v4[7] = 0;
    v4[8] = 0;
    v4[9] = 0;
    *((_DWORD *)v4 + 20) = 0;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 162) = v4;
  *((_QWORD *)this + 163) = 0;
  *((_QWORD *)this + 164) = 0;
  *((_QWORD *)this + 175) = 0;
  return this;
}

```

## disassembly

```asm
0x1800378f0  mov     r11, rsp
0x1800378f3  mov     [r11+18h], rbx
0x1800378f7  mov     [r11+20h], rbp
0x1800378fb  mov     [r11+8], rcx
0x1800378ff  push    rdi
0x180037900  sub     rsp, 30h
0x180037904  mov     rdi, rcx
0x180037907  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003790e  movdqu  xmmword ptr [rcx], xmm0
0x180037912  xor     ebp, ebp
0x180037914  mov     [rcx+10h], rbp
0x180037918  mov     [rcx+18h], rbp
0x18003791c  mov     [rcx+20h], rbp
0x180037920  mov     [rcx+28h], rbp
0x180037924  mov     [rcx+30h], rbp
0x180037928  mov     [rcx+38h], rbp
0x18003792c  mov     [rcx+40h], rbp
0x180037930  mov     [rcx+48h], rbp
0x180037934  mov     [rcx+53h], bpl
0x180037938  mov     eax, 0FF000000h
0x18003793d  and     [rcx+50h], eax
0x180037940  mov     [rcx+57h], bpl
0x180037944  and     [rcx+54h], eax
0x180037947  mov     [rcx+60h], rbp
0x18003794b  mov     [rcx+68h], ebp
0x18003794e  mov     [rcx+6Ch], bpl
0x180037952  mov     [rcx+78h], bp
0x180037956  mov     [rcx+7Ah], bpl
0x18003795a  mov     [rcx+7Ch], ebp
0x18003795d  mov     [rcx+80h], bp
0x180037964  mov     [rcx+84h], rbp
0x18003796b  mov     [rcx+8Ch], ebp
0x180037971  mov     [rcx+90h], bpl
0x180037978  mov     byte ptr [rcx+9Ch], 0FEh
0x18003797f  mov     [rcx+0A0h], rbp
0x180037986  mov     [rcx+0A8h], rbp
0x18003798d  mov     [rcx+0B0h], bpl
0x180037994  mov     [rcx+0B8h], rbp
0x18003799b  mov     [rcx+0C0h], ebp
0x1800379a1  mov     [rcx+0C8h], rbp
0x1800379a8  mov     [rcx+0D0h], rbp
0x1800379af  mov     [rcx+0D8h], rbp
0x1800379b6  mov     [rcx+0E0h], ebp
0x1800379bc  mov     [rcx+0E4h], bp
0x1800379c3  lea     ebx, [rbp+2]
0x1800379c6  mov     [rcx+0E8h], ebx
0x1800379cc  mov     [rcx+0ECh], bpl
0x1800379d3  mov     [rcx+0F0h], ebp
0x1800379d9  mov     [rcx+0F4h], bp
0x1800379e0  mov     [rcx+0F8h], rbp
0x1800379e7  mov     [rcx+100h], rbp
0x1800379ee  mov     [rcx+108h], rbp
0x1800379f5  mov     [rcx+110h], bpl
0x1800379fc  mov     [rcx+114h], ebp
0x180037a02  lea     eax, [rbp+3]
0x180037a05  mov     [rcx+118h], eax
0x180037a0b  mov     [rcx+11Ch], eax
0x180037a11  mov     [rcx+120h], rbp
0x180037a18  mov     [rcx+128h], rbp
0x180037a1f  mov     [rcx+130h], rbp
0x180037a26  mov     [rcx+138h], rbp
0x180037a2d  mov     [rcx+140h], rbp
0x180037a34  mov     [rcx+148h], rbp
0x180037a3b  mov     [rcx+150h], rbp
0x180037a42  mov     [rcx+158h], rbp
0x180037a49  mov     [rcx+160h], rbp
0x180037a50  mov     [rcx+168h], rbp
0x180037a57  mov     [rcx+170h], rbp
0x180037a5e  mov     [rcx+178h], rbp
0x180037a65  mov     [rcx+180h], rbp
0x180037a6c  mov     [rcx+188h], rbp
0x180037a73  mov     [rcx+190h], rbp
0x180037a7a  mov     [rcx+198h], rbp
0x180037a81  mov     [rcx+1A0h], rbp
0x180037a88  mov     [rcx+1A8h], rbp
0x180037a8f  add     rcx, 1B0h; void *
0x180037a96  lea     rax, ??1?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::~vector<unsigned __int64>(void)
0x180037a9d  mov     [r11-18h], rax
0x180037aa1  lea     r9, ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x180037aa8  mov     r8d, ebx; unsigned __int64
0x180037aab  lea     edx, [rbp+18h]; unsigned __int64
0x180037aae  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180037ab3  nop
0x180037ab4  lea     rcx, [rdi+1E0h]; void *
0x180037abb  lea     rax, ??1?$map@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@@std@@QEAA@XZ; std::map<_GUID,std::wstring,GuidCompare,std::allocator<std::pair<_GUID const,std::wstring>>>::~map<_GUID,std::wstring,GuidCompare,std::allocator<std::pair<_GUID const,std::wstring>>>(void)
0x180037ac2  mov     [rsp+38h+var_18], rax; void (*)(void *)
0x180037ac7  lea     r9, ??0?$map@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@@std@@QEAA@XZ; void (*)(void *)
0x180037ace  mov     r8d, ebx; unsigned __int64
0x180037ad1  lea     edx, [rbp+10h]; unsigned __int64
0x180037ad4  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180037ad9  nop
0x180037ada  mov     [rdi+200h], rbp
0x180037ae1  mov     [rdi+208h], rbp
0x180037ae8  mov     [rdi+210h], rbp
0x180037aef  mov     [rdi+218h], rbp
0x180037af6  mov     [rdi+220h], rbp
0x180037afd  mov     [rdi+228h], rbp
0x180037b04  mov     [rdi+230h], rbp
0x180037b0b  mov     [rdi+238h], rbp
0x180037b12  mov     [rdi+240h], rbp
0x180037b19  mov     [rdi+248h], rbp
0x180037b20  mov     [rdi+250h], rbp
0x180037b27  mov     [rdi+258h], rbp
0x180037b2e  mov     [rdi+260h], rbp
0x180037b35  mov     [rdi+268h], rbp
0x180037b3c  mov     [rdi+270h], rbp
0x180037b43  lea     rbx, [rdi+278h]
0x180037b4a  mov     rcx, rbx
0x180037b4d  call    ??0BlockerData@@QEAA@PEBGW4BlockerType@@@Z; BlockerData::BlockerData(ushort const *,BlockerType)
0x180037b52  lea     rax, ??_7ProcessorData@@6B@; const ProcessorData::`vftable'
0x180037b59  mov     [rbx], rax
0x180037b5c  lea     rcx, [rbx+240h]; pguid
0x180037b63  call    cs:__imp_CoCreateGuid
0x180037b69  nop
0x180037b6a  lea     rcx, [rdi+4C8h]
0x180037b71  call    ??0?$map@USrumKey@@V?$unique_ptr@UEnergyEstimationInfo@@U?$default_delete@UEnergyEstimationInfo@@@std@@@std@@U?$less@USrumKey@@@3@V?$allocator@U?$pair@$$CBUSrumKey@@V?$unique_ptr@UEnergyEstimationInfo@@U?$default_delete@UEnergyEstimationInfo@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>(void)
0x180037b76  nop
0x180037b77  lea     rcx, [rdi+4D8h]
0x180037b7e  call    ??0?$map@USrumKey@@V?$unique_ptr@UEnergyEstimationInfo@@U?$default_delete@UEnergyEstimationInfo@@@std@@@std@@U?$less@USrumKey@@@3@V?$allocator@U?$pair@$$CBUSrumKey@@V?$unique_ptr@UEnergyEstimationInfo@@U?$default_delete@UEnergyEstimationInfo@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>(void)
0x180037b83  nop
0x180037b84  mov     [rdi+4E8h], ebp
0x180037b8a  lea     rcx, [rdi+4F0h]
0x180037b91  call    ??0?$map@USrumKey@@V?$unique_ptr@UEnergyEstimationInfo@@U?$default_delete@UEnergyEstimationInfo@@@std@@@std@@U?$less@USrumKey@@@3@V?$allocator@U?$pair@$$CBUSrumKey@@V?$unique_ptr@UEnergyEstimationInfo@@U?$default_delete@UEnergyEstimationInfo@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>(void)
0x180037b96  nop
0x180037b97  lea     rcx, [rdi+500h]
0x180037b9e  call    ??0?$map@USrumKey@@V?$unique_ptr@UEnergyEstimationInfo@@U?$default_delete@UEnergyEstimationInfo@@@std@@@std@@U?$less@USrumKey@@@3@V?$allocator@U?$pair@$$CBUSrumKey@@V?$unique_ptr@UEnergyEstimationInfo@@U?$default_delete@UEnergyEstimationInfo@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>::map<SrumKey,std::unique_ptr<EnergyEstimationInfo>>(void)
0x180037ba3  nop
0x180037ba4  mov     [rdi+528h], rbp
0x180037bab  mov     [rdi+530h], rbp
0x180037bb2  mov     [rdi+538h], rbp
0x180037bb9  mov     [rdi+540h], rbp
0x180037bc0  lea     rbx, [rdi+548h]
0x180037bc7  mov     [rbx], rbp
0x180037bca  mov     [rbx+8], rbp
0x180037bce  lea     ecx, [rbp+1]
0x180037bd1  call    ??$_Get_size_of_n@$0EI@@std@@YA_K_K@Z; std::_Get_size_of_n<72>(unsigned __int64)
0x180037bd6  mov     rcx, rax
0x180037bd9  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180037bde  mov     [rax], rax
0x180037be1  mov     [rax+8], rax
0x180037be5  mov     [rax+10h], rax
0x180037be9  mov     word ptr [rax+18h], 101h
0x180037bef  mov     [rbx], rax
0x180037bf2  mov     [rdi+558h], rbp
0x180037bf9  mov     [rdi+560h], rbp
0x180037c00  mov     [rdi+568h], ebp
0x180037c06  mov     [rdi+56Ch], bpl
0x180037c0d  mov     [rdi+570h], rbp
0x180037c14  mov     [rdi+580h], rbp
0x180037c1b  mov     [rdi+588h], rbp
0x180037c22  mov     [rdi+590h], rbp
0x180037c29  mov     [rdi+598h], rbp
0x180037c30  mov     [rdi+5A0h], ebp
0x180037c36  xor     edx, edx
0x180037c38  lea     rcx, [rdi+5A8h]
0x180037c3f  call    ??0SegmentDataEx@@QEAA@W4ScenarioSegment@@@Z; SegmentDataEx::SegmentDataEx(ScenarioSegment)
0x180037c44  lea     rcx, [rdi+628h]
0x180037c4b  lea     edx, [rbp+1]
0x180037c4e  call    ??0SegmentDataEx@@QEAA@W4ScenarioSegment@@@Z; SegmentDataEx::SegmentDataEx(ScenarioSegment)
0x180037c53  nop
0x180037c54  mov     [rdi+6A8h], bpl
0x180037c5b  mov     [rdi+6ACh], ebp
0x180037c61  mov     dword ptr [rdi+58h], 11h
0x180037c68  lea     ecx, [rbp+58h]; dwBytes
0x180037c6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037c70  mov     [rsp+38h+arg_0], rax
0x180037c75  test    rax, rax
0x180037c78  jz      short loc_180037CA5
0x180037c7a  mov     [rax], rbp
0x180037c7d  mov     [rax+8], rbp
0x180037c81  mov     [rax+10h], rbp
0x180037c85  mov     [rax+18h], rbp
0x180037c89  mov     [rax+20h], rbp
0x180037c8d  mov     [rax+28h], rbp
0x180037c91  mov     [rax+30h], ebp
0x180037c94  mov     [rax+38h], rbp
0x180037c98  mov     [rax+40h], rbp
0x180037c9c  mov     [rax+48h], rbp
0x180037ca0  mov     [rax+50h], ebp
0x180037ca3  jmp     short loc_180037CA8
0x180037ca5  mov     rax, rbp
0x180037ca8  mov     [rdi+510h], rax
0x180037caf  mov     [rdi+518h], rbp
0x180037cb6  mov     [rdi+520h], rbp
0x180037cbd  mov     [rdi+578h], rbp
0x180037cc4  mov     rax, rdi
0x180037cc7  mov     rbx, [rsp+38h+arg_10]
0x180037ccc  mov     rbp, [rsp+38h+arg_18]
0x180037cd1  add     rsp, 30h
0x180037cd5  pop     rdi
0x180037cd6  retn
```
