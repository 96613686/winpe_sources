# DdmPortSetProtocolCompression

- ea: `0x180013bd0`
- end: `0x180013df3`
- name: `DdmPortSetProtocolCompression`
- size: `547`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x180013bd0`
- `0x18003d100`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180013d12`
- `KERNEL32!LeaveCriticalSection` at `0x180013d12`
- `KERNEL32!EnterCriticalSection` at `0x180013ce6`
- `KERNEL32!EnterCriticalSection` at `0x180013ce6`

## string_xrefs

- `0x180013c8b`: `DdmPortSetProtocolCompression`
- `0x180013d59`: `DdmPortSetProtocolCompression`
- `0x180013d60`: `%s: deviceObj->SetProtocolCompression failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmPortSetProtocolCompression(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
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
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v9 + 616LL))(v9, a2, a3, a4);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
    if ( v10 && (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v19) = 0;
      LOWORD(v15) = 0;
      v11 = v9 ? *(unsigned int *)(v9 + 96) : 0xFFFFFFFFLL;
      ConvertPortNoToString(&v15, v11);
      FormatRRASErrorString(
        &v19,
        L"%s: deviceObj->SetProtocolCompression failed for port (%ld):%d.",
        L"DdmPortSetProtocolCompression",
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
      FormatRRASErrorString(&v19, L"%s: Port %ld not found.", L"DdmPortSetProtocolCompression", a1);
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
0x180013bd0  push    rbp
0x180013bd2  push    rbx
0x180013bd3  push    rsi
0x180013bd4  push    rdi
0x180013bd5  push    r12
0x180013bd7  push    r13
0x180013bd9  push    r14
0x180013bdb  push    r15
0x180013bdd  lea     rbp, [rsp-788h]
0x180013be5  sub     rsp, 888h
0x180013bec  mov     rax, cs:__security_cookie
0x180013bf3  xor     rax, rsp
0x180013bf6  mov     [rbp+7C0h+var_50], rax
0x180013bfd  mov     r15, r8
0x180013c00  mov     esi, edx
0x180013c02  mov     r14, rcx
0x180013c05  xor     r13d, r13d
0x180013c08  xor     edx, edx; Val
0x180013c0a  mov     [rsp+8C0h+var_890], r13
0x180013c0f  mov     r8d, 7FCh; Size
0x180013c15  mov     [rsp+8C0h+var_850], r13d
0x180013c1a  lea     rcx, [rsp+8C0h+var_84C]; void *
0x180013c1f  mov     r12, r9
0x180013c22  call    memset_0
0x180013c27  xorps   xmm0, xmm0
0x180013c2a  mov     [rsp+8C0h+var_878], r13d
0x180013c2f  xor     eax, eax
0x180013c31  movups  [rsp+8C0h+var_874], xmm0
0x180013c36  mov     [rsp+8C0h+var_854], eax
0x180013c3a  movups  [rsp+8C0h+var_864], xmm0
0x180013c3f  lea     ecx, [rax+11h]; unsigned int
0x180013c42  movups  [rsp+8C0h+var_888], xmm0
0x180013c47  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180013c4c  lea     r8, [rsp+8C0h+var_890]
0x180013c51  mov     rdx, r14
0x180013c54  mov     rcx, rax
0x180013c57  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180013c5c  mov     rbx, [rsp+8C0h+var_890]
0x180013c61  test    rbx, rbx
0x180013c64  jnz     short loc_180013CE2
0x180013c66  test    cs:byte_1800CF404, 10h
0x180013c6d  jz      short loc_180013CD8
0x180013c6f  mov     edx, r14d
0x180013c72  mov     word ptr [rsp+8C0h+var_850], r13w
0x180013c78  lea     rcx, [rsp+8C0h+var_878]
0x180013c7d  mov     word ptr [rsp+8C0h+var_878], r13w
0x180013c83  call    ConvertPortNoToString
0x180013c88  mov     r9, r14
0x180013c8b  lea     r8, aDdmportsetprot; "DdmPortSetProtocolCompression"
0x180013c92  lea     rdx, aSPortLdNotFoun; "%s: Port %ld not found."
0x180013c99  lea     rcx, [rsp+8C0h+var_850]
0x180013c9e  call    FormatRRASErrorString
0x180013ca3  test    cs:byte_1800CF404, 10h
0x180013caa  jz      short loc_180013CD8
0x180013cac  lea     rax, [rsp+8C0h+var_878]
0x180013cb1  mov     [rsp+8C0h+var_898], rax
0x180013cb6  lea     r9, [rsp+8C0h+var_888]
0x180013cbb  lea     r8, [rsp+8C0h+var_850]
0x180013cc0  mov     [rsp+8C0h+var_8A0], r13
0x180013cc5  lea     rdx, RasDdmParamTraceInfo
0x180013ccc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013cd3  call    McTemplateU0zjzz_EventWriteTransfer
0x180013cd8  mov     esi, 490h
0x180013cdd  jmp     loc_180013DA6
0x180013ce2  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013ce6  call    cs:__imp_EnterCriticalSection
0x180013ced  nop     dword ptr [rax+rax+00h]
0x180013cf2  mov     rax, [rbx]
0x180013cf5  mov     r9, r12
0x180013cf8  mov     r8, r15
0x180013cfb  mov     edx, esi
0x180013cfd  mov     rcx, rbx
0x180013d00  mov     rax, [rax+268h]
0x180013d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d0c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013d10  mov     esi, eax
0x180013d12  call    cs:__imp_LeaveCriticalSection
0x180013d19  nop     dword ptr [rax+rax+00h]
0x180013d1e  test    esi, esi
0x180013d20  jz      loc_180013DA6
0x180013d26  test    cs:byte_1800CF404, 8
0x180013d2d  jz      short loc_180013DA6
0x180013d2f  mov     word ptr [rsp+8C0h+var_850], r13w
0x180013d35  mov     word ptr [rsp+8C0h+var_878], r13w
0x180013d3b  test    rbx, rbx
0x180013d3e  jz      short loc_180013D45
0x180013d40  mov     edx, [rbx+60h]
0x180013d43  jmp     short loc_180013D48
0x180013d45  or      edx, 0FFFFFFFFh
0x180013d48  lea     rcx, [rsp+8C0h+var_878]
0x180013d4d  call    ConvertPortNoToString
0x180013d52  mov     r9, r14
0x180013d55  mov     dword ptr [rsp+8C0h+var_8A0], esi
0x180013d59  lea     r8, aDdmportsetprot; "DdmPortSetProtocolCompression"
0x180013d60  lea     rdx, aSDeviceobjSetp; "%s: deviceObj->SetProtocolCompression f"...
0x180013d67  lea     rcx, [rsp+8C0h+var_850]
0x180013d6c  call    FormatRRASErrorString
0x180013d71  test    cs:byte_1800CF404, 8
0x180013d78  jz      short loc_180013DA6
0x180013d7a  lea     rax, [rsp+8C0h+var_878]
0x180013d7f  mov     [rsp+8C0h+var_898], rax
0x180013d84  lea     r9, [rsp+8C0h+var_888]
0x180013d89  lea     r8, [rsp+8C0h+var_850]
0x180013d8e  mov     [rsp+8C0h+var_8A0], r13
0x180013d93  lea     rdx, RasDdmParamTraceError
0x180013d9a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013da1  call    McTemplateU0zjzz_EventWriteTransfer
0x180013da6  test    rbx, rbx
0x180013da9  jz      short loc_180013DCD
0x180013dab  or      eax, 0FFFFFFFFh
0x180013dae  lock xadd [rbx+8], eax
0x180013db3  cmp     eax, 1
0x180013db6  jnz     short loc_180013DCD
0x180013db8  mov     rcx, [rsp+8C0h+var_890]
0x180013dbd  mov     edx, 1
0x180013dc2  mov     rax, [rcx]
0x180013dc5  mov     rax, [rax]
0x180013dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dcd  mov     eax, esi
0x180013dcf  mov     rcx, [rbp+7C0h+var_50]
0x180013dd6  xor     rcx, rsp; StackCookie
0x180013dd9  call    __security_check_cookie
0x180013dde  add     rsp, 888h
0x180013de5  pop     r15
0x180013de7  pop     r14
0x180013de9  pop     r13
0x180013deb  pop     r12
0x180013ded  pop     rdi
0x180013dee  pop     rsi
0x180013def  pop     rbx
0x180013df0  pop     rbp
0x180013df1  retn
```
