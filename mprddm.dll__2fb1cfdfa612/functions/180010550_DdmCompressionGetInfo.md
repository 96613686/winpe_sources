# DdmCompressionGetInfo

- ea: `0x180010550`
- end: `0x18001078d`
- name: `DdmCompressionGetInfo`
- size: `573`
- prototype: `__int64 __fastcall(int Value)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x180010550`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180010613`
- `msvcrt!_itow_s` at `0x1800106e2`
- `msvcrt!_itow_s` at `0x180010613`
- `msvcrt!_itow_s` at `0x1800106e2`
- `KERNEL32!LeaveCriticalSection` at `0x18001069f`
- `KERNEL32!LeaveCriticalSection` at `0x18001069f`
- `KERNEL32!EnterCriticalSection` at `0x18001067b`
- `KERNEL32!EnterCriticalSection` at `0x18001067b`

## string_xrefs

- `0x18001061c`: `DdmCompressionGetInfo`
- `0x1800106ef`: `DdmCompressionGetInfo`
- `0x1800106f6`: `%s: deviceObj->CompressionGetInfo failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmCompressionGetInfo(__int64 Value, __int64 a2, __int64 a3)
{
  struct DdmDeviceTable *Instance; // rax
  __int64 v7; // rbx
  unsigned int v8; // esi
  int v9; // ecx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v12; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v14; // [rsp+4Ch] [rbp-B4h]
  __int128 v15; // [rsp+5Ch] [rbp-A4h]
  int v16; // [rsp+6Ch] [rbp-94h]
  int v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v11 = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  *(_DWORD *)Buffer = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  v12 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, Value, &v11);
  v7 = v11;
  if ( v11 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v7 + 600LL))(v7, a2, a3);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
    if ( v8 && (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v17) = 0;
      Buffer[0] = 0;
      if ( v7 )
      {
        v9 = *(_DWORD *)(v7 + 96);
        if ( v9 != -1 )
          _itow_s(v9, Buffer, 0x14u, 10);
      }
      FormatRRASErrorString(
        &v17,
        L"%s: deviceObj->CompressionGetInfo failed for port (%ld):%d.",
        L"DdmCompressionGetInfo",
        Value,
        v8);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v17,
          (unsigned int)&v12,
          0,
          (__int64)Buffer);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF) == 1 && v7 )
      (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
  }
  else
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v17) = 0;
      Buffer[0] = 0;
      if ( (_DWORD)Value != -1 )
        _itow_s(Value, Buffer, (unsigned int)(v11 + 20), v11 + 10);
      FormatRRASErrorString(&v17, L"%s: Port %ld not found.", L"DdmCompressionGetInfo", Value);
      if ( (byte_1800C8404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v17,
          (unsigned int)&v12,
          0,
          (__int64)Buffer);
    }
    return 1168;
  }
  return v8;
}

