# CMSDiscMasterObj::RecordDisc(uchar,uchar)

- ea: `0x18000d830`
- end: `0x18000e0d2`
- name: `?RecordDisc@CMSDiscMasterObj@@UEAAJEE@Z`
- size: `2210`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *__hidden this, unsigned __int8, unsigned __int8)`
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002ac4`
- `0x18000701c`
- `0x180007bd4`
- `0x180007c60`
- `0x180007d80`
- `0x180007dd0`
- `0x18000b0b4`
- `0x18000b4b0`
- `0x18000b578`
- `0x18000c330`
- `0x18000c69c`
- `0x18000d830`
- `0x180010aac`
- `0x1800127ec`
- `0x180013108`
- `0x180013dcc`
- `0x180013f44`
- `0x1800140ac`
- `0x1800168f8`
- `0x180019010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000dc15`
- `ole32!CoCreateInstance` at `0x18000dc15`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dc62`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dc62`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d981`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dce3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dfad`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d981`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dce3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dfad`
- `KERNEL32!ResetEvent` at `0x18000da11`
- `KERNEL32!ResetEvent` at `0x18000de97`
- `KERNEL32!ResetEvent` at `0x18000da11`
- `KERNEL32!ResetEvent` at `0x18000de97`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::RecordDisc(CMSDiscMasterObj *this, unsigned __int8 a2, unsigned __int8 a3)
{
  char v3; // r12
  char v6; // r14
  char v7; // r15
  bool v8; // si
  int WritableDisc; // edi
  int v10; // edi
  __int64 *LastComError; // rax
  __int64 v12; // rcx
  int v13; // eax
  void *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  int v24; // r14d
  struct IUnknown **v25; // r15
  HRESULT Instance; // eax
  OLECHAR *v27; // rax
  struct IUnknown *v28; // rcx
  int v29; // edi
  __int64 *v30; // rax
  int v31; // eax
  int v32; // edx
  __int64 v33; // rdx
  OLECHAR *v34; // rcx
  int v35; // eax
  OLECHAR *v36; // rcx
  void *v37; // rcx
  __int64 v38; // rcx
  int v39; // edi
  __int64 v40; // rcx
  _BYTE v42[7]; // [rsp+31h] [rbp-3Fh] BYREF
  BSTR v43; // [rsp+38h] [rbp-38h] BYREF
  struct IFileSystemImageResult *v44; // [rsp+40h] [rbp-30h] BYREF
  int v45; // [rsp+48h] [rbp-28h] BYREF
  unsigned int v46; // [rsp+4Ch] [rbp-24h] BYREF
  __int64 v47; // [rsp+50h] [rbp-20h] BYREF
  int v48; // [rsp+58h] [rbp-18h] BYREF
  int v49; // [rsp+5Ch] [rbp-14h] BYREF
  BSTR v50; // [rsp+60h] [rbp-10h]
  BSTR bstrString; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  LODWORD(bstrString) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids, this, a2, a3);
  LOBYTE(bstrString) = 0;
  v48 = 0;
  v6 = 0;
  v45 = 0;
  v7 = 0;
  v50 = 0;
  v8 = 0;
  v47 = 0;
  v44 = 0;
  WritableDisc = CMSDiscMasterObj::IsCallLegal(this, 717);
  if ( WritableDisc >= 0 )
  {
    if ( *((_BYTE *)this + 184) )
    {
      WritableDisc = -2147220973;
      goto LABEL_108;
    }
    if ( *(_QWORD *)&IID_IJolietDiscMaster.Data1 == *(_QWORD *)((char *)this + 356)
      && *(_QWORD *)IID_IJolietDiscMaster.Data4 == *(_QWORD *)((char *)this + 364) )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, struct IFileSystemImageResult **))(**((_QWORD **)this + 61) + 312LL))(
              *((_QWORD *)this + 61),
              &v44);
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          LastComError = (__int64 *)GetLastComError(&bstrString);
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            65,
            (unsigned int)&WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
            v10,
            *LastComError);
          v3 = 1;
        }
        if ( (v3 & 1) != 0 )
          SysFreeString(bstrString);
        v12 = (unsigned int)v10;
        goto LABEL_16;
      }
      if ( *((_DWORD *)this + 126) > 1u
        && *((_BYTE *)this + 508)
        && !CMSDiscMasterObj::IsSameMultiSessionJolietDiscStillPresent(this, v44) )
      {
        WritableDisc = -2147220957;
        goto LABEL_108;
      }
      v13 = ((__int64 (__fastcall *)(struct IFileSystemImageResult *, __int64 *))v44->lpVtbl->get_ImageStream)(
              v44,
              &v47);
      if ( v13 < 0 )
      {
        v12 = (unsigned int)v13;
LABEL_16:
        WritableDisc = TranslateIMAPI2Error(v12);
        goto LABEL_108;
      }
