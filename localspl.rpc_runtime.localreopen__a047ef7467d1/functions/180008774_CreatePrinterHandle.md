# CreatePrinterHandle

- ea: `0x180008774`
- end: `0x180008cb0`
- name: `CreatePrinterHandle`
- size: `1340`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007fd8`
- `0x18004fe9c`
- `0x18005640c`

## callees

- `0x1800051f0`
- `0x1800086e0`
- `0x180008730`
- `0x180008774`
- `0x18000bc0c`
- `0x180015ba0`
- `0x18001ee20`
- `0x180047318`
- `0x180054638`
- `0x180065e24`
- `0x18009ffb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bf6`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180008af9`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180008af9`
- `SPOOLSS!DllFreeSplStr` at `0x18000890e`
- `SPOOLSS!DllFreeSplStr` at `0x18000891b`
- `SPOOLSS!DllFreeSplStr` at `0x180008925`
- `SPOOLSS!DllFreeSplStr` at `0x18000892f`
- `SPOOLSS!DllFreeSplStr` at `0x180008939`
- `SPOOLSS!DllFreeSplStr` at `0x18000890e`
- `SPOOLSS!DllFreeSplStr` at `0x18000891b`
- `SPOOLSS!DllFreeSplStr` at `0x180008925`
- `SPOOLSS!DllFreeSplStr` at `0x18000892f`
- `SPOOLSS!DllFreeSplStr` at `0x180008939`
- `SPOOLSS!DllFreeSplMem` at `0x18000895a`
- `SPOOLSS!DllFreeSplMem` at `0x180008963`
- `SPOOLSS!DllFreeSplMem` at `0x18000895a`
- `SPOOLSS!DllFreeSplMem` at `0x180008963`
- `SPOOLSS!DllAllocSplMem` at `0x18000879e`
- `SPOOLSS!DllAllocSplMem` at `0x180008b44`
- `SPOOLSS!DllAllocSplMem` at `0x18000879e`
- `SPOOLSS!DllAllocSplMem` at `0x180008b44`
- `SPOOLSS!AllocSplStr` at `0x18000881a`
- `SPOOLSS!AllocSplStr` at `0x180008827`
- `SPOOLSS!AllocSplStr` at `0x1800089e9`
- `SPOOLSS!AllocSplStr` at `0x1800089fa`
- `SPOOLSS!AllocSplStr` at `0x180008b8e`
- `SPOOLSS!AllocSplStr` at `0x180008bb4`
- `SPOOLSS!AllocSplStr` at `0x18000881a`
- `SPOOLSS!AllocSplStr` at `0x180008827`
- `SPOOLSS!AllocSplStr` at `0x1800089e9`
- `SPOOLSS!AllocSplStr` at `0x1800089fa`
- `SPOOLSS!AllocSplStr` at `0x180008b8e`
- `SPOOLSS!AllocSplStr` at `0x180008bb4`
- `SPOOLSS!IsNamedPipeRpcCall` at `0x180008997`
- `SPOOLSS!IsNamedPipeRpcCall` at `0x180008997`

## string_xrefs

- `0x1800087b3`: `CreatePrinterHandle`
- `0x1800088f3`: `CreatePrinterHandle`
- `0x180008a1c`: `CreatePrinterHandle`
- `0x180008b5d`: `CreatePrinterHandle`
- `0x180008be5`: `CreatePrinterHandle`
- `0x180008c1c`: `CreatePrinterHandle`

## pseudocode

```c
__int64 __fastcall CreatePrinterHandle(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        unsigned int a11,
        __int64 a12,
        int a13,
        __int64 a14)
{
  __int64 v15; // r15
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // eax
  DWORD v26; // eax
  DWORD v27; // esi
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v31; // rsi
  __int64 v32; // rax
  int v33; // r12d
  DWORD *v34; // rsi
  _DWORD *v35; // r9
  int v36; // r14d
  struct _GENERIC_MAPPING *v37; // rdx
  __int64 v38; // rax
  void *v39; // rax
  __int64 v40; // rax
  __int64 Datatype; // rax
  DWORD LastError; // eax
  __int64 v43; // rcx
  unsigned int *v44; // rcx
  __int64 v45; // rcx
  unsigned int v46; // eax
  __int64 v47; // rcx

  v15 = 0;
  v19 = DllAllocSplMem(344);
  v20 = v19;
  if ( !v19 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceWarning("CreatePrinterHandle", L"Failed to allocate SPOOL struct.");
    return v15;
  }
  *(_DWORD *)v19 = 17997;
  *(_QWORD *)(v19 + 64) = a3;
  *(_QWORD *)(v19 + 216) = a14;
  *(_QWORD *)(v19 + 96) = a5;
  *(_QWORD *)(v19 + 80) = a6;
  *(_QWORD *)(v19 + 104) = a8;
  *(_QWORD *)(v19 + 72) = a4;
  *(_DWORD *)(v19 + 88) = a7;
  *(_DWORD *)(v19 + 112) = 0;
  *(_QWORD *)(v19 + 56) = 0;
  *(_QWORD *)(v19 + 24) = AllocSplStr(a1);
  v21 = AllocSplStr(a2);
  *(_QWORD *)(v20 + 32) = v21;
  *(_QWORD *)(v20 + 264) = 0;
  *(_QWORD *)(v20 + 272) = 0;
  *(_QWORD *)(v20 + 288) = 0;
  *(_DWORD *)(v20 + 280) = 0;
  *(_DWORD *)(v20 + 312) = 0;
  *(_QWORD *)(v20 + 320) = 0;
  if ( !*(_QWORD *)(v20 + 24) || a2 && !v21 )
    goto LABEL_14;
  *(_QWORD *)(v20 + 168) = a10;
  if ( !(unsigned int)GetClientSessionData(v20 + 284) )
    goto LABEL_14;
  v24 = geCollectUsersInfo;
  if ( !geCollectUsersInfo )
  {
    GetSplInitSettingFromReg(v23, v22, a10);
    v24 = geCollectUsersInfo;
  }
  if ( v24 == 4 && (*(_DWORD *)(a10 + 168) & 0x1000000) != 0 && (a7 & 0x11) != 0 )
  {
    v25 = AttachUserInformation((struct _SPOOL *)v20);
    v26 = StatusFromHResult(v25);
    v27 = v26;
    if ( v26 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "CreatePrinterHandle",
        L"Failed to attach user information to handle.  Error %d",
        v26);
      SetLastError(v27);
LABEL_14:
      DllFreeSplStr(*(_QWORD *)(v20 + 240));
      DllFreeSplStr(*(_QWORD *)(v20 + 232));
      DllFreeSplStr(*(_QWORD *)(v20 + 24));
      DllFreeSplStr(*(_QWORD *)(v20 + 40));
      DllFreeSplStr(*(_QWORD *)(v20 + 32));
      v28 = *(_QWORD *)(v20 + 48);
      if ( v28 )
        SafeDecrementReference((unsigned int *)(v28 + 16));
      v29 = *(_QWORD *)(v20 + 56);
      if ( v29 )
        DllFreeSplMem(v29);
      DllFreeSplMem(v20);
      return v15;
    }
  }
  if ( (a7 & 0x40) != 0 )
  {
    v31 = a12;
    if ( a12 )
    {
      if ( a13 != 1 )
      {
        if ( a13 != 3 )
          goto LABEL_29;
        v31 = a12 + 8;
        *(_DWORD *)(v20 + 280) = *(_DWORD *)(a12 + 4);
      }
      *(_OWORD *)(v20 + 224) = *(_OWORD *)v31;
      *(_OWORD *)(v20 + 240) = *(_OWORD *)(v31 + 16);
      *(_QWORD *)(v20 + 256) = *(_QWORD *)(v31 + 32);
      *(_QWORD *)(v20 + 240) = AllocSplStr(*(_QWORD *)(v31 + 16));
      v32 = AllocSplStr(*(_QWORD *)(v31 + 8));
      *(_QWORD *)(v20 + 232) = v32;
      if ( !*(_QWORD *)(v20 + 240) || !v32 )
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "CreatePrinterHandle",
          L"Could not allocate memory for user name or machine name.");
    }
    else
    {
      IsNamedPipeRpcCall();
    }
  }
