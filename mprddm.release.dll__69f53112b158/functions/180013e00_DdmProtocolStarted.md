# DdmProtocolStarted

- ea: `0x180013e00`
- end: `0x18001400f`
- name: `DdmProtocolStarted`
- size: `527`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x180013e00`
- `0x18003d100`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180013f31`
- `KERNEL32!LeaveCriticalSection` at `0x180013f31`
- `KERNEL32!EnterCriticalSection` at `0x180013f0d`
- `KERNEL32!EnterCriticalSection` at `0x180013f0d`

## string_xrefs

- `0x180013eb9`: `DdmProtocolStarted: Port %ld not found.`
- `0x180013f70`: `DdmProtocolStarted: deviceObj->ProtocolStarted failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmProtocolStarted(__int64 a1)
{
  struct DdmDeviceTable *Instance; // rax
  __int64 v3; // rbx
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v7; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v8; // [rsp+40h] [rbp-C8h] BYREF
  _DWORD v9[10]; // [rsp+50h] [rbp-B8h] BYREF
  int v10; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v11[2044]; // [rsp+7Ch] [rbp-8Ch] BYREF

  v7 = 0;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  memset(v9, 0, sizeof(v9));
  v8 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, a1, &v7);
  v3 = v7;
  if ( v7 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 512LL))(v3);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
    if ( v4 && (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v10) = 0;
      LOWORD(v9[0]) = 0;
      v5 = v3 ? *(unsigned int *)(v3 + 96) : 0xFFFFFFFFLL;
      ConvertPortNoToString(v9, v5);
      FormatRRASErrorString(&v10, L"DdmProtocolStarted: deviceObj->ProtocolStarted failed for port (%ld):%d.", a1, v4);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v10,
          (unsigned int)&v8,
          0,
          (__int64)v9);
    }
  }
  else
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v10) = 0;
      LOWORD(v9[0]) = 0;
      ConvertPortNoToString(v9, (unsigned int)a1);
      FormatRRASErrorString(&v10, L"DdmProtocolStarted: Port %ld not found.", a1);
      if ( (byte_1800CF404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v10,
          (unsigned int)&v8,
          0,
          (__int64)v9);
    }
    v4 = 1168;
  }
  if ( v3 && _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
  return v4;
}

```

## disassembly