LABEL_25:
      v14 = (void *)*((_QWORD *)this + 53);
      if ( v14 )
        ResetEvent(v14);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          66,
          &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
          *((unsigned int *)this + 126));
      if ( *((_DWORD *)this + 51) )
      {
        *((_DWORD *)this + 73) |= 0x1000u;
        *((_DWORD *)this + 77) = 3;
      }
      CMyUpdateList::UpdateAll((CMSDiscMasterObj *)((char *)this + 192));
      LOBYTE(v15) = 1;
      v16 = WriterOpenExclusive(*((_QWORD *)this + 60), v15);
      WritableDisc = v16;
      if ( v16 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_37;
        v19 = 67;
LABEL_36:
        WPP_SF_d(v18[7], v19, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids, (unsigned int)v16);
LABEL_37:
        v7 = 0;
        goto LABEL_108;
      }
      v6 = 1;
      LOBYTE(v17) = 1;
      v16 = WriterLockTray(*((_QWORD *)this + 60), v17);
      WritableDisc = v16;
      if ( v16 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_37;
        v19 = 68;
        goto LABEL_36;
      }
      v8 = (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 59) + 96LL))(*((_QWORD *)this + 59)) >= 0;
      v20 = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(**((_QWORD **)this + 59) + 104LL))(
              *((_QWORD *)this + 59),
              &v48,
              &v45);
      WritableDisc = v20;
      if ( v20 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_47;
        v22 = 69;
        v23 = (unsigned int)v20;
        goto LABEL_46;
      }
      if ( (v45 & 8) != 0 )
      {
        WritableDisc = -2147220976;
LABEL_50:
        v7 = 0;
        goto LABEL_108;
      }
      WritableDisc = WriterLoadWritableDisc(*((_QWORD *)this + 60), *((unsigned int *)this + 126));
      if ( WritableDisc < 0 )
      {
        WritableDisc = -2147220976;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_47;
        v22 = 70;
        v23 = 2147746320LL;
LABEL_46:
        WPP_SF_d(v21[7], v22, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids, v23);
LABEL_47:
        v7 = (char)bstrString;
        goto LABEL_108;
      }
      v24 = 0;
      if ( *(_QWORD *)&IID_IJolietDiscMaster.Data1 != *(_QWORD *)((char *)this + 356)
        || *(_QWORD *)IID_IJolietDiscMaster.Data4 != *(_QWORD *)((char *)this + 364) )
      {
        if ( *(_QWORD *)&IID_IRedbookDiscMaster.Data1 == *(_QWORD *)((char *)this + 356)
          && *(_QWORD *)IID_IRedbookDiscMaster.Data4 == *(_QWORD *)((char *)this + 364) )
        {
          v42[0] = 0;
          LODWORD(v43) = 0;
          v49 = 0;
          v38 = *((_QWORD *)this + 60);
          v39 = 135;
          v46 = 1;
          if ( (int)WriterGetCaps(v38, v42, (unsigned int *)&v43, &v46, &v49) >= 0 && v46 )
            v39 = 0xF0 / v46 + 10;
          WritableDisc = CRedbookTracks::RecordDisc(
                           (CMSDiscMasterObj *)((char *)this + 512),
                           **((struct IDiscRecorder2 ***)this + 60),
                           (CMSDiscMasterObj *)((char *)this + 192),
                           v39);
          if ( WritableDisc < 0 )
          {
            v6 = 1;
            goto LABEL_50;
          }
        }
        goto LABEL_92;
      }
      v25 = (struct IUnknown **)((char *)this + 464);
      Instance = CoCreateInstance(
                   &GUID_2735412a_7f64_5b0f_8f00_5d77afbe261e,
                   0,
                   0x17u,
                   &GUID_27354153_9f64_5b0f_8f00_5d77afbe261e,
                   (LPVOID *)this + 58);
      WritableDisc = Instance;
      if ( Instance < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            71,
            &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
            (unsigned int)Instance);
