# PublicNetworkListManager::ClientIpHlpEventMgrCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180021360`
- end: `0x18002176d`
- name: `?ClientIpHlpEventMgrCallback@PublicNetworkListManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `1037`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PublicNetworkListManager *Context, PTP_WAIT Wait, __int64 WaitResult)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006770`
- `0x180006810`
- `0x180006ec8`
- `0x180009184`
- `0x180009d08`
- `0x180009d28`
- `0x18000c650`
- `0x1800120d0`
- `0x180020388`
- `0x180021360`
- `0x180029534`
- `0x18002a3e4`
- `0x18002a48c`
- `0x18002b064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002170d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002170d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800216e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800216e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021570`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800215b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021570`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800215b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800215fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800215fb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800216cb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800216cb`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180021438`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180021438`

## string_xrefs

- `0x18002175b`: `onecore\net\netprofiles\service\src\public\lib\networklistmanagerimpl.cpp`

## pseudocode

```c
void __fastcall PublicNetworkListManager::ClientIpHlpEventMgrCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PublicNetworkListManager *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  DWORD v4; // r15d
  char v5; // r14
  PublicNetworkListManager *v6; // rsi
  __int64 v7; // r8
  PVOID *v8; // rcx
  _DWORD *v9; // rdi
  char v10; // r12
  void *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  _QWORD **v14; // rcx
  _QWORD *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int64 v19; // rax
  __int64 v20; // r8
  PVOID *v21; // rcx
  signed int LastError; // eax
  unsigned int v23; // ebx
  unsigned int lpdwindex; // [rsp+20h] [rbp-49h]
  char v25; // [rsp+30h] [rbp-39h]
  _BYTE v26[7]; // [rsp+31h] [rbp-38h] BYREF
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+38h] [rbp-31h] BYREF
  ULONGLONG TickCount64; // [rsp+40h] [rbp-29h]
  PublicNetworkListManager **v29; // [rsp+48h] [rbp-21h]
  char v30; // [rsp+50h] [rbp-19h]
  PublicNetworkListManager *v31; // [rsp+58h] [rbp-11h] BYREF
  HANDLE pHandles; // [rsp+60h] [rbp-9h] BYREF
  DWORD dwindex; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = 0;
  v25 = 0;
  TickCount64 = 0;
  v31 = Context;
  v5 = 0;
  v29 = &v31;
  v30 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  wil::CoInitializeEx(v26, 4, Wait, WaitResult);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  v6 = v31;
  pHandles = (HANDLE)*((_QWORD *)v31 + 96);
  while ( 1 )
  {
    dwindex = -1;
    CoWaitForMultipleHandles(8u, v4, 1u, &pHandles, &dwindex);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, v7, dwindex);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( dwindex )
      break;
    v9 = 0;
    v10 = 0;
    while ( 1 )
    {
      v27 = 0;
      wil::EnterCriticalSection(&v27, (char *)v6 + 712);
      v12 = *((_QWORD *)v6 + 95);
      if ( v12 )
      {
        v13 = *((_QWORD *)v6 + 94);
        v14 = *(_QWORD ***)v13;
        v9 = *(_DWORD **)(*(_QWORD *)v13 + 16LL);
        if ( *v9 == 7 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
          v5 = 1;
        }
        else
        {
          v15 = *v14;
          *((_QWORD *)v6 + 95) = v12 - 1;
          *v14[1] = v15;
          v15[1] = v14[1];
          std::_Deallocate<16>(v14, 0x18u);
        }
      }
      else
      {
        v10 = 1;
        wil::details::ResetEvent(*((wil::details **)v6 + 96), v11);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v27);
      if ( v10 )
        break;
      if ( v5 )
        goto LABEL_47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, v16, (unsigned int)*v9);
      if ( v25 )
      {
        v19 = GetTickCount64() - TickCount64;
        if ( v19 >= 0x1388 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, v20, (unsigned int)v19);
          goto LABEL_42;
        }
        v4 = 5000 - v19;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, v20, (unsigned int)v19, v4);
      }
      else
      {
        v17 = (unsigned int)*v9;
        if ( (unsigned int)(v17 - 5) <= 1 )
        {
          PublicNetworkListManager::TriggerDestEvaluation(v31, v17, v9 + 1);
        }
        else
        {
          v25 = 1;
          TickCount64 = GetTickCount64();
          v4 = 5000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, v18, 5000);
        }
      }
      CoTaskMemFree(v9);
    }
    if ( v5 )
      goto LABEL_47;
  }
  if ( dwindex != 258 )
  {
    LastError = GetLastError();
    v23 = LastError;
    if ( LastError > 0 )
      v23 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v23);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x135D,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\networklistmanagerimpl.cpp",
      (const char *)v23,
      lpdwindex);
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
    WPP_SF_(v8[2], dwindex - 28, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
LABEL_42:
  PublicNetworkListManager::ClientHandleIpHlpEvent((struct _RTL_CRITICAL_SECTION *)v31);
LABEL_47:
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
      WPP_SF_(v21[2], 233, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  }
  if ( v26[0] )
    CoUninitialize();
  SetThreadpoolWait(*((PTP_WAIT *)v31 + 88), *((HANDLE *)v31 + 96), 0);
}

```

