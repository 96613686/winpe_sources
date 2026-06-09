# CUiccHandler2::EnumerateInterfaces(void)

- ea: `0x18002e0a0`
- end: `0x18002e57a`
- name: `?EnumerateInterfaces@CUiccHandler2@@IEAA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@@2@@std@@XZ`
- size: `1242`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800308d0`

## callees

- `0x1800017c4`
- `0x1800045c0`
- `0x180004894`
- `0x18000e1f8`
- `0x180012d80`
- `0x180012e18`
- `0x18002b040`
- `0x18002b2f0`
- `0x18002bfb0`
- `0x18002cb64`
- `0x18002e0a0`
- `0x1800320a0`
- `0x180032624`
- `0x180038b00`
- `0x18003acb4`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18002e1ed`
- `msvcrt!wcsnlen` at `0x18002e1ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e2d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e2d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e438`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e454`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e438`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e454`
- `OLEAUT32!__imp_VariantInit` at `0x18002e483`
- `OLEAUT32!__imp_VariantInit` at `0x18002e483`
- `OLEAUT32!__imp_VariantClear` at `0x18002e4c7`
- `OLEAUT32!__imp_VariantClear` at `0x18002e4c7`
- `ntdll!RtlPublishWnfStateData` at `0x18002e403`
- `ntdll!RtlPublishWnfStateData` at `0x18002e403`
- `ntdll!RtlQueryWnfStateData` at `0x18002e399`
- `ntdll!RtlQueryWnfStateData` at `0x18002e399`
- `ntdll!RtlNtStatusToDosError` at `0x18002e3a5`
- `ntdll!RtlNtStatusToDosError` at `0x18002e3a5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002e425`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002e425`

## pseudocode

