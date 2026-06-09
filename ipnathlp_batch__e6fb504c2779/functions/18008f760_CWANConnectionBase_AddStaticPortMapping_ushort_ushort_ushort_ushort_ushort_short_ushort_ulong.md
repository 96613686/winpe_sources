# CWANConnectionBase::AddStaticPortMapping(ushort *,ushort,ushort *,ushort,ushort *,short,ushort *,ulong)

- ea: `0x18008f760`
- end: `0x18008fccd`
- name: `?AddStaticPortMapping@CWANConnectionBase@@IEAAJPEAGG0G0F0K@Z`
- size: `1389`
- prototype: `__int64 __fastcall(CWANConnectionBase *this, unsigned __int16 *, u_short, unsigned __int16 *, u_short, BSTR pbstr, __int16, BSTR bstrString)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008f5d0`

## callees

- `0x18003313c`
- `0x180051f30`
- `0x18008f760`
- `0x180090144`
- `0x180091644`
- `0x1800926d8`
- `0x180095b04`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18008f88d`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18008f88d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008f826`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008f845`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008fa00`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008fa79`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008f826`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008f845`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008fa00`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008fa79`
- `ntdll!RtlIpv4StringToAddressW` at `0x18008fb71`
- `ntdll!RtlIpv4StringToAddressW` at `0x18008fb71`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f8ff`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f8ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fc13`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fc2f`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fc43`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fc58`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fc13`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fc2f`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fc43`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fc58`
- `OLEAUT32!__imp_SysStringLen` at `0x18008f86f`
- `OLEAUT32!__imp_SysStringLen` at `0x18008f8b0`
- `OLEAUT32!__imp_SysStringLen` at `0x18008f86f`
- `OLEAUT32!__imp_SysStringLen` at `0x18008f8b0`
- `WS2_32!__imp_htons` at `0x18008f7ec`
- `WS2_32!__imp_htons` at `0x18008f800`
- `WS2_32!__imp_htons` at `0x18008f9cc`
- `WS2_32!__imp_htons` at `0x18008fa2a`
- `WS2_32!__imp_htons` at `0x18008fa40`
- `WS2_32!__imp_htons` at `0x18008f7ec`
- `WS2_32!__imp_htons` at `0x18008f800`
- `WS2_32!__imp_htons` at `0x18008f9cc`
- `WS2_32!__imp_htons` at `0x18008fa2a`
- `WS2_32!__imp_htons` at `0x18008fa40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008fc04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008fc04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008f8cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008f8cc`

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
0x18008f760  mov     [rsp-8+arg_8], rbx
0x18008f765  push    rbp
0x18008f766  push    rsi
0x18008f767  push    rdi
0x18008f768  push    r12
0x18008f76a  push    r13
0x18008f76c  push    r14
0x18008f76e  push    r15
0x18008f770  lea     rbp, [rsp-7]
0x18008f775  sub     rsp, 0B0h
0x18008f77c  mov     rax, cs:__security_cookie
0x18008f783  xor     rax, rsp
0x18008f786  mov     [rbp+37h+var_40], rax
0x18008f78a  movsd   xmm0, qword ptr cs:a00000; "00000"
0x18008f792  xor     r12d, r12d
0x18008f795  mov     eax, dword ptr cs:a00000+8; "0"
0x18008f79b  mov     rbx, r9
0x18008f79e  mov     rsi, [rbp+37h+pbstr]
0x18008f7a2  mov     r13, rcx
0x18008f7a5  mov     r15, [rbp+37h+bstrString]
0x18008f7a9  movzx   ecx, r8w; hostshort
0x18008f7ad  mov     [rbp+37h+var_78], rbx
0x18008f7b1  mov     edi, r12d
0x18008f7b4  mov     [rbp+37h+var_60], r12
0x18008f7b8  mov     [rbp+37h+var_90], r12
0x18008f7bc  mov     [rbp+37h+var_88], r12
0x18008f7c0  mov     dword ptr [rbp+37h+Addr.S_un], r12d
0x18008f7c4  movsd   qword ptr [rbp+37h+Buffer], xmm0
0x18008f7c9  mov     [rbp+37h+var_A0], r12w
0x18008f7ce  mov     [rbp+37h+var_9C], r12w
0x18008f7d3  mov     [rbp+37h+var_58], r12
0x18008f7d7  mov     [rbp+37h+var_70], r12
0x18008f7db  mov     [rbp+37h+var_68], r12
0x18008f7df  mov     [rbp+37h+var_94], r12w
0x18008f7e4  mov     [rbp+37h+var_98], r8w
0x18008f7e9  mov     [rbp+37h+var_48], eax
0x18008f7ec  call    cs:__imp_htons
0x18008f7f3  nop     dword ptr [rax+rax+00h]
0x18008f7f8  movzx   ecx, [rbp+37h+arg_20]; hostshort
0x18008f7fc  mov     [rbp+37h+var_A0], ax
0x18008f800  call    cs:__imp_htons
0x18008f807  nop     dword ptr [rax+rax+00h]
0x18008f80c  mov     [rbp+37h+var_9C], ax
0x18008f810  lea     rdx, aTcp; "TCP"
0x18008f817  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008f81b  mov     rcx, rbx
0x18008f81e  cmp     [rbp+37h+arg_30], ax
0x18008f822  setz    [rbp+37h+var_96]
0x18008f826  call    cs:__imp__o__wcsicmp
0x18008f82d  nop     dword ptr [rax+rax+00h]
0x18008f832  test    eax, eax
0x18008f834  jnz     short loc_18008F83B
0x18008f836  mov     r12b, 6
0x18008f839  jmp     short loc_18008F85C
0x18008f83b  lea     rdx, aUdp; "UDP"
0x18008f842  mov     rcx, rbx
0x18008f845  call    cs:__imp__o__wcsicmp
0x18008f84c  nop     dword ptr [rax+rax+00h]
0x18008f851  test    eax, eax
0x18008f853  jnz     loc_18008FC21
0x18008f859  mov     r12b, 11h
0x18008f85c  xor     r8d, r8d
0x18008f85f  mov     r14d, r8d
0x18008f862  cmp     [r15], r8w
0x18008f866  jnz     loc_18008F91D
0x18008f86c  mov     rcx, rsi; pbstr
0x18008f86f  call    cs:__imp_SysStringLen
0x18008f876  nop     dword ptr [rax+rax+00h]
0x18008f87b  movzx   ecx, [rbp+37h+var_98]; Value
0x18008f87f  lea     rdx, [rbp+37h+Buffer]; Buffer
0x18008f883  mov     r8d, 0Ah; Radix
0x18008f889  lea     r14d, [rax+1]
0x18008f88d  call    cs:__imp__itow
0x18008f894  nop     dword ptr [rax+rax+00h]
0x18008f899  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008f89d  lea     rax, [rbp+37h+Buffer]
0x18008f8a1  xor     ecx, ecx
0x18008f8a3  inc     rbx
0x18008f8a6  cmp     [rax+rbx*2], cx
0x18008f8aa  jnz     short loc_18008F8A3
0x18008f8ac  mov     rcx, [rbp+37h+var_78]; pbstr
0x18008f8b0  call    cs:__imp_SysStringLen
0x18008f8b7  nop     dword ptr [rax+rax+00h]
0x18008f8bc  mov     eax, eax
0x18008f8be  add     rbx, rax
0x18008f8c1  add     rbx, r14
0x18008f8c4  lea     rcx, ds:4[rbx*2]; cb
0x18008f8cc  call    cs:__imp_CoTaskMemAlloc
0x18008f8d3  nop     dword ptr [rax+rax+00h]
0x18008f8d8  mov     r14, rax
0x18008f8db  test    rax, rax
0x18008f8de  jz      short loc_18008F913
0x18008f8e0  mov     rax, [rbp+37h+var_78]
0x18008f8e4  lea     rdx, [rbx+2]; unsigned __int64
0x18008f8e8  lea     r9, [rbp+37h+Buffer]
0x18008f8ec  mov     [rsp+0E0h+var_C0], rax
0x18008f8f1  mov     r8, rsi; unsigned __int16 *
0x18008f8f4  mov     rcx, r14; unsigned __int16 *
0x18008f8f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008f8fc  mov     rcx, r14; psz
0x18008f8ff  call    cs:__imp_SysAllocString
0x18008f906  nop     dword ptr [rax+rax+00h]
0x18008f90b  mov     r15, rax
0x18008f90e  test    rax, rax
0x18008f911  jnz     short loc_18008F91D
0x18008f913  mov     ebx, 8007000Eh
0x18008f918  jmp     loc_18008FBFC
0x18008f91d  movzx   r8d, [rbp+37h+var_A0]; unsigned __int16
0x18008f922  lea     rax, [rbp+37h+var_90]
0x18008f926  mov     rcx, [r13+80h]; struct IHNetIcsSettings *
0x18008f92d  mov     r9b, r12b; unsigned __int8
0x18008f930  xor     edx, edx; unsigned int
0x18008f932  mov     [rsp+0E0h+var_C0], rax; struct IHNetPortMappingProtocol **
0x18008f937  call    ?SearchPortMapping@@YAJPEAUIHNetIcsSettings@@KGEPEAPEAUIHNetPortMappingProtocol@@@Z; SearchPortMapping(IHNetIcsSettings *,ulong,ushort,uchar,IHNetPortMappingProtocol * *)
0x18008f93c  test    eax, eax
0x18008f93e  js      loc_18008FAB4
0x18008f944  mov     rcx, [r13+60h]
0x18008f948  lea     r8, [rbp+37h+var_88]
0x18008f94c  mov     rdx, [rbp+37h+var_90]
0x18008f950  mov     rax, [rcx]
0x18008f953  mov     rax, [rax+70h]
0x18008f957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f95c  xor     r12d, r12d
0x18008f95f  mov     ebx, eax
0x18008f961  test    eax, eax
0x18008f963  js      loc_18008FBFC
0x18008f969  mov     rdx, [rbp+37h+var_88]; struct IHNetPortMappingBinding *
0x18008f96d  lea     rax, [rbp+37h+var_68]
0x18008f971  mov     rcx, [rbp+37h+var_90]; struct IHNetPortMappingProtocol *
0x18008f975  lea     r9, [rbp+37h+var_58]; unsigned __int16 **
0x18008f979  mov     [rsp+0E0h+var_A8], rax; unsigned __int16 **
0x18008f97e  lea     r8, [rbp+37h+var_A0]; unsigned __int16 *
0x18008f982  lea     rax, [rbp+37h+var_94]
0x18008f986  mov     [rsp+0E0h+var_B0], rax; __int16 *
0x18008f98b  lea     rax, [rbp+37h+var_70]
0x18008f98f  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 **
0x18008f994  lea     rax, [rbp+37h+var_9C]
0x18008f998  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x18008f99d  call    ?FillStaticMappingInformation@@YAJPEAUIHNetPortMappingProtocol@@PEAUIHNetPortMappingBinding@@PEAGPEAPEAG23PEAF3@Z; FillStaticMappingInformation(IHNetPortMappingProtocol *,IHNetPortMappingBinding *,ushort *,ushort * *,ushort *,ushort * *,short *,ushort * *)
0x18008f9a2  mov     ebx, eax
0x18008f9a4  test    eax, eax
0x18008f9a6  js      short loc_18008F9E3
0x18008f9a8  mov     rcx, [rbp+37h+var_90]
0x18008f9ac  lea     rdx, [rbp+37h+var_98]
0x18008f9b0  mov     byte ptr [rbp+37h+var_98], r12b
0x18008f9b4  mov     rax, [rcx]
0x18008f9b7  mov     rax, [rax+48h]
0x18008f9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f9c0  mov     ebx, eax
0x18008f9c2  cmp     byte ptr [rbp+37h+var_98], r12b
0x18008f9c6  jz      short loc_18008F9EC
0x18008f9c8  movzx   ecx, [rbp+37h+arg_20]; hostshort
0x18008f9cc  call    cs:__imp_htons
0x18008f9d3  nop     dword ptr [rax+rax+00h]
0x18008f9d8  cmp     [rbp+37h+var_A0], ax
0x18008f9dc  jz      short loc_18008F9EC
0x18008f9de  mov     ebx, 80070005h
0x18008f9e3  mov     rdi, [rbp+37h+var_70]
0x18008f9e7  jmp     loc_18008FBFC
0x18008f9ec  mov     rdi, [rbp+37h+var_70]
0x18008f9f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008f9f4  cmp     [rbp+37h+var_94], ax
0x18008f9f8  jnz     short loc_18008FA26
0x18008f9fa  mov     rdx, rdi
0x18008f9fd  mov     rcx, rsi
0x18008fa00  call    cs:__imp__o__wcsicmp
0x18008fa07  nop     dword ptr [rax+rax+00h]
0x18008fa0c  test    eax, eax
0x18008fa0e  jz      short loc_18008FA26
0x18008fa10  lea     rcx, a718; "718"
0x18008fa17  mov     ebx, 80070057h
0x18008fa1c  call    ?SetUPnPError@@YAJPEAG@Z; SetUPnPError(ushort *)
0x18008fa21  jmp     loc_18008FBFC
0x18008fa26  movzx   ecx, [rbp+37h+arg_20]; hostshort
0x18008fa2a  call    cs:__imp_htons
0x18008fa31  nop     dword ptr [rax+rax+00h]
0x18008fa36  cmp     [rbp+37h+var_9C], ax
0x18008fa3a  jz      short loc_18008FA72
0x18008fa3c  movzx   ecx, [rbp+37h+arg_20]; hostshort
0x18008fa40  call    cs:__imp_htons
0x18008fa47  nop     dword ptr [rax+rax+00h]
0x18008fa4c  mov     rcx, [rbp+37h+var_88]
0x18008fa50  movzx   r8d, ax
0x18008fa54  mov     [rbp+37h+var_9C], ax
0x18008fa58  mov     rdx, [rcx]
0x18008fa5b  mov     rax, [rdx+68h]
0x18008fa5f  movzx   edx, r8w
0x18008fa63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa68  mov     ebx, eax
0x18008fa6a  test    eax, eax
0x18008fa6c  js      loc_18008FBFC
0x18008fa72  mov     rcx, [rbp+37h+var_68]
0x18008fa76  mov     rdx, r15
0x18008fa79  call    cs:__imp__o__wcsicmp
0x18008fa80  nop     dword ptr [rax+rax+00h]
0x18008fa85  test    eax, eax
0x18008fa87  jz      loc_18008FB44
0x18008fa8d  mov     rcx, [rbp+37h+var_90]
0x18008fa91  mov     rdx, r15
0x18008fa94  mov     rax, [rcx]
0x18008fa97  mov     rax, [rax+20h]
0x18008fa9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008faa0  mov     ebx, eax
0x18008faa2  test    eax, eax
0x18008faa4  jns     loc_18008FB44
0x18008faaa  mov     ebx, 80070057h
0x18008faaf  jmp     loc_18008FBFC
0x18008fab4  mov     rcx, [r13+80h]
0x18008fabb  lea     r8, [rbp+37h+var_60]
0x18008fabf  lea     rdx, IID_IHNetProtocolSettings
0x18008fac6  mov     rax, [rcx]
0x18008fac9  mov     rax, [rax]
0x18008facc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fad1  mov     ebx, eax
0x18008fad3  test    eax, eax
0x18008fad5  js      loc_18008FBFC
0x18008fadb  mov     rcx, [rbp+37h+var_60]
0x18008fadf  lea     rdx, [rbp+37h+var_90]
0x18008fae3  movzx   r9d, [rbp+37h+var_A0]
0x18008fae8  mov     r8b, r12b
0x18008faeb  mov     [rsp+0E0h+var_C0], rdx
0x18008faf0  mov     rdx, r15
0x18008faf3  mov     rax, [rcx]
0x18008faf6  mov     rax, [rax+30h]
0x18008fafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008faff  mov     ebx, eax
0x18008fb01  test    eax, eax
0x18008fb03  js      loc_18008FBFC
0x18008fb09  mov     rcx, [r13+60h]
0x18008fb0d  lea     r8, [rbp+37h+var_88]
0x18008fb11  mov     rdx, [rbp+37h+var_90]
0x18008fb15  mov     rax, [rcx]
0x18008fb18  mov     rax, [rax+70h]
0x18008fb1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb21  mov     ebx, eax
0x18008fb23  test    eax, eax
0x18008fb25  js      loc_18008FBEC
0x18008fb2b  mov     rcx, [rbp+37h+var_88]
0x18008fb2f  movzx   edx, [rbp+37h+var_9C]
0x18008fb33  mov     rax, [rcx]
0x18008fb36  mov     rax, [rax+68h]
0x18008fb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb3f  mov     ebx, eax
0x18008fb41  mov     r12b, 1
0x18008fb44  mov     rdx, rsi; String2
0x18008fb47  lea     rcx, a0000; "0.0.0.0"
0x18008fb4e  call    wcscmp_0
0x18008fb53  xor     r13d, r13d
0x18008fb56  test    eax, eax
0x18008fb58  jz      short loc_18008FBCE
0x18008fb5a  cmp     [rsi], r13w
0x18008fb5e  jz      short loc_18008FBCE
0x18008fb60  lea     r9, [rbp+37h+Addr]; Addr
0x18008fb64  mov     [rbp+37h+var_78], r13
0x18008fb68  lea     r8, [rbp+37h+var_78]; Terminator
0x18008fb6c  mov     dl, 1; Strict
0x18008fb6e  mov     rcx, rsi; S
0x18008fb71  call    cs:__imp_RtlIpv4StringToAddressW
0x18008fb78  nop     dword ptr [rax+rax+00h]
0x18008fb7d  test    eax, eax
0x18008fb7f  js      short loc_18008FBA0
0x18008fb81  mov     rax, [rbp+37h+var_78]
0x18008fb85  cmp     [rax], r13w
0x18008fb89  jnz     short loc_18008FBA0
0x18008fb8b  mov     rcx, [rbp+37h+var_88]
0x18008fb8f  mov     edx, dword ptr [rbp+37h+Addr.S_un]
0x18008fb92  mov     rax, [rcx]
0x18008fb95  mov     rax, [rax+58h]
0x18008fb99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb9e  jmp     short loc_18008FBB3
0x18008fba0  mov     rcx, [rbp+37h+var_88]
0x18008fba4  mov     rdx, rsi
0x18008fba7  mov     rax, [rcx]
0x18008fbaa  mov     rax, [rax+48h]
0x18008fbae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fbb3  mov     ebx, eax
0x18008fbb5  test    eax, eax
0x18008fbb7  js      short loc_18008FBD2
0x18008fbb9  mov     rcx, [rbp+37h+var_88]
0x18008fbbd  mov     dl, [rbp+37h+var_96]
0x18008fbc0  mov     rax, [rcx]
0x18008fbc3  mov     rax, [rax+30h]
0x18008fbc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fbcc  mov     ebx, eax
0x18008fbce  test    ebx, ebx
0x18008fbd0  jns     short loc_18008FBFC
0x18008fbd2  cmp     r12b, 1
0x18008fbd6  jnz     short loc_18008FBFC
0x18008fbd8  mov     rcx, [rbp+37h+var_90]
0x18008fbdc  mov     rax, [rcx]
0x18008fbdf  mov     rax, [rax+50h]
0x18008fbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fbe8  mov     ebx, eax
0x18008fbea  jmp     short loc_18008FBFC
0x18008fbec  mov     rcx, [rbp+37h+var_90]
0x18008fbf0  mov     rax, [rcx]
0x18008fbf3  mov     rax, [rax+50h]
0x18008fbf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fbfc  test    r14, r14
0x18008fbff  jz      short loc_18008FC26
  ... truncated ...
```
