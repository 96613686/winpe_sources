# LtPartGetClassObject

- ea: `0x180002890`
- end: `0x180002b5b`
- name: `LtPartGetClassObject`
- size: `715`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002440`

## callees

- `0x180002890`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800028e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000298c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002a13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ae4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800028e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000298c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002a13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ae4`

## pseudocode

```c
__int64 __fastcall LtPartGetClassObject(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rsi
  unsigned int v9; // ebp
  __int64 v10; // rax
  _QWORD *v11; // rax
  int v12; // eax
  __int64 v13; // rax
  _QWORD *v14; // rax
  __int64 v15; // rax
  _QWORD *v16; // rax

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v6 = *a1 - clsidSLTPART;
  if ( *a1 == clsidSLTPART )
    v6 = a1[1] - 0x968735A7FB8538DLL;
  if ( v6 )
  {
    v10 = *a1 - clsidSLTPartitionUsers;
    if ( *a1 == clsidSLTPartitionUsers )
      v10 = a1[1] + 0x5C9F957E77223465LL;
    if ( v10 )
    {
      v13 = *a1 - clsidSLTPARTITIONROLES;
      if ( *a1 == clsidSLTPARTITIONROLES )
        v13 = a1[1] - 0x54DDB8023319A984LL;
      if ( v13 )
      {
        v9 = -2147221231;
        v15 = *a1 - clsidSLTPARTITIONROLEMEMBERS;
        if ( *a1 == clsidSLTPARTITIONROLEMEMBERS )
          v15 = a1[1] - 0x3B140EBC21A67CA3LL;
        if ( v15 )
          return v9;
        v16 = CoTaskMemAlloc(0x90u);
        v8 = v16;
        if ( !v16 )
          return 2147942414LL;
        v16[4] = 0;
        *((_DWORD *)v16 + 10) = 0;
        v16[6] = 0;
        v16[7] = 0;
        *v16 = &CLTPartitionRoleMembers::`vftable'{for `IClassFactory'};
        v16[1] = &CLTPartitionRoleMembers::`vftable'{for `ISimpleTableWrite'};
        v16[2] = &CLTPartitionRoleMembers::`vftable'{for `ISimpleLogicTableDispenser'};
        v16[3] = &CLTPartitionBase::`vftable'{for `ISimpleTableControl'};
        v16[10] = 0;
        v16[11] = 0;
        *((GUID *)v16 + 4) = GUID_NULL;
        v12 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CLTPartitionRoleMembers::`vftable'{for `IClassFactory'})(
                v16,
                a2,
                a3);
      }
      else
      {
        v14 = CoTaskMemAlloc(0x58u);
        v8 = v14;
        if ( !v14 )
          return 2147942414LL;
        v14[4] = 0;
        *((_DWORD *)v14 + 10) = 0;
        v14[6] = 0;
        v14[7] = 0;
        *v14 = &CLTPartitionRoles::`vftable'{for `IClassFactory'};
        v14[1] = &CLTPartitionRoles::`vftable'{for `ISimpleTableWrite'};
        v14[2] = &CLTPartitionRoles::`vftable'{for `ISimpleLogicTableDispenser'};
        v14[3] = &CLTPartitionBase::`vftable'{for `ISimpleTableControl'};
        v14[10] = 0;
        *((GUID *)v14 + 4) = GUID_NULL;
        v12 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CLTPartitionRoles::`vftable'{for `IClassFactory'})(
                v14,
                a2,
                a3);
      }
    }
    else
    {
      v11 = CoTaskMemAlloc(0x60u);
      v8 = v11;
      if ( !v11 )
        return 2147942414LL;
      v11[4] = 0;
      *v11 = &CLTPartitionUsers::`vftable'{for `IClassFactory'};
      v11[1] = &CLTPartitionUsers::`vftable'{for `ISimpleTableWrite'};
      v11[2] = &CLTPartitionUsers::`vftable'{for `ISimpleTableControl'};
      v11[3] = &CLTPartitionUsers::`vftable'{for `ISimpleLogicTableDispenser'};
      *((_DWORD *)v11 + 10) = 0;
      v11[6] = 0;
      v11[10] = 0;
      v11[11] = 0;
      v12 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CLTPartitionUsers::`vftable'{for `IClassFactory'})(
              v11,
              a2,
              a3);
    }
    v9 = v12;
    if ( v12 < 0 )
    {
LABEL_20:
      (*(void (__fastcall **)(_QWORD *, __int64))(*v8 + 40LL))(v8, 1);
      *a3 = 0;
    }
    return v9;
  }
  v7 = CoTaskMemAlloc(0x40u);
  v8 = v7;
  if ( v7 )
  {
    v7[4] = 0;
    *((_DWORD *)v7 + 10) = 0;
    v7[6] = 0;
    v7[7] = 0;
    *v7 = &CLTPartition::`vftable'{for `IClassFactory'};
    v7[1] = &CLTPartition::`vftable'{for `ISimpleTableWrite'};
    v7[2] = &CLTPartition::`vftable'{for `ISimpleLogicTableDispenser'};
    v7[3] = &CLTPartitionBase::`vftable'{for `ISimpleTableControl'};
    v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))v7[1])(v7 + 1, a2, a3);
    if ( (v9 & 0x80000000) != 0 )
      goto LABEL_20;
    return v9;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180002890  push    rbx
