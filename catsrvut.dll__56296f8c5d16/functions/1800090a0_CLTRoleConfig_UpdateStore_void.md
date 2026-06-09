# CLTRoleConfig::UpdateStore(void)

- ea: `0x1800090a0`
- end: `0x18000949c`
- name: `?UpdateStore@CLTRoleConfig@@UEAAJXZ`
- size: `1020`
- prototype: `__int64 __fastcall(CLTRoleConfig *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180007208`
- `0x1800090a0`
- `0x18001e864`
- `0x18001efa0`
- `0x180026924`
- `0x18002bac4`
- `0x1800422c8`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000924a`
- `msvcrt!_wcsicmp` at `0x18000924a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009347`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009347`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093c2`

## pseudocode

```c
__int64 __fastcall CLTRoleConfig::UpdateStore(CLTRoleConfig *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v3)(_QWORD, GUID *, __int64 *); // rax
  __int64 result; // rax
  const struct _GUID *v5; // rcx
  int SecurityAdmin; // ebx
  int v7; // esi
  int v8; // eax
  __int64 *v9; // rcx
  __int64 v10; // r10
  int v11; // eax
  const wchar_t *RoleName; // rax
  int v13; // eax
  int v14; // eax
  unsigned int v15; // ecx
  __int64 v16; // rax
  bool v17; // sf
  int v18; // eax
  unsigned int *v19; // [rsp+20h] [rbp-59h]
  struct ISimpleTableDispenser *v20; // [rsp+30h] [rbp-49h]
  unsigned int v21; // [rsp+40h] [rbp-39h] BYREF
  int v22; // [rsp+44h] [rbp-35h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-31h] BYREF
  LPVOID v24; // [rsp+50h] [rbp-29h] BYREF
  void *v25; // [rsp+58h] [rbp-21h] BYREF
  struct _GUID *v26; // [rsp+60h] [rbp-19h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-11h] BYREF
  __int64 v28; // [rsp+70h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-1h] BYREF
  __int64 v30; // [rsp+80h] [rbp+7h]
  struct _GUID v31; // [rsp+88h] [rbp+Fh] BYREF

  v25 = 0;
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  v28 = 0;
  v22 = 0;
  v24 = 0;
  v30 = 0;
  pv = 0;
  String1 = 0;
  v26 = 0;
  v3 = *v2;
  v23 = 0;
  result = (*v3)(v2, &IID_ISimpleTableControl, &v28);
  if ( (int)result < 0 )
    return result;
  SecurityAdmin = GetSecurityAdmin(v5, &v25);
  if ( SecurityAdmin < 0 )
    goto LABEL_48;
  v7 = 0;
  SecurityAdmin = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 104LL))(*((_QWORD *)this + 5));
  if ( SecurityAdmin < 0 )
    goto LABEL_48;
  while ( 1 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 5) + 112LL))(*((_QWORD *)this + 5), &v22);
    v9 = (__int64 *)*((_QWORD *)this + 5);
    v10 = *v9;
    if ( v8 < 0 )
      break;
    SecurityAdmin = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _QWORD, _QWORD, wchar_t **))(v10 + 152))(
                      v9,
                      1,
                      0,
                      0,
                      0,
                      &String1);
    if ( SecurityAdmin < 0 )
      goto LABEL_48;
    SecurityAdmin = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, struct _GUID **))(**((_QWORD **)this + 5) + 152LL))(
                      *((_QWORD *)this + 5),
                      0,
                      0,
                      0,
                      0,
                      &v26);
    if ( SecurityAdmin < 0 )
      goto LABEL_48;
    v31 = 0;
    v21 = 0;
    SecurityAdmin = GetSomeApplicationProperties(v26, &v31, &v23, &v21, 0, 0, v20, 0);
    if ( SecurityAdmin < 0 )
      goto LABEL_48;
    if ( !v21 )
      goto LABEL_38;
    SecurityAdmin = GetSomePartitionProperties(&v31, &v21, 0);
    if ( SecurityAdmin < 0 )
      goto LABEL_48;
    if ( !v21 )
    {
LABEL_38:
      SecurityAdmin = -2146368470;
      goto LABEL_48;
    }
    v11 = v22;
    if ( v22 == 3 )
    {
      if ( !v23 )
        goto LABEL_18;
      RoleName = CPartitionRoleCheck::GetRoleName(1);
      if ( !_wcsicmp(String1, RoleName) )
      {
        v13 = MoveToSecondUserInRole(v26, String1);
        SecurityAdmin = v13;
        if ( v13 == -2146367487 )
        {
          SecurityAdmin = -2146368461;
          goto LABEL_48;
        }
        if ( v13 < 0 )
          goto LABEL_48;
      }
      v11 = v22;
    }
    if ( ((v11 - 1) & 0xFFFFFFFD) == 0 )
    {
LABEL_18:
      HIDWORD(v19) = 0;
      SecurityAdmin = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 5) + 152LL))(
                        *((_QWORD *)this + 5),
                        2,
                        0);
      if ( SecurityAdmin < 0 )
        goto LABEL_48;
      v14 = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *, bool))(*(_QWORD *)v25 + 80LL))(
              v25,
              v30,
              &v24,
              v22 == 1);
      v15 = 1;
      v21 = 1;
      if ( v14 )
      {
        if ( v14 < 0 )
          goto LABEL_36;
      }
      else
      {
        v16 = *(_QWORD *)&v26->Data1 - *(_QWORD *)&CLSID_SystemApplication.Data1;
        if ( *(_QWORD *)&v26->Data1 == *(_QWORD *)&CLSID_SystemApplication.Data1 )
          v16 = *(_QWORD *)v26->Data4 - *(_QWORD *)CLSID_SystemApplication.Data4;
        if ( v16
          || v22 != 1
          || (*(unsigned int (__fastcall **)(void *, LPVOID, LPVOID *, _QWORD))(*(_QWORD *)v25 + 88LL))(
               v25,
               v24,
               &pv,
               0)
          || !pv )
        {
LABEL_29:
          SecurityAdmin = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 80LL))(v28);
          if ( SecurityAdmin >= 0 )
          {
            SecurityAdmin = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, LPVOID))(**((_QWORD **)this + 5) + 160LL))(
                              *((_QWORD *)this + 5),
                              2,
                              0,
                              v24);
            if ( SecurityAdmin >= 0 )
              SecurityAdmin = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 144LL))(*((_QWORD *)this + 5));
          }
          CoTaskMemFree(v24);
          v17 = SecurityAdmin < 0;
          goto LABEL_33;
        }
        CheckUserAllowedInRole(String1, (unsigned __int16 *)pv, (int *)&v21);
        CoTaskMemFree(pv);
        v15 = v21;
      }
      if ( v15 )
        goto LABEL_29;
      CoTaskMemFree(v24);
