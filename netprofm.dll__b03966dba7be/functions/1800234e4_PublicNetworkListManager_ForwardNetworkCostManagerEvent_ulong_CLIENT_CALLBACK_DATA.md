# PublicNetworkListManager::ForwardNetworkCostManagerEvent(ulong,CLIENT_CALLBACK_DATA *)

- ea: `0x1800234e4`
- end: `0x18002369a`
- name: `?ForwardNetworkCostManagerEvent@PublicNetworkListManager@@AEAAJKPEAUCLIENT_CALLBACK_DATA@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, unsigned int, struct CLIENT_CALLBACK_DATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fe20`

## callees

- `0x180008160`
- `0x18000b77c`
- `0x1800120d0`
- `0x18001ef34`
- `0x180023090`
- `0x1800234e4`
- `0x1800295c8`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023570`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023570`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PublicNetworkListManager::ForwardNetworkCostManagerEvent(
        PublicNetworkListManager *this,
        unsigned int a2,
        const struct _GUID *a3)
{
  int GITEntry; // esi
  __int64 v7; // r8
  struct NLM_SOCKADDR *v8; // rbx
  struct NLM_SOCKADDR *v9; // rax
  int v10; // eax
  __int64 v12; // [rsp+48h] [rbp-40h] BYREF

  v12 = 0;
  GITEntry = PublicNetworkListManager::RetrieveGITEntry(
               (int)this + 544,
               (int)this + 504,
               a2,
               (int)this + 224,
               (__int64)&GUID_dcb00009_570f_4a9b_8d69_199fdba5723b,
               (__int64)&v12);
  if ( GITEntry >= 0 )
  {
    v8 = 0;
    if ( *(_QWORD *)&GUID_NULL.Data1 != *(_QWORD *)&a3->Data1 || *(_QWORD *)GUID_NULL.Data4 != *(_QWORD *)a3->Data4 )
    {
      v9 = (struct NLM_SOCKADDR *)CoTaskMemAlloc(0x80u);
      v8 = v9;
      if ( !v9 )
      {
        GITEntry = -2147024882;
        goto LABEL_16;
      }
      GITEntry = PublicNetworkListManager::FindAddressInListFromGUIDLockHeld(this, a3, v9);
      if ( GITEntry < 0 )
        goto LABEL_16;
    }
    if ( a3[1].Data1 == 2049 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct NLM_SOCKADDR *))(*(_QWORD *)v12 + 24LL))(
              v12,
              *(unsigned int *)&a3[1].Data2,
              v8);
    }
    else
    {
      if ( a3[1].Data1 != 2050 )
      {
        GITEntry = -2147024809;
LABEL_12:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dLLL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            122,
            v7,
            (unsigned int)GITEntry,
            a2,
            a3[1].Data1,
            *(_DWORD *)&a3[1].Data2);
        goto LABEL_16;
      }
      v10 = (*(__int64 (__fastcall **)(__int64, struct NLM_SOCKADDR *))(*(_QWORD *)v12 + 32LL))(v12, v8);
    }
    GITEntry = v10;
    if ( v10 < 0 )
      goto LABEL_12;
LABEL_16:
    if ( v8 )
      CoTaskMemFree(v8);
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, v7, a2, a3[1].Data1, *(_DWORD *)&a3[1].Data2);
LABEL_21:
  wil::com_ptr_t<INetworkEvents,wil::err_exception_policy>::~com_ptr_t<INetworkEvents,wil::err_exception_policy>(&v12);
  return (unsigned int)GITEntry;
}

