# EfsxStreamDpapiNgProtectorDataCreate(_EFSX_DATUM_PROTECTOR_INFO *,_EFS_FILE_KEY const *,_EFSX_DATUM * *)

- ea: `0x18007b470`
- end: `0x18007b7b4`
- name: `?EfsxStreamDpapiNgProtectorDataCreate@@YAKPEAU_EFSX_DATUM_PROTECTOR_INFO@@PEBU_EFS_FILE_KEY@@PEAPEAU_EFSX_DATUM@@@Z`
- size: `836`
- prototype: `unsigned int __fastcall(struct _EFSX_DATUM_PROTECTOR_INFO *, const struct _EFS_FILE_KEY *, struct _EFSX_DATUM **)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007de68`
- `0x18007eb90`

## callees

- `0x18004a89c`
- `0x180063698`
- `0x180066d30`
- `0x180066fd0`
- `0x1800695bc`
- `0x180069810`
- `0x180069c6c`
- `0x18006a3d4`
- `0x18006abd0`
- `0x18007b470`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007b718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007b718`
- `ncrypt!NCryptCreateProtectionDescriptor` at `0x18007b5fd`
- `ncrypt!NCryptCreateProtectionDescriptor` at `0x18007b5fd`
- `ncrypt!NCryptProtectSecret` at `0x18007b649`
- `ncrypt!NCryptProtectSecret` at `0x18007b649`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x18007b727`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x18007b727`
- `bcrypt!BCryptExportKey` at `0x18007b51b`
- `bcrypt!BCryptExportKey` at `0x18007b5b1`
- `bcrypt!BCryptExportKey` at `0x18007b51b`
- `bcrypt!BCryptExportKey` at `0x18007b5b1`
- `ntdll!RtlNtStatusToDosError` at `0x18007b536`
- `ntdll!RtlNtStatusToDosError` at `0x18007b5bd`
- `ntdll!RtlNtStatusToDosError` at `0x18007b536`
- `ntdll!RtlNtStatusToDosError` at `0x18007b5bd`

## pseudocode

```c
__int64 __fastcall EfsxStreamDpapiNgProtectorDataCreate(
        struct _EFSX_DATUM_PROTECTOR_INFO *a1,
        BCRYPT_KEY_HANDLE *a2,
        struct _EFSX_DATUM **a3)
{
  PUCHAR v5; // rdi
  struct _EFSX_DATUM *v6; // rsi
  unsigned int v7; // eax
  struct _EFSX_DATUM *v8; // r15
  unsigned int v9; // ebx
  NTSTATUS v10; // eax
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  struct _EFSX_DATUM *v14; // rcx
  struct _EFSX_DATUM *v15; // r14
  __int64 v16; // rax
  PUCHAR v17; // rdx
  char cbOutput; // [rsp+20h] [rbp-49h]
  unsigned __int64 v20; // [rsp+40h] [rbp-29h] BYREF
  PUCHAR pbOutput; // [rsp+48h] [rbp-21h] BYREF
  struct _EFSX_DATUM *v22; // [rsp+50h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-11h] BYREF
  __int64 v24; // [rsp+60h] [rbp-9h] BYREF
  struct _EFSX_DATUM *v25; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v26[10]; // [rsp+70h] [rbp+7h] BYREF
  ULONG pcbResult; // [rsp+E8h] [rbp+7Fh] BYREF

