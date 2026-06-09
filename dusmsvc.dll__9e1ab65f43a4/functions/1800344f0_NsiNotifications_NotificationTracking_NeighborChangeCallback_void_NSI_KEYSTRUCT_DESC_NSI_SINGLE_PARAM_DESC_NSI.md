# NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)

- ea: `0x1800344f0`
- end: `0x180034940`
- name: `?NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z`
- size: `1104`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007c90`
- `0x18000f094`
- `0x1800319d4`
- `0x180031a78`
- `0x180031b20`
- `0x180031bc4`
- `0x180031c6c`
- `0x180031d34`
- `0x180031e00`
- `0x180031ea4`
- `0x1800344f0`
- `0x1800364ec`
- `0x180036668`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003470d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034791`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003484f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800348b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003470d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034791`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003484f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800348b7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800347e8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180034911`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800347e8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180034911`
- `NSI!NsiFreeTable` at `0x180034814`
- `NSI!NsiFreeTable` at `0x180034814`
- `NSI!NsiAllocateAndGetTable` at `0x180034661`
- `NSI!NsiAllocateAndGetTable` at `0x180034661`

## pseudocode

```c
void __fastcall NsiNotifications::NotificationTracking::NeighborChangeCallback(__int64 **a1, __int64 a2)
{
  __int64 *v2; // rbx
  __int64 v3; // rdi
  __int64 **v4; // r8
  unsigned int v5; // r9d
  __int64 *v6; // r10
  int v7; // eax
  bool v8; // zf
  unsigned __int8 v9; // si
  const NPI_MODULEID *v10; // rdx
  __int64 *v11; // r9
  unsigned int Table; // eax
  __int64 v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  struct _TP_WORK *v17; // rcx
  __int64 v18; // rsi
  _QWORD v19[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v20; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v21[80]; // [rsp+90h] [rbp-70h]
  int v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+F0h] [rbp-10h]
  __int64 v24; // [rsp+F8h] [rbp-8h]
  __int64 v25; // [rsp+100h] [rbp+0h]
  __int64 v26; // [rsp+108h] [rbp+8h] BYREF
  __int64 v27; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v28; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v2 = *a1;
  v3 = **a1;
  if ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load(v3, a2, a1) )
  {
    if ( v5 )
    {
      switch ( v5 )
      {
        case 1u:
          v7 = *((_DWORD *)v2 + 50) >> 1;
          break;
        case 2u:
          v7 = *((_DWORD *)v2 + 50) >> 2;
          break;
        case 3u:
          v7 = *((_DWORD *)v2 + 50) >> 3;
          break;
        default:
          return;
      }
      v8 = (v7 & 1) == 0;
    }
    else
    {
      v8 = (v2[25] & 1) == 0;
    }
    if ( !v8 )
    {
      if ( *((_DWORD *)v4 + 2) == 1 )
      {
        v9 = 1;
        v10 = &NPI_MS_IPV4_MODULEID;
      }
      else
      {
        v9 = 0;
        v10 = &NPI_MS_IPV6_MODULEID;
      }
      if ( v5 > 2 )
      {
        v26 = 0;
        v27 = 0;
        v25 = 0;
        v24 = 0;
        v23 = 0;
        v28 = 0;
        v11 = &v27;
        if ( v9 )
          v11 = &v26;
        Table = NsiAllocateAndGetTable(1, v10, 11, v11);
        if ( Table )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x6E9,
            (unsigned int)"OneCore\\Private\\Net\\inc\\nsinotificationtracking.h",
            (const char *)Table,
            8 * (v9 ^ 1) + 24);
LABEL_33:
          v15 = v26;
          if ( !v9 )
            v15 = v27;
          NsiFreeTable(v15, v25, v24, v23);
          return;
        }
        v13 = 0;
        if ( !v28 )
          goto LABEL_33;
        while ( 1 )
        {
          v14 = 32LL * (unsigned int)v13;
          *(_QWORD *)&v20 = v3;
          *((_QWORD *)&v20 + 1) = v2;
          if ( v9 )
          {
            *(_OWORD *)v21 = *(_OWORD *)(v26 + 24 * v13);
            *(_QWORD *)&v21[16] = *(_QWORD *)(v26 + 24 * v13 + 16);
            *(_OWORD *)&v21[24] = *(_OWORD *)(v14 + v25);
            *(_OWORD *)&v21[40] = *(_OWORD *)(v14 + v25 + 16);
            *(_OWORD *)&v21[56] = *(_OWORD *)(v24 + 16LL * (unsigned int)v13);
            *(_DWORD *)&v21[72] = *(_DWORD *)(v23 + 4 * v13);
            EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 1632));
            v19[0] = v3 + 1632;
            if ( !*(_BYTE *)(v3 + 1896) )
            {
              if ( *(_DWORD *)(v3 + 1624) == 1 )
                ___emplace_back_V_lambda_2___BA___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_2___BA___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
                  v3 + 1776,
                  &v20);
              else
                ___emplace_back_V_lambda_2___BA___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_2___BA___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
                  (_QWORD *)(v3 + 1856),
                  (__int64)&v20);