```c
_QWORD *__fastcall CUiccHandler2::EnumerateInterfaces(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rsi
  int v4; // eax
  unsigned __int64 v5; // r13
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r14
  unsigned int v9; // edx
  void ***v10; // rbx
  void ***v11; // rdi
  void **v12; // rsi
  int v13; // edx
  __int64 v14; // r8
  __int16 v15; // cx
  __int16 v16; // cx
  __int64 v17; // rax
  int v18; // r8d
  const WCHAR *v19; // rax
  __int64 v20; // rax
  NTSTATUS v21; // eax
  unsigned __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  int v26; // [rsp+20h] [rbp-E0h]
  unsigned int v27; // [rsp+30h] [rbp-D0h]
  _DWORD v28[3]; // [rsp+34h] [rbp-CCh] BYREF
  const WCHAR *v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h]
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h] BYREF
  __int64 v35; // [rsp+80h] [rbp-80h]
  void *v36[2]; // [rsp+90h] [rbp-70h] BYREF
  LONG v37; // [rsp+A0h] [rbp-60h]
  _QWORD *v38; // [rsp+A8h] [rbp-58h]
  char v39; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v40; // [rsp+C0h] [rbp-40h] BYREF
  int v41; // [rsp+D0h] [rbp-30h]
  void **v42; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v43; // [rsp+E8h] [rbp-18h]
  HANDLE hObject[2]; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+100h] [rbp+0h]
  __int128 v46; // [rsp+108h] [rbp+8h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  __int128 v48; // [rsp+120h] [rbp+20h] BYREF
  void *v49[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v50; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v3 = a1;
  v32 = a1;
  v38 = a2;
  *a2 = 0;
  a2[1] = 0;
  *a2 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,Uicc>>>::_Buyheadnode();
  v28[1] = 1;
  v30 = 0;
  v31 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64 *))(**(_QWORD **)(v3 + 32) + 40LL))(
         *(_QWORD *)(v3 + 32),
         &v31,
         &v30);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v4,
      v26);
  CellState::FromCellularSnapshot(&v34, v30);
  v5 = 0;
  v6 = v35;
  v7 = v34;
  if ( (v35 - v34) >> 5 )
  {
    do
    {
      if ( (v6 - v7) >> 5 <= v5 )
        std::vector<UiccKeySet>::_Xran();
      v8 = *(_QWORD *)std::map<std::wstring,std::shared_ptr<Modem>>::at(v36, v7 + 32 * v5);
      v9 = 0;
      v27 = 0;
      v40 = 0;
      v41 = 0;
      v10 = *(void ****)(v8 + 64);
      v11 = *(void ****)(v8 + 72);
      while ( v10 != v11 )
      {
        if ( *(_BYTE *)(v8 + 112) )
        {
          *((_DWORD *)&v40 + 2 * v9 + 2) = (*v10 != 0) + 1;
          v27 = v9 + 1;
        }
        v12 = *v10;
        if ( *v10 )
        {
          if ( ((unsigned __int64)v12[3] < 8 || (v12 = (void **)*v12) != 0)
            && wcsnlen((const wchar_t *)v12, 0x15u) - 15 <= 5 )
          {
            v13 = 0;
            while ( 1 )
            {
              v14 = 2 * v13;
              v15 = *((_WORD *)v12 + v14);
              if ( !v15 )
                break;
              if ( (unsigned __int16)(v15 - 97) > 5u
                && (unsigned __int16)(v15 - 65) > 5u
                && (unsigned __int16)(v15 - 48) > 9u )
              {
                goto LABEL_26;
              }
              v16 = *((_WORD *)v12 + v14 + 1);
              if ( !v16 )
                break;
              if ( (unsigned __int16)(v16 - 97) > 5u
                && (unsigned __int16)(v16 - 65) > 5u
                && (unsigned __int16)(v16 - 48) > 9u )
              {
                goto LABEL_26;
              }
              if ( ++v13 >= 10 )
              {
                if ( *((_WORD *)v12 + 20) )
                  goto LABEL_26;
                break;
              }
            }
            v50 = 7;
            v49[2] = 0;
            LOWORD(v49[0]) = 0;
            std::wstring::assign(v49, *v10, 0, 0xFFFFFFFFFFFFFFFFuLL);
            if ( !*v10 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x24,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\inc\\nullable.h",
                (const char *)0x8007139FLL,
                v26);
            v17 = std::_Tree_buy<std::pair<std::wstring const,Uicc>>::_Buynode<std::wstring &,Uicc>(a2, v49);
            std::_Tree<std::_Tmap_traits<std::wstring,Uicc,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Uicc>>,0>>::_Insert_nohint<std::pair<std::wstring const,Uicc> &,std::_Tree_node<std::pair<std::wstring const,Uicc>,void *> *>(
              (_DWORD)a2,
              (unsigned int)&v39,
              v18,
              v17 + 32,
              v17);
            if ( v50 >= 8 )
              operator delete(v49[0]);
          }
          else
          {
LABEL_26:
            if ( (unsigned int)dword_180052170 > 3 )
            {
              if ( *(_QWORD *)(v8 + 24) < 8u )
                v19 = (const WCHAR *)v8;
              else
                v19 = *(const WCHAR **)v8;
              v29 = v19;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                (__int64)&dword_180052170,
                (__int64)&byte_180049887,
                0,
                0,
                &v29);
            }
          }
        }
        ++v10;
        v9 = v27;
      }
      if ( *(_BYTE *)(v8 + 112) )
      {
        v42 = &WnfSubscriberT<MvProvisioningSessionNotification>::`vftable';
        v43 = WNF_DEVM_MULTIVARIANT_PROVISIONING_SESSIONS;
        *(_OWORD *)hObject = 0;
        v45 = 0;
        v46 = 0;
        v47 = 0;
        v48 = 0;
        std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>>::_Buyheadnode();
        *(_QWORD *)&v48 = v20;
        v28[0] = 0;
        v26 = 0;
        v21 = RtlQueryWnfStateData(v28, v43, WnfSubscriberT<MvProvisioningSessionNotification>::CallbackWrapper, &v42);
        if ( v21 < 0 )
          RtlNtStatusToDosError(v21);
        if ( !v28[0] )
        {
          v22 = (__int64)(*(_QWORD *)(v8 + 72) - *(_QWORD *)(v8 + 64)) >> 3;
          LODWORD(v40) = v22;
          if ( v22 > 0xFFFFFFFF )
          {
            LODWORD(v40) = -1;
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x308,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
              v22 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
              0);
          }
          v26 = 0;
          v23 = RtlPublishWnfStateData(WNF_DEVM_MULTIVARIANT_PROVISIONING_SESSIONS, 0, &v40, 20);
          if ( v23 < 0 )
            wil::details::in1diag3::_Throw_NtStatus(
              retaddr,
              (void *)0x30A,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
              (const char *)(unsigned int)v23,
              0);
        }
        v42 = &WnfSubscriberT<MvProvisioningSessionNotification>::`vftable';
        if ( hObject[0] )
        {
          RtlUnsubscribeWnfNotificationWaitForCompletion();
          hObject[0] = 0;
        }
        if ( hObject[1] )
        {
          CloseHandle(hObject[1]);
          hObject[1] = 0;
        }
        std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>(&v48);
        if ( hObject[1] )
          CloseHandle(hObject[1]);
      }
      ++v5;
      v6 = v35;
      v7 = v34;
    }
    while ( v5 < (v35 - v34) >> 5 );
    v3 = v32;
  }
  VariantInit(&pvarg);
  pvarg.lVal = v37;
  pvarg.vt = 19;
  v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, VARIANTARG *))(**(_QWORD **)(v3 + 16) + 64LL))(
          *(_QWORD *)(v3 + 16),
          L"CellularSequence",
          &pvarg);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x313,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v24,
      v26);
  VariantClear(&pvarg);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Modem>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Modem>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Modem>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Modem>>>,0>>(v36);
  std::vector<std::wstring>::_Tidy((__int64)&v34);
  return a2;
}

```