LABEL_29:
  v33 = a7 & 0x10;
  if ( (a7 & 0x10) != 0 || (a7 & 0x100) != 0 )
  {
    v34 = (DWORD *)(v20 + 116);
    v36 = ValidateObjectAccess(0, a11, v20, (_DWORD *)(v20 + 116), a10, 1);
    if ( v36 && (a7 & 0x40) != 0 && (a11 & 1) != 0 && (unsigned int)ValidateObjectAccess(0, 1, 0, 0, a10, 1) )
      *(_DWORD *)(v20 + 88) |= 0x200u;
    v37 = &GenericMapping;
  }
  else
  {
    v34 = (DWORD *)(v20 + 116);
    v35 = (_DWORD *)(v20 + 116);
    if ( ((unsigned __int8)a7 & (unsigned __int8)(v33 + 2)) != 0 )
    {
      v36 = ValidateObjectAccess((unsigned int)(v33 + 2), a11, *(_QWORD *)(v20 + 80), v35, a10, 1);
      v37 = &GenericMapping;
    }
    else
    {
      v36 = ValidateObjectAccess(1, a11, v20, v35, a10, 1);
      v37 = &stru_18013DDE8;
    }
  }
  MapGenericMask(v34, v37);
  if ( !v36 )
  {
    SetLastError(5u);
    v15 = 0;
    goto LABEL_14;
  }
  if ( !a3 )
    goto LABEL_61;
  if ( a9 )
  {
    v38 = *(_QWORD *)(a9 + 8);
    if ( v38 )
    {
      v39 = (void *)DllAllocSplMem(*(unsigned __int16 *)(v38 + 68) + (unsigned int)*(unsigned __int16 *)(v38 + 70));
      *(_QWORD *)(v20 + 56) = v39;
      if ( !v39 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceWarning("CreatePrinterHandle", L"Failed to allocate memory for devmode.");
LABEL_47:
        v15 = 0;
        goto LABEL_14;
      }
      memcpy_0(
        v39,
        *(const void **)(a9 + 8),
        *(unsigned __int16 *)(*(_QWORD *)(a9 + 8) + 68LL)
      + (unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(a9 + 8) + 70LL));
    }
    if ( *(_QWORD *)a9 )
    {
      v40 = AllocSplStr(*(_QWORD *)a9);
      *(_QWORD *)(v20 + 40) = v40;
      Datatype = FindDatatype(*(_QWORD *)(a3 + 56), v40);
      goto LABEL_53;
    }
  }
  else
  {
    *(_DWORD *)(v20 + 312) = 1;
  }
  *(_QWORD *)(v20 + 40) = AllocSplStr(*(_QWORD *)(a3 + 64));
  Datatype = *(_QWORD *)(a3 + 56);
