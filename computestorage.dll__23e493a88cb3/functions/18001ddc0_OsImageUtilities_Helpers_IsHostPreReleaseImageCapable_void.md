# OsImageUtilities::Helpers::IsHostPreReleaseImageCapable(void)

- ea: `0x18001ddc0`
- end: `0x18001dfde`
- name: `?IsHostPreReleaseImageCapable@Helpers@OsImageUtilities@@YA_NXZ`
- size: `542`
- prototype: `bool __fastcall(OsImageUtilities::Helpers *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ea88`

## callees

- `0x180002690`
- `0x1800026b4`
- `0x1800127bc`
- `0x18001ddc0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001de14`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001de14`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001dde5`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001dde5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001def4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001df76`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001def4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001df76`

## string_xrefs

- `0x18001dfb7`: `onecore\vm\common\mgmt\inc\VirtualizationSettings.h`
- `0x18001df9f`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001dfcc`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
bool __fastcall OsImageUtilities::Helpers::IsHostPreReleaseImageCapable(OsImageUtilities::Helpers *this)
{
  bool v1; // bl
  _QWORD *v2; // rdi
  bool v3; // si
  LPVOID v4; // rcx
  int v6; // eax
  int v7; // eax
  LPVOID v8; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  __int16 v10[2]; // [rsp+50h] [rbp-20h] BYREF
  __int16 v11; // [rsp+54h] [rbp-1Ch] BYREF
  LPVOID v12; // [rsp+58h] [rbp-18h] BYREF
  __int64 v13; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v1 = 1;
  RoInitialize(1);
  v12 = 0;
  if ( CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &v12) >= 0 )
  {
    v10[0] = 0;
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v12 + 24LL))(v12, v10);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        (const char *)(unsigned int)v6,
        ppv);
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v12 + 112LL))(v12, &v11);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    if ( v10[0] != -1 )
      v1 = v11 == 0;
    v8 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    }
    RoUninitialize();
    return v1;
  }
  else
  {
    v2 = operator new(0x30u);
    *v2 = &Vml::VmMachineLocalSettingsStore::`vftable';
    v2[1] = 0;
    *((_OWORD *)v2 + 1) = 0;
    v2[4] = 0;
    v2[5] = 7;
    *((_WORD *)v2 + 8) = 0;
    v13 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD, __int64))(*v2 + 8LL))(v2, 0, 131097) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\vm\\common\\mgmt\\inc\\VirtualizationSettings.h",
        (const char *)0x8000FFFFLL,
        ppv);
    LODWORD(v13) = 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, const unsigned __int16 *, __int64 *))(*v2 + 56LL))(
           v2,
           L"AzureFeatureSet",
           &v13) )
    {
      v3 = (_DWORD)v13 != 0;
    }
    else
    {
      v3 = 0;
    }
    (*(void (__fastcall **)(_QWORD *, __int64))*v2)(v2, 1);
    v4 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    RoUninitialize();
    return v3;
  }
}

