# ConsumerControlNexusDevice::Initialize(PnpDevice *)

- ea: `0x18012628c`
- end: `0x1801265b6`
- name: `?Initialize@ConsumerControlNexusDevice@@AEAAJPEAVPnpDevice@@@Z`
- size: `810`
- prototype: `__int64 __fastcall(ConsumerControlNexusDevice *__hidden this, struct PnpDevice *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180126dac`

## callees

- `0x18002f9b4`
- `0x18002f9d0`
- `0x18008daac`
- `0x18008e2b4`
- `0x18008ead4`
- `0x1800af9b8`
- `0x1800f2448`
- `0x1800f2478`
- `0x1801251e0`
- `0x1801252cc`
- `0x180126094`
- `0x18012628c`
- `0x180126c94`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801262b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801262b7`
- `HID!HidD_GetPreparsedData` at `0x18012631b`
- `HID!HidD_GetPreparsedData` at `0x18012631b`
- `HID!HidP_GetCaps` at `0x1801263c0`
- `HID!HidP_GetCaps` at `0x1801263c0`
- `HID!HidP_GetSpecificButtonCaps` at `0x18012646c`
- `HID!HidP_GetSpecificButtonCaps` at `0x18012646c`

## pseudocode

```c
__int64 __fastcall ConsumerControlNexusDevice::Initialize(ConsumerControlNexusDevice *this, struct PnpDevice *a2)
{
  PnpDevice **v2; // r14
  PnpDevice *v4; // rdi
  int InterfacePath; // ebx
  unsigned int v6; // r8d
  __int64 v7; // rdx
  __int64 result; // rax
  PHIDP_PREPARSED_DATA *v9; // rdi
  const char *v10; // r9
  PHIDP_PREPARSED_DATA v11; // rax
  struct _HIDP_CAPS *v12; // rax
  struct _HIDP_CAPS *v13; // rbx
  NTSTATUS Caps; // eax
  unsigned __int64 NumberInputButtonCaps; // rcx
  unsigned __int64 v16; // rax
  struct _HIDP_BUTTON_CAPS *v17; // rax
  NTSTATUS SpecificButtonCaps; // eax
  PnpDevice *v19; // rcx
  unsigned int v20; // edx
  unsigned __int64 v21; // r8
  unsigned int v22; // eax
  __int64 v23; // rbx
  char *v24; // rax
  ConsumerControlNexusDevice **v25; // rdx
  int v26; // eax
  unsigned int v27; // ecx
  int ButtonCaps; // [rsp+20h] [rbp-30h]
  int ButtonCapsa; // [rsp+20h] [rbp-30h]
  _QWORD v30[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned __int64 ButtonCapsLength; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v33; // [rsp+A0h] [rbp+50h] BYREF
  struct _HIDP_BUTTON_CAPS *v34; // [rsp+A8h] [rbp+58h] BYREF

  v2 = (PnpDevice **)((char *)this + 16);
  Microsoft::WRL::ComPtr<HidLampArrayDevice>::operator=((char *)this + 16);
  v4 = *v2;
  WindowsDeleteString(*((HSTRING *)this + 3));
  *((_QWORD *)this + 3) = 0;
  InterfacePath = PnpDevice::GetInterfacePath(v4, (HSTRING *)this + 3);
  if ( InterfacePath < 0 )
  {
    v7 = 72;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\consumercontrolnexusdevice.cpp",
      (const char *)(unsigned int)InterfacePath,
      ButtonCaps);
    return (unsigned int)InterfacePath;
  }
  InterfacePath = PnpDevice::OpenInterface(*v2, 0x80000000, v6);
  if ( InterfacePath < 0 )
  {
    v7 = 74;
    goto LABEL_3;
  }
  v9 = (PHIDP_PREPARSED_DATA *)((char *)this + 32);
  if ( !HidD_GetPreparsedData(*((HANDLE *)*v2 + 5), (PHIDP_PREPARSED_DATA *)this + 4) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4E,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\consumercontrolnexusdevice.cpp",
             v10);
  v11 = *v9;
  if ( *((_WORD *)*v9 + 5) != 12 )
  {
    InterfacePath = -2147418113;
    v7 = 81;
    goto LABEL_3;
  }
  if ( *((_WORD *)v11 + 4) != 1 )
  {
    InterfacePath = -2147418113;
    v7 = 82;
    goto LABEL_3;
  }
  *((_QWORD *)this + 12) = *((unsigned __int16 *)v11 + 11);
  v12 = (struct _HIDP_CAPS *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v30[0] = v12;
  v13 = v12;
  if ( !v12 )
  {
    InterfacePath = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\consumercontrolnexusdevice.cpp",
      (const char *)0x8007000ELL,
      ButtonCaps);
LABEL_26:
    std::unique_ptr<InputObservation::APP_MOUSE_INPUT_OBSERVER_PACKET>::~unique_ptr<InputObservation::APP_MOUSE_INPUT_OBSERVER_PACKET>(v30);
    return (unsigned int)InterfacePath;
  }
  Caps = HidP_GetCaps(*v9, v12);
  if ( Caps < 0 )
  {
    InterfacePath = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x58,
                      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\consume"
                                    "rcontrolnexusdevice.cpp",
                      (const char *)(unsigned int)Caps,
                      ButtonCaps);
    goto LABEL_26;
  }
  NumberInputButtonCaps = v13->NumberInputButtonCaps;
  *((_WORD *)this + 20) = NumberInputButtonCaps;
  LOWORD(ButtonCapsLength) = NumberInputButtonCaps;
  v16 = 72 * NumberInputButtonCaps;
  if ( !is_mul_ok(NumberInputButtonCaps, 0x48u) )
    v16 = -1;
  v17 = (struct _HIDP_BUTTON_CAPS *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
  v34 = v17;
  if ( !v17 )
  {
    InterfacePath = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\consumercontrolnexusdevice.cpp",
      (const char *)0x8007000ELL,
      ButtonCaps);
LABEL_21:
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v34);
    goto LABEL_26;
  }
  SpecificButtonCaps = HidP_GetSpecificButtonCaps(HidP_Input, 0xCu, 0, 0xD0u, v17, (PUSHORT)&ButtonCapsLength, *v9);
  if ( SpecificButtonCaps < 0 )
  {
    InterfacePath = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x69,
                      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\consume"
                                    "rcontrolnexusdevice.cpp",
                      (const char *)(unsigned int)SpecificButtonCaps,
                      ButtonCapsa);
    goto LABEL_21;
  }
  if ( !(_WORD)ButtonCapsLength )
  {
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v34);
    InterfacePath = -2147418113;
    goto LABEL_26;
  }
  VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v34);
  std::unique_ptr<InputObservation::APP_MOUSE_INPUT_OBSERVER_PACKET>::~unique_ptr<InputObservation::APP_MOUSE_INPUT_OBSERVER_PACKET>(v30);
  v19 = *v2;
  ButtonCapsLength = 0;
  v33 = 0;
  result = PnpDevice::OutputIoctl(v19, v20, v21, &v33, &ButtonCapsLength);
  if ( (int)result >= 0 )
  {
    if ( ButtonCapsLength != 4 )
    {
      InterfacePath = -2147418113;
      v7 = 123;
      goto LABEL_3;
    }
    v22 = v33;
    if ( !v33 )
    {
      InterfacePath = -2147418113;
      v7 = 124;
      goto LABEL_3;
    }
    if ( v33 > 0x40 )
    {
      v22 = 64;
      v33 = 64;
    }
    v23 = *((_QWORD *)this + 12);
    while ( *((_DWORD *)this + 16) < v22 )
    {
      v24 = (char *)operator new[](v23 + 87, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v24 )
      {
        InterfacePath = -2147024882;
        v7 = 141;
        goto LABEL_3;
      }
      *((_QWORD *)v24 + 2) = this;
      *(_OWORD *)(v24 + 24) = 0;
      *(_OWORD *)(v24 + 40) = 0;
      *((_DWORD *)v24 + 14) = 0;
      *((_QWORD *)v24 + 8) = 0;
      *((_QWORD *)v24 + 9) = *((_QWORD *)this + 12);
      v25 = (ConsumerControlNexusDevice **)*((_QWORD *)this + 7);
      if ( *v25 != (ConsumerControlNexusDevice *)((char *)this + 48) )
        __fastfail(3u);
      *(_QWORD *)v24 = (char *)this + 48;
      *((_QWORD *)v24 + 1) = v25;
      *v25 = (ConsumerControlNexusDevice *)v24;
      ++*((_DWORD *)this + 16);
      *((_QWORD *)this + 7) = v24;
      v22 = v33;
    }
    v26 = ConsumerControlNexusDevice::QueueInputBuffers(this);
    v27 = 0;
    if ( v26 < 0 )
      return (unsigned int)v26;
    return v27;
  }
  return result;
}

