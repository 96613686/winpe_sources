# CMsftDiscFormat2RawCD::PrepareMedia(void)

- ea: `0x18002f540`
- end: `0x18002fb40`
- name: `?PrepareMedia@CMsftDiscFormat2RawCD@@UEAAJXZ`
- size: `1536`
- prototype: `__int64 __fastcall(CMsftDiscFormat2RawCD *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000a86c`
- `0x180011b4c`
- `0x1800140f4`
- `0x180016778`
- `0x1800170ec`
- `0x18001724c`
- `0x18002d8a8`
- `0x18002db08`
- `0x18002efc0`
- `0x18002f540`
- `0x18002fe88`
- `0x1800301a8`
- `0x1800303d8`
- `0x180030500`
- `0x1800464ec`
- `0x18004932c`
- `0x180049408`
- `0x18004a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002f65c`
- `ole32!CoCreateInstance` at `0x18002f65c`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2RawCD::PrepareMedia(CMsftDiscFormat2RawCD *this)
{
  unsigned __int8 v1; // si
  __int64 v3; // rcx
  signed int v4; // ebx
  unsigned __int8 v5; // r15
  const struct _GUID *v6; // r8
  HRESULT Instance; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  const struct _GUID *v11; // r8
  CMsftDiscFormat2RawCD *v12; // rcx
  struct IDiscRecorder2Ex *v13; // rdx
  struct IDiscRecorder2 *v14; // rdx
  int IsSupported; // eax
  int v16; // eax
  unsigned __int8 v17; // r8
  unsigned __int8 v18; // r9
  int v19; // eax
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  int LastPossibleLeadoutStartTimeAsLba; // eax
  __int64 v25; // [rsp+30h] [rbp-20h] BYREF
  int v26; // [rsp+38h] [rbp-18h]
  _QWORD v27[2]; // [rsp+40h] [rbp-10h] BYREF
  __int16 v28; // [rsp+88h] [rbp+38h] BYREF
  enum _IMAPI_MEDIA_PHYSICAL_TYPE v29; // [rsp+90h] [rbp+40h] BYREF
  struct IUnknown *ppv; // [rsp+98h] [rbp+48h] BYREF

  v1 = 0;
  v27[0] = 0;
  v27[1] = 0;
  v29 = IMAPI_MEDIA_TYPE_UNKNOWN;
  ppv = 0;
  v25 = 0;
  v26 = 0;
  v4 = CMsftDiscFormat2RawCD::ValidateRecorderSet(this);
  if ( v4 < 0 )
    goto LABEL_8;
  if ( *(_WORD *)(v3 + 192) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 40, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
    }
    v4 = -1062599165;
    goto LABEL_8;
  }
  Instance = CoCreateInstance(
               &CLSID_MsftWriteEngine2,
               0,
               0x17u,
               &GUID_27354135_7f64_5b0f_8f00_5d77afbe261e,
               (LPVOID *)&ppv);
  v4 = Instance;
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))ppv->lpVtbl[3].QueryInterface)(
                 ppv,
                 *((_QWORD *)this + 23));
    v4 = Instance;
    if ( Instance < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
      {
        goto LABEL_8;
      }
      v10 = 42;
      goto LABEL_20;
    }
    if ( *((_DWORD *)this + 23) != -16843010 )
      ATL::AtlThrowImpl(-2147467259);
    Instance = ATL::AtlAdvise(ppv, (struct IUnknown *)this + 6, v11, (unsigned int *)this + 23);
    v4 = Instance;
    if ( Instance < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
      {
        goto LABEL_8;
      }
      v10 = 43;
      goto LABEL_20;
    }
    v4 = CMsftDiscFormat2RawCD::ValidateMediaInDrive(
           v12,
           *((struct IDiscRecorder2Ex **)this + 23),
           &v29,
           (struct CMsftDiscInformation *)v27);
    if ( v4 < 0 )
      goto LABEL_38;
    v14 = (struct IDiscRecorder2 *)*((_QWORD *)this + 22);
    v28 = 0;
    IsSupported = CMsftDiscFormat2RawCD::IsSupported(
                    this,
                    v14,
                    (unsigned __int8 *)&v28,
                    -1,
                    (struct CMsftDiscFormat2RawCD::SupportedRawSectorTypes *)&v25);
    v4 = IsSupported;
    if ( IsSupported < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 47),
          44,
          &WPP_465922b870433540ecd6931719c7292a_Traceguids,
          (unsigned int)IsSupported);
      }
