# PnpDeviceWatcher::StartDeviceObject(PnpDeviceWatcher::DeviceListEntry &)

- ea: `0x1801243d4`
- end: `0x1801246b9`
- name: `?StartDeviceObject@PnpDeviceWatcher@@AEAAJAEAUDeviceListEntry@1@@Z`
- size: `741`
- prototype: `__int64 __fastcall(PnpDeviceWatcher *__hidden this, struct PnpDeviceWatcher::DeviceListEntry *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18005ca58`

## callees

- `0x18002f9d0`
- `0x18002fea0`
- `0x180030260`
- `0x180064a30`
- `0x18008e2b4`
- `0x18008ead4`
- `0x1800ad318`
- `0x1800f2448`
- `0x180123c2c`
- `0x1801243b8`
- `0x1801243d4`
- `0x1801246c0`
- `0x180125288`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012450e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012465f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012450e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012465f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180124558`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180124558`

## string_xrefs

- `0x180124562`: `Failed to exclusively open LampArray device, adding to retry list`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PnpDeviceWatcher::StartDeviceObject(
        PnpDeviceWatcher *this,
        struct PnpDeviceWatcher::DeviceListEntry *a2)
{
  char *v4; // r15
  char *i; // rbx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 *v8; // rcx
  const char *v9; // r8
  __int64 v10; // rdx
  unsigned int v11; // ebx
  __int64 v13; // rdx
  int v14; // ecx
  int v15; // ecx
  PnpDevice *v16; // rbx
  int InterfacePath; // eax
  int v18; // r8d
  int v19; // r9d
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  __int64 v22; // rax
  InputContext *v23; // rcx
  PnpDeviceWatcher **v24; // rcx
  int v25; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  HSTRING string; // [rsp+78h] [rbp+48h] BYREF
  PCWSTR StringRawBuffer; // [rsp+80h] [rbp+50h] BYREF
  const char *v29; // [rsp+88h] [rbp+58h] BYREF

  if ( *(_DWORD *)(*((_QWORD *)a2 + 2) + 124LL) == 2 )
    return 0;
  if ( !*(_QWORD *)(*((_QWORD *)a2 + 2) + 16LL) )
  {
    v4 = (char *)this + 64;
    for ( i = (char *)*((_QWORD *)this + 8); i != v4; i = *(char **)i )
    {
      if ( i != (char *)a2 )
      {
        v6 = *((_QWORD *)a2 + 2);
        v7 = *((_QWORD *)i + 2);
        if ( *(_DWORD *)(v6 + 124) != 1 )
        {
          v9 = "onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpdevice.cpp";
          v10 = 918;
          goto LABEL_14;
        }
        if ( *(_DWORD *)(v7 + 112) == *(_DWORD *)(v6 + 112) )
        {
          v8 = (__int64 *)(v6 + 16);
          if ( *(_QWORD *)(v6 + 16) )
            v6 = *v8;
          if ( *(_DWORD *)(v7 + 108) < *(_DWORD *)(v6 + 108) )
            Microsoft::WRL::ComPtr<HidLampArrayDevice>::operator=(v8);
        }
      }
    }
  }
  v13 = *((_QWORD *)a2 + 2);
  v14 = *(_DWORD *)(v13 + 124);
  if ( !v14 )
    goto LABEL_20;
  v15 = v14 - 1;
  if ( v15 )
  {
    if ( v15 != 1 )
    {
LABEL_20:
      v9 = "onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpdevicewatcher.cpp";
      v10 = 569;
LABEL_14:
      v11 = -2147418113;
      goto LABEL_15;
    }
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)(v13 + 124), 2);
  }
  if ( *((_BYTE *)a2 + 24) || !*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) )
    return 0;
  *((_BYTE *)a2 + 24) = 1;
  if ( (!IsEdition(0x1820u) || *(_DWORD *)(*((_QWORD *)a2 + 2) + 120LL) != 65548)
    && PnpDevice::OpenInterface(*((PnpDevice **)a2 + 2)) == -2147024864 )
  {
    string = 0;
    v16 = (PnpDevice *)*((_QWORD *)a2 + 2);
    WindowsDeleteString(0);
    string = 0;
    InterfacePath = PnpDevice::GetInterfacePath(v16, &string);
    v11 = InterfacePath;
    if ( InterfacePath >= 0 )
    {
      if ( (unsigned int)dword_180241248 > 5 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v29 = "Failed to exclusively open LampArray device, adding to retry list";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (unsigned int)&dword_180241248,
          (unsigned int)&unk_180207418,
          v18,
          v19,
          (__int64)&v29,
          (__int64)&StringRawBuffer);
      }
      v20 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      v21 = v20;
      if ( v20 )
      {
        *v20 = 0;
        v20[1] = 0;
        v20[3] = 0;
        v20[2] = 0;
        v22 = *((_QWORD *)a2 + 2);
        if ( v22 )
        {
          _InterlockedAdd((volatile signed __int32 *)(v22 + 8), 1u);
          v23 = (InputContext *)v21[2];
          v21[2] = v22;
          if ( v23 )
            InputContext::Release(v23);
        }
        *((_WORD *)v21 + 14) = 3000;
        *((_DWORD *)v21 + 6) = QpcTimeConverter::GetCurrentMilliSecTime((PnpDeviceWatcher *)((char *)this + 112)) + 100;
        StringRawBuffer = 0;
        v24 = (PnpDeviceWatcher **)*((_QWORD *)this + 12);
        if ( *v24 != (PnpDeviceWatcher *)((char *)this + 88) )
          __fastfail(3u);
        *v21 = (char *)this + 88;
        v21[1] = v24;
        *v24 = (PnpDeviceWatcher *)v21;
        *((_QWORD *)this + 12) = v21;
        ++*((_DWORD *)this + 26);
        std::unique_ptr<PnpDeviceWatcher::DeviceListEntry>::~unique_ptr<PnpDeviceWatcher::DeviceListEntry>(&StringRawBuffer);
        v11 = 0;
      }
      else
      {
        StringRawBuffer = 0;
        v11 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24E,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpdevicewatcher.cpp",
          (const char *)0x8007000ELL,
          v25);
        std::unique_ptr<PnpDeviceWatcher::DeviceListEntry>::~unique_ptr<PnpDeviceWatcher::DeviceListEntry>(&StringRawBuffer);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpdevicewatcher.cpp",
        (const char *)(unsigned int)InterfacePath,
        v25);
    }
    WindowsDeleteString(string);
    return v11;
  }
  v11 = LampArrayRawInputProvider::OnLampArrayAdded(*(LampArrayRawInputProvider **)this, *((struct PnpDevice **)a2 + 2));
  if ( (v11 & 0x80000000) != 0 )
  {
    v9 = "onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpdevicewatcher.cpp";
    v10 = 604;
LABEL_15:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, (unsigned int)v9, (const char *)v11, v25);
    return v11;
  }
  if ( v11 != 1 )
    return 0;
  PnpDeviceWatcher::StopDeviceObject(this, a2);
  return 1;
}