## disassembly

```asm
0x180021360  push    rbp
0x180021362  push    rbx
0x180021363  push    rsi
0x180021364  push    rdi
0x180021365  push    r12
0x180021367  push    r13
0x180021369  push    r14
0x18002136b  push    r15
0x18002136d  lea     rbp, [rsp-1Fh]
0x180021372  sub     rsp, 88h
0x180021379  mov     rax, cs:__security_cookie
0x180021380  xor     rax, rsp
0x180021383  mov     [rbp+57h+var_50], rax
0x180021387  xor     r15d, r15d
0x18002138a  mov     [rbp+57h+var_90], r15b
0x18002138e  mov     [rbp+57h+var_80], r15
0x180021392  mov     [rbp+57h+var_68], rdx
0x180021396  xor     r14b, r14b
0x180021399  lea     rax, [rbp+57h+var_68]
0x18002139d  mov     [rbp+57h+var_78], rax
0x1800213a1  mov     [rbp+57h+var_70], 1
0x1800213a5  lea     rbx, WPP_GLOBAL_Control
0x1800213ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213b3  cmp     rcx, rbx
0x1800213b6  jz      short loc_1800213D3
0x1800213b8  test    byte ptr [rcx+1Ch], 8
0x1800213bc  jz      short loc_1800213D3
0x1800213be  mov     edx, 0DEh
0x1800213c3  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800213ca  mov     rcx, [rcx+10h]
0x1800213ce  call    WPP_SF_
0x1800213d3  mov     edx, 4
0x1800213d8  lea     rcx, [rbp+57h+var_8F]
0x1800213dc  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x1800213e1  nop
0x1800213e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213e9  cmp     rcx, rbx
0x1800213ec  jz      short loc_180021409
0x1800213ee  test    byte ptr [rcx+1Ch], 8
0x1800213f2  jz      short loc_180021409
0x1800213f4  mov     edx, 0DFh
0x1800213f9  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180021400  mov     rcx, [rcx+10h]
0x180021404  call    WPP_SF_
0x180021409  mov     rsi, [rbp+57h+var_68]
0x18002140d  mov     rax, [rsi+300h]
0x180021414  mov     [rbp+57h+pHandles], rax
0x180021418  mov     [rbp+57h+dwindex], 0FFFFFFFFh
0x18002141f  mov     edx, r15d; dwTimeout
0x180021422  lea     rax, [rbp+57h+dwindex]
0x180021426  mov     qword ptr [rsp+0C0h+lpdwindex], rax; unsigned int
0x18002142b  lea     r9, [rbp+57h+pHandles]; pHandles
0x18002142f  mov     ecx, 8; dwFlags
0x180021434  lea     r8d, [rcx-7]; cHandles
0x180021438  call    cs:__imp_CoWaitForMultipleHandles
0x18002143e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021445  cmp     rcx, rbx
0x180021448  jz      short loc_180021469
0x18002144a  test    byte ptr [rcx+1Ch], 4
0x18002144e  jz      short loc_180021469
0x180021450  mov     edx, 0E0h
0x180021455  mov     r9d, [rbp+57h+dwindex]
0x180021459  mov     rcx, [rcx+10h]
0x18002145d  call    WPP_SF_L
0x180021462  mov     rcx, cs:WPP_GLOBAL_Control
0x180021469  mov     eax, [rbp+57h+dwindex]
0x18002146c  test    eax, eax
0x18002146e  jnz     loc_180021644
0x180021474  xor     edi, edi
0x180021476  xor     r12b, r12b
0x180021479  mov     [rbp+57h+var_88], 0
0x180021481  lea     rdx, [rsi+2C8h]
0x180021488  lea     rcx, [rbp+57h+var_88]
0x18002148c  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180021491  mov     r8, [rsi+2F8h]
0x180021498  test    r8, r8
0x18002149b  jnz     short loc_1800214AE
0x18002149d  mov     r12b, 1
0x1800214a0  mov     rcx, [rsi+300h]; this
0x1800214a7  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x1800214ac  jmp     short loc_180021514
0x1800214ae  mov     rax, [rsi+2F0h]
0x1800214b5  mov     rcx, [rax]
0x1800214b8  mov     rdi, [rcx+10h]
0x1800214bc  cmp     dword ptr [rdi], 7
0x1800214bf  jnz     short loc_1800214ED
0x1800214c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214c8  cmp     rcx, rbx
0x1800214cb  jz      short loc_1800214E8
0x1800214cd  test    byte ptr [rcx+1Ch], 4
0x1800214d1  jz      short loc_1800214E8
0x1800214d3  mov     edx, 0E1h
0x1800214d8  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800214df  mov     rcx, [rcx+10h]
0x1800214e3  call    WPP_SF_
0x1800214e8  mov     r14b, 1
0x1800214eb  jmp     short loc_180021514
0x1800214ed  mov     rdx, [rcx]
0x1800214f0  lea     rax, [r8-1]
0x1800214f4  mov     [rsi+2F8h], rax
0x1800214fb  mov     rax, [rcx+8]
0x1800214ff  mov     [rax], rdx
0x180021502  mov     rax, [rcx+8]
0x180021506  mov     [rdx+8], rax
0x18002150a  mov     edx, 18h
0x18002150f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021514  mov     bl, r14b
0x180021517  lea     rcx, [rbp+57h+var_88]
0x18002151b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180021520  test    r12b, r12b
0x180021523  jnz     loc_180021606
0x180021529  test    r14b, r14b
0x18002152c  jnz     loc_18002166F
0x180021532  mov     rcx, cs:WPP_GLOBAL_Control
0x180021539  lea     rbx, WPP_GLOBAL_Control
0x180021540  cmp     rcx, rbx
0x180021543  jz      short loc_18002155C
0x180021545  test    byte ptr [rcx+1Ch], 4
0x180021549  jz      short loc_18002155C
0x18002154b  mov     edx, 0E2h
0x180021550  mov     r9d, [rdi]
0x180021553  mov     rcx, [rcx+10h]
0x180021557  call    WPP_SF_L
0x18002155c  cmp     [rbp+57h+var_90], 0
0x180021560  jnz     short loc_1800215B6
0x180021562  mov     edx, [rdi]
0x180021564  lea     eax, [rdx-5]
0x180021567  cmp     eax, 1
0x18002156a  jbe     short loc_1800215A7
0x18002156c  mov     [rbp+57h+var_90], 1
0x180021570  call    cs:__imp_GetTickCount64
0x180021576  mov     [rbp+57h+var_80], rax
0x18002157a  mov     eax, 1388h
0x18002157f  mov     r15d, eax
0x180021582  mov     rcx, cs:WPP_GLOBAL_Control
0x180021589  cmp     rcx, rbx
0x18002158c  jz      short loc_1800215F8
0x18002158e  test    byte ptr [rcx+1Ch], 4
0x180021592  jz      short loc_1800215F8
0x180021594  mov     edx, 0E3h
0x180021599  mov     r9d, eax
0x18002159c  mov     rcx, [rcx+10h]
0x1800215a0  call    WPP_SF_L
0x1800215a5  jmp     short loc_1800215F8
0x1800215a7  lea     r8, [rdi+4]
0x1800215ab  mov     rcx, [rbp+57h+var_68]
0x1800215af  call    ?TriggerDestEvaluation@PublicNetworkListManager@@QEAAJW4CLIENT_DEST_EVENT_TYPE@@AEBU_GUID@@@Z; PublicNetworkListManager::TriggerDestEvaluation(CLIENT_DEST_EVENT_TYPE,_GUID const &)
0x1800215b4  jmp     short loc_1800215F8
0x1800215b6  call    cs:__imp_GetTickCount64
0x1800215bc  sub     rax, [rbp+57h+var_80]
0x1800215c0  mov     ecx, 1388h
0x1800215c5  cmp     rax, rcx
0x1800215c8  jnb     short loc_180021616
0x1800215ca  mov     r15d, ecx
0x1800215cd  sub     r15, rax
0x1800215d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215d7  cmp     rcx, rbx
0x1800215da  jz      short loc_1800215F8
0x1800215dc  test    byte ptr [rcx+1Ch], 4
0x1800215e0  jz      short loc_1800215F8
0x1800215e2  mov     r9d, eax
0x1800215e5  mov     edx, 0E5h
0x1800215ea  mov     [rsp+0C0h+lpdwindex], r15d
0x1800215ef  mov     rcx, [rcx+10h]
0x1800215f3  call    WPP_SF_DD
0x1800215f8  mov     rcx, rdi; pv
0x1800215fb  call    cs:__imp_CoTaskMemFree
0x180021601  jmp     loc_180021479
0x180021606  test    bl, bl
0x180021608  lea     rbx, WPP_GLOBAL_Control
0x18002160f  jnz     short loc_180021676
0x180021611  jmp     loc_180021418
0x180021616  mov     rcx, cs:WPP_GLOBAL_Control
0x18002161d  cmp     rcx, rbx
0x180021620  jz      short loc_180021639
0x180021622  test    byte ptr [rcx+1Ch], 4
0x180021626  jz      short loc_180021639
0x180021628  mov     r9d, eax
0x18002162b  mov     edx, 0E4h
0x180021630  mov     rcx, [rcx+10h]
0x180021634  call    WPP_SF_L
0x180021639  mov     rcx, [rbp+57h+var_68]; this
0x18002163d  call    ?ClientHandleIpHlpEvent@PublicNetworkListManager@@AEAAJXZ; PublicNetworkListManager::ClientHandleIpHlpEvent(void)
0x180021642  jmp     short loc_180021676
0x180021644  cmp     eax, 102h
0x180021649  jnz     loc_18002170D
0x18002164f  cmp     rcx, rbx
0x180021652  jz      short loc_180021639
0x180021654  test    byte ptr [rcx+1Ch], 4
0x180021658  jz      short loc_180021639
0x18002165a  lea     edx, [rax-1Ch]
0x18002165d  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180021664  mov     rcx, [rcx+10h]
0x180021668  call    WPP_SF_
0x18002166d  jmp     short loc_180021639
0x18002166f  lea     rbx, WPP_GLOBAL_Control
0x180021676  mov     rcx, cs:WPP_GLOBAL_Control
0x18002167d  cmp     rcx, rbx
0x180021680  jz      short loc_1800216C5
0x180021682  test    byte ptr [rcx+1Ch], 8
0x180021686  jz      short loc_1800216A4
0x180021688  mov     edx, 0E8h
0x18002168d  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180021694  mov     rcx, [rcx+10h]
0x180021698  call    WPP_SF_
0x18002169d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216a4  cmp     rcx, rbx
0x1800216a7  jz      short loc_1800216C5
0x1800216a9  test    byte ptr [rcx+1Ch], 8
0x1800216ad  jz      short loc_1800216C5
0x1800216af  mov     edx, 0E9h
0x1800216b4  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800216bb  mov     rcx, [rcx+10h]
0x1800216bf  call    WPP_SF_
0x1800216c4  nop
0x1800216c5  cmp     [rbp+57h+var_8F], 0
0x1800216c9  jz      short loc_1800216D2
0x1800216cb  call    cs:__imp_CoUninitialize
0x1800216d1  nop
0x1800216d2  mov     rcx, [rbp+57h+var_68]
0x1800216d6  xor     r8d, r8d; pftTimeout
0x1800216d9  mov     rdx, [rcx+300h]; h
0x1800216e0  mov     rcx, [rcx+2C0h]; pwa
0x1800216e7  call    cs:__imp_SetThreadpoolWait
0x1800216ed  mov     rcx, [rbp+57h+var_50]
0x1800216f1  xor     rcx, rsp; StackCookie
0x1800216f4  call    __security_check_cookie
0x1800216f9  add     rsp, 88h
0x180021700  pop     r15
0x180021702  pop     r14
0x180021704  pop     r13
0x180021706  pop     r12
0x180021708  pop     rdi
0x180021709  pop     rsi
0x18002170a  pop     rbx
0x18002170b  pop     rbp
0x18002170c  retn
0x18002170d  call    cs:__imp_GetLastError
0x180021713  nop
0x180021714  mov     ebx, eax
0x180021716  test    eax, eax
0x180021718  jle     short loc_180021723
0x18002171a  movzx   ebx, ax
0x18002171d  or      ebx, 80070000h
0x180021723  mov     rcx, cs:WPP_GLOBAL_Control
0x18002172a  lea     rax, WPP_GLOBAL_Control
0x180021731  cmp     rcx, rax
0x180021734  jz      short loc_180021754
0x180021736  test    byte ptr [rcx+1Ch], 1
0x18002173a  jz      short loc_180021754
0x18002173c  mov     edx, 0E7h
0x180021741  mov     r9d, ebx
0x180021744  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18002174b  mov     rcx, [rcx+10h]
0x18002174f  call    WPP_SF_d
0x180021754  mov     rcx, [rbp+5Fh]; this
0x180021758  mov     r9d, ebx; char *
0x18002175b  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x180021762  mov     edx, 135Dh; void *
0x180021767  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