LABEL_61:
        v6 = 1;
        goto LABEL_47;
      }
      v27 = SysAllocString(L"IMAPIv1 Shim");
      v28 = *v25;
      v50 = v27;
      v29 = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *))v28->lpVtbl[10].QueryInterface)(v28, v27);
      if ( v29 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v30 = (__int64 *)GetLastComError(&v43);
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            72,
            (unsigned int)&WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
            v29,
            *v30);
          v3 = 2;
        }
        if ( (v3 & 2) != 0 )
          SysFreeString(v43);
        v6 = 1;
        WritableDisc = TranslateIMAPI2Error((unsigned int)v29);
LABEL_69:
        v7 = (char)bstrString;
        goto LABEL_108;
      }
      v31 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))(*v25)->lpVtbl[4].QueryInterface)(
              *v25,
              **((_QWORD **)this + 60));
      WritableDisc = v31;
      if ( v31 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            73,
            &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
            (unsigned int)v31);
        WritableDisc = -2147220972;
        goto LABEL_61;
      }
      v32 = *(_DWORD *)(*((_QWORD *)this + 60) + 36LL);
      if ( v32 )
      {
        if ( v32 != 1 )
        {
LABEL_80:
          if ( *((_DWORD *)this + 17) != -16843010 )
            ATL::AtlThrowImpl(-2147467259);
          ATL::AtlAdvise(*v25, (struct IUnknown *)this + 3, &IID_DDiscFormat2DataEvents, (unsigned int *)this + 17);
          LOBYTE(bstrString) = 1;
          if ( !a2 )
          {
            v34 = (OLECHAR *)*((_QWORD *)this + 59);
            v43 = v34;
            if ( v34 )
              (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v34 + 8LL))(v34);
            *(_BYTE *)(GetInternalClassPtr<IDiscRecorder,CMSDiscRecorderObj>(&v43) + 149) = 1;
            v35 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))(*v25)->lpVtbl[13].Release)(*v25, v47);
            v24 = v35;
            if ( v35 < 0 )
            {
              v24 = TranslateIMAPI2Error((unsigned int)v35);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  74,
                  &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
                  (unsigned int)v24);
              }
            }
            v36 = (OLECHAR *)*((_QWORD *)this + 59);
            v43 = v36;
            if ( v36 )
              (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v36 + 8LL))(v36);
            *(_BYTE *)(GetInternalClassPtr<IDiscRecorder,CMSDiscRecorderObj>(&v43) + 149) = 0;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
          v47 = 0;
          ((void (__fastcall *)(struct IFileSystemImageResult *))v44->lpVtbl->Release)(v44);
          v44 = 0;
LABEL_92:
          v37 = (void *)*((_QWORD *)this + 53);
          if ( v37 )
            ResetEvent(v37);
          if ( v24 >= 0 )
            v24 = WritableDisc;
          WritableDisc = v24;
          if ( a3 )
          {
            WriterLockTray(*((_QWORD *)this + 60), 0);
            WriterOpenExclusive(*((_QWORD *)this + 60), 0);
            v6 = 0;
            (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 60) + 56LL))(**((_QWORD **)this + 60));
          }
          else
          {
            v6 = 1;
          }
          (*(void (__fastcall **)(CMSDiscMasterObj *))(*(_QWORD *)this + 80LL))(this);
          goto LABEL_69;
        }
        v33 = 0;
      }
      else
      {
        v33 = 0xFFFFFFFFLL;
      }
      ((void (__fastcall *)(struct IUnknown *, __int64))(*v25)->lpVtbl[4].Release)(*v25, v33);
      goto LABEL_80;
    }
    if ( *(_QWORD *)&IID_IRedbookDiscMaster.Data1 == *(_QWORD *)((char *)this + 356)
      && *(_QWORD *)IID_IRedbookDiscMaster.Data4 == *(_QWORD *)((char *)this + 364) )
    {
      goto LABEL_25;
    }
    WritableDisc = -2147467263;
  }
