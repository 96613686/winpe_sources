# CNetworkMonitor::TakeSnapshot(int)

- ea: `0x18000e8f0`
- end: `0x18000f1b6`
- name: `?TakeSnapshot@CNetworkMonitor@@IEAAXH@Z`
- size: `2246`
- prototype: `void __fastcall(CNetworkMonitor *__hidden this, int)`
- caller_count: `9`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f8b0`
- `0x180021ab0`
- `0x180042b5c`
- `0x180058780`
- `0x18007c2f0`
- `0x1800865b4`
- `0x180086d54`
- `0x1800870c0`
- `0x18009d360`

## callees

- `0x18000e370`
- `0x18000e8f0`
- `0x180020bd0`
- `0x1800634e0`
- `0x180091afc`
- `0x180091b20`
- `0x180099ff8`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800ab7fc`
- `0x1800b1980`
- `0x1800b4c10`
- `0x1800e9bd8`
- `0x1800f5ccc`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e938`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e938`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ebb1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ebb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eb34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eb34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eaee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eaee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ec6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000eca7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ec6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000eca7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed75`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000e9e0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ea2a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000eed0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000e9e0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ea2a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000eed0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000e9ab`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000e9ab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000efe6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000efe6`
- `IPHLPAPI!GetIfEntry` at `0x18000e9ee`
- `IPHLPAPI!GetIfEntry` at `0x18000e9ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CNetworkMonitor::TakeSnapshot(CNetworkMonitor *this, unsigned int a2)
{
  unsigned int v2; // r15d
  volatile signed __int32 *v4; // rax
  volatile signed __int32 *v5; // rbx
  unsigned __int16 v6; // r14
  volatile signed __int32 **v7; // rdi
  _BYTE *v8; // rax
  DWORD IfEntry; // eax
  EVENT_LOG **v10; // rdx
  __int64 v11; // r8
  signed int v12; // edi
  __int64 v13; // r14
  LARGE_INTEGER *v14; // r15
  __int64 v15; // rdi
  struct _RTL_CRITICAL_SECTION *v16; // rsi
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 i; // rdx
  HKEY v20; // rdi
  LSTATUS Value; // eax
  LONG *p_HighPart; // rsi
  EVENT_LOG *v23; // r10
  unsigned int v24; // edi
  void *v25; // rcx
  ULONGLONG TickCount64; // rdi
  __int64 v27; // rcx
  ULONGLONG v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rcx
  unsigned int v31; // r15d
  unsigned __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdi
  void *v36; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData[4]; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type[2]; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp-70h] BYREF
  __int128 v42; // [rsp+98h] [rbp-68h]
  volatile signed __int32 *v43; // [rsp+B0h] [rbp-50h]
  __int128 v44; // [rsp+C0h] [rbp-40h] BYREF
  struct sockaddr pExceptionObject[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v46; // [rsp+F0h] [rbp-10h]
  __int128 v47; // [rsp+100h] [rbp+0h]
  __int128 v48; // [rsp+110h] [rbp+10h]
  __int128 v49; // [rsp+120h] [rbp+20h]
  __int128 v50; // [rsp+130h] [rbp+30h]
  __int128 v51; // [rsp+140h] [rbp+40h]

  v2 = a2;
  v4 = (volatile signed __int32 *)HeapAlloc(hBitsHeap, 8u, 0x10u);
  v5 = v4;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
    *(_OWORD *)&pExceptionObject[0].sa_data[6] = 0;
    *(_QWORD *)&pExceptionObject[0].sa_family = &ComError::`vftable';
    *(_QWORD *)&pExceptionObject[1].sa_data[6] = 2147942414LL;
    LODWORD(v46) = 1;
    throw (ComError *)pExceptionObject;
  }
  v6 = 0;
  v43 = v4;
  *((_DWORD *)v4 + 2) = 1;
  *(_QWORD *)v4 = 0;
  v7 = (volatile signed __int32 **)CopyThreadToken(&v36);
  if ( *(_QWORD *)v5 != *(_QWORD *)*v7 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( (unsigned __int64)(*(_QWORD *)v5 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v5);
        *(_QWORD *)v5 = 0;
      }
      operator delete((void *)v5, 0x10u);
    }
    v5 = *v7;
    v43 = v5;
    _InterlockedIncrement(v5 + 2);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v36 + 2, 0xFFFFFFFF) == 1 )
  {
    v25 = v36;
    if ( (unsigned __int64)(*(_QWORD *)v36 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v36);
      *(_QWORD *)v36 = 0;
      v25 = v36;
    }
    operator delete(v25, 0x10u);
  }
  RevertToSelf();
  v8 = (char *)this + 192;
  v36 = (char *)this + 192;
  while ( 1 )
  {
    if ( !v2 )
    {
      *((_DWORD *)this + 38) = 0;
      *v8 = 0;
      *((_BYTE *)this + 193) = 0;
    }
    *((_DWORD *)this + 177) = *((_DWORD *)this + 2);
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    IfEntry = GetIfEntry((PMIB_IFROW)((char *)this + 196));
    v12 = IfEntry;
    if ( IfEntry != 13 )
      break;
    v30 = *((_QWORD *)this + 132);
    if ( v30 )
    {
      memset(pExceptionObject, 0, sizeof(pExceptionObject));
      v46 = 0;
      v47 = 0;
      v48 = 0;
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, struct sockaddr *))(*(_QWORD *)v30 + 256LL))(v30, pExceptionObject);
      CNetworkMonitor::FindIGDDevice(this, v31, pExceptionObject, (bool *)this + 1130, 1);
      *((_QWORD *)this + 20) = 0;
      *((_QWORD *)this + 21) = 0;
      *((_QWORD *)this + 22) = 0;
      *((_QWORD *)this + 23) = 0;
      if ( *((_DWORD *)this + 2) != v31 )
      {
        *((_DWORD *)this + 2) = v31;
        CNetworkMonitor::Reset(this);
      }
      v8 = v36;
      if ( *(_BYTE *)v36 )
      {
        *(_QWORD *)cbData = 0;
        QueryPerformanceCounter((LARGE_INTEGER *)cbData);
        *(_QWORD *)cbData -= *((_QWORD *)this + 10);
        v32 = *(_QWORD *)cbData / *((__int64 *)g_GlobalInfo + 1);
        *(_QWORD *)cbData = v32;
        if ( v32 > 5 )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              WPP_c87c0f7aed2e3dfaa1338313329e445d_Traceguids,
              (unsigned int)v32);
          }
          *((_DWORD *)this + 37) = 1060320051;
          *((_DWORD *)this + 34) = 1060320051;
          *((_DWORD *)this + 36) = 1060320051;
        }
        v8 = v36;
      }
      *v8 = 0;
      ++v6;
      v36 = v8;
      v2 = a2;
      if ( v6 < 0xAu )
        continue;
    }
    goto LABEL_66;
  }
  if ( IfEntry )
  {
LABEL_66:
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_c87c0f7aed2e3dfaa1338313329e445d_Traceguids,
        v2,
        *((_DWORD *)this + 2),
        v12);
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    *((_DWORD *)this + 38) = v12;
    *(_OWORD *)&pExceptionObject[0].sa_data[6] = 0;
    *(_QWORD *)&pExceptionObject[0].sa_family = &ComError::`vftable';
    *(_QWORD *)&pExceptionObject[1].sa_data[6] = (unsigned int)v12 | 0x14F00000000LL;
    LODWORD(v46) = 1;
    throw (ComError *)pExceptionObject;
  }
  if ( v2 && *((_QWORD *)this + 20) && *((_QWORD *)this + 22) )
  {
    v13 = (int)v2;
    v14 = (LARGE_INTEGER *)((char *)this + 24 * (int)v2);
    v14[4] = PerformanceCount;
  }
  else
  {
    v13 = (int)v2;
    v14 = (LARGE_INTEGER *)((char *)this + 24 * (int)v2);
    QueryPerformanceCounter(v14 + 4);
  }
  v14[5].LowPart = *((_DWORD *)this + 187);
  v14[5].HighPart = *((_DWORD *)this + 193);
  if ( !*((_QWORD *)g_Manager + 208) )
    goto LABEL_28;
  v15 = *((_QWORD *)g_GlobalInfo + 2);
  v39 = 0;
  v16 = (struct _RTL_CRITICAL_SECTION *)(v15 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  *(_QWORD *)Type = v15 + 48;
  v17 = *(_QWORD *)(v15 + 48);
  v18 = *(_QWORD *)(v17 + 8);
  v42 = (unsigned __int64)v18;
  for ( i = v17; !*(_BYTE *)(v18 + 25); v18 = *(_QWORD *)v18 )
  {
    *(_QWORD *)&v42 = v18;
    if ( *(_DWORD *)(v18 + 32) >= v39 )
    {
      DWORD2(v42) = 1;
      i = v18;
    }
    else
    {
      DWORD2(v42) = 0;
      v18 += 16;
    }
  }
  if ( *(_BYTE *)(i + 25) || v39 < *(_DWORD *)(i + 32) )
  {
    if ( *(_QWORD *)(v15 + 56) == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    *(_QWORD *)cbData = &v39;
    v33 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(
            (__int64)&v44,
            v15 + 48,
            v17,
            v15 + 48,
            (_DWORD **)cbData);
    v34 = *(_QWORD *)(v33 + 8);
    *(_QWORD *)(v33 + 8) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>((__int64)&v44);
    *(_OWORD *)cbData = v42;
    i = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
          *(_QWORD *)Type,
          cbData,
          v34);
  }
  v20 = (HKEY)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(i + 40) + 16LL))(*(_QWORD *)(i + 40));
  if ( v16 )
    LeaveCriticalSection(v16);
  *(_DWORD *)Data = 0;
  Type[0] = 4;
  cbData[0] = 4;
  Value = RegQueryValueExW(v20, L"BITSTotalByteSource", 0, Type, Data, cbData);
  if ( !Value )
  {
    if ( Type[0] == 4 && cbData[0] == 4 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (int)WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
          *(int *)Data,
          (__int64)L"BITSTotalByteSource");
      if ( !*(_DWORD *)Data )
        goto LABEL_28;
      goto LABEL_25;
    }
    goto LABEL_89;
  }
  if ( Value != 2 )
  {
LABEL_89:
    v10 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_SDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        v11,
        (unsigned int)L"BITSTotalByteSource",
        Value,
        1);
  }
