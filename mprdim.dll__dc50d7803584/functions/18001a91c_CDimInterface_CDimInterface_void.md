# CDimInterface::~CDimInterface(void)

- ea: `0x18001a91c`
- end: `0x18001abb1`
- name: `??1CDimInterface@@UEAA@XZ`
- size: `661`
- prototype: `void __fastcall(CDimInterface *__hidden this)`
- caller_count: `9`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a84c`
- `0x18001ad60`
- `0x18001ada0`
- `0x18001ade0`
- `0x18001ae60`
- `0x18001aea0`
- `0x18001aee0`
- `0x18001af20`
- `0x18001afa0`

## callees

- `0x180009cb8`
- `0x18000df70`
- `0x18001a78c`
- `0x18001a7c0`
- `0x18001a7e4`
- `0x18001a91c`
- `0x18001b750`
- `0x1800219f4`
- `0x18002dd98`
- `0x180032c24`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ab17`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ab17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aabd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aaf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aabd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aaf3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ab52`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ab52`

## string_xrefs

- `0x18001a9f7`: `CDimInterface::~CDimInterface(): DeleteInterface from router manager failed : %d`

## pseudocode

```c
void __fastcall CDimInterface::~CDimInterface(CDimInterface *this)
{
  __int64 v2; // rdx
  CDimRouterManager *v3; // rcx
  int v4; // r15d
  __int64 *v5; // rdi
  __int64 v6; // rbx
  char *v7; // r8
  unsigned int v8; // eax
  _QWORD *v9; // rax
  __int128 *v10; // r9
  __int64 i; // rax
  void *v12; // r8
  void *v13; // r8
  void *v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  GUID ActivityId; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+54h] [rbp-ACh]
  __int128 v22; // [rsp+64h] [rbp-9Ch]
  int v23; // [rsp+74h] [rbp-8Ch]
  int v24; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  *(_QWORD *)this = &CDimInterface::`vftable';
  ActivityId = 0;
  v19 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v4 = SetActivityId((LPGUID)this + 194);
  v5 = (__int64 *)*((_QWORD *)this + 34);
  v6 = *v5;
  while ( (__int64 *)v6 != v5 )
  {
    v7 = *(char **)(v6 + 32);
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v8 = CDimRouterManager::DeleteInterface(v3, *(_DWORD *)(v6 + 24), v7);
      v7 = (char *)v8;
      if ( v8 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          LOWORD(v24) = 0;
          LOWORD(v20) = 0;
          FormatRRASErrorString(
            &v24,
            L"CDimInterface::~CDimInterface(): DeleteInterface from router manager failed : %d",
            v8);
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            v9 = (_QWORD *)((char *)this + 8);
            if ( *((_QWORD *)this + 4) >= 8u )
              v9 = (_QWORD *)*v9;
            v10 = &v19;
            if ( this != (CDimInterface *)-3104LL )
              LODWORD(v10) = (_DWORD)this + 3104;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceError,
              (unsigned int)&v24,
              (_DWORD)v10,
              (__int64)v9,
              (__int64)&v20);
          }
        }
      }
    }
    if ( !*(_BYTE *)(v6 + 49) )
    {
      v3 = *(CDimRouterManager **)(v6 + 16);
      if ( *((_BYTE *)v3 + 49) )
      {
        for ( i = *(_QWORD *)(v6 + 8); !*(_BYTE *)(i + 49) && v6 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v6 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(
              v3,
              v2,
              v7);
      }
      v6 = i;
    }
  }
  FreeCertificateBlob((char *)this + 872, 0);
  FreeCertificateBlob((char *)this + 896, 0);
  v12 = (void *)*((_QWORD *)this + 111);
  if ( v12 )
    HeapFree(hHeap, 0, v12);
  v13 = (void *)*((_QWORD *)this + 116);
  if ( v13 )
    HeapFree(hHeap, 0, v13);
  v14 = (void *)*((_QWORD *)this + 117);
  if ( v14 )
    HeapFree(hHeap, 0, v14);
  CDimInterface::CloseNotifyCallerEvent(this);
  if ( v4 )
    ReSetActivityId(&ActivityId);
  operator delete[](*((void **)this + 398));
  std::_Tree<std::_Tset_traits<std::wstring,CDimInterface::_HOST_NAME_COMP,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,CDimInterface::_HOST_NAME_COMP,std::allocator<std::wstring>,0>>((__int64)this + 3152);
  std::_Tree<std::_Tset_traits<_ROUTER_IP_ADDRESS,CDimInterface::_ROUTER_IP_ADDRESS_COMP,std::allocator<_ROUTER_IP_ADDRESS>,0>>::~_Tree<std::_Tset_traits<_ROUTER_IP_ADDRESS,CDimInterface::_ROUTER_IP_ADDRESS_COMP,std::allocator<_ROUTER_IP_ADDRESS>,0>>((__int64)this + 3120);
  std::_Tree<std::_Tmap_traits<unsigned long,CDimInterface::_INTERFACE_TRANSPORT_INFO,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CDimInterface::_INTERFACE_TRANSPORT_INFO>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,CDimInterface::_INTERFACE_TRANSPORT_INFO,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CDimInterface::_INTERFACE_TRANSPORT_INFO>>,0>>((char *)this + 264);
  *((_QWORD *)this + 27) = &critical_section::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  LOBYTE(v15) = 1;
  std::wstring::_Tidy((char *)this + 176, v15, 0);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy((char *)this + 48, v16, 0);
  LOBYTE(v17) = 1;
  std::wstring::_Tidy((char *)this + 8, v17, 0);
}

