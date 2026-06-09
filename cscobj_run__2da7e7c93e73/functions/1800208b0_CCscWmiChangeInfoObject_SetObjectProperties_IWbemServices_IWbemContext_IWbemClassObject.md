# CCscWmiChangeInfoObject::_SetObjectProperties(IWbemServices *,IWbemContext *,IWbemClassObject *)

- ea: `0x1800208b0`
- end: `0x180020bbd`
- name: `?_SetObjectProperties@CCscWmiChangeInfoObject@@MEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@@Z`
- size: `781`
- prototype: `int(CCscWmiChangeInfoObject *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800208b0`
- `0x180022dc4`
- `0x18002c010`

## string_xrefs

- `0x1800209ca`: `CreatedOffline`
- `0x18002098f`: `DeletedOffline`

## pseudocode

```c
__int64 __fastcall CCscWmiChangeInfoObject::_SetObjectProperties(
        CCscWmiChangeInfoObject *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemClassObject *a4)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-10h] BYREF
  int v15; // [rsp+50h] [rbp+20h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
  }
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
  v14 = 0;
  v7 = (**v6)(v6, &GUID_a96e6fa4_e0d1_4c29_960b_ee508fe68c72, &v14);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v15 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 24LL))(v14, &v15);
    v8 = v9;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_36;
      v11 = 34;
    }
    else
    {
      v8 = WmiProp_SetBooleanProperty(a4, L"Dirty", v15);
      if ( v8 < 0 )
        goto LABEL_36;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 32LL))(v14, &v15);
      v8 = v9;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_36;
        v11 = 35;
        goto LABEL_35;
      }
      v8 = WmiProp_SetBooleanProperty(a4, L"DeletedOffline", v15);
      if ( v8 < 0 )
        goto LABEL_36;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 40LL))(v14, &v15);
      v8 = v9;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_36;
        v11 = 36;
        goto LABEL_35;
      }
      v8 = WmiProp_SetBooleanProperty(a4, L"CreatedOffline", v15);
      if ( v8 < 0 )
        goto LABEL_36;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 48LL))(v14, &v15);
      v8 = v9;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_36;
        v11 = 37;
        goto LABEL_35;
      }
      v8 = WmiProp_SetBooleanProperty(a4, L"ModifiedData", v15);
      if ( v8 < 0 )
        goto LABEL_36;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 56LL))(v14, &v15);
      v8 = v9;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_36;
        v11 = 38;
        goto LABEL_35;
      }
      v8 = WmiProp_SetBooleanProperty(a4, L"ModifiedAttributes", v15);
      if ( v8 < 0 )
      {
LABEL_36:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_37:
        v12 = WPP_GLOBAL_Control;
        goto LABEL_38;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 64LL))(v14, &v15);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v8 = WmiProp_SetBooleanProperty(a4, L"ModifiedTime", v15);
        goto LABEL_36;
      }
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_36;
      v11 = 39;
    }
LABEL_35:
    WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v9);
    goto LABEL_36;
  }
  if ( v7 != -2147467262 )
    goto LABEL_37;
  v12 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  v8 = -2147024846;
LABEL_38:
  if ( (_UNKNOWN *)v12 != &WPP_GLOBAL_Control && (*(_DWORD *)(v12 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v12 + 16), 41, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800208b0  mov     [rsp-18h+arg_8], rbx
0x1800208b5  mov     [rsp-18h+arg_10], rsi
0x1800208ba  push    rbp
0x1800208bb  push    rdi
0x1800208bc  push    r14
0x1800208be  mov     rbp, rsp
0x1800208c1  sub     rsp, 30h
0x1800208c5  mov     rdi, r9
0x1800208c8  mov     rbx, rcx
0x1800208cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208d2  lea     rsi, WPP_GLOBAL_Control
0x1800208d9  lea     r14, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x1800208e0  cmp     rcx, rsi
0x1800208e3  jz      short loc_1800208FF
0x1800208e5  test    dword ptr [rcx+1Ch], 4000000h
0x1800208ec  jz      short loc_1800208FF
0x1800208ee  mov     rcx, [rcx+10h]
0x1800208f2  mov     edx, 21h ; '!'
0x1800208f7  mov     r8, r14
0x1800208fa  call    WPP_SF_
0x1800208ff  mov     rcx, [rbx+10h]
0x180020903  lea     r8, [rbp+var_10]
0x180020907  mov     [rbp+var_10], 0
0x18002090f  lea     rdx, _GUID_a96e6fa4_e0d1_4c29_960b_ee508fe68c72
0x180020916  mov     rax, [rcx]
0x180020919  mov     rax, [rax]
0x18002091c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020921  mov     ebx, eax
0x180020923  test    eax, eax
0x180020925  js      loc_180020B82
0x18002092b  mov     rcx, [rbp+var_10]
0x18002092f  lea     rdx, [rbp+arg_0]
0x180020933  mov     [rbp+arg_0], 0
0x18002093a  mov     rax, [rcx]
0x18002093d  mov     rax, [rax+18h]
0x180020941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020946  mov     ebx, eax
0x180020948  test    eax, eax
0x18002094a  js      loc_180020B0E
0x180020950  mov     r8d, [rbp+arg_0]; int
0x180020954  lea     rdx, CSCWMI_STR_PROP_DIRTY; "Dirty"
0x18002095b  mov     rcx, rdi; struct IWbemClassObject *
0x18002095e  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x180020963  mov     ebx, eax
0x180020965  test    eax, eax
0x180020967  js      loc_180020B34
0x18002096d  mov     rcx, [rbp+var_10]
0x180020971  lea     rdx, [rbp+arg_0]
0x180020975  mov     rax, [rcx]
0x180020978  mov     rax, [rax+20h]
0x18002097c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020981  mov     ebx, eax
0x180020983  test    eax, eax
0x180020985  js      loc_180020AF5
0x18002098b  mov     r8d, [rbp+arg_0]; int
0x18002098f  lea     rdx, CSCWMI_STR_PROP_DELETEDOFFLINE; "DeletedOffline"
0x180020996  mov     rcx, rdi; struct IWbemClassObject *
0x180020999  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x18002099e  mov     ebx, eax
0x1800209a0  test    eax, eax
0x1800209a2  js      loc_180020B34
0x1800209a8  mov     rcx, [rbp+var_10]
0x1800209ac  lea     rdx, [rbp+arg_0]
0x1800209b0  mov     rax, [rcx]
0x1800209b3  mov     rax, [rax+28h]
0x1800209b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209bc  mov     ebx, eax
0x1800209be  test    eax, eax
0x1800209c0  js      loc_180020ADC
0x1800209c6  mov     r8d, [rbp+arg_0]; int
0x1800209ca  lea     rdx, CSCWMI_STR_PROP_CREATEDOFFLINE; "CreatedOffline"
0x1800209d1  mov     rcx, rdi; struct IWbemClassObject *
0x1800209d4  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x1800209d9  mov     ebx, eax
0x1800209db  test    eax, eax
0x1800209dd  js      loc_180020B34
0x1800209e3  mov     rcx, [rbp+var_10]
0x1800209e7  lea     rdx, [rbp+arg_0]
0x1800209eb  mov     rax, [rcx]
0x1800209ee  mov     rax, [rax+30h]
0x1800209f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209f7  mov     ebx, eax
0x1800209f9  test    eax, eax
0x1800209fb  js      loc_180020AC3
0x180020a01  mov     r8d, [rbp+arg_0]; int
0x180020a05  lea     rdx, CSCWMI_STR_PROP_MODIFIEDDATA; "ModifiedData"
0x180020a0c  mov     rcx, rdi; struct IWbemClassObject *
0x180020a0f  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x180020a14  mov     ebx, eax
0x180020a16  test    eax, eax
0x180020a18  js      loc_180020B34
0x180020a1e  mov     rcx, [rbp+var_10]
0x180020a22  lea     rdx, [rbp+arg_0]
0x180020a26  mov     rax, [rcx]
0x180020a29  mov     rax, [rax+38h]
0x180020a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a32  mov     ebx, eax
0x180020a34  test    eax, eax
0x180020a36  js      short loc_180020AAA
0x180020a38  mov     r8d, [rbp+arg_0]; int
0x180020a3c  lea     rdx, CSCWMI_STR_PROP_MODIFIEDATTR; "ModifiedAttributes"
0x180020a43  mov     rcx, rdi; struct IWbemClassObject *
0x180020a46  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x180020a4b  mov     ebx, eax
0x180020a4d  test    eax, eax
0x180020a4f  js      loc_180020B34
0x180020a55  mov     rcx, [rbp+var_10]
0x180020a59  lea     rdx, [rbp+arg_0]
0x180020a5d  mov     rax, [rcx]
0x180020a60  mov     rax, [rax+40h]
0x180020a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a69  mov     ebx, eax
0x180020a6b  test    eax, eax
0x180020a6d  js      short loc_180020A89
0x180020a6f  mov     r8d, [rbp+arg_0]; int
0x180020a73  lea     rdx, CSCWMI_STR_PROP_MODIFIEDTIME; "ModifiedTime"
0x180020a7a  mov     rcx, rdi; struct IWbemClassObject *
0x180020a7d  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x180020a82  mov     ebx, eax
0x180020a84  jmp     loc_180020B34
0x180020a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a90  cmp     rcx, rsi
0x180020a93  jz      loc_180020B34
0x180020a99  test    byte ptr [rcx+1Ch], 2
0x180020a9d  jz      loc_180020B34
0x180020aa3  mov     edx, 27h ; '''
0x180020aa8  jmp     short loc_180020B25
0x180020aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ab1  cmp     rcx, rsi
0x180020ab4  jz      short loc_180020B34
0x180020ab6  test    byte ptr [rcx+1Ch], 2
0x180020aba  jz      short loc_180020B34
0x180020abc  mov     edx, 26h ; '&'
0x180020ac1  jmp     short loc_180020B25
0x180020ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180020aca  cmp     rcx, rsi
0x180020acd  jz      short loc_180020B34
0x180020acf  test    byte ptr [rcx+1Ch], 2
0x180020ad3  jz      short loc_180020B34
0x180020ad5  mov     edx, 25h ; '%'
0x180020ada  jmp     short loc_180020B25
0x180020adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ae3  cmp     rcx, rsi
0x180020ae6  jz      short loc_180020B34
0x180020ae8  test    byte ptr [rcx+1Ch], 2
0x180020aec  jz      short loc_180020B34
0x180020aee  mov     edx, 24h ; '$'
0x180020af3  jmp     short loc_180020B25
0x180020af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020afc  cmp     rcx, rsi
0x180020aff  jz      short loc_180020B34
0x180020b01  test    byte ptr [rcx+1Ch], 2
0x180020b05  jz      short loc_180020B34
0x180020b07  mov     edx, 23h ; '#'
0x180020b0c  jmp     short loc_180020B25
0x180020b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b15  cmp     rcx, rsi
0x180020b18  jz      short loc_180020B34
0x180020b1a  test    byte ptr [rcx+1Ch], 2
0x180020b1e  jz      short loc_180020B34
0x180020b20  mov     edx, 22h ; '"'
0x180020b25  mov     rcx, [rcx+10h]
0x180020b29  mov     r9d, eax
0x180020b2c  mov     r8, r14
0x180020b2f  call    WPP_SF_d
0x180020b34  mov     rcx, [rbp+var_10]
0x180020b38  mov     rax, [rcx]
0x180020b3b  mov     rax, [rax+10h]
0x180020b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b44  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b4b  cmp     rcx, rsi
0x180020b4e  jz      short loc_180020B6D
0x180020b50  test    dword ptr [rcx+1Ch], 4000000h
0x180020b57  jz      short loc_180020B6D
0x180020b59  mov     rcx, [rcx+10h]
0x180020b5d  mov     edx, 29h ; ')'
0x180020b62  mov     r9d, ebx
0x180020b65  mov     r8, r14
0x180020b68  call    WPP_SF_d
0x180020b6d  mov     rsi, [rsp+30h+arg_10]
0x180020b72  mov     eax, ebx
0x180020b74  mov     rbx, [rsp+30h+arg_8]
0x180020b79  add     rsp, 30h
0x180020b7d  pop     r14
0x180020b7f  pop     rdi
0x180020b80  pop     rbp
0x180020b81  retn
0x180020b82  cmp     eax, 80004002h
0x180020b87  jnz     short loc_180020B44
0x180020b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b90  cmp     rcx, rsi
0x180020b93  jz      short loc_180020BB6
0x180020b95  test    dword ptr [rcx+1Ch], 4000000h
0x180020b9c  jz      short loc_180020BB6
0x180020b9e  mov     rcx, [rcx+10h]
0x180020ba2  mov     edx, 28h ; '('
0x180020ba7  mov     r8, r14
0x180020baa  call    WPP_SF_
0x180020baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bb6  mov     ebx, 80070032h
0x180020bbb  jmp     short loc_180020B4B
```
