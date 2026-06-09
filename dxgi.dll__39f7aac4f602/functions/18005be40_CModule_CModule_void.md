# CModule::CModule(void)

- ea: `0x18005be40`
- end: `0x18005c556`
- name: `??0CModule@@QEAA@XZ`
- size: `1814`
- prototype: `CModule *__fastcall(CModule *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005be20`

## callees

- `0x18000c6b0`
- `0x18001a6d4`
- `0x18001b22c`
- `0x18001c5a4`
- `0x1800306f4`
- `0x1800404e4`
- `0x18004d4a4`
- `0x180052cbc`
- `0x1800547b4`
- `0x18005b854`
- `0x18005be40`
- `0x18005ffa8`
- `0x180061f40`
- `0x180064640`
- `0x1800650dc`
- `0x180069768`
- `0x180075fa0`
- `0x180075fc4`
- `0x180076f20`
- `0x180089cc8`
- `0x18008a4c8`
- `0x18008ab64`
- `0x180091ec0`
- `0x180092bac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18005c40a`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18005c4a3`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18005c40a`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18005c4a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18005c456`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18005c456`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005c3b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005c3b8`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleInformation` at `0x18005c2d0`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleInformation` at `0x18005c2d0`

## string_xrefs

- `0x18005c32a`: `c:\windows\system32`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
CModule *__fastcall CModule::CModule(CModule *this)
{
  ATL::CAtlComModule *v1; // rcx
  CModule::EffectCreationInfo *v2; // rbx
  __int64 v3; // rdi
  _QWORD *v4; // rax
  __int64 size_of; // rax
  __int64 v6; // rax
  const char *v7; // rdx
  CModule *v8; // rcx
  _WORD *v9; // rsi
  unsigned __int16 *v10; // rbx
  unsigned __int16 *v11; // rdi
  _WORD *v12; // rsi
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rdi
  CModule *v17; // rcx
  CModule *v18; // rcx
  _QWORD v20[4]; // [rsp+20h] [rbp-E0h] BYREF
  _MODULEINFO modinfo; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v22[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v23[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v24; // [rsp+88h] [rbp-78h]
  _QWORD v25[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v26; // [rsp+A8h] [rbp-58h]
  _BYTE v27[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v28[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v29[32]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Filename[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Buffer[264]; // [rsp+320h] [rbp+220h] BYREF

  v20[2] = g_Module;
  *(_OWORD *)&CriticalSection.DebugInfo = 0;
  *(_OWORD *)&CriticalSection.OwningThread = 0;
  CriticalSection.SpinCount = 0;
  qword_1801099A8 = 0;
  qword_1801099B0 = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)g_Module;
  qword_1801099E0 = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection) >= 0 )
    LODWORD(qword_1801099A8) = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  ATL::CAtlComModule::ExecuteObjectMain(v1, 1);
  g_Module[0] = (__int64)&CModule::`vftable';
  hObject = 0;
  qword_180109A08 = 0;
  *(_OWORD *)&xmmword_180109A10 = 0;
  byte_180109A20 = 0;
  stru_180109A28 = 0;
  *(_QWORD *)&qword_180109A30 = 0;
  dword_180109A38 = 0;
  word_180109A3C = 0;
  byte_180109A3E = 0;
  byte_180109A40 = 0;
  qword_180109A48 = 0;
  stru_180109A50 = 0;
  byte_180109A58 = 0;
  byte_180109A60 = 0;
  qword_180109A68 = 0;
  xmmword_180109A70 = 0;
  xmmword_180109A80 = 0;
  dword_180109AA8 = 0;
  qword_180109AB8 = 0;
  xmmword_180109AC0 = 0;
  xmmword_180109AD0 = 0;
  qword_180109AE0 = 0;
  qword_180109AB0 = (__int64)&CDXGIMutexInSeparateThread::`vftable';
  qword_180109AE8 = 0;
  dword_180109AF0 = 0;
  xmmword_180109B00 = 0;
  xmmword_180109B10 = 0;
  qword_180109B20 = 0;
  qword_180109B28 = 0;
  qword_180109AF8 = (__int64)&CDXGIMutexInSeparateThread::`vftable';
  qword_180109B30 = 0;
  dword_180109B38 = 0;
  lpMem = 0;
  *(_OWORD *)&xmmword_180109B60 = 0;
  qword_180109B70 = 0;
  qword_180109B78 = 0;
  byte_180109B81 = 0;
  byte_180109B82 &= 0xFCu;
  byte_180109B83 &= 0xFCu;
  byte_180109B85 = 0;
  byte_180109B88 = 0;
  dword_180109B8C = 0;
  byte_180109B90 = 0;
  dword_180109B94 = 0;
  byte_180109B98 = 0;
  qword_180109B9C = 0;
  byte_180109BA4 = 0;
  dword_180109BA6 = 0x10000;
  byte_180109BAC = 0;
  qword_180109BB0 = 0;
  dword_180109BB8 = 0;
  byte_180109BBC = 0;
  byte_180109BBD &= 0xFCu;
  byte_180109BBE &= 0xFCu;
  byte_180109BBF &= 0xFCu;
  byte_180109BC0 &= 0xFCu;
  byte_180109BC1 &= 0xFCu;
  byte_180109BC8 &= 0xFCu;
  byte_180109BC9 &= 0xFCu;
  byte_180109BCA &= 0xFCu;
  word_180109BCB = 0;
  byte_180109BCD &= 0xFCu;
  byte_180109BD0 = 0;
  qword_180109BD8 = 0;
  word_180109BE1 = 0;
  LOBYTE(dword_180109BE4) = 0;
  HIWORD(dword_180109BE4) = 0;
  dword_180109BE8 = 0;
  qword_180109BEC = 0;
  qword_180109BF4 = 0;
  qword_180109BFC = 0;
  qword_180109C04 = 0;
  byte_180109C0C = 0;
  word_180109C0E = 0;
  byte_180109C10 = 0;
  xmmword_180109C18 = 0;
  byte_180109C28 &= 0xFCu;
  byte_180109C30 = 0;
  qword_180109C38 = 0;
  byte_180109C40 = 0;
  qword_180109C48 = 0;
  byte_180109C50 &= 0xFCu;
  byte_180109C5C = 0;
  qword_180109C60 = 0;
  byte_180109C68 = 0;
  byte_180109C6C = 0;
  dword_180109C70 = 0;
  std::string::string(&qword_180109C78);
  byte_180109C98 = 0;
  dword_180109C9C = 0;
  v2 = (CModule::EffectCreationInfo *)qword_180109CA0;
  v3 = 3;
  do
  {
    CModule::EffectCreationInfo::EffectCreationInfo(v2);
    v2 = (CModule::EffectCreationInfo *)((char *)v2 + 56);
    --v3;
  }
  while ( v3 );
  byte_180109D48 = 0;
  xmmword_180109D4C = 0;
  qword_180109D60 = 0;
  qword_180109D68 = 0;
  v4 = operator new(0x30u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  qword_180109D60 = (__int64)v4;
  qword_180109D70 = 0;
  byte_180109D78 = 0;
  qword_180109D80 = 0;
  qword_180109D88 = 0;
  qword_180109D90 = 0;
  size_of = std::_Get_size_of_n<40>(1);
  v6 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *(_QWORD *)v6 = v6;
  *(_QWORD *)(v6 + 8) = v6;
  *(_QWORD *)(v6 + 16) = v6;
  *(_WORD *)(v6 + 24) = 257;
  qword_180109D88 = v6;
  byte_180109D98 = 0;
  dword_180109D9C = 0;
  byte_180109DA0 &= 0xFCu;
  byte_180109DA4 = 0;
  dword_180109DA8 = 0;
  byte_180109DB8 = 0;
  qword_180109DC0 = 0;
  byte_180109DC8 &= 0xFCu;
  byte_180109DC9 &= 0xFCu;
  dword_180109DCC = 0;
  xmmword_180109DD0 = 0;
  xmmword_180109DE0 = 0;
  qword_180109DF0 = 0;
  byte_180109DF8 = 0;
  qword_180109E10 = 0;
  dword_180109E18 = 2;
  memset(&modinfo, 0, sizeof(modinfo));
  if ( K32GetModuleInformation((HANDLE)0xFFFFFFFFFFFFFFFFLL, hModule, &modinfo, 0x18u) )
  {
    qword_180109B48 = (__int64)modinfo.lpBaseOfDll;
    qword_180109B50 = (__int64)modinfo.lpBaseOfDll + modinfo.SizeOfImage;
  }
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&xmmword_180109DD0) >= 0 )
  {
    byte_180109BE0 = 1;
    byte_180109BE0 = CModule::CompatShimExists(v8, v7);
    if ( byte_180109BE0 )
    {
      std::wstring::wstring(v27, L"c:\\windows\\system32");
      std::wstring::wstring(v28, L"wudfhost.exe");
      std::wstring::wstring(v29, L"svchost.exe");
      v20[0] = v27;
      v20[1] = Filename;
      std::vector<std::wstring>::vector<std::wstring>(v22, v20);
      `eh vector destructor iterator'(v27, 0x20u, 3u, std::wstring::~wstring);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl)
        && GetSystemDirectoryW(Buffer, 0x104u) )
      {
        std::wstring::wstring(v23, Buffer);
        v9 = v23;
        if ( v24 > 7 )
          v9 = (_WORD *)v23[0];
        v10 = *(unsigned __int16 **)std::wstring::end(v23, v20);
        v11 = (unsigned __int16 *)v23;
        if ( v24 > 7 )
          v11 = (unsigned __int16 *)v23[0];
        while ( v11 != v10 )
          *v9++ = _o_towlower(*v11++);
        std::wstring::operator=(v22[0], v23);
        std::wstring::_Tidy_deallocate(v23);
      }
      memset_0(Filename, 0, 0x208u);
      if ( GetModuleFileNameW(0, Filename, 0x104u) )
      {
        std::wstring::wstring(v25, Filename);
        v12 = v25;
        if ( v26 > 7 )
          v12 = (_WORD *)v25[0];
        v13 = *(unsigned __int16 **)std::wstring::end(v25, v20);
        v14 = (unsigned __int16 *)v25;
        if ( v26 > 7 )
          v14 = (unsigned __int16 *)v25[0];
        while ( v14 != v13 )
          *v12++ = _o_towlower(*v14++);
        v15 = v22[0];
        v16 = v22[1];
        while ( v15 != v16 )
        {
          if ( std::wstring::find(v25, v15) != -1 )
          {
            byte_180109BE0 = 0;
            break;
          }
          v15 += 32;
        }
        std::wstring::_Tidy_deallocate(v25);
      }
      std::vector<std::wstring>::_Tidy(v22);
      if ( byte_180109BE0 )
      {
        CModule::InitPresentEffectsEligibility((CModule *)g_Module);
        if ( (int)CModule::ApplyModeChangeOnLaunch(v17) < 0 )
          CModule::RecordJournalImpl(v18, -2147467259, "Failed to apply mode change on launch");
      }
    }
    HIDWORD(qword_180109A08) = IsProcessDWM();
  }
  else
  {
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  }
  return (CModule *)g_Module;
}

```

## disassembly

```asm
0x18005be40  push    rbp
0x18005be42  push    rbx
0x18005be43  push    rsi
0x18005be44  push    rdi
0x18005be45  push    r14
0x18005be47  push    r15
0x18005be49  lea     rbp, [rsp-448h]
0x18005be51  sub     rsp, 548h
0x18005be58  mov     rax, cs:__security_cookie
0x18005be5f  xor     rax, rsp
0x18005be62  mov     [rbp+470h+var_40], rax
0x18005be69  mov     rax, [rsp+570h+var_540]
0x18005be6e  mov     [rsp+570h+var_540], rax
0x18005be73  lea     r15, ?g_Module@@3VCModule@@A; CModule g_Module
0x18005be7a  mov     [rsp+570h+var_540], r15
0x18005be7f  xorps   xmm0, xmm0
0x18005be82  xor     eax, eax
0x18005be84  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x18005be8b  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x18005be92  mov     cs:CriticalSection.SpinCount, rax
0x18005be99  xor     r14d, r14d
0x18005be9c  mov     cs:qword_1801099A8, r14
0x18005bea3  mov     cs:qword_1801099B0, r14
0x18005beaa  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, r15; ATL::CAtlModule * ATL::_pAtlModule
0x18005beb1  mov     cs:qword_1801099E0, r14
0x18005beb8  lea     rcx, CriticalSection; this
0x18005bebf  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18005bec4  test    eax, eax
0x18005bec6  jns     short loc_18005BED1
0x18005bec8  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18005becf  jmp     short loc_18005BEDB
0x18005bed1  mov     dword ptr cs:qword_1801099A8, 38h ; '8'
0x18005bedb  mov     dl, 1; bool
0x18005bedd  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x18005bee2  nop
0x18005bee3  lea     rax, ??_7CModule@@6B@; const CModule::`vftable'
0x18005beea  mov     cs:?g_Module@@3VCModule@@A, rax; CModule g_Module
0x18005bef1  mov     cs:hObject, r14
0x18005bef8  mov     cs:qword_180109A08, r14
0x18005beff  xorps   xmm0, xmm0
0x18005bf02  movdqa  cs:xmmword_180109A10, xmm0
0x18005bf0a  mov     cs:byte_180109A20, r14b
0x18005bf11  mov     qword ptr cs:stru_180109A28.Data, r14
0x18005bf18  mov     cs:qword_180109A30, r14
0x18005bf1f  mov     cs:dword_180109A38, r14d
0x18005bf26  mov     cs:word_180109A3C, r14w
0x18005bf2e  mov     cs:byte_180109A3E, r14b
0x18005bf35  mov     cs:byte_180109A40, r14b
0x18005bf3c  mov     cs:qword_180109A48, r14
0x18005bf43  mov     qword ptr cs:stru_180109A50.Data, r14
0x18005bf4a  mov     cs:byte_180109A58, r14b
0x18005bf51  mov     cs:byte_180109A60, r14b
0x18005bf58  mov     cs:qword_180109A68, r14
0x18005bf5f  movdqa  cs:xmmword_180109A70, xmm0
0x18005bf67  xorps   xmm1, xmm1
0x18005bf6a  movdqa  cs:xmmword_180109A80, xmm1
0x18005bf72  mov     cs:dword_180109AA8, r14d
0x18005bf79  mov     cs:qword_180109AB8, r14
0x18005bf80  movdqa  cs:xmmword_180109AC0, xmm0
0x18005bf88  movdqa  cs:xmmword_180109AD0, xmm1
0x18005bf90  mov     cs:qword_180109AE0, r14
0x18005bf97  lea     rax, ??_7CDXGIMutexInSeparateThread@@6B@; const CDXGIMutexInSeparateThread::`vftable'
0x18005bf9e  mov     cs:qword_180109AB0, rax
0x18005bfa5  mov     cs:qword_180109AE8, r14
0x18005bfac  mov     cs:dword_180109AF0, r14d
0x18005bfb3  movdqa  cs:xmmword_180109B00, xmm0
0x18005bfbb  movdqa  cs:xmmword_180109B10, xmm1
0x18005bfc3  mov     cs:qword_180109B20, r14
0x18005bfca  mov     cs:qword_180109B28, r14
0x18005bfd1  mov     cs:qword_180109AF8, rax
0x18005bfd8  mov     cs:qword_180109B30, r14
0x18005bfdf  mov     cs:dword_180109B38, r14d
0x18005bfe6  mov     cs:lpMem, r14
0x18005bfed  movdqa  cs:xmmword_180109B60, xmm0
0x18005bff5  mov     cs:qword_180109B70, r14
0x18005bffc  mov     cs:qword_180109B78, r14
0x18005c003  mov     cs:byte_180109B81, r14b
0x18005c00a  mov     sil, 0FCh
0x18005c00d  and     cs:byte_180109B82, sil
0x18005c014  and     cs:byte_180109B83, sil
0x18005c01b  mov     cs:byte_180109B85, r14b
0x18005c022  mov     cs:byte_180109B88, r14b
0x18005c029  mov     cs:dword_180109B8C, r14d
0x18005c030  mov     cs:byte_180109B90, r14b
0x18005c037  mov     cs:dword_180109B94, r14d
0x18005c03e  mov     cs:byte_180109B98, r14b
0x18005c045  xor     eax, eax
0x18005c047  mov     cs:qword_180109B9C, rax
0x18005c04e  mov     cs:byte_180109BA4, r14b
0x18005c055  mov     cs:dword_180109BA6, 10000h
0x18005c05f  mov     cs:byte_180109BAC, r14b
0x18005c066  mov     cs:qword_180109BB0, rax
0x18005c06d  mov     cs:dword_180109BB8, eax
0x18005c073  mov     dword ptr cs:qword_180109BB0, r14d
0x18005c07a  mov     cs:byte_180109BBC, r14b
0x18005c081  and     cs:byte_180109BBD, sil
0x18005c088  and     cs:byte_180109BBE, sil
0x18005c08f  and     cs:byte_180109BBF, sil
0x18005c096  and     cs:byte_180109BC0, sil
0x18005c09d  and     cs:byte_180109BC1, sil
0x18005c0a4  and     cs:byte_180109BC8, sil
0x18005c0ab  and     cs:byte_180109BC9, sil
0x18005c0b2  and     cs:byte_180109BCA, sil
0x18005c0b9  mov     cs:word_180109BCB, r14w
0x18005c0c1  and     cs:byte_180109BCD, sil
0x18005c0c8  mov     cs:byte_180109BD0, r14b
0x18005c0cf  mov     cs:qword_180109BD8, r14
0x18005c0d6  mov     cs:word_180109BE1, r14w
0x18005c0de  mov     byte ptr cs:dword_180109BE4, r14b
0x18005c0e5  mov     word ptr cs:dword_180109BE4+2, r14w
0x18005c0ed  mov     cs:dword_180109BE8, eax
0x18005c0f3  mov     cs:qword_180109BEC, r14
0x18005c0fa  mov     cs:qword_180109BF4, r14
0x18005c101  mov     cs:qword_180109BFC, r14
0x18005c108  mov     cs:qword_180109C04, r14
0x18005c10f  mov     cs:byte_180109C0C, r14b
0x18005c116  mov     cs:word_180109C0E, r14w
0x18005c11e  mov     cs:byte_180109C10, r14b
0x18005c125  movups  cs:xmmword_180109C18, xmm0
0x18005c12c  and     cs:byte_180109C28, sil
0x18005c133  mov     cs:byte_180109C30, r14b
0x18005c13a  mov     cs:qword_180109C38, rax
0x18005c141  mov     cs:byte_180109C40, r14b
0x18005c148  mov     cs:qword_180109C48, rax
0x18005c14f  and     cs:byte_180109C50, sil
0x18005c156  mov     cs:byte_180109C5C, r14b
0x18005c15d  mov     cs:qword_180109C60, rax
0x18005c164  mov     cs:byte_180109C68, r14b
0x18005c16b  mov     cs:byte_180109C6C, r14b
0x18005c172  mov     cs:dword_180109C70, eax
0x18005c178  lea     rcx, qword_180109C78
0x18005c17f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18005c184  nop
0x18005c185  mov     cs:byte_180109C98, r14b
0x18005c18c  xor     eax, eax
0x18005c18e  mov     cs:dword_180109C9C, eax
0x18005c194  lea     rbx, qword_180109CA0
0x18005c19b  lea     edi, [rax+3]
0x18005c19e  mov     rcx, rbx; this
0x18005c1a1  call    ??0EffectCreationInfo@CModule@@QEAA@XZ; CModule::EffectCreationInfo::EffectCreationInfo(void)
0x18005c1a6  add     rbx, 38h ; '8'
0x18005c1aa  sub     rdi, 1
0x18005c1ae  jnz     short loc_18005C19E
0x18005c1b0  mov     cs:byte_180109D48, r14b
0x18005c1b7  xorps   xmm0, xmm0
0x18005c1ba  movups  cs:xmmword_180109D4C, xmm0
0x18005c1c1  mov     cs:qword_180109D60, r14
0x18005c1c8  mov     cs:qword_180109D68, r14
0x18005c1cf  lea     ecx, [rdi+30h]; dwBytes
0x18005c1d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c1d7  mov     [rax], rax
0x18005c1da  mov     [rax+8], rax
0x18005c1de  mov     [rax+10h], rax
0x18005c1e2  mov     word ptr [rax+18h], 101h
0x18005c1e8  mov     cs:qword_180109D60, rax
0x18005c1ef  xor     eax, eax
0x18005c1f1  mov     cs:qword_180109D70, rax
0x18005c1f8  mov     cs:byte_180109D78, r14b
0x18005c1ff  mov     cs:qword_180109D80, r14
0x18005c206  mov     cs:qword_180109D88, r14
0x18005c20d  mov     cs:qword_180109D90, r14
0x18005c214  lea     ecx, [rdi+1]
0x18005c217  call    ??$_Get_size_of_n@$0CI@@std@@YA_K_K@Z; std::_Get_size_of_n<40>(unsigned __int64)
0x18005c21c  mov     rcx, rax
0x18005c21f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18005c224  mov     [rax], rax
0x18005c227  mov     [rax+8], rax
0x18005c22b  mov     [rax+10h], rax
0x18005c22f  mov     word ptr [rax+18h], 101h
0x18005c235  mov     cs:qword_180109D88, rax
0x18005c23c  mov     cs:byte_180109D98, r14b
0x18005c243  xor     eax, eax
0x18005c245  mov     cs:dword_180109D9C, eax
0x18005c24b  and     cs:byte_180109DA0, sil
0x18005c252  mov     cs:byte_180109DA4, r14b
0x18005c259  mov     cs:dword_180109DA8, eax
0x18005c25f  mov     cs:byte_180109DB8, r14b
0x18005c266  mov     cs:qword_180109DC0, rax
0x18005c26d  and     cs:byte_180109DC8, sil
0x18005c274  and     cs:byte_180109DC9, sil
0x18005c27b  mov     cs:dword_180109DCC, r14d
0x18005c282  xorps   xmm0, xmm0
0x18005c285  movups  cs:xmmword_180109DD0, xmm0
0x18005c28c  movups  cs:xmmword_180109DE0, xmm0
0x18005c293  mov     cs:qword_180109DF0, rax
0x18005c29a  mov     cs:byte_180109DF8, r14b
0x18005c2a1  mov     cs:qword_180109E10, r14
0x18005c2a8  mov     cs:dword_180109E18, 2
0x18005c2b2  movups  xmmword ptr [rsp+570h+modinfo.lpBaseOfDll], xmm0
0x18005c2b7  mov     [rsp+570h+modinfo.EntryPoint], rax
0x18005c2bc  lea     r9d, [rdi+18h]; cb
0x18005c2c0  lea     r8, [rsp+570h+modinfo]; lpmodinfo
0x18005c2c5  mov     rdx, cs:hModule; hModule
0x18005c2cc  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x18005c2d0  call    cs:__imp_K32GetModuleInformation
0x18005c2d6  test    eax, eax
0x18005c2d8  jz      short loc_18005C2F4
0x18005c2da  mov     rcx, [rsp+570h+modinfo.lpBaseOfDll]
0x18005c2df  mov     cs:qword_180109B48, rcx
0x18005c2e6  mov     eax, [rsp+570h+modinfo.SizeOfImage]
0x18005c2ea  add     rax, rcx
0x18005c2ed  mov     cs:qword_180109B50, rax
0x18005c2f4  lea     rcx, xmmword_180109DD0; this
0x18005c2fb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18005c300  test    eax, eax
0x18005c302  jns     short loc_18005C310
0x18005c304  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18005c30b  jmp     loc_18005C534
0x18005c310  mov     cs:byte_180109BE0, 1
0x18005c317  call    ?CompatShimExists@CModule@@AEAA_NPEBD@Z; CModule::CompatShimExists(char const *)
0x18005c31c  mov     cs:byte_180109BE0, al
0x18005c322  test    al, al
0x18005c324  jz      loc_18005C529
0x18005c32a  lea     rdx, aCWindowsSystem; "c:\\windows\\system32"
0x18005c331  lea     rcx, [rbp+470h+var_4C0]
0x18005c335  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c33a  nop
0x18005c33b  lea     rdx, aWudfhostExe; "wudfhost.exe"
0x18005c342  lea     rcx, [rbp+470h+var_4A0]
0x18005c346  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c34b  nop
0x18005c34c  lea     rdx, aSvchostExe; "svchost.exe"
0x18005c353  lea     rcx, [rbp+470h+var_480]
0x18005c357  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c35c  nop
0x18005c35d  lea     rax, [rbp+470h+var_4C0]
0x18005c361  mov     [rsp+570h+var_550], rax
0x18005c366  lea     rax, [rbp+470h+Filename]
0x18005c36a  mov     [rsp+570h+var_548], rax
0x18005c36f  lea     rdx, [rsp+570h+var_550]
0x18005c374  lea     rcx, [rsp+570h+var_518]
0x18005c379  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(std::initializer_list<std::wstring>,std::allocator<std::wstring> const &)
0x18005c37e  nop
0x18005c37f  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18005c386  mov     edx, 20h ; ' '; unsigned __int64
0x18005c38b  lea     r8d, [rdx-1Dh]; unsigned __int64
0x18005c38f  lea     rcx, [rbp+470h+var_4C0]; void *
0x18005c393  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18005c398  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x18005c39f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x18005c3a4  test    al, al
0x18005c3a6  jz      loc_18005C439
0x18005c3ac  mov     edx, 104h; uSize
0x18005c3b1  lea     rcx, [rbp+470h+Buffer]; lpBuffer
0x18005c3b8  call    cs:__imp_GetSystemDirectoryW
0x18005c3be  test    eax, eax
0x18005c3c0  jz      short loc_18005C439
0x18005c3c2  lea     rdx, [rbp+470h+Buffer]
0x18005c3c9  lea     rcx, [rsp+570h+var_500]
0x18005c3ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c3d3  lea     rsi, [rsp+570h+var_500]
0x18005c3d8  cmp     [rbp+470h+var_4E8], 7
0x18005c3dd  cmova   rsi, [rsp+570h+var_500]
0x18005c3e3  lea     rdx, [rsp+570h+var_550]
0x18005c3e8  lea     rcx, [rsp+570h+var_500]
0x18005c3ed  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18005c3f2  mov     rbx, [rax]
0x18005c3f5  lea     rdi, [rsp+570h+var_500]
0x18005c3fa  cmp     [rbp+470h+var_4E8], 7
0x18005c3ff  cmova   rdi, [rsp+570h+var_500]
0x18005c405  jmp     short loc_18005C41B
0x18005c407  movzx   ecx, word ptr [rdi]
0x18005c40a  call    cs:__imp__o_towlower
0x18005c410  mov     [rsi], ax
0x18005c413  lea     rsi, [rsi+2]
0x18005c417  add     rdi, 2
0x18005c41b  cmp     rdi, rbx
0x18005c41e  jnz     short loc_18005C407
0x18005c420  lea     rdx, [rsp+570h+var_500]
0x18005c425  mov     rcx, [rsp+570h+var_518]
0x18005c42a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005c42f  lea     rcx, [rsp+570h+var_500]
0x18005c434  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c439  xor     edx, edx; Val
0x18005c43b  mov     r8d, 208h; Size
0x18005c441  lea     rcx, [rbp+470h+Filename]; void *
0x18005c445  call    memset_0
0x18005c44a  mov     r8d, 104h; nSize
0x18005c450  lea     rdx, [rbp+470h+Filename]; lpFilename
0x18005c454  xor     ecx, ecx; hModule
0x18005c456  call    cs:__imp_GetModuleFileNameW
0x18005c45c  test    eax, eax
0x18005c45e  jz      loc_18005C4F3
0x18005c464  lea     rdx, [rbp+470h+Filename]
0x18005c468  lea     rcx, [rbp+470h+var_4E0]
0x18005c46c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c471  lea     rsi, [rbp+470h+var_4E0]
0x18005c475  cmp     [rbp+470h+var_4C8], 7
0x18005c47a  cmova   rsi, [rbp+470h+var_4E0]
0x18005c47f  lea     rdx, [rsp+570h+var_550]
0x18005c484  lea     rcx, [rbp+470h+var_4E0]
0x18005c488  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18005c48d  mov     rbx, [rax]
0x18005c490  lea     rdi, [rbp+470h+var_4E0]
0x18005c494  cmp     [rbp+470h+var_4C8], 7
0x18005c499  cmova   rdi, [rbp+470h+var_4E0]
0x18005c49e  jmp     short loc_18005C4B4
0x18005c4a0  movzx   ecx, word ptr [rdi]
0x18005c4a3  call    cs:__imp__o_towlower
0x18005c4a9  mov     [rsi], ax
  ... truncated ...
```
