# DdmProtocolStarted

- ea: `0x180013a30`
- end: `0x180013c51`
- name: `DdmProtocolStarted`
- size: `545`
- prototype: `__int64 __fastcall(int Value)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x180013a30`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180013aef`
- `msvcrt!_itow_s` at `0x180013bad`
- `msvcrt!_itow_s` at `0x180013aef`
- `msvcrt!_itow_s` at `0x180013bad`
- `KERNEL32!LeaveCriticalSection` at `0x180013b6e`
- `KERNEL32!LeaveCriticalSection` at `0x180013b6e`
- `KERNEL32!EnterCriticalSection` at `0x180013b50`
- `KERNEL32!EnterCriticalSection` at `0x180013b50`

## string_xrefs

- `0x180013af8`: `DdmProtocolStarted: Port %ld not found.`
- `0x180013bb6`: `DdmProtocolStarted: deviceObj->ProtocolStarted failed for port (%ld):%d.`

## pseudocode

```c
__int64 __fastcall DdmProtocolStarted(__int64 Value)
{
  struct DdmDeviceTable *Instance; // rax
  __int64 v3; // rbx
  unsigned int v4; // esi
  int v5; // ecx
  __int64 v7; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v8; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v10; // [rsp+4Ch] [rbp-B4h]
  __int128 v11; // [rsp+5Ch] [rbp-A4h]
  int v12; // [rsp+6Ch] [rbp-94h]
  int v13; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v7 = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  *(_DWORD *)Buffer = 0;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  v8 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, Value, &v7);
  v3 = v7;
  if ( v7 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 512LL))(v3);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
    if ( v4 && (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v13) = 0;
      Buffer[0] = 0;
      if ( v3 )
      {
        v5 = *(_DWORD *)(v3 + 96);
        if ( v5 != -1 )
          _itow_s(v5, Buffer, 0x14u, 10);
      }
      FormatRRASErrorString(
        &v13,
        L"DdmProtocolStarted: deviceObj->ProtocolStarted failed for port (%ld):%d.",
        Value,
        v4);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v13,
          (unsigned int)&v8,
          0,
          (__int64)Buffer);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) == 1 && v3 )
      (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
  }
  else
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v13) = 0;
      Buffer[0] = 0;
      if ( (_DWORD)Value != -1 )
        _itow_s(Value, Buffer, (unsigned int)(v7 + 20), v7 + 10);
      FormatRRASErrorString(&v13, L"DdmProtocolStarted: Port %ld not found.", Value);
      if ( (byte_1800C8404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v13,
          (unsigned int)&v8,
          0,
          (__int64)Buffer);
    }
    return 1168;
  }
  return v4;
}

