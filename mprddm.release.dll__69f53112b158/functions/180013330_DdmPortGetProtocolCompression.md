# DdmPortGetProtocolCompression

- ea: `0x180013330`
- end: `0x180013553`
- name: `DdmPortGetProtocolCompression`
- size: `547`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x180013330`
- `0x18003d100`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180013472`
- `KERNEL32!LeaveCriticalSection` at `0x180013472`
- `KERNEL32!EnterCriticalSection` at `0x180013446`
- `KERNEL32!EnterCriticalSection` at `0x180013446`

## string_xrefs

- `0x1800133eb`: `DdmPortGetProtocolCompression`
- `0x1800134b9`: `DdmPortGetProtocolCompression`
- `0x1800134c0`: `%s: deviceObj->GetProtocolCompression failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmPortGetProtocolCompression(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  struct DdmDeviceTable *Instance; // rax
  __int64 v9; // rbx
  unsigned int v10; // esi
  __int64 v11; // rdx
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+4Ch] [rbp-B4h]
  __int128 v17; // [rsp+5Ch] [rbp-A4h]
  int v18; // [rsp+6Ch] [rbp-94h]
  int v19; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v13 = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v15 = 0;
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v14 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, a1, &v13);
  v9 = v13;
  if ( v13 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 16));
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v9 + 608LL))(v9, a2, a3, a4);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
    if ( v10 && (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v19) = 0;
      LOWORD(v15) = 0;
      v11 = v9 ? *(unsigned int *)(v9 + 96) : 0xFFFFFFFFLL;
      ConvertPortNoToString(&v15, v11);
      FormatRRASErrorString(
        &v19,
        L"%s: deviceObj->GetProtocolCompression failed for port (%ld):%d.",
        L"DdmPortGetProtocolCompression",
        a1,
        v10);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v19,
          (unsigned int)&v14,
          0,
          (__int64)&v15);
    }
  }
  else
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v19) = 0;
      LOWORD(v15) = 0;
      ConvertPortNoToString(&v15, (unsigned int)a1);
      FormatRRASErrorString(&v19, L"%s: Port %ld not found.", L"DdmPortGetProtocolCompression", a1);
      if ( (byte_1800CF404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v19,
          (unsigned int)&v14,
          0,
          (__int64)&v15);
    }
    v10 = 1168;
  }
  if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v13)(v13, 1);
  return v10;
}

```

## disassembly