LABEL_31:
              wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v19);
              _InterlockedIncrement64((volatile signed __int64 *)(v3 + 1760));
              SubmitThreadpoolWork(*(PTP_WORK *)(v3 + 1752));
              goto LABEL_32;
            }
          }
          else
          {
            *(_OWORD *)v21 = *(_OWORD *)(v14 + v27);
            *(_OWORD *)&v21[16] = *(_OWORD *)(v14 + v27 + 16);
            *(_OWORD *)&v21[32] = *(_OWORD *)(v14 + v25);
            *(_OWORD *)&v21[48] = *(_OWORD *)(v14 + v25 + 16);
            *(_OWORD *)&v21[64] = *(_OWORD *)(v24 + 16LL * (unsigned int)v13);
            v22 = *(_DWORD *)(v23 + 4 * v13);
            EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 1632));
            v19[0] = v3 + 1632;
            if ( !*(_BYTE *)(v3 + 1896) )
            {
              if ( *(_DWORD *)(v3 + 1624) == 1 )
                ___emplace_back_V_lambda_3___BC___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_3___BC___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
                  v3 + 1776,
                  &v20);
              else
                ___emplace_back_V_lambda_3___BC___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_3___BC___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
                  (_QWORD *)(v3 + 1856),
                  (__int64)&v20);
              goto LABEL_31;
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v19);
LABEL_32:
          v13 = (unsigned int)(v13 + 1);
          if ( (unsigned int)v13 >= v28 )
            goto LABEL_33;
        }
      }
      v16 = *v6;
      *(_QWORD *)&v20 = v3;
      *((_QWORD *)&v20 + 1) = v2;
      *(_DWORD *)v21 = v5;
      *(_OWORD *)&v21[8] = *(_OWORD *)(v16 + 8);
      if ( v9 )
      {
        *(_QWORD *)&v21[24] = *(_QWORD *)(v16 + 24);
        EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 1632));
        v19[0] = v3 + 1632;
        if ( !*(_BYTE *)(v3 + 1896) )
        {
          if ( *(_DWORD *)(v3 + 1624) == 1 )
            ___emplace_back_V_lambda_4___BG___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_4___BG___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
              v3 + 1776,
              &v20);
          else
            ___emplace_back_V_lambda_4___BG___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_4___BG___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
              (_QWORD *)(v3 + 1856),
              &v20);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v19);
          _InterlockedIncrement64((volatile signed __int64 *)(v3 + 1760));
          v17 = *(struct _TP_WORK **)(v3 + 1752);
