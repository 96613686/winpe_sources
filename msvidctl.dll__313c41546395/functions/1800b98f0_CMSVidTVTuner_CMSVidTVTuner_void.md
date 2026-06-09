# CMSVidTVTuner::CMSVidTVTuner(void)

- ea: `0x1800b98f0`
- end: `0x1800b9a7d`
- name: `??0CMSVidTVTuner@@QEAA@XZ`
- size: `397`
- prototype: `CMSVidTVTuner *__fastcall(CMSVidTVTuner *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800b95b4`
- `0x1800b96f8`

## callees

- `0x18001414c`
- `0x1800b98f0`
- `0x1800ee91c`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800b99b6`
- `KERNEL32!GetCurrentProcessId` at `0x1800b99be`
- `KERNEL32!GetCurrentProcessId` at `0x1800b99b6`
- `KERNEL32!GetCurrentProcessId` at `0x1800b99be`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
CMSVidTVTuner *__fastcall CMSVidTVTuner::CMSVidTVTuner(CMSVidTVTuner *this)
{
  __int64 CurrentProcessId; // rbp
  DWORD v3; // r14d

  *((_DWORD *)this + 50) = 0;
  *((_QWORD *)this + 1) = 0;
  std::vector<DSPin>::vector<DSPin>((char *)this + 56);
  *((_QWORD *)this + 4) = &CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `IDispatchConnectionPointImpl<CMSVidTVTuner,&_GUID const IID_IDispatch>'};
  *((_QWORD *)this + 5) = &CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `IDispatchConnectionPointImpl<CMSVidTVTuner,&_GUID const IID_IMSVidDeviceEvent>'};
  *((_QWORD *)this + 6) = &CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `IDispatchCPImpl<CMSVidTVTuner>'};
  *((_QWORD *)this + 10) = &CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `MSVideoControl::CProxy_InputDeviceEvent<CMSVidTVTuner>'};
  *((_QWORD *)this + 11) = &CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `IDispatchConnectionPointImpl<CMSVidTVTuner,&_GUID const IID_IMSVidTunerEvent>'};
  *((_QWORD *)this + 12) = &CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable';
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_DWORD *)this + 55) = -1;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 60) = -1;
  *((_DWORD *)this + 61) = -1;
  *((_WORD *)this + 124) = 0;
  *((_QWORD *)this + 32) = 0;
  CurrentProcessId = GetCurrentProcessId();
  v3 = GetCurrentProcessId();
  EHOME_TraceEventing::LoadTraceEvent((EHOME_TraceEventing *)&g_TraceEventing);
  if ( !qword_18021D640
    || ((unsigned int (__fastcall *)(const wchar_t *, __int64 *, _QWORD, _QWORD, __int64, GUID *, int, int, char *))*g_TraceEventing)(
         L"MSVidTVTuner Event Provider",
         qword_180168FF0,
         0,
         v3,
         CurrentProcessId,
         &EH_Tuning_Events_GUID,
         1,
         1,
         (char *)this + 220) )
  {
    *((_DWORD *)this + 55) = -1;
  }
  else
  {
    EHOME_TraceEventing::LoadTraceEvent((EHOME_TraceEventing *)&g_TraceEventing);
    if ( !qword_18021D640
      || (*(unsigned int (__fastcall **)(__int64, char *))(g_TraceEventing + 32LL))(8, (char *)this + 224) )
    {
      *((_QWORD *)this + 28) = 0;
    }
  }
  *((_BYTE *)this + 216) = 0;
  return this;
}

