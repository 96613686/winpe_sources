# Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(void *,_BLUETOOTH_DEVICE_INFO const *,_BTH_PNP_INFO *,int)

- ea: `0x180026808`
- end: `0x180026b8c`
- name: `?BthpFindPnpInfo@BthServ@Services@Bluetooth@Microsoft@@YAXPEAXPEBU_BLUETOOTH_DEVICE_INFO@@PEAU_BTH_PNP_INFO@@H@Z`
- size: `900`
- prototype: `void __fastcall(Microsoft::Bluetooth::Services::BthServ *this, void *, const struct _BLUETOOTH_DEVICE_INFO *, struct _BTH_PNP_INFO *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025648`
- `0x180027ea8`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x18002472c`
- `0x1800247d0`
- `0x180024a1c`
- `0x180024c84`
- `0x180024f34`
- `0x180025e10`
- `0x180026808`
- `0x180026c70`
- `0x180027788`
- `0x18002840c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002691e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800269a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002691e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800269a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800269bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800269bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026933`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026996`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800268d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800268ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800268d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800268ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b6e`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        const struct _BLUETOOTH_DEVICE_INFO *a3,
        struct _BTH_PNP_INFO *a4)
{
  const struct _BLUETOOTH_DEVICE_INFO *v4; // r14
  int v7; // esi
  int v8; // r12d
  Microsoft::Bluetooth::Services::BthServ *FirstServiceInternal; // r13
  Microsoft::Bluetooth::Services::BthServ *v10; // r15
  struct _GUID *v11; // r8
  Microsoft::Bluetooth::Services::BthServ *v12; // rdi
  HANDLE ProcessHeap; // rax
  Microsoft::Bluetooth::Services::BthServ *v14; // rbx
  unsigned int *v15; // r9
  DWORD LastError; // esi
  struct _BLUETOOTH_SDP_RECORD *v17; // rax
  struct _GUID *v18; // r8
  HANDLE v19; // rax
  Microsoft::Bluetooth::Services::BthServ *v20; // rbx
  __int64 v21; // rdi
  void *v22; // rdx
  unsigned int *v23; // r9
  struct _BLUETOOTH_SDP_RECORD *v24; // rax
  Microsoft::Bluetooth::Services::BthServ *v25; // rbx
  struct _BLUETOOTH_SDP_RECORD *v26; // rdi
  Microsoft::Bluetooth::Services::BthServ *v27; // r12
  Microsoft::Bluetooth::Services::BthServ *Record; // rax
  Microsoft::Bluetooth::Services::BthServ *v29; // r14
  struct _BLUETOOTH_SDP_RECORD *v30; // rax
  unsigned int *v31; // r9
  unsigned int v32; // esi
  void *v33; // rdx
  unsigned int v34; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v35[2]; // [rsp+28h] [rbp-D8h]
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+34h] [rbp-CCh]
  int v38; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v39[4]; // [rsp+44h] [rbp-BCh] BYREF
  Microsoft::Bluetooth::Services::BthServ *v40; // [rsp+48h] [rbp-B8h]
  unsigned int v41; // [rsp+50h] [rbp-B0h]
  char v42; // [rsp+54h] [rbp-ACh]
  Microsoft::Bluetooth::Services::BthServ *v43; // [rsp+60h] [rbp-A0h]
  __int128 v44; // [rsp+610h] [rbp+510h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v45; // [rsp+620h] [rbp+520h]
  __int64 v46; // [rsp+628h] [rbp+528h]

  v4 = a3;
  *(_QWORD *)v35 = a3;
  v7 = (int)a4;
  memset_0(v39, 0, 0x5C4u);
  v46 = 0;
  v8 = 0;
  *(_QWORD *)&v44 = 32;
  v37 = 0;
  *((_QWORD *)&v44 + 1) = a2;
  v45 = this;
  v38 = 1480;
  FirstServiceInternal = (Microsoft::Bluetooth::Services::BthServ *)Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(
                                                                      &v44,
                                                                      &v38,
                                                                      v7 == 0 ? 2 : 0);
  if ( FirstServiceInternal )
  {
    while ( 1 )
    {
      v10 = 0;
      v44 = 0;
      if ( v38 != 1480 )
      {
        SetLastError(0x51Au);
        goto LABEL_33;
      }
      SetLastError(0xDu);
      if ( (v42 & 2) == 0 )
        goto LABEL_33;
      v12 = v43;
      if ( !v43 )
        goto LABEL_33;
      if ( (*(_BYTE *)v43 & 0xF8) != 0x30 )
        goto LABEL_33;
      ProcessHeap = GetProcessHeap();
      v14 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(ProcessHeap, 0, 0x18u);
      if ( !v14 )
        goto LABEL_33;
      v34 = 0;
      LastError = 1168;
      v17 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
              v12,
              (Microsoft::Bluetooth::Services::BthServ *)((char *)v40 + v41),
              &v34,
              v15);
      *(_QWORD *)v14 = v17;
      if ( v17 )
      {
        LastError = 0;
        *((_QWORD *)v14 + 1) = (char *)v17 + v34;
        v10 = v14;
        if ( Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(v14, &v44, v18) )
          goto LABEL_12;
        LastError = GetLastError();
        v10 = 0;
      }
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v14);
LABEL_12:
      SetLastError(LastError);
      if ( !v10 )
        goto LABEL_33;
      while ( *(_OWORD *)&PnPInformationServiceClass_UUID != v44 )
      {
LABEL_30:
        if ( !Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(v10, &v44, v11) )
        {
          v8 = v37;
          goto LABEL_32;
        }
      }
      v20 = v40;
      v21 = v41;
      if ( v40 && v41 )
      {
        SetLastError(0xDu);
        if ( (*(_BYTE *)v20 & 0xF8) == 0x30 )
        {
          v34 = 0;
          v24 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
                  v20,
                  (Microsoft::Bluetooth::Services::BthServ *)((char *)v20 + v21),
                  &v34,
                  v23);
          v25 = v24;
          if ( v24 )
          {
            v26 = (struct _BLUETOOTH_SDP_RECORD *)((char *)v24 + v34);
            while ( 1 )
            {
              while ( 1 )
              {
                if ( v25 >= v26 )
                {
LABEL_27:
                  v4 = *(const struct _BLUETOOTH_DEVICE_INFO **)v35;
                  goto LABEL_28;
                }
                v27 = v25;
                Record = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(v25, v26, v11);
                v29 = Record;
                if ( Record )
                {
                  v30 = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(Record, v26, v11);
                  v25 = v30;
                  if ( v30 )
                    break;
                }
LABEL_26:
                if ( !v25 )
                  goto LABEL_27;
              }
              v32 = (_DWORD)v30 - (_DWORD)v29;
              if ( (int)v30 - (int)v29 < v34 )
              {
                if ( (*(_BYTE *)v27 & 0xF8) != 8 )
                  goto LABEL_27;
                v36 = 0;
                if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(
                                      v27,
                                      v26,
                                      &v36,
                                      v31)
                  || !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpExtractPNPAttributes(
                                      (Microsoft::Bluetooth::Services::BthServ *)v36,
                                      v29,
                                      (unsigned __int8 *)v32,
                                      *(__int64 *)v35) )
                {
                  goto LABEL_27;
                }
                goto LABEL_26;
              }
            }
          }
        }
      }
      else
      {
        SetLastError(0x57u);
      }
LABEL_28:
      if ( (v4->fRemembered & 0xF) != 0xF )
      {
        v4->fRemembered = 0;
        goto LABEL_30;
      }
      v8 = 1;
      v37 = 1;
LABEL_32:
      Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(v10, v22);
LABEL_33:
      if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(
                            FirstServiceInternal,
                            &v38,
                            (struct _BLUETOOTH_SERVICE_RECORD *)v11)
        || v8 )
      {
        Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(FirstServiceInternal, v33);
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x180026808  mov     [rsp-8+arg_18], rbx
0x18002680d  push    rbp
0x18002680e  push    rsi
0x18002680f  push    rdi
0x180026810  push    r12
0x180026812  push    r13
0x180026814  push    r14
0x180026816  push    r15
0x180026818  lea     rbp, [rsp-540h]
0x180026820  sub     rsp, 640h
0x180026827  mov     rax, cs:__security_cookie
0x18002682e  xor     rax, rsp
0x180026831  mov     [rbp+570h+var_40], rax
0x180026838  mov     r14, r8
0x18002683b  mov     qword ptr [rsp+670h+var_648], r8
0x180026840  mov     rdi, rdx
0x180026843  mov     rbx, rcx
0x180026846  xor     edx, edx; Val
0x180026848  lea     rcx, [rsp+670h+var_62C]; void *
0x18002684d  mov     r8d, 5C4h; Size
0x180026853  mov     esi, r9d
0x180026856  call    memset_0
0x18002685b  and     dword ptr [rbp+570h+var_60+4], 0
0x180026862  lea     rdx, [rsp+670h+var_630]
0x180026867  and     [rbp+570h+var_48], 0
0x18002686f  lea     rcx, [rbp+570h+var_60]
0x180026876  xor     r12d, r12d
0x180026879  mov     dword ptr [rbp+570h+var_60], 20h ; ' '
0x180026883  neg     esi
0x180026885  mov     [rsp+670h+var_640+4], r12d
0x18002688a  mov     qword ptr [rbp+570h+var_60+8], rdi
0x180026891  sbb     r8d, r8d
0x180026894  mov     [rbp+570h+var_50], rbx
0x18002689b  not     r8d
0x18002689e  mov     [rsp+670h+var_630], 5C8h
0x1800268a6  and     r8d, 2
0x1800268aa  call    ?BluetoothFindFirstServiceInternal@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x1800268af  mov     r13, rax
0x1800268b2  test    rax, rax
0x1800268b5  jz      loc_180026B3E
0x1800268bb  xor     r15d, r15d
0x1800268be  xorps   xmm0, xmm0
0x1800268c1  cmp     [rsp+670h+var_630], 5C8h
0x1800268c9  movups  [rbp+570h+var_60], xmm0
0x1800268d0  jz      short loc_1800268E8
0x1800268d2  mov     ecx, 51Ah; dwErrCode
0x1800268d7  call    cs:__imp_SetLastError
0x1800268de  nop     dword ptr [rax+rax+00h]
0x1800268e3  jmp     loc_180026B1C
0x1800268e8  mov     ecx, 0Dh; dwErrCode
0x1800268ed  call    cs:__imp_SetLastError
0x1800268f4  nop     dword ptr [rax+rax+00h]
0x1800268f9  test    [rsp+670h+var_61C], 2
0x1800268fe  jz      loc_180026B1C
0x180026904  mov     rdi, [rsp+670h+var_610]
0x180026909  test    rdi, rdi
0x18002690c  jz      loc_180026B1C
0x180026912  mov     al, [rdi]
0x180026914  and     al, 0F8h
0x180026916  cmp     al, 30h ; '0'
0x180026918  jnz     loc_180026B1C
0x18002691e  call    cs:__imp_GetProcessHeap
0x180026925  nop     dword ptr [rax+rax+00h]
0x18002692a  xor     edx, edx; dwFlags
0x18002692c  mov     rcx, rax; hHeap
0x18002692f  lea     r8d, [rdx+18h]; dwBytes
0x180026933  call    cs:__imp_HeapAlloc
0x18002693a  nop     dword ptr [rax+rax+00h]
0x18002693f  mov     rbx, rax
0x180026942  test    rax, rax
0x180026945  jz      loc_180026B1C
0x18002694b  mov     edx, [rsp+670h+var_620]
0x18002694f  lea     r8, [rsp+670h+var_650]; void *
0x180026954  add     rdx, [rsp+670h+var_628]; struct _BLUETOOTH_SDP_RECORD *
0x180026959  mov     rcx, rdi; this
0x18002695c  and     [rsp+670h+var_650], r15d
0x180026961  mov     esi, 490h
0x180026966  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x18002696b  mov     [rbx], rax
0x18002696e  test    rax, rax
0x180026971  jz      short loc_1800269A7
0x180026973  mov     ecx, [rsp+670h+var_650]
0x180026977  lea     rdx, [rbp+570h+var_60]; void *
0x18002697e  add     rcx, rax
0x180026981  xor     esi, esi
0x180026983  mov     [rbx+8], rcx
0x180026987  mov     r15, rbx
0x18002698a  mov     rcx, rbx; this
0x18002698d  call    ?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)
0x180026992  test    eax, eax
0x180026994  jnz     short loc_1800269C7
0x180026996  call    cs:__imp_GetLastError
0x18002699d  nop     dword ptr [rax+rax+00h]
0x1800269a2  mov     esi, eax
0x1800269a4  xor     r15d, r15d
0x1800269a7  call    cs:__imp_GetProcessHeap
0x1800269ae  nop     dword ptr [rax+rax+00h]
0x1800269b3  mov     r8, rbx; lpMem
0x1800269b6  xor     edx, edx; dwFlags
0x1800269b8  mov     rcx, rax; hHeap
0x1800269bb  call    cs:__imp_HeapFree
0x1800269c2  nop     dword ptr [rax+rax+00h]
0x1800269c7  mov     ecx, esi; dwErrCode
0x1800269c9  call    cs:__imp_SetLastError
0x1800269d0  nop     dword ptr [rax+rax+00h]
0x1800269d5  test    r15, r15
0x1800269d8  jz      loc_180026B1C
0x1800269de  mov     rax, qword ptr cs:PnPInformationServiceClass_UUID.Data1
0x1800269e5  cmp     rax, qword ptr [rbp+570h+var_60]
0x1800269ec  jnz     loc_180026AF8
0x1800269f2  mov     rax, qword ptr cs:PnPInformationServiceClass_UUID.Data4
0x1800269f9  cmp     rax, qword ptr [rbp+570h+var_60+8]
0x180026a00  jnz     loc_180026AF8
0x180026a06  mov     rbx, [rsp+670h+var_628]
0x180026a0b  mov     edi, [rsp+670h+var_620]
0x180026a0f  test    rbx, rbx
0x180026a12  jz      loc_180026B69
0x180026a18  test    edi, edi
0x180026a1a  jz      loc_180026B69
0x180026a20  mov     ecx, 0Dh; dwErrCode
0x180026a25  call    cs:__imp_SetLastError
0x180026a2c  nop     dword ptr [rax+rax+00h]
0x180026a31  mov     al, [rbx]
0x180026a33  and     al, 0F8h
0x180026a35  cmp     al, 30h ; '0'
0x180026a37  jnz     loc_180026AE4
0x180026a3d  and     [rsp+670h+var_650], 0
0x180026a42  lea     rdx, [rbx+rdi]; struct _BLUETOOTH_SDP_RECORD *
0x180026a46  lea     r8, [rsp+670h+var_650]; void *
0x180026a4b  mov     rcx, rbx; this
0x180026a4e  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180026a53  mov     rbx, rax
0x180026a56  test    rax, rax
0x180026a59  jz      loc_180026AE4
0x180026a5f  mov     edi, [rsp+670h+var_650]
0x180026a63  add     rdi, rax
0x180026a66  cmp     rbx, rdi
0x180026a69  jnb     short loc_180026ADF
0x180026a6b  mov     rdx, rdi; struct _BLUETOOTH_SDP_RECORD *
0x180026a6e  mov     rcx, rbx; this
0x180026a71  mov     r12, rbx
0x180026a74  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180026a79  mov     r14, rax
0x180026a7c  test    rax, rax
0x180026a7f  jz      short loc_180026ADA
0x180026a81  mov     rdx, rdi; struct _BLUETOOTH_SDP_RECORD *
0x180026a84  mov     rcx, rax; this
0x180026a87  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180026a8c  mov     rbx, rax
0x180026a8f  test    rax, rax
0x180026a92  jz      short loc_180026ADA
0x180026a94  mov     esi, eax
0x180026a96  sub     esi, r14d
0x180026a99  cmp     esi, [rsp+670h+var_650]
0x180026a9d  jnb     short loc_180026A66
0x180026a9f  mov     al, [r12]
0x180026aa3  and     al, 0F8h
0x180026aa5  cmp     al, 8
0x180026aa7  jnz     short loc_180026ADF
0x180026aa9  and     [rsp+670h+var_640], 0
0x180026aae  lea     r8, [rsp+670h+var_640]; void *
0x180026ab3  mov     rdx, rdi; struct _BLUETOOTH_SDP_RECORD *
0x180026ab6  mov     rcx, r12; this
0x180026ab9  call    ?BthpTransposeAndExtendBytes@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180026abe  test    eax, eax
0x180026ac0  jz      short loc_180026ADF
0x180026ac2  mov     r9, qword ptr [rsp+670h+var_648]; unsigned int
0x180026ac7  mov     r8d, esi; unsigned __int8 *
0x180026aca  mov     ecx, [rsp+670h+var_640]; this
0x180026ace  mov     rdx, r14; unsigned int
0x180026ad1  call    ?BthpExtractPNPAttributes@BthServ@Services@Bluetooth@Microsoft@@YAHKPEAEKPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpExtractPNPAttributes(ulong,uchar *,ulong,void *)
0x180026ad6  test    eax, eax
0x180026ad8  jz      short loc_180026ADF
0x180026ada  test    rbx, rbx
0x180026add  jnz     short loc_180026A66
0x180026adf  mov     r14, qword ptr [rsp+670h+var_648]
0x180026ae4  mov     eax, [r14+18h]
0x180026ae8  and     eax, 0Fh
0x180026aeb  cmp     al, 0Fh
0x180026aed  jz      loc_180026B7F
0x180026af3  and     dword ptr [r14+18h], 0
0x180026af8  lea     rdx, [rbp+570h+var_60]; void *
0x180026aff  mov     rcx, r15; this
0x180026b02  call    ?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)
0x180026b07  test    eax, eax
0x180026b09  jnz     loc_1800269DE
0x180026b0f  mov     r12d, [rsp+670h+var_640+4]
0x180026b14  mov     rcx, r15; this
0x180026b17  call    ?BluetoothFindClassIdClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(void *)
0x180026b1c  lea     rdx, [rsp+670h+var_630]; void *
0x180026b21  mov     rcx, r13; this
0x180026b24  call    ?BluetoothFindNextService@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_BLUETOOTH_SERVICE_RECORD@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(void *,_BLUETOOTH_SERVICE_RECORD *)
0x180026b29  test    eax, eax
0x180026b2b  jz      short loc_180026B36
0x180026b2d  test    r12d, r12d
0x180026b30  jz      loc_1800268BB
0x180026b36  mov     rcx, r13; this
0x180026b39  call    ?BluetoothFindServiceClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void *)
0x180026b3e  mov     rcx, [rbp+570h+var_40]
0x180026b45  xor     rcx, rsp; StackCookie
0x180026b48  call    __security_check_cookie
0x180026b4d  mov     rbx, [rsp+670h+arg_18]
0x180026b55  add     rsp, 640h
0x180026b5c  pop     r15
0x180026b5e  pop     r14
0x180026b60  pop     r13
0x180026b62  pop     r12
0x180026b64  pop     rdi
0x180026b65  pop     rsi
0x180026b66  pop     rbp
0x180026b67  retn
0x180026b69  mov     ecx, 57h ; 'W'; dwErrCode
0x180026b6e  call    cs:__imp_SetLastError
0x180026b75  nop     dword ptr [rax+rax+00h]
0x180026b7a  jmp     loc_180026AE4
0x180026b7f  mov     r12d, 1
0x180026b85  mov     [rsp+670h+var_640+4], r12d
0x180026b8a  jmp     short loc_180026B14
```
