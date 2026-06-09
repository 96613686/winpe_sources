# ProcessSetPrinter2(_INIPRINTER *,_INIPRINTER *,_INIPRINTER *,ulong *,_devicemodeW *)

- ea: `0x18005939c`
- end: `0x1800596a3`
- name: `?ProcessSetPrinter2@@YAXPEAU_INIPRINTER@@00PEAKPEAU_devicemodeW@@@Z`
- size: `775`
- prototype: `void __fastcall(struct _INIPRINTER *, struct _INIPRINTER *, struct _INIPRINTER *, unsigned int *, struct _devicemodeW *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180057b58`

## callees

- `0x180005d90`
- `0x180008730`
- `0x18000e890`
- `0x180013b00`
- `0x1800318ec`
- `0x18005939c`
- `0x1800596ac`
- `0x1800737b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800594b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800594b2`
- `SPOOLSS!DllFreeSplStr` at `0x1800593de`
- `SPOOLSS!DllFreeSplStr` at `0x1800594eb`
- `SPOOLSS!DllFreeSplStr` at `0x18005951b`
- `SPOOLSS!DllFreeSplStr` at `0x180059572`
- `SPOOLSS!DllFreeSplStr` at `0x1800595e4`
- `SPOOLSS!DllFreeSplStr` at `0x180059618`
- `SPOOLSS!DllFreeSplStr` at `0x1800593de`
- `SPOOLSS!DllFreeSplStr` at `0x1800594eb`
- `SPOOLSS!DllFreeSplStr` at `0x18005951b`
- `SPOOLSS!DllFreeSplStr` at `0x180059572`
- `SPOOLSS!DllFreeSplStr` at `0x1800595e4`
- `SPOOLSS!DllFreeSplStr` at `0x180059618`
- `SPOOLSS!RevertToPrinterSelf` at `0x180059434`
- `SPOOLSS!RevertToPrinterSelf` at `0x180059434`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800594c0`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800594c0`

## pseudocode

