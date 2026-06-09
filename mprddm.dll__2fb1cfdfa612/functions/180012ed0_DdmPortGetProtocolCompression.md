# DdmPortGetProtocolCompression

- ea: `0x180012ed0`
- end: `0x18001310b`
- name: `DdmPortGetProtocolCompression`
- size: `571`
- prototype: `__int64 __fastcall(int Value)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x180012ed0`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180012f94`
- `msvcrt!_itow_s` at `0x180013065`
- `msvcrt!_itow_s` at `0x180012f94`
- `msvcrt!_itow_s` at `0x180013065`
- `KERNEL32!LeaveCriticalSection` at `0x180013022`
- `KERNEL32!LeaveCriticalSection` at `0x180013022`
- `KERNEL32!EnterCriticalSection` at `0x180012ffc`
- `KERNEL32!EnterCriticalSection` at `0x180012ffc`

## string_xrefs

- `0x180012f9d`: `DdmPortGetProtocolCompression`
- `0x180013072`: `DdmPortGetProtocolCompression`
- `0x180013079`: `%s: deviceObj->GetProtocolCompression failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmPortGetProtocolCompression(__int64 Value, unsigned int a2, __int64 a3, __int64 a4)
{
  struct DdmDeviceTable *Instance; // rax
  __int64 v9; // rbx
  unsigned int v10; // esi
  int v11; // ecx
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+4Ch] [rbp-B4h]
  __int128 v17; // [rsp+5Ch] [rbp-A4h]
  int v18; // [rsp+6Ch] [rbp-94h]
  int v19; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v13 = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  *(_DWORD *)Buffer = 0;
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v14 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, Value, &v13);
  v9 = v13;
  if ( v13 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 16));
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v9 + 608LL))(v9, a2, a3, a4);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
    if ( v10 && (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v19) = 0;
      Buffer[0] = 0;
      if ( v9 )
      {
        v11 = *(_DWORD *)(v9 + 96);
        if ( v11 != -1 )
          _itow_s(v11, Buffer, 0x14u, 10);
      }
      FormatRRASErrorString(
        &v19,
        L"%s: deviceObj->GetProtocolCompression failed for port (%ld):%d.",
        L"DdmPortGetProtocolCompression",
        Value,
        v10);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v19,
          (unsigned int)&v14,
          0,
          (__int64)Buffer);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 0xFFFFFFFF) == 1 && v9 )
      (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
  }
  else
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v19) = 0;
      Buffer[0] = 0;
      if ( (_DWORD)Value != -1 )
        _itow_s(Value, Buffer, (unsigned int)(v13 + 20), v13 + 10);
      FormatRRASErrorString(&v19, L"%s: Port %ld not found.", L"DdmPortGetProtocolCompression", Value);
      if ( (byte_1800C8404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v19,
          (unsigned int)&v14,
          0,
          (__int64)Buffer);
    }
    return 1168;
  }
  return v10;
}

