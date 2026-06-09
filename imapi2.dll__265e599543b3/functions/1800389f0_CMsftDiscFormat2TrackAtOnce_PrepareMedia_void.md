# CMsftDiscFormat2TrackAtOnce::PrepareMedia(void)

- ea: `0x1800389f0`
- end: `0x1800391bc`
- name: `?PrepareMedia@CMsftDiscFormat2TrackAtOnce@@UEAAJXZ`
- size: `1996`
- prototype: `__int64 __fastcall(CMsftDiscFormat2TrackAtOnce *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180009b80`
- `0x18000a5f0`
- `0x18000a86c`
- `0x180011b4c`
- `0x1800140f4`
- `0x180016778`
- `0x1800170ec`
- `0x18001724c`
- `0x18003734c`
- `0x1800375a8`
- `0x180037a04`
- `0x1800389f0`
- `0x180039740`
- `0x180039f98`
- `0x1800464ec`
- `0x18004932c`
- `0x18004984a`
- `0x18004a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180038b61`
- `ole32!CoCreateInstance` at `0x180038b61`
- `KERNEL32!GetTickCount` at `0x180038a24`
- `KERNEL32!GetTickCount` at `0x180038a24`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2TrackAtOnce::PrepareMedia(CMsftDiscFormat2TrackAtOnce *this)
{
  unsigned int v1; // r13d
  char v3; // si
  struct IDiscRecorder2Ex *v4; // rdx
  struct _GUID *v5; // r8
  unsigned __int8 lpVtbl; // r9
  signed int v7; // ebx
  HRESULT Instance; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  char v11; // r14
  unsigned __int8 v12; // di
  int CurrentPhysicalMediaType; // eax
  __int64 i; // rcx
  char v15; // cl
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r12
  int v23; // eax
  const struct _GUID *v24; // r8
  int LastPossibleLeadoutStartTimeAsLba; // eax
  _QWORD v27[2]; // [rsp+30h] [rbp-10h] BYREF
  struct IDiscRecorder2Ex v28; // [rsp+80h] [rbp+40h] BYREF
  struct IUnknown *ppv; // [rsp+88h] [rbp+48h] BYREF
  __int64 v30; // [rsp+90h] [rbp+50h] BYREF

  v1 = 0;
  LODWORD(v28.lpVtbl) = 0;
  v3 = 0;
  v27[0] = 0;
  v27[1] = 0;
  ppv = 0;
  v30 = 0;
  *((_DWORD *)this + 274) = GetTickCount();
  if ( !*((_QWORD *)this + 24) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 25, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v7 = -1062599414;
    goto LABEL_41;
  }
  if ( *((_WORD *)this + 100) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 26, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v7 = -1062599421;
    goto LABEL_41;
  }
  Instance = ATL::CComObject<CMsftDiscFormat2TrackAtOnceEventArgs>::CreateInstance(&v30);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    v4 = (struct IDiscRecorder2Ex *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 345) < 4u )
    {
      goto LABEL_41;
    }
    v10 = 27;
    goto LABEL_18;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
  Instance = CoCreateInstance(
               &CLSID_MsftWriteEngine2,
               0,
               0x17u,
               &GUID_27354135_7f64_5b0f_8f00_5d77afbe261e,
               (LPVOID *)&ppv);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    v4 = (struct IDiscRecorder2Ex *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
    {
      goto LABEL_41;
    }
    v10 = 28;
    goto LABEL_18;
  }
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))ppv->lpVtbl[3].QueryInterface)(
               ppv,
               *((_QWORD *)this + 24));
  v7 = Instance;
  if ( Instance < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    v4 = (struct IDiscRecorder2Ex *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
    {
      goto LABEL_41;
    }
    v10 = 29;
    goto LABEL_18;
  }
  if ( *((_DWORD *)this + 23) != -16843010 )
    ATL::AtlThrowImpl(-2147467259);
  Instance = ATL::AtlAdvise(ppv, (struct IUnknown *)this + 6, v5, (unsigned int *)this + 23);
  v7 = Instance;
  if ( Instance >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))ppv->lpVtbl[5].Release)(ppv, 2352);
    if ( v7 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        31,
        WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
        (unsigned int)v7);
    }
    v3 = 1;
    goto LABEL_41;
  }
  v9 = WPP_GLOBAL_Control;
  v4 = (struct IDiscRecorder2Ex *)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
  {
    v10 = 30;
LABEL_18:
    WPP_SF_d(v9[42], v10, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, (unsigned int)Instance);
  }
