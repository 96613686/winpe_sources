# CWebDriverHost::HandleWebDriverCommand(ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x180065cd0`
- end: `0x180066154`
- name: `?HandleWebDriverCommand@CWebDriverHost@@UEAAJKPEBG00@Z`
- size: `1156`
- prototype: `int(CWebDriverHost *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180018b30`
- `0x18001c3a0`
- `0x18002343c`
- `0x18002b5a0`
- `0x180064dd4`
- `0x180065184`
- `0x180065cd0`
- `0x180066a44`
- `0x180066a88`
- `0x180066d24`
- `0x180066ecc`
- `0x180066fb0`
- `0x18006709c`
- `0x1800671bc`
- `0x180067260`
- `0x180067440`
- `0x18007cdc8`
- `0x18007cfec`
- `0x180085010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180065feb`
- `OLEAUT32!__imp_SysAllocString` at `0x180065ff7`
- `OLEAUT32!__imp_SysAllocString` at `0x180066004`
- `OLEAUT32!__imp_SysAllocString` at `0x180065feb`
- `OLEAUT32!__imp_SysAllocString` at `0x180065ff7`
- `OLEAUT32!__imp_SysAllocString` at `0x180066004`
- `OLEAUT32!__imp_SysFreeString` at `0x180066055`
- `OLEAUT32!__imp_SysFreeString` at `0x180066063`
- `OLEAUT32!__imp_SysFreeString` at `0x180066071`
- `OLEAUT32!__imp_SysFreeString` at `0x180066055`
- `OLEAUT32!__imp_SysFreeString` at `0x180066063`
- `OLEAUT32!__imp_SysFreeString` at `0x180066071`
- `edgeIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180065f71`
- `edgeIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180065f71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800660b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800660b1`

## pseudocode

