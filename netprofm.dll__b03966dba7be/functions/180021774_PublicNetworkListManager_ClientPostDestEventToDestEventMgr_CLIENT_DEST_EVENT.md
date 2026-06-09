# PublicNetworkListManager::ClientPostDestEventToDestEventMgr(CLIENT_DEST_EVENT *)

- ea: `0x180021774`
- end: `0x18002190d`
- name: `?ClientPostDestEventToDestEventMgr@PublicNetworkListManager@@QEAAJPEAUCLIENT_DEST_EVENT@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, struct CLIENT_DEST_EVENT *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020388`
- `0x1800219d0`
- `0x18002a294`
- `0x18002ea30`

## callees

- `0x180006770`
- `0x180006810`
- `0x180009184`
- `0x180009d08`
- `0x18001e6c8`
- `0x180021774`
- `0x180029e3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800218ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800218ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800217c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800217c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021838`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800217dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800217dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PublicNetworkListManager::ClientPostDestEventToDestEventMgr(
        PublicNetworkListManager *this,
        struct CLIENT_DEST_EVENT *a2)
{
  unsigned int v4; // ebx
  _OWORD *v5; // rax
  void *v6; // rsi
  __int128 v7; // xmm0
  __int64 v8; // r14
  void *v9; // rdx
  signed int LastError; // eax
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v13[10]; // [rsp+28h] [rbp-50h] BYREF

  v4 = -2147467259;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  if ( *((_QWORD *)this + 88) )
  {
    v5 = CoTaskMemAlloc(0x14u);
    v6 = v5;
    if ( v5 )
    {
      v7 = *(_OWORD *)a2;
      v12 = 0;
      *v5 = v7;
      *((_DWORD *)v5 + 4) = *((_DWORD *)a2 + 4);
      wil::EnterCriticalSection(&v12, (char *)this + 712);
      v8 = *((_QWORD *)this + 95);
      v13[0] = v6;
      v13[1] = this;
      v4 = wil::ResultFromException__PublicNetworkListManager::ClientPostDestEventToDestEventMgr_::_8_::_lambda_1___(v13);
      if ( (v4 & 0x80000000) == 0 )
      {
        if ( !v8 )
          wil::details::SetEvent(*((wil::details **)this + 96), v9);
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        CoTaskMemFree(v6);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v4);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v12);
    }
    else
    {
      v4 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180021774  push    rbx
0x180021776  push    rbp
0x180021777  push    rsi
0x180021778  push    rdi
0x180021779  push    r14
0x18002177b  push    r15
0x18002177d  sub     rsp, 48h
0x180021781  mov     r14, rdx
0x180021784  mov     rdi, rcx
0x180021787  mov     ebx, 80004005h
0x18002178c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021793  lea     r15, WPP_GLOBAL_Control
0x18002179a  cmp     rcx, r15
0x18002179d  jz      short loc_1800217BA
0x18002179f  test    byte ptr [rcx+1Ch], 8
0x1800217a3  jz      short loc_1800217BA
0x1800217a5  mov     rcx, [rcx+10h]
0x1800217a9  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800217b0  mov     edx, 0AEh
0x1800217b5  call    WPP_SF_
0x1800217ba  lea     rbp, [rdi+298h]
0x1800217c1  mov     rcx, rbp; lpCriticalSection
0x1800217c4  call    cs:__imp_EnterCriticalSection
0x1800217ca  cmp     qword ptr [rdi+2C0h], 0
0x1800217d2  jz      loc_1800218CB
0x1800217d8  mov     ecx, 14h; cb
0x1800217dd  call    cs:__imp_CoTaskMemAlloc
0x1800217e3  mov     rsi, rax
0x1800217e6  test    rax, rax
0x1800217e9  jz      loc_18002189F
0x1800217ef  movups  xmm0, xmmword ptr [r14]
0x1800217f3  lea     rdx, [rdi+2C8h]
0x1800217fa  mov     [rsp+78h+var_58], 0
0x180021803  lea     rcx, [rsp+78h+var_58]
0x180021808  movups  xmmword ptr [rax], xmm0
0x18002180b  mov     eax, [r14+10h]
0x18002180f  mov     [rsi+10h], eax
0x180021812  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180021817  mov     r14, [rdi+2F8h]
0x18002181e  lea     rcx, [rsp+78h+var_50]
0x180021823  mov     [rsp+78h+var_50], rsi
0x180021828  mov     [rsp+78h+var_48], rdi
0x18002182d  call    wil__ResultFromException__PublicNetworkListManager__ClientPostDestEventToDestEventMgr____8____lambda_1___
0x180021832  mov     ebx, eax
0x180021834  test    eax, eax
0x180021836  jns     short loc_180021882
0x180021838  call    cs:__imp_GetLastError
0x18002183e  mov     ebx, eax
0x180021840  test    eax, eax
0x180021842  jle     short loc_18002184D
0x180021844  movzx   ebx, ax
0x180021847  or      ebx, 80070000h
0x18002184d  mov     rcx, rsi; pv
0x180021850  call    cs:__imp_CoTaskMemFree
0x180021856  mov     rcx, cs:WPP_GLOBAL_Control
0x18002185d  cmp     rcx, r15
0x180021860  jz      short loc_180021893
0x180021862  test    byte ptr [rcx+1Ch], 1
0x180021866  jz      short loc_180021893
0x180021868  mov     rcx, [rcx+10h]
0x18002186c  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180021873  mov     edx, 0AFh
0x180021878  mov     r9d, ebx
0x18002187b  call    WPP_SF_d
0x180021880  jmp     short loc_180021893
0x180021882  test    r14, r14
0x180021885  jnz     short loc_180021893
0x180021887  mov     rcx, [rdi+300h]; this
0x18002188e  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180021893  lea     rcx, [rsp+78h+var_58]
0x180021898  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18002189d  jmp     short loc_1800218CB
0x18002189f  mov     ebx, 8007000Eh
0x1800218a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218ab  cmp     rcx, r15
0x1800218ae  jz      short loc_1800218CB
0x1800218b0  test    byte ptr [rcx+1Ch], 1
0x1800218b4  jz      short loc_1800218CB
0x1800218b6  mov     rcx, [rcx+10h]
0x1800218ba  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800218c1  mov     edx, 0B0h
0x1800218c6  call    WPP_SF_
0x1800218cb  mov     rcx, rbp; lpCriticalSection
0x1800218ce  call    cs:__imp_LeaveCriticalSection
0x1800218d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218db  cmp     rcx, r15
0x1800218de  jz      short loc_1800218FE
0x1800218e0  test    byte ptr [rcx+1Ch], 8
0x1800218e4  jz      short loc_1800218FE
0x1800218e6  mov     rcx, [rcx+10h]
0x1800218ea  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800218f1  mov     edx, 0B1h
0x1800218f6  mov     r9d, ebx
0x1800218f9  call    WPP_SF_d
0x1800218fe  mov     eax, ebx
0x180021900  add     rsp, 48h
0x180021904  pop     r15
0x180021906  pop     r14
0x180021908  pop     rdi
0x180021909  pop     rsi
0x18002190a  pop     rbp
0x18002190b  pop     rbx
0x18002190c  retn
```
