# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::CleanupPreviousAssociations(void)

- ea: `0x18002f4ec`
- end: `0x18002fb3c`
- name: `?CleanupPreviousAssociations@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAXXZ`
- size: `1616`
- prototype: `void __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002e418`

## callees

- `0x1800017a0`
- `0x180001bcc`
- `0x180011b9c`
- `0x180012004`
- `0x1800120b8`
- `0x180012384`
- `0x18001245c`
- `0x18001f1cc`
- `0x18002dcd0`
- `0x18002e094`
- `0x18002f4ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f861`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f861`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f79a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f79a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f7b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f7b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f877`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f7d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f896`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f7d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f896`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f7c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f7c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fad1`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002f888`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002faad`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002f888`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002faad`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x18002f83d`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x18002f83d`

## string_xrefs

- `0x18002fb11`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002fb2a`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::CleanupPreviousAssociations(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this)
{
  char v2; // di
  _BYTE *v3; // rcx
  char v4; // dl
  _UNKNOWN **v5; // rax
  char v6; // dl
  __int64 v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rax
  HANDLE EventW; // rsi
  const char *v11; // r9
  HANDLE v12; // r15
  DWORD LastError; // ebx
  int v14; // eax
  __int64 j; // r8
  __int64 v16; // rsi
  DWORD v17; // ebx
  __int64 v18; // rbx
  _BYTE *v19; // rcx
  _UNKNOWN **v20; // rdx
  _QWORD *v21; // rax
  char v22; // r10
  char v23; // r10
  unsigned int v24; // eax
  int v25; // edx
  bool v26; // cf
  char v27; // al
  __int64 *v28; // rax
  __int64 i; // rax
  int v30; // [rsp+28h] [rbp-E0h]
  int v31; // [rsp+28h] [rbp-E0h]
  int v32; // [rsp+30h] [rbp-D8h]
  _DWORD *v33; // [rsp+30h] [rbp-D8h]
  __int64 v34; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-98h]
  __int64 v36; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v37[2]; // [rsp+80h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-78h]
  __int128 v39; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v40[3]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v41; // [rsp+C0h] [rbp-48h] BYREF
  int v42; // [rsp+D0h] [rbp-38h]
  int v43; // [rsp+D4h] [rbp-34h]
  __int64 v44; // [rsp+D8h] [rbp-30h]
  __int128 v45; // [rsp+E0h] [rbp-28h]
  int v46; // [rsp+F0h] [rbp-18h]
  int v47; // [rsp+F4h] [rbp-14h]
  int v48; // [rsp+F8h] [rbp-10h]
  __int64 *v49; // [rsp+100h] [rbp-8h]
  _DWORD v50[3]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v51; // [rsp+114h] [rbp+Ch]
  __int128 v52; // [rsp+124h] [rbp+1Ch]
  __int64 v53; // [rsp+134h] [rbp+2Ch]
  int v54; // [rsp+13Ch] [rbp+34h]
  int v55; // [rsp+140h] [rbp+38h]
  __int128 v56; // [rsp+148h] [rbp+40h]
  int v57; // [rsp+158h] [rbp+50h]
  int v58; // [rsp+15Ch] [rbp+54h]
  __int64 v59; // [rsp+160h] [rbp+58h]
  int v60; // [rsp+168h] [rbp+60h]
  int v61; // [rsp+16Ch] [rbp+64h]
  __int64 *v62; // [rsp+170h] [rbp+68h]
  int v63; // [rsp+178h] [rbp+70h]
  __int128 v64; // [rsp+180h] [rbp+78h]
  int v65; // [rsp+190h] [rbp+88h]
  int v66; // [rsp+194h] [rbp+8Ch]
  __int64 v67; // [rsp+198h] [rbp+90h]
  int v68; // [rsp+1A0h] [rbp+98h]
  int v69; // [rsp+1A4h] [rbp+9Ch]
  const struct _GUID *v70; // [rsp+1A8h] [rbp+A0h]
  int v71; // [rsp+1B0h] [rbp+A8h]
  __int128 v72; // [rsp+1B8h] [rbp+B0h]
  int v73; // [rsp+1C8h] [rbp+C0h]
  int v74; // [rsp+1CCh] [rbp+C4h]
  __int64 v75; // [rsp+1D0h] [rbp+C8h]
  int v76; // [rsp+1D8h] [rbp+D0h]
  int v77; // [rsp+1DCh] [rbp+D4h]
  __int64 v78; // [rsp+1E0h] [rbp+D8h]
  int v79; // [rsp+1E8h] [rbp+E0h]
  int v80; // [rsp+1F0h] [rbp+E8h]
  __int128 v81; // [rsp+1F4h] [rbp+ECh]
  __int128 v82; // [rsp+204h] [rbp+FCh]
  __int64 v83; // [rsp+214h] [rbp+10Ch]
  int v84; // [rsp+21Ch] [rbp+114h]
  wil::details::in1diag3 *retaddr; // [rsp+260h] [rbp+158h]

  v2 = 1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v4 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    v4 = 0;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v3 = WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  if ( v3 == (_BYTE *)&WPP_GLOBAL_Control || (v6 = 1, v3[25] < 4u) )
    v6 = 0;
  if ( v6 || v5 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sS(
      *((_QWORD *)v3 + 2),
      v6,
      v5 != &WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v3 + 5),
      v30,
      v32,
      45,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
  v7 = -1;
  LOBYTE(v34) = -1;
  v50[0] = 0x100000;
  v50[2] = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 2;
  v56 = DEVPKEY_Aep_IsAssociated;
  v57 = 16;
  v58 = 0;
  v59 = 0;
  v60 = 17;
  v61 = 1;
  v62 = &v34;
  v63 = 2;
  v64 = DEVPKEY_Aep_ProtocolId;
  v65 = 5;
  v66 = 0;
  v67 = 0;
  v68 = 13;
  v69 = 16;
  v70 = &DAF_ProtocolId_BluetoothLE;
  v71 = 65538;
  v72 = DEVPKEY_Aep_AepId;
  v73 = 8;
  v74 = 0;
  v75 = 0;
  v76 = 18;
  v8 = *((_QWORD *)this + 8);
  do
    ++v7;
  while ( *(_WORD *)(v8 + 2 * v7 + 2) );
  v77 = 2 * v7;
  v78 = v8;
  v79 = 0x200000;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v45 = DEVPKEY_DasParam_AepStoreOnly;
  v46 = 4;
  v47 = 17;
  v48 = 1;
  v49 = &v34;
  v41 = DEVPKEY_BluetoothLE_PrepairingDeviceId;
  v42 = 7;
  v43 = 0;
  v44 = 0;
  v37[1] = this;
  hObject = 0;
  v39 = 0;
  v9 = operator new(0x40u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *(_QWORD *)&v39 = v9;
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v12);
    SetLastError(LastError);
  }
  hObject = EventW;
  if ( !EventW )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      v11);
  v35 = 0;
  v33 = v50;
  v31 = 5;
  v14 = DevCreateObjectQueryEx(5, 0, 1, &v41);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)(unsigned int)v14,
      5);
  WaitForSingleObject(hObject, 0x2710u);
  v16 = v35;
  if ( v35 )
  {
    v17 = GetLastError();
    DevCloseObjectQuery(v16);
    SetLastError(v17);
  }
  v35 = 0;
  v18 = *(_QWORD *)v39;
  v19 = WPP_GLOBAL_Control;
  v20 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  while ( !*(_BYTE *)(v18 + 25) )
  {
    v21 = (_QWORD *)(v18 + 32);
    if ( *(_QWORD *)(v18 + 56) > 7u )
      v21 = (_QWORD *)*v21;
    v37[0] = v21;
    if ( v19 == (_BYTE *)&WPP_GLOBAL_Control || (v22 = 1, v19[25] < 5u) )
      v22 = 0;
    if ( v22 || v20 != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v19 + 2), v22, v20 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v19 + 5));
      v19 = WPP_GLOBAL_Control;
      v20 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    }
    if ( v19 == (_BYTE *)&WPP_GLOBAL_Control || (v23 = 1, v19[25] < 4u) )
      v23 = 0;
    LOBYTE(j) = v20 != &WPP_RECORDER_INITIALIZED;
    if ( v23 || v20 != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sS(
        *((_QWORD *)v19 + 2),
        v23,
        (_BYTE)j,
        *((_QWORD *)v19 + 5),
        v31,
        (_DWORD)v33,
        58,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    v40[0] = &v36;
    v40[1] = v37;
    v40[2] = this;
    v24 = wil::ResultFromException__lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5___(v40, v20, j);
    j = v24;
    LODWORD(v36) = v24;
    v25 = 0;
    v19 = WPP_GLOBAL_Control;
    if ( v24 )
      v26 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
    else
      v26 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v27 = 1, LOBYTE(v25) = !v26, !v25) )
      v27 = 0;
    v20 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    if ( v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(j) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v20) = v27;
      WPP_RECORDER_AND_TRACE_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v20,
        j,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
      v19 = WPP_GLOBAL_Control;
      v20 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    }
    v28 = *(__int64 **)(v18 + 16);
    if ( *((_BYTE *)v28 + 25) )
    {
      for ( i = *(_QWORD *)(v18 + 8); !*(_BYTE *)(i + 25) && v18 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
        v18 = i;
      v18 = i;
    }
    else
    {
      v18 = *(_QWORD *)(v18 + 16);
      for ( j = *v28; !*(_BYTE *)(j + 25); j = *(_QWORD *)j )
        v18 = j;
    }
  }
  if ( v19 == (_BYTE *)&WPP_GLOBAL_Control || v19[25] < 5u )
    v2 = 0;
  LOBYTE(j) = v20 != &WPP_RECORDER_INITIALIZED;
  if ( v2 || v20 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v19 + 2), v2, (_BYTE)j, *((_QWORD *)v19 + 5));
  if ( v35 )
    DevCloseObjectQuery(v35);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(
    &v39,
    v20,
    j);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x18002f4ec  mov     rax, rsp
