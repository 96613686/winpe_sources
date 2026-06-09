# EfsxStreamRecreateKeyAgmtParams(_EFSX_DATUM_KEY_AGMT_DATA const *,_EFSX_DATUM_BLOB * *,_EFSX_DATUM_BLOB * *,void * *,uchar * *)

- ea: `0x18007f60c`
- end: `0x18007f974`
- name: `?EfsxStreamRecreateKeyAgmtParams@@YAKPEBU_EFSX_DATUM_KEY_AGMT_DATA@@PEAPEAU_EFSX_DATUM_BLOB@@1PEAPEAXPEAPEAE@Z`
- size: `872`
- prototype: `unsigned int __fastcall(const struct _EFSX_DATUM_KEY_AGMT_DATA *, struct _EFSX_DATUM_BLOB **, struct _EFSX_DATUM_BLOB **, void **, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007e500`

## callees

- `0x18004a89c`
- `0x180063698`
- `0x180069810`
- `0x18006ace4`
- `0x18006ff74`
- `0x18007af54`
- `0x18007b7bc`
- `0x18007f60c`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007f951`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007f951`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007f737`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007f737`
- `bcrypt!BCryptDestroyKey` at `0x18007f916`
- `bcrypt!BCryptDestroyKey` at `0x18007f931`
- `bcrypt!BCryptDestroyKey` at `0x18007f940`
- `bcrypt!BCryptDestroyKey` at `0x18007f916`
- `bcrypt!BCryptDestroyKey` at `0x18007f931`
- `bcrypt!BCryptDestroyKey` at `0x18007f940`
- `bcrypt!BCryptImportKeyPair` at `0x18007f791`
- `bcrypt!BCryptImportKeyPair` at `0x18007f791`
- `ntdll!RtlNtStatusToDosError` at `0x18007f743`
- `ntdll!RtlNtStatusToDosError` at `0x18007f79d`
- `ntdll!RtlNtStatusToDosError` at `0x18007f743`
- `ntdll!RtlNtStatusToDosError` at `0x18007f79d`

## pseudocode

