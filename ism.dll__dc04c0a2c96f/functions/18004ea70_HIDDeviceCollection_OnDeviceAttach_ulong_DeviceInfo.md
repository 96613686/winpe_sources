# HIDDeviceCollection::OnDeviceAttach(ulong,DeviceInfo * *)

- ea: `0x18004ea70`
- end: `0x18004ed77`
- name: `?OnDeviceAttach@HIDDeviceCollection@@MEAAJKPEAPEAUDeviceInfo@@@Z`
- size: `775`
- prototype: `__int64 __fastcall(HIDDeviceCollection *__hidden this, unsigned int, struct DeviceInfo **)`
- caller_count: `12`
- callee_count: `14`
- tags: `reparse_path`

## callers

- `0x18004e990`
- `0x180099200`
- `0x1800e67c0`
- `0x180118170`
- `0x18011d4d0`
- `0x18011e3a0`
- `0x18011ece0`
- `0x18011f0c0`
- `0x18011f640`
- `0x180120a20`
- `0x180120f90`
- `0x180121360`

## callees

- `0x18002f9b4`
- `0x18004ea70`
- `0x18004ed80`
- `0x180080774`
- `0x180089c4c`
- `0x18008dcac`
- `0x18008ead4`
- `0x1800af9b8`
- `0x1800f08d8`
- `0x1800f0990`
- `0x1800f0acc`
- `0x1800f246c`
- `0x180121790`
- `0x1801ce010`

## import_xrefs

- `HID!HidP_GetCaps` at `0x18004eb92`
- `HID!HidP_GetCaps` at `0x18004eb92`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDeviceProperties` at `0x18004ebe4`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDeviceProperties` at `0x18004ebe4`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDevicePreparsedData` at `0x18004eb35`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDevicePreparsedData` at `0x18004eb6e`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDevicePreparsedData` at `0x18004eb35`
- `ext-ms-win-ntuser-rim-l1-1-0!RIMGetDevicePreparsedData` at `0x18004eb6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HIDDeviceCollection::OnDeviceAttach(HIDDeviceCollection *this, int a2, struct DeviceInfo **a3)
{
  __int64 v5; // rdi
  __int64 i; // rcx
  __int64 v7; // rsi
  __int64 v8; // r13
  int v9; // eax
  _DWORD *v10; // r12
  NTSTATUS Caps; // eax
  HIDDeviceCollection *v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned __int16 v16; // dx
  unsigned __int16 v17; // r8
  unsigned __int16 v18; // r9
  __int64 v20; // rdx
  _DWORD *v21; // rbx
  __int64 v22; // rdx
  size_t Size; // [rsp+20h] [rbp-79h] BYREF
  __int64 v24; // [rsp+28h] [rbp-71h] BYREF
  _DWORD *v25; // [rsp+30h] [rbp-69h] BYREF
  int v26; // [rsp+38h] [rbp-61h]
  int v27; // [rsp+3Ch] [rbp-5Dh] BYREF
  _OWORD v28[2]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v29; // [rsp+60h] [rbp-39h]
  _HIDP_CAPS Capabilities; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v26 = a2;
  v27 = 0;
  LODWORD(Size) = 0;
  v24 = 0;
  memset(v28, 0, sizeof(v28));
  v29 = 0;
  if ( !a3 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\hiddevicecollection.cpp",
      (const char *)0x8000FFFFLL,
      Size);
  v5 = (__int64)*a3;
  if ( !*a3 )
  {
    v21 = operator new(0x60Cu);
    v25 = v21;
    memset_0(v21, 0, 0x60Cu);
    v21[2] = 1548;
    std::unique_ptr<LegacyDeviceInfo>::reset(&v24, v21);
    v5 = v24;
    if ( !v24 )
    {
      v14 = -2147024882;
      v20 = 243;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\hiddevicecollection.cpp",
        (const char *)v14,
        Size);
LABEL_19:
      std::unique_ptr<LegacyDeviceInfo>::~unique_ptr<LegacyDeviceInfo>(&v24);
      return v14;
    }
    a2 = v26;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0x100 )
    {
      v14 = -2147023728;
      v20 = 248;
      goto LABEL_18;
    }
    v7 = *((_QWORD *)this + i + 78);
    if ( v7 )
    {
      if ( !*(_QWORD *)(v7 + 16) || *(_DWORD *)(v7 + 40) == a2 )
        break;
    }
  }
  if ( !(*(unsigned __int8 (__fastcall **)(HIDDeviceCollection *, _QWORD))(*(_QWORD *)this + 104LL))(
          this,
          *((_QWORD *)this + i + 78)) )
  {
    v14 = -2147418113;
    v20 = 252;
    goto LABEL_18;
  }
  v8 = *(_QWORD *)(v7 + 16);
  v9 = RIMGetDevicePreparsedData(*((_QWORD *)this + 10), v8, 0, &Size);
  if ( v9 < 0 )
  {
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x10B,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\hiddevicecollection.cpp",
            (const char *)(unsigned int)v9,
            Size);
    goto LABEL_19;
  }
  v10 = operator new[]((unsigned int)Size);
  v25 = v10;
  memset_0(v10, 0, (unsigned int)Size);
  Caps = RIMGetDevicePreparsedData(*((_QWORD *)this + 10), v8, v10, &Size);
  if ( Caps < 0 )
  {
    v22 = 280;
LABEL_28:
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v22,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\hiddevicecollection.cpp",
            (const char *)(unsigned int)Caps,
            Size);