LABEL_53:
  *(_QWORD *)(v20 + 48) = Datatype;
  if ( *(_QWORD *)(a3 + 56) )
  {
    if ( !Datatype )
    {
      LastError = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "CreatePrinterHandle",
        L"Failed to find PrintProcessor for datatype %ws.  Error %d",
        *(_QWORD *)(v20 + 40),
        LastError);
LABEL_56:
      SetLastError(0x70Cu);
      goto LABEL_47;
    }
  }
  else if ( !Datatype )
  {
    goto LABEL_59;
  }
  SafeIncrementReference((unsigned int *)(Datatype + 16));
LABEL_59:
  if ( !*(_QWORD *)(v20 + 40) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceWarning("CreatePrinterHandle", L"Failed to allocate memory for datatype.");
    goto LABEL_56;
  }
LABEL_61:
  if ( (a7 & 1) != 0 )
  {
    v43 = *(_QWORD *)(v20 + 64);
    *(_QWORD *)(v20 + 8) = *(_QWORD *)(v43 + 200);
    *(_QWORD *)(v43 + 200) = v20;
  }
  else
  {
    if ( (a7 & 0x10) != 0 || (a7 & 0x100) != 0 )
    {
      v44 = (unsigned int *)(a10 + 16);
      *(_QWORD *)(v20 + 8) = *(_QWORD *)(a10 + 88);
      *(_QWORD *)(a10 + 88) = v20;
    }
    else
    {
      if ( (a7 & 6) == 0 || !a6 )
        goto LABEL_70;
      v44 = (unsigned int *)(a6 + 24);
    }
    SafeIncrementReference(v44);
  }