```c
__int64 __fastcall EfsxStreamRecreateKeyAgmtParams(
        const struct _EFSX_DATUM_KEY_AGMT_DATA *a1,
        struct _EFSX_DATUM_BLOB **a2,
        struct _EFSX_DATUM_BLOB **a3,
        void **a4,
        unsigned __int8 **a5)
{
  void *v5; // r12
  struct _EFSX_DATUM_BLOB *v6; // rsi
  unsigned __int8 *v7; // r15
  BCRYPT_KEY_HANDLE v8; // r14
  unsigned int v9; // eax
  unsigned int v10; // ebx
  struct _EFSX_DATUM *v11; // rdi
  unsigned __int16 v12; // ax
  int v13; // r8d
  _DWORD *v14; // r13
  const WCHAR *v15; // rdx
  int v16; // eax
  ULONG v17; // eax
  unsigned __int16 v18; // ax
  int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned __int16 v22; // ax
  unsigned int v23; // r10d
  unsigned __int16 v24; // ax
  unsigned int v25; // eax
  char pbInput; // [rsp+20h] [rbp-60h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-40h] BYREF
  struct _EFSX_DATUM *v29; // [rsp+48h] [rbp-38h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp-30h] BYREF
  struct _EFSX_DATUM_BLOB *v31; // [rsp+58h] [rbp-28h] BYREF
  void *v32; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int8 *v33; // [rsp+68h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+70h] [rbp-10h] BYREF

  v5 = 0;
  phAlgorithm = 0;
  v6 = 0;
  v32 = 0;
  v7 = 0;
  v29 = 0;
  v8 = 0;
  v33 = 0;
  v31 = 0;
  phKey = 0;
  hKey = 0;
  v9 = EfsxDatumKeyAgmtDataQueryPublicKey(a1, &v29);
  v10 = v9;
  if ( v9 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v9, 27, 20);
    v11 = v29;
    goto LABEL_36;
  }
  v11 = v29;
  v12 = 0;
  if ( *(_WORD *)v29 >= 0xCu )
    v12 = *(_WORD *)v29 - 12;
  if ( v12 < 8u )
  {
    pbInput = 23;
LABEL_7:
    v13 = 50;
    v10 = 50;
LABEL_8:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v13, 27, pbInput);
    goto LABEL_36;
  }
  v14 = (_DWORD *)((char *)v29 + 12);
  if ( *((_DWORD *)v29 + 3) == 827016005 )
  {
    v15 = L"ECDH_P256";
  }
  else if ( *v14 == 860570437 )
  {
    v15 = L"ECDH_P384";
  }
  else
  {
    if ( *v14 != 894124869 )
    {
      pbInput = 39;
      goto LABEL_7;
    }
    v15 = L"ECDH_P521";
  }
  v16 = BCryptOpenAlgorithmProvider(&phAlgorithm, v15, L"Microsoft Primitive Provider", 0);
  if ( v16 < 0 )
  {
    v17 = RtlNtStatusToDosError(v16);
    v10 = v17;
    if ( v17 )
    {
      pbInput = 47;
LABEL_19:
      v13 = v17;
      goto LABEL_8;
    }
  }
  v18 = 0;
  if ( *(_WORD *)v11 >= 0xCu )
    v18 = *(_WORD *)v11 - 12;
  v19 = BCryptImportKeyPair(phAlgorithm, 0, L"ECCPUBLICBLOB", &phKey, (PUCHAR)v11 + 12, v18, 0);
  if ( v19 < 0 )
  {
    v17 = RtlNtStatusToDosError(v19);
    v10 = v17;
    if ( v17 )
    {
      pbInput = 58;
      goto LABEL_19;
    }
  }
  v20 = EfsSecondaryKeyCreate(phKey, &hKey);
  v10 = v20;
  if ( v20 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v20, 27, 61);
    v8 = hKey;
  }
  else
  {
    v8 = hKey;
    v21 = EfsxStreamExportPublicKeyB(hKey, 9u, &v31);
    v10 = v21;
    if ( v21 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v21, 27, 65);
      v6 = v31;
    }
    else
    {
      v6 = v31;
      v22 = 0;
      if ( *(_WORD *)v31 >= 0xCu )
        v22 = *(_WORD *)v31 - 12;
      v23 = v22;
      v24 = 0;
      if ( *(_WORD *)v11 >= 0xCu )
        v24 = *(_WORD *)v11 - 12;
      v25 = EfsxStreamDeriveKekB(v8, phKey, (char *)v11 + 12, v24, (char *)v31 + 12, v23, &v32, &v33);
      v10 = v25;
      if ( v25 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v25, 27, 74);
        v5 = v32;
        v7 = v33;
      }
      else
      {
        *a4 = v32;
        *a5 = v33;
        *a2 = v11;
        v11 = 0;
        *a3 = v6;
        v6 = 0;
      }
    }
  }
LABEL_36:
  if ( v11 )
    EfsxDatumFree(v11);
  if ( v6 )
    EfsxDatumFree(v6);
  if ( v5 )
    BCryptDestroyKey(v5);
  if ( v7 )
    EdppAuditSiteFree(v7);
  if ( v8 )
    BCryptDestroyKey(v8);
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v10;
}

```

## disassembly

