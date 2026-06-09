# DdmDevice::~DdmDevice(void)

- ea: `0x180031578`
- end: `0x1800316da`
- name: `??1DdmDevice@@UEAA@XZ`
- size: `354`
- prototype: `void __fastcall(DdmDevice *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002b44c`
- `0x1800316e0`
- `0x18003ebfc`
- `0x1800930a1`

## callees

- `0x180007d00`
- `0x180031578`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18003168f`
- `KERNEL32!DeleteCriticalSection` at `0x18003169f`
- `KERNEL32!DeleteCriticalSection` at `0x18003168f`
- `KERNEL32!DeleteCriticalSection` at `0x18003169f`

## pseudocode

```c
void __fastcall DdmDevice::~DdmDevice(DdmDevice *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // [rsp+20h] [rbp-E0h]
  int v4; // [rsp+28h] [rbp-D8h]
  int v5; // [rsp+30h] [rbp-D0h]
  __int128 v6; // [rsp+40h] [rbp-C0h] BYREF
  int v7; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v8; // [rsp+54h] [rbp-ACh]
  __int128 v9; // [rsp+64h] [rbp-9Ch]
  int v10; // [rsp+74h] [rbp-8Ch]
  int v11; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v12[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  *(_QWORD *)this = &DdmDevice::`vftable';
  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v6 = 0;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    LOWORD(v7) = 0;
    ConvertPortNoToString(&v7, *((unsigned int *)this + 24));
    v5 = *((_DWORD *)this + 297);
    v4 = *((_DWORD *)this + 32);
    v3 = *((_DWORD *)this + 26);
    FormatRRASErrorString(
      &v11,
      L"%s(hport: %ld, State: %d, ConnectionState: %d, Number of Routes: %u)",
      L"DdmDevice::~DdmDevice",
      *((_QWORD *)this + 12),
      v3,
      v4,
      v5);
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v11,
        (unsigned int)&v6,
        0,
        (__int64)&v7);
  }
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 147);
  if ( v2 )
    (**v2)(v2, 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  *(_QWORD *)this = &std::tr1::_Node_base::`vftable';
}

```

## disassembly

```asm
0x180031578  mov     [rsp-8+arg_8], rbx
0x18003157d  mov     [rsp-8+arg_10], rdi
0x180031582  push    rbp
0x180031583  lea     rbp, [rsp-790h]
0x18003158b  sub     rsp, 890h
0x180031592  mov     rax, cs:__security_cookie
0x180031599  xor     rax, rsp
0x18003159c  mov     [rbp+790h+var_10], rax
0x1800315a3  mov     rbx, rcx
0x1800315a6  lea     rax, ??_7DdmDevice@@6B@; const DdmDevice::`vftable'
0x1800315ad  mov     [rcx], rax
0x1800315b0  xor     edi, edi
0x1800315b2  mov     [rbp+790h+var_810], edi
0x1800315b5  xor     edx, edx; Val
0x1800315b7  mov     r8d, 7FCh; Size
0x1800315bd  lea     rcx, [rbp+790h+var_80C]; void *
0x1800315c1  call    memset_0
0x1800315c6  mov     [rsp+890h+var_840], edi
0x1800315ca  xorps   xmm0, xmm0
0x1800315cd  xor     eax, eax
0x1800315cf  movups  [rsp+890h+var_83C], xmm0
0x1800315d4  movups  [rsp+890h+var_82C], xmm0
0x1800315d9  mov     [rsp+890h+var_81C], eax
0x1800315dd  movups  [rsp+890h+var_850], xmm0
0x1800315e2  test    cs:byte_1800CF404, 10h
0x1800315e9  jz      loc_18003166F
0x1800315ef  mov     word ptr [rbp+790h+var_810], di
0x1800315f3  mov     word ptr [rsp+890h+var_840], di
0x1800315f8  mov     edx, [rbx+60h]
0x1800315fb  lea     rcx, [rsp+890h+var_840]
0x180031600  call    ConvertPortNoToString
0x180031605  mov     eax, [rbx+4A4h]
0x18003160b  mov     [rsp+890h+var_860], eax
0x18003160f  mov     eax, [rbx+80h]
0x180031615  mov     dword ptr [rsp+890h+var_868], eax
0x180031619  mov     eax, [rbx+68h]
0x18003161c  mov     dword ptr [rsp+890h+var_870], eax
0x180031620  mov     r9, [rbx+60h]
0x180031624  lea     r8, aDdmdeviceDdmde; "DdmDevice::~DdmDevice"
0x18003162b  lea     rdx, aSHportLdStateD; "%s(hport: %ld, State: %d, ConnectionSta"...
0x180031632  lea     rcx, [rbp+790h+var_810]
0x180031636  call    FormatRRASErrorString
0x18003163b  test    cs:byte_1800CF404, 10h
0x180031642  jz      short loc_18003166F
0x180031644  lea     rax, [rsp+890h+var_840]
0x180031649  mov     [rsp+890h+var_868], rax
0x18003164e  mov     [rsp+890h+var_870], rdi
0x180031653  lea     r9, [rsp+890h+var_850]
0x180031658  lea     r8, [rbp+790h+var_810]
0x18003165c  lea     rdx, RasDdmParamTraceInfo
0x180031663  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003166a  call    McTemplateU0zjzz_EventWriteTransfer
0x18003166f  mov     rcx, [rbx+498h]
0x180031676  test    rcx, rcx
0x180031679  jz      short loc_18003168B
0x18003167b  mov     rax, [rcx]
0x18003167e  mov     edx, 1
0x180031683  mov     rax, [rax]
0x180031686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003168b  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003168f  call    cs:__imp_DeleteCriticalSection
0x180031696  nop     dword ptr [rax+rax+00h]
0x18003169b  lea     rcx, [rbx+38h]; lpCriticalSection
0x18003169f  call    cs:__imp_DeleteCriticalSection
0x1800316a6  nop     dword ptr [rax+rax+00h]
0x1800316ab  lea     rax, ??_7_Node_base@tr1@std@@6B@; const std::tr1::_Node_base::`vftable'
0x1800316b2  mov     [rbx], rax
0x1800316b5  mov     rcx, [rbp+790h+var_10]
0x1800316bc  xor     rcx, rsp; StackCookie
0x1800316bf  call    __security_check_cookie
0x1800316c4  lea     r11, [rsp+890h+var_s0]
0x1800316cc  mov     rbx, [r11+18h]
0x1800316d0  mov     rdi, [r11+20h]
0x1800316d4  mov     rsp, r11
0x1800316d7  pop     rbp
0x1800316d8  retn
```
