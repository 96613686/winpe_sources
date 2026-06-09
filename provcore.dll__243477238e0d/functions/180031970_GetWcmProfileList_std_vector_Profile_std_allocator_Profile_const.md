# GetWcmProfileList(std::vector<Profile,std::allocator<Profile>> const &)

- ea: `0x180031970`
- end: `0x180031bbc`
- name: `?GetWcmProfileList@@YA?AV?$shared_ptr@U_WCM_PROFILE_INFO_LIST@@@std@@AEBV?$vector@UProfile@@V?$allocator@UProfile@@@std@@@2@@Z`
- size: `588`
- prototype: `std::shared_ptr<_WCM_PROFILE_INFO_LIST> *__fastcall(std::shared_ptr<_WCM_PROFILE_INFO_LIST> *result, const std::vector<Profile> *profileList)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032790`

## callees

- `0x180008bd0`
- `0x18000af94`
- `0x180011844`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x180031044`
- `0x180031970`
- `0x180031cb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800319bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800319bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_WCM_PROFILE_INFO_LIST *__fastcall GetWcmProfileList(
        _WCM_PROFILE_INFO_LIST *result,
        const std::vector<Profile> *profileList)
{
  int v4; // esi
  _WCM_PROFILE_INFO_LIST *v5; // rax
  Profile *Myfirst; // r14
  Profile *Mylast; // r12
  _WCM_PROFILE_INFO_LIST *Ptr; // rdi
  const wchar_t *v9; // rax
  _GUID *v10; // r9
  int v11; // ecx
  int v12; // ecx
  const wchar_t *v13; // rdx
  const wchar_t *id; // rax
  unsigned __int16 v15; // dx
  const _GUID *v16; // r8
  unsigned __int64 v17; // r9
  std::shared_ptr<_WCM_PROFILE_INFO_LIST> wcmProfileList; // [rsp+30h] [rbp-78h] BYREF
  int v20; // [rsp+40h] [rbp-68h]
  std::wstring v21; // [rsp+48h] [rbp-60h] BYREF

  wcmProfileList._Ptr = result;
  v4 = 0;
  v20 = 0;
  v5 = (_WCM_PROFILE_INFO_LIST *)CoTaskMemAlloc(
                                   532
                                 * (0x8E38E38E38E38E39uLL
                                  * (((char *)profileList->_Mypair._Myval2._Mylast
                                    - (char *)profileList->_Mypair._Myval2._Myfirst) >> 3)
                                  - 1)
                                 + 536);
  if ( v5 )
  {
    wcmProfileList = 0;
    std::shared_ptr<_WCM_PROFILE_INFO_LIST>::shared_ptr<_WCM_PROFILE_INFO_LIST>(
      &wcmProfileList,
      v5,
      (void (__fastcall *)(void *))CoTaskMemFree);
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x11u, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids);
    }
    Myfirst = profileList->_Mypair._Myval2._Myfirst;
    Mylast = profileList->_Mypair._Myval2._Mylast;
    Ptr = wcmProfileList._Ptr;
    while ( Myfirst != Mylast )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Myfirst->Name._Mypair._Myval2);
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Myfirst->Name._Mypair._Myval2);
      std::_Copy_memmove<_GUID *,_GUID *>(
        v10,
        (_GUID *)&v9[Myfirst->Name._Mypair._Myval2._Mysize],
        (_GUID *)Ptr->ProfileInfo,
        (unsigned __int64)v10);
      Ptr->ProfileInfo[0].strProfileName[Myfirst->Name._Mypair._Myval2._Mysize] = 0;
      Ptr->ProfileInfo[0].AdapterGUID = Myfirst->InterfaceGuid;
      if ( Myfirst->MediaType )
      {
        if ( Myfirst->MediaType == MediaTypeWwan )
          v11 = 3;
        else
          v11 = 0;
      }
      else
      {
        v11 = 2;
      }
      Ptr->ProfileInfo[0].Media = v11;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        v12 = v11 - 2;
        if ( v12 )
        {
          if ( v12 == 1 )
            v13 = L"MBN";
          else
            v13 = L"UNKNOWN";
        }
        else
        {
          v13 = L"WLAN";
        }
        std::wstring::wstring(&v21, v13);
        v4 |= 6u;
        id = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v21._Mypair._Myval2);
        WPP_SF_S_guid_S(
          WPP_GLOBAL_Control->Control.Logger,
          v15,
          v16,
          Ptr->ProfileInfo[0].strProfileName,
          &Ptr->ProfileInfo[0].AdapterGUID,
          id);
      }
      if ( (v4 & 2) != 0 )
      {
        v4 &= ~2u;
        std::wstring::_Tidy_deallocate(&v21);
      }
      ++Myfirst;
    }
    v17 = 0x8E38E38E38E38E39uLL
        * (((char *)profileList->_Mypair._Myval2._Mylast - (char *)profileList->_Mypair._Myval2._Myfirst) >> 3);
    Ptr->dwNumberOfItems = v17;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x13u, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids, v17);
    }
    *(_QWORD *)&result->dwNumberOfItems = Ptr;
    *(_QWORD *)&result->ProfileInfo[0].strProfileName[2] = wcmProfileList._Rep;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x10u, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids);
    }
    *(_QWORD *)&result->dwNumberOfItems = 0;
    *(_QWORD *)&result->ProfileInfo[0].strProfileName[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180031970  mov     [rsp+arg_10], rbx
0x180031975  push    rbp
0x180031976  push    rsi
0x180031977  push    rdi
0x180031978  push    r12
0x18003197a  push    r13
0x18003197c  push    r14
0x18003197e  push    r15
0x180031980  sub     rsp, 70h
0x180031984  mov     r15, profileList
0x180031987  mov     rbx, rcx
0x18003198a  mov     [rsp+0A8h+wcmProfileList._Ptr], rcx
0x18003198f  xor     esi, esi
0x180031991  mov     [rsp+0A8h+var_68], esi
0x180031995  mov     rax, [profileList+8]
0x180031999  sub     rax, [profileList]
0x18003199c  sar     rax, 3
0x1800319a0  mov     rcx, 8E38E38E38E38E39h
0x1800319aa  imul    rax, rcx
0x1800319ae  dec     rax
0x1800319b1  imul    rcx, rax, 214h
0x1800319b8  add     rcx, 218h; cb
0x1800319bf  call    cs:__imp_CoTaskMemAlloc
0x1800319c5  test    rax, rax
0x1800319c8  jnz     short loc_180031A02
0x1800319ca  lea     rbp, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800319d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319d8  cmp     rcx, rbp
0x1800319db  jz      short loc_1800319F6
0x1800319dd  test    byte ptr [rcx+1Ch], 2
0x1800319e1  jz      short loc_1800319F6
0x1800319e3  lea     edx, [rsi+10h]; id
0x1800319e6  lea     r8, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids; TraceGuid
0x1800319ed  mov     rcx, [rcx+10h]; Logger
0x1800319f1  call    WPP_SF_
0x1800319f6  mov     [rbx], rsi
0x1800319f9  mov     [rbx+8], rsi
0x1800319fd  jmp     loc_180031BA1
0x180031a02  xorps   xmm0, xmm0
0x180031a05  movups  xmmword ptr [rsp+0A8h+wcmProfileList._Ptr], xmm0
0x180031a0a  mov     r8, cs:__imp_CoTaskMemFree; _Dt
0x180031a11  mov     profileList, rax; _Px
0x180031a14  lea     rcx, [rsp+0A8h+wcmProfileList]; this
0x180031a19  call    ??$?0U_WCM_PROFILE_INFO_LIST@@P6AXPEAX@Z$0A@@?$shared_ptr@U_WCM_PROFILE_INFO_LIST@@@std@@QEAA@PEAU_WCM_PROFILE_INFO_LIST@@P6AXPEAX@Z@Z; std::shared_ptr<_WCM_PROFILE_INFO_LIST>::shared_ptr<_WCM_PROFILE_INFO_LIST>(_WCM_PROFILE_INFO_LIST *,void (*)(void *))
0x180031a1e  nop
0x180031a1f  lea     rbp, WPP_GLOBAL_Control; __annotation("TMF:",
0x180031a26  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a2d  cmp     rcx, rbp
0x180031a30  jz      short loc_180031A4D
0x180031a32  test    byte ptr [rcx+1Ch], 10h
0x180031a36  jz      short loc_180031A4D
0x180031a38  mov     edx, 11h; id
0x180031a3d  lea     r8, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids; TraceGuid
0x180031a44  mov     rcx, [rcx+10h]; Logger
0x180031a48  call    WPP_SF_
0x180031a4d  mov     r14, [r15]
0x180031a50  mov     r12, [r15+8]
0x180031a54  mov     rdi, [rsp+0A8h+wcmProfileList._Ptr]
0x180031a59  jmp     loc_180031B49
0x180031a5e  lea     rcx, [r14+8]; this
0x180031a62  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031a67  mov     r9, rax
0x180031a6a  lea     rcx, [r14+8]; this
0x180031a6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031a73  mov     rcx, [r14+18h]
0x180031a77  lea     profileList, [rax+rcx*2]; _Last
0x180031a7b  lea     r8, [rdi+4]; _Dest
0x180031a7f  mov     rcx, r9; _First
0x180031a82  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180031a87  mov     rcx, [r14+18h]
0x180031a8b  xor     eax, eax
0x180031a8d  mov     [rdi+rcx*2+4], ax
0x180031a92  movups  xmm0, xmmword ptr [r14+28h]
0x180031a97  movdqu  xmmword ptr [rdi+204h], xmm0
0x180031a9f  mov     ecx, [r14]
0x180031aa2  test    ecx, ecx
0x180031aa4  jz      short loc_180031AB6
0x180031aa6  cmp     ecx, 1
0x180031aa9  jz      short loc_180031AAF
0x180031aab  xor     ecx, ecx
0x180031aad  jmp     short loc_180031ABB
0x180031aaf  mov     ecx, 3
0x180031ab4  jmp     short loc_180031ABB
0x180031ab6  mov     ecx, 2
0x180031abb  mov     [rdi+214h], ecx
0x180031ac1  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180031ac8  cmp     rax, rbp
0x180031acb  jz      short loc_180031B32
0x180031acd  test    byte ptr [rax+1Ch], 10h
0x180031ad1  jz      short loc_180031B32
0x180031ad3  sub     ecx, 2
0x180031ad6  jz      short loc_180031AEF
0x180031ad8  cmp     ecx, 1
0x180031adb  jz      short loc_180031AE6
0x180031add  lea     profileList, aUnknown; "UNKNOWN"
0x180031ae4  jmp     short loc_180031AF6
0x180031ae6  lea     profileList, PrefixString; "MBN"
0x180031aed  jmp     short loc_180031AF6
0x180031aef  lea     profileList, aWlan_0; "WLAN"
0x180031af6  lea     rcx, [rsp+0A8h+var_60]; this
0x180031afb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180031b00  or      esi, 6
0x180031b03  lea     rcx, [rsp+0A8h+var_60]; this
0x180031b08  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031b0d  lea     rcx, [rdi+204h]
0x180031b14  mov     [rsp+0A8h+id], rax; id
0x180031b19  mov     [rsp+0A8h+Logger], rcx; Logger
0x180031b1e  lea     r9, [rdi+4]; _a3
0x180031b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b29  mov     rcx, [rcx+10h]; Logger
0x180031b2d  call    WPP_SF_S_guid_S
0x180031b32  test    sil, 2
0x180031b36  jz      short loc_180031B45
0x180031b38  and     esi, 0FFFFFFFDh
0x180031b3b  lea     rcx, [rsp+0A8h+var_60]; this
0x180031b40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031b45  add     r14, 48h ; 'H'
0x180031b49  cmp     r14, r12
0x180031b4c  jnz     loc_180031A5E
0x180031b52  mov     r9, [r15+8]
0x180031b56  sub     r9, [r15]
0x180031b59  sar     r9, 3
0x180031b5d  mov     rax, 8E38E38E38E38E39h
0x180031b67  imul    r9, rax; _a1
0x180031b6b  mov     [rdi], r9d
0x180031b6e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180031b75  cmp     rcx, rbp
0x180031b78  jz      short loc_180031B95
0x180031b7a  test    byte ptr [rcx+1Ch], 10h
0x180031b7e  jz      short loc_180031B95
0x180031b80  mov     edx, 13h; id
0x180031b85  lea     r8, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids; TraceGuid
0x180031b8c  mov     rcx, [rcx+10h]; Logger
0x180031b90  call    WPP_SF_d
0x180031b95  mov     [rbx], rdi
0x180031b98  mov     rax, [rsp+0A8h+wcmProfileList._Rep]
0x180031b9d  mov     [rbx+8], rax
0x180031ba1  mov     rax, rbx
0x180031ba4  mov     rbx, [rsp+0A8h+arg_10]
0x180031bac  add     rsp, 70h
0x180031bb0  pop     r15
0x180031bb2  pop     r14
0x180031bb4  pop     r13
0x180031bb6  pop     r12
0x180031bb8  pop     rdi
0x180031bb9  pop     rsi
0x180031bba  pop     rbp
0x180031bbb  retn
```
