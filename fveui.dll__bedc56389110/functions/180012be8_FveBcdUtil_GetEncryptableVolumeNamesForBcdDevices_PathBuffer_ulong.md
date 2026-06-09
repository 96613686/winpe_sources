# FveBcdUtil::GetEncryptableVolumeNamesForBcdDevices(PathBuffer * *,ulong *)

- ea: `0x180012be8`
- end: `0x1800132c1`
- name: `?GetEncryptableVolumeNamesForBcdDevices@FveBcdUtil@@SAJPEAPEAVPathBuffer@@PEAK@Z`
- size: `1753`
- prototype: `__int64 __fastcall(struct PathBuffer **, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update`

## callers

- `0x180007360`

## callees

- `0x180001248`
- `0x180001318`
- `0x180001bb0`
- `0x180002028`
- `0x180002774`
- `0x1800027e0`
- `0x1800027ec`
- `0x180002810`
- `0x18000281c`
- `0x1800037a0`
- `0x180004bd4`
- `0x18000b9f8`
- `0x18000e354`
- `0x18000ff64`
- `0x180011f5c`
- `0x180011fb8`
- `0x180012010`
- `0x180012be8`
- `0x1800132c8`
- `0x180013660`

## import_xrefs

- `bcd!BcdOpenSystemStore` at `0x180012c84`
- `bcd!BcdOpenSystemStore` at `0x180012c84`
- `bcd!BcdCloseStore` at `0x1800131e6`
- `bcd!BcdCloseStore` at `0x1800131e6`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetEncryptableVolumeNamesForBcdDevices(struct PathBuffer **a1, unsigned int *a2)
{
  __int64 v2; // rdx
  int v3; // r13d
  NTSTATUS v4; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned __int64 v10; // rbx
  PathBuffer *v11; // rdi
  __int64 v12; // rax
  bool v13; // cf
  unsigned __int64 v14; // rax
  unsigned __int64 *v15; // rax
  __int64 v16; // rdx
  void *(*v17)(void *); // r9
  int UniqueBcdDevicePaths; // eax
  __int64 v19; // r14
  __int64 v20; // rax
  unsigned __int64 v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rdx
  void *(*v24)(void *); // r9
  PathBuffer *v25; // rsi
  __int64 v26; // r14
  __int64 v27; // r15
  int v28; // eax
  int v29; // eax
  int IsVolumeEncryptable_0; // eax
  int VolumeNameW_0; // eax
  int v32; // eax
  PVOID *v33; // rcx
  __int64 v34; // rdx
  PVOID *v35; // rcx
  PVOID *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  unsigned int v41[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v42; // [rsp+38h] [rbp-C8h] BYREF
  int v43; // [rsp+40h] [rbp-C0h] BYREF
  void *v44; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  struct PathBuffer **v46; // [rsp+58h] [rbp-A8h]
  _BYTE v47[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v48[264]; // [rsp+80h] [rbp-80h] BYREF

  v45 = (__int64)a2;
  v46 = a1;
  v42 = -1;
  v44 = 0;
  v43 = 0;
  memset_0(v48, 0, 0x208u);
  v3 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids);
  v4 = BcdOpenSystemStore(&v44, v2);
  v5 = FromNtStatus(v4);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_100;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)v5);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 0x40) == 0 )
      goto LABEL_100;
    v8 = 48;
    v9 = v6;
    goto LABEL_98;
  }
  v10 = 10;
  v11 = 0;
  for ( v41[0] = 10; ; v10 = v41[0] )
  {
    if ( v11 )
      PathBuffer::`vector deleting destructor'(v11);
    v12 = 8 * v10;
    if ( !is_mul_ok(v10, 8u) )
      v12 = -1;
    v13 = __CFADD__(v12, 8);
    v14 = v12 + 8;
    if ( v13 )
      v14 = -1;
    v15 = (unsigned __int64 *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v15
      || (v11 = (PathBuffer *)(v15 + 1),
          *v15 = v10,
          `vector constructor iterator'((PathBuffer *)(v15 + 1), v16, v10, v17),
          !v11) )
    {
      v6 = -2147024882;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_100;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          2147942414LL);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 0x40) == 0 )
        goto LABEL_100;
      v8 = 50;
      v9 = 2147942414LL;
