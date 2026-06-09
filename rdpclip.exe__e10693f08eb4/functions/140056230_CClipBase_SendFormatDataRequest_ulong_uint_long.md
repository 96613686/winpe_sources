# CClipBase::SendFormatDataRequest(ulong,uint,long *)

- ea: `0x140056230`
- end: `0x140056a13`
- name: `?SendFormatDataRequest@CClipBase@@UEAAJKIPEAJ@Z`
- size: `2019`
- prototype: `int(CClipBase *__hidden this, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x14000a640`
- `0x14000cae0`
- `0x140010ed4`
- `0x140039df4`
- `0x140043bc8`
- `0x140045ce0`
- `0x140046190`
- `0x1400476f0`
- `0x14004ce20`
- `0x140050940`
- `0x140056230`
- `0x14006a0e2`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005634f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005634f`

## string_xrefs

- `0x14005687a`: `CreateClipboardPdu failed!`
- `0x14005657f`: `UpdateContext failed.`
- `0x140056727`: `OpenVirtualChannel failed`

## pseudocode

```c
__int64 __fastcall CClipBase::SendFormatDataRequest(CClipBase *this, unsigned int a2, unsigned int a3, int *a4)
{
  unsigned int v4; // ebx
  bool v5; // zf
  int CanAcquireUniqueId; // edi
  unsigned __int8 v9; // r12
  int v10; // r9d
  struct IRdrVirtualChannel *v11; // r10
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  PVOID *v16; // rax
  unsigned int v17; // eax
  int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // rbx
  CLIPBOARD_DATA_CHANNEL_CONTEXT *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  int v24; // ebx
  unsigned int v25; // eax
  const unsigned __int16 * near *v26; // rbx
  unsigned int v27; // eax
  unsigned int v28; // ebx
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  unsigned int v32; // edi
  int v33; // ebx
  unsigned int v34; // eax
  int v35; // ebx
  char *v36; // r13
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned int v39; // eax
  int v41; // [rsp+28h] [rbp-59h]
  struct IRdrVirtualChannel **v42; // [rsp+30h] [rbp-51h]
  int v43; // [rsp+48h] [rbp-39h] BYREF
  struct IRdrVirtualChannel *v44; // [rsp+50h] [rbp-31h] BYREF
  int v45; // [rsp+58h] [rbp-29h]
  int v46; // [rsp+5Ch] [rbp-25h] BYREF
  int v47; // [rsp+60h] [rbp-21h] BYREF
  unsigned int v48; // [rsp+64h] [rbp-1Dh] BYREF
  unsigned int v49; // [rsp+68h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-11h] BYREF
  __int16 v51[2]; // [rsp+78h] [rbp-9h] BYREF
  unsigned int v52; // [rsp+7Ch] [rbp-5h]
  unsigned int v53; // [rsp+80h] [rbp-1h]
  struct IRdrVirtualChannel *v54; // [rsp+88h] [rbp+7h] BYREF
  _BYTE v55[72]; // [rsp+90h] [rbp+Fh] BYREF
  int Src; // [rsp+E8h] [rbp+67h] BYREF
  unsigned int v57; // [rsp+ECh] [rbp+6Bh]
  unsigned int v58; // [rsp+F8h] [rbp+77h]
  int *v59; // [rsp+100h] [rbp+7Fh]

  v59 = a4;
  v58 = a3;
  v4 = a3;
  v5 = *((_DWORD *)this + 75) == 1;
  hMem = 0;
  v49 = 0;
  v48 = 0;
  v43 = 0;
  v44 = 0;
  if ( !v5 )
  {
    CanAcquireUniqueId = -2092629014;
    goto LABEL_105;
  }
  v9 = *((_BYTE *)this + 136);
  v45 = *((_DWORD *)this + 55);
  if ( !v45 )
  {
    CanAcquireUniqueId = -2147467259;
    v46 = -2147467259;
    Src = 0;
    v47 = 0;
    CheckClipboardStateTable(11, v9, &v47, &Src, &v46);
    if ( Src )
      CanAcquireUniqueId = v46;
    if ( v47 )
      goto LABEL_105;
  }
  CanAcquireUniqueId = CFormatIdMap::LookupRemoteId((CClipBase *)((char *)this + 152), v4, &v48);
  if ( CanAcquireUniqueId < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        208,
        &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        CurrentThreadActivityIdPrefix,
        v4,
        CanAcquireUniqueId);
    }
    LocalFree(hMem);
    goto LABEL_105;
  }
  if ( v10 )
  {
    Src = (int)v11;
    if ( v44 != v11 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v44);
      v44 = 0;
      TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v44);
    }
    CanAcquireUniqueId = CProxyDataObjectManager::CanAcquireUniqueId(*((CProxyDataObjectManager **)this + 28), a2, &Src);
    if ( CanAcquireUniqueId < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 209;
      v15 = "CanAcquireUniqueId failed";
      goto LABEL_23;
    }
    if ( Src )
      goto LABEL_45;
    CanAcquireUniqueId = CDataChannelManager::GetDataChannel(*((CDataChannelManager **)this + 100), a2, &v43, &v44);
    if ( CanAcquireUniqueId >= 0 )
    {
      v54 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = v43;
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          211,
          &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
          v19,
          v18,
          a2);
        v4 = v58;
      }
      v9 = 2;
      v53 = v4;
      v52 = a2;
      v51[0] = 514;
      if ( v44 )
      {
        TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v54);
        v54 = v44;
        TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v54);
      }
      v20 = *((_QWORD *)this + 100);
      v21 = CLIPBOARD_DATA_CHANNEL_CONTEXT::CLIPBOARD_DATA_CHANNEL_CONTEXT(
              (CLIPBOARD_DATA_CHANNEL_CONTEXT *)v55,
              (const struct CLIPBOARD_DATA_CHANNEL_CONTEXT *)v51);
      CanAcquireUniqueId = CDataChannelManager::UpdateContext(v20, v43, (__int64)v21);
      if ( CanAcquireUniqueId < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v42) = CanAcquireUniqueId;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          212,
          (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
          v22,
          (__int64)"UpdateContext failed.",
          v42);
      }
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v54);
      v4 = v58;
    }
    else
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        210,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v17,
        (__int64)"GetDataChannel failed.",
        CanAcquireUniqueId);
    }
    v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_43:
    if ( !v44 )
      goto LABEL_46;
    if ( (*(unsigned int (__fastcall **)(struct IRdrVirtualChannel *))(*(_QWORD *)v44 + 72LL))(v44) )
      goto LABEL_60;