LABEL_48:
          SubmitThreadpoolWork(v17);
          return;
        }
      }
      else
      {
        v18 = **v4;
        *(_OWORD *)&v21[24] = *(_OWORD *)(v16 + 24);
        EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 1632));
        v19[0] = v18 + 1632;
        if ( !*(_BYTE *)(v18 + 1896) )
        {
          if ( *(_DWORD *)(v18 + 1624) == 1 )
            ___emplace_back_V_lambda_5___BI___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_5___BI___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
              v18 + 1776,
              &v20);
          else
            ___emplace_back_V_lambda_5___BI___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_5___BI___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
              (_QWORD *)(v18 + 1856),
              (__int64)&v20);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v19);
          _InterlockedIncrement64((volatile signed __int64 *)(v18 + 1760));
          v17 = *(struct _TP_WORK **)(v18 + 1752);
          goto LABEL_48;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v19);
    }
  }
}

```

## disassembly

```asm
0x1800344f0  mov     [rsp-8+arg_8], rbx
0x1800344f5  mov     [rsp-8+arg_10], rsi
0x1800344fa  push    rbp
0x1800344fb  push    rdi
0x1800344fc  push    r12
0x1800344fe  push    r14
0x180034500  push    r15
0x180034502  lea     rbp, [rsp-30h]
0x180034507  sub     rsp, 130h
0x18003450e  mov     rax, cs:__security_cookie
0x180034515  xor     rax, rsp
0x180034518  mov     [rbp+50h+var_30], rax
0x18003451c  mov     r10, rdx
0x18003451f  mov     r8, rcx
0x180034522  mov     rbx, [rcx]
0x180034525  mov     rdi, [rbx]
0x180034528  mov     rcx, rdi
0x18003452b  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180034530  test    al, al
0x180034532  jnz     loc_180034918
0x180034538  mov     ecx, r9d
0x18003453b  test    r9d, r9d
0x18003453e  jz      short loc_180034577
0x180034540  sub     ecx, 1
0x180034543  jz      short loc_180034569
0x180034545  sub     ecx, 1
0x180034548  jz      short loc_18003455E
0x18003454a  cmp     ecx, 1
0x18003454d  jnz     loc_180034918
0x180034553  mov     eax, [rbx+0C8h]
0x180034559  shr     eax, 3
0x18003455c  jmp     short loc_180034571
0x18003455e  mov     eax, [rbx+0C8h]
0x180034564  shr     eax, 2
0x180034567  jmp     short loc_180034571
0x180034569  mov     eax, [rbx+0C8h]
0x18003456f  shr     eax, 1
0x180034571  and     al, 1
0x180034573  test    al, al
0x180034575  jmp     short loc_18003457E
0x180034577  test    byte ptr [rbx+0C8h], 1
0x18003457e  jz      loc_180034918
0x180034584  cmp     dword ptr [r8+8], 1
0x180034589  jnz     short loc_180034597
0x18003458b  mov     sil, 1
0x18003458e  lea     rdx, NPI_MS_IPV4_MODULEID
0x180034595  jmp     short loc_1800345A1
0x180034597  xor     sil, sil
0x18003459a  lea     rdx, NPI_MS_IPV6_MODULEID
0x1800345a1  mov     ecx, r9d
0x1800345a4  test    r9d, r9d
0x1800345a7  jz      loc_18003481F
0x1800345ad  sub     ecx, 1
0x1800345b0  jz      loc_18003481F
0x1800345b6  sub     ecx, 1
0x1800345b9  jz      loc_18003481F
0x1800345bf  cmp     ecx, 1
0x1800345c2  jnz     loc_180034918
0x1800345c8  mov     [rbp+50h+var_48], 0
0x1800345d0  mov     [rbp+50h+var_40], 0
0x1800345d8  mov     [rbp+50h+var_50], 0
0x1800345e0  mov     [rbp+50h+var_58], 0
0x1800345e8  mov     [rbp+50h+var_60], 0
0x1800345f0  mov     [rbp+50h+var_38], 0
0x1800345f7  movzx   eax, sil
0x1800345fb  xor     eax, ecx
0x1800345fd  lea     eax, ds:18h[rax*8]
0x180034604  lea     r9, [rbp+50h+var_40]
0x180034608  lea     rcx, [rbp+50h+var_48]
0x18003460c  test    sil, sil
0x18003460f  cmovnz  r9, rcx
0x180034613  mov     [rsp+150h+var_F0], 1
0x180034618  lea     rcx, [rbp+50h+var_38]
0x18003461c  mov     [rsp+150h+var_F8], rcx
0x180034621  mov     [rsp+150h+var_100], 4
0x180034629  lea     rcx, [rbp+50h+var_60]
0x18003462d  mov     [rsp+150h+var_108], rcx
0x180034632  mov     [rsp+150h+var_110], 10h
0x18003463a  lea     rcx, [rbp+50h+var_58]
0x18003463e  mov     [rsp+150h+var_118], rcx
0x180034643  mov     [rsp+150h+var_120], 20h ; ' '
0x18003464b  lea     rcx, [rbp+50h+var_50]
0x18003464f  mov     [rsp+150h+var_128], rcx
0x180034654  mov     [rsp+150h+var_130], eax; unsigned int
0x180034658  mov     ecx, 1
0x18003465d  lea     r8d, [rcx+0Ah]
0x180034661  call    cs:__imp_NsiAllocateAndGetTable
0x180034667  test    eax, eax
0x180034669  jz      short loc_180034688
0x18003466b  mov     rcx, [rbp+58h]; this
0x18003466f  mov     r9d, eax; char *
0x180034672  lea     r8, aOnecorePrivate_0; "OneCore\\Private\\Net\\inc\\nsinotifica"...
0x180034679  mov     edx, 6E9h; void *
0x18003467e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180034683  jmp     loc_1800347FB
0x180034688  xor     r15d, r15d
0x18003468b  cmp     [rbp+50h+var_38], r15d
0x18003468f  jbe     loc_1800347FB
0x180034695  lea     r12, [rdi+660h]
0x18003469c  lea     r14, [rdi+6F0h]
0x1800346a3  mov     edx, r15d
0x1800346a6  shl     rdx, 5
0x1800346aa  mov     r9d, r15d
0x1800346ad  add     r9, r9
0x1800346b0  mov     [rbp+50h+var_D0], rdi
0x1800346b4  mov     [rbp+50h+var_C8], rbx
0x1800346b8  test    sil, sil
0x1800346bb  jz      loc_18003474B
0x1800346c1  lea     rcx, [r15+r15*2]
0x1800346c5  mov     rax, [rbp+50h+var_48]
0x1800346c9  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800346cd  movaps  [rbp+50h+var_C0], xmm0
0x1800346d1  movsd   xmm1, qword ptr [rax+rcx*8+10h]
0x1800346d7  movsd   qword ptr [rbp+50h+var_B0], xmm1
0x1800346dc  mov     rax, [rbp+50h+var_50]
0x1800346e0  movups  xmm0, xmmword ptr [rdx+rax]
0x1800346e4  movups  [rbp+50h+var_B0+8], xmm0
0x1800346e8  movups  xmm1, xmmword ptr [rdx+rax+10h]
0x1800346ed  movups  [rbp+50h+var_98], xmm1
0x1800346f1  mov     rax, [rbp+50h+var_58]
0x1800346f5  movups  xmm0, xmmword ptr [rax+r9*8]
0x1800346fa  movdqu  [rbp+50h+var_88], xmm0
0x1800346ff  mov     rax, [rbp+50h+var_60]
0x180034703  mov     ecx, [rax+r15*4]
0x180034707  mov     [rbp+50h+var_78], ecx
0x18003470a  mov     rcx, r12; lpCriticalSection
0x18003470d  call    cs:__imp_EnterCriticalSection
0x180034713  mov     [rsp+150h+var_E0], r12
0x180034718  cmp     byte ptr [r14+78h], 0
0x18003471d  jnz     loc_1800347A3
0x180034723  lea     rdx, [rbp+50h+var_D0]
0x180034727  cmp     dword ptr [rdi+658h], 1
0x18003472e  jnz     short loc_18003473D
0x180034730  mov     rcx, r14
0x180034733  call    ??$emplace_back@V_lambda_2_@?BA@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_2_@?BA@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::function<void (void)>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`16'::_lambda_2_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`16'::_lambda_2_ &&)
0x180034738  jmp     loc_1800347CF
0x18003473d  lea     rcx, [r14+50h]
0x180034741  call    ??$emplace_back@V_lambda_2_@?BA@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_2_@?BA@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`16'::_lambda_2_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`16'::_lambda_2_ &&)
0x180034746  jmp     loc_1800347CF
0x18003474b  mov     rax, [rbp+50h+var_40]
0x18003474f  movups  xmm0, xmmword ptr [rdx+rax]
0x180034753  movaps  [rbp+50h+var_C0], xmm0
0x180034757  movups  xmm1, xmmword ptr [rdx+rax+10h]
0x18003475c  movaps  [rbp+50h+var_B0], xmm1
0x180034760  mov     rax, [rbp+50h+var_50]
0x180034764  movups  xmm0, xmmword ptr [rdx+rax]
0x180034768  movaps  xmmword ptr [rbp-50h], xmm0
0x18003476c  movups  xmm1, xmmword ptr [rdx+rax+10h]
0x180034771  movaps  [rbp+50h+var_98+8], xmm1
0x180034775  mov     rax, [rbp+50h+var_58]
0x180034779  movups  xmm0, xmmword ptr [rax+r9*8]
0x18003477e  movdqu  [rbp+50h+var_88+8], xmm0
0x180034783  mov     rax, [rbp+50h+var_60]
0x180034787  mov     ecx, [rax+r15*4]
0x18003478b  mov     [rbp+50h+var_70], ecx
0x18003478e  mov     rcx, r12; lpCriticalSection
0x180034791  call    cs:__imp_EnterCriticalSection
0x180034797  mov     [rsp+150h+var_E0], r12
0x18003479c  cmp     byte ptr [r14+78h], 0
0x1800347a1  jz      short loc_1800347AF
0x1800347a3  lea     rcx, [rsp+150h+var_E0]
0x1800347a8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800347ad  jmp     short loc_1800347EE
0x1800347af  lea     rdx, [rbp+50h+var_D0]
0x1800347b3  cmp     dword ptr [rdi+658h], 1
0x1800347ba  jnz     short loc_1800347C6
0x1800347bc  mov     rcx, r14
0x1800347bf  call    ??$emplace_back@V_lambda_3_@?BC@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_3_@?BC@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::function<void (void)>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`18'::_lambda_3_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`18'::_lambda_3_ &&)
0x1800347c4  jmp     short loc_1800347CF
0x1800347c6  lea     rcx, [r14+50h]
0x1800347ca  call    ??$emplace_back@V_lambda_3_@?BC@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_3_@?BC@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`18'::_lambda_3_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`18'::_lambda_3_ &&)
0x1800347cf  lea     rcx, [rsp+150h+var_E0]
0x1800347d4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800347d9  lock inc qword ptr [rdi+6E0h]
0x1800347e1  mov     rcx, [rdi+6D8h]; pwk
0x1800347e8  call    cs:__imp_SubmitThreadpoolWork
0x1800347ee  inc     r15d
0x1800347f1  cmp     r15d, [rbp+50h+var_38]
0x1800347f5  jb      loc_1800346A3
0x1800347fb  mov     r9, [rbp+50h+var_60]
0x1800347ff  mov     r8, [rbp+50h+var_58]
0x180034803  mov     rdx, [rbp+50h+var_50]
0x180034807  test    sil, sil
0x18003480a  mov     rcx, [rbp+50h+var_48]
0x18003480e  jnz     short loc_180034814
0x180034810  mov     rcx, [rbp+50h+var_40]
0x180034814  call    cs:__imp_NsiFreeTable
0x18003481a  jmp     loc_180034918
0x18003481f  mov     rcx, [r10]
0x180034822  mov     [rbp+50h+var_D0], rdi
0x180034826  mov     [rbp+50h+var_C8], rbx
0x18003482a  mov     dword ptr [rbp+50h+var_C0], r9d
0x18003482e  movups  xmm0, xmmword ptr [rcx+8]
0x180034832  movups  [rbp+50h+var_C0+8], xmm0
0x180034836  test    sil, sil
0x180034839  jz      short loc_18003489F
0x18003483b  movsd   xmm1, qword ptr [rcx+18h]
0x180034840  movsd   qword ptr [rbp+50h+var_B0+8], xmm1
0x180034845  lea     rbx, [rdi+660h]
0x18003484c  mov     rcx, rbx; lpCriticalSection
0x18003484f  call    cs:__imp_EnterCriticalSection
0x180034855  mov     [rsp+150h+var_E0], rbx
0x18003485a  lea     rcx, [rdi+6F0h]
0x180034861  cmp     byte ptr [rcx+78h], 0
0x180034865  jnz     short loc_1800348CF
0x180034867  lea     rdx, [rbp+50h+var_D0]
0x18003486b  cmp     dword ptr [rdi+658h], 1
0x180034872  jnz     short loc_18003487B
0x180034874  call    ??$emplace_back@V_lambda_4_@?BG@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_4_@?BG@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::function<void (void)>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`22'::_lambda_4_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`22'::_lambda_4_ &&)
0x180034879  jmp     short loc_180034884
0x18003487b  add     rcx, 50h ; 'P'
0x18003487f  call    ??$emplace_back@V_lambda_4_@?BG@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_4_@?BG@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`22'::_lambda_4_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`22'::_lambda_4_ &&)
0x180034884  lea     rcx, [rsp+150h+var_E0]
0x180034889  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003488e  lock inc qword ptr [rdi+6E0h]
0x180034896  mov     rcx, [rdi+6D8h]
0x18003489d  jmp     short loc_180034911
0x18003489f  mov     rax, [r8]
0x1800348a2  mov     rsi, [rax]
0x1800348a5  movups  xmm1, xmmword ptr [rcx+18h]
0x1800348a9  movups  [rbp+50h+var_B0+8], xmm1
0x1800348ad  lea     rbx, [rsi+660h]
0x1800348b4  mov     rcx, rbx; lpCriticalSection
0x1800348b7  call    cs:__imp_EnterCriticalSection
0x1800348bd  mov     [rsp+150h+var_E0], rbx
0x1800348c2  lea     rcx, [rsi+6F0h]
0x1800348c9  cmp     byte ptr [rcx+78h], 0
0x1800348cd  jz      short loc_1800348DB
0x1800348cf  lea     rcx, [rsp+150h+var_E0]
0x1800348d4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800348d9  jmp     short loc_180034918
0x1800348db  lea     rdx, [rbp+50h+var_D0]
0x1800348df  cmp     dword ptr [rsi+658h], 1
0x1800348e6  jnz     short loc_1800348EF
0x1800348e8  call    ??$emplace_back@V_lambda_5_@?BI@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_5_@?BI@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::function<void (void)>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`24'::_lambda_5_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`24'::_lambda_5_ &&)
0x1800348ed  jmp     short loc_1800348F8
0x1800348ef  add     rcx, 50h ; 'P'
0x1800348f3  call    ??$emplace_back@V_lambda_5_@?BI@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_5_@?BI@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`24'::_lambda_5_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`24'::_lambda_5_ &&)
0x1800348f8  lea     rcx, [rsp+150h+var_E0]
0x1800348fd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180034902  lock inc qword ptr [rsi+6E0h]
0x18003490a  mov     rcx, [rsi+6D8h]; pwk
0x180034911  call    cs:__imp_SubmitThreadpoolWork
0x180034917  nop
0x180034918  mov     rcx, [rbp+50h+var_30]
0x18003491c  xor     rcx, rsp; StackCookie
0x18003491f  call    __security_check_cookie
0x180034924  lea     r11, [rsp+150h+var_20]
0x18003492c  mov     rbx, [r11+38h]
0x180034930  mov     rsi, [r11+40h]
0x180034934  mov     rsp, r11
0x180034937  pop     r15
0x180034939  pop     r14
0x18003493b  pop     r12
0x18003493d  pop     rdi
0x18003493e  pop     rbp
0x18003493f  retn
```