0x180002892  push    rdi
0x180002893  sub     rsp, 28h
0x180002897  mov     rbx, r8
0x18000289a  mov     rdi, rdx
0x18000289d  test    r8, r8
0x1800028a0  jnz     short loc_1800028AE
0x1800028a2  mov     eax, 80070057h
0x1800028a7  add     rsp, 28h
0x1800028ab  pop     rdi
0x1800028ac  pop     rbx
0x1800028ad  retn
0x1800028ae  mov     [rsp+38h+var_18], r14
0x1800028b3  xor     r14d, r14d
0x1800028b6  mov     [r8], r14
0x1800028b9  mov     rax, [rcx]
0x1800028bc  sub     rax, cs:clsidSLTPART
0x1800028c3  jnz     short loc_1800028D0
0x1800028c5  mov     rax, [rcx+8]
0x1800028c9  sub     rax, cs:qword_180060AB0
0x1800028d0  mov     [rsp+38h+arg_0], rbp
0x1800028d5  mov     [rsp+38h+arg_8], rsi
0x1800028da  test    rax, rax
0x1800028dd  jnz     loc_18000296B
0x1800028e3  mov     ecx, 40h ; '@'; cb
0x1800028e8  call    cs:__imp_CoTaskMemAlloc
0x1800028ee  mov     [rsp+38h+arg_10], rax
0x1800028f3  mov     rsi, rax
0x1800028f6  test    rax, rax
0x1800028f9  jz      loc_180002B51
0x1800028ff  lea     rcx, [rax+8]
0x180002903  mov     [rax+20h], r14
0x180002907  mov     [rax+28h], r14d
0x18000290b  test    rsi, rsi
0x18000290e  mov     [rax+30h], r14
0x180002912  mov     r8, rbx
0x180002915  mov     [rax+38h], r14
0x180002919  mov     rdx, rdi
0x18000291c  lea     rax, ??_7CLTPartition@@6BIClassFactory@@@; const CLTPartition::`vftable'{for `IClassFactory'}
0x180002923  mov     [rsi], rax
0x180002926  lea     rax, ??_7CLTPartition@@6BISimpleTableWrite@@@; const CLTPartition::`vftable'{for `ISimpleTableWrite'}
0x18000292d  mov     [rcx], rax
0x180002930  lea     rax, ??_7CLTPartition@@6BISimpleLogicTableDispenser@@@; const CLTPartition::`vftable'{for `ISimpleLogicTableDispenser'}
0x180002937  mov     [rsi+10h], rax
0x18000293b  cmovz   rcx, r14
0x18000293f  lea     rax, ??_7CLTPartitionBase@@6BISimpleTableControl@@@; const CLTPartitionBase::`vftable'{for `ISimpleTableControl'}
0x180002946  mov     [rsi+18h], rax
0x18000294a  mov     rax, [rcx]
0x18000294d  mov     rax, [rax]
0x180002950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002955  mov     ebp, eax
0x180002957  test    eax, eax
0x180002959  jns     loc_180002AA6
0x18000295f  mov     rcx, [rsi]
0x180002962  mov     rax, [rcx+28h]
0x180002966  jmp     loc_180002A96
0x18000296b  mov     rax, [rcx]
0x18000296e  sub     rax, cs:clsidSLTPartitionUsers
0x180002975  jnz     short loc_180002982
0x180002977  mov     rax, [rcx+8]
0x18000297b  sub     rax, cs:qword_180060AC0
0x180002982  test    rax, rax
0x180002985  jnz     short loc_1800029EE
0x180002987  mov     ecx, 60h ; '`'; cb
0x18000298c  call    cs:__imp_CoTaskMemAlloc
0x180002992  mov     [rsp+38h+arg_10], rax
0x180002997  mov     rsi, rax
0x18000299a  test    rax, rax
0x18000299d  jz      loc_180002B51
0x1800029a3  lea     rax, ??_7CLTPartitionUsers@@6BIClassFactory@@@; const CLTPartitionUsers::`vftable'{for `IClassFactory'}
0x1800029aa  mov     [rsi+20h], r14
0x1800029ae  mov     [rsi], rax
0x1800029b1  lea     rax, ??_7CLTPartitionUsers@@6BISimpleTableWrite@@@; const CLTPartitionUsers::`vftable'{for `ISimpleTableWrite'}
0x1800029b8  mov     [rsi+8], rax
0x1800029bc  lea     rax, ??_7CLTPartitionUsers@@6BISimpleTableControl@@@; const CLTPartitionUsers::`vftable'{for `ISimpleTableControl'}
0x1800029c3  mov     [rsi+10h], rax
0x1800029c7  lea     rax, ??_7CLTPartitionUsers@@6BISimpleLogicTableDispenser@@@; const CLTPartitionUsers::`vftable'{for `ISimpleLogicTableDispenser'}
0x1800029ce  mov     [rsi+18h], rax
0x1800029d2  mov     [rsi+28h], r14d
0x1800029d6  mov     [rsi+30h], r14
0x1800029da  mov     [rsi+50h], r14
0x1800029de  mov     [rsi+58h], r14
0x1800029e2  mov     rax, cs:??_7CLTPartitionUsers@@6BIClassFactory@@@; const CLTPartitionUsers::`vftable'{for `IClassFactory'}
0x1800029e9  jmp     loc_180002A7B
0x1800029ee  mov     rax, [rcx]
0x1800029f1  sub     rax, cs:clsidSLTPARTITIONROLES
0x1800029f8  jnz     short loc_180002A05
0x1800029fa  mov     rax, [rcx+8]
0x1800029fe  sub     rax, cs:qword_180060AD0
0x180002a05  test    rax, rax
0x180002a08  jnz     loc_180002ABE
0x180002a0e  mov     ecx, 58h ; 'X'; cb
0x180002a13  call    cs:__imp_CoTaskMemAlloc
0x180002a19  mov     [rsp+38h+arg_10], rax
0x180002a1e  mov     rsi, rax
0x180002a21  test    rax, rax
0x180002a24  jz      loc_180002B51
0x180002a2a  mov     [rax+20h], r14
0x180002a2e  mov     [rax+28h], r14d
0x180002a32  mov     [rax+30h], r14
0x180002a36  mov     [rax+38h], r14
0x180002a3a  lea     rax, ??_7CLTPartitionRoles@@6BIClassFactory@@@; const CLTPartitionRoles::`vftable'{for `IClassFactory'}
0x180002a41  mov     [rsi], rax
0x180002a44  lea     rax, ??_7CLTPartitionRoles@@6BISimpleTableWrite@@@; const CLTPartitionRoles::`vftable'{for `ISimpleTableWrite'}
0x180002a4b  mov     [rsi+8], rax
0x180002a4f  lea     rax, ??_7CLTPartitionRoles@@6BISimpleLogicTableDispenser@@@; const CLTPartitionRoles::`vftable'{for `ISimpleLogicTableDispenser'}
0x180002a56  mov     [rsi+10h], rax
0x180002a5a  lea     rax, ??_7CLTPartitionBase@@6BISimpleTableControl@@@; const CLTPartitionBase::`vftable'{for `ISimpleTableControl'}
0x180002a61  mov     [rsi+18h], rax
0x180002a65  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180002a6c  mov     [rsi+50h], r14
0x180002a70  movups  xmmword ptr [rsi+40h], xmm0
0x180002a74  mov     rax, cs:??_7CLTPartitionRoles@@6BIClassFactory@@@; const CLTPartitionRoles::`vftable'{for `IClassFactory'}
0x180002a7b  mov     r8, rbx
0x180002a7e  mov     rdx, rdi
0x180002a81  mov     rcx, rsi
0x180002a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a89  mov     ebp, eax
0x180002a8b  test    eax, eax
0x180002a8d  jns     short loc_180002AA6
0x180002a8f  mov     rax, [rsi]
0x180002a92  mov     rax, [rax+28h]
0x180002a96  mov     rcx, rsi
0x180002a99  mov     edx, 1
0x180002a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa3  mov     [rbx], r14
0x180002aa6  mov     eax, ebp
0x180002aa8  mov     rsi, [rsp+38h+arg_8]
0x180002aad  mov     rbp, [rsp+38h+arg_0]
0x180002ab2  mov     r14, [rsp+38h+var_18]
0x180002ab7  add     rsp, 28h
0x180002abb  pop     rdi
0x180002abc  pop     rbx
0x180002abd  retn
0x180002abe  mov     rax, [rcx]
0x180002ac1  mov     ebp, 80040111h
0x180002ac6  sub     rax, cs:clsidSLTPARTITIONROLEMEMBERS
0x180002acd  jnz     short loc_180002ADA
0x180002acf  mov     rax, [rcx+8]
0x180002ad3  sub     rax, cs:qword_180060AE0
0x180002ada  test    rax, rax
0x180002add  jnz     short loc_180002AA6
0x180002adf  mov     ecx, 90h; cb
0x180002ae4  call    cs:__imp_CoTaskMemAlloc
0x180002aea  mov     [rsp+38h+arg_10], rax
0x180002aef  mov     rsi, rax
0x180002af2  test    rax, rax
0x180002af5  jz      short loc_180002B51
0x180002af7  mov     [rax+20h], r14
0x180002afb  mov     [rax+28h], r14d
0x180002aff  mov     [rax+30h], r14
0x180002b03  mov     [rax+38h], r14
0x180002b07  lea     rax, ??_7CLTPartitionRoleMembers@@6BIClassFactory@@@; const CLTPartitionRoleMembers::`vftable'{for `IClassFactory'}
0x180002b0e  mov     [rsi], rax
0x180002b11  lea     rax, ??_7CLTPartitionRoleMembers@@6BISimpleTableWrite@@@; const CLTPartitionRoleMembers::`vftable'{for `ISimpleTableWrite'}
0x180002b18  mov     [rsi+8], rax
0x180002b1c  lea     rax, ??_7CLTPartitionRoleMembers@@6BISimpleLogicTableDispenser@@@; const CLTPartitionRoleMembers::`vftable'{for `ISimpleLogicTableDispenser'}
0x180002b23  mov     [rsi+10h], rax
0x180002b27  lea     rax, ??_7CLTPartitionBase@@6BISimpleTableControl@@@; const CLTPartitionBase::`vftable'{for `ISimpleTableControl'}
0x180002b2e  mov     [rsi+18h], rax
0x180002b32  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180002b39  mov     [rsi+50h], r14
0x180002b3d  mov     [rsi+58h], r14
0x180002b41  movups  xmmword ptr [rsi+40h], xmm0
0x180002b45  mov     rax, cs:??_7CLTPartitionRoleMembers@@6BIClassFactory@@@; const CLTPartitionRoleMembers::`vftable'{for `IClassFactory'}
0x180002b4c  jmp     loc_180002A7B
0x180002b51  mov     eax, 8007000Eh
0x180002b56  jmp     loc_180002AA8
```
