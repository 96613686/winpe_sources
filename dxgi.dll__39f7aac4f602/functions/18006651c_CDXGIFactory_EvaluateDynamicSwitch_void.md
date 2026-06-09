# CDXGIFactory::EvaluateDynamicSwitch(void)

- ea: `0x18006651c`
- end: `0x18006673c`
- name: `?EvaluateDynamicSwitch@CDXGIFactory@@AEAA?AU_DYNAMIC_SWITCH_DECISION@@XZ`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f008`

## callees

- `0x180018408`
- `0x180019650`
- `0x18003f86c`
- `0x18006651c`
- `0x180075fa0`
- `0x180076f20`
- `0x180091e70`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180066579`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180066579`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryUserSettings` at `0x1800665bd`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryUserSettings` at `0x1800665bd`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabase` at `0x180066608`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabase` at `0x180066608`
- `ext-ms-win-dx-dxdbhelper-l1-1-3!__imp_QueryFinalDynamicSwitchPreferenceDecision` at `0x1800666c8`
- `ext-ms-win-dx-dxdbhelper-l1-1-3!__imp_QueryFinalDynamicSwitchPreferenceDecision` at `0x1800666c8`

## string_xrefs

- `0x1800665ce`: `onecoreuap\windows\directx\dxg\dxgi\dll\factory.cpp`
- `0x180066619`: `onecoreuap\windows\directx\dxg\dxgi\dll\factory.cpp`
- `0x1800666d9`: `onecoreuap\windows\directx\dxg\dxgi\dll\factory.cpp`

## pseudocode

```c
__int64 __fastcall CDXGIFactory::EvaluateDynamicSwitch(__int64 a1, __int64 a2)
{
  int UserSettings; // eax
  int v5; // eax
  int DirectXDatabase; // eax
  int AdapterIndexByGpuPreference; // eax
  unsigned int v8; // esi
  bool v9; // bl
  int FinalDynamicSwitchPreferenceDecision; // eax
  int v12[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v13; // [rsp+38h] [rbp-C8h]
  _BYTE v14[376]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v15; // [rsp+1C8h] [rbp+C8h]
  int v16; // [rsp+1E8h] [rbp+E8h]
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+270h] [rbp+170h] BYREF
  int v18; // [rsp+290h] [rbp+190h]
  unsigned int v19; // [rsp+568h] [rbp+468h]
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  memset_0(&requestPacket.adapterId, 0, 0x300u);
  requestPacket.type = -34;
  requestPacket.size = 776;
  if ( DisplayConfigGetDeviceInfo(&requestPacket) || v19 <= 1 || !v18 )
  {
    *(_DWORD *)(a2 + 8) = 5;
    goto LABEL_21;
  }
  v12[0] = 0;
  v12[1] = 4;
  UserSettings = QueryUserSettings(0, 0, 0, v12);
  if ( UserSettings < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13DF,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\factory.cpp",
      (const char *)(unsigned int)UserSettings,
      4);
  v5 = v12[0];
  if ( !v12[0] )
  {
    DirectXDatabase = QueryDirectXDatabase(0, 0, 0, 0);
    if ( DirectXDatabase < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13E2,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\factory.cpp",
        (const char *)(unsigned int)DirectXDatabase,
        (int)v12);
    v5 = v12[0];
  }
  if ( v5 == 0x80000000 )
  {
    *(_DWORD *)(a2 + 8) = 7;
LABEL_21:
    *(_DWORD *)(a2 + 12) = 3000;
    *(_QWORD *)a2 = 0;
    return a2;
  }
  if ( v5 == 2 )
  {
    AdapterIndexByGpuPreference = SAdapterDesc::GetAdapterIndexByGpuPreference(0, 2, a1 + 280, 0);
    SAdapterDesc::SAdapterDesc(
      (SAdapterDesc *)v14,
      (const struct SAdapterDesc *)(*(_QWORD *)(a1 + 280) + 536LL * AdapterIndexByGpuPreference));
    v8 = v15;
    v9 = (v16 & 0x10) != 0;
    SAdapterDesc::~SAdapterDesc((SAdapterDesc *)v14);
  }
  else
  {
    v9 = 0;
    v8 = 0;
  }
  v13 = 0;
  if ( v9 )
  {
    FinalDynamicSwitchPreferenceDecision = QueryFinalDynamicSwitchPreferenceDecision(0, 0, v8, EscapeCB);
    if ( FinalDynamicSwitchPreferenceDecision < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1401,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\factory.cpp",
        (const char *)(unsigned int)FinalDynamicSwitchPreferenceDecision,
        0);
  }
  else
  {
    DWORD2(v13) = 6;
  }
  *(_OWORD *)a2 = v13;
  return a2;
}

