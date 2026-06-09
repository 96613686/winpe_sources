# GetModulePath(_GUID const &,ushort * *)

- ea: `0x14006abf0`
- end: `0x14006ae11`
- name: `?GetModulePath@@YAJAEBU_GUID@@PEAPEAG@Z`
- size: `545`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002d3e0`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140011b10`
- `0x14001c380`
- `0x14002fa90`
- `0x140033ab0`
- `0x14006abf0`
- `0x14006ae20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14006adca`
- `ADVAPI32!RegCloseKey` at `0x14006add9`
- `ADVAPI32!RegCloseKey` at `0x14006adca`
- `ADVAPI32!RegCloseKey` at `0x14006add9`
- `ole32!StringFromCLSID` at `0x14006ac8e`
- `ole32!StringFromCLSID` at `0x14006ac8e`
- `ole32!CoTaskMemFree` at `0x14006ad7a`
- `ole32!CoTaskMemFree` at `0x14006ad7a`

## string_xrefs

- `0x14006ac51`: `\CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetModulePath(IID *rclsid, unsigned __int16 **a2)
{
  HKEY v4; // rsi
  HKEY v5; // r14
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v7; // rbx
  HRESULT v8; // edi
  __int64 v9; // r8
  int v10; // eax
  int v11; // eax
  int ResourceString; // eax
  int v13; // ecx
  unsigned __int16 *v14; // rdx
  HKEY hKey[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v17; // [rsp+30h] [rbp-40h]
  HKEY v18[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v19; // [rsp+48h] [rbp-28h]
  __int64 v20; // [rsp+50h] [rbp-20h]
  LPOLESTR lpsz; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v22; // [rsp+60h] [rbp-10h] BYREF

  v4 = 0;
  hKey[0] = 0;
  hKey[1] = 0;
  v17 = 0;
  v5 = 0;
  v18[0] = 0;
  v18[1] = 0;
  v19 = 0;
  lpsz = 0;
  v22 = 0;
  ATL::operator+(&v22, &detail::strRegistryRoot, L"\\CLSID\\");
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v7 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  v20 = v7;
  v8 = StringFromCLSID(rclsid, &lpsz);
  if ( v8 >= 0 )
  {
    if ( lpsz )
    {
      v9 = -1;
      do
        ++v9;
      while ( lpsz[v9] );
    }
    else
    {
      v9 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::Append(&v22, lpsz, v9);
    v10 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_LOCAL_MACHINE, v22, 0x20019u);
    v4 = hKey[0];
    if ( v10 )
      goto LABEL_8;
    if ( !(unsigned int)GetResourceString(hKey[0], L"InProcServer32", a2) )
    {
      ATL::CSimpleStringT<unsigned short,0>::Append(&v22, L"\\", 1);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v22, L"InprocServer32", 14);
      v11 = ATL::CRegKey::Open((ATL::CRegKey *)v18, HKEY_LOCAL_MACHINE, v22, 0x20019u);
      v5 = v18[0];
      if ( v11 )
      {
LABEL_8:
        v8 = -2147467259;
        goto LABEL_14;
      }
      ResourceString = GetResourceString(v18[0], &WindowName, a2);
      v13 = v8;
      if ( !ResourceString )
        v13 = -2147467259;
      v8 = v13;
    }
  }
LABEL_14:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 - 24) + 8LL))(*(_QWORD *)(v7 - 24));
  }
  v14 = v22 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
  }
  if ( v5 )
    RegCloseKey(v5);
  if ( v4 )
    RegCloseKey(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14006abf0  mov     [rsp-28h+arg_10], rbx
0x14006abf5  mov     [rsp-28h+arg_18], rsi
0x14006abfa  push    rbp
0x14006abfb  push    rdi
0x14006abfc  push    r12
0x14006abfe  push    r14
0x14006ac00  push    r15
0x14006ac02  mov     rbp, rsp
0x14006ac05  sub     rsp, 70h
0x14006ac09  mov     rax, cs:__security_cookie
0x14006ac10  xor     rax, rsp
0x14006ac13  mov     [rbp+var_8], rax
0x14006ac17  mov     r15, rdx
0x14006ac1a  mov     rdi, rcx
0x14006ac1d  xorps   xmm0, xmm0
0x14006ac20  movups  xmmword ptr [rbp+hKey], xmm0
0x14006ac24  xor     r12d, r12d
0x14006ac27  mov     esi, r12d
0x14006ac2a  mov     [rbp+hKey], r12
0x14006ac2e  mov     dword ptr [rbp+hKey+8], r12d
0x14006ac32  mov     [rbp+var_40], r12
0x14006ac36  movups  xmmword ptr [rbp+var_38], xmm0
0x14006ac3a  mov     r14d, r12d
0x14006ac3d  mov     [rbp+var_38], r12
0x14006ac41  mov     dword ptr [rbp+var_38+8], r12d
0x14006ac45  mov     [rbp+var_28], r12
0x14006ac49  mov     [rbp+lpsz], r12
0x14006ac4d  mov     [rbp+var_10], r12
0x14006ac51  lea     r8, aClsid_0; "\\CLSID\\"
0x14006ac58  lea     rdx, ?strRegistryRoot@detail@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> detail::strRegistryRoot
0x14006ac5f  lea     rcx, [rbp+var_10]
0x14006ac63  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14006ac68  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14006ac6d  mov     rcx, rax
0x14006ac70  test    rax, rax
0x14006ac73  jz      loc_14006AE06
0x14006ac79  mov     rax, [rax]
0x14006ac7c  call    qword ptr [rax+18h]
0x14006ac7f  lea     rbx, [rax+18h]
0x14006ac83  mov     [rbp+var_20], rbx
0x14006ac87  lea     rdx, [rbp+lpsz]; lplpsz
0x14006ac8b  mov     rcx, rdi; rclsid
0x14006ac8e  call    cs:__imp_StringFromCLSID
0x14006ac94  mov     edi, eax
0x14006ac96  test    eax, eax
0x14006ac98  js      loc_14006AD71
0x14006ac9e  mov     rdx, [rbp+lpsz]
0x14006aca2  test    rdx, rdx
0x14006aca5  jnz     short loc_14006ACAC
0x14006aca7  mov     r8d, r12d
0x14006acaa  jmp     short loc_14006ACBA
0x14006acac  or      r8, 0FFFFFFFFFFFFFFFFh
0x14006acb0  inc     r8
0x14006acb3  cmp     [rdx+r8*2], r12w
0x14006acb8  jnz     short loc_14006ACB0
0x14006acba  lea     rcx, [rbp+var_10]
0x14006acbe  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14006acc3  mov     r9d, 20019h; unsigned int
0x14006acc9  mov     r8, [rbp+var_10]; unsigned __int16 *
0x14006accd  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14006acd4  lea     rcx, [rbp+hKey]; this
0x14006acd8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14006acdd  mov     rsi, [rbp+hKey]
0x14006ace1  test    eax, eax
0x14006ace3  jz      short loc_14006ACEF
0x14006ace5  mov     edi, 80004005h
0x14006acea  jmp     loc_14006AD71
0x14006acef  mov     r8, r15; unsigned __int16 **
0x14006acf2  lea     rdx, aInprocserver32_0; "InProcServer32"
0x14006acf9  mov     rcx, rsi; hKey
0x14006acfc  call    ?GetResourceString@@YAHPEAUHKEY__@@PEBGPEAPEAG@Z; GetResourceString(HKEY__ *,ushort const *,ushort * *)
0x14006ad01  test    eax, eax
0x14006ad03  jnz     short loc_14006AD71
0x14006ad05  lea     r8d, [rax+1]
0x14006ad09  lea     rdx, SubBlock; "\\"
0x14006ad10  lea     rcx, [rbp+var_10]
0x14006ad14  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14006ad19  mov     r8d, 0Eh
0x14006ad1f  lea     rdx, aInprocserver32; "InprocServer32"
0x14006ad26  lea     rcx, [rbp+var_10]
0x14006ad2a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14006ad2f  mov     r9d, 20019h; unsigned int
0x14006ad35  mov     r8, [rbp+var_10]; unsigned __int16 *
0x14006ad39  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14006ad40  lea     rcx, [rbp+var_38]; this
0x14006ad44  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14006ad49  mov     r14, [rbp+var_38]
0x14006ad4d  test    eax, eax
0x14006ad4f  jnz     short loc_14006ACE5
0x14006ad51  mov     r8, r15; unsigned __int16 **
0x14006ad54  lea     rdx, WindowName; lpValueName
0x14006ad5b  mov     rcx, r14; hKey
0x14006ad5e  call    ?GetResourceString@@YAHPEAUHKEY__@@PEBGPEAPEAG@Z; GetResourceString(HKEY__ *,ushort const *,ushort * *)
0x14006ad63  mov     ecx, edi
0x14006ad65  mov     edi, 80004005h
0x14006ad6a  test    eax, eax
0x14006ad6c  cmovz   ecx, edi
0x14006ad6f  mov     edi, ecx
0x14006ad71  mov     rcx, [rbp+lpsz]; pv
0x14006ad75  test    rcx, rcx
0x14006ad78  jz      short loc_14006AD81
0x14006ad7a  call    cs:__imp_CoTaskMemFree
0x14006ad80  nop
0x14006ad81  lea     rdx, [rbx-18h]
0x14006ad85  or      eax, 0FFFFFFFFh
0x14006ad88  lock xadd [rdx+10h], eax
0x14006ad8d  sub     eax, 1
0x14006ad90  jg      short loc_14006ADA0
0x14006ad92  lfence
0x14006ad95  mov     rcx, [rdx]
0x14006ad98  mov     rax, [rcx]
0x14006ad9b  call    qword ptr [rax+8]
0x14006ad9e  nop
0x14006ad9f  nop
0x14006ada0  mov     rdx, [rbp+var_10]
0x14006ada4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14006ada8  or      eax, 0FFFFFFFFh
0x14006adab  lock xadd [rdx+10h], eax
0x14006adb0  sub     eax, 1
0x14006adb3  jg      short loc_14006ADC2
0x14006adb5  lfence
0x14006adb8  mov     rcx, [rdx]
0x14006adbb  mov     rax, [rcx]
0x14006adbe  call    qword ptr [rax+8]
0x14006adc1  nop
0x14006adc2  test    r14, r14
0x14006adc5  jz      short loc_14006ADD1
0x14006adc7  mov     rcx, r14; hKey
0x14006adca  call    cs:__imp_RegCloseKey
0x14006add0  nop
0x14006add1  test    rsi, rsi
0x14006add4  jz      short loc_14006ADDF
0x14006add6  mov     rcx, rsi; hKey
0x14006add9  call    cs:__imp_RegCloseKey
0x14006addf  mov     eax, edi
0x14006ade1  mov     rcx, [rbp+var_8]
0x14006ade5  xor     rcx, rsp; StackCookie
0x14006ade8  call    __security_check_cookie
0x14006aded  lea     r11, [rsp+70h+var_s0]
0x14006adf2  mov     rbx, [r11+40h]
0x14006adf6  mov     rsi, [r11+48h]
0x14006adfa  mov     rsp, r11
0x14006adfd  pop     r15
0x14006adff  pop     r14
0x14006ae01  pop     r12
0x14006ae03  pop     rdi
0x14006ae04  pop     rbp
0x14006ae05  retn
0x14006ae06  mov     ecx, 80004005h; int
0x14006ae0b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