LABEL_45:
    v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_46:
    LOBYTE(Src) = 0;
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v23, a2);
    }
    CanAcquireUniqueId = CClipBase::GetDynamicVirtualChannel(
                           (CClipBase *)((char *)this - 48),
                           a2,
                           v4,
                           (unsigned __int8 *)&Src,
                           &v43,
                           &v44);
    if ( CanAcquireUniqueId < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 214;
      v15 = "GetDynamicVirtualChannel failed.";
      goto LABEL_23;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v24 = v43;
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        215,
        &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v25,
        v24,
        a2);
    }
    v9 = Src;
LABEL_60:
    if ( !v44
      || (*(unsigned int (__fastcall **)(struct IRdrVirtualChannel *))(*(_QWORD *)v44 + 72LL))(v44)
      || (CanAcquireUniqueId = (*(__int64 (__fastcall **)(struct IRdrVirtualChannel *))(*(_QWORD *)v44 + 56LL))(v44),
          CanAcquireUniqueId >= 0) )
    {
      v47 = -2147467259;
      Src = 0;
      v46 = 0;
      CheckClipboardStateTable(11, v9, &v46, &Src, &v47);
      if ( Src )
        CanAcquireUniqueId = v47;
      if ( v46 )
        goto LABEL_105;
      goto LABEL_70;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_105;
    }
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 216;
    v15 = "OpenVirtualChannel failed";
LABEL_23:
    LODWORD(v42) = CanAcquireUniqueId;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      v13,
      (__int64)v15,
      v42);
    goto LABEL_105;
  }
  v43 = (int)v11;
  if ( *((struct IRdrVirtualChannel **)this + 73) == v44 )
    goto LABEL_71;
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v44);
  v44 = (struct IRdrVirtualChannel *)*((_QWORD *)this + 73);
  TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v44);
