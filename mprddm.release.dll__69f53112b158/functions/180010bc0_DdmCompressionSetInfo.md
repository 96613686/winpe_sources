# DdmCompressionSetInfo

- ea: `0x180010bc0`
- end: `0x180010ddb`
- name: `DdmCompressionSetInfo`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x180010bc0`
- `0x18003d100`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180010cfc`
- `KERNEL32!LeaveCriticalSection` at `0x180010cfc`
- `KERNEL32!EnterCriticalSection` at `0x180010cd2`
- `KERNEL32!EnterCriticalSection` at `0x180010cd2`

## string_xrefs

- `0x180010c77`: `DdmCompressionSetInfo`
- `0x180010d43`: `DdmCompressionSetInfo`
- `0x180010d4a`: `%s: deviceObj->CompressionSetInfo failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmCompressionSetInfo(__int64 a1, __int64 a2, __int64 a3)
{
  struct DdmDeviceTable *Instance; // rax
  __int64 v7; // rbx
  unsigned int v8; // esi
  __int64 v9; // rdx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v12; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v14; // [rsp+4Ch] [rbp-B4h]
  __int128 v15; // [rsp+5Ch] [rbp-A4h]
  int v16; // [rsp+6Ch] [rbp-94h]
  int v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v11 = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v13 = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  v12 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, a1, &v11);
  v7 = v11;
  if ( v11 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v7 + 592LL))(v7, a2, a3);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
    if ( v8 && (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v17) = 0;
      LOWORD(v13) = 0;
      v9 = v7 ? *(unsigned int *)(v7 + 96) : 0xFFFFFFFFLL;
      ConvertPortNoToString(&v13, v9);
      FormatRRASErrorString(
        &v17,
        L"%s: deviceObj->CompressionSetInfo failed for port (%ld):%d.",
        L"DdmCompressionSetInfo",
        a1,
        v8);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v17,
          (unsigned int)&v12,
          0,
          (__int64)&v13);
    }
  }
  else
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v17) = 0;
      LOWORD(v13) = 0;
      ConvertPortNoToString(&v13, (unsigned int)a1);
      FormatRRASErrorString(&v17, L"%s: Port %ld not found.", L"DdmCompressionSetInfo", a1);
      if ( (byte_1800CF404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v17,
          (unsigned int)&v12,
          0,
          (__int64)&v13);
    }
    v8 = 1168;
  }
  if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
  return v8;
}

```

## disassembly

