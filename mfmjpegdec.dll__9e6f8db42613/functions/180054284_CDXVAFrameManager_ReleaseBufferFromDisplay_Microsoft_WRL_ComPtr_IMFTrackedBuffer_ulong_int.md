# CDXVAFrameManager::ReleaseBufferFromDisplay(Microsoft::WRL::ComPtr<IMFTrackedBuffer> &,ulong &,int &)

- ea: `0x180054284`
- end: `0x180054504`
- name: `?ReleaseBufferFromDisplay@CDXVAFrameManager@@IEAAJAEAV?$ComPtr@UIMFTrackedBuffer@@@WRL@Microsoft@@AEAKAEAH@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053ee0`

## callees

- `0x180043280`
- `0x180044d78`
- `0x18004a11c`
- `0x1800528c0`
- `0x180054284`
- `0x180054a4c`
- `0x180054b20`
- `0x180054b90`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005449b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005449b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800542b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800543ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800542b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800543ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800543e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800543e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDXVAFrameManager::ReleaseBufferFromDisplay(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  _QWORD *v5; // r12
  unsigned int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // r15d
  __int64 v8; // rbx
  unsigned int v9; // esi
  unsigned int v10; // ebp
  unsigned int v11; // eax
  unsigned int i; // ebp
  __int64 v13; // r14
  unsigned __int64 v14; // rbx
  __int64 v15; // r12
  __int64 v16; // rcx
  __int64 v17; // rbx
  unsigned int v19; // [rsp+40h] [rbp-68h]
  int v20; // [rsp+44h] [rbp-64h]
  __int64 v21; // [rsp+48h] [rbp-60h] BYREF
  _QWORD v22[11]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v23; // [rsp+B0h] [rbp+8h]

  v5 = a2;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = 0;
  v8 = a1 + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v21 = v8;
  v9 = *(_DWORD *)(a1 + 908);
  v20 = *(_DWORD *)(a1 + 904);
  *a3 = 0xFFFF;
  v10 = 0;
LABEL_2:
  v23 = v10;
  if ( v10 >= *(_DWORD *)(a1 + 912) )
    goto LABEL_24;
  v11 = *(_DWORD *)(a1 + 4LL * v9 + 136);
  v19 = v11;
  for ( i = 0; ; ++i )
  {
    if ( i >= v11 )
      goto LABEL_20;
    v13 = *(_QWORD *)(a1 + 8LL * v9 + 264);
    if ( v13 )
    {
      v14 = (unsigned __int64)i << 6;
      if ( *(_QWORD *)(v14 + v13) == *v5 )
      {
        if ( g_wppLevels >= 4u )
          WPP_SF_qddq(*((_QWORD *)WPP_GLOBAL_Control + 2));
        if ( *(_QWORD *)(v14 + v13 + 40) )
        {
          v15 = v14 + v13;
          if ( !*(_QWORD *)(v14 + v13 + 48)
            && (event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v15 + 48, 0)) != 0
            || (event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v14 + v13 + 40) + 24LL))(*(_QWORD *)(v14 + v13 + 40), *(_QWORD *)(v15 + 48))) != 0 )
          {
            v5 = a2;
LABEL_20:
            v9 = ((_BYTE)v9 + 1) & 0x1F;
            v10 = v23 + 1;
            goto LABEL_2;
          }
          if ( g_wppLevels >= 4u )
            WPP_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              &WPP_2ae34273ea0c3e44748ef5ee268f3ee0_Traceguids,
              *(_QWORD *)(v15 + 48),
              a1);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
            &v21,
            0);
          WaitForSingleObject(*(HANDLE *)(v15 + 48), 0xFFFFFFFF);
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
            &v21,
            a1 + 24);
          v22[0] = 0;
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v22);
          v5 = a2;
        }
      }
    }
    v16 = *(_QWORD *)(a1 + 8LL * v9 + 264);
    if ( v16 )
    {
      v17 = v16 + ((unsigned __int64)i << 6);
      if ( *(_QWORD *)v17 == *v5 )
        break;
    }
    v11 = v19;
  }
  *a3 = i;
  *(_WORD *)(v17 + 8) = -1;
  *a4 = v9;
  if ( *(_BYTE *)(v17 + 16) && v9 == (((_BYTE)v20 - 1) & 0x1F) )
  {
    *(_BYTE *)(v17 + 16) = 0;
    *(_BYTE *)(v17 + 56) = 0;
    SetEvent(*(HANDLE *)(a1 + 120));
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = 0;
LABEL_24:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
    return event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  if ( g_wppLevels >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_2ae34273ea0c3e44748ef5ee268f3ee0_Traceguids, a1);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)v17);
  *(_BYTE *)(v17 + 16) = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
  return 0;
}

