# CDataIntegrityScanTaskHandler::ScanTaskCompleted(_TP_CALLBACK_INSTANCE *)

- ea: `0x18000502c`
- end: `0x1800056ad`
- name: `?ScanTaskCompleted@CDataIntegrityScanTaskHandler@@AEAAXPEAU_TP_CALLBACK_INSTANCE@@@Z`
- size: `1665`
- prototype: `void __fastcall(CDataIntegrityScanTaskHandler *this, struct _TP_CALLBACK_INSTANCE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800056c0`

## callees

- `0x180002e30`
- `0x180003018`
- `0x180003134`
- `0x1800032f8`
- `0x180003660`
- `0x180003a7c`
- `0x18000502c`
- `0x180006470`
- `0x180006498`
- `0x180006688`
- `0x180006874`
- `0x1800068b4`
- `0x18000be0c`
- `0x180039010`

## import_xrefs

- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18000548d`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18000550c`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18000548d`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18000550c`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x180005588`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x180005588`
- `KERNEL32!SetEvent` at `0x180005370`
- `KERNEL32!SetEvent` at `0x180005370`
- `KERNEL32!WaitForSingleObject` at `0x180005422`
- `KERNEL32!WaitForSingleObject` at `0x180005422`
- `KERNEL32!ResetEvent` at `0x18000533d`
- `KERNEL32!ResetEvent` at `0x18000533d`
- `KERNEL32!ReleaseSemaphore` at `0x1800053ec`
- `KERNEL32!ReleaseSemaphore` at `0x1800053ec`
- `KERNEL32!DisassociateCurrentThreadFromCallback` at `0x1800054ca`
- `KERNEL32!DisassociateCurrentThreadFromCallback` at `0x1800054ca`
- `KERNEL32!CloseThreadpoolWait` at `0x1800055ae`
- `KERNEL32!CloseThreadpoolWait` at `0x1800055ae`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800051a4`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800051a4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000511c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000511c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005685`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005685`

## string_xrefs

- `0x18000514d`: `Hr = CoInit.Initialize( COINIT_MULTITHREADED )`
- `0x180005062`: `CDataIntegrityScanTaskHandler::ScanTaskCompleted`
- `0x1800051dc`: `Hr = AtlUnmarshalPtr( m_TaskCompletedWorkContext.TaskHandlerStatusMarshal, IID_ITaskHandlerStatus, &TaskHandlerStatusUnknown )`

## pseudocode

```c
void __fastcall CDataIntegrityScanTaskHandler::ScanTaskCompleted(
        CDataIntegrityScanTaskHandler *this,
        struct _TP_CALLBACK_INSTANCE *a2)
{
  __int64 v4; // r9
  USHORT v5; // dx
  USHORT Length; // cx
  USHORT v7; // ax
  PVOID *v8; // rcx
  HRESULT v9; // eax
  IStream *v10; // rsi
  LPVOID v11; // rdx
  HRESULT v12; // edi
  PVOID *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  PVOID *v16; // rcx
  PVOID *v17; // rcx
  __int64 v18; // r8
  PVOID *v19; // rcx
  __int64 v20; // r9
  unsigned int v21; // eax
  __int64 v22; // [rsp+30h] [rbp-40h] BYREF
  CDataIntegrityScanTaskHandler *v23; // [rsp+38h] [rbp-38h] BYREF
  __int64 v24; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v25[2]; // [rsp+48h] [rbp-28h] BYREF
  const char *v26; // [rsp+58h] [rbp-18h] BYREF
  HRESULT v27; // [rsp+60h] [rbp-10h]
  LPVOID ppv; // [rsp+C8h] [rbp+58h] BYREF

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v4 + 16) = "CDataIntegrityScanTaskHandler::ScanTaskCompleted";
  v26 = "CDataIntegrityScanTaskHandler::ScanTaskCompleted";
  v5 = ++*(_WORD *)(v4 + 8);
  Length = GlobalIndentString.Length;
  v7 = GlobalIndentString.Length;
  if ( v5 < GlobalIndentString.Length )
    v7 = *(_WORD *)(v4 + 8);
  LOWORD(v25[0]) = v7;
  if ( v5 < GlobalIndentString.Length )
    Length = v5;
  WORD1(v25[0]) = Length;
  HIDWORD(v25[0]) = 0;
  v25[1] = off_180047060;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDataIntegrityScanTaskHandler::ScanTaskCompleted");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_(v8[2], 49, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
  v9 = CoInitializeEx(0, 0);
  v27 = v9;
  if ( v9 >= 0 )
  {
    v23 = this;
    v10 = (IStream *)*((_QWORD *)this + 53);
    v11 = 0;
    ppv = 0;
    v12 = -2147024809;
    if ( v10 )
    {
      (*(void (__fastcall **)(IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 40LL))(v10, 0, 0, 0);
      v12 = CoUnmarshalInterface(v10, &IID_ITaskHandlerStatus, &ppv);
      v11 = ppv;
    }
    v27 = v12;
    if ( v12 < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
            (unsigned int)"Hr = AtlUnmarshalPtr( m_TaskCompletedWorkContext.TaskHandlerStatusMarshal, IID_ITaskHandlerSta"
                          "tus, &TaskHandlerStatusUnknown )",
            v12);
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 2u )
          WPP_SF_d(v13[2], 52, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, (unsigned int)v12);
      }