```

## disassembly

```asm
0x1800b98f0  mov     [rsp+arg_0], rcx
0x1800b98f5  push    rbx
0x1800b98f6  push    rbp
0x1800b98f7  push    rsi
0x1800b98f8  push    rdi
0x1800b98f9  push    r14
0x1800b98fb  push    r15
0x1800b98fd  sub     rsp, 58h
0x1800b9901  mov     rbx, rcx
0x1800b9904  xor     r15d, r15d
0x1800b9907  mov     [rcx+0C8h], r15d
0x1800b990e  mov     [rcx+8], r15
0x1800b9912  add     rcx, 38h ; '8'
0x1800b9916  call    ??0?$vector@VDSPin@@V?$allocator@VDSPin@@@std@@@std@@QEAA@XZ; std::vector<DSPin>::vector<DSPin>(void)
0x1800b991b  lea     rcx, ??_7?$CProxy_IMSVidAnalogTuner@VCMSVidTVTuner@@@@6B?$IDispatchConnectionPointImpl@VCMSVidTVTuner@@$1?IID_IDispatch@@3U_GUID@@B@@@; const CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `IDispatchConnectionPointImpl<CMSVidTVTuner,&_GUID const IID_IDispatch>'}
0x1800b9922  mov     [rbx+20h], rcx
0x1800b9926  lea     rax, ??_7?$CProxy_IMSVidAnalogTuner@VCMSVidTVTuner@@@@6B?$IDispatchConnectionPointImpl@VCMSVidTVTuner@@$1?IID_IMSVidDeviceEvent@@3U_GUID@@B@@@; const CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `IDispatchConnectionPointImpl<CMSVidTVTuner,&_GUID const IID_IMSVidDeviceEvent>'}
0x1800b992d  mov     [rbx+28h], rax
0x1800b9931  lea     rax, ??_7?$CProxy_IMSVidAnalogTuner@VCMSVidTVTuner@@@@6B?$IDispatchCPImpl@VCMSVidTVTuner@@@@@; const CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `IDispatchCPImpl<CMSVidTVTuner>'}
0x1800b9938  mov     [rbx+30h], rax
0x1800b993c  lea     rax, ??_7?$CProxy_IMSVidAnalogTuner@VCMSVidTVTuner@@@@6B?$CProxy_InputDeviceEvent@VCMSVidTVTuner@@@MSVideoControl@@@; const CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `MSVideoControl::CProxy_InputDeviceEvent<CMSVidTVTuner>'}
0x1800b9943  mov     [rbx+50h], rax
0x1800b9947  lea     rax, ??_7?$CProxy_IMSVidAnalogTuner@VCMSVidTVTuner@@@@6B?$IDispatchConnectionPointImpl@VCMSVidTVTuner@@$1?IID_IMSVidTunerEvent@@3U_GUID@@B@@@; const CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'{for `IDispatchConnectionPointImpl<CMSVidTVTuner,&_GUID const IID_IMSVidTunerEvent>'}
0x1800b994e  mov     [rbx+58h], rax
0x1800b9952  lea     rax, ??_7?$CProxy_IMSVidAnalogTuner@VCMSVidTVTuner@@@@6B@; const CProxy_IMSVidAnalogTuner<CMSVidTVTuner>::`vftable'
0x1800b9959  mov     [rbx+60h], rax
0x1800b995d  mov     [rbx+70h], r15
0x1800b9961  mov     [rbx+78h], r15d
0x1800b9965  mov     [rbx+0B0h], r15
0x1800b996c  mov     [rbx+0B8h], r15
0x1800b9973  mov     [rbx+0D0h], r15
0x1800b997a  lea     rsi, [rbx+0DCh]
0x1800b9981  mov     dword ptr [rsi], 0FFFFFFFFh
0x1800b9987  lea     rdi, [rbx+0E0h]
0x1800b998e  mov     [rdi], r15
0x1800b9991  mov     [rbx+0E8h], r15
0x1800b9998  or      eax, 0FFFFFFFFh
0x1800b999b  mov     [rbx+0F0h], eax
0x1800b99a1  mov     [rbx+0F4h], eax
0x1800b99a7  mov     [rbx+0F8h], r15w
0x1800b99af  mov     [rbx+100h], r15
0x1800b99b6  call    cs:__imp_GetCurrentProcessId
0x1800b99bc  mov     ebp, eax
0x1800b99be  call    cs:__imp_GetCurrentProcessId
0x1800b99c4  mov     r14d, eax
0x1800b99c7  lea     rcx, ?g_TraceEventing@@3VEHOME_TraceEventing@@A; this
0x1800b99ce  call    ?LoadTraceEvent@EHOME_TraceEventing@@QEAAXXZ; EHOME_TraceEventing::LoadTraceEvent(void)
0x1800b99d3  cmp     cs:qword_18021D640, r15
0x1800b99da  jz      loc_1800B9A60
0x1800b99e0  mov     r9d, r14d
0x1800b99e3  mov     rax, cs:?g_TraceEventing@@3VEHOME_TraceEventing@@A; EHOME_TraceEventing g_TraceEventing
0x1800b99ea  mov     [rsp+88h+var_48], rsi
0x1800b99ef  lea     r8d, [r15+1]
0x1800b99f3  mov     [rsp+88h+var_50], r8d
0x1800b99f8  mov     [rsp+88h+var_58], r8d
0x1800b99fd  lea     r8, ?EH_Tuning_Events_GUID@@3PAU_GUID@@A; _GUID near * EH_Tuning_Events_GUID
0x1800b9a04  mov     [rsp+88h+var_60], r8
0x1800b9a09  mov     [rsp+88h+var_68], rbp
0x1800b9a0e  xor     r8d, r8d
0x1800b9a11  lea     rdx, qword_180168FF0
0x1800b9a18  lea     rcx, aMsvidtvtunerEv; "MSVidTVTuner Event Provider"
0x1800b9a1f  mov     rax, [rax]
0x1800b9a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a27  test    eax, eax
0x1800b9a29  jnz     short loc_1800B9A60
0x1800b9a2b  lea     rcx, ?g_TraceEventing@@3VEHOME_TraceEventing@@A; this
0x1800b9a32  call    ?LoadTraceEvent@EHOME_TraceEventing@@QEAAXXZ; EHOME_TraceEventing::LoadTraceEvent(void)
0x1800b9a37  cmp     cs:qword_18021D640, r15
0x1800b9a3e  jz      short loc_1800B9A5B
0x1800b9a40  lea     ecx, [r15+8]
0x1800b9a44  mov     rax, cs:?g_TraceEventing@@3VEHOME_TraceEventing@@A; EHOME_TraceEventing g_TraceEventing
0x1800b9a4b  mov     rdx, rdi
0x1800b9a4e  mov     rax, [rax+20h]
0x1800b9a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a57  test    eax, eax
0x1800b9a59  jz      short loc_1800B9A66
0x1800b9a5b  mov     [rdi], r15
0x1800b9a5e  jmp     short loc_1800B9A66
0x1800b9a60  mov     dword ptr [rsi], 0FFFFFFFFh
0x1800b9a66  mov     [rbx+0D8h], r15b
0x1800b9a6d  mov     rax, rbx
0x1800b9a70  add     rsp, 58h
0x1800b9a74  pop     r15
0x1800b9a76  pop     r14
0x1800b9a78  pop     rdi
0x1800b9a79  pop     rsi
0x1800b9a7a  pop     rbp
0x1800b9a7b  pop     rbx
0x1800b9a7c  retn
```