```

## disassembly

```asm
0x180054284  mov     [rsp+arg_18], r9
0x180054289  mov     [rsp+arg_10], r8
0x18005428e  mov     [rsp+arg_8], rdx
0x180054293  push    rbx
0x180054294  push    rbp
0x180054295  push    rsi
0x180054296  push    rdi
0x180054297  push    r12
0x180054299  push    r13
0x18005429b  push    r14
0x18005429d  push    r15
0x18005429f  sub     rsp, 68h
0x1800542a3  mov     r14, r8
0x1800542a6  mov     r12, rdx
0x1800542a9  mov     rdi, rcx
0x1800542ac  xor     r15d, r15d
0x1800542af  lea     rbx, [rcx+18h]
0x1800542b3  mov     rcx, rbx; lpCriticalSection
0x1800542b6  call    cs:__imp_EnterCriticalSection
0x1800542bc  mov     [rsp+0A8h+var_60], rbx
0x1800542c1  mov     esi, [rdi+38Ch]
0x1800542c7  mov     eax, [rdi+388h]
0x1800542cd  mov     [rsp+0A8h+var_64], eax
0x1800542d1  mov     dword ptr [r14], 0FFFFh
0x1800542d8  xor     ebp, ebp
0x1800542da  mov     [rsp+0A8h+arg_0], ebp
0x1800542e1  cmp     ebp, [rdi+390h]
0x1800542e7  jnb     loc_1800544A4
0x1800542ed  mov     r13d, esi
0x1800542f0  mov     eax, [rdi+r13*4+88h]
0x1800542f8  mov     [rsp+0A8h+var_68], eax
0x1800542fc  xor     ebp, ebp
0x1800542fe  cmp     ebp, eax
0x180054300  jnb     loc_18005444F
0x180054306  mov     r14, [rdi+r13*8+108h]
0x18005430e  test    r14, r14
0x180054311  jz      loc_18005441D
0x180054317  mov     r9, [r12]
0x18005431b  mov     ebx, ebp
0x18005431d  shl     rbx, 6
0x180054321  cmp     [rbx+r14], r9
0x180054325  jnz     loc_18005441D
0x18005432b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180054332  jb      short loc_180054351
0x180054334  mov     [rsp+0A8h+var_78], rdi
0x180054339  mov     [rsp+0A8h+var_80], ebp
0x18005433d  mov     dword ptr [rsp+0A8h+var_88], esi
0x180054341  mov     rcx, cs:WPP_GLOBAL_Control
0x180054348  mov     rcx, [rcx+10h]
0x18005434c  call    WPP_SF_qddq
0x180054351  cmp     qword ptr [rbx+r14+28h], 0
0x180054357  jz      loc_18005441D
0x18005435d  lea     r12, [rbx+r14]
0x180054361  cmp     qword ptr [r12+30h], 0
0x180054367  jnz     short loc_180054380
0x180054369  xor     edx, edx
0x18005436b  lea     rcx, [r12+30h]
0x180054370  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180054375  mov     r15d, eax
0x180054378  test    eax, eax
0x18005437a  jnz     loc_180054447
0x180054380  mov     rcx, [rbx+r14+28h]
0x180054385  mov     rax, [rcx]
0x180054388  mov     rdx, [r12+30h]
0x18005438d  mov     rax, [rax+18h]
0x180054391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054396  mov     r15d, eax
0x180054399  test    eax, eax
0x18005439b  jnz     loc_180054447
0x1800543a1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x1800543a8  jb      short loc_1800543CE
0x1800543aa  lea     edx, [rax+21h]
0x1800543ad  mov     [rsp+0A8h+var_88], rdi
0x1800543b2  mov     r9, [r12+30h]
0x1800543b7  lea     r8, WPP_2ae34273ea0c3e44748ef5ee268f3ee0_Traceguids
0x1800543be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800543c5  mov     rcx, [rcx+10h]
0x1800543c9  call    WPP_SF_qq
0x1800543ce  xor     edx, edx
0x1800543d0  lea     rcx, [rsp+0A8h+var_60]
0x1800543d5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x1800543da  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800543dd  mov     rcx, [r12+30h]; hHandle
0x1800543e2  call    cs:__imp_WaitForSingleObject
0x1800543e8  nop
0x1800543e9  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800543ed  call    cs:__imp_EnterCriticalSection
0x1800543f3  nop
0x1800543f4  lea     rdx, [rdi+18h]
0x1800543f8  lea     rcx, [rsp+0A8h+var_60]
0x1800543fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x180054402  mov     [rsp+0A8h+var_58], 0
0x18005440b  lea     rcx, [rsp+0A8h+var_58]
0x180054410  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180054415  mov     r12, [rsp+0A8h+arg_8]
0x18005441d  mov     rcx, [rdi+r13*8+108h]
0x180054425  test    rcx, rcx
0x180054428  jz      short loc_18005443C
0x18005442a  mov     ebx, ebp
0x18005442c  shl     rbx, 6
0x180054430  add     rbx, rcx
0x180054433  mov     rax, [r12]
0x180054437  cmp     [rbx], rax
0x18005443a  jz      short loc_180054462
0x18005443c  inc     ebp
0x18005443e  mov     eax, [rsp+0A8h+var_68]
0x180054442  jmp     loc_1800542FE
0x180054447  mov     r12, [rsp+0A8h+arg_8]
0x18005444f  inc     esi
0x180054451  and     esi, 1Fh
0x180054454  mov     ebp, [rsp+0A8h+arg_0]
0x18005445b  inc     ebp
0x18005445d  jmp     loc_1800542DA
0x180054462  mov     rax, [rsp+0A8h+arg_10]
0x18005446a  mov     [rax], ebp
0x18005446c  mov     word ptr [rbx+8], 0FFFFh
0x180054472  mov     rax, [rsp+0A8h+arg_18]
0x18005447a  mov     [rax], esi
0x18005447c  cmp     byte ptr [rbx+10h], 0
0x180054480  jz      short loc_1800544C2
0x180054482  mov     eax, [rsp+0A8h+var_64]
0x180054486  dec     eax
0x180054488  and     eax, 1Fh
0x18005448b  cmp     esi, eax
0x18005448d  jnz     short loc_1800544C2
0x18005448f  mov     byte ptr [rbx+10h], 0
0x180054493  mov     byte ptr [rbx+38h], 0
0x180054497  mov     rcx, [rdi+78h]; hEvent
0x18005449b  call    cs:__imp_SetEvent
0x1800544a1  xor     r15d, r15d
0x1800544a4  lea     rcx, [rsp+0A8h+var_60]
0x1800544a9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800544ae  mov     eax, r15d
0x1800544b1  add     rsp, 68h
0x1800544b5  pop     r15
0x1800544b7  pop     r14
0x1800544b9  pop     r13
0x1800544bb  pop     r12
0x1800544bd  pop     rdi
0x1800544be  pop     rsi
0x1800544bf  pop     rbp
0x1800544c0  pop     rbx
0x1800544c1  retn
0x1800544c2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x1800544c9  jb      short loc_1800544EA
0x1800544cb  mov     edx, 22h ; '"'
0x1800544d0  mov     r9, rdi
0x1800544d3  lea     r8, WPP_2ae34273ea0c3e44748ef5ee268f3ee0_Traceguids
0x1800544da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800544e1  mov     rcx, [rcx+10h]
0x1800544e5  call    WPP_SF_q
0x1800544ea  mov     rcx, rbx
0x1800544ed  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800544f2  mov     byte ptr [rbx+10h], 0
0x1800544f6  lea     rcx, [rsp+0A8h+var_60]
0x1800544fb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180054500  xor     eax, eax
0x180054502  jmp     short loc_1800544B1
```