LABEL_41:
  v11 = 0;
  v12 = 0;
  do
  {
    while ( 1 )
    {
      if ( v7 >= 0 )
      {
        CurrentPhysicalMediaType = Imapi2Utility::GetCurrentPhysicalMediaType(
                                     *((struct IDiscRecorder2Ex **)this + 24),
                                     &v28,
                                     (enum _IMAPI_MEDIA_PHYSICAL_TYPE *)v5);
        v7 = CurrentPhysicalMediaType;
        if ( CurrentPhysicalMediaType >= 0 )
        {
          lpVtbl = (unsigned __int8)v28.lpVtbl;
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)i >= 2 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 42),
                  33,
                  WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
                  LODWORD(v28.lpVtbl));
              }
              v7 = -1062599417;
              goto LABEL_74;
            }
            v4 = (struct IDiscRecorder2Ex *)&qword_18005A9F8;
            if ( *((_DWORD *)&qword_18005A9F8 + i) == LODWORD(v28.lpVtbl) )
              break;
          }
          CMsftDiscInformation::Init((CMsftDiscInformation *)v27, *((struct IDiscRecorder2Ex **)this + 24));
          LOBYTE(v4) = 3;
          v15 = *(_BYTE *)(v27[0] + 2LL);
          if ( (v15 & 3) != 0 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
            {
              v17 = 35;
              goto LABEL_62;
            }
LABEL_63:
            v7 = -1062599418;
            goto LABEL_74;
          }
          if ( *(_BYTE *)(v27[0] + 3LL) != 1 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
            {
              goto LABEL_63;
            }
            v17 = 36;
            goto LABEL_62;
          }
          if ( (v15 & 0xC) != 0 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
            {
              goto LABEL_63;
            }
            v17 = 37;
LABEL_62:
            WPP_SF_(v16[42], v17, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
            goto LABEL_63;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0 )
        {
          LOBYTE(v4) = 3;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              32,
              WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
              (unsigned int)CurrentPhysicalMediaType);
        }
      }
LABEL_74:
      if ( v1 || v7 < 0 )
        break;
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 23) + 72LL))(
             *((_QWORD *)this + 23),
             1,
             *((_QWORD *)this + 26));
      if ( v7 < 0 )
      {
        if ( v7 == -1062600175 )
          v7 = -1062599409;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            38,
            WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
            (unsigned int)v7);
        }
        break;
      }
      v12 = 1;
      LOBYTE(v4) = 1;
      v18 = Imapi2Utility::PreventAllowMediumRemoval(*((Imapi2Utility **)this + 24), v4, (unsigned __int8)v5, lpVtbl);
      v7 = v18;
      if ( v18 >= 0 )
      {
        v19 = CMsftDiscFormat2TrackAtOnce::CacheCurrentWriteParametersModePage(this);
        v7 = v19;
        if ( v19 >= 0 )
        {
          v19 = CMsftDiscFormat2TrackAtOnce::SendModifiedModePage(this);
          v7 = v19;
          if ( v19 >= 0 )
          {
            v19 = CMsftDiscFormat2TrackAtOnce::ValidateModePageParametersStuck(this);
            v7 = v19;
            if ( v19 >= 0
              || (v20 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == &WPP_GLOBAL_Control)
              || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
            {
              v11 = 1;
              break;
            }
            v21 = 42;
            goto LABEL_100;
          }
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
          {
            v21 = 41;
            goto LABEL_100;
          }
        }
        else
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
          {
            v21 = 40;
LABEL_100:
            WPP_SF_d(v20[42], v21, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, (unsigned int)v19);
          }
        }
        v1 = 1;
        v11 = 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            39,
            WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
            (unsigned int)v18);
        }
        v1 = 1;
      }
    }
    ++v1;
  }
  while ( v1 < 2 );
  v22 = v30;
  if ( v7 < 0 )
    goto LABEL_115;
  v7 = (*(__int64 (__fastcall **)(CMsftDiscFormat2TrackAtOnce *, _QWORD, _QWORD))(*(_QWORD *)this + 128LL))(
         this,
         *((unsigned int *)this + 277),
         *((unsigned __int16 *)this + 556));
  if ( v7 >= 0 )
  {
    *(_QWORD *)((char *)this + 1100) = 0;
    *((_DWORD *)this + 277) = -1;
    *((_WORD *)this + 108) = 0;
    *((_WORD *)this + 556) = 0;
    *((_DWORD *)this + 68) = CMsftDiscInformation::get_LastPossibleLeadoutStartTimeAsLba((CMsftDiscInformation *)v27)
                           + 150;
    LastPossibleLeadoutStartTimeAsLba = CMsftDiscInformation::get_LastPossibleLeadoutStartTimeAsLba((CMsftDiscInformation *)v27);
    *((_QWORD *)this + 35) = 0;
    *((_DWORD *)this + 69) = LastPossibleLeadoutStartTimeAsLba - 2;
    *((_DWORD *)this + 55) = v28.lpVtbl;
    *((_QWORD *)this + 32) = ppv;
    *((_QWORD *)this + 33) = v22;
    memset_0((char *)this + 288, 0, 0x324u);
    *((_WORD *)this + 100) = -1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        43,
        WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
        (unsigned int)v7);
    }