```asm
0x180013330  push    rbp
0x180013332  push    rbx
0x180013333  push    rsi
0x180013334  push    rdi
0x180013335  push    r12
0x180013337  push    r13
0x180013339  push    r14
0x18001333b  push    r15
0x18001333d  lea     rbp, [rsp-788h]
0x180013345  sub     rsp, 888h
0x18001334c  mov     rax, cs:__security_cookie
0x180013353  xor     rax, rsp
0x180013356  mov     [rbp+7C0h+var_50], rax
0x18001335d  mov     r15, r8
0x180013360  mov     esi, edx
0x180013362  mov     r14, rcx
0x180013365  xor     r13d, r13d
0x180013368  xor     edx, edx; Val
0x18001336a  mov     [rsp+8C0h+var_890], r13
0x18001336f  mov     r8d, 7FCh; Size
0x180013375  mov     [rsp+8C0h+var_850], r13d
0x18001337a  lea     rcx, [rsp+8C0h+var_84C]; void *
0x18001337f  mov     r12, r9
0x180013382  call    memset_0
0x180013387  xorps   xmm0, xmm0
0x18001338a  mov     [rsp+8C0h+var_878], r13d
0x18001338f  xor     eax, eax
0x180013391  movups  [rsp+8C0h+var_874], xmm0
0x180013396  mov     [rsp+8C0h+var_854], eax
0x18001339a  movups  [rsp+8C0h+var_864], xmm0
0x18001339f  lea     ecx, [rax+11h]; unsigned int
0x1800133a2  movups  [rsp+8C0h+var_888], xmm0
0x1800133a7  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x1800133ac  lea     r8, [rsp+8C0h+var_890]
0x1800133b1  mov     rdx, r14
0x1800133b4  mov     rcx, rax
0x1800133b7  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x1800133bc  mov     rbx, [rsp+8C0h+var_890]
0x1800133c1  test    rbx, rbx
0x1800133c4  jnz     short loc_180013442
0x1800133c6  test    cs:byte_1800CF404, 10h
0x1800133cd  jz      short loc_180013438
0x1800133cf  mov     edx, r14d
0x1800133d2  mov     word ptr [rsp+8C0h+var_850], r13w
0x1800133d8  lea     rcx, [rsp+8C0h+var_878]
0x1800133dd  mov     word ptr [rsp+8C0h+var_878], r13w
0x1800133e3  call    ConvertPortNoToString
0x1800133e8  mov     r9, r14
0x1800133eb  lea     r8, aDdmportgetprot; "DdmPortGetProtocolCompression"
0x1800133f2  lea     rdx, aSPortLdNotFoun; "%s: Port %ld not found."
0x1800133f9  lea     rcx, [rsp+8C0h+var_850]
0x1800133fe  call    FormatRRASErrorString
0x180013403  test    cs:byte_1800CF404, 10h
0x18001340a  jz      short loc_180013438
0x18001340c  lea     rax, [rsp+8C0h+var_878]
0x180013411  mov     [rsp+8C0h+var_898], rax
0x180013416  lea     r9, [rsp+8C0h+var_888]
0x18001341b  lea     r8, [rsp+8C0h+var_850]
0x180013420  mov     [rsp+8C0h+var_8A0], r13
0x180013425  lea     rdx, RasDdmParamTraceInfo
0x18001342c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013433  call    McTemplateU0zjzz_EventWriteTransfer
0x180013438  mov     esi, 490h
0x18001343d  jmp     loc_180013506
0x180013442  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013446  call    cs:__imp_EnterCriticalSection
0x18001344d  nop     dword ptr [rax+rax+00h]
0x180013452  mov     rax, [rbx]
0x180013455  mov     r9, r12
0x180013458  mov     r8, r15
0x18001345b  mov     edx, esi
0x18001345d  mov     rcx, rbx
0x180013460  mov     rax, [rax+260h]
0x180013467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001346c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013470  mov     esi, eax
0x180013472  call    cs:__imp_LeaveCriticalSection
0x180013479  nop     dword ptr [rax+rax+00h]
0x18001347e  test    esi, esi
0x180013480  jz      loc_180013506
0x180013486  test    cs:byte_1800CF404, 8
0x18001348d  jz      short loc_180013506
0x18001348f  mov     word ptr [rsp+8C0h+var_850], r13w
0x180013495  mov     word ptr [rsp+8C0h+var_878], r13w
0x18001349b  test    rbx, rbx
0x18001349e  jz      short loc_1800134A5
0x1800134a0  mov     edx, [rbx+60h]
0x1800134a3  jmp     short loc_1800134A8
0x1800134a5  or      edx, 0FFFFFFFFh
0x1800134a8  lea     rcx, [rsp+8C0h+var_878]
0x1800134ad  call    ConvertPortNoToString
0x1800134b2  mov     r9, r14
0x1800134b5  mov     dword ptr [rsp+8C0h+var_8A0], esi
0x1800134b9  lea     r8, aDdmportgetprot; "DdmPortGetProtocolCompression"
0x1800134c0  lea     rdx, aSDeviceobjGetp; "%s: deviceObj->GetProtocolCompression f"...
0x1800134c7  lea     rcx, [rsp+8C0h+var_850]
0x1800134cc  call    FormatRRASErrorString
0x1800134d1  test    cs:byte_1800CF404, 8
0x1800134d8  jz      short loc_180013506
0x1800134da  lea     rax, [rsp+8C0h+var_878]
0x1800134df  mov     [rsp+8C0h+var_898], rax
0x1800134e4  lea     r9, [rsp+8C0h+var_888]
0x1800134e9  lea     r8, [rsp+8C0h+var_850]
0x1800134ee  mov     [rsp+8C0h+var_8A0], r13
0x1800134f3  lea     rdx, RasDdmParamTraceError
0x1800134fa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013501  call    McTemplateU0zjzz_EventWriteTransfer
0x180013506  test    rbx, rbx
0x180013509  jz      short loc_18001352D
0x18001350b  or      eax, 0FFFFFFFFh
0x18001350e  lock xadd [rbx+8], eax
0x180013513  cmp     eax, 1
0x180013516  jnz     short loc_18001352D
0x180013518  mov     rcx, [rsp+8C0h+var_890]
0x18001351d  mov     edx, 1
0x180013522  mov     rax, [rcx]
0x180013525  mov     rax, [rax]
0x180013528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001352d  mov     eax, esi
0x18001352f  mov     rcx, [rbp+7C0h+var_50]
0x180013536  xor     rcx, rsp; StackCookie
0x180013539  call    __security_check_cookie
0x18001353e  add     rsp, 888h
0x180013545  pop     r15
0x180013547  pop     r14
0x180013549  pop     r13
0x18001354b  pop     r12
0x18001354d  pop     rdi
0x18001354e  pop     rsi
0x18001354f  pop     rbx
0x180013550  pop     rbp
0x180013551  retn
```
