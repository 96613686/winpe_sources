# DdmNotificationHandler::DriverNotificationHandler(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180047350`
- end: `0x180047e8e`
- name: `?DriverNotificationHandler@DdmNotificationHandler@@CAKPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `2878`
- prototype: `unsigned int __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007c0c`
- `0x180007d00`
- `0x180007e8c`
- `0x180027c90`
- `0x1800281a0`
- `0x1800283c0`
- `0x18003c4a0`
- `0x18003c620`
- `0x18003cd74`
- `0x18003d100`
- `0x18003d278`
- `0x18003d68c`
- `0x18003df58`
- `0x180047350`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180092b90`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004786e`
- `KERNEL32!LocalFree` at `0x18004786e`
- `KERNEL32!LeaveCriticalSection` at `0x1800477c1`
- `KERNEL32!LeaveCriticalSection` at `0x180047882`
- `KERNEL32!LeaveCriticalSection` at `0x180047b7f`
- `KERNEL32!LeaveCriticalSection` at `0x180047bc2`
- `KERNEL32!LeaveCriticalSection` at `0x180047caa`
- `KERNEL32!LeaveCriticalSection` at `0x180047dbd`
- `KERNEL32!LeaveCriticalSection` at `0x1800477c1`
- `KERNEL32!LeaveCriticalSection` at `0x180047882`
- `KERNEL32!LeaveCriticalSection` at `0x180047b7f`
- `KERNEL32!LeaveCriticalSection` at `0x180047bc2`
- `KERNEL32!LeaveCriticalSection` at `0x180047caa`
- `KERNEL32!LeaveCriticalSection` at `0x180047dbd`
- `KERNEL32!EnterCriticalSection` at `0x18004760a`
- `KERNEL32!EnterCriticalSection` at `0x18004765f`
- `KERNEL32!EnterCriticalSection` at `0x1800476a4`
- `KERNEL32!EnterCriticalSection` at `0x1800476f1`
- `KERNEL32!EnterCriticalSection` at `0x1800478aa`
- `KERNEL32!EnterCriticalSection` at `0x180047916`
- `KERNEL32!EnterCriticalSection` at `0x180047a77`
- `KERNEL32!EnterCriticalSection` at `0x180047c86`
- `KERNEL32!EnterCriticalSection` at `0x180047d9c`
- `KERNEL32!EnterCriticalSection` at `0x18004760a`
- `KERNEL32!EnterCriticalSection` at `0x18004765f`
- `KERNEL32!EnterCriticalSection` at `0x1800476a4`
- `KERNEL32!EnterCriticalSection` at `0x1800476f1`
- `KERNEL32!EnterCriticalSection` at `0x1800478aa`
- `KERNEL32!EnterCriticalSection` at `0x180047916`
- `KERNEL32!EnterCriticalSection` at `0x180047a77`
- `KERNEL32!EnterCriticalSection` at `0x180047c86`
- `KERNEL32!EnterCriticalSection` at `0x180047d9c`
- `KERNEL32!HeapFree` at `0x180047e0e`
- `KERNEL32!HeapFree` at `0x180047e26`
- `KERNEL32!HeapFree` at `0x180047e0e`
- `KERNEL32!HeapFree` at `0x180047e26`

## string_xrefs

- `0x18004773a`: `%s:MarkPortConnectComplete failed: %d`
- `0x180047d02`: `%s:MarkPortConnectComplete failed: %d`
- `0x1800479c6`: `Failed to create device object: %d`
- `0x180047b2d`: `DdmAcceptIncomingCall failed for port: %ld`
- `0x180047972`: `DdmAnswerIncomingCall failed for port: %ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdmNotificationHandler::DriverNotificationHandler(
        struct _TP_CALLBACK_INSTANCE *a1,
        unsigned int *a2,
        struct _TP_WORK *a3)
{
  unsigned int v4; // r14d
  __int64 *v5; // rbx
  __int64 v6; // r8
  __int64 v7; // rax
  unsigned int i; // edi
  __int64 *v9; // r13
  __int64 v10; // rax
  struct DdmDeviceTable *v11; // rax
  struct DdmDeviceTable *v12; // rax
  struct DdmDeviceTable *v13; // rax
  struct DdmDeviceTable *v14; // rax
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rax
  DdmDeviceTable *v18; // rax
  DWORD v19; // ecx
  struct DdmDeviceTable *v20; // rax
  __int64 v21; // rdx
  struct DdmDeviceTable *v22; // rax
  unsigned int v23; // eax
  __int64 v24; // r8
  __int64 v25; // rax
  DdmDeviceTable *v26; // rax
  DdmDeviceTable *v27; // rax
  __int64 *v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rdx
  DdmDeviceTable *v31; // rax
  struct DdmDeviceTable *Instance; // rax
  __int64 v33; // rdx
  DdmDeviceTable *v34; // rax
  DWORD v35; // ecx
  struct DdmDeviceTable *v36; // rax
  struct DdmDeviceTable *v37; // rax
  __int64 v39; // [rsp+28h] [rbp-D8h]
  __int64 *v40; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v41[3]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v42; // [rsp+50h] [rbp-B0h]
  _QWORD v43[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v44[6]; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+7Ch] [rbp-84h]
  __int128 v46; // [rsp+1C40h] [rbp+1B40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+1C50h] [rbp+1B50h] BYREF
  const wchar_t *v48; // [rsp+1C60h] [rbp+1B60h]
  int v49; // [rsp+1C68h] [rbp+1B68h]
  int v50; // [rsp+1C6Ch] [rbp+1B6Ch]
  int v51; // [rsp+1C70h] [rbp+1B70h] BYREF
  __int128 v52; // [rsp+1C74h] [rbp+1B74h]
  __int128 v53; // [rsp+1C84h] [rbp+1B84h]
  int v54; // [rsp+1C94h] [rbp+1B94h]
  int v55; // [rsp+1CA0h] [rbp+1BA0h] BYREF
  _BYTE v56[2044]; // [rsp+1CA4h] [rbp+1BA4h] BYREF