```

## disassembly

```asm
0x180010550  mov     [rsp-8+arg_18], rbx
0x180010555  push    rbp
0x180010556  push    rsi
0x180010557  push    rdi
0x180010558  push    r14
0x18001055a  push    r15
0x18001055c  lea     rbp, [rsp-780h]
0x180010564  sub     rsp, 880h
0x18001056b  mov     rax, cs:__security_cookie
0x180010572  xor     rax, rsp
0x180010575  mov     [rbp+7A0h+var_30], rax
0x18001057c  mov     r15, r8
0x18001057f  mov     [rsp+8A0h+var_870], 0
0x180010588  mov     rsi, rdx
0x18001058b  mov     r14, rcx
0x18001058e  xor     eax, eax
0x180010590  lea     rcx, [rsp+8A0h+var_82C]; void *
0x180010595  xor     edx, edx; Val
0x180010597  mov     [rsp+8A0h+var_830], eax
0x18001059b  mov     r8d, 7FCh; Size
0x1800105a1  call    memset_0
0x1800105a6  xor     eax, eax
0x1800105a8  xorps   xmm0, xmm0
0x1800105ab  mov     dword ptr [rsp+8A0h+Buffer], eax
0x1800105af  movups  [rsp+8A0h+var_854], xmm0
0x1800105b4  mov     [rsp+8A0h+var_834], eax
0x1800105b8  lea     ecx, [rax+11h]; unsigned int
0x1800105bb  movups  [rsp+8A0h+var_844], xmm0
0x1800105c0  movups  [rsp+8A0h+var_868], xmm0
0x1800105c5  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x1800105ca  lea     r8, [rsp+8A0h+var_870]
0x1800105cf  mov     rdx, r14
0x1800105d2  mov     rcx, rax
0x1800105d5  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x1800105da  mov     rbx, [rsp+8A0h+var_870]
0x1800105df  test    rbx, rbx
0x1800105e2  jnz     loc_180010677
0x1800105e8  test    cs:byte_1800C8404, 10h
0x1800105ef  jz      short loc_18001066D
0x1800105f1  xor     eax, eax
0x1800105f3  mov     word ptr [rsp+8A0h+var_830], ax
0x1800105f8  mov     [rsp+8A0h+Buffer], ax
0x1800105fd  cmp     r14d, 0FFFFFFFFh
0x180010601  jz      short loc_180010619
0x180010603  lea     r9d, [rbx+0Ah]; Radix
0x180010607  mov     ecx, r14d; Value
0x18001060a  lea     r8d, [rbx+14h]; BufferCount
0x18001060e  lea     rdx, [rsp+8A0h+Buffer]; Buffer
0x180010613  call    cs:__imp__itow_s
0x180010619  mov     r9, r14
0x18001061c  lea     r8, aDdmcompression; "DdmCompressionGetInfo"
0x180010623  lea     rdx, aSPortLdNotFoun; "%s: Port %ld not found."
0x18001062a  lea     rcx, [rsp+8A0h+var_830]
0x18001062f  call    FormatRRASErrorString
0x180010634  test    cs:byte_1800C8404, 10h
0x18001063b  jz      short loc_18001066D
0x18001063d  lea     rax, [rsp+8A0h+Buffer]
0x180010642  mov     [rsp+8A0h+var_878], rax
0x180010647  lea     r9, [rsp+8A0h+var_868]
0x18001064c  lea     r8, [rsp+8A0h+var_830]
0x180010651  mov     [rsp+8A0h+var_880], 0
0x18001065a  lea     rdx, RasDdmParamTraceInfo
0x180010661  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010668  call    McTemplateU0zjzz_EventWriteTransfer
0x18001066d  mov     esi, 490h
0x180010672  jmp     loc_180010765
0x180010677  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001067b  call    cs:__imp_EnterCriticalSection
0x180010681  mov     rax, [rbx]
0x180010684  mov     r8, r15
0x180010687  mov     rdx, rsi
0x18001068a  mov     rcx, rbx
0x18001068d  mov     rax, [rax+258h]
0x180010694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010699  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001069d  mov     esi, eax
0x18001069f  call    cs:__imp_LeaveCriticalSection
0x1800106a5  test    esi, esi
0x1800106a7  jz      loc_180010740
0x1800106ad  test    cs:byte_1800C8404, 8
0x1800106b4  jz      loc_180010740
0x1800106ba  xor     ecx, ecx
0x1800106bc  mov     word ptr [rsp+8A0h+var_830], cx
0x1800106c1  mov     [rsp+8A0h+Buffer], cx
0x1800106c6  test    rbx, rbx
0x1800106c9  jz      short loc_1800106E8
0x1800106cb  mov     ecx, [rbx+60h]; Value
0x1800106ce  cmp     ecx, 0FFFFFFFFh
0x1800106d1  jz      short loc_1800106E8
0x1800106d3  mov     r9d, 0Ah; Radix
0x1800106d9  lea     rdx, [rsp+8A0h+Buffer]; Buffer
0x1800106de  lea     r8d, [r9+0Ah]; BufferCount
0x1800106e2  call    cs:__imp__itow_s
0x1800106e8  mov     r9, r14
0x1800106eb  mov     dword ptr [rsp+8A0h+var_880], esi
0x1800106ef  lea     r8, aDdmcompression; "DdmCompressionGetInfo"
0x1800106f6  lea     rdx, aSDeviceobjComp; "%s: deviceObj->CompressionGetInfo faile"...
0x1800106fd  lea     rcx, [rsp+8A0h+var_830]
0x180010702  call    FormatRRASErrorString
0x180010707  test    cs:byte_1800C8404, 8
0x18001070e  jz      short loc_180010740
0x180010710  lea     rax, [rsp+8A0h+Buffer]
0x180010715  mov     [rsp+8A0h+var_878], rax
0x18001071a  lea     r9, [rsp+8A0h+var_868]
0x18001071f  lea     r8, [rsp+8A0h+var_830]
0x180010724  mov     [rsp+8A0h+var_880], 0
0x18001072d  lea     rdx, RasDdmParamTraceError
0x180010734  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001073b  call    McTemplateU0zjzz_EventWriteTransfer
0x180010740  or      eax, 0FFFFFFFFh
0x180010743  lock xadd [rbx+8], eax
0x180010748  cmp     eax, 1
0x18001074b  jnz     short loc_180010765
0x18001074d  test    rbx, rbx
0x180010750  jz      short loc_180010765
0x180010752  mov     rax, [rbx]
0x180010755  mov     edx, 1
0x18001075a  mov     rcx, rbx
0x18001075d  mov     rax, [rax]
0x180010760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010765  mov     eax, esi
0x180010767  mov     rcx, [rbp+7A0h+var_30]
0x18001076e  xor     rcx, rsp; StackCookie
0x180010771  call    __security_check_cookie
0x180010776  mov     rbx, [rsp+8A0h+arg_18]
0x18001077e  add     rsp, 880h
0x180010785  pop     r15
0x180010787  pop     r14
0x180010789  pop     rdi
0x18001078a  pop     rsi
0x18001078b  pop     rbp
0x18001078c  retn
```
