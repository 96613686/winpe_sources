# RasEapCreateUserProperties

- ea: `0x18001d950`
- end: `0x18001da61`
- name: `RasEapCreateUserProperties`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003ad0`
- `0x180003bd0`
- `0x180004690`
- `0x18000e500`
- `0x18001cbe4`
- `0x18001d950`

## pseudocode

```c
__int64 __fastcall RasEapCreateUserProperties(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        struct _EAPMSCHAPv2_CONN_PROPERTIES *a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8,
        struct _EAPMSCHAPv2_USER_PROPERTIES **a9,
        unsigned int *a10)
{
  _QWORD *v13; // rcx
  unsigned int UserProperties; // ebx
  const unsigned __int16 *v15; // rdx
  struct _EAPMSCHAPv2_USER_PROPERTIES *v17; // [rsp+28h] [rbp-60h]
  unsigned int v18; // [rsp+30h] [rbp-58h]
  struct IXMLDOMDocument2 *v19[7]; // [rsp+50h] [rbp-38h] BYREF

  v19[0] = 0;
  DebuggingInit(1);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    v13 = WPP_GLOBAL_Control;
  }
  if ( a1 == 26 )
  {
    if ( a9 && a10 && a4 )
    {
      *a9 = 0;
      *a10 = 0;
      UserProperties = CopyXmlDoc(a4, (LPVOID *)v19);
      if ( !UserProperties )
        UserProperties = MsChapV2CreateUserProperties(a2, v15, v19[0], a5, a6, v17, v18, a9, a10);
    }
    else
    {
      UserProperties = 160;
    }
  }
  else
  {
    if ( v13 != &WPP_GLOBAL_Control )
      WPP_SF_d(v13[2], 18, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    UserProperties = 50;
  }
  DebuggingInit(0);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)v19);
  return UserProperties;
}

```

## disassembly

```asm
0x18001d950  push    rbx
0x18001d952  push    rbp
0x18001d953  push    rsi
0x18001d954  push    rdi
0x18001d955  push    r14
0x18001d957  sub     rsp, 60h
0x18001d95b  mov     ebx, ecx
0x18001d95d  mov     [rsp+88h+var_38], 0
0x18001d966  mov     ecx, 1
0x18001d96b  mov     rbp, r9
0x18001d96e  mov     r14d, edx
0x18001d971  call    DebuggingInit
0x18001d976  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d97d  lea     rdi, WPP_GLOBAL_Control
0x18001d984  cmp     rcx, rdi
0x18001d987  jz      short loc_18001D9A8
0x18001d989  mov     rcx, [rcx+10h]
0x18001d98d  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001d994  mov     edx, 11h
0x18001d999  mov     r9d, ebx
0x18001d99c  call    WPP_SF_d
0x18001d9a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9a8  cmp     ebx, 1Ah
0x18001d9ab  jz      short loc_18001D9D1
0x18001d9ad  cmp     rcx, rdi
0x18001d9b0  jz      short loc_18001D9CA
0x18001d9b2  mov     rcx, [rcx+10h]
0x18001d9b6  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001d9bd  mov     edx, 12h
0x18001d9c2  mov     r9d, ebx
0x18001d9c5  call    WPP_SF_d
0x18001d9ca  mov     ebx, 32h ; '2'
0x18001d9cf  jmp     short loc_18001DA43
0x18001d9d1  mov     rdi, [rsp+88h+arg_40]
0x18001d9d9  test    rdi, rdi
0x18001d9dc  jz      short loc_18001DA3E
0x18001d9de  mov     rsi, [rsp+88h+arg_48]
0x18001d9e6  test    rsi, rsi
0x18001d9e9  jz      short loc_18001DA3E
0x18001d9eb  test    rbp, rbp
0x18001d9ee  jz      short loc_18001DA3E
0x18001d9f0  mov     qword ptr [rdi], 0
0x18001d9f7  lea     rdx, [rsp+88h+var_38]
0x18001d9fc  mov     rcx, rbp
0x18001d9ff  mov     dword ptr [rsi], 0
0x18001da05  call    ?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z; CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)
0x18001da0a  mov     ebx, eax
0x18001da0c  test    eax, eax
0x18001da0e  jnz     short loc_18001DA43
0x18001da10  mov     eax, [rsp+88h+arg_28]
0x18001da17  mov     ecx, r14d; unsigned int
0x18001da1a  mov     r9, [rsp+88h+arg_20]; struct _EAPMSCHAPv2_CONN_PROPERTIES *
0x18001da22  mov     r8, [rsp+88h+var_38]; struct IXMLDOMDocument2 *
0x18001da27  mov     [rsp+88h+var_48], rsi; unsigned int *
0x18001da2c  mov     [rsp+88h+var_50], rdi; struct _EAPMSCHAPv2_USER_PROPERTIES **
0x18001da31  mov     [rsp+88h+var_68], eax; unsigned int
0x18001da35  call    ?MsChapV2CreateUserProperties@@YAKKPEBGPEAUIXMLDOMDocument2@@PEAU_EAPMSCHAPv2_CONN_PROPERTIES@@KPEAU_EAPMSCHAPv2_USER_PROPERTIES@@KPEAPEAU3@PEAK@Z; MsChapV2CreateUserProperties(ulong,ushort const *,IXMLDOMDocument2 *,_EAPMSCHAPv2_CONN_PROPERTIES *,ulong,_EAPMSCHAPv2_USER_PROPERTIES *,ulong,_EAPMSCHAPv2_USER_PROPERTIES * *,ulong *)
0x18001da3a  mov     ebx, eax
0x18001da3c  jmp     short loc_18001DA43
0x18001da3e  mov     ebx, 0A0h
0x18001da43  xor     ecx, ecx
0x18001da45  call    DebuggingInit
0x18001da4a  lea     rcx, [rsp+88h+var_38]
0x18001da4f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001da54  mov     eax, ebx
0x18001da56  add     rsp, 60h
0x18001da5a  pop     r14
0x18001da5c  pop     rdi
0x18001da5d  pop     rsi
0x18001da5e  pop     rbp
0x18001da5f  pop     rbx
0x18001da60  retn
```
