# DdmCompressionGetInfo

- ea: `0x180010990`
- end: `0x180010bab`
- name: `DdmCompressionGetInfo`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x180010990`
- `0x18003d100`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180010acc`
- `KERNEL32!LeaveCriticalSection` at `0x180010acc`
- `KERNEL32!EnterCriticalSection` at `0x180010aa2`
- `KERNEL32!EnterCriticalSection` at `0x180010aa2`

## string_xrefs

- `0x180010a47`: `DdmCompressionGetInfo`
- `0x180010b13`: `DdmCompressionGetInfo`
- `0x180010b1a`: `%s: deviceObj->CompressionGetInfo failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmCompressionGetInfo(__int64 a1, __int64 a2, __int64 a3)
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
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v7 + 600LL))(v7, a2, a3);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
    if ( v8 && (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v17) = 0;
      LOWORD(v13) = 0;
      v9 = v7 ? *(unsigned int *)(v7 + 96) : 0xFFFFFFFFLL;
      ConvertPortNoToString(&v13, v9);
      FormatRRASErrorString(
        &v17,
        L"%s: deviceObj->CompressionGetInfo failed for port (%ld):%d.",
        L"DdmCompressionGetInfo",
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
      FormatRRASErrorString(&v17, L"%s: Port %ld not found.", L"DdmCompressionGetInfo", a1);
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
0x180010990  push    rbp
0x180010992  push    rbx
0x180010993  push    rsi
0x180010994  push    rdi
0x180010995  push    r12
0x180010997  push    r14
0x180010999  push    r15
0x18001099b  lea     rbp, [rsp-780h]
0x1800109a3  sub     rsp, 880h
0x1800109aa  mov     rax, cs:__security_cookie
0x1800109b1  xor     rax, rsp
0x1800109b4  mov     [rbp+7B0h+var_40], rax
0x1800109bb  mov     r15, r8
0x1800109be  mov     rsi, rdx
0x1800109c1  mov     r14, rcx
0x1800109c4  xor     r12d, r12d
0x1800109c7  xor     edx, edx; Val
0x1800109c9  mov     [rsp+8B0h+var_880], r12
0x1800109ce  mov     r8d, 7FCh; Size
0x1800109d4  mov     [rsp+8B0h+var_840], r12d
0x1800109d9  lea     rcx, [rsp+8B0h+var_83C]; void *
0x1800109de  call    memset_0
0x1800109e3  xorps   xmm0, xmm0
0x1800109e6  mov     [rsp+8B0h+var_868], r12d
0x1800109eb  xor     eax, eax
0x1800109ed  movups  [rsp+8B0h+var_864], xmm0
0x1800109f2  mov     [rsp+8B0h+var_844], eax
0x1800109f6  movups  [rsp+8B0h+var_854], xmm0
0x1800109fb  lea     ecx, [rax+11h]; unsigned int
0x1800109fe  movups  [rsp+8B0h+var_878], xmm0
0x180010a03  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180010a08  lea     r8, [rsp+8B0h+var_880]
0x180010a0d  mov     rdx, r14
0x180010a10  mov     rcx, rax
0x180010a13  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180010a18  mov     rbx, [rsp+8B0h+var_880]
0x180010a1d  test    rbx, rbx
0x180010a20  jnz     short loc_180010A9E
0x180010a22  test    cs:byte_1800CF404, 10h
0x180010a29  jz      short loc_180010A94
0x180010a2b  mov     edx, r14d
0x180010a2e  mov     word ptr [rsp+8B0h+var_840], r12w
0x180010a34  lea     rcx, [rsp+8B0h+var_868]
0x180010a39  mov     word ptr [rsp+8B0h+var_868], r12w
0x180010a3f  call    ConvertPortNoToString
0x180010a44  mov     r9, r14
0x180010a47  lea     r8, aDdmcompression; "DdmCompressionGetInfo"
0x180010a4e  lea     rdx, aSPortLdNotFoun; "%s: Port %ld not found."
0x180010a55  lea     rcx, [rsp+8B0h+var_840]
0x180010a5a  call    FormatRRASErrorString
0x180010a5f  test    cs:byte_1800CF404, 10h
0x180010a66  jz      short loc_180010A94
0x180010a68  lea     rax, [rsp+8B0h+var_868]
0x180010a6d  mov     [rsp+8B0h+var_888], rax
0x180010a72  lea     r9, [rsp+8B0h+var_878]
0x180010a77  lea     r8, [rsp+8B0h+var_840]
0x180010a7c  mov     [rsp+8B0h+var_890], r12
0x180010a81  lea     rdx, RasDdmParamTraceInfo
0x180010a88  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010a8f  call    McTemplateU0zjzz_EventWriteTransfer
0x180010a94  mov     esi, 490h
0x180010a99  jmp     loc_180010B60
0x180010a9e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180010aa2  call    cs:__imp_EnterCriticalSection
0x180010aa9  nop     dword ptr [rax+rax+00h]
0x180010aae  mov     rax, [rbx]
0x180010ab1  mov     r8, r15
0x180010ab4  mov     rdx, rsi
0x180010ab7  mov     rcx, rbx
0x180010aba  mov     rax, [rax+258h]
0x180010ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac6  lea     rcx, [rbx+10h]; lpCriticalSection
0x180010aca  mov     esi, eax
0x180010acc  call    cs:__imp_LeaveCriticalSection
0x180010ad3  nop     dword ptr [rax+rax+00h]
0x180010ad8  test    esi, esi
0x180010ada  jz      loc_180010B60
0x180010ae0  test    cs:byte_1800CF404, 8
0x180010ae7  jz      short loc_180010B60
0x180010ae9  mov     word ptr [rsp+8B0h+var_840], r12w
0x180010aef  mov     word ptr [rsp+8B0h+var_868], r12w
0x180010af5  test    rbx, rbx
0x180010af8  jz      short loc_180010AFF
0x180010afa  mov     edx, [rbx+60h]
0x180010afd  jmp     short loc_180010B02
0x180010aff  or      edx, 0FFFFFFFFh
0x180010b02  lea     rcx, [rsp+8B0h+var_868]
0x180010b07  call    ConvertPortNoToString
0x180010b0c  mov     r9, r14
0x180010b0f  mov     dword ptr [rsp+8B0h+var_890], esi
0x180010b13  lea     r8, aDdmcompression; "DdmCompressionGetInfo"
0x180010b1a  lea     rdx, aSDeviceobjComp; "%s: deviceObj->CompressionGetInfo faile"...
0x180010b21  lea     rcx, [rsp+8B0h+var_840]
0x180010b26  call    FormatRRASErrorString
0x180010b2b  test    cs:byte_1800CF404, 8
0x180010b32  jz      short loc_180010B60
0x180010b34  lea     rax, [rsp+8B0h+var_868]
0x180010b39  mov     [rsp+8B0h+var_888], rax
0x180010b3e  lea     r9, [rsp+8B0h+var_878]
0x180010b43  lea     r8, [rsp+8B0h+var_840]
0x180010b48  mov     [rsp+8B0h+var_890], r12
0x180010b4d  lea     rdx, RasDdmParamTraceError
0x180010b54  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010b5b  call    McTemplateU0zjzz_EventWriteTransfer
0x180010b60  test    rbx, rbx
0x180010b63  jz      short loc_180010B87
0x180010b65  or      eax, 0FFFFFFFFh
0x180010b68  lock xadd [rbx+8], eax
0x180010b6d  cmp     eax, 1
0x180010b70  jnz     short loc_180010B87
0x180010b72  mov     rcx, [rsp+8B0h+var_880]
0x180010b77  mov     edx, 1
0x180010b7c  mov     rax, [rcx]
0x180010b7f  mov     rax, [rax]
0x180010b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b87  mov     eax, esi
0x180010b89  mov     rcx, [rbp+7B0h+var_40]
0x180010b90  xor     rcx, rsp; StackCookie
0x180010b93  call    __security_check_cookie
0x180010b98  add     rsp, 880h
0x180010b9f  pop     r15
0x180010ba1  pop     r14
0x180010ba3  pop     r12
0x180010ba5  pop     rdi
0x180010ba6  pop     rsi
0x180010ba7  pop     rbx
0x180010ba8  pop     rbp
0x180010ba9  retn
```
