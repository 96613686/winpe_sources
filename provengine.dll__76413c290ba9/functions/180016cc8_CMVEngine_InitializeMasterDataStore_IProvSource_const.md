# CMVEngine::InitializeMasterDataStore(IProvSource const *)

- ea: `0x180016cc8`
- end: `0x180016f53`
- name: `?InitializeMasterDataStore@CMVEngine@@AEAAJPEBUIProvSource@@@Z`
- size: `651`
- prototype: `__int64 __fastcall(CMVEngine *__hidden this, const struct IProvSource *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001eeec`

## callees

- `0x1800010c8`
- `0x18000c360`
- `0x18000e04c`
- `0x180016cc8`
- `0x18001a4a0`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d19`

## pseudocode

```c
__int64 __fastcall CMVEngine::InitializeMasterDataStore(CMVEngine *this, const struct IProvSource *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  LPVOID v6; // rcx
  LPVOID v8; // rbx
  __int64 (__fastcall *v9)(LPVOID, _QWORD *, _QWORD); // r15
  unsigned int v10; // edi
  _QWORD *v11; // rax
  int v12; // eax
  unsigned int v13; // r15d
  __int64 *v14; // rcx
  __int64 v15; // rax
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 *v18; // rdi
  __int64 *v19; // rbx
  __int64 v20; // rax
  __int64 *v21; // rdi
  __int64 v22; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-29h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-21h] BYREF
  const struct IProvSource *v25; // [rsp+40h] [rbp-19h] BYREF
  __int64 v26; // [rsp+48h] [rbp-11h]
  __int64 v27; // [rsp+50h] [rbp-9h]
  _BYTE v28[32]; // [rsp+58h] [rbp-1h] BYREF
  __int64 **v29; // [rsp+78h] [rbp+1Fh]
  __int64 v30; // [rsp+80h] [rbp+27h]

  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_da5a95c1_cb6b_4798_88a9_473c087d9464,
         0,
         1u,
         &GUID_3daf6bc7_1982_4939_a974_3ee4c5bb2031,
         &ppv);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v8 = ppv;
    v9 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, _QWORD))(*(_QWORD *)ppv + 24LL);
    v10 = ProfileSourceFromProvSource(a2);
    v11 = (_QWORD *)(*(__int64 (__fastcall **)(const struct IProvSource *))(*(_QWORD *)a2 + 56LL))(a2);
    if ( v11[3] >= 8u )
      v11 = (_QWORD *)*v11;
    v12 = v9(v8, v11, v10);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v16 = (__int64 *)*((_QWORD *)this + 36);
      v17 = v16[1];
      v18 = v16;
      if ( *(_BYTE *)(v17 + 25) )
        goto LABEL_35;
      do
      {
        if ( *(_QWORD *)(v17 + 32) >= (unsigned __int64)a2 )
        {
          v18 = (__int64 *)v17;
          v17 = *(_QWORD *)v17;
        }
        else
        {
          v17 = *(_QWORD *)(v17 + 16);
        }
        v19 = v18;
      }
      while ( !*(_BYTE *)(v17 + 25) );
      if ( v18 == v16 || (unsigned __int64)a2 < v18[4] )
      {
LABEL_35:
        v25 = a2;
        v26 = 0;
        v27 = 0;
        v20 = std::_Tree_buy<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>::_Buynode<std::pair<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>(
                (__int64)this + 288,
                &v25);
        std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_hint<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(
          (__int64 ***)this + 36,
          &v24,
          v18,
          (unsigned __int64 *)(v20 + 32),
          v20);
        v19 = v24;
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v21 = (__int64 *)ppv;
      if ( (LPVOID)v19[5] != ppv )
      {
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
        v22 = v19[5];
        v19[5] = (__int64)v21;
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        v21 = (__int64 *)ppv;
      }
      if ( !v21 )
        return v13;
      ppv = 0;
      v15 = *v21;
      v14 = v21;
    }
    else
    {
      if ( (unsigned int)dword_18005A000 > 2 )
      {
        LODWORD(v24) = v12;
        v29 = &v24;
        v30 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F4F5, 0, 0, 3, v28);
      }
      v14 = (__int64 *)ppv;
      if ( !ppv )
        return v13;
      ppv = 0;
      v15 = *v14;
    }
    (*(void (__fastcall **)(__int64 *))(v15 + 16))(v14);
    return v13;
  }
  if ( (unsigned int)dword_18005A000 > 2 )
  {
    LODWORD(v24) = v4;
    v29 = &v24;
    v30 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F815, 0, 0, 3, v28);
  }
  v6 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x180016cc8  mov     [rsp-8+arg_10], rbx