  v4 = 0;
  v5 = 0;
  v40 = 0;
  LODWORD(v41[0]) = 0;
  v55 = 0;
  memset_0(v56, 0, sizeof(v56));
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v46 = 0;
  if ( !a2 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( aInvalidParamet[v7] );
      v48 = L"Invalid Parameter";
      v49 = 2 * v7 + 2;
      v50 = 0;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v6,
        2u,
        &v47);
    }
    goto LABEL_92;
  }
  msgdbgprint(1, 2, a2);
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v55) = 0;
    LOWORD(v51) = 0;
    ConvertPortNoToString(&v51, a2[2]);
    FormatRRASErrorString(
      &v55,
      L"Processing Message (Id:%d) for hPort=%I64u, hCall=%I64u",
      *a2,
      *((_QWORD *)a2 + 1),
      *((_QWORD *)a2 + 2));
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v55,
        (unsigned int)&v46,
        0,
        (__int64)&v51);
  }
  if ( *a2 == 1 )
  {
    Instance = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::FindDevice(Instance, *((_QWORD *)a2 + 1), &v40);
    v5 = v40;
    if ( v40 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v40 + 2));
      v4 = (*(__int64 (__fastcall **)(__int64 *))(*v5 + 448))(v5);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 2));
      if ( v4 )
      {
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v55) = 0;
          LOWORD(v51) = 0;
          v33 = v5 ? *((unsigned int *)v5 + 24) : 0xFFFFFFFFLL;
          ConvertPortNoToString(&v51, v33);
          FormatRRASErrorString(
            &v55,
            L"%s:MarkPortConnectComplete failed: %d",
            L"DdmNotificationHandler::DriverNotificationHandler",
            v4);
          if ( (byte_1800CF404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v55,
              (unsigned int)&v46,
              0,
              (__int64)&v51);
        }
      }
      else
      {
        v34 = DdmDeviceTable::GetInstance(0x11u);
        DdmDeviceTable::UpdateDeviceBundleMap(v34);
        ExecuteComponentTest(v35);
        if ( *((_WORD *)v5 + 68) == 15 )
        {
          v36 = DdmDeviceTable::GetInstance(0x11u);
          (**((void (__fastcall ***)(__int64))v36 + 20))((__int64)v36 + 160);
          LODWORD(v41[0]) = 1;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 2));
        (*(void (__fastcall **)(__int64 *))(*v5 + 344))(v5);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 2));
        if ( LODWORD(v41[0]) )
        {
          v37 = DdmDeviceTable::GetInstance(0x11u);
          (*(void (__fastcall **)(__int64))(*((_QWORD *)v37 + 20) + 16LL))((__int64)v37 + 160);
        }
      }
      goto LABEL_40;
    }
    goto LABEL_73;
  }
  if ( *a2 == 2 )
  {
    v22 = DdmDeviceTable::GetInstance(0x11u);
    v23 = DdmDeviceTable::CreateNewDevice(v22, a2[6], &v40, 0);
    v4 = v23;
    v5 = v40;
    if ( !v40 )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v55) = 0;
        FormatRRASErrorString(&v55, L"Failed to create device object: %d", v23);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)&v56[2 * v25 - 4] );
          v48 = (const wchar_t *)&v55;
          v49 = 2 * v25 + 2;
          v50 = 0;
          McGenEventWrite_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasDdmTraceError,
            v24,
            2u,
            &v47);
        }
      }
      goto LABEL_40;
    }
    v26 = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::AddDevice(v26);
    v27 = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::AddDeviceCallMap(v27);
    v28 = v40;
    EnterCriticalSection((LPCRITICAL_SECTION)(v40 + 2));
    (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v28 + 248))(v28, a2[7], *((_QWORD *)a2 + 4));
    v29 = *v28;
    *(_OWORD *)&v41[1] = *(_OWORD *)(a2 + 15);
    v42 = a2[19];
    v47 = *(struct _EVENT_DATA_DESCRIPTOR *)(a2 + 10);
    LODWORD(v48) = a2[14];
    (*(void (__fastcall **)(__int64 *, struct _EVENT_DATA_DESCRIPTOR *, _QWORD *))(v29 + 528))(v28, &v47, &v41[1]);
    v4 = DdmAcceptIncomingCall(&v40, a2[4]);
    v5 = v40;
    if ( !v4 )
    {
      (*(void (__fastcall **)(__int64 *))(*v40 + 352))(v40);
      goto LABEL_39;
    }
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v55) = 0;
      LOWORD(v51) = 0;
      if ( v40 )
        v30 = *((unsigned int *)v40 + 24);
      else
        v30 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v51, v30);
      FormatRRASErrorString(&v55, L"DdmAcceptIncomingCall failed for port: %ld", v5[12]);
