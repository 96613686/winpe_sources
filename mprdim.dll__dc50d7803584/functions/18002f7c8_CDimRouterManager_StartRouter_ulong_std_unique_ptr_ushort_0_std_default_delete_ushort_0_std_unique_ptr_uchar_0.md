# CDimRouterManager::StartRouter(ulong,std::unique_ptr<ushort [0],std::default_delete<ushort [0]>> &,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,ulong,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,ulong)

- ea: `0x18002f7c8`
- end: `0x18002fab8`
- name: `?StartRouter@CDimRouterManager@@AEAAKKAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@3@K1K@Z`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002de10`
- `0x18002eb5c`

## callees

- `0x18000b604`
- `0x18000def0`
- `0x18001abd0`
- `0x18002d814`
- `0x18002da54`
- `0x18002ed7c`
- `0x18002f7c8`
- `0x18002fe4c`
- `0x18003012c`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f89e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f89e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fa46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fa46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002faad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002faad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f88c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f88c`

## string_xrefs

- `0x18002f8c6`: `CDimRouterManager::StartRouter returned %d for protocolId %d`

## pseudocode

```c
__int64 __fastcall CDimRouterManager::StartRouter(
        __int64 a1,
        unsigned int a2,
        LPCWSTR *a3,
        void **a4,
        int a5,
        _QWORD *a6,
        unsigned int a7)
{
  _QWORD *v11; // rax
  _QWORD *v12; // rdi
  void *v13; // rcx
  unsigned int v14; // edx
  unsigned int RouterManagerDll; // esi
  FARPROC ProcAddress; // r10
  RTL_SRWLOCK *v18; // r12
  __int64 v19; // r14
  __int64 v20; // rbx
  __int64 v21; // rax
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v23[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v22 = a2;
  v11 = operator new(0x188u);
  v23[0] = v11;
  v12 = v11;
  if ( v11 )
  {
    v11[47] = 0;
    memset_0(v11, 0, 0x168u);
    *((_BYTE *)v12 + 360) = 0;
    v12[46] = 0;
    *((_DWORD *)v12 + 96) = 0;
  }
  else
  {
    v12 = 0;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  RouterManagerDll = CDimRouterManager::LoadRouterManagerDll(v13, (HMODULE *)v12 + 46, a3);
  if ( RouterManagerDll )
    goto LABEL_7;
  ProcAddress = GetProcAddress((HMODULE)v12[46], "StartRouter");
  if ( ProcAddress )
  {
    v12[25] = DIMConnectInterface;
    v12[26] = DIMDisconnectInterface;
    v12[27] = DIMSaveInterfaceInfo;
    v12[28] = DIMRestoreInterfaceInfo;
    v12[29] = DIMSaveGlobalInfo;
    v12[30] = DIMRouterStopped;
    v12[31] = DIMInterfaceEnabled;
    v12[32] = DIMGetRouterPhoneBookInfo;
    v12[33] = DIMGetInterfaceHandle;
    v12[42] = DIMGetInterfaceDeviceGuid;
    v12[43] = DIMGetRoutingDomainIdForInterface;
    v12[44] = DIMGetInfoForTenantInterface;
    *((_DWORD *)v12 + 68) = *(_BYTE *)(a1 + 56) == 1;
    RouterManagerDll = ((__int64 (__fastcall *)(_QWORD *, bool, _QWORD, _QWORD, unsigned int))ProcAddress)(
                         v12,
                         (gblDIMConfigInfo & 0x12) == gblDIMConfigInfo,
                         *a6,
                         a7,
                         a2);
    if ( !RouterManagerDll )
    {
      if ( a5 )
      {
        std::unique_ptr<unsigned char [0]>::operator=((void **)v12 + 47, a4);
        *((_DWORD *)v12 + 96) = a5;
      }
      *((_BYTE *)v12 + 360) = 1;
      goto LABEL_17;
    }
LABEL_7:
    if ( v12 )
      CDimRouterManager::_ROUTER::`scalar deleting destructor'((CDimRouterManager::_ROUTER *)v12, v14);
    goto LABEL_9;
  }
  RouterManagerDll = GetLastError();
  if ( RouterManagerDll )
    goto LABEL_7;
