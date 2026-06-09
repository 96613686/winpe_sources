# SelectiveSuspendTroubleshooter::ProcessUsb3DeviceRundownEvent(_EVENT_RECORD *)

- ea: `0x180034ed0`
- end: `0x18003524f`
- name: `?ProcessUsb3DeviceRundownEvent@SelectiveSuspendTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `895`
- prototype: `void(SelectiveSuspendTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x1800237a0`

## callees

- `0x180004e20`
- `0x18001be60`
- `0x18001c8cc`
- `0x1800253e0`
- `0x180027bcc`
- `0x180034ed0`
- `0x180036874`
- `0x18003bb60`
- `0x18003bf74`
- `0x180045670`
- `0x18004ca90`
- `0x18006abe4`
- `0x18006ad04`
- `0x18006af78`
- `0x18006afa0`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180034f9f`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180034f9f`

## string_xrefs

- `0x180034fb8`: `fid_PortPathDepth`
- `0x18003503a`: `fid_DeviceDescriptor`
- `0x180034fdb`: `fid_PortPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SelectiveSuspendTroubleshooter::ProcessUsb3DeviceRundownEvent(
        SelectiveSuspendTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  __int128 v4; // xmm0
  unsigned int i; // edi
  _DWORD *v6; // r8
  void *v7; // r14
  char v8; // si
  __int64 QuadPart; // rbx
  __int64 v10; // rax
  __int64 v11; // rbx
  _QWORD *v12; // rax
  _BYTE v13[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v14; // [rsp+64h] [rbp-9Ch] BYREF
  int v15; // [rsp+68h] [rbp-98h] BYREF
  int v16; // [rsp+6Ch] [rbp-94h] BYREF
  int v17; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+74h] [rbp-8Ch] BYREF
  int v19; // [rsp+78h] [rbp-88h] BYREF
  void *v20; // [rsp+80h] [rbp-80h] BYREF
  __int128 v21; // [rsp+88h] [rbp-78h]
  BYTE pBuffer[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE *v23; // [rsp+A0h] [rbp-60h]
  _BYTE v24[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v25[32]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v26; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v27; // [rsp+F0h] [rbp-10h]
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v29; // [rsp+108h] [rbp+8h] BYREF
  __int128 v30; // [rsp+118h] [rbp+18h]
  int v31[32]; // [rsp+130h] [rbp+30h] BYREF
  _DWORD v32[6]; // [rsp+1B0h] [rbp+B0h] BYREF

  *(_QWORD *)pBuffer = 0;
  v13[0] = 0;
  v4 = 0;
  v29 = 0;
  v30 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v29);
  v26 = v4;
  v27 = 0;
  std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(&v20);
  v14 = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  v15 = 0;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"fid_UsbDevice";
  if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, pBuffer)
    && !GetEventProperty(a2, L"fid_PortPathDepth", &v14, 4u)
    && !GetEventProperty(a2, L"fid_PortPath", v32, 0x18u) )
  {
    for ( i = 0; i < v14; ++i )
    {
      v6 = &v32[i];
      if ( (_QWORD)v21 == *((_QWORD *)&v21 + 1) )
      {
        std::vector<unsigned long>::_Emplace_reallocate<unsigned long const &>(&v20, v21, v6);
      }
      else
      {
        *(_DWORD *)v21 = *v6;
        *(_QWORD *)&v21 = v21 + 4;
      }
    }
    if ( !GetEventProperty(a2, L"fid_DeviceDescriptor", &v26, 0x12u)
      && !GetEventProperty(a2, L"fid_Suspended", v13, 1u)
      && !GetEventProperty(a2, L"fid_PciBus", &v17, 4u)
      && !GetEventProperty(a2, L"fid_PciDevice", &v16, 4u)
      && !GetEventProperty(a2, L"fid_PciFunction", &v15, 4u)
      && !GetEventProperty(a2, L"fid_PciVendorId", &v19, 4u)
      && !GetEventProperty(a2, L"fid_PciDeviceId", &v18, 4u) )
    {
      if ( (unsigned int)GetEventProperty(a2) )
        std::wstring::assign(&v29, &qword_18009CA18);
      v23 = v25;
      v7 = (void *)std::wstring::wstring((__int64)v25, &v29);
      v8 = v13[0] != 0;
      QuadPart = a2->EventHeader.TimeStamp.QuadPart;
      v10 = std::vector<unsigned long>::vector<unsigned long>(v24, &v20);
      v11 = UsbDevice::UsbDevice((int)v31, v19, v18, v17, v16, v15, WORD4(v26), WORD5(v26), v10, QuadPart, v8, v7);
      v12 = (_QWORD *)std::map<void *,UsbDevice>::_Try_emplace<void * const &,>(
                        (char *)this + 24,
                        &pPropertyData,
                        pBuffer);
      UsbDevice::operator=(*v12 + 40LL, v11);
      UsbDevice::~UsbDevice((UsbDevice *)v31);
    }
  }
  if ( v20 )
  {
    std::_Deallocate<16>(v20, (*((_QWORD *)&v21 + 1) - (_QWORD)v20) & 0xFFFFFFFFFFFFFFFCuLL);
    v20 = 0;
    v21 = 0;
  }
  if ( *((_QWORD *)&v30 + 1) > 7u )
    std::_Deallocate<16>((void *)v29, 2LL * *((_QWORD *)&v30 + 1) + 2);
}

