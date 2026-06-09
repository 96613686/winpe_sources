# CSecurityAdmin2::RefreshSecurityDatabase(void)

- ea: `0x1800286b0`
- end: `0x1800289c1`
- name: `?RefreshSecurityDatabase@CSecurityAdmin2@@QEAAJXZ`
- size: `785`
- prototype: `__int64 __fastcall(CSecurityAdmin2 *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180026b60`

## callees

- `0x1800269a8`
- `0x18002800c`
- `0x1800286b0`
- `0x180028da8`
- `0x1800293c8`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002870a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028814`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002870a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028814`
- `CLBCatQ!ServerGetApplicationType` at `0x1800287d2`
- `CLBCatQ!ServerGetApplicationType` at `0x1800287d2`

## pseudocode

```c
__int64 __fastcall CSecurityAdmin2::RefreshSecurityDatabase(struct ISimpleTableDispenser **this)
{
  CSecurityAdmin2 *v2; // rcx
  int Instance; // ebx
  const struct _GUID *v4; // r8
  CSecurityAdmin2 *v5; // rcx
  const struct _GUID *v6; // r8
  int v7; // edi
  unsigned int v9; // [rsp+30h] [rbp-29h]
  unsigned int v10; // [rsp+30h] [rbp-29h]
  struct ISimpleTableDispenser *ppv; // [rsp+50h] [rbp-9h] BYREF
  struct _GUID *v12; // [rsp+58h] [rbp-1h] BYREF
  void *v13; // [rsp+60h] [rbp+7h] BYREF
  unsigned __int16 *v14; // [rsp+68h] [rbp+Fh] BYREF
  _QWORD v15[2]; // [rsp+70h] [rbp+17h] BYREF
  int v16; // [rsp+80h] [rbp+27h]
  int v17; // [rsp+84h] [rbp+2Bh]
  unsigned int v18; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v19; // [rsp+D0h] [rbp+77h] BYREF
  void *v20; // [rsp+D8h] [rbp+7Fh] BYREF

  ppv = 0;
  v13 = 0;
  v20 = 0;
  v12 = 0;
  v14 = 0;
  v18 = 0;
  v19 = 0;
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = CSecurityAdmin2::GetTable(v2, ppv, v4, &TID_APPLICATION, 0, 0, v9, 0x20000u, &v13);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v13 + 24LL))(v13);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v13 + 32LL))(v13);
        if ( Instance >= 0 )
        {
          while ( (*(int (__fastcall **)(void *))(*(_QWORD *)v13 + 40LL))(v13) >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, _QWORD, struct _GUID **))(*(_QWORD *)v13 + 64LL))(
                         v13,
                         0,
                         0,
                         0,
                         &v12);
            if ( Instance < 0 )
              break;
            Instance = ServerGetApplicationType(ppv, v12, &v18);
            if ( Instance < 0 )
              break;
            v19 = v18;
            (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
            Instance = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
            if ( Instance < 0 )
              break;
            v15[0] = v12;
            v15[1] = 0;
            v16 = 72;
            v17 = 16;
            Instance = CSecurityAdmin2::GetTable(
                         v5,
                         ppv,
                         v6,
                         &tidCOMSERVICES_ROLEDEFINITION,
                         v15,
                         (void *)1,
                         v10,
                         0x20000u,
                         &v20);
            if ( Instance < 0 )
              break;
            Instance = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v20 + 24LL))(v20);
            if ( Instance < 0 )
              break;
            Instance = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v20 + 32LL))(v20);
            if ( Instance < 0 )
              break;
            v7 = 0;
            while ( (*(int (__fastcall **)(void *))(*(_QWORD *)v20 + 40LL))(v20) >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)v20 + 64LL))(
                           v20,
                           1,
                           0,
                           0,
                           &v14);
              if ( Instance < 0 )
                goto LABEL_21;
              Instance = CSecurityAdmin2::UpdateRole(this, v12, v14);
              if ( Instance < 0 )
                goto LABEL_21;
              ++v7;
            }
            if ( v7 )
            {
              Instance = CSecurityAdmin2::UpdateSecurityDescriptors(
                           (CSecurityAdmin2 *)this,
                           v12,
                           0,
                           0,
                           0,
                           0,
                           0,
                           &v19,
                           1);
              if ( Instance < 0 )
                break;
              Instance = CSecurityAdmin2::UpdateSecurityPerimeter(this, v12);
              if ( Instance < 0 )
                break;
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
            v20 = 0;
          }
        }
      }
    }
  }
LABEL_21:
  if ( ppv )
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v13 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v20 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800286b0  mov     [rsp-8+arg_0], rbx
0x1800286b5  push    rbp
0x1800286b6  push    rsi
0x1800286b7  push    rdi
0x1800286b8  push    r14
0x1800286ba  push    r15
0x1800286bc  lea     rbp, [rsp-37h]
0x1800286c1  sub     rsp, 90h
0x1800286c8  xor     r14d, r14d
0x1800286cb  lea     rax, [rbp+57h+var_60]
0x1800286cf  mov     rsi, rcx
0x1800286d2  mov     [rbp+57h+var_60], r14
0x1800286d6  lea     r9, IID_ISimpleTableDispenser; riid
0x1800286dd  mov     [rbp+57h+var_50], r14
0x1800286e1  xor     edx, edx; pUnkOuter
0x1800286e3  mov     [rbp+57h+arg_18], r14
0x1800286e7  lea     r15d, [r14+1]
0x1800286eb  mov     [rbp+57h+var_58], r14
0x1800286ef  mov     r8d, r15d; dwClsContext
0x1800286f2  mov     [rbp+57h+var_48], r14
0x1800286f6  lea     rcx, CLSID_STDispenser; rclsid
0x1800286fd  mov     [rbp+57h+arg_8], r14d
0x180028701  mov     [rbp+57h+arg_10], r14d
0x180028705  mov     [rsp+0B0h+ppv], rax; ppv
0x18002870a  call    cs:__imp_CoCreateInstance
0x180028710  mov     ebx, eax
0x180028712  test    eax, eax
0x180028714  js      loc_180028969
0x18002871a  mov     rdx, [rbp+57h+var_60]; struct ISimpleTableDispenser *
0x18002871e  lea     rax, [rbp+57h+var_50]
0x180028722  mov     [rsp+0B0h+var_70], rax; void **
0x180028727  lea     r9, TID_APPLICATION; struct _GUID *
0x18002872e  mov     dword ptr [rsp+0B0h+var_78], 20000h; unsigned int
0x180028736  mov     [rsp+0B0h+var_88], r14; void *
0x18002873b  mov     [rsp+0B0h+ppv], r14; void *
0x180028740  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180028745  mov     ebx, eax
0x180028747  test    eax, eax
0x180028749  js      loc_180028969
0x18002874f  mov     rcx, [rbp+57h+var_50]
0x180028753  mov     rax, [rcx]
0x180028756  mov     rax, [rax+18h]
0x18002875a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002875f  mov     ebx, eax
0x180028761  test    eax, eax
0x180028763  js      loc_180028969
0x180028769  mov     rcx, [rbp+57h+var_50]
0x18002876d  mov     rax, [rcx]
0x180028770  mov     rax, [rax+20h]
0x180028774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028779  mov     ebx, eax
0x18002877b  test    eax, eax
0x18002877d  js      loc_180028969
0x180028783  mov     rcx, [rbp+57h+var_50]
0x180028787  mov     rax, [rcx]
0x18002878a  mov     rax, [rax+28h]
0x18002878e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028793  test    eax, eax
0x180028795  js      loc_180028969
0x18002879b  mov     rcx, [rbp+57h+var_50]
0x18002879f  lea     rdx, [rbp+57h+var_58]
0x1800287a3  mov     [rsp+0B0h+ppv], rdx
0x1800287a8  xor     r9d, r9d
0x1800287ab  xor     r8d, r8d
0x1800287ae  xor     edx, edx
0x1800287b0  mov     rax, [rcx]
0x1800287b3  mov     rax, [rax+40h]
0x1800287b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287bc  mov     ebx, eax
0x1800287be  test    eax, eax
0x1800287c0  js      loc_180028969
0x1800287c6  mov     rdx, [rbp+57h+var_58]
0x1800287ca  lea     r8, [rbp+57h+arg_8]
0x1800287ce  mov     rcx, [rbp+57h+var_60]
0x1800287d2  call    cs:__imp_ServerGetApplicationType
0x1800287d8  mov     ebx, eax
0x1800287da  test    eax, eax
0x1800287dc  js      loc_180028969
0x1800287e2  mov     eax, [rbp+57h+arg_8]
0x1800287e5  mov     rcx, [rbp+57h+var_60]
0x1800287e9  mov     [rbp+57h+arg_10], eax
0x1800287ec  mov     rax, [rcx]
0x1800287ef  mov     rax, [rax+10h]
0x1800287f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287f8  lea     rax, [rbp+57h+var_60]
0x1800287fc  mov     r8d, r15d; dwClsContext
0x1800287ff  lea     r9, IID_ISimpleTableDispenser; riid
0x180028806  mov     [rsp+0B0h+ppv], rax; ppv
0x18002880b  xor     edx, edx; pUnkOuter
0x18002880d  lea     rcx, CLSID_STDispenser; rclsid
0x180028814  call    cs:__imp_CoCreateInstance
0x18002881a  mov     ebx, eax
0x18002881c  test    eax, eax
0x18002881e  js      loc_180028969
0x180028824  mov     rax, [rbp+57h+var_58]
0x180028828  lea     r9, tidCOMSERVICES_ROLEDEFINITION; struct _GUID *
0x18002882f  mov     rdx, [rbp+57h+var_60]; struct ISimpleTableDispenser *
0x180028833  mov     [rbp+57h+var_40], rax
0x180028837  lea     rax, [rbp+57h+arg_18]
0x18002883b  mov     [rsp+0B0h+var_70], rax; void **
0x180028840  lea     rax, [rbp+57h+var_40]
0x180028844  mov     dword ptr [rsp+0B0h+var_78], 20000h; unsigned int
0x18002884c  mov     [rsp+0B0h+var_88], r15; void *
0x180028851  mov     [rsp+0B0h+ppv], rax; void *
0x180028856  mov     [rbp+57h+var_38], r14
0x18002885a  mov     [rbp+57h+var_30], 48h ; 'H'
0x180028861  mov     [rbp+57h+var_2C], 10h
0x180028868  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x18002886d  mov     ebx, eax
0x18002886f  test    eax, eax
0x180028871  js      loc_180028969
0x180028877  mov     rcx, [rbp+57h+arg_18]
0x18002887b  mov     rax, [rcx]
0x18002887e  mov     rax, [rax+18h]
0x180028882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028887  mov     ebx, eax
0x180028889  test    eax, eax
0x18002888b  js      loc_180028969
0x180028891  mov     rcx, [rbp+57h+arg_18]
0x180028895  mov     rax, [rcx]
0x180028898  mov     rax, [rax+20h]
0x18002889c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288a1  mov     ebx, eax
0x1800288a3  test    eax, eax
0x1800288a5  js      loc_180028969
0x1800288ab  mov     edi, r14d
0x1800288ae  mov     rcx, [rbp+57h+arg_18]
0x1800288b2  mov     rax, [rcx]
0x1800288b5  mov     rax, [rax+28h]
0x1800288b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288be  test    eax, eax
0x1800288c0  js      short loc_180028905
0x1800288c2  mov     rcx, [rbp+57h+arg_18]
0x1800288c6  lea     rdx, [rbp+57h+var_48]
0x1800288ca  mov     [rsp+0B0h+ppv], rdx
0x1800288cf  xor     r9d, r9d
0x1800288d2  xor     r8d, r8d
0x1800288d5  mov     edx, r15d
0x1800288d8  mov     rax, [rcx]
0x1800288db  mov     rax, [rax+40h]
0x1800288df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288e4  mov     ebx, eax
0x1800288e6  test    eax, eax
0x1800288e8  js      short loc_180028969
0x1800288ea  mov     r8, [rbp+57h+var_48]; unsigned __int16 *
0x1800288ee  mov     rcx, rsi; this
0x1800288f1  mov     rdx, [rbp+57h+var_58]; struct _GUID *
0x1800288f5  call    ?UpdateRole@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAG@Z; CSecurityAdmin2::UpdateRole(_GUID const &,ushort *)
0x1800288fa  mov     ebx, eax
0x1800288fc  test    eax, eax
0x1800288fe  js      short loc_180028969
0x180028900  add     edi, r15d
0x180028903  jmp     short loc_1800288AE
0x180028905  test    edi, edi
0x180028907  jz      short loc_180028950
0x180028909  mov     rdx, [rbp+57h+var_58]; struct _GUID *
0x18002890d  lea     rax, [rbp+57h+arg_10]
0x180028911  mov     dword ptr [rsp+0B0h+var_70], r15d; int
0x180028916  xor     r9d, r9d; struct _GUID *
0x180028919  mov     [rsp+0B0h+var_78], rax; unsigned int *
0x18002891e  xor     r8d, r8d; struct _GUID *
0x180028921  mov     [rsp+0B0h+var_80], r14; unsigned int *
0x180028926  mov     rcx, rsi; this
0x180028929  mov     [rsp+0B0h+var_88], r14; struct _GUID *
0x18002892e  mov     [rsp+0B0h+ppv], r14; struct _GUID *
0x180028933  call    ?UpdateSecurityDescriptors@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAU2@111PEAK2H@Z; CSecurityAdmin2::UpdateSecurityDescriptors(_GUID const &,_GUID *,_GUID *,_GUID *,_GUID *,ulong *,ulong *,int)
0x180028938  mov     ebx, eax
0x18002893a  test    eax, eax
0x18002893c  js      short loc_180028969
0x18002893e  mov     rdx, [rbp+57h+var_58]; struct _GUID *
0x180028942  mov     rcx, rsi; this
0x180028945  call    ?UpdateSecurityPerimeter@CSecurityAdmin2@@QEAAJAEBU_GUID@@@Z; CSecurityAdmin2::UpdateSecurityPerimeter(_GUID const &)
0x18002894a  mov     ebx, eax
0x18002894c  test    eax, eax
0x18002894e  js      short loc_180028969
0x180028950  mov     rcx, [rbp+57h+arg_18]
0x180028954  mov     rax, [rcx]
0x180028957  mov     rax, [rax+10h]
0x18002895b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028960  mov     [rbp+57h+arg_18], r14
0x180028964  jmp     loc_180028783
0x180028969  mov     rcx, [rbp+57h+var_60]
0x18002896d  test    rcx, rcx
0x180028970  jz      short loc_18002897E
0x180028972  mov     rax, [rcx]
0x180028975  mov     rax, [rax+10h]
0x180028979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002897e  mov     rcx, [rbp+57h+var_50]
0x180028982  test    rcx, rcx
0x180028985  jz      short loc_180028993
0x180028987  mov     rax, [rcx]
0x18002898a  mov     rax, [rax+10h]
0x18002898e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028993  mov     rcx, [rbp+57h+arg_18]
0x180028997  test    rcx, rcx
0x18002899a  jz      short loc_1800289A8
0x18002899c  mov     rax, [rcx]
0x18002899f  mov     rax, [rax+10h]
0x1800289a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289a8  mov     eax, ebx
0x1800289aa  mov     rbx, [rsp+0B0h+arg_0]
0x1800289b2  add     rsp, 90h
0x1800289b9  pop     r15
0x1800289bb  pop     r14
0x1800289bd  pop     rdi
0x1800289be  pop     rsi
0x1800289bf  pop     rbp
0x1800289c0  retn
```