LABEL_115:
    if ( v3 )
    {
      v23 = ATL::AtlUnadvise(ppv, (const struct _GUID *)v4, *((_DWORD *)this + 23));
      *((_DWORD *)this + 23) = -16843010;
      if ( v23 < 0 )
      {
        v4 = (struct IDiscRecorder2Ex *)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            44,
            WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
            (unsigned int)v23);
        }
      }
    }
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( ppv )
    {
      ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
      ppv = 0;
    }
    LOBYTE(v4) = v11;
    CMsftDiscFormat2TrackAtOnce::CleanupFromPreparedMedia(this, (const struct _GUID *)v4, v12, lpVtbl);
  }
  if ( (v7 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v7, (int)&CLSID_MsftDiscFormat2TrackAtOnce, v24);
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)v27);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800389f0  mov     [rsp-38h+arg_18], rbx
0x1800389f5  push    rbp
0x1800389f6  push    rsi
0x1800389f7  push    rdi
0x1800389f8  push    r12
0x1800389fa  push    r13
0x1800389fc  push    r14
0x1800389fe  push    r15
0x180038a00  mov     rbp, rsp
0x180038a03  sub     rsp, 40h
0x180038a07  xor     r13d, r13d
0x180038a0a  mov     r15, rcx
0x180038a0d  mov     dword ptr [rbp+arg_0.lpVtbl], r13d
0x180038a11  mov     sil, r13b
0x180038a14  mov     [rbp+var_10], r13
0x180038a18  mov     [rbp+var_8], r13
0x180038a1c  mov     [rbp+arg_8], r13
0x180038a20  mov     [rbp+arg_10], r13
0x180038a24  call    cs:__imp_GetTickCount
0x180038a2a  mov     r14b, 3
0x180038a2d  mov     [r15+448h], eax
0x180038a34  lea     rax, WPP_GLOBAL_Control
0x180038a3b  mov     dil, 4
0x180038a3e  cmp     [r15+0C0h], r13
0x180038a45  jnz     short loc_180038A86
0x180038a47  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a4e  cmp     rcx, rax
0x180038a51  jz      short loc_180038A7C
0x180038a53  test    [rcx+15Ch], dil
0x180038a5a  jz      short loc_180038A7C
0x180038a5c  cmp     [rcx+159h], r14b
0x180038a63  jb      short loc_180038A7C
0x180038a65  mov     rcx, [rcx+150h]
0x180038a6c  lea     edx, [r13+19h]
0x180038a70  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038a77  call    WPP_SF_
0x180038a7c  mov     ebx, 0C0AA050Ah
0x180038a81  jmp     loc_180038CB4
0x180038a86  cmp     [r15+0C8h], r13w
0x180038a8e  jz      short loc_180038AD0
0x180038a90  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a97  cmp     rcx, rax
0x180038a9a  jz      short loc_180038AC6
0x180038a9c  test    [rcx+15Ch], dil
0x180038aa3  jz      short loc_180038AC6
0x180038aa5  cmp     [rcx+159h], r14b
0x180038aac  jb      short loc_180038AC6
0x180038aae  mov     rcx, [rcx+150h]
0x180038ab5  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038abc  mov     edx, 1Ah
0x180038ac1  call    WPP_SF_
0x180038ac6  mov     ebx, 0C0AA0503h
0x180038acb  jmp     loc_180038CB4
0x180038ad0  lea     rcx, [rbp+arg_10]
0x180038ad4  call    ?CreateInstance@?$CComObject@VCMsftDiscFormat2TrackAtOnceEventArgs@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMsftDiscFormat2TrackAtOnceEventArgs>::CreateInstance(ATL::CComObject<CMsftDiscFormat2TrackAtOnceEventArgs> * *)
0x180038ad9  mov     ebx, eax
0x180038adb  test    eax, eax
0x180038add  jns     short loc_180038B30
0x180038adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ae6  lea     rdx, WPP_GLOBAL_Control
0x180038aed  cmp     rcx, rdx
0x180038af0  jz      loc_180038CB4
0x180038af6  test    [rcx+15Ch], dil
0x180038afd  jz      loc_180038CB4
0x180038b03  cmp     [rcx+159h], dil
0x180038b0a  jb      loc_180038CB4
0x180038b10  mov     edx, 1Bh
0x180038b15  mov     rcx, [rcx+150h]
0x180038b1c  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038b23  mov     r9d, eax
0x180038b26  call    WPP_SF_d
0x180038b2b  jmp     loc_180038CB4
0x180038b30  mov     r12, [rbp+arg_10]
0x180038b34  mov     rcx, r12
0x180038b37  mov     rax, [r12]
0x180038b3b  mov     rax, [rax+8]
0x180038b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b44  xor     edx, edx; pUnkOuter
0x180038b46  lea     rax, [rbp+arg_8]
0x180038b4a  lea     r9, _GUID_27354135_7f64_5b0f_8f00_5d77afbe261e; riid
0x180038b51  mov     [rsp+40h+ppv], rax; ppv
0x180038b56  lea     rcx, CLSID_MsftWriteEngine2; rclsid
0x180038b5d  lea     r8d, [rdx+17h]; dwClsContext
0x180038b61  call    cs:__imp_CoCreateInstance
0x180038b67  mov     ebx, eax
0x180038b69  test    eax, eax
0x180038b6b  jns     short loc_180038BA8
0x180038b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b74  lea     rdx, WPP_GLOBAL_Control
0x180038b7b  cmp     rcx, rdx
0x180038b7e  jz      loc_180038CB4
0x180038b84  test    [rcx+15Ch], dil
0x180038b8b  jz      loc_180038CB4
0x180038b91  cmp     [rcx+159h], r14b
0x180038b98  jb      loc_180038CB4
0x180038b9e  mov     edx, 1Ch
0x180038ba3  jmp     loc_180038B15
0x180038ba8  mov     rcx, [rbp+arg_8]
0x180038bac  mov     rdx, [r15+0C0h]
0x180038bb3  mov     rax, [rcx]
0x180038bb6  mov     rax, [rax+48h]
0x180038bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bbf  mov     ebx, eax
0x180038bc1  test    eax, eax
0x180038bc3  jns     short loc_180038C00
0x180038bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180038bcc  lea     rdx, WPP_GLOBAL_Control
0x180038bd3  cmp     rcx, rdx
0x180038bd6  jz      loc_180038CB4
0x180038bdc  test    [rcx+15Ch], dil
0x180038be3  jz      loc_180038CB4
0x180038be9  cmp     [rcx+159h], r14b
0x180038bf0  jb      loc_180038CB4
0x180038bf6  mov     edx, 1Dh
0x180038bfb  jmp     loc_180038B15
0x180038c00  lea     rdx, [r15+30h]; struct IUnknown *
0x180038c04  lea     r9, [rdx+2Ch]; unsigned int *
0x180038c08  cmp     dword ptr [r9], 0FEFEFEFEh
0x180038c0f  jnz     loc_1800391B1
0x180038c15  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180038c19  call    ?AtlAdvise@ATL@@YAJPEAUIUnknown@@0AEBU_GUID@@PEAK@Z; ATL::AtlAdvise(IUnknown *,IUnknown *,_GUID const &,ulong *)
0x180038c1e  mov     ebx, eax
0x180038c20  test    eax, eax
0x180038c22  jns     short loc_180038C53
0x180038c24  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c2b  lea     rdx, WPP_GLOBAL_Control
0x180038c32  cmp     rcx, rdx
0x180038c35  jz      short loc_180038CB4
0x180038c37  test    [rcx+15Ch], dil
0x180038c3e  jz      short loc_180038CB4
0x180038c40  cmp     [rcx+159h], r14b
0x180038c47  jb      short loc_180038CB4
0x180038c49  mov     edx, 1Eh
0x180038c4e  jmp     loc_180038B15
0x180038c53  mov     rcx, [rbp+arg_8]
0x180038c57  mov     edx, 930h
0x180038c5c  mov     rax, [rcx]
0x180038c5f  mov     rax, [rax+88h]
0x180038c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c6b  mov     ebx, eax
0x180038c6d  test    eax, eax
0x180038c6f  jns     short loc_180038CB1
0x180038c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c78  lea     rax, WPP_GLOBAL_Control
0x180038c7f  cmp     rcx, rax
0x180038c82  jz      short loc_180038CB1
0x180038c84  test    [rcx+15Ch], dil
0x180038c8b  jz      short loc_180038CB1
0x180038c8d  cmp     [rcx+159h], r14b
0x180038c94  jb      short loc_180038CB1
0x180038c96  mov     rcx, [rcx+150h]
0x180038c9d  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038ca4  mov     edx, 1Fh
0x180038ca9  mov     r9d, ebx
0x180038cac  call    WPP_SF_d
0x180038cb1  mov     sil, 1
0x180038cb4  mov     r14b, r13b
0x180038cb7  lea     r12, WPP_GLOBAL_Control
0x180038cbe  mov     dil, r13b
0x180038cc1  test    ebx, ebx
0x180038cc3  js      loc_180038E32
0x180038cc9  mov     rcx, [r15+0C0h]; this
0x180038cd0  lea     rdx, [rbp+arg_0]; struct IDiscRecorder2Ex *
0x180038cd4  call    ?GetCurrentPhysicalMediaType@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z; Imapi2Utility::GetCurrentPhysicalMediaType(IDiscRecorder2Ex *,_IMAPI_MEDIA_PHYSICAL_TYPE *)
0x180038cd9  mov     ebx, eax
0x180038cdb  test    eax, eax
0x180038cdd  jns     short loc_180038D2A
0x180038cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ce6  cmp     rcx, r12
0x180038ce9  jz      loc_180038E32
0x180038cef  test    byte ptr [rcx+15Ch], 4
0x180038cf6  jz      loc_180038E32
0x180038cfc  mov     dl, 3
0x180038cfe  cmp     [rcx+159h], dl
0x180038d04  jb      loc_180038E32
0x180038d0a  mov     rcx, [rcx+150h]
0x180038d11  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038d18  mov     edx, 20h ; ' '
0x180038d1d  mov     r9d, eax
0x180038d20  call    WPP_SF_d
0x180038d25  jmp     loc_180038E32
0x180038d2a  mov     r9d, dword ptr [rbp+arg_0.lpVtbl]
0x180038d2e  xor     ecx, ecx
0x180038d30  cmp     ecx, 2
0x180038d33  jnb     loc_180038DF7
0x180038d39  lea     rdx, qword_18005A9F8
0x180038d40  cmp     [rdx+rcx*4], r9d
0x180038d44  jz      short loc_180038D4A
0x180038d46  inc     ecx
0x180038d48  jmp     short loc_180038D30
0x180038d4a  mov     rdx, [r15+0C0h]; struct IDiscRecorder2Ex *
0x180038d51  lea     rcx, [rbp+var_10]; this
0x180038d55  call    ?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscInformation::Init(IDiscRecorder2Ex *)
0x180038d5a  mov     rax, [rbp+var_10]
0x180038d5e  mov     dl, 3
0x180038d60  movzx   ecx, byte ptr [rax+2]
0x180038d64  test    dl, cl
0x180038d66  jz      short loc_180038D8C
0x180038d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d6f  cmp     rcx, r12
0x180038d72  jz      short loc_180038DC7
0x180038d74  test    byte ptr [rcx+15Ch], 4
0x180038d7b  jz      short loc_180038DC7
0x180038d7d  cmp     [rcx+159h], dl
0x180038d83  jb      short loc_180038DC7
0x180038d85  mov     edx, 23h ; '#'
0x180038d8a  jmp     short loc_180038DB4
0x180038d8c  cmp     byte ptr [rax+3], 1
0x180038d90  jz      short loc_180038DCE
0x180038d92  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d99  cmp     rcx, r12
0x180038d9c  jz      short loc_180038DC7
0x180038d9e  test    byte ptr [rcx+15Ch], 4
0x180038da5  jz      short loc_180038DC7
0x180038da7  cmp     [rcx+159h], dl
0x180038dad  jb      short loc_180038DC7
0x180038daf  mov     edx, 24h ; '$'
0x180038db4  mov     rcx, [rcx+150h]
0x180038dbb  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038dc2  call    WPP_SF_
0x180038dc7  mov     ebx, 0C0AA0506h
0x180038dcc  jmp     short loc_180038E32
0x180038dce  test    cl, 0Ch
0x180038dd1  jz      short loc_180038E32
0x180038dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180038dda  cmp     rcx, r12
0x180038ddd  jz      short loc_180038DC7
0x180038ddf  test    byte ptr [rcx+15Ch], 4
0x180038de6  jz      short loc_180038DC7
0x180038de8  cmp     [rcx+159h], dl
0x180038dee  jb      short loc_180038DC7
0x180038df0  mov     edx, 25h ; '%'
0x180038df5  jmp     short loc_180038DB4
0x180038df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180038dfe  cmp     rcx, r12
0x180038e01  jz      short loc_180038E2D
0x180038e03  test    byte ptr [rcx+15Ch], 4
0x180038e0a  jz      short loc_180038E2D
0x180038e0c  cmp     byte ptr [rcx+159h], 3
0x180038e13  jb      short loc_180038E2D
0x180038e15  mov     rcx, [rcx+150h]
0x180038e1c  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038e23  mov     edx, 21h ; '!'
0x180038e28  call    WPP_SF_d
0x180038e2d  mov     ebx, 0C0AA0507h
0x180038e32  test    r13d, r13d
0x180038e35  jnz     loc_180038FC9
0x180038e3b  test    ebx, ebx
0x180038e3d  js      loc_180038FC9
0x180038e43  mov     rcx, [r15+0B8h]
0x180038e4a  lea     edx, [r13+1]
0x180038e4e  mov     r8, [r15+0D0h]
0x180038e55  mov     rax, [rcx]
0x180038e58  mov     rax, [rax+48h]
0x180038e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e61  mov     ebx, eax
0x180038e63  test    eax, eax
0x180038e65  jns     short loc_180038EB6
0x180038e67  cmp     ebx, 0C0AA0211h
0x180038e6d  mov     eax, 0C0AA050Fh
0x180038e72  cmovz   ebx, eax
0x180038e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180038e7c  cmp     rcx, r12
0x180038e7f  jz      short loc_180038EAD
0x180038e81  test    byte ptr [rcx+15Ch], 4
0x180038e88  jz      short loc_180038EAD
0x180038e8a  cmp     byte ptr [rcx+159h], 3
0x180038e91  jb      short loc_180038EAD
0x180038e93  mov     rcx, [rcx+150h]
0x180038e9a  lea     edx, [r13+26h]
0x180038e9e  mov     r9d, ebx
0x180038ea1  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038ea8  call    WPP_SF_d
0x180038ead  test    ebx, ebx
0x180038eaf  jns     short loc_180038EB9
0x180038eb1  jmp     loc_180038FC9
0x180038eb6  mov     dil, 1
0x180038eb9  mov     rcx, [r15+0C0h]; this
0x180038ec0  mov     dl, 1; struct IDiscRecorder2Ex *
0x180038ec2  call    ?PreventAllowMediumRemoval@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EE@Z; Imapi2Utility::PreventAllowMediumRemoval(IDiscRecorder2Ex *,uchar,uchar)
0x180038ec7  mov     ebx, eax
0x180038ec9  test    eax, eax
0x180038ecb  jns     short loc_180038F0E
0x180038ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ed4  cmp     rcx, r12
0x180038ed7  jz      short loc_180038F06
0x180038ed9  test    byte ptr [rcx+15Ch], 4
0x180038ee0  jz      short loc_180038F06
0x180038ee2  cmp     byte ptr [rcx+159h], 3
0x180038ee9  jb      short loc_180038F06
0x180038eeb  mov     rcx, [rcx+150h]
0x180038ef2  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038ef9  mov     edx, 27h ; '''
0x180038efe  mov     r9d, eax
0x180038f01  call    WPP_SF_d
0x180038f06  inc     r13d
0x180038f09  jmp     loc_180038CC1
0x180038f0e  mov     rcx, r15; this
0x180038f11  call    ?CacheCurrentWriteParametersModePage@CMsftDiscFormat2TrackAtOnce@@AEAAJXZ; CMsftDiscFormat2TrackAtOnce::CacheCurrentWriteParametersModePage(void)
0x180038f16  mov     ebx, eax
  ... truncated ...
```