LABEL_67:
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v55,
          (unsigned int)&v46,
          0,
          (__int64)&v51);
    }
  }
  else
  {
    if ( *a2 != 3 )
    {
      if ( *a2 == 4 )
      {
        v14 = DdmDeviceTable::GetInstance(0x11u);
        DdmDeviceTable::FindDevice(v14, *((_QWORD *)a2 + 1), &v40);
        v5 = v40;
        if ( v40 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v40 + 2));
          v15 = (*(__int64 (__fastcall **)(__int64 *))(*v5 + 448))(v5);
          v4 = v15;
          if ( v15 )
          {
            if ( (byte_1800CF404 & 8) != 0 )
            {
              LOWORD(v55) = 0;
              FormatRRASErrorString(
                &v55,
                L"%s:MarkPortConnectComplete failed: %d",
                L"DdmNotificationHandler::DriverNotificationHandler",
                v15);
              if ( (byte_1800CF404 & 8) != 0 )
              {
                v17 = -1;
                do
                  ++v17;
                while ( *(_WORD *)&v56[2 * v17 - 4] );
                v48 = (const wchar_t *)&v55;
                v49 = 2 * v17 + 2;
                v50 = 0;
                McGenEventWrite_EventWriteTransfer(
                  (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (const EVENT_DESCRIPTOR *)RasDdmTraceError,
                  v16,
                  2u,
                  &v47);
              }
            }
            (*(void (__fastcall **)(__int64 *))(*v5 + 176))(v5);
          }
          else
          {
            LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 2));
            v18 = DdmDeviceTable::GetInstance(0x11u);
            DdmDeviceTable::UpdateDeviceBundleMap(v18);
            ExecuteComponentTest(v19);
            EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 2));
            v4 = (*(__int64 (__fastcall **)(__int64 *))(*v5 + 88))(v5);
            if ( !v4 )
              v4 = (*(__int64 (__fastcall **)(__int64 *))(*v5 + 96))(v5);
          }
          goto LABEL_39;
        }
        goto LABEL_73;
      }
      if ( *a2 == 5 )
        goto LABEL_27;
      if ( *a2 == 6 )
      {
        v13 = DdmDeviceTable::GetInstance(0x11u);
        DdmDeviceTable::FindDevice(v13, *((_QWORD *)a2 + 1), &v40);
        v5 = v40;
        if ( v40 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v40 + 2));
          (*(void (__fastcall **)(__int64 *))(*v5 + 360))(v5);
          goto LABEL_39;
        }
        goto LABEL_73;
      }
      if ( *a2 == 7 )
      {
LABEL_27:
        v12 = DdmDeviceTable::GetInstance(0x11u);
        DdmDeviceTable::FindDevice(v12, *((_QWORD *)a2 + 1), &v40);
        v5 = v40;
        if ( v40 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v40 + 2));
          (*(void (__fastcall **)(__int64 *))(*v5 + 104))(v5);
          goto LABEL_39;
        }
      }
      else
      {
        if ( *a2 != 8 )
        {
          if ( *a2 == 9 )
          {
            for ( i = 0; i < a2[6]; ++i )
            {
              v43[0] = 14;
              v43[1] = 0;
              memset_0(v44, 0, 0x1BD0u);
              v44[4] = a2[2 * i + 7];
              v45 = (a2[2 * i + 8] != 1) + 1;
              v9 = qword_1800CE4C8;
              v10 = 3;
              v41[0] = 3;
              do
              {
                if ( *((_DWORD *)v9 - 11) == 1 )
                {
                  ((void (__fastcall *)(_QWORD *))*v9)(v43);
                  v10 = v41[0];
                }
                v9 += 10;
                v41[0] = --v10;
              }
              while ( v10 );
            }
          }
          goto LABEL_40;
        }
        v11 = DdmDeviceTable::GetInstance(0x11u);
        DdmDeviceTable::FindDevice(v11, *((_QWORD *)a2 + 1), &v40);
        v5 = v40;
        if ( v40 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v40 + 2));
          (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v5 + 120))(v5, *((_QWORD *)a2 + 4), a2[6]);
