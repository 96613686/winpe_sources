# Win32NetworkAdapterConfigurationHelper::IsTcpSettingStatic(bool,ushort const *,IWbemClassObject *,bool &)

- ea: `0x18022d00c`
- end: `0x18022d172`
- name: `?IsTcpSettingStatic@Win32NetworkAdapterConfigurationHelper@@AEAAJ_NPEBGPEAUIWbemClassObject@@AEA_N@Z`
- size: `358`
- prototype: `__int64 __fastcall(Win32NetworkAdapterConfigurationHelper *__hidden this, bool, const unsigned __int16 *, struct IWbemClassObject *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18022ac34`

## callees

- `0x18005f0c0`
- `0x18006c530`
- `0x18022d00c`
- `0x18022d5d4`
- `0x1802b7010`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18022d0db`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18022d0db`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18022d0ef`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18022d0ef`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18022d0ba`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18022d0f9`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18022d0ba`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18022d0f9`
- `OLEAUT32!__imp_VariantInit` at `0x18022d06b`
- `OLEAUT32!__imp_VariantInit` at `0x18022d06b`
- `OLEAUT32!__imp_VariantClear` at `0x18022d0b1`
- `OLEAUT32!__imp_VariantClear` at `0x18022d0b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Win32NetworkAdapterConfigurationHelper::IsTcpSettingStatic(
        Win32NetworkAdapterConfigurationHelper *this,
        char a2,
        const unsigned __int16 *a3,
        struct IWbemClassObject *a4,
        bool *a5)
{
  NTSTATUS v8; // ebx
  NET_IFINDEX Lo; // edi
  NTSTATUS v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  bool v13; // sf
  NET_LUID InterfaceLuid; // [rsp+40h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-29h] BYREF
  GUID InterfaceGuid; // [rsp+60h] [rbp-11h] BYREF
  __int128 v18; // [rsp+70h] [rbp-1h] BYREF
  __m128i si128; // [rsp+80h] [rbp+Fh]

  v18 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v18) = 0;
  InterfaceGuid = 0;
  *a5 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v8 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a4->lpVtbl->Get)(
         a4,
         L"InterfaceIndex",
         0,
         &pvarg,
         0,
         0);
  if ( v8 < 0 )
    goto LABEL_17;
  Lo = pvarg.cyVal.Lo;
  VariantClear(&pvarg);
  v10 = SetCurrentThreadCompartmentScope(0xFFFFFFFF);
  v8 = v10;
  if ( !v10 )
  {
    InterfaceLuid.Value = 0;
    v8 = ConvertInterfaceIndexToLuid(Lo, &InterfaceLuid);
    if ( !v8 )
      v8 = ConvertInterfaceLuidToGuid(&InterfaceLuid, &InterfaceGuid);
    SetCurrentThreadCompartmentScope(0);
    if ( v8 == 2 )
    {
      v8 = -2147217406;
      goto LABEL_17;
    }
    v13 = v8 < 0;
    if ( v8 <= 0 )
      goto LABEL_13;
    v8 = (unsigned __int16)v8;
    goto LABEL_11;
  }
  if ( v10 > 0 )
  {
    v8 = (unsigned __int16)v10;
LABEL_11:
    v8 |= 0x80070000;
  }
  v13 = v8 < 0;
LABEL_13:
  if ( !v13 )
  {
    LOBYTE(v12) = a2;
    v8 = Win32NetworkAdapterConfigurationHelper::ReadTcpSetting(v11, &InterfaceGuid, v12, a3, &v18);
    if ( v8 >= 0 )
    {
      if ( si128.m128i_i64[0] )
        *a5 = 1;
    }
  }
LABEL_17:
  std::wstring::~wstring(&v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18022d00c  mov     [rsp-8+arg_0], rbx
0x18022d011  push    rbp
0x18022d012  push    rsi
0x18022d013  push    rdi
0x18022d014  push    r14
0x18022d016  push    r15
0x18022d018  lea     rbp, [rsp-2Fh]
0x18022d01d  sub     rsp, 0A0h
0x18022d024  mov     rax, cs:__security_cookie
0x18022d02b  xor     rax, rsp
0x18022d02e  mov     [rbp+4Fh+var_30], rax
0x18022d032  mov     rbx, r9
0x18022d035  mov     r15, r8
0x18022d038  mov     r14b, dl
0x18022d03b  mov     rsi, [rbp+4Fh+arg_20]
0x18022d03f  xorps   xmm0, xmm0
0x18022d042  movups  [rbp+4Fh+var_50], xmm0
0x18022d046  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18022d04e  movdqu  [rbp+4Fh+var_40], xmm1
0x18022d053  xor     eax, eax
0x18022d055  mov     word ptr [rbp+4Fh+var_50], ax
0x18022d059  movups  xmmword ptr [rbp+4Fh+InterfaceGuid.Data1], xmm0
0x18022d05d  mov     [rsi], al
0x18022d05f  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x18022d063  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x18022d067  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18022d06b  call    cs:__imp_VariantInit
0x18022d071  mov     rax, [rbx]
0x18022d074  mov     [rsp+0C0h+var_98], 0
0x18022d07d  mov     [rsp+0C0h+var_A0], 0
0x18022d086  lea     r9, [rbp+4Fh+pvarg]
0x18022d08a  xor     r8d, r8d
0x18022d08d  lea     rdx, aInterfaceindex; "InterfaceIndex"
0x18022d094  mov     rcx, rbx
0x18022d097  mov     rax, [rax+20h]
0x18022d09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022d0a0  mov     ebx, eax
0x18022d0a2  test    eax, eax
0x18022d0a4  js      loc_18022D144
0x18022d0aa  mov     edi, dword ptr [rbp+4Fh+pvarg+8]
0x18022d0ad  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18022d0b1  call    cs:__imp_VariantClear
0x18022d0b7  or      ecx, 0FFFFFFFFh; CompartmentScope
0x18022d0ba  call    cs:__imp_SetCurrentThreadCompartmentScope
0x18022d0c0  mov     ebx, eax
0x18022d0c2  test    eax, eax
0x18022d0c4  jz      short loc_18022D0CD
0x18022d0c6  jle     short loc_18022D118
0x18022d0c8  movzx   ebx, ax
0x18022d0cb  jmp     short loc_18022D112
0x18022d0cd  mov     qword ptr [rbp+4Fh+InterfaceLuid], 0
0x18022d0d5  lea     rdx, [rbp+4Fh+InterfaceLuid]; InterfaceLuid
0x18022d0d9  mov     ecx, edi; InterfaceIndex
0x18022d0db  call    cs:__imp_ConvertInterfaceIndexToLuid
0x18022d0e1  mov     ebx, eax
0x18022d0e3  test    eax, eax
0x18022d0e5  jnz     short loc_18022D0F7
0x18022d0e7  lea     rdx, [rbp+4Fh+InterfaceGuid]; InterfaceGuid
0x18022d0eb  lea     rcx, [rbp+4Fh+InterfaceLuid]; InterfaceLuid
0x18022d0ef  call    cs:__imp_ConvertInterfaceLuidToGuid
0x18022d0f5  mov     ebx, eax
0x18022d0f7  xor     ecx, ecx; CompartmentScope
0x18022d0f9  call    cs:__imp_SetCurrentThreadCompartmentScope
0x18022d0ff  cmp     ebx, 2
0x18022d102  jnz     short loc_18022D10B
0x18022d104  mov     ebx, 80041002h
0x18022d109  jmp     short loc_18022D144
0x18022d10b  test    ebx, ebx
0x18022d10d  jle     short loc_18022D11A
0x18022d10f  movzx   ebx, bx
0x18022d112  or      ebx, 80070000h
0x18022d118  test    ebx, ebx
0x18022d11a  js      short loc_18022D144
0x18022d11c  lea     rax, [rbp+4Fh+var_50]
0x18022d120  mov     [rsp+0C0h+var_A0], rax
0x18022d125  mov     r9, r15
0x18022d128  mov     r8b, r14b
0x18022d12b  lea     rdx, [rbp+4Fh+InterfaceGuid]
0x18022d12f  call    ?ReadTcpSetting@Win32NetworkAdapterConfigurationHelper@@AEAAJAEBU_GUID@@_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32NetworkAdapterConfigurationHelper::ReadTcpSetting(_GUID const &,bool,ushort const *,std::wstring &)
0x18022d134  mov     ebx, eax
0x18022d136  test    eax, eax
0x18022d138  js      short loc_18022D144
0x18022d13a  cmp     qword ptr [rbp+4Fh+var_40], 0
0x18022d13f  jz      short loc_18022D144
0x18022d141  mov     byte ptr [rsi], 1
0x18022d144  lea     rcx, [rbp+4Fh+var_50]; void *
0x18022d148  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18022d14d  mov     eax, ebx
0x18022d14f  mov     rcx, [rbp+4Fh+var_30]
0x18022d153  xor     rcx, rsp; StackCookie
0x18022d156  call    __security_check_cookie
0x18022d15b  mov     rbx, [rsp+0C0h+arg_0]
0x18022d163  add     rsp, 0A0h
0x18022d16a  pop     r15
0x18022d16c  pop     r14
0x18022d16e  pop     rdi
0x18022d16f  pop     rsi
0x18022d170  pop     rbp
0x18022d171  retn
```