LABEL_70:
  v10 = v45;
LABEL_71:
  if ( (unsigned __int8)(v9 - 2) > 4u && v9 < 9u )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = (&g_rgszStateStrings)[v9];
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        217,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v27,
        (__int64)v26);
    }
    CanAcquireUniqueId = -2147467259;
    goto LABEL_105;
  }
  v28 = v10 != 0 ? 8 : 4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v29);
  }
  LOWORD(v41) = 0;
  CanAcquireUniqueId = (*(__int64 (__fastcall **)(struct IRdrVirtualChannel *, HLOCAL *, unsigned int *, __int64, int, unsigned int))(*(_QWORD *)v44 + 32LL))(
                         v44,
                         &hMem,
                         &v49,
                         4,
                         v41,
                         v28);
  if ( CanAcquireUniqueId < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_105;
    }
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 219;
    v15 = "CreateClipboardPdu failed!";
    goto LABEL_23;
  }
  v32 = v48;
  if ( v45 )
  {
    v57 = v48;
    Src = v43;
    memcpy_0((char *)hMem + 8, &Src, v28);
  }
  else
  {
    *((_DWORD *)hMem + 2) = v48;
    *((_DWORD *)this + 73) = v58;
    *((_DWORD *)this + 72) = a2;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v33 = v43;
    v34 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      222,
      &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      v34,
      v58,
      v32,
      v33);
  }
  v35 = v45;
  if ( v45 )
  {
    LOBYTE(v31) = 5;
    (*(void (__fastcall **)(CClipBase *, _QWORD, __int64, __int64))(*(_QWORD *)this + 40LL))(
      this,
      (unsigned int)v43,
      v31,
      11);
    v36 = (char *)this - 48;
  }
  else
  {
    v36 = (char *)this - 48;
    LOBYTE(v30) = 5;
    (*(void (__fastcall **)(char *, __int64, __int64))(*((_QWORD *)this - 6) + 24LL))((char *)this - 48, v30, 11);
  }
  CanAcquireUniqueId = (*(__int64 (__fastcall **)(struct IRdrVirtualChannel *, HLOCAL, _QWORD))(*(_QWORD *)v44 + 40LL))(
                         v44,
                         hMem,
                         v49);
  if ( CanAcquireUniqueId < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        223,
        &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v39,
        CanAcquireUniqueId);
    }
    if ( v35 )
    {
      LOBYTE(v38) = v9;
      (*(void (__fastcall **)(CClipBase *, _QWORD, __int64, __int64))(*(_QWORD *)this + 40LL))(
        this,
        (unsigned int)v43,
        v38,
        11);
    }
    else
    {
      LOBYTE(v37) = v9;
      (*(void (__fastcall **)(char *, __int64, __int64))(*(_QWORD *)v36 + 24LL))(v36, v37, 11);
    }
  }
LABEL_105:
  *v59 = v43;
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v44);
  return (unsigned int)CanAcquireUniqueId;
}