```

## disassembly

```asm
0x180013a30  mov     [rsp-8+arg_8], rbx
0x180013a35  mov     [rsp-8+arg_10], rsi
0x180013a3a  push    rbp
0x180013a3b  push    rdi
0x180013a3c  push    r14
0x180013a3e  lea     rbp, [rsp-780h]
0x180013a46  sub     rsp, 880h
0x180013a4d  mov     rax, cs:__security_cookie
0x180013a54  xor     rax, rsp
0x180013a57  mov     [rbp+790h+var_20], rax
0x180013a5e  mov     r14, rcx
0x180013a61  mov     [rsp+890h+var_860], 0
0x180013a6a  xor     eax, eax
0x180013a6c  lea     rcx, [rsp+890h+var_81C]; void *
0x180013a71  xor     edx, edx; Val
0x180013a73  mov     [rsp+890h+var_820], eax
0x180013a77  mov     r8d, 7FCh; Size
0x180013a7d  call    memset_0
0x180013a82  xor     eax, eax
0x180013a84  xorps   xmm0, xmm0
0x180013a87  mov     dword ptr [rsp+890h+Buffer], eax
0x180013a8b  movups  [rsp+890h+var_844], xmm0
0x180013a90  mov     [rsp+890h+var_824], eax
0x180013a94  lea     ecx, [rax+11h]; unsigned int
0x180013a97  movups  [rsp+890h+var_834], xmm0
0x180013a9c  movups  [rsp+890h+var_858], xmm0
0x180013aa1  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180013aa6  lea     r8, [rsp+890h+var_860]
0x180013aab  mov     rdx, r14
0x180013aae  mov     rcx, rax
0x180013ab1  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180013ab6  mov     rbx, [rsp+890h+var_860]
0x180013abb  test    rbx, rbx
0x180013abe  jnz     loc_180013B4C
0x180013ac4  test    cs:byte_1800C8404, 10h
0x180013acb  jz      short loc_180013B42
0x180013acd  xor     eax, eax
0x180013acf  mov     word ptr [rsp+890h+var_820], ax
0x180013ad4  mov     [rsp+890h+Buffer], ax
0x180013ad9  cmp     r14d, 0FFFFFFFFh
0x180013add  jz      short loc_180013AF5
0x180013adf  lea     r9d, [rbx+0Ah]; Radix
0x180013ae3  mov     ecx, r14d; Value
0x180013ae6  lea     r8d, [rbx+14h]; BufferCount
0x180013aea  lea     rdx, [rsp+890h+Buffer]; Buffer
0x180013aef  call    cs:__imp__itow_s
0x180013af5  mov     r8, r14
0x180013af8  lea     rdx, aDdmprotocolsta_0; "DdmProtocolStarted: Port %ld not found."
0x180013aff  lea     rcx, [rsp+890h+var_820]
0x180013b04  call    FormatRRASErrorString
0x180013b09  test    cs:byte_1800C8404, 10h
0x180013b10  jz      short loc_180013B42
0x180013b12  lea     rax, [rsp+890h+Buffer]
0x180013b17  mov     [rsp+890h+var_868], rax
0x180013b1c  lea     r9, [rsp+890h+var_858]
0x180013b21  lea     r8, [rsp+890h+var_820]
0x180013b26  mov     [rsp+890h+var_870], 0
0x180013b2f  lea     rdx, RasDdmParamTraceInfo
0x180013b36  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013b3d  call    McTemplateU0zjzz_EventWriteTransfer
0x180013b42  mov     esi, 490h
0x180013b47  jmp     loc_180013C28
0x180013b4c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013b50  call    cs:__imp_EnterCriticalSection
0x180013b56  mov     rax, [rbx]
0x180013b59  mov     rcx, rbx
0x180013b5c  mov     rax, [rax+200h]
0x180013b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b68  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013b6c  mov     esi, eax
0x180013b6e  call    cs:__imp_LeaveCriticalSection
0x180013b74  test    esi, esi
0x180013b76  jz      loc_180013C03
0x180013b7c  test    cs:byte_1800C8404, 8
0x180013b83  jz      short loc_180013C03
0x180013b85  xor     ecx, ecx
0x180013b87  mov     word ptr [rsp+890h+var_820], cx
0x180013b8c  mov     [rsp+890h+Buffer], cx
0x180013b91  test    rbx, rbx
0x180013b94  jz      short loc_180013BB3
0x180013b96  mov     ecx, [rbx+60h]; Value
0x180013b99  cmp     ecx, 0FFFFFFFFh
0x180013b9c  jz      short loc_180013BB3
0x180013b9e  mov     r9d, 0Ah; Radix
0x180013ba4  lea     rdx, [rsp+890h+Buffer]; Buffer
0x180013ba9  lea     r8d, [r9+0Ah]; BufferCount
0x180013bad  call    cs:__imp__itow_s
0x180013bb3  mov     r9d, esi
0x180013bb6  lea     rdx, aDdmprotocolsta; "DdmProtocolStarted: deviceObj->Protocol"...
0x180013bbd  mov     r8, r14
0x180013bc0  lea     rcx, [rsp+890h+var_820]
0x180013bc5  call    FormatRRASErrorString
0x180013bca  test    cs:byte_1800C8404, 8
0x180013bd1  jz      short loc_180013C03
0x180013bd3  lea     rax, [rsp+890h+Buffer]
0x180013bd8  mov     [rsp+890h+var_868], rax
0x180013bdd  lea     r9, [rsp+890h+var_858]
0x180013be2  lea     r8, [rsp+890h+var_820]
0x180013be7  mov     [rsp+890h+var_870], 0
0x180013bf0  lea     rdx, RasDdmParamTraceError
0x180013bf7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013bfe  call    McTemplateU0zjzz_EventWriteTransfer
0x180013c03  or      eax, 0FFFFFFFFh
0x180013c06  lock xadd [rbx+8], eax
0x180013c0b  cmp     eax, 1
0x180013c0e  jnz     short loc_180013C28
0x180013c10  test    rbx, rbx
0x180013c13  jz      short loc_180013C28
0x180013c15  mov     rax, [rbx]
0x180013c18  mov     edx, 1
0x180013c1d  mov     rcx, rbx
0x180013c20  mov     rax, [rax]
0x180013c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c28  mov     eax, esi
0x180013c2a  mov     rcx, [rbp+790h+var_20]
0x180013c31  xor     rcx, rsp; StackCookie
0x180013c34  call    __security_check_cookie
0x180013c39  lea     r11, [rsp+890h+var_10]
0x180013c41  mov     rbx, [r11+28h]
0x180013c45  mov     rsi, [r11+30h]
0x180013c49  mov     rsp, r11
0x180013c4c  pop     r14
0x180013c4e  pop     rdi
0x180013c4f  pop     rbp
0x180013c50  retn
```