```asm
0x180010bc0  push    rbp
0x180010bc2  push    rbx
0x180010bc3  push    rsi
0x180010bc4  push    rdi
0x180010bc5  push    r12
0x180010bc7  push    r14
0x180010bc9  push    r15
0x180010bcb  lea     rbp, [rsp-780h]
0x180010bd3  sub     rsp, 880h
0x180010bda  mov     rax, cs:__security_cookie
0x180010be1  xor     rax, rsp
0x180010be4  mov     [rbp+7B0h+var_40], rax
0x180010beb  mov     r15, r8
0x180010bee  mov     rsi, rdx
0x180010bf1  mov     r14, rcx
0x180010bf4  xor     r12d, r12d
0x180010bf7  xor     edx, edx; Val
0x180010bf9  mov     [rsp+8B0h+var_880], r12
0x180010bfe  mov     r8d, 7FCh; Size
0x180010c04  mov     [rsp+8B0h+var_840], r12d
0x180010c09  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180010c0e  call    memset_0
0x180010c13  xorps   xmm0, xmm0
0x180010c16  mov     [rsp+8B0h+var_868], r12d
0x180010c1b  xor     eax, eax
0x180010c1d  movups  [rsp+8B0h+var_864], xmm0
0x180010c22  mov     [rsp+8B0h+var_844], eax
0x180010c26  movups  [rsp+8B0h+var_854], xmm0
0x180010c2b  lea     ecx, [rax+11h]; unsigned int
0x180010c2e  movups  [rsp+8B0h+var_878], xmm0
0x180010c33  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180010c38  lea     r8, [rsp+8B0h+var_880]
0x180010c3d  mov     rdx, r14
0x180010c40  mov     rcx, rax
0x180010c43  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180010c48  mov     rbx, [rsp+8B0h+var_880]
0x180010c4d  test    rbx, rbx
0x180010c50  jnz     short loc_180010CCE
0x180010c52  test    cs:byte_1800CF404, 10h
0x180010c59  jz      short loc_180010CC4
0x180010c5b  mov     edx, r14d
0x180010c5e  mov     word ptr [rsp+8B0h+var_840], r12w
0x180010c64  lea     rcx, [rsp+8B0h+var_868]
0x180010c69  mov     word ptr [rsp+8B0h+var_868], r12w
0x180010c6f  call    ConvertPortNoToString
0x180010c74  mov     r9, r14
0x180010c77  lea     r8, aDdmcompression_0; "DdmCompressionSetInfo"
0x180010c7e  lea     rdx, aSPortLdNotFoun; "%s: Port %ld not found."
0x180010c85  lea     rcx, [rsp+8B0h+var_840]
0x180010c8a  call    FormatRRASErrorString
0x180010c8f  test    cs:byte_1800CF404, 10h
0x180010c96  jz      short loc_180010CC4
0x180010c98  lea     rax, [rsp+8B0h+var_868]
0x180010c9d  mov     [rsp+8B0h+var_888], rax
0x180010ca2  lea     r9, [rsp+8B0h+var_878]
0x180010ca7  lea     r8, [rsp+8B0h+var_840]
0x180010cac  mov     [rsp+8B0h+var_890], r12
0x180010cb1  lea     rdx, RasDdmParamTraceInfo
0x180010cb8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010cbf  call    McTemplateU0zjzz_EventWriteTransfer
0x180010cc4  mov     esi, 490h
0x180010cc9  jmp     loc_180010D90
0x180010cce  lea     rcx, [rbx+10h]; lpCriticalSection
0x180010cd2  call    cs:__imp_EnterCriticalSection
0x180010cd9  nop     dword ptr [rax+rax+00h]
0x180010cde  mov     rax, [rbx]
0x180010ce1  mov     r8, r15
0x180010ce4  mov     rdx, rsi
0x180010ce7  mov     rcx, rbx
0x180010cea  mov     rax, [rax+250h]
0x180010cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cf6  lea     rcx, [rbx+10h]; lpCriticalSection
0x180010cfa  mov     esi, eax
0x180010cfc  call    cs:__imp_LeaveCriticalSection
0x180010d03  nop     dword ptr [rax+rax+00h]
0x180010d08  test    esi, esi
0x180010d0a  jz      loc_180010D90
0x180010d10  test    cs:byte_1800CF404, 8
0x180010d17  jz      short loc_180010D90
0x180010d19  mov     word ptr [rsp+8B0h+var_840], r12w
0x180010d1f  mov     word ptr [rsp+8B0h+var_868], r12w
0x180010d25  test    rbx, rbx
0x180010d28  jz      short loc_180010D2F
0x180010d2a  mov     edx, [rbx+60h]
0x180010d2d  jmp     short loc_180010D32
0x180010d2f  or      edx, 0FFFFFFFFh
0x180010d32  lea     rcx, [rsp+8B0h+var_868]
0x180010d37  call    ConvertPortNoToString
0x180010d3c  mov     r9, r14
0x180010d3f  mov     dword ptr [rsp+8B0h+var_890], esi
0x180010d43  lea     r8, aDdmcompression_0; "DdmCompressionSetInfo"
0x180010d4a  lea     rdx, aSDeviceobjComp_0; "%s: deviceObj->CompressionSetInfo faile"...
0x180010d51  lea     rcx, [rsp+8B0h+var_840]
0x180010d56  call    FormatRRASErrorString
0x180010d5b  test    cs:byte_1800CF404, 8
0x180010d62  jz      short loc_180010D90
0x180010d64  lea     rax, [rsp+8B0h+var_868]
0x180010d69  mov     [rsp+8B0h+var_888], rax
0x180010d6e  lea     r9, [rsp+8B0h+var_878]
0x180010d73  lea     r8, [rsp+8B0h+var_840]
0x180010d78  mov     [rsp+8B0h+var_890], r12
0x180010d7d  lea     rdx, RasDdmParamTraceError
0x180010d84  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010d8b  call    McTemplateU0zjzz_EventWriteTransfer
0x180010d90  test    rbx, rbx
0x180010d93  jz      short loc_180010DB7
0x180010d95  or      eax, 0FFFFFFFFh
0x180010d98  lock xadd [rbx+8], eax
0x180010d9d  cmp     eax, 1
0x180010da0  jnz     short loc_180010DB7
0x180010da2  mov     rcx, [rsp+8B0h+var_880]
0x180010da7  mov     edx, 1
0x180010dac  mov     rax, [rcx]
0x180010daf  mov     rax, [rax]
0x180010db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010db7  mov     eax, esi
0x180010db9  mov     rcx, [rbp+7B0h+var_40]
0x180010dc0  xor     rcx, rsp; StackCookie
0x180010dc3  call    __security_check_cookie
0x180010dc8  add     rsp, 880h
0x180010dcf  pop     r15
0x180010dd1  pop     r14
0x180010dd3  pop     r12
0x180010dd5  pop     rdi
0x180010dd6  pop     rsi
0x180010dd7  pop     rbx
0x180010dd8  pop     rbp
0x180010dd9  retn
```
