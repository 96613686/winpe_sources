# DdmCompressionSetInfo

- ea: `0x1800107a0`
- end: `0x1800109dd`
- name: `DdmCompressionSetInfo`
- size: `573`
- prototype: `__int64 __fastcall(int Value)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x1800107a0`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180010863`
- `msvcrt!_itow_s` at `0x180010932`
- `msvcrt!_itow_s` at `0x180010863`
- `msvcrt!_itow_s` at `0x180010932`
- `KERNEL32!LeaveCriticalSection` at `0x1800108ef`
- `KERNEL32!LeaveCriticalSection` at `0x1800108ef`
- `KERNEL32!EnterCriticalSection` at `0x1800108cb`
- `KERNEL32!EnterCriticalSection` at `0x1800108cb`

## string_xrefs

- `0x18001086c`: `DdmCompressionSetInfo`
- `0x18001093f`: `DdmCompressionSetInfo`
- `0x180010946`: `%s: deviceObj->CompressionSetInfo failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmCompressionSetInfo(__int64 Value, __int64 a2, __int64 a3)
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
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v7 + 592LL))(v7, a2, a3);
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
        L"%s: deviceObj->CompressionSetInfo failed for port (%ld):%d.",
        L"DdmCompressionSetInfo",
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
      FormatRRASErrorString(&v17, L"%s: Port %ld not found.", L"DdmCompressionSetInfo", Value);
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
0x1800107a0  mov     [rsp-8+arg_18], rbx
0x1800107a5  push    rbp
0x1800107a6  push    rsi
0x1800107a7  push    rdi
0x1800107a8  push    r14
0x1800107aa  push    r15
0x1800107ac  lea     rbp, [rsp-780h]
0x1800107b4  sub     rsp, 880h
0x1800107bb  mov     rax, cs:__security_cookie
0x1800107c2  xor     rax, rsp
0x1800107c5  mov     [rbp+7A0h+var_30], rax
0x1800107cc  mov     r15, r8
0x1800107cf  mov     [rsp+8A0h+var_870], 0
0x1800107d8  mov     rsi, rdx
0x1800107db  mov     r14, rcx
0x1800107de  xor     eax, eax
0x1800107e0  lea     rcx, [rsp+8A0h+var_82C]; void *
0x1800107e5  xor     edx, edx; Val
0x1800107e7  mov     [rsp+8A0h+var_830], eax
0x1800107eb  mov     r8d, 7FCh; Size
0x1800107f1  call    memset_0
0x1800107f6  xor     eax, eax
0x1800107f8  xorps   xmm0, xmm0
0x1800107fb  mov     dword ptr [rsp+8A0h+Buffer], eax
0x1800107ff  movups  [rsp+8A0h+var_854], xmm0
0x180010804  mov     [rsp+8A0h+var_834], eax
0x180010808  lea     ecx, [rax+11h]; unsigned int
0x18001080b  movups  [rsp+8A0h+var_844], xmm0
0x180010810  movups  [rsp+8A0h+var_868], xmm0
0x180010815  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001081a  lea     r8, [rsp+8A0h+var_870]
0x18001081f  mov     rdx, r14
0x180010822  mov     rcx, rax
0x180010825  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18001082a  mov     rbx, [rsp+8A0h+var_870]
0x18001082f  test    rbx, rbx
0x180010832  jnz     loc_1800108C7
0x180010838  test    cs:byte_1800C8404, 10h
0x18001083f  jz      short loc_1800108BD
0x180010841  xor     eax, eax
0x180010843  mov     word ptr [rsp+8A0h+var_830], ax
0x180010848  mov     [rsp+8A0h+Buffer], ax
0x18001084d  cmp     r14d, 0FFFFFFFFh
0x180010851  jz      short loc_180010869
0x180010853  lea     r9d, [rbx+0Ah]; Radix
0x180010857  mov     ecx, r14d; Value
0x18001085a  lea     r8d, [rbx+14h]; BufferCount
0x18001085e  lea     rdx, [rsp+8A0h+Buffer]; Buffer
0x180010863  call    cs:__imp__itow_s
0x180010869  mov     r9, r14
0x18001086c  lea     r8, aDdmcompression_0; "DdmCompressionSetInfo"
0x180010873  lea     rdx, aSPortLdNotFoun; "%s: Port %ld not found."
0x18001087a  lea     rcx, [rsp+8A0h+var_830]
0x18001087f  call    FormatRRASErrorString
0x180010884  test    cs:byte_1800C8404, 10h
0x18001088b  jz      short loc_1800108BD
0x18001088d  lea     rax, [rsp+8A0h+Buffer]
0x180010892  mov     [rsp+8A0h+var_878], rax
0x180010897  lea     r9, [rsp+8A0h+var_868]
0x18001089c  lea     r8, [rsp+8A0h+var_830]
0x1800108a1  mov     [rsp+8A0h+var_880], 0
0x1800108aa  lea     rdx, RasDdmParamTraceInfo
0x1800108b1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800108b8  call    McTemplateU0zjzz_EventWriteTransfer
0x1800108bd  mov     esi, 490h
0x1800108c2  jmp     loc_1800109B5
0x1800108c7  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800108cb  call    cs:__imp_EnterCriticalSection
0x1800108d1  mov     rax, [rbx]
0x1800108d4  mov     r8, r15
0x1800108d7  mov     rdx, rsi
0x1800108da  mov     rcx, rbx
0x1800108dd  mov     rax, [rax+250h]
0x1800108e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108e9  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800108ed  mov     esi, eax
0x1800108ef  call    cs:__imp_LeaveCriticalSection
0x1800108f5  test    esi, esi
0x1800108f7  jz      loc_180010990
0x1800108fd  test    cs:byte_1800C8404, 8
0x180010904  jz      loc_180010990
0x18001090a  xor     ecx, ecx
0x18001090c  mov     word ptr [rsp+8A0h+var_830], cx
0x180010911  mov     [rsp+8A0h+Buffer], cx
0x180010916  test    rbx, rbx
0x180010919  jz      short loc_180010938
0x18001091b  mov     ecx, [rbx+60h]; Value
0x18001091e  cmp     ecx, 0FFFFFFFFh
0x180010921  jz      short loc_180010938
0x180010923  mov     r9d, 0Ah; Radix
0x180010929  lea     rdx, [rsp+8A0h+Buffer]; Buffer
0x18001092e  lea     r8d, [r9+0Ah]; BufferCount
0x180010932  call    cs:__imp__itow_s
0x180010938  mov     r9, r14
0x18001093b  mov     dword ptr [rsp+8A0h+var_880], esi
0x18001093f  lea     r8, aDdmcompression_0; "DdmCompressionSetInfo"
0x180010946  lea     rdx, aSDeviceobjComp_0; "%s: deviceObj->CompressionSetInfo faile"...
0x18001094d  lea     rcx, [rsp+8A0h+var_830]
0x180010952  call    FormatRRASErrorString
0x180010957  test    cs:byte_1800C8404, 8
0x18001095e  jz      short loc_180010990
0x180010960  lea     rax, [rsp+8A0h+Buffer]
0x180010965  mov     [rsp+8A0h+var_878], rax
0x18001096a  lea     r9, [rsp+8A0h+var_868]
0x18001096f  lea     r8, [rsp+8A0h+var_830]
0x180010974  mov     [rsp+8A0h+var_880], 0
0x18001097d  lea     rdx, RasDdmParamTraceError
0x180010984  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001098b  call    McTemplateU0zjzz_EventWriteTransfer
0x180010990  or      eax, 0FFFFFFFFh
0x180010993  lock xadd [rbx+8], eax
0x180010998  cmp     eax, 1
0x18001099b  jnz     short loc_1800109B5
0x18001099d  test    rbx, rbx
0x1800109a0  jz      short loc_1800109B5
0x1800109a2  mov     rax, [rbx]
0x1800109a5  mov     edx, 1
0x1800109aa  mov     rcx, rbx
0x1800109ad  mov     rax, [rax]
0x1800109b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109b5  mov     eax, esi
0x1800109b7  mov     rcx, [rbp+7A0h+var_30]
0x1800109be  xor     rcx, rsp; StackCookie
0x1800109c1  call    __security_check_cookie
0x1800109c6  mov     rbx, [rsp+8A0h+arg_18]
0x1800109ce  add     rsp, 880h
0x1800109d5  pop     r15
0x1800109d7  pop     r14
0x1800109d9  pop     rdi
0x1800109da  pop     rsi
0x1800109db  pop     rbp
0x1800109dc  retn
```