```c
void __fastcall ProcessSetPrinter2(
        struct _INIPRINTER *a1,
        struct _INIPRINTER *a2,
        struct _INIPRINTER *a3,
        unsigned int *a4,
        struct _devicemodeW *a5)
{
  struct _INISPOOLER *v5; // r14
  __int64 v7; // rcx
  _DWORD *v11; // rbp
  __int64 v12; // rcx
  __int16 v13; // ax
  __int64 v14; // rax
  HANDLE v15; // rbp
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  _DWORD *v22; // r14
  __int64 v23; // rax
  _DWORD *v24; // rbp
  __int64 v25; // rax
  int v26; // eax
  _DWORD *v27; // rax
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  if ( a4 )
  {
    v5 = (struct _INISPOOLER *)*((_QWORD *)a1 + 35);
    v7 = *((_QWORD *)a1 + 5);
    hKey = 0;
    v11 = (_DWORD *)((char *)a1 + 400);
    if ( *((_QWORD *)a3 + 5) != v7 )
    {
      DllFreeSplStr(v7);
      v12 = *((_QWORD *)a3 + 5);
      *((_QWORD *)a1 + 5) = v12;
      v13 = HashName(v12);
      *a4 |= 4u;
      *((_WORD *)a1 + 24) = v13;
      *v11 &= ~2u;
    }
    v14 = *((_QWORD *)a1 + 11);
    if ( *((_QWORD *)a3 + 11) != v14 )
    {
      if ( v14 && *(_DWORD *)(v14 + 16) )
        SafeDecrementReference((unsigned int *)(v14 + 16));
      if ( (*(_DWORD *)(*((_QWORD *)a1 + 35) + 168LL) & 0x200) != 0 )
      {
        v15 = RevertToPrinterSelf();
        if ( !(unsigned int)OpenPrinterKey((__int64)a1, 0x2001Fu, &hKey, L"PrinterDriverData", 1) )
        {
          DeleteSubkeys(hKey, v5);
          RegClearKey(hKey, v5);
          if ( *((_DWORD *)a1 + 132) )
            SplRegSetValue(hKey, L"EnableBranchOfficePrinting", 4u, (BYTE *)a1 + 528, 4u, v5);
          RegCloseKey(hKey);
        }
        if ( v15 )
          ImpersonatePrinterClient(v15);
      }
      v16 = *((_QWORD *)a3 + 11);
      v11 = (_DWORD *)((char *)a1 + 400);
      *a4 |= 0x10u;
      *((_QWORD *)a1 + 11) = v16;
      *((_DWORD *)a1 + 100) &= ~0x1000u;
    }
    if ( *((_QWORD *)a3 + 10) != *((_QWORD *)a2 + 10) )
    {
      DllFreeSplStr(*((_QWORD *)a1 + 10));
      v17 = *((_QWORD *)a3 + 10);
      *a4 |= 0x20u;
      *((_QWORD *)a1 + 10) = v17;
      *((_QWORD *)a2 + 10) = v17;
      *v11 &= ~0x20u;
    }
    if ( *((_QWORD *)a3 + 18) != *((_QWORD *)a2 + 18) )
    {
      DllFreeSplStr(*((_QWORD *)a1 + 18));
      v18 = *((_QWORD *)a3 + 18);
      *a4 |= 0x40u;
      *((_QWORD *)a1 + 18) = v18;
      *((_QWORD *)a2 + 18) = v18;
      *v11 &= ~0x80u;
    }
    if ( !(unsigned int)CopyPrinterDevModeToIniPrinter(a1, a5) )
    {
      *a4 |= 0x80u;
      *v11 &= ~0x200u;
    }
    if ( *((_QWORD *)a3 + 16) != *((_QWORD *)a2 + 16) )
    {
      DllFreeSplStr(*((_QWORD *)a1 + 16));
      v19 = *((_QWORD *)a3 + 16);
      *a4 |= 0x100u;
      *((_QWORD *)a1 + 16) = v19;
      *((_QWORD *)a2 + 16) = v19;
      *v11 &= ~0x40u;
    }
    if ( *((_QWORD *)a2 + 7) == *((_QWORD *)a3 + 7) )
    {
      v22 = (_DWORD *)((char *)a1 + 400);
    }
    else
    {
      v20 = *((_QWORD *)a1 + 7);
      if ( v20 )
        SafeDecrementReference((unsigned int *)(v20 + 16));
      v21 = *((_QWORD *)a3 + 7);
      v22 = (_DWORD *)((char *)a1 + 400);
      *a4 |= 0x200u;
      *((_QWORD *)a1 + 7) = v21;
      *((_QWORD *)a2 + 7) = v21;
      *((_DWORD *)a1 + 100) &= ~0x800u;
    }
    if ( *((_QWORD *)a2 + 8) == *((_QWORD *)a3 + 8) )
    {
      v24 = v22;
    }
    else
    {
      DllFreeSplStr(*((_QWORD *)a1 + 8));
      v23 = *((_QWORD *)a3 + 8);
      v24 = (_DWORD *)((char *)a1 + 400);
      *a4 |= 0x800u;
      *((_QWORD *)a1 + 8) = v23;
      *((_QWORD *)a2 + 8) = v23;
      *v22 &= ~4u;
    }
    if ( *((_QWORD *)a2 + 9) == *((_QWORD *)a3 + 9) )
    {
      v24 = v22;
    }
    else
    {
      DllFreeSplStr(*((_QWORD *)a1 + 9));
      v25 = *((_QWORD *)a3 + 9);
      *a4 |= 0x400u;
      *((_QWORD *)a1 + 9) = v25;
      *((_QWORD *)a2 + 9) = v25;
      *v22 &= ~8u;
    }
    v26 = *((_DWORD *)a3 + 28);
    if ( v26 == *((_DWORD *)a1 + 28) )
    {
      v27 = v24;
    }
    else
    {
      *a4 |= 0x4000u;
      *((_DWORD *)a1 + 28) = v26;
      v27 = (_DWORD *)((char *)a1 + 400);
      *v24 &= ~0x40000000u;
    }
    v28 = *((_DWORD *)a3 + 29);
    if ( v28 == *((_DWORD *)a1 + 29) )
    {
      v27 = v24;
    }
    else
    {
      *a4 |= 0x8000u;
      *((_DWORD *)a1 + 29) = v28;
      *v24 &= ~0x80000000;
    }
    v29 = *((_DWORD *)a3 + 30);
    if ( v29 != *((_DWORD *)a1 + 30) )
    {
      *a4 |= 0x10000u;
      *((_DWORD *)a1 + 30) = v29;
      *v27 &= ~0x8000000u;
    }
    v30 = *((_DWORD *)a3 + 31);
    if ( v30 != *((_DWORD *)a1 + 31) )
    {
      *a4 |= 0x20000u;
      *((_DWORD *)a1 + 31) = v30;
      *v27 &= ~0x2000000u;
    }
  }
}

```