0x180016ccd  push    rbp
0x180016cce  push    rsi
0x180016ccf  push    rdi
0x180016cd0  push    r14
0x180016cd2  push    r15
0x180016cd4  lea     rbp, [rsp-37h]
0x180016cd9  sub     rsp, 90h
0x180016ce0  mov     rax, cs:__security_cookie
0x180016ce7  xor     rax, rsp
0x180016cea  mov     [rbp+57h+var_28], rax
0x180016cee  mov     rsi, rdx
0x180016cf1  mov     r14, rcx
0x180016cf4  mov     [rbp+57h+var_80], 0
0x180016cfc  lea     rax, [rbp+57h+var_80]
0x180016d00  mov     [rsp+0B0h+ppv], rax; ppv
0x180016d05  lea     r9, _GUID_3daf6bc7_1982_4939_a974_3ee4c5bb2031; riid
0x180016d0c  xor     edx, edx; pUnkOuter
0x180016d0e  lea     r8d, [rdx+1]; dwClsContext
0x180016d12  lea     rcx, _GUID_da5a95c1_cb6b_4798_88a9_473c087d9464; rclsid
0x180016d19  call    cs:__imp_CoCreateInstance
0x180016d1f  mov     ebx, eax
0x180016d21  test    eax, eax
0x180016d23  jns     short loc_180016D93
0x180016d25  mov     ecx, cs:dword_18005A000
0x180016d2b  cmp     ecx, 2
0x180016d2e  jbe     short loc_180016D6E
0x180016d30  mov     dword ptr [rbp+57h+var_78], eax
0x180016d33  lea     rax, [rbp+57h+var_78]
0x180016d37  mov     [rbp+57h+var_38], rax
0x180016d3b  mov     [rbp+57h+var_30], 4
0x180016d43  lea     rax, [rbp+57h+var_58]
0x180016d47  mov     [rsp+0B0h+var_88], rax
0x180016d4c  mov     dword ptr [rsp+0B0h+ppv], 3
0x180016d54  xor     r9d, r9d
0x180016d57  xor     r8d, r8d
0x180016d5a  lea     rdx, byte_18004F815
0x180016d61  lea     rcx, dword_18005A000
0x180016d68  call    _tlgWriteTransfer_EventWriteTransfer
0x180016d6d  nop
0x180016d6e  mov     rcx, [rbp+57h+var_80]
0x180016d72  test    rcx, rcx
0x180016d75  jz      short loc_180016D8C
0x180016d77  mov     [rbp+57h+var_80], 0
0x180016d7f  mov     rax, [rcx]
0x180016d82  mov     rax, [rax+10h]
0x180016d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d8b  nop
0x180016d8c  mov     eax, ebx
0x180016d8e  jmp     loc_180016F30
0x180016d93  mov     rbx, [rbp+57h+var_80]
0x180016d97  mov     rax, [rbx]
0x180016d9a  mov     r15, [rax+18h]
0x180016d9e  mov     rcx, rsi
0x180016da1  call    ?ProfileSourceFromProvSource@@YA?AW4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003@@PEBUIProvSource@@@Z; ProfileSourceFromProvSource(IProvSource const *)
0x180016da6  mov     edi, eax
0x180016da8  mov     rcx, [rsi]
0x180016dab  mov     rax, [rcx+38h]
0x180016daf  mov     rcx, rsi
0x180016db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016db7  cmp     qword ptr [rax+18h], 8
0x180016dbc  jb      short loc_180016DC1
0x180016dbe  mov     rax, [rax]
0x180016dc1  mov     r8d, edi
0x180016dc4  mov     rdx, rax
0x180016dc7  mov     rcx, rbx
0x180016dca  mov     rax, r15
0x180016dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dd2  mov     r15d, eax
0x180016dd5  test    eax, eax
0x180016dd7  jns     short loc_180016E3F
0x180016dd9  mov     ecx, cs:dword_18005A000
0x180016ddf  cmp     ecx, 2
0x180016de2  jbe     short loc_180016E22
0x180016de4  mov     dword ptr [rbp+57h+var_78], eax
0x180016de7  lea     rax, [rbp+57h+var_78]
0x180016deb  mov     [rbp+57h+var_38], rax
0x180016def  mov     [rbp+57h+var_30], 4
0x180016df7  lea     rax, [rbp+57h+var_58]
0x180016dfb  mov     [rsp+0B0h+var_88], rax
0x180016e00  mov     dword ptr [rsp+0B0h+ppv], 3
0x180016e08  xor     r9d, r9d
0x180016e0b  xor     r8d, r8d
0x180016e0e  lea     rdx, byte_18004F4F5
0x180016e15  lea     rcx, dword_18005A000
0x180016e1c  call    _tlgWriteTransfer_EventWriteTransfer
0x180016e21  nop
0x180016e22  mov     rcx, [rbp+57h+var_80]
0x180016e26  test    rcx, rcx
0x180016e29  jz      loc_180016F2D
0x180016e2f  mov     [rbp+57h+var_80], 0
0x180016e37  mov     rax, [rcx]
0x180016e3a  jmp     loc_180016F23
0x180016e3f  mov     rcx, [r14+120h]
0x180016e46  mov     rax, [rcx+8]
0x180016e4a  mov     rdi, rcx
0x180016e4d  cmp     byte ptr [rax+19h], 0
0x180016e51  jnz     short loc_180016E79
0x180016e53  cmp     [rax+20h], rsi
0x180016e57  jnb     short loc_180016E5F
0x180016e59  mov     rax, [rax+10h]
0x180016e5d  jmp     short loc_180016E65
0x180016e5f  mov     rdi, rax
0x180016e62  mov     rax, [rax]
0x180016e65  mov     rbx, rdi
0x180016e68  cmp     byte ptr [rax+19h], 0
0x180016e6c  jz      short loc_180016E53
0x180016e6e  cmp     rbx, rcx
0x180016e71  jz      short loc_180016E79
0x180016e73  cmp     rsi, [rdi+20h]
0x180016e77  jnb     short loc_180016ED3
0x180016e79  mov     [rbp+57h+var_70], rsi
0x180016e7d  mov     [rbp+57h+var_68], 0
0x180016e85  mov     [rbp+57h+var_60], 0
0x180016e8d  lea     rdx, [rbp+57h+var_70]
0x180016e91  lea     rcx, [r14+120h]
0x180016e98  call    ??$_Buynode@U?$pair@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@?$_Tree_buy@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@1@$$QEAU?$pair@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@1@@Z; std::_Tree_buy<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>::_Buynode<std::pair<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>(std::pair<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &&)
0x180016e9d  lea     r9, [rax+20h]
0x180016ea1  mov     [rsp+0B0h+ppv], rax
0x180016ea6  mov     r8, rdi
0x180016ea9  lea     rdx, [rbp+57h+var_78]
0x180016ead  lea     rcx, [r14+120h]
0x180016eb4  call    ??$_Insert_hint@AEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@U?$less@PEBUIProvSource@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@std@@@std@@@1@AEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_hint<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>>>,std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *)
0x180016eb9  mov     rbx, [rbp+57h+var_78]
0x180016ebd  mov     rcx, [rbp+57h+var_68]
0x180016ec1  test    rcx, rcx
0x180016ec4  jz      short loc_180016ED3
0x180016ec6  mov     rax, [rcx]
0x180016ec9  mov     rax, [rax+10h]
0x180016ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ed2  nop
0x180016ed3  mov     rdi, [rbp+57h+var_80]
0x180016ed7  cmp     [rbx+28h], rdi
0x180016edb  jz      short loc_180016F10
0x180016edd  test    rdi, rdi
0x180016ee0  jz      short loc_180016EF2
0x180016ee2  mov     rax, [rdi]
0x180016ee5  mov     rcx, rdi
0x180016ee8  mov     rax, [rax+8]
0x180016eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ef1  nop
0x180016ef2  mov     rcx, [rbx+28h]
0x180016ef6  mov     [rbx+28h], rdi
0x180016efa  test    rcx, rcx
0x180016efd  jz      short loc_180016F0C
0x180016eff  mov     rax, [rcx]
0x180016f02  mov     rax, [rax+10h]
0x180016f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f0b  nop
0x180016f0c  mov     rdi, [rbp+57h+var_80]
0x180016f10  test    rdi, rdi
0x180016f13  jz      short loc_180016F2D
0x180016f15  mov     [rbp+57h+var_80], 0
0x180016f1d  mov     rax, [rdi]
0x180016f20  mov     rcx, rdi
0x180016f23  mov     rax, [rax+10h]
0x180016f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f2c  nop
0x180016f2d  mov     eax, r15d
0x180016f30  mov     rcx, [rbp+57h+var_28]
0x180016f34  xor     rcx, rsp; StackCookie
0x180016f37  call    __security_check_cookie
0x180016f3c  mov     rbx, [rsp+0B0h+arg_10]
0x180016f44  add     rsp, 90h
0x180016f4b  pop     r15
0x180016f4d  pop     r14
0x180016f4f  pop     rdi
0x180016f50  pop     rsi
0x180016f51  pop     rbp
0x180016f52  retn
```
