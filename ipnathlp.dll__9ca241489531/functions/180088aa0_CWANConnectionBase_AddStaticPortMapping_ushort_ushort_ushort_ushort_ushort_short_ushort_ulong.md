# CWANConnectionBase::AddStaticPortMapping(ushort *,ushort,ushort *,ushort,ushort *,short,ushort *,ulong)

- ea: `0x180088aa0`
- end: `0x180088f94`
- name: `?AddStaticPortMapping@CWANConnectionBase@@IEAAJPEAGG0G0F0K@Z`
- size: `1268`
- prototype: `__int64 __fastcall(CWANConnectionBase *this, unsigned __int16 *, u_short, unsigned __int16 *, u_short, BSTR pbstr, __int16, BSTR bstrString)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180088910`

## callees

- `0x18002e7a4`
- `0x18004e0c0`
- `0x180088aa0`
- `0x1800893d0`
- `0x18008a764`
- `0x18008b68c`
- `0x18008e8e4`
- `0x180090010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180088baf`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180088baf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180088b5a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180088b73`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180088d04`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180088d6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180088b5a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180088b73`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180088d04`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180088d6b`
- `ntdll!RtlIpv4StringToAddressW` at `0x180088e5d`
- `ntdll!RtlIpv4StringToAddressW` at `0x180088e5d`
- `OLEAUT32!__imp_SysAllocString` at `0x180088c0f`
- `OLEAUT32!__imp_SysAllocString` at `0x180088c0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180088ef3`
- `OLEAUT32!__imp_SysFreeString` at `0x180088f09`
- `OLEAUT32!__imp_SysFreeString` at `0x180088f17`
- `OLEAUT32!__imp_SysFreeString` at `0x180088f26`
- `OLEAUT32!__imp_SysFreeString` at `0x180088ef3`
- `OLEAUT32!__imp_SysFreeString` at `0x180088f09`
- `OLEAUT32!__imp_SysFreeString` at `0x180088f17`
- `OLEAUT32!__imp_SysFreeString` at `0x180088f26`
- `OLEAUT32!__imp_SysStringLen` at `0x180088b97`
- `OLEAUT32!__imp_SysStringLen` at `0x180088bcc`
- `OLEAUT32!__imp_SysStringLen` at `0x180088b97`
- `OLEAUT32!__imp_SysStringLen` at `0x180088bcc`
- `WS2_32!__imp_htons` at `0x180088b2c`
- `WS2_32!__imp_htons` at `0x180088b3a`
- `WS2_32!__imp_htons` at `0x180088cd6`
- `WS2_32!__imp_htons` at `0x180088d28`
- `WS2_32!__imp_htons` at `0x180088d38`
- `WS2_32!__imp_htons` at `0x180088b2c`
- `WS2_32!__imp_htons` at `0x180088b3a`
- `WS2_32!__imp_htons` at `0x180088cd6`
- `WS2_32!__imp_htons` at `0x180088d28`
- `WS2_32!__imp_htons` at `0x180088d38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180088be2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180088be2`

## pseudocode

```c
__int64 __fastcall CWANConnectionBase::AddStaticPortMapping(
        CWANConnectionBase *this,
        unsigned __int16 *a2,
        u_short a3,
        unsigned __int16 *a4,
        u_short a5,
        BSTR pbstr,
        __int16 a7,
        BSTR bstrString)
{
  OLECHAR *v10; // r15
  unsigned __int16 *v11; // rdi
  unsigned __int8 v12; // r12
  unsigned __int16 *v13; // r14
  __int64 v14; // r14
  __int64 v15; // rbx
  __int64 v16; // rbx
  int v17; // ebx
  char v18; // r12
  __int64 v19; // r8
  int v20; // eax
  __int64 v21; // rdx
  unsigned __int16 v23[2]; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 v24; // [rsp+44h] [rbp-65h] BYREF
  u_short v25; // [rsp+48h] [rbp-61h] BYREF
  bool v26; // [rsp+4Ah] [rbp-5Fh]
  __int16 v27; // [rsp+4Ch] [rbp-5Dh] BYREF
  struct IHNetPortMappingProtocol *v28; // [rsp+50h] [rbp-59h] BYREF
  struct IHNetPortMappingBinding *v29; // [rsp+58h] [rbp-51h] BYREF
  struct in_addr Addr; // [rsp+60h] [rbp-49h] BYREF
  BSTR v31; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int16 *v32; // [rsp+70h] [rbp-39h] BYREF
  BSTR v33; // [rsp+78h] [rbp-31h] BYREF
  __int64 v34; // [rsp+80h] [rbp-29h] BYREF
  BSTR v35; // [rsp+88h] [rbp-21h] BYREF
  wchar_t Buffer[8]; // [rsp+90h] [rbp-19h] BYREF

  v10 = bstrString;
  v31 = a4;
  v11 = 0;
  v34 = 0;
  v28 = 0;
  v29 = 0;
  Addr = 0;
  wcscpy(Buffer, L"00000");
  v35 = 0;
  v32 = 0;
  v33 = 0;
  v27 = 0;
  v25 = a3;
  v23[0] = htons(a3);
  v24 = htons(a5);
  v26 = a7 == -1;
  if ( (unsigned int)_o__wcsicmp(a4, L"TCP") )
  {
    if ( (unsigned int)_o__wcsicmp(a4, L"UDP") )
    {
      v17 = -2147024809;
      goto LABEL_45;
    }
    v12 = 17;
  }
  else
  {
    v12 = 6;
  }
  v13 = 0;
  if ( !*bstrString )
  {
    v14 = SysStringLen(pbstr) + 1;
    _itow(v25, Buffer, 10);
    v15 = -1;
    do
      ++v15;
    while ( Buffer[v15] );
    v16 = v14 + SysStringLen(v31) + v15;
    v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v16 + 4);
    if ( !v13 || (StringCchPrintfW(v13, v16 + 2, pbstr, Buffer, v31), (v10 = SysAllocString(v13)) == 0) )
    {
      v17 = -2147024882;
      goto LABEL_42;
    }
  }
  if ( (int)SearchPortMapping(*((struct IHNetIcsSettings **)this + 16), 0, v23[0], v12, &v28) < 0 )
  {
    v17 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 16))(
            *((_QWORD *)this + 16),
            &IID_IHNetProtocolSettings,
            &v34);
    if ( v17 < 0 )
      goto LABEL_42;
    LOBYTE(v19) = v12;
    v17 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, _QWORD, struct IHNetPortMappingProtocol **))(*(_QWORD *)v34 + 48LL))(
            v34,
            v10,
            v19,
            v23[0],
            &v28);
    if ( v17 < 0 )
      goto LABEL_42;
    v17 = (*(__int64 (__fastcall **)(_QWORD, struct IHNetPortMappingProtocol *, struct IHNetPortMappingBinding **))(**((_QWORD **)this + 12) + 112LL))(
            *((_QWORD *)this + 12),
            v28,
            &v29);
    if ( v17 < 0 )
    {
      (*(void (__fastcall **)(struct IHNetPortMappingProtocol *))(*(_QWORD *)v28 + 80LL))(v28);
      goto LABEL_42;
    }
    v17 = (*(__int64 (__fastcall **)(struct IHNetPortMappingBinding *, _QWORD))(*(_QWORD *)v29 + 104LL))(v29, v24);
    v18 = 1;
  }
  else
  {
    v18 = 0;
    v17 = (*(__int64 (__fastcall **)(_QWORD, struct IHNetPortMappingProtocol *, struct IHNetPortMappingBinding **))(**((_QWORD **)this + 12) + 112LL))(
            *((_QWORD *)this + 12),
            v28,
            &v29);
    if ( v17 < 0 )
      goto LABEL_42;
    v17 = FillStaticMappingInformation(v28, v29, v23, &v35, &v24, &v32, &v27, &v33);
    if ( v17 < 0 )
      goto LABEL_17;
    LOBYTE(v25) = 0;
    v17 = (*(__int64 (__fastcall **)(struct IHNetPortMappingProtocol *, u_short *))(*(_QWORD *)v28 + 72LL))(v28, &v25);
    if ( (_BYTE)v25 && v23[0] != htons(a5) )
    {
      v17 = -2147024891;
LABEL_17:
      v11 = v32;
      goto LABEL_42;
    }
    v11 = v32;
    if ( v27 == -1 && (unsigned int)_o__wcsicmp(pbstr, v32) )
    {
      v17 = -2147024809;
      SetUPnPError(L"718");
      goto LABEL_42;
    }
    if ( v24 != htons(a5) )
    {
      v24 = htons(a5);
      v17 = (*(__int64 (__fastcall **)(struct IHNetPortMappingBinding *, _QWORD))(*(_QWORD *)v29 + 104LL))(v29, v24);
      if ( v17 < 0 )
        goto LABEL_42;
    }
    if ( (unsigned int)_o__wcsicmp(v33, v10) )
    {
      v17 = (*(__int64 (__fastcall **)(struct IHNetPortMappingProtocol *, OLECHAR *))(*(_QWORD *)v28 + 32LL))(v28, v10);
      if ( v17 < 0 )
      {
        v17 = -2147024809;
        goto LABEL_42;
      }
    }
  }
  if ( wcscmp_0(L"0.0.0.0", pbstr) && *pbstr )
  {
    v31 = 0;
    if ( RtlIpv4StringToAddressW(pbstr, 1u, (LPCWSTR *)&v31, &Addr) < 0 || *v31 )
      v20 = (*(__int64 (__fastcall **)(struct IHNetPortMappingBinding *, BSTR))(*(_QWORD *)v29 + 72LL))(v29, pbstr);
    else
      v20 = (*(__int64 (__fastcall **)(struct IHNetPortMappingBinding *, _QWORD))(*(_QWORD *)v29 + 88LL))(
              v29,
              Addr.S_un.S_addr);
    v17 = v20;
    if ( v20 < 0 )
    {
LABEL_39:
      if ( v18 == 1 )
        v17 = (*(__int64 (__fastcall **)(struct IHNetPortMappingProtocol *))(*(_QWORD *)v28 + 80LL))(v28);
      goto LABEL_42;
    }
    LOBYTE(v21) = v26;
    v17 = (*(__int64 (__fastcall **)(struct IHNetPortMappingBinding *, __int64))(*(_QWORD *)v29 + 48LL))(v29, v21);
  }
  if ( v17 < 0 )
    goto LABEL_39;
