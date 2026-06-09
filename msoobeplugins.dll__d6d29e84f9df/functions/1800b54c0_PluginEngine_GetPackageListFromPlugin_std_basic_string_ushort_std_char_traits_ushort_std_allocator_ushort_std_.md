# PluginEngine::GetPackageListFromPlugin(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>,std::allocator<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>>> *)

- ea: `0x1800b54c0`
- end: `0x1800b5893`
- name: `?GetPackageListFromPlugin@PluginEngine@@UEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@3@@Z`
- size: `979`
- prototype: `__int64 __fastcall(_QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180048600`

## callees

- `0x180003470`
- `0x180003df0`
- `0x180008544`
- `0x18003a9c4`
- `0x18003e4d4`
- `0x180048308`
- `0x180048340`
- `0x18004839c`
- `0x1800628a8`
- `0x1800b4838`
- `0x1800b4a00`
- `0x1800b54c0`
- `0x1800b7438`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b563c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b564c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b56d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b56e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5821`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b584c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b563c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b564c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b56d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b56e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5821`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b584c`

## string_xrefs

- `0x1800b5531`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b5579`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b560c`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b56a6`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::GetPackageListFromPlugin(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 (__fastcall *v6)(_QWORD *, __int64, unsigned int *); // rbx
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 **v11; // rax
  __int64 *v12; // rcx
  __int64 v13; // rax
  int v14; // r15d
  LPVOID *v15; // rcx
  unsigned int m; // edi
  LPVOID *v17; // rcx
  unsigned int k; // r14d
  unsigned int i; // edi
  char *v20; // rbx
  __int64 v21; // r12
  __int64 v22; // r15
  unsigned int j; // edi
  void *v24; // rcx
  int v25; // [rsp+20h] [rbp-E8h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-E0h] BYREF
  unsigned int v27; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v28[2]; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B8h] BYREF
  char v31; // [rsp+58h] [rbp-B0h]
  _QWORD v32[2]; // [rsp+68h] [rbp-A0h] BYREF
  char v33; // [rsp+78h] [rbp-90h]
  LPVOID **p_p_pv; // [rsp+88h] [rbp-80h]
  __int64 v35; // [rsp+90h] [rbp-78h]
  _BYTE v36[32]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v37 = a2;
  v27 = 0;
  v6 = *(__int64 (__fastcall **)(_QWORD *, __int64, unsigned int *))(*a1 + 80LL);
  v7 = std::wstring::wstring(v32, a2);
  v8 = v6(a1, v7, &v27);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( v27 < (unsigned __int64)((__int64)(a1[2] - a1[1]) >> 3) )
    {
      v25 = 0;
      pv = 0;
      v32[0] = &pv;
      v32[1] = &v25;
      v33 = 1;
      v11 = (__int64 **)std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(a1 + 1);
      v12 = *v11;
      v13 = **v11;
      p_pv = &pv;
      v30 = 0;
      v31 = 1;
      v14 = (*(__int64 (__fastcall **)(__int64 *, int *, __int64 *))(v13 + 32))(v12, &v25, &v30);
      wil::details::out_param_t<wistd::unique_ptr<_ProvPackageItem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ProvPackageItem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( v14 >= 0 )
      {
        if ( pv || !v25 )
        {
          if ( *a3 != a3[1] )
          {
            std::_Destroy_range<std::allocator<std::unique_ptr<ProvPackageInfo>>>(*a3);
            a3[1] = *a3;
          }
          for ( i = 0; i < v25; ++i )
          {
            v20 = (char *)operator new(0x60u);
            v28[0] = v20;
            p_p_pv = &p_pv;
            v21 = std::wstring::wstring(&p_pv, *((_QWORD *)pv + 3 * i + 1));
            v35 = v21;
            v22 = std::wstring::wstring(v36, *((_QWORD *)pv + 3 * i));
            v28[1] = v22;
            std::wstring::wstring(v20, v21);
            std::wstring::wstring(v20 + 32, v22);
            std::wstring::wstring(v20 + 64);
            std::wstring::_Tidy_deallocate(v22);
            std::wstring::_Tidy_deallocate(v21);
            v28[0] = v20;
            std::vector<std::unique_ptr<ProvPackageInfo>>::emplace_back<std::unique_ptr<ProvPackageInfo>>(a3, v28);
            std::unique_ptr<ProvPackageInfo>::~unique_ptr<ProvPackageInfo>(v28);
          }
          if ( pv && v25 )
          {
            for ( j = 0; j < v25; ++j )
            {
              CoTaskMemFree(*((LPVOID *)pv + 3 * j));
              CoTaskMemFree(*((LPVOID *)pv + 3 * j + 1));
            }
          }
          v24 = pv;
          pv = 0;
          if ( v24 )
            CoTaskMemFree(v24);
          std::wstring::_Tidy_deallocate(a2);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x76,
            (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
            (const char *)0x80070057LL,
            v25);
          v17 = (LPVOID *)pv;
          if ( pv )
          {
            for ( k = 0; k < v25; v17 = (LPVOID *)pv )
            {
              CoTaskMemFree(v17[3 * k]);
              CoTaskMemFree(*((LPVOID *)pv + 3 * k++ + 1));
            }
          }
          pv = 0;
          if ( v17 )
            CoTaskMemFree(v17);
          std::wstring::_Tidy_deallocate(a2);
          return 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x73,
          (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
          (const char *)(unsigned int)v14,
          v25);
        v15 = (LPVOID *)pv;
        if ( pv )
        {
          for ( m = 0; m < v25; v15 = (LPVOID *)pv )
          {
            CoTaskMemFree(v15[3 * m]);
            CoTaskMemFree(*((LPVOID *)pv + 3 * m++ + 1));
          }
        }
        pv = 0;
        if ( v15 )
          CoTaskMemFree(v15);
        std::wstring::_Tidy_deallocate(a2);
        return (unsigned int)v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)0x80070057LL,
        v25);
      std::wstring::_Tidy_deallocate(a2);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v8,
      v25);
    std::wstring::_Tidy_deallocate(a2);
    return v9;
  }
}