LABEL_25:
  if ( *((_BYTE *)this + 28) )
    goto LABEL_43;
  if ( !*((_BYTE *)this + 1130) )
  {
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v29 = (*(__int64 (__fastcall **)(_QWORD, struct sockaddr *))(**((_QWORD **)this + 132) + 256LL))(
            *((_QWORD *)this + 132),
            pExceptionObject);
    CNetworkMonitor::FindIGDDevice(this, v29, pExceptionObject, (bool *)this + 1130, 0);
  }
LABEL_28:
  if ( !*((_BYTE *)this + 28) )
  {
LABEL_29:
    *((_DWORD *)this + 6 * v13 + 12) = 0;
    p_HighPart = &v14[6].HighPart;
    v14[6].HighPart = 0;
    goto LABEL_30;
  }
LABEL_43:
  if ( *((_BYTE *)this + 1084) )
    goto LABEL_29;
  TickCount64 = GetTickCount64();
  v27 = *((_QWORD *)g_Manager + 208);
  v44 = *(_OWORD *)((char *)this + 12);
  p_HighPart = &v14[6].HighPart;
  (*(void (__fastcall **)(__int64, __int128 *, LARGE_INTEGER *, __int64))(*(_QWORD *)v27 + 56LL))(
    v27,
    &v44,
    v14 + 6,
    (__int64)&v14[6].QuadPart + 4);
  v28 = GetTickCount64() - TickCount64;
  *((_QWORD *)this + 140) = v28;
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control )
    goto LABEL_32;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    goto LABEL_31;
  WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c87c0f7aed2e3dfaa1338313329e445d_Traceguids, v28);