LABEL_111:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
      CoUninitialize();
      goto LABEL_112;
    }
    v14 = *((_QWORD *)this + 53);
    *((_QWORD *)this + 53) = 0;
    v24 = v14;
    v25[0] = &v24;
    ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>(
      &v22,
      v11);
    if ( !*((_DWORD *)this + 60) )
    {
      if ( *((_BYTE *)this + 408) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
        }
        v15 = EnableTaskTrigger(0);
        if ( v15 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
            (unsigned int)"EnableResumeTrigger( TriggerDisable )",
            v15);
        }
      }
    }
    EventWriteTaskComplete((CDataIntegrityScanTaskHandler *)((char *)this + 320));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
    }
    if ( *((_DWORD *)this + 82) == 1 )
    {
      ResetEvent(*((HANDLE *)this + 19));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
      }
    }
    SetEvent(*((HANDLE *)this + 13));
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_BYTE *)this + 216) )
    {
      *((_BYTE *)this + 216) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
      }
      ReleaseSemaphore(*((HANDLE *)this + 28), 1, 0);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 4u )
      WPP_SF_(v16[2], 60, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
    WaitForSingleObject(*((HANDLE *)this + 15), 0xFFFFFFFF);
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 && *((_BYTE *)v17 + 25) >= 4u )
        WPP_SF_q(v17[2], 62, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, *((_QWORD *)this + 31));
    }
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 31), 0);
    CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::Close((char *)this + 248);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        *((_QWORD *)this + 31));
    }
    DisassociateCurrentThreadFromCallback(a2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        *((_QWORD *)this + 33));
    }
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 33), 0);
    CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::Close((char *)this + 264);
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        *((_QWORD *)this + 33));
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v20 = *((_QWORD *)this + 21);
    if ( !v20 )
      goto LABEL_102;
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
      WPP_SF_q(v19[2], 66, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, v20);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 21), 0);
    v20 = *((_QWORD *)this + 21);
    if ( v20 )
    {
      if ( *((_BYTE *)this + 180) && *((_DWORD *)this + 44) )
        goto LABEL_98;
      CloseThreadpoolWait(*((PTP_WAIT *)this + 21));
      *((_QWORD *)this + 21) = 0;
      *((_BYTE *)this + 180) = 0;
    }
    v20 = 0;
LABEL_98:
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    {
LABEL_106:
      v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v22 + 32LL))(
              v22,
              *((unsigned int *)this + 103),
              v18,
              v20);
      v27 = v21;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, v21);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
      CAutoTearDown__lambda_aa2976408c995a0b89773c80cf35e80b___::_CAutoTearDown__lambda_aa2976408c995a0b89773c80cf35e80b___(v25);
      goto LABEL_111;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, v20);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_102:
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
      WPP_SF_(v19[2], 68, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
    goto LABEL_106;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
      (unsigned int)"Hr = CoInit.Initialize( COINIT_MULTITHREADED )",
      v9);
  }