  v26[0] = 0;
  pbOutput = 0;
  v5 = 0;
  pcbResult = 0;
  hMem = 0;
  LODWORD(v20) = 0;
  v6 = 0;
  v22 = 0;
  v25 = 0;
  v24 = 0;
  v7 = EfsxDatumProtectorInfoQueryDescriptor(a1, 0xCu, &v25);
  v8 = v25;
  v9 = v7;
  if ( !v7 )
  {
    v10 = BCryptExportKey(a2[2], 0, L"KeyDataBlob", 0, 0, &pcbResult, 0);
    if ( (int)(v10 + 0x80000000) >= 0 && v10 != -1073741789 )
    {
      v7 = RtlNtStatusToDosError(v10);
      v9 = v7;
      cbOutput = -27;
      goto LABEL_3;
    }
    v9 = EfsxLibAllocZero(pcbResult, (void **)&pbOutput);
    if ( v9 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, pcbResult, 27, 232);
      v5 = pbOutput;
      goto LABEL_25;
    }
    v5 = pbOutput;
    v11 = BCryptExportKey(a2[2], 0, L"KeyDataBlob", pbOutput, pcbResult, &pcbResult, 0);
    if ( v11 < 0 )
    {
      v7 = RtlNtStatusToDosError(v11);
      v9 = v7;
      cbOutput = -14;
      goto LABEL_3;
    }
    v7 = CEfsTokenManager::ModifyCallerContext((CEfsTokenManager *)v26, 1);
    v9 = v7;
    if ( v7 )
    {
      cbOutput = -5;
      goto LABEL_3;
    }
    if ( (int)NCryptCreateProtectionDescriptor((char *)v8 + 8, 0, &v24) < 0 )
    {
      v9 = 87;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 87, 27, 6);
      goto LABEL_25;
    }
    if ( (int)NCryptProtectSecret(v24, 64, v5, pcbResult, 0, 0, &hMem, &v20) < 0 )
    {
      v9 = 87;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 87, 27, 19);
      goto LABEL_25;
    }
    v12 = EfsxDatumBlobCreate(5u, 7u, (const unsigned __int8 *)hMem, (unsigned int)v20, &v22);
    v9 = v12;
    if ( v12 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v12, 27, 26);
      v6 = v22;
      goto LABEL_25;
    }
    v6 = v22;
    v25 = 0;
    v13 = EfsxDatumCreateComplex(7u, &v22, 1u, &v25);
    v14 = v25;
    v9 = v13;
    if ( !v13 )
    {
      if ( v25 && *(_WORD *)v25 >= 0xAu )
      {
        *((_WORD *)v25 + 1) = 2;
        v15 = v14;
        *((_WORD *)v14 + 4) = 0;
        goto LABEL_24;
      }
      v9 = 13;
    }
    v15 = 0;
    if ( v25 )
      EfsxDatumFree(v25);
    if ( v9 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v9, 27, 30);
      goto LABEL_25;
    }
LABEL_24:
    *a3 = v15;
    goto LABEL_25;
  }
  cbOutput = -43;
LABEL_3:
  fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v7, 27, cbOutput);
LABEL_25:
  if ( hMem )
    LocalFree(hMem);
  if ( v24 )
    NCryptCloseProtectionDescriptor();
  if ( v5 )
  {
    v16 = pcbResult;
    v17 = v5;
    if ( pcbResult )
    {
      do
      {
        *v17++ = 0;
        --v16;
      }
      while ( v16 );
    }
    EdppAuditSiteFree(v5);
  }
  if ( v6 )
    EfsxDatumFree(v6);
  if ( v8 )
    EfsxDatumFree(v8);
  CEfsTokenManager::RevertToOriginalToken((CEfsTokenManager *)v26);
  return v9;
}