LABEL_38:
      v5 = 0;
      goto LABEL_39;
    }
    if ( !v28 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 45, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
      }
      v4 = -1062599161;
      goto LABEL_38;
    }
    v1 = 1;
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 22) + 72LL))(
           *((_QWORD *)this + 22),
           1,
           *((_QWORD *)this + 25));
    if ( v4 < 0 )
    {
      if ( v4 == -1062600175 )
        v4 = -1062599164;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 47),
          46,
          &WPP_465922b870433540ecd6931719c7292a_Traceguids,
          (unsigned int)v4);
      }
      v5 = 0;
LABEL_65:
      v1 = 0;
      goto LABEL_39;
    }
    v5 = 1;
    LOBYTE(v13) = 1;
    v19 = Imapi2Utility::PreventAllowMediumRemoval(*((Imapi2Utility **)this + 23), v13, v17, v18);
    v4 = v19;
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 47),
          47,
          &WPP_465922b870433540ecd6931719c7292a_Traceguids,
          (unsigned int)v19);
      }
      goto LABEL_65;
    }
    v20 = CMsftDiscFormat2RawCD::CacheCurrentWriteParametersModePage(this, *((struct IDiscRecorder2Ex **)this + 23));
    v4 = v20;
    if ( v20 >= 0 )
    {
      v20 = CMsftDiscFormat2RawCD::SendModifiedModePage(
              this,
              *((struct IDiscRecorder2Ex **)this + 23),
              (enum _IMAPI_FORMAT2_RAW_CD_DATA_SECTOR_TYPE)*((_DWORD *)this + 54));
      v4 = v20;
      if ( v20 >= 0 )
      {
        v20 = CMsftDiscFormat2RawCD::ValidateModePageParametersStuck(this, *((struct IDiscRecorder2Ex **)this + 23));
        v4 = v20;
        if ( v20 >= 0 )
        {
          v20 = (*(__int64 (__fastcall **)(CMsftDiscFormat2RawCD *, _QWORD, _QWORD))(*(_QWORD *)this + 136LL))(
                  this,
                  *((unsigned int *)this + 52),
                  *((unsigned __int16 *)this + 106));
          v4 = v20;
          if ( v20 >= 0 )
          {
            v23 = v26;
            *(_QWORD *)((char *)this + 220) = v25;
            *((_DWORD *)this + 57) = v23;
            *((_DWORD *)this + 58) = v29;
            *((_QWORD *)this + 34) = ppv;
            *((_DWORD *)this + 70) = CMsftDiscInformation::get_LastSessionLeadinAsLba((CMsftDiscInformation *)v27);
            LastPossibleLeadoutStartTimeAsLba = CMsftDiscInformation::get_LastPossibleLeadoutStartTimeAsLba((CMsftDiscInformation *)v27);
            *((_DWORD *)this + 71) = LastPossibleLeadoutStartTimeAsLba;
            *((_DWORD *)this + 72) = LastPossibleLeadoutStartTimeAsLba - *((_DWORD *)this + 70);
            *((_WORD *)this + 106) = 0;
            *((_WORD *)this + 97) = 0;
            *((_DWORD *)this + 52) = -1;
            *((_WORD *)this + 96) = -1;
            goto LABEL_12;
          }
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
          {
            goto LABEL_39;
          }
          v22 = 51;
          goto LABEL_86;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
        {
          v22 = 50;
          goto LABEL_86;
        }
      }
      else
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
        {
          v22 = 49;
          goto LABEL_86;
        }
      }
    }
    else
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
      {
        v22 = 48;
LABEL_86:
        WPP_SF_d(v21[47], v22, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)v20);
      }
    }