```

## disassembly

```asm
0x1800b54c0  mov     r11, rsp
0x1800b54c3  push    rbx
0x1800b54c4  push    rsi
0x1800b54c5  push    rdi
0x1800b54c6  push    r12
0x1800b54c8  push    r13
0x1800b54ca  push    r14
0x1800b54cc  push    r15
0x1800b54ce  sub     rsp, 0D0h
0x1800b54d5  mov     rax, cs:__security_cookie
0x1800b54dc  xor     rax, rsp
0x1800b54df  mov     [rsp+108h+var_48], rax
0x1800b54e7  mov     r14, r8
0x1800b54ea  mov     rsi, rdx
0x1800b54ed  mov     rdi, rcx
0x1800b54f0  mov     [r11-50h], rdx
0x1800b54f4  xor     r13d, r13d
0x1800b54f7  mov     [rsp+108h+var_D8], r13d
0x1800b54fc  mov     rax, [rcx]
0x1800b54ff  mov     rbx, [rax+50h]
0x1800b5503  lea     rcx, [rsp+108h+var_A0]
0x1800b5508  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b550d  lea     r8, [rsp+108h+var_D8]
0x1800b5512  mov     rdx, rax
0x1800b5515  mov     rcx, rdi
0x1800b5518  mov     rax, rbx
0x1800b551b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5520  mov     ebx, eax
0x1800b5522  test    eax, eax
0x1800b5524  jns     short loc_1800B5551
0x1800b5526  mov     rcx, [rsp+108h]; this
0x1800b552e  mov     r9d, eax; char *
0x1800b5531  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b5538  lea     edx, [r13+5Ch]; void *
0x1800b553c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5541  nop
0x1800b5542  mov     rcx, rsi
0x1800b5545  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b554a  mov     eax, ebx
0x1800b554c  jmp     loc_1800B5870
0x1800b5551  lea     rcx, [rdi+8]
0x1800b5555  mov     edx, [rsp+108h+var_D8]
0x1800b5559  mov     rax, [rcx+8]
0x1800b555d  sub     rax, [rcx]
0x1800b5560  sar     rax, 3
0x1800b5564  cmp     rdx, rax
0x1800b5567  jb      short loc_1800B559A
0x1800b5569  mov     rcx, [rsp+108h]; this
0x1800b5571  mov     edi, 80070057h
0x1800b5576  mov     r9d, edi; char *
0x1800b5579  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b5580  mov     edx, 61h ; 'a'; void *
0x1800b5585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b558a  nop
0x1800b558b  mov     rcx, rsi
0x1800b558e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5593  mov     eax, edi
0x1800b5595  jmp     loc_1800B5870
0x1800b559a  mov     [rsp+108h+var_E8], r13d; int
0x1800b559f  mov     [rsp+108h+pv], r13
0x1800b55a4  lea     r12, [rsp+108h+pv]
0x1800b55a9  mov     [rsp+108h+var_A0], r12
0x1800b55ae  lea     rbx, [rsp+108h+var_E8]
0x1800b55b3  mov     [rsp+108h+var_98], rbx
0x1800b55b8  mov     [rsp+108h+var_90], 1
0x1800b55bd  call    ?at@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@_K@Z; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(unsigned __int64)
0x1800b55c2  mov     rcx, [rax]
0x1800b55c5  mov     rax, [rcx]
0x1800b55c8  lea     rdx, [rsp+108h+pv]
0x1800b55cd  mov     [rsp+108h+var_C0], rdx
0x1800b55d2  mov     [rsp+108h+var_B8], r13
0x1800b55d7  mov     [rsp+108h+var_B0], 1
0x1800b55dc  lea     r8, [rsp+108h+var_B8]
0x1800b55e1  lea     rdx, [rsp+108h+var_E8]
0x1800b55e6  mov     rax, [rax+20h]
0x1800b55ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b55ef  mov     r15d, eax
0x1800b55f2  lea     rcx, [rsp+108h+var_C0]
0x1800b55f7  call    ??1?$out_param_t@V?$unique_ptr@U_ProvPackageItem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ProvPackageItem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ProvPackageItem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800b55fc  test    r15d, r15d
0x1800b55ff  jns     short loc_1800B5680
0x1800b5601  mov     rcx, [rsp+108h]; this
0x1800b5609  mov     r9d, r15d; char *
0x1800b560c  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b5613  mov     edx, 73h ; 's'; void *
0x1800b5618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b561d  nop
0x1800b561e  mov     rcx, [rsp+108h+pv]
0x1800b5623  test    rcx, rcx
0x1800b5626  jz      short loc_1800B565F
0x1800b5628  mov     edi, r13d
0x1800b562b  cmp     [rsp+108h+var_E8], r13d
0x1800b5630  jbe     short loc_1800B565F
0x1800b5632  mov     eax, edi
0x1800b5634  lea     rbx, [rax+rax*2]
0x1800b5638  mov     rcx, [rcx+rbx*8]; pv
0x1800b563c  call    cs:__imp_CoTaskMemFree
0x1800b5642  mov     rcx, [rsp+108h+pv]
0x1800b5647  mov     rcx, [rcx+rbx*8+8]; pv
0x1800b564c  call    cs:__imp_CoTaskMemFree
0x1800b5652  inc     edi
0x1800b5654  mov     rcx, [rsp+108h+pv]; pv
0x1800b5659  cmp     edi, [rsp+108h+var_E8]
0x1800b565d  jb      short loc_1800B5632
0x1800b565f  mov     [rsp+108h+pv], r13
0x1800b5664  test    rcx, rcx
0x1800b5667  jz      short loc_1800B5670
0x1800b5669  call    cs:__imp_CoTaskMemFree
0x1800b566f  nop
0x1800b5670  mov     rcx, rsi
0x1800b5673  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5678  mov     eax, r15d
0x1800b567b  jmp     loc_1800B5870
0x1800b5680  cmp     [rsp+108h+pv], r13
0x1800b5685  jnz     loc_1800B571C
0x1800b568b  cmp     [rsp+108h+var_E8], r13d
0x1800b5690  jz      loc_1800B571C
0x1800b5696  mov     rcx, [rsp+108h]; this
0x1800b569e  mov     edi, 80070057h
0x1800b56a3  mov     r9d, edi; char *
0x1800b56a6  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b56ad  mov     edx, 76h ; 'v'; void *
0x1800b56b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b56b7  nop
0x1800b56b8  mov     rcx, [rsp+108h+pv]
0x1800b56bd  test    rcx, rcx
0x1800b56c0  jz      short loc_1800B56FC
0x1800b56c2  mov     r14d, r13d
0x1800b56c5  cmp     [rsp+108h+var_E8], r13d
0x1800b56ca  jbe     short loc_1800B56FC
0x1800b56cc  mov     eax, r14d
0x1800b56cf  lea     rbx, [rax+rax*2]
0x1800b56d3  mov     rcx, [rcx+rbx*8]; pv
0x1800b56d7  call    cs:__imp_CoTaskMemFree
0x1800b56dd  mov     rcx, [rsp+108h+pv]
0x1800b56e2  mov     rcx, [rcx+rbx*8+8]; pv
0x1800b56e7  call    cs:__imp_CoTaskMemFree
0x1800b56ed  inc     r14d
0x1800b56f0  mov     rcx, [rsp+108h+pv]; pv
0x1800b56f5  cmp     r14d, [rsp+108h+var_E8]
0x1800b56fa  jb      short loc_1800B56CC
0x1800b56fc  mov     [rsp+108h+pv], r13
0x1800b5701  test    rcx, rcx
0x1800b5704  jz      short loc_1800B570D
0x1800b5706  call    cs:__imp_CoTaskMemFree
0x1800b570c  nop
0x1800b570d  mov     rcx, rsi
0x1800b5710  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5715  mov     eax, edi
0x1800b5717  jmp     loc_1800B5870
0x1800b571c  mov     rdx, [r14+8]
0x1800b5720  cmp     [r14], rdx
0x1800b5723  jz      short loc_1800B5734
0x1800b5725  mov     rcx, [r14]
0x1800b5728  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<ProvPackageInfo>>>(std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> * const,std::allocator<std::unique_ptr<ProvPackageInfo>> &)
0x1800b572d  mov     rax, [r14]
0x1800b5730  mov     [r14+8], rax
0x1800b5734  mov     edi, r13d
0x1800b5737  cmp     edi, [rsp+108h+var_E8]
0x1800b573b  jnb     loc_1800B57FB
0x1800b5741  mov     ecx, 60h ; '`'; Size
0x1800b5746  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b574b  mov     rbx, rax
0x1800b574e  mov     [rsp+108h+var_D0], rax
0x1800b5753  lea     rax, [rsp+108h+var_C0]
0x1800b5758  mov     [rsp+108h+var_80], rax
0x1800b5760  mov     ecx, edi
0x1800b5762  lea     r15, [rcx+rcx*2]
0x1800b5766  mov     rdx, [rsp+108h+pv]
0x1800b576b  mov     rdx, [rdx+r15*8+8]
0x1800b5770  lea     rcx, [rsp+108h+var_C0]
0x1800b5775  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b577a  mov     r12, rax
0x1800b577d  mov     [rsp+108h+var_78], rax
0x1800b5785  mov     rdx, [rsp+108h+pv]
0x1800b578a  mov     rdx, [rdx+r15*8]
0x1800b578e  lea     rcx, [rsp+108h+var_70]
0x1800b5796  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b579b  mov     r15, rax
0x1800b579e  mov     [rsp+108h+var_C8], rax
0x1800b57a3  mov     rdx, r12
0x1800b57a6  mov     rcx, rbx
0x1800b57a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b57ae  nop
0x1800b57af  lea     rcx, [rbx+20h]
0x1800b57b3  mov     rdx, r15
0x1800b57b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b57bb  lea     rcx, [rbx+40h]
0x1800b57bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b57c4  nop
0x1800b57c5  mov     rcx, r15
0x1800b57c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b57cd  nop
0x1800b57ce  mov     rcx, r12
0x1800b57d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b57d6  nop
0x1800b57d7  mov     [rsp+108h+var_D0], rbx
0x1800b57dc  lea     rdx, [rsp+108h+var_D0]
0x1800b57e1  mov     rcx, r14
0x1800b57e4  call    ??$emplace_back@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<ProvPackageInfo>>::emplace_back<std::unique_ptr<ProvPackageInfo>>(std::unique_ptr<ProvPackageInfo> &&)
0x1800b57e9  nop
0x1800b57ea  lea     rcx, [rsp+108h+var_D0]
0x1800b57ef  call    ??1?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<ProvPackageInfo>::~unique_ptr<ProvPackageInfo>(void)
0x1800b57f4  inc     edi
0x1800b57f6  jmp     loc_1800B5737
0x1800b57fb  lea     r12, [rsp+108h+pv]
0x1800b5800  cmp     [r12], r13
0x1800b5804  jz      short loc_1800B583D
0x1800b5806  lea     r14, [rsp+108h+var_E8]
0x1800b580b  cmp     [r14], r13d
0x1800b580e  jbe     short loc_1800B583D
0x1800b5810  mov     edi, r13d
0x1800b5813  mov     eax, edi
0x1800b5815  lea     rbx, [rax+rax*2]
0x1800b5819  mov     rcx, [r12]
0x1800b581d  mov     rcx, [rcx+rbx*8]; pv
0x1800b5821  call    cs:__imp_CoTaskMemFree
0x1800b5827  mov     rcx, [r12]
0x1800b582b  mov     rcx, [rcx+rbx*8+8]; pv
0x1800b5830  call    cs:__imp_CoTaskMemFree
0x1800b5836  inc     edi
0x1800b5838  cmp     edi, [r14]
0x1800b583b  jb      short loc_1800B5813
0x1800b583d  mov     rcx, [rsp+108h+pv]; pv
0x1800b5842  mov     [rsp+108h+pv], r13
0x1800b5847  test    rcx, rcx
0x1800b584a  jz      short loc_1800B5853
0x1800b584c  call    cs:__imp_CoTaskMemFree
0x1800b5852  nop
0x1800b5853  mov     rcx, rsi
0x1800b5856  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b585b  xor     eax, eax
0x1800b585d  jmp     short loc_1800B5870
0x1800b585f  mov     rcx, [rsp+108h+var_50]
0x1800b5867  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b586c  mov     eax, [rsp+108h+var_E8]
0x1800b5870  mov     rcx, [rsp+108h+var_48]
0x1800b5878  xor     rcx, rsp; StackCookie
0x1800b587b  call    __security_check_cookie
0x1800b5880  add     rsp, 0D0h
0x1800b5887  pop     r15
0x1800b5889  pop     r14
0x1800b588b  pop     r13
0x1800b588d  pop     r12
0x1800b588f  pop     rdi
0x1800b5890  pop     rsi
0x1800b5891  pop     rbx
0x1800b5892  retn
```