```asm
0x18007f60c  mov     rax, rsp
0x18007f60f  mov     [rax+8], rbx
0x18007f613  mov     [rax+20h], r9
0x18007f617  mov     [rax+18h], r8
0x18007f61b  mov     [rax+10h], rdx
0x18007f61f  push    rbp
0x18007f620  push    rsi
0x18007f621  push    rdi
0x18007f622  push    r12
0x18007f624  push    r13
0x18007f626  push    r14
0x18007f628  push    r15
0x18007f62a  mov     rbp, rsp
0x18007f62d  sub     rsp, 80h
0x18007f634  xor     r12d, r12d
0x18007f637  mov     [rbp+phAlgorithm], 0
0x18007f63f  xor     esi, esi
0x18007f641  mov     [rbp+var_20], r12
0x18007f645  xor     r15d, r15d
0x18007f648  mov     [rbp+var_38], r12
0x18007f64c  xor     r14d, r14d
0x18007f64f  mov     [rbp+var_18], r15
0x18007f653  lea     rdx, [rbp+var_38]; struct _EFSX_DATUM_BLOB **
0x18007f657  mov     [rbp+var_28], rsi
0x18007f65b  mov     [rbp+phKey], rsi
0x18007f65f  mov     [rbp+hKey], r14
0x18007f663  call    ?EfsxDatumKeyAgmtDataQueryPublicKey@@YAKPEBU_EFSX_DATUM_KEY_AGMT_DATA@@PEAPEAU_EFSX_DATUM_BLOB@@@Z; EfsxDatumKeyAgmtDataQueryPublicKey(_EFSX_DATUM_KEY_AGMT_DATA const *,_EFSX_DATUM_BLOB * *)
0x18007f668  mov     ebx, eax
0x18007f66a  test    eax, eax
0x18007f66c  jz      short loc_18007F69A
0x18007f66e  mov     rcx, cs:g_hPublisher
0x18007f675  lea     r9d, [r12+1Bh]
0x18007f67a  mov     r8d, eax
0x18007f67d  mov     dword ptr [rsp+80h+pbInput], 814h
0x18007f685  lea     rdx, EFS_API_ERROR
0x18007f68c  call    fnEfsLogTrace1
0x18007f691  mov     rdi, [rbp+var_38]
0x18007f695  jmp     loc_18007F8F4
0x18007f69a  mov     rdi, [rbp+var_38]
0x18007f69e  xor     eax, eax
0x18007f6a0  movzx   ecx, word ptr [rdi]
0x18007f6a3  sub     cx, 0Ch
0x18007f6a7  cmp     word ptr [rdi], 0Ch
0x18007f6ab  cmovnb  ax, cx
0x18007f6af  cmp     ax, 8
0x18007f6b3  jnb     short loc_18007F6E4
0x18007f6b5  mov     dword ptr [rsp+80h+pbInput], 817h
0x18007f6bd  mov     r8d, 32h ; '2'
0x18007f6c3  mov     ebx, r8d
0x18007f6c6  mov     rcx, cs:g_hPublisher
0x18007f6cd  lea     rdx, EFS_API_ERROR
0x18007f6d4  mov     r9d, 1Bh
0x18007f6da  call    fnEfsLogTrace1
0x18007f6df  jmp     loc_18007F8F4
0x18007f6e4  lea     r13, [rdi+0Ch]
0x18007f6e8  cmp     dword ptr [r13+0], 314B4345h
0x18007f6f0  jz      short loc_18007F722
0x18007f6f2  cmp     dword ptr [r13+0], 334B4345h
0x18007f6fa  jz      short loc_18007F719
0x18007f6fc  cmp     dword ptr [r13+0], 354B4345h
0x18007f704  jz      short loc_18007F710
0x18007f706  mov     dword ptr [rsp+80h+pbInput], 827h
0x18007f70e  jmp     short loc_18007F6BD
0x18007f710  lea     rdx, aEcdhP521; "ECDH_P521"
0x18007f717  jmp     short loc_18007F729
0x18007f719  lea     rdx, aEcdhP384; "ECDH_P384"
0x18007f720  jmp     short loc_18007F729
0x18007f722  lea     rdx, aEcdhP256; "ECDH_P256"
0x18007f729  xor     r9d, r9d; dwFlags
0x18007f72c  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18007f733  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18007f737  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18007f73d  test    eax, eax
0x18007f73f  jns     short loc_18007F75F
0x18007f741  mov     ecx, eax; Status
0x18007f743  call    cs:__imp_RtlNtStatusToDosError
0x18007f749  mov     ebx, eax
0x18007f74b  test    eax, eax
0x18007f74d  jz      short loc_18007F75F
0x18007f74f  mov     dword ptr [rsp+80h+pbInput], 82Fh
0x18007f757  mov     r8d, eax
0x18007f75a  jmp     loc_18007F6C6
0x18007f75f  movzx   edx, word ptr [rdi]
0x18007f762  lea     r9, [rbp+phKey]; phKey
0x18007f766  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18007f76a  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x18007f771  sub     dx, 0Ch
0x18007f775  mov     [rsp+80h+dwFlags], esi; dwFlags
0x18007f779  xor     eax, eax
0x18007f77b  cmp     word ptr [rdi], 0Ch
0x18007f77f  cmovnb  ax, dx
0x18007f783  xor     edx, edx; hImportKey
0x18007f785  movzx   eax, ax
0x18007f788  mov     [rsp+80h+cbInput], eax; cbInput
0x18007f78c  mov     [rsp+80h+pbInput], r13; pbInput
0x18007f791  call    cs:__imp_BCryptImportKeyPair
0x18007f797  test    eax, eax
0x18007f799  jns     short loc_18007F7B3
0x18007f79b  mov     ecx, eax; Status
0x18007f79d  call    cs:__imp_RtlNtStatusToDosError
0x18007f7a3  mov     ebx, eax
0x18007f7a5  test    eax, eax
0x18007f7a7  jz      short loc_18007F7B3
0x18007f7a9  mov     dword ptr [rsp+80h+pbInput], 83Ah
0x18007f7b1  jmp     short loc_18007F757
0x18007f7b3  mov     rcx, [rbp+phKey]; hObject
0x18007f7b7  lea     rdx, [rbp+hKey]; void **
0x18007f7bb  call    ?EfsSecondaryKeyCreate@@YAKPEAXPEAPEAX@Z; EfsSecondaryKeyCreate(void *,void * *)
0x18007f7c0  mov     ebx, eax
0x18007f7c2  test    eax, eax
0x18007f7c4  jz      short loc_18007F7F3
0x18007f7c6  mov     rcx, cs:g_hPublisher
0x18007f7cd  lea     rdx, EFS_API_ERROR
0x18007f7d4  mov     r9d, 1Bh
0x18007f7da  mov     dword ptr [rsp+80h+pbInput], 83Dh
0x18007f7e2  mov     r8d, eax
0x18007f7e5  call    fnEfsLogTrace1
0x18007f7ea  mov     r14, [rbp+hKey]
0x18007f7ee  jmp     loc_18007F8F4
0x18007f7f3  mov     r14, [rbp+hKey]
0x18007f7f7  lea     r8, [rbp+var_28]; struct _EFSX_DATUM_BLOB **
0x18007f7fb  mov     rcx, r14; hKey
0x18007f7fe  mov     edx, 9; unsigned __int16
0x18007f803  call    ?EfsxStreamExportPublicKeyB@@YAKPEAXGPEAPEAU_EFSX_DATUM_BLOB@@@Z; EfsxStreamExportPublicKeyB(void *,ushort,_EFSX_DATUM_BLOB * *)
0x18007f808  mov     ebx, eax
0x18007f80a  test    eax, eax
0x18007f80c  jz      short loc_18007F83B
0x18007f80e  mov     rcx, cs:g_hPublisher
0x18007f815  lea     rdx, EFS_API_ERROR
0x18007f81c  mov     r9d, 1Bh
0x18007f822  mov     dword ptr [rsp+80h+pbInput], 841h
0x18007f82a  mov     r8d, eax
0x18007f82d  call    fnEfsLogTrace1
0x18007f832  mov     rsi, [rbp+var_28]
0x18007f836  jmp     loc_18007F8F4
0x18007f83b  mov     rsi, [rbp+var_28]
0x18007f83f  xor     eax, eax
0x18007f841  mov     dx, 0Ch
0x18007f845  mov     r8, r13; void *
0x18007f848  movzx   ecx, word ptr [rsi]
0x18007f84b  lea     r11, [rsi+0Ch]
0x18007f84f  sub     cx, dx
0x18007f852  cmp     [rsi], dx
0x18007f855  cmovnb  ax, cx
0x18007f859  movzx   ecx, word ptr [rdi]
0x18007f85c  movzx   r10d, ax
0x18007f860  sub     cx, dx
0x18007f863  xor     eax, eax
0x18007f865  cmp     [rdi], dx
0x18007f868  mov     rdx, [rbp+phKey]; void *
0x18007f86c  cmovnb  ax, cx
0x18007f870  mov     rcx, r14; void *
0x18007f873  movzx   r9d, ax; unsigned int
0x18007f877  lea     rax, [rbp+var_18]
0x18007f87b  mov     [rsp+80h+var_48], rax; unsigned __int8 **
0x18007f880  lea     rax, [rbp+var_20]
0x18007f884  mov     qword ptr [rsp+80h+dwFlags], rax; void **
0x18007f889  mov     [rsp+80h+cbInput], r10d; unsigned int
0x18007f88e  mov     [rsp+80h+pbInput], r11; void *
0x18007f893  call    ?EfsxStreamDeriveKekB@@YAKPEAX00K0KPEAPEAXPEAPEAE@Z; EfsxStreamDeriveKekB(void *,void *,void *,ulong,void *,ulong,void * *,uchar * *)
0x18007f898  mov     ebx, eax
0x18007f89a  test    eax, eax
0x18007f89c  jz      short loc_18007F8CC
0x18007f89e  mov     rcx, cs:g_hPublisher
0x18007f8a5  lea     rdx, EFS_API_ERROR
0x18007f8ac  mov     r9d, 1Bh
0x18007f8b2  mov     dword ptr [rsp+80h+pbInput], 84Ah
0x18007f8ba  mov     r8d, eax
0x18007f8bd  call    fnEfsLogTrace1
0x18007f8c2  mov     r12, [rbp+var_20]
0x18007f8c6  mov     r15, [rbp+var_18]
0x18007f8ca  jmp     short loc_18007F8F4
0x18007f8cc  mov     rcx, [rbp+arg_18]
0x18007f8d0  mov     rax, [rbp+var_20]
0x18007f8d4  mov     [rcx], rax
0x18007f8d7  mov     rax, [rbp+arg_20]
0x18007f8db  mov     rcx, [rbp+var_18]
0x18007f8df  mov     [rax], rcx
0x18007f8e2  mov     rax, [rbp+arg_8]
0x18007f8e6  mov     [rax], rdi
0x18007f8e9  xor     edi, edi
0x18007f8eb  mov     rax, [rbp+arg_10]
0x18007f8ef  mov     [rax], rsi
0x18007f8f2  xor     esi, esi
0x18007f8f4  test    rdi, rdi
0x18007f8f7  jz      short loc_18007F901
0x18007f8f9  mov     rcx, rdi; struct _EFSX_DATUM *
0x18007f8fc  call    ?EfsxDatumFree@@YAKPEAU_EFSX_DATUM@@@Z; EfsxDatumFree(_EFSX_DATUM *)
0x18007f901  test    rsi, rsi
0x18007f904  jz      short loc_18007F90E
0x18007f906  mov     rcx, rsi; struct _EFSX_DATUM *
0x18007f909  call    ?EfsxDatumFree@@YAKPEAU_EFSX_DATUM@@@Z; EfsxDatumFree(_EFSX_DATUM *)
0x18007f90e  test    r12, r12
0x18007f911  jz      short loc_18007F91C
0x18007f913  mov     rcx, r12; hKey
0x18007f916  call    cs:__imp_BCryptDestroyKey
0x18007f91c  test    r15, r15
0x18007f91f  jz      short loc_18007F929
0x18007f921  mov     rcx, r15; void *
0x18007f924  call    ?EdppAuditSiteFree@@YAXPEAX@Z; EdppAuditSiteFree(void *)
0x18007f929  test    r14, r14
0x18007f92c  jz      short loc_18007F937
0x18007f92e  mov     rcx, r14; hKey
0x18007f931  call    cs:__imp_BCryptDestroyKey
0x18007f937  mov     rcx, [rbp+phKey]; hKey
0x18007f93b  test    rcx, rcx
0x18007f93e  jz      short loc_18007F946
0x18007f940  call    cs:__imp_BCryptDestroyKey
0x18007f946  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18007f94a  test    rcx, rcx
0x18007f94d  jz      short loc_18007F957
0x18007f94f  xor     edx, edx; dwFlags
0x18007f951  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18007f957  mov     eax, ebx
0x18007f959  mov     rbx, [rsp+80h+arg_0]
0x18007f961  add     rsp, 80h
0x18007f968  pop     r15
0x18007f96a  pop     r14
0x18007f96c  pop     r13
0x18007f96e  pop     r12
0x18007f970  pop     rdi
0x18007f971  pop     rsi
0x18007f972  pop     rbp
0x18007f973  retn
```