```c
__int64 __fastcall CWebDriverHost::HandleWebDriverCommand(
        CWebDriverHost *this,
        unsigned int a2,
        OLECHAR *a3,
        const unsigned __int16 *a4,
        OLECHAR *a5)
{
  int WindowHandles; // edi
  int WindowId; // ebx
  void *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  const unsigned __int16 *v14; // rdx
  char *v15; // rax
  signed __int64 v16; // r10
  __int64 v17; // rcx
  const char *v18; // r9
  int v19; // r15d
  CWebDriverHost *v20; // rcx
  unsigned __int16 *v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // r12d
  OLECHAR *v25; // rdi
  OLECHAR *v26; // rbx
  OLECHAR *v27; // rsi
  int v28; // eax
  int v29; // ecx
  unsigned int v30; // r8d
  unsigned int v32; // r8d
  LPVOID pv; // [rsp+40h] [rbp-30h] BYREF
  int v34; // [rsp+48h] [rbp-28h] BYREF
  __int64 v35; // [rsp+50h] [rbp-20h]
  __int64 v36; // [rsp+58h] [rbp-18h]
  __int64 v37; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v39; // [rsp+B0h] [rbp+40h] BYREF
  OLECHAR *psz; // [rsp+C0h] [rbp+50h]

  psz = a3;
  WindowHandles = 0;
  pv = 0;
  WindowId = 40;
  if ( !*((_QWORD *)this + 13) )
  {
    v11 = operator new(0x28u);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>>>(v11);
    *(_DWORD *)(v12 + 32) = 0;
    *((_QWORD *)this + 13) = v12;
    RegisterAllEndpoints((struct CWebDriverEndpointMapping *)v12);
  }
  CWebDriverEndpointMapping::ParseRequest(*((_QWORD *)this + 13), &v34, a3, a4);
  if ( v34 == 75 )
  {
    CWebDriverHost::_CreateNewSession((void ***)this - 6, a5, a2);
    goto LABEL_74;
  }
  v13 = v35;
  v14 = 0;
  while ( v13 != v36 )
  {
    if ( *(_DWORD *)v13 == 7 )
    {
      v14 = (const unsigned __int16 *)(v13 + 8);
      if ( *(_QWORD *)(v13 + 32) > 7u )
        v14 = *(const unsigned __int16 **)v14;
      break;
    }
    v13 += 40;
  }
  if ( !*((_BYTE *)this + 144) )
    goto LABEL_81;
  v15 = (char *)*((_QWORD *)this + 16);
  v16 = (char *)v14 - v15;
  do
  {
    v17 = *(unsigned __int16 *)&v15[v16];
    v18 = (const char *)(*(unsigned __int16 *)v15 - (unsigned int)v17);
    if ( (_DWORD)v18 )
      break;
    v15 += 2;
  }
  while ( (_DWORD)v17 );
  if ( (_DWORD)v18 )
  {
LABEL_81:
    WindowId = 6;
    goto LABEL_82;
  }
  v19 = 0;
  if ( v34 <= 73 )
  {
    if ( v34 == 73 )
      goto LABEL_57;
    if ( v34 <= 26 )
    {
      if ( v34 != 26 && v34 != 5 )
      {
        if ( v34 != 8 )
        {
          if ( v34 != 22 )
          {
            if ( v34 != 23 && (unsigned int)(v34 - 24) >= 2 )
              goto LABEL_58;
            goto LABEL_57;
          }
          v19 = *((_DWORD *)this + 30);
LABEL_58:
          v24 = CWebDriverHost::_UpdateAndEnsureCurrentCoreWebViewPrivate((char *)this - 48, 0);
          if ( v24 )
          {
            WindowId = 23;
          }
          else
          {
            v25 = SysAllocString(psz);
            v26 = SysAllocString(a4);
            v27 = SysAllocString(a5);
            v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, OLECHAR *, OLECHAR *, OLECHAR *, int))(**((_QWORD **)this + 10)
                                                                                                  + 528LL))(
                    *((_QWORD *)this + 10),
                    a2,
                    v25,
                    v26,
                    v27,
                    v19);
            if ( v28 == -2147019873 )
              v24 = 23;
            v29 = 0;
            if ( v28 != -2147019873 )
              v29 = v28;
            v39 = v29;
            if ( v27 )
              SysFreeString(v27);
            if ( v26 )
              SysFreeString(v26);
            if ( v25 )
              SysFreeString(v25);
            WindowHandles = v39;
            WindowId = v24;
            if ( v24 != 23 )
            {
LABEL_70:
              if ( WindowHandles >= 0 )
                goto LABEL_74;
              goto LABEL_71;
            }
          }
          v32 = 23;
LABEL_79:
          CWebDriverHost::_ReplyToWebDriverServer(
            (CWebDriverHost *)((char *)this - 48),
            a2,
            v32,
            (const unsigned __int16 *)pv,
            0);
          goto LABEL_70;
        }
LABEL_82:
        v32 = WindowId;
        goto LABEL_79;
      }
LABEL_57:
      v19 = *((_DWORD *)this + 28);
      goto LABEL_58;
    }
    if ( v34 == 29 )
    {
LABEL_31:
      v19 = *((_DWORD *)this + 29);
      goto LABEL_58;
    }
    if ( v34 == 60 )
    {
      WindowId = CWebDriverHost::_UpdateAndEnsureCurrentCoreWebViewPrivate((char *)this - 48, 0);
      if ( !WindowId )
      {
        v21 = CWebDriverHost::_ConvertCoreWebViewPrivateIdToWindowHandle(v20, *((_DWORD *)this + 18));
        v22 = *((_QWORD *)this + 12);
        pv = v21;
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _BYTE, unsigned __int16 *))(*(_QWORD *)v22 + 64LL))(
          v22,
          a2,
          0,
          8,
          0,
          v21);
        goto LABEL_74;
      }
      goto LABEL_82;
    }
    if ( v34 != 61 )
    {
      if ( (unsigned int)(v34 - 64) > 1 )
        goto LABEL_58;
      goto LABEL_31;
    }
    WindowHandles = CWebDriverHost::_GetWindowHandles((CWebDriverHost *)((char *)this - 48), (unsigned __int16 **)&pv);
    if ( WindowHandles < 0 )
    {
LABEL_71:
      v30 = 13;
      if ( WindowId )
        v30 = WindowId;
      CWebDriverHost::_ReplyToWebDriverServer((CWebDriverHost *)((char *)this - 48), a2, v30, 0, 0);
      goto LABEL_74;
    }
LABEL_44:
    WindowId = 0;
    goto LABEL_82;
  }
  if ( v34 > 98 )
  {
    if ( v34 != 99 && v34 != 100 )
    {
      if ( v34 == 144 )
        goto LABEL_57;
      if ( v34 != 147 )
      {
        if ( v34 != 148 )
          goto LABEL_58;
        goto LABEL_57;
      }
    }
    v23 = CWebDriverHost::_SetTimeoutJWP((char *)this - 48, a5);
    goto LABEL_47;
  }
  if ( v34 == 98 )
  {
    v23 = CWebDriverHost::_SetTimeout((__int64)this - 48, (__int64)a5, (unsigned __int16 **)&pv);
    goto LABEL_47;
  }
  if ( v34 != 76 )
  {
    if ( v34 == 77 )
      goto LABEL_31;
    if ( v34 == 79 )
      goto LABEL_57;
    if ( v34 != 94 )
    {
      if ( v34 != 97 )
        goto LABEL_58;
      CWebDriverHost::_GetTimeouts((CWebDriverHost *)((char *)this - 48), v14, (unsigned __int16 **)&pv);
      goto LABEL_44;
    }
    v39 = 0;
    WindowId = CWebDriverHost::_GetWindowId(v17, a5, &v39);
    if ( WindowId )
      goto LABEL_82;
    v23 = CWebDriverHost::_UpdateAndEnsureCurrentCoreWebViewPrivate((char *)this - 48, &v39);
LABEL_47:
    WindowId = v23;
    goto LABEL_82;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 31, 1, 0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x323,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverhost.cxx",
      v18);
  CWebDriverHost::_DisconnectAllCoreWebViewPrivate((CWebDriverHost *)((char *)this - 48));
  CWebDriverHost::_ReplyToWebDriverServer((CWebDriverHost *)((char *)this - 48), a2, 0, 0, 1);
  LCIEPostMessageWithoutBuffer(
    *(_DWORD *)(*((_QWORD *)this + 12) + 28LL),
    *(_DWORD *)(*((_QWORD *)this + 12) + 28LL),
    0xD87u,
    0);
LABEL_74:
  CoTaskMemFree(pv);
  if ( v35 )
  {
    std::_Destroy_range<std::allocator<std::pair<enum WebDriverPathVariable,std::wstring>>>(v35, v36);
    std::_Deallocate<16>(v35, 8 * ((v37 - v35) >> 3));
  }
  return (unsigned int)WindowHandles;
}

```