LABEL_30:
  v23 = WPP_GLOBAL_Control;
LABEL_31:
  if ( v23 == (EVENT_LOG *)&WPP_GLOBAL_Control )
  {
LABEL_32:
    v24 = a2;
    goto LABEL_33;
  }
  v24 = a2;
  if ( (*((_BYTE *)v23 + 28) & 0x40) != 0 )
    WPP_SF_lDDDDDD(
      *((_QWORD *)v23 + 2),
      v10,
      v11,
      a2,
      v14[5].LowPart,
      v14[5].HighPart,
      *((_DWORD *)this + 6 * v13 + 12),
      *p_HighPart,
      v14[4].HighPart,
      v14[4].LowPart);
LABEL_33:
  if ( v24 == 2 && !*((_DWORD *)this + 38) )
    *(_BYTE *)v36 = 1;
  SetThreadToken(0, *(HANDLE *)v5);
  if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
  {
    if ( (unsigned __int64)(*(_QWORD *)v5 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v5);
      *(_QWORD *)v5 = 0;
    }
    operator delete((void *)v5, 0x10u);
  }
}

```

## disassembly

```asm
0x18000e8f0  mov     [rsp-8+arg_10], rbx
0x18000e8f5  push    rbp
0x18000e8f6  push    rsi
0x18000e8f7  push    rdi
0x18000e8f8  push    r12
0x18000e8fa  push    r13
0x18000e8fc  push    r14
0x18000e8fe  push    r15
0x18000e900  lea     rbp, [rsp-60h]
0x18000e905  sub     rsp, 160h
0x18000e90c  mov     rax, cs:__security_cookie
0x18000e913  xor     rax, rsp
0x18000e916  mov     [rbp+90h+var_40], rax
0x18000e91a  mov     r15d, edx
0x18000e91d  mov     [rsp+190h+var_140], edx
0x18000e921  mov     r12, rcx
0x18000e924  xor     esi, esi
0x18000e926  mov     edx, 8; dwFlags
0x18000e92b  mov     r8d, 10h; dwBytes
0x18000e931  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000e938  call    cs:__imp_HeapAlloc
0x18000e93e  mov     rbx, rax
0x18000e941  test    rax, rax
0x18000e944  jz      loc_18000EFED
0x18000e94a  mov     r14d, esi
0x18000e94d  mov     [rbp+90h+var_E0], rax
0x18000e951  mov     dword ptr [rax+8], 1
0x18000e958  mov     [rax], rsi
0x18000e95b  lea     rcx, [rsp+190h+var_138]
0x18000e960  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18000e965  mov     rdi, rax
0x18000e968  mov     rcx, [rax]
0x18000e96b  mov     rdx, [rcx]
0x18000e96e  mov     r13d, 0FFFFFFFFh
0x18000e974  cmp     [rbx], rdx
0x18000e977  jz      short loc_18000E995
0x18000e979  mov     ecx, r13d
0x18000e97c  lock xadd [rbx+8], ecx
0x18000e981  cmp     ecx, 1
0x18000e984  jz      loc_18000ED68
0x18000e98a  mov     rbx, [rdi]
0x18000e98d  mov     [rbp+90h+var_E0], rbx
0x18000e991  lock inc dword ptr [rbx+8]
0x18000e995  mov     rcx, [rsp+190h+var_138]
0x18000e99a  mov     eax, r13d
0x18000e99d  lock xadd [rcx+8], eax
0x18000e9a2  cmp     eax, 1
0x18000e9a5  jz      loc_18000EBF9
0x18000e9ab  call    cs:__imp_RevertToSelf
0x18000e9b1  lea     rax, [r12+0C0h]
0x18000e9b9  mov     [rsp+190h+var_138], rax
0x18000e9be  test    r15d, r15d
0x18000e9c1  jz      loc_18000F055
0x18000e9c7  mov     eax, [r12+8]
0x18000e9cc  mov     [r12+2C4h], eax
0x18000e9d4  mov     qword ptr [rbp+90h+PerformanceCount], 0
0x18000e9dc  lea     rcx, [rbp+90h+PerformanceCount]; lpPerformanceCount
0x18000e9e0  call    cs:__imp_QueryPerformanceCounter
0x18000e9e6  lea     rcx, [r12+0C4h]; pIfRow
0x18000e9ee  call    cs:__imp_GetIfEntry
0x18000e9f4  mov     edi, eax
0x18000e9f6  cmp     eax, 0Dh
0x18000e9f9  jz      loc_18000EE2A
0x18000e9ff  test    eax, eax
0x18000ea01  jnz     loc_18000EF22
0x18000ea07  test    r15d, r15d
0x18000ea0a  jz      short loc_18000EA1B
0x18000ea0c  cmp     qword ptr [r12+0A0h], 0
0x18000ea15  jnz     loc_18000F0EE
0x18000ea1b  movsxd  r14, r15d
0x18000ea1e  lea     rax, [r14+r14*2]
0x18000ea22  lea     r15, [r12+rax*8]
0x18000ea26  lea     rcx, [r15+20h]; lpPerformanceCount
0x18000ea2a  call    cs:__imp_QueryPerformanceCounter
0x18000ea30  mov     eax, [r12+2ECh]
0x18000ea38  mov     [r15+28h], eax
0x18000ea3c  mov     eax, [r12+304h]
0x18000ea44  mov     [r15+2Ch], eax
0x18000ea48  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18000ea4f  cmp     qword ptr [rax+680h], 0
0x18000ea57  jz      loc_18000EB66
0x18000ea5d  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18000ea64  mov     rdi, [rax+10h]
0x18000ea68  mov     [rbp+90h+var_110], 0
0x18000ea6f  lea     rsi, [rdi+8]
0x18000ea73  mov     rcx, rsi; lpCriticalSection
0x18000ea76  call    cs:__imp_EnterCriticalSection
0x18000ea7c  lea     r9, [rdi+30h]
0x18000ea80  mov     qword ptr [rbp+90h+Type], r9
0x18000ea84  mov     r8, [r9]
0x18000ea87  mov     rax, [r8+8]
0x18000ea8b  mov     qword ptr [rbp+90h+var_F8], rax
0x18000ea8f  xor     r10d, r10d
0x18000ea92  mov     qword ptr [rbp+90h+var_F8+8], r10
0x18000ea96  mov     rdx, r8
0x18000ea99  mov     ecx, [rbp+90h+var_110]
0x18000ea9c  cmp     [rax+19h], r10b
0x18000eaa0  jnz     short loc_18000EAC0
0x18000eaa2  mov     qword ptr [rbp+90h+var_F8], rax
0x18000eaa6  cmp     [rax+20h], ecx
0x18000eaa9  jge     loc_18000EBEA
0x18000eaaf  mov     dword ptr [rbp+90h+var_F8+8], r10d
0x18000eab3  add     rax, 10h
0x18000eab7  mov     rax, [rax]
0x18000eaba  cmp     [rax+19h], r10b
0x18000eabe  jz      short loc_18000EAA2
0x18000eac0  cmp     [rdx+19h], r10b
0x18000eac4  jnz     loc_18000EFCB
0x18000eaca  cmp     ecx, [rdx+20h]
0x18000eacd  jl      loc_18000EFCB
0x18000ead3  mov     rcx, [rdx+28h]
0x18000ead7  mov     rax, [rcx]
0x18000eada  mov     rax, [rax+10h]
0x18000eade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eae3  mov     rdi, rax
0x18000eae6  test    rsi, rsi
0x18000eae9  jz      short loc_18000EAF5
0x18000eaeb  mov     rcx, rsi; lpCriticalSection
0x18000eaee  call    cs:__imp_LeaveCriticalSection
0x18000eaf4  nop
0x18000eaf5  mov     dword ptr [rsp+190h+Data], 0
0x18000eafd  mov     [rbp+90h+Type], 4
0x18000eb04  mov     [rsp+190h+cbData], 4
0x18000eb0c  lea     rax, [rsp+190h+cbData]
0x18000eb11  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18000eb16  lea     rax, [rsp+190h+Data]
0x18000eb1b  mov     [rsp+190h+lpData], rax; lpData
0x18000eb20  lea     r9, [rbp+90h+Type]; lpType
0x18000eb24  xor     r8d, r8d; lpReserved
0x18000eb27  lea     rsi, ValueName; "BITSTotalByteSource"
0x18000eb2e  mov     rdx, rsi; lpValueName
0x18000eb31  mov     rcx, rdi; hKey
0x18000eb34  call    cs:__imp_RegQueryValueExW
0x18000eb3a  test    eax, eax
0x18000eb3c  jz      loc_18000ED90
0x18000eb42  cmp     eax, 2
0x18000eb45  jnz     loc_18000F199
0x18000eb4b  cmp     byte ptr [r12+1Ch], 0
0x18000eb51  jnz     loc_18000EC5C
0x18000eb57  cmp     byte ptr [r12+46Ah], 0
0x18000eb60  jz      loc_18000EDCC
0x18000eb66  cmp     byte ptr [r12+1Ch], 0
0x18000eb6c  jnz     loc_18000EC5C
0x18000eb72  lea     rax, [r14+r14*2]
0x18000eb76  xor     ecx, ecx
0x18000eb78  mov     [r12+rax*8+30h], ecx
0x18000eb7d  lea     rsi, [r15+34h]
0x18000eb81  mov     [rsi], ecx
0x18000eb83  mov     r10, cs:WPP_GLOBAL_Control
0x18000eb8a  lea     rcx, WPP_GLOBAL_Control
0x18000eb91  mov     eax, 2
0x18000eb96  cmp     r10, rcx
0x18000eb99  jnz     loc_18000ECF7
0x18000eb9f  mov     edi, [rsp+190h+var_140]
0x18000eba3  cmp     edi, 2
0x18000eba6  jz      loc_18000ED4C
0x18000ebac  mov     rdx, [rbx]; Token
0x18000ebaf  xor     ecx, ecx; Thread
0x18000ebb1  call    cs:__imp_SetThreadToken
0x18000ebb7  lock xadd [rbx+8], r13d
0x18000ebbd  cmp     r13d, 1
0x18000ebc1  jz      short loc_18000EC30
0x18000ebc3  mov     rcx, [rbp+90h+var_40]
0x18000ebc7  xor     rcx, rsp; StackCookie
0x18000ebca  call    __security_check_cookie
0x18000ebcf  mov     rbx, [rsp+190h+arg_10]
0x18000ebd7  add     rsp, 160h
0x18000ebde  pop     r15
0x18000ebe0  pop     r14
0x18000ebe2  pop     r13
0x18000ebe4  pop     r12
0x18000ebe6  pop     rdi
0x18000ebe7  pop     rsi
0x18000ebe8  pop     rbp
0x18000ebe9  retn
0x18000ebea  mov     dword ptr [rbp+90h+var_F8+8], 1
0x18000ebf1  mov     rdx, rax
0x18000ebf4  jmp     loc_18000EAB7
0x18000ebf9  mov     rcx, [rsp+190h+var_138]
0x18000ebfe  mov     rdx, [rcx]
0x18000ec01  lea     rax, [rdx-1]
0x18000ec05  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ec09  ja      short loc_18000EC21
0x18000ec0b  mov     rcx, rdx; hObject
0x18000ec0e  call    cs:__imp_CloseHandle
0x18000ec14  mov     rax, [rsp+190h+var_138]
0x18000ec19  mov     [rax], rsi
0x18000ec1c  mov     rcx, [rsp+190h+var_138]; void *
0x18000ec21  mov     edx, 10h; unsigned __int64
0x18000ec26  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ec2b  jmp     loc_18000E9AB
0x18000ec30  mov     rcx, [rbx]; hObject
0x18000ec33  lea     rax, [rcx-1]
0x18000ec37  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ec3b  ja      short loc_18000EC4A
0x18000ec3d  call    cs:__imp_CloseHandle
0x18000ec43  mov     qword ptr [rbx], 0
0x18000ec4a  mov     edx, 10h; unsigned __int64
0x18000ec4f  mov     rcx, rbx; void *
0x18000ec52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ec57  jmp     loc_18000EBC3
0x18000ec5c  cmp     byte ptr [r12+43Ch], 0
0x18000ec65  jnz     loc_18000EB72
0x18000ec6b  call    cs:__imp_GetTickCount64
0x18000ec71  mov     rdi, rax
0x18000ec74  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18000ec7b  mov     rcx, [rcx+680h]
0x18000ec82  movups  xmm0, xmmword ptr [r12+0Ch]
0x18000ec88  movaps  [rbp+90h+var_D0], xmm0
0x18000ec8c  lea     rsi, [r15+34h]
0x18000ec90  mov     rdx, [rcx]
0x18000ec93  lea     r8, [r15+30h]
0x18000ec97  mov     rax, [rdx+38h]
0x18000ec9b  mov     r9, rsi
0x18000ec9e  lea     rdx, [rbp+90h+var_D0]
0x18000eca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eca7  call    cs:__imp_GetTickCount64
0x18000ecad  sub     rax, rdi
0x18000ecb0  mov     [r12+460h], rax
0x18000ecb8  mov     r10, cs:WPP_GLOBAL_Control
0x18000ecbf  lea     rcx, WPP_GLOBAL_Control
0x18000ecc6  cmp     r10, rcx
0x18000ecc9  jz      loc_18000EB9F
0x18000eccf  test    byte ptr [r10+1Ch], 40h
0x18000ecd4  jz      loc_18000EB91
0x18000ecda  mov     edx, 13h
0x18000ecdf  mov     r9, rax
0x18000ece2  lea     r8, WPP_c87c0f7aed2e3dfaa1338313329e445d_Traceguids
0x18000ece9  mov     rcx, [r10+10h]
0x18000eced  call    WPP_SF_q
0x18000ecf2  jmp     loc_18000EB83
0x18000ecf7  mov     edi, [rsp+190h+var_140]
0x18000ecfb  test    byte ptr [r10+1Ch], 40h
0x18000ed00  jz      loc_18000EBA3
0x18000ed06  add     rax, r14
0x18000ed09  lea     rcx, [rax+rax*2]
0x18000ed0d  mov     eax, [r15+20h]
0x18000ed11  mov     [rsp+190h+var_148], eax
0x18000ed15  mov     eax, [r15+24h]
0x18000ed19  mov     [rsp+190h+var_150], eax
0x18000ed1d  mov     eax, [rsi]
0x18000ed1f  mov     [rsp+190h+var_158], eax
0x18000ed23  mov     eax, [r12+rcx*8]
0x18000ed27  mov     [rsp+190h+var_160], eax
0x18000ed2b  mov     eax, [r15+2Ch]
0x18000ed2f  mov     dword ptr [rsp+190h+lpcbData], eax
0x18000ed33  mov     eax, [r15+28h]
0x18000ed37  mov     dword ptr [rsp+190h+lpData], eax
0x18000ed3b  mov     r9d, edi
0x18000ed3e  mov     rcx, [r10+10h]
0x18000ed42  call    WPP_SF_lDDDDDD
0x18000ed47  jmp     loc_18000EBA3
0x18000ed4c  cmp     dword ptr [r12+98h], 0
0x18000ed55  jnz     loc_18000EBAC
0x18000ed5b  mov     rax, [rsp+190h+var_138]
0x18000ed60  mov     byte ptr [rax], 1
0x18000ed63  jmp     loc_18000EBAC
0x18000ed68  mov     rcx, [rbx]; hObject
0x18000ed6b  lea     rdx, [rcx-1]
0x18000ed6f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000ed73  ja      short loc_18000ED7E
0x18000ed75  call    cs:__imp_CloseHandle
0x18000ed7b  mov     [rbx], rsi
0x18000ed7e  mov     edx, 10h; unsigned __int64
0x18000ed83  mov     rcx, rbx; void *
0x18000ed86  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ed8b  jmp     loc_18000E98A
0x18000ed90  cmp     [rbp+90h+Type], 4
0x18000ed94  jnz     loc_18000F199
0x18000ed9a  cmp     [rsp+190h+cbData], 4
0x18000ed9f  jnz     loc_18000F199
0x18000eda5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edac  lea     rax, WPP_GLOBAL_Control
0x18000edb3  cmp     rcx, rax
0x18000edb6  jnz     loc_18000F16B
0x18000edbc  cmp     dword ptr [rsp+190h+Data], 0
0x18000edc1  jz      loc_18000EB66
0x18000edc7  jmp     loc_18000EB4B
0x18000edcc  xorps   xmm0, xmm0
0x18000edcf  movups  [rbp+90h+pExceptionObject], xmm0
0x18000edd3  movups  [rbp+90h+var_B0], xmm0
0x18000edd7  movups  [rbp+90h+var_A0], xmm0
0x18000eddb  movups  [rbp+90h+var_90], xmm0
0x18000eddf  movups  [rbp+90h+var_80], xmm0
0x18000ede3  movups  [rbp+90h+var_70], xmm0
0x18000ede7  movups  [rbp+90h+var_60], xmm0
0x18000edeb  movups  [rbp+90h+var_50], xmm0
0x18000edef  mov     rcx, [r12+420h]
0x18000edf7  mov     rax, [rcx]
0x18000edfa  lea     rdx, [rbp+90h+pExceptionObject]
0x18000edfe  mov     rax, [rax+100h]
0x18000ee05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee0a  mov     byte ptr [rsp+190h+lpData], 0; bool
0x18000ee0f  lea     r9, [r12+46Ah]; bool *
0x18000ee17  lea     r8, [rbp+90h+pExceptionObject]; struct sockaddr *
0x18000ee1b  mov     edx, eax; unsigned int
0x18000ee1d  mov     rcx, r12; this
0x18000ee20  call    ?FindIGDDevice@CNetworkMonitor@@IEAAXKPEAUsockaddr@@PEA_N_N@Z; CNetworkMonitor::FindIGDDevice(ulong,sockaddr *,bool *,bool)
0x18000ee25  jmp     loc_18000EB66
0x18000ee2a  mov     rcx, [r12+420h]
  ... truncated ...
```