```

## disassembly

```asm
0x180012ed0  push    rbp
0x180012ed2  push    rbx
0x180012ed3  push    rsi
0x180012ed4  push    rdi
0x180012ed5  push    r12
0x180012ed7  push    r14
0x180012ed9  push    r15
0x180012edb  lea     rbp, [rsp-780h]
0x180012ee3  sub     rsp, 880h
0x180012eea  mov     rax, cs:__security_cookie
0x180012ef1  xor     rax, rsp
0x180012ef4  mov     [rbp+7B0h+var_40], rax
0x180012efb  mov     r15, r8
0x180012efe  mov     [rsp+8B0h+var_880], 0
0x180012f07  mov     esi, edx
0x180012f09  mov     r14, rcx
0x180012f0c  xor     eax, eax
0x180012f0e  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180012f13  xor     edx, edx; Val
0x180012f15  mov     [rsp+8B0h+var_840], eax
0x180012f19  mov     r8d, 7FCh; Size
0x180012f1f  mov     r12, r9
0x180012f22  call    memset_0
0x180012f27  xor     eax, eax
0x180012f29  xorps   xmm0, xmm0
0x180012f2c  mov     dword ptr [rsp+8B0h+Buffer], eax
0x180012f30  movups  [rsp+8B0h+var_864], xmm0
0x180012f35  mov     [rsp+8B0h+var_844], eax
0x180012f39  lea     ecx, [rax+11h]; unsigned int
0x180012f3c  movups  [rsp+8B0h+var_854], xmm0
0x180012f41  movups  [rsp+8B0h+var_878], xmm0
0x180012f46  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180012f4b  lea     r8, [rsp+8B0h+var_880]
0x180012f50  mov     rdx, r14
0x180012f53  mov     rcx, rax
0x180012f56  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180012f5b  mov     rbx, [rsp+8B0h+var_880]
0x180012f60  test    rbx, rbx
0x180012f63  jnz     loc_180012FF8
0x180012f69  test    cs:byte_1800C8404, 10h
0x180012f70  jz      short loc_180012FEE
0x180012f72  xor     eax, eax
0x180012f74  mov     word ptr [rsp+8B0h+var_840], ax
0x180012f79  mov     [rsp+8B0h+Buffer], ax
0x180012f7e  cmp     r14d, 0FFFFFFFFh
0x180012f82  jz      short loc_180012F9A
0x180012f84  lea     r9d, [rbx+0Ah]; Radix
0x180012f88  mov     ecx, r14d; Value
0x180012f8b  lea     r8d, [rbx+14h]; BufferCount
0x180012f8f  lea     rdx, [rsp+8B0h+Buffer]; Buffer
0x180012f94  call    cs:__imp__itow_s
0x180012f9a  mov     r9, r14
0x180012f9d  lea     r8, aDdmportgetprot; "DdmPortGetProtocolCompression"
0x180012fa4  lea     rdx, aSPortLdNotFoun; "%s: Port %ld not found."
0x180012fab  lea     rcx, [rsp+8B0h+var_840]
0x180012fb0  call    FormatRRASErrorString
0x180012fb5  test    cs:byte_1800C8404, 10h
0x180012fbc  jz      short loc_180012FEE
0x180012fbe  lea     rax, [rsp+8B0h+Buffer]
0x180012fc3  mov     [rsp+8B0h+var_888], rax
0x180012fc8  lea     r9, [rsp+8B0h+var_878]
0x180012fcd  lea     r8, [rsp+8B0h+var_840]
0x180012fd2  mov     [rsp+8B0h+var_890], 0
0x180012fdb  lea     rdx, RasDdmParamTraceInfo
0x180012fe2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180012fe9  call    McTemplateU0zjzz_EventWriteTransfer
0x180012fee  mov     esi, 490h
0x180012ff3  jmp     loc_1800130E8
0x180012ff8  lea     rcx, [rbx+10h]; lpCriticalSection
0x180012ffc  call    cs:__imp_EnterCriticalSection
0x180013002  mov     rax, [rbx]
0x180013005  mov     r9, r12
0x180013008  mov     r8, r15
0x18001300b  mov     edx, esi
0x18001300d  mov     rcx, rbx
0x180013010  mov     rax, [rax+260h]
0x180013017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001301c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013020  mov     esi, eax
0x180013022  call    cs:__imp_LeaveCriticalSection
0x180013028  test    esi, esi
0x18001302a  jz      loc_1800130C3
0x180013030  test    cs:byte_1800C8404, 8
0x180013037  jz      loc_1800130C3
0x18001303d  xor     ecx, ecx
0x18001303f  mov     word ptr [rsp+8B0h+var_840], cx
0x180013044  mov     [rsp+8B0h+Buffer], cx
0x180013049  test    rbx, rbx
0x18001304c  jz      short loc_18001306B
0x18001304e  mov     ecx, [rbx+60h]; Value
0x180013051  cmp     ecx, 0FFFFFFFFh
0x180013054  jz      short loc_18001306B
0x180013056  mov     r9d, 0Ah; Radix
0x18001305c  lea     rdx, [rsp+8B0h+Buffer]; Buffer
0x180013061  lea     r8d, [r9+0Ah]; BufferCount
0x180013065  call    cs:__imp__itow_s
0x18001306b  mov     r9, r14
0x18001306e  mov     dword ptr [rsp+8B0h+var_890], esi
0x180013072  lea     r8, aDdmportgetprot; "DdmPortGetProtocolCompression"
0x180013079  lea     rdx, aSDeviceobjGetp; "%s: deviceObj->GetProtocolCompression f"...
0x180013080  lea     rcx, [rsp+8B0h+var_840]
0x180013085  call    FormatRRASErrorString
0x18001308a  test    cs:byte_1800C8404, 8
0x180013091  jz      short loc_1800130C3
0x180013093  lea     rax, [rsp+8B0h+Buffer]
0x180013098  mov     [rsp+8B0h+var_888], rax
0x18001309d  lea     r9, [rsp+8B0h+var_878]
0x1800130a2  lea     r8, [rsp+8B0h+var_840]
0x1800130a7  mov     [rsp+8B0h+var_890], 0
0x1800130b0  lea     rdx, RasDdmParamTraceError
0x1800130b7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800130be  call    McTemplateU0zjzz_EventWriteTransfer
0x1800130c3  or      eax, 0FFFFFFFFh
0x1800130c6  lock xadd [rbx+8], eax
0x1800130cb  cmp     eax, 1
0x1800130ce  jnz     short loc_1800130E8
0x1800130d0  test    rbx, rbx
0x1800130d3  jz      short loc_1800130E8
0x1800130d5  mov     rax, [rbx]
0x1800130d8  mov     edx, 1
0x1800130dd  mov     rcx, rbx
0x1800130e0  mov     rax, [rax]
0x1800130e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130e8  mov     eax, esi
0x1800130ea  mov     rcx, [rbp+7B0h+var_40]
0x1800130f1  xor     rcx, rsp; StackCookie
0x1800130f4  call    __security_check_cookie
0x1800130f9  add     rsp, 880h
0x180013100  pop     r15
0x180013102  pop     r14
0x180013104  pop     r12
0x180013106  pop     rdi
0x180013107  pop     rsi
0x180013108  pop     rbx
0x180013109  pop     rbp
0x18001310a  retn
```