```

## disassembly

```asm
0x1800234e4  mov     r11, rsp
0x1800234e7  push    rbx
0x1800234e8  push    rbp
0x1800234e9  push    rsi
0x1800234ea  push    rdi
0x1800234eb  push    r14
0x1800234ed  sub     rsp, 60h
0x1800234f1  mov     rax, cs:__security_cookie
0x1800234f8  xor     rax, rsp
0x1800234fb  mov     [rsp+88h+var_38], rax
0x180023500  mov     rdi, r8
0x180023503  mov     r14d, edx
0x180023506  mov     rbp, rcx
0x180023509  mov     qword ptr [r11-40h], 0
0x180023511  lea     r9, [rcx+0E0h]
0x180023518  lea     rdx, [rcx+1F8h]
0x18002351f  add     rcx, 220h
0x180023526  lea     rax, [r11-40h]
0x18002352a  mov     [r11-60h], rax
0x18002352e  lea     rax, _GUID_dcb00009_570f_4a9b_8d69_199fdba5723b
0x180023535  mov     [r11-68h], rax
0x180023539  mov     r8d, r14d
0x18002353c  call    ?RetrieveGITEntry@PublicNetworkListManager@@CAJPEBV?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@PEAU_RTL_CRITICAL_SECTION@@KAEBV?$CComPtr@UIGlobalInterfaceTable@@@ATL@@AEBU_GUID@@PEAPEAX@Z; PublicNetworkListManager::RetrieveGITEntry(std::map<ulong,CLIENT_CALLBACK_INTERFACE> const *,_RTL_CRITICAL_SECTION *,ulong,ATL::CComPtr<IGlobalInterfaceTable> const &,_GUID const &,void * *)
0x180023541  mov     esi, eax
0x180023543  test    eax, eax
0x180023545  js      loc_18002363D
0x18002354b  xor     ebx, ebx
0x18002354d  mov     [rsp+88h+var_48], rbx
0x180023552  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180023559  cmp     rax, [rdi]
0x18002355c  jnz     short loc_18002356B
0x18002355e  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180023565  cmp     rax, [rdi+8]
0x180023569  jz      short loc_18002359F
0x18002356b  mov     ecx, 80h; cb
0x180023570  call    cs:__imp_CoTaskMemAlloc
0x180023576  mov     rbx, rax
0x180023579  mov     [rsp+88h+var_48], rax
0x18002357e  test    rax, rax
0x180023581  jz      loc_180023628
0x180023587  mov     r8, rax; struct NLM_SOCKADDR *
0x18002358a  mov     rdx, rdi; struct _GUID *
0x18002358d  mov     rcx, rbp; this
0x180023590  call    ?FindAddressInListFromGUIDLockHeld@PublicNetworkListManager@@AEAAJAEBU_GUID@@PEAUNLM_SOCKADDR@@@Z; PublicNetworkListManager::FindAddressInListFromGUIDLockHeld(_GUID const &,NLM_SOCKADDR *)
0x180023595  mov     esi, eax
0x180023597  test    eax, eax
0x180023599  js      loc_18002362D
0x18002359f  mov     ecx, [rdi+10h]
0x1800235a2  sub     ecx, 801h
0x1800235a8  jz      short loc_1800235CC
0x1800235aa  cmp     ecx, 1
0x1800235ad  jz      short loc_1800235B6
0x1800235af  mov     esi, 80070057h
0x1800235b4  jmp     short loc_1800235E9
0x1800235b6  mov     rcx, [rsp+88h+var_40]
0x1800235bb  mov     rax, [rcx]
0x1800235be  mov     rdx, rbx
0x1800235c1  mov     rax, [rax+20h]
0x1800235c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235ca  jmp     short loc_1800235E3
0x1800235cc  mov     rcx, [rsp+88h+var_40]
0x1800235d1  mov     rax, [rcx]
0x1800235d4  mov     r8, rbx
0x1800235d7  mov     edx, [rdi+14h]
0x1800235da  mov     rax, [rax+18h]
0x1800235de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235e3  mov     esi, eax
0x1800235e5  test    eax, eax
0x1800235e7  jns     short loc_18002362D
0x1800235e9  lea     rax, WPP_GLOBAL_Control
0x1800235f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235f7  cmp     rcx, rax
0x1800235fa  jz      short loc_18002362D
0x1800235fc  test    byte ptr [rcx+1Ch], 1
0x180023600  jz      short loc_18002362D
0x180023602  mov     edx, 7Ah ; 'z'
0x180023607  mov     eax, [rdi+14h]
0x18002360a  mov     [rsp+88h+var_58], eax
0x18002360e  mov     eax, [rdi+10h]
0x180023611  mov     [rsp+88h+var_60], eax
0x180023615  mov     [rsp+88h+var_68], r14d
0x18002361a  mov     r9d, esi
0x18002361d  mov     rcx, [rcx+10h]
0x180023621  call    WPP_SF_dLLL
0x180023626  jmp     short loc_18002362D
0x180023628  mov     esi, 8007000Eh
0x18002362d  test    rbx, rbx
0x180023630  jz      short loc_180023676
0x180023632  mov     rcx, rbx; pv
0x180023635  call    cs:__imp_CoTaskMemFree
0x18002363b  jmp     short loc_180023676
0x18002363d  lea     rax, WPP_GLOBAL_Control
0x180023644  mov     rcx, cs:WPP_GLOBAL_Control
0x18002364b  cmp     rcx, rax
0x18002364e  jz      short loc_180023676
0x180023650  test    byte ptr [rcx+1Ch], 1
0x180023654  jz      short loc_180023676
0x180023656  mov     edx, 7Bh ; '{'
0x18002365b  mov     eax, [rdi+14h]
0x18002365e  mov     [rsp+88h+var_60], eax
0x180023662  mov     eax, [rdi+10h]
0x180023665  mov     [rsp+88h+var_68], eax
0x180023669  mov     r9d, r14d
0x18002366c  mov     rcx, [rcx+10h]
0x180023670  call    WPP_SF_LLL
0x180023675  nop
0x180023676  lea     rcx, [rsp+88h+var_40]
0x18002367b  call    ??1?$com_ptr_t@UINetworkEvents@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkEvents,wil::err_exception_policy>::~com_ptr_t<INetworkEvents,wil::err_exception_policy>(void)
0x180023680  mov     eax, esi
0x180023682  mov     rcx, [rsp+88h+var_38]
0x180023687  xor     rcx, rsp; StackCookie
0x18002368a  call    __security_check_cookie
0x18002368f  add     rsp, 60h
0x180023693  pop     r14
0x180023695  pop     rdi
0x180023696  pop     rsi
0x180023697  pop     rbp
0x180023698  pop     rbx
0x180023699  retn
```