LABEL_108:
  SysFreeString(v50);
  if ( v8 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 59) + 136LL))(*((_QWORD *)this + 59));
  if ( v7 )
  {
    ATL::AtlUnadvise(*((struct IUnknown **)this + 58), &IID_DDiscFormat2DataEvents, *((_DWORD *)this + 17));
    *((_DWORD *)this + 17) = -16843010;
  }
  if ( v6 )
  {
    WriterLockTray(*((_QWORD *)this + 60), 0);
    WriterOpenExclusive(*((_QWORD *)this + 60), 0);
  }
  v40 = *((_QWORD *)this + 58);
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    *((_QWORD *)this + 58) = 0;
  }
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v44 )
    ((void (__fastcall *)(struct IFileSystemImageResult *))v44->lpVtbl->Release)(v44);
  if ( *((_DWORD *)this + 51) )
  {
    *((_DWORD *)this + 73) |= 0x4000u;
    *((_DWORD *)this + 82) = WritableDisc;
  }
  CMyUpdateList::UpdateAll((CMSDiscMasterObj *)((char *)this + 192));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      75,
      &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
      this,
      WritableDisc);
  return (unsigned int)WritableDisc;
}

```

## disassembly

```asm
0x18000d830  mov     [rsp-38h+arg_0], rbx
0x18000d835  mov     [rsp-38h+arg_10], r8b
0x18000d83a  push    rbp
0x18000d83b  push    rsi
0x18000d83c  push    rdi
0x18000d83d  push    r12
0x18000d83f  push    r13
0x18000d841  push    r14
0x18000d843  push    r15
0x18000d845  mov     rbp, rsp
0x18000d848  sub     rsp, 70h
0x18000d84c  xor     edi, edi
0x18000d84e  movzx   eax, r8b
0x18000d852  mov     r12d, edi
0x18000d855  mov     dword ptr [rbp+bstrString], edi
0x18000d858  movzx   r13d, dl
0x18000d85c  mov     rbx, rcx
0x18000d85f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d866  lea     rdx, WPP_GLOBAL_Control
0x18000d86d  cmp     rcx, rdx
0x18000d870  jz      short loc_18000D897
0x18000d872  test    byte ptr [rcx+44h], 1
0x18000d876  jz      short loc_18000D897
0x18000d878  mov     rcx, [rcx+38h]
0x18000d87c  lea     edx, [rdi+40h]
0x18000d87f  mov     [rsp+70h+var_48], eax
0x18000d883  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000d88a  mov     r9, rbx
0x18000d88d  mov     dword ptr [rsp+70h+ppv], r13d
0x18000d892  call    WPP_SF_qDD
0x18000d897  mov     edx, 2CDh; unsigned int
0x18000d89c  mov     byte ptr [rbp+bstrString], dil
0x18000d8a0  mov     rcx, rbx; this
0x18000d8a3  mov     [rbp+var_18], edi
0x18000d8a6  mov     r14b, dil
0x18000d8a9  mov     [rbp+var_28], edi
0x18000d8ac  mov     r15b, dil
0x18000d8af  mov     [rbp+var_10], rdi
0x18000d8b3  mov     sil, dil
0x18000d8b6  mov     [rbp+var_20], rdi
0x18000d8ba  mov     [rbp+var_30], rdi
0x18000d8be  call    ?IsCallLegal@CMSDiscMasterObj@@AEAAJK@Z; CMSDiscMasterObj::IsCallLegal(ulong)
0x18000d8c3  mov     edi, eax
0x18000d8c5  test    eax, eax
0x18000d8c7  js      loc_18000DFA2
0x18000d8cd  cmp     [rbx+0B8h], sil
0x18000d8d4  jz      short loc_18000D8E0
0x18000d8d6  mov     edi, 80040213h
0x18000d8db  jmp     loc_18000DFA2
0x18000d8e0  mov     rax, qword ptr cs:IID_IJolietDiscMaster.Data1
0x18000d8e7  cmp     rax, [rbx+164h]
0x18000d8ee  jnz     loc_18000D9DD
0x18000d8f4  mov     rax, qword ptr cs:IID_IJolietDiscMaster.Data4
0x18000d8fb  cmp     rax, [rbx+16Ch]
0x18000d902  jnz     loc_18000D9DD
0x18000d908  mov     rcx, [rbx+1E8h]
0x18000d90f  lea     rdx, [rbp+var_30]
0x18000d913  mov     rax, [rcx]
0x18000d916  mov     rax, [rax+138h]
0x18000d91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d922  mov     edi, eax
0x18000d924  test    eax, eax
0x18000d926  jns     short loc_18000D995
0x18000d928  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d92f  lea     rax, WPP_GLOBAL_Control
0x18000d936  cmp     rcx, rax
0x18000d939  jz      short loc_18000D977
0x18000d93b  test    byte ptr [rcx+44h], 1
0x18000d93f  jz      short loc_18000D977
0x18000d941  lea     rcx, [rbp+bstrString]
0x18000d945  call    ?GetLastComError@@YA?AVCComBSTR@ATL@@XZ; GetLastComError(void)
0x18000d94a  mov     edx, 41h ; 'A'
0x18000d94f  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000d956  mov     r9d, edi
0x18000d959  mov     rcx, [rax]
0x18000d95c  mov     [rsp+70h+ppv], rcx
0x18000d961  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d968  mov     rcx, [rcx+38h]
0x18000d96c  call    WPP_SF_DS
0x18000d971  mov     r12d, 1
0x18000d977  test    r12b, 1
0x18000d97b  jz      short loc_18000D987
0x18000d97d  mov     rcx, [rbp+bstrString]; bstrString
0x18000d981  call    cs:__imp_SysFreeString
0x18000d987  mov     ecx, edi
0x18000d989  call    TranslateIMAPI2Error
0x18000d98e  mov     edi, eax
0x18000d990  jmp     loc_18000DFA2
0x18000d995  cmp     dword ptr [rbx+1F8h], 1
0x18000d99c  jbe     short loc_18000D9C1
0x18000d99e  cmp     [rbx+1FCh], sil
0x18000d9a5  jz      short loc_18000D9C1
0x18000d9a7  mov     rdx, [rbp+var_30]; struct IFileSystemImageResult *
0x18000d9ab  mov     rcx, rbx; this
0x18000d9ae  call    ?IsSameMultiSessionJolietDiscStillPresent@CMSDiscMasterObj@@AEAAEPEAUIFileSystemImageResult@@@Z; CMSDiscMasterObj::IsSameMultiSessionJolietDiscStillPresent(IFileSystemImageResult *)
0x18000d9b3  test    al, al
0x18000d9b5  jnz     short loc_18000D9C1
0x18000d9b7  mov     edi, 80040223h
0x18000d9bc  jmp     loc_18000DFA2
0x18000d9c1  mov     rcx, [rbp+var_30]
0x18000d9c5  lea     rdx, [rbp+var_20]
0x18000d9c9  mov     rax, [rcx]
0x18000d9cc  mov     rax, [rax+38h]
0x18000d9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d5  test    eax, eax
0x18000d9d7  jns     short loc_18000DA05
0x18000d9d9  mov     ecx, eax
0x18000d9db  jmp     short loc_18000D989
0x18000d9dd  mov     rax, qword ptr cs:IID_IRedbookDiscMaster.Data1
0x18000d9e4  cmp     rax, [rbx+164h]
0x18000d9eb  jnz     loc_18000DF9D
0x18000d9f1  mov     rax, qword ptr cs:IID_IRedbookDiscMaster.Data4
0x18000d9f8  cmp     rax, [rbx+16Ch]
0x18000d9ff  jnz     loc_18000DF9D
0x18000da05  mov     rcx, [rbx+1A8h]; hEvent
0x18000da0c  test    rcx, rcx
0x18000da0f  jz      short loc_18000DA17
0x18000da11  call    cs:__imp_ResetEvent
0x18000da17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da1e  lea     rax, WPP_GLOBAL_Control
0x18000da25  cmp     rcx, rax
0x18000da28  jz      short loc_18000DA4C
0x18000da2a  test    byte ptr [rcx+44h], 1
0x18000da2e  jz      short loc_18000DA4C
0x18000da30  mov     r9d, [rbx+1F8h]
0x18000da37  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000da3e  mov     rcx, [rcx+38h]
0x18000da42  mov     edx, 42h ; 'B'
0x18000da47  call    WPP_SF_d
0x18000da4c  lea     r15, [rbx+0C0h]
0x18000da53  cmp     [r15+0Ch], r12d
0x18000da57  jz      short loc_18000DA6B
0x18000da59  bts     dword ptr [rbx+124h], 0Ch
0x18000da61  mov     dword ptr [rbx+134h], 3
0x18000da6b  mov     rcx, r15; this
0x18000da6e  call    ?UpdateAll@CMyUpdateList@@QEAAXXZ; CMyUpdateList::UpdateAll(void)
0x18000da73  mov     rcx, [rbx+1E0h]
0x18000da7a  mov     dl, 1
0x18000da7c  call    WriterOpenExclusive
0x18000da81  mov     edi, eax
0x18000da83  test    eax, eax
0x18000da85  jns     short loc_18000DAC0
0x18000da87  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da8e  lea     r12, WPP_GLOBAL_Control
0x18000da95  cmp     rcx, r12
0x18000da98  jz      short loc_18000DAB8
0x18000da9a  test    byte ptr [rcx+44h], 1
0x18000da9e  jz      short loc_18000DAB8
0x18000daa0  mov     edx, 43h ; 'C'
0x18000daa5  mov     rcx, [rcx+38h]
0x18000daa9  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000dab0  mov     r9d, eax
0x18000dab3  call    WPP_SF_d
0x18000dab8  mov     r15b, sil
0x18000dabb  jmp     loc_18000DFA9
0x18000dac0  mov     rcx, [rbx+1E0h]
0x18000dac7  mov     r14b, 1
0x18000daca  mov     dl, r14b
0x18000dacd  mov     [rbp+var_40], r14b
0x18000dad1  call    WriterLockTray
0x18000dad6  mov     edi, eax
0x18000dad8  test    eax, eax
0x18000dada  jns     short loc_18000DAFC
0x18000dadc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dae3  lea     r12, WPP_GLOBAL_Control
0x18000daea  cmp     rcx, r12
0x18000daed  jz      short loc_18000DAB8
0x18000daef  test    [rcx+44h], r14b
0x18000daf3  jz      short loc_18000DAB8
0x18000daf5  mov     edx, 44h ; 'D'
0x18000dafa  jmp     short loc_18000DAA5
0x18000dafc  mov     rcx, [rbx+1D8h]
0x18000db03  mov     rax, [rcx]
0x18000db06  mov     rax, [rax+60h]
0x18000db0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db0f  mov     rcx, [rbx+1D8h]
0x18000db16  lea     r8, [rbp+var_28]
0x18000db1a  mov     esi, eax
0x18000db1c  lea     rdx, [rbp+var_18]
0x18000db20  shr     esi, 1Fh
0x18000db23  xor     sil, r14b
0x18000db26  mov     rax, [rcx]
0x18000db29  mov     rax, [rax+68h]
0x18000db2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db32  mov     edi, eax
0x18000db34  test    eax, eax
0x18000db36  jns     short loc_18000DB72
0x18000db38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db3f  lea     r12, WPP_GLOBAL_Control
0x18000db46  cmp     rcx, r12
0x18000db49  jz      short loc_18000DB69
0x18000db4b  test    [rcx+44h], r14b
0x18000db4f  jz      short loc_18000DB69
0x18000db51  mov     edx, 45h ; 'E'
0x18000db56  mov     r9d, eax
0x18000db59  mov     rcx, [rcx+38h]
0x18000db5d  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000db64  call    WPP_SF_d
0x18000db69  mov     r15b, byte ptr [rbp+bstrString]
0x18000db6d  jmp     loc_18000DFA9
0x18000db72  test    byte ptr [rbp+var_28], 8
0x18000db76  jz      short loc_18000DB85
0x18000db78  mov     edi, 80040210h
0x18000db7d  mov     r15b, r12b
0x18000db80  jmp     loc_18000DFA2
0x18000db85  mov     edx, [rbx+1F8h]
0x18000db8b  mov     rcx, [rbx+1E0h]
0x18000db92  call    WriterLoadWritableDisc
0x18000db97  xor     ecx, ecx
0x18000db99  mov     edi, eax
0x18000db9b  test    eax, eax
0x18000db9d  jns     short loc_18000DBCA
0x18000db9f  mov     edi, 80040210h
0x18000dba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbab  lea     r12, WPP_GLOBAL_Control
0x18000dbb2  cmp     rcx, r12
0x18000dbb5  jz      short loc_18000DB69
0x18000dbb7  test    [rcx+44h], r14b
0x18000dbbb  jz      short loc_18000DB69
0x18000dbbd  mov     edx, 46h ; 'F'
0x18000dbc2  mov     r9d, 80040210h
0x18000dbc8  jmp     short loc_18000DB59
0x18000dbca  mov     rax, qword ptr cs:IID_IJolietDiscMaster.Data1
0x18000dbd1  mov     r14d, ecx
0x18000dbd4  cmp     rax, [rbx+164h]
0x18000dbdb  jnz     loc_18000DEEB
0x18000dbe1  mov     rax, qword ptr cs:IID_IJolietDiscMaster.Data4
0x18000dbe8  cmp     rax, [rbx+16Ch]
0x18000dbef  jnz     loc_18000DEEB
0x18000dbf5  xor     edx, edx; pUnkOuter
0x18000dbf7  lea     r15, [rbx+1D0h]
0x18000dbfe  lea     r9, _GUID_27354153_9f64_5b0f_8f00_5d77afbe261e; riid
0x18000dc05  mov     [rsp+70h+ppv], r15; ppv
0x18000dc0a  lea     rcx, _GUID_2735412a_7f64_5b0f_8f00_5d77afbe261e; rclsid
0x18000dc11  lea     r8d, [rdx+17h]; dwClsContext
0x18000dc15  call    cs:__imp_CoCreateInstance
0x18000dc1b  mov     edi, eax
0x18000dc1d  test    eax, eax
0x18000dc1f  jns     short loc_18000DC5B
0x18000dc21  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc28  lea     r12, WPP_GLOBAL_Control
0x18000dc2f  cmp     rcx, r12
0x18000dc32  jz      short loc_18000DC52
0x18000dc34  test    byte ptr [rcx+44h], 1
0x18000dc38  jz      short loc_18000DC52
0x18000dc3a  mov     rcx, [rcx+38h]
0x18000dc3e  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000dc45  mov     edx, 47h ; 'G'
0x18000dc4a  mov     r9d, eax
0x18000dc4d  call    WPP_SF_d
0x18000dc52  mov     r14b, [rbp+var_40]
0x18000dc56  jmp     loc_18000DB69
0x18000dc5b  lea     rcx, psz; "IMAPIv1 Shim"
0x18000dc62  call    cs:__imp_SysAllocString
0x18000dc68  mov     rcx, [r15]
0x18000dc6b  mov     r8, rax
0x18000dc6e  mov     [rbp+var_10], rax
0x18000dc72  mov     rdx, [rcx]
0x18000dc75  mov     rax, [rdx+0F0h]
0x18000dc7c  mov     rdx, r8
0x18000dc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc84  mov     edi, eax
0x18000dc86  test    eax, eax
0x18000dc88  jns     short loc_18000DCFF
0x18000dc8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc91  lea     rax, WPP_GLOBAL_Control
0x18000dc98  cmp     rcx, rax
0x18000dc9b  jz      short loc_18000DCD9
0x18000dc9d  test    byte ptr [rcx+44h], 1
0x18000dca1  jz      short loc_18000DCD9
0x18000dca3  lea     rcx, [rbp+var_38]
0x18000dca7  call    ?GetLastComError@@YA?AVCComBSTR@ATL@@XZ; GetLastComError(void)
0x18000dcac  mov     edx, 48h ; 'H'
0x18000dcb1  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000dcb8  mov     r9d, edi
0x18000dcbb  mov     rcx, [rax]
0x18000dcbe  mov     [rsp+70h+ppv], rcx
0x18000dcc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcca  mov     rcx, [rcx+38h]
0x18000dcce  call    WPP_SF_DS
0x18000dcd3  mov     r12d, 2
0x18000dcd9  test    r12b, 2
0x18000dcdd  jz      short loc_18000DCE9
0x18000dcdf  mov     rcx, [rbp+var_38]; bstrString
0x18000dce3  call    cs:__imp_SysFreeString
0x18000dce9  mov     ecx, edi
0x18000dceb  call    TranslateIMAPI2Error
0x18000dcf0  mov     r14b, [rbp+var_40]
0x18000dcf4  mov     edi, eax
0x18000dcf6  mov     r15b, byte ptr [rbp+bstrString]
0x18000dcfa  jmp     loc_18000DFA2
0x18000dcff  mov     rcx, [r15]
0x18000dd02  mov     rdx, [rbx+1E0h]
0x18000dd09  mov     rax, [rcx]
0x18000dd0c  mov     rdx, [rdx]
0x18000dd0f  mov     rax, [rax+60h]
0x18000dd13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd18  mov     edi, eax
0x18000dd1a  test    eax, eax
0x18000dd1c  jns     short loc_18000DD59
  ... truncated ...
```
