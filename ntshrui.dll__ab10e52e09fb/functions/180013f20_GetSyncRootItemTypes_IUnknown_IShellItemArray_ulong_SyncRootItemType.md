# _GetSyncRootItemTypes(IUnknown *,IShellItemArray *,ulong *,SyncRootItemType *)

- ea: `0x180013f20`
- end: `0x1800143cb`
- name: `?_GetSyncRootItemTypes@@YAJPEAUIUnknown@@PEAUIShellItemArray@@PEAKPEAW4SyncRootItemType@@@Z`
- size: `1195`
- prototype: `__int64 __fastcall(IUnknown *punk, struct IShellItemArray *, unsigned int *, enum SyncRootItemType *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013c80`
- `0x18001f880`

## callees

- `0x180008900`
- `0x180013f20`
- `0x180016004`
- `0x18001c4a8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014053`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014053`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014176`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014176`
- `SHCORE!IUnknown_QueryService` at `0x180014301`
- `SHCORE!IUnknown_QueryService` at `0x180014301`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180014254`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180014254`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall _GetSyncRootItemTypes(
        IUnknown *punk,
        struct IShellItemArray *a2,
        unsigned int *a3,
        enum SyncRootItemType *a4)
{
  HRESULT v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, void **); // rdi
  int v10; // eax
  unsigned int v11; // r15d
  unsigned int v12; // edi
  struct IShellItem *v13; // rbx
  int v14; // eax
  void *v15; // rcx
  struct IShellItem *v16; // rcx
  LPVOID v17; // rcx
  int (__fastcall ***v18)(_QWORD, GUID *, void **); // rcx
  __int64 v19; // rcx
  int v21; // r12d
  unsigned int v22; // r15d
  __int16 v23; // ax
  __int64 v24; // [rsp+30h] [rbp-30h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, void **); // [rsp+38h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  struct IShellItem *v28; // [rsp+50h] [rbp-10h] BYREF
  __int64 v29; // [rsp+58h] [rbp-8h] BYREF
  void *ppvOut; // [rsp+A8h] [rbp+48h] BYREF
  void *pulRet; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v32; // [rsp+B8h] [rbp+58h] BYREF

  if ( a3 )
    *a3 = 0;
  *(_DWORD *)a4 = 0;
  v24 = 0;
  v25 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v25);
  v25 = 0;
  if ( a2 )
  {
    v8 = ((__int64 (__fastcall *)(struct IShellItemArray *, GUID *, _QWORD))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
           &v25);
  }
  else
  {
    ppvOut = 0;
    v8 = IUnknown_QueryService(punk, &IID_IFolderView, &GUID_cde725b0_ccc9_4519_917e_325d72fab4ce, &ppvOut);
    if ( v8 >= 0 )
      v8 = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD))(*(_QWORD *)ppvOut + 40LL))(
             ppvOut,
             &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
             &v25);
    ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&ppvOut);
  }
  if ( v8 >= 0 )
  {
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v24);
    v9 = v25;
    v24 = 0;
    LODWORD(ppvOut) = 0;
    pulRet = 0;
    if ( (int)(**v25)(v25, &GUID_d4c5a1a7_e152_4a59_b3f6_0190a5a6d385, &pulRet) < 0 )
    {
      v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, void **), void **))(*v9)[7])(v9, &ppvOut);
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)pulRet + 24LL))(pulRet, &ppvOut);
      (*(void (__fastcall **)(void *))(*(_QWORD *)pulRet + 16LL))(pulRet);
    }
    if ( v8 >= 0 )
    {
      if ( (unsigned int)ppvOut > 0x10 )
      {
        pulRet = 0;
        v8 = SHCoCreateInstance(
               0,
               &CLSID_ShellItemArrayAsCollection,
               0,
               &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
               &pulRet);
        v21 = 0;
        v22 = 0;
        if ( v8 >= 0 )
        {
          while ( v21 >= 0 && v22 < 0x10 )
          {
            v32 = 0;
            v21 = (*v9)[8](v9, (GUID *)v22, (void **)&v32);
            if ( v21 >= 0 )
              v8 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)pulRet + 40LL))(pulRet, v32);
            if ( v32 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            ++v22;
            if ( v8 < 0 )
              goto LABEL_50;
          }
          v8 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))pulRet)(
                 pulRet,
                 &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                 &v24);
        }
LABEL_50:
        if ( pulRet )
          (*(void (__fastcall **)(void *))(*(_QWORD *)pulRet + 16LL))(pulRet);
      }
      else
      {
        v8 = (**v9)(v9, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, (void **)&v24);
      }
      if ( v8 >= 0 )
      {
        ppv = 0;
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
        v8 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
        if ( v8 >= 0 )
        {
          LODWORD(ppvOut) = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v24 + 56LL))(v24, &ppvOut);
          v8 = v10;
          v11 = 100;
          if ( (unsigned int)ppvOut < 0x64 )
            v11 = (unsigned int)ppvOut;
          v12 = 0;
          if ( v10 >= 0 )
          {
            while ( v12 < v11 && !*(_DWORD *)a4 )
            {
              v28 = 0;
              v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IShellItem **))(*(_QWORD *)v24 + 64LL))(
                     v24,
                     v12,
                     &v28);
              if ( v8 >= 0 )
              {
                v13 = v28;
                pv = 0;
                LODWORD(pulRet) = 0;
                if ( ((unsigned int (__fastcall *)(struct IShellItem *, __int64, void **))v28->lpVtbl->GetAttributes)(
                       v28,
                       0x40000000,
                       &pulRet)
                  && ((LODWORD(pulRet) = 0, (int)IShellItem_GetFilePlaceholderStatus(v13, (ULONG *)&pulRet) < 0)
                   || ((unsigned __int8)pulRet & 2) != 0)
                  || ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))v13->lpVtbl->GetDisplayName)(
                       v13,
                       2147647488LL,
                       &pv) < 0 )
                {
                  v8 = 0;
                }
                else
                {
                  v29 = 0;
                  LODWORD(pulRet) = 0;
                  v14 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64 *, _QWORD, void **))(*(_QWORD *)ppv + 32LL))(
                          ppv,
                          pv,
                          &v29,
                          0,
                          &pulRet);
                  v8 = v14;
                  if ( v14 >= 0 )
                  {
                    if ( ((unsigned __int8)pulRet & 2) != 0 )
                      *(_DWORD *)a4 |= 2u;
                    LODWORD(v32) = 0;
                    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 168LL))(v29, &v32);
                    if ( v8 >= 0 )
                    {
                      v23 = v32;
                      if ( (v32 & 1) != 0 )
                        *(_DWORD *)a4 |= 1u;
                      if ( (v23 & 0x100) != 0 )
                        *(_DWORD *)a4 |= 4u;
                    }
                  }
                  else if ( v14 == -2147023728 )
                  {
                    v8 = 0;
                  }
                  if ( v29 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                }
                v15 = pv;
                pv = 0;
                CoTaskMemFree(v15);
              }
              v16 = v28;
              if ( v28 )
              {
                v28 = 0;
                ((void (__fastcall *)(struct IShellItem *))v16->lpVtbl->Release)(v16);
              }
              ++v12;
              if ( v8 < 0 )
                goto LABEL_33;
            }
            if ( a3 )
              *a3 = (unsigned int)ppvOut;
          }
        }
LABEL_33:
        v17 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
    }
  }
  v18 = (int (__fastcall ***)(_QWORD, GUID *, void **))v25;
  if ( v25 )
  {
    v25 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, void **)))(*v18)[2])(v18);
  }
  v19 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180013f20  mov     [rsp-38h+arg_0], rbx
0x180013f25  push    rbp
0x180013f26  push    rsi
0x180013f27  push    rdi
0x180013f28  push    r12
0x180013f2a  push    r13
0x180013f2c  push    r14
0x180013f2e  push    r15
0x180013f30  mov     rbp, rsp
0x180013f33  sub     rsp, 60h
0x180013f37  mov     rsi, r9
0x180013f3a  mov     r14, r8
0x180013f3d  mov     rbx, rdx
0x180013f40  mov     rdi, rcx
0x180013f43  xor     r13d, r13d
0x180013f46  test    r8, r8
0x180013f49  jz      short loc_180013F4E
0x180013f4b  mov     [r8], r13d
0x180013f4e  mov     [r9], r13d
0x180013f51  mov     [rbp+var_30], r13
0x180013f55  mov     [rbp+var_28], r13
0x180013f59  lea     rcx, [rbp+var_28]
0x180013f5d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180013f62  mov     [rbp+var_28], r13
0x180013f66  test    rbx, rbx
0x180013f69  jz      loc_1800142E8
0x180013f6f  mov     rax, [rbx]
0x180013f72  lea     r8, [rbp+var_28]
0x180013f76  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x180013f7d  mov     rcx, rbx
0x180013f80  mov     rax, [rax]
0x180013f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f88  mov     ebx, eax
0x180013f8a  test    ebx, ebx
0x180013f8c  js      loc_1800141C8
0x180013f92  lea     rcx, [rbp+var_30]
0x180013f96  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180013f9b  mov     rdi, [rbp+var_28]
0x180013f9f  mov     [rbp+var_30], r13
0x180013fa3  mov     dword ptr [rbp+ppvOut], r13d
0x180013fa7  mov     [rbp+pulRet], r13
0x180013fab  mov     rax, [rdi]
0x180013fae  lea     r8, [rbp+pulRet]
0x180013fb2  lea     rdx, _GUID_d4c5a1a7_e152_4a59_b3f6_0190a5a6d385
0x180013fb9  mov     rcx, rdi
0x180013fbc  mov     rax, [rax]
0x180013fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fc4  lea     rdx, [rbp+ppvOut]
0x180013fc8  test    eax, eax
0x180013fca  js      loc_18001421E
0x180013fd0  mov     rcx, [rbp+pulRet]
0x180013fd4  mov     rax, [rcx]
0x180013fd7  mov     rax, [rax+18h]
0x180013fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fe0  mov     ebx, eax
0x180013fe2  mov     rcx, [rbp+pulRet]
0x180013fe6  mov     rax, [rcx]
0x180013fe9  mov     rax, [rax+10h]
0x180013fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ff2  test    ebx, ebx
0x180013ff4  js      loc_1800141C8
0x180013ffa  cmp     dword ptr [rbp+ppvOut], 10h
0x180013ffe  ja      loc_180014234
0x180014004  mov     rax, [rdi]
0x180014007  lea     r8, [rbp+var_30]
0x18001400b  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x180014012  mov     rcx, rdi
0x180014015  mov     rax, [rax]
0x180014018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001401d  mov     ebx, eax
0x18001401f  test    ebx, ebx
0x180014021  js      loc_1800141C8
0x180014027  mov     [rbp+var_20], r13
0x18001402b  lea     rcx, [rbp+var_20]
0x18001402f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180014034  lea     rax, [rbp+var_20]
0x180014038  mov     [rsp+60h+ppv], rax; ppv
0x18001403d  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180014044  xor     edx, edx; pUnkOuter
0x180014046  mov     r8d, 1; dwClsContext
0x18001404c  lea     rcx, CLSID_SyncRootManager; rclsid
0x180014053  call    cs:__imp_CoCreateInstance
0x180014059  mov     ebx, eax
0x18001405b  test    eax, eax
0x18001405d  js      loc_1800141AE
0x180014063  mov     dword ptr [rbp+ppvOut], r13d
0x180014067  mov     rcx, [rbp+var_30]
0x18001406b  mov     rax, [rcx]
0x18001406e  lea     rdx, [rbp+ppvOut]
0x180014072  mov     rax, [rax+38h]
0x180014076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001407b  mov     ebx, eax
0x18001407d  mov     r15d, 64h ; 'd'
0x180014083  cmp     dword ptr [rbp+ppvOut], r15d
0x180014087  cmovb   r15d, dword ptr [rbp+ppvOut]
0x18001408c  mov     edi, r13d
0x18001408f  test    eax, eax
0x180014091  js      loc_1800141AE
0x180014097  cmp     edi, r15d
0x18001409a  jnb     loc_1800141A3
0x1800140a0  cmp     dword ptr [rsi], 0
0x1800140a3  jnz     loc_1800141A3
0x1800140a9  mov     [rbp+var_10], r13
0x1800140ad  mov     rcx, [rbp+var_30]
0x1800140b1  mov     rax, [rcx]
0x1800140b4  lea     r8, [rbp+var_10]
0x1800140b8  mov     edx, edi
0x1800140ba  mov     rax, [rax+40h]
0x1800140be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140c3  mov     ebx, eax
0x1800140c5  test    eax, eax
0x1800140c7  js      loc_18001417D
0x1800140cd  mov     rbx, [rbp+var_10]
0x1800140d1  mov     [rbp+pv], r13
0x1800140d5  mov     dword ptr [rbp+pulRet], r13d
0x1800140d9  mov     rax, [rbx]
0x1800140dc  lea     r8, [rbp+pulRet]
0x1800140e0  mov     edx, 40000000h
0x1800140e5  mov     rcx, rbx
0x1800140e8  mov     rax, [rax+30h]
0x1800140ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140f1  test    eax, eax
0x1800140f3  jnz     loc_180014359
0x1800140f9  mov     rax, [rbx]
0x1800140fc  lea     r8, [rbp+pv]
0x180014100  mov     edx, 80028000h
0x180014105  mov     rcx, rbx
0x180014108  mov     rax, [rax+28h]
0x18001410c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014111  test    eax, eax
0x180014113  js      loc_180014216
0x180014119  mov     [rbp+var_8], r13
0x18001411d  mov     dword ptr [rbp+pulRet], r13d
0x180014121  mov     rcx, [rbp+var_20]
0x180014125  mov     rax, [rcx]
0x180014128  lea     rdx, [rbp+pulRet]
0x18001412c  mov     [rsp+60h+ppv], rdx
0x180014131  xor     r9d, r9d
0x180014134  lea     r8, [rbp+var_8]
0x180014138  mov     rdx, [rbp+pv]
0x18001413c  mov     rax, [rax+20h]
0x180014140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014145  mov     ebx, eax
0x180014147  test    eax, eax
0x180014149  jns     loc_180014380
0x18001414f  cmp     eax, 80070490h
0x180014154  cmovz   ebx, r13d
0x180014158  mov     rcx, [rbp+var_8]
0x18001415c  test    rcx, rcx
0x18001415f  jz      short loc_18001416E
0x180014161  mov     rax, [rcx]
0x180014164  mov     rax, [rax+10h]
0x180014168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001416d  nop
0x18001416e  mov     rcx, [rbp+pv]; pv
0x180014172  mov     [rbp+pv], r13
0x180014176  call    cs:__imp_CoTaskMemFree
0x18001417c  nop
0x18001417d  mov     rcx, [rbp+var_10]
0x180014181  test    rcx, rcx
0x180014184  jz      short loc_180014197
0x180014186  mov     [rbp+var_10], r13
0x18001418a  mov     rax, [rcx]
0x18001418d  mov     rax, [rax+10h]
0x180014191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014196  nop
0x180014197  inc     edi
0x180014199  test    ebx, ebx
0x18001419b  jns     loc_180014097
0x1800141a1  jmp     short loc_1800141AE
0x1800141a3  test    r14, r14
0x1800141a6  jz      short loc_1800141AE
0x1800141a8  mov     eax, dword ptr [rbp+ppvOut]
0x1800141ab  mov     [r14], eax
0x1800141ae  mov     rcx, [rbp+var_20]
0x1800141b2  test    rcx, rcx
0x1800141b5  jz      short loc_1800141C8
0x1800141b7  mov     [rbp+var_20], r13
0x1800141bb  mov     rax, [rcx]
0x1800141be  mov     rax, [rax+10h]
0x1800141c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141c7  nop
0x1800141c8  mov     rcx, [rbp+var_28]
0x1800141cc  test    rcx, rcx
0x1800141cf  jz      short loc_1800141E2
0x1800141d1  mov     [rbp+var_28], r13
0x1800141d5  mov     rax, [rcx]
0x1800141d8  mov     rax, [rax+10h]
0x1800141dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141e1  nop
0x1800141e2  mov     rcx, [rbp+var_30]
0x1800141e6  test    rcx, rcx
0x1800141e9  jz      short loc_1800141FC
0x1800141eb  mov     [rbp+var_30], r13
0x1800141ef  mov     rax, [rcx]
0x1800141f2  mov     rax, [rax+10h]
0x1800141f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141fb  nop
0x1800141fc  mov     eax, ebx
0x1800141fe  mov     rbx, [rsp+60h+arg_0]
0x180014206  add     rsp, 60h
0x18001420a  pop     r15
0x18001420c  pop     r14
0x18001420e  pop     r13
0x180014210  pop     r12
0x180014212  pop     rdi
0x180014213  pop     rsi
0x180014214  pop     rbp
0x180014215  retn
0x180014216  mov     ebx, r13d
0x180014219  jmp     loc_18001416E
0x18001421e  mov     rax, [rdi]
0x180014221  mov     rcx, rdi
0x180014224  mov     rax, [rax+38h]
0x180014228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001422d  mov     ebx, eax
0x18001422f  jmp     loc_180013FF2
0x180014234  mov     [rbp+pulRet], r13
0x180014238  lea     rax, [rbp+pulRet]
0x18001423c  mov     [rsp+60h+ppv], rax; ppv
0x180014241  lea     r9, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; riid
0x180014248  xor     r8d, r8d; pUnkOuter
0x18001424b  lea     rdx, CLSID_ShellItemArrayAsCollection; pclsid
0x180014252  xor     ecx, ecx; pszCLSID
0x180014254  call    cs:__imp_SHCoCreateInstance
0x18001425a  mov     ebx, eax
0x18001425c  mov     r12d, r13d
0x18001425f  mov     r15d, r13d
0x180014262  test    eax, eax
0x180014264  js      short loc_1800142CD
0x180014266  test    r12d, r12d
0x180014269  js      loc_180014338
0x18001426f  cmp     r15d, 10h
0x180014273  jnb     loc_180014338
0x180014279  mov     [rbp+arg_18], r13
0x18001427d  mov     rax, [rdi]
0x180014280  lea     r8, [rbp+arg_18]
0x180014284  mov     edx, r15d
0x180014287  mov     rcx, rdi
0x18001428a  mov     rax, [rax+40h]
0x18001428e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014293  mov     r12d, eax
0x180014296  test    eax, eax
0x180014298  js      short loc_1800142B0
0x18001429a  mov     rcx, [rbp+pulRet]
0x18001429e  mov     r8, [rcx]
0x1800142a1  mov     rdx, [rbp+arg_18]
0x1800142a5  mov     rax, [r8+28h]
0x1800142a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ae  mov     ebx, eax
0x1800142b0  mov     rcx, [rbp+arg_18]
0x1800142b4  test    rcx, rcx
0x1800142b7  jz      short loc_1800142C6
0x1800142b9  mov     rax, [rcx]
0x1800142bc  mov     rax, [rax+10h]
0x1800142c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142c5  nop
0x1800142c6  inc     r15d
0x1800142c9  test    ebx, ebx
0x1800142cb  jns     short loc_180014266
0x1800142cd  mov     rcx, [rbp+pulRet]
0x1800142d1  test    rcx, rcx
0x1800142d4  jz      short loc_1800142E3
0x1800142d6  mov     rax, [rcx]
0x1800142d9  mov     rax, [rax+10h]
0x1800142dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e2  nop
0x1800142e3  jmp     loc_18001401F
0x1800142e8  mov     [rbp+ppvOut], r13
0x1800142ec  lea     r9, [rbp+ppvOut]; ppvOut
0x1800142f0  lea     r8, _GUID_cde725b0_ccc9_4519_917e_325d72fab4ce; riid
0x1800142f7  lea     rdx, IID_IFolderView; guidService
0x1800142fe  mov     rcx, rdi; punk
0x180014301  call    cs:__imp_IUnknown_QueryService
0x180014307  mov     ebx, eax
0x180014309  test    eax, eax
0x18001430b  js      short loc_18001432A
0x18001430d  mov     rcx, [rbp+ppvOut]
0x180014311  mov     rax, [rcx]
0x180014314  lea     r8, [rbp+var_28]
0x180014318  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x18001431f  mov     rax, [rax+28h]
0x180014323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014328  mov     ebx, eax
0x18001432a  lea     rcx, [rbp+ppvOut]
0x18001432e  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180014333  jmp     loc_180013F8A
0x180014338  mov     rcx, [rbp+pulRet]
0x18001433c  mov     rax, [rcx]
0x18001433f  lea     r8, [rbp+var_30]
0x180014343  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x18001434a  mov     rax, [rax]
0x18001434d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014352  mov     ebx, eax
0x180014354  jmp     loc_1800142CD
0x180014359  mov     dword ptr [rbp+pulRet], r13d
0x18001435d  lea     rdx, [rbp+pulRet]; pulRet
0x180014361  mov     rcx, rbx; struct IShellItem *
0x180014364  call    ?IShellItem_GetFilePlaceholderStatus@@YAJPEAUIShellItem@@PEAK@Z; IShellItem_GetFilePlaceholderStatus(IShellItem *,ulong *)
0x180014369  test    eax, eax
  ... truncated ...
```