LABEL_39:
          LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 2));
          goto LABEL_40;
        }
      }
LABEL_73:
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v55) = 0;
        LOWORD(v51) = 0;
        ConvertPortNoToString(&v51, a2[2]);
        FormatRRASErrorString(&v55, L"No device found for port: %ld", *((_QWORD *)a2 + 1));
        if ( (byte_1800CF404 & 0x10) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)&v55,
            (unsigned int)&v46,
            0,
            (__int64)&v51);
      }
      v4 = 1168;
      goto LABEL_40;
    }
    v20 = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::FindDevice(v20, *((_QWORD *)a2 + 1), &v40);
    v5 = v40;
    if ( !v40 )
      goto LABEL_73;
    EnterCriticalSection((LPCRITICAL_SECTION)(v40 + 2));
    v4 = DdmAnswerIncomingCall(&v40);
    v5 = v40;
    if ( !v4 )
      goto LABEL_39;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v55) = 0;
      LOWORD(v51) = 0;
      if ( v40 )
        v21 = *((unsigned int *)v40 + 24);
      else
        v21 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v51, v21);
      FormatRRASErrorString(&v55, L"DdmAnswerIncomingCall failed for port: %ld", v5[12]);
      goto LABEL_67;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 2));
  v31 = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::RemoveDevice(v31);
  v5 = v40;
LABEL_40:
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v55) = 0;
    LOWORD(v51) = 0;
    ConvertPortNoToString(&v51, a2[2]);
    LODWORD(v39) = v4;
    FormatRRASErrorString(
      &v55,
      L"Processing Done for Message (Id:%d) for hPort=%I64u, hCall=%I64u. Error: %d",
      *a2,
      *((_QWORD *)a2 + 1),
      *((_QWORD *)a2 + 2),
      v39);
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v55,
        (unsigned int)&v46,
        0,
        (__int64)&v51);
  }
  if ( *a2 == 8 )
  {
    if ( a2[6] )
      LocalFree(*((HLOCAL *)a2 + 4));
  }
  else if ( *a2 == 2 && a2[7] )
  {
    HeapFree(hHeap, 0, *((LPVOID *)a2 + 4));
  }
  HeapFree(hHeap, 0, a2);
