# CAppImport::QueryPartitionInfo(ushort const *,ushort * *,ushort * *,_GUID *)

- ea: `0x180044390`
- end: `0x180044648`
- name: `?QueryPartitionInfo@CAppImport@@AEAAJPEBGPEAPEAG1PEAU_GUID@@@Z`
- size: `696`
- prototype: `int(CAppImport *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043b4c`

## callees

- `0x18000a01c`
- `0x18001a6c8`
- `0x180044390`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x180044412`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180044412`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800445f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004460d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800445f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004460d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800445cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800445cd`

## pseudocode

```c
__int64 __fastcall CAppImport::QueryPartitionInfo(
        CAppImport *this,
        const unsigned __int16 *a2,
        LPVOID *a3,
        LPVOID *a4,
        struct _GUID *a5)
{
  int v8; // eax
  bool v9; // zf
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  struct _GUID *v13; // r14
  __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  unsigned __int16 *v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int16 *v18; // rax
  struct _GUID *v20; // [rsp+50h] [rbp-20h] BYREF
  const unsigned __int16 *v21; // [rsp+58h] [rbp-18h] BYREF
  int v22; // [rsp+60h] [rbp-10h]
  int v23; // [rsp+64h] [rbp-Ch]
  int v24; // [rsp+68h] [rbp-8h]
  int v25; // [rsp+6Ch] [rbp-4h]
  __int64 v26; // [rsp+A8h] [rbp+38h] BYREF
  unsigned __int16 *v27; // [rsp+B0h] [rbp+40h]
  signed __int64 v28; // [rsp+B8h] [rbp+48h] BYREF

  *a4 = 0;
  v27 = 0;
  v20 = 0;
  *a3 = 0;
  v21 = a2;
  v22 = 0;
  v23 = -268435455;
  v24 = 130;
  v8 = safe_lstrlenW(a2);
  v9 = *((_QWORD *)this + 9) == 0;
  v26 = 0;
  v25 = 2 * v8 + 2;
  if ( v9 )
  {
    v28 = 0;
    if ( (int)GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v28) < 0 )
    {
LABEL_6:
      v11 = 0;
      goto LABEL_25;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, v28, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v10 = memcmp_0(tidCOMSERVICES_PARTITION_EXPORT, &TID_APPLICATION, 0x10u);
  if ( (*(int (__fastcall **)(_QWORD, __int64 *, __int64 *, const unsigned __int16 **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
         *((_QWORD *)this + 9),
         didCOMSERVICES,
         tidCOMSERVICES_PARTITION_EXPORT,
         &v21,
         1,
         1,
         v10 != 0 ? 1048583 : 1048581,
         &v26) < 0 )
    goto LABEL_6;
  if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v26 + 24LL))(v26) < 0 )
    goto LABEL_6;
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 40LL))(v26);
  v11 = v12;
  if ( v12 == -2146367487 )
    goto LABEL_6;
  v13 = a5;
  if ( v12 < 0 )
    goto LABEL_20;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, struct _GUID **))(*(_QWORD *)v26 + 64LL))(
          v26,
          0,
          0,
          0,
          &v20);
  if ( v11 < 0 )
    goto LABEL_20;
  v14 = v26;
  *v13 = *v20;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v14 + 64LL))(v14, 1, 0);
  if ( v11 < 0 )
    goto LABEL_20;
  if ( !v27 )
  {
LABEL_16:
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v26 + 64LL))(v26, 2, 0);
    if ( v11 < 0 )
      goto LABEL_20;
    if ( !v27 )
      goto LABEL_25;
    v17 = (int)(safe_lstrlenW(v27) + 1);
    v18 = (unsigned __int16 *)CoTaskMemAlloc(2 * v17);
    *a4 = v18;
    if ( v18 )
    {
      v11 = StringCchCopyW(v18, v17, v27);
      if ( v11 >= 0 )
        goto LABEL_25;
      goto LABEL_20;
    }
    goto LABEL_14;
  }
  v15 = (int)(safe_lstrlenW(v27) + 1);
  v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * v15);
  *a3 = v16;
  if ( v16 )
  {
    v11 = StringCchCopyW(v16, v15, v27);
    if ( v11 < 0 )
      goto LABEL_20;
    goto LABEL_16;
  }
LABEL_14:
  v11 = -2147024882;