LABEL_98:
      WPP_SF_d(v7[2], v8, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v9);
      goto LABEL_99;
    }
    UniqueBcdDevicePaths = FveBcdUtil::GetUniqueBcdDevicePaths(v44, v11, v41);
    v6 = UniqueBcdDevicePaths;
    if ( UniqueBcdDevicePaths != -2147024774 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, 2147942522LL);
  }
  if ( UniqueBcdDevicePaths < 0 )
  {
    v36 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          (unsigned int)UniqueBcdDevicePaths);
        v36 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 0x40) != 0 )
        WPP_SF_d(v36[2], 53, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v6);
    }
    goto LABEL_91;
  }
  v19 = v41[0];
  v20 = 8LL * v41[0];
  if ( !is_mul_ok(v41[0], 8u) )
    v20 = -1;
  v13 = __CFADD__(v20, 8);
  v21 = v20 + 8;
  if ( v13 )
    v21 = -1;
  v22 = operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v22
    || (v25 = (PathBuffer *)(v22 + 1),
        *v22 = v19,
        `vector constructor iterator'((PathBuffer *)(v22 + 1), v23, (unsigned int)v19, v24),
        !v25) )
  {
    v6 = -2147024882;
    v35 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          2147942414LL);
        v35 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 0x40) != 0 )
        WPP_SF_d(v35[2], 55, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, 2147942414LL);
    }
    goto LABEL_91;
  }
  v26 = 0;
  v27 = 0;
  if ( !v41[0] )
  {
LABEL_57:
    *v46 = v25;
    *(_DWORD *)v45 = v26;
    goto LABEL_91;
  }
  while ( 2 )
  {
    if ( v42 != -1 )
    {
      FveCloseVolume_0(v42);
      v42 = -1;
    }
    v28 = StringCchPrintfW(v48, 0x104u, L"\\\\?\\GLOBALROOT%s", *((_QWORD *)v11 + v27));
    v6 = v28;
    if ( v28 < 0 )
    {
      v33 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
            (unsigned int)v28);
          v33 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 0x40) != 0 )
        {
          v34 = 57;
          goto LABEL_76;
        }
      }
      goto LABEL_77;
    }
    v29 = FveOpenVolumeW_0(v48, 0, &v42);
    v6 = v29;
    if ( v29 == -2144272310 || v29 == -2144272363 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          (unsigned int)v29);
LABEL_55:
      v6 = 0;
LABEL_56:
      v27 = (unsigned int)(v27 + 1);
      if ( (unsigned int)v27 >= v41[0] )
        goto LABEL_57;
      continue;
    }
    break;
  }
  if ( v29 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)v29);
    if ( v3 >= 0 )
      v3 = v6;
    goto LABEL_55;
  }
  IsVolumeEncryptable_0 = FveIsVolumeEncryptable_0(v42);
  if ( IsVolumeEncryptable_0 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)IsVolumeEncryptable_0);
    goto LABEL_56;
  }
  v43 = 260;
  VolumeNameW_0 = FveGetVolumeNameW_0(v42, &v43, v48);
  v6 = VolumeNameW_0;
  if ( VolumeNameW_0 >= 0 )
  {
    v32 = PathBuffer::Initialize((PathBuffer *)((char *)v25 + 8 * v26), v48);
    v6 = v32;
    if ( v32 < 0 )
    {
      v33 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
            (unsigned int)v32);
          v33 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 0x40) != 0 )
        {
          v34 = 64;
LABEL_76:
          WPP_SF_d(v33[2], v34, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v6);
          goto LABEL_77;
        }
      }
      goto LABEL_77;
    }
    v26 = (unsigned int)(v26 + 1);
    goto LABEL_56;
  }
  v33 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)VolumeNameW_0);
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 0x40) != 0 )
    {
      v34 = 62;
      goto LABEL_76;
    }
  }
LABEL_77:
  PathBuffer::`vector deleting destructor'(v25);
LABEL_91:
  PathBuffer::`vector deleting destructor'(v11);
LABEL_99:
  v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_100:
  if ( v42 != -1 )
  {
    FveCloseVolume_0(v42);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    v42 = -1;
  }
  if ( v44 )
  {
    BcdCloseStore(v44);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 < 0 )
  {
    TelemetryProviderRegistrar::TelemetryProviderRegistrar(
      (TelemetryProviderRegistrar *)v47,
      &g_hBitLockerBcdUpdateProvider,
      &g_bitLockerBcdUpdateProviderInitLock,
      &g_bitLockerBcdUpdateProviderRefCount);
    if ( (unsigned int)dword_18003D590 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003D590) )
    {
      v45 = 0x1000000;
      v41[0] = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v37,
        (__int64)&word_180037346,
        v38,
        v39,
        (__int64)v41,
        (__int64)&v45);
    }
    TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v47);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_d(v7[2], 65, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180012be8  mov     [rsp-8+arg_10], rbx
0x180012bed  mov     [rsp-8+arg_18], rsi
0x180012bf2  push    rbp
0x180012bf3  push    rdi
0x180012bf4  push    r13
0x180012bf6  push    r14
0x180012bf8  push    r15
0x180012bfa  lea     rbp, [rsp-1A0h]
0x180012c02  sub     rsp, 2A0h
0x180012c09  mov     rax, cs:__security_cookie
0x180012c10  xor     rax, rsp
0x180012c13  mov     [rbp+1C0h+var_30], rax
0x180012c1a  mov     [rsp+2C0h+var_270], rdx
0x180012c1f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180012c23  mov     [rsp+2C0h+var_268], rcx
0x180012c28  xor     edx, edx; Val
0x180012c2a  lea     rcx, [rbp+1C0h+var_240]; void *
0x180012c2e  mov     [rsp+2C0h+var_288], r14
0x180012c33  mov     r8d, 208h; Size
0x180012c39  mov     [rsp+2C0h+var_278], 0
0x180012c42  mov     [rsp+2C0h+var_280], 0
0x180012c4a  call    memset_0
0x180012c4f  xor     r13d, r13d
0x180012c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c59  lea     r15, WPP_GLOBAL_Control
0x180012c60  cmp     rcx, r15
0x180012c63  jz      short loc_180012C7F
0x180012c65  test    byte ptr [rcx+1Ch], 20h
0x180012c69  jz      short loc_180012C7F
0x180012c6b  mov     rcx, [rcx+10h]
0x180012c6f  lea     edx, [r14+2Fh]
0x180012c73  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180012c7a  call    WPP_SF_
0x180012c7f  lea     rcx, [rsp+2C0h+var_278]
0x180012c84  call    cs:__imp_BcdOpenSystemStore
0x180012c8a  mov     ecx, eax; int
0x180012c8c  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180012c91  mov     ebx, eax
0x180012c93  test    eax, eax
0x180012c95  jns     short loc_180012CEC
0x180012c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c9e  cmp     rcx, r15
0x180012ca1  jz      loc_1800131BC
0x180012ca7  test    byte ptr [rcx+1Ch], 2
0x180012cab  jz      short loc_180012CCC
0x180012cad  mov     rcx, [rcx+10h]
0x180012cb1  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180012cb8  mov     edx, 2Fh ; '/'
0x180012cbd  mov     r9d, eax
0x180012cc0  call    WPP_SF_d
0x180012cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ccc  cmp     rcx, r15
0x180012ccf  jz      loc_1800131BC
0x180012cd5  test    byte ptr [rcx+1Ch], 40h
0x180012cd9  jz      loc_1800131BC
0x180012cdf  mov     edx, 30h ; '0'
0x180012ce4  mov     r9d, ebx
0x180012ce7  jmp     loc_1800131A5
0x180012cec  mov     ebx, 0Ah
0x180012cf1  xor     edi, edi
0x180012cf3  mov     [rsp+2C0h+var_290], ebx
0x180012cf7  mov     esi, 8007007Ah
0x180012cfc  test    rdi, rdi
0x180012cff  jz      short loc_180012D09
0x180012d01  mov     rcx, rdi; this
0x180012d04  call    ??_EPathBuffer@@QEAAPEAXI@Z; PathBuffer::`vector deleting destructor'(uint)
0x180012d09  mov     eax, 8
0x180012d0e  mul     rbx
0x180012d11  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012d18  cmovb   rax, r14
0x180012d1c  add     rax, 8
0x180012d20  cmovb   rax, r14
0x180012d24  mov     rcx, rax; unsigned __int64
0x180012d27  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012d2c  test    rax, rax
0x180012d2f  jz      loc_18001315A
0x180012d35  lea     rdi, [rax+8]
0x180012d39  mov     [rax], rbx
0x180012d3c  mov     rcx, rdi; this
0x180012d3f  mov     r8, rbx; unsigned __int64
0x180012d42  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180012d47  test    rdi, rdi
0x180012d4a  jz      loc_18001315A
0x180012d50  mov     rcx, [rsp+2C0h+var_278]; void *
0x180012d55  lea     r8, [rsp+2C0h+var_290]; unsigned int *
0x180012d5a  mov     rdx, rdi; struct PathBuffer *
0x180012d5d  call    ?GetUniqueBcdDevicePaths@FveBcdUtil@@CAJPEAXPEAVPathBuffer@@PEAK@Z; FveBcdUtil::GetUniqueBcdDevicePaths(void *,PathBuffer *,ulong *)
0x180012d62  mov     ebx, eax
0x180012d64  cmp     eax, esi
0x180012d66  jnz     short loc_180012D9B
0x180012d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d6f  cmp     rcx, r15
0x180012d72  jz      short loc_180012D92
0x180012d74  test    byte ptr [rcx+1Ch], 8
0x180012d78  jz      short loc_180012D92
0x180012d7a  mov     rcx, [rcx+10h]
0x180012d7e  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180012d85  mov     edx, 33h ; '3'
0x180012d8a  mov     r9d, esi
0x180012d8d  call    WPP_SF_d
0x180012d92  mov     ebx, [rsp+2C0h+var_290]
0x180012d96  jmp     loc_180012CFC
0x180012d9b  test    ebx, ebx
0x180012d9d  js      loc_1800130FC
0x180012da3  mov     r14d, [rsp+2C0h+var_290]
0x180012da8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012daf  mov     eax, 8
0x180012db4  mul     r14
0x180012db7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012dbe  cmovb   rax, rcx
0x180012dc2  add     rax, 8
0x180012dc6  cmovb   rax, rcx
0x180012dca  mov     rcx, rax; unsigned __int64
0x180012dcd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012dd2  test    rax, rax
0x180012dd5  jz      loc_18001309B
0x180012ddb  lea     rsi, [rax+8]
0x180012ddf  mov     [rax], r14
0x180012de2  mov     rcx, rsi; this
0x180012de5  mov     r8d, r14d; unsigned __int64
0x180012de8  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180012ded  test    rsi, rsi
0x180012df0  jz      loc_18001309B
0x180012df6  xor     r14d, r14d
0x180012df9  xor     r15d, r15d
0x180012dfc  cmp     [rsp+2C0h+var_290], r13d
0x180012e01  jbe     loc_180012F73
0x180012e07  mov     rcx, [rsp+2C0h+var_288]
0x180012e0c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012e10  jz      short loc_180012E20
0x180012e12  call    FveCloseVolume_0
0x180012e17  mov     [rsp+2C0h+var_288], 0FFFFFFFFFFFFFFFFh
0x180012e20  mov     r9, [rdi+r15*8]
0x180012e24  lea     r8, aGlobalrootS; "\\\\?\\GLOBALROOT%s"
0x180012e2b  mov     edx, 104h; unsigned __int64
0x180012e30  lea     rcx, [rbp+1C0h+var_240]; unsigned __int16 *
0x180012e34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012e39  mov     ebx, eax
0x180012e3b  test    eax, eax
0x180012e3d  js      loc_180013036
0x180012e43  lea     r8, [rsp+2C0h+var_288]
0x180012e48  xor     edx, edx
0x180012e4a  lea     rcx, [rbp+1C0h+var_240]
0x180012e4e  call    FveOpenVolumeW_0
0x180012e53  mov     ebx, eax
0x180012e55  cmp     eax, 8031004Ah
0x180012e5a  jz      loc_180012F32
0x180012e60  cmp     eax, 80310015h
0x180012e65  jz      loc_180012F32
0x180012e6b  test    eax, eax
0x180012e6d  jns     short loc_180012EAC
0x180012e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e76  lea     rax, WPP_GLOBAL_Control
0x180012e7d  cmp     rcx, rax
0x180012e80  jz      short loc_180012EA0
0x180012e82  test    byte ptr [rcx+1Ch], 4
0x180012e86  jz      short loc_180012EA0
0x180012e88  mov     rcx, [rcx+10h]
0x180012e8c  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180012e93  mov     edx, 3Bh ; ';'
0x180012e98  mov     r9d, ebx
0x180012e9b  call    WPP_SF_d
0x180012ea0  test    r13d, r13d
0x180012ea3  cmovns  r13d, ebx
0x180012ea7  jmp     loc_180012F63
0x180012eac  mov     rcx, [rsp+2C0h+var_288]
0x180012eb1  call    FveIsVolumeEncryptable_0
0x180012eb6  test    eax, eax
0x180012eb8  jns     short loc_180012EF5
0x180012eba  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ec1  lea     rdx, WPP_GLOBAL_Control
0x180012ec8  cmp     rcx, rdx
0x180012ecb  jz      loc_180012F65
0x180012ed1  test    byte ptr [rcx+1Ch], 8
0x180012ed5  jz      loc_180012F65
0x180012edb  mov     rcx, [rcx+10h]
0x180012edf  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180012ee6  mov     edx, 3Ch ; '<'
0x180012eeb  mov     r9d, eax
0x180012eee  call    WPP_SF_d
0x180012ef3  jmp     short loc_180012F65
0x180012ef5  mov     rcx, [rsp+2C0h+var_288]
0x180012efa  lea     r8, [rbp+1C0h+var_240]
0x180012efe  lea     rdx, [rsp+2C0h+var_280]
0x180012f03  mov     [rsp+2C0h+var_280], 104h
0x180012f0b  call    FveGetVolumeNameW_0
0x180012f10  mov     ebx, eax
0x180012f12  test    eax, eax
0x180012f14  js      loc_180012FE8
0x180012f1a  lea     rcx, [rsi+r14*8]; this
0x180012f1e  lea     rdx, [rbp+1C0h+var_240]; unsigned __int16 *
0x180012f22  call    ?Initialize@PathBuffer@@QEAAJPEBG@Z; PathBuffer::Initialize(ushort const *)
0x180012f27  mov     ebx, eax
0x180012f29  test    eax, eax
0x180012f2b  js      short loc_180012F8F
0x180012f2d  inc     r14d
0x180012f30  jmp     short loc_180012F65
0x180012f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f39  lea     rax, WPP_GLOBAL_Control
0x180012f40  cmp     rcx, rax
0x180012f43  jz      short loc_180012F63
0x180012f45  test    byte ptr [rcx+1Ch], 8
0x180012f49  jz      short loc_180012F63
0x180012f4b  mov     rcx, [rcx+10h]
0x180012f4f  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180012f56  mov     edx, 3Ah ; ':'
0x180012f5b  mov     r9d, ebx
0x180012f5e  call    WPP_SF_d
0x180012f63  xor     ebx, ebx
0x180012f65  inc     r15d
0x180012f68  cmp     r15d, [rsp+2C0h+var_290]
0x180012f6d  jb      loc_180012E07
0x180012f73  mov     rax, [rsp+2C0h+var_268]
0x180012f78  lea     r15, WPP_GLOBAL_Control
0x180012f7f  mov     [rax], rsi
0x180012f82  mov     rax, [rsp+2C0h+var_270]
0x180012f87  mov     [rax], r14d
0x180012f8a  jmp     loc_1800130F6
0x180012f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f96  lea     r15, WPP_GLOBAL_Control
0x180012f9d  cmp     rcx, r15
0x180012fa0  jz      loc_180013091
0x180012fa6  test    byte ptr [rcx+1Ch], 2
0x180012faa  jz      short loc_180012FCB
0x180012fac  mov     rcx, [rcx+10h]
0x180012fb0  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180012fb7  mov     edx, 3Fh ; '?'
0x180012fbc  mov     r9d, ebx
0x180012fbf  call    WPP_SF_d
0x180012fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fcb  cmp     rcx, r15
0x180012fce  jz      loc_180013091
0x180012fd4  test    byte ptr [rcx+1Ch], 40h
0x180012fd8  jz      loc_180013091
0x180012fde  mov     edx, 40h ; '@'
0x180012fe3  jmp     loc_18001307E
0x180012fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fef  lea     r15, WPP_GLOBAL_Control
0x180012ff6  cmp     rcx, r15
0x180012ff9  jz      loc_180013091
0x180012fff  test    byte ptr [rcx+1Ch], 2
0x180013003  jz      short loc_180013024
0x180013005  mov     rcx, [rcx+10h]
0x180013009  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180013010  mov     edx, 3Dh ; '='
0x180013015  mov     r9d, ebx
0x180013018  call    WPP_SF_d
0x18001301d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013024  cmp     rcx, r15
0x180013027  jz      short loc_180013091
0x180013029  test    byte ptr [rcx+1Ch], 40h
0x18001302d  jz      short loc_180013091
0x18001302f  mov     edx, 3Eh ; '>'
0x180013034  jmp     short loc_18001307E
0x180013036  mov     rcx, cs:WPP_GLOBAL_Control
0x18001303d  lea     r15, WPP_GLOBAL_Control
0x180013044  cmp     rcx, r15
0x180013047  jz      short loc_180013091
0x180013049  test    byte ptr [rcx+1Ch], 2
0x18001304d  jz      short loc_18001306E
0x18001304f  mov     rcx, [rcx+10h]
0x180013053  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001305a  mov     edx, 38h ; '8'
0x18001305f  mov     r9d, ebx
0x180013062  call    WPP_SF_d
0x180013067  mov     rcx, cs:WPP_GLOBAL_Control
0x18001306e  cmp     rcx, r15
0x180013071  jz      short loc_180013091
0x180013073  test    byte ptr [rcx+1Ch], 40h
0x180013077  jz      short loc_180013091
0x180013079  mov     edx, 39h ; '9'
0x18001307e  mov     rcx, [rcx+10h]
0x180013082  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180013089  mov     r9d, ebx
0x18001308c  call    WPP_SF_d
0x180013091  mov     rcx, rsi; this
0x180013094  call    ??_EPathBuffer@@QEAAPEAXI@Z; PathBuffer::`vector deleting destructor'(uint)
0x180013099  jmp     short loc_1800130F6
0x18001309b  mov     esi, 8007000Eh
0x1800130a0  mov     ebx, esi
0x1800130a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130a9  cmp     rcx, r15
0x1800130ac  jz      short loc_1800130F6
0x1800130ae  test    byte ptr [rcx+1Ch], 2
0x1800130b2  jz      short loc_1800130D3
0x1800130b4  mov     rcx, [rcx+10h]
0x1800130b8  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x1800130bf  mov     edx, 36h ; '6'
0x1800130c4  mov     r9d, esi
0x1800130c7  call    WPP_SF_d
0x1800130cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130d3  cmp     rcx, r15
0x1800130d6  jz      short loc_1800130F6
0x1800130d8  test    byte ptr [rcx+1Ch], 40h
0x1800130dc  jz      short loc_1800130F6
0x1800130de  mov     rcx, [rcx+10h]
0x1800130e2  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x1800130e9  mov     edx, 37h ; '7'
0x1800130ee  mov     r9d, esi
0x1800130f1  call    WPP_SF_d
  ... truncated ...
```