LABEL_30:
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v25);
    goto LABEL_19;
  }
  memset_0(&Capabilities, 0, sizeof(Capabilities));
  Caps = HidP_GetCaps((PHIDP_PREPARSED_DATA)v10, &Capabilities);
  if ( Caps < 0 )
  {
    v22 = 286;
    goto LABEL_28;
  }
  v13 = HIDDeviceCollection::ConvertHIDTLCIdToInputType(
          v12,
          Capabilities.Usage,
          Capabilities.UsagePage,
          (enum InputType *)&v27);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\hiddevicecollection.cpp",
      (const char *)(unsigned int)v13,
      Size);
    goto LABEL_30;
  }
  v15 = Size;
  *(_QWORD *)(v7 + 48) = v10;
  *(_DWORD *)(v7 + 56) = v15;
  v25 = 0;
  *(_DWORD *)v5 = v26;
  *(_DWORD *)(v5 + 4) = v27;
  if ( (int)RIMGetDeviceProperties(*((_QWORD *)this + 10), v8, v28) >= 0 )
  {
    v16 = WORD4(v28[0]);
    *(_WORD *)(v5 + 32) = WORD4(v28[0]);
    v17 = WORD5(v28[0]);
    *(_WORD *)(v5 + 34) = WORD5(v28[0]);
    v18 = WORD6(v28[0]);
    *(_WORD *)(v5 + 36) = WORD6(v28[0]);
    RawInputProvidersTelemetry::LogRawInputDeviceAttached(*(_DWORD *)(v5 + 4), v16, v17, v18);
  }
  *a3 = (struct DeviceInfo *)v5;
  v24 = 0;
  VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v25);
  std::unique_ptr<LegacyDeviceInfo>::~unique_ptr<LegacyDeviceInfo>(&v24);
  return 0;
}