```

## disassembly

```asm
0x1801243d4  mov     [rsp-38h+arg_0], rbx
0x1801243d9  push    rbp
0x1801243da  push    rsi
0x1801243db  push    rdi
0x1801243dc  push    r12
0x1801243de  push    r13
0x1801243e0  push    r14
0x1801243e2  push    r15
0x1801243e4  mov     rbp, rsp
0x1801243e7  sub     rsp, 30h
0x1801243eb  mov     rdi, rdx
0x1801243ee  mov     rsi, rcx
0x1801243f1  mov     rax, [rdx+10h]
0x1801243f5  mov     r8d, [rax+7Ch]
0x1801243f9  nop
0x1801243fa  mov     r14d, 2
0x180124400  cmp     r8d, r14d
0x180124403  jz      loc_1801246A2
0x180124409  mov     rax, [rdx+10h]
0x18012440d  lea     r13d, [r14-1]
0x180124411  xor     r12d, r12d
0x180124414  cmp     [rax+10h], r12
0x180124418  jnz     short loc_180124488
0x18012441a  lea     r15, [rcx+40h]
0x18012441e  mov     rbx, [r15]
0x180124421  cmp     rbx, r15
0x180124424  jz      short loc_180124488
0x180124426  cmp     rbx, rdi
0x180124429  jz      short loc_18012445F
0x18012442b  mov     r8, [rdi+10h]
0x18012442f  mov     rdx, [rbx+10h]
0x180124433  mov     eax, [r8+7Ch]
0x180124437  nop
0x180124438  cmp     eax, r13d
0x18012443b  jnz     short loc_180124464
0x18012443d  mov     eax, [r8+70h]
0x180124441  cmp     [rdx+70h], eax
0x180124444  jnz     short loc_18012445F
0x180124446  lea     rcx, [r8+10h]
0x18012444a  cmp     [rcx], r12
0x18012444d  cmovnz  r8, [rcx]
0x180124451  mov     eax, [r8+6Ch]
0x180124455  cmp     [rdx+6Ch], eax
0x180124458  jnb     short loc_18012445F
0x18012445a  call    ??4?$ComPtr@VHidLampArrayDevice@@@WRL@Microsoft@@QEAAAEAV012@PEAVHidLampArrayDevice@@@Z; Microsoft::WRL::ComPtr<HidLampArrayDevice>::operator=(HidLampArrayDevice *)
0x18012445f  mov     rbx, [rbx]
0x180124462  jmp     short loc_180124421
0x180124464  lea     r8, aOnecoreuapWind_237; "onecoreuap\\windows\\moderncore\\inputv"...
0x18012446b  mov     edx, 396h; void *
0x180124470  mov     ebx, 8000FFFFh
0x180124475  mov     rcx, [rbp+38h]; this
0x180124479  mov     r9d, ebx; char *
0x18012447c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124481  mov     eax, ebx
0x180124483  jmp     loc_1801246A4
0x180124488  mov     rdx, [rdi+10h]
0x18012448c  mov     ecx, [rdx+7Ch]
0x18012448f  nop
0x180124490  test    ecx, ecx
0x180124492  jz      short loc_18012449E
0x180124494  sub     ecx, r13d
0x180124497  jz      short loc_1801244AC
0x180124499  cmp     ecx, r13d
0x18012449c  jz      short loc_1801244B0
0x18012449e  lea     r8, aOnecoreuapWind_207; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801244a5  mov     edx, 239h
0x1801244aa  jmp     short loc_180124470
0x1801244ac  xchg    r14d, [rdx+7Ch]
0x1801244b0  cmp     [rdi+18h], r12b
0x1801244b4  jnz     loc_1801246A2
0x1801244ba  mov     rax, [rdi+10h]
0x1801244be  cmp     [rax+20h], r12
0x1801244c2  jz      loc_1801246A2
0x1801244c8  mov     [rdi+18h], r13b
0x1801244cc  mov     ecx, 1820h; unsigned __int64
0x1801244d1  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x1801244d6  test    al, al
0x1801244d8  jz      short loc_1801244F0
0x1801244da  mov     rax, [rdi+10h]
0x1801244de  cmp     word ptr [rax+78h], 0Ch
0x1801244e3  jnz     short loc_1801244F0
0x1801244e5  cmp     [rax+7Ah], r13w
0x1801244ea  jz      loc_18012466A
0x1801244f0  mov     rcx, [rdi+10h]; this
0x1801244f4  call    ?OpenInterface@PnpDevice@@QEAAJXZ; PnpDevice::OpenInterface(void)
0x1801244f9  cmp     eax, 80070020h
0x1801244fe  jnz     loc_18012466A
0x180124504  mov     [rbp+string], r12
0x180124508  mov     rbx, [rdi+10h]
0x18012450c  xor     ecx, ecx; string
0x18012450e  call    cs:__imp_WindowsDeleteString
0x180124514  mov     [rbp+string], r12
0x180124518  lea     rdx, [rbp+string]; HSTRING *
0x18012451c  mov     rcx, rbx; this
0x18012451f  call    ?GetInterfacePath@PnpDevice@@QEAAJPEAPEAUHSTRING__@@@Z; PnpDevice::GetInterfacePath(HSTRING__ * *)
0x180124524  mov     ebx, eax
0x180124526  test    eax, eax
0x180124528  jns     short loc_180124547
0x18012452a  mov     rcx, [rbp+38h]; this
0x18012452e  mov     r9d, eax; char *
0x180124531  lea     r8, aOnecoreuapWind_207; "onecoreuap\\windows\\moderncore\\inputv"...
0x180124538  mov     edx, 249h; void *
0x18012453d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124542  jmp     loc_18012465B
0x180124547  mov     eax, cs:dword_180241248
0x18012454d  cmp     eax, 5
0x180124550  jbe     short loc_180124592
0x180124552  xor     edx, edx; length
0x180124554  mov     rcx, [rbp+string]; string
0x180124558  call    cs:__imp_WindowsGetStringRawBuffer
0x18012455e  mov     [rbp+arg_10], rax
0x180124562  lea     rax, aFailedToExclus_0; "Failed to exclusively open LampArray de"...
0x180124569  mov     [rbp+arg_18], rax
0x18012456d  lea     rax, [rbp+arg_10]
0x180124571  mov     [rsp+30h+var_8], rax
0x180124576  lea     rax, [rbp+arg_18]
0x18012457a  mov     qword ptr [rsp+30h+var_10], rax; int
0x18012457f  lea     rdx, unk_180207418
0x180124586  lea     rcx, dword_180241248
0x18012458d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180124592  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180124599  mov     ecx, 20h ; ' '; unsigned __int64
0x18012459e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801245a3  mov     rbx, rax
0x1801245a6  test    rax, rax
0x1801245a9  jz      loc_180124631
0x1801245af  mov     [rax], r12
0x1801245b2  mov     [rax+8], r12
0x1801245b6  mov     [rax+18h], r12
0x1801245ba  mov     [rax+10h], r12
0x1801245be  mov     rax, [rdi+10h]
0x1801245c2  cmp     r12, rax
0x1801245c5  jz      short loc_1801245E4
0x1801245c7  test    rax, rax
0x1801245ca  jz      short loc_1801245D1
0x1801245cc  lock add [rax+8], r13d
0x1801245d1  mov     rcx, [rbx+10h]; this
0x1801245d5  mov     [rbx+10h], rax
0x1801245d9  test    rcx, rcx
0x1801245dc  jz      short loc_1801245E4
0x1801245de  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x1801245e3  nop
0x1801245e4  mov     word ptr [rbx+1Ch], 0BB8h
0x1801245ea  lea     rcx, [rsi+70h]; this
0x1801245ee  call    ?GetCurrentMilliSecTime@QpcTimeConverter@@QEBAIXZ; QpcTimeConverter::GetCurrentMilliSecTime(void)
0x1801245f3  add     eax, 64h ; 'd'
0x1801245f6  mov     [rbx+18h], eax
0x1801245f9  lea     rax, [rsi+58h]
0x1801245fd  mov     [rbp+arg_10], r12
0x180124601  mov     rcx, [rax+8]
0x180124605  cmp     [rcx], rax
0x180124608  jz      short loc_180124611
0x18012460a  mov     ecx, 3
0x18012460f  int     29h; Win8: RtlFailFast(ecx)
0x180124611  mov     [rbx], rax
0x180124614  mov     [rbx+8], rcx
0x180124618  mov     [rcx], rbx
0x18012461b  mov     [rax+8], rbx
0x18012461f  add     [rax+10h], r13d
0x180124623  lea     rcx, [rbp+arg_10]
0x180124627  call    ??1?$unique_ptr@UDeviceListEntry@PnpDeviceWatcher@@U?$default_delete@UDeviceListEntry@PnpDeviceWatcher@@@std@@@std@@QEAA@XZ; std::unique_ptr<PnpDeviceWatcher::DeviceListEntry>::~unique_ptr<PnpDeviceWatcher::DeviceListEntry>(void)
0x18012462c  mov     ebx, r12d
0x18012462f  jmp     short loc_18012465B
0x180124631  mov     [rbp+arg_10], r12
0x180124635  mov     rcx, [rbp+38h]; this
0x180124639  mov     ebx, 8007000Eh
0x18012463e  mov     r9d, ebx; char *
0x180124641  lea     r8, aOnecoreuapWind_207; "onecoreuap\\windows\\moderncore\\inputv"...
0x180124648  mov     edx, 24Eh; void *
0x18012464d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124652  lea     rcx, [rbp+arg_10]
0x180124656  call    ??1?$unique_ptr@UDeviceListEntry@PnpDeviceWatcher@@U?$default_delete@UDeviceListEntry@PnpDeviceWatcher@@@std@@@std@@QEAA@XZ; std::unique_ptr<PnpDeviceWatcher::DeviceListEntry>::~unique_ptr<PnpDeviceWatcher::DeviceListEntry>(void)
0x18012465b  mov     rcx, [rbp+string]; string
0x18012465f  call    cs:__imp_WindowsDeleteString
0x180124665  jmp     loc_180124481
0x18012466a  mov     rdx, [rdi+10h]; struct PnpDevice *
0x18012466e  mov     rcx, [rsi]; this
0x180124671  call    ?OnLampArrayAdded@LampArrayRawInputProvider@@QEAAJPEAVPnpDevice@@@Z; LampArrayRawInputProvider::OnLampArrayAdded(PnpDevice *)
0x180124676  mov     ebx, eax
0x180124678  test    eax, eax
0x18012467a  jns     short loc_18012468D
0x18012467c  lea     r8, aOnecoreuapWind_207; "onecoreuap\\windows\\moderncore\\inputv"...
0x180124683  mov     edx, 25Ch
0x180124688  jmp     loc_180124475
0x18012468d  cmp     ebx, r13d
0x180124690  jnz     short loc_1801246A2
0x180124692  mov     rdx, rdi; struct PnpDeviceWatcher::DeviceListEntry *
0x180124695  mov     rcx, rsi; this
0x180124698  call    ?StopDeviceObject@PnpDeviceWatcher@@AEAAXAEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::StopDeviceObject(PnpDeviceWatcher::DeviceListEntry &)
0x18012469d  mov     eax, r13d
0x1801246a0  jmp     short loc_1801246A4
0x1801246a2  xor     eax, eax
0x1801246a4  mov     rbx, [rsp+30h+arg_0]
0x1801246a9  add     rsp, 30h
0x1801246ad  pop     r15
0x1801246af  pop     r14
0x1801246b1  pop     r13
0x1801246b3  pop     r12
0x1801246b5  pop     rdi
0x1801246b6  pop     rsi
0x1801246b7  pop     rbp
0x1801246b8  retn
```
