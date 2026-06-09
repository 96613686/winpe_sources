# CMsftDiscFormat2Erase::EraseByWrite(_IMAPI_MEDIA_PHYSICAL_TYPE)

- ea: `0x180025508`
- end: `0x180025dc8`
- name: `?EraseByWrite@CMsftDiscFormat2Erase@@AEAAJW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z`
- size: `2240`
- prototype: `__int64 __fastcall(CMsftDiscFormat2Erase *__hidden this, enum _IMAPI_MEDIA_PHYSICAL_TYPE)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025dd0`

## callees

- `0x180002fc8`
- `0x18000fdb0`
- `0x18000fdd4`
- `0x180011b4c`
- `0x1800140f4`
- `0x180016778`
- `0x1800170ec`
- `0x18001724c`
- `0x180023a78`
- `0x180025508`
- `0x180026860`
- `0x180026ce0`
- `0x180042430`
- `0x1800437d8`
- `0x180044254`
- `0x180046708`
- `0x180046a94`
- `0x180047598`
- `0x180048000`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180025d30`
- `ole32!CoTaskMemFree` at `0x180025d30`
- `ole32!CoCreateInstance` at `0x180025685`
- `ole32!CoCreateInstance` at `0x1800256ad`
- `ole32!CoCreateInstance` at `0x180025804`
- `ole32!CoCreateInstance` at `0x180025685`
- `ole32!CoCreateInstance` at `0x1800256ad`
- `ole32!CoCreateInstance` at `0x180025804`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Erase::EraseByWrite(
        CMsftDiscFormat2Erase *this,
        enum _IMAPI_MEDIA_PHYSICAL_TYPE a2,
        enum Imapi2Utility::_FORMAT_STATUS *a3,
        unsigned int *a4)
{
  char v6; // r12
  struct IDiscRecorder2Ex **v7; // rbx
  struct IDiscRecorder2Ex *v8; // rdx
  HRESULT DiscInformation; // edi
  struct IDiscRecorder2Ex *v10; // rcx
  bool v11; // zf
  HRESULT Instance; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int lpVtbl; // r14d
  int v16; // ecx
  int *v17; // r13
  unsigned int *v18; // rbx
  __int16 v19; // ax
  unsigned __int64 v20; // rbx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  const struct _GUID *v23; // r8
  unsigned int v24; // ebx
  Imapi2Utility::CTaskTimeEstimator *v25; // rax
  __int64 v26; // rax
  int v27; // eax
  struct IUnknown *v28; // rcx
  __int64 v29; // r9
  LPVOID v30; // rdx
  int v31; // eax
  struct IUnknown *v32; // rcx
  __int64 v33; // r9
  __int64 v34; // r8
  LPVOID v35; // rdx
  Imapi2Utility::CTaskTimeEstimator *v36; // rcx
  int v37; // eax
  int v38; // eax
  void *v39; // rcx
  void *v40; // rcx
  const struct _GUID *v41; // r8
  unsigned int v43; // [rsp+30h] [rbp-30h] BYREF
  struct IUnknown *v44; // [rsp+38h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-20h] BYREF
  LPVOID v46; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-10h] BYREF
  struct IDiscRecorder2Ex v49; // [rsp+B0h] [rbp+50h] BYREF
  struct IDiscRecorder2Ex v50; // [rsp+B8h] [rbp+58h] BYREF

  ppv = 0;
  v6 = 0;
  v46 = 0;
  v44 = 0;
  v7 = (struct IDiscRecorder2Ex **)((char *)this + 168);
  pv = 0;
  v43 = 0;
  if ( a2 == IMAPI_MEDIA_TYPE_DVDPLUSRW )
  {
    DiscInformation = CMsftDiscFormat2Erase::GetDiscInformation(
                        *v7,
                        (struct _DISC_INFORMATION **)&pv,
                        &v43,
                        (unsigned int)a4);
    if ( DiscInformation >= 0 )
    {
      if ( (*((_BYTE *)pv + 2) & 3) == 0 )
      {
LABEL_4:
        DiscInformation = 0;
        goto LABEL_122;
      }
      goto LABEL_10;
    }
  }
  else
  {
    if ( a2 != IMAPI_MEDIA_TYPE_BDRE )
      goto LABEL_10;
    v10 = *v7;
    LODWORD(v49.lpVtbl) = -1;
    DiscInformation = Imapi2Utility::GetMediaFormatStatus((Imapi2Utility *)v10, &v49, a3);
    if ( DiscInformation < 0 )
      v11 = DiscInformation == -1062600174;
    else
      v11 = ((LODWORD(v49.lpVtbl) - 1) & 0xFFFFFFFD) == 0;
    if ( v11 )
      goto LABEL_4;
    if ( DiscInformation >= 0 )
    {
LABEL_10:
      LODWORD(v50.lpVtbl) = 0;
      LODWORD(v49.lpVtbl) = 0;
      Instance = Imapi2Utility::ReadMediaCapacity((Imapi2Utility *)*v7, &v50, (unsigned int *)&v49, a4);
      DiscInformation = Instance;
      if ( Instance < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 3u )
        {
          goto LABEL_108;
        }
        v14 = 54;
        goto LABEL_71;
      }
      lpVtbl = (unsigned int)v49.lpVtbl;
      v16 = 1250;
      if ( a2 == IMAPI_MEDIA_TYPE_DVDPLUSRW && !*((_WORD *)this + 88) )
        lpVtbl = 1250;
      v17 = (int *)((char *)this + 200);
      v18 = (unsigned int *)((char *)this + 204);
      if ( lpVtbl >= 0x9C4 )
      {
        v19 = *((_WORD *)this + 88);
        *v18 = 1250;
        if ( v19 )
          v16 = lpVtbl - 1250;
      }
      else
      {
        *v18 = lpVtbl;
        v16 = lpVtbl;
      }
      *v17 = v16;
      DiscInformation = CoCreateInstance(
                          &CLSID_MsftStreamZero,
                          0,
                          0x17u,
                          &GUID_0000000c_0000_0000_c000_000000000046,
                          &ppv);
      if ( DiscInformation < 0
        || (DiscInformation = CoCreateInstance(
                                &CLSID_MsftStreamZero,
                                0,
                                0x17u,
                                &GUID_0000000c_0000_0000_c000_000000000046,
                                &v46),
            DiscInformation < 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            55,
            &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids,
            (unsigned int)DiscInformation);
        }
        goto LABEL_108;
      }
      v20 = (unsigned __int64)*((unsigned int *)this + 50) << 11;
      DiscInformation = (*(__int64 (__fastcall **)(LPVOID, unsigned __int64))(*(_QWORD *)ppv + 48LL))(ppv, v20);
      if ( DiscInformation < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 4u )
        {
          goto LABEL_108;
        }
        v22 = 56;
        goto LABEL_35;
      }
      v20 = (unsigned __int64)*((unsigned int *)this + 51) << 11;
      DiscInformation = (*(__int64 (__fastcall **)(LPVOID, unsigned __int64))(*(_QWORD *)v46 + 48LL))(v46, v20);
      if ( DiscInformation < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 4u )
        {
          goto LABEL_108;
        }
        v22 = 57;
LABEL_35:
        WPP_SF_id(v21[32], v22, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids, v20, DiscInformation);
        goto LABEL_108;
      }
      Instance = CoCreateInstance(
                   &CLSID_MsftWriteEngine2,
                   0,
                   0x17u,
                   &GUID_27354135_7f64_5b0f_8f00_5d77afbe261e,
                   (LPVOID *)&v44);
      DiscInformation = Instance;
      if ( Instance < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 3u )
        {
          goto LABEL_108;
        }
        v14 = 58;
        goto LABEL_71;
      }
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v44->lpVtbl[3].QueryInterface)(
                   v44,
                   *((_QWORD *)this + 21));
      DiscInformation = Instance;
      if ( Instance < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 3u )
        {
          goto LABEL_108;
        }
        v14 = 59;
        goto LABEL_71;
      }
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v44->lpVtbl[3].Release)(v44, 0);
      DiscInformation = Instance;
      if ( Instance < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 3u )
        {
          goto LABEL_108;
        }
        v14 = 60;
        goto LABEL_71;
      }
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v44->lpVtbl[4].AddRef)(v44, 3000);
      DiscInformation = Instance;
      if ( Instance < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 3u )
        {
          goto LABEL_108;
        }
        v14 = 61;
        goto LABEL_71;
      }
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v44->lpVtbl[5].QueryInterface)(v44, 3000);
      DiscInformation = Instance;
      if ( Instance < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 3u )
        {
          goto LABEL_108;
        }
        v14 = 62;
        goto LABEL_71;
      }
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v44->lpVtbl[5].Release)(v44, 2048);
      DiscInformation = Instance;
      if ( Instance < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 3u )
        {
          goto LABEL_108;
        }
        v14 = 63;
        goto LABEL_71;
      }
      if ( *((_DWORD *)this + 23) != -16843010 )
        ATL::AtlThrowImpl(-2147467259);
      Instance = ATL::AtlAdvise(v44, (struct IUnknown *)this + 6, v23, (unsigned int *)this + 23);
      DiscInformation = Instance;
      if ( Instance < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 265) < 3u )
        {
          goto LABEL_108;
        }
        v14 = 64;
        goto LABEL_71;
      }
      LODWORD(v49.lpVtbl) = 0;
      LODWORD(v50.lpVtbl) = 0;
      v24 = 15000;
      DiscInformation = CMsftDiscFormat2Erase::EstimateEraseTimesForEraseByWriteMedia(
                          this,
                          a2,
                          (unsigned int *)&v49,
                          (unsigned int *)&v50);
      if ( DiscInformation >= 0 )
      {
        v24 = (unsigned int)v49.lpVtbl;
        if ( *((_WORD *)this + 88) )
          v24 = (unsigned int)v50.lpVtbl;
      }
      v25 = (Imapi2Utility::CTaskTimeEstimator *)operator new(0x3Cu);
      if ( v25 )
        v26 = Imapi2Utility::CTaskTimeEstimator::CTaskTimeEstimator(
                v25,
                v24,
                *((_DWORD *)this + 50) + *((_DWORD *)this + 51));
      else
        v26 = 0;
      *((_QWORD *)this + 24) = v26;
      if ( v26 )
      {
        if ( DiscInformation < 0 )
        {
          v6 = 1;
          goto LABEL_108;
        }
        v27 = Imapi2Utility::RequestAutomaticOPC(*((Imapi2Utility **)this + 21), v8);
        if ( v27 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            66,
            &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids,
            (unsigned int)v27);
        }
        Imapi2Utility::CTaskTimeEstimator::StartNow(*((Imapi2Utility::CTaskTimeEstimator **)this + 24));
        v28 = v44;
        v29 = (unsigned int)*v17;
        v30 = ppv;
        *((_BYTE *)this + 208) = 1;
        v31 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, _QWORD, __int64))v28->lpVtbl[2].AddRef)(
                v28,
                v30,
                0,
                v29);
        DiscInformation = v31;
        if ( v31 >= 0 )
        {
          v32 = v44;
          v33 = *((unsigned int *)this + 51);
          v34 = lpVtbl - *((_DWORD *)this + 51);
          v35 = v46;
          *((_BYTE *)this + 208) = 0;
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, __int64, __int64))v32->lpVtbl[2].AddRef)(
                       v32,
                       v35,
                       v34,
                       v33);
          DiscInformation = Instance;
          v6 = 1;
          if ( Instance >= 0 )
            goto LABEL_108;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 265) < 3u )
          {
            goto LABEL_108;
          }
          v14 = 68;
LABEL_71:
          WPP_SF_d(v13[32], v14, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids, (unsigned int)Instance);
          goto LABEL_108;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            67,
            &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids,
            (unsigned int)v31);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 65, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids);
        }
        DiscInformation = -2147024882;
      }
      v6 = 1;
    }
  }
LABEL_108:
  v36 = (Imapi2Utility::CTaskTimeEstimator *)*((_QWORD *)this + 24);
  if ( v36 )
    Imapi2Utility::CTaskTimeEstimator::EndNow(v36);
  if ( DiscInformation >= 0 )
  {
    v37 = Imapi2Utility::SendSynchronizeCacheCommand(*((Imapi2Utility **)this + 21), v8, 0, (unsigned __int8)a4);
    DiscInformation = v37;
    if ( v37 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        69,
        &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids,
        (unsigned int)v37);
    }
  }
  if ( v6 )
  {
    v38 = ATL::AtlUnadvise(v44, (const struct _GUID *)v8, *((_DWORD *)this + 23));
    *((_DWORD *)this + 23) = -16843010;
    if ( v38 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        70,
        &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids,
        (unsigned int)v38);
    }
  }
LABEL_122:
  v39 = (void *)*((_QWORD *)this + 24);
  if ( v39 )
    operator delete(v39);
  v40 = pv;
  *((_QWORD *)this + 24) = 0;
  CoTaskMemFree(v40);
  pv = 0;
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v44 )
  {
    ((void (__fastcall *)(struct IUnknown *))v44->lpVtbl->Release)(v44);
    v44 = 0;
  }
  if ( (DiscInformation & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(DiscInformation, (int)&CLSID_MsftDiscFormat2Erase, v41);
  return (unsigned int)DiscInformation;
}

```