LABEL_70:
  v45 = *(_QWORD *)(v20 + 64);
  if ( v45 )
  {
    v46 = SafeIncrementReference((unsigned int *)(v45 + 16));
    v47 = *(_QWORD *)(v20 + 64);
    if ( v46 > *(_DWORD *)(v47 + 248) )
      *(_DWORD *)(v47 + 248) = *(_DWORD *)(v47 + 16);
  }
  return v20;
}

```

## disassembly

```asm
0x180008774  push    rbx
0x180008776  push    rbp
0x180008777  push    rsi
0x180008778  push    rdi
0x180008779  push    r12
0x18000877b  push    r13
0x18000877d  push    r14
0x18000877f  push    r15
0x180008781  sub     rsp, 48h
0x180008785  mov     r14, rcx
0x180008788  xor     r15d, r15d
0x18000878b  mov     ecx, 158h
0x180008790  mov     [rsp+88h+var_58], r15
0x180008795  mov     rsi, r9
0x180008798  mov     r13, r8
0x18000879b  mov     rdi, rdx
0x18000879e  call    cs:__imp_DllAllocSplMem
0x1800087a4  mov     rbx, rax
0x1800087a7  test    rax, rax
0x1800087aa  jnz     short loc_1800087C4
0x1800087ac  lea     rdx, aFailedToAlloca_24; "Failed to allocate SPOOL struct."
0x1800087b3  lea     rcx, aCreateprinterh_0; "CreatePrinterHandle"
0x1800087ba  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800087bf  jmp     loc_180008969
0x1800087c4  mov     ebp, [rsp+88h+arg_30]
0x1800087cb  mov     rcx, r14
0x1800087ce  mov     dword ptr [rax], 464Dh
0x1800087d4  mov     [rax+40h], r13
0x1800087d8  mov     rax, [rsp+88h+arg_68]
0x1800087e0  mov     [rbx+0D8h], rax
0x1800087e7  mov     rax, [rsp+88h+arg_20]
0x1800087ef  mov     [rbx+60h], rax
0x1800087f3  mov     rax, [rsp+88h+arg_28]
0x1800087fb  mov     [rbx+50h], rax
0x1800087ff  mov     rax, [rsp+88h+arg_38]
0x180008807  mov     [rbx+68h], rax
0x18000880b  mov     [rbx+48h], rsi
0x18000880f  mov     [rbx+58h], ebp
0x180008812  mov     [rbx+70h], r15d
0x180008816  mov     [rbx+38h], r15
0x18000881a  call    cs:__imp_AllocSplStr
0x180008820  mov     rcx, rdi
0x180008823  mov     [rbx+18h], rax
0x180008827  call    cs:__imp_AllocSplStr
0x18000882d  xor     r14d, r14d
0x180008830  mov     [rbx+20h], rax
0x180008834  mov     [rbx+108h], r14
0x18000883b  mov     [rbx+110h], r14
0x180008842  mov     [rbx+120h], r14
0x180008849  mov     [rbx+118h], r14d
0x180008850  mov     [rbx+138h], r14d
0x180008857  mov     [rbx+140h], r14
0x18000885e  cmp     [rbx+18h], r14
0x180008862  jz      loc_180008907
0x180008868  test    rdi, rdi
0x18000886b  jz      short loc_180008876
0x18000886d  test    rax, rax
0x180008870  jz      loc_180008907
0x180008876  mov     rdi, [rsp+88h+arg_48]
0x18000887e  lea     rcx, [rbx+11Ch]
0x180008885  mov     [rbx+0A8h], rdi
0x18000888c  call    GetClientSessionData
0x180008891  test    eax, eax
0x180008893  jz      short loc_180008907
0x180008895  mov     eax, cs:geCollectUsersInfo
0x18000889b  test    eax, eax
0x18000889d  jnz     short loc_1800088AD
0x18000889f  mov     r8, rdi
0x1800088a2  call    GetSplInitSettingFromReg
0x1800088a7  mov     eax, cs:geCollectUsersInfo
0x1800088ad  cmp     eax, 4
0x1800088b0  jnz     loc_18000897D
0x1800088b6  test    dword ptr [rdi+0A8h], 1000000h
0x1800088c0  jz      loc_18000897D
0x1800088c6  test    bpl, 11h
0x1800088ca  jz      loc_18000897D
0x1800088d0  mov     rcx, rbx; struct _SPOOL *
0x1800088d3  call    ?AttachUserInformation@@YAJPEAU_SPOOL@@@Z; AttachUserInformation(_SPOOL *)
0x1800088d8  mov     ecx, eax
0x1800088da  call    StatusFromHResult
0x1800088df  mov     esi, eax
0x1800088e1  test    eax, eax
0x1800088e3  jz      loc_18000897D
0x1800088e9  mov     r8d, eax
0x1800088ec  lea     rdx, aFailedToAttach; "Failed to attach user information to ha"...
0x1800088f3  lea     rcx, aCreateprinterh_0; "CreatePrinterHandle"
0x1800088fa  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800088ff  mov     ecx, esi; dwErrCode
0x180008901  call    cs:__imp_SetLastError
0x180008907  mov     rcx, [rbx+0F0h]
0x18000890e  call    cs:__imp_DllFreeSplStr
0x180008914  mov     rcx, [rbx+0E8h]
0x18000891b  call    cs:__imp_DllFreeSplStr
0x180008921  mov     rcx, [rbx+18h]
0x180008925  call    cs:__imp_DllFreeSplStr
0x18000892b  mov     rcx, [rbx+28h]
0x18000892f  call    cs:__imp_DllFreeSplStr
0x180008935  mov     rcx, [rbx+20h]
0x180008939  call    cs:__imp_DllFreeSplStr
0x18000893f  mov     rcx, [rbx+30h]
0x180008943  test    rcx, rcx
0x180008946  jz      short loc_180008951
0x180008948  add     rcx, 10h; unsigned int *
0x18000894c  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180008951  mov     rcx, [rbx+38h]
0x180008955  test    rcx, rcx
0x180008958  jz      short loc_180008960
0x18000895a  call    cs:__imp_DllFreeSplMem
0x180008960  mov     rcx, rbx
0x180008963  call    cs:__imp_DllFreeSplMem
0x180008969  mov     rax, r15
0x18000896c  add     rsp, 48h
0x180008970  pop     r15
0x180008972  pop     r14
0x180008974  pop     r13
0x180008976  pop     r12
0x180008978  pop     rdi
0x180008979  pop     rsi
0x18000897a  pop     rbp
0x18000897b  pop     rbx
0x18000897c  retn
0x18000897d  mov     r15d, ebp
0x180008980  and     r15d, 40h
0x180008984  jz      loc_180008A28
0x18000898a  mov     rsi, [rsp+88h+arg_58]
0x180008992  test    rsi, rsi
0x180008995  jnz     short loc_1800089A2
0x180008997  call    cs:__imp_IsNamedPipeRpcCall
0x18000899d  jmp     loc_180008A28
0x1800089a2  cmp     [rsp+88h+arg_60], 1
0x1800089aa  jz      short loc_1800089C3
0x1800089ac  cmp     [rsp+88h+arg_60], 3
0x1800089b4  jnz     short loc_180008A28
0x1800089b6  mov     eax, [rsi+4]
0x1800089b9  add     rsi, 8
0x1800089bd  mov     [rbx+118h], eax
0x1800089c3  movups  xmm0, xmmword ptr [rsi]
0x1800089c6  movups  xmmword ptr [rbx+0E0h], xmm0
0x1800089cd  movups  xmm1, xmmword ptr [rsi+10h]
0x1800089d1  movups  xmmword ptr [rbx+0F0h], xmm1
0x1800089d8  movsd   xmm0, qword ptr [rsi+20h]
0x1800089dd  movsd   qword ptr [rbx+100h], xmm0
0x1800089e5  mov     rcx, [rsi+10h]
0x1800089e9  call    cs:__imp_AllocSplStr
0x1800089ef  mov     [rbx+0F0h], rax
0x1800089f6  mov     rcx, [rsi+8]
0x1800089fa  call    cs:__imp_AllocSplStr
0x180008a00  mov     [rbx+0E8h], rax
0x180008a07  cmp     [rbx+0F0h], r14
0x180008a0e  jz      short loc_180008A15
0x180008a10  test    rax, rax
0x180008a13  jnz     short loc_180008A28
0x180008a15  lea     rdx, aCouldNotAlloca; "Could not allocate memory for user name"...
0x180008a1c  lea     rcx, aCreateprinterh_0; "CreatePrinterHandle"
0x180008a23  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180008a28  mov     r12d, ebp
0x180008a2b  and     r12d, 10h
0x180008a2f  jnz     short loc_180008A8D
0x180008a31  bt      ebp, 8
0x180008a35  jb      short loc_180008A8D
0x180008a37  mov     edx, [rsp+88h+arg_50]
0x180008a3e  lea     ecx, [r12+2]
0x180008a43  mov     [rsp+88h+var_60], 1
0x180008a4b  lea     rsi, [rbx+74h]
0x180008a4f  mov     [rsp+88h+var_68], rdi
0x180008a54  mov     r9, rsi
0x180008a57  test    cl, bpl
0x180008a5a  jz      short loc_180008A74
0x180008a5c  mov     r8, [rbx+50h]
0x180008a60  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x180008a65  mov     r14d, eax
0x180008a68  lea     rdx, GenericMapping
0x180008a6f  jmp     loc_180008AF6
0x180008a74  mov     r8, rbx
0x180008a77  mov     ecx, 1
0x180008a7c  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x180008a81  mov     r14d, eax
0x180008a84  lea     rdx, stru_18013DDE8
0x180008a8b  jmp     short loc_180008AF6
0x180008a8d  mov     edx, [rsp+88h+arg_50]
0x180008a94  lea     rsi, [rbx+74h]
0x180008a98  mov     r9, rsi
0x180008a9b  mov     [rsp+88h+var_60], 1
0x180008aa3  mov     r8, rbx
0x180008aa6  mov     [rsp+88h+var_68], rdi
0x180008aab  xor     ecx, ecx
0x180008aad  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x180008ab2  mov     r14d, eax
0x180008ab5  test    eax, eax
0x180008ab7  jz      short loc_180008AEF
0x180008ab9  test    r15d, r15d
0x180008abc  jz      short loc_180008AEF
0x180008abe  test    byte ptr [rsp+88h+arg_50], 1
0x180008ac6  jz      short loc_180008AEF
0x180008ac8  xor     r9d, r9d
0x180008acb  mov     [rsp+88h+var_60], 1
0x180008ad3  xor     r8d, r8d
0x180008ad6  mov     [rsp+88h+var_68], rdi
0x180008adb  xor     ecx, ecx
0x180008add  lea     edx, [r9+1]
0x180008ae1  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x180008ae6  test    eax, eax
0x180008ae8  jz      short loc_180008AEF
0x180008aea  bts     dword ptr [rbx+58h], 9
0x180008aef  lea     rdx, ?GenericMapping@@3PAU_GENERIC_MAPPING@@A; GenericMapping
0x180008af6  mov     rcx, rsi; AccessMask
0x180008af9  call    cs:__imp_MapGenericMask
0x180008aff  test    r14d, r14d
0x180008b02  jnz     short loc_180008B18
0x180008b04  lea     ecx, [r14+5]; dwErrCode
0x180008b08  call    cs:__imp_SetLastError
0x180008b0e  mov     r15, [rsp+88h+var_58]
0x180008b13  jmp     loc_180008907
0x180008b18  xor     r14d, r14d
0x180008b1b  test    r13, r13
0x180008b1e  jz      loc_180008C2A
0x180008b24  mov     rsi, [rsp+88h+arg_40]
0x180008b2c  test    rsi, rsi
0x180008b2f  jz      short loc_180008BA6
0x180008b31  mov     rax, [rsi+8]
0x180008b35  test    rax, rax
0x180008b38  jz      short loc_180008B86
0x180008b3a  movzx   ecx, word ptr [rax+46h]
0x180008b3e  movzx   eax, word ptr [rax+44h]
0x180008b42  add     ecx, eax
0x180008b44  call    cs:__imp_DllAllocSplMem
0x180008b4a  mov     [rbx+38h], rax
0x180008b4e  mov     rcx, rax; void *
0x180008b51  test    rax, rax
0x180008b54  jnz     short loc_180008B71
0x180008b56  lea     rdx, aFailedToAlloca_9; "Failed to allocate memory for devmode."
0x180008b5d  lea     rcx, aCreateprinterh_0; "CreatePrinterHandle"
0x180008b64  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180008b69  mov     r15, r14
0x180008b6c  jmp     loc_180008907
0x180008b71  mov     rdx, [rsi+8]; Src
0x180008b75  movzx   r8d, word ptr [rdx+46h]
0x180008b7a  movzx   eax, word ptr [rdx+44h]
0x180008b7e  add     r8, rax; Size
0x180008b81  call    memcpy_0
0x180008b86  mov     rcx, [rsi]
0x180008b89  test    rcx, rcx
0x180008b8c  jz      short loc_180008BB0
0x180008b8e  call    cs:__imp_AllocSplStr
0x180008b94  mov     [rbx+28h], rax
0x180008b98  mov     rdx, rax
0x180008b9b  mov     rcx, [r13+38h]
0x180008b9f  call    FindDatatype
0x180008ba4  jmp     short loc_180008BC2
0x180008ba6  mov     dword ptr [rbx+138h], 1
0x180008bb0  mov     rcx, [r13+40h]
0x180008bb4  call    cs:__imp_AllocSplStr
0x180008bba  mov     [rbx+28h], rax
0x180008bbe  mov     rax, [r13+38h]
0x180008bc2  mov     [rbx+30h], rax
0x180008bc6  cmp     [r13+38h], r14
0x180008bca  jz      short loc_180008C01
0x180008bcc  test    rax, rax
0x180008bcf  jnz     short loc_180008C06
0x180008bd1  call    cs:__imp_GetLastError
0x180008bd7  mov     r8, [rbx+28h]
0x180008bdb  lea     rdx, aFailedToFindPr; "Failed to find PrintProcessor for datat"...
0x180008be2  mov     r9d, eax
0x180008be5  lea     rcx, aCreateprinterh_0; "CreatePrinterHandle"
0x180008bec  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180008bf1  mov     ecx, 70Ch; dwErrCode
0x180008bf6  call    cs:__imp_SetLastError
0x180008bfc  jmp     loc_180008B69
0x180008c01  test    rax, rax
0x180008c04  jz      short loc_180008C0F
0x180008c06  lea     rcx, [rax+10h]; unsigned int *
0x180008c0a  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180008c0f  cmp     [rbx+28h], r14
0x180008c13  jnz     short loc_180008C2A
0x180008c15  lea     rdx, aFailedToAlloca_6; "Failed to allocate memory for datatype."
0x180008c1c  lea     rcx, aCreateprinterh_0; "CreatePrinterHandle"
0x180008c23  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180008c28  jmp     short loc_180008BF1
0x180008c2a  test    bpl, 1
0x180008c2e  jz      short loc_180008C48
0x180008c30  mov     rcx, [rbx+40h]
0x180008c34  mov     rax, [rcx+0C8h]
0x180008c3b  mov     [rbx+8], rax
0x180008c3f  mov     [rcx+0C8h], rbx
0x180008c46  jmp     short loc_180008C81
0x180008c48  test    r12d, r12d
0x180008c4b  jnz     short loc_180008C6C
0x180008c4d  bt      ebp, 8
0x180008c51  jb      short loc_180008C6C
0x180008c53  test    bpl, 6
0x180008c57  jz      short loc_180008C81
0x180008c59  mov     rax, [rsp+88h+arg_28]
0x180008c61  test    rax, rax
0x180008c64  jz      short loc_180008C81
0x180008c66  lea     rcx, [rax+18h]
0x180008c6a  jmp     short loc_180008C7C
0x180008c6c  mov     rax, [rdi+58h]
0x180008c70  lea     rcx, [rdi+10h]; unsigned int *
0x180008c74  mov     [rbx+8], rax
0x180008c78  mov     [rdi+58h], rbx
  ... truncated ...
```