## disassembly

```asm
0x180065cd0  mov     [rsp-38h+arg_8], rbx
0x180065cd5  mov     [rsp-38h+psz], r8
0x180065cda  push    rbp
0x180065cdb  push    rsi
0x180065cdc  push    rdi
0x180065cdd  push    r12
0x180065cdf  push    r13
0x180065ce1  push    r14
0x180065ce3  push    r15
0x180065ce5  mov     rbp, rsp
0x180065ce8  sub     rsp, 70h
0x180065cec  xor     r12d, r12d
0x180065cef  mov     rsi, r9
0x180065cf2  mov     r15, r8
0x180065cf5  mov     r13d, edx
0x180065cf8  mov     r14, rcx
0x180065cfb  mov     edi, r12d
0x180065cfe  mov     [rbp+pv], r12
0x180065d02  lea     ebx, [r12+28h]
0x180065d07  cmp     [rcx+68h], r12
0x180065d0b  jnz     short loc_180065D29
0x180065d0d  mov     ecx, ebx; Size
0x180065d0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065d14  mov     rcx, rax
0x180065d17  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>>>(std::allocator<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>> const &)
0x180065d1c  mov     [rcx+20h], r12d
0x180065d20  mov     [r14+68h], rcx
0x180065d24  call    ?RegisterAllEndpoints@@YAXAEAVCWebDriverEndpointMapping@@@Z; RegisterAllEndpoints(CWebDriverEndpointMapping &)
0x180065d29  mov     rcx, [r14+68h]
0x180065d2d  lea     rdx, [rbp+var_28]
0x180065d31  mov     r9, rsi
0x180065d34  mov     r8, r15
0x180065d37  call    ?ParseRequest@CWebDriverEndpointMapping@@QEAA?AVCWebDriverRequestedEndpoint@@PEBG0@Z; CWebDriverEndpointMapping::ParseRequest(ushort const *,ushort const *)
0x180065d3c  mov     r8d, [rbp+var_28]
0x180065d40  cmp     r8d, 4Bh ; 'K'
0x180065d44  jnz     short loc_180065D5B
0x180065d46  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x180065d4a  lea     rcx, [r14-30h]; this
0x180065d4e  mov     r8d, r13d; unsigned int
0x180065d51  call    ?_CreateNewSession@CWebDriverHost@@AEAAXPEBGK@Z; CWebDriverHost::_CreateNewSession(ushort const *,ulong)
0x180065d56  jmp     loc_1800660AD
0x180065d5b  mov     rax, [rbp+var_20]
0x180065d5f  mov     rdx, r12
0x180065d62  cmp     rax, [rbp+var_18]
0x180065d66  jz      short loc_180065D80
0x180065d68  cmp     dword ptr [rax], 7
0x180065d6b  jz      short loc_180065D72
0x180065d6d  add     rax, rbx
0x180065d70  jmp     short loc_180065D62
0x180065d72  lea     rdx, [rax+8]
0x180065d76  cmp     qword ptr [rdx+18h], 7
0x180065d7b  jbe     short loc_180065D80
0x180065d7d  mov     rdx, [rdx]; unsigned __int16 *
0x180065d80  cmp     [r14+90h], r12b
0x180065d87  jz      loc_18006614A
0x180065d8d  mov     rax, [r14+80h]
0x180065d94  mov     r10, rdx
0x180065d97  sub     r10, rax
0x180065d9a  movzx   r9d, word ptr [rax]
0x180065d9e  movzx   ecx, word ptr [rax+r10]
0x180065da3  sub     r9d, ecx; char *
0x180065da6  jnz     short loc_180065DB0
0x180065da8  add     rax, 2
0x180065dac  test    ecx, ecx
0x180065dae  jnz     short loc_180065D9A
0x180065db0  test    r9d, r9d
0x180065db3  jnz     loc_18006614A
0x180065db9  mov     r15d, r12d
0x180065dbc  cmp     r8d, 49h ; 'I'
0x180065dc0  jg      loc_180065EB3
0x180065dc6  jz      loc_180065FCD
0x180065dcc  cmp     r8d, 1Ah
0x180065dd0  jg      short loc_180065E1E
0x180065dd2  jz      loc_180065FCD
0x180065dd8  sub     r8d, 5
0x180065ddc  jz      loc_180065FCD
0x180065de2  sub     r8d, 3
0x180065de6  jz      loc_18006614F
0x180065dec  sub     r8d, 0Eh
0x180065df0  jz      short loc_180065E15
0x180065df2  sub     r8d, 1
0x180065df6  jz      loc_180065FCD
0x180065dfc  sub     r8d, 1
0x180065e00  jz      loc_180065FCD
0x180065e06  cmp     r8d, 1
0x180065e0a  jz      loc_180065FCD
0x180065e10  jmp     loc_180065FD1
0x180065e15  mov     r15d, [r14+78h]
0x180065e19  jmp     loc_180065FD1
0x180065e1e  sub     r8d, 1Dh
0x180065e22  jz      short loc_180065E40
0x180065e24  sub     r8d, 1Fh
0x180065e28  jz      short loc_180065E65
0x180065e2a  sub     r8d, 1
0x180065e2e  jz      short loc_180065E49
0x180065e30  sub     r8d, 3
0x180065e34  jz      short loc_180065E40
0x180065e36  cmp     r8d, 1
0x180065e3a  jnz     loc_180065FD1
0x180065e40  mov     r15d, [r14+74h]
0x180065e44  jmp     loc_180065FD1
0x180065e49  lea     rcx, [r14-30h]; this
0x180065e4d  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180065e51  call    ?_GetWindowHandles@CWebDriverHost@@AEAAJPEAPEAG@Z; CWebDriverHost::_GetWindowHandles(ushort * *)
0x180065e56  mov     edi, eax
0x180065e58  test    eax, eax
0x180065e5a  js      loc_18006608D
0x180065e60  jmp     loc_180065EFA
0x180065e65  lea     rcx, [r14-30h]
0x180065e69  xor     edx, edx
0x180065e6b  call    ?_UpdateAndEnsureCurrentCoreWebViewPrivate@CWebDriverHost@@AEAA?AW4WebDriverResponseCode@@PEBK@Z; CWebDriverHost::_UpdateAndEnsureCurrentCoreWebViewPrivate(ulong const *)
0x180065e70  mov     ebx, eax
0x180065e72  test    eax, eax
0x180065e74  jnz     loc_18006614F
0x180065e7a  mov     edx, [r14+48h]; unsigned int
0x180065e7e  call    ?_ConvertCoreWebViewPrivateIdToWindowHandle@CWebDriverHost@@AEAAPEAGK@Z; CWebDriverHost::_ConvertCoreWebViewPrivateIdToWindowHandle(ulong)
0x180065e83  mov     rcx, [r14+60h]
0x180065e87  lea     r9d, [rbx+8]
0x180065e8b  mov     [rbp+pv], rax
0x180065e8f  xor     r8d, r8d
0x180065e92  mov     [rsp+70h+var_48], rax
0x180065e97  mov     byte ptr [rsp+70h+var_50], r12b
0x180065e9c  mov     rdx, [rcx]
0x180065e9f  mov     r10, [rdx+40h]
0x180065ea3  mov     edx, r13d
0x180065ea6  mov     rax, r10
0x180065ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065eae  jmp     loc_1800660AD
0x180065eb3  cmp     r8d, 62h ; 'b'
0x180065eb7  jg      loc_180065FA5
0x180065ebd  jz      loc_180065F92
0x180065ec3  sub     r8d, 4Ch ; 'L'
0x180065ec7  jz      short loc_180065F31
0x180065ec9  sub     r8d, 1
0x180065ecd  jz      loc_180065E40
0x180065ed3  sub     r8d, 2
0x180065ed7  jz      loc_180065FCD
0x180065edd  sub     r8d, 0Fh
0x180065ee1  jz      short loc_180065F02
0x180065ee3  cmp     r8d, 3
0x180065ee7  jnz     loc_180065FD1
0x180065eed  lea     rcx, [r14-30h]; this
0x180065ef1  lea     r8, [rbp+pv]; unsigned __int16 **
0x180065ef5  call    ?_GetTimeouts@CWebDriverHost@@AEAAXPEBGPEAPEAG@Z; CWebDriverHost::_GetTimeouts(ushort const *,ushort * *)
0x180065efa  mov     ebx, r12d
0x180065efd  jmp     loc_18006614F
0x180065f02  mov     rdx, [rbp+arg_20]
0x180065f06  lea     r8, [rbp+arg_0]
0x180065f0a  mov     [rbp+arg_0], r12d
0x180065f0e  call    ?_GetWindowId@CWebDriverHost@@AEAA?AW4WebDriverResponseCode@@PEBGPEAK@Z; CWebDriverHost::_GetWindowId(ushort const *,ulong *)
0x180065f13  mov     ebx, eax
0x180065f15  test    eax, eax
0x180065f17  jnz     loc_18006614F
0x180065f1d  lea     rcx, [r14-30h]
0x180065f21  lea     rdx, [rbp+arg_0]
0x180065f25  call    ?_UpdateAndEnsureCurrentCoreWebViewPrivate@CWebDriverHost@@AEAA?AW4WebDriverResponseCode@@PEBK@Z; CWebDriverHost::_UpdateAndEnsureCurrentCoreWebViewPrivate(ulong const *)
0x180065f2a  mov     ebx, eax
0x180065f2c  jmp     loc_18006614F
0x180065f31  mov     esi, 1
0x180065f36  xor     eax, eax
0x180065f38  lock cmpxchg [r14+7Ch], esi
0x180065f3e  jnz     short loc_180065F7C
0x180065f40  lea     rcx, [r14-30h]; this
0x180065f44  call    ?_DisconnectAllCoreWebViewPrivate@CWebDriverHost@@AEAAXXZ; CWebDriverHost::_DisconnectAllCoreWebViewPrivate(void)
0x180065f49  xor     r9d, r9d; unsigned __int16 *
0x180065f4c  mov     [rsp+70h+var_50], esi; int
0x180065f50  xor     r8d, r8d; unsigned int
0x180065f53  lea     rcx, [r14-30h]; this
0x180065f57  mov     edx, r13d; unsigned int
0x180065f5a  call    ?_ReplyToWebDriverServer@CWebDriverHost@@AEAAJKKPEBGH@Z; CWebDriverHost::_ReplyToWebDriverServer(ulong,ulong,ushort const *,int)
0x180065f5f  mov     rax, [r14+60h]
0x180065f63  xor     r9d, r9d
0x180065f66  mov     r8d, 0D87h
0x180065f6c  mov     ecx, [rax+1Ch]
0x180065f6f  mov     edx, ecx
0x180065f71  call    cs:__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z; LCIEPostMessageWithoutBuffer(ulong,ulong,ulong,ulong)
0x180065f77  jmp     loc_1800660AD
0x180065f7c  mov     rcx, [rbp+38h]; this
0x180065f80  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180065f87  mov     edx, 323h; void *
0x180065f8c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180065f92  mov     rdx, [rbp+arg_20]
0x180065f96  lea     rcx, [r14-30h]
0x180065f9a  lea     r8, [rbp+pv]
0x180065f9e  call    ?_SetTimeout@CWebDriverHost@@AEAA?AW4WebDriverResponseCode@@PEBGPEAPEAG@Z; CWebDriverHost::_SetTimeout(ushort const *,ushort * *)
0x180065fa3  jmp     short loc_180065F2A
0x180065fa5  mov     ecx, r8d
0x180065fa8  sub     ecx, 63h ; 'c'
0x180065fab  jz      loc_180066138
0x180065fb1  sub     ecx, 1
0x180065fb4  jz      loc_180066138
0x180065fba  sub     ecx, 2Ch ; ','
0x180065fbd  jz      short loc_180065FCD
0x180065fbf  sub     ecx, 3
0x180065fc2  jz      loc_180066138
0x180065fc8  cmp     ecx, 1
0x180065fcb  jnz     short loc_180065FD1
0x180065fcd  mov     r15d, [r14+70h]
0x180065fd1  lea     rcx, [r14-30h]
0x180065fd5  xor     edx, edx
0x180065fd7  call    ?_UpdateAndEnsureCurrentCoreWebViewPrivate@CWebDriverHost@@AEAA?AW4WebDriverResponseCode@@PEBK@Z; CWebDriverHost::_UpdateAndEnsureCurrentCoreWebViewPrivate(ulong const *)
0x180065fdc  mov     r12d, eax
0x180065fdf  test    eax, eax
0x180065fe1  jnz     loc_18006610F
0x180065fe7  mov     rcx, [rbp+psz]; psz
0x180065feb  call    cs:__imp_SysAllocString
0x180065ff1  mov     rcx, rsi; psz
0x180065ff4  mov     rdi, rax
0x180065ff7  call    cs:__imp_SysAllocString
0x180065ffd  mov     rcx, [rbp+arg_20]; psz
0x180066001  mov     rbx, rax
0x180066004  call    cs:__imp_SysAllocString
0x18006600a  mov     rcx, [r14+50h]
0x18006600e  mov     r9, rbx
0x180066011  mov     rsi, rax
0x180066014  mov     dword ptr [rsp+70h+var_48], r15d
0x180066019  mov     r8, rdi
0x18006601c  mov     qword ptr [rsp+70h+var_50], rsi
0x180066021  mov     rdx, [rcx]
0x180066024  mov     rax, [rdx+210h]
0x18006602b  mov     edx, r13d
0x18006602e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066033  mov     edx, 8007139Fh
0x180066038  lea     r15d, [r12+17h]
0x18006603d  cmp     eax, edx
0x18006603f  cmovz   r12d, r15d
0x180066043  xor     ecx, ecx
0x180066045  cmp     eax, edx
0x180066047  cmovnz  ecx, eax
0x18006604a  mov     [rbp+arg_0], ecx
0x18006604d  test    rsi, rsi
0x180066050  jz      short loc_18006605B
0x180066052  mov     rcx, rsi; bstrString
0x180066055  call    cs:__imp_SysFreeString
0x18006605b  test    rbx, rbx
0x18006605e  jz      short loc_180066069
0x180066060  mov     rcx, rbx; bstrString
0x180066063  call    cs:__imp_SysFreeString
0x180066069  test    rdi, rdi
0x18006606c  jz      short loc_180066077
0x18006606e  mov     rcx, rdi; bstrString
0x180066071  call    cs:__imp_SysFreeString
0x180066077  mov     edi, [rbp+arg_0]
0x18006607a  mov     ebx, r12d
0x18006607d  cmp     r12d, r15d
0x180066080  jz      loc_180066118
0x180066086  xor     r12d, r12d
0x180066089  test    edi, edi
0x18006608b  jns     short loc_1800660AD
0x18006608d  test    ebx, ebx
0x18006608f  mov     [rsp+70h+var_50], r12d; int
0x180066094  mov     r8d, 0Dh
0x18006609a  lea     rcx, [r14-30h]; this
0x18006609e  cmovnz  r8d, ebx; unsigned int
0x1800660a2  mov     edx, r13d; unsigned int
0x1800660a5  xor     r9d, r9d; unsigned __int16 *
0x1800660a8  call    ?_ReplyToWebDriverServer@CWebDriverHost@@AEAAJKKPEBGH@Z; CWebDriverHost::_ReplyToWebDriverServer(ulong,ulong,ushort const *,int)
0x1800660ad  mov     rcx, [rbp+pv]; pv
0x1800660b1  call    cs:__imp_CoTaskMemFree
0x1800660b7  cmp     [rbp+var_20], r12
0x1800660bb  jz      short loc_1800660F5
0x1800660bd  mov     rdx, [rbp+var_18]
0x1800660c1  mov     rcx, [rbp+var_20]
0x1800660c5  call    ??$_Destroy_range@V?$allocator@U?$pair@W4WebDriverPathVariable@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@YAXPEAU?$pair@W4WebDriverPathVariable@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@QEAU10@AEAV?$allocator@U?$pair@W4WebDriverPathVariable@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<WebDriverPathVariable,std::wstring>>>(std::pair<WebDriverPathVariable,std::wstring> *,std::pair<WebDriverPathVariable,std::wstring> * const,std::allocator<std::pair<WebDriverPathVariable,std::wstring>> &)
0x1800660ca  mov     rax, [rbp+var_10]
0x1800660ce  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800660d8  sub     rax, [rbp+var_20]
0x1800660dc  sar     rax, 3
0x1800660e0  imul    rax, rcx
0x1800660e4  mov     rcx, [rbp+var_20]
0x1800660e8  lea     rdx, [rax+rax*4]
0x1800660ec  shl     rdx, 3
0x1800660f0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800660f5  mov     rbx, [rsp+70h+arg_8]
0x1800660fd  mov     eax, edi
0x1800660ff  add     rsp, 70h
0x180066103  pop     r15
0x180066105  pop     r14
0x180066107  pop     r13
0x180066109  pop     r12
0x18006610b  pop     rdi
0x18006610c  pop     rsi
0x18006610d  pop     rbp
0x18006610e  retn
0x18006610f  mov     r15d, 17h
0x180066115  mov     ebx, r15d
0x180066118  xor     r12d, r12d
0x18006611b  mov     r8d, r15d; unsigned int
0x18006611e  mov     r9, [rbp+pv]; unsigned __int16 *
0x180066122  lea     rcx, [r14-30h]; this
0x180066126  mov     edx, r13d; unsigned int
0x180066129  mov     [rsp+70h+var_50], r12d; int
0x18006612e  call    ?_ReplyToWebDriverServer@CWebDriverHost@@AEAAJKKPEBGH@Z; CWebDriverHost::_ReplyToWebDriverServer(ulong,ulong,ushort const *,int)
0x180066133  jmp     loc_180066089
0x180066138  mov     rdx, [rbp+arg_20]
0x18006613c  lea     rcx, [r14-30h]
0x180066140  call    ?_SetTimeoutJWP@CWebDriverHost@@AEAA?AW4WebDriverResponseCode@@PEBGW4WebDriverCommandCode@@@Z; CWebDriverHost::_SetTimeoutJWP(ushort const *,WebDriverCommandCode)
0x180066145  jmp     loc_180065F2A
0x18006614a  mov     ebx, 6
0x18006614f  mov     r8d, ebx
  ... truncated ...
```