LABEL_17:
  v18 = (RTL_SRWLOCK *)(a1 + 8);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  v19 = a1 + 24;
  std::_Tree<std::_Tmap_traits<unsigned long,CDimRouterManager::_ROUTER *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CDimRouterManager::_ROUTER *>>,0>>::lower_bound(
    v19,
    v23,
    &v22);
  v20 = v23[0];
  if ( v23[0] == *(_QWORD *)(v19 + 8) || a2 < *(_DWORD *)(v23[0] + 24LL) )
  {
    LODWORD(v23[0]) = a2;
    v23[1] = 0;
    v21 = std::_Tree_val<std::_Tmap_traits<unsigned long,CDimRouterManager::_ROUTER *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CDimRouterManager::_ROUTER *>>,0>>::_Buynode<std::pair<unsigned long const,CDimRouterManager::_ROUTER *>>(
            v19,
            v23);
    std::_Tree<std::_Tmap_traits<unsigned long,CDimRouterManager::_ROUTER *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CDimRouterManager::_ROUTER *>>,0>>::_Insert(
      v19,
      v23,
      v20,
      v21);
    v20 = v23[0];
  }
  *(_QWORD *)(v20 + 32) = v12;
  ReleaseSRWLockExclusive(v18);
LABEL_9:
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"CDimRouterManager::StartRouter returned %d for protocolId %d", RouterManagerDll, a2);
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v24);
  }
  return RouterManagerDll;
}