```

## disassembly

```asm
0x180034ed0  mov     [rsp-8+arg_10], rbx
0x180034ed5  mov     [rsp-8+arg_18], rsi
0x180034eda  push    rbp
0x180034edb  push    rdi
0x180034edc  push    r12
0x180034ede  push    r14
0x180034ee0  push    r15
0x180034ee2  lea     rbp, [rsp-0D0h]
0x180034eea  sub     rsp, 1D0h
0x180034ef1  mov     rax, cs:__security_cookie
0x180034ef8  xor     rax, rsp
0x180034efb  mov     [rbp+0F0h+var_28], rax
0x180034f02  mov     rbx, rdx
0x180034f05  mov     r15, rcx
0x180034f08  xor     r12d, r12d
0x180034f0b  mov     qword ptr [rbp+0F0h+var_158], r12
0x180034f0f  mov     [rsp+1F0h+var_190], r12b
0x180034f14  xorps   xmm0, xmm0
0x180034f17  movups  [rbp+0F0h+var_E8], xmm0
0x180034f1b  xorps   xmm1, xmm1
0x180034f1e  movdqu  [rbp+0F0h+var_D8], xmm1
0x180034f23  lea     rcx, [rbp+0F0h+var_E8]
0x180034f27  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180034f2c  nop
0x180034f2d  xor     eax, eax
0x180034f2f  movups  [rbp+0F0h+var_110], xmm0
0x180034f33  mov     [rbp+0F0h+var_100], ax
0x180034f37  lea     rcx, [rbp+0F0h+var_170]; void *
0x180034f3b  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x180034f40  nop
0x180034f41  mov     [rsp+1F0h+var_18C], r12d
0x180034f46  mov     [rsp+1F0h+var_178], r12d
0x180034f4b  mov     [rsp+1F0h+var_17C], r12d
0x180034f50  mov     [rsp+1F0h+var_180], r12d
0x180034f55  mov     [rsp+1F0h+var_184], r12d
0x180034f5a  mov     [rsp+1F0h+var_188], r12d
0x180034f5f  mov     [rbp+0F0h+var_F8.Reserved], r12d
0x180034f63  mov     [rbp+0F0h+var_F8.ArrayIndex], 0FFFFFFFFh
0x180034f6a  lea     rax, aFidUsbdevice; "fid_UsbDevice"
0x180034f71  mov     [rbp+0F0h+var_F8.PropertyName], rax
0x180034f75  lea     rax, [rbp+0F0h+var_158]
0x180034f79  mov     [rsp+1F0h+pBuffer], rax; pBuffer
0x180034f7e  mov     [rsp+1F0h+BufferSize], 8; BufferSize
0x180034f86  lea     rax, [rbp+0F0h+var_F8]
0x180034f8a  mov     [rsp+1F0h+pPropertyData], rax; pPropertyData
0x180034f8f  lea     r14d, [r12+1]
0x180034f94  mov     r9d, r14d; PropertyDataCount
0x180034f97  xor     r8d, r8d; pTdhContext
0x180034f9a  xor     edx, edx; TdhContextCount
0x180034f9c  mov     rcx, rbx; pEvent
0x180034f9f  call    cs:__imp_TdhGetProperty
0x180034fa5  test    eax, eax
0x180034fa7  jnz     loc_1800351E4
0x180034fad  lea     esi, [rax+4]
0x180034fb0  mov     r9d, esi; unsigned int
0x180034fb3  lea     r8, [rsp+1F0h+var_18C]; void *
0x180034fb8  lea     rdx, aFidPortpathdep; "fid_PortPathDepth"
0x180034fbf  mov     rcx, rbx; struct _EVENT_RECORD *
0x180034fc2  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x180034fc7  test    eax, eax
0x180034fc9  jnz     loc_1800351E4
0x180034fcf  lea     r9d, [r12+18h]; unsigned int
0x180034fd4  lea     r8, [rbp+0F0h+var_40]; void *
0x180034fdb  lea     rdx, aFidPortpath; "fid_PortPath"
0x180034fe2  mov     rcx, rbx; struct _EVENT_RECORD *
0x180034fe5  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x180034fea  test    eax, eax
0x180034fec  jnz     loc_1800351E4
0x180034ff2  mov     edi, r12d
0x180034ff5  cmp     [rsp+1F0h+var_18C], r12d
0x180034ffa  jbe     short loc_180035030
0x180034ffc  mov     eax, edi
0x180034ffe  lea     r8, [rbp+0F0h+var_40]
0x180035005  lea     r8, [r8+rax*4]
0x180035009  mov     rdx, qword ptr [rbp+0F0h+var_168]
0x18003500d  cmp     rdx, qword ptr [rbp+0F0h+var_168+8]
0x180035011  jz      short loc_18003501E
0x180035013  mov     eax, [r8]
0x180035016  mov     [rdx], eax
0x180035018  add     qword ptr [rbp+0F0h+var_168], rsi
0x18003501c  jmp     short loc_180035027
0x18003501e  lea     rcx, [rbp+0F0h+var_170]
0x180035022  call    ??$_Emplace_reallocate@AEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAKAEBK@Z; std::vector<ulong>::_Emplace_reallocate<ulong const &>(ulong * const,ulong const &)
0x180035027  add     edi, r14d
0x18003502a  cmp     edi, [rsp+1F0h+var_18C]
0x18003502e  jb      short loc_180034FFC
0x180035030  mov     r9d, 12h; unsigned int
0x180035036  lea     r8, [rbp+0F0h+var_110]; void *
0x18003503a  lea     rdx, aFidDevicedescr; "fid_DeviceDescriptor"
0x180035041  mov     rcx, rbx; struct _EVENT_RECORD *
0x180035044  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x180035049  test    eax, eax
0x18003504b  jnz     loc_1800351E4
0x180035051  mov     r9d, r14d; unsigned int
0x180035054  lea     r8, [rsp+1F0h+var_190]; void *
0x180035059  lea     rdx, aFidSuspended; "fid_Suspended"
0x180035060  mov     rcx, rbx; struct _EVENT_RECORD *
0x180035063  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x180035068  test    eax, eax
0x18003506a  jnz     loc_1800351E4
0x180035070  mov     r9d, esi; unsigned int
0x180035073  lea     r8, [rsp+1F0h+var_180]; void *
0x180035078  lea     rdx, aFidPcibus; "fid_PciBus"
0x18003507f  mov     rcx, rbx; struct _EVENT_RECORD *
0x180035082  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x180035087  test    eax, eax
0x180035089  jnz     loc_1800351E4
0x18003508f  mov     r9d, esi; unsigned int
0x180035092  lea     r8, [rsp+1F0h+var_184]; void *
0x180035097  lea     rdx, aFidPcidevice; "fid_PciDevice"
0x18003509e  mov     rcx, rbx; struct _EVENT_RECORD *
0x1800350a1  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x1800350a6  test    eax, eax
0x1800350a8  jnz     loc_1800351E4
0x1800350ae  mov     r9d, esi; unsigned int
0x1800350b1  lea     r8, [rsp+1F0h+var_188]; void *
0x1800350b6  lea     rdx, aFidPcifunction; "fid_PciFunction"
0x1800350bd  mov     rcx, rbx; struct _EVENT_RECORD *
0x1800350c0  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x1800350c5  test    eax, eax
0x1800350c7  jnz     loc_1800351E4
0x1800350cd  mov     r9d, esi; unsigned int
0x1800350d0  lea     r8, [rsp+1F0h+var_178]; void *
0x1800350d5  lea     rdx, aFidPcivendorid; "fid_PciVendorId"
0x1800350dc  mov     rcx, rbx; struct _EVENT_RECORD *
0x1800350df  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x1800350e4  test    eax, eax
0x1800350e6  jnz     loc_1800351E4
0x1800350ec  mov     r9d, esi; unsigned int
0x1800350ef  lea     r8, [rsp+1F0h+var_17C]; void *
0x1800350f4  lea     rdx, aFidPcideviceid; "fid_PciDeviceId"
0x1800350fb  mov     rcx, rbx; struct _EVENT_RECORD *
0x1800350fe  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGPEAXK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,void *,ulong)
0x180035103  test    eax, eax
0x180035105  jnz     loc_1800351E4
0x18003510b  xor     r9d, r9d
0x18003510e  lea     r8, [rbp+0F0h+var_E8]
0x180035112  lea     rdx, aFidPdoname; "fid_PdoName"
0x180035119  mov     rcx, rbx; pEvent
0x18003511c  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x180035121  test    eax, eax
0x180035123  jz      short loc_180035135
0x180035125  lea     rdx, qword_18009CA18
0x18003512c  lea     rcx, [rbp+0F0h+var_E8]
0x180035130  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180035135  lea     rax, [rbp+0F0h+var_130]
0x180035139  mov     [rbp+0F0h+var_150], rax
0x18003513d  lea     rdx, [rbp+0F0h+var_E8]
0x180035141  lea     rcx, [rbp+0F0h+var_130]
0x180035145  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003514a  mov     r14, rax
0x18003514d  cmp     [rsp+1F0h+var_190], r12b
0x180035152  setnz   sil
0x180035156  mov     rbx, [rbx+10h]
0x18003515a  lea     rdx, [rbp+0F0h+var_170]
0x18003515e  lea     rcx, [rbp+0F0h+var_148]
0x180035162  call    ??0?$vector@KV?$allocator@K@std@@@std@@QEAA@AEBV01@@Z; std::vector<ulong>::vector<ulong>(std::vector<ulong> const &)
0x180035167  mov     r11d, [rsp+1F0h+var_188]
0x18003516c  mov     edi, [rsp+1F0h+var_184]
0x180035170  movzx   ecx, word ptr [rbp+0F0h+var_110+0Ah]
0x180035174  movzx   r10d, word ptr [rbp+0F0h+var_110+8]
0x180035179  mov     [rsp+1F0h+var_198], r14; void *
0x18003517e  mov     [rsp+1F0h+var_1A0], sil; char
0x180035183  mov     [rsp+1F0h+var_1A8], rbx; __int64
0x180035188  mov     [rsp+1F0h+var_1B0], rax; __int64
0x18003518d  mov     [rsp+1F0h+var_1B8], ecx; int
0x180035191  mov     dword ptr [rsp+1F0h+pBuffer], r10d; int
0x180035196  mov     [rsp+1F0h+BufferSize], r11d; int
0x18003519b  mov     dword ptr [rsp+1F0h+pPropertyData], edi; int
0x18003519f  mov     r9d, [rsp+1F0h+var_180]; int
0x1800351a4  mov     r8d, [rsp+1F0h+var_17C]; int
0x1800351a9  mov     edx, [rsp+1F0h+var_178]; int
0x1800351ad  lea     rcx, [rbp+0F0h+var_C0]; int
0x1800351b1  call    ??0UsbDevice@@QEAA@KKKKKKKV?$vector@KV?$allocator@K@std@@@std@@T_LARGE_INTEGER@@EV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; UsbDevice::UsbDevice(ulong,ulong,ulong,ulong,ulong,ulong,ulong,std::vector<ulong>,_LARGE_INTEGER,uchar,std::wstring)
0x1800351b6  mov     rbx, rax
0x1800351b9  lea     rcx, [r15+18h]
0x1800351bd  lea     r8, [rbp+0F0h+var_158]
0x1800351c1  lea     rdx, [rbp+0F0h+var_F8]
0x1800351c5  call    ??$_Try_emplace@AEBQEAX$$V@?$map@PEAXVUsbDevice@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXVUsbDevice@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAXVUsbDevice@@@std@@PEAX@std@@_N@1@AEBQEAX@Z; std::map<void *,UsbDevice>::_Try_emplace<void * const &,>(void * const &)
0x1800351ca  mov     rcx, [rax]
0x1800351cd  add     rcx, 28h ; '('
0x1800351d1  mov     rdx, rbx
0x1800351d4  call    ??4UsbDevice@@QEAAAEAV0@$$QEAV0@@Z; UsbDevice::operator=(UsbDevice &&)
0x1800351d9  nop
0x1800351da  lea     rcx, [rbp+0F0h+var_C0]; this
0x1800351de  call    ??1UsbDevice@@QEAA@XZ; UsbDevice::~UsbDevice(void)
0x1800351e3  nop
0x1800351e4  mov     rcx, [rbp+0F0h+var_170]
0x1800351e8  test    rcx, rcx
0x1800351eb  jz      short loc_180035209
0x1800351ed  mov     rdx, qword ptr [rbp+0F0h+var_168+8]
0x1800351f1  sub     rdx, rcx
0x1800351f4  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800351f8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800351fd  mov     [rbp+0F0h+var_170], r12
0x180035201  xorps   xmm0, xmm0
0x180035204  movdqu  [rbp+0F0h+var_168], xmm0
0x180035209  mov     rdx, qword ptr [rbp+0F0h+var_D8+8]
0x18003520d  cmp     rdx, 7
0x180035211  jbe     short loc_180035224
0x180035213  lea     rdx, ds:2[rdx*2]
0x18003521b  mov     rcx, qword ptr [rbp+0F0h+var_E8]
0x18003521f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180035224  mov     rcx, [rbp+0F0h+var_28]
0x18003522b  xor     rcx, rsp; StackCookie
0x18003522e  call    __security_check_cookie
0x180035233  lea     r11, [rsp+1F0h+var_20]
0x18003523b  mov     rbx, [r11+40h]
0x18003523f  mov     rsi, [r11+48h]
0x180035243  mov     rsp, r11
0x180035246  pop     r15
0x180035248  pop     r14
0x18003524a  pop     r12
0x18003524c  pop     rdi
0x18003524d  pop     rbp
0x18003524e  retn
```