## disassembly

```asm
0x180025508  mov     [rsp-38h+arg_0], rbx
0x18002550d  mov     [rsp-38h+arg_8], edx
0x180025511  push    rbp
0x180025512  push    rsi
0x180025513  push    rdi
0x180025514  push    r12
0x180025516  push    r13
0x180025518  push    r14
0x18002551a  push    r15
0x18002551c  mov     rbp, rsp
0x18002551f  sub     rsp, 60h
0x180025523  mov     rsi, rcx
0x180025526  mov     r15d, edx
0x180025529  xor     ecx, ecx
0x18002552b  mov     [rbp+var_20], rcx
0x18002552f  mov     r12b, cl
0x180025532  mov     [rbp+var_18], rcx
0x180025536  mov     [rbp+var_28], rcx
0x18002553a  lea     rbx, [rsi+0A8h]
0x180025541  mov     [rbp+pv], rcx
0x180025545  mov     [rbp+var_30], ecx
0x180025548  cmp     edx, 7
0x18002554b  jnz     short loc_18002557A
0x18002554d  mov     rcx, [rbx]; struct IDiscRecorder2Ex *
0x180025550  lea     r8, [rbp+var_30]; unsigned int *
0x180025554  lea     rdx, [rbp+pv]; struct _DISC_INFORMATION **
0x180025558  call    ?GetDiscInformation@CMsftDiscFormat2Erase@@CAJPEAUIDiscRecorder2Ex@@PEAPEAU_DISC_INFORMATION@@PEAKK@Z; CMsftDiscFormat2Erase::GetDiscInformation(IDiscRecorder2Ex *,_DISC_INFORMATION * *,ulong *,ulong)
0x18002555d  xor     ecx, ecx
0x18002555f  mov     edi, eax
0x180025561  test    eax, eax
0x180025563  js      loc_180025C50
0x180025569  mov     rax, [rbp+pv]
0x18002556d  test    byte ptr [rax+2], 3
0x180025571  jnz     short loc_1800255AF
0x180025573  mov     edi, ecx
0x180025575  jmp     loc_180025D10
0x18002557a  cmp     r15d, 13h
0x18002557e  jnz     short loc_1800255AF
0x180025580  mov     rcx, [rbx]; this
0x180025583  lea     rdx, [rbp+arg_10]; struct IDiscRecorder2Ex *
0x180025587  mov     dword ptr [rbp+arg_10.lpVtbl], 0FFFFFFFFh
0x18002558e  call    ?GetMediaFormatStatus@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_FORMAT_STATUS@1@@Z; Imapi2Utility::GetMediaFormatStatus(IDiscRecorder2Ex *,Imapi2Utility::_FORMAT_STATUS *)
0x180025593  xor     ecx, ecx
0x180025595  mov     edi, eax
0x180025597  test    eax, eax
0x180025599  js      short loc_180025606
0x18002559b  mov     eax, dword ptr [rbp+arg_10.lpVtbl]
0x18002559e  dec     eax
0x1800255a0  test    eax, 0FFFFFFFDh
0x1800255a5  jz      short loc_180025573
0x1800255a7  test    edi, edi
0x1800255a9  js      loc_180025C50
0x1800255af  mov     dword ptr [rbp+arg_18.lpVtbl], ecx
0x1800255b2  lea     r8, [rbp+arg_10]; unsigned int *
0x1800255b6  mov     dword ptr [rbp+arg_10.lpVtbl], ecx
0x1800255b9  lea     rdx, [rbp+arg_18]; struct IDiscRecorder2Ex *
0x1800255bd  mov     rcx, [rbx]; this
0x1800255c0  call    ?ReadMediaCapacity@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAK1@Z; Imapi2Utility::ReadMediaCapacity(IDiscRecorder2Ex *,ulong *,ulong *)
0x1800255c5  mov     edi, eax
0x1800255c7  test    eax, eax
0x1800255c9  jns     short loc_18002560E
0x1800255cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255d2  lea     rbx, WPP_GLOBAL_Control
0x1800255d9  cmp     rcx, rbx
0x1800255dc  jz      loc_180025C57
0x1800255e2  test    byte ptr [rcx+10Ch], 4
0x1800255e9  jz      loc_180025C57
0x1800255ef  cmp     byte ptr [rcx+109h], 3
0x1800255f6  jb      loc_180025C57
0x1800255fc  mov     edx, 36h ; '6'
0x180025601  jmp     loc_1800259F2
0x180025606  cmp     edi, 0C0AA0212h
0x18002560c  jmp     short loc_1800255A5
0x18002560e  mov     r14d, dword ptr [rbp+arg_10.lpVtbl]
0x180025612  mov     ecx, 4E2h
0x180025617  cmp     r15d, 7
0x18002561b  jnz     short loc_18002562A
0x18002561d  xor     edi, edi
0x18002561f  cmp     [rsi+0B0h], di
0x180025626  cmovz   r14d, ecx
0x18002562a  lea     r13, [rsi+0C8h]
0x180025631  lea     rbx, [rsi+0CCh]
0x180025638  cmp     r14d, 9C4h
0x18002563f  jnb     short loc_180025649
0x180025641  mov     [rbx], r14d
0x180025644  mov     ecx, r14d
0x180025647  jmp     short loc_18002565E
0x180025649  movzx   eax, word ptr [rsi+0B0h]
0x180025650  mov     [rbx], ecx
0x180025652  test    ax, ax
0x180025655  jz      short loc_18002565E
0x180025657  lea     ecx, [r14-4E2h]
0x18002565e  mov     rax, r13
0x180025661  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x180025668  mov     r15d, 17h
0x18002566e  xor     edx, edx; pUnkOuter
0x180025670  mov     r8d, r15d; dwClsContext
0x180025673  mov     [rax], ecx
0x180025675  lea     rax, [rbp+var_20]
0x180025679  lea     rcx, CLSID_MsftStreamZero; rclsid
0x180025680  mov     [rsp+60h+ppv], rax; ppv
0x180025685  call    cs:__imp_CoCreateInstance
0x18002568b  mov     edi, eax
0x18002568d  test    eax, eax
0x18002568f  js      short loc_1800256C1
0x180025691  lea     rax, [rbp+var_18]
0x180025695  mov     r8d, r15d; dwClsContext
0x180025698  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x18002569f  mov     [rsp+60h+ppv], rax; ppv
0x1800256a4  xor     edx, edx; pUnkOuter
0x1800256a6  lea     rcx, CLSID_MsftStreamZero; rclsid
0x1800256ad  call    cs:__imp_CoCreateInstance
0x1800256b3  mov     edi, eax
0x1800256b5  test    eax, eax
0x1800256b7  js      short loc_1800256C1
0x1800256b9  mov     r15, rbx
0x1800256bc  mov     rax, r13
0x1800256bf  jmp     short loc_18002571B
0x1800256c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256c8  lea     rbx, WPP_GLOBAL_Control
0x1800256cf  cmp     rcx, rbx
0x1800256d2  jz      loc_180025C57
0x1800256d8  test    byte ptr [rcx+10Ch], 4
0x1800256df  jz      short loc_180025705
0x1800256e1  cmp     byte ptr [rcx+109h], 3
0x1800256e8  jb      short loc_180025705
0x1800256ea  mov     rcx, [rcx+100h]
0x1800256f1  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x1800256f8  mov     edx, 37h ; '7'
0x1800256fd  mov     r9d, edi
0x180025700  call    WPP_SF_d
0x180025705  test    edi, edi
0x180025707  js      loc_180025C57
0x18002570d  lea     rax, [rsi+0C8h]
0x180025714  lea     r15, [rsi+0CCh]
0x18002571b  mov     ebx, [rax]
0x18002571d  mov     rcx, [rbp+var_20]
0x180025721  shl     rbx, 0Bh
0x180025725  mov     rdx, rbx
0x180025728  mov     rax, [rcx]
0x18002572b  mov     rax, [rax+30h]
0x18002572f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025734  mov     edi, eax
0x180025736  test    eax, eax
0x180025738  jns     short loc_18002578F
0x18002573a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025741  lea     rax, WPP_GLOBAL_Control
0x180025748  cmp     rcx, rax
0x18002574b  jz      loc_180025C50
0x180025751  test    byte ptr [rcx+10Ch], 4
0x180025758  jz      loc_180025C50
0x18002575e  cmp     byte ptr [rcx+109h], 4
0x180025765  jb      loc_180025C50
0x18002576b  mov     edx, 38h ; '8'
0x180025770  mov     rcx, [rcx+100h]
0x180025777  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x18002577e  mov     r9, rbx
0x180025781  mov     dword ptr [rsp+60h+ppv], edi
0x180025785  call    WPP_SF_id
0x18002578a  jmp     loc_180025C50
0x18002578f  mov     rcx, [rbp+var_18]
0x180025793  mov     ebx, [r15]
0x180025796  shl     rbx, 0Bh
0x18002579a  mov     rdx, rbx
0x18002579d  mov     rax, [rcx]
0x1800257a0  mov     rax, [rax+30h]
0x1800257a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257a9  mov     edi, eax
0x1800257ab  test    eax, eax
0x1800257ad  jns     short loc_1800257E7
0x1800257af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257b6  lea     rax, WPP_GLOBAL_Control
0x1800257bd  cmp     rcx, rax
0x1800257c0  jz      loc_180025C50
0x1800257c6  test    byte ptr [rcx+10Ch], 4
0x1800257cd  jz      loc_180025C50
0x1800257d3  cmp     byte ptr [rcx+109h], 4
0x1800257da  jb      loc_180025C50
0x1800257e0  mov     edx, 39h ; '9'
0x1800257e5  jmp     short loc_180025770
0x1800257e7  xor     edx, edx; pUnkOuter
0x1800257e9  lea     rax, [rbp+var_28]
0x1800257ed  lea     r9, _GUID_27354135_7f64_5b0f_8f00_5d77afbe261e; riid
0x1800257f4  mov     [rsp+60h+ppv], rax; ppv
0x1800257f9  lea     rcx, CLSID_MsftWriteEngine2; rclsid
0x180025800  lea     r8d, [rdx+17h]; dwClsContext
0x180025804  call    cs:__imp_CoCreateInstance
0x18002580a  mov     edi, eax
0x18002580c  test    eax, eax
0x18002580e  jns     short loc_18002584B
0x180025810  mov     rcx, cs:WPP_GLOBAL_Control
0x180025817  lea     rbx, WPP_GLOBAL_Control
0x18002581e  cmp     rcx, rbx
0x180025821  jz      loc_180025C57
0x180025827  test    byte ptr [rcx+10Ch], 4
0x18002582e  jz      loc_180025C57
0x180025834  cmp     byte ptr [rcx+109h], 3
0x18002583b  jb      loc_180025C57
0x180025841  mov     edx, 3Ah ; ':'
0x180025846  jmp     loc_1800259F2
0x18002584b  mov     rcx, [rbp+var_28]
0x18002584f  mov     rdx, [rsi+0A8h]
0x180025856  mov     rax, [rcx]
0x180025859  mov     rax, [rax+48h]
0x18002585d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025862  mov     edi, eax
0x180025864  test    eax, eax
0x180025866  jns     short loc_1800258A3
0x180025868  mov     rcx, cs:WPP_GLOBAL_Control
0x18002586f  lea     rbx, WPP_GLOBAL_Control
0x180025876  cmp     rcx, rbx
0x180025879  jz      loc_180025C57
0x18002587f  test    byte ptr [rcx+10Ch], 4
0x180025886  jz      loc_180025C57
0x18002588c  cmp     byte ptr [rcx+109h], 3
0x180025893  jb      loc_180025C57
0x180025899  mov     edx, 3Bh ; ';'
0x18002589e  jmp     loc_1800259F2
0x1800258a3  mov     rcx, [rbp+var_28]
0x1800258a7  xor     edx, edx
0x1800258a9  mov     rax, [rcx]
0x1800258ac  mov     rax, [rax+58h]
0x1800258b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258b5  mov     edi, eax
0x1800258b7  test    eax, eax
0x1800258b9  jns     short loc_1800258F6
0x1800258bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258c2  lea     rbx, WPP_GLOBAL_Control
0x1800258c9  cmp     rcx, rbx
0x1800258cc  jz      loc_180025C57
0x1800258d2  test    byte ptr [rcx+10Ch], 4
0x1800258d9  jz      loc_180025C57
0x1800258df  cmp     byte ptr [rcx+109h], 3
0x1800258e6  jb      loc_180025C57
0x1800258ec  mov     edx, 3Ch ; '<'
0x1800258f1  jmp     loc_1800259F2
0x1800258f6  mov     rcx, [rbp+var_28]
0x1800258fa  mov     ebx, 0BB8h
0x1800258ff  mov     edx, ebx
0x180025901  mov     rax, [rcx]
0x180025904  mov     rax, [rax+68h]
0x180025908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002590d  mov     edi, eax
0x18002590f  test    eax, eax
0x180025911  jns     short loc_18002594E
0x180025913  mov     rcx, cs:WPP_GLOBAL_Control
0x18002591a  lea     rbx, WPP_GLOBAL_Control
0x180025921  cmp     rcx, rbx
0x180025924  jz      loc_180025C57
0x18002592a  test    byte ptr [rcx+10Ch], 4
0x180025931  jz      loc_180025C57
0x180025937  cmp     byte ptr [rcx+109h], 3
0x18002593e  jb      loc_180025C57
0x180025944  mov     edx, 3Dh ; '='
0x180025949  jmp     loc_1800259F2
0x18002594e  mov     rcx, [rbp+var_28]
0x180025952  mov     edx, ebx
0x180025954  mov     rax, [rcx]
0x180025957  mov     rax, [rax+78h]
0x18002595b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025960  mov     edi, eax
0x180025962  test    eax, eax
0x180025964  jns     short loc_18002599E
0x180025966  mov     rcx, cs:WPP_GLOBAL_Control
0x18002596d  lea     rbx, WPP_GLOBAL_Control
0x180025974  cmp     rcx, rbx
0x180025977  jz      loc_180025C57
0x18002597d  test    byte ptr [rcx+10Ch], 4
0x180025984  jz      loc_180025C57
0x18002598a  cmp     byte ptr [rcx+109h], 3
0x180025991  jb      loc_180025C57
0x180025997  mov     edx, 3Eh ; '>'
0x18002599c  jmp     short loc_1800259F2
0x18002599e  mov     rcx, [rbp+var_28]
0x1800259a2  mov     edx, 800h
0x1800259a7  mov     rax, [rcx]
0x1800259aa  mov     rax, [rax+88h]
0x1800259b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259b6  mov     edi, eax
0x1800259b8  test    eax, eax
0x1800259ba  jns     short loc_180025A0D
0x1800259bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259c3  lea     rbx, WPP_GLOBAL_Control
0x1800259ca  cmp     rcx, rbx
0x1800259cd  jz      loc_180025C57
0x1800259d3  test    byte ptr [rcx+10Ch], 4
0x1800259da  jz      loc_180025C57
0x1800259e0  cmp     byte ptr [rcx+109h], 3
0x1800259e7  jb      loc_180025C57
0x1800259ed  mov     edx, 3Fh ; '?'
0x1800259f2  mov     rcx, [rcx+100h]
0x1800259f9  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x180025a00  mov     r9d, eax
0x180025a03  call    WPP_SF_d
0x180025a08  jmp     loc_180025C57
0x180025a0d  lea     rdx, [rsi+30h]; struct IUnknown *
0x180025a11  lea     r9, [rdx+2Ch]; unsigned int *
0x180025a15  cmp     dword ptr [r9], 0FEFEFEFEh
0x180025a1c  jnz     loc_180025DBD
0x180025a22  mov     rcx, [rbp+var_28]; struct IUnknown *
  ... truncated ...
```
