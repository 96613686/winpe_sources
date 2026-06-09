# AliasComponentWorker(ushort const *,ushort const *,ushort const *,_GUID const &,ushort const *)

- ea: `0x18001a924`
- end: `0x18001b398`
- name: `?AliasComponentWorker@@YAJPEBG00AEBU_GUID@@0@Z`
- size: `2676`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a7e0`

## callees

- `0x18001a924`
- `0x18001b3a0`
- `0x18001bcc0`
- `0x18001c774`
- `0x18001c934`
- `0x18001cbdc`
- `0x180031000`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!CLSIDFromStringByBitness` at `0x18001aa95`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18001aad5`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18001aa95`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18001aad5`
- `CLBCatQ!ServerGetApplicationType` at `0x18001aa54`
- `CLBCatQ!ServerGetApplicationType` at `0x18001aa54`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a9da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a9da`

## pseudocode

```c
__int64 __fastcall AliasComponentWorker(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _GUID *a4,
        const unsigned __int16 *a5)
{
  HRESULT Instance; // ebx
  int v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // esi
  int v14; // eax
  const struct _GUID *v15; // r13
  struct _GUID *v16; // r9
  __int64 v17; // r8
  int v18; // esi
  unsigned int v19; // eax
  int v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  int Data1; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  struct ISimpleTableDispenser *ppv; // [rsp+68h] [rbp-98h] BYREF
  const struct _GUID *v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+78h] [rbp-88h] BYREF
  int v27; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v28; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v29; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h] BYREF
  int v31; // [rsp+90h] [rbp-70h] BYREF
  int v32; // [rsp+94h] [rbp-6Ch] BYREF
  int v33; // [rsp+98h] [rbp-68h] BYREF
  const struct _GUID *v34; // [rsp+A0h] [rbp-60h]
  struct _GUID Buf2; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID Buf1; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v37; // [rsp+C8h] [rbp-38h] BYREF
  struct _GUID v38; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID v39; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v40; // [rsp+F8h] [rbp-8h] BYREF
  struct _GUID *v41; // [rsp+110h] [rbp+10h] BYREF
  __int64 v42; // [rsp+118h] [rbp+18h]
  int v43; // [rsp+120h] [rbp+20h]
  int v44; // [rsp+124h] [rbp+24h]
  GUID *p_Buf1; // [rsp+128h] [rbp+28h]
  int v46; // [rsp+130h] [rbp+30h]
  int v47; // [rsp+134h] [rbp+34h]
  int v48; // [rsp+138h] [rbp+38h]
  int v49; // [rsp+13Ch] [rbp+3Ch]
  int *v50; // [rsp+140h] [rbp+40h]
  int v51; // [rsp+148h] [rbp+48h]
  int v52; // [rsp+14Ch] [rbp+4Ch]
  int v53; // [rsp+150h] [rbp+50h]
  int v54; // [rsp+154h] [rbp+54h]

  v28 = 0;
  v32 = 0;
  v25 = 0;
  v29 = 0;
  v27 = 1;
  v31 = 1;
  v33 = 0;
  ppv = 0;
  v21 = 0;
  v23 = 0;
  v30 = 0;
  Data1 = 0;
  v26 = 0;
  v38 = 0;
  v40 = 0;
  v37 = 0;
  v39 = 0;
  Buf1 = 0;
  Buf2 = 0;
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 0x17u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance < 0 )
    goto LABEL_62;
  v10 = ResolveAppIdFromName(ppv, a1, &v37, &Buf1);
  v11 = 0;
  Instance = v10;
  if ( v10 < 0 )
    goto LABEL_62;
  Instance = ResolveAppIdFromName(ppv, a3, &v39, &Buf2);
  if ( Instance < 0 )
    goto LABEL_62;
  if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    Instance = -2146367477;
    goto LABEL_62;
  }
  Instance = ServerGetApplicationType(ppv, &v37, &v27);
  if ( Instance >= 0 )
  {
    if ( v27 == 3 )
    {
LABEL_7:
      Instance = -2146367479;
      goto LABEL_62;
    }
    v31 = v27;
    v12 = 0x400000;
    if ( v27 == 1 )
      v12 = 0x200000;
    Instance = CLSIDFromStringByBitness(a2, &v38);
    if ( Instance >= 0 )
    {
      Instance = CheckSourceComponentExists(ppv, &Buf1, &v37, &v38, v12);
      if ( Instance >= 0 )
      {
        if ( (int)CLSIDFromStringByBitness(a5, &v40) >= 0 && v40 != *(_OWORD *)a4 )
          return 2148599829LL;
        Instance = TargetComponentExists(ppv, &Buf1, &v39, a4, v12, v20, 0);
        if ( Instance >= 0 )
        {
          Instance = IsEventClassComponent(ppv, &Buf1, &v37, &v38, &v26);
          if ( Instance >= 0 )
          {
            if ( v26 )
            {
              Instance = -2146367456;
              goto LABEL_62;
            }
            Instance = ValidateSourceAndDestinationApps(ppv, &v37, &v39);
            if ( Instance < 0 )
              goto LABEL_62;
            v42 = 0;
            v43 = 72;
            v41 = &v38;
            p_Buf1 = &Buf1;
            v48 = 72;
            v50 = &v31;
            v44 = 16;
            v46 = 0;
            v47 = 6;
            v49 = 16;
            v51 = 0;
            v52 = 8;
            v53 = 19;
            v54 = 4;
            Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int64 *, struct _GUID **, __int64, int, unsigned int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                         ppv,
                         didCOMSERVICES,
                         tidCOMSERVICES_CLASSES,
                         &v41,
                         3,
                         1,
                         v12,
                         &v21);
            if ( Instance < 0 )
              goto LABEL_62;
            Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v21 + 72LL))(
                         v21,
                         0,
                         0,
                         0,
                         0,
                         0,
                         0,
                         0,
                         &v29);
            if ( Instance < 0 )
              goto LABEL_62;
            Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
            if ( Instance < 0 )
              goto LABEL_62;
            v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 40LL))(v21);
            Instance = v14;
            if ( v14 == -2146367487 )
              goto LABEL_7;
            if ( v14 < 0 )
              goto LABEL_62;
            Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 120LL))(v21);
            if ( Instance < 0 )
              goto LABEL_62;
            v15 = 0;
            v34 = 0;
            v26 = 0;
            if ( !v29 )
            {
LABEL_71:
              Data1 |= 0x1000u;
              if ( !memcmp_0(&Buf2, &GUID_DefaultAppPartition, 0x10u) )
              {
                v41 = a4;
                v43 = 72;
                v48 = 72;
                p_Buf1 = &GUID_DefaultAppPartition;
                v42 = 0;
                v44 = 16;
                v46 = 1;
                v47 = 1;
                v49 = 16;
                Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, const struct _GUID *, struct _GUID **, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                             ppv,
                             didCOMSERVICES,
                             &tidCOMSERVICES_CLASSES_INTERNAL,
                             &v41,
                             2,
                             1,
                             1,
                             &v30);
                if ( Instance < 0 )
                  goto LABEL_62;
                Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 24LL))(v30);
                if ( Instance < 0 )
                  goto LABEL_62;
                Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int *, _QWORD))(*(_QWORD *)v30 + 72LL))(
                             v30,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             &v33,
                             0);
                if ( Instance < 0 )
                  goto LABEL_62;
                if ( v30 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                  v30 = 0;
                }
                if ( v33 )
                  Data1 |= 0x10000u;
                else
                  Data1 &= ~0x10000u;
              }
              Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v21 + 160LL))(
                           v21,
                           30,
                           0,
                           &Data1);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 160LL))(v21, 10);
                if ( Instance >= 0 )
                {
                  Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 144LL))(v21);
                  if ( Instance >= 0 )
                  {
                    v18 = v12 | 8;
                    Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int128 *, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                                 ppv,
                                 didCOMCLASSIC,
                                 &tidCOMCLASSIC_CLASSES,
                                 0,
                                 0,
                                 1,
                                 v18,
                                 &v23);
                    if ( Instance >= 0 )
                    {
                      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
                      if ( Instance >= 0 )
                      {
                        Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 120LL))(v23);
                        if ( Instance >= 0 )
                        {
                          Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct _GUID *))(*(_QWORD *)v23 + 160LL))(
                                       v23,
                                       0,
                                       0,
                                       a4);
                          if ( Instance >= 0 )
                          {
                            Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const struct _GUID *))(*(_QWORD *)v23 + 160LL))(
                                         v23,
                                         1,
                                         0,
                                         v15);
                            if ( Instance >= 0 )
                            {
                              v19 = 0;
                              while ( *((_DWORD *)&g_mapThreadModels + 4 * v19 + 2) != v26 )
                              {
                                if ( ++v19 >= 4 )
                                  goto LABEL_93;
                              }
                              Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v23 + 160LL))(
                                           v23,
                                           2,
                                           0,
                                           *((_QWORD *)&g_mapThreadModels + 2 * v19));
                              if ( Instance < 0 )
                                goto LABEL_62;
LABEL_93:
                              Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v23 + 160LL))(
                                           v23,
                                           3,
                                           0,
                                           a5);
                              if ( Instance >= 0 )
                              {
                                Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v23 + 160LL))(
                                             v23,
                                             5,
                                             0,
                                             a5);
                                if ( Instance >= 0 )
                                {
                                  Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const struct _GUID *))(*(_QWORD *)v23 + 160LL))(
                                               v23,
                                               4,
                                               0,
                                               v34);
                                  if ( Instance >= 0 )
                                  {
                                    Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 144LL))(v23);
                                    if ( Instance >= 0 )
                                    {
                                      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 96LL))(v23);
                                      if ( Instance >= 0 )
                                      {
                                        if ( v23 )
                                        {
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                                          v23 = 0;
                                        }
                                        Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 96LL))(v21);
                                        if ( Instance >= 0 )
                                        {
                                          if ( v21 )
                                          {
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                                            v21 = 0;
                                          }
                                          Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int128 *, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                                                       ppv,
                                                       didCOMCLASSIC,
                                                       &tidCOMCLASSIC_PROGIDS,
                                                       0,
                                                       0,
                                                       1,
                                                       v18,
                                                       &v21);
                                          if ( Instance >= 0 )
                                          {
                                            Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
                                            if ( Instance >= 0 )
                                            {
                                              Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 120LL))(v21);
                                              if ( Instance >= 0 )
                                              {
                                                Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const unsigned __int16 *))(*(_QWORD *)v21 + 160LL))(
                                                             v21,
                                                             0,
                                                             0,
                                                             a5);
                                                if ( Instance >= 0 )
                                                {
                                                  Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _GUID *))(*(_QWORD *)v21 + 160LL))(
                                                               v21,
                                                               1,
                                                               0,
                                                               a4);
                                                  if ( Instance >= 0 )
                                                  {
                                                    Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21
                                                                                                  + 144LL))(v21);
                                                    if ( Instance >= 0 )
                                                    {
                                                      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 96LL))(v21);
                                                      if ( Instance >= 0 )
                                                      {
                                                        if ( v21 )
                                                        {
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                                                          v21 = 0;
                                                        }
                                                        Instance = UpdateRelatedComponentInfo(ppv, &v41, &Buf1, a4, 1);
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              goto LABEL_62;
            }
            while ( 1 )
            {
              Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *, const struct _GUID **))(*(_QWORD *)v21 + 64LL))(
                           v21,
                           v11,
                           &v32,
                           &v28,
                           &v25);
              if ( Instance < 0 )
                break;
              if ( v11 > 0xA )
              {
                switch ( v11 )
                {
                  case 0x18u:
                  case 0x19u:
                    v16 = 0;
                    v28 = 0;
LABEL_55:
                    v25 = v16;
                    break;
                  case 0x1Eu:
                    Data1 = v25->Data1;
                    break;
                  case 0x21u:
                  case 0x27u:
                  case 0x29u:
                  case 0x31u:
                    goto LABEL_52;
                }
              }
              else if ( v11 != 10 )
              {
                switch ( v11 )
                {
                  case 0u:
                    v25 = a4;
                    break;
                  case 1u:
                    v15 = v25;
                    break;
                  case 2u:
                    v26 = v25->Data1;
                    break;
                  case 3u:
                    goto LABEL_52;
                  case 4u:
                    v34 = v25;
                    break;
                  case 5u:
LABEL_52:
                    v25 = (const struct _GUID *)a5;
                    break;
                  case 9u:
                    if ( !v25 )
                    {
                      Instance = -2147024809;
                      goto LABEL_62;
                    }
                    v16 = &v39;
                    goto LABEL_55;
                }
              }
              v17 = 0;
              if ( v32 == 128 )
                v17 = v28;
              Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v21 + 160LL))(v21, v11, v17);
              if ( Instance < 0 )
                break;
              if ( ++v11 >= v29 )
                goto LABEL_71;
            }
          }
        }
      }
    }
  }
LABEL_62:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001a924  push    rbp
0x18001a926  push    rbx
0x18001a927  push    rsi
0x18001a928  push    rdi
0x18001a929  push    r12
0x18001a92b  push    r13
0x18001a92d  push    r14
0x18001a92f  push    r15
0x18001a931  lea     rbp, [rsp-78h]
0x18001a936  sub     rsp, 178h
0x18001a93d  mov     rax, cs:__security_cookie
0x18001a944  xor     rax, rsp
0x18001a947  mov     [rbp+0B0h+var_50], rax
0x18001a94b  mov     r12, [rbp+0B0h+arg_20]
0x18001a952  xor     r13d, r13d
0x18001a955  xorps   xmm0, xmm0
0x18001a958  mov     [rbp+0B0h+var_130], r13d
0x18001a95c  xorps   xmm1, xmm1
0x18001a95f  mov     [rbp+0B0h+var_11C], r13d
0x18001a963  mov     r15, r9
0x18001a966  mov     [rsp+1B0h+var_140], r13
0x18001a96b  lea     eax, [r13+1]
0x18001a96f  mov     [rbp+0B0h+var_12C], r13d
0x18001a973  mov     [rsp+1B0h+var_134], eax
0x18001a977  lea     r9, IID_ISimpleTableDispenser; riid
0x18001a97e  mov     [rbp+0B0h+var_120], eax
0x18001a981  mov     rsi, r8
0x18001a984  lea     rax, [rsp+1B0h+var_148]
0x18001a989  mov     [rbp+0B0h+var_118], r13d
0x18001a98d  mov     r14, rdx
0x18001a990  mov     [rsp+1B0h+ppv], rax; ppv
0x18001a995  mov     rdi, rcx
0x18001a998  mov     [rsp+1B0h+var_148], r13
0x18001a99d  xor     edx, edx; pUnkOuter
0x18001a99f  mov     [rsp+1B0h+var_160], r13
0x18001a9a4  lea     r8d, [r13+17h]; dwClsContext
0x18001a9a8  mov     [rsp+1B0h+var_150], r13
0x18001a9ad  lea     rcx, CLSID_STDispenser; rclsid
0x18001a9b4  mov     [rbp+0B0h+var_128], r13
0x18001a9b8  mov     [rsp+1B0h+var_158], r13d
0x18001a9bd  mov     [rsp+1B0h+var_138], r13d
0x18001a9c2  movups  xmmword ptr [rbp+0B0h+var_D8.Data1], xmm0
0x18001a9c6  movups  [rbp+0B0h+var_B8], xmm1
0x18001a9ca  movups  xmmword ptr [rbp+0B0h+var_E8.Data1], xmm0
0x18001a9ce  movups  xmmword ptr [rbp+0B0h+var_C8.Data1], xmm1
0x18001a9d2  movups  [rbp+0B0h+Buf1], xmm0
0x18001a9d6  movups  [rbp+0B0h+Buf2], xmm1
0x18001a9da  call    cs:__imp_CoCreateInstance
0x18001a9e0  mov     ebx, eax
0x18001a9e2  test    eax, eax
0x18001a9e4  js      loc_18001AE09
0x18001a9ea  mov     rcx, [rsp+1B0h+var_148]; struct ISimpleTableDispenser *
0x18001a9ef  lea     r9, [rbp+0B0h+Buf1]; struct _GUID *
0x18001a9f3  lea     r8, [rbp+0B0h+var_E8]; struct _GUID *
0x18001a9f7  mov     rdx, rdi; unsigned __int16 *
0x18001a9fa  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x18001a9ff  xor     edi, edi
0x18001aa01  mov     ebx, eax
0x18001aa03  test    eax, eax
0x18001aa05  js      loc_18001AE0B
0x18001aa0b  mov     rcx, [rsp+1B0h+var_148]; struct ISimpleTableDispenser *
0x18001aa10  lea     r9, [rbp+0B0h+Buf2]; struct _GUID *
0x18001aa14  lea     r8, [rbp+0B0h+var_C8]; struct _GUID *
0x18001aa18  mov     rdx, rsi; unsigned __int16 *
0x18001aa1b  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x18001aa20  mov     ebx, eax
0x18001aa22  test    eax, eax
0x18001aa24  js      loc_18001AE0B
0x18001aa2a  lea     r13d, [rdi+10h]
0x18001aa2e  mov     r8d, r13d; Size
0x18001aa31  lea     rdx, [rbp+0B0h+Buf2]; Buf2
0x18001aa35  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x18001aa39  call    memcmp_0
0x18001aa3e  test    eax, eax
0x18001aa40  jnz     loc_18001B38E
0x18001aa46  mov     rcx, [rsp+1B0h+var_148]
0x18001aa4b  lea     r8, [rsp+1B0h+var_134]
0x18001aa50  lea     rdx, [rbp+0B0h+var_E8]
0x18001aa54  call    cs:__imp_ServerGetApplicationType
0x18001aa5a  mov     ebx, eax
0x18001aa5c  test    eax, eax
0x18001aa5e  js      loc_18001AE0B
0x18001aa64  mov     r8d, [rsp+1B0h+var_134]
0x18001aa69  cmp     r8d, 3
0x18001aa6d  jnz     short loc_18001AA79
0x18001aa6f  mov     ebx, 80110809h
0x18001aa74  jmp     loc_18001AE0B
0x18001aa79  cmp     r8d, 1
0x18001aa7d  mov     [rbp+0B0h+var_120], r8d
0x18001aa81  mov     eax, 200000h
0x18001aa86  lea     rdx, [rbp+0B0h+var_D8]
0x18001aa8a  mov     esi, 400000h
0x18001aa8f  mov     rcx, r14
0x18001aa92  cmovz   esi, eax
0x18001aa95  call    cs:__imp_CLSIDFromStringByBitness
0x18001aa9b  mov     ebx, eax
0x18001aa9d  test    eax, eax
0x18001aa9f  js      loc_18001AE0B
0x18001aaa5  mov     rcx, [rsp+1B0h+var_148]; struct ISimpleTableDispenser *
0x18001aaaa  lea     r9, [rbp+0B0h+var_D8]; struct _GUID *
0x18001aaae  lea     r8, [rbp+0B0h+var_E8]; struct _GUID *
0x18001aab2  mov     dword ptr [rsp+1B0h+ppv], esi; unsigned int
0x18001aab6  lea     rdx, [rbp+0B0h+Buf1]; struct _GUID *
0x18001aaba  call    ?CheckSourceComponentExists@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@11K@Z; CheckSourceComponentExists(ISimpleTableDispenser *,_GUID const &,_GUID const &,_GUID const &,ulong)
0x18001aabf  mov     ebx, eax
0x18001aac1  test    eax, eax
0x18001aac3  js      loc_18001AE0B
0x18001aac9  mov     r8d, [rsp+1B0h+var_134]
0x18001aace  lea     rdx, [rbp+0B0h+var_B8]
0x18001aad2  mov     rcx, r12
0x18001aad5  call    cs:__imp_CLSIDFromStringByBitness
0x18001aadb  test    eax, eax
0x18001aadd  js      short loc_18001AAFC
0x18001aadf  mov     rax, qword ptr [rbp+0B0h+var_B8]
0x18001aae3  cmp     rax, [r15]
0x18001aae6  jnz     short loc_18001AAF2
0x18001aae8  mov     rax, qword ptr [rbp+0B0h+var_B8+8]
0x18001aaec  cmp     rax, [r15+8]
0x18001aaf0  jz      short loc_18001AAFC
0x18001aaf2  mov     eax, 80110815h
0x18001aaf7  jmp     loc_18001AE73
0x18001aafc  mov     rcx, [rsp+1B0h+var_148]; struct ISimpleTableDispenser *
0x18001ab01  lea     r8, [rbp+0B0h+var_C8]; struct _GUID *
0x18001ab05  mov     [rsp+1B0h+var_180], rdi; enum ECOMPONENTLOCATION *
0x18001ab0a  lea     rdx, [rbp+0B0h+Buf1]; struct _GUID *
0x18001ab0e  mov     r9, r15; struct _GUID *
0x18001ab11  mov     dword ptr [rsp+1B0h+ppv], esi; unsigned int
0x18001ab15  call    ?TargetComponentExists@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@11KHPEAW4ECOMPONENTLOCATION@@@Z; TargetComponentExists(ISimpleTableDispenser *,_GUID const &,_GUID const &,_GUID const &,ulong,int,ECOMPONENTLOCATION *)
0x18001ab1a  mov     ebx, eax
0x18001ab1c  test    eax, eax
0x18001ab1e  js      loc_18001AE0B
0x18001ab24  mov     rcx, [rsp+1B0h+var_148]; struct ISimpleTableDispenser *
0x18001ab29  lea     rax, [rsp+1B0h+var_138]
0x18001ab2e  lea     r9, [rbp+0B0h+var_D8]; struct _GUID *
0x18001ab32  mov     [rsp+1B0h+ppv], rax; int *
0x18001ab37  lea     r8, [rbp+0B0h+var_E8]; struct _GUID *
0x18001ab3b  lea     rdx, [rbp+0B0h+Buf1]; struct _GUID *
0x18001ab3f  call    ?IsEventClassComponent@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@11PEAH@Z; IsEventClassComponent(ISimpleTableDispenser *,_GUID const &,_GUID const &,_GUID const &,int *)
0x18001ab44  mov     ebx, eax
0x18001ab46  test    eax, eax
0x18001ab48  js      loc_18001AE0B
0x18001ab4e  cmp     [rsp+1B0h+var_138], edi
0x18001ab52  jz      short loc_18001AB5E
0x18001ab54  mov     ebx, 80110820h
0x18001ab59  jmp     loc_18001AE0B
0x18001ab5e  mov     rcx, [rsp+1B0h+var_148]; struct ISimpleTableDispenser *
0x18001ab63  lea     r8, [rbp+0B0h+var_C8]; struct _GUID *
0x18001ab67  lea     rdx, [rbp+0B0h+var_E8]; struct _GUID *
0x18001ab6b  call    ?ValidateSourceAndDestinationApps@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@1@Z; ValidateSourceAndDestinationApps(ISimpleTableDispenser *,_GUID const &,_GUID const &)
0x18001ab70  mov     ebx, eax
0x18001ab72  test    eax, eax
0x18001ab74  js      loc_18001AE0B
0x18001ab7a  mov     ecx, 48h ; 'H'
0x18001ab7f  mov     [rbp+0B0h+var_98], rdi
0x18001ab83  mov     [rbp+0B0h+var_90], ecx
0x18001ab86  lea     rax, [rbp+0B0h+var_D8]
0x18001ab8a  mov     [rbp+0B0h+var_A0], rax
0x18001ab8e  lea     rdx, [rsp+1B0h+var_160]
0x18001ab93  mov     [rsp+1B0h+var_178], rdx
0x18001ab98  lea     rax, [rbp+0B0h+Buf1]
0x18001ab9c  mov     [rbp+0B0h+var_88], rax
0x18001aba0  lea     r9, [rbp+0B0h+var_A0]
0x18001aba4  mov     [rbp+0B0h+var_78], ecx
0x18001aba7  lea     rax, [rbp+0B0h+var_120]
0x18001abab  mov     rcx, [rsp+1B0h+var_148]
0x18001abb0  lea     r8, tidCOMSERVICES_CLASSES
0x18001abb7  mov     [rbp+0B0h+var_70], rax
0x18001abbb  lea     rdx, didCOMSERVICES
0x18001abc2  mov     [rbp+0B0h+var_8C], r13d
0x18001abc6  mov     [rbp+0B0h+var_80], edi
0x18001abc9  mov     [rbp+0B0h+var_7C], 6
0x18001abd0  mov     [rbp+0B0h+var_74], r13d
0x18001abd4  mov     [rbp+0B0h+var_68], edi
0x18001abd7  mov     [rbp+0B0h+var_64], 8
0x18001abde  mov     [rbp+0B0h+var_60], 13h
0x18001abe5  mov     [rbp+0B0h+var_5C], 4
0x18001abec  mov     rax, [rcx]
0x18001abef  mov     dword ptr [rsp+1B0h+var_180], esi
0x18001abf3  mov     dword ptr [rsp+1B0h+var_188], 1
0x18001abfb  mov     [rsp+1B0h+ppv], 3
0x18001ac04  mov     rax, [rax+18h]
0x18001ac08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac0d  mov     ebx, eax
0x18001ac0f  test    eax, eax
0x18001ac11  js      loc_18001AE0B
0x18001ac17  mov     rcx, [rsp+1B0h+var_160]
0x18001ac1c  lea     rdx, [rbp+0B0h+var_12C]
0x18001ac20  mov     [rsp+1B0h+var_170], rdx
0x18001ac25  xor     r9d, r9d
0x18001ac28  mov     [rsp+1B0h+var_178], rdi
0x18001ac2d  xor     r8d, r8d
0x18001ac30  mov     [rsp+1B0h+var_180], rdi
0x18001ac35  xor     edx, edx
0x18001ac37  mov     rax, [rcx]
0x18001ac3a  mov     [rsp+1B0h+var_188], rdi
0x18001ac3f  mov     [rsp+1B0h+ppv], rdi
0x18001ac44  mov     rax, [rax+48h]
0x18001ac48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac4d  mov     ebx, eax
0x18001ac4f  test    eax, eax
0x18001ac51  js      loc_18001AE0B
0x18001ac57  mov     rcx, [rsp+1B0h+var_160]
0x18001ac5c  mov     rax, [rcx]
0x18001ac5f  mov     rax, [rax+18h]
0x18001ac63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac68  mov     ebx, eax
0x18001ac6a  test    eax, eax
0x18001ac6c  js      loc_18001AE0B
0x18001ac72  mov     rcx, [rsp+1B0h+var_160]
0x18001ac77  mov     rax, [rcx]
0x18001ac7a  mov     rax, [rax+28h]
0x18001ac7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac83  mov     ebx, eax
0x18001ac85  cmp     eax, 80110801h
0x18001ac8a  jz      loc_18001AA6F
0x18001ac90  test    eax, eax
0x18001ac92  js      loc_18001AE0B
0x18001ac98  mov     rcx, [rsp+1B0h+var_160]
0x18001ac9d  mov     rax, [rcx]
0x18001aca0  mov     rax, [rax+78h]
0x18001aca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aca9  mov     ebx, eax
0x18001acab  test    eax, eax
0x18001acad  js      loc_18001AE0B
0x18001acb3  mov     r14, rdi
0x18001acb6  mov     r13, rdi
0x18001acb9  mov     [rbp+0B0h+var_110], rdi
0x18001acbd  mov     [rsp+1B0h+var_138], edi
0x18001acc1  cmp     [rbp+0B0h+var_12C], edi
0x18001acc4  jbe     loc_18001AE93
0x18001acca  mov     rcx, [rsp+1B0h+var_160]
0x18001accf  lea     rdx, [rsp+1B0h+var_140]
0x18001acd4  mov     [rsp+1B0h+ppv], rdx
0x18001acd9  lea     r9, [rbp+0B0h+var_130]
0x18001acdd  lea     r8, [rbp+0B0h+var_11C]
0x18001ace1  mov     edx, edi
0x18001ace3  mov     rax, [rcx]
0x18001ace6  mov     rax, [rax+40h]
0x18001acea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acef  mov     ebx, eax
0x18001acf1  test    eax, eax
0x18001acf3  js      loc_18001AE09
0x18001acf9  cmp     edi, 0Ah
0x18001acfc  ja      short loc_18001AD74
0x18001acfe  jz      short loc_18001AD6A
0x18001ad00  mov     eax, edi
0x18001ad02  test    edi, edi
0x18001ad04  jz      short loc_18001AD60
0x18001ad06  sub     eax, 1
0x18001ad09  jz      short loc_18001AD56
0x18001ad0b  sub     eax, 1
0x18001ad0e  jz      short loc_18001AD48
0x18001ad10  sub     eax, 1
0x18001ad13  jz      loc_18001ADA0
0x18001ad19  sub     eax, 1
0x18001ad1c  jz      short loc_18001AD3D
0x18001ad1e  sub     eax, 1
0x18001ad21  jz      short loc_18001ADA0
0x18001ad23  cmp     eax, 4
0x18001ad26  jnz     short loc_18001AD99
0x18001ad28  cmp     [rsp+1B0h+var_140], 0
0x18001ad2e  jz      loc_18001AE04
0x18001ad34  lea     r9, [rbp+0B0h+var_C8]
0x18001ad38  jmp     loc_18001ADBF
0x18001ad3d  mov     r9, [rsp+1B0h+var_140]
0x18001ad42  mov     [rbp+0B0h+var_110], r9
0x18001ad46  jmp     short loc_18001ADC4
0x18001ad48  mov     r9, [rsp+1B0h+var_140]
0x18001ad4d  mov     eax, [r9]
0x18001ad50  mov     [rsp+1B0h+var_138], eax
0x18001ad54  jmp     short loc_18001ADC4
0x18001ad56  mov     r9, [rsp+1B0h+var_140]
0x18001ad5b  mov     r13, r9
0x18001ad5e  jmp     short loc_18001ADC4
0x18001ad60  mov     r9, r15
0x18001ad63  mov     [rsp+1B0h+var_140], r15
0x18001ad68  jmp     short loc_18001ADC4
0x18001ad6a  mov     r9, [rsp+1B0h+var_140]
0x18001ad6f  mov     r14, r9
0x18001ad72  jmp     short loc_18001ADC4
0x18001ad74  mov     eax, edi
0x18001ad76  sub     eax, 18h
0x18001ad79  jz      short loc_18001ADB8
0x18001ad7b  sub     eax, 1
0x18001ad7e  jz      short loc_18001ADB8
0x18001ad80  sub     eax, 5
0x18001ad83  jz      short loc_18001ADAA
0x18001ad85  sub     eax, 3
0x18001ad88  jz      short loc_18001ADA0
0x18001ad8a  sub     eax, 6
0x18001ad8d  jz      short loc_18001ADA0
0x18001ad8f  sub     eax, 2
0x18001ad92  jz      short loc_18001ADA0
0x18001ad94  cmp     eax, 8
0x18001ad97  jz      short loc_18001ADA0
0x18001ad99  mov     r9, [rsp+1B0h+var_140]
0x18001ad9e  jmp     short loc_18001ADC4
0x18001ada0  mov     r9, r12
0x18001ada3  mov     [rsp+1B0h+var_140], r12
0x18001ada8  jmp     short loc_18001ADC4
  ... truncated ...
```