LABEL_39:
    v16 = ATL::AtlUnadvise(ppv, (const struct _GUID *)v13, *((_DWORD *)this + 23));
    *((_DWORD *)this + 23) = -16843010;
    if ( v16 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 47),
        52,
        &WPP_465922b870433540ecd6931719c7292a_Traceguids,
        (unsigned int)v16);
    }
    goto LABEL_9;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
  {
    goto LABEL_8;
  }
  v10 = 41;
LABEL_20:
  WPP_SF_d(v9[47], v10, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)Instance);
LABEL_8:
  v5 = 0;
LABEL_9:
  if ( ppv )
  {
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
    ppv = 0;
  }
  CMsftDiscFormat2RawCD::CleanupFromPreparedMedia(
    this,
    *((struct IDiscRecorder2Ex **)this + 23),
    *((struct IDiscRecorder2 **)this + 22),
    v1,
    v5);
LABEL_12:
  if ( (v4 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v4, (int)&CLSID_MsftDiscFormat2RawCD, v6);
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)v27);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002f540  mov     [rsp-28h+arg_0], rbx
0x18002f545  push    rbp
0x18002f546  push    rsi
0x18002f547  push    rdi
0x18002f548  push    r13
0x18002f54a  push    r15
0x18002f54c  mov     rbp, rsp
0x18002f54f  sub     rsp, 50h
0x18002f553  xor     esi, esi
0x18002f555  mov     rdi, rcx
0x18002f558  mov     [rbp+var_10], rsi
0x18002f55c  mov     [rbp+var_8], rsi
0x18002f560  mov     [rbp+arg_10], esi
0x18002f563  mov     [rbp+arg_18], rsi
0x18002f567  mov     [rbp+var_20], rsi
0x18002f56b  mov     [rbp+var_18], esi
0x18002f56e  call    ?ValidateRecorderSet@CMsftDiscFormat2RawCD@@AEAAJXZ; CMsftDiscFormat2RawCD::ValidateRecorderSet(void)
0x18002f573  mov     ebx, eax
0x18002f575  test    eax, eax
0x18002f577  js      short loc_18002F5C6
0x18002f579  cmp     [rcx+0C0h], si
0x18002f580  jz      loc_18002F63F
0x18002f586  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f58d  lea     r13, WPP_GLOBAL_Control
0x18002f594  cmp     rcx, r13
0x18002f597  jz      short loc_18002F5C1
0x18002f599  test    byte ptr [rcx+184h], 4
0x18002f5a0  jz      short loc_18002F5C1
0x18002f5a2  cmp     byte ptr [rcx+181h], 3
0x18002f5a9  jb      short loc_18002F5C1
0x18002f5ab  mov     rcx, [rcx+178h]
0x18002f5b2  lea     edx, [rsi+28h]
0x18002f5b5  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f5bc  call    WPP_SF_
0x18002f5c1  mov     ebx, 0C0AA0603h
0x18002f5c6  mov     r15b, sil
0x18002f5c9  mov     rcx, [rbp+arg_18]
0x18002f5cd  test    rcx, rcx
0x18002f5d0  jz      short loc_18002F5E6
0x18002f5d2  mov     rax, [rcx]
0x18002f5d5  mov     rax, [rax+10h]
0x18002f5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5de  mov     [rbp+arg_18], 0
0x18002f5e6  mov     r8, [rdi+0B0h]; struct IDiscRecorder2 *
0x18002f5ed  mov     r9b, sil; unsigned __int8
0x18002f5f0  mov     rdx, [rdi+0B8h]; struct IDiscRecorder2Ex *
0x18002f5f7  mov     rcx, rdi; this
0x18002f5fa  mov     byte ptr [rsp+50h+ppv], r15b; unsigned __int8
0x18002f5ff  call    ?CleanupFromPreparedMedia@CMsftDiscFormat2RawCD@@AEAAXPEAUIDiscRecorder2Ex@@PEAUIDiscRecorder2@@EE@Z; CMsftDiscFormat2RawCD::CleanupFromPreparedMedia(IDiscRecorder2Ex *,IDiscRecorder2 *,uchar,uchar)
0x18002f604  mov     eax, ebx
0x18002f606  and     eax, 80FF0000h
0x18002f60b  cmp     eax, 80AA0000h
0x18002f610  jnz     short loc_18002F620
0x18002f612  lea     rdx, CLSID_MsftDiscFormat2RawCD; int
0x18002f619  mov     ecx, ebx; dwMessageId
0x18002f61b  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002f620  lea     rcx, [rbp+var_10]; this
0x18002f624  call    ??1CMsftDiscInformation@@QEAA@XZ; CMsftDiscInformation::~CMsftDiscInformation(void)
0x18002f629  mov     eax, ebx
0x18002f62b  mov     rbx, [rsp+50h+arg_0]
0x18002f633  add     rsp, 50h
0x18002f637  pop     r15
0x18002f639  pop     r13
0x18002f63b  pop     rdi
0x18002f63c  pop     rsi
0x18002f63d  pop     rbp
0x18002f63e  retn
0x18002f63f  xor     edx, edx; pUnkOuter
0x18002f641  lea     rax, [rbp+arg_18]
0x18002f645  lea     r9, _GUID_27354135_7f64_5b0f_8f00_5d77afbe261e; riid
0x18002f64c  mov     [rsp+50h+ppv], rax; ppv
0x18002f651  lea     rcx, CLSID_MsftWriteEngine2; rclsid
0x18002f658  lea     r8d, [rdx+17h]; dwClsContext
0x18002f65c  call    cs:__imp_CoCreateInstance
0x18002f662  mov     ebx, eax
0x18002f664  test    eax, eax
0x18002f666  jns     short loc_18002F6B9
0x18002f668  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f66f  lea     r13, WPP_GLOBAL_Control
0x18002f676  cmp     rcx, r13
0x18002f679  jz      loc_18002F5C6
0x18002f67f  test    byte ptr [rcx+184h], 4
0x18002f686  jz      loc_18002F5C6
0x18002f68c  cmp     byte ptr [rcx+181h], 3
0x18002f693  jb      loc_18002F5C6
0x18002f699  mov     edx, 29h ; ')'
0x18002f69e  mov     rcx, [rcx+178h]
0x18002f6a5  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f6ac  mov     r9d, eax
0x18002f6af  call    WPP_SF_d
0x18002f6b4  jmp     loc_18002F5C6
0x18002f6b9  mov     rcx, [rbp+arg_18]
0x18002f6bd  mov     rdx, [rdi+0B8h]
0x18002f6c4  mov     rax, [rcx]
0x18002f6c7  mov     rax, [rax+48h]
0x18002f6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6d0  mov     ebx, eax
0x18002f6d2  test    eax, eax
0x18002f6d4  jns     short loc_18002F70E
0x18002f6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6dd  lea     r13, WPP_GLOBAL_Control
0x18002f6e4  cmp     rcx, r13
0x18002f6e7  jz      loc_18002F5C6
0x18002f6ed  test    byte ptr [rcx+184h], 4
0x18002f6f4  jz      loc_18002F5C6
0x18002f6fa  cmp     byte ptr [rcx+181h], 3
0x18002f701  jb      loc_18002F5C6
0x18002f707  mov     edx, 2Ah ; '*'
0x18002f70c  jmp     short loc_18002F69E
0x18002f70e  lea     rdx, [rdi+30h]; struct IUnknown *
0x18002f712  lea     r9, [rdx+2Ch]; unsigned int *
0x18002f716  cmp     dword ptr [r9], 0FEFEFEFEh
0x18002f71d  jnz     loc_18002FB35
0x18002f723  mov     rcx, [rbp+arg_18]; struct IUnknown *
0x18002f727  call    ?AtlAdvise@ATL@@YAJPEAUIUnknown@@0AEBU_GUID@@PEAK@Z; ATL::AtlAdvise(IUnknown *,IUnknown *,_GUID const &,ulong *)
0x18002f72c  mov     ebx, eax
0x18002f72e  test    eax, eax
0x18002f730  jns     short loc_18002F76D
0x18002f732  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f739  lea     r13, WPP_GLOBAL_Control
0x18002f740  cmp     rcx, r13
0x18002f743  jz      loc_18002F5C6
0x18002f749  test    byte ptr [rcx+184h], 4
0x18002f750  jz      loc_18002F5C6
0x18002f756  cmp     byte ptr [rcx+181h], 3
0x18002f75d  jb      loc_18002F5C6
0x18002f763  mov     edx, 2Bh ; '+'
0x18002f768  jmp     loc_18002F69E
0x18002f76d  mov     rdx, [rdi+0B8h]; struct IDiscRecorder2Ex *
0x18002f774  lea     r9, [rbp+var_10]; struct CMsftDiscInformation *
0x18002f778  lea     r8, [rbp+arg_10]; enum _IMAPI_MEDIA_PHYSICAL_TYPE *
0x18002f77c  call    ?ValidateMediaInDrive@CMsftDiscFormat2RawCD@@AEAAJPEAUIDiscRecorder2Ex@@AEAW4_IMAPI_MEDIA_PHYSICAL_TYPE@@AEAVCMsftDiscInformation@@@Z; CMsftDiscFormat2RawCD::ValidateMediaInDrive(IDiscRecorder2Ex *,_IMAPI_MEDIA_PHYSICAL_TYPE &,CMsftDiscInformation &)
0x18002f781  lea     r13, WPP_GLOBAL_Control
0x18002f788  mov     ebx, eax
0x18002f78a  lea     r15, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f791  test    eax, eax
0x18002f793  js      short loc_18002F7F8
0x18002f795  mov     rdx, [rdi+0B0h]; struct IDiscRecorder2 *
0x18002f79c  lea     rax, [rbp+var_20]
0x18002f7a0  or      r9d, 0FFFFFFFFh; __int16
0x18002f7a4  mov     [rsp+50h+ppv], rax; struct CMsftDiscFormat2RawCD::SupportedRawSectorTypes *
0x18002f7a9  lea     r8, [rbp+arg_8]; __int16 *
0x18002f7ad  mov     [rbp+arg_8], si
0x18002f7b1  mov     rcx, rdi; this
0x18002f7b4  call    ?IsSupported@CMsftDiscFormat2RawCD@@AEAAJPEAUIDiscRecorder2@@PEAFFPEAUSupportedRawSectorTypes@1@@Z; CMsftDiscFormat2RawCD::IsSupported(IDiscRecorder2 *,short *,short,CMsftDiscFormat2RawCD::SupportedRawSectorTypes *)
0x18002f7b9  mov     ebx, eax
0x18002f7bb  test    eax, eax
0x18002f7bd  jns     loc_18002F861
0x18002f7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7ca  cmp     rcx, r13
0x18002f7cd  jz      short loc_18002F7F8
0x18002f7cf  test    byte ptr [rcx+184h], 4
0x18002f7d6  jz      short loc_18002F7F8
0x18002f7d8  cmp     byte ptr [rcx+181h], 3
0x18002f7df  jb      short loc_18002F7F8
0x18002f7e1  mov     rcx, [rcx+178h]
0x18002f7e8  mov     edx, 2Ch ; ','
0x18002f7ed  mov     r9d, eax
0x18002f7f0  mov     r8, r15
0x18002f7f3  call    WPP_SF_d
0x18002f7f8  mov     r15b, sil
0x18002f7fb  mov     r8d, [rdi+5Ch]; unsigned int
0x18002f7ff  mov     rcx, [rbp+arg_18]; struct IUnknown *
0x18002f803  call    ?AtlUnadvise@ATL@@YAJPEAUIUnknown@@AEBU_GUID@@K@Z; ATL::AtlUnadvise(IUnknown *,_GUID const &,ulong)
0x18002f808  mov     dword ptr [rdi+5Ch], 0FEFEFEFEh
0x18002f80f  test    eax, eax
0x18002f811  jns     loc_18002F5C9
0x18002f817  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f81e  cmp     rcx, r13
0x18002f821  jz      loc_18002F5C9
0x18002f827  test    byte ptr [rcx+184h], 4
0x18002f82e  jz      loc_18002F5C9
0x18002f834  cmp     byte ptr [rcx+181h], 3
0x18002f83b  jb      loc_18002F5C9
0x18002f841  mov     rcx, [rcx+178h]
0x18002f848  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f84f  mov     edx, 34h ; '4'
0x18002f854  mov     r9d, eax
0x18002f857  call    WPP_SF_d
0x18002f85c  jmp     loc_18002F5C9
0x18002f861  cmp     [rbp+arg_8], si
0x18002f865  jnz     short loc_18002F8A3
0x18002f867  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f86e  cmp     rcx, r13
0x18002f871  jz      short loc_18002F899
0x18002f873  test    byte ptr [rcx+184h], 4
0x18002f87a  jz      short loc_18002F899
0x18002f87c  cmp     byte ptr [rcx+181h], 3
0x18002f883  jb      short loc_18002F899
0x18002f885  mov     rcx, [rcx+178h]
0x18002f88c  mov     edx, 2Dh ; '-'
0x18002f891  mov     r8, r15
0x18002f894  call    WPP_SF_
0x18002f899  mov     ebx, 0C0AA0607h
0x18002f89e  jmp     loc_18002F7F8
0x18002f8a3  mov     rcx, [rdi+0B0h]
0x18002f8aa  mov     esi, 1
0x18002f8af  mov     r8, [rdi+0C8h]
0x18002f8b6  mov     edx, esi
0x18002f8b8  mov     rax, [rcx]
0x18002f8bb  mov     rax, [rax+48h]
0x18002f8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8c4  mov     ebx, eax
0x18002f8c6  test    eax, eax
0x18002f8c8  jns     short loc_18002F914
0x18002f8ca  cmp     ebx, 0C0AA0211h
0x18002f8d0  mov     eax, 0C0AA0604h
0x18002f8d5  cmovz   ebx, eax
0x18002f8d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8df  cmp     rcx, r13
0x18002f8e2  jz      short loc_18002F90B
0x18002f8e4  test    byte ptr [rcx+184h], 4
0x18002f8eb  jz      short loc_18002F90B
0x18002f8ed  cmp     byte ptr [rcx+181h], 3
0x18002f8f4  jb      short loc_18002F90B
0x18002f8f6  mov     rcx, [rcx+178h]
0x18002f8fd  lea     edx, [rsi+2Dh]
0x18002f900  mov     r9d, ebx
0x18002f903  mov     r8, r15
0x18002f906  call    WPP_SF_d
0x18002f90b  xor     r15b, r15b
0x18002f90e  test    ebx, ebx
0x18002f910  jns     short loc_18002F917
0x18002f912  jmp     short loc_18002F965
0x18002f914  mov     r15b, sil
0x18002f917  mov     rcx, [rdi+0B8h]; this
0x18002f91e  mov     dl, sil; struct IDiscRecorder2Ex *
0x18002f921  call    ?PreventAllowMediumRemoval@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EE@Z; Imapi2Utility::PreventAllowMediumRemoval(IDiscRecorder2Ex *,uchar,uchar)
0x18002f926  mov     ebx, eax
0x18002f928  test    eax, eax
0x18002f92a  jns     short loc_18002F96D
0x18002f92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f933  cmp     rcx, r13
0x18002f936  jz      short loc_18002F965
0x18002f938  test    byte ptr [rcx+184h], 4
0x18002f93f  jz      short loc_18002F965
0x18002f941  cmp     byte ptr [rcx+181h], 3
0x18002f948  jb      short loc_18002F965
0x18002f94a  mov     rcx, [rcx+178h]
0x18002f951  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f958  mov     edx, 2Fh ; '/'
0x18002f95d  mov     r9d, eax
0x18002f960  call    WPP_SF_d
0x18002f965  xor     sil, sil
0x18002f968  jmp     loc_18002F7FB
0x18002f96d  mov     rdx, [rdi+0B8h]; struct IDiscRecorder2Ex *
0x18002f974  mov     rcx, rdi; this
0x18002f977  call    ?CacheCurrentWriteParametersModePage@CMsftDiscFormat2RawCD@@AEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscFormat2RawCD::CacheCurrentWriteParametersModePage(IDiscRecorder2Ex *)
0x18002f97c  mov     ebx, eax
0x18002f97e  test    eax, eax
0x18002f980  jns     short loc_18002F9B6
0x18002f982  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f989  cmp     rcx, r13
0x18002f98c  jz      loc_18002F7FB
0x18002f992  test    byte ptr [rcx+184h], 4
0x18002f999  jz      loc_18002F7FB
0x18002f99f  cmp     byte ptr [rcx+181h], 3
0x18002f9a6  jb      loc_18002F7FB
0x18002f9ac  mov     edx, 30h ; '0'
0x18002f9b1  jmp     loc_18002FAA1
0x18002f9b6  mov     r8d, [rdi+0D8h]; enum _IMAPI_FORMAT2_RAW_CD_DATA_SECTOR_TYPE
0x18002f9bd  mov     rcx, rdi; this
0x18002f9c0  mov     rdx, [rdi+0B8h]; struct IDiscRecorder2Ex *
0x18002f9c7  call    ?SendModifiedModePage@CMsftDiscFormat2RawCD@@AEAAJPEAUIDiscRecorder2Ex@@W4_IMAPI_FORMAT2_RAW_CD_DATA_SECTOR_TYPE@@@Z; CMsftDiscFormat2RawCD::SendModifiedModePage(IDiscRecorder2Ex *,_IMAPI_FORMAT2_RAW_CD_DATA_SECTOR_TYPE)
0x18002f9cc  mov     ebx, eax
0x18002f9ce  test    eax, eax
0x18002f9d0  jns     short loc_18002FA06
0x18002f9d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9d9  cmp     rcx, r13
0x18002f9dc  jz      loc_18002F7FB
0x18002f9e2  test    byte ptr [rcx+184h], 4
0x18002f9e9  jz      loc_18002F7FB
0x18002f9ef  cmp     byte ptr [rcx+181h], 3
0x18002f9f6  jb      loc_18002F7FB
0x18002f9fc  mov     edx, 31h ; '1'
0x18002fa01  jmp     loc_18002FAA1
0x18002fa06  mov     rdx, [rdi+0B8h]; struct IDiscRecorder2Ex *
0x18002fa0d  mov     rcx, rdi; this
0x18002fa10  call    ?ValidateModePageParametersStuck@CMsftDiscFormat2RawCD@@AEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscFormat2RawCD::ValidateModePageParametersStuck(IDiscRecorder2Ex *)
0x18002fa15  mov     ebx, eax
0x18002fa17  test    eax, eax
0x18002fa19  jns     short loc_18002FA4C
0x18002fa1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa22  cmp     rcx, r13
0x18002fa25  jz      loc_18002F7FB
0x18002fa2b  test    byte ptr [rcx+184h], 4
0x18002fa32  jz      loc_18002F7FB
0x18002fa38  cmp     byte ptr [rcx+181h], 3
0x18002fa3f  jb      loc_18002F7FB
0x18002fa45  mov     edx, 32h ; '2'
0x18002fa4a  jmp     short loc_18002FAA1
0x18002fa4c  mov     rax, [rdi]
0x18002fa4f  mov     rcx, rdi
0x18002fa52  movzx   r8d, word ptr [rdi+0D4h]
0x18002fa5a  mov     edx, [rdi+0D0h]
0x18002fa60  mov     rax, [rax+88h]
0x18002fa67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa6c  mov     ebx, eax
0x18002fa6e  test    eax, eax
0x18002fa70  jns     short loc_18002FABC
  ... truncated ...
```