```

## disassembly

```asm
0x18004ea70  mov     [rsp-8+arg_8], rbx
0x18004ea75  push    rbp
0x18004ea76  push    rsi
0x18004ea77  push    rdi
0x18004ea78  push    r12
0x18004ea7a  push    r13
0x18004ea7c  push    r14
0x18004ea7e  push    r15
0x18004ea80  lea     rbp, [rsp-27h]
0x18004ea85  sub     rsp, 0C0h
0x18004ea8c  mov     rax, cs:__security_cookie
0x18004ea93  xor     rax, rsp
0x18004ea96  mov     [rbp+57h+var_40], rax
0x18004ea9a  mov     r15, r8
0x18004ea9d  mov     [rbp+57h+var_B8], edx
0x18004eaa0  mov     r14, rcx
0x18004eaa3  mov     [rbp+57h+var_B4], 0
0x18004eaaa  mov     dword ptr [rbp+57h+Size], 0
0x18004eab1  mov     [rbp+57h+var_C8], 0
0x18004eab9  xorps   xmm0, xmm0
0x18004eabc  xor     eax, eax
0x18004eabe  movups  [rbp+57h+var_B0], xmm0
0x18004eac2  movups  [rbp+57h+var_A0], xmm0
0x18004eac6  mov     [rbp+57h+var_90], rax
0x18004eaca  test    r8, r8
0x18004eacd  jz      loc_18004EC94
0x18004ead3  mov     rdi, [r8]
0x18004ead6  test    rdi, rdi
0x18004ead9  jz      loc_18004ECB0
0x18004eadf  xor     ecx, ecx
0x18004eae1  cmp     ecx, 100h
0x18004eae7  jnb     loc_18004EC44
0x18004eaed  mov     rsi, [r14+rcx*8+270h]
0x18004eaf5  test    rsi, rsi
0x18004eaf8  jz      loc_18004EC3D
0x18004eafe  cmp     qword ptr [rsi+10h], 0
0x18004eb03  jnz     loc_18004EC34
0x18004eb09  mov     rax, [r14]
0x18004eb0c  mov     rdx, rsi
0x18004eb0f  mov     rcx, r14
0x18004eb12  mov     rax, [rax+68h]
0x18004eb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb1b  test    al, al
0x18004eb1d  jz      loc_18004ECFF
0x18004eb23  mov     r13, [rsi+10h]
0x18004eb27  lea     r9, [rbp+57h+Size]
0x18004eb2b  xor     r8d, r8d
0x18004eb2e  mov     rdx, r13
0x18004eb31  mov     rcx, [r14+50h]
0x18004eb35  call    cs:__imp_RIMGetDevicePreparsedData
0x18004eb3b  test    eax, eax
0x18004eb3d  js      loc_18004ED0E
0x18004eb43  mov     ecx, dword ptr [rbp+57h+Size]; unsigned __int64
0x18004eb46  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004eb4b  mov     r12, rax
0x18004eb4e  mov     [rbp+57h+var_C0], rax
0x18004eb52  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18004eb56  xor     edx, edx; Val
0x18004eb58  mov     rcx, rax; void *
0x18004eb5b  call    memset_0
0x18004eb60  lea     r9, [rbp+57h+Size]
0x18004eb64  mov     r8, r12
0x18004eb67  mov     rdx, r13
0x18004eb6a  mov     rcx, [r14+50h]
0x18004eb6e  call    cs:__imp_RIMGetDevicePreparsedData
0x18004eb74  test    eax, eax
0x18004eb76  js      loc_18004ED2D
0x18004eb7c  xor     edx, edx; Val
0x18004eb7e  lea     r8d, [rdx+40h]; Size
0x18004eb82  lea     rcx, [rbp+57h+Capabilities]; void *
0x18004eb86  call    memset_0
0x18004eb8b  lea     rdx, [rbp+57h+Capabilities]; Capabilities
0x18004eb8f  mov     rcx, r12; PreparsedData
0x18004eb92  call    cs:__imp_HidP_GetCaps
0x18004eb98  test    eax, eax
0x18004eb9a  js      loc_18004ED34
0x18004eba0  lea     r9, [rbp+57h+var_B4]; enum InputType *
0x18004eba4  movzx   r8d, [rbp+57h+Capabilities.UsagePage]; unsigned __int16
0x18004eba9  movzx   edx, [rbp+57h+Capabilities.Usage]; unsigned __int16
0x18004ebad  call    ?ConvertHIDTLCIdToInputType@HIDDeviceCollection@@AEAAJGGPEAW4InputType@@@Z; HIDDeviceCollection::ConvertHIDTLCIdToInputType(ushort,ushort,InputType *)
0x18004ebb2  mov     ebx, eax
0x18004ebb4  test    eax, eax
0x18004ebb6  js      loc_18004ED50
0x18004ebbc  mov     eax, dword ptr [rbp+57h+Size]
0x18004ebbf  mov     [rsi+30h], r12
0x18004ebc3  mov     [rsi+38h], eax
0x18004ebc6  mov     [rbp+57h+var_C0], 0
0x18004ebce  mov     eax, [rbp+57h+var_B8]
0x18004ebd1  mov     [rdi], eax
0x18004ebd3  mov     eax, [rbp+57h+var_B4]
0x18004ebd6  mov     [rdi+4], eax
0x18004ebd9  lea     r8, [rbp+57h+var_B0]
0x18004ebdd  mov     rdx, r13
0x18004ebe0  mov     rcx, [r14+50h]
0x18004ebe4  call    cs:__imp_RIMGetDeviceProperties
0x18004ebea  test    eax, eax
0x18004ebec  js      short loc_18004EC12
0x18004ebee  movzx   edx, word ptr [rbp+57h+var_B0+8]; unsigned __int16
0x18004ebf2  mov     [rdi+20h], dx
0x18004ebf6  movzx   r8d, word ptr [rbp+57h+var_B0+0Ah]; unsigned __int16
0x18004ebfb  mov     [rdi+22h], r8w
0x18004ec00  movzx   r9d, word ptr [rbp+57h+var_B0+0Ch]; unsigned __int16
0x18004ec05  mov     [rdi+24h], r9w
0x18004ec0a  mov     ecx, [rdi+4]; unsigned int
0x18004ec0d  call    ?LogRawInputDeviceAttached@RawInputProvidersTelemetry@@SAXIGGG@Z; RawInputProvidersTelemetry::LogRawInputDeviceAttached(uint,ushort,ushort,ushort)
0x18004ec12  mov     [r15], rdi
0x18004ec15  mov     [rbp+57h+var_C8], 0
0x18004ec1d  lea     rcx, [rbp+57h+var_C0]
0x18004ec21  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x18004ec26  nop
0x18004ec27  lea     rcx, [rbp+57h+var_C8]
0x18004ec2b  call    ??1?$unique_ptr@ULegacyDeviceInfo@@U?$default_delete@ULegacyDeviceInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<LegacyDeviceInfo>::~unique_ptr<LegacyDeviceInfo>(void)
0x18004ec30  xor     eax, eax
0x18004ec32  jmp     short loc_18004EC6D
0x18004ec34  cmp     [rsi+28h], edx
0x18004ec37  jz      loc_18004EB09
0x18004ec3d  inc     ecx
0x18004ec3f  jmp     loc_18004EAE1
0x18004ec44  mov     ebx, 80070490h
0x18004ec49  mov     edx, 0F8h; void *
0x18004ec4e  mov     r9d, ebx; char *
0x18004ec51  lea     r8, aOnecoreuapWind_224; "onecoreuap\\windows\\moderncore\\inputv"...
0x18004ec58  mov     rcx, [rbp+5Fh]; this
0x18004ec5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec61  nop
0x18004ec62  lea     rcx, [rbp+57h+var_C8]
0x18004ec66  call    ??1?$unique_ptr@ULegacyDeviceInfo@@U?$default_delete@ULegacyDeviceInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<LegacyDeviceInfo>::~unique_ptr<LegacyDeviceInfo>(void)
0x18004ec6b  mov     eax, ebx
0x18004ec6d  mov     rcx, [rbp+57h+var_40]
0x18004ec71  xor     rcx, rsp; StackCookie
0x18004ec74  call    __security_check_cookie
0x18004ec79  mov     rbx, [rsp+0F0h+arg_8]
0x18004ec81  add     rsp, 0C0h
0x18004ec88  pop     r15
0x18004ec8a  pop     r14
0x18004ec8c  pop     r13
0x18004ec8e  pop     r12
0x18004ec90  pop     rdi
0x18004ec91  pop     rsi
0x18004ec92  pop     rbp
0x18004ec93  retn
0x18004ec94  mov     rcx, [rbp+5Fh]; this
0x18004ec98  mov     r9d, 8000FFFFh; char *
0x18004ec9e  lea     r8, aOnecoreuapWind_224; "onecoreuap\\windows\\moderncore\\inputv"...
0x18004eca5  mov     edx, 0D9h; void *
0x18004ecaa  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18004ecb0  mov     edi, 60Ch
0x18004ecb5  mov     ecx, edi; Size
0x18004ecb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ecbc  mov     rbx, rax
0x18004ecbf  mov     [rbp+57h+var_C0], rax
0x18004ecc3  mov     r8d, edi; Size
0x18004ecc6  xor     edx, edx; Val
0x18004ecc8  mov     rcx, rax; void *
0x18004eccb  call    memset_0
0x18004ecd0  mov     [rbx+8], edi
0x18004ecd3  mov     rdx, rbx
0x18004ecd6  lea     rcx, [rbp+57h+var_C8]
0x18004ecda  call    ?reset@?$unique_ptr@ULegacyDeviceInfo@@U?$default_delete@ULegacyDeviceInfo@@@std@@@std@@QEAAXPEAULegacyDeviceInfo@@@Z; std::unique_ptr<LegacyDeviceInfo>::reset(LegacyDeviceInfo *)
0x18004ecdf  mov     rdi, [rbp+57h+var_C8]
0x18004ece3  test    rdi, rdi
0x18004ece6  jnz     short loc_18004ECF7
0x18004ece8  mov     ebx, 8007000Eh
0x18004eced  mov     edx, 0F3h
0x18004ecf2  jmp     loc_18004EC4E
0x18004ecf7  mov     edx, [rbp+57h+var_B8]
0x18004ecfa  jmp     loc_18004EADF
0x18004ecff  mov     ebx, 8000FFFFh
0x18004ed04  mov     edx, 0FCh
0x18004ed09  jmp     loc_18004EC4E
0x18004ed0e  mov     rcx, [rbp+5Fh]; this
0x18004ed12  mov     r9d, eax; char *
0x18004ed15  lea     r8, aOnecoreuapWind_224; "onecoreuap\\windows\\moderncore\\inputv"...
0x18004ed1c  mov     edx, 10Bh; void *
0x18004ed21  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004ed26  mov     ebx, eax
0x18004ed28  jmp     loc_18004EC62
0x18004ed2d  mov     edx, 118h
0x18004ed32  jmp     short loc_18004ED39
0x18004ed34  mov     edx, 11Eh; void *
0x18004ed39  lea     r8, aOnecoreuapWind_224; "onecoreuap\\windows\\moderncore\\inputv"...
0x18004ed40  mov     r9d, eax; char *
0x18004ed43  mov     rcx, [rbp+5Fh]; this
0x18004ed47  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004ed4c  mov     ebx, eax
0x18004ed4e  jmp     short loc_18004ED68
0x18004ed50  mov     rcx, [rbp+5Fh]; this
0x18004ed54  mov     r9d, eax; char *
0x18004ed57  lea     r8, aOnecoreuapWind_224; "onecoreuap\\windows\\moderncore\\inputv"...
0x18004ed5e  mov     edx, 123h; void *
0x18004ed63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ed68  lea     rcx, [rbp+57h+var_C0]
0x18004ed6c  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x18004ed71  jmp     loc_18004EC62
```
