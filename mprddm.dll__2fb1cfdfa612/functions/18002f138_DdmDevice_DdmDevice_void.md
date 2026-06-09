# DdmDevice::~DdmDevice(void)

- ea: `0x18002f138`
- end: `0x18002f296`
- name: `??1DdmDevice@@UEAA@XZ`
- size: `350`
- prototype: `void __fastcall(DdmDevice *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002916c`
- `0x18002f2a0`
- `0x18003d2dc`
- `0x18008cba2`

## callees

- `0x180007c50`
- `0x18002f138`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18002f1c8`
- `msvcrt!_itow_s` at `0x18002f1c8`
- `KERNEL32!DeleteCriticalSection` at `0x18002f25c`
- `KERNEL32!DeleteCriticalSection` at `0x18002f266`
- `KERNEL32!DeleteCriticalSection` at `0x18002f25c`
- `KERNEL32!DeleteCriticalSection` at `0x18002f266`

## pseudocode

```c
void __fastcall DdmDevice::~DdmDevice(DdmDevice *this)
{
  int v2; // ecx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  int v4; // [rsp+20h] [rbp-E0h]
  int v5; // [rsp+28h] [rbp-D8h]
  int v6; // [rsp+30h] [rbp-D0h]
  __int128 v7; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Buffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v9; // [rsp+54h] [rbp-ACh]
  __int128 v10; // [rsp+64h] [rbp-9Ch]
  int v11; // [rsp+74h] [rbp-8Ch]
  int v12; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v13[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  *(_QWORD *)this = &DdmDevice::`vftable';
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  *(_DWORD *)Buffer = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v7 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v12) = 0;
    Buffer[0] = 0;
    v2 = *((_DWORD *)this + 24);
    if ( v2 != -1 )
      _itow_s(v2, Buffer, 0x14u, 10);
    v6 = *((_DWORD *)this + 297);
    v5 = *((_DWORD *)this + 32);
    v4 = *((_DWORD *)this + 26);
    FormatRRASErrorString(
      &v12,
      L"%s(hport: %ld, State: %d, ConnectionState: %d, Number of Routes: %u)",
      L"DdmDevice::~DdmDevice",
      *((_QWORD *)this + 12),
      v4,
      v5,
      v6);
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v12,
        (unsigned int)&v7,
        0,
        (__int64)Buffer);
  }
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 147);
  if ( v3 )
    (**v3)(v3, 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  *(_QWORD *)this = &std::tr1::_Node_base::`vftable';
}

```

## disassembly

```asm
0x18002f138  mov     [rsp-8+arg_8], rbx
0x18002f13d  push    rbp
0x18002f13e  lea     rbp, [rsp-790h]
0x18002f146  sub     rsp, 890h
0x18002f14d  mov     rax, cs:__security_cookie
0x18002f154  xor     rax, rsp
0x18002f157  mov     [rbp+790h+var_10], rax
0x18002f15e  mov     rbx, rcx
0x18002f161  lea     rax, ??_7DdmDevice@@6B@; const DdmDevice::`vftable'
0x18002f168  mov     [rcx], rax
0x18002f16b  xor     eax, eax
0x18002f16d  mov     [rbp+790h+var_810], eax
0x18002f170  xor     edx, edx; Val
0x18002f172  mov     r8d, 7FCh; Size
0x18002f178  lea     rcx, [rbp+790h+var_80C]; void *
0x18002f17c  call    memset_0
0x18002f181  xor     eax, eax
0x18002f183  mov     dword ptr [rsp+890h+Buffer], eax
0x18002f187  xorps   xmm0, xmm0
0x18002f18a  movups  [rsp+890h+var_83C], xmm0
0x18002f18f  movups  [rsp+890h+var_82C], xmm0
0x18002f194  mov     [rsp+890h+var_81C], eax
0x18002f198  movups  [rsp+890h+var_850], xmm0
0x18002f19d  test    cs:byte_1800C8404, 10h
0x18002f1a4  jz      loc_18002F23C
0x18002f1aa  mov     word ptr [rbp+790h+var_810], ax
0x18002f1ae  mov     [rsp+890h+Buffer], ax
0x18002f1b3  mov     ecx, [rbx+60h]; Value
0x18002f1b6  cmp     ecx, 0FFFFFFFFh
0x18002f1b9  jz      short loc_18002F1CE
0x18002f1bb  lea     r9d, [rax+0Ah]; Radix
0x18002f1bf  lea     r8d, [rax+14h]; BufferCount
0x18002f1c3  lea     rdx, [rsp+890h+Buffer]; Buffer
0x18002f1c8  call    cs:__imp__itow_s
0x18002f1ce  mov     eax, [rbx+4A4h]
0x18002f1d4  mov     [rsp+890h+var_860], eax
0x18002f1d8  mov     eax, [rbx+80h]
0x18002f1de  mov     dword ptr [rsp+890h+var_868], eax
0x18002f1e2  mov     eax, [rbx+68h]
0x18002f1e5  mov     dword ptr [rsp+890h+var_870], eax
0x18002f1e9  mov     r9, [rbx+60h]
0x18002f1ed  lea     r8, aDdmdeviceDdmde; "DdmDevice::~DdmDevice"
0x18002f1f4  lea     rdx, aSHportLdStateD; "%s(hport: %ld, State: %d, ConnectionSta"...
0x18002f1fb  lea     rcx, [rbp+790h+var_810]
0x18002f1ff  call    FormatRRASErrorString
0x18002f204  test    cs:byte_1800C8404, 10h
0x18002f20b  jz      short loc_18002F23C
0x18002f20d  lea     rax, [rsp+890h+Buffer]
0x18002f212  mov     [rsp+890h+var_868], rax
0x18002f217  mov     [rsp+890h+var_870], 0
0x18002f220  lea     r9, [rsp+890h+var_850]
0x18002f225  lea     r8, [rbp+790h+var_810]
0x18002f229  lea     rdx, RasDdmParamTraceInfo
0x18002f230  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002f237  call    McTemplateU0zjzz_EventWriteTransfer
0x18002f23c  mov     rcx, [rbx+498h]
0x18002f243  test    rcx, rcx
0x18002f246  jz      short loc_18002F258
0x18002f248  mov     rax, [rcx]
0x18002f24b  mov     edx, 1
0x18002f250  mov     rax, [rax]
0x18002f253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f258  lea     rcx, [rbx+10h]; lpCriticalSection
0x18002f25c  call    cs:__imp_DeleteCriticalSection
0x18002f262  lea     rcx, [rbx+38h]; lpCriticalSection
0x18002f266  call    cs:__imp_DeleteCriticalSection
0x18002f26c  lea     rax, ??_7_Node_base@tr1@std@@6B@; const std::tr1::_Node_base::`vftable'
0x18002f273  mov     [rbx], rax
0x18002f276  mov     rcx, [rbp+790h+var_10]
0x18002f27d  xor     rcx, rsp; StackCookie
0x18002f280  call    __security_check_cookie
0x18002f285  mov     rbx, [rsp+890h+arg_8]
0x18002f28d  add     rsp, 890h
0x18002f294  pop     rbp
0x18002f295  retn
```
