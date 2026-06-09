# DdmPortSetProtocolCompression

- ea: `0x1800137e0`
- end: `0x180013a1b`
- name: `DdmPortSetProtocolCompression`
- size: `571`
- prototype: `__int64 __fastcall(int Value)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x1800137e0`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800138a4`
- `msvcrt!_itow_s` at `0x180013975`
- `msvcrt!_itow_s` at `0x1800138a4`
- `msvcrt!_itow_s` at `0x180013975`
- `KERNEL32!LeaveCriticalSection` at `0x180013932`
- `KERNEL32!LeaveCriticalSection` at `0x180013932`
- `KERNEL32!EnterCriticalSection` at `0x18001390c`
- `KERNEL32!EnterCriticalSection` at `0x18001390c`

## string_xrefs

- `0x1800138ad`: `DdmPortSetProtocolCompression`
- `0x180013982`: `DdmPortSetProtocolCompression`
- `0x180013989`: `%s: deviceObj->SetProtocolCompression failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmPortSetProtocolCompression(__int64 Value, unsigned int a2, __int64 a3, __int64 a4)
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
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v9 + 616LL))(v9, a2, a3, a4);
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
        L"%s: deviceObj->SetProtocolCompression failed for port (%ld):%d.",
        L"DdmPortSetProtocolCompression",
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
      FormatRRASErrorString(&v19, L"%s: Port %ld not found.", L"DdmPortSetProtocolCompression", Value);
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
0x1800137e0  push    rbp
0x1800137e2  push    rbx
0x1800137e3  push    rsi
0x1800137e4  push    rdi
0x1800137e5  push    r12
0x1800137e7  push    r14
0x1800137e9  push    r15
0x1800137eb  lea     rbp, [rsp-780h]
0x1800137f3  sub     rsp, 880h
0x1800137fa  mov     rax, cs:__security_cookie
0x180013801  xor     rax, rsp
0x180013804  mov     [rbp+7B0h+var_40], rax
0x18001380b  mov     r15, r8
0x18001380e  mov     [rsp+8B0h+var_880], 0
0x180013817  mov     esi, edx
0x180013819  mov     r14, rcx
0x18001381c  xor     eax, eax
0x18001381e  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180013823  xor     edx, edx; Val
0x180013825  mov     [rsp+8B0h+var_840], eax
0x180013829  mov     r8d, 7FCh; Size
0x18001382f  mov     r12, r9
0x180013832  call    memset_0
0x180013837  xor     eax, eax
0x180013839  xorps   xmm0, xmm0
0x18001383c  mov     dword ptr [rsp+8B0h+Buffer], eax
0x180013840  movups  [rsp+8B0h+var_864], xmm0
0x180013845  mov     [rsp+8B0h+var_844], eax
0x180013849  lea     ecx, [rax+11h]; unsigned int
0x18001384c  movups  [rsp+8B0h+var_854], xmm0
0x180013851  movups  [rsp+8B0h+var_878], xmm0
0x180013856  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001385b  lea     r8, [rsp+8B0h+var_880]
0x180013860  mov     rdx, r14
0x180013863  mov     rcx, rax
0x180013866  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18001386b  mov     rbx, [rsp+8B0h+var_880]
0x180013870  test    rbx, rbx
0x180013873  jnz     loc_180013908
0x180013879  test    cs:byte_1800C8404, 10h
0x180013880  jz      short loc_1800138FE
0x180013882  xor     eax, eax
0x180013884  mov     word ptr [rsp+8B0h+var_840], ax
0x180013889  mov     [rsp+8B0h+Buffer], ax
0x18001388e  cmp     r14d, 0FFFFFFFFh
0x180013892  jz      short loc_1800138AA
0x180013894  lea     r9d, [rbx+0Ah]; Radix
0x180013898  mov     ecx, r14d; Value
0x18001389b  lea     r8d, [rbx+14h]; BufferCount
0x18001389f  lea     rdx, [rsp+8B0h+Buffer]; Buffer
0x1800138a4  call    cs:__imp__itow_s
0x1800138aa  mov     r9, r14
0x1800138ad  lea     r8, aDdmportsetprot; "DdmPortSetProtocolCompression"
0x1800138b4  lea     rdx, aSPortLdNotFoun; "%s: Port %ld not found."
0x1800138bb  lea     rcx, [rsp+8B0h+var_840]
0x1800138c0  call    FormatRRASErrorString
0x1800138c5  test    cs:byte_1800C8404, 10h
0x1800138cc  jz      short loc_1800138FE
0x1800138ce  lea     rax, [rsp+8B0h+Buffer]
0x1800138d3  mov     [rsp+8B0h+var_888], rax
0x1800138d8  lea     r9, [rsp+8B0h+var_878]
0x1800138dd  lea     r8, [rsp+8B0h+var_840]
0x1800138e2  mov     [rsp+8B0h+var_890], 0
0x1800138eb  lea     rdx, RasDdmParamTraceInfo
0x1800138f2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800138f9  call    McTemplateU0zjzz_EventWriteTransfer
0x1800138fe  mov     esi, 490h
0x180013903  jmp     loc_1800139F8
0x180013908  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001390c  call    cs:__imp_EnterCriticalSection
0x180013912  mov     rax, [rbx]
0x180013915  mov     r9, r12
0x180013918  mov     r8, r15
0x18001391b  mov     edx, esi
0x18001391d  mov     rcx, rbx
0x180013920  mov     rax, [rax+268h]
0x180013927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001392c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013930  mov     esi, eax
0x180013932  call    cs:__imp_LeaveCriticalSection
0x180013938  test    esi, esi
0x18001393a  jz      loc_1800139D3
0x180013940  test    cs:byte_1800C8404, 8
0x180013947  jz      loc_1800139D3
0x18001394d  xor     ecx, ecx
0x18001394f  mov     word ptr [rsp+8B0h+var_840], cx
0x180013954  mov     [rsp+8B0h+Buffer], cx
0x180013959  test    rbx, rbx
0x18001395c  jz      short loc_18001397B
0x18001395e  mov     ecx, [rbx+60h]; Value
0x180013961  cmp     ecx, 0FFFFFFFFh
0x180013964  jz      short loc_18001397B
0x180013966  mov     r9d, 0Ah; Radix
0x18001396c  lea     rdx, [rsp+8B0h+Buffer]; Buffer
0x180013971  lea     r8d, [r9+0Ah]; BufferCount
0x180013975  call    cs:__imp__itow_s
0x18001397b  mov     r9, r14
0x18001397e  mov     dword ptr [rsp+8B0h+var_890], esi
0x180013982  lea     r8, aDdmportsetprot; "DdmPortSetProtocolCompression"
0x180013989  lea     rdx, aSDeviceobjSetp; "%s: deviceObj->SetProtocolCompression f"...
0x180013990  lea     rcx, [rsp+8B0h+var_840]
0x180013995  call    FormatRRASErrorString
0x18001399a  test    cs:byte_1800C8404, 8
0x1800139a1  jz      short loc_1800139D3
0x1800139a3  lea     rax, [rsp+8B0h+Buffer]
0x1800139a8  mov     [rsp+8B0h+var_888], rax
0x1800139ad  lea     r9, [rsp+8B0h+var_878]
0x1800139b2  lea     r8, [rsp+8B0h+var_840]
0x1800139b7  mov     [rsp+8B0h+var_890], 0
0x1800139c0  lea     rdx, RasDdmParamTraceError
0x1800139c7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800139ce  call    McTemplateU0zjzz_EventWriteTransfer
0x1800139d3  or      eax, 0FFFFFFFFh
0x1800139d6  lock xadd [rbx+8], eax
0x1800139db  cmp     eax, 1
0x1800139de  jnz     short loc_1800139F8
0x1800139e0  test    rbx, rbx
0x1800139e3  jz      short loc_1800139F8
0x1800139e5  mov     rax, [rbx]
0x1800139e8  mov     edx, 1
0x1800139ed  mov     rcx, rbx
0x1800139f0  mov     rax, [rax]
0x1800139f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139f8  mov     eax, esi
0x1800139fa  mov     rcx, [rbp+7B0h+var_40]
0x180013a01  xor     rcx, rsp; StackCookie
0x180013a04  call    __security_check_cookie
0x180013a09  add     rsp, 880h
0x180013a10  pop     r15
0x180013a12  pop     r14
0x180013a14  pop     r12
0x180013a16  pop     rdi
0x180013a17  pop     rsi
0x180013a18  pop     rbx
0x180013a19  pop     rbp
0x180013a1a  retn
```
