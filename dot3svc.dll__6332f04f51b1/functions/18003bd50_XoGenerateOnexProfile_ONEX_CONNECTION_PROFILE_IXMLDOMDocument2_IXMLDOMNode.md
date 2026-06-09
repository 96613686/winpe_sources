# XoGenerateOnexProfile(_ONEX_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x18003bd50`
- end: `0x18003bf67`
- name: `?XoGenerateOnexProfile@@YAKPEAU_ONEX_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `535`
- prototype: `unsigned int __fastcall(struct _ONEX_CONNECTION_PROFILE *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033ae0`

## callees

- `0x1800326fc`
- `0x18003aa34`
- `0x18003acc4`
- `0x18003acfc`
- `0x18003ada8`
- `0x18003bd50`
- `0x18003c2e0`
- `0x18003c52c`

## string_xrefs

- `0x18003bd7f`: `http://www.microsoft.com/networking/OneX/v1`
- `0x18003bdb0`: `http://www.microsoft.com/networking/OneX/v1`
- `0x18003bec5`: `http://www.microsoft.com/networking/OneX/v1`
- `0x18003bf05`: `http://www.microsoft.com/networking/OneX/v1`
- `0x18003bdb9`: `cacheUserData`

## pseudocode

```c
__int64 __fastcall XoGenerateOnexProfile(
        struct _ONEX_CONNECTION_PROFILE *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  unsigned int SingleSignOn; // esi
  const unsigned __int16 *v6; // r9
  struct IXMLDOMNode *v7; // rbx
  struct IXMLDOMNode **v9; // [rsp+28h] [rbp-40h]
  struct IXMLDOMNode **v10; // [rsp+38h] [rbp-30h]
  struct IXMLDOMNode *v11; // [rsp+88h] [rbp+20h] BYREF

  v11 = 0;
  SingleSignOn = XcAddChildElement(
                   a2,
                   a3,
                   (OLECHAR *)L"OneX",
                   (OLECHAR *)L"http://www.microsoft.com/networking/OneX/v1",
                   0,
                   &v11);
  if ( !SingleSignOn )
  {
    v7 = v11;
    if ( ((*((_BYTE *)a1 + 8) & 1) == 0
       || (SingleSignOn = XcAddChildElementBoolean(
                            a2,
                            v11,
                            L"cacheUserData",
                            L"http://www.microsoft.com/networking/OneX/v1",
                            (*((_DWORD *)a1 + 3) & 2) == 0,
                            v9)) == 0)
      && ((*((_BYTE *)a1 + 8) & 8) == 0
       || (SingleSignOn = XcAddChildElementDWORD(a2, v7, (OLECHAR *)L"heldPeriod", v6, *((_DWORD *)a1 + 6), v9)) == 0)
      && ((*((_BYTE *)a1 + 8) & 0x10) == 0
       || (SingleSignOn = XcAddChildElementDWORD(a2, v7, (OLECHAR *)L"authPeriod", v6, *((_DWORD *)a1 + 7), v9)) == 0)
      && ((*((_BYTE *)a1 + 8) & 0x20) == 0
       || (SingleSignOn = XcAddChildElementDWORD(a2, v7, (OLECHAR *)L"startPeriod", v6, *((_DWORD *)a1 + 8), v9)) == 0)
      && ((*((_BYTE *)a1 + 8) & 0x40) == 0
       || (SingleSignOn = XcAddChildElementDWORD(a2, v7, (OLECHAR *)L"maxStart", v6, *((_DWORD *)a1 + 9), v9)) == 0)
      && (*((char *)a1 + 8) >= 0
       || (SingleSignOn = XcAddChildElementDWORD(a2, v7, (OLECHAR *)L"maxAuthFailures", v6, *((_DWORD *)a1 + 10), v9)) == 0)
      && ((*((_BYTE *)a1 + 8) & 2) == 0
       || (SingleSignOn = XcAddChildElementEnum(
                            a2,
                            v7,
                            (OLECHAR *)L"supplicantMode",
                            (OLECHAR *)L"http://www.microsoft.com/networking/OneX/v1",
                            *((_DWORD *)a1 + 4),
                            (const struct _XC_STRING_VALUE_MAPPING *)&off_180042520,
                            3u,
                            v10)) == 0)
      && ((*((_BYTE *)a1 + 8) & 4) == 0
       || (SingleSignOn = XcAddChildElementEnum(
                            a2,
                            v7,
                            (OLECHAR *)L"authMode",
                            (OLECHAR *)L"http://www.microsoft.com/networking/OneX/v1",
                            *((_DWORD *)a1 + 5),
                            (const struct _XC_STRING_VALUE_MAPPING *)&off_1800424E0,
                            4u,
                            v10)) == 0) )
    {
      SingleSignOn = XopGenerateSingleSignOn(a1, a2, v7);
      if ( !SingleSignOn )
        SingleSignOn = XopGenerateEapConfig(a1, a2, v7);
    }
  }
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)&v11);
  return SingleSignOn;
}

```

## disassembly

```asm
0x18003bd50  mov     r11, rsp
0x18003bd53  push    rbx
0x18003bd54  push    rbp
0x18003bd55  push    rsi
0x18003bd56  push    rdi
0x18003bd57  sub     rsp, 48h
0x18003bd5b  mov     rdi, rcx
0x18003bd5e  mov     qword ptr [r11+20h], 0
0x18003bd66  lea     rcx, [r11+20h]
0x18003bd6a  mov     rax, r8
0x18003bd6d  mov     rbp, rdx
0x18003bd70  mov     [r11-40h], rcx
0x18003bd74  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003bd77  mov     qword ptr [r11-48h], 0
0x18003bd7f  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003bd86  mov     rdx, rax; struct IXMLDOMNode *
0x18003bd89  lea     r8, aOnex; "OneX"
0x18003bd90  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18003bd95  mov     esi, eax
0x18003bd97  test    eax, eax
0x18003bd99  jnz     loc_18003BF4F
0x18003bd9f  test    byte ptr [rdi+8], 1
0x18003bda3  mov     rbx, [rsp+68h+arg_18]
0x18003bdab  jz      short loc_18003BDDE
0x18003bdad  mov     eax, [rdi+0Ch]
0x18003bdb0  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003bdb7  shr     eax, 1
0x18003bdb9  lea     r8, aCacheuserdata; "cacheUserData"
0x18003bdc0  not     eax
0x18003bdc2  mov     rdx, rbx; struct IXMLDOMNode *
0x18003bdc5  and     eax, 1
0x18003bdc8  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003bdcb  mov     [rsp+68h+var_48], eax; int
0x18003bdcf  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x18003bdd4  mov     esi, eax
0x18003bdd6  test    eax, eax
0x18003bdd8  jnz     loc_18003BF4F
0x18003bdde  test    byte ptr [rdi+8], 8
0x18003bde2  jz      short loc_18003BE07
0x18003bde4  mov     eax, [rdi+18h]
0x18003bde7  lea     r8, aHeldperiod; "heldPeriod"
0x18003bdee  mov     rdx, rbx; struct IXMLDOMNode *
0x18003bdf1  mov     [rsp+68h+var_48], eax; unsigned int
0x18003bdf5  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003bdf8  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18003bdfd  mov     esi, eax
0x18003bdff  test    eax, eax
0x18003be01  jnz     loc_18003BF4F
0x18003be07  test    byte ptr [rdi+8], 10h
0x18003be0b  jz      short loc_18003BE30
0x18003be0d  mov     eax, [rdi+1Ch]
0x18003be10  lea     r8, aAuthperiod; "authPeriod"
0x18003be17  mov     rdx, rbx; struct IXMLDOMNode *
0x18003be1a  mov     [rsp+68h+var_48], eax; unsigned int
0x18003be1e  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003be21  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18003be26  mov     esi, eax
0x18003be28  test    eax, eax
0x18003be2a  jnz     loc_18003BF4F
0x18003be30  test    byte ptr [rdi+8], 20h
0x18003be34  jz      short loc_18003BE59
0x18003be36  mov     eax, [rdi+20h]
0x18003be39  lea     r8, aStartperiod; "startPeriod"
0x18003be40  mov     rdx, rbx; struct IXMLDOMNode *
0x18003be43  mov     [rsp+68h+var_48], eax; unsigned int
0x18003be47  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003be4a  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18003be4f  mov     esi, eax
0x18003be51  test    eax, eax
0x18003be53  jnz     loc_18003BF4F
0x18003be59  test    byte ptr [rdi+8], 40h
0x18003be5d  jz      short loc_18003BE82
0x18003be5f  mov     eax, [rdi+24h]
0x18003be62  lea     r8, aMaxstart; "maxStart"
0x18003be69  mov     rdx, rbx; struct IXMLDOMNode *
0x18003be6c  mov     [rsp+68h+var_48], eax; unsigned int
0x18003be70  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003be73  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18003be78  mov     esi, eax
0x18003be7a  test    eax, eax
0x18003be7c  jnz     loc_18003BF4F
0x18003be82  test    byte ptr [rdi+8], 80h
0x18003be86  jz      short loc_18003BEAB
0x18003be88  mov     eax, [rdi+28h]
0x18003be8b  lea     r8, aMaxauthfailure; "maxAuthFailures"
0x18003be92  mov     rdx, rbx; struct IXMLDOMNode *
0x18003be95  mov     [rsp+68h+var_48], eax; unsigned int
0x18003be99  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003be9c  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18003bea1  mov     esi, eax
0x18003bea3  test    eax, eax
0x18003bea5  jnz     loc_18003BF4F
0x18003beab  test    byte ptr [rdi+8], 2
0x18003beaf  jz      short loc_18003BEEB
0x18003beb1  lea     rax, off_180042520; "inhibitTransmission"
0x18003beb8  mov     [rsp+68h+var_38], 3; unsigned int
0x18003bec0  mov     [rsp+68h+var_40], rax; struct _XC_STRING_VALUE_MAPPING *
0x18003bec5  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003becc  mov     eax, [rdi+10h]
0x18003becf  lea     r8, aSupplicantmode; "supplicantMode"
0x18003bed6  mov     rdx, rbx; struct IXMLDOMNode *
0x18003bed9  mov     [rsp+68h+var_48], eax; unsigned int
0x18003bedd  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003bee0  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18003bee5  mov     esi, eax
0x18003bee7  test    eax, eax
0x18003bee9  jnz     short loc_18003BF4F
0x18003beeb  test    byte ptr [rdi+8], 4
0x18003beef  jz      short loc_18003BF2B
0x18003bef1  lea     rax, off_1800424E0; "machineOrUser"
0x18003bef8  mov     [rsp+68h+var_38], 4; unsigned int
0x18003bf00  mov     [rsp+68h+var_40], rax; struct _XC_STRING_VALUE_MAPPING *
0x18003bf05  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003bf0c  mov     eax, [rdi+14h]
0x18003bf0f  lea     r8, aAuthmode; "authMode"
0x18003bf16  mov     rdx, rbx; struct IXMLDOMNode *
0x18003bf19  mov     [rsp+68h+var_48], eax; unsigned int
0x18003bf1d  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003bf20  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18003bf25  mov     esi, eax
0x18003bf27  test    eax, eax
0x18003bf29  jnz     short loc_18003BF4F
0x18003bf2b  mov     r8, rbx; struct IXMLDOMNode *
0x18003bf2e  mov     rdx, rbp; struct IXMLDOMDocument2 *
0x18003bf31  mov     rcx, rdi; struct _ONEX_CONNECTION_PROFILE *
0x18003bf34  call    ?XopGenerateSingleSignOn@@YAKPEAU_ONEX_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XopGenerateSingleSignOn(_ONEX_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x18003bf39  mov     esi, eax
0x18003bf3b  test    eax, eax
0x18003bf3d  jnz     short loc_18003BF4F
0x18003bf3f  mov     r8, rbx; struct IXMLDOMNode *
0x18003bf42  mov     rdx, rbp; struct IXMLDOMDocument2 *
0x18003bf45  mov     rcx, rdi; struct _ONEX_CONNECTION_PROFILE *
0x18003bf48  call    ?XopGenerateEapConfig@@YAKPEAU_ONEX_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XopGenerateEapConfig(_ONEX_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x18003bf4d  mov     esi, eax
0x18003bf4f  lea     rcx, [rsp+68h+arg_18]
0x18003bf57  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003bf5c  mov     eax, esi
0x18003bf5e  add     rsp, 48h
0x18003bf62  pop     rdi
0x18003bf63  pop     rsi
0x18003bf64  pop     rbp
0x18003bf65  pop     rbx
0x18003bf66  retn
```