```

## disassembly

```asm
0x18001ddc0  push    rbp
0x18001ddc2  push    rbx
0x18001ddc3  push    rsi
0x18001ddc4  push    rdi
0x18001ddc5  push    r14
0x18001ddc7  mov     rbp, rsp
0x18001ddca  sub     rsp, 70h
0x18001ddce  mov     rax, cs:__security_cookie
0x18001ddd5  xor     rax, rsp
0x18001ddd8  mov     [rbp+var_8], rax
0x18001dddc  xor     r14d, r14d
0x18001dddf  lea     ebx, [r14+1]
0x18001dde3  mov     ecx, ebx
0x18001dde5  call    cs:__imp_RoInitialize
0x18001ddec  nop     dword ptr [rax+rax+00h]
0x18001ddf1  mov     [rbp+var_3F], bl
0x18001ddf4  mov     [rbp+var_18], r14
0x18001ddf8  lea     rax, [rbp+var_18]
0x18001ddfc  mov     qword ptr [rsp+70h+ppv], rax; int
0x18001de01  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x18001de08  mov     r8d, ebx; dwClsContext
0x18001de0b  xor     edx, edx; pUnkOuter
0x18001de0d  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x18001de14  call    cs:__imp_CoCreateInstance
0x18001de1b  nop     dword ptr [rax+rax+00h]
0x18001de20  test    eax, eax
0x18001de22  jns     loc_18001DF05
0x18001de28  xorps   xmm0, xmm0
0x18001de2b  movups  [rbp+var_38], xmm0
0x18001de2f  lea     ecx, [rbx+2Fh]; Size
0x18001de32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001de37  mov     rdi, rax
0x18001de3a  lea     rax, ??_7VmMachineLocalSettingsStore@Vml@@6B@; const Vml::VmMachineLocalSettingsStore::`vftable'
0x18001de41  mov     [rdi], rax
0x18001de44  mov     [rdi+8], r14
0x18001de48  xorps   xmm0, xmm0
0x18001de4b  movups  xmmword ptr [rdi+10h], xmm0
0x18001de4f  mov     [rdi+20h], r14
0x18001de53  mov     qword ptr [rdi+28h], 7
0x18001de5b  mov     [rdi+10h], r14w
0x18001de60  mov     [rbp+var_10], r14
0x18001de64  lea     rax, ??_7VirtualizationSettings@@6B@; const VirtualizationSettings::`vftable'
0x18001de6b  mov     qword ptr [rbp+var_38], rax
0x18001de6f  mov     [rbp+var_28], r14
0x18001de73  mov     qword ptr [rbp+var_38+8], rdi
0x18001de77  mov     rax, [rdi]
0x18001de7a  xor     edx, edx
0x18001de7c  mov     r8d, 20019h
0x18001de82  mov     rcx, rdi
0x18001de85  mov     rax, [rax+8]
0x18001de89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de8e  mov     rcx, [rbp+28h]; this
0x18001de92  test    al, al
0x18001de94  jz      loc_18001DFB1
0x18001de9a  mov     dword ptr [rbp+var_10], r14d
0x18001de9e  mov     rax, [rdi]
0x18001dea1  lea     r8, [rbp+var_10]
0x18001dea5  lea     rdx, ?AzureFeatureSetEnabled@VirtualizationSettings@@2QBGB; "AzureFeatureSet"
0x18001deac  mov     rcx, rdi
0x18001deaf  mov     rax, [rax+38h]
0x18001deb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deb8  test    al, al
0x18001deba  jz      short loc_18001DEC6
0x18001debc  cmp     dword ptr [rbp+var_10], r14d
0x18001dec0  setnz   sil
0x18001dec4  jmp     short loc_18001DEC9
0x18001dec6  mov     sil, r14b
0x18001dec9  mov     rax, [rdi]
0x18001decc  mov     edx, ebx
0x18001dece  mov     rcx, rdi
0x18001ded1  mov     rax, [rax]
0x18001ded4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ded9  nop
0x18001deda  mov     rcx, [rbp+var_18]
0x18001dede  test    rcx, rcx
0x18001dee1  jz      short loc_18001DEF4
0x18001dee3  mov     [rbp+var_18], r14
0x18001dee7  mov     rdx, [rcx]
0x18001deea  mov     rax, [rdx+10h]
0x18001deee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001def3  nop
0x18001def4  call    cs:__imp_RoUninitialize
0x18001defb  nop     dword ptr [rax+rax+00h]
0x18001df00  mov     al, sil
0x18001df03  jmp     short loc_18001DF84
0x18001df05  mov     [rbp+var_20], r14w
0x18001df0a  mov     rcx, [rbp+var_18]
0x18001df0e  mov     rax, [rcx]
0x18001df11  lea     rdx, [rbp+var_20]
0x18001df15  mov     rax, [rax+18h]
0x18001df19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df1e  mov     rcx, [rbp+28h]; this
0x18001df22  test    eax, eax
0x18001df24  js      loc_18001DFC9
0x18001df2a  mov     [rbp+var_1C], r14w
0x18001df2f  mov     rcx, [rbp+var_18]
0x18001df33  mov     rax, [rcx]
0x18001df36  lea     rdx, [rbp+var_1C]
0x18001df3a  mov     rax, [rax+70h]
0x18001df3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df43  mov     rcx, [rbp+28h]; this
0x18001df47  test    eax, eax
0x18001df49  js      short loc_18001DF9C
0x18001df4b  cmp     [rbp+var_20], 0FFFFh
0x18001df50  jz      short loc_18001DF5C
0x18001df52  cmp     [rbp+var_1C], r14w
0x18001df57  jz      short loc_18001DF5C
0x18001df59  mov     bl, r14b
0x18001df5c  mov     rcx, [rbp+var_18]
0x18001df60  test    rcx, rcx
0x18001df63  jz      short loc_18001DF76
0x18001df65  mov     [rbp+var_18], r14
0x18001df69  mov     rax, [rcx]
0x18001df6c  mov     rax, [rax+10h]
0x18001df70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df75  nop
0x18001df76  call    cs:__imp_RoUninitialize
0x18001df7d  nop     dword ptr [rax+rax+00h]
0x18001df82  mov     al, bl
0x18001df84  mov     rcx, [rbp+var_8]
0x18001df88  xor     rcx, rsp; StackCookie
0x18001df8b  call    __security_check_cookie
0x18001df90  add     rsp, 70h
0x18001df94  pop     r14
0x18001df96  pop     rdi
0x18001df97  pop     rsi
0x18001df98  pop     rbx
0x18001df99  pop     rbp
0x18001df9a  retn
0x18001df9c  mov     r9d, eax; char *
0x18001df9f  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001dfa6  mov     edx, 171h; void *
0x18001dfab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dfb1  mov     r9d, 8000FFFFh; char *
0x18001dfb7  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\mgmt\\inc\\Virtual"...
0x18001dfbe  mov     edx, 0ABh; void *
0x18001dfc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dfc9  mov     r9d, eax; char *
0x18001dfcc  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001dfd3  mov     edx, 16Eh; void *
0x18001dfd8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
