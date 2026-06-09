# CSecurityAdmin2::RefreshSecurityDatabase(void)

- ea: `0x1800360b0`
- end: `0x1800363c1`
- name: `?RefreshSecurityDatabase@CSecurityAdmin2@@QEAAJXZ`
- size: `785`
- prototype: `__int64 __fastcall(CSecurityAdmin2 *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180033f20`

## callees

- `0x180033d68`
- `0x180035a0c`
- `0x1800360b0`
- `0x1800367a8`
- `0x180036dc4`
- `0x180058010`

## import_xrefs

- `CLBCatQ!ServerGetApplicationType` at `0x1800361d2`
- `CLBCatQ!ServerGetApplicationType` at `0x1800361d2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003610a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036214`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003610a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036214`

## pseudocode

```c
__int64 __fastcall CSecurityAdmin2::RefreshSecurityDatabase(CSecurityAdmin2 *this)
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
              Instance = CSecurityAdmin2::UpdateSecurityDescriptors(this, v12, 0, 0, 0, 0, 0, &v19, 1);
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
0x1800360b0  mov     [rsp-8+arg_0], rbx
0x1800360b5  push    rbp
0x1800360b6  push    rsi
0x1800360b7  push    rdi
0x1800360b8  push    r14
0x1800360ba  push    r15
0x1800360bc  lea     rbp, [rsp-37h]
0x1800360c1  sub     rsp, 90h
0x1800360c8  xor     r14d, r14d
0x1800360cb  lea     rax, [rbp+57h+var_60]
0x1800360cf  mov     rsi, rcx
0x1800360d2  mov     [rbp+57h+var_60], r14
0x1800360d6  lea     r9, IID_ISimpleTableDispenser; riid
0x1800360dd  mov     [rbp+57h+var_50], r14
0x1800360e1  xor     edx, edx; pUnkOuter
0x1800360e3  mov     [rbp+57h+arg_18], r14
0x1800360e7  lea     r15d, [r14+1]
0x1800360eb  mov     [rbp+57h+var_58], r14
0x1800360ef  mov     r8d, r15d; dwClsContext
0x1800360f2  mov     [rbp+57h+var_48], r14
0x1800360f6  lea     rcx, CLSID_STDispenser; rclsid
0x1800360fd  mov     [rbp+57h+arg_8], r14d
0x180036101  mov     [rbp+57h+arg_10], r14d
0x180036105  mov     [rsp+0B0h+ppv], rax; ppv
0x18003610a  call    cs:__imp_CoCreateInstance
0x180036110  mov     ebx, eax
0x180036112  test    eax, eax
0x180036114  js      loc_180036369
0x18003611a  mov     rdx, [rbp+57h+var_60]; struct ISimpleTableDispenser *
0x18003611e  lea     rax, [rbp+57h+var_50]
0x180036122  mov     [rsp+0B0h+var_70], rax; void **
0x180036127  lea     r9, TID_APPLICATION; struct _GUID *
0x18003612e  mov     dword ptr [rsp+0B0h+var_78], 20000h; unsigned int
0x180036136  mov     [rsp+0B0h+var_88], r14; void *
0x18003613b  mov     [rsp+0B0h+ppv], r14; void *
0x180036140  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180036145  mov     ebx, eax
0x180036147  test    eax, eax
0x180036149  js      loc_180036369
0x18003614f  mov     rcx, [rbp+57h+var_50]
0x180036153  mov     rax, [rcx]
0x180036156  mov     rax, [rax+18h]
0x18003615a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003615f  mov     ebx, eax
0x180036161  test    eax, eax
0x180036163  js      loc_180036369
0x180036169  mov     rcx, [rbp+57h+var_50]
0x18003616d  mov     rax, [rcx]
0x180036170  mov     rax, [rax+20h]
0x180036174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036179  mov     ebx, eax
0x18003617b  test    eax, eax
0x18003617d  js      loc_180036369
0x180036183  mov     rcx, [rbp+57h+var_50]
0x180036187  mov     rax, [rcx]
0x18003618a  mov     rax, [rax+28h]
0x18003618e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036193  test    eax, eax
0x180036195  js      loc_180036369
0x18003619b  mov     rcx, [rbp+57h+var_50]
0x18003619f  lea     rdx, [rbp+57h+var_58]
0x1800361a3  mov     [rsp+0B0h+ppv], rdx
0x1800361a8  xor     r9d, r9d
0x1800361ab  xor     r8d, r8d
0x1800361ae  xor     edx, edx
0x1800361b0  mov     rax, [rcx]
0x1800361b3  mov     rax, [rax+40h]
0x1800361b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361bc  mov     ebx, eax
0x1800361be  test    eax, eax
0x1800361c0  js      loc_180036369
0x1800361c6  mov     rdx, [rbp+57h+var_58]
0x1800361ca  lea     r8, [rbp+57h+arg_8]
0x1800361ce  mov     rcx, [rbp+57h+var_60]
0x1800361d2  call    cs:__imp_ServerGetApplicationType
0x1800361d8  mov     ebx, eax
0x1800361da  test    eax, eax
0x1800361dc  js      loc_180036369
0x1800361e2  mov     eax, [rbp+57h+arg_8]
0x1800361e5  mov     rcx, [rbp+57h+var_60]
0x1800361e9  mov     [rbp+57h+arg_10], eax
0x1800361ec  mov     rax, [rcx]
0x1800361ef  mov     rax, [rax+10h]
0x1800361f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361f8  lea     rax, [rbp+57h+var_60]
0x1800361fc  mov     r8d, r15d; dwClsContext
0x1800361ff  lea     r9, IID_ISimpleTableDispenser; riid
0x180036206  mov     [rsp+0B0h+ppv], rax; ppv
0x18003620b  xor     edx, edx; pUnkOuter
0x18003620d  lea     rcx, CLSID_STDispenser; rclsid
0x180036214  call    cs:__imp_CoCreateInstance
0x18003621a  mov     ebx, eax
0x18003621c  test    eax, eax
0x18003621e  js      loc_180036369
0x180036224  mov     rax, [rbp+57h+var_58]
0x180036228  lea     r9, tidCOMSERVICES_ROLEDEFINITION; struct _GUID *
0x18003622f  mov     rdx, [rbp+57h+var_60]; struct ISimpleTableDispenser *
0x180036233  mov     [rbp+57h+var_40], rax
0x180036237  lea     rax, [rbp+57h+arg_18]
0x18003623b  mov     [rsp+0B0h+var_70], rax; void **
0x180036240  lea     rax, [rbp+57h+var_40]
0x180036244  mov     dword ptr [rsp+0B0h+var_78], 20000h; unsigned int
0x18003624c  mov     [rsp+0B0h+var_88], r15; void *
0x180036251  mov     [rsp+0B0h+ppv], rax; void *
0x180036256  mov     [rbp+57h+var_38], r14
0x18003625a  mov     [rbp+57h+var_30], 48h ; 'H'
0x180036261  mov     [rbp+57h+var_2C], 10h
0x180036268  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x18003626d  mov     ebx, eax
0x18003626f  test    eax, eax
0x180036271  js      loc_180036369
0x180036277  mov     rcx, [rbp+57h+arg_18]
0x18003627b  mov     rax, [rcx]
0x18003627e  mov     rax, [rax+18h]
0x180036282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036287  mov     ebx, eax
0x180036289  test    eax, eax
0x18003628b  js      loc_180036369
0x180036291  mov     rcx, [rbp+57h+arg_18]
0x180036295  mov     rax, [rcx]
0x180036298  mov     rax, [rax+20h]
0x18003629c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362a1  mov     ebx, eax
0x1800362a3  test    eax, eax
0x1800362a5  js      loc_180036369
0x1800362ab  mov     edi, r14d
0x1800362ae  mov     rcx, [rbp+57h+arg_18]
0x1800362b2  mov     rax, [rcx]
0x1800362b5  mov     rax, [rax+28h]
0x1800362b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362be  test    eax, eax
0x1800362c0  js      short loc_180036305
0x1800362c2  mov     rcx, [rbp+57h+arg_18]
0x1800362c6  lea     rdx, [rbp+57h+var_48]
0x1800362ca  mov     [rsp+0B0h+ppv], rdx
0x1800362cf  xor     r9d, r9d
0x1800362d2  xor     r8d, r8d
0x1800362d5  mov     edx, r15d
0x1800362d8  mov     rax, [rcx]
0x1800362db  mov     rax, [rax+40h]
0x1800362df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362e4  mov     ebx, eax
0x1800362e6  test    eax, eax
0x1800362e8  js      short loc_180036369
0x1800362ea  mov     r8, [rbp+57h+var_48]; unsigned __int16 *
0x1800362ee  mov     rcx, rsi; this
0x1800362f1  mov     rdx, [rbp+57h+var_58]; struct _GUID *
0x1800362f5  call    ?UpdateRole@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAG@Z; CSecurityAdmin2::UpdateRole(_GUID const &,ushort *)
0x1800362fa  mov     ebx, eax
0x1800362fc  test    eax, eax
0x1800362fe  js      short loc_180036369
0x180036300  add     edi, r15d
0x180036303  jmp     short loc_1800362AE
0x180036305  test    edi, edi
0x180036307  jz      short loc_180036350
0x180036309  mov     rdx, [rbp+57h+var_58]; struct _GUID *
0x18003630d  lea     rax, [rbp+57h+arg_10]
0x180036311  mov     dword ptr [rsp+0B0h+var_70], r15d; int
0x180036316  xor     r9d, r9d; struct _GUID *
0x180036319  mov     [rsp+0B0h+var_78], rax; unsigned int *
0x18003631e  xor     r8d, r8d; struct _GUID *
0x180036321  mov     [rsp+0B0h+var_80], r14; unsigned int *
0x180036326  mov     rcx, rsi; this
0x180036329  mov     [rsp+0B0h+var_88], r14; struct _GUID *
0x18003632e  mov     [rsp+0B0h+ppv], r14; struct _GUID *
0x180036333  call    ?UpdateSecurityDescriptors@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAU2@111PEAK2H@Z; CSecurityAdmin2::UpdateSecurityDescriptors(_GUID const &,_GUID *,_GUID *,_GUID *,_GUID *,ulong *,ulong *,int)
0x180036338  mov     ebx, eax
0x18003633a  test    eax, eax
0x18003633c  js      short loc_180036369
0x18003633e  mov     rdx, [rbp+57h+var_58]; struct _GUID *
0x180036342  mov     rcx, rsi; this
0x180036345  call    ?UpdateSecurityPerimeter@CSecurityAdmin2@@QEAAJAEBU_GUID@@@Z; CSecurityAdmin2::UpdateSecurityPerimeter(_GUID const &)
0x18003634a  mov     ebx, eax
0x18003634c  test    eax, eax
0x18003634e  js      short loc_180036369
0x180036350  mov     rcx, [rbp+57h+arg_18]
0x180036354  mov     rax, [rcx]
0x180036357  mov     rax, [rax+10h]
0x18003635b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036360  mov     [rbp+57h+arg_18], r14
0x180036364  jmp     loc_180036183
0x180036369  mov     rcx, [rbp+57h+var_60]
0x18003636d  test    rcx, rcx
0x180036370  jz      short loc_18003637E
0x180036372  mov     rax, [rcx]
0x180036375  mov     rax, [rax+10h]
0x180036379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003637e  mov     rcx, [rbp+57h+var_50]
0x180036382  test    rcx, rcx
0x180036385  jz      short loc_180036393
0x180036387  mov     rax, [rcx]
0x18003638a  mov     rax, [rax+10h]
0x18003638e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036393  mov     rcx, [rbp+57h+arg_18]
0x180036397  test    rcx, rcx
0x18003639a  jz      short loc_1800363A8
0x18003639c  mov     rax, [rcx]
0x18003639f  mov     rax, [rax+10h]
0x1800363a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363a8  mov     eax, ebx
0x1800363aa  mov     rbx, [rsp+0B0h+arg_0]
0x1800363b2  add     rsp, 90h
0x1800363b9  pop     r15
0x1800363bb  pop     r14
0x1800363bd  pop     rdi
0x1800363be  pop     rsi
0x1800363bf  pop     rbp
0x1800363c0  retn
```