```asm
0x180013e00  mov     rax, rsp
0x180013e03  mov     [rax+10h], rbx
0x180013e07  mov     [rax+18h], rsi
0x180013e0b  mov     [rax+20h], rdi
0x180013e0f  push    rbp
0x180013e10  push    r14
0x180013e12  push    r15
0x180013e14  lea     rbp, [rax-798h]
0x180013e1b  sub     rsp, 880h
0x180013e22  mov     rax, cs:__security_cookie
0x180013e29  xor     rax, rsp
0x180013e2c  mov     [rbp+790h+var_20], rax
0x180013e33  mov     r14, rcx
0x180013e36  xor     r15d, r15d
0x180013e39  lea     rcx, [rsp+890h+var_81C]; void *
0x180013e3e  mov     qword ptr [rsp+890h+var_860], r15
0x180013e43  xor     edx, edx; Val
0x180013e45  mov     [rsp+890h+var_820], r15d
0x180013e4a  mov     r8d, 7FCh; Size
0x180013e50  call    memset_0
0x180013e55  xorps   xmm0, xmm0
0x180013e58  mov     dword ptr [rsp+890h+var_84C+4], r15d
0x180013e5d  xor     eax, eax
0x180013e5f  movups  [rsp+890h+var_84C+8], xmm0
0x180013e64  mov     [rsp+890h+var_824], eax
0x180013e68  movups  xmmword ptr [rsp+890h+var_83C+8], xmm0
0x180013e6d  lea     ecx, [rax+11h]; unsigned int
0x180013e70  movups  [rsp+890h+var_860+8], xmm0
0x180013e75  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180013e7a  lea     r8, [rsp+890h+var_860]
0x180013e7f  mov     rdx, r14
0x180013e82  mov     rcx, rax
0x180013e85  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180013e8a  mov     rbx, qword ptr [rsp+890h+var_860]
0x180013e8f  test    rbx, rbx
0x180013e92  jnz     short loc_180013F09
0x180013e94  test    cs:byte_1800CF404, 10h
0x180013e9b  jz      short loc_180013EFF
0x180013e9d  mov     edx, r14d
0x180013ea0  mov     word ptr [rsp+890h+var_820], r15w
0x180013ea6  lea     rcx, [rsp+890h+var_84C+4]
0x180013eab  mov     word ptr [rsp+890h+var_84C+4], r15w
0x180013eb1  call    ConvertPortNoToString
0x180013eb6  mov     r8, r14
0x180013eb9  lea     rdx, aDdmprotocolsta_0; "DdmProtocolStarted: Port %ld not found."
0x180013ec0  lea     rcx, [rsp+890h+var_820]
0x180013ec5  call    FormatRRASErrorString
0x180013eca  test    cs:byte_1800CF404, 10h
0x180013ed1  jz      short loc_180013EFF
0x180013ed3  lea     rax, [rsp+890h+var_84C+4]
0x180013ed8  mov     [rsp+890h+var_868], rax
0x180013edd  lea     r9, [rsp+890h+var_860+8]
0x180013ee2  lea     r8, [rsp+890h+var_820]
0x180013ee7  mov     [rsp+890h+var_870], r15
0x180013eec  lea     rdx, RasDdmParamTraceInfo
0x180013ef3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013efa  call    McTemplateU0zjzz_EventWriteTransfer
0x180013eff  mov     esi, 490h
0x180013f04  jmp     loc_180013FB9
0x180013f09  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013f0d  call    cs:__imp_EnterCriticalSection
0x180013f14  nop     dword ptr [rax+rax+00h]
0x180013f19  mov     rax, [rbx]
0x180013f1c  mov     rcx, rbx
0x180013f1f  mov     rax, [rax+200h]
0x180013f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f2b  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013f2f  mov     esi, eax
0x180013f31  call    cs:__imp_LeaveCriticalSection
0x180013f38  nop     dword ptr [rax+rax+00h]
0x180013f3d  test    esi, esi
0x180013f3f  jz      short loc_180013FB9
0x180013f41  test    cs:byte_1800CF404, 8
0x180013f48  jz      short loc_180013FB9
0x180013f4a  mov     word ptr [rsp+890h+var_820], r15w
0x180013f50  mov     word ptr [rsp+890h+var_84C+4], r15w
0x180013f56  test    rbx, rbx
0x180013f59  jz      short loc_180013F60
0x180013f5b  mov     edx, [rbx+60h]
0x180013f5e  jmp     short loc_180013F63
0x180013f60  or      edx, 0FFFFFFFFh
0x180013f63  lea     rcx, [rsp+890h+var_84C+4]
0x180013f68  call    ConvertPortNoToString
0x180013f6d  mov     r9d, esi
0x180013f70  lea     rdx, aDdmprotocolsta; "DdmProtocolStarted: deviceObj->Protocol"...
0x180013f77  mov     r8, r14
0x180013f7a  lea     rcx, [rsp+890h+var_820]
0x180013f7f  call    FormatRRASErrorString
0x180013f84  test    cs:byte_1800CF404, 8
0x180013f8b  jz      short loc_180013FB9
0x180013f8d  lea     rax, [rsp+890h+var_84C+4]
0x180013f92  mov     [rsp+890h+var_868], rax
0x180013f97  lea     r9, [rsp+890h+var_860+8]
0x180013f9c  lea     r8, [rsp+890h+var_820]
0x180013fa1  mov     [rsp+890h+var_870], r15
0x180013fa6  lea     rdx, RasDdmParamTraceError
0x180013fad  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013fb4  call    McTemplateU0zjzz_EventWriteTransfer
0x180013fb9  test    rbx, rbx
0x180013fbc  jz      short loc_180013FE0
0x180013fbe  or      eax, 0FFFFFFFFh
0x180013fc1  lock xadd [rbx+8], eax
0x180013fc6  cmp     eax, 1
0x180013fc9  jnz     short loc_180013FE0
0x180013fcb  mov     rcx, qword ptr [rsp+890h+var_860]
0x180013fd0  mov     edx, 1
0x180013fd5  mov     rax, [rcx]
0x180013fd8  mov     rax, [rax]
0x180013fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fe0  mov     eax, esi
0x180013fe2  mov     rcx, [rbp+790h+var_20]
0x180013fe9  xor     rcx, rsp; StackCookie
0x180013fec  call    __security_check_cookie
0x180013ff1  lea     r11, [rsp+890h+var_10]
0x180013ff9  mov     rbx, [r11+28h]
0x180013ffd  mov     rsi, [r11+30h]
0x180014001  mov     rdi, [r11+38h]
0x180014005  mov     rsp, r11
0x180014008  pop     r15
0x18001400a  pop     r14
0x18001400c  pop     rbp
0x18001400d  retn
```