LABEL_20:
  if ( *a3 )
  {
    CoTaskMemFree(*a3);
    *a3 = 0;
  }
  if ( *a4 )
  {
    CoTaskMemFree(*a4);
    *a4 = 0;
  }
  *v13 = GUID_NULL;
LABEL_25:
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180044390  push    rbp
0x180044392  push    rbx
0x180044393  push    rsi
0x180044394  push    rdi
0x180044395  push    r14
0x180044397  mov     rbp, rsp
0x18004439a  sub     rsp, 70h
0x18004439e  mov     qword ptr [r9], 0
0x1800443a5  mov     rbx, rcx
0x1800443a8  mov     rcx, rdx; unsigned __int16 *
0x1800443ab  mov     [rbp+arg_10], 0
0x1800443b3  mov     rdi, r9
0x1800443b6  mov     [rbp+var_20], 0
0x1800443be  mov     rsi, r8
0x1800443c1  mov     qword ptr [r8], 0
0x1800443c8  mov     [rbp+var_18], rdx
0x1800443cc  mov     [rbp+var_10], 0
0x1800443d3  mov     [rbp+var_C], 0F0000001h
0x1800443da  mov     [rbp+var_8], 82h
0x1800443e1  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800443e6  cmp     qword ptr [rbx+48h], 0
0x1800443eb  mov     [rbp+arg_8], 0
0x1800443f3  lea     eax, ds:2[rax*2]
0x1800443fa  mov     [rbp+var_4], eax
0x1800443fd  jnz     short loc_18004443E
0x1800443ff  lea     rdx, [rbp+arg_18]
0x180044403  mov     [rbp+arg_18], 0
0x18004440b  lea     rcx, IID_ISimpleTableDispenser
0x180044412  call    cs:__imp_GetSimpleTableDispenser
0x180044418  test    eax, eax
0x18004441a  js      loc_1800444A8
0x180044420  mov     rcx, [rbp+arg_18]
0x180044424  xor     eax, eax
0x180044426  lock cmpxchg [rbx+48h], rcx
0x18004442c  jz      short loc_18004443E
0x18004442e  mov     rcx, [rbp+arg_18]
0x180044432  mov     rax, [rcx]
0x180044435  mov     rax, [rax+10h]
0x180044439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004443e  mov     r8d, 10h; Size
0x180044444  lea     rdx, TID_APPLICATION; Buf2
0x18004444b  lea     rcx, tidCOMSERVICES_PARTITION_EXPORT; Buf1
0x180044452  call    memcmp_0
0x180044457  mov     rcx, [rbx+48h]
0x18004445b  lea     r9, [rbp+arg_8]
0x18004445f  mov     [rsp+70h+var_38], r9
0x180044464  lea     r8, tidCOMSERVICES_PARTITION_EXPORT
0x18004446b  neg     eax
0x18004446d  lea     r9, [rbp+var_18]
0x180044471  mov     rax, [rcx]
0x180044474  sbb     edx, edx
0x180044476  and     edx, 2
0x180044479  add     edx, 100005h
0x18004447f  mov     [rsp+70h+var_40], edx
0x180044483  lea     rdx, didCOMSERVICES
0x18004448a  mov     rax, [rax+18h]
0x18004448e  mov     [rsp+70h+var_48], 1
0x180044496  mov     [rsp+70h+var_50], 1
0x18004449f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444a4  test    eax, eax
0x1800444a6  jns     short loc_1800444AF
0x1800444a8  xor     ebx, ebx
0x1800444aa  jmp     loc_180044626
0x1800444af  mov     rcx, [rbp+arg_8]
0x1800444b3  mov     rax, [rcx]
0x1800444b6  mov     rax, [rax+18h]
0x1800444ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444bf  test    eax, eax
0x1800444c1  js      short loc_1800444A8
0x1800444c3  mov     rcx, [rbp+arg_8]
0x1800444c7  mov     rax, [rcx]
0x1800444ca  mov     rax, [rax+28h]
0x1800444ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444d3  mov     ebx, eax
0x1800444d5  cmp     eax, 80110801h
0x1800444da  jz      short loc_1800444A8
0x1800444dc  mov     r14, [rbp+arg_20]
0x1800444e0  test    eax, eax
0x1800444e2  js      loc_1800445F0
0x1800444e8  mov     rcx, [rbp+arg_8]
0x1800444ec  lea     rdx, [rbp+var_20]
0x1800444f0  mov     [rsp+70h+var_50], rdx
0x1800444f5  xor     r9d, r9d
0x1800444f8  xor     r8d, r8d
0x1800444fb  xor     edx, edx
0x1800444fd  mov     rax, [rcx]
0x180044500  mov     rax, [rax+40h]
0x180044504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044509  mov     ebx, eax
0x18004450b  test    eax, eax
0x18004450d  js      loc_1800445F0
0x180044513  mov     rax, [rbp+var_20]
0x180044517  lea     rdx, [rbp+arg_10]
0x18004451b  mov     rcx, [rbp+arg_8]
0x18004451f  xor     r9d, r9d
0x180044522  mov     [rsp+70h+var_50], rdx
0x180044527  xor     r8d, r8d
0x18004452a  movups  xmm0, xmmword ptr [rax]
0x18004452d  lea     edx, [r9+1]
0x180044531  movdqu  xmmword ptr [r14], xmm0
0x180044536  mov     rax, [rcx]
0x180044539  mov     rax, [rax+40h]
0x18004453d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044542  mov     ebx, eax
0x180044544  test    eax, eax
0x180044546  js      loc_1800445F0
0x18004454c  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x180044550  test    rcx, rcx
0x180044553  jz      short loc_18004458D
0x180044555  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004455a  inc     eax
0x18004455c  movsxd  rbx, eax
0x18004455f  lea     rcx, [rbx+rbx]; cb
0x180044563  call    cs:__imp_CoTaskMemAlloc
0x180044569  mov     [rsi], rax
0x18004456c  test    rax, rax
0x18004456f  jnz     short loc_180044578
0x180044571  mov     ebx, 8007000Eh
0x180044576  jmp     short loc_1800445F0
0x180044578  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x18004457c  mov     rdx, rbx; unsigned __int64
0x18004457f  mov     rcx, rax; unsigned __int16 *
0x180044582  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044587  mov     ebx, eax
0x180044589  test    eax, eax
0x18004458b  js      short loc_1800445F0
0x18004458d  mov     rcx, [rbp+arg_8]
0x180044591  lea     r8, [rbp+arg_10]
0x180044595  xor     r9d, r9d
0x180044598  mov     [rsp+70h+var_50], r8
0x18004459d  xor     r8d, r8d
0x1800445a0  mov     rax, [rcx]
0x1800445a3  lea     edx, [r9+2]
0x1800445a7  mov     rax, [rax+40h]
0x1800445ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445b0  mov     ebx, eax
0x1800445b2  test    eax, eax
0x1800445b4  js      short loc_1800445F0
0x1800445b6  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x1800445ba  test    rcx, rcx
0x1800445bd  jz      short loc_180044626
0x1800445bf  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800445c4  inc     eax
0x1800445c6  movsxd  rbx, eax
0x1800445c9  lea     rcx, [rbx+rbx]; cb
0x1800445cd  call    cs:__imp_CoTaskMemAlloc
0x1800445d3  mov     [rdi], rax
0x1800445d6  test    rax, rax
0x1800445d9  jz      short loc_180044571
0x1800445db  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x1800445df  mov     rdx, rbx; unsigned __int64
0x1800445e2  mov     rcx, rax; unsigned __int16 *
0x1800445e5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800445ea  mov     ebx, eax
0x1800445ec  test    eax, eax
0x1800445ee  jns     short loc_180044626
0x1800445f0  mov     rcx, [rsi]; pv
0x1800445f3  test    rcx, rcx
0x1800445f6  jz      short loc_180044605
0x1800445f8  call    cs:__imp_CoTaskMemFree
0x1800445fe  mov     qword ptr [rsi], 0
0x180044605  mov     rcx, [rdi]; pv
0x180044608  test    rcx, rcx
0x18004460b  jz      short loc_18004461A
0x18004460d  call    cs:__imp_CoTaskMemFree
0x180044613  mov     qword ptr [rdi], 0
0x18004461a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180044621  movdqu  xmmword ptr [r14], xmm0
0x180044626  mov     rcx, [rbp+arg_8]
0x18004462a  test    rcx, rcx
0x18004462d  jz      short loc_18004463B
0x18004462f  mov     rax, [rcx]
0x180044632  mov     rax, [rax+10h]
0x180044636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004463b  mov     eax, ebx
0x18004463d  add     rsp, 70h
0x180044641  pop     r14
0x180044643  pop     rdi
0x180044644  pop     rsi
0x180044645  pop     rbx
0x180044646  pop     rbp
0x180044647  retn
```