LABEL_42:
  if ( v13 )
  {
    CoTaskMemFree(v13);
    SysFreeString(v10);
  }
LABEL_45:
  if ( v35 )
    SysFreeString(v35);
  if ( v11 )
    SysFreeString(v11);
  if ( v33 )
    SysFreeString(v33);
  if ( v29 )
    (*(void (__fastcall **)(struct IHNetPortMappingBinding *))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v28 )
    (*(void (__fastcall **)(struct IHNetPortMappingProtocol *))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180088aa0  mov     [rsp-8+arg_8], rbx
0x180088aa5  push    rbp
0x180088aa6  push    rsi
0x180088aa7  push    rdi
0x180088aa8  push    r12
0x180088aaa  push    r13
0x180088aac  push    r14
0x180088aae  push    r15
0x180088ab0  lea     rbp, [rsp-7]
0x180088ab5  sub     rsp, 0B0h
0x180088abc  mov     rax, cs:__security_cookie
0x180088ac3  xor     rax, rsp
0x180088ac6  mov     [rbp+37h+var_40], rax
0x180088aca  movsd   xmm0, qword ptr cs:a00000; "00000"
0x180088ad2  xor     r12d, r12d
0x180088ad5  mov     eax, dword ptr cs:a00000+8; "0"
0x180088adb  mov     rbx, r9
0x180088ade  mov     rsi, [rbp+37h+pbstr]
0x180088ae2  mov     r13, rcx
0x180088ae5  mov     r15, [rbp+37h+bstrString]
0x180088ae9  movzx   ecx, r8w; hostshort
0x180088aed  mov     [rbp+37h+var_78], rbx
0x180088af1  mov     edi, r12d
0x180088af4  mov     [rbp+37h+var_60], r12
0x180088af8  mov     [rbp+37h+var_90], r12
0x180088afc  mov     [rbp+37h+var_88], r12
0x180088b00  mov     dword ptr [rbp+37h+Addr.S_un], r12d
0x180088b04  movsd   qword ptr [rbp+37h+Buffer], xmm0
0x180088b09  mov     [rbp+37h+var_A0], r12w
0x180088b0e  mov     [rbp+37h+var_9C], r12w
0x180088b13  mov     [rbp+37h+var_58], r12
0x180088b17  mov     [rbp+37h+var_70], r12
0x180088b1b  mov     [rbp+37h+var_68], r12
0x180088b1f  mov     [rbp+37h+var_94], r12w
0x180088b24  mov     [rbp+37h+var_98], r8w
0x180088b29  mov     [rbp+37h+var_48], eax
0x180088b2c  call    cs:__imp_htons
0x180088b32  movzx   ecx, [rbp+37h+arg_20]; hostshort
0x180088b36  mov     [rbp+37h+var_A0], ax
0x180088b3a  call    cs:__imp_htons
0x180088b40  mov     [rbp+37h+var_9C], ax
0x180088b44  lea     rdx, aTcp; "TCP"
0x180088b4b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180088b4f  mov     rcx, rbx
0x180088b52  cmp     [rbp+37h+arg_30], ax
0x180088b56  setz    [rbp+37h+var_96]
0x180088b5a  call    cs:__imp__o__wcsicmp
0x180088b60  test    eax, eax
0x180088b62  jnz     short loc_180088B69
0x180088b64  mov     r12b, 6
0x180088b67  jmp     short loc_180088B84
0x180088b69  lea     rdx, aUdp; "UDP"
0x180088b70  mov     rcx, rbx
0x180088b73  call    cs:__imp__o__wcsicmp
0x180088b79  test    eax, eax
0x180088b7b  jnz     loc_180088EFB
0x180088b81  mov     r12b, 11h
0x180088b84  xor     r8d, r8d
0x180088b87  mov     r14d, r8d
0x180088b8a  cmp     [r15], r8w
0x180088b8e  jnz     loc_180088C27
0x180088b94  mov     rcx, rsi; pbstr
0x180088b97  call    cs:__imp_SysStringLen
0x180088b9d  movzx   ecx, [rbp+37h+var_98]; Value
0x180088ba1  lea     rdx, [rbp+37h+Buffer]; Buffer
0x180088ba5  mov     r8d, 0Ah; Radix
0x180088bab  lea     r14d, [rax+1]
0x180088baf  call    cs:__imp__itow
0x180088bb5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180088bb9  lea     rax, [rbp+37h+Buffer]
0x180088bbd  xor     ecx, ecx
0x180088bbf  inc     rbx
0x180088bc2  cmp     [rax+rbx*2], cx
0x180088bc6  jnz     short loc_180088BBF
0x180088bc8  mov     rcx, [rbp+37h+var_78]; pbstr
0x180088bcc  call    cs:__imp_SysStringLen
0x180088bd2  mov     eax, eax
0x180088bd4  add     rbx, rax
0x180088bd7  add     rbx, r14
0x180088bda  lea     rcx, ds:4[rbx*2]; cb
0x180088be2  call    cs:__imp_CoTaskMemAlloc
0x180088be8  mov     r14, rax
0x180088beb  test    rax, rax
0x180088bee  jz      short loc_180088C1D
0x180088bf0  mov     rax, [rbp+37h+var_78]
0x180088bf4  lea     rdx, [rbx+2]; unsigned __int64
0x180088bf8  lea     r9, [rbp+37h+Buffer]
0x180088bfc  mov     [rsp+0E0h+var_C0], rax
0x180088c01  mov     r8, rsi; unsigned __int16 *
0x180088c04  mov     rcx, r14; unsigned __int16 *
0x180088c07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180088c0c  mov     rcx, r14; psz
0x180088c0f  call    cs:__imp_SysAllocString
0x180088c15  mov     r15, rax
0x180088c18  test    rax, rax
0x180088c1b  jnz     short loc_180088C27
0x180088c1d  mov     ebx, 8007000Eh
0x180088c22  jmp     loc_180088EE2
0x180088c27  movzx   r8d, [rbp+37h+var_A0]; unsigned __int16
0x180088c2c  lea     rax, [rbp+37h+var_90]
0x180088c30  mov     rcx, [r13+80h]; struct IHNetIcsSettings *
0x180088c37  mov     r9b, r12b; unsigned __int8
0x180088c3a  xor     edx, edx; unsigned int
0x180088c3c  mov     [rsp+0E0h+var_C0], rax; struct IHNetPortMappingProtocol **
0x180088c41  call    ?SearchPortMapping@@YAJPEAUIHNetIcsSettings@@KGEPEAPEAUIHNetPortMappingProtocol@@@Z; SearchPortMapping(IHNetIcsSettings *,ulong,ushort,uchar,IHNetPortMappingProtocol * *)
0x180088c46  test    eax, eax
0x180088c48  js      loc_180088DA0
0x180088c4e  mov     rcx, [r13+60h]
0x180088c52  lea     r8, [rbp+37h+var_88]
0x180088c56  mov     rdx, [rbp+37h+var_90]
0x180088c5a  mov     rax, [rcx]
0x180088c5d  mov     rax, [rax+70h]
0x180088c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088c66  xor     r12d, r12d
0x180088c69  mov     ebx, eax
0x180088c6b  test    eax, eax
0x180088c6d  js      loc_180088EE2
0x180088c73  mov     rdx, [rbp+37h+var_88]; struct IHNetPortMappingBinding *
0x180088c77  lea     rax, [rbp+37h+var_68]
0x180088c7b  mov     rcx, [rbp+37h+var_90]; struct IHNetPortMappingProtocol *
0x180088c7f  lea     r9, [rbp+37h+var_58]; unsigned __int16 **
0x180088c83  mov     [rsp+0E0h+var_A8], rax; unsigned __int16 **
0x180088c88  lea     r8, [rbp+37h+var_A0]; unsigned __int16 *
0x180088c8c  lea     rax, [rbp+37h+var_94]
0x180088c90  mov     [rsp+0E0h+var_B0], rax; __int16 *
0x180088c95  lea     rax, [rbp+37h+var_70]
0x180088c99  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 **
0x180088c9e  lea     rax, [rbp+37h+var_9C]
0x180088ca2  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x180088ca7  call    ?FillStaticMappingInformation@@YAJPEAUIHNetPortMappingProtocol@@PEAUIHNetPortMappingBinding@@PEAGPEAPEAG23PEAF3@Z; FillStaticMappingInformation(IHNetPortMappingProtocol *,IHNetPortMappingBinding *,ushort *,ushort * *,ushort *,ushort * *,short *,ushort * *)
0x180088cac  mov     ebx, eax
0x180088cae  test    eax, eax
0x180088cb0  js      short loc_180088CE7
0x180088cb2  mov     rcx, [rbp+37h+var_90]
0x180088cb6  lea     rdx, [rbp+37h+var_98]
0x180088cba  mov     byte ptr [rbp+37h+var_98], r12b
0x180088cbe  mov     rax, [rcx]
0x180088cc1  mov     rax, [rax+48h]
0x180088cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088cca  mov     ebx, eax
0x180088ccc  cmp     byte ptr [rbp+37h+var_98], r12b
0x180088cd0  jz      short loc_180088CF0
0x180088cd2  movzx   ecx, [rbp+37h+arg_20]; hostshort
0x180088cd6  call    cs:__imp_htons
0x180088cdc  cmp     [rbp+37h+var_A0], ax
0x180088ce0  jz      short loc_180088CF0
0x180088ce2  mov     ebx, 80070005h
0x180088ce7  mov     rdi, [rbp+37h+var_70]
0x180088ceb  jmp     loc_180088EE2
0x180088cf0  mov     rdi, [rbp+37h+var_70]
0x180088cf4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180088cf8  cmp     [rbp+37h+var_94], ax
0x180088cfc  jnz     short loc_180088D24
0x180088cfe  mov     rdx, rdi
0x180088d01  mov     rcx, rsi
0x180088d04  call    cs:__imp__o__wcsicmp
0x180088d0a  test    eax, eax
0x180088d0c  jz      short loc_180088D24
0x180088d0e  lea     rcx, a718; "718"
0x180088d15  mov     ebx, 80070057h
0x180088d1a  call    ?SetUPnPError@@YAJPEAG@Z; SetUPnPError(ushort *)
0x180088d1f  jmp     loc_180088EE2
0x180088d24  movzx   ecx, [rbp+37h+arg_20]; hostshort
0x180088d28  call    cs:__imp_htons
0x180088d2e  cmp     [rbp+37h+var_9C], ax
0x180088d32  jz      short loc_180088D64
0x180088d34  movzx   ecx, [rbp+37h+arg_20]; hostshort
0x180088d38  call    cs:__imp_htons
0x180088d3e  mov     rcx, [rbp+37h+var_88]
0x180088d42  movzx   r8d, ax
0x180088d46  mov     [rbp+37h+var_9C], ax
0x180088d4a  mov     rdx, [rcx]
0x180088d4d  mov     rax, [rdx+68h]
0x180088d51  movzx   edx, r8w
0x180088d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088d5a  mov     ebx, eax
0x180088d5c  test    eax, eax
0x180088d5e  js      loc_180088EE2
0x180088d64  mov     rcx, [rbp+37h+var_68]
0x180088d68  mov     rdx, r15
0x180088d6b  call    cs:__imp__o__wcsicmp
0x180088d71  test    eax, eax
0x180088d73  jz      loc_180088E30
0x180088d79  mov     rcx, [rbp+37h+var_90]
0x180088d7d  mov     rdx, r15
0x180088d80  mov     rax, [rcx]
0x180088d83  mov     rax, [rax+20h]
0x180088d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088d8c  mov     ebx, eax
0x180088d8e  test    eax, eax
0x180088d90  jns     loc_180088E30
0x180088d96  mov     ebx, 80070057h
0x180088d9b  jmp     loc_180088EE2
0x180088da0  mov     rcx, [r13+80h]
0x180088da7  lea     r8, [rbp+37h+var_60]
0x180088dab  lea     rdx, IID_IHNetProtocolSettings
0x180088db2  mov     rax, [rcx]
0x180088db5  mov     rax, [rax]
0x180088db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088dbd  mov     ebx, eax
0x180088dbf  test    eax, eax
0x180088dc1  js      loc_180088EE2
0x180088dc7  mov     rcx, [rbp+37h+var_60]
0x180088dcb  lea     rdx, [rbp+37h+var_90]
0x180088dcf  movzx   r9d, [rbp+37h+var_A0]
0x180088dd4  mov     r8b, r12b
0x180088dd7  mov     [rsp+0E0h+var_C0], rdx
0x180088ddc  mov     rdx, r15
0x180088ddf  mov     rax, [rcx]
0x180088de2  mov     rax, [rax+30h]
0x180088de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088deb  mov     ebx, eax
0x180088ded  test    eax, eax
0x180088def  js      loc_180088EE2
0x180088df5  mov     rcx, [r13+60h]
0x180088df9  lea     r8, [rbp+37h+var_88]
0x180088dfd  mov     rdx, [rbp+37h+var_90]
0x180088e01  mov     rax, [rcx]
0x180088e04  mov     rax, [rax+70h]
0x180088e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e0d  mov     ebx, eax
0x180088e0f  test    eax, eax
0x180088e11  js      loc_180088ED2
0x180088e17  mov     rcx, [rbp+37h+var_88]
0x180088e1b  movzx   edx, [rbp+37h+var_9C]
0x180088e1f  mov     rax, [rcx]
0x180088e22  mov     rax, [rax+68h]
0x180088e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e2b  mov     ebx, eax
0x180088e2d  mov     r12b, 1
0x180088e30  mov     rdx, rsi; String2
0x180088e33  lea     rcx, a0000; "0.0.0.0"
0x180088e3a  call    wcscmp_0
0x180088e3f  xor     r13d, r13d
0x180088e42  test    eax, eax
0x180088e44  jz      short loc_180088EB4
0x180088e46  cmp     [rsi], r13w
0x180088e4a  jz      short loc_180088EB4
0x180088e4c  lea     r9, [rbp+37h+Addr]; Addr
0x180088e50  mov     [rbp+37h+var_78], r13
0x180088e54  lea     r8, [rbp+37h+var_78]; Terminator
0x180088e58  mov     dl, 1; Strict
0x180088e5a  mov     rcx, rsi; S
0x180088e5d  call    cs:__imp_RtlIpv4StringToAddressW
0x180088e63  test    eax, eax
0x180088e65  js      short loc_180088E86
0x180088e67  mov     rax, [rbp+37h+var_78]
0x180088e6b  cmp     [rax], r13w
0x180088e6f  jnz     short loc_180088E86
0x180088e71  mov     rcx, [rbp+37h+var_88]
0x180088e75  mov     edx, dword ptr [rbp+37h+Addr.S_un]
0x180088e78  mov     rax, [rcx]
0x180088e7b  mov     rax, [rax+58h]
0x180088e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e84  jmp     short loc_180088E99
0x180088e86  mov     rcx, [rbp+37h+var_88]
0x180088e8a  mov     rdx, rsi
0x180088e8d  mov     rax, [rcx]
0x180088e90  mov     rax, [rax+48h]
0x180088e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e99  mov     ebx, eax
0x180088e9b  test    eax, eax
0x180088e9d  js      short loc_180088EB8
0x180088e9f  mov     rcx, [rbp+37h+var_88]
0x180088ea3  mov     dl, [rbp+37h+var_96]
0x180088ea6  mov     rax, [rcx]
0x180088ea9  mov     rax, [rax+30h]
0x180088ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088eb2  mov     ebx, eax
0x180088eb4  test    ebx, ebx
0x180088eb6  jns     short loc_180088EE2
0x180088eb8  cmp     r12b, 1
0x180088ebc  jnz     short loc_180088EE2
0x180088ebe  mov     rcx, [rbp+37h+var_90]
0x180088ec2  mov     rax, [rcx]
0x180088ec5  mov     rax, [rax+50h]
0x180088ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ece  mov     ebx, eax
0x180088ed0  jmp     short loc_180088EE2
0x180088ed2  mov     rcx, [rbp+37h+var_90]
0x180088ed6  mov     rax, [rcx]
0x180088ed9  mov     rax, [rax+50h]
0x180088edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ee2  test    r14, r14
0x180088ee5  jz      short loc_180088F00
0x180088ee7  mov     rcx, r14; pv
0x180088eea  call    cs:__imp_CoTaskMemFree
0x180088ef0  mov     rcx, r15; bstrString
0x180088ef3  call    cs:__imp_SysFreeString
0x180088ef9  jmp     short loc_180088F00
0x180088efb  mov     ebx, 80070057h
0x180088f00  mov     rcx, [rbp+37h+var_58]; bstrString
0x180088f04  test    rcx, rcx
0x180088f07  jz      short loc_180088F0F
0x180088f09  call    cs:__imp_SysFreeString
0x180088f0f  test    rdi, rdi
0x180088f12  jz      short loc_180088F1D
0x180088f14  mov     rcx, rdi; bstrString
0x180088f17  call    cs:__imp_SysFreeString
0x180088f1d  mov     rcx, [rbp+37h+var_68]; bstrString
  ... truncated ...
```