LABEL_36:
      v22 = 0;
      v7 = 1;
      SecurityAdmin = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 64LL))(v28, 0);
      v17 = SecurityAdmin < 0;
LABEL_33:
      if ( v17 )
        goto LABEL_48;
    }
  }
  SecurityAdmin = (*(__int64 (**)(void))(v10 + 96))();
  if ( SecurityAdmin >= 0 )
  {
    LODWORD(v19) = 3;
    v18 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, char *, unsigned int *))(*(_QWORD *)v25 + 32LL))(
            v25,
            *((_QWORD *)this + 6),
            1,
            (char *)this + 56,
            v19);
    SecurityAdmin = 0;
    if ( v18 != 1 )
      SecurityAdmin = v18;
    if ( SecurityAdmin == -2146367487 )
    {
      SecurityAdmin = -2146367480;
      goto LABEL_45;
    }
    if ( SecurityAdmin >= 0 )
    {
LABEL_46:
      SecurityAdmin = 0;
      if ( v7 )
        SecurityAdmin = -2146368497;
    }
    else
    {
LABEL_45:
      if ( v7 )
        goto LABEL_46;
    }
  }
LABEL_48:
  if ( v25 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return (unsigned int)SecurityAdmin;
}

```

## disassembly

```asm
0x1800090a0  push    rbp
0x1800090a2  push    rbx
0x1800090a3  push    rsi
0x1800090a4  push    rdi
0x1800090a5  push    r14
0x1800090a7  push    r15
0x1800090a9  lea     rbp, [rsp-2Fh]
0x1800090ae  sub     rsp, 0A8h
0x1800090b5  mov     rax, cs:__security_cookie
0x1800090bc  xor     rax, rsp
0x1800090bf  mov     [rbp+57h+var_38], rax
0x1800090c3  xor     r14d, r14d
0x1800090c6  lea     r8, [rbp+57h+var_60]
0x1800090ca  mov     rdi, rcx
0x1800090cd  mov     [rbp+57h+var_78], r14
0x1800090d1  mov     rcx, [rcx+28h]
0x1800090d5  lea     rdx, IID_ISimpleTableControl
0x1800090dc  mov     [rbp+57h+var_60], r14
0x1800090e0  mov     [rbp+57h+var_8C], r14d
0x1800090e4  mov     [rbp+57h+var_80], r14
0x1800090e8  mov     [rbp+57h+var_50], r14
0x1800090ec  mov     [rbp+57h+pv], r14
0x1800090f0  mov     [rbp+57h+String1], r14
0x1800090f4  mov     [rbp+57h+var_70], r14
0x1800090f8  mov     rax, [rcx]
0x1800090fb  mov     [rbp+57h+var_88], r14d
0x1800090ff  mov     rax, [rax]
0x180009102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009107  test    eax, eax
0x180009109  js      loc_180009480
0x18000910f  lea     rdx, [rbp+57h+var_78]; void **
0x180009113  call    ?GetSecurityAdmin@@YAJAEBU_GUID@@PEAPEAX@Z; GetSecurityAdmin(_GUID const &,void * *)
0x180009118  mov     ebx, eax
0x18000911a  test    eax, eax
0x18000911c  js      loc_180009454
0x180009122  mov     rcx, [rdi+28h]
0x180009126  mov     esi, r14d
0x180009129  mov     rax, [rcx]
0x18000912c  mov     rax, [rax+68h]
0x180009130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009135  mov     ebx, eax
0x180009137  test    eax, eax
0x180009139  js      loc_180009454
0x18000913f  lea     r15d, [r14+1]
0x180009143  mov     rcx, [rdi+28h]
0x180009147  lea     rdx, [rbp+57h+var_8C]
0x18000914b  mov     rax, [rcx]
0x18000914e  mov     rax, [rax+70h]
0x180009152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009157  mov     rcx, [rdi+28h]
0x18000915b  mov     r10, [rcx]
0x18000915e  test    eax, eax
0x180009160  js      loc_1800093F5
0x180009166  lea     rax, [rbp+57h+String1]
0x18000916a  xor     r9d, r9d
0x18000916d  mov     [rsp+0D0h+var_A8], rax
0x180009172  xor     r8d, r8d
0x180009175  mov     rax, [r10+98h]
0x18000917c  mov     edx, r15d
0x18000917f  mov     [rsp+0D0h+var_B0], r14
0x180009184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009189  mov     ebx, eax
0x18000918b  test    eax, eax
0x18000918d  js      loc_180009454
0x180009193  mov     rcx, [rdi+28h]
0x180009197  lea     rdx, [rbp+57h+var_70]
0x18000919b  mov     [rsp+0D0h+var_A8], rdx
0x1800091a0  xor     r9d, r9d
0x1800091a3  xor     r8d, r8d
0x1800091a6  mov     [rsp+0D0h+var_B0], r14
0x1800091ab  xor     edx, edx
0x1800091ad  mov     rax, [rcx]
0x1800091b0  mov     rax, [rax+98h]
0x1800091b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091bc  mov     ebx, eax
0x1800091be  test    eax, eax
0x1800091c0  js      loc_180009454
0x1800091c6  mov     rcx, [rbp+57h+var_70]; struct _GUID *
0x1800091ca  lea     r9, [rbp+57h+var_90]; unsigned int *
0x1800091ce  xorps   xmm0, xmm0
0x1800091d1  mov     [rsp+0D0h+var_98], r14; enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *
0x1800091d6  mov     [rsp+0D0h+var_A8], r14; unsigned int *
0x1800091db  lea     r8, [rbp+57h+var_88]; unsigned int *
0x1800091df  lea     rdx, [rbp+57h+var_48]; struct _GUID *
0x1800091e3  mov     [rsp+0D0h+var_B0], r14; unsigned int *
0x1800091e8  movups  xmmword ptr [rbp+57h+var_48.Data1], xmm0
0x1800091ec  mov     [rbp+57h+var_90], r14d
0x1800091f0  call    ?GetSomeApplicationProperties@@YAJAEBU_GUID@@PEAU1@PEAK2222PEAW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; GetSomeApplicationProperties(_GUID const &,_GUID *,ulong *,ulong *,ulong *,ulong *,ulong *,__MIDL___MIDL_itf_registrar_0000_0000_0001 *)
0x1800091f5  mov     ebx, eax
0x1800091f7  test    eax, eax
0x1800091f9  js      loc_180009454
0x1800091ff  cmp     [rbp+57h+var_90], r14d
0x180009203  jz      loc_1800093EE
0x180009209  xor     r8d, r8d; unsigned int *
0x18000920c  lea     rdx, [rbp+57h+var_90]; unsigned int *
0x180009210  lea     rcx, [rbp+57h+var_48]; struct _GUID *
0x180009214  call    ?GetSomePartitionProperties@@YAJAEBU_GUID@@PEAK1@Z; GetSomePartitionProperties(_GUID const &,ulong *,ulong *)
0x180009219  mov     ebx, eax
0x18000921b  test    eax, eax
0x18000921d  js      loc_180009454
0x180009223  cmp     [rbp+57h+var_90], r14d
0x180009227  jz      loc_1800093EE
0x18000922d  mov     eax, [rbp+57h+var_8C]
0x180009230  cmp     eax, 3
0x180009233  jnz     short loc_180009279
0x180009235  cmp     [rbp+57h+var_88], r14d
0x180009239  jz      short loc_180009286
0x18000923b  mov     ecx, r15d; int
0x18000923e  call    ?GetRoleName@CPartitionRoleCheck@@SAPEBGJ@Z; CPartitionRoleCheck::GetRoleName(long)
0x180009243  mov     rcx, [rbp+57h+String1]; String1
0x180009247  mov     rdx, rax; String2
0x18000924a  call    cs:__imp__wcsicmp
0x180009250  test    eax, eax
0x180009252  jnz     short loc_180009276
0x180009254  mov     rdx, [rbp+57h+String1]; unsigned __int16 *
0x180009258  mov     rcx, [rbp+57h+var_70]; struct _GUID *
0x18000925c  call    ?MoveToSecondUserInRole@@YAJAEAU_GUID@@PEAG@Z; MoveToSecondUserInRole(_GUID &,ushort *)
0x180009261  mov     ebx, eax
0x180009263  cmp     eax, 80110801h
0x180009268  jz      loc_1800093E7
0x18000926e  test    eax, eax
0x180009270  js      loc_180009454
0x180009276  mov     eax, [rbp+57h+var_8C]
0x180009279  dec     eax
0x18000927b  test    eax, 0FFFFFFFDh
0x180009280  jnz     loc_180009143
0x180009286  mov     rcx, [rdi+28h]
0x18000928a  lea     rdx, [rbp+57h+var_50]
0x18000928e  mov     [rsp+0D0h+var_A8], rdx
0x180009293  xor     r9d, r9d
0x180009296  xor     r8d, r8d
0x180009299  mov     [rsp+0D0h+var_B0], r14
0x18000929e  mov     rax, [rcx]
0x1800092a1  lea     edx, [r9+2]
0x1800092a5  mov     rax, [rax+98h]
0x1800092ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092b1  mov     ebx, eax
0x1800092b3  test    eax, eax
0x1800092b5  js      loc_180009454
0x1800092bb  mov     rcx, [rbp+57h+var_78]
0x1800092bf  lea     r8, [rbp+57h+var_80]
0x1800092c3  cmp     [rbp+57h+var_8C], r15d
0x1800092c7  mov     r9d, r14d
0x1800092ca  mov     rdx, [rbp+57h+var_50]
0x1800092ce  setz    r9b
0x1800092d2  mov     rax, [rcx]
0x1800092d5  mov     rax, [rax+50h]
0x1800092d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092de  mov     ecx, r15d
0x1800092e1  mov     [rbp+57h+var_90], ecx
0x1800092e4  test    eax, eax
0x1800092e6  jnz     short loc_180009352
0x1800092e8  mov     rcx, [rbp+57h+var_70]
0x1800092ec  mov     rax, [rcx]
0x1800092ef  sub     rax, qword ptr cs:CLSID_SystemApplication.Data1
0x1800092f6  jnz     short loc_180009303
0x1800092f8  mov     rax, [rcx+8]
0x1800092fc  sub     rax, qword ptr cs:CLSID_SystemApplication.Data4
0x180009303  test    rax, rax
0x180009306  jnz     short loc_180009358
0x180009308  cmp     [rbp+57h+var_8C], r15d
0x18000930c  jnz     short loc_180009358
0x18000930e  mov     rcx, [rbp+57h+var_78]
0x180009312  lea     r8, [rbp+57h+pv]
0x180009316  mov     rdx, [rbp+57h+var_80]
0x18000931a  xor     r9d, r9d
0x18000931d  mov     rax, [rcx]
0x180009320  mov     rax, [rax+58h]
0x180009324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009329  test    eax, eax
0x18000932b  jnz     short loc_180009358
0x18000932d  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x180009331  test    rdx, rdx
0x180009334  jz      short loc_180009358
0x180009336  mov     rcx, [rbp+57h+String1]; unsigned __int16 *
0x18000933a  lea     r8, [rbp+57h+var_90]; int *
0x18000933e  call    ?CheckUserAllowedInRole@@YAXPEAG0PEAH@Z; CheckUserAllowedInRole(ushort *,ushort *,int *)
0x180009343  mov     rcx, [rbp+57h+pv]; pv
0x180009347  call    cs:__imp_CoTaskMemFree
0x18000934d  mov     ecx, [rbp+57h+var_90]
0x180009350  jmp     short loc_180009354
0x180009352  js      short loc_1800093C8
0x180009354  test    ecx, ecx
0x180009356  jz      short loc_1800093BE
0x180009358  mov     rcx, [rbp+57h+var_60]
0x18000935c  mov     rax, [rcx]
0x18000935f  mov     rax, [rax+50h]
0x180009363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009368  mov     ebx, eax
0x18000936a  test    eax, eax
0x18000936c  js      short loc_1800093A7
0x18000936e  mov     rcx, [rdi+28h]
0x180009372  xor     r8d, r8d
0x180009375  mov     r9, [rbp+57h+var_80]
0x180009379  mov     rax, [rcx]
0x18000937c  lea     edx, [r8+2]
0x180009380  mov     rax, [rax+0A0h]
0x180009387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000938c  mov     ebx, eax
0x18000938e  test    eax, eax
0x180009390  js      short loc_1800093A7
0x180009392  mov     rcx, [rdi+28h]
0x180009396  mov     rax, [rcx]
0x180009399  mov     rax, [rax+90h]
0x1800093a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093a5  mov     ebx, eax
0x1800093a7  mov     rcx, [rbp+57h+var_80]; pv
0x1800093ab  call    cs:__imp_CoTaskMemFree
0x1800093b1  test    ebx, ebx
0x1800093b3  jns     loc_180009143
0x1800093b9  jmp     loc_180009454
0x1800093be  mov     rcx, [rbp+57h+var_80]; pv
0x1800093c2  call    cs:__imp_CoTaskMemFree
0x1800093c8  mov     rcx, [rbp+57h+var_60]
0x1800093cc  xor     edx, edx
0x1800093ce  mov     [rbp+57h+var_8C], r14d
0x1800093d2  mov     esi, r15d
0x1800093d5  mov     rax, [rcx]
0x1800093d8  mov     rax, [rax+40h]
0x1800093dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093e1  mov     ebx, eax
0x1800093e3  test    eax, eax
0x1800093e5  jmp     short loc_1800093B3
0x1800093e7  mov     ebx, 80110433h
0x1800093ec  jmp     short loc_180009454
0x1800093ee  mov     ebx, 8011042Ah
0x1800093f3  jmp     short loc_180009454
0x1800093f5  mov     rax, [r10+60h]
0x1800093f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093fe  mov     ebx, eax
0x180009400  test    eax, eax
0x180009402  js      short loc_180009454
0x180009404  mov     rcx, [rbp+57h+var_78]
0x180009408  lea     r9, [rdi+38h]
0x18000940c  mov     rdx, [rdi+30h]
0x180009410  mov     r8d, r15d
0x180009413  mov     dword ptr [rsp+0D0h+var_B0], 3
0x18000941b  mov     rax, [rcx]
0x18000941e  mov     rax, [rax+20h]
0x180009422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009427  cmp     eax, r15d
0x18000942a  mov     ebx, r14d
0x18000942d  cmovnz  ebx, eax
0x180009430  cmp     ebx, 80110801h
0x180009436  jnz     short loc_18000943F
0x180009438  mov     ebx, 80110808h
0x18000943d  jmp     short loc_180009443
0x18000943f  test    ebx, ebx
0x180009441  jns     short loc_180009447
0x180009443  test    esi, esi
0x180009445  jz      short loc_180009454
0x180009447  test    esi, esi
0x180009449  mov     ebx, r14d
0x18000944c  mov     eax, 8011040Fh
0x180009451  cmovnz  ebx, eax
0x180009454  mov     rcx, [rbp+57h+var_78]
0x180009458  test    rcx, rcx
0x18000945b  jz      short loc_180009469
0x18000945d  mov     rax, [rcx]
0x180009460  mov     rax, [rax+10h]
0x180009464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009469  mov     rcx, [rbp+57h+var_60]
0x18000946d  test    rcx, rcx
0x180009470  jz      short loc_18000947E
0x180009472  mov     rax, [rcx]
0x180009475  mov     rax, [rax+10h]
0x180009479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000947e  mov     eax, ebx
0x180009480  mov     rcx, [rbp+57h+var_38]
0x180009484  xor     rcx, rsp; StackCookie
0x180009487  call    __security_check_cookie
0x18000948c  add     rsp, 0A8h
0x180009493  pop     r15
0x180009495  pop     r14
0x180009497  pop     rdi
0x180009498  pop     rsi
0x180009499  pop     rbx
0x18000949a  pop     rbp
0x18000949b  retn
```