LABEL_92:
  if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64 *, __int64))*v40)(v40, 1);
  return v4;
}

```

## disassembly

```asm
0x180047350  mov     rax, rsp
0x180047353  mov     [rax+8], rbx
0x180047357  mov     [rax+18h], rsi
0x18004735b  mov     [rax+20h], rdi
0x18004735f  push    rbp
0x180047360  push    r12
0x180047362  push    r13
0x180047364  push    r14
0x180047366  push    r15
0x180047368  lea     rbp, [rax-23D8h]
0x18004736f  mov     eax, 24B0h
0x180047374  call    _alloca_probe
0x180047379  sub     rsp, rax
0x18004737c  mov     rax, cs:__security_cookie
0x180047383  xor     rax, rsp
0x180047386  mov     [rbp+23D0h+var_30], rax
0x18004738d  mov     rsi, rdx
0x180047390  xor     r13d, r13d
0x180047393  mov     r14d, r13d
0x180047396  mov     ebx, r13d
0x180047399  mov     [rsp+24D0h+var_24A0], rbx
0x18004739e  mov     dword ptr [rsp+24D0h+var_2498], r13d
0x1800473a3  mov     [rbp+23D0h+var_830], r13d
0x1800473aa  xor     edx, edx; Val
0x1800473ac  mov     r8d, 7FCh; Size
0x1800473b2  lea     rcx, [rbp+23D0h+var_82C]; void *
0x1800473b9  call    memset_0
0x1800473be  mov     [rbp+23D0h+var_860], r13d
0x1800473c5  xorps   xmm0, xmm0
0x1800473c8  xor     eax, eax
0x1800473ca  movups  [rbp+23D0h+var_85C], xmm0
0x1800473d1  movups  [rbp+23D0h+var_84C], xmm0
0x1800473d8  mov     [rbp+23D0h+var_83C], eax
0x1800473de  movups  [rbp+23D0h+var_890], xmm0
0x1800473e5  test    rsi, rsi
0x1800473e8  jnz     short loc_180047454
0x1800473ea  mov     r15b, 10h
0x1800473ed  test    cs:byte_1800CF404, r15b
0x1800473f4  jz      loc_180047E33
0x1800473fa  lea     rcx, aInvalidParamet; "Invalid Parameter"
0x180047401  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047405  inc     rax
0x180047408  cmp     [rcx+rax*2], r13w
0x18004740d  jnz     short loc_180047405
0x18004740f  lea     eax, ds:2[rax*2]
0x180047416  mov     [rbp+23D0h+var_870], rcx
0x18004741d  mov     [rbp+23D0h+var_868], eax
0x180047423  mov     [rbp+23D0h+var_864], r13d
0x18004742a  lea     rax, [rbp+23D0h+var_880]
0x180047431  mov     [rsp+24D0h+var_24B0], rax
0x180047436  mov     r9d, 2
0x18004743c  lea     rdx, RasDdmTraceInfo
0x180047443  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004744a  call    McGenEventWrite_EventWriteTransfer
0x18004744f  jmp     loc_180047E33
0x180047454  mov     edx, 2
0x180047459  lea     ecx, [rdx-1]
0x18004745c  mov     r8, rsi
0x18004745f  call    msgdbgprint
0x180047464  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004746b  mov     r15b, 10h
0x18004746e  test    cs:byte_1800CF404, r15b
0x180047475  jz      short loc_1800474F0
0x180047477  mov     word ptr [rbp+23D0h+var_830], r13w
0x18004747f  mov     word ptr [rbp+23D0h+var_860], r13w
0x180047487  mov     edx, [rsi+8]
0x18004748a  lea     rcx, [rbp+23D0h+var_860]
0x180047491  call    ConvertPortNoToString
0x180047496  mov     rax, [rsi+10h]
0x18004749a  mov     [rsp+24D0h+var_24B0], rax
0x18004749f  mov     r9, [rsi+8]
0x1800474a3  mov     r8d, [rsi]
0x1800474a6  lea     rdx, aProcessingMess; "Processing Message (Id:%d) for hPort=%I"...
0x1800474ad  lea     rcx, [rbp+23D0h+var_830]
0x1800474b4  call    FormatRRASErrorString
0x1800474b9  test    cs:byte_1800CF404, r15b
0x1800474c0  jz      short loc_1800474F0
0x1800474c2  lea     rax, [rbp+23D0h+var_860]
0x1800474c9  mov     [rsp+24D0h+var_24A8], rax
0x1800474ce  mov     [rsp+24D0h+var_24B0], r13
0x1800474d3  lea     r9, [rbp+23D0h+var_890]
0x1800474da  lea     r8, [rbp+23D0h+var_830]
0x1800474e1  lea     rdx, RasDdmParamTraceInfo
0x1800474e8  mov     rcx, r12
0x1800474eb  call    McTemplateU0zjzz_EventWriteTransfer
0x1800474f0  mov     ecx, [rsi]
0x1800474f2  sub     ecx, 1
0x1800474f5  jz      loc_180047BD3
0x1800474fb  sub     ecx, 1
0x1800474fe  jz      loc_18004797E
0x180047504  sub     ecx, 1
0x180047507  jz      loc_1800478E7
0x18004750d  sub     ecx, 1
0x180047510  jz      loc_1800476BF
0x180047516  sub     ecx, 1
0x180047519  jz      loc_180047632
0x18004751f  sub     ecx, 1
0x180047522  jz      loc_180047677
0x180047528  sub     ecx, 1
0x18004752b  jz      loc_180047632
0x180047531  sub     ecx, 1
0x180047534  jz      loc_1800475DD
0x18004753a  cmp     ecx, 1
0x18004753d  jnz     loc_1800477D0
0x180047543  mov     edi, r13d
0x180047546  cmp     [rsi+18h], r13d
0x18004754a  jbe     loc_1800477D0
0x180047550  mov     [rsp+24D0h+var_2470], 0Eh
0x180047559  mov     qword ptr [rsp+24D0h+var_2468], r13
0x18004755e  xor     edx, edx; Val
0x180047560  mov     r8d, 1BD0h; Size
0x180047566  lea     rcx, [rsp+24D0h+var_2460]; void *
0x18004756b  call    memset_0
0x180047570  mov     ecx, edi
0x180047572  movzx   eax, word ptr [rsi+rcx*8+1Ch]
0x180047577  mov     [rsp+24D0h+var_2458], ax
0x18004757c  mov     eax, r13d
0x18004757f  cmp     dword ptr [rsi+rcx*8+20h], 1
0x180047584  setnz   al
0x180047587  inc     eax
0x180047589  mov     [rsp+24D0h+var_2454], eax
0x18004758d  lea     r13, qword_1800CE4C8
0x180047594  mov     eax, 3
0x180047599  mov     qword ptr [rsp+24D0h+var_2498], rax
0x18004759e  cmp     dword ptr [r13-2Ch], 1
0x1800475a3  jnz     short loc_1800475B8
0x1800475a5  lea     rcx, [rsp+24D0h+var_2470]
0x1800475aa  mov     rax, [r13+0]
0x1800475ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475b3  mov     rax, qword ptr [rsp+24D0h+var_2498]
0x1800475b8  add     r13, 50h ; 'P'
0x1800475bc  sub     rax, 1
0x1800475c0  mov     qword ptr [rsp+24D0h+var_2498], rax
0x1800475c5  jnz     short loc_18004759E
0x1800475c7  inc     edi
0x1800475c9  cmp     edi, [rsi+18h]
0x1800475cc  mov     r13d, 0
0x1800475d2  jb      loc_180047550
0x1800475d8  jmp     loc_1800477D0
0x1800475dd  mov     ecx, 11h; unsigned int
0x1800475e2  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x1800475e7  lea     r8, [rsp+24D0h+var_24A0]
0x1800475ec  mov     rdx, [rsi+8]
0x1800475f0  mov     rcx, rax
0x1800475f3  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x1800475f8  mov     rbx, [rsp+24D0h+var_24A0]
0x1800475fd  test    rbx, rbx
0x180047600  jz      loc_180047BFE
0x180047606  lea     rcx, [rbx+10h]; lpCriticalSection
0x18004760a  call    cs:__imp_EnterCriticalSection
0x180047611  nop     dword ptr [rax+rax+00h]
0x180047616  mov     rax, [rbx]
0x180047619  mov     r8d, [rsi+18h]
0x18004761d  mov     rdx, [rsi+20h]
0x180047621  mov     rcx, rbx
0x180047624  mov     rax, [rax+78h]
0x180047628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004762d  jmp     loc_180047BBE
0x180047632  mov     ecx, 11h; unsigned int
0x180047637  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18004763c  lea     r8, [rsp+24D0h+var_24A0]
0x180047641  mov     rdx, [rsi+8]
0x180047645  mov     rcx, rax
0x180047648  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18004764d  mov     rbx, [rsp+24D0h+var_24A0]
0x180047652  test    rbx, rbx
0x180047655  jz      loc_180047BFE
0x18004765b  lea     rcx, [rbx+10h]; lpCriticalSection
0x18004765f  call    cs:__imp_EnterCriticalSection
0x180047666  nop     dword ptr [rax+rax+00h]
0x18004766b  mov     rax, [rbx]
0x18004766e  mov     rax, [rax+68h]
0x180047672  jmp     loc_180047BB6
0x180047677  mov     ecx, 11h; unsigned int
0x18004767c  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180047681  lea     r8, [rsp+24D0h+var_24A0]
0x180047686  mov     rdx, [rsi+8]
0x18004768a  mov     rcx, rax
0x18004768d  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180047692  mov     rbx, [rsp+24D0h+var_24A0]
0x180047697  test    rbx, rbx
0x18004769a  jz      loc_180047BFE
0x1800476a0  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800476a4  call    cs:__imp_EnterCriticalSection
0x1800476ab  nop     dword ptr [rax+rax+00h]
0x1800476b0  mov     rax, [rbx]
0x1800476b3  mov     rax, [rax+168h]
0x1800476ba  jmp     loc_180047BB6
0x1800476bf  mov     edi, 11h
0x1800476c4  mov     ecx, edi; unsigned int
0x1800476c6  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x1800476cb  lea     r8, [rsp+24D0h+var_24A0]
0x1800476d0  mov     rdx, [rsi+8]
0x1800476d4  mov     rcx, rax
0x1800476d7  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x1800476dc  mov     rbx, [rsp+24D0h+var_24A0]
0x1800476e1  test    rbx, rbx
0x1800476e4  jz      loc_180047BFE
0x1800476ea  lea     r13, [rbx+10h]
0x1800476ee  mov     rcx, r13; lpCriticalSection
0x1800476f1  call    cs:__imp_EnterCriticalSection
0x1800476f8  nop     dword ptr [rax+rax+00h]
0x1800476fd  mov     rax, [rbx]
0x180047700  mov     rcx, rbx
0x180047703  mov     rax, [rax+1C0h]
0x18004770a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004770f  mov     r14d, eax
0x180047712  test    eax, eax
0x180047714  jz      loc_18004787F
0x18004771a  test    cs:byte_1800CF404, 8
0x180047721  jz      loc_1800477AC
0x180047727  xor     edi, edi
0x180047729  mov     word ptr [rbp+23D0h+var_830], di
0x180047730  mov     r9d, eax
0x180047733  lea     r8, aDdmnotificatio_0; "DdmNotificationHandler::DriverNotificat"...
0x18004773a  lea     rdx, aSMarkportconne; "%s:MarkPortConnectComplete failed: %d"
0x180047741  lea     rcx, [rbp+23D0h+var_830]
0x180047748  call    FormatRRASErrorString
0x18004774d  test    cs:byte_1800CF404, 8
0x180047754  jz      short loc_1800477AC
0x180047756  lea     rcx, [rbp+23D0h+var_830]
0x18004775d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047761  inc     rax
0x180047764  cmp     [rcx+rax*2], di
0x180047768  jnz     short loc_180047761
0x18004776a  lea     eax, ds:2[rax*2]
0x180047771  lea     rcx, [rbp+23D0h+var_830]
0x180047778  mov     [rbp+23D0h+var_870], rcx
0x18004777f  mov     [rbp+23D0h+var_868], eax
0x180047785  mov     [rbp+23D0h+var_864], edi
0x18004778b  lea     rax, [rbp+23D0h+var_880]
0x180047792  mov     [rsp+24D0h+var_24B0], rax
0x180047797  mov     r9d, 2
0x18004779d  lea     rdx, RasDdmTraceError
0x1800477a4  mov     rcx, r12
0x1800477a7  call    McGenEventWrite_EventWriteTransfer
0x1800477ac  mov     rax, [rbx]
0x1800477af  mov     rcx, rbx
0x1800477b2  mov     rax, [rax+0B0h]
0x1800477b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477be  mov     rcx, r13; lpCriticalSection
0x1800477c1  call    cs:__imp_LeaveCriticalSection
0x1800477c8  nop     dword ptr [rax+rax+00h]
0x1800477cd  xor     r13d, r13d
0x1800477d0  test    cs:byte_1800CF404, r15b
0x1800477d7  jz      short loc_180047857
0x1800477d9  mov     word ptr [rbp+23D0h+var_830], r13w
0x1800477e1  mov     word ptr [rbp+23D0h+var_860], r13w
0x1800477e9  mov     edx, [rsi+8]
0x1800477ec  lea     rcx, [rbp+23D0h+var_860]
0x1800477f3  call    ConvertPortNoToString
0x1800477f8  mov     dword ptr [rsp+24D0h+var_24A8], r14d
0x1800477fd  mov     rax, [rsi+10h]
0x180047801  mov     [rsp+24D0h+var_24B0], rax
0x180047806  mov     r9, [rsi+8]
0x18004780a  mov     r8d, [rsi]
0x18004780d  lea     rdx, aProcessingDone; "Processing Done for Message (Id:%d) for"...
0x180047814  lea     rcx, [rbp+23D0h+var_830]
0x18004781b  call    FormatRRASErrorString
0x180047820  test    cs:byte_1800CF404, r15b
0x180047827  jz      short loc_180047857
0x180047829  lea     rax, [rbp+23D0h+var_860]
0x180047830  mov     [rsp+24D0h+var_24A8], rax
0x180047835  mov     [rsp+24D0h+var_24B0], r13
0x18004783a  lea     r9, [rbp+23D0h+var_890]
0x180047841  lea     r8, [rbp+23D0h+var_830]
0x180047848  lea     rdx, RasDdmParamTraceInfo
0x18004784f  mov     rcx, r12
0x180047852  call    McTemplateU0zjzz_EventWriteTransfer
0x180047857  cmp     dword ptr [rsi], 8
0x18004785a  jnz     loc_180047DF6
0x180047860  cmp     [rsi+18h], r13d
0x180047864  jbe     loc_180047E1A
0x18004786a  mov     rcx, [rsi+20h]; hMem
0x18004786e  call    cs:__imp_LocalFree
0x180047875  nop     dword ptr [rax+rax+00h]
0x18004787a  jmp     loc_180047E1A
0x18004787f  mov     rcx, r13; lpCriticalSection
0x180047882  call    cs:__imp_LeaveCriticalSection
0x180047889  nop     dword ptr [rax+rax+00h]
0x18004788e  mov     ecx, edi; unsigned int
0x180047890  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180047895  lea     rdx, [rsp+24D0h+var_24A0]
0x18004789a  mov     rcx, rax; this
0x18004789d  call    ?UpdateDeviceBundleMap@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::UpdateDeviceBundleMap(RasObjPtr<DdmDevice> &)
0x1800478a2  call    ExecuteComponentTest
0x1800478a7  mov     rcx, r13; lpCriticalSection
0x1800478aa  call    cs:__imp_EnterCriticalSection
0x1800478b1  nop     dword ptr [rax+rax+00h]
0x1800478b6  mov     rax, [rbx]
0x1800478b9  mov     rcx, rbx
0x1800478bc  mov     rax, [rax+58h]
0x1800478c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478c5  mov     r14d, eax
0x1800478c8  test    eax, eax
0x1800478ca  jnz     loc_1800477BE
0x1800478d0  mov     rax, [rbx]
0x1800478d3  mov     rcx, rbx
0x1800478d6  mov     rax, [rax+60h]
0x1800478da  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
