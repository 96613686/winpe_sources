# CAppImport::CreateInstallList(_GUID,ushort *,_GUID * *,ulong *,_GUID * *,ulong *,__MIDL___MIDL_itf_registrar_0000_0000_0001 *)

- ea: `0x18003b308`
- end: `0x18003b736`
- name: `?CreateInstallList@CAppImport@@AEAAJU_GUID@@PEAGPEAPEAU2@PEAK23PEAW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z`
- size: `1070`
- prototype: `__int64 __fastcall(CAppImport *this, struct _GUID *, unsigned __int16 *, LPVOID *, unsigned int *, struct _GUID **, unsigned int *, enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003caa0`

## callees

- `0x18001a6c8`
- `0x18003b308`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18003b3b3`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003b3b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b4da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b4f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b4da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b4f9`

## pseudocode

```c
__int64 __fastcall CAppImport::CreateInstallList(
        CAppImport *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        LPVOID *a4,
        unsigned int *a5,
        struct _GUID **a6,
        unsigned int *a7,
        enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *a8)
{
  int v10; // r13d
  int v11; // eax
  signed __int64 v12; // r9
  __int64 v13; // r10
  int SimpleTableDispenser; // ebx
  int v15; // eax
  bool v16; // sf
  unsigned int i; // edi
  int v18; // eax
  SIZE_T v19; // rax
  struct _GUID *v20; // rax
  int v21; // eax
  signed __int64 v23; // [rsp+50h] [rbp-69h] BYREF
  signed __int64 v24; // [rsp+58h] [rbp-61h] BYREF
  int v25; // [rsp+60h] [rbp-59h] BYREF
  struct _GUID *v26; // [rsp+68h] [rbp-51h] BYREF
  _DWORD *v27; // [rsp+70h] [rbp-49h] BYREF
  _DWORD *v28; // [rsp+78h] [rbp-41h] BYREF
  int *v29; // [rsp+80h] [rbp-39h] BYREF
  enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *v30; // [rsp+88h] [rbp-31h]
  unsigned __int16 *v31; // [rsp+90h] [rbp-29h] BYREF
  int v32; // [rsp+98h] [rbp-21h]
  int v33; // [rsp+9Ch] [rbp-1Dh]
  int v34; // [rsp+A0h] [rbp-19h]
  int v35; // [rsp+A4h] [rbp-15h]
  __int64 v36; // [rsp+A8h] [rbp-11h]
  int v37; // [rsp+B0h] [rbp-9h]
  int v38; // [rsp+B4h] [rbp-5h]
  int v39; // [rsp+B8h] [rbp-1h]
  int v40; // [rsp+BCh] [rbp+3h]

  *a4 = 0;
  *a6 = 0;
  v10 = 3;
  *a5 = 0;
  *a7 = 0;
  v30 = a8;
  v31 = a3;
  v32 = 0;
  v33 = -268435455;
  v34 = 130;
  v11 = safe_lstrlenW(a3);
  v36 = v13;
  v37 = v12;
  v38 = 9;
  v39 = 72;
  v35 = 2 * v11 + 2;
  v40 = 16;
  v23 = v12;
  if ( *((_QWORD *)this + 9) == v12 )
  {
    v24 = v12;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v24);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_6;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, v24, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v15 = memcmp_0(tidCOMSERVICES_CLASSES_EXPORT, &TID_APPLICATION, 0x10u);
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, signed __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                           *((_QWORD *)this + 9),
                           didCOMSERVICES,
                           tidCOMSERVICES_CLASSES_EXPORT,
                           &v31,
                           2,
                           1,
                           v15 != 0 ? 7 : 5,
                           &v23);
LABEL_6:
  v16 = SimpleTableDispenser < 0;
  if ( SimpleTableDispenser )
    goto LABEL_40;
  if ( !v23 )
  {
LABEL_8:
    SimpleTableDispenser = -2147024882;
LABEL_41:
    if ( *a4 )
    {
      CoTaskMemFree(*a4);
      *a4 = 0;
    }
    if ( *a6 )
    {
      CoTaskMemFree(*a6);
      *a6 = 0;
    }
    goto LABEL_45;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(signed __int64))(*(_QWORD *)v23 + 24LL))(v23);
  if ( SimpleTableDispenser )
    goto LABEL_39;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(signed __int64))(*(_QWORD *)v23 + 32LL))(v23);
  if ( SimpleTableDispenser )
    goto LABEL_39;
  for ( i = 0; ; ++i )
  {
    v18 = (*(__int64 (__fastcall **)(signed __int64))(*(_QWORD *)v23 + 40LL))(v23);
    SimpleTableDispenser = v18;
    if ( v18 == -2146367487 )
      break;
    if ( v18 )
      goto LABEL_39;
  }
  if ( !i )
  {
    SimpleTableDispenser = 0;
    goto LABEL_45;
  }
  v19 = 16LL * i;
  if ( !is_mul_ok(i, 0x10u) )
    v19 = -1;
  *a4 = CoTaskMemAlloc(v19);
  v20 = (struct _GUID *)CoTaskMemAlloc(saturated_mul(i, 0x10u));
  *a6 = v20;
  if ( !*a4 || !v20 )
    goto LABEL_8;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(signed __int64))(*(_QWORD *)v23 + 32LL))(v23);
  if ( SimpleTableDispenser )
  {
LABEL_39:
    v16 = SimpleTableDispenser < 0;
LABEL_40:
    if ( !v16 )
      goto LABEL_45;
    goto LABEL_41;
  }
  while ( 1 )
  {
    LODWORD(v24) = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v21 = (*(__int64 (__fastcall **)(signed __int64))(*(_QWORD *)v23 + 40LL))(v23);
    SimpleTableDispenser = v21;
    if ( v21 == -2146367487 )
      break;
    if ( v21 )
      goto LABEL_39;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(signed __int64, _QWORD, signed __int64 *, int *, struct _GUID **))(*(_QWORD *)v23 + 64LL))(
                             v23,
                             0,
                             &v24,
                             &v25,
                             &v26);
    if ( SimpleTableDispenser )
      goto LABEL_39;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(signed __int64, __int64, signed __int64 *, int *, _DWORD **))(*(_QWORD *)v23 + 64LL))(
                             v23,
                             30,
                             &v24,
                             &v25,
                             &v27);
    if ( SimpleTableDispenser )
      goto LABEL_39;
    if ( v27 && (*v27 & 0x1000) != 0 )
    {
      SimpleTableDispenser = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD, _QWORD, _DWORD **))(*(_QWORD *)v23 + 64LL))(
                               v23,
                               (unsigned int)(SimpleTableDispenser + 43),
                               0,
                               0,
                               &v28);
      if ( SimpleTableDispenser )
        goto LABEL_39;
      if ( *v28 )
      {
        if ( i <= *a7 )
          goto LABEL_35;
        (*a6)[(*a7)++] = *v26;
      }
      else
      {
        if ( i <= *a5 )
        {
LABEL_35:
          SimpleTableDispenser = -2147024809;
          goto LABEL_41;
        }
        *((struct _GUID *)*a4 + (*a5)++) = *v26;
        if ( v10 == 3 )
        {
          v29 = 0;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(signed __int64, __int64, _QWORD, _QWORD, int **))(*(_QWORD *)v23 + 64LL))(
                                   v23,
                                   8,
                                   0,
                                   0,
                                   &v29);
          if ( SimpleTableDispenser )
            goto LABEL_39;
          v10 = *v29;
        }
      }
    }
  }
  SimpleTableDispenser = 0;
  if ( !*a5 )
  {
    *(GUID *)*a4 = GUID_NULL;
    ++*a5;
  }
LABEL_45:
  if ( v23 )
    (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v23 + 16LL))(v23);
  *(_DWORD *)v30 = v10;
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18003b308  mov     [rsp-8+arg_8], rbx
0x18003b30d  push    rbp
0x18003b30e  push    rsi
0x18003b30f  push    rdi
0x18003b310  push    r12
0x18003b312  push    r13
0x18003b314  push    r14
0x18003b316  push    r15
0x18003b318  lea     rbp, [rsp-7]
0x18003b31d  sub     rsp, 0C0h
0x18003b324  mov     rax, [rbp+37h+arg_38]
0x18003b328  mov     r14, r9
0x18003b32b  mov     r15, [rbp+37h+arg_28]
0x18003b32f  xor     r9d, r9d
0x18003b332  mov     rsi, [rbp+37h+arg_20]
0x18003b336  mov     rdi, rcx
0x18003b339  mov     r12, [rbp+37h+arg_30]
0x18003b33d  mov     rcx, r8; unsigned __int16 *
0x18003b340  mov     [r14], r9
0x18003b343  mov     r10, rdx
0x18003b346  mov     [r15], r9
0x18003b349  lea     r13d, [r9+3]
0x18003b34d  mov     [rsi], r9d
0x18003b350  mov     [r12], r9d
0x18003b354  mov     [rbp+37h+var_68], rax
0x18003b358  mov     [rbp+37h+var_60], r8
0x18003b35c  mov     [rbp+37h+var_58], r9d
0x18003b360  mov     [rbp+37h+var_54], 0F0000001h
0x18003b367  mov     [rbp+37h+var_50], 82h
0x18003b36e  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003b373  mov     [rbp+37h+var_48], r10
0x18003b377  mov     [rbp+37h+var_40], r9d
0x18003b37b  mov     [rbp+37h+var_3C], 9
0x18003b382  lea     eax, ds:2[rax*2]
0x18003b389  mov     [rbp+37h+var_38], 48h ; 'H'
0x18003b390  mov     [rbp+37h+var_4C], eax
0x18003b393  mov     [rbp+37h+var_34], 10h
0x18003b39a  mov     [rbp+37h+var_A0], r9
0x18003b39e  cmp     [rdi+48h], r9
0x18003b3a2  jnz     short loc_18003B3E1
0x18003b3a4  lea     rdx, [rbp+37h+var_98]
0x18003b3a8  mov     [rbp+37h+var_98], r9
0x18003b3ac  lea     rcx, IID_ISimpleTableDispenser
0x18003b3b3  call    cs:__imp_GetSimpleTableDispenser
0x18003b3b9  mov     ebx, eax
0x18003b3bb  test    eax, eax
0x18003b3bd  js      loc_18003B446
0x18003b3c3  mov     rcx, [rbp+37h+var_98]
0x18003b3c7  xor     eax, eax
0x18003b3c9  lock cmpxchg [rdi+48h], rcx
0x18003b3cf  jz      short loc_18003B3E1
0x18003b3d1  mov     rcx, [rbp+37h+var_98]
0x18003b3d5  mov     rax, [rcx]
0x18003b3d8  mov     rax, [rax+10h]
0x18003b3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3e1  mov     r8d, 10h; Size
0x18003b3e7  lea     rdx, TID_APPLICATION; Buf2
0x18003b3ee  lea     rcx, tidCOMSERVICES_CLASSES_EXPORT; Buf1
0x18003b3f5  call    memcmp_0
0x18003b3fa  mov     rcx, [rdi+48h]
0x18003b3fe  lea     r9, [rbp+37h+var_A0]
0x18003b402  mov     [rsp+0F0h+var_B8], r9
0x18003b407  lea     r8, tidCOMSERVICES_CLASSES_EXPORT
0x18003b40e  neg     eax
0x18003b410  lea     r9, [rbp+37h+var_60]
0x18003b414  mov     rax, [rcx]
0x18003b417  sbb     edx, edx
0x18003b419  and     edx, 2
0x18003b41c  add     edx, 5
0x18003b41f  mov     [rsp+0F0h+var_C0], edx
0x18003b423  lea     rdx, didCOMSERVICES
0x18003b42a  mov     rax, [rax+18h]
0x18003b42e  mov     [rsp+0F0h+var_C8], 1
0x18003b436  mov     [rsp+0F0h+var_D0], 2
0x18003b43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b444  mov     ebx, eax
0x18003b446  test    ebx, ebx
0x18003b448  jnz     loc_18003B6D1
0x18003b44e  cmp     [rbp+37h+var_A0], 0
0x18003b453  jnz     short loc_18003B45F
0x18003b455  mov     ebx, 8007000Eh
0x18003b45a  jmp     loc_18003B6D3
0x18003b45f  mov     rcx, [rbp+37h+var_A0]
0x18003b463  mov     rax, [rcx]
0x18003b466  mov     rax, [rax+18h]
0x18003b46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b46f  mov     ebx, eax
0x18003b471  test    eax, eax
0x18003b473  jnz     loc_18003B6CF
0x18003b479  mov     rcx, [rbp+37h+var_A0]
0x18003b47d  mov     rax, [rcx]
0x18003b480  mov     rax, [rax+20h]
0x18003b484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b489  mov     ebx, eax
0x18003b48b  test    eax, eax
0x18003b48d  jnz     loc_18003B6CF
0x18003b493  xor     edi, edi
0x18003b495  mov     rcx, [rbp+37h+var_A0]
0x18003b499  mov     rax, [rcx]
0x18003b49c  mov     rax, [rax+28h]
0x18003b4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4a5  mov     ebx, eax
0x18003b4a7  cmp     eax, 80110801h
0x18003b4ac  jz      short loc_18003B4BA
0x18003b4ae  test    eax, eax
0x18003b4b0  jnz     loc_18003B6CF
0x18003b4b6  inc     edi
0x18003b4b8  jmp     short loc_18003B495
0x18003b4ba  test    edi, edi
0x18003b4bc  jz      loc_18003B6CB
0x18003b4c2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003b4c9  mov     ebx, edi
0x18003b4cb  mov     eax, 10h
0x18003b4d0  mul     rbx
0x18003b4d3  cmovb   rax, rcx
0x18003b4d7  mov     rcx, rax; cb
0x18003b4da  call    cs:__imp_CoTaskMemAlloc
0x18003b4e0  mov     [r14], rax
0x18003b4e3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003b4ea  mov     eax, 10h
0x18003b4ef  mul     rbx
0x18003b4f2  cmovb   rax, rcx
0x18003b4f6  mov     rcx, rax; cb
0x18003b4f9  call    cs:__imp_CoTaskMemAlloc
0x18003b4ff  mov     [r15], rax
0x18003b502  cmp     qword ptr [r14], 0
0x18003b506  jz      loc_18003B455
0x18003b50c  test    rax, rax
0x18003b50f  jz      loc_18003B455
0x18003b515  mov     rcx, [rbp+37h+var_A0]
0x18003b519  mov     rax, [rcx]
0x18003b51c  mov     rax, [rax+20h]
0x18003b520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b525  mov     ebx, eax
0x18003b527  test    eax, eax
0x18003b529  jnz     loc_18003B6CF
0x18003b52f  mov     rcx, [rbp+37h+var_A0]
0x18003b533  mov     dword ptr [rbp+37h+var_98], 0
0x18003b53a  mov     [rbp+37h+var_90], 0
0x18003b541  mov     [rbp+37h+var_88], 0
0x18003b549  mov     [rbp+37h+var_80], 0
0x18003b551  mov     [rbp+37h+var_78], 0
0x18003b559  mov     rax, [rcx]
0x18003b55c  mov     rax, [rax+28h]
0x18003b560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b565  mov     ebx, eax
0x18003b567  cmp     eax, 80110801h
0x18003b56c  jz      loc_18003B6B3
0x18003b572  test    eax, eax
0x18003b574  jnz     loc_18003B6CF
0x18003b57a  mov     rcx, [rbp+37h+var_A0]
0x18003b57e  lea     rdx, [rbp+37h+var_88]
0x18003b582  mov     [rsp+0F0h+var_D0], rdx
0x18003b587  lea     r9, [rbp+37h+var_90]
0x18003b58b  lea     r8, [rbp+37h+var_98]
0x18003b58f  xor     edx, edx
0x18003b591  mov     rax, [rcx]
0x18003b594  mov     rax, [rax+40h]
0x18003b598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b59d  mov     ebx, eax
0x18003b59f  test    eax, eax
0x18003b5a1  jnz     loc_18003B6CF
0x18003b5a7  mov     rcx, [rbp+37h+var_A0]
0x18003b5ab  lea     rdx, [rbp+37h+var_80]
0x18003b5af  mov     [rsp+0F0h+var_D0], rdx
0x18003b5b4  lea     r9, [rbp+37h+var_90]
0x18003b5b8  lea     r8, [rbp+37h+var_98]
0x18003b5bc  lea     edx, [rbx+1Eh]
0x18003b5bf  mov     rax, [rcx]
0x18003b5c2  mov     rax, [rax+40h]
0x18003b5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5cb  mov     ebx, eax
0x18003b5cd  test    eax, eax
0x18003b5cf  jnz     loc_18003B6CF
0x18003b5d5  mov     rax, [rbp+37h+var_80]
0x18003b5d9  test    rax, rax
0x18003b5dc  jz      loc_18003B52F
0x18003b5e2  test    dword ptr [rax], 1000h
0x18003b5e8  jz      loc_18003B52F
0x18003b5ee  mov     rcx, [rbp+37h+var_A0]
0x18003b5f2  lea     rdx, [rbp+37h+var_78]
0x18003b5f6  mov     [rsp+0F0h+var_D0], rdx
0x18003b5fb  xor     r9d, r9d
0x18003b5fe  xor     r8d, r8d
0x18003b601  lea     edx, [rbx+2Bh]
0x18003b604  mov     rax, [rcx]
0x18003b607  mov     rax, [rax+40h]
0x18003b60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b610  mov     ebx, eax
0x18003b612  test    eax, eax
0x18003b614  jnz     loc_18003B6CF
0x18003b61a  mov     rax, [rbp+37h+var_78]
0x18003b61e  cmp     [rax], ebx
0x18003b620  jz      short loc_18003B64B
0x18003b622  cmp     edi, [r12]
0x18003b626  jbe     loc_18003B6AC
0x18003b62c  mov     edx, [r12]
0x18003b630  mov     rax, [rbp+37h+var_88]
0x18003b634  add     rdx, rdx
0x18003b637  mov     rcx, [r15]
0x18003b63a  movups  xmm0, xmmword ptr [rax]
0x18003b63d  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x18003b642  inc     dword ptr [r12]
0x18003b646  jmp     loc_18003B52F
0x18003b64b  cmp     edi, [rsi]
0x18003b64d  jbe     short loc_18003B6AC
0x18003b64f  mov     edx, [rsi]
0x18003b651  mov     rax, [rbp+37h+var_88]
0x18003b655  add     rdx, rdx
0x18003b658  mov     rcx, [r14]
0x18003b65b  movups  xmm0, xmmword ptr [rax]
0x18003b65e  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x18003b663  inc     dword ptr [rsi]
0x18003b665  cmp     r13d, 3
0x18003b669  jnz     loc_18003B52F
0x18003b66f  mov     rcx, [rbp+37h+var_A0]
0x18003b673  lea     rdx, [rbp+37h+var_70]
0x18003b677  mov     [rbp+37h+var_70], 0
0x18003b67f  xor     r9d, r9d
0x18003b682  mov     [rsp+0F0h+var_D0], rdx
0x18003b687  xor     r8d, r8d
0x18003b68a  lea     edx, [r13+5]
0x18003b68e  mov     rax, [rcx]
0x18003b691  mov     rax, [rax+40h]
0x18003b695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b69a  mov     ebx, eax
0x18003b69c  test    eax, eax
0x18003b69e  jnz     short loc_18003B6CF
0x18003b6a0  mov     rax, [rbp+37h+var_70]
0x18003b6a4  mov     r13d, [rax]
0x18003b6a7  jmp     loc_18003B52F
0x18003b6ac  mov     ebx, 80070057h
0x18003b6b1  jmp     short loc_18003B6D3
0x18003b6b3  xor     ebx, ebx
0x18003b6b5  cmp     [rsi], ebx
0x18003b6b7  jnz     short loc_18003B6FD
0x18003b6b9  mov     rax, [r14]
0x18003b6bc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003b6c3  movdqu  xmmword ptr [rax], xmm0
0x18003b6c7  inc     dword ptr [rsi]
0x18003b6c9  jmp     short loc_18003B6FD
0x18003b6cb  xor     ebx, ebx
0x18003b6cd  jmp     short loc_18003B6FD
0x18003b6cf  test    ebx, ebx
0x18003b6d1  jns     short loc_18003B6FD
0x18003b6d3  mov     rcx, [r14]; pv
0x18003b6d6  test    rcx, rcx
0x18003b6d9  jz      short loc_18003B6E8
0x18003b6db  call    cs:__imp_CoTaskMemFree
0x18003b6e1  mov     qword ptr [r14], 0
0x18003b6e8  mov     rcx, [r15]; pv
0x18003b6eb  test    rcx, rcx
0x18003b6ee  jz      short loc_18003B6FD
0x18003b6f0  call    cs:__imp_CoTaskMemFree
0x18003b6f6  mov     qword ptr [r15], 0
0x18003b6fd  mov     rcx, [rbp+37h+var_A0]
0x18003b701  test    rcx, rcx
0x18003b704  jz      short loc_18003B712
0x18003b706  mov     rax, [rcx]
0x18003b709  mov     rax, [rax+10h]
0x18003b70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b712  mov     rax, [rbp+37h+var_68]
0x18003b716  mov     [rax], r13d
0x18003b719  mov     eax, ebx
0x18003b71b  mov     rbx, [rsp+0F0h+arg_8]
0x18003b723  add     rsp, 0C0h
0x18003b72a  pop     r15
0x18003b72c  pop     r14
0x18003b72e  pop     r13
0x18003b730  pop     r12
0x18003b732  pop     rdi
0x18003b733  pop     rsi
0x18003b734  pop     rbp
0x18003b735  retn
```