## disassembly

```asm
0x18002e0a0  mov     [rsp-8+arg_10], rbx
0x18002e0a5  push    rbp
0x18002e0a6  push    rsi
0x18002e0a7  push    rdi
0x18002e0a8  push    r12
0x18002e0aa  push    r13
0x18002e0ac  push    r14
0x18002e0ae  push    r15
0x18002e0b0  lea     rbp, [rsp-60h]
0x18002e0b5  sub     rsp, 160h
0x18002e0bc  mov     rax, cs:__security_cookie
0x18002e0c3  xor     rax, rsp
0x18002e0c6  mov     [rbp+90h+var_40], rax
0x18002e0ca  mov     r12, rdx
0x18002e0cd  mov     rsi, rcx
0x18002e0d0  mov     [rsp+190h+var_138], rcx
0x18002e0d5  mov     [rbp+90h+var_E8], rdx
0x18002e0d9  xor     r15d, r15d
0x18002e0dc  mov     [rsp+190h+var_158], r15d
0x18002e0e1  mov     [rdx], r15
0x18002e0e4  mov     [rdx+8], r15
0x18002e0e8  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,Uicc>>>::_Buyheadnode(void)
0x18002e0ed  mov     [r12], rax
0x18002e0f1  mov     [rsp+190h+var_158], 1
0x18002e0f9  mov     [rsp+190h+var_148], r15
0x18002e0fe  mov     [rsp+190h+var_140], r15d
0x18002e103  mov     rcx, [rsi+20h]
0x18002e107  mov     rax, [rcx]
0x18002e10a  lea     r8, [rsp+190h+var_148]
0x18002e10f  lea     rdx, [rsp+190h+var_140]
0x18002e114  mov     rax, [rax+28h]
0x18002e118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e11d  mov     rcx, [rbp+98h]; this
0x18002e124  test    eax, eax
0x18002e126  js      loc_18002E511
0x18002e12c  mov     rdx, [rsp+190h+var_148]
0x18002e131  lea     rcx, [rsp+190h+var_118]
0x18002e136  call    ?FromCellularSnapshot@CellState@@SA?AV1@PEAU_MVCellularStateHdr@@@Z; CellState::FromCellularSnapshot(_MVCellularStateHdr *)
0x18002e13b  nop
0x18002e13c  mov     r13d, r15d
0x18002e13f  mov     rcx, [rbp+90h+var_110]
0x18002e143  mov     rax, rcx
0x18002e146  mov     r8, [rsp+190h+var_118]
0x18002e14b  sub     rax, r8
0x18002e14e  sar     rax, 5
0x18002e152  test    rax, rax
0x18002e155  jz      loc_18002E47E
0x18002e15b  sub     rcx, r8
0x18002e15e  sar     rcx, 5
0x18002e162  cmp     rcx, r13
0x18002e165  jbe     loc_18002E50B
0x18002e16b  mov     rdx, r13
0x18002e16e  shl     rdx, 5
0x18002e172  add     rdx, r8
0x18002e175  lea     rcx, [rbp+90h+var_100]
0x18002e179  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@UModem@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::map<std::wstring,std::shared_ptr<Modem>>::at(std::wstring const &)
0x18002e17e  mov     r14, [rax]
0x18002e181  mov     edx, r15d
0x18002e184  mov     [rsp+190h+var_160], edx
0x18002e188  xorps   xmm0, xmm0
0x18002e18b  xor     eax, eax
0x18002e18d  movups  [rbp+90h+var_D0], xmm0
0x18002e191  mov     [rbp+90h+var_C0], eax
0x18002e194  mov     rbx, [r14+40h]
0x18002e198  mov     rdi, [r14+48h]
0x18002e19c  cmp     rbx, rdi
0x18002e19f  jz      loc_18002E333
0x18002e1a5  cmp     [r14+70h], r15b
0x18002e1a9  jz      short loc_18002E1C3
0x18002e1ab  mov     rax, [rbx]
0x18002e1ae  neg     rax
0x18002e1b1  sbb     ecx, ecx
0x18002e1b3  neg     ecx
0x18002e1b5  inc     ecx
0x18002e1b7  mov     eax, edx
0x18002e1b9  mov     dword ptr [rbp+rax*8+90h+var_D0+8], ecx
0x18002e1bd  inc     edx
0x18002e1bf  mov     [rsp+190h+var_160], edx
0x18002e1c3  mov     rsi, [rbx]
0x18002e1c6  test    rsi, rsi
0x18002e1c9  jz      loc_18002E326
0x18002e1cf  cmp     qword ptr [rsi+18h], 8
0x18002e1d4  jb      short loc_18002E1E2
0x18002e1d6  mov     rsi, [rsi]
0x18002e1d9  test    rsi, rsi
0x18002e1dc  jz      loc_18002E2E4
0x18002e1e2  mov     r15, rsi
0x18002e1e5  mov     edx, 15h; MaxCount
0x18002e1ea  mov     rcx, rsi; Source
0x18002e1ed  call    cs:__imp_wcsnlen
0x18002e1f3  add     rax, 0FFFFFFFFFFFFFFF1h
0x18002e1f7  mov     r11d, 5
0x18002e1fd  cmp     rax, r11
0x18002e200  ja      loc_18002E2E1
0x18002e206  xor     r10d, r10d
0x18002e209  mov     edx, r10d
0x18002e20c  lea     eax, [rdx+rdx]
0x18002e20f  movsxd  r8, eax
0x18002e212  movzx   ecx, word ptr [rsi+r8*2]
0x18002e217  test    cx, cx
0x18002e21a  jz      short loc_18002E271
0x18002e21c  lea     eax, [rcx-61h]
0x18002e21f  cmp     ax, r11w
0x18002e223  jbe     short loc_18002E23C
0x18002e225  lea     eax, [rcx-41h]
0x18002e228  cmp     ax, r11w
0x18002e22c  jbe     short loc_18002E23C
0x18002e22e  sub     cx, 30h ; '0'
0x18002e232  cmp     cx, 9
0x18002e236  ja      loc_18002E2E1
0x18002e23c  movzx   ecx, word ptr [rsi+r8*2+2]
0x18002e242  test    cx, cx
0x18002e245  jz      short loc_18002E271
0x18002e247  lea     eax, [rcx-61h]
0x18002e24a  cmp     ax, r11w
0x18002e24e  jbe     short loc_18002E263
0x18002e250  lea     eax, [rcx-41h]
0x18002e253  cmp     ax, r11w
0x18002e257  jbe     short loc_18002E263
0x18002e259  sub     cx, 30h ; '0'
0x18002e25d  cmp     cx, 9
0x18002e261  ja      short loc_18002E2E1
0x18002e263  inc     edx
0x18002e265  cmp     edx, 0Ah
0x18002e268  jl      short loc_18002E20C
0x18002e26a  cmp     [r15+28h], r10w
0x18002e26f  jnz     short loc_18002E2E1
0x18002e271  mov     [rbp+90h+var_48], 7
0x18002e279  xor     r15d, r15d
0x18002e27c  mov     [rbp+90h+var_50], r15
0x18002e280  mov     word ptr [rbp+90h+var_60], r15w
0x18002e285  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002e289  xor     r8d, r8d
0x18002e28c  mov     rdx, [rbx]
0x18002e28f  lea     rcx, [rbp+90h+var_60]; void *
0x18002e293  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002e298  nop
0x18002e299  mov     r8, [rbx]
0x18002e29c  mov     rcx, [rbp+98h]; this
0x18002e2a3  test    r8, r8
0x18002e2a6  jz      loc_18002E53B
0x18002e2ac  lea     rdx, [rbp+90h+var_60]
0x18002e2b0  mov     rcx, r12
0x18002e2b3  call    ??$_Buynode@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@PEAX@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAUUicc@@@Z; std::_Tree_buy<std::pair<std::wstring const,Uicc>>::_Buynode<std::wstring &,Uicc>(std::wstring &,Uicc &&)
0x18002e2b8  lea     r9, [rax+20h]
0x18002e2bc  mov     qword ptr [rsp+190h+var_170], rax
0x18002e2c1  lea     rdx, [rbp+90h+var_E0]
0x18002e2c5  mov     rcx, r12
0x18002e2c8  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUicc@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Uicc,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Uicc>>,0>>::_Insert_nohint<std::pair<std::wstring const,Uicc> &,std::_Tree_node<std::pair<std::wstring const,Uicc>,void *> *>(bool,std::pair<std::wstring const,Uicc> &,std::_Tree_node<std::pair<std::wstring const,Uicc>,void *> *)
0x18002e2cd  nop
0x18002e2ce  cmp     [rbp+90h+var_48], 8
0x18002e2d3  jb      short loc_18002E326
0x18002e2d5  mov     rcx, [rbp+90h+var_60]
0x18002e2d9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002e2df  jmp     short loc_18002E326
0x18002e2e1  xor     r15d, r15d
0x18002e2e4  mov     eax, cs:dword_180052170
0x18002e2ea  cmp     eax, 3
0x18002e2ed  jbe     short loc_18002E326
0x18002e2ef  cmp     qword ptr [r14+18h], 8
0x18002e2f4  jb      short loc_18002E2FB
0x18002e2f6  mov     rax, [r14]
0x18002e2f9  jmp     short loc_18002E2FE
0x18002e2fb  mov     rax, r14
0x18002e2fe  mov     [rsp+190h+var_150], rax
0x18002e303  lea     rax, [rsp+190h+var_150]
0x18002e308  mov     qword ptr [rsp+190h+var_170], rax
0x18002e30d  xor     r9d, r9d
0x18002e310  xor     r8d, r8d
0x18002e313  lea     rdx, byte_180049887
0x18002e31a  lea     rcx, dword_180052170
0x18002e321  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002e326  add     rbx, 8
0x18002e32a  mov     edx, [rsp+190h+var_160]
0x18002e32e  jmp     loc_18002E19C
0x18002e333  cmp     [r14+70h], r15b
0x18002e337  jz      loc_18002E45A
0x18002e33d  lea     rbx, ??_7?$WnfSubscriberT@UMvProvisioningSessionNotification@@@@6B@; const WnfSubscriberT<MvProvisioningSessionNotification>::`vftable'
0x18002e344  mov     [rbp+90h+var_B0], rbx
0x18002e348  mov     rax, cs:WNF_DEVM_MULTIVARIANT_PROVISIONING_SESSIONS
0x18002e34f  mov     [rbp+90h+var_A8], rax
0x18002e353  xorps   xmm0, xmm0
0x18002e356  movdqa  xmmword ptr [rbp+90h+hObject], xmm0
0x18002e35b  mov     [rbp+90h+var_90], 0
0x18002e363  xor     eax, eax
0x18002e365  movups  [rbp+90h+var_88], xmm0
0x18002e369  mov     [rbp+90h+var_78], rax
0x18002e36d  movdqa  [rbp+90h+var_70], xmm0
0x18002e372  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>>::_Buyheadnode(void)
0x18002e377  mov     qword ptr [rbp+90h+var_70], rax
0x18002e37b  mov     [rsp+190h+var_15C], r15d
0x18002e380  mov     qword ptr [rsp+190h+var_170], r15; int
0x18002e385  lea     r9, [rbp+90h+var_B0]
0x18002e389  lea     r8, ?CallbackWrapper@?$WnfSubscriberT@UMvProvisioningSessionNotification@@@@KAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; WnfSubscriberT<MvProvisioningSessionNotification>::CallbackWrapper(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18002e390  mov     rdx, [rbp+90h+var_A8]
0x18002e394  lea     rcx, [rsp+190h+var_15C]
0x18002e399  call    cs:__imp_RtlQueryWnfStateData
0x18002e39f  test    eax, eax
0x18002e3a1  jns     short loc_18002E3AB
0x18002e3a3  mov     ecx, eax; Status
0x18002e3a5  call    cs:__imp_RtlNtStatusToDosError
0x18002e3ab  cmp     [rsp+190h+var_15C], r15d
0x18002e3b0  jnz     short loc_18002E418
0x18002e3b2  mov     rax, [r14+48h]
0x18002e3b6  sub     rax, [r14+40h]
0x18002e3ba  sar     rax, 3
0x18002e3be  mov     esi, 0FFFFFFFFh
0x18002e3c3  cmp     rax, rsi
0x18002e3c6  mov     dword ptr [rbp+90h+var_D0], eax
0x18002e3c9  jbe     short loc_18002E3CE
0x18002e3cb  mov     dword ptr [rbp+90h+var_D0], esi
0x18002e3ce  cmp     rsi, rax
0x18002e3d1  sbb     r9d, r9d
0x18002e3d4  and     r9d, 80070216h; char *
0x18002e3db  mov     rcx, [rbp+98h]; this
0x18002e3e2  cmp     rax, rsi
0x18002e3e5  ja      loc_18002E568
0x18002e3eb  mov     qword ptr [rsp+190h+var_170], r15; int
0x18002e3f0  mov     r9d, 14h
0x18002e3f6  lea     r8, [rbp+90h+var_D0]
0x18002e3fa  xor     edx, edx
0x18002e3fc  mov     rcx, cs:WNF_DEVM_MULTIVARIANT_PROVISIONING_SESSIONS
0x18002e403  call    cs:__imp_RtlPublishWnfStateData
0x18002e409  mov     rcx, [rbp+98h]; this
0x18002e410  test    eax, eax
0x18002e412  js      loc_18002E553
0x18002e418  mov     [rbp+90h+var_B0], rbx
0x18002e41c  mov     rcx, [rbp+90h+hObject]
0x18002e420  test    rcx, rcx
0x18002e423  jz      short loc_18002E42F
0x18002e425  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18002e42b  mov     [rbp+90h+hObject], r15
0x18002e42f  mov     rcx, [rbp+90h+hObject+8]; hObject
0x18002e433  test    rcx, rcx
0x18002e436  jz      short loc_18002E442
0x18002e438  call    cs:__imp_CloseHandle
0x18002e43e  mov     [rbp+90h+hObject+8], r15
0x18002e442  lea     rcx, [rbp+90h+var_70]
0x18002e446  call    ??1?$_Tree@V?$_Tset_traits@V?$shared_ptr@V?$function@$$A6AXAEBUMvProvisioningSessionNotification@@@Z@std@@@std@@U?$less@V?$shared_ptr@V?$function@$$A6AXAEBUMvProvisioningSessionNotification@@@Z@std@@@std@@@2@V?$allocator@V?$shared_ptr@V?$function@$$A6AXAEBUMvProvisioningSessionNotification@@@Z@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>(void)
0x18002e44b  mov     rcx, [rbp+90h+hObject+8]; hObject
0x18002e44f  test    rcx, rcx
0x18002e452  jz      short loc_18002E45A
0x18002e454  call    cs:__imp_CloseHandle
0x18002e45a  inc     r13
0x18002e45d  mov     rcx, [rbp+90h+var_110]
0x18002e461  mov     rax, rcx
0x18002e464  mov     r8, [rsp+190h+var_118]
0x18002e469  sub     rax, r8
0x18002e46c  sar     rax, 5
0x18002e470  cmp     r13, rax
0x18002e473  jb      loc_18002E15B
0x18002e479  mov     rsi, [rsp+190h+var_138]
0x18002e47e  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18002e483  call    cs:__imp_VariantInit
0x18002e489  nop
0x18002e48a  mov     eax, [rbp+90h+var_F0]
0x18002e48d  mov     dword ptr [rsp+190h+pvarg+8], eax
0x18002e491  mov     eax, 13h
0x18002e496  mov     word ptr [rsp+190h+pvarg], ax
0x18002e49b  mov     rcx, [rsi+10h]
0x18002e49f  mov     rax, [rcx]
0x18002e4a2  lea     r8, [rsp+190h+pvarg]
0x18002e4a7  lea     rdx, ?gc_wszCellularSequence@@3QBGB; "CellularSequence"
0x18002e4ae  mov     rax, [rax+40h]
0x18002e4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4b7  mov     rcx, [rbp+98h]; this
0x18002e4be  test    eax, eax
0x18002e4c0  js      short loc_18002E526
0x18002e4c2  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18002e4c7  call    cs:__imp_VariantClear
0x18002e4cd  nop
0x18002e4ce  lea     rcx, [rbp+90h+var_100]
0x18002e4d2  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Modem>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Modem>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Modem>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Modem>>>,0>>(void)
0x18002e4d7  lea     rcx, [rsp+190h+var_118]
0x18002e4dc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002e4e1  mov     rax, r12
0x18002e4e4  mov     rcx, [rbp+90h+var_40]
0x18002e4e8  xor     rcx, rsp; StackCookie
0x18002e4eb  call    __security_check_cookie
0x18002e4f0  mov     rbx, [rsp+190h+arg_10]
0x18002e4f8  add     rsp, 160h
0x18002e4ff  pop     r15
0x18002e501  pop     r14
0x18002e503  pop     r13
0x18002e505  pop     r12
0x18002e507  pop     rdi
0x18002e508  pop     rsi
0x18002e509  pop     rbp
0x18002e50a  retn
0x18002e50b  call    ?_Xran@?$vector@UUiccKeySet@@V?$allocator@UUiccKeySet@@@std@@@std@@IEBAXXZ; std::vector<UiccKeySet>::_Xran(void)
0x18002e511  mov     r9d, eax; char *
0x18002e514  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e51b  mov     edx, 2D4h; void *
0x18002e520  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e526  mov     r9d, eax; char *
0x18002e529  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e530  mov     edx, 313h; void *
0x18002e535  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e53b  mov     r9d, 8007139Fh; char *
0x18002e541  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\multivariant\\"...
  ... truncated ...
```