```

## disassembly

```asm
0x18006651c  mov     [rsp-8+arg_10], rbx
0x180066521  push    rbp
0x180066522  push    rsi
0x180066523  push    rdi
0x180066524  lea     rbp, [rsp-490h]
0x18006652c  sub     rsp, 590h
0x180066533  mov     rax, cs:__security_cookie
0x18006653a  xor     rax, rsp
0x18006653d  mov     [rbp+4A0h+var_20], rax
0x180066544  mov     rdi, rdx
0x180066547  mov     rbx, rcx
0x18006654a  xor     edx, edx; Val
0x18006654c  lea     rcx, [rbp+4A0h+requestPacket.adapterId]; void *
0x180066553  mov     r8d, 300h; Size
0x180066559  call    memset_0
0x18006655e  lea     rcx, [rbp+4A0h+requestPacket]; requestPacket
0x180066565  mov     [rbp+4A0h+requestPacket.type], 0FFFFFFDEh
0x18006656f  mov     [rbp+4A0h+requestPacket.size], 308h
0x180066579  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18006657f  test    eax, eax
0x180066581  jnz     loc_180066702
0x180066587  cmp     [rbp+4A0h+var_38], 1
0x18006658e  jbe     loc_180066702
0x180066594  cmp     [rbp+4A0h+var_310], eax
0x18006659a  jz      loc_180066702
0x1800665a0  mov     [rsp+5A0h+var_570], eax
0x1800665a4  lea     r9, [rsp+5A0h+var_570]
0x1800665a9  mov     eax, 4
0x1800665ae  xor     r8d, r8d
0x1800665b1  xor     edx, edx
0x1800665b3  mov     [rsp+5A0h+var_56C], eax
0x1800665b7  xor     ecx, ecx
0x1800665b9  mov     [rsp+5A0h+var_580], eax; int
0x1800665bd  call    cs:__imp_QueryUserSettings
0x1800665c3  test    eax, eax
0x1800665c5  jns     short loc_1800665E2
0x1800665c7  mov     rcx, [rbp+4A8h]; this
0x1800665ce  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x1800665d5  mov     r9d, eax; char *
0x1800665d8  mov     edx, 13DFh; void *
0x1800665dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800665e2  mov     eax, [rsp+5A0h+var_570]
0x1800665e6  test    eax, eax
0x1800665e8  jnz     short loc_180066631
0x1800665ea  lea     rax, [rsp+5A0h+var_56C]
0x1800665ef  xor     r9d, r9d
0x1800665f2  mov     [rsp+5A0h+var_578], rax
0x1800665f7  xor     r8d, r8d
0x1800665fa  lea     rax, [rsp+5A0h+var_570]
0x1800665ff  xor     edx, edx
0x180066601  xor     ecx, ecx
0x180066603  mov     qword ptr [rsp+5A0h+var_580], rax; int
0x180066608  call    cs:__imp_QueryDirectXDatabase
0x18006660e  test    eax, eax
0x180066610  jns     short loc_18006662D
0x180066612  mov     rcx, [rbp+4A8h]; this
0x180066619  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x180066620  mov     r9d, eax; char *
0x180066623  mov     edx, 13E2h; void *
0x180066628  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006662d  mov     eax, [rsp+5A0h+var_570]
0x180066631  cmp     eax, 80000000h
0x180066636  jnz     short loc_180066644
0x180066638  mov     dword ptr [rdi+8], 7
0x18006663f  jmp     loc_180066709
0x180066644  mov     edx, 2
0x180066649  cmp     eax, edx
0x18006664b  jnz     short loc_180066697
0x18006664d  xor     r9d, r9d
0x180066650  lea     r8, [rbx+118h]
0x180066657  xor     ecx, ecx
0x180066659  call    ?GetAdapterIndexByGpuPreference@SAdapterDesc@@SAIIW4DXGI_GPU_PREFERENCE@@AEBV?$vector@USAdapterDesc@@V?$allocator@USAdapterDesc@@@std@@@std@@PEAV?$vector@U?$pair@PEBUSAdapterDesc@@I@std@@V?$allocator@U?$pair@PEBUSAdapterDesc@@I@std@@@2@@4@@Z; SAdapterDesc::GetAdapterIndexByGpuPreference(uint,DXGI_GPU_PREFERENCE,std::vector<SAdapterDesc> const &,std::vector<std::pair<SAdapterDesc const *,uint>> *)
0x18006665e  movsxd  rcx, eax
0x180066661  imul    rdx, rcx, 218h
0x180066668  lea     rcx, [rsp+5A0h+var_550]; this
0x18006666d  add     rdx, [rbx+118h]; struct SAdapterDesc *
0x180066674  call    ??0SAdapterDesc@@QEAA@AEBU0@@Z; SAdapterDesc::SAdapterDesc(SAdapterDesc const &)
0x180066679  mov     ebx, [rbp+4A0h+var_3B8]
0x18006667f  lea     rcx, [rsp+5A0h+var_550]; this
0x180066684  mov     esi, [rbp+4A0h+var_3D8]
0x18006668a  shr     ebx, 4
0x18006668d  and     bl, 1
0x180066690  call    ??1SAdapterDesc@@QEAA@XZ; SAdapterDesc::~SAdapterDesc(void)
0x180066695  jmp     short loc_18006669B
0x180066697  xor     bl, bl
0x180066699  xor     esi, esi
0x18006669b  xorps   xmm0, xmm0
0x18006669e  movups  [rsp+5A0h+var_568], xmm0
0x1800666a3  test    bl, bl
0x1800666a5  jz      short loc_1800666EF
0x1800666a7  lea     rax, [rsp+5A0h+var_568]
0x1800666ac  mov     r8d, esi
0x1800666af  mov     [rsp+5A0h+var_578], rax
0x1800666b4  lea     r9, ?EscapeCB@@YAJPEAXPEBU_D3DDDICB_ESCAPE@@@Z; EscapeCB(void *,_D3DDDICB_ESCAPE const *)
0x1800666bb  xor     edx, edx
0x1800666bd  mov     qword ptr [rsp+5A0h+var_580], 0; int
0x1800666c6  xor     ecx, ecx
0x1800666c8  call    cs:__imp_QueryFinalDynamicSwitchPreferenceDecision
0x1800666ce  test    eax, eax
0x1800666d0  jns     short loc_1800666F7
0x1800666d2  mov     rcx, [rbp+4A8h]; this
0x1800666d9  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x1800666e0  mov     r9d, eax; char *
0x1800666e3  mov     edx, 1401h; void *
0x1800666e8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800666ed  jmp     short loc_1800666F7
0x1800666ef  mov     dword ptr [rsp+5A0h+var_568+8], 6
0x1800666f7  movups  xmm0, [rsp+5A0h+var_568]
0x1800666fc  movdqu  xmmword ptr [rdi], xmm0
0x180066700  jmp     short loc_180066717
0x180066702  mov     dword ptr [rdi+8], 5
0x180066709  mov     dword ptr [rdi+0Ch], 0BB8h
0x180066710  mov     qword ptr [rdi], 0
0x180066717  mov     rax, rdi
0x18006671a  mov     rcx, [rbp+4A0h+var_20]
0x180066721  xor     rcx, rsp; StackCookie
0x180066724  call    __security_check_cookie
0x180066729  mov     rbx, [rsp+5A0h+arg_10]
0x180066731  add     rsp, 590h
0x180066738  pop     rdi
0x180066739  pop     rsi
0x18006673a  pop     rbp
0x18006673b  retn
```