LABEL_112:
  CHResultImp::~CHResultImp((CHResultImp *)&v26);
}

```

## disassembly

```asm
0x18000502c  mov     [rsp-38h+arg_0], rbx
0x180005031  push    rbp
0x180005032  push    rsi
0x180005033  push    rdi
0x180005034  push    r12
0x180005036  push    r13
0x180005038  push    r14
0x18000503a  push    r15
0x18000503c  mov     rbp, rsp
0x18000503f  sub     rsp, 70h
0x180005043  mov     r14, rdx
0x180005046  mov     rbx, rcx
0x180005049  mov     r8d, cs:_tls_index
0x180005050  mov     rax, gs:58h
0x180005059  mov     r9, [rax+r8*8]
0x18000505d  mov     eax, 10h
0x180005062  lea     r8, aCdataintegrity_2; "CDataIntegrityScanTaskHandler::ScanTask"...
0x180005069  mov     [rax+r9], r8
0x18000506d  mov     [rbp+var_18], r8
0x180005071  mov     edx, 8
0x180005076  mov     r15d, 1
0x18000507c  add     [rdx+r9], r15w
0x180005081  movzx   edx, word ptr [rdx+r9]
0x180005086  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18000508d  movzx   eax, cx
0x180005090  cmp     dx, cx
0x180005093  cmovb   ax, dx
0x180005097  mov     word ptr [rbp+var_28], ax
0x18000509b  cmovb   cx, dx
0x18000509f  mov     word ptr [rbp+var_28+2], cx
0x1800050a3  xor     eax, eax
0x1800050a5  mov     dword ptr [rbp+var_28+4], eax
0x1800050a8  mov     rax, cs:off_180047060; "                                       "...
0x1800050af  mov     [rbp+var_20], rax
0x1800050b3  lea     r12, WPP_GLOBAL_Control
0x1800050ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050c1  cmp     rcx, r12
0x1800050c4  jz      short loc_1800050EF
0x1800050c6  test    [rcx+1Ch], r15b
0x1800050ca  jz      short loc_1800050EF
0x1800050cc  cmp     byte ptr [rcx+19h], 5
0x1800050d0  jb      short loc_1800050EF
0x1800050d2  lea     edx, [r15+0Ch]
0x1800050d6  mov     [rsp+70h+var_50], r8; __int64
0x1800050db  lea     r9, [rbp+var_28]
0x1800050df  mov     rcx, [rcx+10h]; LoggerHandle
0x1800050e3  call    WPP_SF_aZs
0x1800050e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050ef  lea     r13, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x1800050f6  cmp     rcx, r12
0x1800050f9  jz      short loc_180005118
0x1800050fb  test    [rcx+1Ch], r15b
0x1800050ff  jz      short loc_180005118
0x180005101  cmp     byte ptr [rcx+19h], 4
0x180005105  jb      short loc_180005118
0x180005107  mov     edx, 31h ; '1'
0x18000510c  mov     r8, r13
0x18000510f  mov     rcx, [rcx+10h]
0x180005113  call    WPP_SF_
0x180005118  xor     edx, edx; dwCoInit
0x18000511a  xor     ecx, ecx; pvReserved
0x18000511c  call    cs:__imp_CoInitializeEx
0x180005122  mov     [rbp+arg_10], eax
0x180005125  mov     [rbp+var_10], eax
0x180005128  test    eax, eax
0x18000512a  jns     short loc_180005166
0x18000512c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005133  cmp     rcx, r12
0x180005136  jz      short loc_180005161
0x180005138  test    [rcx+1Ch], r15b
0x18000513c  jz      short loc_180005161
0x18000513e  cmp     byte ptr [rcx+19h], 2
0x180005142  jb      short loc_180005161
0x180005144  mov     edx, 32h ; '2'
0x180005149  mov     dword ptr [rsp+70h+var_50], eax
0x18000514d  lea     r9, aHrCoinitInitia; "Hr = CoInit.Initialize( COINIT_MULTITHR"...
0x180005154  mov     r8, r13
0x180005157  mov     rcx, [rcx+10h]
0x18000515b  call    WPP_SF_sd
0x180005160  nop
0x180005161  jmp     loc_18000568C
0x180005166  mov     [rbp+var_38], rbx
0x18000516a  mov     rsi, [rbx+1A8h]
0x180005171  xor     edx, edx
0x180005173  mov     [rbp+ppv], rdx
0x180005177  mov     edi, 80070057h
0x18000517c  test    rsi, rsi
0x18000517f  jz      short loc_1800051B0
0x180005181  mov     rax, [rsi]
0x180005184  xor     r9d, r9d
0x180005187  xor     r8d, r8d
0x18000518a  mov     rcx, rsi
0x18000518d  mov     rax, [rax+28h]
0x180005191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005196  lea     r8, [rbp+ppv]; ppv
0x18000519a  lea     rdx, IID_ITaskHandlerStatus; riid
0x1800051a1  mov     rcx, rsi; pStm
0x1800051a4  call    cs:__imp_CoUnmarshalInterface
0x1800051aa  mov     edi, eax
0x1800051ac  mov     rdx, [rbp+ppv]
0x1800051b0  mov     [rbp+var_10], edi
0x1800051b3  xor     esi, esi
0x1800051b5  test    edi, edi
0x1800051b7  jns     short loc_18000522C
0x1800051b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051c0  cmp     rcx, r12
0x1800051c3  jz      loc_180005671
0x1800051c9  test    [rcx+1Ch], r15b
0x1800051cd  jz      short loc_1800051F6
0x1800051cf  cmp     byte ptr [rcx+19h], 2
0x1800051d3  jb      short loc_1800051F6
0x1800051d5  lea     edx, [rsi+33h]
0x1800051d8  mov     dword ptr [rsp+70h+var_50], edi
0x1800051dc  lea     r9, aHrAtlunmarshal; "Hr = AtlUnmarshalPtr( m_TaskCompletedWo"...
0x1800051e3  mov     r8, r13
0x1800051e6  mov     rcx, [rcx+10h]
0x1800051ea  call    WPP_SF_sd
0x1800051ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051f6  cmp     rcx, r12
0x1800051f9  jz      loc_180005671
0x1800051ff  test    [rcx+1Ch], r15b
0x180005203  jz      loc_180005671
0x180005209  cmp     byte ptr [rcx+19h], 2
0x18000520d  jb      loc_180005671
0x180005213  mov     edx, 34h ; '4'
0x180005218  mov     r9d, edi
0x18000521b  mov     r8, r13
0x18000521e  mov     rcx, [rcx+10h]
0x180005222  call    WPP_SF_d
0x180005227  jmp     loc_180005671
0x18000522c  mov     rax, [rbx+1A8h]
0x180005233  mov     [rbx+1A8h], rsi
0x18000523a  mov     [rbp+var_30], rax
0x18000523e  lea     rax, [rbp+var_30]
0x180005242  mov     [rbp+var_28], rax
0x180005246  lea     rcx, [rbp+var_40]
0x18000524a  call    ??0?$CComQIPtr@UITaskHandlerStatus@@$1?_GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>(IUnknown *)
0x18000524f  nop
0x180005250  cmp     [rbx+0F0h], esi
0x180005256  jnz     loc_1800052F8
0x18000525c  cmp     [rbx+198h], sil
0x180005263  jnz     short loc_1800052CF
0x180005265  mov     rcx, cs:WPP_GLOBAL_Control
0x18000526c  cmp     rcx, r12
0x18000526f  jz      short loc_18000528E
0x180005271  test    [rcx+1Ch], r15b
0x180005275  jz      short loc_18000528E
0x180005277  cmp     byte ptr [rcx+19h], 4
0x18000527b  jb      short loc_18000528E
0x18000527d  mov     edx, 35h ; '5'
0x180005282  mov     r8, r13
0x180005285  mov     rcx, [rcx+10h]
0x180005289  call    WPP_SF_
0x18000528e  xor     ecx, ecx
0x180005290  call    ?EnableTaskTrigger@@YAJW4TaskTriggerOption@@PEBG@Z; EnableTaskTrigger(TaskTriggerOption,ushort const *)
0x180005295  test    eax, eax
0x180005297  jns     short loc_1800052F8
0x180005299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052a0  cmp     rcx, r12
0x1800052a3  jz      short loc_1800052F8
0x1800052a5  test    [rcx+1Ch], r15b
0x1800052a9  jz      short loc_1800052F8
0x1800052ab  cmp     byte ptr [rcx+19h], 2
0x1800052af  jb      short loc_1800052F8
0x1800052b1  mov     edx, 36h ; '6'
0x1800052b6  mov     dword ptr [rsp+70h+var_50], eax
0x1800052ba  lea     r9, aEnableresumetr; "EnableResumeTrigger( TriggerDisable )"
0x1800052c1  mov     r8, r13
0x1800052c4  mov     rcx, [rcx+10h]
0x1800052c8  call    WPP_SF_sd
0x1800052cd  jmp     short loc_1800052F8
0x1800052cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052d6  cmp     rcx, r12
0x1800052d9  jz      short loc_1800052F8
0x1800052db  test    [rcx+1Ch], r15b
0x1800052df  jz      short loc_1800052F8
0x1800052e1  cmp     byte ptr [rcx+19h], 4
0x1800052e5  jb      short loc_1800052F8
0x1800052e7  mov     edx, 37h ; '7'
0x1800052ec  mov     r8, r13
0x1800052ef  mov     rcx, [rcx+10h]
0x1800052f3  call    WPP_SF_
0x1800052f8  lea     rcx, [rbx+140h]; struct _SCRUB_ENVIRONMENT *
0x1800052ff  call    ?EventWriteTaskComplete@@YAXPEAU_SCRUB_ENVIRONMENT@@@Z; EventWriteTaskComplete(_SCRUB_ENVIRONMENT *)
0x180005304  mov     rcx, cs:WPP_GLOBAL_Control
0x18000530b  cmp     rcx, r12
0x18000530e  jz      short loc_18000532D
0x180005310  test    [rcx+1Ch], r15b
0x180005314  jz      short loc_18000532D
0x180005316  cmp     byte ptr [rcx+19h], 4
0x18000531a  jb      short loc_18000532D
0x18000531c  mov     edx, 38h ; '8'
0x180005321  mov     r8, r13
0x180005324  mov     rcx, [rcx+10h]
0x180005328  call    WPP_SF_
0x18000532d  cmp     [rbx+148h], r15d
0x180005334  jnz     short loc_18000536C
0x180005336  mov     rcx, [rbx+98h]; hEvent
0x18000533d  call    cs:__imp_ResetEvent
0x180005343  mov     rcx, cs:WPP_GLOBAL_Control
0x18000534a  cmp     rcx, r12
0x18000534d  jz      short loc_18000536C
0x18000534f  test    [rcx+1Ch], r15b
0x180005353  jz      short loc_18000536C
0x180005355  cmp     byte ptr [rcx+19h], 4
0x180005359  jb      short loc_18000536C
0x18000535b  mov     edx, 39h ; '9'
0x180005360  mov     r8, r13
0x180005363  mov     rcx, [rcx+10h]
0x180005367  call    WPP_SF_
0x18000536c  mov     rcx, [rbx+68h]; hEvent
0x180005370  call    cs:__imp_SetEvent
0x180005376  mov     rcx, cs:WPP_GLOBAL_Control
0x18000537d  cmp     rcx, r12
0x180005380  jz      short loc_1800053A6
0x180005382  test    [rcx+1Ch], r15b
0x180005386  jz      short loc_1800053A6
0x180005388  cmp     byte ptr [rcx+19h], 4
0x18000538c  jb      short loc_1800053A6
0x18000538e  mov     edx, 3Ah ; ':'
0x180005393  mov     r8, r13
0x180005396  mov     rcx, [rcx+10h]
0x18000539a  call    WPP_SF_
0x18000539f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053a6  cmp     [rbx+0D8h], sil
0x1800053ad  jz      short loc_1800053F9
0x1800053af  mov     [rbx+0D8h], sil
0x1800053b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053bd  cmp     rcx, r12
0x1800053c0  jz      short loc_1800053DF
0x1800053c2  test    [rcx+1Ch], r15b
0x1800053c6  jz      short loc_1800053DF
0x1800053c8  cmp     byte ptr [rcx+19h], 4
0x1800053cc  jb      short loc_1800053DF
0x1800053ce  mov     edx, 3Bh ; ';'
0x1800053d3  mov     r8, r13
0x1800053d6  mov     rcx, [rcx+10h]
0x1800053da  call    WPP_SF_
0x1800053df  xor     r8d, r8d; lpPreviousCount
0x1800053e2  mov     edx, r15d; lReleaseCount
0x1800053e5  mov     rcx, [rbx+0E0h]; hSemaphore
0x1800053ec  call    cs:__imp_ReleaseSemaphore
0x1800053f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053f9  cmp     rcx, r12
0x1800053fc  jz      short loc_18000541B
0x1800053fe  test    [rcx+1Ch], r15b
0x180005402  jz      short loc_18000541B
0x180005404  cmp     byte ptr [rcx+19h], 4
0x180005408  jb      short loc_18000541B
0x18000540a  mov     edx, 3Ch ; '<'
0x18000540f  mov     r8, r13
0x180005412  mov     rcx, [rcx+10h]
0x180005416  call    WPP_SF_
0x18000541b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000541e  mov     rcx, [rbx+78h]; hHandle
0x180005422  call    cs:__imp_WaitForSingleObject
0x180005428  mov     rcx, cs:WPP_GLOBAL_Control
0x18000542f  cmp     rcx, r12
0x180005432  jz      short loc_180005481
0x180005434  test    [rcx+1Ch], r15b
0x180005438  jz      short loc_180005458
0x18000543a  cmp     byte ptr [rcx+19h], 4
0x18000543e  jb      short loc_180005458
0x180005440  mov     edx, 3Dh ; '='
0x180005445  mov     r8, r13
0x180005448  mov     rcx, [rcx+10h]
0x18000544c  call    WPP_SF_
0x180005451  mov     rcx, cs:WPP_GLOBAL_Control
0x180005458  cmp     rcx, r12
0x18000545b  jz      short loc_180005481
0x18000545d  test    [rcx+1Ch], r15b
0x180005461  jz      short loc_180005481
0x180005463  cmp     byte ptr [rcx+19h], 4
0x180005467  jb      short loc_180005481
0x180005469  mov     edx, 3Eh ; '>'
0x18000546e  mov     r9, [rbx+0F8h]
0x180005475  mov     r8, r13
0x180005478  mov     rcx, [rcx+10h]
0x18000547c  call    WPP_SF_q
0x180005481  lea     rdi, [rbx+0F8h]
0x180005488  xor     edx, edx; fCancelPendingCallbacks
0x18000548a  mov     rcx, [rdi]; pwk
0x18000548d  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180005493  mov     rcx, rdi
0x180005496  call    ?Close@?$CHandleT@PEAU_TP_WORK@@UThreadPoolWorkTrait@@@@QEAAXXZ; CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::Close(void)
0x18000549b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054a2  cmp     rcx, r12
0x1800054a5  jz      short loc_1800054C7
0x1800054a7  test    [rcx+1Ch], r15b
0x1800054ab  jz      short loc_1800054C7
0x1800054ad  cmp     byte ptr [rcx+19h], 4
0x1800054b1  jb      short loc_1800054C7
0x1800054b3  mov     edx, 3Fh ; '?'
0x1800054b8  mov     r9, [rdi]
0x1800054bb  mov     r8, r13
0x1800054be  mov     rcx, [rcx+10h]
0x1800054c2  call    WPP_SF_q
0x1800054c7  mov     rcx, r14; pci
0x1800054ca  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x1800054d0  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