## disassembly

```asm
0x18005939c  test    r9, r9
0x18005939f  jz      locret_1800596A2
0x1800593a5  push    rbx
0x1800593a6  push    rbp
0x1800593a7  push    rsi
0x1800593a8  push    rdi
0x1800593a9  push    r14
0x1800593ab  push    r15
0x1800593ad  sub     rsp, 38h
0x1800593b1  mov     r14, [rcx+118h]
0x1800593b8  mov     rbx, rcx
0x1800593bb  mov     rcx, [rcx+28h]
0x1800593bf  mov     rdi, r9
0x1800593c2  mov     rsi, r8
0x1800593c5  mov     r15, rdx
0x1800593c8  mov     [rsp+68h+hKey], 0
0x1800593d1  lea     rbp, [rbx+190h]
0x1800593d8  cmp     [r8+28h], rcx
0x1800593dc  jz      short loc_1800593FC
0x1800593de  call    cs:__imp_DllFreeSplStr
0x1800593e4  mov     rcx, [rsi+28h]
0x1800593e8  mov     [rbx+28h], rcx
0x1800593ec  call    HashName
0x1800593f1  or      dword ptr [rdi], 4
0x1800593f4  mov     [rbx+30h], ax
0x1800593f8  and     dword ptr [rbp+0], 0FFFFFFFDh
0x1800593fc  mov     rax, [rbx+58h]
0x180059400  cmp     [rsi+58h], rax
0x180059404  jz      loc_1800594DD
0x18005940a  test    rax, rax
0x18005940d  jz      short loc_18005941D
0x18005940f  lea     rcx, [rax+10h]; unsigned int *
0x180059413  cmp     dword ptr [rcx], 0
0x180059416  jz      short loc_18005941D
0x180059418  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x18005941d  mov     rax, [rbx+118h]
0x180059424  test    dword ptr [rax+0A8h], 200h
0x18005942e  jz      loc_1800594C6
0x180059434  call    cs:__imp_RevertToPrinterSelf
0x18005943a  lea     r9, szPrinterData; "PrinterDriverData"
0x180059441  mov     [rsp+68h+var_48], 1
0x180059449  lea     r8, [rsp+68h+hKey]
0x18005944e  mov     edx, 2001Fh
0x180059453  mov     rcx, rbx
0x180059456  mov     rbp, rax
0x180059459  call    OpenPrinterKey
0x18005945e  test    eax, eax
0x180059460  jnz     short loc_1800594B8
0x180059462  mov     rcx, [rsp+68h+hKey]; void *
0x180059467  mov     rdx, r14; struct _INISPOOLER *
0x18005946a  call    DeleteSubkeys
0x18005946f  mov     rcx, [rsp+68h+hKey]; void *
0x180059474  mov     rdx, r14; struct _INISPOOLER *
0x180059477  call    ?RegClearKey@@YAXPEAXPEAU_INISPOOLER@@@Z; RegClearKey(void *,_INISPOOLER *)
0x18005947c  lea     r9, [rbx+210h]; unsigned __int8 *
0x180059483  cmp     dword ptr [r9], 0
0x180059487  jz      short loc_1800594AD
0x180059489  mov     rcx, [rsp+68h+hKey]; void *
0x18005948e  lea     rdx, szBranchOfficePrintingEnabled; "EnableBranchOfficePrinting"
0x180059495  mov     [rsp+68h+var_40], r14; struct _INISPOOLER *
0x18005949a  mov     r8d, 4; unsigned int
0x1800594a0  mov     [rsp+68h+var_48], 4; unsigned int
0x1800594a8  call    ?SplRegSetValue@@YAJPEAXPEBGKPEBEKPEAU_INISPOOLER@@@Z; SplRegSetValue(void *,ushort const *,ulong,uchar const *,ulong,_INISPOOLER *)
0x1800594ad  mov     rcx, [rsp+68h+hKey]; hKey
0x1800594b2  call    cs:__imp_RegCloseKey
0x1800594b8  test    rbp, rbp
0x1800594bb  jz      short loc_1800594C6
0x1800594bd  mov     rcx, rbp; hToken
0x1800594c0  call    cs:__imp_ImpersonatePrinterClient
0x1800594c6  mov     rax, [rsi+58h]
0x1800594ca  lea     rbp, [rbx+190h]
0x1800594d1  or      dword ptr [rdi], 10h
0x1800594d4  mov     [rbx+58h], rax
0x1800594d8  btr     dword ptr [rbp+0], 0Ch
0x1800594dd  mov     rax, [r15+50h]
0x1800594e1  cmp     [rsi+50h], rax
0x1800594e5  jz      short loc_180059504
0x1800594e7  mov     rcx, [rbx+50h]
0x1800594eb  call    cs:__imp_DllFreeSplStr
0x1800594f1  mov     rax, [rsi+50h]
0x1800594f5  or      dword ptr [rdi], 20h
0x1800594f8  mov     [rbx+50h], rax
0x1800594fc  mov     [r15+50h], rax
0x180059500  and     dword ptr [rbp+0], 0FFFFFFDFh
0x180059504  mov     rax, [r15+90h]
0x18005950b  cmp     [rsi+90h], rax
0x180059512  jz      short loc_18005953E
0x180059514  mov     rcx, [rbx+90h]
0x18005951b  call    cs:__imp_DllFreeSplStr
0x180059521  mov     rax, [rsi+90h]
0x180059528  or      dword ptr [rdi], 40h
0x18005952b  mov     [rbx+90h], rax
0x180059532  mov     [r15+90h], rax
0x180059539  btr     dword ptr [rbp+0], 7
0x18005953e  mov     rdx, [rsp+68h+arg_20]
0x180059546  mov     rcx, rbx
0x180059549  call    CopyPrinterDevModeToIniPrinter
0x18005954e  test    eax, eax
0x180059550  jnz     short loc_18005955B
0x180059552  bts     dword ptr [rdi], 7
0x180059556  btr     dword ptr [rbp+0], 9
0x18005955b  mov     rax, [r15+80h]
0x180059562  cmp     [rsi+80h], rax
0x180059569  jz      short loc_180059595
0x18005956b  mov     rcx, [rbx+80h]
0x180059572  call    cs:__imp_DllFreeSplStr
0x180059578  mov     rax, [rsi+80h]
0x18005957f  bts     dword ptr [rdi], 8
0x180059583  mov     [rbx+80h], rax
0x18005958a  mov     [r15+80h], rax
0x180059591  and     dword ptr [rbp+0], 0FFFFFFBFh
0x180059595  mov     rax, [rsi+38h]
0x180059599  cmp     [r15+38h], rax
0x18005959d  jz      short loc_1800595CF
0x18005959f  mov     rcx, [rbx+38h]
0x1800595a3  test    rcx, rcx
0x1800595a6  jz      short loc_1800595B1
0x1800595a8  add     rcx, 10h; unsigned int *
0x1800595ac  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800595b1  mov     rax, [rsi+38h]
0x1800595b5  lea     r14, [rbx+190h]
0x1800595bc  bts     dword ptr [rdi], 9
0x1800595c0  mov     [rbx+38h], rax
0x1800595c4  mov     [r15+38h], rax
0x1800595c8  btr     dword ptr [r14], 0Bh
0x1800595cd  jmp     short loc_1800595D6
0x1800595cf  lea     r14, [rbx+190h]
0x1800595d6  mov     rax, [rsi+40h]
0x1800595da  cmp     [r15+40h], rax
0x1800595de  jz      short loc_180059607
0x1800595e0  mov     rcx, [rbx+40h]
0x1800595e4  call    cs:__imp_DllFreeSplStr
0x1800595ea  mov     rax, [rsi+40h]
0x1800595ee  lea     rbp, [rbx+190h]
0x1800595f5  bts     dword ptr [rdi], 0Bh
0x1800595f9  mov     [rbx+40h], rax
0x1800595fd  mov     [r15+40h], rax
0x180059601  and     dword ptr [r14], 0FFFFFFFBh
0x180059605  jmp     short loc_18005960A
0x180059607  mov     rbp, r14
0x18005960a  mov     rax, [rsi+48h]
0x18005960e  cmp     [r15+48h], rax
0x180059612  jz      short loc_180059634
0x180059614  mov     rcx, [rbx+48h]
0x180059618  call    cs:__imp_DllFreeSplStr
0x18005961e  mov     rax, [rsi+48h]
0x180059622  bts     dword ptr [rdi], 0Ah
0x180059626  mov     [rbx+48h], rax
0x18005962a  mov     [r15+48h], rax
0x18005962e  and     dword ptr [r14], 0FFFFFFF7h
0x180059632  jmp     short loc_180059637
0x180059634  mov     rbp, r14
0x180059637  mov     eax, [rsi+70h]
0x18005963a  cmp     eax, [rbx+70h]
0x18005963d  jz      short loc_180059654
0x18005963f  bts     dword ptr [rdi], 0Eh
0x180059643  mov     [rbx+70h], eax
0x180059646  lea     rax, [rbx+190h]
0x18005964d  btr     dword ptr [rbp+0], 1Eh
0x180059652  jmp     short loc_180059657
0x180059654  mov     rax, rbp
0x180059657  mov     ecx, [rsi+74h]
0x18005965a  cmp     ecx, [rbx+74h]
0x18005965d  jz      short loc_18005966D
0x18005965f  bts     dword ptr [rdi], 0Fh
0x180059663  mov     [rbx+74h], ecx
0x180059666  btr     dword ptr [rbp+0], 1Fh
0x18005966b  jmp     short loc_180059670
0x18005966d  mov     rax, rbp
0x180059670  mov     ecx, [rsi+78h]
0x180059673  cmp     ecx, [rbx+78h]
0x180059676  jz      short loc_180059683
0x180059678  bts     dword ptr [rdi], 10h
0x18005967c  mov     [rbx+78h], ecx
0x18005967f  btr     dword ptr [rax], 1Bh
0x180059683  mov     ecx, [rsi+7Ch]
0x180059686  cmp     ecx, [rbx+7Ch]
0x180059689  jz      short loc_180059696
0x18005968b  bts     dword ptr [rdi], 11h
0x18005968f  mov     [rbx+7Ch], ecx
0x180059692  btr     dword ptr [rax], 19h
0x180059696  add     rsp, 38h
0x18005969a  pop     r15
0x18005969c  pop     r14
0x18005969e  pop     rdi
0x18005969f  pop     rsi
0x1800596a0  pop     rbp
0x1800596a1  pop     rbx
0x1800596a2  retn
```