```

## disassembly

```asm
0x18001a91c  mov     [rsp-8+arg_8], rbx
0x18001a921  mov     [rsp-8+arg_10], rsi
0x18001a926  push    rbp
0x18001a927  push    rdi
0x18001a928  push    r13
0x18001a92a  push    r14
0x18001a92c  push    r15
0x18001a92e  lea     rbp, [rsp-790h]
0x18001a936  sub     rsp, 890h
0x18001a93d  mov     rax, cs:__security_cookie
0x18001a944  xor     rax, rsp
0x18001a947  mov     [rbp+7B0h+var_30], rax
0x18001a94e  mov     rsi, rcx
0x18001a951  lea     rax, ??_7CDimInterface@@6B@; const CDimInterface::`vftable'
0x18001a958  mov     [rcx], rax
0x18001a95b  xorps   xmm0, xmm0
0x18001a95e  movups  xmmword ptr [rsp+8B0h+ActivityId.Data1], xmm0
0x18001a963  xorps   xmm1, xmm1
0x18001a966  movups  [rsp+8B0h+var_870], xmm1
0x18001a96b  xor     eax, eax
0x18001a96d  mov     [rbp+7B0h+var_830], eax
0x18001a970  xor     edx, edx; Val
0x18001a972  mov     r8d, 7FCh; Size
0x18001a978  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18001a97c  call    memset_0
0x18001a981  xor     eax, eax
0x18001a983  mov     [rsp+8B0h+var_860], eax
0x18001a987  xorps   xmm0, xmm0
0x18001a98a  movups  [rsp+8B0h+var_85C], xmm0
0x18001a98f  movups  [rsp+8B0h+var_84C], xmm0
0x18001a994  mov     [rsp+8B0h+var_83C], eax
0x18001a998  lea     r14, [rsi+0C20h]
0x18001a99f  lea     rdx, [rsp+8B0h+ActivityId]
0x18001a9a4  mov     rcx, r14; ActivityId
0x18001a9a7  call    SetActivityId
0x18001a9ac  mov     r15d, eax
0x18001a9af  lea     r13, [rsi+108h]
0x18001a9b6  mov     rdi, [r13+8]
0x18001a9ba  mov     rbx, [rdi]
0x18001a9bd  cmp     rbx, rdi
0x18001a9c0  jz      loc_18001AA8C
0x18001a9c6  mov     r8, [rbx+20h]; void *
0x18001a9ca  lea     rax, [r8-1]
0x18001a9ce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a9d2  ja      short loc_18001AA50
0x18001a9d4  mov     edx, [rbx+18h]; unsigned int
0x18001a9d7  call    ?DeleteInterface@CDimRouterManager@@QEAAKKPEAX@Z; CDimRouterManager::DeleteInterface(ulong,void *)
0x18001a9dc  mov     r8d, eax
0x18001a9df  test    eax, eax
0x18001a9e1  jz      short loc_18001AA50
0x18001a9e3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001a9ea  jz      short loc_18001AA50
0x18001a9ec  xor     eax, eax
0x18001a9ee  mov     word ptr [rbp+7B0h+var_830], ax
0x18001a9f2  mov     word ptr [rsp+8B0h+var_860], ax
0x18001a9f7  lea     rdx, aCdiminterfaceC; "CDimInterface::~CDimInterface(): Delete"...
0x18001a9fe  lea     rcx, [rbp+7B0h+var_830]
0x18001aa02  call    FormatRRASErrorString
0x18001aa07  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001aa0e  jz      short loc_18001AA50
0x18001aa10  lea     rax, [rsi+8]
0x18001aa14  cmp     qword ptr [rax+18h], 8
0x18001aa19  jb      short loc_18001AA1E
0x18001aa1b  mov     rax, [rax]
0x18001aa1e  lea     r9, [rsp+8B0h+var_870]
0x18001aa23  test    r14, r14
0x18001aa26  cmovnz  r9, r14
0x18001aa2a  lea     rcx, [rsp+8B0h+var_860]
0x18001aa2f  mov     [rsp+8B0h+var_888], rcx
0x18001aa34  mov     [rsp+8B0h+var_890], rax
0x18001aa39  lea     r8, [rbp+7B0h+var_830]
0x18001aa3d  lea     rdx, RasDimParamTraceError
0x18001aa44  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001aa4b  call    McTemplateU0zjzz_EventWriteTransfer
0x18001aa50  cmp     byte ptr [rbx+31h], 0
0x18001aa54  jnz     loc_18001A9BD
0x18001aa5a  mov     rcx, [rbx+10h]
0x18001aa5e  cmp     byte ptr [rcx+31h], 0
0x18001aa62  jnz     short loc_18001AA6B
0x18001aa64  call    ?_Min@?$_Tree_val@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Node *)
0x18001aa69  jmp     short loc_18001AA84
0x18001aa6b  mov     rax, [rbx+8]
0x18001aa6f  jmp     short loc_18001AA7E
0x18001aa71  cmp     rbx, [rax+10h]
0x18001aa75  jnz     short loc_18001AA84
0x18001aa77  mov     rbx, rax
0x18001aa7a  mov     rax, [rax+8]
0x18001aa7e  cmp     byte ptr [rax+31h], 0
0x18001aa82  jz      short loc_18001AA71
0x18001aa84  mov     rbx, rax
0x18001aa87  jmp     loc_18001A9BD
0x18001aa8c  lea     rcx, [rsi+368h]
0x18001aa93  xor     edx, edx
0x18001aa95  call    FreeCertificateBlob
0x18001aa9a  lea     rcx, [rsi+380h]
0x18001aaa1  xor     edx, edx
0x18001aaa3  call    FreeCertificateBlob
0x18001aaa8  mov     r8, [rsi+378h]; lpMem
0x18001aaaf  test    r8, r8
0x18001aab2  jz      short loc_18001AAC3
0x18001aab4  xor     edx, edx; dwFlags
0x18001aab6  mov     rcx, cs:hHeap; hHeap
0x18001aabd  call    cs:__imp_HeapFree
0x18001aac3  mov     r8, [rsi+3A0h]; lpMem
0x18001aaca  test    r8, r8
0x18001aacd  jz      short loc_18001AADE
0x18001aacf  xor     edx, edx; dwFlags
0x18001aad1  mov     rcx, cs:hHeap; hHeap
0x18001aad8  call    cs:__imp_HeapFree
0x18001aade  mov     r8, [rsi+3A8h]; lpMem
0x18001aae5  test    r8, r8
0x18001aae8  jz      short loc_18001AAF9
0x18001aaea  xor     edx, edx; dwFlags
0x18001aaec  mov     rcx, cs:hHeap; hHeap
0x18001aaf3  call    cs:__imp_HeapFree
0x18001aaf9  mov     rcx, rsi; this
0x18001aafc  call    ?CloseNotifyCallerEvent@CDimInterface@@UEAAXXZ; CDimInterface::CloseNotifyCallerEvent(void)
0x18001ab01  test    r15d, r15d
0x18001ab04  jz      short loc_18001AB10
0x18001ab06  lea     rcx, [rsp+8B0h+ActivityId]; ActivityId
0x18001ab0b  call    ReSetActivityId
0x18001ab10  mov     rcx, [rsi+0C70h]
0x18001ab17  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001ab1d  lea     rcx, [rsi+0C50h]
0x18001ab24  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_HOST_NAME_COMP@CDimInterface@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,CDimInterface::_HOST_NAME_COMP,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,CDimInterface::_HOST_NAME_COMP,std::allocator<std::wstring>,0>>(void)
0x18001ab29  lea     rcx, [rsi+0C30h]
0x18001ab30  call    ??1?$_Tree@V?$_Tset_traits@U_ROUTER_IP_ADDRESS@@U_ROUTER_IP_ADDRESS_COMP@CDimInterface@@V?$allocator@U_ROUTER_IP_ADDRESS@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_ROUTER_IP_ADDRESS,CDimInterface::_ROUTER_IP_ADDRESS_COMP,std::allocator<_ROUTER_IP_ADDRESS>,0>>::~_Tree<std::_Tset_traits<_ROUTER_IP_ADDRESS,CDimInterface::_ROUTER_IP_ADDRESS_COMP,std::allocator<_ROUTER_IP_ADDRESS>,0>>(void)
0x18001ab35  mov     rcx, r13
0x18001ab38  call    ??1?$_Tree@V?$_Tmap_traits@KU_INTERFACE_TRANSPORT_INFO@CDimInterface@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKU_INTERFACE_TRANSPORT_INFO@CDimInterface@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,CDimInterface::_INTERFACE_TRANSPORT_INFO,std::less<ulong>,std::allocator<std::pair<ulong const,CDimInterface::_INTERFACE_TRANSPORT_INFO>>,0>>::~_Tree<std::_Tmap_traits<ulong,CDimInterface::_INTERFACE_TRANSPORT_INFO,std::less<ulong>,std::allocator<std::pair<ulong const,CDimInterface::_INTERFACE_TRANSPORT_INFO>>,0>>(void)
0x18001ab3d  lea     rax, ??_7critical_section@@6B@; const critical_section::`vftable'
0x18001ab44  mov     [rsi+0D8h], rax
0x18001ab4b  lea     rcx, [rsi+0E0h]; lpCriticalSection
0x18001ab52  call    cs:__imp_DeleteCriticalSection
0x18001ab58  lea     rcx, [rsi+0B0h]
0x18001ab5f  xor     r8d, r8d
0x18001ab62  mov     dl, 1
0x18001ab64  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab69  lea     rcx, [rsi+30h]
0x18001ab6d  xor     r8d, r8d
0x18001ab70  mov     dl, 1
0x18001ab72  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab77  lea     rcx, [rsi+8]
0x18001ab7b  xor     r8d, r8d
0x18001ab7e  mov     dl, 1
0x18001ab80  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab85  nop
0x18001ab86  mov     rcx, [rbp+7B0h+var_30]
0x18001ab8d  xor     rcx, rsp; StackCookie
0x18001ab90  call    __security_check_cookie
0x18001ab95  lea     r11, [rsp+8B0h+var_20]
0x18001ab9d  mov     rbx, [r11+38h]
0x18001aba1  mov     rsi, [r11+40h]
0x18001aba5  mov     rsp, r11
0x18001aba8  pop     r15
0x18001abaa  pop     r14
0x18001abac  pop     r13
0x18001abae  pop     rdi
0x18001abaf  pop     rbp
0x18001abb0  retn
```