```

## disassembly

```asm
0x140056230  mov     rax, rsp
0x140056233  mov     [rax+10h], rbx
0x140056237  mov     [rax+20h], r9
0x14005623b  mov     [rax+18h], r8d
0x14005623f  push    rbp
0x140056240  push    rsi
0x140056241  push    rdi
0x140056242  push    r12
0x140056244  push    r13
0x140056246  push    r14
0x140056248  push    r15
0x14005624a  lea     rbp, [rax-5Fh]
0x14005624e  sub     rsp, 0A0h
0x140056255  xor     r10d, r10d
0x140056258  mov     ebx, r8d
0x14005625b  cmp     dword ptr [rcx+12Ch], 1
0x140056262  mov     r13d, edx
0x140056265  mov     r14, rcx
0x140056268  mov     [rbp+57h+hMem], r10
0x14005626c  mov     [rbp+57h+var_70], r10d
0x140056270  mov     [rbp+57h+var_74], r10d
0x140056274  mov     [rbp+57h+var_90], r10d
0x140056278  mov     [rbp+57h+var_88], r10
0x14005627c  jz      short loc_140056288
0x14005627e  mov     edi, 834503EAh
0x140056283  jmp     loc_1400569E4
0x140056288  mov     r9d, [rcx+0DCh]
0x14005628f  mov     eax, 80004005h
0x140056294  mov     r12b, [rcx+88h]
0x14005629b  mov     [rbp+57h+var_80], r9d
0x14005629f  test    r9d, r9d
0x1400562a2  jnz     short loc_1400562E8
0x1400562a4  mov     edi, eax
0x1400562a6  mov     [rbp+57h+var_7C], eax
0x1400562a9  lea     rax, [rbp+57h+var_7C]
0x1400562ad  mov     [rbp+57h+Src], r10d
0x1400562b1  lea     r9, [rbp+57h+Src]; int *
0x1400562b5  mov     [rsp+0D0h+var_B0], rax; int *
0x1400562ba  lea     r8, [rbp+57h+var_78]; int *
0x1400562be  mov     [rbp+57h+var_78], r10d
0x1400562c2  mov     dl, r12b; unsigned __int8
0x1400562c5  mov     ecx, 0Bh; int
0x1400562ca  call    ?CheckClipboardStateTable@@YAXJEPEAH0PEAJ@Z; CheckClipboardStateTable(long,uchar,int *,int *,long *)
0x1400562cf  xor     r10d, r10d
0x1400562d2  cmp     [rbp+57h+Src], r10d
0x1400562d6  cmovnz  edi, [rbp+57h+var_7C]
0x1400562da  cmp     [rbp+57h+var_78], r10d
0x1400562de  jnz     loc_1400569E4
0x1400562e4  mov     r9d, [rbp+57h+var_80]
0x1400562e8  lea     rcx, [r14+98h]; this
0x1400562ef  mov     edx, ebx; unsigned int
0x1400562f1  lea     r8, [rbp+57h+var_74]; unsigned int *
0x1400562f5  call    ?LookupRemoteId@CFormatIdMap@@QEAAJIPEAI@Z; CFormatIdMap::LookupRemoteId(uint,uint *)
0x1400562fa  mov     edi, eax
0x1400562fc  test    eax, eax
0x1400562fe  jns     short loc_14005635A
0x140056300  mov     rax, cs:WPP_GLOBAL_Control
0x140056307  lea     rsi, WPP_GLOBAL_Control
0x14005630e  cmp     rax, rsi
0x140056311  jz      short loc_14005634B
0x140056313  test    byte ptr [rax+1Ch], 1
0x140056317  jz      short loc_14005634B
0x140056319  cmp     byte ptr [rax+19h], 5
0x14005631d  jb      short loc_14005634B
0x14005631f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140056324  mov     rcx, cs:WPP_GLOBAL_Control
0x14005632b  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140056332  mov     edx, 0D0h
0x140056337  mov     dword ptr [rsp+0D0h+var_A8], edi
0x14005633b  mov     r9d, eax
0x14005633e  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x140056342  mov     rcx, [rcx+10h]
0x140056346  call    WPP_SF_DdD
0x14005634b  mov     rcx, [rbp+57h+hMem]; hMem
0x14005634f  call    cs:__imp_LocalFree
0x140056355  jmp     loc_1400569E4
0x14005635a  lea     rsi, WPP_GLOBAL_Control
0x140056361  lea     r15, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140056368  test    r9d, r9d
0x14005636b  jnz     short loc_1400563A4
0x14005636d  mov     rax, [rbp+57h+var_88]
0x140056371  mov     [rbp+57h+var_90], r10d
0x140056375  cmp     [r14+248h], rax
0x14005637c  jz      loc_140056772
0x140056382  lea     rcx, [rbp+57h+var_88]
0x140056386  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14005638b  mov     rax, [r14+248h]
0x140056392  lea     rcx, [rbp+57h+var_88]
0x140056396  mov     [rbp+57h+var_88], rax
0x14005639a  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14005639f  jmp     loc_14005676E
0x1400563a4  mov     [rbp+57h+Src], r10d
0x1400563a8  cmp     [rbp+57h+var_88], r10
0x1400563ac  jz      short loc_1400563C8
0x1400563ae  lea     rcx, [rbp+57h+var_88]
0x1400563b2  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400563b7  lea     rcx, [rbp+57h+var_88]
0x1400563bb  mov     [rbp+57h+var_88], 0
0x1400563c3  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x1400563c8  mov     rcx, [r14+0E0h]; this
0x1400563cf  lea     r8, [rbp+57h+Src]; int *
0x1400563d3  mov     edx, r13d; unsigned int
0x1400563d6  call    ?CanAcquireUniqueId@CProxyDataObjectManager@@QEAAJKPEAH@Z; CProxyDataObjectManager::CanAcquireUniqueId(ulong,int *)
0x1400563db  mov     edi, eax
0x1400563dd  test    eax, eax
0x1400563df  jns     short loc_14005643A
0x1400563e1  mov     rax, cs:WPP_GLOBAL_Control
0x1400563e8  cmp     rax, rsi
0x1400563eb  jz      loc_1400569E4
0x1400563f1  test    byte ptr [rax+1Ch], 8
0x1400563f5  jz      loc_1400569E4
0x1400563fb  cmp     byte ptr [rax+19h], 2
0x1400563ff  jb      loc_1400569E4
0x140056405  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005640a  mov     edx, 0D1h
0x14005640f  lea     rcx, aCanacquireuniq; "CanAcquireUniqueId failed"
0x140056416  mov     dword ptr [rsp+0D0h+var_A8], edi
0x14005641a  mov     r9d, eax
0x14005641d  mov     [rsp+0D0h+var_B0], rcx
0x140056422  mov     r8, r15
0x140056425  mov     rcx, cs:WPP_GLOBAL_Control
0x14005642c  mov     rcx, [rcx+10h]
0x140056430  call    WPP_SF_DsD
0x140056435  jmp     loc_1400569E4
0x14005643a  cmp     [rbp+57h+Src], 0
0x14005643e  jnz     loc_1400565DA
0x140056444  mov     rcx, [r14+320h]; this
0x14005644b  lea     r9, [rbp+57h+var_88]; struct IRdrVirtualChannel **
0x14005644f  lea     r8, [rbp+57h+var_90]; int *
0x140056453  mov     edx, r13d; unsigned int
0x140056456  call    ?GetDataChannel@CDataChannelManager@@QEAAJKPEAJPEAPEAVIRdrVirtualChannel@@@Z; CDataChannelManager::GetDataChannel(ulong,long *,IRdrVirtualChannel * *)
0x14005645b  mov     edi, eax
0x14005645d  test    eax, eax
0x14005645f  jns     short loc_1400564BA
0x140056461  mov     rax, cs:WPP_GLOBAL_Control
0x140056468  cmp     rax, rsi
0x14005646b  jz      loc_1400565BD
0x140056471  test    byte ptr [rax+1Ch], 8
0x140056475  jz      loc_1400565BD
0x14005647b  cmp     byte ptr [rax+19h], 2
0x14005647f  jb      loc_1400565BD
0x140056485  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005648a  lea     rcx, aGetdatachannel; "GetDataChannel failed."
0x140056491  mov     dword ptr [rsp+0D0h+var_A8], edi
0x140056495  mov     [rsp+0D0h+var_B0], rcx
0x14005649a  mov     edx, 0D2h
0x14005649f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400564a6  mov     r9d, eax
0x1400564a9  mov     r8, r15
0x1400564ac  mov     rcx, [rcx+10h]
0x1400564b0  call    WPP_SF_DsD
0x1400564b5  jmp     loc_1400565B6
0x1400564ba  mov     [rbp+57h+var_50], 0
0x1400564c2  mov     rax, cs:WPP_GLOBAL_Control
0x1400564c9  cmp     rax, rsi
0x1400564cc  jz      short loc_140056509
0x1400564ce  test    byte ptr [rax+1Ch], 1
0x1400564d2  jz      short loc_140056509
0x1400564d4  cmp     byte ptr [rax+19h], 2
0x1400564d8  jb      short loc_140056509
0x1400564da  mov     ebx, [rbp+57h+var_90]
0x1400564dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400564e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400564e9  mov     edx, 0D3h
0x1400564ee  mov     dword ptr [rsp+0D0h+var_A8], r13d
0x1400564f3  mov     r9d, eax
0x1400564f6  mov     r8, r15
0x1400564f9  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1400564fd  mov     rcx, [rcx+10h]
0x140056501  call    WPP_SF_DdD
0x140056506  mov     ebx, [rbp+57h+arg_10]
0x140056509  cmp     [rbp+57h+var_88], 0
0x14005650e  mov     r12b, 2
0x140056511  mov     [rbp+57h+var_58], ebx
0x140056514  mov     [rbp+57h+var_5C], r13d
0x140056518  mov     [rbp+57h+var_60], 202h
0x14005651e  jz      short loc_14005653A
0x140056520  lea     rcx, [rbp+57h+var_50]
0x140056524  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140056529  mov     rax, [rbp+57h+var_88]
0x14005652d  lea     rcx, [rbp+57h+var_50]
0x140056531  mov     [rbp+57h+var_50], rax
0x140056535  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14005653a  mov     rbx, [r14+320h]
0x140056541  lea     rdx, [rbp+57h+var_60]; struct CLIPBOARD_DATA_CHANNEL_CONTEXT *
0x140056545  lea     rcx, [rbp+57h+var_48]; this
0x140056549  call    ??0CLIPBOARD_DATA_CHANNEL_CONTEXT@@QEAA@AEBU0@@Z; CLIPBOARD_DATA_CHANNEL_CONTEXT::CLIPBOARD_DATA_CHANNEL_CONTEXT(CLIPBOARD_DATA_CHANNEL_CONTEXT const &)
0x14005654e  mov     edx, [rbp+57h+var_90]
0x140056551  mov     r8, rax
0x140056554  mov     rcx, rbx
0x140056557  call    ?UpdateContext@CDataChannelManager@@QEAAJJUCLIPBOARD_DATA_CHANNEL_CONTEXT@@@Z; CDataChannelManager::UpdateContext(long,CLIPBOARD_DATA_CHANNEL_CONTEXT)
0x14005655c  mov     edi, eax
0x14005655e  test    eax, eax
0x140056560  jns     short loc_1400565AA
0x140056562  mov     rax, cs:WPP_GLOBAL_Control
0x140056569  cmp     rax, rsi
0x14005656c  jz      short loc_1400565AA
0x14005656e  test    byte ptr [rax+1Ch], 8
0x140056572  jz      short loc_1400565AA
0x140056574  cmp     [rax+19h], r12b
0x140056578  jb      short loc_1400565AA
0x14005657a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005657f  lea     rcx, aUpdatecontextF; "UpdateContext failed."
0x140056586  mov     dword ptr [rsp+0D0h+var_A8], edi
0x14005658a  mov     [rsp+0D0h+var_B0], rcx
0x14005658f  mov     edx, 0D4h
0x140056594  mov     rcx, cs:WPP_GLOBAL_Control
0x14005659b  mov     r9d, eax
0x14005659e  mov     r8, r15
0x1400565a1  mov     rcx, [rcx+10h]
0x1400565a5  call    WPP_SF_DsD
0x1400565aa  lea     rcx, [rbp+57h+var_50]
0x1400565ae  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400565b3  mov     ebx, [rbp+57h+arg_10]
0x1400565b6  mov     rax, cs:WPP_GLOBAL_Control
0x1400565bd  mov     rcx, [rbp+57h+var_88]
0x1400565c1  test    rcx, rcx
0x1400565c4  jz      short loc_1400565E1
0x1400565c6  mov     rax, [rcx]
0x1400565c9  mov     rax, [rax+48h]
0x1400565cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400565d2  test    eax, eax
0x1400565d4  jnz     loc_1400566C8
0x1400565da  mov     rax, cs:WPP_GLOBAL_Control
0x1400565e1  mov     byte ptr [rbp+57h+Src], 0
0x1400565e5  cmp     rax, rsi
0x1400565e8  jz      short loc_14005661B
0x1400565ea  test    byte ptr [rax+1Ch], 1
0x1400565ee  jz      short loc_14005661B
0x1400565f0  cmp     byte ptr [rax+19h], 5
0x1400565f4  jb      short loc_14005661B
0x1400565f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400565fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140056602  mov     edx, 0D5h
0x140056607  mov     r9d, eax
0x14005660a  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x14005660f  mov     r8, r15
0x140056612  mov     rcx, [rcx+10h]
0x140056616  call    WPP_SF_Dd
0x14005661b  lea     rax, [rbp+57h+var_88]
0x14005661f  mov     r8d, ebx; unsigned int
0x140056622  mov     [rsp+0D0h+var_A8], rax; struct IRdrVirtualChannel **
0x140056627  lea     r9, [rbp+57h+Src]; unsigned __int8 *
0x14005662b  lea     rax, [rbp+57h+var_90]
0x14005662f  mov     edx, r13d; unsigned int
0x140056632  lea     rcx, [r14-30h]; this
0x140056636  mov     [rsp+0D0h+var_B0], rax; int *
0x14005663b  call    ?GetDynamicVirtualChannel@CClipBase@@AEAAJKIPEAEPEAJPEAPEAVIRdrVirtualChannel@@@Z; CClipBase::GetDynamicVirtualChannel(ulong,uint,uchar *,long *,IRdrVirtualChannel * *)
0x140056640  mov     edi, eax
0x140056642  test    eax, eax
0x140056644  jns     short loc_140056680
0x140056646  mov     rax, cs:WPP_GLOBAL_Control
0x14005664d  cmp     rax, rsi
0x140056650  jz      loc_1400569E4
0x140056656  test    byte ptr [rax+1Ch], 8
0x14005665a  jz      loc_1400569E4
0x140056660  cmp     byte ptr [rax+19h], 2
0x140056664  jb      loc_1400569E4
0x14005666a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005666f  mov     edx, 0D6h
0x140056674  lea     rcx, aGetdynamicvirt; "GetDynamicVirtualChannel failed."
0x14005667b  jmp     loc_140056416
0x140056680  mov     rax, cs:WPP_GLOBAL_Control
0x140056687  cmp     rax, rsi
0x14005668a  jz      short loc_1400566C4
0x14005668c  test    byte ptr [rax+1Ch], 1
0x140056690  jz      short loc_1400566C4
0x140056692  cmp     byte ptr [rax+19h], 5
0x140056696  jb      short loc_1400566C4
0x140056698  mov     ebx, [rbp+57h+var_90]
0x14005669b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400566a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400566a7  mov     edx, 0D7h
0x1400566ac  mov     dword ptr [rsp+0D0h+var_A8], r13d
0x1400566b1  mov     r9d, eax
0x1400566b4  mov     r8, r15
0x1400566b7  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1400566bb  mov     rcx, [rcx+10h]
0x1400566bf  call    WPP_SF_DdD
0x1400566c4  mov     r12b, byte ptr [rbp+57h+Src]
0x1400566c8  mov     rcx, [rbp+57h+var_88]
0x1400566cc  xor     ebx, ebx
0x1400566ce  test    rcx, rcx
0x1400566d1  jz      short loc_140056733
0x1400566d3  mov     rax, [rcx]
0x1400566d6  mov     rax, [rax+48h]
0x1400566da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400566df  test    eax, eax
0x1400566e1  jnz     short loc_140056733
0x1400566e3  mov     rcx, [rbp+57h+var_88]
0x1400566e7  mov     rax, [rcx]
0x1400566ea  mov     rax, [rax+38h]
0x1400566ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400566f3  mov     edi, eax
0x1400566f5  test    eax, eax
0x1400566f7  jns     short loc_140056733
0x1400566f9  mov     rax, cs:WPP_GLOBAL_Control
0x140056700  cmp     rax, rsi
0x140056703  jz      loc_1400569E4
0x140056709  test    byte ptr [rax+1Ch], 8
  ... truncated ...
```
