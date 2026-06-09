# PnpDevice::MakeAndInitialize(HSTRING__ *,PnpDeviceWatcher *,PnpDevice * *)

- ea: `0x180124ddc`
- end: `0x18012517f`
- name: `?MakeAndInitialize@PnpDevice@@CAJPEAUHSTRING__@@PEAVPnpDeviceWatcher@@PEAPEAV1@@Z`
- size: `931`
- prototype: `__int64 __fastcall(HSTRING string, struct PnpDeviceWatcher *, struct PnpDevice **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fbec`

## callees

- `0x180014450`
- `0x18002e38c`
- `0x18002e4cc`
- `0x18002e7b8`
- `0x18002fea0`
- `0x180064668`
- `0x180069c60`
- `0x18008ead4`
- `0x1800f0990`
- `0x1800f2731`
- `0x180124ddc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801250c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801250f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180125121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180125145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801250c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801250f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180125121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180125145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180124f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180124f13`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x180124fd3`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x180124fd3`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180124f22`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180124f22`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PnpDevice::MakeAndInitialize(HSTRING string, struct PnpDeviceWatcher *a2, struct PnpDevice **a3)
{
  char *v5; // rax
  char *v6; // rbx
  int v8; // eax
  int DeviceGuidProperty; // edi
  DEVINST *v10; // r15
  WCHAR *StringRawBuffer; // rax
  CONFIGRET DevNodeW; // eax
  unsigned int v13; // edx
  unsigned int v14; // esi
  int v15; // eax
  unsigned int v16; // edi
  DEVINST v17; // edi
  int i; // r12d
  CONFIGRET Parent; // eax
  unsigned int v20; // edx
  int v21; // eax
  int v22; // r8d
  int v23; // eax
  struct _GUID *pdnDevInst; // [rsp+20h] [rbp-40h] BYREF
  HSTRING stringa; // [rsp+28h] [rbp-38h] BYREF
  HSTRING v26; // [rsp+30h] [rbp-30h] BYREF
  struct PnpDevice **v27; // [rsp+38h] [rbp-28h]
  struct _DEVPROPKEY Buf1; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v27 = a3;
  v26 = string;
  *a3 = 0;
  v5 = (char *)RefCountedObject::operator new(0x98u);
  v6 = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = &RefCountedObject::`vftable';
    *((_DWORD *)v5 + 2) = 1;
    *(_QWORD *)v5 = &PnpDevice::`vftable';
    *((_QWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 3) = 0;
    *((_QWORD *)v5 + 4) = 0;
    *((_QWORD *)v5 + 5) = -1;
    *((_QWORD *)v5 + 6) = 0;
    *(GUID *)(v5 + 56) = GUID_NULL;
    *(GUID *)(v5 + 72) = GUID_NULL;
    *(GUID *)(v5 + 88) = GUID_NULL;
    *((_QWORD *)v5 + 13) = 0;
    *((_QWORD *)v5 + 14) = 0;
    *((_QWORD *)v5 + 15) = 0;
    v5[128] = 0;
    *(_QWORD *)(v5 + 132) = 0;
    *((_QWORD *)v5 + 18) = 0;
  }
  else
  {
    v6 = 0;
  }
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x282,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpdevice.cpp",
      (const char *)0x8007000ELL,
      (int)pdnDevInst);
    return 2147942414LL;
  }
  v8 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v6 + 3, &v26);
  DeviceGuidProperty = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x285,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpdevice.cpp",
      (const char *)(unsigned int)v8,
      (int)pdnDevInst);
    InputContext::Release((InputContext *)v6);
    return (unsigned int)DeviceGuidProperty;
  }
  v10 = (DEVINST *)(v6 + 104);
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
  DevNodeW = CM_Locate_DevNodeW((PDEVINST)v6 + 26, StringRawBuffer, 0);
  v14 = -2147023728;
  if ( DevNodeW )
  {
    *v10 = 0;
    v15 = PnpApiWrapper::Details::ConfigretToHresult((PnpApiWrapper::Details *)DevNodeW, v13);
    v16 = v15;
    if ( v15 == -2147023728 )
    {
LABEL_12:
      InputContext::Release((InputContext *)v6);
      return v14;
    }
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x338,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpapiwrapper.cpp",
        (const char *)(unsigned int)v15,
        (int)pdnDevInst);
      v14 = v16;
      goto LABEL_12;
    }
  }
  LODWORD(pdnDevInst) = *v10;
  DeviceGuidProperty = PnpApiWrapper::Details::GetDeviceGuidProperty(
                         (PnpApiWrapper::Details *)Adapters::GetDeviceNodeProperty,
                         (unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *))&pdnDevInst,
                         (void *)&DEVPKEY_Device_ClassGuid,
                         (const struct _DEVPROPKEY *)(v6 + 56),
                         pdnDevInst);
  if ( DeviceGuidProperty < 0 )
  {
LABEL_31:
    InputContext::Release((InputContext *)v6);
  }
  else
  {
    *((_QWORD *)v6 + 18) = a2;
    v17 = *v10;
    *((_DWORD *)v6 + 28) = *v10;
    *(_OWORD *)(v6 + 88) = *(_OWORD *)(v6 + 56);
    LODWORD(pdnDevInst) = v17;
    for ( i = 1; ; ++i )
    {
      Buf1.fmtid = 0;
      Parent = CM_Get_Parent((PDEVINST)&pdnDevInst, v17, 0);
      if ( Parent )
      {
        LODWORD(pdnDevInst) = 0;
        v21 = PnpApiWrapper::Details::ConfigretToHresult((PnpApiWrapper::Details *)Parent, v20);
        DeviceGuidProperty = v21;
        if ( v21 == -2147023728 )
        {
          DeviceGuidProperty = -2147023728;
          goto LABEL_31;
        }
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37D,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpapiwrapper.cpp",
            (const char *)(unsigned int)v21,
            (int)pdnDevInst);
          goto LABEL_31;
        }
      }
      else
      {
        v22 = (int)pdnDevInst;
      }
      LODWORD(v26) = v22;
      DeviceGuidProperty = PnpApiWrapper::Details::GetDeviceGuidProperty(
                             (PnpApiWrapper::Details *)Adapters::GetDeviceNodeProperty,
                             (unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *))&v26,
                             (void *)&DEVPKEY_Device_ClassGuid,
                             &Buf1,
                             pdnDevInst);
      if ( DeviceGuidProperty < 0 )
        goto LABEL_31;
      if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
        break;
      v23 = memcmp_0(&Buf1, qword_1801F96E8, 0x10u);
      v17 = (unsigned int)pdnDevInst;
      if ( !v23 || !memcmp_0(&Buf1, qword_1801F96D8, 0x10u) )
      {
        *(DEVPROPGUID *)(v6 + 88) = Buf1.fmtid;
        *((_DWORD *)v6 + 28) = v17;
        *((_DWORD *)v6 + 27) = i;
      }
    }
    stringa = 0;
    WindowsDeleteString(0);
    stringa = 0;
    LODWORD(v26) = *v10;
    DeviceGuidProperty = PnpApiWrapper::Details::GetDeviceStringProperty(
                           (PnpApiWrapper::Details *)Adapters::GetDeviceNodeProperty,
                           (unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *))&v26,
                           (void *)&DEVPKEY_Device_HardwareIds,
                           (const struct _DEVPROPKEY *)&stringa,
                           (HSTRING *)pdnDevInst);
    if ( DeviceGuidProperty >= 0 )
    {
      DeviceGuidProperty = PnpDevice::ParseHardwareIdStrings((PnpDevice *)v6, stringa);
      if ( DeviceGuidProperty >= 0 )
      {
        _InterlockedExchange((volatile __int32 *)v6 + 31, 1);
        *v27 = (struct PnpDevice *)v6;
        WindowsDeleteString(stringa);
        return 0;
      }
    }
    WindowsDeleteString(stringa);
    stringa = 0;
    InputContext::Release((InputContext *)v6);
  }
  return (unsigned int)DeviceGuidProperty;
}