```

## disassembly

```asm
0x18012628c  push    rbp
0x18012628e  push    rbx
0x18012628f  push    rsi
0x180126290  push    rdi
0x180126291  push    r13
0x180126293  push    r14
0x180126295  push    r15
0x180126297  mov     rbp, rsp
0x18012629a  sub     rsp, 50h
0x18012629e  lea     r14, [rcx+10h]
0x1801262a2  mov     rsi, rcx
0x1801262a5  mov     rcx, r14
0x1801262a8  call    ??4?$ComPtr@VHidLampArrayDevice@@@WRL@Microsoft@@QEAAAEAV012@PEAVHidLampArrayDevice@@@Z; Microsoft::WRL::ComPtr<HidLampArrayDevice>::operator=(HidLampArrayDevice *)
0x1801262ad  mov     rdi, [r14]
0x1801262b0  lea     rbx, [rsi+18h]
0x1801262b4  mov     rcx, [rbx]; string
0x1801262b7  call    cs:__imp_WindowsDeleteString
0x1801262bd  xor     r15d, r15d
0x1801262c0  mov     rdx, rbx; HSTRING *
0x1801262c3  mov     rcx, rdi; this
0x1801262c6  mov     [rbx], r15
0x1801262c9  call    ?GetInterfacePath@PnpDevice@@QEAAJPEAPEAUHSTRING__@@@Z; PnpDevice::GetInterfacePath(HSTRING__ * *)
0x1801262ce  mov     ebx, eax
0x1801262d0  test    eax, eax
0x1801262d2  jns     short loc_1801262F2
0x1801262d4  lea     edx, [r15+48h]; void *
0x1801262d8  mov     rcx, [rbp+38h]; this
0x1801262dc  lea     r8, aOnecoreuapWind_193; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801262e3  mov     r9d, ebx; char *
0x1801262e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801262eb  mov     eax, ebx
0x1801262ed  jmp     loc_1801265A7
0x1801262f2  mov     rcx, [r14]; this
0x1801262f5  mov     edx, 80000000h; unsigned int
0x1801262fa  call    ?OpenInterface@PnpDevice@@QEAAJKK@Z; PnpDevice::OpenInterface(ulong,ulong)
0x1801262ff  mov     ebx, eax
0x180126301  test    eax, eax
0x180126303  jns     short loc_18012630C
0x180126305  mov     edx, 4Ah ; 'J'
0x18012630a  jmp     short loc_1801262D8
0x18012630c  mov     rax, [r14]
0x18012630f  lea     rdi, [rsi+20h]
0x180126313  mov     rdx, rdi; PreparsedData
0x180126316  mov     rcx, [rax+28h]; HidDeviceObject
0x18012631a  nop
0x18012631b  call    cs:__imp_HidD_GetPreparsedData
0x180126321  test    al, al
0x180126323  jnz     short loc_18012633F
0x180126325  mov     rcx, [rbp+38h]; this
0x180126329  lea     r8, aOnecoreuapWind_193; "onecoreuap\\windows\\moderncore\\inputv"...
0x180126330  mov     edx, 4Eh ; 'N'; void *
0x180126335  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012633a  jmp     loc_1801265A7
0x18012633f  mov     rax, [rdi]
0x180126342  mov     r13d, 0Ch
0x180126348  cmp     [rax+0Ah], r13w
0x18012634d  jz      short loc_18012635D
0x18012634f  mov     ebx, 8000FFFFh
0x180126354  lea     edx, [r13+45h]
0x180126358  jmp     loc_1801262D8
0x18012635d  mov     ecx, 1
0x180126362  cmp     [rax+8], cx
0x180126366  jz      short loc_180126375
0x180126368  mov     ebx, 8000FFFFh
0x18012636d  lea     edx, [rcx+51h]
0x180126370  jmp     loc_1801262D8
0x180126375  movzx   eax, word ptr [rax+16h]
0x180126379  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180126380  mov     ecx, 40h ; '@'; unsigned __int64
0x180126385  mov     [rsi+60h], rax
0x180126389  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18012638e  mov     [rbp+var_10], rax
0x180126392  mov     rbx, rax
0x180126395  test    rax, rax
0x180126398  jnz     short loc_1801263BA
0x18012639a  mov     rcx, [rbp+38h]; this
0x18012639e  lea     r8, aOnecoreuapWind_193; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801263a5  mov     ebx, 8007000Eh
0x1801263aa  lea     edx, [rax+57h]; void *
0x1801263ad  mov     r9d, ebx; char *
0x1801263b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801263b5  jmp     loc_1801264A7
0x1801263ba  mov     rcx, [rdi]; PreparsedData
0x1801263bd  mov     rdx, rbx; Capabilities
0x1801263c0  call    cs:__imp_HidP_GetCaps
0x1801263c6  test    eax, eax
0x1801263c8  jns     short loc_1801263E9
0x1801263ca  mov     rcx, [rbp+38h]; this
0x1801263ce  lea     r8, aOnecoreuapWind_193; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801263d5  mov     r9d, eax; char *
0x1801263d8  mov     edx, 58h ; 'X'; void *
0x1801263dd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801263e2  mov     ebx, eax
0x1801263e4  jmp     loc_1801264A7
0x1801263e9  movzx   eax, word ptr [rbx+2Eh]
0x1801263ed  mov     ecx, eax
0x1801263ef  mov     [rsi+28h], ax
0x1801263f3  mov     word ptr [rbp+arg_0], ax
0x1801263f7  mov     eax, 48h ; 'H'
0x1801263fc  mul     rcx
0x1801263ff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180126406  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18012640d  cmovb   rax, rcx
0x180126411  mov     rcx, rax; unsigned __int64
0x180126414  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180126419  mov     [rbp+arg_18], rax
0x18012641d  test    rax, rax
0x180126420  jnz     short loc_180126448
0x180126422  mov     rcx, [rbp+38h]; this
0x180126426  lea     r8, aOnecoreuapWind_193; "onecoreuap\\windows\\moderncore\\inputv"...
0x18012642d  mov     ebx, 8007000Eh
0x180126432  lea     edx, [rax+61h]; void *
0x180126435  mov     r9d, ebx; char *
0x180126438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012643d  lea     rcx, [rbp+arg_18]
0x180126441  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x180126446  jmp     short loc_1801264A7
0x180126448  mov     rcx, [rdi]
0x18012644b  mov     r9d, 0D0h; Usage
0x180126451  mov     [rsp+50h+PreparsedData], rcx; PreparsedData
0x180126456  xor     r8d, r8d; LinkCollection
0x180126459  lea     rcx, [rbp+arg_0]
0x18012645d  mov     edx, r13d; UsagePage
0x180126460  mov     [rsp+50h+ButtonCapsLength], rcx; ButtonCapsLength
0x180126465  xor     ecx, ecx; ReportType
0x180126467  mov     [rsp+50h+ButtonCaps], rax; int
0x18012646c  call    cs:__imp_HidP_GetSpecificButtonCaps
0x180126472  test    eax, eax
0x180126474  jns     short loc_180126492
0x180126476  mov     rcx, [rbp+38h]; this
0x18012647a  lea     r8, aOnecoreuapWind_193; "onecoreuap\\windows\\moderncore\\inputv"...
0x180126481  mov     r9d, eax; char *
0x180126484  mov     edx, 69h ; 'i'; void *
0x180126489  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18012648e  mov     ebx, eax
0x180126490  jmp     short loc_18012643D
0x180126492  lea     rcx, [rbp+arg_18]
0x180126496  cmp     word ptr [rbp+arg_0], r15w
0x18012649b  jnz     short loc_1801264B5
0x18012649d  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x1801264a2  mov     ebx, 8000FFFFh
0x1801264a7  lea     rcx, [rbp+var_10]
0x1801264ab  call    ??1?$unique_ptr@UAPP_MOUSE_INPUT_OBSERVER_PACKET@InputObservation@@U?$default_delete@UAPP_MOUSE_INPUT_OBSERVER_PACKET@InputObservation@@@std@@@std@@QEAA@XZ; std::unique_ptr<InputObservation::APP_MOUSE_INPUT_OBSERVER_PACKET>::~unique_ptr<InputObservation::APP_MOUSE_INPUT_OBSERVER_PACKET>(void)
0x1801264b0  jmp     loc_1801262EB
0x1801264b5  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x1801264ba  lea     rcx, [rbp+var_10]
0x1801264be  call    ??1?$unique_ptr@UAPP_MOUSE_INPUT_OBSERVER_PACKET@InputObservation@@U?$default_delete@UAPP_MOUSE_INPUT_OBSERVER_PACKET@InputObservation@@@std@@@std@@QEAA@XZ; std::unique_ptr<InputObservation::APP_MOUSE_INPUT_OBSERVER_PACKET>::~unique_ptr<InputObservation::APP_MOUSE_INPUT_OBSERVER_PACKET>(void)
0x1801264c3  mov     rcx, [r14]; this
0x1801264c6  lea     rax, [rbp+arg_0]
0x1801264ca  lea     r9, [rbp+arg_10]; void *
0x1801264ce  mov     [rsp+50h+ButtonCaps], rax; unsigned __int64 *
0x1801264d3  mov     [rbp+arg_0], r15
0x1801264d7  mov     [rbp+arg_10], r15d
0x1801264db  call    ?OutputIoctl@PnpDevice@@QEAAJK_KPEAXPEA_K@Z; PnpDevice::OutputIoctl(ulong,unsigned __int64,void *,unsigned __int64 *)
0x1801264e0  test    eax, eax
0x1801264e2  js      loc_1801265A7
0x1801264e8  cmp     [rbp+arg_0], 4
0x1801264ed  jz      short loc_1801264FE
0x1801264ef  mov     ebx, 8000FFFFh
0x1801264f4  mov     edx, 7Bh ; '{'
0x1801264f9  jmp     loc_1801262D8
0x1801264fe  mov     eax, [rbp+arg_10]
0x180126501  test    eax, eax
0x180126503  jnz     short loc_180126512
0x180126505  mov     ebx, 8000FFFFh
0x18012650a  lea     edx, [rax+7Ch]
0x18012650d  jmp     loc_1801262D8
0x180126512  cmp     eax, 40h ; '@'
0x180126515  jbe     short loc_18012651F
0x180126517  mov     eax, 40h ; '@'
0x18012651c  mov     [rbp+arg_10], eax
0x18012651f  mov     rbx, [rsi+60h]
0x180126523  cmp     [rsi+40h], eax
0x180126526  jnb     short loc_180126595
0x180126528  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18012652f  lea     rcx, [rbx+57h]; unsigned __int64
0x180126533  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180126538  test    rax, rax
0x18012653b  jz      short loc_180126586
0x18012653d  mov     [rax+10h], rsi
0x180126541  xorps   xmm0, xmm0
0x180126544  movups  xmmword ptr [rax+18h], xmm0
0x180126548  movups  xmmword ptr [rax+28h], xmm0
0x18012654c  mov     [rax+38h], r15d
0x180126550  mov     [rax+40h], r15
0x180126554  mov     rcx, [rsi+60h]
0x180126558  mov     [rax+48h], rcx
0x18012655c  lea     rcx, [rsi+30h]
0x180126560  mov     rdx, [rcx+8]
0x180126564  cmp     [rdx], rcx
0x180126567  jnz     short loc_18012657F
0x180126569  mov     [rax], rcx
0x18012656c  mov     [rax+8], rdx
0x180126570  mov     [rdx], rax
0x180126573  inc     dword ptr [rcx+10h]
0x180126576  mov     [rcx+8], rax
0x18012657a  mov     eax, [rbp+arg_10]
0x18012657d  jmp     short loc_180126523
0x18012657f  mov     ecx, 3
0x180126584  int     29h; Win8: RtlFailFast(ecx)
0x180126586  mov     ebx, 8007000Eh
0x18012658b  mov     edx, 8Dh
0x180126590  jmp     loc_1801262D8
0x180126595  mov     rcx, rsi; this
0x180126598  call    ?QueueInputBuffers@ConsumerControlNexusDevice@@AEAAJXZ; ConsumerControlNexusDevice::QueueInputBuffers(void)
0x18012659d  test    eax, eax
0x18012659f  mov     ecx, r15d
0x1801265a2  cmovs   ecx, eax
0x1801265a5  mov     eax, ecx
0x1801265a7  add     rsp, 50h
0x1801265ab  pop     r15
0x1801265ad  pop     r14
0x1801265af  pop     r13
0x1801265b1  pop     rdi
0x1801265b2  pop     rsi
0x1801265b3  pop     rbx
0x1801265b4  pop     rbp
0x1801265b5  retn
```