```

## disassembly

```asm
0x18007b470  push    rbp
0x18007b472  push    rbx
0x18007b473  push    rsi
0x18007b474  push    rdi
0x18007b475  push    r12
0x18007b477  push    r13
0x18007b479  push    r14
0x18007b47b  push    r15
0x18007b47d  lea     rbp, [rsp-1Fh]
0x18007b482  sub     rsp, 88h
0x18007b489  xor     r13d, r13d
0x18007b48c  mov     r12, r8
0x18007b48f  mov     r14, rdx
0x18007b492  mov     [rbp+57h+var_50], r13
0x18007b496  lea     r8, [rbp+57h+var_58]; struct _EFSX_DATUM_DESCRIPTOR **
0x18007b49a  mov     [rbp+57h+pbOutput], r13
0x18007b49e  mov     edi, r13d
0x18007b4a1  mov     [rbp+57h+arg_18], r13d
0x18007b4a5  lea     edx, [r13+0Ch]; unsigned __int16
0x18007b4a9  mov     [rbp+57h+hMem], r13
0x18007b4ad  mov     dword ptr [rbp+57h+var_80], r13d
0x18007b4b1  mov     esi, r13d
0x18007b4b4  mov     [rbp+57h+var_70], r13
0x18007b4b8  mov     [rbp+57h+var_58], r13
0x18007b4bc  mov     [rbp+57h+var_60], r13
0x18007b4c0  call    ?EfsxDatumProtectorInfoQueryDescriptor@@YAKPEBU_EFSX_DATUM_PROTECTOR_INFO@@GPEAPEAU_EFSX_DATUM_DESCRIPTOR@@@Z; EfsxDatumProtectorInfoQueryDescriptor(_EFSX_DATUM_PROTECTOR_INFO const *,ushort,_EFSX_DATUM_DESCRIPTOR * *)
0x18007b4c5  mov     r15, [rbp+57h+var_58]
0x18007b4c9  mov     ebx, eax
0x18007b4cb  test    eax, eax
0x18007b4cd  jz      short loc_18007B4F8
0x18007b4cf  mov     [rsp+0C0h+cbOutput], 5D5h
0x18007b4d7  mov     r8d, eax
0x18007b4da  mov     rcx, cs:g_hPublisher
0x18007b4e1  lea     rdx, EFS_API_ERROR
0x18007b4e8  mov     r9d, 1Bh
0x18007b4ee  call    fnEfsLogTrace1
0x18007b4f3  jmp     loc_18007B70F
0x18007b4f8  mov     rcx, [r14+10h]; hKey
0x18007b4fc  lea     rax, [rbp+57h+arg_18]
0x18007b500  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x18007b505  lea     r8, pszBlobType; "KeyDataBlob"
0x18007b50c  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x18007b511  xor     r9d, r9d; pbOutput
0x18007b514  xor     edx, edx; hExportKey
0x18007b516  mov     [rsp+0C0h+cbOutput], r13d; cbOutput
0x18007b51b  call    cs:__imp_BCryptExportKey
0x18007b521  mov     edx, 80000000h
0x18007b526  lea     ecx, [rax+rdx]
0x18007b529  test    edx, ecx
0x18007b52b  jnz     short loc_18007B548
0x18007b52d  cmp     eax, 0C0000023h
0x18007b532  jz      short loc_18007B548
0x18007b534  mov     ecx, eax; Status
0x18007b536  call    cs:__imp_RtlNtStatusToDosError
0x18007b53c  mov     ebx, eax
0x18007b53e  mov     [rsp+0C0h+cbOutput], 5E5h
0x18007b546  jmp     short loc_18007B4D7
0x18007b548  mov     ecx, [rbp+57h+arg_18]; unsigned __int64
0x18007b54b  lea     rdx, [rbp+57h+pbOutput]; void **
0x18007b54f  call    ?EfsxLibAllocZero@@YAK_KPEAPEAX@Z; EfsxLibAllocZero(unsigned __int64,void * *)
0x18007b554  mov     ebx, eax
0x18007b556  test    eax, eax
0x18007b558  jz      short loc_18007B588
0x18007b55a  mov     r8d, [rbp+57h+arg_18]
0x18007b55e  lea     rdx, EFS_ERROR_MEMORY
0x18007b565  mov     rcx, cs:g_hPublisher
0x18007b56c  mov     r9d, 1Bh
0x18007b572  mov     [rsp+0C0h+cbOutput], 5E8h
0x18007b57a  call    fnEfsLogTrace1
0x18007b57f  mov     rdi, [rbp+57h+pbOutput]
0x18007b583  jmp     loc_18007B70F
0x18007b588  mov     rdi, [rbp+57h+pbOutput]
0x18007b58c  lea     rax, [rbp+57h+arg_18]
0x18007b590  mov     rcx, [r14+10h]; hKey
0x18007b594  lea     r8, pszBlobType; "KeyDataBlob"
0x18007b59b  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x18007b5a0  mov     r9, rdi; pbOutput
0x18007b5a3  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x18007b5a8  xor     edx, edx; hExportKey
0x18007b5aa  mov     eax, [rbp+57h+arg_18]
0x18007b5ad  mov     [rsp+0C0h+cbOutput], eax; cbOutput
0x18007b5b1  call    cs:__imp_BCryptExportKey
0x18007b5b7  test    eax, eax
0x18007b5b9  jns     short loc_18007B5D2
0x18007b5bb  mov     ecx, eax; Status
0x18007b5bd  call    cs:__imp_RtlNtStatusToDosError
0x18007b5c3  mov     ebx, eax
0x18007b5c5  mov     [rsp+0C0h+cbOutput], 5F2h
0x18007b5cd  jmp     loc_18007B4D7
0x18007b5d2  mov     edx, 1; unsigned int
0x18007b5d7  lea     rcx, [rbp+57h+var_50]; this
0x18007b5db  call    ?ModifyCallerContext@CEfsTokenManager@@QEAAKK@Z; CEfsTokenManager::ModifyCallerContext(ulong)
0x18007b5e0  mov     ebx, eax
0x18007b5e2  test    eax, eax
0x18007b5e4  jz      short loc_18007B5F3
0x18007b5e6  mov     [rsp+0C0h+cbOutput], 5FBh
0x18007b5ee  jmp     loc_18007B4D7
0x18007b5f3  lea     rcx, [r15+8]
0x18007b5f7  xor     edx, edx
0x18007b5f9  lea     r8, [rbp+57h+var_60]
0x18007b5fd  call    cs:__imp_NCryptCreateProtectionDescriptor
0x18007b603  test    eax, eax
0x18007b605  jns     short loc_18007B61D
0x18007b607  mov     r8d, 57h ; 'W'
0x18007b60d  mov     [rsp+0C0h+cbOutput], 606h
0x18007b615  mov     ebx, r8d
0x18007b618  jmp     loc_18007B4DA
0x18007b61d  mov     r9d, [rbp+57h+arg_18]
0x18007b621  lea     rax, [rbp+57h+var_80]
0x18007b625  mov     rcx, [rbp+57h+var_60]
0x18007b629  mov     r8, rdi
0x18007b62c  mov     [rsp+0C0h+var_88], rax
0x18007b631  mov     edx, 40h ; '@'
0x18007b636  lea     rax, [rbp+57h+hMem]
0x18007b63a  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18007b63f  mov     [rsp+0C0h+pcbResult], r13
0x18007b644  mov     qword ptr [rsp+0C0h+cbOutput], r13
0x18007b649  call    cs:__imp_NCryptProtectSecret
0x18007b64f  test    eax, eax
0x18007b651  jns     short loc_18007B669
0x18007b653  mov     r8d, 57h ; 'W'
0x18007b659  mov     [rsp+0C0h+cbOutput], 613h
0x18007b661  mov     ebx, r8d
0x18007b664  jmp     loc_18007B4DA
0x18007b669  mov     r9d, dword ptr [rbp+57h+var_80]; unsigned __int64
0x18007b66d  lea     rax, [rbp+57h+var_70]
0x18007b671  mov     r8, [rbp+57h+hMem]; unsigned __int8 *
0x18007b675  mov     r14d, 7
0x18007b67b  mov     edx, r14d; unsigned __int16
0x18007b67e  mov     qword ptr [rsp+0C0h+cbOutput], rax; struct _EFSX_DATUM_BLOB **
0x18007b683  lea     ecx, [r14-2]; unsigned __int16
0x18007b687  call    ?EfsxDatumBlobCreate@@YAKGGPEBE_KPEAPEAU_EFSX_DATUM_BLOB@@@Z; EfsxDatumBlobCreate(ushort,ushort,uchar const *,unsigned __int64,_EFSX_DATUM_BLOB * *)
0x18007b68c  mov     ebx, eax
0x18007b68e  test    eax, eax
0x18007b690  jz      short loc_18007B6BA
0x18007b692  mov     rcx, cs:g_hPublisher
0x18007b699  lea     r9d, [r14+14h]
0x18007b69d  mov     r8d, eax
0x18007b6a0  mov     [rsp+0C0h+cbOutput], 61Ah
0x18007b6a8  lea     rdx, EFS_API_ERROR
0x18007b6af  call    fnEfsLogTrace1
0x18007b6b4  mov     rsi, [rbp+57h+var_70]
0x18007b6b8  jmp     short loc_18007B70F
0x18007b6ba  mov     rsi, [rbp+57h+var_70]
0x18007b6be  lea     r9, [rbp+57h+var_58]; struct _EFSX_DATUM **
0x18007b6c2  mov     r8d, 1; unsigned __int16
0x18007b6c8  mov     [rbp+57h+var_70], rsi
0x18007b6cc  mov     ecx, r14d; unsigned __int16
0x18007b6cf  mov     [rbp+57h+var_58], r13
0x18007b6d3  lea     rdx, [rbp+57h+var_70]; struct _EFSX_DATUM **
0x18007b6d7  call    ?EfsxDatumCreateComplex@@YAKGPEAPEBU_EFSX_DATUM@@GPEAPEAU1@@Z; EfsxDatumCreateComplex(ushort,_EFSX_DATUM const * *,ushort,_EFSX_DATUM * *)
0x18007b6dc  mov     rcx, [rbp+57h+var_58]; struct _EFSX_DATUM *
0x18007b6e0  mov     ebx, eax
0x18007b6e2  test    eax, eax
0x18007b6e4  jnz     loc_18007B78F
0x18007b6ea  test    rcx, rcx
0x18007b6ed  jz      loc_18007B78A
0x18007b6f3  cmp     word ptr [rcx], 0Ah
0x18007b6f7  jb      loc_18007B78A
0x18007b6fd  mov     word ptr [rcx+2], 2
0x18007b703  mov     r14, rcx
0x18007b706  mov     [rcx+8], r13w
0x18007b70b  mov     [r12], r14
0x18007b70f  mov     rcx, [rbp+57h+hMem]; hMem
0x18007b713  test    rcx, rcx
0x18007b716  jz      short loc_18007B71E
0x18007b718  call    cs:__imp_LocalFree
0x18007b71e  mov     rcx, [rbp+57h+var_60]
0x18007b722  test    rcx, rcx
0x18007b725  jz      short loc_18007B72D
0x18007b727  call    cs:__imp_NCryptCloseProtectionDescriptor
0x18007b72d  test    rdi, rdi
0x18007b730  jz      short loc_18007B751
0x18007b732  mov     eax, [rbp+57h+arg_18]
0x18007b735  mov     rdx, rdi
0x18007b738  test    rax, rax
0x18007b73b  jz      short loc_18007B749
0x18007b73d  mov     [rdx], r13b
0x18007b740  inc     rdx
0x18007b743  sub     rax, 1
0x18007b747  jnz     short loc_18007B73D
0x18007b749  mov     rcx, rdi; void *
0x18007b74c  call    ?EdppAuditSiteFree@@YAXPEAX@Z; EdppAuditSiteFree(void *)
0x18007b751  test    rsi, rsi
0x18007b754  jz      short loc_18007B75E
0x18007b756  mov     rcx, rsi; struct _EFSX_DATUM *
0x18007b759  call    ?EfsxDatumFree@@YAKPEAU_EFSX_DATUM@@@Z; EfsxDatumFree(_EFSX_DATUM *)
0x18007b75e  test    r15, r15
0x18007b761  jz      short loc_18007B76B
0x18007b763  mov     rcx, r15; struct _EFSX_DATUM *
0x18007b766  call    ?EfsxDatumFree@@YAKPEAU_EFSX_DATUM@@@Z; EfsxDatumFree(_EFSX_DATUM *)
0x18007b76b  lea     rcx, [rbp+57h+var_50]; this
0x18007b76f  call    ?RevertToOriginalToken@CEfsTokenManager@@QEAAXXZ; CEfsTokenManager::RevertToOriginalToken(void)
0x18007b774  mov     eax, ebx
0x18007b776  add     rsp, 88h
0x18007b77d  pop     r15
0x18007b77f  pop     r14
0x18007b781  pop     r13
0x18007b783  pop     r12
0x18007b785  pop     rdi
0x18007b786  pop     rsi
0x18007b787  pop     rbx
0x18007b788  pop     rbp
0x18007b789  retn
0x18007b78a  mov     ebx, 0Dh
0x18007b78f  mov     r14, r13
0x18007b792  test    rcx, rcx
0x18007b795  jz      short loc_18007B79C
0x18007b797  call    ?EfsxDatumFree@@YAKPEAU_EFSX_DATUM@@@Z; EfsxDatumFree(_EFSX_DATUM *)
0x18007b79c  test    ebx, ebx
0x18007b79e  jz      loc_18007B70B
0x18007b7a4  mov     [rsp+0C0h+cbOutput], 61Eh
0x18007b7ac  mov     r8d, ebx
0x18007b7af  jmp     loc_18007B4DA
```