```

## disassembly

```asm
0x180124ddc  mov     [rsp-38h+arg_8], rbx
0x180124de1  push    rbp
0x180124de2  push    rsi
0x180124de3  push    rdi
0x180124de4  push    r12
0x180124de6  push    r13
0x180124de8  push    r14
0x180124dea  push    r15
0x180124dec  mov     rbp, rsp
0x180124def  sub     rsp, 60h
0x180124df3  mov     rax, cs:__security_cookie
0x180124dfa  xor     rax, rsp
0x180124dfd  mov     [rbp+var_10], rax
0x180124e01  mov     [rbp+var_28], r8
0x180124e05  mov     r13, rdx
0x180124e08  mov     rsi, rcx
0x180124e0b  mov     [rbp+var_30], rcx
0x180124e0f  xor     r12d, r12d
0x180124e12  mov     [r8], r12
0x180124e15  mov     ecx, 98h; Size
0x180124e1a  call    ??2RefCountedObject@@SAPEAX_K@Z; RefCountedObject::operator new(unsigned __int64)
0x180124e1f  mov     rbx, rax
0x180124e22  lea     r14d, [r12+1]
0x180124e27  test    rax, rax
0x180124e2a  jz      short loc_180124EA3
0x180124e2c  lea     rax, ??_7RefCountedObject@@6B@; const RefCountedObject::`vftable'
0x180124e33  mov     [rbx], rax
0x180124e36  mov     [rbx+8], r14d
0x180124e3a  lea     rax, ??_7PnpDevice@@6B@; const PnpDevice::`vftable'
0x180124e41  mov     [rbx], rax
0x180124e44  mov     [rbx+10h], r12
0x180124e48  mov     [rbx+18h], r12
0x180124e4c  mov     [rbx+20h], r12
0x180124e50  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180124e58  mov     [rbx+30h], r12
0x180124e5c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180124e63  movdqu  xmmword ptr [rbx+38h], xmm0
0x180124e68  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180124e6f  movdqu  xmmword ptr [rbx+48h], xmm1
0x180124e74  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180124e7b  movdqu  xmmword ptr [rbx+58h], xmm0
0x180124e80  mov     [rbx+68h], r12
0x180124e84  mov     [rbx+70h], r12
0x180124e88  mov     [rbx+78h], r12
0x180124e8c  mov     [rbx+80h], r12b
0x180124e93  mov     [rbx+84h], r12
0x180124e9a  mov     [rbx+90h], r12
0x180124ea1  jmp     short loc_180124EA6
0x180124ea3  mov     rbx, r12
0x180124ea6  test    rbx, rbx
0x180124ea9  jnz     short loc_180124ED0
0x180124eab  mov     rcx, [rbp+38h]; this
0x180124eaf  mov     ebx, 8007000Eh
0x180124eb4  mov     r9d, ebx; char *
0x180124eb7  lea     r8, aOnecoreuapWind_237; "onecoreuap\\windows\\moderncore\\inputv"...
0x180124ebe  mov     edx, 282h; void *
0x180124ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124ec8  nop
0x180124ec9  mov     eax, ebx
0x180124ecb  jmp     loc_18012515B
0x180124ed0  lea     rcx, [rbx+18h]; newString
0x180124ed4  lea     rdx, [rbp+var_30]; HSTRING *
0x180124ed8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180124edd  mov     edi, eax
0x180124edf  test    eax, eax
0x180124ee1  jns     short loc_180124F0A
0x180124ee3  mov     rcx, [rbp+38h]; this
0x180124ee7  mov     r9d, eax; char *
0x180124eea  lea     r8, aOnecoreuapWind_237; "onecoreuap\\windows\\moderncore\\inputv"...
0x180124ef1  mov     edx, 285h; void *
0x180124ef6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124efb  nop
0x180124efc  mov     rcx, rbx; this
0x180124eff  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x180124f04  nop
0x180124f05  jmp     loc_180125159
0x180124f0a  lea     r15, [rbx+68h]
0x180124f0e  xor     edx, edx; length
0x180124f10  mov     rcx, rsi; string
0x180124f13  call    cs:__imp_WindowsGetStringRawBuffer
0x180124f19  xor     r8d, r8d; ulFlags
0x180124f1c  mov     rdx, rax; pDeviceID
0x180124f1f  mov     rcx, r15; pdnDevInst
0x180124f22  call    cs:__imp_CM_Locate_DevNodeW
0x180124f28  mov     esi, 80070490h
0x180124f2d  test    eax, eax
0x180124f2f  jz      short loc_180124F6F
0x180124f31  mov     [r15], r12d
0x180124f34  mov     ecx, eax; this
0x180124f36  call    ?ConfigretToHresult@Details@PnpApiWrapper@@YAJK@Z; PnpApiWrapper::Details::ConfigretToHresult(ulong)
0x180124f3b  mov     edi, eax
0x180124f3d  cmp     eax, esi
0x180124f3f  jz      short loc_180124F5F
0x180124f41  test    eax, eax
0x180124f43  jns     short loc_180124F6F
0x180124f45  mov     rcx, [rbp+38h]; this
0x180124f49  mov     r9d, eax; char *
0x180124f4c  lea     r8, aOnecoreuapWind_228; "onecoreuap\\windows\\moderncore\\inputv"...
0x180124f53  mov     edx, 338h; void *
0x180124f58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124f5d  mov     esi, edi
0x180124f5f  mov     rcx, rbx; this
0x180124f62  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x180124f67  nop
0x180124f68  mov     eax, esi
0x180124f6a  jmp     loc_18012515B
0x180124f6f  mov     eax, [r15]
0x180124f72  mov     dword ptr [rbp+pdnDevInst], eax
0x180124f75  lea     r9, [rbx+38h]; struct _DEVPROPKEY *
0x180124f79  lea     r8, DEVPKEY_Device_ClassGuid; void *
0x180124f80  lea     rdx, [rbp+pdnDevInst]; unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *)
0x180124f84  lea     rcx, ?GetDeviceNodeProperty@Adapters@@YAKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z; this
0x180124f8b  call    ?GetDeviceGuidProperty@Details@PnpApiWrapper@@YAJP6AKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z01AEAU_GUID@@@Z; PnpApiWrapper::Details::GetDeviceGuidProperty(ulong (*)(void *,_DEVPROPKEY const *,ulong *,void *,uint &),void *,_DEVPROPKEY const *,_GUID &)
0x180124f90  mov     edi, eax
0x180124f92  test    eax, eax
0x180124f94  jns     short loc_180124FA4
0x180124f96  mov     rcx, rbx; this
0x180124f99  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x180124f9e  nop
0x180124f9f  jmp     loc_180125159
0x180124fa4  mov     [rbx+90h], r13
0x180124fab  mov     edi, [r15]
0x180124fae  mov     [rbx+70h], edi
0x180124fb1  movups  xmm0, xmmword ptr [rbx+38h]
0x180124fb5  movdqu  xmmword ptr [rbx+58h], xmm0
0x180124fba  mov     dword ptr [rbp+pdnDevInst], edi
0x180124fbd  mov     r12d, r14d
0x180124fc0  xor     r13d, r13d
0x180124fc3  xorps   xmm0, xmm0
0x180124fc6  movups  [rbp+Buf1], xmm0
0x180124fca  xor     r8d, r8d; ulFlags
0x180124fcd  mov     edx, edi; dnDevInst
0x180124fcf  lea     rcx, [rbp+pdnDevInst]; pdnDevInst
0x180124fd3  call    cs:__imp_CM_Get_Parent
0x180124fd9  test    eax, eax
0x180124fdb  jz      short loc_180125016
0x180124fdd  mov     r8d, r13d
0x180124fe0  mov     dword ptr [rbp+pdnDevInst], r13d
0x180124fe4  mov     ecx, eax; this
0x180124fe6  call    ?ConfigretToHresult@Details@PnpApiWrapper@@YAJK@Z; PnpApiWrapper::Details::ConfigretToHresult(ulong)
0x180124feb  mov     edi, eax
0x180124fed  cmp     eax, esi
0x180124fef  jz      loc_1801250AB
0x180124ff5  test    eax, eax
0x180124ff7  jns     short loc_18012501A
0x180124ff9  mov     rcx, [rbp+38h]; this
0x180124ffd  mov     r9d, eax; char *
0x180125000  lea     r8, aOnecoreuapWind_228; "onecoreuap\\windows\\moderncore\\inputv"...
0x180125007  mov     edx, 37Dh; void *
0x18012500c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125011  jmp     loc_1801250AD
0x180125016  mov     r8d, dword ptr [rbp+pdnDevInst]
0x18012501a  mov     dword ptr [rbp+var_30], r8d
0x18012501e  lea     r9, [rbp+Buf1]; struct _DEVPROPKEY *
0x180125022  lea     r8, DEVPKEY_Device_ClassGuid; void *
0x180125029  lea     rdx, [rbp+var_30]; unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *)
0x18012502d  lea     rcx, ?GetDeviceNodeProperty@Adapters@@YAKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z; this
0x180125034  call    ?GetDeviceGuidProperty@Details@PnpApiWrapper@@YAJP6AKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z01AEAU_GUID@@@Z; PnpApiWrapper::Details::GetDeviceGuidProperty(ulong (*)(void *,_DEVPROPKEY const *,ulong *,void *,uint &),void *,_DEVPROPKEY const *,_GUID &)
0x180125039  mov     edi, eax
0x18012503b  test    eax, eax
0x18012503d  js      loc_180125150
0x180125043  mov     edi, 10h
0x180125048  mov     r8d, edi; Size
0x18012504b  lea     rdx, GUID_NULL; Buf2
0x180125052  lea     rcx, [rbp+Buf1]; Buf1
0x180125056  call    memcmp_0
0x18012505b  test    eax, eax
0x18012505d  jz      short loc_1801250BB
0x18012505f  mov     r8d, edi; Size
0x180125062  lea     rdx, qword_1801F96E8; Buf2
0x180125069  lea     rcx, [rbp+Buf1]; Buf1
0x18012506d  call    memcmp_0
0x180125072  mov     edi, dword ptr [rbp+pdnDevInst]
0x180125075  test    eax, eax
0x180125077  jz      short loc_180125093
0x180125079  mov     r8d, 10h; Size
0x18012507f  lea     rdx, qword_1801F96D8; Buf2
0x180125086  lea     rcx, [rbp+Buf1]; Buf1
0x18012508a  call    memcmp_0
0x18012508f  test    eax, eax
0x180125091  jnz     short loc_1801250A3
0x180125093  movups  xmm0, [rbp+Buf1]
0x180125097  movdqu  xmmword ptr [rbx+58h], xmm0
0x18012509c  mov     [rbx+70h], edi
0x18012509f  mov     [rbx+6Ch], r12d
0x1801250a3  add     r12d, r14d
0x1801250a6  jmp     loc_180124FC3
0x1801250ab  mov     edi, esi
0x1801250ad  mov     rcx, rbx; this
0x1801250b0  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x1801250b5  nop
0x1801250b6  jmp     loc_180125159
0x1801250bb  mov     [rbp+string], r13
0x1801250bf  xor     ecx, ecx; string
0x1801250c1  call    cs:__imp_WindowsDeleteString
0x1801250c7  mov     [rbp+string], r13
0x1801250cb  mov     eax, [r15]
0x1801250ce  mov     dword ptr [rbp+var_30], eax
0x1801250d1  lea     r9, [rbp+string]; struct _DEVPROPKEY *
0x1801250d5  lea     r8, DEVPKEY_Device_HardwareIds; void *
0x1801250dc  lea     rdx, [rbp+var_30]; unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *)
0x1801250e0  lea     rcx, ?GetDeviceNodeProperty@Adapters@@YAKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z; this
0x1801250e7  call    ?GetDeviceStringProperty@Details@PnpApiWrapper@@YAJP6AKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z01AEAPEAUHSTRING__@@@Z; PnpApiWrapper::Details::GetDeviceStringProperty(ulong (*)(void *,_DEVPROPKEY const *,ulong *,void *,uint &),void *,_DEVPROPKEY const *,HSTRING__ * &)
0x1801250ec  mov     edi, eax
0x1801250ee  test    eax, eax
0x1801250f0  jns     short loc_18012510B
0x1801250f2  mov     rcx, [rbp+string]; string
0x1801250f6  call    cs:__imp_WindowsDeleteString
0x1801250fc  mov     [rbp+string], r13
0x180125100  mov     rcx, rbx; this
0x180125103  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x180125108  nop
0x180125109  jmp     short loc_180125159
0x18012510b  mov     rdx, [rbp+string]; HSTRING
0x18012510f  mov     rcx, rbx; this
0x180125112  call    ?ParseHardwareIdStrings@PnpDevice@@AEAAJPEAUHSTRING__@@@Z; PnpDevice::ParseHardwareIdStrings(HSTRING__ *)
0x180125117  mov     edi, eax
0x180125119  test    eax, eax
0x18012511b  jns     short loc_180125136
0x18012511d  mov     rcx, [rbp+string]; string
0x180125121  call    cs:__imp_WindowsDeleteString
0x180125127  mov     [rbp+string], r13
0x18012512b  mov     rcx, rbx; this
0x18012512e  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x180125133  nop
0x180125134  jmp     short loc_180125159
0x180125136  xchg    r14d, [rbx+7Ch]
0x18012513a  mov     rax, [rbp+var_28]
0x18012513e  mov     [rax], rbx
0x180125141  mov     rcx, [rbp+string]; string
0x180125145  call    cs:__imp_WindowsDeleteString
0x18012514b  nop
0x18012514c  xor     eax, eax
0x18012514e  jmp     short loc_18012515B
0x180125150  mov     rcx, rbx; this
0x180125153  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x180125158  nop
0x180125159  mov     eax, edi
0x18012515b  mov     rcx, [rbp+var_10]
0x18012515f  xor     rcx, rsp; StackCookie
0x180125162  call    __security_check_cookie
0x180125167  mov     rbx, [rsp+60h+arg_8]
0x18012516f  add     rsp, 60h
0x180125173  pop     r15
0x180125175  pop     r14
0x180125177  pop     r13
0x180125179  pop     r12
0x18012517b  pop     rdi
0x18012517c  pop     rsi
0x18012517d  pop     rbp
0x18012517e  retn
```