0x18002f4ef  mov     [rax+10h], rbx
0x18002f4f3  mov     [rax+18h], rsi
0x18002f4f7  mov     [rax+20h], rdi
0x18002f4fb  push    rbp
0x18002f4fc  push    r12
0x18002f4fe  push    r13
0x18002f500  push    r14
0x18002f502  push    r15
0x18002f504  lea     rbp, [rax-158h]
0x18002f50b  sub     rsp, 230h
0x18002f512  mov     rax, cs:__security_cookie
0x18002f519  xor     rax, rsp
0x18002f51c  mov     [rbp+150h+var_30], rax
0x18002f523  mov     r14, rcx
0x18002f526  lea     r13, WPP_GLOBAL_Control
0x18002f52d  xor     r12d, r12d
0x18002f530  lea     edi, [r12+1]
0x18002f535  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f53c  cmp     rcx, r13
0x18002f53f  jz      short loc_18002F54A
0x18002f541  cmp     byte ptr [rcx+19h], 5
0x18002f545  mov     dl, dil
0x18002f548  jnb     short loc_18002F54D
0x18002f54a  mov     dl, r12b
0x18002f54d  lea     r9, WPP_RECORDER_INITIALIZED
0x18002f554  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002f55b  cmp     rax, r9
0x18002f55e  setnz   r8b
0x18002f562  lea     r10, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f569  test    dl, dl
0x18002f56b  jnz     short loc_18002F572
0x18002f56d  test    r8b, r8b
0x18002f570  jz      short loc_18002F5AC
0x18002f572  mov     [rsp+250h+var_208], r14
0x18002f577  mov     [rsp+250h+var_218], r10
0x18002f57c  mov     word ptr [rsp+250h+var_220], 2Ch ; ','
0x18002f583  mov     r9, [rcx+28h]
0x18002f587  mov     rcx, [rcx+10h]
0x18002f58b  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f590  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f597  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002f59e  lea     r9, WPP_RECORDER_INITIALIZED
0x18002f5a5  lea     r10, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f5ac  cmp     rcx, r13
0x18002f5af  jz      short loc_18002F5BA
0x18002f5b1  cmp     byte ptr [rcx+19h], 4
0x18002f5b5  mov     dl, dil
0x18002f5b8  jnb     short loc_18002F5BD
0x18002f5ba  mov     dl, r12b
0x18002f5bd  cmp     rax, r9
0x18002f5c0  setnz   r8b
0x18002f5c4  test    dl, dl
0x18002f5c6  jnz     short loc_18002F5CD
0x18002f5c8  test    r8b, r8b
0x18002f5cb  jz      short loc_18002F5EF
0x18002f5cd  mov     rax, [r14+40h]
0x18002f5d1  mov     [rsp+250h+var_208], rax
0x18002f5d6  mov     [rsp+250h+var_218], r10
0x18002f5db  mov     word ptr [rsp+250h+var_220], 2Dh ; '-'
0x18002f5e2  mov     r9, [rcx+28h]
0x18002f5e6  mov     rcx, [rcx+10h]
0x18002f5ea  call    WPP_RECORDER_AND_TRACE_SF_sS
0x18002f5ef  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002f5f3  mov     byte ptr [rsp+250h+var_1F0], cl
0x18002f5f7  mov     [rbp+150h+var_150], 100000h
0x18002f5fe  mov     [rbp+150h+var_148], r12d
0x18002f602  xorps   xmm0, xmm0
0x18002f605  xor     eax, eax
0x18002f607  movups  [rbp+150h+var_144], xmm0
0x18002f60b  movups  [rbp+150h+var_134], xmm0
0x18002f60f  mov     [rbp+150h+var_124], rax
0x18002f613  mov     [rbp+150h+var_11C], eax
0x18002f616  lea     r8d, [rcx+3]
0x18002f61a  mov     [rbp+150h+var_118], r8d
0x18002f61e  movups  xmm0, cs:DEVPKEY_Aep_IsAssociated
0x18002f625  movaps  [rbp+150h+var_110], xmm0
0x18002f629  mov     eax, cs:dword_18003E220
0x18002f62f  mov     [rbp+150h+var_100], eax
0x18002f632  mov     [rbp+150h+var_FC], r12d
0x18002f636  mov     [rbp+150h+var_F8], r12
0x18002f63a  lea     edx, [rcx+12h]
0x18002f63d  mov     [rbp+150h+var_F0], edx
0x18002f640  mov     [rbp+150h+var_EC], edi
0x18002f643  lea     rax, [rsp+250h+var_1F0]
0x18002f648  mov     [rbp+150h+var_E8], rax
0x18002f64c  mov     [rbp+150h+var_E0], r8d
0x18002f650  movups  xmm0, cs:DEVPKEY_Aep_ProtocolId
0x18002f657  movups  [rbp+150h+var_D8], xmm0
0x18002f65b  mov     eax, cs:dword_18003E208
0x18002f661  mov     [rbp+150h+var_C8], eax
0x18002f667  mov     [rbp+150h+var_C4], r12d
0x18002f66e  mov     [rbp+150h+var_C0], r12
0x18002f675  mov     [rbp+150h+var_B8], 0Dh
0x18002f67f  mov     [rbp+150h+var_B4], 10h
0x18002f689  lea     rax, DAF_ProtocolId_BluetoothLE
0x18002f690  mov     [rbp+150h+var_B0], rax
0x18002f697  mov     [rbp+150h+var_A8], 10002h
0x18002f6a1  movups  xmm0, cs:DEVPKEY_Aep_AepId
0x18002f6a8  movaps  [rbp+150h+var_A0], xmm0
0x18002f6af  mov     eax, cs:dword_18003E2D8
0x18002f6b5  mov     [rbp+150h+var_90], eax
0x18002f6bb  mov     [rbp+150h+var_8C], r12d
0x18002f6c2  mov     [rbp+150h+var_88], r12
0x18002f6c9  mov     [rbp+150h+var_80], 12h
0x18002f6d3  mov     rax, [r14+40h]
0x18002f6d7  inc     rcx
0x18002f6da  cmp     [rax+rcx*2+2], r12w
0x18002f6e0  jnz     short loc_18002F6D7
0x18002f6e2  add     ecx, ecx
0x18002f6e4  mov     [rbp+150h+var_7C], ecx
0x18002f6ea  mov     [rbp+150h+var_78], rax
0x18002f6f1  mov     [rbp+150h+var_70], 200000h
0x18002f6fb  mov     [rbp+150h+var_68], r12d
0x18002f702  xorps   xmm0, xmm0
0x18002f705  xor     eax, eax
0x18002f707  movups  [rbp+150h+var_64], xmm0
0x18002f70e  movups  [rbp+150h+var_54], xmm0
0x18002f715  mov     [rbp+150h+var_44], rax
0x18002f71c  mov     [rbp+150h+var_3C], eax
0x18002f722  movups  xmm0, cs:DEVPKEY_DasParam_AepStoreOnly
0x18002f729  movups  [rbp+150h+var_178], xmm0
0x18002f72d  mov     eax, cs:dword_18003E1D0
0x18002f733  mov     [rbp+150h+var_168], eax
0x18002f736  mov     [rbp+150h+var_164], edx
0x18002f739  mov     [rbp+150h+var_160], edi
0x18002f73c  lea     rax, [rsp+250h+var_1F0]
0x18002f741  mov     [rbp+150h+var_158], rax
0x18002f745  movups  xmm0, cs:DEVPKEY_BluetoothLE_PrepairingDeviceId
0x18002f74c  movups  [rbp+150h+var_198], xmm0
0x18002f750  mov     eax, cs:dword_18003EF20
0x18002f756  mov     [rbp+150h+var_188], eax
0x18002f759  mov     [rbp+150h+var_184], r12d
0x18002f75d  mov     [rbp+150h+var_180], r12
0x18002f761  mov     [rbp+150h+var_1D0], r14
0x18002f765  mov     [rbp+150h+hObject], r12
0x18002f769  xorps   xmm0, xmm0
0x18002f76c  movdqu  [rbp+150h+var_1C0], xmm0
0x18002f771  mov     ecx, 40h ; '@'; Size
0x18002f776  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f77b  mov     [rax], rax
0x18002f77e  mov     [rax+8], rax
0x18002f782  mov     [rax+10h], rax
0x18002f786  mov     word ptr [rax+18h], 101h
0x18002f78c  mov     qword ptr [rbp+150h+var_1C0], rax
0x18002f790  xor     r9d, r9d; lpName
0x18002f793  xor     r8d, r8d; bInitialState
0x18002f796  xor     edx, edx; bManualReset
0x18002f798  xor     ecx, ecx; lpEventAttributes
0x18002f79a  call    cs:__imp_CreateEventW
0x18002f7a1  nop     dword ptr [rax+rax+00h]
0x18002f7a6  mov     rsi, rax
0x18002f7a9  mov     r15, [rbp+150h+hObject]
0x18002f7ad  lea     rdx, [r15-1]
0x18002f7b1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002f7b5  ja      short loc_18002F7E2
0x18002f7b7  call    cs:__imp_GetLastError
0x18002f7be  nop     dword ptr [rax+rax+00h]
0x18002f7c3  mov     ebx, eax
0x18002f7c5  mov     rcx, r15; hObject
0x18002f7c8  call    cs:__imp_CloseHandle
0x18002f7cf  nop     dword ptr [rax+rax+00h]
0x18002f7d4  mov     ecx, ebx; dwErrCode
0x18002f7d6  call    cs:__imp_SetLastError
0x18002f7dd  nop     dword ptr [rax+rax+00h]
0x18002f7e2  mov     [rbp+150h+hObject], rsi
0x18002f7e6  test    rsi, rsi
0x18002f7e9  jz      loc_18002FB23
0x18002f7ef  mov     [rsp+250h+var_1E8], r12
0x18002f7f4  lea     rax, [rsp+250h+var_1E8]
0x18002f7f9  mov     [rsp+250h+var_200], rax
0x18002f7fe  lea     rax, [rbp+150h+var_1D0]
0x18002f802  mov     [rsp+250h+var_208], rax
0x18002f807  lea     rax, ?s_PairedDeviceQueryCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_PairedDeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18002f80e  mov     [rsp+250h+var_210], rax
0x18002f813  lea     rax, [rbp+150h+var_178]
0x18002f817  mov     [rsp+250h+var_218], rax
0x18002f81c  mov     dword ptr [rsp+250h+var_220], edi
0x18002f820  lea     rax, [rbp+150h+var_150]
0x18002f824  mov     [rsp+250h+var_228], rax
0x18002f829  mov     [rsp+250h+var_230], 5; int
0x18002f831  lea     r9, [rbp+150h+var_198]
0x18002f835  mov     r8d, edi
0x18002f838  xor     edx, edx
0x18002f83a  lea     ecx, [rdx+5]
0x18002f83d  call    cs:__imp_DevCreateObjectQueryEx
0x18002f844  nop     dword ptr [rax+rax+00h]
0x18002f849  mov     rcx, [rbp+158h]; this
0x18002f850  test    eax, eax
0x18002f852  js      loc_18002FB0E
0x18002f858  mov     edx, 2710h; dwMilliseconds
0x18002f85d  mov     rcx, [rbp+150h+hObject]; hHandle
0x18002f861  call    cs:__imp_WaitForSingleObject
0x18002f868  nop     dword ptr [rax+rax+00h]
0x18002f86d  mov     rsi, [rsp+250h+var_1E8]
0x18002f872  test    rsi, rsi
0x18002f875  jz      short loc_18002F8A2
0x18002f877  call    cs:__imp_GetLastError
0x18002f87e  nop     dword ptr [rax+rax+00h]
0x18002f883  mov     ebx, eax
0x18002f885  mov     rcx, rsi
0x18002f888  call    cs:__imp_DevCloseObjectQuery
0x18002f88f  nop     dword ptr [rax+rax+00h]
0x18002f894  mov     ecx, ebx; dwErrCode
0x18002f896  call    cs:__imp_SetLastError
0x18002f89d  nop     dword ptr [rax+rax+00h]
0x18002f8a2  mov     [rsp+250h+var_1E8], r12
0x18002f8a7  mov     rbx, qword ptr [rbp+150h+var_1C0]
0x18002f8ab  mov     rbx, [rbx]
0x18002f8ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8b5  mov     rdx, cs:WPP_RECORDER_INITIALIZED
0x18002f8bc  lea     rsi, WPP_RECORDER_INITIALIZED
0x18002f8c3  lea     r15, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f8ca  cmp     [rbx+19h], r12b
0x18002f8ce  jnz     loc_18002FA62
0x18002f8d4  lea     rax, [rbx+20h]
0x18002f8d8  cmp     qword ptr [rax+18h], 7
0x18002f8dd  jbe     short loc_18002F8E2
0x18002f8df  mov     rax, [rax]
0x18002f8e2  mov     [rsp+250h+var_1D8], rax
0x18002f8e7  cmp     rcx, r13
0x18002f8ea  jz      short loc_18002F8F5
0x18002f8ec  cmp     byte ptr [rcx+19h], 5
0x18002f8f0  mov     r10b, dil
0x18002f8f3  jnb     short loc_18002F8F8
0x18002f8f5  mov     r10b, r12b
0x18002f8f8  cmp     rdx, rsi
0x18002f8fb  setnz   r8b
0x18002f8ff  test    r10b, r10b
0x18002f902  jnz     short loc_18002F909
0x18002f904  test    r8b, r8b
0x18002f907  jz      short loc_18002F938
0x18002f909  mov     [rsp+250h+var_218], r15
0x18002f90e  mov     word ptr [rsp+250h+var_220], 39h ; '9'
0x18002f915  mov     r9, [rcx+28h]
0x18002f919  mov     dl, r10b
0x18002f91c  mov     rcx, [rcx+10h]
0x18002f920  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002f925  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f92c  mov     rdx, cs:WPP_RECORDER_INITIALIZED
0x18002f933  mov     rax, [rsp+250h+var_1D8]
0x18002f938  cmp     rcx, r13
0x18002f93b  jz      short loc_18002F946
0x18002f93d  cmp     byte ptr [rcx+19h], 4
0x18002f941  mov     r10b, dil
0x18002f944  jnb     short loc_18002F949
0x18002f946  mov     r10b, r12b
0x18002f949  cmp     rdx, rsi
0x18002f94c  setnz   r8b
0x18002f950  test    r10b, r10b
0x18002f953  jnz     short loc_18002F95A
0x18002f955  test    r8b, r8b
0x18002f958  jz      short loc_18002F97B
0x18002f95a  mov     [rsp+250h+var_208], rax
0x18002f95f  mov     [rsp+250h+var_218], r15
0x18002f964  mov     word ptr [rsp+250h+var_220], 3Ah ; ':'
0x18002f96b  mov     r9, [rcx+28h]
0x18002f96f  mov     dl, r10b
0x18002f972  mov     rcx, [rcx+10h]
0x18002f976  call    WPP_RECORDER_AND_TRACE_SF_sS
0x18002f97b  lea     rax, [rsp+250h+var_1E0]
0x18002f980  mov     [rbp+150h+var_1B0], rax
0x18002f984  lea     rax, [rsp+250h+var_1D8]
0x18002f989  mov     [rbp+150h+var_1A8], rax
0x18002f98d  mov     [rbp+150h+var_1A0], r14
0x18002f991  lea     rcx, [rbp+150h+var_1B0]
0x18002f995  call    wil__ResultFromException__lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5___
0x18002f99a  mov     r8d, eax
0x18002f99d  mov     dword ptr [rsp+250h+var_1E0], eax
0x18002f9a1  mov     edx, r12d
0x18002f9a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9ab  test    eax, eax
0x18002f9ad  jnz     short loc_18002F9B5
0x18002f9af  cmp     byte ptr [rcx+19h], 5
0x18002f9b3  jmp     short loc_18002F9B9
0x18002f9b5  cmp     byte ptr [rcx+19h], 2
0x18002f9b9  setnb   dl
0x18002f9bc  cmp     rcx, r13
0x18002f9bf  jz      short loc_18002F9C8
0x18002f9c1  test    edx, edx
0x18002f9c3  mov     al, dil
0x18002f9c6  jnz     short loc_18002F9CB
0x18002f9c8  mov     al, r12b
0x18002f9cb  mov     rdx, cs:WPP_RECORDER_INITIALIZED
0x18002f9d2  cmp     rdx, rsi
0x18002f9d5  setnz   r10b
0x18002f9d9  test    al, al
0x18002f9db  jnz     short loc_18002F9E2
0x18002f9dd  test    r10b, r10b
0x18002f9e0  jz      short loc_18002FA13
0x18002f9e2  mov     dword ptr [rsp+250h+var_208], r8d
0x18002f9e7  mov     [rsp+250h+var_218], r15
0x18002f9ec  mov     word ptr [rsp+250h+var_220], 3Fh ; '?'
0x18002f9f3  mov     r9, [rcx+28h]
0x18002f9f7  mov     r8b, r10b
0x18002f9fa  mov     dl, al
0x18002f9fc  mov     rcx, [rcx+10h]
0x18002fa00  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002fa05  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa0c  mov     rdx, cs:WPP_RECORDER_INITIALIZED
  ... truncated ...
```