```

## disassembly

```asm
0x18002f7c8  push    rbp
0x18002f7ca  push    rbx
0x18002f7cb  push    rsi
0x18002f7cc  push    rdi
0x18002f7cd  push    r12
0x18002f7cf  push    r13
0x18002f7d1  push    r14
0x18002f7d3  push    r15
0x18002f7d5  lea     rbp, [rsp-768h]
0x18002f7dd  sub     rsp, 868h
0x18002f7e4  mov     rax, cs:__security_cookie
0x18002f7eb  xor     rax, rsp
0x18002f7ee  mov     [rbp+7A0h+var_50], rax
0x18002f7f5  mov     r13, [rbp+7A0h+arg_28]
0x18002f7fc  mov     r14, rcx
0x18002f7ff  mov     ecx, 188h; Size
0x18002f804  mov     [rsp+8A0h+var_870], edx
0x18002f808  mov     r12, r9
0x18002f80b  mov     rsi, r8
0x18002f80e  mov     r15d, edx
0x18002f811  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f816  xor     ebx, ebx
0x18002f818  mov     [rsp+8A0h+var_868], rax
0x18002f81d  mov     rdi, rax
0x18002f820  test    rax, rax
0x18002f823  jz      short loc_18002F851
0x18002f825  xor     edx, edx; Val
0x18002f827  mov     [rax+178h], rbx
0x18002f82e  mov     r8d, 168h; Size
0x18002f834  mov     rcx, rax; void *
0x18002f837  call    memset_0
0x18002f83c  mov     [rdi+168h], bl
0x18002f842  mov     [rdi+170h], rbx
0x18002f849  mov     [rdi+180h], ebx
0x18002f84f  jmp     short loc_18002F854
0x18002f851  mov     rdi, rbx
0x18002f854  xor     edx, edx; Val
0x18002f856  mov     [rsp+8A0h+var_850], ebx
0x18002f85a  mov     r8d, 7FCh; Size
0x18002f860  lea     rcx, [rsp+8A0h+var_84C]; void *
0x18002f865  call    memset_0
0x18002f86a  lea     rbx, [rdi+170h]
0x18002f871  mov     r8, rsi
0x18002f874  mov     rdx, rbx
0x18002f877  call    ?LoadRouterManagerDll@CDimRouterManager@@AEAAKAEAPEAUHINSTANCE__@@AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@@Z; CDimRouterManager::LoadRouterManagerDll(HINSTANCE__ * &,std::unique_ptr<ushort [0]> &)
0x18002f87c  mov     esi, eax
0x18002f87e  test    eax, eax
0x18002f880  jnz     short loc_18002F8AE
0x18002f882  mov     rcx, [rbx]; hModule
0x18002f885  lea     rdx, ProcName; "StartRouter"
0x18002f88c  call    cs:__imp_GetProcAddress
0x18002f892  mov     r10, rax
0x18002f895  test    rax, rax
0x18002f898  jnz     loc_18002F928
0x18002f89e  call    cs:__imp_GetLastError
0x18002f8a4  mov     esi, eax
0x18002f8a6  test    eax, eax
0x18002f8a8  jz      loc_18002FA3F
0x18002f8ae  test    rdi, rdi
0x18002f8b1  jz      short loc_18002F8BB
0x18002f8b3  mov     rcx, rdi; this
0x18002f8b6  call    ??_G_ROUTER@CDimRouterManager@@QEAAPEAXI@Z; CDimRouterManager::_ROUTER::`scalar deleting destructor'(uint)
0x18002f8bb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18002f8c2  jz      short loc_18002F903
0x18002f8c4  xor     eax, eax
0x18002f8c6  lea     rdx, aCdimroutermana_0; "CDimRouterManager::StartRouter returned"...
0x18002f8cd  mov     r9d, r15d
0x18002f8d0  mov     word ptr [rsp+8A0h+var_850], ax
0x18002f8d5  mov     r8d, esi
0x18002f8d8  lea     rcx, [rsp+8A0h+var_850]
0x18002f8dd  call    FormatRRASErrorString
0x18002f8e2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18002f8e9  jz      short loc_18002F903
0x18002f8eb  lea     r8, [rsp+8A0h+var_850]
0x18002f8f0  lea     rdx, RasDimTraceInfo
0x18002f8f7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002f8fe  call    McTemplateU0z_EventWriteTransfer
0x18002f903  mov     eax, esi
0x18002f905  mov     rcx, [rbp+7A0h+var_50]
0x18002f90c  xor     rcx, rsp; StackCookie
0x18002f90f  call    __security_check_cookie
0x18002f914  add     rsp, 868h
0x18002f91b  pop     r15
0x18002f91d  pop     r14
0x18002f91f  pop     r13
0x18002f921  pop     r12
0x18002f923  pop     rdi
0x18002f924  pop     rsi
0x18002f925  pop     rbx
0x18002f926  pop     rbp
0x18002f927  retn
0x18002f928  mov     r9d, [rbp+7A0h+arg_30]
0x18002f92f  lea     rax, ?DIMConnectInterface@@YAKPEAXK@Z; DIMConnectInterface(void *,ulong)
0x18002f936  mov     [rdi+0C8h], rax
0x18002f93d  mov     rcx, rdi
0x18002f940  lea     rax, ?DIMDisconnectInterface@@YAKPEAXK@Z; DIMDisconnectInterface(void *,ulong)
0x18002f947  mov     [rsp+8A0h+var_880], r15d
0x18002f94c  mov     [rdi+0D0h], rax
0x18002f953  lea     rax, ?DIMSaveInterfaceInfo@@YAKPEAXK0K@Z; DIMSaveInterfaceInfo(void *,ulong,void *,ulong)
0x18002f95a  mov     [rdi+0D8h], rax
0x18002f961  lea     rax, ?DIMRestoreInterfaceInfo@@YAKPEAXK0PEAK@Z; DIMRestoreInterfaceInfo(void *,ulong,void *,ulong *)
0x18002f968  mov     [rdi+0E0h], rax
0x18002f96f  lea     rax, ?DIMSaveGlobalInfo@@YAKKPEAXK@Z; DIMSaveGlobalInfo(ulong,void *,ulong)
0x18002f976  mov     [rdi+0E8h], rax
0x18002f97d  lea     rax, ?DIMRouterStopped@@YAXKK@Z; DIMRouterStopped(ulong,ulong)
0x18002f984  mov     [rdi+0F0h], rax
0x18002f98b  lea     rax, ?DIMInterfaceEnabled@@YAXPEAXKH@Z; DIMInterfaceEnabled(void *,ulong,int)
0x18002f992  mov     [rdi+0F8h], rax
0x18002f999  lea     rax, ?DIMGetRouterPhoneBookInfo@@YAKPEBGPEAXPEAPEAUtagRASENTRYW@@@Z; DIMGetRouterPhoneBookInfo(ushort const *,void *,tagRASENTRYW * *)
0x18002f9a0  mov     [rdi+100h], rax
0x18002f9a7  lea     rax, ?DIMGetInterfaceHandle@@YAKPEAGKPEAPEAX@Z; DIMGetInterfaceHandle(ushort *,ulong,void * *)
0x18002f9ae  mov     [rdi+108h], rax
0x18002f9b5  lea     rax, ?DIMGetInterfaceDeviceGuid@@YAKPEAXPEAU_GUID@@@Z; DIMGetInterfaceDeviceGuid(void *,_GUID *)
0x18002f9bc  mov     [rdi+150h], rax
0x18002f9c3  lea     rax, ?DIMGetRoutingDomainIdForInterface@@YAKPEAXPEAU_GUID@@@Z; DIMGetRoutingDomainIdForInterface(void *,_GUID *)
0x18002f9ca  mov     [rdi+158h], rax
0x18002f9d1  lea     rax, ?DIMGetInfoForTenantInterface@@YAKPEAXPEAT_NET_LUID_LH@@PEAK@Z; DIMGetInfoForTenantInterface(void *,_NET_LUID_LH *,ulong *)
0x18002f9d8  mov     [rdi+160h], rax
0x18002f9df  xor     eax, eax
0x18002f9e1  cmp     byte ptr [r14+38h], 1
0x18002f9e6  setz    al
0x18002f9e9  xor     edx, edx
0x18002f9eb  mov     [rdi+110h], eax
0x18002f9f1  mov     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x18002f9f7  mov     r8, [r13+0]
0x18002f9fb  and     eax, 12h
0x18002f9fe  cmp     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x18002fa04  mov     rax, r10
0x18002fa07  setz    dl
0x18002fa0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa0f  mov     esi, eax
0x18002fa11  test    eax, eax
0x18002fa13  jnz     loc_18002F8AE
0x18002fa19  mov     ebx, [rbp+7A0h+arg_20]
0x18002fa1f  test    ebx, ebx
0x18002fa21  jz      short loc_18002FA38
0x18002fa23  lea     rcx, [rdi+178h]
0x18002fa2a  mov     rdx, r12
0x18002fa2d  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=(std::unique_ptr<uchar [0]> &&)
0x18002fa32  mov     [rdi+180h], ebx
0x18002fa38  mov     byte ptr [rdi+168h], 1
0x18002fa3f  lea     r12, [r14+8]
0x18002fa43  mov     rcx, r12; SRWLock
0x18002fa46  call    cs:__imp_AcquireSRWLockExclusive
0x18002fa4c  add     r14, 18h
0x18002fa50  lea     r8, [rsp+8A0h+var_870]
0x18002fa55  mov     rcx, r14
0x18002fa58  lea     rdx, [rsp+8A0h+var_868]
0x18002fa5d  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@KPEAU_ROUTER@CDimRouterManager@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@KPEAU_ROUTER@CDimRouterManager@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@std@@@4@$0A@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,CDimRouterManager::_ROUTER *,std::less<ulong>,std::allocator<std::pair<ulong const,CDimRouterManager::_ROUTER *>>,0>>::lower_bound(ulong const &)
0x18002fa62  mov     rbx, [rsp+8A0h+var_868]
0x18002fa67  cmp     rbx, [r14+8]
0x18002fa6b  jz      short loc_18002FA73
0x18002fa6d  cmp     r15d, [rbx+18h]
0x18002fa71  jnb     short loc_18002FAA6
0x18002fa73  lea     rdx, [rsp+8A0h+var_868]
0x18002fa78  mov     dword ptr [rsp+8A0h+var_868], r15d
0x18002fa7d  mov     rcx, r14
0x18002fa80  mov     [rsp+8A0h+var_860], 0
0x18002fa89  call    ??$_Buynode@U?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@std@@@?$_Tree_val@V?$_Tmap_traits@KPEAU_ROUTER@CDimRouterManager@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@std@@@4@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@KPEAU_ROUTER@CDimRouterManager@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@std@@@4@$0A@@std@@@1@$$QEAU?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@1@@Z; std::_Tree_val<std::_Tmap_traits<ulong,CDimRouterManager::_ROUTER *,std::less<ulong>,std::allocator<std::pair<ulong const,CDimRouterManager::_ROUTER *>>,0>>::_Buynode<std::pair<ulong const,CDimRouterManager::_ROUTER *>>(std::pair<ulong const,CDimRouterManager::_ROUTER *> &&)
0x18002fa8e  mov     r9, rax
0x18002fa91  lea     rdx, [rsp+8A0h+var_868]
0x18002fa96  mov     r8, rbx
0x18002fa99  mov     rcx, r14
0x18002fa9c  call    ?_Insert@?$_Tree@V?$_Tmap_traits@KPEAU_ROUTER@CDimRouterManager@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@KPEAU_ROUTER@CDimRouterManager@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@std@@@4@$0A@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tmap_traits@KPEAU_ROUTER@CDimRouterManager@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@std@@@4@$0A@@std@@@std@@@2@PEAU_Node@?$_Tree_nod@V?$_Tmap_traits@KPEAU_ROUTER@CDimRouterManager@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_ROUTER@CDimRouterManager@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,CDimRouterManager::_ROUTER *,std::less<ulong>,std::allocator<std::pair<ulong const,CDimRouterManager::_ROUTER *>>,0>>::_Insert(std::_Tree_const_iterator<std::_Tree_val<std::_Tmap_traits<ulong,CDimRouterManager::_ROUTER *,std::less<ulong>,std::allocator<std::pair<ulong const,CDimRouterManager::_ROUTER *>>,0>>>,std::_Tree_nod<std::_Tmap_traits<ulong,CDimRouterManager::_ROUTER *,std::less<ulong>,std::allocator<std::pair<ulong const,CDimRouterManager::_ROUTER *>>,0>>::_Node *)
0x18002faa1  mov     rbx, [rsp+8A0h+var_868]
0x18002faa6  mov     rcx, r12; SRWLock
0x18002faa9  mov     [rbx+20h], rdi
0x18002faad  call    cs:__imp_ReleaseSRWLockExclusive
0x18002fab3  jmp     loc_18002F8BB
```
